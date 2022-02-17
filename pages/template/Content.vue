<template>
	<div class="container-fluid h-100">
		<ContentsNavs />
		<div class="row h-100">
			<div class="col-4 border-right">
				<b-tabs v-show="!activeContentSetting" fill>
					<b-tab title="Metadata">
						<b-form class="mt-3">
							<div class="form-group">
								<label for="campaignName">Campaign Name</label>
								<input type="text"
									v-model="campaignName"
									class="form-control custom-input"
									id="campaignName"
									placeholder="Enter your campaign name"
								/>
							</div>
							<div class="form-group">
								<label for="subject">Subject</label>
								<input type="text"
									v-model="subject"
									class="form-control custom-input" 
									id="subject"
									placeholder="Enter your subject"
								/>
							</div>
							<div class="form-group">
								<label for="preview">Preview</label>
								<input type="text"
									v-model="preview"
									class="form-control custom-input" 
									id="preview"
									placeholder="Enter your preview text"
								/>
							</div>
							<div class="form-group">
								<label for="from">From</label>
								<input type="text" 
									class="form-control custom-input" 
									id="from"
									placeholder="Select Sender"
								/>
							</div>
						</b-form>
					</b-tab>
					<b-tab title="Build">
						<h5 class="mt-3">
							<span class=""> > </span> ADD A BLOCK
						</h5>
						<div class="container">
							<div class="row">
								<div class="col">
									<drag class="drag"
										:transfer-data="{ type: 'image', group: 'block' }"
										@dragstart="dragStart"
										@dragend="dragEnd"
									>
										<div class="border block-wrapper text-center m-auto">
											<b-icon
												icon="images"
												class="d-block m-auto"
												font-scale="1.5"
											></b-icon>
											Image
										</div>
									</drag>
								</div>
								<div class="col">
									<drag class="drag"
										:transfer-data="{ type: 'text', group: 'block' }"
										@dragstart="dragStart"
										@dragend="dragEnd"
									>
										<div class="border block-wrapper text-center m-auto">
											<b-icon
												icon="card-text"
												class="d-block m-auto"
												font-scale="1.5"
											></b-icon>
											Text
										</div>
									</drag>
								</div>
								<div class="col">
									<drag class="drag"
										:transfer-data="{ type: 'button', group: 'block' }"
										@dragstart="dragStart"
										@dragend="dragEnd"
									>
										<div class="border block-wrapper text-center m-auto">
											<b-iconstack class="d-block m-auto">
												<b-icon
													stacked
													shift-v="-6"
													icon="hand-index"
													font-scale="0.75"
												></b-icon>
												<b-icon
													stacked
													icon="square"
												></b-icon>
											</b-iconstack>
											Button
										</div>
									</drag>
								</div>
							</div>
							<div class="row mt-3">
								<div class="col">
									<drag class="drag"
										:transfer-data="{ type: 'divider', group: 'block' }"
										@dragstart="dragStart"
										@dragend="dragEnd"
									>
										<div class="border block-wrapper text-center m-auto">
											<b-icon
												icon="hr"
												class="d-block m-auto"
												font-scale="1.5"
											></b-icon>
											Divider
										</div>
									</drag>
								</div>
								<div class="col">
									<drag class="drag"
										:transfer-data="{ type: 'spacer', group: 'block' }"
										@dragstart="dragStart"
										@dragend="dragEnd"
									>
										<div class="border block-wrapper text-center m-auto">
											<b-icon
												icon="distribute-vertical"
												class="d-block m-auto"
												font-scale="1.5"
											></b-icon>
											Spacer
										</div>
									</drag>
								</div>
								<div class="col">
									<drag class="drag"
										:transfer-data="{ type: 'social', group: 'block' }"
										@dragstart="dragStart"
										@dragend="dragEnd"
									>
										<div class="border block-wrapper text-center m-auto">
											<b-icon
												icon="share"
												class="d-block m-auto"
												font-scale="1.5"
											></b-icon>
											Social
										</div>
									</drag>
								</div>
							</div>
							<div class="row mt-3">
								<div class="col">
									<drag class="drag" :transfer-data="{ type: 'unsubscribe', group: 'block' }">
										<div class="border block-wrapper text-center m-auto">
											<b-iconstack 
												class="d-block m-auto"
												font-scale="1.25"
											>
												<b-icon
													stacked
													shift-v="-6"
													shift-h="6"
													icon="x-circle-fill"
												></b-icon>
												<b-icon
													font-scale="2"
													stacked
													icon="envelope"
												></b-icon>		
											</b-iconstack>
											Unsubscribe
										</div>
									</drag>
								</div>
								<div class="col" />
								<div class="col" />
							</div>
						</div>
						<h5 class="mt-3">
							<span class=""> > </span> ADD A SECTION
						</h5>
						<div class="container">
							<div class="row">
								<div class="col">
									<drag class="drag"
										:transfer-data="{ 
											type: 'section5050',
											group: 'section',
											subsections: {
												left: null,
												right: null,
											}
										}"
										@dragstart="dragStart"
										@dragend="dragEnd"
									>
										<div class="border block-wrapper text-center m-auto">
											<b-iconstack class="d-block m-auto">
												<b-icon
													icon="square"
												></b-icon>
												<b-icon
													stacked
													icon="dash"
													rotate="90"
												></b-icon>
											</b-iconstack>
											2 Columns
											(50-50)
										</div>
									</drag>
								</div>
								<div class="col">
									<drag class="drag"
										:transfer-data="{ 
											type: 'section2080',
											group: 'section',
											subsections: {
												left: null,
												right: null,
											}
										}"
										@dragstart="dragStart"
										@dragend="dragEnd"
									>
										<div class="border block-wrapper text-center m-auto">
											<b-iconstack class="d-block m-auto">
												<b-icon
													icon="square"
												></b-icon>
												<b-icon
													stacked
													shift-h="-2"
													icon="dash"
													rotate="90"
												></b-icon>
											</b-iconstack>
											2 Columns
											(20-80)
										</div>
									</drag>
								</div>
								<div class="col" />
							</div>
						</div>
					</b-tab>
					<b-tab title="Test">
						<form class="mt-3">
							<div class="form-group">
								<label for="sendATestEmail">Send a Test Email</label>
								<input type="text" 
									class="form-control custom-input" 
									id="sendATestEmail"
									placeholder="Enter up to 10 Email Addresses"
								/>
							</div>
							<button @click.prevent="" class="btn btn-secondary">Send a Test Message</button>
						</form>
					</b-tab>
				</b-tabs>
				<b-tabs v-show="activeContentSetting" fill>
					<b-tab>
						<template #title>
							<div class="d-flex justify-content-between">
								<span>Settings</span>
								<b-icon
									icon="arrow-left-circle"
									@click.stop="closeSettings"
								></b-icon>
							</div>
						</template>
						<component class="mt-5" :is="typeToSettings[activeContentSetting]" />
					</b-tab>
				</b-tabs>
			</div>
			<div class="col-8">
				<div class="mx-auto w-75 h-100 d-block" :class="{ 'dropzone': isDragging }">
					<drop class="drop h-100" @drop="handleDrop">
						<draggable
							:list="items"
							handle=".handle"
						>
							<template v-for="(item, index) in items">
								<component
									class="mb-3"
									:is="typeToComponents[item.type]"
									:key="index + '-' + item.type"
									:draghandle="true"
									@remove-content="removeContent(index)"
									@open-settings="openSettings(index)"
								>
									<template v-if="item.group === 'section'" v-slot:left>
										<component
											v-if="item.subsections.left"
											:class="{
												'w-50': item.type === 'section5050',
												'w-25': item.type === 'section2080'
											}"
											:draghandle="false"
											:is="typeToComponents[item.subsections.left.type]"
											@remove-content="removeLeftContent(index)"
										/>
										<drop
											v-else
											class="drop py-3 border rounded d-flex align-items-center justify-content-center"
											:class="{
												'w-50': item.type === 'section5050',
												'w-25': item.type === 'section2080'
											}"
											@drop="handleLeftDrop(index, ...arguments)"
										>
											<div>
											<b-icon
												icon="plus-circle"
											></b-icon>
											Add Section
											</div>
										</drop>
									</template>
									<template v-if="item.group === 'section'" v-slot:right>
										<component
											v-if="item.subsections.right"
											:class="{
												'w-50': item.type === 'section5050',
												'w-75': item.type === 'section2080'
											}"
											:draghandle="false"
											:is="typeToComponents[item.subsections.right.type]"
											@remove-content="removeRightContent(index)"
										/>
										<drop
											v-else
											class="drop py-3 border rounded d-flex align-items-center justify-content-center"
											:class="{
												'w-50': item.type === 'section5050',
												'w-75': item.type === 'section2080'
											}"
											@drop="handleRightDrop(index, ...arguments)"
										>
											<b-icon
												icon="plus-circle"
											></b-icon>
											Add Section
										</drop>
									</template>
								</component>
							</template>
						</draggable>
					</drop>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import { Drag, Drop } from 'vue-drag-drop';
import draggable from "vuedraggable";

export default {
	components: {
		Drag,
		Drop,
		draggable,
	},
	data() {
		return {
			campaignName: '',
			subject: '',
			preview: '',
			items: [],
			typeToComponents: {
				'image': 'ContentsSubsImage',
				'text': 'ContentsSubsText',
				'button': 'ContentsSubsButton',
				'divider': 'ContentsSubsDivider',
				'spacer': 'ContentsSubsSpacer',
				'social': 'ContentsSubsSocial',
				'section5050': 'ContentsSubsSection',
				'section2080': 'ContentsSubsSection',
			},
			typeToSettings: {
				'text': 'ContentsSettingsText',
				'spacer': 'ContentsSettingsSpacer',
				'divider': 'ContentsSettingsDivider',
			},
			isDragging: false,
			activeContentSetting: '',
		}
	},
	methods: {
		handleDrop(data) {
			if (data) {
				this.items.push(data);
			}
		},
		handleLeftDrop(index, data, event) {
			event.stopPropagation();
			if (data.group === 'block') {
				this.items[index].subsections.left = data;
			}
		},
		handleRightDrop(index, data, event) {
			event.stopPropagation();
			if (data.group === 'block') {
				this.items[index].subsections.right = data;
			}
		},
		dragStart() {
			this.isDragging = true;
		},
		dragEnd() {
			this.isDragging = false;
		},
		removeContent(index) {
			this.items.splice(index, 1);
		},
		removeLeftContent(index) {
			this.items[index].subsections.left = null;
		},
		removeRightContent(index) {
			this.items[index].subsections.right = null;
		},
		openSettings(index) {
			this.activeContentSetting = this.items[index].type;
		},
		closeSettings() {
			this.activeContentSetting = '';
		}
	}
	
}
</script>
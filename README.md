# MeetingTranscriptSummarizer
This repository contains the Power Platform Solution for the Meeting Transcript Summarizer Flow.

---

## 🔧 Deployment Instructions
After importing the Solution into your target Power Platform environment, please configure the following **Environment Variables** and **Connection References**.

0.You will need a Azure Subscription and a new or an existing resource group to include the fowllowing 2 services before the solution can really spin up

1.Azure Blog Storage
2.Azure Speech Service
An Azure Speech resource in one of the regions where the fast transcription API is available. For the current list of supported regions, see the Speech service regions table list here https://learn.microsoft.com/en-us/azure/ai-services/speech-service/regions?tabs=stt

An audio file (less than 5 hours long and less than 500 MB in size) in one of the formats and codecs supported by the batch transcription API: WAV, MP3, OPUS/OGG, FLAC, WMA, AAC, ALAW in WAV container, MULAW in WAV container, AMR, WebM, and SPEEX. For more information about supported audio formats, see supported audio formats.

---

### 📌 Environment Variables

| Name | Description | Example |
|------|-------------|---------|
| SPOSiteURL-UploadFile | SharePoint Site URL | https://<your-tenant>.sharepoint.com/sites/<site> |
| SPOLibraryName-UploadFile | SharePoint Document Library Name | MeetingVoice |
| SpeechServiceAPIKEY | Azure Speech Service API Key | **Set during import** |
| HTTP-FastTranscriptionAPI-EndPoint | Azure Speech API Endpoint | https://<region>.api.cognitive.microsoft.com/speechtotext/transcriptions:transcribe?api-version=2024-11-15 |
| ContainerFolderNameInBlob | Azure Blob Container Name | audiocontainer |

---

### 🔗 Connection References

During Solution import, you will be prompted to assign the following Connection References:

| Connection Reference | Required Connector |
|----------------------|--------------------|
| MeetingSummarizer-BlobStorageAccount | Azure Blob Storage |
| MeetingSummarizer-Dataverse For Prompt | Microsoft Dataverse |

Please ensure these connections are mapped to your environment-specific resources.

---

## 🚀 Solution Import

1. Import the unmanaged solution into your environment.
2. Assign the required Connection References.
3. Set the Environment Variable values.
4. Turn on the Flow after import.

---

# NetTraceMarkContextActivityStart(void *,uint)

- ea: `0x18001000c`
- end: `0x18001016b`
- name: `?NetTraceMarkContextActivityStart@@YAXPEAXI@Z`
- size: `351`
- prototype: `void(void *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f91c`
- `0x18000fce8`

## callees

- `0x18000f830`
- `0x18001000c`
- `0x180012db0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18001012b`
- `ADVAPI32!EventWriteTransfer` at `0x18001012b`
- `ADVAPI32!EventActivityIdControl` at `0x18001005b`
- `ADVAPI32!EventActivityIdControl` at `0x18001013d`
- `ADVAPI32!EventActivityIdControl` at `0x18001005b`
- `ADVAPI32!EventActivityIdControl` at `0x18001013d`

## pseudocode

```c
void __fastcall NetTraceMarkContextActivityStart(void *a1, unsigned int a2)
{
  const struct _GUID *v4; // r9
  unsigned int v5; // [rsp+30h] [rbp-9h] BYREF
  GUID RelatedActivityId; // [rsp+38h] [rbp-1h] BYREF
  GUID ActivityId; // [rsp+48h] [rbp+Fh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp+1Fh] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp+2Fh] BYREF
  unsigned int *v10; // [rsp+78h] [rbp+3Fh]
  __int64 v11; // [rsp+80h] [rbp+47h]

  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    ActivityId = 0;
    EventActivityIdControl(1u, &ActivityId);
    *(_QWORD *)RelatedActivityId.Data4 = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&RelatedActivityId.Data1 = a1;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfo(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStart, &RelatedActivityId, v4, a2);
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
      v5 = a2;
      EventDescriptor.Keyword = 0x8000000000000001uLL;
      if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
      {
        *(_QWORD *)&UserData.Size = 16;
        UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
        v10 = &v5;
        v11 = 4;
        EventWriteTransfer(
          Microsoft_Windows_Networking_CorrelationHandle,
          &EventDescriptor,
          &ActivityId,
          &RelatedActivityId,
          2u,
          &UserData);
      }
      else
      {
        EventWriteTransfer(
          Microsoft_Windows_Networking_CorrelationHandle,
          &EventDescriptor,
          &ActivityId,
          &RelatedActivityId,
          0,
          0);
      }
    }
    EventActivityIdControl(2u, &ActivityId);
  }
}

```

## disassembly

```asm
0x18001000c  mov     [rsp-8+arg_8], rbx
0x180010011  mov     [rsp-8+arg_10], rdi
0x180010016  push    rbp
0x180010017  lea     rbp, [rsp-57h]
0x18001001c  sub     rsp, 90h
0x180010023  mov     rax, cs:__security_cookie
0x18001002a  xor     rax, rsp
0x18001002d  mov     [rbp+57h+var_8], rax
0x180010031  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180010037  mov     ebx, edx
0x180010039  mov     rdi, rcx
0x18001003c  test    eax, eax
0x18001003e  jz      loc_180010149
0x180010044  xorps   xmm0, xmm0
0x180010047  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18001004b  xorps   xmm1, xmm1
0x18001004e  mov     ecx, 1; ControlCode
0x180010053  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180010057  movups  xmmword ptr [rbp+57h+RelatedActivityId.Data1], xmm1
0x18001005b  call    cs:__imp_EventActivityIdControl
0x180010062  nop     dword ptr [rax+rax+00h]
0x180010067  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x18001006e  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180010074  movdqu  xmmword ptr [rbp+57h+RelatedActivityId.Data1], xmm0
0x180010079  mov     qword ptr [rbp+57h+RelatedActivityId.Data1], rdi
0x18001007d  test    eax, eax
0x18001007f  jz      short loc_18001009C
0x180010081  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x180010088  lea     r8, [rbp+57h+RelatedActivityId]; struct _GUID *
0x18001008c  lea     rdx, ActivityStart; EventDescriptor
0x180010093  mov     [rsp+90h+UserDataCount], ebx; unsigned int
0x180010097  call    ?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z; EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)
0x18001009c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800100a2  mov     edi, 2
0x1800100a7  test    eax, eax
0x1800100a9  jz      loc_180010137
0x1800100af  mov     rax, cs:ActivityTransfer
0x1800100b6  lea     r9, [rbp+57h+RelatedActivityId]; RelatedActivityId
0x1800100ba  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x1800100c1  lea     r8, [rbp+57h+ActivityId]; ActivityId
0x1800100c5  mov     qword ptr [rbp+57h+EventDescriptor.Id], rax
0x1800100c9  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800100cd  mov     rax, 8000000000000001h
0x1800100d7  mov     [rbp+57h+var_60], ebx
0x1800100da  mov     [rbp+57h+EventDescriptor.Keyword], rax
0x1800100de  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x1800100e4  test    eax, eax
0x1800100e6  jz      short loc_18001011A
0x1800100e8  lea     rax, Microsoft_Windows_Networking_ProviderId
0x1800100ef  mov     [rbp+57h+var_20], 10h
0x1800100f7  mov     [rbp+57h+var_28], rax
0x1800100fb  lea     rax, [rbp+57h+var_60]
0x1800100ff  mov     [rbp+57h+var_18], rax
0x180010103  lea     rax, [rbp+57h+var_28]
0x180010107  mov     [rsp+90h+UserData], rax
0x18001010c  mov     [rsp+90h+UserDataCount], edi
0x180010110  mov     [rbp+57h+var_10], 4
0x180010118  jmp     short loc_18001012B
0x18001011a  mov     [rsp+90h+UserData], 0; UserData
0x180010123  mov     [rsp+90h+UserDataCount], 0; UserDataCount
0x18001012b  call    cs:__imp_EventWriteTransfer
0x180010132  nop     dword ptr [rax+rax+00h]
0x180010137  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18001013b  mov     ecx, edi; ControlCode
0x18001013d  call    cs:__imp_EventActivityIdControl
0x180010144  nop     dword ptr [rax+rax+00h]
0x180010149  mov     rcx, [rbp+57h+var_8]
0x18001014d  xor     rcx, rsp; StackCookie
0x180010150  call    __security_check_cookie
0x180010155  lea     r11, [rsp+90h+var_s0]
0x18001015d  mov     rbx, [r11+18h]
0x180010161  mov     rdi, [r11+20h]
0x180010165  mov     rsp, r11
0x180010168  pop     rbp
0x180010169  retn
```

# GetPublisherCommand::GetEvents(void *)

- ea: `0x1400100dc`
- end: `0x14001044a`
- name: `?GetEvents@GetPublisherCommand@@AEAAXPEAX@Z`
- size: `878`
- prototype: `void __fastcall(GetPublisherCommand *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000db10`

## callees

- `0x14000cafc`
- `0x14000d900`
- `0x14000dac4`
- `0x14000e924`
- `0x1400100dc`
- `0x140010450`
- `0x140022cec`
- `0x140026fe8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400102e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400103b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400102e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400103b6`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextEventMetadata` at `0x140010137`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextEventMetadata` at `0x140010137`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenEventMetadataEnum` at `0x1400100f7`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenEventMetadataEnum` at `0x1400100f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GetPublisherCommand::GetEvents(GetPublisherCommand *this, void *a2)
{
  EVT_HANDLE v4; // rbx
  EVT_HANDLE EventMetadata; // rbp
  DWORD v6; // ebx
  const wchar_t *Src; // rax
  DWORD LastError; // ebx
  const wchar_t *v9; // rax
  const char *PropertyId; // [rsp+20h] [rbp-78h]
  _BYTE pExceptionObject[88]; // [rsp+40h] [rbp-58h] BYREF
  EVT_HANDLE v12; // [rsp+B0h] [rbp+18h] BYREF
  EVT_HANDLE v13; // [rsp+B8h] [rbp+20h] BYREF

  v4 = EvtOpenEventMetadataEnum(a2, 0);
  v13 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, LastError);
    }
    v9 = (const wchar_t *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v9 = *(const wchar_t **)v9;
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, PropertyId, 302, 0x19u, v9);
    throw (EvtException *)pExceptionObject;
  }
  XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"events");
  XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
  while ( 1 )
  {
    EventMetadata = EvtNextEventMetadata(v4, 0);
    v12 = EventMetadata;
    if ( !EventMetadata )
      break;
    XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"event");
    GetPublisherCommand::GetPropertyEventMetadata(this, L"value", a2, EventMetadata, EventMetadataEventID, 8u, 0);
    GetPublisherCommand::GetPropertyEventMetadata(this, L"version", a2, EventMetadata, EventMetadataEventVersion, 8u, 0);
    GetPublisherCommand::GetPropertyEventMetadata(this, L"opcode", a2, EventMetadata, EventMetadataEventOpcode, 8u, 0);
    GetPublisherCommand::GetPropertyEventMetadata(this, L"channel", a2, EventMetadata, EventMetadataEventChannel, 8u, 0);
    GetPublisherCommand::GetPropertyEventMetadata(this, L"level", a2, EventMetadata, EventMetadataEventLevel, 8u, 0);
    GetPublisherCommand::GetPropertyEventMetadata(this, L"task", a2, EventMetadata, EventMetadataEventTask, 8u, 0);
    GetPublisherCommand::GetPropertyEventMetadata(
      this,
      L"keywords",
      a2,
      EventMetadata,
      EventMetadataEventKeyword,
      0xAu,
      L"0x%I64x");
    GetPublisherCommand::GetPropertyEventMetadata(
      this,
      L"message",
      a2,
      EventMetadata,
      EventMetadataEventMessageID,
      8u,
      0);
    XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
    XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
    tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v12);
  }
  v6 = GetLastError();
  if ( v6 != 259 )
  {
    if ( !v6 )
      v6 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, v6);
    }
    Src = (const wchar_t *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      Src = *(const wchar_t **)Src;
    EvtException::EvtException((EvtException *)pExceptionObject, v6, 0, 0, PropertyId, 316, 0x1Au, Src);
    throw (EvtException *)pExceptionObject;
  }
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v12);
  XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v13);
}

```

## disassembly

```asm
0x1400100dc  mov     [rsp+arg_0], rbx
0x1400100e1  push    rbp
0x1400100e2  push    rsi
0x1400100e3  push    rdi
0x1400100e4  push    r12
0x1400100e6  push    r14
0x1400100e8  sub     rsp, 70h
0x1400100ec  mov     r14, rdx
0x1400100ef  mov     rdi, rcx
0x1400100f2  xor     edx, edx; Flags
0x1400100f4  mov     rcx, r14; PublisherMetadata
0x1400100f7  call    cs:__imp_EvtOpenEventMetadataEnum
0x1400100fd  mov     rbx, rax
0x140010100  mov     [rsp+98h+arg_18], rax
0x140010108  test    rax, rax
0x14001010b  jz      loc_1400103B6
0x140010111  lea     rsi, [rdi+48h]
0x140010115  lea     rdx, aEvents; "events"
0x14001011c  mov     rcx, rsi; this
0x14001011f  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x140010124  mov     rcx, rsi; this
0x140010127  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14001012c  mov     r12d, 8
0x140010132  xor     edx, edx; Flags
0x140010134  mov     rcx, rbx; EventMetadataEnum
0x140010137  call    cs:__imp_EvtNextEventMetadata
0x14001013d  mov     rbp, rax
0x140010140  mov     [rsp+98h+arg_10], rax
0x140010148  test    rax, rax
0x14001014b  jz      loc_1400102E1
0x140010151  lea     rdx, aEvent; "event"
0x140010158  mov     rcx, rsi; this
0x14001015b  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x140010160  mov     [rsp+98h+var_68], 0; wchar_t *
0x140010169  mov     [rsp+98h+var_70], r12d; unsigned int
0x14001016e  mov     dword ptr [rsp+98h+PropertyId], 0; PropertyId
0x140010176  mov     r9, rbp; EventMetadata
0x140010179  mov     r8, r14; void *
0x14001017c  lea     rdx, aValue; "value"
0x140010183  mov     rcx, rdi; this
0x140010186  call    ?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x14001018b  mov     [rsp+98h+var_68], 0; wchar_t *
0x140010194  mov     [rsp+98h+var_70], r12d; unsigned int
0x140010199  mov     dword ptr [rsp+98h+PropertyId], 1; PropertyId
0x1400101a1  mov     r9, rbp; EventMetadata
0x1400101a4  mov     r8, r14; void *
0x1400101a7  lea     rdx, aVersion; "version"
0x1400101ae  mov     rcx, rdi; this
0x1400101b1  call    ?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x1400101b6  mov     [rsp+98h+var_68], 0; wchar_t *
0x1400101bf  mov     [rsp+98h+var_70], r12d; unsigned int
0x1400101c4  mov     dword ptr [rsp+98h+PropertyId], 4; PropertyId
0x1400101cc  mov     r9, rbp; EventMetadata
0x1400101cf  mov     r8, r14; void *
0x1400101d2  lea     rdx, aOpcode_0; "opcode"
0x1400101d9  mov     rcx, rdi; this
0x1400101dc  call    ?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x1400101e1  mov     [rsp+98h+var_68], 0; wchar_t *
0x1400101ea  mov     [rsp+98h+var_70], r12d; unsigned int
0x1400101ef  mov     dword ptr [rsp+98h+PropertyId], 2; PropertyId
0x1400101f7  mov     r9, rbp; EventMetadata
0x1400101fa  mov     r8, r14; void *
0x1400101fd  lea     rdx, aChannel; "channel"
0x140010204  mov     rcx, rdi; this
0x140010207  call    ?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x14001020c  mov     [rsp+98h+var_68], 0; wchar_t *
0x140010215  mov     [rsp+98h+var_70], r12d; unsigned int
0x14001021a  mov     dword ptr [rsp+98h+PropertyId], 3; PropertyId
0x140010222  mov     r9, rbp; EventMetadata
0x140010225  mov     r8, r14; void *
0x140010228  lea     rdx, aLevel; "level"
0x14001022f  mov     rcx, rdi; this
0x140010232  call    ?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x140010237  mov     [rsp+98h+var_68], 0; wchar_t *
0x140010240  mov     [rsp+98h+var_70], r12d; unsigned int
0x140010245  mov     dword ptr [rsp+98h+PropertyId], 5; PropertyId
0x14001024d  mov     r9, rbp; EventMetadata
0x140010250  mov     r8, r14; void *
0x140010253  lea     rdx, aTask_0; "task"
0x14001025a  mov     rcx, rdi; this
0x14001025d  call    ?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x140010262  lea     rax, a0xI64x; "0x%I64x"
0x140010269  mov     [rsp+98h+var_68], rax; wchar_t *
0x14001026e  mov     [rsp+98h+var_70], 0Ah; unsigned int
0x140010276  mov     dword ptr [rsp+98h+PropertyId], 6; PropertyId
0x14001027e  mov     r9, rbp; EventMetadata
0x140010281  mov     r8, r14; void *
0x140010284  lea     rdx, aKeywords; "keywords"
0x14001028b  mov     rcx, rdi; this
0x14001028e  call    ?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x140010293  mov     [rsp+98h+var_68], 0; wchar_t *
0x14001029c  mov     [rsp+98h+var_70], r12d; unsigned int
0x1400102a1  mov     dword ptr [rsp+98h+PropertyId], 7; PropertyId
0x1400102a9  mov     r9, rbp; EventMetadata
0x1400102ac  mov     r8, r14; void *
0x1400102af  lea     rdx, aMessage; "message"
0x1400102b6  mov     rcx, rdi; this
0x1400102b9  call    ?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x1400102be  mov     rcx, rsi; this
0x1400102c1  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x1400102c6  mov     rcx, rsi; this
0x1400102c9  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x1400102ce  nop
0x1400102cf  lea     rcx, [rsp+98h+arg_10]
0x1400102d7  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>(void)
0x1400102dc  jmp     loc_140010132
0x1400102e1  call    cs:__imp_GetLastError
0x1400102e7  mov     ebx, eax
0x1400102e9  cmp     eax, 103h
0x1400102ee  jz      loc_14001037F
0x1400102f4  mov     eax, 507h
0x1400102f9  test    ebx, ebx
0x1400102fb  cmovz   ebx, eax
0x1400102fe  lea     rax, WPP_GLOBAL_Control
0x140010305  mov     rcx, cs:WPP_GLOBAL_Control
0x14001030c  cmp     rcx, rax
0x14001030f  jz      short loc_140010338
0x140010311  test    dword ptr [rcx+1Ch], 400000h
0x140010318  jz      short loc_140010338
0x14001031a  cmp     byte ptr [rcx+19h], 2
0x14001031e  jb      short loc_140010338
0x140010320  mov     edx, 17h
0x140010325  mov     r9d, ebx
0x140010328  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x14001032f  mov     rcx, [rcx+10h]
0x140010333  call    WPP_SF_d
0x140010338  lea     rax, [rdi+28h]
0x14001033c  cmp     qword ptr [rax+18h], 7
0x140010341  jbe     short loc_140010346
0x140010343  mov     rax, [rax]
0x140010346  mov     [rsp+98h+Src], rax; Src
0x14001034b  mov     dword ptr [rsp+98h+var_68], 1Ah; unsigned int
0x140010353  mov     [rsp+98h+var_70], 13Ch; int
0x14001035b  xor     r9d, r9d; unsigned int
0x14001035e  xor     r8d, r8d; unsigned int
0x140010361  mov     edx, ebx; unsigned int
0x140010363  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140010368  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001036d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140010374  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140010379  call    _CxxThrowException_0
0x14001037f  lea     rcx, [rsp+98h+arg_10]
0x140010387  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>(void)
0x14001038c  mov     rcx, rsi; this
0x14001038f  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x140010394  nop
0x140010395  lea     rcx, [rsp+98h+arg_18]
0x14001039d  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>(void)
0x1400103a2  mov     rbx, [rsp+98h+arg_0]
0x1400103aa  add     rsp, 70h
0x1400103ae  pop     r14
0x1400103b0  pop     r12
0x1400103b2  pop     rdi
0x1400103b3  pop     rsi
0x1400103b4  pop     rbp
0x1400103b5  retn
0x1400103b6  call    cs:__imp_GetLastError
0x1400103bc  nop
0x1400103bd  mov     ebx, eax
0x1400103bf  mov     eax, 507h
0x1400103c4  test    ebx, ebx
0x1400103c6  cmovz   ebx, eax
0x1400103c9  lea     rax, WPP_GLOBAL_Control
0x1400103d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103d7  cmp     rcx, rax
0x1400103da  jz      short loc_140010403
0x1400103dc  test    dword ptr [rcx+1Ch], 400000h
0x1400103e3  jz      short loc_140010403
0x1400103e5  cmp     byte ptr [rcx+19h], 2
0x1400103e9  jb      short loc_140010403
0x1400103eb  mov     edx, 16h
0x1400103f0  mov     r9d, ebx
0x1400103f3  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x1400103fa  mov     rcx, [rcx+10h]
0x1400103fe  call    WPP_SF_d
0x140010403  lea     rax, [rdi+28h]
0x140010407  cmp     qword ptr [rax+18h], 7
0x14001040c  jbe     short loc_140010411
0x14001040e  mov     rax, [rax]
0x140010411  mov     [rsp+98h+Src], rax; Src
0x140010416  mov     dword ptr [rsp+98h+var_68], 19h; unsigned int
0x14001041e  mov     [rsp+98h+var_70], 12Eh; int
0x140010426  xor     r9d, r9d; unsigned int
0x140010429  xor     r8d, r8d; unsigned int
0x14001042c  mov     edx, ebx; unsigned int
0x14001042e  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140010433  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140010438  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001043f  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140010444  call    _CxxThrowException_0
```

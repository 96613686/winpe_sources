# GetPublisherCommand::Execute(void)

- ea: `0x14000db10`
- end: `0x14000e316`
- name: `?Execute@GetPublisherCommand@@UEAAXXZ`
- size: `2054`
- prototype: `void __fastcall(GetPublisherCommand *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000b470`
- `0x14000cafc`
- `0x14000d900`
- `0x14000dac4`
- `0x14000db10`
- `0x14000e31c`
- `0x14000e8c4`
- `0x14000e924`
- `0x1400100dc`
- `0x140010450`
- `0x1400217b8`
- `0x140022cec`
- `0x140026bb8`
- `0x140026dc4`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db67`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x14000db51`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x14000db51`

## string_xrefs

- `0x14000e063`: `tasks`
- `0x14000e07f`: `tasks`
- `0x14000dc6c`: `helpLink`
- `0x14000dcef`: `http://schemas.microsoft.com/win/2004/08/events`
- `0x14000dcf6`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GetPublisherCommand::Execute(GetPublisherCommand *this)
{
  char *Src; // r14
  const WCHAR *v3; // rdx
  EVT_HANDLE v4; // rsi
  DWORD LastError; // ebx
  GetPublisherCommand *v6; // rcx
  GetPublisherCommand *v7; // rcx
  void *PropertyArray; // r14
  DWORD i; // r15d
  GetPublisherCommand *v10; // rcx
  void *v11; // r14
  DWORD j; // r15d
  GetPublisherCommand *v13; // rcx
  void *v14; // r15
  DWORD k; // r14d
  const wchar_t *v16; // rdx
  unsigned int v17; // r9d
  GetPublisherCommand *v18; // rcx
  void *v19; // r14
  DWORD m; // r15d
  void *v21; // r14
  DWORD n; // r15d
  const char *Flags; // [rsp+20h] [rbp-49h]
  const wchar_t *ArrayIndex; // [rsp+28h] [rbp-41h]
  const wchar_t *ArrayIndexa; // [rsp+28h] [rbp-41h]
  const wchar_t *ArrayIndexb; // [rsp+28h] [rbp-41h]
  const wchar_t *ArrayIndexc; // [rsp+28h] [rbp-41h]
  const wchar_t *ArrayIndexd; // [rsp+28h] [rbp-41h]
  const wchar_t *ArrayIndexe; // [rsp+28h] [rbp-41h]
  void *v30; // [rsp+40h] [rbp-29h] BYREF
  void *v31; // [rsp+48h] [rbp-21h] BYREF
  EVT_HANDLE v32; // [rsp+50h] [rbp-19h] BYREF
  __int128 pExceptionObject; // [rsp+58h] [rbp-11h] BYREF
  __int64 v34; // [rsp+68h] [rbp-1h]
  unsigned int v35; // [rsp+D0h] [rbp+67h] BYREF
  void *v36; // [rsp+D8h] [rbp+6Fh] BYREF
  void *v37; // [rsp+E0h] [rbp+77h] BYREF
  void *v38; // [rsp+E8h] [rbp+7Fh] BYREF

  Src = (char *)this + 40;
  if ( *((_QWORD *)this + 8) <= 7u )
    v3 = (const WCHAR *)((char *)this + 40);
  else
    v3 = *(const WCHAR **)Src;
  v4 = EvtOpenPublisherMetadata(*((EVT_HANDLE *)this + 3), v3, 0, 0, 0);
  v32 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, LastError);
    }
    if ( *((_QWORD *)Src + 3) > 7u )
      Src = *(char **)Src;
    EvtException::EvtException(
      (EvtException *)&pExceptionObject,
      LastError,
      0,
      0,
      Flags,
      352,
      0x15u,
      (const wchar_t *)Src);
    throw (EvtException *)&pExceptionObject;
  }
  pExceptionObject = 0;
  v34 = 0;
  XmlPrinter::Start((GetPublisherCommand *)((char *)this + 72), *((void **)this + 2), *((_BYTE *)this + 112));
  XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"provider");
  if ( *((_QWORD *)Src + 3) > 7u )
    Src = *(char **)Src;
  XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), L"name", (const wchar_t *)Src);
  GetPublisherCommand::GetProperty(this, L"guid", v4, EvtPublisherMetadataPublisherGuid, 0xFu, ArrayIndex);
  GetPublisherCommand::GetProperty(this, L"helpLink", v4, EvtPublisherMetadataHelpLink, 1u, ArrayIndexa);
  GetPublisherCommand::GetProperty(this, L"resourceFileName", v4, EvtPublisherMetadataResourceFilePath, 1u, ArrayIndexb);
  GetPublisherCommand::GetProperty(
    this,
    L"parameterFileName",
    v4,
    EvtPublisherMetadataParameterFilePath,
    1u,
    ArrayIndexc);
  GetPublisherCommand::GetProperty(this, L"messageFileName", v4, EvtPublisherMetadataMessageFilePath, 1u, ArrayIndexd);
  GetPublisherCommand::GetProperty(this, L"message", v4, EvtPublisherMetadataPublisherMessageID, 8u, ArrayIndexe);
  if ( *((_BYTE *)this + 104) )
    XmlPrinter::PrintNameValue(
      (GetPublisherCommand *)((char *)this + 72),
      L"xmlns",
      L"http://schemas.microsoft.com/win/2004/08/events");
  XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
  v35 = 0;
  PropertyArray = GetPublisherCommand::GetPropertyArray(
                    v6,
                    L"channels",
                    v4,
                    EvtPublisherMetadataChannelReferences,
                    &v35);
  v31 = PropertyArray;
  if ( PropertyArray )
  {
    XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"channels");
    XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
    for ( i = 0; i < v35; ++i )
    {
      XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"channel");
      GetPublisherCommand::GetPropertyArrayElement(this, L"name", v4, PropertyArray, 7u, i, 1u, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"id", v4, PropertyArray, 9u, i, 8u, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"flags", v4, PropertyArray, 0xAu, i, 8u, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"message", v4, PropertyArray, 0xBu, i, 8u, 0);
      XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
      XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
    }
    XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
  }
  v11 = GetPublisherCommand::GetPropertyArray(v7, L"levels", v4, EvtPublisherMetadataLevels, &v35);
  v30 = v11;
  if ( v11 )
  {
    XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"levels");
    XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
    for ( j = 0; j < v35; ++j )
    {
      XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"level");
      GetPublisherCommand::GetPropertyArrayElement(this, L"name", v4, v11, 0xDu, j, 1u, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"value", v4, v11, 0xEu, j, 8u, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"message", v4, v11, 0xFu, j, 8u, 0);
      XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
      XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
    }
    XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
  }
  v14 = GetPublisherCommand::GetPropertyArray(v10, L"opcodes", v4, EvtPublisherMetadataOpcodes, &v35);
  v38 = v14;
  if ( v14 )
  {
    XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"opcodes");
    XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
    for ( k = 0; k < v35; ++k )
    {
      XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"opcode");
      GetPublisherCommand::GetPropertyArrayElement(this, L"name", v4, v14, 0x16u, k, 1u, 0);
      GetPublisherCommand::GetPropertyOpcodeValue(this, v16, v14, v17, k);
      GetPublisherCommand::GetPropertyArrayElement(this, L"message", v4, v14, 0x18u, k, 8u, 0);
      XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
      XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
    }
    XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
  }
  v19 = GetPublisherCommand::GetPropertyArray(v13, L"tasks", v4, EvtPublisherMetadataTasks, &v35);
  v37 = v19;
  if ( v19 )
  {
    XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"tasks");
    XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
    for ( m = 0; m < v35; ++m )
    {
      XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"task");
      GetPublisherCommand::GetPropertyArrayElement(this, L"name", v4, v19, 0x11u, m, 1u, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"value", v4, v19, 0x13u, m, 8u, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"eventGUID", v4, v19, 0x12u, m, 0xFu, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"message", v4, v19, 0x14u, m, 8u, 0);
      XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
      XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
    }
    XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
  }
  v21 = GetPublisherCommand::GetPropertyArray(v18, L"keywords", v4, EvtPublisherMetadataKeywords, &v35);
  v36 = v21;
  if ( v21 )
  {
    XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"keywords");
    XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
    for ( n = 0; n < v35; ++n )
    {
      XmlPrinter::PrintStartElement((GetPublisherCommand *)((char *)this + 72), L"keyword");
      GetPublisherCommand::GetPropertyArrayElement(this, L"name", v4, v21, 0x1Au, n, 1u, 0);
      GetPublisherCommand::GetPropertyArrayElement(this, L"mask", v4, v21, 0x1Bu, n, 0xAu, L"%I64x");
      GetPublisherCommand::GetPropertyArrayElement(this, L"message", v4, v21, 0x1Cu, n, 8u, 0);
      XmlPrinter::PrintStartElementEnd((GetPublisherCommand *)((char *)this + 72));
      XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
    }
    XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
  }
  if ( *((_BYTE *)this + 113) )
    GetPublisherCommand::GetEvents(this, v4);
  XmlPrinter::PrintEndElement((GetPublisherCommand *)((char *)this + 72));
  *((_QWORD *)this + 9) = -1;
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v36);
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v37);
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v38);
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v30);
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v31);
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v32);
}

```

## disassembly

```asm
0x14000db10  push    rbp
0x14000db12  push    rbx
0x14000db13  push    rsi
0x14000db14  push    rdi
0x14000db15  push    r12
0x14000db17  push    r13
0x14000db19  push    r14
0x14000db1b  push    r15
0x14000db1d  lea     rbp, [rsp-1Fh]
0x14000db22  sub     rsp, 88h
0x14000db29  mov     rdi, rcx
0x14000db2c  lea     r14, [rcx+28h]
0x14000db30  cmp     qword ptr [r14+18h], 7
0x14000db35  jbe     short loc_14000DB3C
0x14000db37  mov     rdx, [r14]
0x14000db3a  jmp     short loc_14000DB3F
0x14000db3c  mov     rdx, r14; PublisherId
0x14000db3f  xor     r12d, r12d
0x14000db42  mov     [rsp+0C0h+Flags], r12d; char *
0x14000db47  xor     r9d, r9d; Locale
0x14000db4a  xor     r8d, r8d; LogFilePath
0x14000db4d  mov     rcx, [rcx+18h]; Session
0x14000db51  call    cs:__imp_EvtOpenPublisherMetadata
0x14000db57  mov     rsi, rax
0x14000db5a  mov     [rbp+57h+var_70], rax
0x14000db5e  test    rax, rax
0x14000db61  jnz     loc_14000DBF2
0x14000db67  call    cs:__imp_GetLastError
0x14000db6d  mov     ebx, eax
0x14000db6f  mov     eax, 507h
0x14000db74  test    ebx, ebx
0x14000db76  cmovz   ebx, eax
0x14000db79  lea     rax, WPP_GLOBAL_Control
0x14000db80  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db87  cmp     rcx, rax
0x14000db8a  jz      short loc_14000DBB1
0x14000db8c  test    dword ptr [rcx+1Ch], 400000h
0x14000db93  jz      short loc_14000DBB1
0x14000db95  cmp     byte ptr [rcx+19h], 2
0x14000db99  jb      short loc_14000DBB1
0x14000db9b  lea     edx, [rsi+18h]
0x14000db9e  mov     r9d, ebx
0x14000dba1  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x14000dba8  mov     rcx, [rcx+10h]
0x14000dbac  call    WPP_SF_d
0x14000dbb1  cmp     qword ptr [r14+18h], 7
0x14000dbb6  jbe     short loc_14000DBBB
0x14000dbb8  mov     r14, [r14]
0x14000dbbb  mov     [rsp+0C0h+Src], r14; Src
0x14000dbc0  mov     [rsp+0C0h+var_90], 15h; unsigned int
0x14000dbc8  mov     dword ptr [rsp+0C0h+ArrayIndex], 160h; int
0x14000dbd0  xor     r9d, r9d; unsigned int
0x14000dbd3  xor     r8d, r8d; unsigned int
0x14000dbd6  mov     edx, ebx; unsigned int
0x14000dbd8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000dbdc  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000dbe1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000dbe8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000dbec  call    _CxxThrowException_0
0x14000dbf2  xorps   xmm0, xmm0
0x14000dbf5  movdqu  [rbp+57h+pExceptionObject], xmm0
0x14000dbfa  mov     [rbp+57h+var_58], r12
0x14000dbfe  lea     rbx, [rdi+48h]
0x14000dc02  mov     r8b, [rdi+70h]; bool
0x14000dc06  mov     rdx, [rdi+10h]; void *
0x14000dc0a  mov     rcx, rbx; this
0x14000dc0d  call    ?Start@XmlPrinter@@QEAAXPEAX_N@Z; XmlPrinter::Start(void *,bool)
0x14000dc12  lea     rdx, aProvider; "provider"
0x14000dc19  mov     rcx, rbx; this
0x14000dc1c  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000dc21  cmp     qword ptr [r14+18h], 7
0x14000dc26  jbe     short loc_14000DC2B
0x14000dc28  mov     r14, [r14]
0x14000dc2b  mov     r8, r14; wchar_t *
0x14000dc2e  lea     rdx, aName_0; "name"
0x14000dc35  mov     rcx, rbx; this
0x14000dc38  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14000dc3d  mov     [rsp+0C0h+Flags], 0Fh; unsigned int
0x14000dc45  xor     r9d, r9d; PropertyId
0x14000dc48  mov     r8, rsi; void *
0x14000dc4b  lea     rdx, aGuid_0; "guid"
0x14000dc52  mov     rcx, rdi; this
0x14000dc55  call    ?GetProperty@GetPublisherCommand@@AEAAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetProperty(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x14000dc5a  mov     r13d, 1
0x14000dc60  mov     [rsp+0C0h+Flags], r13d; unsigned int
0x14000dc65  lea     r9d, [r13+3]; PropertyId
0x14000dc69  mov     r8, rsi; void *
0x14000dc6c  lea     rdx, aHelplink_0; "helpLink"
0x14000dc73  mov     rcx, rdi; this
0x14000dc76  call    ?GetProperty@GetPublisherCommand@@AEAAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetProperty(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x14000dc7b  mov     [rsp+0C0h+Flags], r13d; unsigned int
0x14000dc80  mov     r9d, r13d; PropertyId
0x14000dc83  mov     r8, rsi; void *
0x14000dc86  lea     rdx, aResourcefilena_0; "resourceFileName"
0x14000dc8d  mov     rcx, rdi; this
0x14000dc90  call    ?GetProperty@GetPublisherCommand@@AEAAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetProperty(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x14000dc95  mov     [rsp+0C0h+Flags], r13d; unsigned int
0x14000dc9a  lea     r9d, [r13+1]; PropertyId
0x14000dc9e  mov     r8, rsi; void *
0x14000dca1  lea     rdx, aParameterfilen_0; "parameterFileName"
0x14000dca8  mov     rcx, rdi; this
0x14000dcab  call    ?GetProperty@GetPublisherCommand@@AEAAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetProperty(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x14000dcb0  mov     [rsp+0C0h+Flags], r13d; unsigned int
0x14000dcb5  lea     r9d, [r13+2]; PropertyId
0x14000dcb9  mov     r8, rsi; void *
0x14000dcbc  lea     rdx, aMessagefilenam_0; "messageFileName"
0x14000dcc3  mov     rcx, rdi; this
0x14000dcc6  call    ?GetProperty@GetPublisherCommand@@AEAAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetProperty(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x14000dccb  mov     [rsp+0C0h+Flags], 8; unsigned int
0x14000dcd3  lea     r9d, [r13+4]; PropertyId
0x14000dcd7  mov     r8, rsi; void *
0x14000dcda  lea     rdx, aMessage; "message"
0x14000dce1  mov     rcx, rdi; this
0x14000dce4  call    ?GetProperty@GetPublisherCommand@@AEAAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@K0@Z; GetPublisherCommand::GetProperty(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong,wchar_t const *)
0x14000dce9  cmp     [rdi+68h], r12b
0x14000dced  jz      short loc_14000DD05
0x14000dcef  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/win/2004/0"...
0x14000dcf6  lea     rdx, aXmlns; "xmlns"
0x14000dcfd  mov     rcx, rbx; this
0x14000dd00  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14000dd05  mov     rcx, rbx; this
0x14000dd08  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000dd0d  mov     [rbp+57h+arg_0], r12d
0x14000dd11  lea     rax, [rbp+57h+arg_0]
0x14000dd15  mov     qword ptr [rsp+0C0h+Flags], rax; unsigned int *
0x14000dd1a  mov     r9d, 6; enum _EVT_PUBLISHER_METADATA_PROPERTY_ID
0x14000dd20  mov     r8, rsi; void *
0x14000dd23  lea     rdx, aChannels_2; "channels"
0x14000dd2a  call    ?GetPropertyArray@GetPublisherCommand@@AEAAPEAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@AEAK@Z; GetPublisherCommand::GetPropertyArray(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong &)
0x14000dd2f  mov     r14, rax
0x14000dd32  mov     [rbp+57h+var_78], rax
0x14000dd36  test    rax, rax
0x14000dd39  jz      loc_14000DE50
0x14000dd3f  lea     rdx, aChannels_2; "channels"
0x14000dd46  mov     rcx, rbx; this
0x14000dd49  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000dd4e  mov     rcx, rbx; this
0x14000dd51  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000dd56  mov     r15d, r12d
0x14000dd59  cmp     [rbp+57h+arg_0], r12d
0x14000dd5d  jbe     loc_14000DE48
0x14000dd63  lea     rdx, aChannel; "channel"
0x14000dd6a  mov     rcx, rbx; this
0x14000dd6d  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000dd72  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000dd77  mov     [rsp+0C0h+var_90], r13d; unsigned int
0x14000dd7c  mov     dword ptr [rsp+0C0h+ArrayIndex], r15d; ArrayIndex
0x14000dd81  mov     [rsp+0C0h+Flags], 7; PropertyId
0x14000dd89  mov     r9, r14; ObjectArray
0x14000dd8c  mov     r8, rsi; void *
0x14000dd8f  lea     rdx, aName_0; "name"
0x14000dd96  mov     rcx, rdi; this
0x14000dd99  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000dd9e  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000dda3  mov     [rsp+0C0h+var_90], 8; unsigned int
0x14000ddab  mov     dword ptr [rsp+0C0h+ArrayIndex], r15d; ArrayIndex
0x14000ddb0  mov     [rsp+0C0h+Flags], 9; PropertyId
0x14000ddb8  mov     r9, r14; ObjectArray
0x14000ddbb  mov     r8, rsi; void *
0x14000ddbe  lea     rdx, aId_0; "id"
0x14000ddc5  mov     rcx, rdi; this
0x14000ddc8  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000ddcd  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000ddd2  mov     [rsp+0C0h+var_90], 8; unsigned int
0x14000ddda  mov     dword ptr [rsp+0C0h+ArrayIndex], r15d; ArrayIndex
0x14000dddf  mov     [rsp+0C0h+Flags], 0Ah; PropertyId
0x14000dde7  mov     r9, r14; ObjectArray
0x14000ddea  mov     r8, rsi; void *
0x14000dded  lea     rdx, aFlags_0; "flags"
0x14000ddf4  mov     rcx, rdi; this
0x14000ddf7  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000ddfc  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000de01  mov     [rsp+0C0h+var_90], 8; unsigned int
0x14000de09  mov     dword ptr [rsp+0C0h+ArrayIndex], r15d; ArrayIndex
0x14000de0e  mov     [rsp+0C0h+Flags], 0Bh; PropertyId
0x14000de16  mov     r9, r14; ObjectArray
0x14000de19  mov     r8, rsi; void *
0x14000de1c  lea     rdx, aMessage; "message"
0x14000de23  mov     rcx, rdi; this
0x14000de26  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000de2b  mov     rcx, rbx; this
0x14000de2e  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000de33  mov     rcx, rbx; this
0x14000de36  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000de3b  add     r15d, r13d
0x14000de3e  cmp     r15d, [rbp+57h+arg_0]
0x14000de42  jb      loc_14000DD63
0x14000de48  mov     rcx, rbx; this
0x14000de4b  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000de50  lea     rax, [rbp+57h+arg_0]
0x14000de54  mov     qword ptr [rsp+0C0h+Flags], rax; unsigned int *
0x14000de59  mov     r9d, 0Ch; enum _EVT_PUBLISHER_METADATA_PROPERTY_ID
0x14000de5f  mov     r8, rsi; void *
0x14000de62  lea     rdx, aLevels; "levels"
0x14000de69  call    ?GetPropertyArray@GetPublisherCommand@@AEAAPEAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@AEAK@Z; GetPublisherCommand::GetPropertyArray(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong &)
0x14000de6e  mov     r14, rax
0x14000de71  mov     [rbp+57h+var_80], rax
0x14000de75  test    rax, rax
0x14000de78  jz      loc_14000DF60
0x14000de7e  lea     rdx, aLevels; "levels"
0x14000de85  mov     rcx, rbx; this
0x14000de88  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000de8d  mov     rcx, rbx; this
0x14000de90  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000de95  mov     r15d, r12d
0x14000de98  cmp     [rbp+57h+arg_0], r12d
0x14000de9c  jbe     loc_14000DF58
0x14000dea2  lea     rdx, aLevel; "level"
0x14000dea9  mov     rcx, rbx; this
0x14000deac  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000deb1  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000deb6  mov     [rsp+0C0h+var_90], r13d; unsigned int
0x14000debb  mov     dword ptr [rsp+0C0h+ArrayIndex], r15d; ArrayIndex
0x14000dec0  mov     [rsp+0C0h+Flags], 0Dh; PropertyId
0x14000dec8  mov     r9, r14; ObjectArray
0x14000decb  mov     r8, rsi; void *
0x14000dece  lea     rdx, aName_0; "name"
0x14000ded5  mov     rcx, rdi; this
0x14000ded8  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000dedd  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000dee2  mov     [rsp+0C0h+var_90], 8; unsigned int
0x14000deea  mov     dword ptr [rsp+0C0h+ArrayIndex], r15d; ArrayIndex
0x14000deef  mov     [rsp+0C0h+Flags], 0Eh; PropertyId
0x14000def7  mov     r9, r14; ObjectArray
0x14000defa  mov     r8, rsi; void *
0x14000defd  lea     rdx, aValue; "value"
0x14000df04  mov     rcx, rdi; this
0x14000df07  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000df0c  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000df11  mov     [rsp+0C0h+var_90], 8; unsigned int
0x14000df19  mov     dword ptr [rsp+0C0h+ArrayIndex], r15d; ArrayIndex
0x14000df1e  mov     [rsp+0C0h+Flags], 0Fh; PropertyId
0x14000df26  mov     r9, r14; ObjectArray
0x14000df29  mov     r8, rsi; void *
0x14000df2c  lea     rdx, aMessage; "message"
0x14000df33  mov     rcx, rdi; this
0x14000df36  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000df3b  mov     rcx, rbx; this
0x14000df3e  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000df43  mov     rcx, rbx; this
0x14000df46  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000df4b  add     r15d, r13d
0x14000df4e  cmp     r15d, [rbp+57h+arg_0]
0x14000df52  jb      loc_14000DEA2
0x14000df58  mov     rcx, rbx; this
0x14000df5b  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000df60  lea     rax, [rbp+57h+arg_0]
0x14000df64  mov     qword ptr [rsp+0C0h+Flags], rax; unsigned int *
0x14000df69  mov     r9d, 15h; enum _EVT_PUBLISHER_METADATA_PROPERTY_ID
0x14000df6f  mov     r8, rsi; void *
0x14000df72  lea     rdx, aOpcodes; "opcodes"
0x14000df79  call    ?GetPropertyArray@GetPublisherCommand@@AEAAPEAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@AEAK@Z; GetPublisherCommand::GetPropertyArray(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong &)
0x14000df7e  mov     r15, rax
0x14000df81  mov     [rbp+57h+arg_18], rax
0x14000df85  test    rax, rax
0x14000df88  jz      loc_14000E051
0x14000df8e  lea     rdx, aOpcodes; "opcodes"
0x14000df95  mov     rcx, rbx; this
0x14000df98  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000df9d  mov     rcx, rbx; this
0x14000dfa0  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000dfa5  mov     r14d, r12d
0x14000dfa8  cmp     [rbp+57h+arg_0], r12d
0x14000dfac  jbe     loc_14000E049
0x14000dfb2  lea     rdx, aOpcode_0; "opcode"
0x14000dfb9  mov     rcx, rbx; this
0x14000dfbc  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000dfc1  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000dfc6  mov     [rsp+0C0h+var_90], r13d; unsigned int
0x14000dfcb  mov     dword ptr [rsp+0C0h+ArrayIndex], r14d; ArrayIndex
0x14000dfd0  mov     [rsp+0C0h+Flags], 16h; PropertyId
0x14000dfd8  mov     r9, r15; ObjectArray
0x14000dfdb  mov     r8, rsi; void *
0x14000dfde  lea     rdx, aName_0; "name"
0x14000dfe5  mov     rcx, rdi; this
0x14000dfe8  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000dfed  mov     [rsp+0C0h+Flags], r14d; unsigned int
0x14000dff2  mov     r8, r15; void *
0x14000dff5  mov     rcx, rdi; this
0x14000dff8  call    ?GetPropertyOpcodeValue@GetPublisherCommand@@AEAAXPEB_WPEAXKK@Z; GetPublisherCommand::GetPropertyOpcodeValue(wchar_t const *,void *,ulong,ulong)
0x14000dffd  mov     [rsp+0C0h+Src], r12; wchar_t *
0x14000e002  mov     [rsp+0C0h+var_90], 8; unsigned int
0x14000e00a  mov     dword ptr [rsp+0C0h+ArrayIndex], r14d; ArrayIndex
0x14000e00f  mov     [rsp+0C0h+Flags], 18h; PropertyId
0x14000e017  mov     r9, r15; ObjectArray
0x14000e01a  mov     r8, rsi; void *
0x14000e01d  lea     rdx, aMessage; "message"
0x14000e024  mov     rcx, rdi; this
0x14000e027  call    ?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z; GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)
0x14000e02c  mov     rcx, rbx; this
0x14000e02f  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000e034  mov     rcx, rbx; this
0x14000e037  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000e03c  add     r14d, r13d
0x14000e03f  cmp     r14d, [rbp+57h+arg_0]
0x14000e043  jb      loc_14000DFB2
0x14000e049  mov     rcx, rbx; this
0x14000e04c  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000e051  lea     rax, [rbp+57h+arg_0]
0x14000e055  mov     qword ptr [rsp+0C0h+Flags], rax; unsigned int *
  ... truncated ...
```

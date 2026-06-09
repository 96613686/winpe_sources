# GetChannelCommand::Execute(void)

- ea: `0x14000e550`
- end: `0x14000e8bc`
- name: `?Execute@GetChannelCommand@@UEAAXXZ`
- size: `876`
- prototype: `void __fastcall(GetChannelCommand *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000cafc`
- `0x14000d900`
- `0x14000dac4`
- `0x14000e550`
- `0x14000e8c4`
- `0x14000e924`
- `0x140010450`
- `0x1400217b8`
- `0x140022cec`
- `0x1400260f8`
- `0x1400262e4`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e591`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x14000e577`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x14000e577`

## string_xrefs

- `0x14000e6ec`: `channelAccess`
- `0x14000e701`: `http://schemas.microsoft.com/win/2004/08/events`
- `0x14000e708`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GetChannelCommand::Execute(GetChannelCommand *this)
{
  char *Src; // rbx
  const WCHAR *v3; // rdx
  EVT_HANDLE v4; // rsi
  DWORD LastError; // edi
  const char *v6; // [rsp+20h] [rbp-78h]
  _BYTE pExceptionObject[88]; // [rsp+40h] [rbp-58h] BYREF
  EVT_HANDLE v8; // [rsp+A0h] [rbp+8h] BYREF

  Src = (char *)this + 40;
  if ( *((_QWORD *)this + 8) <= 7u )
    v3 = (const WCHAR *)((char *)this + 40);
  else
    v3 = *(const WCHAR **)Src;
  v4 = EvtOpenChannelConfig(*((EVT_HANDLE *)this + 3), v3, 0);
  v8 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids, LastError);
    }
    if ( *((_QWORD *)Src + 3) > 7u )
      Src = *(char **)Src;
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v6, 144, 0x1Du, (const wchar_t *)Src);
    throw (EvtException *)pExceptionObject;
  }
  XmlPrinter::Start((GetChannelCommand *)((char *)this + 72), *((void **)this + 2), *((_BYTE *)this + 112));
  XmlPrinter::PrintStartElement((GetChannelCommand *)((char *)this + 72), L"channel");
  if ( *((_QWORD *)Src + 3) > 7u )
    Src = *(char **)Src;
  XmlPrinter::PrintNameValue((GetChannelCommand *)((char *)this + 72), L"name", (const wchar_t *)Src);
  GetChannelCommand::GetProperty(this, L"enabled", v4, EvtChannelConfigEnabled, 0xDu, 0);
  GetChannelCommand::GetPropertyEnum(this, L"type", v4, EvtChannelConfigType);
  GetChannelCommand::GetProperty(this, L"owningPublisher", v4, EvtChannelConfigOwningPublisher, 1u, 0);
  GetChannelCommand::GetPropertyEnum(this, L"isolation", v4, EvtChannelConfigIsolation);
  GetChannelCommand::GetProperty(this, L"channelAccess", v4, EvtChannelConfigAccess, 1u, 0);
  if ( *((_BYTE *)this + 104) )
    XmlPrinter::PrintNameValue(
      (GetChannelCommand *)((char *)this + 72),
      L"xmlns",
      L"http://schemas.microsoft.com/win/2004/08/events");
  XmlPrinter::PrintStartElementEnd((GetChannelCommand *)((char *)this + 72));
  XmlPrinter::PrintStartElement((GetChannelCommand *)((char *)this + 72), L"logging");
  XmlPrinter::PrintStartElementEnd((GetChannelCommand *)((char *)this + 72));
  GetChannelCommand::GetProperty(this, L"logFileName", v4, EvtChannelLoggingConfigLogFilePath, 1u, 0);
  GetChannelCommand::GetProperty(this, L"retention", v4, EvtChannelLoggingConfigRetention, 0xDu, 0);
  GetChannelCommand::GetProperty(this, L"autoBackup", v4, EvtChannelLoggingConfigAutoBackup, 0xDu, 0);
  GetChannelCommand::GetProperty(this, L"maxSize", v4, EvtChannelLoggingConfigMaxSize, 0xAu, 0);
  XmlPrinter::PrintEndElement((GetChannelCommand *)((char *)this + 72));
  XmlPrinter::PrintStartElement((GetChannelCommand *)((char *)this + 72), L"publishing");
  XmlPrinter::PrintStartElementEnd((GetChannelCommand *)((char *)this + 72));
  GetChannelCommand::GetProperty(this, L"fileMax", v4, EvtChannelPublishingConfigFileMax, 8u, 0);
  GetChannelCommand::GetProperty(this, L"level", v4, EvtChannelPublishingConfigLevel, 8u, 0);
  GetChannelCommand::GetProperty(this, L"keywords", v4, EvtChannelPublishingConfigKeywords, 0xAu, L"0x%I64x");
  GetChannelCommand::GetProperty(this, L"controlGuid", v4, EvtChannelPublishingConfigControlGuid, 0xFu, 0);
  XmlPrinter::PrintEndElement((GetChannelCommand *)((char *)this + 72));
  XmlPrinter::PrintEndElement((GetChannelCommand *)((char *)this + 72));
  *((_QWORD *)this + 9) = -1;
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v8);
}

```

## disassembly

```asm
0x14000e550  push    rbx
0x14000e552  push    rsi
0x14000e553  push    rdi
0x14000e554  push    r14
0x14000e556  sub     rsp, 78h
0x14000e55a  mov     rdi, rcx
0x14000e55d  lea     rbx, [rcx+28h]
0x14000e561  cmp     qword ptr [rbx+18h], 7
0x14000e566  jbe     short loc_14000E56D
0x14000e568  mov     rdx, [rbx]
0x14000e56b  jmp     short loc_14000E570
0x14000e56d  mov     rdx, rbx; ChannelPath
0x14000e570  xor     r8d, r8d; Flags
0x14000e573  mov     rcx, [rcx+18h]; Session
0x14000e577  call    cs:__imp_EvtOpenChannelConfig
0x14000e57d  mov     rsi, rax
0x14000e580  mov     [rsp+98h+arg_0], rax
0x14000e588  test    rax, rax
0x14000e58b  jnz     loc_14000E61E
0x14000e591  call    cs:__imp_GetLastError
0x14000e597  mov     edi, eax
0x14000e599  mov     eax, 507h
0x14000e59e  test    edi, edi
0x14000e5a0  cmovz   edi, eax
0x14000e5a3  lea     rax, WPP_GLOBAL_Control
0x14000e5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5b1  cmp     rcx, rax
0x14000e5b4  jz      short loc_14000E5DB
0x14000e5b6  test    dword ptr [rcx+1Ch], 400000h
0x14000e5bd  jz      short loc_14000E5DB
0x14000e5bf  cmp     byte ptr [rcx+19h], 2
0x14000e5c3  jb      short loc_14000E5DB
0x14000e5c5  lea     edx, [rsi+10h]
0x14000e5c8  mov     r9d, edi
0x14000e5cb  lea     r8, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids
0x14000e5d2  mov     rcx, [rcx+10h]
0x14000e5d6  call    WPP_SF_d
0x14000e5db  cmp     qword ptr [rbx+18h], 7
0x14000e5e0  jbe     short loc_14000E5E5
0x14000e5e2  mov     rbx, [rbx]
0x14000e5e5  mov     [rsp+98h+Src], rbx; Src
0x14000e5ea  mov     [rsp+98h+var_68], 1Dh; unsigned int
0x14000e5f2  mov     dword ptr [rsp+98h+var_70], 90h; int
0x14000e5fa  xor     r9d, r9d; unsigned int
0x14000e5fd  xor     r8d, r8d; unsigned int
0x14000e600  mov     edx, edi; unsigned int
0x14000e602  lea     rcx, [rsp+98h+pExceptionObject]; this
0x14000e607  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000e60c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000e613  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x14000e618  call    _CxxThrowException_0
0x14000e61e  lea     r14, [rdi+48h]
0x14000e622  mov     r8b, [rdi+70h]; bool
0x14000e626  mov     rdx, [rdi+10h]; void *
0x14000e62a  mov     rcx, r14; this
0x14000e62d  call    ?Start@XmlPrinter@@QEAAXPEAX_N@Z; XmlPrinter::Start(void *,bool)
0x14000e632  lea     rdx, aChannel; "channel"
0x14000e639  mov     rcx, r14; this
0x14000e63c  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000e641  cmp     qword ptr [rbx+18h], 7
0x14000e646  jbe     short loc_14000E64B
0x14000e648  mov     rbx, [rbx]
0x14000e64b  mov     r8, rbx; wchar_t *
0x14000e64e  lea     rdx, aName_0; "name"
0x14000e655  mov     rcx, r14; this
0x14000e658  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14000e65d  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e666  mov     dword ptr [rsp+98h+var_78], 0Dh; unsigned int
0x14000e66e  xor     r9d, r9d; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e671  mov     r8, rsi; void *
0x14000e674  lea     rdx, aEnabled_0; "enabled"
0x14000e67b  mov     rcx, rdi; this
0x14000e67e  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e683  mov     r9d, 2; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e689  mov     r8, rsi; void *
0x14000e68c  lea     rdx, aType; "type"
0x14000e693  mov     rcx, rdi; this
0x14000e696  call    ?GetPropertyEnum@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; GetChannelCommand::GetPropertyEnum(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x14000e69b  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e6a4  mov     ebx, 1
0x14000e6a9  mov     dword ptr [rsp+98h+var_78], ebx; unsigned int
0x14000e6ad  lea     r9d, [rbx+2]; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e6b1  mov     r8, rsi; void *
0x14000e6b4  lea     rdx, aOwningpublishe_0; "owningPublisher"
0x14000e6bb  mov     rcx, rdi; this
0x14000e6be  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e6c3  mov     r9d, ebx; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e6c6  mov     r8, rsi; void *
0x14000e6c9  lea     rdx, aIsolation_0; "isolation"
0x14000e6d0  mov     rcx, rdi; this
0x14000e6d3  call    ?GetPropertyEnum@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; GetChannelCommand::GetPropertyEnum(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x14000e6d8  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e6e1  mov     dword ptr [rsp+98h+var_78], ebx; unsigned int
0x14000e6e5  lea     r9d, [rbx+4]; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e6e9  mov     r8, rsi; void *
0x14000e6ec  lea     rdx, aChannelaccess; "channelAccess"
0x14000e6f3  mov     rcx, rdi; this
0x14000e6f6  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e6fb  cmp     byte ptr [rdi+68h], 0
0x14000e6ff  jz      short loc_14000E717
0x14000e701  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/win/2004/0"...
0x14000e708  lea     rdx, aXmlns; "xmlns"
0x14000e70f  mov     rcx, r14; this
0x14000e712  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14000e717  mov     rcx, r14; this
0x14000e71a  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000e71f  lea     rdx, aLogging; "logging"
0x14000e726  mov     rcx, r14; this
0x14000e729  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000e72e  mov     rcx, r14; this
0x14000e731  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000e736  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e73f  mov     dword ptr [rsp+98h+var_78], ebx; unsigned int
0x14000e743  mov     r9d, 9; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e749  mov     r8, rsi; void *
0x14000e74c  lea     rdx, aLogfilename_0; "logFileName"
0x14000e753  mov     rcx, rdi; this
0x14000e756  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e75b  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e764  mov     dword ptr [rsp+98h+var_78], 0Dh; unsigned int
0x14000e76c  mov     r9d, 6; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e772  mov     r8, rsi; void *
0x14000e775  lea     rdx, aRetention_0; "retention"
0x14000e77c  mov     rcx, rdi; this
0x14000e77f  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e784  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e78d  mov     dword ptr [rsp+98h+var_78], 0Dh; unsigned int
0x14000e795  mov     r9d, 7; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e79b  mov     r8, rsi; void *
0x14000e79e  lea     rdx, aAutobackup; "autoBackup"
0x14000e7a5  mov     rcx, rdi; this
0x14000e7a8  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e7ad  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e7b6  mov     dword ptr [rsp+98h+var_78], 0Ah; unsigned int
0x14000e7be  mov     ebx, 8
0x14000e7c3  mov     r9d, ebx; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e7c6  mov     r8, rsi; void *
0x14000e7c9  lea     rdx, aMaxsize; "maxSize"
0x14000e7d0  mov     rcx, rdi; this
0x14000e7d3  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e7d8  mov     rcx, r14; this
0x14000e7db  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000e7e0  lea     rdx, aPublishing; "publishing"
0x14000e7e7  mov     rcx, r14; this
0x14000e7ea  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x14000e7ef  mov     rcx, r14; this
0x14000e7f2  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x14000e7f7  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e800  mov     dword ptr [rsp+98h+var_78], ebx; unsigned int
0x14000e804  lea     r9d, [rbx+0Ch]; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e808  mov     r8, rsi; void *
0x14000e80b  lea     rdx, aFilemax_0; "fileMax"
0x14000e812  mov     rcx, rdi; this
0x14000e815  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e81a  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e823  mov     dword ptr [rsp+98h+var_78], ebx; unsigned int
0x14000e827  lea     r9d, [rbx+2]; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e82b  mov     r8, rsi; void *
0x14000e82e  lea     rdx, aLevel; "level"
0x14000e835  mov     rcx, rdi; this
0x14000e838  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e83d  lea     rax, a0xI64x; "0x%I64x"
0x14000e844  mov     [rsp+98h+var_70], rax; wchar_t *
0x14000e849  mov     dword ptr [rsp+98h+var_78], 0Ah; unsigned int
0x14000e851  lea     r9d, [rbx+3]; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e855  mov     r8, rsi; void *
0x14000e858  lea     rdx, aKeywords; "keywords"
0x14000e85f  mov     rcx, rdi; this
0x14000e862  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e867  mov     [rsp+98h+var_70], 0; wchar_t *
0x14000e870  mov     dword ptr [rsp+98h+var_78], 0Fh; unsigned int
0x14000e878  lea     r9d, [rbx+4]; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x14000e87c  mov     r8, rsi; void *
0x14000e87f  lea     rdx, aControlguid_0; "controlGuid"
0x14000e886  mov     rcx, rdi; this
0x14000e889  call    ?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z; GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)
0x14000e88e  mov     rcx, r14; this
0x14000e891  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000e896  mov     rcx, r14; this
0x14000e899  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14000e89e  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x14000e8a5  lea     rcx, [rsp+98h+arg_0]
0x14000e8ad  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>(void)
0x14000e8b2  add     rsp, 78h
0x14000e8b6  pop     r14
0x14000e8b8  pop     rdi
0x14000e8b9  pop     rsi
0x14000e8ba  pop     rbx
0x14000e8bb  retn
```

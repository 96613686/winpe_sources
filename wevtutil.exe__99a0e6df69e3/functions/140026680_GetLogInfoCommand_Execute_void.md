# GetLogInfoCommand::Execute(void)

- ea: `0x140026680`
- end: `0x140026894`
- name: `?Execute@GetLogInfoCommand@@UEAAXXZ`
- size: `532`
- prototype: `void __fastcall(GetLogInfoCommand *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000cafc`
- `0x14000d900`
- `0x14000dac4`
- `0x14000e8c4`
- `0x14000e924`
- `0x140010450`
- `0x140022cec`
- `0x140026680`
- `0x14002689c`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400266d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400266d1`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenLog` at `0x1400266b7`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenLog` at `0x1400266b7`

## string_xrefs

- `0x1400267af`: `lastAccessTime`
- `0x1400267cf`: `lastWriteTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GetLogInfoCommand::Execute(GetLogInfoCommand *this)
{
  char *Src; // rbx
  const WCHAR *v3; // rdx
  EVT_HANDLE v4; // rsi
  DWORD LastError; // edi
  const char *v6; // [rsp+20h] [rbp-58h]
  const wchar_t *v7; // [rsp+28h] [rbp-50h]
  const wchar_t *v8; // [rsp+28h] [rbp-50h]
  const wchar_t *v9; // [rsp+28h] [rbp-50h]
  const wchar_t *v10; // [rsp+28h] [rbp-50h]
  const wchar_t *v11; // [rsp+28h] [rbp-50h]
  const wchar_t *v12; // [rsp+28h] [rbp-50h]
  const wchar_t *v13; // [rsp+28h] [rbp-50h]
  _BYTE pExceptionObject[48]; // [rsp+40h] [rbp-38h] BYREF
  EVT_HANDLE v15; // [rsp+80h] [rbp+8h] BYREF

  Src = (char *)this + 40;
  if ( *((_QWORD *)this + 8) <= 7u )
    v3 = (const WCHAR *)((char *)this + 40);
  else
    v3 = *(const WCHAR **)Src;
  v4 = EvtOpenLog(*((EVT_HANDLE *)this + 3), v3, (unsigned int)(*((_BYTE *)this + 113) != 0) + 1);
  v15 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ddea4538a2063d21a9f201416765e880_Traceguids, LastError);
    }
    if ( *((_QWORD *)Src + 3) > 7u )
      Src = *(char **)Src;
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v6, 73, 0x1Fu, (const wchar_t *)Src);
    throw (EvtException *)pExceptionObject;
  }
  XmlPrinter::Start((GetLogInfoCommand *)((char *)this + 72), *((void **)this + 2), *((_BYTE *)this + 112));
  XmlPrinter::PrintStartElement((GetLogInfoCommand *)((char *)this + 72), L"log");
  GetLogInfoCommand::GetProperty(this, L"creationTime", v4, EvtLogCreationTime, 0x11u, v7);
  GetLogInfoCommand::GetProperty(this, L"lastAccessTime", v4, EvtLogLastAccessTime, 0x11u, v8);
  GetLogInfoCommand::GetProperty(this, L"lastWriteTime", v4, EvtLogLastWriteTime, 0x11u, v9);
  GetLogInfoCommand::GetProperty(this, L"fileSize", v4, EvtLogFileSize, 0xAu, v10);
  GetLogInfoCommand::GetProperty(this, L"attributes", v4, EvtLogAttributes, 8u, v11);
  GetLogInfoCommand::GetProperty(this, L"numberOfLogRecords", v4, EvtLogNumberOfLogRecords, 0xAu, v12);
  GetLogInfoCommand::GetProperty(this, L"oldestRecordNumber", v4, EvtLogOldestRecordNumber, 0xAu, v13);
  XmlPrinter::PrintStartElementEnd((GetLogInfoCommand *)((char *)this + 72));
  XmlPrinter::PrintEndElement((GetLogInfoCommand *)((char *)this + 72));
  *((_QWORD *)this + 9) = -1;
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v15);
}

```

## disassembly

```asm
0x140026680  mov     [rsp+arg_8], rbx
0x140026685  mov     [rsp+arg_10], rsi
0x14002668a  push    rdi
0x14002668b  sub     rsp, 70h
0x14002668f  mov     rdi, rcx
0x140026692  mov     al, [rcx+71h]
0x140026695  neg     al
0x140026697  sbb     r8d, r8d
0x14002669a  neg     r8d
0x14002669d  inc     r8d; Flags
0x1400266a0  lea     rbx, [rcx+28h]
0x1400266a4  cmp     qword ptr [rbx+18h], 7
0x1400266a9  jbe     short loc_1400266B0
0x1400266ab  mov     rdx, [rbx]
0x1400266ae  jmp     short loc_1400266B3
0x1400266b0  mov     rdx, rbx; Path
0x1400266b3  mov     rcx, [rcx+18h]; Session
0x1400266b7  call    cs:__imp_EvtOpenLog
0x1400266bd  mov     rsi, rax
0x1400266c0  mov     [rsp+78h+arg_0], rax
0x1400266c8  test    rax, rax
0x1400266cb  jnz     loc_14002675E
0x1400266d1  call    cs:__imp_GetLastError
0x1400266d7  mov     edi, eax
0x1400266d9  mov     eax, 507h
0x1400266de  test    edi, edi
0x1400266e0  cmovz   edi, eax
0x1400266e3  lea     rax, WPP_GLOBAL_Control
0x1400266ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400266f1  cmp     rcx, rax
0x1400266f4  jz      short loc_14002671B
0x1400266f6  test    dword ptr [rcx+1Ch], 400000h
0x1400266fd  jz      short loc_14002671B
0x1400266ff  cmp     byte ptr [rcx+19h], 2
0x140026703  jb      short loc_14002671B
0x140026705  lea     edx, [rsi+0Ch]
0x140026708  mov     r9d, edi
0x14002670b  lea     r8, WPP_ddea4538a2063d21a9f201416765e880_Traceguids
0x140026712  mov     rcx, [rcx+10h]
0x140026716  call    WPP_SF_d
0x14002671b  cmp     qword ptr [rbx+18h], 7
0x140026720  jbe     short loc_140026725
0x140026722  mov     rbx, [rbx]
0x140026725  mov     [rsp+78h+Src], rbx; Src
0x14002672a  mov     [rsp+78h+var_48], 1Fh; unsigned int
0x140026732  mov     dword ptr [rsp+78h+var_50], 49h ; 'I'; int
0x14002673a  xor     r9d, r9d; unsigned int
0x14002673d  xor     r8d, r8d; unsigned int
0x140026740  mov     edx, edi; unsigned int
0x140026742  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140026747  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14002674c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026753  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140026758  call    _CxxThrowException_0
0x14002675e  lea     rbx, [rdi+48h]
0x140026762  mov     r8b, [rdi+70h]; bool
0x140026766  mov     rdx, [rdi+10h]; void *
0x14002676a  mov     rcx, rbx; this
0x14002676d  call    ?Start@XmlPrinter@@QEAAXPEAX_N@Z; XmlPrinter::Start(void *,bool)
0x140026772  lea     rdx, aLog; "log"
0x140026779  mov     rcx, rbx; this
0x14002677c  call    ?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z; XmlPrinter::PrintStartElement(wchar_t const *)
0x140026781  mov     dword ptr [rsp+78h+var_58], 11h; unsigned int
0x140026789  xor     r9d, r9d; enum _EVT_LOG_PROPERTY_ID
0x14002678c  mov     r8, rsi; void *
0x14002678f  lea     rdx, aCreationtime; "creationTime"
0x140026796  mov     rcx, rdi; this
0x140026799  call    ?GetProperty@GetLogInfoCommand@@AEAAXPEB_WPEAXW4_EVT_LOG_PROPERTY_ID@@K0@Z; GetLogInfoCommand::GetProperty(wchar_t const *,void *,_EVT_LOG_PROPERTY_ID,ulong,wchar_t const *)
0x14002679e  mov     dword ptr [rsp+78h+var_58], 11h; unsigned int
0x1400267a6  mov     r9d, 1; enum _EVT_LOG_PROPERTY_ID
0x1400267ac  mov     r8, rsi; void *
0x1400267af  lea     rdx, aLastaccesstime; "lastAccessTime"
0x1400267b6  mov     rcx, rdi; this
0x1400267b9  call    ?GetProperty@GetLogInfoCommand@@AEAAXPEB_WPEAXW4_EVT_LOG_PROPERTY_ID@@K0@Z; GetLogInfoCommand::GetProperty(wchar_t const *,void *,_EVT_LOG_PROPERTY_ID,ulong,wchar_t const *)
0x1400267be  mov     dword ptr [rsp+78h+var_58], 11h; unsigned int
0x1400267c6  mov     r9d, 2; enum _EVT_LOG_PROPERTY_ID
0x1400267cc  mov     r8, rsi; void *
0x1400267cf  lea     rdx, aLastwritetime; "lastWriteTime"
0x1400267d6  mov     rcx, rdi; this
0x1400267d9  call    ?GetProperty@GetLogInfoCommand@@AEAAXPEB_WPEAXW4_EVT_LOG_PROPERTY_ID@@K0@Z; GetLogInfoCommand::GetProperty(wchar_t const *,void *,_EVT_LOG_PROPERTY_ID,ulong,wchar_t const *)
0x1400267de  mov     dword ptr [rsp+78h+var_58], 0Ah; unsigned int
0x1400267e6  mov     r9d, 3; enum _EVT_LOG_PROPERTY_ID
0x1400267ec  mov     r8, rsi; void *
0x1400267ef  lea     rdx, aFilesize; "fileSize"
0x1400267f6  mov     rcx, rdi; this
0x1400267f9  call    ?GetProperty@GetLogInfoCommand@@AEAAXPEB_WPEAXW4_EVT_LOG_PROPERTY_ID@@K0@Z; GetLogInfoCommand::GetProperty(wchar_t const *,void *,_EVT_LOG_PROPERTY_ID,ulong,wchar_t const *)
0x1400267fe  mov     dword ptr [rsp+78h+var_58], 8; unsigned int
0x140026806  mov     r9d, 4; enum _EVT_LOG_PROPERTY_ID
0x14002680c  mov     r8, rsi; void *
0x14002680f  lea     rdx, aAttributes; "attributes"
0x140026816  mov     rcx, rdi; this
0x140026819  call    ?GetProperty@GetLogInfoCommand@@AEAAXPEB_WPEAXW4_EVT_LOG_PROPERTY_ID@@K0@Z; GetLogInfoCommand::GetProperty(wchar_t const *,void *,_EVT_LOG_PROPERTY_ID,ulong,wchar_t const *)
0x14002681e  mov     dword ptr [rsp+78h+var_58], 0Ah; unsigned int
0x140026826  mov     r9d, 5; enum _EVT_LOG_PROPERTY_ID
0x14002682c  mov     r8, rsi; void *
0x14002682f  lea     rdx, aNumberoflogrec; "numberOfLogRecords"
0x140026836  mov     rcx, rdi; this
0x140026839  call    ?GetProperty@GetLogInfoCommand@@AEAAXPEB_WPEAXW4_EVT_LOG_PROPERTY_ID@@K0@Z; GetLogInfoCommand::GetProperty(wchar_t const *,void *,_EVT_LOG_PROPERTY_ID,ulong,wchar_t const *)
0x14002683e  mov     dword ptr [rsp+78h+var_58], 0Ah; unsigned int
0x140026846  mov     r9d, 6; enum _EVT_LOG_PROPERTY_ID
0x14002684c  mov     r8, rsi; void *
0x14002684f  lea     rdx, aOldestrecordnu; "oldestRecordNumber"
0x140026856  mov     rcx, rdi; this
0x140026859  call    ?GetProperty@GetLogInfoCommand@@AEAAXPEB_WPEAXW4_EVT_LOG_PROPERTY_ID@@K0@Z; GetLogInfoCommand::GetProperty(wchar_t const *,void *,_EVT_LOG_PROPERTY_ID,ulong,wchar_t const *)
0x14002685e  mov     rcx, rbx; this
0x140026861  call    ?PrintStartElementEnd@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintStartElementEnd(void)
0x140026866  mov     rcx, rbx; this
0x140026869  call    ?PrintEndElement@XmlPrinter@@QEAAXXZ; XmlPrinter::PrintEndElement(void)
0x14002686e  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x140026875  lea     rcx, [rsp+78h+arg_0]
0x14002687d  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>(void)
0x140026882  lea     r11, [rsp+78h+var_8]
0x140026887  mov     rbx, [r11+18h]
0x14002688b  mov     rsi, [r11+20h]
0x14002688f  mov     rsp, r11
0x140026892  pop     rdi
0x140026893  retn
```

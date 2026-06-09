# CUmRdpDr::BackgroundThread(void)

- ea: `0x1800101ec`
- end: `0x180010321`
- name: `?BackgroundThread@CUmRdpDr@@AEAAKXZ`
- size: `309`
- prototype: `unsigned int __fastcall(CUmRdpDr *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180013ba0`

## callees

- `0x1800085bc`
- `0x18000a01c`
- `0x1800101ec`
- `0x1800197e8`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800102b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800102b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800102e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800102e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010296`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010296`
- `ntdll!DbgPrint` at `0x18001022c`
- `ntdll!DbgPrint` at `0x18001022c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800102fd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800102fd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010217`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010217`

## pseudocode

```c
__int64 __fastcall CUmRdpDr::BackgroundThread(DWORD *this)
{
  unsigned int v2; // ebp
  HRESULT v3; // eax
  int v4; // edi
  HANDLE *v5; // rbx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-260h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-248h] BYREF

  v2 = 1;
  v3 = CoInitializeEx(0, 2u);
  v4 = v3;
  if ( v3 >= 0 )
  {
    dwFlagsAndAttributes = *this;
    StringCchPrintfW(FileName, 0x105u, L"\\\\.\\%s%s%ld", L"RdpDrDvMgr", L"\\session", dwFlagsAndAttributes);
    FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0x40000080u, 0);
    v5 = (HANDLE *)(this + 544);
    *((_QWORD *)this + 272) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v2 = 0;
      SetLastError(LastError);
      TsLogError(&EVENT_NOTIFY_PRINTER_REDIRECTION_FAILED, 0, 0);
    }
    else
    {
      CUmRdpDr::MainLoop((CUmRdpDr *)this);
    }
  }
  else
  {
    DbgPrint("Failed in CoInitializeEx - 0x%8x\n", v3);
    v5 = (HANDLE *)(this + 544);
  }
  if ( *v5 != (HANDLE)-1LL )
  {
    if ( CloseHandle(*v5) )
      *v5 = (HANDLE)-1LL;
    else
      GetLastError();
  }
  if ( v4 >= 0 )
    CoUninitialize();
  return v2;
}

```

## disassembly

```asm
0x1800101ec  push    rbx
0x1800101ee  push    rbp
0x1800101ef  push    rsi
0x1800101f0  push    rdi
0x1800101f1  sub     rsp, 268h
0x1800101f8  mov     rax, cs:__security_cookie
0x1800101ff  xor     rax, rsp
0x180010202  mov     [rsp+288h+var_38], rax
0x18001020a  mov     rsi, rcx
0x18001020d  mov     ebp, 1
0x180010212  xor     ecx, ecx; pvReserved
0x180010214  lea     edx, [rbp+1]; dwCoInit
0x180010217  call    cs:__imp_CoInitializeEx
0x18001021d  mov     edi, eax
0x18001021f  test    eax, eax
0x180010221  jns     short loc_18001023E
0x180010223  mov     edx, eax
0x180010225  lea     rcx, Format; "Failed in CoInitializeEx - 0x%8x\n"
0x18001022c  call    cs:__imp_DbgPrint
0x180010232  lea     rbx, [rsi+880h]
0x180010239  jmp     loc_1800102D7
0x18001023e  mov     eax, [rsi]
0x180010240  lea     r9, aRdpdrdvmgr; "RdpDrDvMgr"
0x180010247  mov     [rsp+288h+dwFlagsAndAttributes], eax
0x18001024b  lea     r8, aSSLd; "\\\\.\\%s%s%ld"
0x180010252  lea     rax, aSession; "\\session"
0x180010259  mov     edx, 105h; unsigned __int64
0x18001025e  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x180010263  mov     qword ptr [rsp+288h+dwCreationDisposition], rax
0x180010268  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001026d  mov     r8d, 3; dwShareMode
0x180010273  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x18001027c  mov     [rsp+288h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x180010284  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180010289  xor     r9d, r9d; lpSecurityAttributes
0x18001028c  mov     [rsp+288h+dwCreationDisposition], r8d; dwCreationDisposition
0x180010291  mov     edx, 0C0000000h; dwDesiredAccess
0x180010296  call    cs:__imp_CreateFileW
0x18001029c  lea     rbx, [rsi+880h]
0x1800102a3  mov     [rbx], rax
0x1800102a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800102aa  jnz     short loc_1800102CF
0x1800102ac  call    cs:__imp_GetLastError
0x1800102b2  mov     ecx, eax; dwErrCode
0x1800102b4  xor     ebp, ebp
0x1800102b6  call    cs:__imp_SetLastError
0x1800102bc  xor     r8d, r8d; unsigned __int16 **
0x1800102bf  lea     rcx, EVENT_NOTIFY_PRINTER_REDIRECTION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800102c6  xor     edx, edx; int
0x1800102c8  call    ?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z; TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)
0x1800102cd  jmp     short loc_1800102D7
0x1800102cf  mov     rcx, rsi; this
0x1800102d2  call    ?MainLoop@CUmRdpDr@@AEAAXXZ; CUmRdpDr::MainLoop(void)
0x1800102d7  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800102db  jz      short loc_1800102F9
0x1800102dd  mov     rcx, [rbx]; hObject
0x1800102e0  call    cs:__imp_CloseHandle
0x1800102e6  test    eax, eax
0x1800102e8  jnz     short loc_1800102F2
0x1800102ea  call    cs:__imp_GetLastError
0x1800102f0  jmp     short loc_1800102F9
0x1800102f2  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800102f9  test    edi, edi
0x1800102fb  js      short loc_180010303
0x1800102fd  call    cs:__imp_CoUninitialize
0x180010303  mov     eax, ebp
0x180010305  mov     rcx, [rsp+288h+var_38]
0x18001030d  xor     rcx, rsp; StackCookie
0x180010310  call    __security_check_cookie
0x180010315  add     rsp, 268h
0x18001031c  pop     rdi
0x18001031d  pop     rsi
0x18001031e  pop     rbp
0x18001031f  pop     rbx
0x180010320  retn
```

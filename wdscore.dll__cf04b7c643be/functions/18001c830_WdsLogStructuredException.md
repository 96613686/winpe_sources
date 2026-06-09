# WdsLogStructuredException

- ea: `0x18001c830`
- end: `0x18001ca5f`
- name: `WdsLogStructuredException`
- size: `559`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18001adb0`

## callees

- `0x180002250`
- `0x180019eb8`
- `0x18001a4a8`
- `0x18001b1a4`
- `0x18001b348`
- `0x18001c830`
- `0x18001dc70`
- `0x180022bcc`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c947`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001c935`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001c935`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001ca14`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001ca14`

## string_xrefs

- `0x18001c972`: `Exception (code 0x%08X: %s) occurred at 0x%p in %s (+%p).  Minidump attached (%d bytes) to diagerr.xml and %s.`

## pseudocode

```c
int __fastcall WdsLogStructuredException(struct _EXCEPTION_POINTERS *a1)
{
  __int64 v2; // rsi
  void *v3; // r14
  const WCHAR *ExceptionAddress; // r15
  char *v5; // r13
  __int64 v6; // rcx
  const void *v7; // rax
  PEXCEPTION_RECORD ExceptionRecord; // rcx
  HMODULE v9; // rax
  HMODULE v10; // rbx
  DWORD LastError; // edi
  const WCHAR *lpModuleName; // rbx
  __int64 SystemExceptionString; // rax
  __int64 v14; // r8
  LPCVOID v15; // r12
  const char *v16; // rdx
  int *v17; // rax
  int result; // eax
  DWORD ExceptionCode; // [rsp+60h] [rbp-A0h]
  _ULARGE_INTEGER v20; // [rsp+68h] [rbp-98h] BYREF
  void *v21; // [rsp+70h] [rbp-90h] BYREF
  void *v22; // [rsp+78h] [rbp-88h] BYREF
  LPCVOID lpBaseAddress; // [rsp+80h] [rbp-80h]
  WCHAR Filename[10]; // [rsp+90h] [rbp-70h] BYREF
  char v25[508]; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned __int16 v26[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v20.QuadPart = 0;
  v2 = -1;
  wcscpy(Filename, L"<unknown>");
  v21 = (void *)-1LL;
  v22 = 0;
  lpBaseAddress = 0;
  v3 = 0;
  ExceptionCode = 0;
  ExceptionAddress = 0;
  v5 = 0;
  memset_0(v25, 0, 0x1F4u);
  memset_0(v26, 0, 0x208u);
  if ( (unsigned int)CreateMiniDumpFileName(v6, v26) )
  {
    v7 = BeginMiniDump(a1, v26, &v21, &v20, &v22);
    v2 = (__int64)v21;
    v3 = v22;
    lpBaseAddress = v7;
  }
  if ( a1 )
  {
    ExceptionRecord = a1->ExceptionRecord;
    if ( a1->ExceptionRecord )
    {
      ExceptionAddress = (const WCHAR *)ExceptionRecord->ExceptionAddress;
      ExceptionCode = ExceptionRecord->ExceptionCode;
    }
    v9 = (HMODULE)pIPtoHModule(ExceptionAddress);
    v10 = v9;
    if ( v9 )
    {
      GetModuleFileNameW(v9, Filename, 0x104u);
      v5 = (char *)((char *)ExceptionAddress - (char *)v10);
    }
  }
  LastError = GetLastError();
  lpModuleName = (const WCHAR *)a1->ContextRecord->Rip;
  SystemExceptionString = pGetSystemExceptionString(ExceptionCode);
  v15 = lpBaseAddress;
  v16 = "Exception (code 0x%08X: %s) occurred at 0x%p in %s (+%p).  Minidump attached (%d bytes) to diagerr.xml and %s.";
  if ( !lpBaseAddress )
    v16 = "Exception (code 0x%08X: %s) occurred at 0x%p in %s (+%p).";
  v17 = (int *)ConstructPartialMsgW(
                 0x1000001u,
                 v16,
                 v14,
                 SystemExceptionString,
                 ExceptionAddress,
                 Filename,
                 v5,
                 v20.LowPart,
                 v26);
  result = WdsSetupLogMessageW(
             v17,
             589824,
             (__int64)L"D",
             (__int64)&byte_180030077,
             0,
             L"<unknown>",
             L"WdsLogStructuredException",
             lpModuleName,
             LastError,
             (__int64)v15,
             v20.LowPart);
  if ( v15 )
  {
    result = UnmapViewOfFile(v15);
    if ( v3 )
      result = CloseHandleWrapper(v3);
    if ( v2 != -1 )
      return CloseHandleWrapper(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18001c830  push    rbp
0x18001c832  push    rbx
0x18001c833  push    rsi
0x18001c834  push    rdi
0x18001c835  push    r12
0x18001c837  push    r13
0x18001c839  push    r14
0x18001c83b  push    r15
0x18001c83d  lea     rbp, [rsp-3C8h]
0x18001c845  sub     rsp, 4C8h
0x18001c84c  mov     rax, cs:__security_cookie
0x18001c853  xor     rax, rsp
0x18001c856  mov     [rbp+400h+var_50], rax
0x18001c85d  movups  xmm0, xmmword ptr cs:aUnknown; "<unknown>"
0x18001c864  mov     eax, dword ptr cs:aUnknown+10h; ">"
0x18001c86a  xor     edi, edi
0x18001c86c  mov     r12, rcx
0x18001c86f  mov     qword ptr [rsp+500h+var_498], rdi
0x18001c874  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001c878  movaps  xmmword ptr [rbp+400h+Filename], xmm0
0x18001c87c  xor     edx, edx; Val
0x18001c87e  mov     [rsp+500h+var_490], rsi
0x18001c883  mov     r8d, 1F4h; Size
0x18001c889  mov     [rsp+500h+var_488], rdi
0x18001c88e  lea     rcx, [rbp+400h+var_45C]; void *
0x18001c892  mov     [rbp+400h+lpBaseAddress], rdi
0x18001c896  mov     r14d, edi
0x18001c899  mov     [rsp+500h+var_4A0], edi
0x18001c89d  mov     r15d, edi
0x18001c8a0  mov     [rbp+400h+var_460], eax
0x18001c8a3  mov     r13d, edi
0x18001c8a6  call    memset_0
0x18001c8ab  xor     edx, edx; Val
0x18001c8ad  lea     rcx, [rbp+400h+var_260]; void *
0x18001c8b4  mov     r8d, 208h; Size
0x18001c8ba  call    memset_0
0x18001c8bf  lea     rdx, [rbp+400h+var_260]; unsigned __int16 *
0x18001c8c6  call    ?CreateMiniDumpFileName@@YAHIPEAG@Z; CreateMiniDumpFileName(uint,ushort *)
0x18001c8cb  test    eax, eax
0x18001c8cd  jz      short loc_18001C900
0x18001c8cf  lea     rax, [rsp+500h+var_488]
0x18001c8d4  mov     rcx, r12; struct _EXCEPTION_POINTERS *
0x18001c8d7  lea     r9, [rsp+500h+var_498]; union _ULARGE_INTEGER *
0x18001c8dc  mov     [rsp+500h+var_4E0], rax; void **
0x18001c8e1  lea     r8, [rsp+500h+var_490]; void **
0x18001c8e6  lea     rdx, [rbp+400h+var_260]; unsigned __int16 *
0x18001c8ed  call    ?BeginMiniDump@@YAPEAXPEAU_EXCEPTION_POINTERS@@PEBGPEAPEAXPEAT_ULARGE_INTEGER@@2@Z; BeginMiniDump(_EXCEPTION_POINTERS *,ushort const *,void * *,_ULARGE_INTEGER *,void * *)
0x18001c8f2  mov     rsi, [rsp+500h+var_490]
0x18001c8f7  mov     r14, [rsp+500h+var_488]
0x18001c8fc  mov     [rbp+400h+lpBaseAddress], rax
0x18001c900  test    r12, r12
0x18001c903  jz      short loc_18001C947
0x18001c905  mov     rcx, [r12]
0x18001c909  test    rcx, rcx
0x18001c90c  jz      short loc_18001C918
0x18001c90e  mov     eax, [rcx]
0x18001c910  mov     r15, [rcx+10h]
0x18001c914  mov     [rsp+500h+var_4A0], eax
0x18001c918  mov     rcx, r15; lpModuleName
0x18001c91b  call    pIPtoHModule
0x18001c920  mov     rbx, rax
0x18001c923  test    rax, rax
0x18001c926  jz      short loc_18001C947
0x18001c928  mov     r8d, 104h; nSize
0x18001c92e  lea     rdx, [rbp+400h+Filename]; lpFilename
0x18001c932  mov     rcx, rax; hModule
0x18001c935  call    cs:__imp_GetModuleFileNameW
0x18001c93c  nop     dword ptr [rax+rax+00h]
0x18001c941  mov     r13, r15
0x18001c944  sub     r13, rbx
0x18001c947  call    cs:__imp_GetLastError
0x18001c94e  nop     dword ptr [rax+rax+00h]
0x18001c953  mov     rcx, [r12+8]
0x18001c958  mov     edi, eax
0x18001c95a  mov     r8d, [rsp+500h+var_4A0]
0x18001c95f  mov     rbx, [rcx+0F8h]
0x18001c966  mov     ecx, r8d
0x18001c969  call    pGetSystemExceptionString
0x18001c96e  mov     r12, [rbp+400h+lpBaseAddress]
0x18001c972  lea     rdx, aExceptionCode0_0; "Exception (code 0x%08X: %s) occurred at"...
0x18001c979  mov     r9, rax
0x18001c97c  test    r12, r12
0x18001c97f  lea     rax, aExceptionCode0_1; "Exception (code 0x%08X: %s) occurred at"...
0x18001c986  mov     ecx, 1000001h; unsigned int
0x18001c98b  cmovz   rdx, rax; char *
0x18001c98f  lea     rax, [rbp+400h+var_260]
0x18001c996  mov     qword ptr [rsp+500h+var_4C0], rax
0x18001c99b  mov     eax, dword ptr [rsp+500h+var_498]
0x18001c99f  mov     dword ptr [rsp+500h+lpModuleName], eax
0x18001c9a3  lea     rax, [rbp+400h+Filename]
0x18001c9a7  mov     [rsp+500h+var_4D0], r13
0x18001c9ac  mov     [rsp+500h+var_4D8], rax
0x18001c9b1  mov     [rsp+500h+var_4E0], r15
0x18001c9b6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001c9bb  mov     ecx, dword ptr [rsp+500h+var_498]
0x18001c9bf  lea     r9, byte_180030077; int
0x18001c9c6  mov     [rsp+500h+var_4B0], ecx; int
0x18001c9ca  lea     r8, aD_1; "D"
0x18001c9d1  mov     [rsp+500h+var_4B8], r12; __int64
0x18001c9d6  lea     rcx, aWdslogstructur_0; "WdsLogStructuredException"
0x18001c9dd  mov     [rsp+500h+var_4C0], edi; int
0x18001c9e1  mov     edx, 90000h; int
0x18001c9e6  mov     [rsp+500h+lpModuleName], rbx; lpModuleName
0x18001c9eb  mov     [rsp+500h+var_4D0], rcx; __int64
0x18001c9f0  lea     rcx, aUnknown; "<unknown>"
0x18001c9f7  mov     [rsp+500h+var_4D8], rcx; unsigned __int16 *
0x18001c9fc  mov     rcx, rax; int
0x18001c9ff  mov     dword ptr [rsp+500h+var_4E0], 0; int
0x18001ca07  call    WdsSetupLogMessageW
0x18001ca0c  test    r12, r12
0x18001ca0f  jz      short loc_18001CA3B
0x18001ca11  mov     rcx, r12; lpBaseAddress
0x18001ca14  call    cs:__imp_UnmapViewOfFile
0x18001ca1b  nop     dword ptr [rax+rax+00h]
0x18001ca20  test    r14, r14
0x18001ca23  jz      short loc_18001CA2D
0x18001ca25  mov     rcx, r14
0x18001ca28  call    CloseHandleWrapper
0x18001ca2d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001ca31  jz      short loc_18001CA3B
0x18001ca33  mov     rcx, rsi
0x18001ca36  call    CloseHandleWrapper
0x18001ca3b  mov     rcx, [rbp+400h+var_50]
0x18001ca42  xor     rcx, rsp; StackCookie
0x18001ca45  call    __security_check_cookie
0x18001ca4a  add     rsp, 4C8h
0x18001ca51  pop     r15
0x18001ca53  pop     r14
0x18001ca55  pop     r13
0x18001ca57  pop     r12
0x18001ca59  pop     rdi
0x18001ca5a  pop     rsi
0x18001ca5b  pop     rbx
0x18001ca5c  pop     rbp
0x18001ca5d  retn
```

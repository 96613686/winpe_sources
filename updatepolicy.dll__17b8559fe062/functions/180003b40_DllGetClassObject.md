# DllGetClassObject

- ea: `0x180003b40`
- end: `0x180003bfb`
- name: `DllGetClassObject`
- size: `187`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003984`
- `0x180003b40`
- `0x180005a1c`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003b74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003b74`

## string_xrefs

- `0x180003b6d`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int Dll; // eax
  FARPROC ProcAddress; // rbp
  signed int LastError; // eax
  __int64 v9; // r9
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Dll = UndockedModuleForwarder::LoadDll((UndockedModuleForwarder *)rclsid);
  if ( Dll < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)(unsigned int)Dll,
      v11);
  ProcAddress = GetProcAddress(hLibModule, "DllGetClassObject");
  LastError = GetLastError();
  v9 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v9 = (unsigned int)LastError;
  if ( (int)v9 >= 0 )
    v9 = 2147549183LL;
  if ( !ProcAddress )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)v9,
      v11);
  return ((__int64 (__fastcall *)(const IID *const, const IID *const, LPVOID *, __int64))ProcAddress)(
           rclsid,
           riid,
           ppv,
           v9);
}

```

## disassembly

```asm
0x180003b40  mov     [rsp+arg_0], rbx
0x180003b45  mov     [rsp+arg_8], rbp
0x180003b4a  mov     [rsp+arg_10], rsi
0x180003b4f  push    rdi; int
0x180003b50  sub     rsp, 20h
0x180003b54  mov     rbx, r8
0x180003b57  mov     rdi, rdx
0x180003b5a  mov     rsi, rcx
0x180003b5d  call    ?LoadDll@UndockedModuleForwarder@@AEAAJXZ; UndockedModuleForwarder::LoadDll(void)
0x180003b62  test    eax, eax
0x180003b64  js      short loc_180003BE1
0x180003b66  mov     rcx, cs:hLibModule; hModule
0x180003b6d  lea     rdx, ProcName; "DllGetClassObject"
0x180003b74  call    cs:__imp_GetProcAddress
0x180003b7a  mov     rbp, rax
0x180003b7d  call    cs:__imp_GetLastError
0x180003b83  movzx   r9d, ax
0x180003b87  or      r9d, 80070000h
0x180003b8e  test    eax, eax
0x180003b90  cmovle  r9d, eax
0x180003b94  mov     eax, 8000FFFFh
0x180003b99  test    r9d, r9d
0x180003b9c  cmovns  r9d, eax; char *
0x180003ba0  test    rbp, rbp
0x180003ba3  jz      short loc_180003BCA
0x180003ba5  mov     r8, rbx
0x180003ba8  mov     rdx, rdi
0x180003bab  mov     rcx, rsi
0x180003bae  mov     rax, rbp
0x180003bb1  mov     rbx, [rsp+28h+arg_0]
0x180003bb6  mov     rbp, [rsp+28h+arg_8]
0x180003bbb  mov     rsi, [rsp+28h+arg_10]
0x180003bc0  add     rsp, 20h
0x180003bc4  pop     rdi
0x180003bc5  jmp     _guard_dispatch_icall
0x180003bca  mov     rcx, [rsp+28h]; this
0x180003bcf  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003bd6  mov     edx, 7Ah ; 'z'; void *
0x180003bdb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180003be1  mov     rcx, [rsp+28h]; this
0x180003be6  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003bed  mov     r9d, eax; char *
0x180003bf0  mov     edx, 74h ; 't'; void *
0x180003bf5  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

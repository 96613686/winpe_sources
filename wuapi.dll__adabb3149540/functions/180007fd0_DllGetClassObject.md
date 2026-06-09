# DllGetClassObject

- ea: `0x180007fd0`
- end: `0x18000808b`
- name: `DllGetClassObject`
- size: `187`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007b64`
- `0x180007fd0`
- `0x18000a140`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008004`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000800d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000800d`

## string_xrefs

- `0x180007ffd`: `DllGetClassObject`

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
0x180007fd0  mov     [rsp+arg_0], rbx
0x180007fd5  mov     [rsp+arg_8], rbp
0x180007fda  mov     [rsp+arg_10], rsi
0x180007fdf  push    rdi; int
0x180007fe0  sub     rsp, 20h
0x180007fe4  mov     rbx, r8
0x180007fe7  mov     rdi, rdx
0x180007fea  mov     rsi, rcx
0x180007fed  call    ?LoadDll@UndockedModuleForwarder@@AEAAJXZ; UndockedModuleForwarder::LoadDll(void)
0x180007ff2  test    eax, eax
0x180007ff4  js      short loc_180008071
0x180007ff6  mov     rcx, cs:hLibModule; hModule
0x180007ffd  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180008004  call    cs:__imp_GetProcAddress
0x18000800a  mov     rbp, rax
0x18000800d  call    cs:__imp_GetLastError
0x180008013  movzx   r9d, ax
0x180008017  or      r9d, 80070000h
0x18000801e  test    eax, eax
0x180008020  cmovle  r9d, eax
0x180008024  mov     eax, 8000FFFFh
0x180008029  test    r9d, r9d
0x18000802c  cmovns  r9d, eax; char *
0x180008030  test    rbp, rbp
0x180008033  jz      short loc_18000805A
0x180008035  mov     r8, rbx
0x180008038  mov     rdx, rdi
0x18000803b  mov     rcx, rsi
0x18000803e  mov     rax, rbp
0x180008041  mov     rbx, [rsp+28h+arg_0]
0x180008046  mov     rbp, [rsp+28h+arg_8]
0x18000804b  mov     rsi, [rsp+28h+arg_10]
0x180008050  add     rsp, 20h
0x180008054  pop     rdi
0x180008055  jmp     _guard_dispatch_icall
0x18000805a  mov     rcx, [rsp+28h]; this
0x18000805f  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180008066  mov     edx, 7Ah ; 'z'; void *
0x18000806b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180008071  mov     rcx, [rsp+28h]; this
0x180008076  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x18000807d  mov     r9d, eax; char *
0x180008080  mov     edx, 74h ; 't'; void *
0x180008085  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

# WUServiceMain

- ea: `0x180006790`
- end: `0x180006839`
- name: `WUServiceMain`
- size: `169`
- prototype: `__int64 __fastcall(UndockedModuleForwarder *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180005d80`
- `0x180006790`
- `0x180008ac8`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800067bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800067bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067c4`

## string_xrefs

- `0x1800067b4`: `WUServiceMain`

## pseudocode

```c
__int64 __fastcall WUServiceMain(UndockedModuleForwarder *a1, __int64 a2)
{
  unsigned int v3; // edi
  int Dll; // eax
  FARPROC ProcAddress; // rsi
  signed int LastError; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = (unsigned int)a1;
  Dll = UndockedModuleForwarder::LoadDll(a1);
  if ( Dll < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)(unsigned int)Dll,
      v10);
  ProcAddress = GetProcAddress(hLibModule, "WUServiceMain");
  LastError = GetLastError();
  v8 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v8 = (unsigned int)LastError;
  if ( (int)v8 >= 0 )
    v8 = 2147549183LL;
  if ( !ProcAddress )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)v8,
      v10);
  return ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64))ProcAddress)(v3, a2, v7, v8);
}

```

## disassembly

```asm
0x180006790  mov     [rsp+arg_0], rbx
0x180006795  mov     [rsp+arg_8], rsi
0x18000679a  push    rdi; int
0x18000679b  sub     rsp, 20h
0x18000679f  mov     rbx, rdx
0x1800067a2  mov     edi, ecx
0x1800067a4  call    ?LoadDll@UndockedModuleForwarder@@AEAAJXZ; UndockedModuleForwarder::LoadDll(void)
0x1800067a9  test    eax, eax
0x1800067ab  js      short loc_18000681F
0x1800067ad  mov     rcx, cs:hLibModule; hModule
0x1800067b4  lea     rdx, aWuservicemain_0; "WUServiceMain"
0x1800067bb  call    cs:__imp_GetProcAddress
0x1800067c1  mov     rsi, rax
0x1800067c4  call    cs:__imp_GetLastError
0x1800067ca  movzx   r9d, ax
0x1800067ce  or      r9d, 80070000h
0x1800067d5  test    eax, eax
0x1800067d7  cmovle  r9d, eax
0x1800067db  mov     eax, 8000FFFFh
0x1800067e0  test    r9d, r9d
0x1800067e3  cmovns  r9d, eax; char *
0x1800067e7  test    rsi, rsi
0x1800067ea  jz      short loc_180006808
0x1800067ec  mov     rdx, rbx
0x1800067ef  mov     ecx, edi
0x1800067f1  mov     rax, rsi
0x1800067f4  mov     rbx, [rsp+28h+arg_0]
0x1800067f9  mov     rsi, [rsp+28h+arg_8]
0x1800067fe  add     rsp, 20h
0x180006802  pop     rdi
0x180006803  jmp     _guard_dispatch_icall
0x180006808  mov     rcx, [rsp+28h]; this
0x18000680d  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180006814  mov     edx, 37h ; '7'; void *
0x180006819  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000681f  mov     rcx, [rsp+28h]; this
0x180006824  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x18000682b  mov     r9d, eax; char *
0x18000682e  mov     edx, 31h ; '1'; void *
0x180006833  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

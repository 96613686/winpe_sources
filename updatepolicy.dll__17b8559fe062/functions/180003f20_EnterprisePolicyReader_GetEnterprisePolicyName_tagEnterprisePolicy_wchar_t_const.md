# EnterprisePolicyReader::GetEnterprisePolicyName(tagEnterprisePolicy,wchar_t const * *)

- ea: `0x180003f20`
- end: `0x180003fc9`
- name: `?GetEnterprisePolicyName@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEB_W@Z`
- size: `169`
- prototype: `__int64 __fastcall(UndockedModuleForwarder *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180003984`
- `0x180003f20`
- `0x180005a1c`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f4b`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::GetEnterprisePolicyName(UndockedModuleForwarder *a1, __int64 a2)
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
      (int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)(unsigned int)Dll,
      v10);
  ProcAddress = GetProcAddress(hLibModule, "GetEnterprisePolicyName");
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
      (int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)v8,
      v10);
  return ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64))ProcAddress)(v3, a2, v7, v8);
}

```

## disassembly

```asm
0x180003f20  mov     [rsp+arg_0], rbx
0x180003f25  mov     [rsp+arg_8], rsi
0x180003f2a  push    rdi; int
0x180003f2b  sub     rsp, 20h
0x180003f2f  mov     rbx, rdx
0x180003f32  mov     edi, ecx
0x180003f34  call    ?LoadDll@UndockedModuleForwarder@@AEAAJXZ; UndockedModuleForwarder::LoadDll(void)
0x180003f39  test    eax, eax
0x180003f3b  js      short loc_180003FAF
0x180003f3d  mov     rcx, cs:hLibModule; hModule
0x180003f44  lea     rdx, aGetenterprisep_0; "GetEnterprisePolicyName"
0x180003f4b  call    cs:__imp_GetProcAddress
0x180003f51  mov     rsi, rax
0x180003f54  call    cs:__imp_GetLastError
0x180003f5a  movzx   r9d, ax
0x180003f5e  or      r9d, 80070000h
0x180003f65  test    eax, eax
0x180003f67  cmovle  r9d, eax
0x180003f6b  mov     eax, 8000FFFFh
0x180003f70  test    r9d, r9d
0x180003f73  cmovns  r9d, eax; char *
0x180003f77  test    rsi, rsi
0x180003f7a  jz      short loc_180003F98
0x180003f7c  mov     rdx, rbx
0x180003f7f  mov     ecx, edi
0x180003f81  mov     rax, rsi
0x180003f84  mov     rbx, [rsp+28h+arg_0]
0x180003f89  mov     rsi, [rsp+28h+arg_8]
0x180003f8e  add     rsp, 20h
0x180003f92  pop     rdi
0x180003f93  jmp     _guard_dispatch_icall
0x180003f98  mov     rcx, [rsp+28h]; this
0x180003f9d  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003fa4  mov     edx, 37h ; '7'; void *
0x180003fa9  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180003faf  mov     rcx, [rsp+28h]; this
0x180003fb4  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003fbb  mov     r9d, eax; char *
0x180003fbe  mov     edx, 31h ; '1'; void *
0x180003fc3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

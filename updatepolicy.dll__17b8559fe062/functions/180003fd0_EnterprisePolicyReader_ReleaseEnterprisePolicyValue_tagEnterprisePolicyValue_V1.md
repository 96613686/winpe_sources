# EnterprisePolicyReader::ReleaseEnterprisePolicyValue(tagEnterprisePolicyValue_V1 * *)

- ea: `0x180003fd0`
- end: `0x18000406b`
- name: `?ReleaseEnterprisePolicyValue@EnterprisePolicyReader@@SAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180003984`
- `0x180003fd0`
- `0x180005a1c`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ffd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ff4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ff4`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReleaseEnterprisePolicyValue(struct tagEnterprisePolicyValue_V1 **a1)
{
  int Dll; // eax
  FARPROC ProcAddress; // rdi
  signed int LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Dll = UndockedModuleForwarder::LoadDll((UndockedModuleForwarder *)a1);
  if ( Dll < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x31,
      (int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)(unsigned int)Dll,
      v9);
  ProcAddress = GetProcAddress(hLibModule, "ReleaseEnterprisePolicyValue");
  LastError = GetLastError();
  v7 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v7 = (unsigned int)LastError;
  if ( (int)v7 >= 0 )
    v7 = 2147549183LL;
  if ( !ProcAddress )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x37,
      (int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleForwarder.h",
      (const char *)v7,
      v9);
  return ((__int64 (__fastcall *)(struct tagEnterprisePolicyValue_V1 **, __int64, __int64, __int64))ProcAddress)(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x180003fd0  mov     [rsp+arg_0], rbx
0x180003fd5  push    rdi; int
0x180003fd6  sub     rsp, 20h
0x180003fda  mov     rbx, rcx
0x180003fdd  call    ?LoadDll@UndockedModuleForwarder@@AEAAJXZ; UndockedModuleForwarder::LoadDll(void)
0x180003fe2  test    eax, eax
0x180003fe4  js      short loc_180004051
0x180003fe6  mov     rcx, cs:hLibModule; hModule
0x180003fed  lea     rdx, aReleaseenterpr_0; "ReleaseEnterprisePolicyValue"
0x180003ff4  call    cs:__imp_GetProcAddress
0x180003ffa  mov     rdi, rax
0x180003ffd  call    cs:__imp_GetLastError
0x180004003  movzx   r9d, ax
0x180004007  or      r9d, 80070000h
0x18000400e  test    eax, eax
0x180004010  cmovle  r9d, eax
0x180004014  mov     eax, 8000FFFFh
0x180004019  test    r9d, r9d
0x18000401c  cmovns  r9d, eax; char *
0x180004020  test    rdi, rdi
0x180004023  jz      short loc_18000403A
0x180004025  mov     rcx, rbx
0x180004028  mov     rax, rdi
0x18000402b  mov     rbx, [rsp+28h+arg_0]
0x180004030  add     rsp, 20h
0x180004034  pop     rdi
0x180004035  jmp     _guard_dispatch_icall
0x18000403a  mov     rcx, [rsp+28h]; this
0x18000403f  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180004046  mov     edx, 37h ; '7'; void *
0x18000404b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180004051  mov     rcx, [rsp+28h]; this
0x180004056  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x18000405d  mov     r9d, eax; char *
0x180004060  mov     edx, 31h ; '1'; void *
0x180004065  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

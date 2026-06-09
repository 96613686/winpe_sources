# UpdatePolicyReader::GetUpdatePolicyName(tagUpdatePolicy,wchar_t const * *)

- ea: `0x180003e70`
- end: `0x180003f19`
- name: `?GetUpdatePolicyName@UpdatePolicyReader@@SAJW4tagUpdatePolicy@@PEAPEB_W@Z`
- size: `169`
- prototype: `__int64 __fastcall(UndockedModuleForwarder *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180003984`
- `0x180003e70`
- `0x180005a1c`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ea4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003e9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003e9b`

## string_xrefs

- `0x180003e94`: `GetUpdatePolicyName`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::GetUpdatePolicyName(UndockedModuleForwarder *a1, __int64 a2)
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
  ProcAddress = GetProcAddress(hLibModule, "GetUpdatePolicyName");
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
0x180003e70  mov     [rsp+arg_0], rbx
0x180003e75  mov     [rsp+arg_8], rsi
0x180003e7a  push    rdi; int
0x180003e7b  sub     rsp, 20h
0x180003e7f  mov     rbx, rdx
0x180003e82  mov     edi, ecx
0x180003e84  call    ?LoadDll@UndockedModuleForwarder@@AEAAJXZ; UndockedModuleForwarder::LoadDll(void)
0x180003e89  test    eax, eax
0x180003e8b  js      short loc_180003EFF
0x180003e8d  mov     rcx, cs:hLibModule; hModule
0x180003e94  lea     rdx, aGetupdatepolic_0; "GetUpdatePolicyName"
0x180003e9b  call    cs:__imp_GetProcAddress
0x180003ea1  mov     rsi, rax
0x180003ea4  call    cs:__imp_GetLastError
0x180003eaa  movzx   r9d, ax
0x180003eae  or      r9d, 80070000h
0x180003eb5  test    eax, eax
0x180003eb7  cmovle  r9d, eax
0x180003ebb  mov     eax, 8000FFFFh
0x180003ec0  test    r9d, r9d
0x180003ec3  cmovns  r9d, eax; char *
0x180003ec7  test    rsi, rsi
0x180003eca  jz      short loc_180003EE8
0x180003ecc  mov     rdx, rbx
0x180003ecf  mov     ecx, edi
0x180003ed1  mov     rax, rsi
0x180003ed4  mov     rbx, [rsp+28h+arg_0]
0x180003ed9  mov     rsi, [rsp+28h+arg_8]
0x180003ede  add     rsp, 20h
0x180003ee2  pop     rdi
0x180003ee3  jmp     _guard_dispatch_icall
0x180003ee8  mov     rcx, [rsp+28h]; this
0x180003eed  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003ef4  mov     edx, 37h ; '7'; void *
0x180003ef9  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180003eff  mov     rcx, [rsp+28h]; this
0x180003f04  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180003f0b  mov     r9d, eax; char *
0x180003f0e  mov     edx, 31h ; '1'; void *
0x180003f13  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

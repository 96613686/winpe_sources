# ReadAthenaMailSettings(char *,char *)

- ea: `0x180012ea4`
- end: `0x180012fce`
- name: `?ReadAthenaMailSettings@@YAHPEAD0@Z`
- size: `298`
- prototype: `__int64 __fastcall(char *, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012fd4`
- `0x180013058`

## callees

- `0x180012ea4`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180012ee8`
- `ole32!CoCreateInstance` at `0x180012ee8`
- `ole32!CoUninitialize` at `0x180012fb1`
- `ole32!CoUninitialize` at `0x180012fb1`
- `ole32!CoInitialize` at `0x180012ebb`
- `ole32!CoInitialize` at `0x180012ebb`

## pseudocode

```c
_BOOL8 __fastcall ReadAthenaMailSettings(char *a1, char *a2)
{
  HRESULT v4; // ebx
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  CoInitialize(0);
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_ImnAccountManager, 0, 1u, &IID_IImnAccountManager, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
    if ( v4 >= 0 )
    {
      v6 = 0;
      v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 64LL))(ppv, 1, &v6);
      if ( !v4 )
      {
        if ( !a2
          || (v4 = (*(__int64 (__fastcall **)(__int64, __int64, char *, __int64))(*(_QWORD *)v6 + 40LL))(
                     v6,
                     338166768,
                     a2,
                     256),
              v4 >= 0) )
        {
          if ( a1 )
            v4 = (*(__int64 (__fastcall **)(__int64, __int64, char *, __int64))(*(_QWORD *)v6 + 40LL))(
                   v6,
                   338822128,
                   a1,
                   256);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  CoUninitialize();
  return v4 == 0;
}

```

## disassembly

```asm
0x180012ea4  mov     [rsp+arg_0], rbx
0x180012ea9  mov     [rsp+arg_8], rsi
0x180012eae  push    rdi
0x180012eaf  sub     rsp, 30h
0x180012eb3  mov     rsi, rcx
0x180012eb6  mov     rdi, rdx
0x180012eb9  xor     ecx, ecx; pvReserved
0x180012ebb  call    cs:__imp_CoInitialize
0x180012ec1  xor     edx, edx; pUnkOuter
0x180012ec3  mov     [rsp+38h+arg_18], 0
0x180012ecc  lea     rax, [rsp+38h+arg_18]
0x180012ed1  lea     r9, IID_IImnAccountManager; riid
0x180012ed8  mov     [rsp+38h+ppv], rax; ppv
0x180012edd  lea     rcx, CLSID_ImnAccountManager; rclsid
0x180012ee4  lea     r8d, [rdx+1]; dwClsContext
0x180012ee8  call    cs:__imp_CoCreateInstance
0x180012eee  mov     ebx, eax
0x180012ef0  test    eax, eax
0x180012ef2  js      loc_180012FB1
0x180012ef8  mov     rcx, [rsp+38h+arg_18]
0x180012efd  xor     edx, edx
0x180012eff  mov     rax, [rcx]
0x180012f02  mov     rax, [rax+18h]
0x180012f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f0b  mov     ebx, eax
0x180012f0d  test    eax, eax
0x180012f0f  js      loc_180012FA0
0x180012f15  mov     rcx, [rsp+38h+arg_18]
0x180012f1a  lea     r8, [rsp+38h+arg_10]
0x180012f1f  mov     [rsp+38h+arg_10], 0
0x180012f28  mov     edx, 1
0x180012f2d  mov     rax, [rcx]
0x180012f30  mov     rax, [rax+40h]
0x180012f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f39  mov     ebx, eax
0x180012f3b  test    eax, eax
0x180012f3d  jnz     short loc_180012FA0
0x180012f3f  test    rdi, rdi
0x180012f42  jz      short loc_180012F69
0x180012f44  mov     rcx, [rsp+38h+arg_10]
0x180012f49  mov     r9d, 100h
0x180012f4f  mov     r8, rdi
0x180012f52  mov     edx, 142803F0h
0x180012f57  mov     rax, [rcx]
0x180012f5a  mov     rax, [rax+28h]
0x180012f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f63  mov     ebx, eax
0x180012f65  test    eax, eax
0x180012f67  js      short loc_180012F8F
0x180012f69  test    rsi, rsi
0x180012f6c  jz      short loc_180012F8F
0x180012f6e  mov     rcx, [rsp+38h+arg_10]
0x180012f73  mov     r9d, 100h
0x180012f79  mov     r8, rsi
0x180012f7c  mov     edx, 143203F0h
0x180012f81  mov     rax, [rcx]
0x180012f84  mov     rax, [rax+28h]
0x180012f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f8d  mov     ebx, eax
0x180012f8f  mov     rcx, [rsp+38h+arg_10]
0x180012f94  mov     rax, [rcx]
0x180012f97  mov     rax, [rax+10h]
0x180012f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fa0  mov     rcx, [rsp+38h+arg_18]
0x180012fa5  mov     rax, [rcx]
0x180012fa8  mov     rax, [rax+10h]
0x180012fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fb1  call    cs:__imp_CoUninitialize
0x180012fb7  mov     rsi, [rsp+38h+arg_8]
0x180012fbc  xor     eax, eax
0x180012fbe  test    ebx, ebx
0x180012fc0  mov     rbx, [rsp+38h+arg_0]
0x180012fc5  setz    al
0x180012fc8  add     rsp, 30h
0x180012fcc  pop     rdi
0x180012fcd  retn
```

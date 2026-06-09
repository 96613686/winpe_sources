# CElevationConfig::GetElevated(ISPPLUA * *)

- ea: `0x180003e14`
- end: `0x180003ed1`
- name: `?GetElevated@CElevationConfig@@QEAAJPEAPEAUISPPLUA@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(CElevationConfig *__hidden this, struct ISPPLUA **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004790`
- `0x180004880`

## callees

- `0x180003520`
- `0x180003540`
- `0x180003e14`
- `0x1800041c8`
- `0x180004288`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003ec3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003ec3`

## pseudocode

```c
__int64 __fastcall CElevationConfig::GetElevated(CElevationConfig *this, struct ISPPLUA **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  LPVOID *ppv; // rdi
  const struct _GUID *v7; // rdx
  const struct _GUID *v8; // r8
  HRESULT Instance; // eax

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2147942487LL;
LABEL_10:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_11;
  }
  ppv = (LPVOID *)((char *)this + 144);
  if ( !*((_QWORD *)this + 18)
    && (*((_DWORD *)this + 34) == 2 || IsUserAdmin()
      ? (Instance = CoCreateInstance(&CLSID_SPPLUAObject, 0, 0x17u, &IID_ISPPLUA, ppv))
      : (Instance = CoCreateInstanceAsAdmin(*((HWND *)this + 19), v7, v8, ppv)),
        v4 = Instance,
        Instance < 0)
    || (Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ISPPLUA **))*ppv)(*ppv, &IID_ISPPLUA, a2),
        v4 = Instance,
        Instance < 0) )
  {
    v5 = (unsigned int)Instance;
    goto LABEL_10;
  }
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x180003e14  mov     [rsp+arg_0], rbx
0x180003e19  mov     [rsp+arg_8], rsi
0x180003e1e  push    rdi
0x180003e1f  sub     rsp, 30h
0x180003e23  mov     rsi, rdx
0x180003e26  mov     rbx, rcx
0x180003e29  test    rdx, rdx
0x180003e2c  jnz     short loc_180003E37
0x180003e2e  mov     ebx, 80070057h
0x180003e33  mov     ecx, ebx
0x180003e35  jmp     short loc_180003E8B
0x180003e37  lea     rdi, [rcx+90h]
0x180003e3e  cmp     qword ptr [rdi], 0
0x180003e42  jnz     short loc_180003E6B
0x180003e44  cmp     dword ptr [rcx+88h], 2
0x180003e4b  jz      short loc_180003EAA
0x180003e4d  call    ?IsUserAdmin@@YAHXZ; IsUserAdmin(void)
0x180003e52  test    eax, eax
0x180003e54  jnz     short loc_180003EAA
0x180003e56  mov     rcx, [rbx+98h]; HWND
0x180003e5d  mov     r9, rdi; void **
0x180003e60  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180003e65  mov     ebx, eax
0x180003e67  test    eax, eax
0x180003e69  js      short loc_180003E89
0x180003e6b  mov     rcx, [rdi]
0x180003e6e  lea     rdx, IID_ISPPLUA
0x180003e75  mov     r8, rsi
0x180003e78  mov     rax, [rcx]
0x180003e7b  mov     rax, [rax]
0x180003e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e83  mov     ebx, eax
0x180003e85  test    eax, eax
0x180003e87  jns     short loc_180003E90
0x180003e89  mov     ecx, eax
0x180003e8b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003e90  mov     ecx, ebx
0x180003e92  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003e97  mov     rsi, [rsp+38h+arg_8]
0x180003e9c  mov     eax, ebx
0x180003e9e  mov     rbx, [rsp+38h+arg_0]
0x180003ea3  add     rsp, 30h
0x180003ea7  pop     rdi
0x180003ea8  retn
0x180003eaa  xor     edx, edx; pUnkOuter
0x180003eac  mov     [rsp+38h+ppv], rdi; ppv
0x180003eb1  lea     r9, IID_ISPPLUA; riid
0x180003eb8  lea     rcx, CLSID_SPPLUAObject; rclsid
0x180003ebf  lea     r8d, [rdx+17h]; dwClsContext
0x180003ec3  call    cs:__imp_CoCreateInstance
0x180003eca  nop     dword ptr [rax+rax+00h]
0x180003ecf  jmp     short loc_180003E65
```

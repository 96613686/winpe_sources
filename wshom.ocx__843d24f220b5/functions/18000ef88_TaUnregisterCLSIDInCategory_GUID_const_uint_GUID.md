# TaUnregisterCLSIDInCategory(_GUID const &,uint,_GUID *)

- ea: `0x18000ef88`
- end: `0x18000f017`
- name: `?TaUnregisterCLSIDInCategory@@YAJAEBU_GUID@@IPEAU1@@Z`
- size: `143`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e1b0`

## callees

- `0x18000ef88`
- `0x180011010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000efce`
- `ole32!CoCreateInstance` at `0x18000efce`

## pseudocode

```c
HRESULT __fastcall TaUnregisterCLSIDInCategory(const struct _GUID *a1, unsigned int a2, struct _GUID *a3)
{
  HRESULT result; // eax
  int v7; // ebx
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  if ( !a2 )
    return 0;
  ppv = 0;
  result = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv);
  if ( result >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, _QWORD, struct _GUID *))(*(_QWORD *)ppv + 48LL))(
           ppv,
           a1,
           a2,
           a3);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000ef88  mov     [rsp+arg_0], rbx
0x18000ef8d  mov     [rsp+arg_8], rsi
0x18000ef92  push    rdi
0x18000ef93  sub     rsp, 30h
0x18000ef97  mov     rdi, r8
0x18000ef9a  mov     ebx, edx
0x18000ef9c  mov     rsi, rcx
0x18000ef9f  test    edx, edx
0x18000efa1  jnz     short loc_18000EFA7
0x18000efa3  xor     eax, eax
0x18000efa5  jmp     short loc_18000F007
0x18000efa7  xor     edx, edx; pUnkOuter
0x18000efa9  mov     [rsp+38h+arg_18], 0
0x18000efb2  lea     rax, [rsp+38h+arg_18]
0x18000efb7  lea     r9, IID_ICatRegister; riid
0x18000efbe  mov     [rsp+38h+ppv], rax; ppv
0x18000efc3  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000efca  lea     r8d, [rdx+1]; dwClsContext
0x18000efce  call    cs:__imp_CoCreateInstance
0x18000efd4  test    eax, eax
0x18000efd6  js      short loc_18000F007
0x18000efd8  mov     rcx, [rsp+38h+arg_18]
0x18000efdd  mov     r9, rdi
0x18000efe0  mov     r8d, ebx
0x18000efe3  mov     rdx, rsi
0x18000efe6  mov     rax, [rcx]
0x18000efe9  mov     rax, [rax+30h]
0x18000efed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eff2  mov     rcx, [rsp+38h+arg_18]
0x18000eff7  mov     ebx, eax
0x18000eff9  mov     rdx, [rcx]
0x18000effc  mov     rax, [rdx+10h]
0x18000f000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f005  mov     eax, ebx
0x18000f007  mov     rbx, [rsp+38h+arg_0]
0x18000f00c  mov     rsi, [rsp+38h+arg_8]
0x18000f011  add     rsp, 30h
0x18000f015  pop     rdi
0x18000f016  retn
```

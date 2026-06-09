# TaRegisterCLSIDInCategory(_GUID const &,uint,_GUID *)

- ea: `0x18000eef0`
- end: `0x18000ef7f`
- name: `?TaRegisterCLSIDInCategory@@YAJAEBU_GUID@@IPEAU1@@Z`
- size: `143`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int, struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e1b0`
- `0x18000e280`

## callees

- `0x18000eef0`
- `0x180011010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000ef36`
- `ole32!CoCreateInstance` at `0x18000ef36`

## pseudocode

```c
HRESULT __fastcall TaRegisterCLSIDInCategory(const struct _GUID *a1, unsigned int a2, struct _GUID *a3)
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
    v7 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, _QWORD, struct _GUID *))(*(_QWORD *)ppv + 40LL))(
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
0x18000eef0  mov     [rsp+arg_0], rbx
0x18000eef5  mov     [rsp+arg_8], rsi
0x18000eefa  push    rdi
0x18000eefb  sub     rsp, 30h
0x18000eeff  mov     rdi, r8
0x18000ef02  mov     ebx, edx
0x18000ef04  mov     rsi, rcx
0x18000ef07  test    edx, edx
0x18000ef09  jnz     short loc_18000EF0F
0x18000ef0b  xor     eax, eax
0x18000ef0d  jmp     short loc_18000EF6F
0x18000ef0f  xor     edx, edx; pUnkOuter
0x18000ef11  mov     [rsp+38h+arg_18], 0
0x18000ef1a  lea     rax, [rsp+38h+arg_18]
0x18000ef1f  lea     r9, IID_ICatRegister; riid
0x18000ef26  mov     [rsp+38h+ppv], rax; ppv
0x18000ef2b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000ef32  lea     r8d, [rdx+1]; dwClsContext
0x18000ef36  call    cs:__imp_CoCreateInstance
0x18000ef3c  test    eax, eax
0x18000ef3e  js      short loc_18000EF6F
0x18000ef40  mov     rcx, [rsp+38h+arg_18]
0x18000ef45  mov     r9, rdi
0x18000ef48  mov     r8d, ebx
0x18000ef4b  mov     rdx, rsi
0x18000ef4e  mov     rax, [rcx]
0x18000ef51  mov     rax, [rax+28h]
0x18000ef55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef5a  mov     rcx, [rsp+38h+arg_18]
0x18000ef5f  mov     ebx, eax
0x18000ef61  mov     rdx, [rcx]
0x18000ef64  mov     rax, [rdx+10h]
0x18000ef68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef6d  mov     eax, ebx
0x18000ef6f  mov     rbx, [rsp+38h+arg_0]
0x18000ef74  mov     rsi, [rsp+38h+arg_8]
0x18000ef79  add     rsp, 30h
0x18000ef7d  pop     rdi
0x18000ef7e  retn
```

# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180027ba0`
- end: `0x180027c15`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180027ba0`
- `0x180058010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180027be2`
- `ole32!CoCreateInstance` at `0x180027be2`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // edi
  _QWORD *v5; // rbx

  if ( !a2 )
    return 2147500035LL;
  Instance = 0;
  v5 = (_QWORD *)((char *)this + 64);
  if ( *((_QWORD *)this + 8)
    || (Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)this + 8),
        Instance >= 0) )
  {
    *a2 = (struct IGlobalInterfaceTable *)*v5;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180027ba0  mov     [rsp+arg_0], rbx
0x180027ba5  mov     [rsp+arg_8], rsi
0x180027baa  push    rdi
0x180027bab  sub     rsp, 30h
0x180027baf  mov     rsi, rdx
0x180027bb2  test    rdx, rdx
0x180027bb5  jnz     short loc_180027BBE
0x180027bb7  mov     eax, 80004003h
0x180027bbc  jmp     short loc_180027C05
0x180027bbe  xor     edi, edi
0x180027bc0  lea     rbx, [rcx+40h]
0x180027bc4  cmp     [rbx], rdi
0x180027bc7  jnz     short loc_180027BEE
0x180027bc9  mov     [rsp+38h+ppv], rbx; ppv
0x180027bce  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180027bd5  xor     edx, edx; pUnkOuter
0x180027bd7  lea     r8d, [rdi+1]; dwClsContext
0x180027bdb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180027be2  call    cs:__imp_CoCreateInstance
0x180027be8  mov     edi, eax
0x180027bea  test    eax, eax
0x180027bec  js      short loc_180027C03
0x180027bee  mov     rcx, [rbx]
0x180027bf1  mov     [rsi], rcx
0x180027bf4  mov     rcx, [rbx]
0x180027bf7  mov     rdx, [rcx]
0x180027bfa  mov     rax, [rdx+8]
0x180027bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c03  mov     eax, edi
0x180027c05  mov     rbx, [rsp+38h+arg_0]
0x180027c0a  mov     rsi, [rsp+38h+arg_8]
0x180027c0f  add     rsp, 30h
0x180027c13  pop     rdi
0x180027c14  retn
```

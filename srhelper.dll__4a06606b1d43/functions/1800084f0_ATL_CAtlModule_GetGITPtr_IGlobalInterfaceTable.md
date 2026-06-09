# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800084f0`
- end: `0x180008565`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800084f0`
- `0x180016010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180008532`
- `ole32!CoCreateInstance` at `0x180008532`

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
0x1800084f0  mov     [rsp+arg_0], rbx
0x1800084f5  mov     [rsp+arg_8], rsi
0x1800084fa  push    rdi
0x1800084fb  sub     rsp, 30h
0x1800084ff  mov     rsi, rdx
0x180008502  test    rdx, rdx
0x180008505  jnz     short loc_18000850E
0x180008507  mov     eax, 80004003h
0x18000850c  jmp     short loc_180008555
0x18000850e  xor     edi, edi
0x180008510  lea     rbx, [rcx+40h]
0x180008514  cmp     [rbx], rdi
0x180008517  jnz     short loc_18000853E
0x180008519  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180008520  mov     [rsp+38h+ppv], rbx; ppv
0x180008525  xor     edx, edx; pUnkOuter
0x180008527  lea     r8d, [rdi+1]; dwClsContext
0x18000852b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180008532  call    cs:__imp_CoCreateInstance
0x180008538  mov     edi, eax
0x18000853a  test    eax, eax
0x18000853c  js      short loc_180008553
0x18000853e  mov     rcx, [rbx]
0x180008541  mov     [rsi], rcx
0x180008544  mov     rcx, [rbx]
0x180008547  mov     rdx, [rcx]
0x18000854a  mov     rax, [rdx+8]
0x18000854e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008553  mov     eax, edi
0x180008555  mov     rbx, [rsp+38h+arg_0]
0x18000855a  mov     rsi, [rsp+38h+arg_8]
0x18000855f  add     rsp, 30h
0x180008563  pop     rdi
0x180008564  retn
```

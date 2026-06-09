# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800093e0`
- end: `0x180009455`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800093e0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009422`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009422`

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
0x1800093e0  mov     [rsp+arg_0], rbx
0x1800093e5  mov     [rsp+arg_8], rsi
0x1800093ea  push    rdi
0x1800093eb  sub     rsp, 30h
0x1800093ef  mov     rsi, rdx
0x1800093f2  test    rdx, rdx
0x1800093f5  jnz     short loc_1800093FE
0x1800093f7  mov     eax, 80004003h
0x1800093fc  jmp     short loc_180009445
0x1800093fe  xor     edi, edi
0x180009400  lea     rbx, [rcx+40h]
0x180009404  cmp     [rbx], rdi
0x180009407  jnz     short loc_18000942E
0x180009409  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009410  mov     [rsp+38h+ppv], rbx; ppv
0x180009415  xor     edx, edx; pUnkOuter
0x180009417  lea     r8d, [rdi+1]; dwClsContext
0x18000941b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009422  call    cs:__imp_CoCreateInstance
0x180009428  mov     edi, eax
0x18000942a  test    eax, eax
0x18000942c  js      short loc_180009443
0x18000942e  mov     rcx, [rbx]
0x180009431  mov     [rsi], rcx
0x180009434  mov     rcx, [rbx]
0x180009437  mov     rdx, [rcx]
0x18000943a  mov     rax, [rdx+8]
0x18000943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009443  mov     eax, edi
0x180009445  mov     rbx, [rsp+38h+arg_0]
0x18000944a  mov     rsi, [rsp+38h+arg_8]
0x18000944f  add     rsp, 30h
0x180009453  pop     rdi
0x180009454  retn
```

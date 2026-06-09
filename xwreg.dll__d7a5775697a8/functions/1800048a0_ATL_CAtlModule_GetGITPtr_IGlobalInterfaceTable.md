# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800048a0`
- end: `0x180004915`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800048a0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800048e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800048e2`

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
0x1800048a0  mov     [rsp+arg_0], rbx
0x1800048a5  mov     [rsp+arg_8], rsi
0x1800048aa  push    rdi
0x1800048ab  sub     rsp, 30h
0x1800048af  mov     rsi, rdx
0x1800048b2  test    rdx, rdx
0x1800048b5  jnz     short loc_1800048BE
0x1800048b7  mov     eax, 80004003h
0x1800048bc  jmp     short loc_180004905
0x1800048be  xor     edi, edi
0x1800048c0  lea     rbx, [rcx+40h]
0x1800048c4  cmp     [rbx], rdi
0x1800048c7  jnz     short loc_1800048EE
0x1800048c9  mov     [rsp+38h+ppv], rbx; ppv
0x1800048ce  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800048d5  xor     edx, edx; pUnkOuter
0x1800048d7  lea     r8d, [rdi+1]; dwClsContext
0x1800048db  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800048e2  call    cs:__imp_CoCreateInstance
0x1800048e8  mov     edi, eax
0x1800048ea  test    eax, eax
0x1800048ec  js      short loc_180004903
0x1800048ee  mov     rcx, [rbx]
0x1800048f1  mov     [rsi], rcx
0x1800048f4  mov     rcx, [rbx]
0x1800048f7  mov     rdx, [rcx]
0x1800048fa  mov     rax, [rdx+8]
0x1800048fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004903  mov     eax, edi
0x180004905  mov     rbx, [rsp+38h+arg_0]
0x18000490a  mov     rsi, [rsp+38h+arg_8]
0x18000490f  add     rsp, 30h
0x180004913  pop     rdi
0x180004914  retn
```

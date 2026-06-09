# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180006730`
- end: `0x1800067a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006730`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006772`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006772`

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
0x180006730  mov     [rsp+arg_0], rbx
0x180006735  mov     [rsp+arg_8], rsi
0x18000673a  push    rdi
0x18000673b  sub     rsp, 30h
0x18000673f  mov     rsi, rdx
0x180006742  test    rdx, rdx
0x180006745  jnz     short loc_18000674E
0x180006747  mov     eax, 80004003h
0x18000674c  jmp     short loc_180006795
0x18000674e  xor     edi, edi
0x180006750  lea     rbx, [rcx+40h]
0x180006754  cmp     [rbx], rdi
0x180006757  jnz     short loc_18000677E
0x180006759  mov     [rsp+38h+ppv], rbx; ppv
0x18000675e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006765  xor     edx, edx; pUnkOuter
0x180006767  lea     r8d, [rdi+1]; dwClsContext
0x18000676b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006772  call    cs:__imp_CoCreateInstance
0x180006778  mov     edi, eax
0x18000677a  test    eax, eax
0x18000677c  js      short loc_180006793
0x18000677e  mov     rcx, [rbx]
0x180006781  mov     [rsi], rcx
0x180006784  mov     rcx, [rbx]
0x180006787  mov     rdx, [rcx]
0x18000678a  mov     rax, [rdx+8]
0x18000678e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006793  mov     eax, edi
0x180006795  mov     rbx, [rsp+38h+arg_0]
0x18000679a  mov     rsi, [rsp+38h+arg_8]
0x18000679f  add     rsp, 30h
0x1800067a3  pop     rdi
0x1800067a4  retn
```

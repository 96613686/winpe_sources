# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180005270`
- end: `0x1800052e5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005270`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800052b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800052b2`

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
0x180005270  mov     [rsp+arg_0], rbx
0x180005275  mov     [rsp+arg_8], rsi
0x18000527a  push    rdi
0x18000527b  sub     rsp, 30h
0x18000527f  mov     rsi, rdx
0x180005282  test    rdx, rdx
0x180005285  jnz     short loc_18000528E
0x180005287  mov     eax, 80004003h
0x18000528c  jmp     short loc_1800052D5
0x18000528e  xor     edi, edi
0x180005290  lea     rbx, [rcx+40h]
0x180005294  cmp     [rbx], rdi
0x180005297  jnz     short loc_1800052BE
0x180005299  mov     [rsp+38h+ppv], rbx; ppv
0x18000529e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800052a5  xor     edx, edx; pUnkOuter
0x1800052a7  lea     r8d, [rdi+1]; dwClsContext
0x1800052ab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800052b2  call    cs:__imp_CoCreateInstance
0x1800052b8  mov     edi, eax
0x1800052ba  test    eax, eax
0x1800052bc  js      short loc_1800052D3
0x1800052be  mov     rcx, [rbx]
0x1800052c1  mov     [rsi], rcx
0x1800052c4  mov     rcx, [rbx]
0x1800052c7  mov     rdx, [rcx]
0x1800052ca  mov     rax, [rdx+8]
0x1800052ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d3  mov     eax, edi
0x1800052d5  mov     rbx, [rsp+38h+arg_0]
0x1800052da  mov     rsi, [rsp+38h+arg_8]
0x1800052df  add     rsp, 30h
0x1800052e3  pop     rdi
0x1800052e4  retn
```

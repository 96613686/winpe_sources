# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800113e0`
- end: `0x18001145c`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800113e0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011422`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011422`

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
0x1800113e0  mov     [rsp+arg_0], rbx
0x1800113e5  mov     [rsp+arg_8], rsi
0x1800113ea  push    rdi
0x1800113eb  sub     rsp, 30h
0x1800113ef  mov     rsi, rdx
0x1800113f2  test    rdx, rdx
0x1800113f5  jnz     short loc_1800113FE
0x1800113f7  mov     eax, 80004003h
0x1800113fc  jmp     short loc_18001144B
0x1800113fe  xor     edi, edi
0x180011400  lea     rbx, [rcx+40h]
0x180011404  cmp     [rbx], rdi
0x180011407  jnz     short loc_180011434
0x180011409  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180011410  mov     [rsp+38h+ppv], rbx; ppv
0x180011415  xor     edx, edx; pUnkOuter
0x180011417  lea     r8d, [rdi+1]; dwClsContext
0x18001141b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180011422  call    cs:__imp_CoCreateInstance
0x180011429  nop     dword ptr [rax+rax+00h]
0x18001142e  mov     edi, eax
0x180011430  test    eax, eax
0x180011432  js      short loc_180011449
0x180011434  mov     rcx, [rbx]
0x180011437  mov     [rsi], rcx
0x18001143a  mov     rcx, [rbx]
0x18001143d  mov     rdx, [rcx]
0x180011440  mov     rax, [rdx+8]
0x180011444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011449  mov     eax, edi
0x18001144b  mov     rbx, [rsp+38h+arg_0]
0x180011450  mov     rsi, [rsp+38h+arg_8]
0x180011455  add     rsp, 30h
0x180011459  pop     rdi
0x18001145a  retn
```

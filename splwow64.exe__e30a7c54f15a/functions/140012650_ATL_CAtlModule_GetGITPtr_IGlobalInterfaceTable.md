# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x140012650`
- end: `0x1400126c5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140012650`
- `0x140016010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140012692`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140012692`

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
0x140012650  mov     [rsp+arg_0], rbx
0x140012655  mov     [rsp+arg_8], rsi
0x14001265a  push    rdi
0x14001265b  sub     rsp, 30h
0x14001265f  mov     rsi, rdx
0x140012662  test    rdx, rdx
0x140012665  jnz     short loc_14001266E
0x140012667  mov     eax, 80004003h
0x14001266c  jmp     short loc_1400126B5
0x14001266e  xor     edi, edi
0x140012670  lea     rbx, [rcx+40h]
0x140012674  cmp     [rbx], rdi
0x140012677  jnz     short loc_14001269E
0x140012679  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x140012680  mov     [rsp+38h+ppv], rbx; ppv
0x140012685  xor     edx, edx; pUnkOuter
0x140012687  lea     r8d, [rdi+1]; dwClsContext
0x14001268b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x140012692  call    cs:__imp_CoCreateInstance
0x140012698  mov     edi, eax
0x14001269a  test    eax, eax
0x14001269c  js      short loc_1400126B3
0x14001269e  mov     rcx, [rbx]
0x1400126a1  mov     [rsi], rcx
0x1400126a4  mov     rcx, [rbx]
0x1400126a7  mov     rdx, [rcx]
0x1400126aa  mov     rax, [rdx+8]
0x1400126ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126b3  mov     eax, edi
0x1400126b5  mov     rbx, [rsp+38h+arg_0]
0x1400126ba  mov     rsi, [rsp+38h+arg_8]
0x1400126bf  add     rsp, 30h
0x1400126c3  pop     rdi
0x1400126c4  retn
```

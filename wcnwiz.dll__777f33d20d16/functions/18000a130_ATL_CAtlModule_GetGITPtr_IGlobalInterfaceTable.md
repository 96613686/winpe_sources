# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000a130`
- end: `0x18000a1a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a130`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a172`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a172`

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
0x18000a130  mov     [rsp+arg_0], rbx
0x18000a135  mov     [rsp+arg_8], rsi
0x18000a13a  push    rdi
0x18000a13b  sub     rsp, 30h
0x18000a13f  mov     rsi, rdx
0x18000a142  test    rdx, rdx
0x18000a145  jnz     short loc_18000A14E
0x18000a147  mov     eax, 80004003h
0x18000a14c  jmp     short loc_18000A195
0x18000a14e  xor     edi, edi
0x18000a150  lea     rbx, [rcx+40h]
0x18000a154  cmp     [rbx], rdi
0x18000a157  jnz     short loc_18000A17E
0x18000a159  mov     [rsp+38h+ppv], rbx; ppv
0x18000a15e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000a165  xor     edx, edx; pUnkOuter
0x18000a167  lea     r8d, [rdi+1]; dwClsContext
0x18000a16b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000a172  call    cs:__imp_CoCreateInstance
0x18000a178  mov     edi, eax
0x18000a17a  test    eax, eax
0x18000a17c  js      short loc_18000A193
0x18000a17e  mov     rcx, [rbx]
0x18000a181  mov     [rsi], rcx
0x18000a184  mov     rcx, [rbx]
0x18000a187  mov     rdx, [rcx]
0x18000a18a  mov     rax, [rdx+8]
0x18000a18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a193  mov     eax, edi
0x18000a195  mov     rbx, [rsp+38h+arg_0]
0x18000a19a  mov     rsi, [rsp+38h+arg_8]
0x18000a19f  add     rsp, 30h
0x18000a1a3  pop     rdi
0x18000a1a4  retn
```

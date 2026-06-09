# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000a2b0`
- end: `0x18000a325`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a2b0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a2f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a2f2`

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
0x18000a2b0  mov     [rsp+arg_0], rbx
0x18000a2b5  mov     [rsp+arg_8], rsi
0x18000a2ba  push    rdi
0x18000a2bb  sub     rsp, 30h
0x18000a2bf  mov     rsi, rdx
0x18000a2c2  test    rdx, rdx
0x18000a2c5  jnz     short loc_18000A2CE
0x18000a2c7  mov     eax, 80004003h
0x18000a2cc  jmp     short loc_18000A315
0x18000a2ce  xor     edi, edi
0x18000a2d0  lea     rbx, [rcx+40h]
0x18000a2d4  cmp     [rbx], rdi
0x18000a2d7  jnz     short loc_18000A2FE
0x18000a2d9  mov     [rsp+38h+ppv], rbx; ppv
0x18000a2de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000a2e5  xor     edx, edx; pUnkOuter
0x18000a2e7  lea     r8d, [rdi+1]; dwClsContext
0x18000a2eb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000a2f2  call    cs:__imp_CoCreateInstance
0x18000a2f8  mov     edi, eax
0x18000a2fa  test    eax, eax
0x18000a2fc  js      short loc_18000A313
0x18000a2fe  mov     rcx, [rbx]
0x18000a301  mov     [rsi], rcx
0x18000a304  mov     rcx, [rbx]
0x18000a307  mov     rdx, [rcx]
0x18000a30a  mov     rax, [rdx+8]
0x18000a30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a313  mov     eax, edi
0x18000a315  mov     rbx, [rsp+38h+arg_0]
0x18000a31a  mov     rsi, [rsp+38h+arg_8]
0x18000a31f  add     rsp, 30h
0x18000a323  pop     rdi
0x18000a324  retn
```

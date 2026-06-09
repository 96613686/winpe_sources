# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800043c0`
- end: `0x18000443c`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800043c0`
- `0x180020010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004402`
- `ole32!CoCreateInstance` at `0x180004402`

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
0x1800043c0  mov     [rsp+arg_0], rbx
0x1800043c5  mov     [rsp+arg_8], rsi
0x1800043ca  push    rdi
0x1800043cb  sub     rsp, 30h
0x1800043cf  mov     rsi, rdx
0x1800043d2  test    rdx, rdx
0x1800043d5  jnz     short loc_1800043DE
0x1800043d7  mov     eax, 80004003h
0x1800043dc  jmp     short loc_18000442B
0x1800043de  xor     edi, edi
0x1800043e0  lea     rbx, [rcx+40h]
0x1800043e4  cmp     [rbx], rdi
0x1800043e7  jnz     short loc_180004414
0x1800043e9  mov     [rsp+38h+ppv], rbx; ppv
0x1800043ee  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800043f5  xor     edx, edx; pUnkOuter
0x1800043f7  lea     r8d, [rdi+1]; dwClsContext
0x1800043fb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004402  call    cs:__imp_CoCreateInstance
0x180004409  nop     dword ptr [rax+rax+00h]
0x18000440e  mov     edi, eax
0x180004410  test    eax, eax
0x180004412  js      short loc_180004429
0x180004414  mov     rcx, [rbx]
0x180004417  mov     [rsi], rcx
0x18000441a  mov     rcx, [rbx]
0x18000441d  mov     rdx, [rcx]
0x180004420  mov     rax, [rdx+8]
0x180004424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004429  mov     eax, edi
0x18000442b  mov     rbx, [rsp+38h+arg_0]
0x180004430  mov     rsi, [rsp+38h+arg_8]
0x180004435  add     rsp, 30h
0x180004439  pop     rdi
0x18000443a  retn
```

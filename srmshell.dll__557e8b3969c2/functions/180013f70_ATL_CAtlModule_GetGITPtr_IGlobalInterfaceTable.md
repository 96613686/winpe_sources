# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180013f70`
- end: `0x180013fe5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180013f70`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013fb2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013fb2`

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
0x180013f70  mov     [rsp+arg_0], rbx
0x180013f75  mov     [rsp+arg_8], rsi
0x180013f7a  push    rdi
0x180013f7b  sub     rsp, 30h
0x180013f7f  mov     rsi, rdx
0x180013f82  test    rdx, rdx
0x180013f85  jnz     short loc_180013F8E
0x180013f87  mov     eax, 80004003h
0x180013f8c  jmp     short loc_180013FD5
0x180013f8e  xor     edi, edi
0x180013f90  lea     rbx, [rcx+40h]
0x180013f94  cmp     [rbx], rdi
0x180013f97  jnz     short loc_180013FBE
0x180013f99  mov     [rsp+38h+ppv], rbx; ppv
0x180013f9e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180013fa5  xor     edx, edx; pUnkOuter
0x180013fa7  lea     r8d, [rdi+1]; dwClsContext
0x180013fab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180013fb2  call    cs:__imp_CoCreateInstance
0x180013fb8  mov     edi, eax
0x180013fba  test    eax, eax
0x180013fbc  js      short loc_180013FD3
0x180013fbe  mov     rcx, [rbx]
0x180013fc1  mov     [rsi], rcx
0x180013fc4  mov     rcx, [rbx]
0x180013fc7  mov     rdx, [rcx]
0x180013fca  mov     rax, [rdx+8]
0x180013fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fd3  mov     eax, edi
0x180013fd5  mov     rbx, [rsp+38h+arg_0]
0x180013fda  mov     rsi, [rsp+38h+arg_8]
0x180013fdf  add     rsp, 30h
0x180013fe3  pop     rdi
0x180013fe4  retn
```

# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180030030`
- end: `0x1800300a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180030030`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030072`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030072`

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
0x180030030  mov     [rsp+arg_0], rbx
0x180030035  mov     [rsp+arg_8], rsi
0x18003003a  push    rdi
0x18003003b  sub     rsp, 30h
0x18003003f  mov     rsi, rdx
0x180030042  test    rdx, rdx
0x180030045  jnz     short loc_18003004E
0x180030047  mov     eax, 80004003h
0x18003004c  jmp     short loc_180030095
0x18003004e  xor     edi, edi
0x180030050  lea     rbx, [rcx+40h]
0x180030054  cmp     [rbx], rdi
0x180030057  jnz     short loc_18003007E
0x180030059  mov     [rsp+38h+ppv], rbx; ppv
0x18003005e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180030065  xor     edx, edx; pUnkOuter
0x180030067  lea     r8d, [rdi+1]; dwClsContext
0x18003006b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180030072  call    cs:__imp_CoCreateInstance
0x180030078  mov     edi, eax
0x18003007a  test    eax, eax
0x18003007c  js      short loc_180030093
0x18003007e  mov     rcx, [rbx]
0x180030081  mov     [rsi], rcx
0x180030084  mov     rcx, [rbx]
0x180030087  mov     rdx, [rcx]
0x18003008a  mov     rax, [rdx+8]
0x18003008e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030093  mov     eax, edi
0x180030095  mov     rbx, [rsp+38h+arg_0]
0x18003009a  mov     rsi, [rsp+38h+arg_8]
0x18003009f  add     rsp, 30h
0x1800300a3  pop     rdi
0x1800300a4  retn
```

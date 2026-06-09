# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180003120`
- end: `0x180003195`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003120`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003162`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003162`

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
0x180003120  mov     [rsp+arg_0], rbx
0x180003125  mov     [rsp+arg_8], rsi
0x18000312a  push    rdi
0x18000312b  sub     rsp, 30h
0x18000312f  mov     rsi, rdx
0x180003132  test    rdx, rdx
0x180003135  jnz     short loc_18000313E
0x180003137  mov     eax, 80004003h
0x18000313c  jmp     short loc_180003185
0x18000313e  xor     edi, edi
0x180003140  lea     rbx, [rcx+40h]
0x180003144  cmp     [rbx], rdi
0x180003147  jnz     short loc_18000316E
0x180003149  mov     [rsp+38h+ppv], rbx; ppv
0x18000314e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003155  xor     edx, edx; pUnkOuter
0x180003157  lea     r8d, [rdi+1]; dwClsContext
0x18000315b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003162  call    cs:__imp_CoCreateInstance
0x180003168  mov     edi, eax
0x18000316a  test    eax, eax
0x18000316c  js      short loc_180003183
0x18000316e  mov     rcx, [rbx]
0x180003171  mov     [rsi], rcx
0x180003174  mov     rcx, [rbx]
0x180003177  mov     rdx, [rcx]
0x18000317a  mov     rax, [rdx+8]
0x18000317e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003183  mov     eax, edi
0x180003185  mov     rbx, [rsp+38h+arg_0]
0x18000318a  mov     rsi, [rsp+38h+arg_8]
0x18000318f  add     rsp, 30h
0x180003193  pop     rdi
0x180003194  retn
```

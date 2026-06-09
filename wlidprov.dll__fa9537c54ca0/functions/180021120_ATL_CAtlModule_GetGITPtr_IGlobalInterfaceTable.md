# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180021120`
- end: `0x180021195`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180021120`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021162`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021162`

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
0x180021120  mov     [rsp+arg_0], rbx
0x180021125  mov     [rsp+arg_8], rsi
0x18002112a  push    rdi
0x18002112b  sub     rsp, 30h
0x18002112f  mov     rsi, rdx
0x180021132  test    rdx, rdx
0x180021135  jnz     short loc_18002113E
0x180021137  mov     eax, 80004003h
0x18002113c  jmp     short loc_180021185
0x18002113e  xor     edi, edi
0x180021140  lea     rbx, [rcx+40h]
0x180021144  cmp     [rbx], rdi
0x180021147  jnz     short loc_18002116E
0x180021149  mov     [rsp+38h+ppv], rbx; ppv
0x18002114e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180021155  xor     edx, edx; pUnkOuter
0x180021157  lea     r8d, [rdi+1]; dwClsContext
0x18002115b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180021162  call    cs:__imp_CoCreateInstance
0x180021168  mov     edi, eax
0x18002116a  test    eax, eax
0x18002116c  js      short loc_180021183
0x18002116e  mov     rcx, [rbx]
0x180021171  mov     [rsi], rcx
0x180021174  mov     rcx, [rbx]
0x180021177  mov     rdx, [rcx]
0x18002117a  mov     rax, [rdx+8]
0x18002117e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021183  mov     eax, edi
0x180021185  mov     rbx, [rsp+38h+arg_0]
0x18002118a  mov     rsi, [rsp+38h+arg_8]
0x18002118f  add     rsp, 30h
0x180021193  pop     rdi
0x180021194  retn
```

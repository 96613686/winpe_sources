# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18001c9b0`
- end: `0x18001ca25`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001c9b0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c9f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c9f2`

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
0x18001c9b0  mov     [rsp+arg_0], rbx
0x18001c9b5  mov     [rsp+arg_8], rsi
0x18001c9ba  push    rdi
0x18001c9bb  sub     rsp, 30h
0x18001c9bf  mov     rsi, rdx
0x18001c9c2  test    rdx, rdx
0x18001c9c5  jnz     short loc_18001C9CE
0x18001c9c7  mov     eax, 80004003h
0x18001c9cc  jmp     short loc_18001CA15
0x18001c9ce  xor     edi, edi
0x18001c9d0  lea     rbx, [rcx+40h]
0x18001c9d4  cmp     [rbx], rdi
0x18001c9d7  jnz     short loc_18001C9FE
0x18001c9d9  mov     [rsp+38h+ppv], rbx; ppv
0x18001c9de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18001c9e5  xor     edx, edx; pUnkOuter
0x18001c9e7  lea     r8d, [rdi+1]; dwClsContext
0x18001c9eb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001c9f2  call    cs:__imp_CoCreateInstance
0x18001c9f8  mov     edi, eax
0x18001c9fa  test    eax, eax
0x18001c9fc  js      short loc_18001CA13
0x18001c9fe  mov     rcx, [rbx]
0x18001ca01  mov     [rsi], rcx
0x18001ca04  mov     rcx, [rbx]
0x18001ca07  mov     rdx, [rcx]
0x18001ca0a  mov     rax, [rdx+8]
0x18001ca0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca13  mov     eax, edi
0x18001ca15  mov     rbx, [rsp+38h+arg_0]
0x18001ca1a  mov     rsi, [rsp+38h+arg_8]
0x18001ca1f  add     rsp, 30h
0x18001ca23  pop     rdi
0x18001ca24  retn
```

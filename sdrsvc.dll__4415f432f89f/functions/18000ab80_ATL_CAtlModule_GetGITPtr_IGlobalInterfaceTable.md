# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000ab80`
- end: `0x18000abf5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ab80`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000abc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000abc2`

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
0x18000ab80  mov     [rsp+arg_0], rbx
0x18000ab85  mov     [rsp+arg_8], rsi
0x18000ab8a  push    rdi
0x18000ab8b  sub     rsp, 30h
0x18000ab8f  mov     rsi, rdx
0x18000ab92  test    rdx, rdx
0x18000ab95  jnz     short loc_18000AB9E
0x18000ab97  mov     eax, 80004003h
0x18000ab9c  jmp     short loc_18000ABE5
0x18000ab9e  xor     edi, edi
0x18000aba0  lea     rbx, [rcx+40h]
0x18000aba4  cmp     [rbx], rdi
0x18000aba7  jnz     short loc_18000ABCE
0x18000aba9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000abb0  mov     [rsp+38h+ppv], rbx; ppv
0x18000abb5  xor     edx, edx; pUnkOuter
0x18000abb7  lea     r8d, [rdi+1]; dwClsContext
0x18000abbb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000abc2  call    cs:__imp_CoCreateInstance
0x18000abc8  mov     edi, eax
0x18000abca  test    eax, eax
0x18000abcc  js      short loc_18000ABE3
0x18000abce  mov     rcx, [rbx]
0x18000abd1  mov     [rsi], rcx
0x18000abd4  mov     rcx, [rbx]
0x18000abd7  mov     rdx, [rcx]
0x18000abda  mov     rax, [rdx+8]
0x18000abde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abe3  mov     eax, edi
0x18000abe5  mov     rbx, [rsp+38h+arg_0]
0x18000abea  mov     rsi, [rsp+38h+arg_8]
0x18000abef  add     rsp, 30h
0x18000abf3  pop     rdi
0x18000abf4  retn
```

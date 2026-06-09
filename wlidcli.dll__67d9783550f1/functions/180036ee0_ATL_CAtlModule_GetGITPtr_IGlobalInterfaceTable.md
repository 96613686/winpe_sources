# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180036ee0`
- end: `0x180036f55`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180036ee0`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036f22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036f22`

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
0x180036ee0  mov     [rsp+arg_0], rbx
0x180036ee5  mov     [rsp+arg_8], rsi
0x180036eea  push    rdi
0x180036eeb  sub     rsp, 30h
0x180036eef  mov     rsi, rdx
0x180036ef2  test    rdx, rdx
0x180036ef5  jnz     short loc_180036EFE
0x180036ef7  mov     eax, 80004003h
0x180036efc  jmp     short loc_180036F45
0x180036efe  xor     edi, edi
0x180036f00  lea     rbx, [rcx+40h]
0x180036f04  cmp     [rbx], rdi
0x180036f07  jnz     short loc_180036F2E
0x180036f09  mov     [rsp+38h+ppv], rbx; ppv
0x180036f0e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180036f15  xor     edx, edx; pUnkOuter
0x180036f17  lea     r8d, [rdi+1]; dwClsContext
0x180036f1b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180036f22  call    cs:__imp_CoCreateInstance
0x180036f28  mov     edi, eax
0x180036f2a  test    eax, eax
0x180036f2c  js      short loc_180036F43
0x180036f2e  mov     rcx, [rbx]
0x180036f31  mov     [rsi], rcx
0x180036f34  mov     rcx, [rbx]
0x180036f37  mov     rdx, [rcx]
0x180036f3a  mov     rax, [rdx+8]
0x180036f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f43  mov     eax, edi
0x180036f45  mov     rbx, [rsp+38h+arg_0]
0x180036f4a  mov     rsi, [rsp+38h+arg_8]
0x180036f4f  add     rsp, 30h
0x180036f53  pop     rdi
0x180036f54  retn
```

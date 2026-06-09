# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180006dd0`
- end: `0x180006e45`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006dd0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e12`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e12`

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
0x180006dd0  mov     [rsp+arg_0], rbx
0x180006dd5  mov     [rsp+arg_8], rsi
0x180006dda  push    rdi
0x180006ddb  sub     rsp, 30h
0x180006ddf  mov     rsi, rdx
0x180006de2  test    rdx, rdx
0x180006de5  jnz     short loc_180006DEE
0x180006de7  mov     eax, 80004003h
0x180006dec  jmp     short loc_180006E35
0x180006dee  xor     edi, edi
0x180006df0  lea     rbx, [rcx+40h]
0x180006df4  cmp     [rbx], rdi
0x180006df7  jnz     short loc_180006E1E
0x180006df9  mov     [rsp+38h+ppv], rbx; ppv
0x180006dfe  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006e05  xor     edx, edx; pUnkOuter
0x180006e07  lea     r8d, [rdi+1]; dwClsContext
0x180006e0b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006e12  call    cs:__imp_CoCreateInstance
0x180006e18  mov     edi, eax
0x180006e1a  test    eax, eax
0x180006e1c  js      short loc_180006E33
0x180006e1e  mov     rcx, [rbx]
0x180006e21  mov     [rsi], rcx
0x180006e24  mov     rcx, [rbx]
0x180006e27  mov     rdx, [rcx]
0x180006e2a  mov     rax, [rdx+8]
0x180006e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e33  mov     eax, edi
0x180006e35  mov     rbx, [rsp+38h+arg_0]
0x180006e3a  mov     rsi, [rsp+38h+arg_8]
0x180006e3f  add     rsp, 30h
0x180006e43  pop     rdi
0x180006e44  retn
```

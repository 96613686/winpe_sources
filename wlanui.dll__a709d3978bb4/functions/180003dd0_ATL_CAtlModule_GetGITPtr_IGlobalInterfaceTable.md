# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180003dd0`
- end: `0x180003e45`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003dd0`
- `0x18001d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003e12`
- `ole32!CoCreateInstance` at `0x180003e12`

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
0x180003dd0  mov     [rsp+arg_0], rbx
0x180003dd5  mov     [rsp+arg_8], rsi
0x180003dda  push    rdi
0x180003ddb  sub     rsp, 30h
0x180003ddf  mov     rsi, rdx
0x180003de2  test    rdx, rdx
0x180003de5  jnz     short loc_180003DEE
0x180003de7  mov     eax, 80004003h
0x180003dec  jmp     short loc_180003E35
0x180003dee  xor     edi, edi
0x180003df0  lea     rbx, [rcx+40h]
0x180003df4  cmp     [rbx], rdi
0x180003df7  jnz     short loc_180003E1E
0x180003df9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003e00  mov     [rsp+38h+ppv], rbx; ppv
0x180003e05  xor     edx, edx; pUnkOuter
0x180003e07  lea     r8d, [rdi+1]; dwClsContext
0x180003e0b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003e12  call    cs:__imp_CoCreateInstance
0x180003e18  mov     edi, eax
0x180003e1a  test    eax, eax
0x180003e1c  js      short loc_180003E33
0x180003e1e  mov     rcx, [rbx]
0x180003e21  mov     [rsi], rcx
0x180003e24  mov     rcx, [rbx]
0x180003e27  mov     rdx, [rcx]
0x180003e2a  mov     rax, [rdx+8]
0x180003e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e33  mov     eax, edi
0x180003e35  mov     rbx, [rsp+38h+arg_0]
0x180003e3a  mov     rsi, [rsp+38h+arg_8]
0x180003e3f  add     rsp, 30h
0x180003e43  pop     rdi
0x180003e44  retn
```

# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180009fb0`
- end: `0x18000a025`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009fb0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009ff2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009ff2`

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
0x180009fb0  mov     [rsp+arg_0], rbx
0x180009fb5  mov     [rsp+arg_8], rsi
0x180009fba  push    rdi
0x180009fbb  sub     rsp, 30h
0x180009fbf  mov     rsi, rdx
0x180009fc2  test    rdx, rdx
0x180009fc5  jnz     short loc_180009FCE
0x180009fc7  mov     eax, 80004003h
0x180009fcc  jmp     short loc_18000A015
0x180009fce  xor     edi, edi
0x180009fd0  lea     rbx, [rcx+40h]
0x180009fd4  cmp     [rbx], rdi
0x180009fd7  jnz     short loc_180009FFE
0x180009fd9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009fe0  mov     [rsp+38h+ppv], rbx; ppv
0x180009fe5  xor     edx, edx; pUnkOuter
0x180009fe7  lea     r8d, [rdi+1]; dwClsContext
0x180009feb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009ff2  call    cs:__imp_CoCreateInstance
0x180009ff8  mov     edi, eax
0x180009ffa  test    eax, eax
0x180009ffc  js      short loc_18000A013
0x180009ffe  mov     rcx, [rbx]
0x18000a001  mov     [rsi], rcx
0x18000a004  mov     rcx, [rbx]
0x18000a007  mov     rdx, [rcx]
0x18000a00a  mov     rax, [rdx+8]
0x18000a00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a013  mov     eax, edi
0x18000a015  mov     rbx, [rsp+38h+arg_0]
0x18000a01a  mov     rsi, [rsp+38h+arg_8]
0x18000a01f  add     rsp, 30h
0x18000a023  pop     rdi
0x18000a024  retn
```

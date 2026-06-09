# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180006330`
- end: `0x1800063a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006330`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006372`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006372`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // ebx
  _QWORD *v5; // rdi

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
0x180006330  mov     [rsp+arg_0], rbx
0x180006335  mov     [rsp+arg_8], rsi
0x18000633a  push    rdi
0x18000633b  sub     rsp, 30h
0x18000633f  mov     rsi, rdx
0x180006342  test    rdx, rdx
0x180006345  jnz     short loc_18000634E
0x180006347  mov     eax, 80004003h
0x18000634c  jmp     short loc_180006395
0x18000634e  xor     ebx, ebx
0x180006350  lea     rdi, [rcx+40h]
0x180006354  cmp     [rdi], rbx
0x180006357  jnz     short loc_18000637E
0x180006359  mov     [rsp+38h+ppv], rdi; ppv
0x18000635e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006365  xor     edx, edx; pUnkOuter
0x180006367  lea     r8d, [rbx+1]; dwClsContext
0x18000636b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006372  call    cs:__imp_CoCreateInstance
0x180006378  mov     ebx, eax
0x18000637a  test    eax, eax
0x18000637c  js      short loc_180006393
0x18000637e  mov     rcx, [rdi]
0x180006381  mov     [rsi], rcx
0x180006384  mov     rcx, [rdi]
0x180006387  mov     rdx, [rcx]
0x18000638a  mov     rax, [rdx+8]
0x18000638e  call    _guard_dispatch_icall
0x180006393  mov     eax, ebx
0x180006395  mov     rbx, [rsp+38h+arg_0]
0x18000639a  mov     rsi, [rsp+38h+arg_8]
0x18000639f  add     rsp, 30h
0x1800063a3  pop     rdi
0x1800063a4  retn
```

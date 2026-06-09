# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180018810`
- end: `0x18001888f`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180018810`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001885c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001885c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // edi
  _QWORD **v5; // rbx

  if ( !a2 )
    return 2147500035LL;
  Instance = 0;
  v5 = (_QWORD **)((char *)this + 64);
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
    (*(void (__fastcall **)(_QWORD, _QWORD))(**v5 + 8LL))(*v5, **v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180018810  push    rdi
0x180018812  sub     rsp, 40h
0x180018816  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001881f  mov     [rsp+48h+arg_0], rbx
0x180018824  mov     [rsp+48h+arg_8], rsi
0x180018829  mov     rsi, rdx
0x18001882c  test    rdx, rdx
0x18001882f  jnz     short loc_180018838
0x180018831  mov     eax, 80004003h
0x180018836  jmp     short loc_18001887F
0x180018838  xor     edi, edi
0x18001883a  lea     rbx, [rcx+40h]
0x18001883e  cmp     [rbx], rdi
0x180018841  jnz     short loc_180018868
0x180018843  mov     [rsp+48h+ppv], rbx; ppv
0x180018848  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18001884f  xor     edx, edx; pUnkOuter
0x180018851  lea     r8d, [rdi+1]; dwClsContext
0x180018855  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001885c  call    cs:__imp_CoCreateInstance
0x180018862  mov     edi, eax
0x180018864  test    eax, eax
0x180018866  js      short loc_18001887D
0x180018868  mov     rcx, [rbx]
0x18001886b  mov     [rsi], rcx
0x18001886e  mov     rcx, [rbx]
0x180018871  mov     rdx, [rcx]
0x180018874  mov     rax, [rdx+8]
0x180018878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001887d  mov     eax, edi
0x18001887f  mov     rbx, [rsp+48h+arg_0]
0x180018884  mov     rsi, [rsp+48h+arg_8]
0x180018889  add     rsp, 40h
0x18001888d  pop     rdi
0x18001888e  retn
```

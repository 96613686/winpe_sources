# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800079e0`
- end: `0x180007a55`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800079e0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007a22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007a22`

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
0x1800079e0  mov     [rsp+arg_0], rbx
0x1800079e5  mov     [rsp+arg_8], rsi
0x1800079ea  push    rdi
0x1800079eb  sub     rsp, 30h
0x1800079ef  mov     rsi, rdx
0x1800079f2  test    rdx, rdx
0x1800079f5  jnz     short loc_1800079FE
0x1800079f7  mov     eax, 80004003h
0x1800079fc  jmp     short loc_180007A45
0x1800079fe  xor     edi, edi
0x180007a00  lea     rbx, [rcx+40h]
0x180007a04  cmp     [rbx], rdi
0x180007a07  jnz     short loc_180007A2E
0x180007a09  mov     [rsp+38h+ppv], rbx; ppv
0x180007a0e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007a15  xor     edx, edx; pUnkOuter
0x180007a17  lea     r8d, [rdi+1]; dwClsContext
0x180007a1b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007a22  call    cs:__imp_CoCreateInstance
0x180007a28  mov     edi, eax
0x180007a2a  test    eax, eax
0x180007a2c  js      short loc_180007A43
0x180007a2e  mov     rcx, [rbx]
0x180007a31  mov     [rsi], rcx
0x180007a34  mov     rcx, [rbx]
0x180007a37  mov     rdx, [rcx]
0x180007a3a  mov     rax, [rdx+8]
0x180007a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a43  mov     eax, edi
0x180007a45  mov     rbx, [rsp+38h+arg_0]
0x180007a4a  mov     rsi, [rsp+38h+arg_8]
0x180007a4f  add     rsp, 30h
0x180007a53  pop     rdi
0x180007a54  retn
```

# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180008100`
- end: `0x180008186`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008100`
- `0x180034010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000814c`
- `ole32!CoCreateInstance` at `0x18000814c`

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
0x180008100  push    rdi
0x180008102  sub     rsp, 40h
0x180008106  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000810f  mov     [rsp+48h+arg_0], rbx
0x180008114  mov     [rsp+48h+arg_8], rsi
0x180008119  mov     rsi, rdx
0x18000811c  test    rdx, rdx
0x18000811f  jnz     short loc_180008128
0x180008121  mov     eax, 80004003h
0x180008126  jmp     short loc_180008175
0x180008128  xor     edi, edi
0x18000812a  lea     rbx, [rcx+40h]
0x18000812e  cmp     [rbx], rdi
0x180008131  jnz     short loc_18000815E
0x180008133  mov     [rsp+48h+ppv], rbx; ppv
0x180008138  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000813f  xor     edx, edx; pUnkOuter
0x180008141  lea     r8d, [rdi+1]; dwClsContext
0x180008145  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000814c  call    cs:__imp_CoCreateInstance
0x180008153  nop     dword ptr [rax+rax+00h]
0x180008158  mov     edi, eax
0x18000815a  test    eax, eax
0x18000815c  js      short loc_180008173
0x18000815e  mov     rcx, [rbx]
0x180008161  mov     [rsi], rcx
0x180008164  mov     rcx, [rbx]
0x180008167  mov     rdx, [rcx]
0x18000816a  mov     rax, [rdx+8]
0x18000816e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008173  mov     eax, edi
0x180008175  mov     rbx, [rsp+48h+arg_0]
0x18000817a  mov     rsi, [rsp+48h+arg_8]
0x18000817f  add     rsp, 40h
0x180008183  pop     rdi
0x180008184  retn
```

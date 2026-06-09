# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180008840`
- end: `0x1800088b6`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008840`
- `0x180015cc0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180008882`
- `ole32!CoCreateInstance` at `0x180008882`

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
0x180008840  mov     [rsp+arg_0], rbx
0x180008845  mov     [rsp+arg_8], rsi
0x18000884a  push    rdi
0x18000884b  sub     rsp, 30h
0x18000884f  mov     rsi, rdx
0x180008852  test    rdx, rdx
0x180008855  jnz     short loc_18000885E
0x180008857  mov     eax, 80004003h
0x18000885c  jmp     short loc_1800088A6
0x18000885e  xor     edi, edi
0x180008860  lea     rbx, [rcx+40h]
0x180008864  cmp     [rbx], rdi
0x180008867  jnz     short loc_18000888E
0x180008869  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180008870  mov     [rsp+38h+ppv], rbx; ppv
0x180008875  xor     edx, edx; pUnkOuter
0x180008877  lea     r8d, [rdi+1]; dwClsContext
0x18000887b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180008882  call    cs:__imp_CoCreateInstance
0x180008888  mov     edi, eax
0x18000888a  test    eax, eax
0x18000888c  js      short loc_1800088A4
0x18000888e  mov     rcx, [rbx]
0x180008891  mov     [rsi], rcx
0x180008894  mov     rcx, [rbx]
0x180008897  mov     rdx, [rcx]
0x18000889a  mov     rax, [rdx+8]
0x18000889e  call    cs:__guard_dispatch_icall_fptr
0x1800088a4  mov     eax, edi
0x1800088a6  mov     rbx, [rsp+38h+arg_0]
0x1800088ab  mov     rsi, [rsp+38h+arg_8]
0x1800088b0  add     rsp, 30h
0x1800088b4  pop     rdi
0x1800088b5  retn
```

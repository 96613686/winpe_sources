# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18001be90`
- end: `0x18001bf05`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001be90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bed2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bed2`

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
0x18001be90  mov     [rsp+arg_0], rbx
0x18001be95  mov     [rsp+arg_8], rsi
0x18001be9a  push    rdi
0x18001be9b  sub     rsp, 30h
0x18001be9f  mov     rsi, rdx
0x18001bea2  test    rdx, rdx
0x18001bea5  jnz     short loc_18001BEAE
0x18001bea7  mov     eax, 80004003h
0x18001beac  jmp     short loc_18001BEF5
0x18001beae  xor     edi, edi
0x18001beb0  lea     rbx, [rcx+40h]
0x18001beb4  cmp     [rbx], rdi
0x18001beb7  jnz     short loc_18001BEDE
0x18001beb9  mov     [rsp+38h+ppv], rbx; ppv
0x18001bebe  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18001bec5  xor     edx, edx; pUnkOuter
0x18001bec7  lea     r8d, [rdi+1]; dwClsContext
0x18001becb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001bed2  call    cs:__imp_CoCreateInstance
0x18001bed8  mov     edi, eax
0x18001beda  test    eax, eax
0x18001bedc  js      short loc_18001BEF3
0x18001bede  mov     rcx, [rbx]
0x18001bee1  mov     [rsi], rcx
0x18001bee4  mov     rcx, [rbx]
0x18001bee7  mov     rdx, [rcx]
0x18001beea  mov     rax, [rdx+8]
0x18001beee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bef3  mov     eax, edi
0x18001bef5  mov     rbx, [rsp+38h+arg_0]
0x18001befa  mov     rsi, [rsp+38h+arg_8]
0x18001beff  add     rsp, 30h
0x18001bf03  pop     rdi
0x18001bf04  retn
```

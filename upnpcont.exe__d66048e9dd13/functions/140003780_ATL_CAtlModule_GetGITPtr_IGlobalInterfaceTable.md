# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x140003780`
- end: `0x1400037f5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003780`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400037c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400037c2`

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
0x140003780  mov     [rsp+arg_0], rbx
0x140003785  mov     [rsp+arg_8], rsi
0x14000378a  push    rdi
0x14000378b  sub     rsp, 30h
0x14000378f  mov     rsi, rdx
0x140003792  test    rdx, rdx
0x140003795  jnz     short loc_14000379E
0x140003797  mov     eax, 80004003h
0x14000379c  jmp     short loc_1400037E5
0x14000379e  xor     edi, edi
0x1400037a0  lea     rbx, [rcx+40h]
0x1400037a4  cmp     [rbx], rdi
0x1400037a7  jnz     short loc_1400037CE
0x1400037a9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1400037b0  mov     [rsp+38h+ppv], rbx; ppv
0x1400037b5  xor     edx, edx; pUnkOuter
0x1400037b7  lea     r8d, [rdi+1]; dwClsContext
0x1400037bb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1400037c2  call    cs:__imp_CoCreateInstance
0x1400037c8  mov     edi, eax
0x1400037ca  test    eax, eax
0x1400037cc  js      short loc_1400037E3
0x1400037ce  mov     rcx, [rbx]
0x1400037d1  mov     [rsi], rcx
0x1400037d4  mov     rcx, [rbx]
0x1400037d7  mov     rdx, [rcx]
0x1400037da  mov     rax, [rdx+8]
0x1400037de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037e3  mov     eax, edi
0x1400037e5  mov     rbx, [rsp+38h+arg_0]
0x1400037ea  mov     rsi, [rsp+38h+arg_8]
0x1400037ef  add     rsp, 30h
0x1400037f3  pop     rdi
0x1400037f4  retn
```

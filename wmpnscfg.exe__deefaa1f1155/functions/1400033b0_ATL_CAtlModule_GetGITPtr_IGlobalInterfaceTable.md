# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1400033b0`
- end: `0x140003425`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400033b0`
- `0x140008010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400033f2`
- `ole32!CoCreateInstance` at `0x1400033f2`

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
0x1400033b0  mov     [rsp+arg_0], rbx
0x1400033b5  mov     [rsp+arg_8], rsi
0x1400033ba  push    rdi
0x1400033bb  sub     rsp, 30h
0x1400033bf  mov     rsi, rdx
0x1400033c2  test    rdx, rdx
0x1400033c5  jnz     short loc_1400033CE
0x1400033c7  mov     eax, 80004003h
0x1400033cc  jmp     short loc_140003415
0x1400033ce  xor     edi, edi
0x1400033d0  lea     rbx, [rcx+40h]
0x1400033d4  cmp     [rbx], rdi
0x1400033d7  jnz     short loc_1400033FE
0x1400033d9  mov     [rsp+38h+ppv], rbx; ppv
0x1400033de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1400033e5  xor     edx, edx; pUnkOuter
0x1400033e7  lea     r8d, [rdi+1]; dwClsContext
0x1400033eb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1400033f2  call    cs:__imp_CoCreateInstance
0x1400033f8  mov     edi, eax
0x1400033fa  test    eax, eax
0x1400033fc  js      short loc_140003413
0x1400033fe  mov     rcx, [rbx]
0x140003401  mov     [rsi], rcx
0x140003404  mov     rcx, [rbx]
0x140003407  mov     rdx, [rcx]
0x14000340a  mov     rax, [rdx+8]
0x14000340e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003413  mov     eax, edi
0x140003415  mov     rbx, [rsp+38h+arg_0]
0x14000341a  mov     rsi, [rsp+38h+arg_8]
0x14000341f  add     rsp, 30h
0x140003423  pop     rdi
0x140003424  retn
```

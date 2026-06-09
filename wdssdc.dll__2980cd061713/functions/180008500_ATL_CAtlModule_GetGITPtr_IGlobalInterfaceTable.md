# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180008500`
- end: `0x18000857c`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008500`
- `0x18000d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180008542`
- `ole32!CoCreateInstance` at `0x180008542`

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
0x180008500  mov     [rsp+arg_0], rbx
0x180008505  mov     [rsp+arg_8], rsi
0x18000850a  push    rdi
0x18000850b  sub     rsp, 30h
0x18000850f  mov     rsi, rdx
0x180008512  test    rdx, rdx
0x180008515  jnz     short loc_18000851E
0x180008517  mov     eax, 80004003h
0x18000851c  jmp     short loc_18000856B
0x18000851e  xor     ebx, ebx
0x180008520  lea     rdi, [rcx+40h]
0x180008524  cmp     [rdi], rbx
0x180008527  jnz     short loc_180008554
0x180008529  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180008530  mov     [rsp+38h+ppv], rdi; ppv
0x180008535  xor     edx, edx; pUnkOuter
0x180008537  lea     r8d, [rbx+1]; dwClsContext
0x18000853b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180008542  call    cs:__imp_CoCreateInstance
0x180008549  nop     dword ptr [rax+rax+00h]
0x18000854e  mov     ebx, eax
0x180008550  test    eax, eax
0x180008552  js      short loc_180008569
0x180008554  mov     rcx, [rdi]
0x180008557  mov     [rsi], rcx
0x18000855a  mov     rcx, [rdi]
0x18000855d  mov     rdx, [rcx]
0x180008560  mov     rax, [rdx+8]
0x180008564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008569  mov     eax, ebx
0x18000856b  mov     rbx, [rsp+38h+arg_0]
0x180008570  mov     rsi, [rsp+38h+arg_8]
0x180008575  add     rsp, 30h
0x180008579  pop     rdi
0x18000857a  retn
```

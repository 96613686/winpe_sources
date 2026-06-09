# CWbemPathCracker::GetKeys(ISWbemNamedValueSet * *)

- ea: `0x1800336b0`
- end: `0x18003373f`
- name: `?GetKeys@CWbemPathCracker@@QEAA_NPEAPEAUISWbemNamedValueSet@@@Z`
- size: `143`
- prototype: `bool __fastcall(CWbemPathCracker *__hidden this, struct ISWbemNamedValueSet **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002eae0`

## callees

- `0x18001fc1c`
- `0x180022d70`
- `0x1800336b0`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800336d9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800336d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CWbemPathCracker::GetKeys(CWbemPathCracker *this, struct ISWbemNamedValueSet **a2)
{
  char v4; // di
  CSWbemNamedValueSet *v5; // rax
  CSWbemNamedValueSet *v6; // rbx
  unsigned int v7; // edx

  v4 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v5 = (CSWbemNamedValueSet *)CWin32DefaultArena::WbemMemAlloc(0x98u);
    if ( v5 )
      v6 = CSWbemNamedValueSet::CSWbemNamedValueSet(v5, this, 1);
    else
      v6 = 0;
    if ( v6 )
    {
      if ( (**(int (__fastcall ***)(CSWbemNamedValueSet *, GUID *, struct ISWbemNamedValueSet **))v6)(
             v6,
             &IID_ISWbemNamedValueSet,
             a2) < 0 )
        CSWbemNamedValueSet::`scalar deleting destructor'(v6, v7);
      else
        return 1;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800336b0  mov     [rsp+arg_0], rbx
0x1800336b5  mov     [rsp+arg_10], rsi
0x1800336ba  push    rdi
0x1800336bb  sub     rsp, 20h
0x1800336bf  mov     rsi, rdx
0x1800336c2  mov     rbx, rcx
0x1800336c5  xor     dil, dil
0x1800336c8  test    rdx, rdx
0x1800336cb  jz      short loc_18003372C
0x1800336cd  mov     qword ptr [rdx], 0
0x1800336d4  mov     ecx, 98h
0x1800336d9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800336df  mov     [rsp+28h+arg_8], rax
0x1800336e4  test    rax, rax
0x1800336e7  jz      short loc_1800336FC
0x1800336e9  mov     r8b, 1; bool
0x1800336ec  mov     rdx, rbx; struct CWbemPathCracker *
0x1800336ef  mov     rcx, rax; this
0x1800336f2  call    ??0CSWbemNamedValueSet@@QEAA@PEAVCWbemPathCracker@@_N@Z; CSWbemNamedValueSet::CSWbemNamedValueSet(CWbemPathCracker *,bool)
0x1800336f7  mov     rbx, rax
0x1800336fa  jmp     short loc_1800336FE
0x1800336fc  xor     ebx, ebx
0x1800336fe  test    rbx, rbx
0x180033701  jz      short loc_18003372C
0x180033703  mov     rax, [rbx]
0x180033706  mov     r8, rsi
0x180033709  lea     rdx, IID_ISWbemNamedValueSet
0x180033710  mov     rcx, rbx
0x180033713  mov     rax, [rax]
0x180033716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003371b  test    eax, eax
0x18003371d  js      short loc_180033724
0x18003371f  mov     dil, 1
0x180033722  jmp     short loc_18003372C
0x180033724  mov     rcx, rbx; this
0x180033727  call    ??_GCSWbemNamedValueSet@@QEAAPEAXI@Z; CSWbemNamedValueSet::`scalar deleting destructor'(uint)
0x18003372c  mov     al, dil
0x18003372f  mov     rbx, [rsp+28h+arg_0]
0x180033734  mov     rsi, [rsp+28h+arg_10]
0x180033739  add     rsp, 20h
0x18003373d  pop     rdi
0x18003373e  retn
```

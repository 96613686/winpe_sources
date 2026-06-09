# UwfCfgCommitRegistry(bool,ushort const *,ushort const *)

- ea: `0x1800181a0`
- end: `0x18001822f`
- name: `?UwfCfgCommitRegistry@@YAJ_NPEBG1@Z`
- size: `143`
- prototype: `__int64 __fastcall(bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f364`
- `0x1800155f0`
- `0x180015af0`
- `0x180017b90`
- `0x1800181a0`
- `0x18001aa08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001821c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001821c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800181df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800181df`

## pseudocode

```c
__int64 __fastcall UwfCfgCommitRegistry(bool a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  bool v6; // cl
  void ***v7; // rdi
  int v8; // ebx

  anonymous_namespace_::uwfCfgApiBreakpoint();
  v7 = 0;
  if ( a2 && a3 )
  {
    EnsureUwfFeatureState(v6);
    v7 = &CUwfProvider::s_UwfProvider;
    EnterCriticalSection(&CUwfProvider::s_CritSec);
    v8 = CUwfProvider::Begin((CUwfProvider *)&CUwfProvider::s_UwfProvider, 0);
    if ( v8 >= 0 )
      v8 = CUwfManagement::CommitRegistry((CUwfManagement *)qword_18002A1D8, a1, a2, a3);
  }
  else
  {
    v8 = -2147024809;
  }
  CUwfManagement::Finalize((CUwfManagement *)(v7 + 1));
  LeaveCriticalSection(&CUwfProvider::s_CritSec);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800181a0  push    rbx
0x1800181a2  push    rbp
0x1800181a3  push    rsi
0x1800181a4  push    rdi
0x1800181a5  push    r14
0x1800181a7  sub     rsp, 20h
0x1800181ab  mov     rsi, r8
0x1800181ae  mov     rbp, rdx
0x1800181b1  mov     r14b, cl
0x1800181b4  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x1800181b9  xor     edi, edi
0x1800181bb  test    rbp, rbp
0x1800181be  jnz     short loc_1800181C7
0x1800181c0  mov     ebx, 80070057h
0x1800181c5  jmp     short loc_18001820C
0x1800181c7  test    rsi, rsi
0x1800181ca  jz      short loc_1800181C0
0x1800181cc  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x1800181d1  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800181d8  lea     rdi, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x1800181df  call    cs:__imp_EnterCriticalSection
0x1800181e5  xor     edx, edx; bool
0x1800181e7  mov     rcx, rdi; this
0x1800181ea  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x1800181ef  mov     ebx, eax
0x1800181f1  test    eax, eax
0x1800181f3  js      short loc_18001820C
0x1800181f5  mov     r9, rsi; unsigned __int16 *
0x1800181f8  lea     rcx, qword_18002A1D8; this
0x1800181ff  mov     r8, rbp; unsigned __int16 *
0x180018202  mov     dl, r14b; bool
0x180018205  call    ?CommitRegistry@CUwfManagement@@QEAAJ_NPEBG1@Z; CUwfManagement::CommitRegistry(bool,ushort const *,ushort const *)
0x18001820a  mov     ebx, eax
0x18001820c  lea     rcx, [rdi+8]; this
0x180018210  call    ?Finalize@CUwfManagement@@QEAAJXZ; CUwfManagement::Finalize(void)
0x180018215  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001821c  call    cs:__imp_LeaveCriticalSection
0x180018222  mov     eax, ebx
0x180018224  add     rsp, 20h
0x180018228  pop     r14
0x18001822a  pop     rdi
0x18001822b  pop     rsi
0x18001822c  pop     rbp
0x18001822d  pop     rbx
0x18001822e  retn
```

# UwfCfgCommitRegistryDeletion(bool,ushort const *,ushort const *)

- ea: `0x180018240`
- end: `0x1800182cf`
- name: `?UwfCfgCommitRegistryDeletion@@YAJ_NPEBG1@Z`
- size: `143`
- prototype: `__int64 __fastcall(char, wchar_t *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f364`
- `0x180015870`
- `0x180015af0`
- `0x180017b90`
- `0x180018240`
- `0x18001aa08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001827f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001827f`

## pseudocode

```c
__int64 __fastcall UwfCfgCommitRegistryDeletion(char a1, wchar_t *a2, unsigned __int16 *a3)
{
  __int64 v6; // rdx
  void ***v7; // rdi
  int v8; // ebx

  anonymous_namespace_::uwfCfgApiBreakpoint();
  v7 = 0;
  if ( a2 && a3 )
  {
    EnsureUwfFeatureState();
    v7 = &CUwfProvider::s_UwfProvider;
    EnterCriticalSection(&CUwfProvider::s_CritSec);
    v8 = CUwfProvider::Begin((CUwfProvider *)&CUwfProvider::s_UwfProvider, 0);
    if ( v8 >= 0 )
      v8 = CUwfManagement::CommitRegistryDeletion((CUwfManagement *)qword_18002A1D8, a1, a2, a3);
  }
  else
  {
    v8 = -2147024809;
  }
  CUwfManagement::Finalize((CUwfManagement *)(v7 + 1), v6);
  LeaveCriticalSection(&CUwfProvider::s_CritSec);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018240  push    rbx
0x180018242  push    rbp
0x180018243  push    rsi
0x180018244  push    rdi
0x180018245  push    r14
0x180018247  sub     rsp, 20h
0x18001824b  mov     rsi, r8
0x18001824e  mov     rbp, rdx
0x180018251  mov     r14b, cl
0x180018254  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180018259  xor     edi, edi
0x18001825b  test    rbp, rbp
0x18001825e  jnz     short loc_180018267
0x180018260  mov     ebx, 80070057h
0x180018265  jmp     short loc_1800182AC
0x180018267  test    rsi, rsi
0x18001826a  jz      short loc_180018260
0x18001826c  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180018271  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018278  lea     rdi, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x18001827f  call    cs:__imp_EnterCriticalSection
0x180018285  xor     edx, edx; bool
0x180018287  mov     rcx, rdi; this
0x18001828a  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x18001828f  mov     ebx, eax
0x180018291  test    eax, eax
0x180018293  js      short loc_1800182AC
0x180018295  mov     r9, rsi; unsigned __int16 *
0x180018298  lea     rcx, qword_18002A1D8; this
0x18001829f  mov     r8, rbp; unsigned __int16 *
0x1800182a2  mov     dl, r14b; bool
0x1800182a5  call    ?CommitRegistryDeletion@CUwfManagement@@QEAAJ_NPEBG1@Z; CUwfManagement::CommitRegistryDeletion(bool,ushort const *,ushort const *)
0x1800182aa  mov     ebx, eax
0x1800182ac  lea     rcx, [rdi+8]; this
0x1800182b0  call    ?Finalize@CUwfManagement@@QEAAJXZ; CUwfManagement::Finalize(void)
0x1800182b5  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800182bc  call    cs:__imp_LeaveCriticalSection
0x1800182c2  mov     eax, ebx
0x1800182c4  add     rsp, 20h
0x1800182c8  pop     r14
0x1800182ca  pop     rdi
0x1800182cb  pop     rsi
0x1800182cc  pop     rbp
0x1800182cd  pop     rbx
0x1800182ce  retn
```

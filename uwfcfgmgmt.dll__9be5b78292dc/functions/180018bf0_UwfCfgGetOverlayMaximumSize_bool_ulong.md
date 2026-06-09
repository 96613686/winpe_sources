# UwfCfgGetOverlayMaximumSize(bool,ulong *)

- ea: `0x180018bf0`
- end: `0x180018c64`
- name: `?UwfCfgGetOverlayMaximumSize@@YAJ_NPEAK@Z`
- size: `116`
- prototype: `__int64 __fastcall(char, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000f364`
- `0x180017050`
- `0x180017b90`
- `0x180018bf0`
- `0x18001aa08`
- `0x18001aa94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c25`

## pseudocode

```c
__int64 __fastcall UwfCfgGetOverlayMaximumSize(char a1, unsigned int *a2)
{
  void ***v4; // rdi
  int OverlayMaximumSize; // ebx

  anonymous_namespace_::uwfCfgApiBreakpoint();
  if ( a2 )
  {
    EnsureUwfFeatureState();
    v4 = &CUwfProvider::s_UwfProvider;
    EnterCriticalSection(&CUwfProvider::s_CritSec);
    OverlayMaximumSize = CUwfProvider::Begin((CUwfProvider *)&CUwfProvider::s_UwfProvider, 0);
    if ( OverlayMaximumSize >= 0 )
      OverlayMaximumSize = CUwfManagement::get_OverlayMaximumSize((CUwfManagement *)qword_18002A1D8, a1, a2);
  }
  else
  {
    v4 = 0;
    OverlayMaximumSize = -2147024809;
  }
  anonymous_namespace_::uwfCfgFinalize(v4, 0);
  return (unsigned int)OverlayMaximumSize;
}

```

## disassembly

```asm
0x180018bf0  push    rbx
0x180018bf2  push    rbp
0x180018bf3  push    rsi
0x180018bf4  push    rdi
0x180018bf5  sub     rsp, 28h
0x180018bf9  mov     rsi, rdx
0x180018bfc  mov     bpl, cl
0x180018bff  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180018c04  test    rsi, rsi
0x180018c07  jnz     short loc_180018C12
0x180018c09  xor     edi, edi
0x180018c0b  mov     ebx, 80070057h
0x180018c10  jmp     short loc_180018C4F
0x180018c12  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180018c17  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018c1e  lea     rdi, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x180018c25  call    cs:__imp_EnterCriticalSection
0x180018c2b  xor     edx, edx; bool
0x180018c2d  mov     rcx, rdi; this
0x180018c30  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x180018c35  mov     ebx, eax
0x180018c37  test    eax, eax
0x180018c39  js      short loc_180018C4F
0x180018c3b  mov     r8, rsi; unsigned int *
0x180018c3e  lea     rcx, qword_18002A1D8; this
0x180018c45  mov     dl, bpl; bool
0x180018c48  call    ?get_OverlayMaximumSize@CUwfManagement@@QEAAJ_NPEAK@Z; CUwfManagement::get_OverlayMaximumSize(bool,ulong *)
0x180018c4d  mov     ebx, eax
0x180018c4f  xor     edx, edx
0x180018c51  mov     rcx, rdi
0x180018c54  call    _anonymous_namespace___uwfCfgFinalize
0x180018c59  mov     eax, ebx
0x180018c5b  add     rsp, 28h
0x180018c5f  pop     rdi
0x180018c60  pop     rsi
0x180018c61  pop     rbp
0x180018c62  pop     rbx
0x180018c63  retn
```

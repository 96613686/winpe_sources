# UwfCfgGetOverlayType(bool,_UWF_CONFIG_OVERLAY_TYPE *)

- ea: `0x180018c70`
- end: `0x180018ce4`
- name: `?UwfCfgGetOverlayType@@YAJ_NPEAW4_UWF_CONFIG_OVERLAY_TYPE@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(char, enum _UWF_CONFIG_OVERLAY_TYPE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000f364`
- `0x180017090`
- `0x180017b90`
- `0x180018c70`
- `0x18001aa08`
- `0x18001aa94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ca5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ca5`

## pseudocode

```c
__int64 __fastcall UwfCfgGetOverlayType(char a1, enum _UWF_CONFIG_OVERLAY_TYPE *a2)
{
  void ***v4; // rdi
  int OverlayType; // ebx

  anonymous_namespace_::uwfCfgApiBreakpoint();
  if ( a2 )
  {
    EnsureUwfFeatureState();
    v4 = &CUwfProvider::s_UwfProvider;
    EnterCriticalSection(&CUwfProvider::s_CritSec);
    OverlayType = CUwfProvider::Begin((CUwfProvider *)&CUwfProvider::s_UwfProvider, 0);
    if ( OverlayType >= 0 )
      OverlayType = CUwfManagement::get_OverlayType((CUwfManagement *)qword_18002A1D8, a1, a2);
  }
  else
  {
    v4 = 0;
    OverlayType = -2147024809;
  }
  anonymous_namespace_::uwfCfgFinalize(v4, 0);
  return (unsigned int)OverlayType;
}

```

## disassembly

```asm
0x180018c70  push    rbx
0x180018c72  push    rbp
0x180018c73  push    rsi
0x180018c74  push    rdi
0x180018c75  sub     rsp, 28h
0x180018c79  mov     rsi, rdx
0x180018c7c  mov     bpl, cl
0x180018c7f  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180018c84  test    rsi, rsi
0x180018c87  jnz     short loc_180018C92
0x180018c89  xor     edi, edi
0x180018c8b  mov     ebx, 80070057h
0x180018c90  jmp     short loc_180018CCF
0x180018c92  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180018c97  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018c9e  lea     rdi, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x180018ca5  call    cs:__imp_EnterCriticalSection
0x180018cab  xor     edx, edx; bool
0x180018cad  mov     rcx, rdi; this
0x180018cb0  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x180018cb5  mov     ebx, eax
0x180018cb7  test    eax, eax
0x180018cb9  js      short loc_180018CCF
0x180018cbb  mov     r8, rsi; enum _UWF_CONFIG_OVERLAY_TYPE *
0x180018cbe  lea     rcx, qword_18002A1D8; this
0x180018cc5  mov     dl, bpl; bool
0x180018cc8  call    ?get_OverlayType@CUwfManagement@@QEAAJ_NPEAW4_UWF_CONFIG_OVERLAY_TYPE@@@Z; CUwfManagement::get_OverlayType(bool,_UWF_CONFIG_OVERLAY_TYPE *)
0x180018ccd  mov     ebx, eax
0x180018ccf  xor     edx, edx
0x180018cd1  mov     rcx, rdi
0x180018cd4  call    _anonymous_namespace___uwfCfgFinalize
0x180018cd9  mov     eax, ebx
0x180018cdb  add     rsp, 28h
0x180018cdf  pop     rdi
0x180018ce0  pop     rsi
0x180018ce1  pop     rbp
0x180018ce2  pop     rbx
0x180018ce3  retn
```

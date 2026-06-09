# UwfCfgSetOverlayMaximumSize(ulong)

- ea: `0x180019fa0`
- end: `0x18001a002`
- name: `?UwfCfgSetOverlayMaximumSize@@YAJK@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000f364`
- `0x180017600`
- `0x180017b90`
- `0x180019fa0`
- `0x18001aa08`
- `0x18001aa94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019fbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019fbd`

## pseudocode

```c
__int64 __fastcall UwfCfgSetOverlayMaximumSize(unsigned int a1)
{
  int v2; // ebx

  anonymous_namespace_::uwfCfgApiBreakpoint();
  EnsureUwfFeatureState();
  EnterCriticalSection(&CUwfProvider::s_CritSec);
  v2 = CUwfProvider::Begin((CUwfProvider *)&CUwfProvider::s_UwfProvider, 1);
  if ( v2 >= 0 )
    v2 = CUwfManagement::set_OverlayMaximumSize((HKEY *)qword_18002A1D8, a1);
  anonymous_namespace_::uwfCfgFinalize(&CUwfProvider::s_UwfProvider, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180019fa0  mov     [rsp+arg_0], rbx
0x180019fa5  push    rdi
0x180019fa6  sub     rsp, 20h
0x180019faa  mov     edi, ecx
0x180019fac  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180019fb1  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180019fb6  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019fbd  call    cs:__imp_EnterCriticalSection
0x180019fc3  mov     dl, 1; bool
0x180019fc5  lea     rcx, ?s_UwfProvider@CUwfProvider@@0V1@A; this
0x180019fcc  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x180019fd1  mov     ebx, eax
0x180019fd3  test    eax, eax
0x180019fd5  js      short loc_180019FE7
0x180019fd7  mov     edx, edi; unsigned int
0x180019fd9  lea     rcx, qword_18002A1D8; this
0x180019fe0  call    ?set_OverlayMaximumSize@CUwfManagement@@QEAAJK@Z; CUwfManagement::set_OverlayMaximumSize(ulong)
0x180019fe5  mov     ebx, eax
0x180019fe7  xor     edx, edx
0x180019fe9  lea     rcx, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x180019ff0  call    _anonymous_namespace___uwfCfgFinalize
0x180019ff5  mov     eax, ebx
0x180019ff7  mov     rbx, [rsp+28h+arg_0]
0x180019ffc  add     rsp, 20h
0x18001a000  pop     rdi
0x18001a001  retn
```

# UwfCfgSetOverlayType(_UWF_CONFIG_OVERLAY_TYPE)

- ea: `0x18001a010`
- end: `0x18001a072`
- name: `?UwfCfgSetOverlayType@@YAJW4_UWF_CONFIG_OVERLAY_TYPE@@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001a620`

## callees

- `0x18000f364`
- `0x1800176f0`
- `0x180017b90`
- `0x18001a010`
- `0x18001aa08`
- `0x18001aa94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a02d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a02d`

## pseudocode

```c
__int64 __fastcall UwfCfgSetOverlayType(unsigned int a1)
{
  int v2; // ebx

  anonymous_namespace_::uwfCfgApiBreakpoint();
  EnsureUwfFeatureState();
  EnterCriticalSection(&CUwfProvider::s_CritSec);
  v2 = CUwfProvider::Begin((CUwfProvider *)&CUwfProvider::s_UwfProvider, 1);
  if ( v2 >= 0 )
    v2 = CUwfManagement::set_OverlayType((__int64)qword_18002A1D8, a1);
  anonymous_namespace_::uwfCfgFinalize(&CUwfProvider::s_UwfProvider, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001a010  mov     [rsp+arg_0], rbx
0x18001a015  push    rdi
0x18001a016  sub     rsp, 20h
0x18001a01a  mov     edi, ecx
0x18001a01c  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x18001a021  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x18001a026  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a02d  call    cs:__imp_EnterCriticalSection
0x18001a033  mov     dl, 1; bool
0x18001a035  lea     rcx, ?s_UwfProvider@CUwfProvider@@0V1@A; this
0x18001a03c  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x18001a041  mov     ebx, eax
0x18001a043  test    eax, eax
0x18001a045  js      short loc_18001A057
0x18001a047  mov     edx, edi
0x18001a049  lea     rcx, qword_18002A1D8
0x18001a050  call    ?set_OverlayType@CUwfManagement@@QEAAJW4_UWF_CONFIG_OVERLAY_TYPE@@@Z; CUwfManagement::set_OverlayType(_UWF_CONFIG_OVERLAY_TYPE)
0x18001a055  mov     ebx, eax
0x18001a057  xor     edx, edx
0x18001a059  lea     rcx, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x18001a060  call    _anonymous_namespace___uwfCfgFinalize
0x18001a065  mov     eax, ebx
0x18001a067  mov     rbx, [rsp+28h+arg_0]
0x18001a06c  add     rsp, 20h
0x18001a070  pop     rdi
0x18001a071  retn
```

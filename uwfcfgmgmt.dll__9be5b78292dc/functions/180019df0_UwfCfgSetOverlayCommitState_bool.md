# UwfCfgSetOverlayCommitState(bool)

- ea: `0x180019df0`
- end: `0x180019e65`
- name: `?UwfCfgSetOverlayCommitState@@YAJ_N@Z`
- size: `117`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000f364`
- `0x180014a90`
- `0x180015af0`
- `0x180017b90`
- `0x180019df0`
- `0x18001aa08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019e1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019e1b`

## pseudocode

```c
__int64 __fastcall UwfCfgSetOverlayCommitState(char a1)
{
  int v2; // ebx
  __int64 v3; // rdx

  anonymous_namespace_::uwfCfgApiBreakpoint();
  EnsureUwfFeatureState();
  if ( a1 )
  {
    EnterCriticalSection(&CUwfProvider::s_CritSec);
    v2 = CUwfProvider::Begin((CUwfProvider *)&CUwfProvider::s_UwfProvider, 0);
    if ( v2 >= 0 )
      v2 = CUwfVolumeDevice::set_RomModeDisposition(qword_18002A1F0, 4);
    CUwfManagement::Finalize((CUwfManagement *)qword_18002A1D8, v3);
    LeaveCriticalSection(&CUwfProvider::s_CritSec);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180019df0  push    rbx
0x180019df2  sub     rsp, 20h
0x180019df6  mov     bl, cl
0x180019df8  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180019dfd  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180019e02  test    bl, bl
0x180019e04  jnz     short loc_180019E0D
0x180019e06  mov     ebx, 80070057h
0x180019e0b  jmp     short loc_180019E5D
0x180019e0d  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019e14  lea     rbx, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x180019e1b  call    cs:__imp_EnterCriticalSection
0x180019e21  xor     edx, edx; bool
0x180019e23  mov     rcx, rbx; this
0x180019e26  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x180019e2b  mov     ebx, eax
0x180019e2d  test    eax, eax
0x180019e2f  js      short loc_180019E44
0x180019e31  mov     edx, 4
0x180019e36  lea     rcx, qword_18002A1F0
0x180019e3d  call    ?set_RomModeDisposition@CUwfVolumeDevice@@QEAAJW4_UWFVOL_ROM_MODE_DISPOSITION@@@Z; CUwfVolumeDevice::set_RomModeDisposition(_UWFVOL_ROM_MODE_DISPOSITION)
0x180019e42  mov     ebx, eax
0x180019e44  lea     rcx, qword_18002A1D8; this
0x180019e4b  call    ?Finalize@CUwfManagement@@QEAAJXZ; CUwfManagement::Finalize(void)
0x180019e50  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019e57  call    cs:__imp_LeaveCriticalSection
0x180019e5d  mov     eax, ebx
0x180019e5f  add     rsp, 20h
0x180019e63  pop     rbx
0x180019e64  retn
```

# UwfCfgGetOverlayCommitState(bool *)

- ea: `0x180018830`
- end: `0x1800188bb`
- name: `?UwfCfgGetOverlayCommitState@@YAJPEA_N@Z`
- size: `139`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000f364`
- `0x180014980`
- `0x180015af0`
- `0x180017b90`
- `0x180018830`
- `0x18001aa08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800188a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800188a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018855`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018855`

## pseudocode

```c
__int64 __fastcall UwfCfgGetOverlayCommitState(bool *a1)
{
  __int64 v2; // rdx
  int RomModeDisposition; // ebx
  int v5; // [rsp+38h] [rbp+10h] BYREF

  anonymous_namespace_::uwfCfgApiBreakpoint();
  EnsureUwfFeatureState();
  EnterCriticalSection(&CUwfProvider::s_CritSec);
  RomModeDisposition = CUwfProvider::Begin((CUwfProvider *)&CUwfProvider::s_UwfProvider, 0);
  if ( RomModeDisposition >= 0 )
  {
    v5 = 0;
    RomModeDisposition = CUwfVolumeDevice::get_RomModeDisposition(
                           (CUwfVolumeDevice *)qword_18002A1F0,
                           (enum _UWFVOL_ROM_MODE_DISPOSITION *)&v5);
    if ( RomModeDisposition >= 0 )
      *a1 = (v5 & 4) != 0;
  }
  CUwfManagement::Finalize((CUwfManagement *)qword_18002A1D8, v2);
  LeaveCriticalSection(&CUwfProvider::s_CritSec);
  return (unsigned int)RomModeDisposition;
}

```

## disassembly

```asm
0x180018830  mov     [rsp+arg_0], rbx
0x180018835  push    rdi
0x180018836  sub     rsp, 20h
0x18001883a  mov     rdi, rcx
0x18001883d  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180018842  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180018847  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001884e  lea     rbx, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x180018855  call    cs:__imp_EnterCriticalSection
0x18001885b  xor     edx, edx; bool
0x18001885d  mov     rcx, rbx; this
0x180018860  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x180018865  mov     ebx, eax
0x180018867  test    eax, eax
0x180018869  js      short loc_180018895
0x18001886b  lea     rdx, [rsp+28h+arg_8]; enum _UWFVOL_ROM_MODE_DISPOSITION *
0x180018870  mov     [rsp+28h+arg_8], 0
0x180018878  lea     rcx, qword_18002A1F0; this
0x18001887f  call    ?get_RomModeDisposition@CUwfVolumeDevice@@QEAAJPEAW4_UWFVOL_ROM_MODE_DISPOSITION@@@Z; CUwfVolumeDevice::get_RomModeDisposition(_UWFVOL_ROM_MODE_DISPOSITION *)
0x180018884  mov     ebx, eax
0x180018886  test    eax, eax
0x180018888  js      short loc_180018895
0x18001888a  mov     eax, [rsp+28h+arg_8]
0x18001888e  shr     eax, 2
0x180018891  and     al, 1
0x180018893  mov     [rdi], al
0x180018895  lea     rcx, qword_18002A1D8; this
0x18001889c  call    ?Finalize@CUwfManagement@@QEAAJXZ; CUwfManagement::Finalize(void)
0x1800188a1  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800188a8  call    cs:__imp_LeaveCriticalSection
0x1800188ae  mov     eax, ebx
0x1800188b0  mov     rbx, [rsp+28h+arg_0]
0x1800188b5  add     rsp, 20h
0x1800188b9  pop     rdi
0x1800188ba  retn
```

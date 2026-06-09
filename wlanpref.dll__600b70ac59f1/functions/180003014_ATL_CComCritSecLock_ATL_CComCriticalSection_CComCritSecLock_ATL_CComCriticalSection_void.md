# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180003014`
- end: `0x180003036`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `66`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000347c`
- `0x180003620`
- `0x180004aec`
- `0x180004f00`
- `0x180005550`
- `0x180007874`
- `0x180007b3c`
- `0x180009090`
- `0x18000a1c0`
- `0x18000baa0`
- `0x18000ce08`
- `0x18000dd64`
- `0x18000de44`
- `0x18000df24`
- `0x180011ef0`
- `0x180011fe0`
- `0x180012380`
- `0x180012610`
- `0x180013410`
- `0x1800134f4`
- `0x180013ac8`
- `0x180013bb4`
- `0x180013fd4`
- `0x1800140c0`
- `0x1800157ec`
- `0x180020030`
- `0x180023fb0`
- `0x1800247f0`
- `0x1800273d0`
- `0x18002749c`
- `0x180027558`
- `0x180027594`
- `0x180029fc0`
- `0x18002a260`
- `0x18002a2b0`
- `0x18002a2ec`
- `0x18002a340`
- `0x18002a410`
- `0x18002a630`
- `0x18002a690`
- `0x18002a6d0`
- `0x18002a710`
- `0x18002a870`
- `0x18002a980`
- `0x18002aaf0`
- `0x18002ab60`
- `0x18002aba0`
- `0x18002af00`
- `0x18002b320`
- `0x18002b5dc`

## callees

- `0x180003014`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003026`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
  {
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
    *(_BYTE *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180003014  push    rbx
0x180003016  sub     rsp, 20h
0x18000301a  cmp     byte ptr [rcx+8], 0
0x18000301e  mov     rbx, rcx
0x180003021  jz      short loc_180003030
0x180003023  mov     rcx, [rcx]; lpCriticalSection
0x180003026  call    cs:__imp_LeaveCriticalSection
0x18000302c  mov     byte ptr [rbx+8], 0
0x180003030  add     rsp, 20h
0x180003034  pop     rbx
0x180003035  retn
```

# SDiagPrvSyncObject::Lock(void)

- ea: `0x1800037fc`
- end: `0x180003815`
- name: `?Lock@SDiagPrvSyncObject@@IEAAXXZ`
- size: `25`
- prototype: `void __fastcall(SDiagPrvSyncObject *__hidden this)`
- caller_count: `49`
- callee_count: `1`
- tags: ``

## callers

- `0x180003930`
- `0x180003a30`
- `0x180003b50`
- `0x180003c30`
- `0x1800042c4`
- `0x1800043a8`
- `0x1800046b0`
- `0x180004a30`
- `0x180004cf0`
- `0x180004f50`
- `0x180005040`
- `0x180005190`
- `0x1800057b4`
- `0x180005af8`
- `0x180005ce0`
- `0x180005e30`
- `0x180006088`
- `0x180006170`
- `0x180006200`
- `0x1800062c0`
- `0x1800063fc`
- `0x180010550`
- `0x180010634`
- `0x180010938`
- `0x180010e88`
- `0x18001114c`
- `0x1800113a0`
- `0x1800115e0`
- `0x1800116d0`
- `0x180011820`
- `0x18001374c`
- `0x180013b60`
- `0x180013ca0`
- `0x180013de0`
- `0x180013f20`
- `0x180014060`
- `0x1800141a0`
- `0x180014280`
- `0x1800143b0`
- `0x1800144f0`
- `0x180014630`
- `0x180014760`
- `0x180014840`
- `0x180014980`
- `0x180014ac0`
- `0x180014c0c`
- `0x180014d44`
- `0x180014e7c`
- `0x180014f1c`

## callees

- `0x1800037fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000380a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000380a`

## pseudocode

```c
void __fastcall SDiagPrvSyncObject::Lock(SDiagPrvSyncObject *this)
{
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x1800037fc  sub     rsp, 28h
0x180003800  cmp     dword ptr [rcx+8], 0
0x180003804  jz      short loc_180003810
0x180003806  add     rcx, 10h; lpCriticalSection
0x18000380a  call    cs:__imp_EnterCriticalSection
0x180003810  add     rsp, 28h
0x180003814  retn
```

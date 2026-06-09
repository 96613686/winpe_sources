# SDiagPrvSyncObject::~SDiagPrvSyncObject(void)

- ea: `0x180003514`
- end: `0x180003538`
- name: `??1SDiagPrvSyncObject@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(SDiagPrvSyncObject *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003660`
- `0x180004574`
- `0x1800059c0`
- `0x1800065bc`
- `0x180010800`
- `0x180013480`
- `0x18001847c`

## callees

- `0x180003514`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000352c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000352c`

## pseudocode

```c
void __fastcall SDiagPrvSyncObject::~SDiagPrvSyncObject(SDiagPrvSyncObject *this)
{
  *(_QWORD *)this = &SDiagPrvSyncObject::`vftable';
  if ( *((_DWORD *)this + 2) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180003514  sub     rsp, 28h
0x180003518  lea     rax, ??_7SDiagPrvSyncObject@@6B@; const SDiagPrvSyncObject::`vftable'
0x18000351f  mov     [rcx], rax
0x180003522  cmp     dword ptr [rcx+8], 0
0x180003526  jz      short loc_180003533
0x180003528  add     rcx, 10h; lpCriticalSection
0x18000352c  call    cs:__imp_DeleteCriticalSection
0x180003532  nop
0x180003533  add     rsp, 28h
0x180003537  retn
```

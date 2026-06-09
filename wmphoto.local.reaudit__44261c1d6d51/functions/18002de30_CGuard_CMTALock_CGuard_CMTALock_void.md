# CGuard<CMTALock>::~CGuard<CMTALock>(void)

- ea: `0x18002de30`
- end: `0x18002de65`
- name: `??1?$CGuard@VCMTALock@@@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `46`
- callee_count: `1`
- tags: ``

## callers

- `0x180028690`
- `0x180031850`
- `0x180038830`
- `0x180038870`
- `0x1800388b0`
- `0x180038980`
- `0x180038a30`
- `0x180038a70`
- `0x180038f80`
- `0x180039080`
- `0x180039120`
- `0x180039410`
- `0x180039480`
- `0x1800395a0`
- `0x1800397d0`
- `0x180039850`
- `0x180039930`
- `0x1800399f0`
- `0x180039b30`
- `0x180039bd0`
- `0x180039d50`
- `0x180039e90`
- `0x18003a5c0`
- `0x18003a7a0`
- `0x18003aac0`
- `0x18003ab30`
- `0x18003abd0`
- `0x18003acb0`
- `0x18003adf0`
- `0x18003ae90`
- `0x18003aed0`
- `0x18003af20`
- `0x18003af80`
- `0x18003b050`
- `0x18003b120`
- `0x18003b1e0`
- `0x18003b400`
- `0x18003b660`
- `0x18003b700`
- `0x18003b920`
- `0x18003ba50`
- `0x18003bb40`
- `0x18003bb90`
- `0x180043f2c`
- `0x18004415d`
- `0x18004419d`

## callees

- `0x18002de30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de4b`

## pseudocode

```c
void __fastcall CGuard<CMTALock>::~CGuard<CMTALock>(__int64 *a1)
{
  __int64 v1; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( *(_BYTE *)(v1 + 48) )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18002de30  push    rbx
0x18002de32  sub     rsp, 20h
0x18002de36  mov     rax, [rcx]
0x18002de39  mov     rbx, rcx
0x18002de3c  test    rax, rax
0x18002de3f  jz      short loc_18002DE5E
0x18002de41  lea     rcx, [rax+8]; lpCriticalSection
0x18002de45  cmp     byte ptr [rcx+28h], 0
0x18002de49  jz      short loc_18002DE57
0x18002de4b  call    cs:__imp_LeaveCriticalSection
0x18002de52  nop     dword ptr [rax+rax+00h]
0x18002de57  mov     qword ptr [rbx], 0
0x18002de5e  add     rsp, 20h
0x18002de62  pop     rbx
0x18002de63  retn
```

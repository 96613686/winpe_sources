# CGuard<CMTALock>::~CGuard<CMTALock>(void)

- ea: `0x18002db34`
- end: `0x18002db62`
- name: `??1?$CGuard@VCMTALock@@@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `46`
- callee_count: `1`
- tags: ``

## callers

- `0x180028530`
- `0x1800314f0`
- `0x1800381f0`
- `0x180038230`
- `0x180038270`
- `0x180038340`
- `0x1800383e0`
- `0x180038420`
- `0x180038920`
- `0x180038a00`
- `0x180038a90`
- `0x180038d70`
- `0x180038de0`
- `0x180038ee0`
- `0x180039100`
- `0x180039170`
- `0x180039250`
- `0x180039300`
- `0x180039440`
- `0x1800394d0`
- `0x180039630`
- `0x180039770`
- `0x180039e90`
- `0x18003a070`
- `0x18003a370`
- `0x18003a3e0`
- `0x18003a470`
- `0x18003a540`
- `0x18003a670`
- `0x18003a710`
- `0x18003a750`
- `0x18003a7a0`
- `0x18003a7f0`
- `0x18003a8c0`
- `0x18003a980`
- `0x18003aa30`
- `0x18003ac50`
- `0x18003aeb0`
- `0x18003af50`
- `0x18003b160`
- `0x18003b290`
- `0x18003b370`
- `0x18003b3c0`
- `0x18004371c`
- `0x18004394d`
- `0x18004398d`

## callees

- `0x18002db34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002db4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002db4f`

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
0x18002db34  push    rbx
0x18002db36  sub     rsp, 20h
0x18002db3a  mov     rax, [rcx]
0x18002db3d  mov     rbx, rcx
0x18002db40  test    rax, rax
0x18002db43  jz      short loc_18002DB5C
0x18002db45  lea     rcx, [rax+8]; lpCriticalSection
0x18002db49  cmp     byte ptr [rcx+28h], 0
0x18002db4d  jz      short loc_18002DB55
0x18002db4f  call    cs:__imp_LeaveCriticalSection
0x18002db55  mov     qword ptr [rbx], 0
0x18002db5c  add     rsp, 20h
0x18002db60  pop     rbx
0x18002db61  retn
```

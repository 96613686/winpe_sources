# CVolume::GetVolumeId(void)

- ea: `0x180003180`
- end: `0x1800031df`
- name: `?GetVolumeId@CVolume@@QEAA?BUCVolumeId@@XZ`
- size: `95`
- prototype: `_OWORD *__fastcall(__int64, _OWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002488`
- `0x1800030c0`
- `0x180005660`
- `0x18000c968`

## callees

- `0x180003180`
- `0x18000d038`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800031cc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800031cc`

## pseudocode

```c
_OWORD *__fastcall CVolume::GetVolumeId(__int64 a1, _OWORD *a2)
{
  int v4; // esi
  bool v5; // zf

  v4 = 0;
  while ( 1 )
  {
    v5 = (*(_BYTE *)(a1 + 568) & 1) == 0;
    *a2 = *(_OWORD *)(a1 + 264);
    if ( v5 )
      break;
    if ( (unsigned int)++v4 > 0xBB8 )
      TrkRaiseWin32Error(258);
    Sleep(0xAu);
  }
  return a2;
}

```

## disassembly

```asm
0x180003180  mov     [rsp+arg_0], rbx
0x180003185  mov     [rsp+arg_8], rsi
0x18000318a  push    rdi
0x18000318b  sub     rsp, 20h
0x18000318f  mov     rbx, rdx
0x180003192  mov     rdi, rcx
0x180003195  xor     esi, esi
0x180003197  test    byte ptr [rdi+238h], 1
0x18000319e  movups  xmm0, xmmword ptr [rdi+108h]
0x1800031a5  movups  xmmword ptr [rbx], xmm0
0x1800031a8  jnz     short loc_1800031BD
0x1800031aa  mov     rsi, [rsp+28h+arg_8]
0x1800031af  mov     rax, rbx
0x1800031b2  mov     rbx, [rsp+28h+arg_0]
0x1800031b7  add     rsp, 20h
0x1800031bb  pop     rdi
0x1800031bc  retn
0x1800031bd  inc     esi
0x1800031bf  cmp     esi, 0BB8h
0x1800031c5  ja      short loc_1800031D4
0x1800031c7  mov     ecx, 0Ah; dwMilliseconds
0x1800031cc  call    cs:__imp_Sleep
0x1800031d2  jmp     short loc_180003197
0x1800031d4  mov     ecx, 102h; int
0x1800031d9  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
```

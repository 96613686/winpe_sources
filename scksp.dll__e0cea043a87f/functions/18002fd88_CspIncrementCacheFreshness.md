# CspIncrementCacheFreshness

- ea: `0x18002fd88`
- end: `0x18002fe00`
- name: `CspIncrementCacheFreshness`
- size: `120`
- prototype: `__int64 __fastcall(struct _CARD_STATE *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d368`
- `0x18002d444`
- `0x18002d504`
- `0x18002d61c`
- `0x18002e3bc`

## callees

- `0x18002f64c`
- `0x18002f794`
- `0x18002fd88`

## pseudocode

```c
unsigned int __fastcall CspIncrementCacheFreshness(struct _CARD_STATE *a1, char a2, __int64 a3)
{
  unsigned int result; // eax
  __int64 v7; // rcx

  *(_DWORD *)a3 = 0;
  *(_WORD *)(a3 + 4) = 0;
  result = I_CspReadCardCacheFile(a1, (struct _CARD_CACHE_FILE_FORMAT *)a3);
  if ( !result )
  {
    if ( (a2 & 1) != 0 )
      ++*(_BYTE *)(a3 + 1);
    if ( (a2 & 2) != 0 )
      ++*(_WORD *)(a3 + 2);
    if ( (a2 & 4) != 0 )
      ++*(_WORD *)(a3 + 4);
    v7 = *((_QWORD *)a1 + 76);
    *(_DWORD *)v7 = *(_DWORD *)a3;
    *(_WORD *)(v7 + 4) = *(_WORD *)(a3 + 4);
    return I_CspWriteCardCacheFile(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18002fd88  mov     [rsp+arg_0], rbx
0x18002fd8d  mov     [rsp+arg_8], rsi
0x18002fd92  push    rdi
0x18002fd93  sub     rsp, 20h
0x18002fd97  xor     eax, eax
0x18002fd99  mov     edi, edx
0x18002fd9b  mov     [r8], eax
0x18002fd9e  mov     rdx, r8; struct _CARD_CACHE_FILE_FORMAT *
0x18002fda1  mov     [r8+4], ax
0x18002fda6  mov     rbx, r8
0x18002fda9  mov     rsi, rcx
0x18002fdac  call    ?I_CspReadCardCacheFile@@YAKPEAU_CARD_STATE@@PEAU_CARD_CACHE_FILE_FORMAT@@@Z; I_CspReadCardCacheFile(_CARD_STATE *,_CARD_CACHE_FILE_FORMAT *)
0x18002fdb1  test    eax, eax
0x18002fdb3  jnz     short loc_18002FDF0
0x18002fdb5  mov     ax, 1
0x18002fdb9  test    al, dil
0x18002fdbc  jz      short loc_18002FDC1
0x18002fdbe  add     [rbx+1], al
0x18002fdc1  test    dil, 2
0x18002fdc5  jz      short loc_18002FDCB
0x18002fdc7  add     [rbx+2], ax
0x18002fdcb  test    dil, 4
0x18002fdcf  jz      short loc_18002FDD5
0x18002fdd1  add     [rbx+4], ax
0x18002fdd5  mov     rcx, [rsi+260h]
0x18002fddc  mov     eax, [rbx]
0x18002fdde  mov     [rcx], eax
0x18002fde0  movzx   eax, word ptr [rbx+4]
0x18002fde4  mov     [rcx+4], ax
0x18002fde8  mov     rcx, rsi; struct _CARD_STATE *
0x18002fdeb  call    ?I_CspWriteCardCacheFile@@YAKPEAU_CARD_STATE@@@Z; I_CspWriteCardCacheFile(_CARD_STATE *)
0x18002fdf0  mov     rbx, [rsp+28h+arg_0]
0x18002fdf5  mov     rsi, [rsp+28h+arg_8]
0x18002fdfa  add     rsp, 20h
0x18002fdfe  pop     rdi
0x18002fdff  retn
```

# TextLogDeletePendingRenameTag

- ea: `0x180016d08`
- end: `0x180016d7b`
- name: `TextLogDeletePendingRenameTag`
- size: `115`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001725c`

## callees

- `0x18000b890`
- `0x180016cac`
- `0x180016d08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016d5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016d5e`

## pseudocode

```c
_BOOL8 __fastcall TextLogDeletePendingRenameTag(__int64 a1)
{
  DWORD v1; // edi
  unsigned int v2; // ebx
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  v1 = 0;
  v2 = 0;
  v6 = 0;
  v5 = 0;
  while ( (unsigned int)TextLogEnumerateOpenSections(a1, v2, &v5) )
  {
    if ( !DWORD1(v5) && (v6 & 0x10000) != 0 )
    {
      v1 = TextLogDeleteCtlTag(a1, v2);
      break;
    }
    ++v2;
  }
  SetLastError(v1);
  return v1 == 0;
}

```

## disassembly

```asm
0x180016d08  mov     [rsp+arg_0], rbx
0x180016d0d  mov     [rsp+arg_8], rsi
0x180016d12  push    rdi
0x180016d13  sub     rsp, 40h
0x180016d17  xor     edi, edi
0x180016d19  xor     ebx, ebx
0x180016d1b  xor     eax, eax
0x180016d1d  xorps   xmm0, xmm0
0x180016d20  mov     [rsp+48h+var_18], eax
0x180016d24  mov     rsi, rcx
0x180016d27  movups  [rsp+48h+var_28], xmm0
0x180016d2c  lea     r8, [rsp+48h+var_28]
0x180016d31  mov     edx, ebx
0x180016d33  mov     rcx, rsi
0x180016d36  call    TextLogEnumerateOpenSections
0x180016d3b  test    eax, eax
0x180016d3d  jz      short loc_180016D5C
0x180016d3f  cmp     dword ptr [rsp+48h+var_28+4], edi
0x180016d43  jnz     short loc_180016D4C
0x180016d45  test    byte ptr [rsp+48h+var_18+2], 1
0x180016d4a  jnz     short loc_180016D50
0x180016d4c  inc     ebx
0x180016d4e  jmp     short loc_180016D2C
0x180016d50  mov     edx, ebx
0x180016d52  mov     rcx, rsi
0x180016d55  call    TextLogDeleteCtlTag
0x180016d5a  mov     edi, eax
0x180016d5c  mov     ecx, edi; dwErrCode
0x180016d5e  call    cs:__imp_SetLastError
0x180016d64  mov     rbx, [rsp+48h+arg_0]
0x180016d69  xor     eax, eax
0x180016d6b  mov     rsi, [rsp+48h+arg_8]
0x180016d70  test    edi, edi
0x180016d72  setz    al
0x180016d75  add     rsp, 40h
0x180016d79  pop     rdi
0x180016d7a  retn
```

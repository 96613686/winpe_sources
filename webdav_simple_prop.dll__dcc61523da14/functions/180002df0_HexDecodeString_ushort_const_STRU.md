# HexDecodeString(ushort const *,STRU *)

- ea: `0x180002df0`
- end: `0x180002f05`
- name: `?HexDecodeString@@YAJPEBGPEAVSTRU@@@Z`
- size: `277`
- prototype: `int __fastcall(const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cdc`

## callees

- `0x180002df0`

## import_xrefs

- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180002ef4`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180002ef4`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180002e27`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180002e27`

## pseudocode

```c
int __fastcall HexDecodeString(const unsigned __int16 *a1, struct STRU *a2)
{
  __int64 v4; // rdx
  int result; // eax
  unsigned __int16 v6; // cx
  const unsigned __int16 *v7; // rbx
  _WORD *v8; // r10
  unsigned __int16 v9; // dx
  unsigned __int16 v10; // r9
  unsigned __int16 v11; // r11
  __int16 v12; // r8
  __int16 v13; // dx
  __int16 v14; // ax

  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( (v4 & 3) != 0 )
    return -2147024809;
  result = STRU::Resize(a2, 2 * v4 + 2);
  if ( result >= 0 )
  {
    v6 = *a1;
    v7 = a1 + 1;
    v8 = (_WORD *)*((_QWORD *)a2 + 4);
    while ( v6 )
    {
      v9 = *v7;
      v10 = v7[1];
      v11 = v7[2];
      if ( (unsigned __int16)(v6 - 48) > 9u )
      {
        if ( (unsigned __int16)(v6 - 65) > 5u )
          v6 = 0;
        else
          v6 -= 55;
      }
      v12 = v9 - 48;
      if ( (unsigned __int16)(v9 - 48) > 9u )
      {
        v12 = v9 - 55;
        if ( (unsigned __int16)(v9 - 65) > 5u )
          v12 = 0;
      }
      v13 = v10 - 48;
      if ( (unsigned __int16)(v10 - 48) > 9u )
      {
        v13 = v10 - 55;
        if ( (unsigned __int16)(v10 - 65) > 5u )
          v13 = 0;
      }
      v14 = v11 - 48;
      if ( (unsigned __int16)(v11 - 48) > 9u )
      {
        v14 = v11 - 55;
        if ( (unsigned __int16)(v11 - 65) > 5u )
          v14 = 0;
      }
      *v8++ = v14 | (16 * (v13 | (16 * (v12 | (16 * v6)))));
      v6 = v7[3];
      v7 += 4;
    }
    *v8 = 0;
    STRU::SyncWithBuffer(a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002df0  push    rbx
0x180002df2  push    rbp
0x180002df3  push    rsi
0x180002df4  push    rdi
0x180002df5  sub     rsp, 28h
0x180002df9  mov     rdi, rdx
0x180002dfc  mov     rbx, rcx
0x180002dff  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002e03  xor     ebp, ebp
0x180002e05  inc     rdx
0x180002e08  cmp     [rcx+rdx*2], bp
0x180002e0c  jnz     short loc_180002E05
0x180002e0e  test    dl, 3
0x180002e11  jz      short loc_180002E1D
0x180002e13  mov     eax, 80070057h
0x180002e18  jmp     loc_180002EFC
0x180002e1d  lea     edx, ds:2[rdx*2]
0x180002e24  mov     rcx, rdi
0x180002e27  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180002e2d  test    eax, eax
0x180002e2f  js      loc_180002EFC
0x180002e35  movzx   ecx, word ptr [rbx]
0x180002e38  add     rbx, 2
0x180002e3c  mov     r10, [rdi+20h]
0x180002e40  jmp     loc_180002EE4
0x180002e45  movzx   edx, word ptr [rbx]
0x180002e48  lea     eax, [rcx-30h]
0x180002e4b  movzx   r9d, word ptr [rbx+2]
0x180002e50  lea     rsi, [rbx+6]
0x180002e54  movzx   r11d, word ptr [rbx+4]
0x180002e59  cmp     ax, 9
0x180002e5d  jbe     short loc_180002E70
0x180002e5f  lea     eax, [rcx-41h]
0x180002e62  cmp     ax, 5
0x180002e66  ja      short loc_180002E6E
0x180002e68  sub     cx, 37h ; '7'
0x180002e6c  jmp     short loc_180002E70
0x180002e6e  mov     ecx, ebp
0x180002e70  lea     r8d, [rdx-30h]
0x180002e74  cmp     r8w, 9
0x180002e79  jbe     short loc_180002E8B
0x180002e7b  lea     eax, [rdx-41h]
0x180002e7e  lea     r8d, [rdx-37h]
0x180002e82  cmp     ax, 5
0x180002e86  jbe     short loc_180002E8B
0x180002e88  mov     r8d, ebp
0x180002e8b  lea     edx, [r9-30h]
0x180002e8f  cmp     dx, 9
0x180002e93  jbe     short loc_180002EA5
0x180002e95  lea     eax, [r9-41h]
0x180002e99  lea     edx, [r9-37h]
0x180002e9d  cmp     ax, 5
0x180002ea1  jbe     short loc_180002EA5
0x180002ea3  mov     edx, ebp
0x180002ea5  lea     eax, [r11-30h]
0x180002ea9  cmp     ax, 9
0x180002ead  jbe     short loc_180002EBF
0x180002eaf  lea     eax, [r11-41h]
0x180002eb3  cmp     ax, 5
0x180002eb7  lea     eax, [r11-37h]
0x180002ebb  jbe     short loc_180002EBF
0x180002ebd  mov     eax, ebp
0x180002ebf  shl     cx, 4
0x180002ec3  or      cx, r8w
0x180002ec7  shl     cx, 4
0x180002ecb  or      cx, dx
0x180002ece  shl     cx, 4
0x180002ed2  or      cx, ax
0x180002ed5  mov     [r10], cx
0x180002ed9  add     r10, 2
0x180002edd  movzx   ecx, word ptr [rsi]
0x180002ee0  add     rbx, 8
0x180002ee4  test    cx, cx
0x180002ee7  jnz     loc_180002E45
0x180002eed  mov     rcx, rdi
0x180002ef0  mov     [r10], bp
0x180002ef4  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180002efa  xor     eax, eax
0x180002efc  add     rsp, 28h
0x180002f00  pop     rdi
0x180002f01  pop     rsi
0x180002f02  pop     rbp
0x180002f03  pop     rbx
0x180002f04  retn
```

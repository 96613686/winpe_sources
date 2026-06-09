# UdfVerifyDescriptor

- ea: `0x140049020`
- end: `0x1400491ca`
- name: `UdfVerifyDescriptor`
- size: `426`
- prototype: `char __fastcall(__int64, __int64, __int16, unsigned int, int, char)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c0ec`
- `0x14002cf5c`
- `0x14002eb9c`
- `0x14003aa44`
- `0x14003b79c`
- `0x14003c2e4`
- `0x1400483a8`
- `0x140048c24`
- `0x1400491d0`
- `0x14004d074`
- `0x14004e020`
- `0x140056ea0`

## callees

- `0x140049020`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400491b6`
- `ntoskrnl!ExRaiseStatus` at `0x1400491b6`

## pseudocode

```c
char __fastcall UdfVerifyDescriptor(__int64 a1, __int64 a2, __int16 a3, unsigned int a4, int a5, char a6)
{
  __int16 v6; // ax
  char v10; // bl
  char v11; // dl
  _BYTE *v12; // rax
  _BYTE *i; // rcx
  unsigned __int8 *v14; // r8
  unsigned __int8 *j; // rcx
  unsigned __int64 v16; // rdx
  unsigned __int16 v17; // ax
  int v18; // r9d
  __int64 v19; // rcx
  __int16 v21; // cx
  __int16 v22; // r8

  v6 = *(_WORD *)(a2 + 2);
  if ( v6 != 2 )
  {
    if ( v6 != 3 || (v22 = *(_WORD *)(*(_QWORD *)(a1 + 16) + 2136LL), v22 != 10) && v22 != -1 )
    {
      v10 = a6;
      goto LABEL_31;
    }
  }
  v10 = a6;
  if ( *(_DWORD *)(a2 + 12) != a5 && (a6 & 4) == 0 )
    goto LABEL_31;
  if ( a3 && *(_WORD *)a2 != a3 )
    goto LABEL_31;
  if ( (a6 & 2) == 0 )
  {
    v21 = *(_WORD *)(a2 + 6);
    if ( v21 )
    {
      if ( v21 != *(_WORD *)(*(_QWORD *)(a1 + 16) + 2140LL) )
        goto LABEL_31;
    }
  }
  v11 = 0;
  v12 = (_BYTE *)(a2 + 4);
  for ( i = (_BYTE *)a2; i < v12; ++i )
    v11 += *i;
  v14 = (unsigned __int8 *)(a2 + 16);
  for ( j = (unsigned __int8 *)(a2 + 5); j < v14; ++j )
    v11 += *j;
  if ( *v12 != v11 )
    goto LABEL_31;
  v16 = *(unsigned __int16 *)(a2 + 10);
  if ( (_WORD)v16 )
  {
    if ( v16 <= (unsigned __int64)a4 - 16 )
    {
      v17 = 0;
      v18 = *(unsigned __int16 *)(a2 + 10);
      do
      {
        v19 = *v14++;
        v17 = *((_WORD *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink->Flink + (v19 ^ ((unsigned __int64)v17 >> 8)))
            ^ (v17 << 8);
        --v18;
      }
      while ( v18 );
      if ( *(_WORD *)(a2 + 8) == v17 )
        return 1;
    }
  }
  else if ( !*(_WORD *)(a2 + 8) && a3 == 264 )
  {
    return 1;
  }
LABEL_31:
  if ( (v10 & 1) == 0 )
  {
    *(_DWORD *)(a1 + 24) = -1073741761;
    ExRaiseStatus(-1073741761);
  }
  return 0;
}

```

## disassembly

```asm
0x140049020  mov     [rsp+arg_0], rbx
0x140049025  push    rdi
0x140049026  sub     rsp, 20h
0x14004902a  movzx   eax, word ptr [rdx+2]
0x14004902e  mov     rdi, rcx
0x140049031  mov     ecx, 2
0x140049036  movzx   r10d, r8w
0x14004903a  mov     r11, rdx
0x14004903d  cmp     cx, ax
0x140049040  jnz     loc_14004914C
0x140049046  mov     eax, [rsp+28h+arg_20]
0x14004904a  mov     ebx, [rsp+28h+arg_28]
0x14004904e  cmp     [rdx+0Ch], eax
0x140049051  jnz     loc_14004919C
0x140049057  xor     eax, eax
0x140049059  cmp     ax, r10w
0x14004905d  jnz     loc_140049140
0x140049063  test    bl, 2
0x140049066  jz      loc_140049120
0x14004906c  xor     dl, dl
0x14004906e  lea     rax, [r11+4]
0x140049072  mov     rcx, r11
0x140049075  cmp     r11, rax
0x140049078  jb      loc_140049110
0x14004907e  lea     r8, [r11+10h]
0x140049082  lea     rcx, [r11+5]
0x140049086  cmp     rcx, r8
0x140049089  jb      short loc_140049100
0x14004908b  cmp     [rax], dl
0x14004908d  jnz     loc_1400491A5
0x140049093  movzx   edx, word ptr [r11+0Ah]
0x140049098  test    dx, dx
0x14004909b  jz      loc_140049182
0x1400490a1  mov     ecx, r9d
0x1400490a4  sub     rcx, 10h
0x1400490a8  cmp     rdx, rcx
0x1400490ab  ja      loc_1400491A5
0x1400490b1  xor     eax, eax
0x1400490b3  mov     r9d, edx
0x1400490b6  nop     word ptr [rax+rax+00000000h]
0x1400490c0  movzx   ecx, byte ptr [r8]
0x1400490c4  lea     r8, [r8+1]
0x1400490c8  movzx   edx, ax
0x1400490cb  shr     rdx, 8
0x1400490cf  xor     rdx, rcx
0x1400490d2  shl     ax, 8
0x1400490d6  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x1400490dd  xor     ax, [rcx+rdx*2]
0x1400490e1  add     r9d, 0FFFFFFFFh
0x1400490e5  jnz     short loc_1400490C0
0x1400490e7  cmp     [r11+8], ax
0x1400490ec  jnz     loc_1400491A5
0x1400490f2  mov     al, 1
0x1400490f4  mov     rbx, [rsp+28h+arg_0]
0x1400490f9  add     rsp, 20h
0x1400490fd  pop     rdi
0x1400490fe  retn
0x140049100  add     dl, [rcx]
0x140049102  inc     rcx
0x140049105  cmp     rcx, r8
0x140049108  jnb     short loc_14004908B
0x14004910a  jmp     short loc_140049100
0x140049110  add     dl, [rcx]
0x140049112  inc     rcx
0x140049115  cmp     rcx, rax
0x140049118  jnb     loc_14004907E
0x14004911e  jmp     short loc_140049110
0x140049120  movzx   ecx, word ptr [rdx+6]
0x140049124  test    cx, cx
0x140049127  jz      loc_14004906C
0x14004912d  mov     rax, [rdi+10h]
0x140049131  cmp     cx, [rax+85Ch]
0x140049138  jz      loc_14004906C
0x14004913e  jmp     short loc_1400491A5
0x140049140  cmp     [rdx], r10w
0x140049144  jz      loc_140049063
0x14004914a  jmp     short loc_1400491A5
0x14004914c  mov     ecx, 3
0x140049151  cmp     cx, ax
0x140049154  jnz     short loc_14004917C
0x140049156  mov     rax, [rdi+10h]
0x14004915a  movzx   r8d, word ptr [rax+858h]
0x140049162  cmp     r8w, 0Ah
0x140049167  jz      loc_140049046
0x14004916d  mov     eax, 0FFFFh
0x140049172  cmp     r8w, ax
0x140049176  jz      loc_140049046
0x14004917c  mov     ebx, [rsp+28h+arg_28]
0x140049180  jmp     short loc_1400491A5
0x140049182  xor     eax, eax
0x140049184  cmp     ax, [r11+8]
0x140049189  jnz     short loc_1400491A5
0x14004918b  mov     eax, 108h
0x140049190  cmp     ax, r10w
0x140049194  jz      loc_1400490F2
0x14004919a  jmp     short loc_1400491A5
0x14004919c  test    bl, 4
0x14004919f  jnz     loc_140049057
0x1400491a5  test    bl, 1
0x1400491a8  jnz     short loc_1400491C3
0x1400491aa  mov     ecx, 0C000003Fh; Status
0x1400491af  mov     dword ptr [rdi+18h], 0C000003Fh
0x1400491b6  call    cs:__imp_ExRaiseStatus
0x1400491c3  xor     al, al
0x1400491c5  jmp     loc_1400490F4
```

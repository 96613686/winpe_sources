# PriProcessMessage

- ea: `0x14000b070`
- end: `0x14000b410`
- name: `PriProcessMessage`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000a960`

## callees

- `0x14000223c`
- `0x140009008`
- `0x140009050`
- `0x140009098`
- `0x14000adb4`
- `0x14000b070`
- `0x14000b418`
- `0x14000b614`
- `0x14000b784`
- `0x14000b9bc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000b0d0`
- `ntoskrnl!ProbeForRead` at `0x14000b0d0`
- `ntoskrnl!ProbeForWrite` at `0x14000b0ee`
- `ntoskrnl!ProbeForWrite` at `0x14000b0ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3dd`

## pseudocode

```c
__int64 __fastcall PriProcessMessage(
        __int64 a1,
        volatile void *a2,
        unsigned int a3,
        char *a4,
        SIZE_T Length,
        _DWORD *a6)
{
  unsigned __int64 v7; // rdi
  _DWORD *v10; // r12
  int v11; // ebx
  _OWORD *v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  char *v18; // rdx
  PVOID P; // [rsp+48h] [rbp-60h] BYREF
  char *v21; // [rsp+50h] [rbp-58h] BYREF
  char *v22; // [rsp+58h] [rbp-50h] BYREF
  __int64 v23; // [rsp+60h] [rbp-48h] BYREF
  __int64 v24; // [rsp+68h] [rbp-40h] BYREF
  _QWORD v25[2]; // [rsp+70h] [rbp-38h] BYREF
  char *v26; // [rsp+B8h] [rbp+10h] BYREF

  v7 = a3;
  P = 0;
  if ( !a2 )
    return 3221225485LL;
  if ( a3 < 0x10 )
    return 3221225485LL;
  v10 = a6;
  if ( !a6 )
    return 3221225485LL;
  ProbeForRead(a2, a3, 1u);
  if ( a4 )
    ProbeForWrite(a4, (unsigned int)Length, 1u);
  v11 = PriDuplicateBufferFromUser(&P, a2, (unsigned int)v7);
  if ( v11 >= 0 )
  {
    v12 = P;
    if ( *((_DWORD *)P + 2) > (unsigned int)v7
      || *(_DWORD *)P != 1111638594
      || *((_WORD *)P + 2) != 3
      || *((_WORD *)P + 3) > 1u )
    {
      goto LABEL_44;
    }
    if ( *((_DWORD *)P + 3) != 2 )
    {
      switch ( *((_DWORD *)P + 3) )
      {
        case 3:
          if ( (unsigned int)v7 >= 0x14 )
            *(_DWORD *)a1 = *((_DWORD *)P + 4);
          if ( a4 && (unsigned int)Length >= 4 )
          {
            RtlWriteUShortToUser(a4);
            RtlWriteUShortToUser(a4 + 2);
          }
          goto LABEL_45;
        case 5:
          if ( (unsigned int)v7 < 0x30 || v7 < (unsigned __int64)*((unsigned __int16 *)P + 20) + 48 || !a4 )
            goto LABEL_44;
          if ( (unsigned int)Length < 8 )
          {
            v11 = -2147483643;
            goto LABEL_45;
          }
          v26 = a4;
          v22 = 0;
          v25[0] = 0;
          v25[1] = (char *)P + 42;
          WORD1(v25[0]) = *((_WORD *)P + 20);
          LOWORD(v25[0]) = WORD1(v25[0]);
          v17 = PriStubCreateChild(
                  *((_QWORD *)P + 2),
                  *((unsigned int *)P + 6),
                  *((unsigned int *)P + 7),
                  *((unsigned int *)P + 8),
                  *((_DWORD *)P + 9),
                  v25,
                  &v22);
          v18 = v22;
          break;
        case 6:
          if ( (unsigned int)v7 >= 0x38 && v7 >= (unsigned __int64)*((unsigned int *)P + 12) + 56 )
          {
            v11 = PriStubRename(*((HANDLE *)P + 2));
            goto LABEL_45;
          }
          goto LABEL_44;
        case 7:
          if ( (unsigned int)v7 < 0x28 || (unsigned int)Length < 8 || !a4 )
            goto LABEL_44;
          v24 = *((_QWORD *)P + 3);
          v23 = *((_QWORD *)P + 4);
          v21 = 0;
          v26 = a4;
          v17 = PriSubsumeContext(*((_QWORD *)P + 2), &v24, &v23, &v21);
          v18 = v21;
          break;
        default:
          if ( *((_DWORD *)P + 3) == 8 && (unsigned int)v7 >= 0x28 && (_DWORD)Length )
          {
            v13 = *((_QWORD *)P + 2);
            v14 = *((_QWORD *)P + 3);
            v15 = *((_QWORD *)P + 4);
            LOBYTE(v26) = 0;
            v22 = a4;
            v11 = PriExchangeDirs(v13, v14, v15, a1, &v26);
            LOBYTE(v16) = (_BYTE)v26;
            RtlWriteUCharToUser(v22, v16);
            *v10 = 1;
            goto LABEL_45;
          }
LABEL_44:
          v11 = -1073741811;
          goto LABEL_45;
      }
      v11 = v17;
      RtlWriteULong64ToUser(v26, v18);
      *v10 = 8;
      goto LABEL_45;
    }
    if ( !a1 || (unsigned int)v7 < 0x24 )
      goto LABEL_44;
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 40), 1, 0) )
    {
      v11 = -1073741694;
    }
    else
    {
      *(_OWORD *)(a1 + 24) = v12[1];
      v11 = WMCommListInsert(v12 + 1, a1 + 8, *((unsigned int *)v12 + 8), a1);
    }
  }
LABEL_45:
  if ( P )
    ExFreePoolWithTag(P, 0x574D6365u);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000b070  mov     [rsp+arg_0], rbx
0x14000b075  mov     [rsp+arg_10], rsi
0x14000b07a  push    rdi
0x14000b07b  push    r12
0x14000b07d  push    r13
0x14000b07f  push    r14
0x14000b081  push    r15
0x14000b083  sub     rsp, 80h
0x14000b08a  mov     rsi, r9
0x14000b08d  mov     edi, r8d
0x14000b090  mov     rbx, rdx
0x14000b093  mov     r14, rcx
0x14000b096  mov     [rsp+0A8h+P], 0
0x14000b09f  test    rdx, rdx
0x14000b0a2  jz      loc_14000B3ED
0x14000b0a8  cmp     edi, 10h
0x14000b0ab  jb      loc_14000B3ED
0x14000b0b1  mov     r12, [rsp+0A8h+arg_28]
0x14000b0b9  test    r12, r12
0x14000b0bc  jz      loc_14000B3ED
0x14000b0c2  mov     r13d, 1
0x14000b0c8  mov     r8d, r13d; Alignment
0x14000b0cb  mov     edx, edi; Length
0x14000b0cd  mov     rcx, rbx; Address
0x14000b0d0  call    cs:__imp_ProbeForRead
0x14000b0d7  nop     dword ptr [rax+rax+00h]
0x14000b0dc  test    rsi, rsi
0x14000b0df  jz      short loc_14000B0FA
0x14000b0e1  mov     edx, dword ptr [rsp+0A8h+Length]; Length
0x14000b0e8  mov     r8d, r13d; Alignment
0x14000b0eb  mov     rcx, rsi; Address
0x14000b0ee  call    cs:__imp_ProbeForWrite
0x14000b0f5  nop     dword ptr [rax+rax+00h]
0x14000b0fa  mov     r8d, edi
0x14000b0fd  mov     rdx, rbx
0x14000b100  lea     rcx, [rsp+0A8h+P]
0x14000b105  call    PriDuplicateBufferFromUser
0x14000b10a  mov     ebx, eax
0x14000b10c  mov     [rsp+0A8h+var_68], eax
0x14000b110  test    eax, eax
0x14000b112  js      loc_14000B3C6
0x14000b118  mov     r10, [rsp+0A8h+P]
0x14000b11d  cmp     [r10+8], edi
0x14000b121  ja      loc_14000B3BD
0x14000b127  cmp     dword ptr [r10], 42424242h
0x14000b12e  jnz     loc_14000B3BD
0x14000b134  mov     edx, 3
0x14000b139  cmp     [r10+4], dx
0x14000b13e  jnz     loc_14000B3BD
0x14000b144  cmp     [r10+6], r13w
0x14000b149  ja      loc_14000B3BD
0x14000b14f  mov     ecx, [r10+0Ch]
0x14000b153  sub     ecx, 2
0x14000b156  jz      loc_14000B381
0x14000b15c  sub     ecx, r13d
0x14000b15f  jz      loc_14000B34C
0x14000b165  sub     ecx, 2
0x14000b168  jz      loc_14000B2A4
0x14000b16e  sub     ecx, r13d
0x14000b171  jz      loc_14000B26A
0x14000b177  sub     ecx, r13d
0x14000b17a  jz      short loc_14000B1EA
0x14000b17c  cmp     ecx, r13d
0x14000b17f  jnz     loc_14000B3BD
0x14000b185  cmp     edi, 28h ; '('
0x14000b188  jb      loc_14000B3BD
0x14000b18e  cmp     dword ptr [rsp+0A8h+Length], r13d
0x14000b196  jb      loc_14000B3BD
0x14000b19c  mov     rcx, [r10+10h]
0x14000b1a0  mov     rdx, [r10+18h]
0x14000b1a4  mov     r8, [r10+20h]
0x14000b1a8  mov     byte ptr [rsp+0A8h+arg_8], 0
0x14000b1b0  mov     [rsp+0A8h+var_50], rsi
0x14000b1b5  lea     rax, [rsp+0A8h+arg_8]
0x14000b1bd  mov     [rsp+0A8h+var_88], rax
0x14000b1c2  mov     r9, r14
0x14000b1c5  call    PriExchangeDirs
0x14000b1ca  mov     ebx, eax
0x14000b1cc  mov     [rsp+0A8h+var_68], eax
0x14000b1d0  mov     rcx, [rsp+0A8h+var_50]
0x14000b1d5  mov     dl, byte ptr [rsp+0A8h+arg_8]
0x14000b1dc  call    RtlWriteUCharToUser
0x14000b1e1  mov     [r12], r13d
0x14000b1e5  jmp     loc_14000B3C6
0x14000b1ea  cmp     edi, 28h ; '('
0x14000b1ed  jb      loc_14000B3BD
0x14000b1f3  cmp     dword ptr [rsp+0A8h+Length], 8
0x14000b1fb  jb      loc_14000B3BD
0x14000b201  test    rsi, rsi
0x14000b204  jz      loc_14000B3BD
0x14000b20a  mov     rax, [r10+18h]
0x14000b20e  mov     [rsp+0A8h+var_40], rax
0x14000b213  mov     rax, [r10+20h]
0x14000b217  mov     [rsp+0A8h+var_48], rax
0x14000b21c  mov     [rsp+0A8h+var_58], 0
0x14000b225  mov     [rsp+0A8h+arg_8], rsi
0x14000b22d  lea     r9, [rsp+0A8h+var_58]
0x14000b232  lea     r8, [rsp+0A8h+var_48]
0x14000b237  lea     rdx, [rsp+0A8h+var_40]
0x14000b23c  mov     rcx, [r10+10h]
0x14000b240  call    PriSubsumeContext
0x14000b245  mov     [rsp+0A8h+var_68], eax
0x14000b249  mov     rdx, [rsp+0A8h+var_58]
0x14000b24e  mov     ebx, eax
0x14000b250  mov     rcx, [rsp+0A8h+arg_8]
0x14000b258  call    RtlWriteULong64ToUser
0x14000b25d  mov     dword ptr [r12], 8
0x14000b265  jmp     loc_14000B3C6
0x14000b26a  cmp     edi, 38h ; '8'
0x14000b26d  jb      loc_14000B3BD
0x14000b273  mov     eax, [r10+30h]
0x14000b277  add     rax, 38h ; '8'
0x14000b27b  cmp     rdi, rax
0x14000b27e  jb      loc_14000B3BD
0x14000b284  lea     r8d, [rdi-20h]
0x14000b288  lea     rdx, [r10+20h]
0x14000b28c  mov     r9d, [r10+18h]
0x14000b290  mov     rcx, [r10+10h]; Handle
0x14000b294  call    PriStubRename
0x14000b299  mov     ebx, eax
0x14000b29b  mov     [rsp+0A8h+var_68], eax
0x14000b29f  jmp     loc_14000B3C6
0x14000b2a4  cmp     edi, 30h ; '0'
0x14000b2a7  jb      loc_14000B3BD
0x14000b2ad  movzx   eax, word ptr [r10+28h]
0x14000b2b2  add     rax, 30h ; '0'
0x14000b2b6  cmp     rdi, rax
0x14000b2b9  jb      loc_14000B3BD
0x14000b2bf  test    rsi, rsi
0x14000b2c2  jz      loc_14000B3BD
0x14000b2c8  cmp     dword ptr [rsp+0A8h+Length], 8
0x14000b2d0  jnb     short loc_14000B2DC
0x14000b2d2  mov     ebx, 80000005h
0x14000b2d7  jmp     loc_14000B3C2
0x14000b2dc  mov     [rsp+0A8h+arg_8], rsi
0x14000b2e4  mov     [rsp+0A8h+var_50], 0
0x14000b2ed  xorps   xmm0, xmm0
0x14000b2f0  movups  [rsp+0A8h+var_38], xmm0
0x14000b2f5  lea     rax, [r10+2Ah]
0x14000b2f9  mov     qword ptr [rsp+0A8h+var_38+8], rax
0x14000b2fe  movzx   eax, word ptr [r10+28h]
0x14000b303  mov     word ptr [rsp+0A8h+var_38+2], ax
0x14000b308  mov     word ptr [rsp+0A8h+var_38], ax
0x14000b30d  lea     rax, [rsp+0A8h+var_50]
0x14000b312  mov     [rsp+0A8h+var_78], rax
0x14000b317  lea     rax, [rsp+0A8h+var_38]
0x14000b31c  mov     [rsp+0A8h+var_80], rax
0x14000b321  mov     eax, [r10+24h]
0x14000b325  mov     dword ptr [rsp+0A8h+var_88], eax
0x14000b329  mov     r9d, [r10+20h]
0x14000b32d  mov     r8d, [r10+1Ch]
0x14000b331  mov     edx, [r10+18h]
0x14000b335  mov     rcx, [r10+10h]
0x14000b339  call    PriStubCreateChild
0x14000b33e  mov     [rsp+0A8h+var_68], eax
0x14000b342  mov     rdx, [rsp+0A8h+var_50]
0x14000b347  jmp     loc_14000B24E
0x14000b34c  cmp     edi, 14h
0x14000b34f  jb      short loc_14000B35C
0x14000b351  mov     rax, [rsp+0A8h+P]
0x14000b356  mov     ecx, [rax+10h]
0x14000b359  mov     [r14], ecx
0x14000b35c  test    rsi, rsi
0x14000b35f  jz      short loc_14000B3C6
0x14000b361  cmp     dword ptr [rsp+0A8h+Length], 4
0x14000b369  jb      short loc_14000B3C6
0x14000b36b  mov     rcx, rsi
0x14000b36e  call    RtlWriteUShortToUser
0x14000b373  mov     edx, r13d
0x14000b376  lea     rcx, [rsi+2]
0x14000b37a  call    RtlWriteUShortToUser
0x14000b37f  jmp     short loc_14000B3C6
0x14000b381  test    r14, r14
0x14000b384  jz      short loc_14000B3BD
0x14000b386  cmp     edi, 24h ; '$'
0x14000b389  jb      short loc_14000B3BD
0x14000b38b  xor     eax, eax
0x14000b38d  lock cmpxchg [r14+28h], r13d
0x14000b393  jz      short loc_14000B39C
0x14000b395  mov     ebx, 0C0000082h
0x14000b39a  jmp     short loc_14000B3C2
0x14000b39c  lea     rcx, [r10+10h]
0x14000b3a0  movups  xmm0, xmmword ptr [rcx]
0x14000b3a3  movdqu  xmmword ptr [r14+18h], xmm0
0x14000b3a9  lea     rdx, [r14+8]
0x14000b3ad  mov     r9, r14
0x14000b3b0  mov     r8d, [r10+20h]
0x14000b3b4  call    WMCommListInsert
0x14000b3b9  mov     ebx, eax
0x14000b3bb  jmp     short loc_14000B3C2
0x14000b3bd  mov     ebx, 0C000000Dh
0x14000b3c2  mov     [rsp+0A8h+var_68], ebx
0x14000b3c6  jmp     short loc_14000B3CE
0x14000b3c8  mov     ebx, eax
0x14000b3ca  mov     [rsp+0A8h+var_68], eax
0x14000b3ce  mov     rcx, [rsp+0A8h+P]; P
0x14000b3d3  test    rcx, rcx
0x14000b3d6  jz      short loc_14000B3E9
0x14000b3d8  mov     edx, 574D6365h; Tag
0x14000b3dd  call    cs:__imp_ExFreePoolWithTag
0x14000b3e4  nop     dword ptr [rax+rax+00h]
0x14000b3e9  mov     eax, ebx
0x14000b3eb  jmp     short loc_14000B3F2
0x14000b3ed  mov     eax, 0C000000Dh
0x14000b3f2  lea     r11, [rsp+0A8h+var_28]
0x14000b3fa  mov     rbx, [r11+30h]
0x14000b3fe  mov     rsi, [r11+40h]
0x14000b402  mov     rsp, r11
0x14000b405  pop     r15
0x14000b407  pop     r14
0x14000b409  pop     r13
0x14000b40b  pop     r12
0x14000b40d  pop     rdi
0x14000b40e  retn
```

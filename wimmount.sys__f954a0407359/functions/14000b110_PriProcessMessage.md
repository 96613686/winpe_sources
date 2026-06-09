# PriProcessMessage

- ea: `0x14000b110`
- end: `0x14000b4b0`
- name: `PriProcessMessage`
- size: `928`
- prototype: `__int64 __fastcall(__int64, volatile void *, unsigned int, char *, SIZE_T Length, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000aa00`

## callees

- `0x14000223c`
- `0x140009008`
- `0x140009050`
- `0x140009098`
- `0x14000ae54`
- `0x14000b110`
- `0x14000b4b8`
- `0x14000b6b4`
- `0x14000b824`
- `0x14000ba5c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000b170`
- `ntoskrnl!ProbeForRead` at `0x14000b170`
- `ntoskrnl!ProbeForWrite` at `0x14000b18e`
- `ntoskrnl!ProbeForWrite` at `0x14000b18e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b47d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b47d`

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
0x14000b110  mov     [rsp+arg_0], rbx
0x14000b115  mov     [rsp+arg_10], rsi
0x14000b11a  push    rdi
0x14000b11b  push    r12
0x14000b11d  push    r13
0x14000b11f  push    r14
0x14000b121  push    r15
0x14000b123  sub     rsp, 80h
0x14000b12a  mov     rsi, r9
0x14000b12d  mov     edi, r8d
0x14000b130  mov     rbx, rdx
0x14000b133  mov     r14, rcx
0x14000b136  mov     [rsp+0A8h+P], 0
0x14000b13f  test    rdx, rdx
0x14000b142  jz      loc_14000B48D
0x14000b148  cmp     edi, 10h
0x14000b14b  jb      loc_14000B48D
0x14000b151  mov     r12, [rsp+0A8h+arg_28]
0x14000b159  test    r12, r12
0x14000b15c  jz      loc_14000B48D
0x14000b162  mov     r13d, 1
0x14000b168  mov     r8d, r13d; Alignment
0x14000b16b  mov     edx, edi; Length
0x14000b16d  mov     rcx, rbx; Address
0x14000b170  call    cs:__imp_ProbeForRead
0x14000b177  nop     dword ptr [rax+rax+00h]
0x14000b17c  test    rsi, rsi
0x14000b17f  jz      short loc_14000B19A
0x14000b181  mov     edx, dword ptr [rsp+0A8h+Length]; Length
0x14000b188  mov     r8d, r13d; Alignment
0x14000b18b  mov     rcx, rsi; Address
0x14000b18e  call    cs:__imp_ProbeForWrite
0x14000b195  nop     dword ptr [rax+rax+00h]
0x14000b19a  mov     r8d, edi
0x14000b19d  mov     rdx, rbx
0x14000b1a0  lea     rcx, [rsp+0A8h+P]
0x14000b1a5  call    PriDuplicateBufferFromUser
0x14000b1aa  mov     ebx, eax
0x14000b1ac  mov     [rsp+0A8h+var_68], eax
0x14000b1b0  test    eax, eax
0x14000b1b2  js      loc_14000B466
0x14000b1b8  mov     r10, [rsp+0A8h+P]
0x14000b1bd  cmp     [r10+8], edi
0x14000b1c1  ja      loc_14000B45D
0x14000b1c7  cmp     dword ptr [r10], 42424242h
0x14000b1ce  jnz     loc_14000B45D
0x14000b1d4  mov     edx, 3
0x14000b1d9  cmp     [r10+4], dx
0x14000b1de  jnz     loc_14000B45D
0x14000b1e4  cmp     [r10+6], r13w
0x14000b1e9  ja      loc_14000B45D
0x14000b1ef  mov     ecx, [r10+0Ch]
0x14000b1f3  sub     ecx, 2
0x14000b1f6  jz      loc_14000B421
0x14000b1fc  sub     ecx, r13d
0x14000b1ff  jz      loc_14000B3EC
0x14000b205  sub     ecx, 2
0x14000b208  jz      loc_14000B344
0x14000b20e  sub     ecx, r13d
0x14000b211  jz      loc_14000B30A
0x14000b217  sub     ecx, r13d
0x14000b21a  jz      short loc_14000B28A
0x14000b21c  cmp     ecx, r13d
0x14000b21f  jnz     loc_14000B45D
0x14000b225  cmp     edi, 28h ; '('
0x14000b228  jb      loc_14000B45D
0x14000b22e  cmp     dword ptr [rsp+0A8h+Length], r13d
0x14000b236  jb      loc_14000B45D
0x14000b23c  mov     rcx, [r10+10h]
0x14000b240  mov     rdx, [r10+18h]
0x14000b244  mov     r8, [r10+20h]
0x14000b248  mov     byte ptr [rsp+0A8h+arg_8], 0
0x14000b250  mov     [rsp+0A8h+var_50], rsi
0x14000b255  lea     rax, [rsp+0A8h+arg_8]
0x14000b25d  mov     [rsp+0A8h+var_88], rax
0x14000b262  mov     r9, r14
0x14000b265  call    PriExchangeDirs
0x14000b26a  mov     ebx, eax
0x14000b26c  mov     [rsp+0A8h+var_68], eax
0x14000b270  mov     rcx, [rsp+0A8h+var_50]
0x14000b275  mov     dl, byte ptr [rsp+0A8h+arg_8]
0x14000b27c  call    RtlWriteUCharToUser
0x14000b281  mov     [r12], r13d
0x14000b285  jmp     loc_14000B466
0x14000b28a  cmp     edi, 28h ; '('
0x14000b28d  jb      loc_14000B45D
0x14000b293  cmp     dword ptr [rsp+0A8h+Length], 8
0x14000b29b  jb      loc_14000B45D
0x14000b2a1  test    rsi, rsi
0x14000b2a4  jz      loc_14000B45D
0x14000b2aa  mov     rax, [r10+18h]
0x14000b2ae  mov     [rsp+0A8h+var_40], rax
0x14000b2b3  mov     rax, [r10+20h]
0x14000b2b7  mov     [rsp+0A8h+var_48], rax
0x14000b2bc  mov     [rsp+0A8h+var_58], 0
0x14000b2c5  mov     [rsp+0A8h+arg_8], rsi
0x14000b2cd  lea     r9, [rsp+0A8h+var_58]
0x14000b2d2  lea     r8, [rsp+0A8h+var_48]
0x14000b2d7  lea     rdx, [rsp+0A8h+var_40]
0x14000b2dc  mov     rcx, [r10+10h]
0x14000b2e0  call    PriSubsumeContext
0x14000b2e5  mov     [rsp+0A8h+var_68], eax
0x14000b2e9  mov     rdx, [rsp+0A8h+var_58]
0x14000b2ee  mov     ebx, eax
0x14000b2f0  mov     rcx, [rsp+0A8h+arg_8]
0x14000b2f8  call    RtlWriteULong64ToUser
0x14000b2fd  mov     dword ptr [r12], 8
0x14000b305  jmp     loc_14000B466
0x14000b30a  cmp     edi, 38h ; '8'
0x14000b30d  jb      loc_14000B45D
0x14000b313  mov     eax, [r10+30h]
0x14000b317  add     rax, 38h ; '8'
0x14000b31b  cmp     rdi, rax
0x14000b31e  jb      loc_14000B45D
0x14000b324  lea     r8d, [rdi-20h]
0x14000b328  lea     rdx, [r10+20h]
0x14000b32c  mov     r9d, [r10+18h]
0x14000b330  mov     rcx, [r10+10h]; Handle
0x14000b334  call    PriStubRename
0x14000b339  mov     ebx, eax
0x14000b33b  mov     [rsp+0A8h+var_68], eax
0x14000b33f  jmp     loc_14000B466
0x14000b344  cmp     edi, 30h ; '0'
0x14000b347  jb      loc_14000B45D
0x14000b34d  movzx   eax, word ptr [r10+28h]
0x14000b352  add     rax, 30h ; '0'
0x14000b356  cmp     rdi, rax
0x14000b359  jb      loc_14000B45D
0x14000b35f  test    rsi, rsi
0x14000b362  jz      loc_14000B45D
0x14000b368  cmp     dword ptr [rsp+0A8h+Length], 8
0x14000b370  jnb     short loc_14000B37C
0x14000b372  mov     ebx, 80000005h
0x14000b377  jmp     loc_14000B462
0x14000b37c  mov     [rsp+0A8h+arg_8], rsi
0x14000b384  mov     [rsp+0A8h+var_50], 0
0x14000b38d  xorps   xmm0, xmm0
0x14000b390  movups  [rsp+0A8h+var_38], xmm0
0x14000b395  lea     rax, [r10+2Ah]
0x14000b399  mov     qword ptr [rsp+0A8h+var_38+8], rax
0x14000b39e  movzx   eax, word ptr [r10+28h]
0x14000b3a3  mov     word ptr [rsp+0A8h+var_38+2], ax
0x14000b3a8  mov     word ptr [rsp+0A8h+var_38], ax
0x14000b3ad  lea     rax, [rsp+0A8h+var_50]
0x14000b3b2  mov     [rsp+0A8h+var_78], rax
0x14000b3b7  lea     rax, [rsp+0A8h+var_38]
0x14000b3bc  mov     [rsp+0A8h+var_80], rax
0x14000b3c1  mov     eax, [r10+24h]
0x14000b3c5  mov     dword ptr [rsp+0A8h+var_88], eax
0x14000b3c9  mov     r9d, [r10+20h]
0x14000b3cd  mov     r8d, [r10+1Ch]
0x14000b3d1  mov     edx, [r10+18h]
0x14000b3d5  mov     rcx, [r10+10h]
0x14000b3d9  call    PriStubCreateChild
0x14000b3de  mov     [rsp+0A8h+var_68], eax
0x14000b3e2  mov     rdx, [rsp+0A8h+var_50]
0x14000b3e7  jmp     loc_14000B2EE
0x14000b3ec  cmp     edi, 14h
0x14000b3ef  jb      short loc_14000B3FC
0x14000b3f1  mov     rax, [rsp+0A8h+P]
0x14000b3f6  mov     ecx, [rax+10h]
0x14000b3f9  mov     [r14], ecx
0x14000b3fc  test    rsi, rsi
0x14000b3ff  jz      short loc_14000B466
0x14000b401  cmp     dword ptr [rsp+0A8h+Length], 4
0x14000b409  jb      short loc_14000B466
0x14000b40b  mov     rcx, rsi
0x14000b40e  call    RtlWriteUShortToUser
0x14000b413  mov     edx, r13d
0x14000b416  lea     rcx, [rsi+2]
0x14000b41a  call    RtlWriteUShortToUser
0x14000b41f  jmp     short loc_14000B466
0x14000b421  test    r14, r14
0x14000b424  jz      short loc_14000B45D
0x14000b426  cmp     edi, 24h ; '$'
0x14000b429  jb      short loc_14000B45D
0x14000b42b  xor     eax, eax
0x14000b42d  lock cmpxchg [r14+28h], r13d
0x14000b433  jz      short loc_14000B43C
0x14000b435  mov     ebx, 0C0000082h
0x14000b43a  jmp     short loc_14000B462
0x14000b43c  lea     rcx, [r10+10h]
0x14000b440  movups  xmm0, xmmword ptr [rcx]
0x14000b443  movdqu  xmmword ptr [r14+18h], xmm0
0x14000b449  lea     rdx, [r14+8]
0x14000b44d  mov     r9, r14
0x14000b450  mov     r8d, [r10+20h]
0x14000b454  call    WMCommListInsert
0x14000b459  mov     ebx, eax
0x14000b45b  jmp     short loc_14000B462
0x14000b45d  mov     ebx, 0C000000Dh
0x14000b462  mov     [rsp+0A8h+var_68], ebx
0x14000b466  jmp     short loc_14000B46E
0x14000b468  mov     ebx, eax
0x14000b46a  mov     [rsp+0A8h+var_68], eax
0x14000b46e  mov     rcx, [rsp+0A8h+P]; P
0x14000b473  test    rcx, rcx
0x14000b476  jz      short loc_14000B489
0x14000b478  mov     edx, 574D6365h; Tag
0x14000b47d  call    cs:__imp_ExFreePoolWithTag
0x14000b484  nop     dword ptr [rax+rax+00h]
0x14000b489  mov     eax, ebx
0x14000b48b  jmp     short loc_14000B492
0x14000b48d  mov     eax, 0C000000Dh
0x14000b492  lea     r11, [rsp+0A8h+var_28]
0x14000b49a  mov     rbx, [r11+30h]
0x14000b49e  mov     rsi, [r11+40h]
0x14000b4a2  mov     rsp, r11
0x14000b4a5  pop     r15
0x14000b4a7  pop     r14
0x14000b4a9  pop     r13
0x14000b4ab  pop     r12
0x14000b4ad  pop     rdi
0x14000b4ae  retn
```

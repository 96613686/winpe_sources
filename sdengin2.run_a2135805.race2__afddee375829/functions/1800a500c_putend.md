# putend

- ea: `0x1800a500c`
- end: `0x1800a5542`
- name: `putend`
- size: `1334`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800a3d14`
- `0x1800a8284`

## callees

- `0x1800a1f1c`
- `0x1800a500c`
- `0x1800a8544`
- `0x1800cf552`

## import_xrefs

- `msvcrt!free` at `0x1800a517c`
- `msvcrt!free` at `0x1800a529c`
- `msvcrt!free` at `0x1800a545b`
- `msvcrt!free` at `0x1800a517c`
- `msvcrt!free` at `0x1800a529c`
- `msvcrt!free` at `0x1800a545b`
- `msvcrt!malloc` at `0x1800a5105`
- `msvcrt!malloc` at `0x1800a51f1`
- `msvcrt!malloc` at `0x1800a52ee`
- `msvcrt!malloc` at `0x1800a5474`
- `msvcrt!malloc` at `0x1800a5105`
- `msvcrt!malloc` at `0x1800a51f1`
- `msvcrt!malloc` at `0x1800a52ee`
- `msvcrt!malloc` at `0x1800a5474`
- `KERNEL32!WriteFile` at `0x1800a527a`
- `KERNEL32!WriteFile` at `0x1800a543a`
- `KERNEL32!WriteFile` at `0x1800a527a`
- `KERNEL32!WriteFile` at `0x1800a543a`

## pseudocode

```c
__int64 __fastcall putend(__int64 a1, __int64 a2, __int64 a3, size_t a4, void *Src, HANDLE *a6, __int64 a7)
{
  int v8; // ebp
  int v13; // r15d
  char *v15; // rax
  _DWORD *v16; // rbx
  __int64 v17; // rcx
  HANDLE v18; // rcx
  char *v19; // rax
  __int64 v20; // rcx
  signed int v21; // ebp
  _DWORD *v22; // rax
  BOOL v23; // eax
  char *v24; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-68h] BYREF
  int v26; // [rsp+34h] [rbp-64h]
  __int64 v27; // [rsp+38h] [rbp-60h]
  __int64 v28; // [rsp+40h] [rbp-58h]
  int v29; // [rsp+D0h] [rbp+38h]
  int v30; // [rsp+D0h] [rbp+38h]

  v8 = 0;
  NumberOfBytesWritten = 0;
  v13 = 0;
  if ( !*(_DWORD *)(a7 + 624) || a1 <= 65534 && a2 <= 4294967294LL && a3 <= 4294967294LL )
    goto LABEL_24;
  v13 = 1;
  if ( *(_QWORD *)(a7 + 216) != -1 )
  {
    v28 = DZSetFilePointer(*a6, 0, 1);
    if ( *(__int16 *)(a7 + 3740) >= 0 )
    {
      v26 = 0;
      v27 = a1;
      v30 = 0;
    }
    else
    {
      v8 = *(_DWORD *)(a7 + 3744);
      v30 = *(_DWORD *)(a7 + 3748);
      v26 = v8 + 1;
      v27 = *(unsigned int *)(a7 + 3760);
    }
    v19 = (char *)malloc(0x4Du);
    v16 = v19;
    if ( !v19 )
      return 4;
    v20 = v27;
    *(_DWORD *)v19 = 101075792;
    *(_QWORD *)(v19 + 4) = 44;
    *((_DWORD *)v19 + 3) = 2949165;
    *((_DWORD *)v19 + 4) = v8;
    *((_DWORD *)v19 + 5) = v30;
    *((_QWORD *)v19 + 3) = v20;
    *((_QWORD *)v19 + 4) = a1;
    *((_QWORD *)v19 + 5) = a2;
    *((_QWORD *)v19 + 6) = a3;
    *((_DWORD *)v19 + 15) = v30;
    *((_QWORD *)v19 + 8) = v28;
    *((_DWORD *)v19 + 18) = v26;
    v18 = *a6;
LABEL_21:
    v16[14] = 117853008;
    if ( !WriteFile(v18, v16, 0x4Cu, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 76 )
      goto LABEL_15;
    free(v16);
LABEL_24:
    v21 = a4 + 22;
    if ( *(_QWORD *)(a7 + 216) == -1 )
    {
      if ( (unsigned int)PromptForNewDisk(0, a6, a4 + 22, a7) )
        return *(_DWORD *)(a7 + 208) != 0 ? 9 : 19;
      v22 = malloc(v21 + 1LL);
      v16 = v22;
      if ( v22 )
      {
        *v22 = 101010256;
        if ( *(__int16 *)(a7 + 3740) >= 0 )
        {
          v22[1] = 0;
          if ( v13 )
          {
            if ( a1 > 65534 )
            {
LABEL_37:
              *((_WORD *)v22 + 4) = -1;
              goto LABEL_43;
            }
            *((_WORD *)v22 + 4) = a1;
LABEL_43:
            if ( a1 <= 65534 )
              *((_WORD *)v22 + 5) = a1;
            else
              *((_WORD *)v22 + 5) = -1;
            if ( a2 <= 4294967294LL )
              v22[3] = a2;
            else
              v22[3] = -1;
            if ( a3 > 4294967294LL )
            {
              v22[4] = -1;
LABEL_54:
              *((_WORD *)v22 + 10) = a4;
              if ( a4 )
                memcpy_0((char *)v22 + 22, Src, a4);
              v23 = WriteFile(*a6, v16, v21, &NumberOfBytesWritten, 0);
              goto LABEL_57;
            }
LABEL_53:
            v22[4] = a3;
            goto LABEL_54;
          }
          *((_WORD *)v22 + 4) = a1;
        }
        else
        {
          if ( v13 )
          {
            if ( *(_DWORD *)(a7 + 3744) <= 0xFFFEu )
              *((_WORD *)v22 + 2) = *(_WORD *)(a7 + 3744);
            else
              *((_WORD *)v22 + 2) = -1;
            if ( *(_DWORD *)(a7 + 3748) <= 0xFFFEu )
              *((_WORD *)v22 + 3) = *(_WORD *)(a7 + 3748);
            else
              *((_WORD *)v22 + 3) = -1;
            if ( *(_DWORD *)(a7 + 3760) > 0xFFFEu )
              goto LABEL_37;
            *((_WORD *)v22 + 4) = *(_WORD *)(a7 + 3760);
            goto LABEL_43;
          }
          *((_WORD *)v22 + 2) = *(_WORD *)(a7 + 3744);
          *((_WORD *)v22 + 3) = *(_WORD *)(a7 + 3748);
          *((_WORD *)v22 + 4) = *(_WORD *)(a7 + 3760);
        }
        *((_WORD *)v22 + 5) = a1;
        v22[3] = a2;
        goto LABEL_53;
      }
      return 4;
    }
    v24 = (char *)malloc(v21 + 1LL);
    v16 = v24;
    if ( !v24 )
      return 4;
    *(_DWORD *)v24 = 101010256;
    if ( *(__int16 *)(a7 + 3740) >= 0 )
    {
      *((_DWORD *)v24 + 1) = 0;
      if ( v13 )
        goto LABEL_66;
      *((_WORD *)v24 + 4) = a1;
    }
    else
    {
      if ( v13 )
      {
        *((_DWORD *)v24 + 1) = -1;
LABEL_66:
        *((_WORD *)v24 + 4) = -1;
        *(_QWORD *)(v24 + 10) = -1;
        *((_WORD *)v24 + 9) = -1;
LABEL_69:
        *((_WORD *)v24 + 10) = a4;
        if ( a4 )
          memcpy_0(v24 + 22, Src, a4);
        v23 = WriteFile(*(HANDLE *)(a7 + 216), v16, v21, &NumberOfBytesWritten, 0);
LABEL_57:
        if ( v23 && NumberOfBytesWritten == v21 )
        {
          free(v16);
          return 0;
        }
LABEL_15:
        free(v16);
        return 10;
      }
      *((_WORD *)v24 + 2) = *(_WORD *)(a7 + 3744);
      *((_WORD *)v24 + 3) = *(_WORD *)(a7 + 3748);
      *((_WORD *)v24 + 4) = *(_WORD *)(a7 + 3760);
    }
    *((_WORD *)v24 + 5) = a1;
    *((_DWORD *)v24 + 3) = a2;
    *((_DWORD *)v24 + 4) = a3;
    goto LABEL_69;
  }
  if ( !(unsigned int)PromptForNewDisk(0, a6, 76, a7) )
  {
    v28 = DZSetFilePointer(*a6, 0, 1);
    if ( *(__int16 *)(a7 + 3740) >= 0 )
    {
      v26 = 0;
      v27 = a1;
      v29 = 0;
    }
    else
    {
      v8 = *(_DWORD *)(a7 + 3744);
      v29 = *(_DWORD *)(a7 + 3748);
      v26 = v8 + 1;
      v27 = *(unsigned int *)(a7 + 3760);
    }
    v15 = (char *)malloc(0x4Du);
    v16 = v15;
    if ( !v15 )
      return 4;
    v17 = v27;
    *(_DWORD *)v15 = 101075792;
    *(_QWORD *)(v15 + 4) = 44;
    *((_DWORD *)v15 + 3) = 2949165;
    *((_DWORD *)v15 + 4) = v8;
    *((_DWORD *)v15 + 5) = v29;
    *((_QWORD *)v15 + 3) = v17;
    *((_QWORD *)v15 + 4) = a1;
    *((_QWORD *)v15 + 5) = a2;
    *((_QWORD *)v15 + 6) = a3;
    v18 = *a6;
    *((_DWORD *)v15 + 15) = v29;
    *((_QWORD *)v15 + 8) = v28;
    *((_DWORD *)v15 + 18) = v26;
    goto LABEL_21;
  }
  if ( *(_DWORD *)(a7 + 208) )
    return 9;
  else
    return 19;
}

```

## disassembly

```asm
0x1800a500c  push    rbx
0x1800a500e  push    rbp
0x1800a500f  push    rsi
0x1800a5010  push    rdi
0x1800a5011  push    r12
0x1800a5013  push    r13
0x1800a5015  push    r14
0x1800a5017  push    r15
0x1800a5019  sub     rsp, 58h
0x1800a501d  mov     rdi, [rsp+98h+arg_30]
0x1800a5025  xor     ebp, ebp
0x1800a5027  mov     r14, r9
0x1800a502a  mov     [rsp+98h+NumberOfBytesWritten], ebp
0x1800a502e  mov     r12, r8
0x1800a5031  mov     r13, rdx
0x1800a5034  mov     rsi, rcx
0x1800a5037  mov     r15d, ebp
0x1800a503a  mov     eax, 0FFFFFFFEh
0x1800a503f  cmp     [rdi+270h], ebp
0x1800a5045  jz      loc_1800A52A8
0x1800a504b  cmp     rcx, 0FFFEh
0x1800a5052  jg      short loc_1800A5062
0x1800a5054  cmp     rdx, rax
0x1800a5057  jg      short loc_1800A5062
0x1800a5059  cmp     r8, rax
0x1800a505c  jle     loc_1800A52A8
0x1800a5062  cmp     qword ptr [rdi+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a506a  mov     r15d, 1
0x1800a5070  jnz     loc_1800A5192
0x1800a5076  mov     rbx, [rsp+98h+arg_28]
0x1800a507e  lea     r8d, [r15+4Bh]
0x1800a5082  mov     rdx, rbx
0x1800a5085  mov     r9, rdi
0x1800a5088  xor     ecx, ecx
0x1800a508a  call    PromptForNewDisk
0x1800a508f  test    eax, eax
0x1800a5091  jz      short loc_1800A50AE
0x1800a5093  cmp     [rdi+0D0h], ebp
0x1800a5099  jnz     short loc_1800A50A4
0x1800a509b  lea     eax, [r15+12h]
0x1800a509f  jmp     loc_1800A5530
0x1800a50a4  mov     eax, 9
0x1800a50a9  jmp     loc_1800A5530
0x1800a50ae  mov     rcx, [rbx]
0x1800a50b1  xor     edx, edx
0x1800a50b3  mov     r8d, r15d
0x1800a50b6  call    DZSetFilePointer
0x1800a50bb  mov     [rsp+98h+var_58], rax
0x1800a50c0  cmp     [rdi+0E9Ch], bp
0x1800a50c7  jge     short loc_1800A50F0
0x1800a50c9  mov     ebp, [rdi+0EA0h]
0x1800a50cf  mov     ecx, [rdi+0EA4h]
0x1800a50d5  mov     dword ptr [rsp+98h+arg_30], ecx
0x1800a50dc  lea     eax, [rbp+1]
0x1800a50df  mov     [rsp+98h+var_64], eax
0x1800a50e3  mov     eax, [rdi+0EB0h]
0x1800a50e9  mov     [rsp+98h+var_60], rax
0x1800a50ee  jmp     short loc_1800A5100
0x1800a50f0  mov     [rsp+98h+var_64], ebp
0x1800a50f4  mov     [rsp+98h+var_60], rsi
0x1800a50f9  mov     dword ptr [rsp+98h+arg_30], ebp
0x1800a5100  mov     ecx, 4Dh ; 'M'; Size
0x1800a5105  call    cs:__imp_malloc
0x1800a510c  nop     dword ptr [rax+rax+00h]
0x1800a5111  xor     edx, edx
0x1800a5113  mov     rbx, rax
0x1800a5116  test    rax, rax
0x1800a5119  jz      loc_1800A552B
0x1800a511f  mov     rcx, [rsp+98h+var_60]
0x1800a5124  mov     dword ptr [rax], 6064B50h
0x1800a512a  mov     qword ptr [rax+4], 2Ch ; ','
0x1800a5132  mov     dword ptr [rax+0Ch], 2D002Dh
0x1800a5139  mov     [rax+10h], ebp
0x1800a513c  mov     eax, dword ptr [rsp+98h+arg_30]
0x1800a5143  mov     [rbx+14h], eax
0x1800a5146  mov     [rbx+18h], rcx
0x1800a514a  mov     rcx, [rsp+98h+arg_28]
0x1800a5152  mov     [rbx+20h], rsi
0x1800a5156  mov     [rbx+28h], r13
0x1800a515a  mov     [rbx+30h], r12
0x1800a515e  mov     rcx, [rcx]
0x1800a5161  mov     [rbx+3Ch], eax
0x1800a5164  mov     rax, [rsp+98h+var_58]
0x1800a5169  mov     [rbx+40h], rax
0x1800a516d  mov     eax, [rsp+98h+var_64]
0x1800a5171  mov     [rbx+48h], eax
0x1800a5174  jmp     loc_1800A5260
0x1800a5179  mov     rcx, rbx; Block
0x1800a517c  call    cs:__imp_free
0x1800a5183  nop     dword ptr [rax+rax+00h]
0x1800a5188  mov     eax, 0Ah
0x1800a518d  jmp     loc_1800A5530
0x1800a5192  mov     rcx, [rsp+98h+arg_28]
0x1800a519a  xor     edx, edx
0x1800a519c  mov     r8d, r15d
0x1800a519f  mov     rcx, [rcx]
0x1800a51a2  call    DZSetFilePointer
0x1800a51a7  mov     [rsp+98h+var_58], rax
0x1800a51ac  cmp     [rdi+0E9Ch], bp
0x1800a51b3  jge     short loc_1800A51DC
0x1800a51b5  mov     ebp, [rdi+0EA0h]
0x1800a51bb  mov     ecx, [rdi+0EA4h]
0x1800a51c1  mov     dword ptr [rsp+98h+arg_30], ecx
0x1800a51c8  lea     eax, [rbp+1]
0x1800a51cb  mov     [rsp+98h+var_64], eax
0x1800a51cf  mov     eax, [rdi+0EB0h]
0x1800a51d5  mov     [rsp+98h+var_60], rax
0x1800a51da  jmp     short loc_1800A51EC
0x1800a51dc  mov     [rsp+98h+var_64], ebp
0x1800a51e0  mov     [rsp+98h+var_60], rsi
0x1800a51e5  mov     dword ptr [rsp+98h+arg_30], ebp
0x1800a51ec  mov     ecx, 4Dh ; 'M'; Size
0x1800a51f1  call    cs:__imp_malloc
0x1800a51f8  nop     dword ptr [rax+rax+00h]
0x1800a51fd  xor     edx, edx
0x1800a51ff  mov     rbx, rax
0x1800a5202  test    rax, rax
0x1800a5205  jz      loc_1800A552B
0x1800a520b  mov     rcx, [rsp+98h+var_60]
0x1800a5210  mov     dword ptr [rax], 6064B50h
0x1800a5216  mov     qword ptr [rax+4], 2Ch ; ','
0x1800a521e  mov     dword ptr [rax+0Ch], 2D002Dh
0x1800a5225  mov     [rax+10h], ebp
0x1800a5228  mov     eax, dword ptr [rsp+98h+arg_30]
0x1800a522f  mov     [rbx+14h], eax
0x1800a5232  mov     [rbx+18h], rcx
0x1800a5236  mov     [rbx+20h], rsi
0x1800a523a  mov     [rbx+28h], r13
0x1800a523e  mov     [rbx+30h], r12
0x1800a5242  mov     [rbx+3Ch], eax
0x1800a5245  mov     rax, [rsp+98h+var_58]
0x1800a524a  mov     [rbx+40h], rax
0x1800a524e  mov     eax, [rsp+98h+var_64]
0x1800a5252  mov     [rbx+48h], eax
0x1800a5255  mov     rax, [rsp+98h+arg_28]
0x1800a525d  mov     rcx, [rax]; hFile
0x1800a5260  mov     [rsp+98h+lpOverlapped], rdx; lpOverlapped
0x1800a5265  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a526a  mov     rdx, rbx; lpBuffer
0x1800a526d  mov     dword ptr [rbx+38h], 7064B50h
0x1800a5274  mov     r8d, 4Ch ; 'L'; nNumberOfBytesToWrite
0x1800a527a  call    cs:__imp_WriteFile
0x1800a5281  nop     dword ptr [rax+rax+00h]
0x1800a5286  test    eax, eax
0x1800a5288  jz      loc_1800A5179
0x1800a528e  cmp     [rsp+98h+NumberOfBytesWritten], 4Ch ; 'L'
0x1800a5293  jnz     loc_1800A5179
0x1800a5299  mov     rcx, rbx; Block
0x1800a529c  call    cs:__imp_free
0x1800a52a3  nop     dword ptr [rax+rax+00h]
0x1800a52a8  cmp     qword ptr [rdi+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a52b0  lea     rbp, [r14+16h]
0x1800a52b4  jnz     loc_1800A546E
0x1800a52ba  mov     rdx, [rsp+98h+arg_28]
0x1800a52c2  mov     r9, rdi
0x1800a52c5  mov     r8, rbp
0x1800a52c8  xor     ecx, ecx
0x1800a52ca  call    PromptForNewDisk
0x1800a52cf  test    eax, eax
0x1800a52d1  jz      short loc_1800A52E8
0x1800a52d3  mov     eax, [rdi+0D0h]
0x1800a52d9  neg     eax
0x1800a52db  sbb     eax, eax
0x1800a52dd  and     eax, 0FFFFFFF6h
0x1800a52e0  add     eax, 13h
0x1800a52e3  jmp     loc_1800A5530
0x1800a52e8  movsxd  rcx, ebp
0x1800a52eb  inc     rcx; Size
0x1800a52ee  call    cs:__imp_malloc
0x1800a52f5  nop     dword ptr [rax+rax+00h]
0x1800a52fa  xor     ecx, ecx
0x1800a52fc  mov     rbx, rax
0x1800a52ff  test    rax, rax
0x1800a5302  jz      loc_1800A552B
0x1800a5308  mov     dword ptr [rax], 6054B50h
0x1800a530e  cmp     [rdi+0E9Ch], cx
0x1800a5315  jge     loc_1800A53A1
0x1800a531b  test    r15d, r15d
0x1800a531e  jz      short loc_1800A537E
0x1800a5320  mov     edx, 0FFFEh
0x1800a5325  cmp     [rdi+0EA0h], edx
0x1800a532b  jbe     short loc_1800A5337
0x1800a532d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a5331  mov     [rbx+4], ax
0x1800a5335  jmp     short loc_1800A5346
0x1800a5337  movzx   eax, word ptr [rdi+0EA0h]
0x1800a533e  mov     [rbx+4], ax
0x1800a5342  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a5346  cmp     [rdi+0EA4h], edx
0x1800a534c  jbe     short loc_1800A5354
0x1800a534e  mov     [rbx+6], ax
0x1800a5352  jmp     short loc_1800A5363
0x1800a5354  movzx   eax, word ptr [rdi+0EA4h]
0x1800a535b  mov     [rbx+6], ax
0x1800a535f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a5363  cmp     [rdi+0EB0h], edx
0x1800a5369  jbe     short loc_1800A5371
0x1800a536b  mov     [rbx+8], ax
0x1800a536f  jmp     short loc_1800A53C3
0x1800a5371  movzx   eax, word ptr [rdi+0EB0h]
0x1800a5378  mov     [rbx+8], ax
0x1800a537c  jmp     short loc_1800A53BF
0x1800a537e  movzx   eax, word ptr [rdi+0EA0h]
0x1800a5385  mov     [rbx+4], ax
0x1800a5389  movzx   eax, word ptr [rdi+0EA4h]
0x1800a5390  mov     [rbx+6], ax
0x1800a5394  movzx   eax, word ptr [rdi+0EB0h]
0x1800a539b  mov     [rbx+8], ax
0x1800a539f  jmp     short loc_1800A53F3
0x1800a53a1  xor     eax, eax
0x1800a53a3  mov     [rbx+4], eax
0x1800a53a6  test    r15d, r15d
0x1800a53a9  jz      short loc_1800A53EF
0x1800a53ab  mov     edx, 0FFFEh
0x1800a53b0  cmp     rsi, rdx
0x1800a53b3  jle     short loc_1800A53BB
0x1800a53b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a53b9  jmp     short loc_1800A536B
0x1800a53bb  mov     [rbx+8], si
0x1800a53bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a53c3  cmp     rsi, rdx
0x1800a53c6  jle     short loc_1800A53CE
0x1800a53c8  mov     [rbx+0Ah], ax
0x1800a53cc  jmp     short loc_1800A53D2
0x1800a53ce  mov     [rbx+0Ah], si
0x1800a53d2  mov     edx, 0FFFFFFFEh
0x1800a53d7  cmp     r13, rdx
0x1800a53da  jle     short loc_1800A53E1
0x1800a53dc  mov     [rbx+0Ch], eax
0x1800a53df  jmp     short loc_1800A53E5
0x1800a53e1  mov     [rbx+0Ch], r13d
0x1800a53e5  cmp     r12, rdx
0x1800a53e8  jle     short loc_1800A53FB
0x1800a53ea  mov     [rbx+10h], eax
0x1800a53ed  jmp     short loc_1800A53FF
0x1800a53ef  mov     [rbx+8], si
0x1800a53f3  mov     [rbx+0Ah], si
0x1800a53f7  mov     [rbx+0Ch], r13d
0x1800a53fb  mov     [rbx+10h], r12d
0x1800a53ff  mov     [rbx+14h], r14w
0x1800a5404  test    r14, r14
0x1800a5407  jz      short loc_1800A541F
0x1800a5409  mov     rdx, [rsp+98h+Src]; Src
0x1800a5411  lea     rcx, [rbx+16h]; void *
0x1800a5415  mov     r8, r14; Size
0x1800a5418  call    memcpy_0
0x1800a541d  xor     ecx, ecx
0x1800a541f  mov     rax, [rsp+98h+arg_28]
0x1800a5427  mov     [rsp+98h+lpOverlapped], rcx; lpOverlapped
0x1800a542c  mov     rcx, [rax]; hFile
0x1800a542f  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a5434  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800a5437  mov     rdx, rbx; lpBuffer
0x1800a543a  call    cs:__imp_WriteFile
0x1800a5441  nop     dword ptr [rax+rax+00h]
0x1800a5446  test    eax, eax
0x1800a5448  jz      loc_1800A5179
0x1800a544e  cmp     [rsp+98h+NumberOfBytesWritten], ebp
0x1800a5452  jnz     loc_1800A5179
0x1800a5458  mov     rcx, rbx; Block
0x1800a545b  call    cs:__imp_free
0x1800a5462  nop     dword ptr [rax+rax+00h]
0x1800a5467  xor     eax, eax
0x1800a5469  jmp     loc_1800A5530
0x1800a546e  movsxd  rcx, ebp
0x1800a5471  inc     rcx; Size
0x1800a5474  call    cs:__imp_malloc
0x1800a547b  nop     dword ptr [rax+rax+00h]
0x1800a5480  xor     ecx, ecx
0x1800a5482  mov     rbx, rax
0x1800a5485  test    rax, rax
0x1800a5488  jz      loc_1800A552B
0x1800a548e  mov     dword ptr [rax], 6054B50h
0x1800a5494  cmp     [rdi+0E9Ch], cx
0x1800a549b  jge     short loc_1800A54CE
0x1800a549d  test    r15d, r15d
0x1800a54a0  jz      short loc_1800A54AB
0x1800a54a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a54a6  mov     [rbx+4], eax
0x1800a54a9  jmp     short loc_1800A54DC
0x1800a54ab  movzx   eax, word ptr [rdi+0EA0h]
0x1800a54b2  mov     [rbx+4], ax
0x1800a54b6  movzx   eax, word ptr [rdi+0EA4h]
0x1800a54bd  mov     [rbx+6], ax
0x1800a54c1  movzx   eax, word ptr [rdi+0EB0h]
0x1800a54c8  mov     [rbx+8], ax
0x1800a54cc  jmp     short loc_1800A54EE
0x1800a54ce  xor     eax, eax
0x1800a54d0  mov     [rbx+4], eax
0x1800a54d3  test    r15d, r15d
0x1800a54d6  jz      short loc_1800A54EA
0x1800a54d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a54dc  mov     [rbx+8], ax
0x1800a54e0  mov     [rbx+0Ah], rax
0x1800a54e4  mov     [rbx+12h], ax
0x1800a54e8  jmp     short loc_1800A54FA
0x1800a54ea  mov     [rbx+8], si
0x1800a54ee  mov     [rbx+0Ah], si
0x1800a54f2  mov     [rbx+0Ch], r13d
0x1800a54f6  mov     [rbx+10h], r12d
  ... truncated ...
```

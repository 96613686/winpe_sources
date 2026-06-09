# MTX_RUNLENGTHCOMP_SaveBytes

- ea: `0x180009a50`
- end: `0x180009c72`
- name: `MTX_RUNLENGTHCOMP_SaveBytes`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800088a0`

## callees

- `0x180009a50`
- `0x180009c80`
- `0x18000ddd4`
- `0x18001c9ec`
- `0x18002a566`

## pseudocode

```c
char __fastcall MTX_RUNLENGTHCOMP_SaveBytes(__int64 a1, unsigned __int8 a2, __int64 *a3, unsigned int *a4, _DWORD *a5)
{
  unsigned int v5; // r12d
  __int64 v7; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // ecx
  int v15; // r13d
  __int64 v16; // r8
  __int64 v17; // r8

  v5 = *a4;
  v7 = *a3;
  if ( (*a4 & 0x80000000) == 0 )
  {
    v13 = (unsigned int)*a5;
    if ( (int)v13 >= 0 )
    {
      LOBYTE(v12) = *(_BYTE *)(a1 + 2);
      if ( !(_BYTE)v12 )
      {
        if ( a2 == *(_BYTE *)a1 )
        {
          *(_BYTE *)(a1 + 2) = 1;
          *a3 = v7;
          goto LABEL_37;
        }
        if ( (unsigned int)v13 > v5 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        else if ( (unsigned int)v13 < v5 )
        {
LABEL_10:
          *(_BYTE *)(v13 + v7) = a2;
          LODWORD(v13) = v13 + 1;
          goto LABEL_11;
        }
        v16 = v5 + (v5 >> 1);
        if ( (unsigned int)v16 >= v5 )
        {
          if ( (unsigned int)v16 <= 0x7FFFFFFF )
          {
            *a4 = v16;
            v12 = MTX_mem_realloc(*(_QWORD *)(a1 + 8), v7, v16);
            v7 = v12;
            if ( !v12 )
              goto LABEL_4;
            goto LABEL_10;
          }
LABEL_24:
          *a4 = -1;
        }
LABEL_25:
        v11 = *(_QWORD *)(a1 + 8);
        goto LABEL_3;
      }
      if ( (_BYTE)v12 != 1 )
      {
        if ( (_BYTE)v12 != 2 )
        {
          if ( (_BYTE)v12 != 100 )
            LOBYTE(v12) = MicrosoftTelemetryAssertTriggeredNoArgs();
          *(_BYTE *)a1 = a2;
          *(_BYTE *)(a1 + 2) = 0;
          *a3 = v7;
          goto LABEL_37;
        }
        v14 = v13 + *(unsigned __int8 *)(a1 + 1);
        if ( v14 < (unsigned int)v13 )
          goto LABEL_25;
        if ( v14 < v5 )
          goto LABEL_17;
        v5 = v14 + (v5 >> 1);
        if ( v5 >= v14 )
        {
          if ( v5 <= 0x7FFFFFFF )
          {
            *a4 = v5;
            v12 = MTX_mem_realloc(*(_QWORD *)(a1 + 8), v7, v5);
            v7 = v12;
            if ( !v12 )
              goto LABEL_4;
LABEL_17:
            v15 = *(unsigned __int8 *)(a1 + 1);
            if ( *(_BYTE *)(a1 + 1) )
            {
              LOBYTE(v12) = (unsigned __int8)memset_0((void *)(v7 + v13), a2, *(unsigned __int8 *)(a1 + 1));
              do
              {
                LODWORD(v13) = v13 + 1;
                --v15;
              }
              while ( v15 );
            }
            if ( (unsigned int)v13 > v5 )
              LOBYTE(v12) = MicrosoftTelemetryAssertTriggeredNoArgs();
            *(_BYTE *)(a1 + 2) = 0;
LABEL_11:
            *a3 = v7;
            if ( (int)v13 < 0 )
            {
              *a5 = -1;
              v11 = *(_QWORD *)(a1 + 8);
              goto LABEL_3;
            }
LABEL_37:
            *a5 = v13;
            return v12;
          }
          *a4 = -1;
        }
        v11 = *(_QWORD *)(a1 + 8);
        goto LABEL_3;
      }
      *(_BYTE *)(a1 + 1) = a2;
      if ( a2 )
      {
        LOBYTE(v12) = 2;
        goto LABEL_47;
      }
      if ( (unsigned int)v13 <= v5 )
      {
        if ( (unsigned int)v13 < v5 )
        {
LABEL_33:
          *(_BYTE *)(v13 + v7) = *(_BYTE *)a1;
          LODWORD(v13) = v13 + 1;
          LOBYTE(v12) = 0;
LABEL_47:
          *(_BYTE *)(a1 + 2) = v12;
          goto LABEL_11;
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      v17 = v5 + (v5 >> 1);
      if ( (unsigned int)v17 < v5 )
        goto LABEL_25;
      if ( (unsigned int)v17 > 0x7FFFFFFF )
        goto LABEL_24;
      *a4 = v17;
      v7 = MTX_mem_realloc(*(_QWORD *)(a1 + 8), v7, v17);
      if ( !v7 )
        goto LABEL_4;
      goto LABEL_33;
    }
  }
  v11 = *(_QWORD *)(a1 + 8);
LABEL_3:
  DiscardPointer(v11, v7, 1);
LABEL_4:
  LOBYTE(v12) = 0;
  *a3 = 0;
  return v12;
}

```

## disassembly

```asm
0x180009a50  push    rbx
0x180009a52  push    rbp
0x180009a53  push    rsi
0x180009a54  push    rdi
0x180009a55  push    r12
0x180009a57  push    r13
0x180009a59  push    r14
0x180009a5b  push    r15
0x180009a5d  sub     rsp, 28h
0x180009a61  mov     r12d, [r9]
0x180009a64  mov     r13, r9
0x180009a67  mov     rdi, [r8]
0x180009a6a  mov     rsi, r8
0x180009a6d  movzx   ebp, dl
0x180009a70  mov     r15, rcx
0x180009a73  test    r12d, r12d
0x180009a76  jns     short loc_180009AA0
0x180009a78  mov     rcx, [rcx+8]
0x180009a7c  mov     r8d, 1
0x180009a82  mov     rdx, rdi
0x180009a85  call    DiscardPointer
0x180009a8a  xor     eax, eax
0x180009a8c  mov     [rsi], rax
0x180009a8f  add     rsp, 28h
0x180009a93  pop     r15
0x180009a95  pop     r14
0x180009a97  pop     r13
0x180009a99  pop     r12
0x180009a9b  pop     rdi
0x180009a9c  pop     rsi
0x180009a9d  pop     rbp
0x180009a9e  pop     rbx
0x180009a9f  retn
0x180009aa0  mov     r14, [rsp+68h+arg_20]
0x180009aa8  mov     ebx, [r14]
0x180009aab  test    ebx, ebx
0x180009aad  js      short loc_180009A78
0x180009aaf  movzx   eax, byte ptr [rcx+2]
0x180009ab3  test    al, al
0x180009ab5  jnz     short loc_180009AED
0x180009ab7  cmp     bpl, [rcx]
0x180009aba  jz      loc_180009BD5
0x180009ac0  cmp     ebx, r12d
0x180009ac3  ja      loc_180009BE4
0x180009ac9  jnb     loc_180009B73
0x180009acf  mov     [rbx+rdi], bpl
0x180009ad3  inc     ebx
0x180009ad5  mov     [rsi], rdi
0x180009ad8  test    ebx, ebx
0x180009ada  jns     loc_180009BDC
0x180009ae0  mov     dword ptr [r14], 0FFFFFFFFh
0x180009ae7  mov     rcx, [r15+8]
0x180009aeb  jmp     short loc_180009A7C
0x180009aed  cmp     al, 1
0x180009aef  jz      loc_180009C0C
0x180009af5  cmp     al, 2
0x180009af7  jnz     loc_180009C59
0x180009afd  movzx   ecx, byte ptr [rcx+1]
0x180009b01  add     ecx, ebx
0x180009b03  cmp     ecx, ebx
0x180009b05  jb      short loc_180009B4F
0x180009b07  cmp     ecx, r12d
0x180009b0a  jnb     short loc_180009B5F
0x180009b0c  movzx   r13d, byte ptr [r15+1]
0x180009b11  test    r13d, r13d
0x180009b14  jz      short loc_180009B2E
0x180009b16  mov     r8d, r13d; Size
0x180009b19  lea     rcx, [rdi+rbx]; void *
0x180009b1d  movzx   edx, bpl; Val
0x180009b21  call    memset_0
0x180009b26  inc     ebx
0x180009b28  add     r13d, 0FFFFFFFFh
0x180009b2c  jnz     short loc_180009B26
0x180009b2e  cmp     ebx, r12d
0x180009b31  ja      short loc_180009B58
0x180009b33  mov     byte ptr [r15+2], 0
0x180009b38  jmp     short loc_180009AD5
0x180009b3a  cmp     r8d, 7FFFFFFFh
0x180009b41  jbe     loc_180009BEB
0x180009b47  mov     dword ptr [r13+0], 0FFFFFFFFh
0x180009b4f  mov     rcx, [r15+8]
0x180009b53  jmp     loc_180009A7C
0x180009b58  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009b5d  jmp     short loc_180009B33
0x180009b5f  shr     r12d, 1
0x180009b62  add     r12d, ecx
0x180009b65  cmp     r12d, ecx
0x180009b68  jnb     short loc_180009BC3
0x180009b6a  mov     rcx, [r15+8]
0x180009b6e  jmp     loc_180009A7C
0x180009b73  mov     r8d, r12d
0x180009b76  shr     r8d, 1
0x180009b79  add     r8d, r12d
0x180009b7c  cmp     r8d, r12d
0x180009b7f  jb      short loc_180009B4F
0x180009b81  jmp     short loc_180009B3A
0x180009b83  mov     r8d, r12d
0x180009b86  shr     r8d, 1
0x180009b89  add     r8d, r12d
0x180009b8c  cmp     r8d, r12d
0x180009b8f  jb      short loc_180009B4F
0x180009b91  cmp     r8d, 7FFFFFFFh
0x180009b98  ja      short loc_180009B47
0x180009b9a  mov     [r13+0], r8d
0x180009b9e  mov     rdx, rdi
0x180009ba1  mov     rcx, [r15+8]
0x180009ba5  call    MTX_mem_realloc
0x180009baa  mov     rdi, rax
0x180009bad  test    rax, rax
0x180009bb0  jz      loc_180009A8A
0x180009bb6  movzx   eax, byte ptr [r15]
0x180009bba  mov     [rbx+rdi], al
0x180009bbd  inc     ebx
0x180009bbf  xor     al, al
0x180009bc1  jmp     short loc_180009C2D
0x180009bc3  cmp     r12d, 7FFFFFFFh
0x180009bca  jbe     short loc_180009C36
0x180009bcc  mov     dword ptr [r9], 0FFFFFFFFh
0x180009bd3  jmp     short loc_180009B6A
0x180009bd5  mov     byte ptr [rcx+2], 1
0x180009bd9  mov     [r8], rdi
0x180009bdc  mov     [r14], ebx
0x180009bdf  jmp     loc_180009A8F
0x180009be4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009be9  jmp     short loc_180009B73
0x180009beb  mov     [r13+0], r8d
0x180009bef  mov     rdx, rdi
0x180009bf2  mov     rcx, [r15+8]
0x180009bf6  call    MTX_mem_realloc
0x180009bfb  mov     rdi, rax
0x180009bfe  test    rax, rax
0x180009c01  jz      loc_180009A8A
0x180009c07  jmp     loc_180009ACF
0x180009c0c  mov     [rcx+1], bpl
0x180009c10  test    bpl, bpl
0x180009c13  jnz     short loc_180009C2B
0x180009c15  cmp     ebx, r12d
0x180009c18  jbe     short loc_180009C24
0x180009c1a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009c1f  jmp     loc_180009B83
0x180009c24  jb      short loc_180009BB6
0x180009c26  jmp     loc_180009B83
0x180009c2b  mov     al, 2
0x180009c2d  mov     [r15+2], al
0x180009c31  jmp     loc_180009AD5
0x180009c36  mov     [r9], r12d
0x180009c39  mov     r8d, r12d
0x180009c3c  mov     rcx, [r15+8]
0x180009c40  mov     rdx, rdi
0x180009c43  call    MTX_mem_realloc
0x180009c48  mov     rdi, rax
0x180009c4b  test    rax, rax
0x180009c4e  jnz     loc_180009B0C
0x180009c54  jmp     loc_180009A8A
0x180009c59  cmp     al, 64h ; 'd'
0x180009c5b  jz      short loc_180009C62
0x180009c5d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009c62  mov     [r15], bpl
0x180009c65  mov     byte ptr [r15+2], 0
0x180009c6a  mov     [rsi], rdi
0x180009c6d  jmp     loc_180009BDC
```

# SizeShares

- ea: `0x18002b0d4`
- end: `0x18002b1d6`
- name: `SizeShares`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029220`

## callees

- `0x18002b0d4`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18002b139`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002b139`

## pseudocode

```c
__int64 __fastcall SizeShares(int a1, _QWORD *a2)
{
  __int64 v2; // rbx
  ULONG v5; // r8d
  __int64 v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax

  v2 = -1;
  v5 = 0;
  if ( !a1 )
    goto LABEL_25;
  if ( a1 != 1 )
  {
    if ( a1 == 2 )
    {
LABEL_13:
      v9 = a2[5];
      if ( v9 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)(v9 + 2 * v11) );
        v10 = 2 * (v11 + 1);
      }
      else
      {
        v10 = 0;
      }
      v5 += v10;
      goto LABEL_19;
    }
    if ( a1 != 501 )
    {
      if ( a1 != 502 )
      {
        if ( a1 != 503 )
          goto LABEL_30;
        v6 = a2[7];
        if ( v6 )
        {
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)(v6 + 2 * v7) );
          v5 = 2 * (v7 + 1);
        }
      }
      v8 = (void *)a2[9];
      if ( v8 )
        v5 = RtlLengthSecurityDescriptor(v8) + 4;
      goto LABEL_13;
    }
  }
LABEL_19:
  v12 = a2[2];
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * (v14 + 1);
  }
  else
  {
    v13 = 0;
  }
  v5 += v13;
LABEL_25:
  if ( *a2 )
  {
    do
      ++v2;
    while ( *(_WORD *)(*a2 + 2 * v2) );
    v15 = 2 * (v2 + 1);
  }
  else
  {
    v15 = 0;
  }
  v5 += v15;
LABEL_30:
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v16 = 24;
    }
    else
    {
      v16 = 72;
      if ( a1 == 2 )
        v16 = 56;
    }
  }
  else
  {
    v16 = 8;
  }
  return v5 + v16;
}

```

## disassembly

```asm
0x18002b0d4  push    rbx
0x18002b0d6  push    rbp
0x18002b0d7  push    rsi
0x18002b0d8  push    rdi
0x18002b0d9  sub     rsp, 28h
0x18002b0dd  xor     ebp, ebp
0x18002b0df  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b0e3  mov     rdi, rdx
0x18002b0e6  mov     esi, ecx
0x18002b0e8  mov     r8d, ebp
0x18002b0eb  mov     eax, ecx
0x18002b0ed  test    ecx, ecx
0x18002b0ef  jz      loc_18002B18A
0x18002b0f5  sub     eax, 1
0x18002b0f8  jz      short loc_18002B168
0x18002b0fa  sub     eax, 1
0x18002b0fd  jz      short loc_18002B146
0x18002b0ff  sub     eax, 1F3h
0x18002b104  jz      short loc_18002B168
0x18002b106  sub     eax, 1
0x18002b109  jz      short loc_18002B130
0x18002b10b  cmp     eax, 1
0x18002b10e  jnz     loc_18002B1A9
0x18002b114  mov     rcx, [rdx+38h]
0x18002b118  test    rcx, rcx
0x18002b11b  jz      short loc_18002B130
0x18002b11d  mov     rax, rbx
0x18002b120  inc     rax
0x18002b123  cmp     [rcx+rax*2], bp
0x18002b127  jnz     short loc_18002B120
0x18002b129  lea     r8d, [rax+1]
0x18002b12d  add     r8, r8
0x18002b130  mov     rcx, [rdx+48h]; SecurityDescriptor
0x18002b134  test    rcx, rcx
0x18002b137  jz      short loc_18002B146
0x18002b139  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002b13f  mov     r8d, eax
0x18002b142  add     r8, 4
0x18002b146  mov     rcx, [rdi+28h]
0x18002b14a  test    rcx, rcx
0x18002b14d  jnz     short loc_18002B154
0x18002b14f  mov     rax, rbp
0x18002b152  jmp     short loc_18002B165
0x18002b154  mov     rax, rbx
0x18002b157  inc     rax
0x18002b15a  cmp     [rcx+rax*2], bp
0x18002b15e  jnz     short loc_18002B157
0x18002b160  inc     eax
0x18002b162  add     rax, rax
0x18002b165  add     r8, rax
0x18002b168  mov     rcx, [rdi+10h]
0x18002b16c  test    rcx, rcx
0x18002b16f  jnz     short loc_18002B176
0x18002b171  mov     rax, rbp
0x18002b174  jmp     short loc_18002B187
0x18002b176  mov     rax, rbx
0x18002b179  inc     rax
0x18002b17c  cmp     [rcx+rax*2], bp
0x18002b180  jnz     short loc_18002B179
0x18002b182  inc     eax
0x18002b184  add     rax, rax
0x18002b187  add     r8, rax
0x18002b18a  mov     rax, [rdi]
0x18002b18d  test    rax, rax
0x18002b190  jnz     short loc_18002B197
0x18002b192  mov     rax, rbp
0x18002b195  jmp     short loc_18002B1A6
0x18002b197  inc     rbx
0x18002b19a  cmp     [rax+rbx*2], bp
0x18002b19e  jnz     short loc_18002B197
0x18002b1a0  lea     eax, [rbx+1]
0x18002b1a3  add     rax, rax
0x18002b1a6  add     r8, rax
0x18002b1a9  test    esi, esi
0x18002b1ab  jnz     short loc_18002B1B2
0x18002b1ad  lea     eax, [rsi+8]
0x18002b1b0  jmp     short loc_18002B1CA
0x18002b1b2  cmp     esi, 1
0x18002b1b5  jnz     short loc_18002B1BC
0x18002b1b7  lea     eax, [rsi+17h]
0x18002b1ba  jmp     short loc_18002B1CA
0x18002b1bc  mov     eax, 48h ; 'H'
0x18002b1c1  cmp     esi, 2
0x18002b1c4  lea     ecx, [rax-10h]
0x18002b1c7  cmovz   eax, ecx
0x18002b1ca  add     eax, r8d
0x18002b1cd  add     rsp, 28h
0x18002b1d1  pop     rdi
0x18002b1d2  pop     rsi
0x18002b1d3  pop     rbp
0x18002b1d4  pop     rbx
0x18002b1d5  retn
```

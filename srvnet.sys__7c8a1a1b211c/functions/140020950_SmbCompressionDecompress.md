# SmbCompressionDecompress

- ea: `0x140020950`
- end: `0x140020a8c`
- name: `SmbCompressionDecompress`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020500`

## callees

- `0x140020484`
- `0x1400204a8`
- `0x140020950`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlDecompressBufferEx2` at `0x140020a56`
- `ntoskrnl!RtlDecompressBufferEx2` at `0x140020a56`

## pseudocode

```c
__int64 __fastcall SmbCompressionDecompress(
        int a1,
        unsigned int *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5,
        _DWORD *a6)
{
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  unsigned __int16 v14; // bx
  size_t v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbp
  unsigned int v19; // esi
  int v20; // eax

  if ( !a1 )
    return (unsigned int)-1073741637;
  v10 = a1 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( !v13 )
        {
          if ( a3 >= 8 )
          {
            v15 = a2[1];
            if ( (unsigned int)v15 <= a5 )
            {
              memset(a4, *(unsigned __int8 *)a2, v15);
              v9 = 0;
              *a6 = a2[1];
            }
            else
            {
              return (unsigned int)-1073741789;
            }
          }
          else
          {
            return (unsigned int)-1073739509;
          }
          return v9;
        }
        if ( v13 != 1 )
          return (unsigned int)-1073741217;
        v14 = 6;
      }
      else
      {
        v14 = 4;
      }
    }
    else
    {
      v14 = 3;
    }
  }
  else
  {
    v14 = 2;
  }
  v16 = PplAllocateFromLookasideList();
  v18 = v16;
  if ( v16 )
  {
    if ( a3 < 4 || (v19 = *a2, *a2 > a5) )
    {
      v9 = -1073739509;
    }
    else
    {
      v20 = RtlDecompressBufferEx2(v14, a4, v19, a2 + 1, a3 - 4, 0, a6, v16);
      v9 = v20;
      if ( v20 >= 0 )
      {
        if ( *a6 != v19 )
          v20 = -1073739509;
        v9 = v20;
      }
    }
    PplFreeToLookasideList(v17, v18);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v9;
}

```

## disassembly

```asm
0x140020950  push    rbx
0x140020952  push    rbp
0x140020953  push    rsi
0x140020954  push    rdi
0x140020955  push    r14
0x140020957  push    r15
0x140020959  sub     rsp, 48h
0x14002095d  mov     r15, r9
0x140020960  mov     r14d, r8d
0x140020963  mov     rdi, rdx
0x140020966  test    ecx, ecx
0x140020968  jnz     short loc_140020974
0x14002096a  mov     ebx, 0C00000BBh
0x14002096f  jmp     loc_140020A7C
0x140020974  mov     esi, 4
0x140020979  sub     ecx, 1
0x14002097c  jz      short loc_1400209F7
0x14002097e  sub     ecx, 1
0x140020981  jz      short loc_1400209F0
0x140020983  sub     ecx, 1
0x140020986  jz      short loc_1400209EB
0x140020988  sub     ecx, 1
0x14002098b  jz      short loc_1400209A3
0x14002098d  cmp     ecx, 1
0x140020990  jz      short loc_14002099C
0x140020992  mov     ebx, 0C000025Fh
0x140020997  jmp     loc_140020A7C
0x14002099c  mov     ebx, 6
0x1400209a1  jmp     short loc_1400209FC
0x1400209a3  cmp     r14d, 8
0x1400209a7  jnb     short loc_1400209B3
0x1400209a9  mov     ebx, 0C000090Bh
0x1400209ae  jmp     loc_140020A7C
0x1400209b3  mov     eax, [rdx+4]
0x1400209b6  cmp     eax, [rsp+78h+arg_20]
0x1400209bd  jbe     short loc_1400209C9
0x1400209bf  mov     ebx, 0C0000023h
0x1400209c4  jmp     loc_140020A7C
0x1400209c9  movzx   edx, byte ptr [rdx]; Val
0x1400209cc  mov     r8, rax; Size
0x1400209cf  mov     rcx, r15; void *
0x1400209d2  call    memset
0x1400209d7  mov     rax, [rsp+78h+arg_28]
0x1400209df  xor     ebx, ebx
0x1400209e1  mov     ecx, [rdi+4]
0x1400209e4  mov     [rax], ecx
0x1400209e6  jmp     loc_140020A7C
0x1400209eb  movzx   ebx, si
0x1400209ee  jmp     short loc_1400209FC
0x1400209f0  mov     ebx, 3
0x1400209f5  jmp     short loc_1400209FC
0x1400209f7  mov     ebx, 2
0x1400209fc  call    PplAllocateFromLookasideList
0x140020a01  mov     rbp, rax
0x140020a04  test    rax, rax
0x140020a07  jnz     short loc_140020A10
0x140020a09  mov     ebx, 0C000009Ah
0x140020a0e  jmp     short loc_140020A7C
0x140020a10  cmp     r14d, esi
0x140020a13  jnb     short loc_140020A1C
0x140020a15  mov     ebx, 0C000090Bh
0x140020a1a  jmp     short loc_140020A74
0x140020a1c  mov     esi, [rdi]
0x140020a1e  cmp     esi, [rsp+78h+arg_20]
0x140020a25  ja      short loc_140020A15
0x140020a27  mov     [rsp+78h+var_40], rbp
0x140020a2c  lea     r9, [rdi+4]
0x140020a30  mov     rdi, [rsp+78h+arg_28]
0x140020a38  lea     eax, [r14-4]
0x140020a3c  mov     [rsp+78h+var_48], rdi
0x140020a41  mov     r8d, esi
0x140020a44  mov     [rsp+78h+var_50], 0
0x140020a4c  mov     rdx, r15
0x140020a4f  movzx   ecx, bx
0x140020a52  mov     [rsp+78h+var_58], eax
0x140020a56  call    cs:__imp_RtlDecompressBufferEx2
0x140020a5d  nop     dword ptr [rax+rax+00h]
0x140020a62  mov     ebx, eax
0x140020a64  test    eax, eax
0x140020a66  js      short loc_140020A74
0x140020a68  cmp     [rdi], esi
0x140020a6a  mov     ebx, 0C000090Bh
0x140020a6f  cmovnz  eax, ebx
0x140020a72  mov     ebx, eax
0x140020a74  mov     rdx, rbp
0x140020a77  call    PplFreeToLookasideList
0x140020a7c  mov     eax, ebx
0x140020a7e  add     rsp, 48h
0x140020a82  pop     r15
0x140020a84  pop     r14
0x140020a86  pop     rdi
0x140020a87  pop     rsi
0x140020a88  pop     rbp
0x140020a89  pop     rbx
0x140020a8a  retn
```

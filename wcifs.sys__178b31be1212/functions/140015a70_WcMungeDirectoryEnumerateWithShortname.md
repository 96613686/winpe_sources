# WcMungeDirectoryEnumerateWithShortname

- ea: `0x140015a70`
- end: `0x140015dbb`
- name: `WcMungeDirectoryEnumerateWithShortname`
- size: `843`
- prototype: `__int64 __fastcall(int, char, __int64, char, int, unsigned int, unsigned int *, unsigned int, char, unsigned int **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x140029060`

## callees

- `0x1400020c4`
- `0x140007c90`
- `0x140007cb0`
- `0x14001439c`
- `0x140014400`
- `0x14001443c`
- `0x14001449c`
- `0x14001452c`
- `0x140015a70`

## pseudocode

```c
__int64 __fastcall WcMungeDirectoryEnumerateWithShortname(
        int a1,
        char a2,
        __int64 a3,
        char a4,
        int a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int a8,
        char a9,
        unsigned int **a10,
        unsigned int *a11)
{
  unsigned int v13; // esi
  unsigned int v14; // ebx
  unsigned int v15; // r13d
  unsigned int v16; // r12d
  char v17; // dl
  size_t v18; // r8
  void *v19; // rdx
  void *v20; // rcx
  void *v21; // rcx
  int v22; // edx
  unsigned int v23; // edx
  unsigned int *v24; // r15
  int ULongFromUser; // eax
  unsigned int v26; // eax
  void *v27; // rdx
  void *v28; // rcx

  v13 = 0;
  v14 = 0;
  if ( a1 != 63 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        3,
        18,
        12,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        57,
        a1,
        0);
    v13 = -1073741637;
    goto LABEL_61;
  }
  v15 = *(_DWORD *)(a3 + 60);
  v16 = v15 + 114;
  if ( a8 < v15 + 114 && (a8 < 0x72 || !a2) )
    goto LABEL_61;
  if ( v15 >= a8 - 114 )
    v15 = a8 - 114;
  if ( a9 )
    RtlCopyToUser(a7, (void *)a3, 0x58u);
  else
    RtlCopyVolatileMemory(a7, (const void *)a3, 0x58u);
  if ( !a4 )
  {
    v21 = a7 + 18;
    if ( a9 )
      RtlSetUserMemory(v21, 0xFFu, 0x10u);
    else
      RtlSetVolatileMemory(v21, 255, 0x10u);
LABEL_26:
    if ( a9 )
      RtlWriteUCharToUser((_BYTE *)a7 + 88, 0);
    else
      *((_BYTE *)a7 + 88) = 0;
    goto LABEL_29;
  }
  v17 = *(_BYTE *)(a3 + 88);
  if ( (unsigned __int8)v17 > 0x18u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        2,
        18,
        11,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        0,
        *(char *)(a3 + 88),
        1);
    goto LABEL_26;
  }
  if ( a9 )
    RtlWriteUCharToUser((_BYTE *)a7 + 88, v17);
  else
    *((_BYTE *)a7 + 88) = v17;
  v18 = *(char *)(a3 + 88);
  v19 = (void *)(a3 + 90);
  v20 = (char *)a7 + 90;
  if ( a9 )
    RtlCopyToUser(v20, v19, v18);
  else
    RtlCopyVolatileMemory(v20, v19, v18);
LABEL_29:
  v22 = *(_DWORD *)(a3 + 68);
  if ( v22 == a5 )
  {
    v23 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
    if ( !v23 )
      v23 = 128;
LABEL_40:
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v23);
    else
      a7[14] = v23;
    if ( a9 )
      RtlWriteULongToUser(a7 + 17, 0);
    else
      a7[17] = 0;
    goto LABEL_46;
  }
  if ( (a6 & 0xFFF0000) == 0
    && a6 > 2
    && (a6 & 0xC0000000) != 0x40000000
    && (a6 & 0x30000000) != 0x30000000
    && v22 == a6 )
  {
    v23 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
    if ( !v23 )
      v23 = 128;
    goto LABEL_40;
  }
LABEL_46:
  if ( !a4 )
  {
    v24 = a7 + 14;
    if ( a9 )
      ULongFromUser = RtlReadULongFromUser(a7 + 14);
    else
      ULongFromUser = *v24;
    v26 = ULongFromUser & 0xFFFFBFFF;
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v26);
    else
      *v24 = v26;
  }
  v27 = (void *)(a3 + 114);
  v28 = (char *)a7 + 114;
  if ( a9 )
    RtlCopyToUser(v28, v27, v15);
  else
    RtlCopyVolatileMemory(v28, v27, v15);
  if ( a9 )
    RtlWriteULongToUser(a7, 0);
  else
    *a7 = 0;
  *a10 = a7;
  v14 = v15 + 114;
  if ( v15 + 114 < v16 )
    v13 = -2147483643;
LABEL_61:
  *a11 = v14;
  return v13;
}

```

## disassembly

```asm
0x140015a70  push    rbx
0x140015a72  push    rsi
0x140015a73  push    rdi
0x140015a74  push    r12
0x140015a76  push    r13
0x140015a78  push    r14
0x140015a7a  push    r15
0x140015a7c  sub     rsp, 60h
0x140015a80  mov     r15b, r9b
0x140015a83  mov     r14, r8
0x140015a86  mov     r8d, ecx
0x140015a89  mov     [rsp+98h+var_58], 0
0x140015a8e  xor     esi, esi
0x140015a90  xor     ebx, ebx
0x140015a92  cmp     ecx, 3Fh ; '?'
0x140015a95  jz      short loc_140015AF0
0x140015a97  lea     rcx, WPP_RECORDER_INITIALIZED
0x140015a9e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140015aa5  jz      short loc_140015AE6
0x140015aa7  lea     r9d, [rsi+0Ch]
0x140015aab  mov     [rsp+98h+var_60], r8d
0x140015ab0  mov     [rsp+98h+var_68], 139h
0x140015ab8  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140015abf  mov     [rsp+98h+var_70], rax
0x140015ac4  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x140015acb  mov     [rsp+98h+var_78], rax
0x140015ad0  lea     r8d, [rsi+12h]
0x140015ad4  mov     dl, 3
0x140015ad6  mov     rcx, cs:wil_details_featureDescriptors_a
0x140015add  mov     rcx, [rcx+40h]
0x140015ae1  call    WPP_RECORDER_SF_sDd
0x140015ae6  mov     esi, 0C00000BBh
0x140015aeb  jmp     loc_140015D8F
0x140015af0  mov     r13d, [r14+3Ch]
0x140015af4  lea     r12d, [r13+72h]
0x140015af8  mov     eax, [rsp+98h+arg_38]
0x140015aff  cmp     eax, r12d
0x140015b02  jnb     short loc_140015B15
0x140015b04  cmp     eax, 72h ; 'r'
0x140015b07  jb      loc_140015D93
0x140015b0d  test    dl, dl
0x140015b0f  jz      loc_140015D93
0x140015b15  add     eax, 0FFFFFF8Eh
0x140015b18  cmp     r13d, eax
0x140015b1b  cmovnb  r13d, eax
0x140015b1f  mov     [rsp+98h+var_58], 1
0x140015b24  mov     dil, [rsp+98h+arg_40]
0x140015b2c  mov     r8d, 58h ; 'X'; Size
0x140015b32  mov     rdx, r14; Src
0x140015b35  mov     rbx, [rsp+98h+arg_30]
0x140015b3d  mov     rcx, rbx; void *
0x140015b40  test    dil, dil
0x140015b43  jz      short loc_140015B4C
0x140015b45  call    RtlCopyToUser
0x140015b4a  jmp     short loc_140015B51
0x140015b4c  call    RtlCopyVolatileMemory
0x140015b51  test    r15b, r15b
0x140015b54  jz      loc_140015BEF
0x140015b5a  movsx   edx, byte ptr [r14+58h]
0x140015b5f  cmp     dl, 18h
0x140015b62  ja      short loc_140015B9D
0x140015b64  test    dil, dil
0x140015b67  jz      short loc_140015B74
0x140015b69  lea     rcx, [rbx+58h]
0x140015b6d  call    RtlWriteUCharToUser
0x140015b72  jmp     short loc_140015B77
0x140015b74  mov     [rbx+58h], dl
0x140015b77  movsx   r8, byte ptr [r14+58h]; Size
0x140015b7c  lea     rdx, [r14+5Ah]; Src
0x140015b80  lea     rcx, [rbx+5Ah]; void *
0x140015b84  test    dil, dil
0x140015b87  jz      short loc_140015B93
0x140015b89  call    RtlCopyToUser
0x140015b8e  jmp     loc_140015C27
0x140015b93  call    RtlCopyVolatileMemory
0x140015b98  jmp     loc_140015C27
0x140015b9d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140015ba4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140015bab  jz      short loc_140015C11
0x140015bad  mov     r9d, 0Bh
0x140015bb3  mov     [rsp+98h+var_60], edx
0x140015bb7  mov     [rsp+98h+var_68], 100h
0x140015bbf  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140015bc6  mov     [rsp+98h+var_70], rax
0x140015bcb  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x140015bd2  mov     [rsp+98h+var_78], rax
0x140015bd7  lea     r8d, [r9+7]
0x140015bdb  mov     dl, 2
0x140015bdd  mov     rcx, cs:wil_details_featureDescriptors_a
0x140015be4  mov     rcx, [rcx+40h]
0x140015be8  call    WPP_RECORDER_SF_sDd
0x140015bed  jmp     short loc_140015C11
0x140015bef  lea     rcx, [rbx+48h]; void *
0x140015bf3  mov     r8d, 10h; Size
0x140015bf9  test    dil, dil
0x140015bfc  jz      short loc_140015C07
0x140015bfe  mov     dl, 0FFh
0x140015c00  call    RtlSetUserMemory
0x140015c05  jmp     short loc_140015C11
0x140015c07  mov     edx, 0FFh; Val
0x140015c0c  call    RtlSetVolatileMemory
0x140015c11  test    dil, dil
0x140015c14  jz      short loc_140015C23
0x140015c16  xor     edx, edx
0x140015c18  lea     rcx, [rbx+58h]
0x140015c1c  call    RtlWriteUCharToUser
0x140015c21  jmp     short loc_140015C27
0x140015c23  mov     byte ptr [rbx+58h], 0
0x140015c27  mov     edx, [r14+44h]
0x140015c2b  cmp     edx, [rsp+98h+arg_20]
0x140015c32  jnz     short loc_140015C69
0x140015c34  mov     edx, [r14+38h]
0x140015c38  mov     [rsp+98h+var_50], edx
0x140015c3c  mov     eax, edx
0x140015c3e  btr     eax, 0Ah
0x140015c42  mov     [rsp+98h+var_50], eax
0x140015c46  mov     eax, edx
0x140015c48  and     eax, 0FFFFEBFFh
0x140015c4d  mov     [rsp+98h+var_50], eax
0x140015c51  and     edx, 0FFFFE9FFh
0x140015c57  mov     [rsp+98h+var_50], edx
0x140015c5b  mov     eax, 80h
0x140015c60  cmovz   edx, eax
0x140015c63  mov     [rsp+98h+var_50], edx
0x140015c67  jmp     short loc_140015CDA
0x140015c69  mov     ecx, [rsp+98h+arg_28]
0x140015c70  test    ecx, 0FFF0000h
0x140015c76  jnz     loc_140015D06
0x140015c7c  cmp     ecx, 2
0x140015c7f  jbe     loc_140015D06
0x140015c85  mov     eax, ecx
0x140015c87  and     eax, 0C0000000h
0x140015c8c  cmp     eax, 40000000h
0x140015c91  jz      short loc_140015D06
0x140015c93  mov     eax, ecx
0x140015c95  mov     r8d, 30000000h
0x140015c9b  and     eax, r8d
0x140015c9e  cmp     eax, r8d
0x140015ca1  jz      short loc_140015D06
0x140015ca3  cmp     edx, ecx
0x140015ca5  jnz     short loc_140015D06
0x140015ca7  mov     edx, [r14+38h]
0x140015cab  mov     [rsp+98h+var_48], edx
0x140015caf  mov     eax, edx
0x140015cb1  btr     eax, 0Ah
0x140015cb5  mov     [rsp+98h+var_48], eax
0x140015cb9  mov     eax, edx
0x140015cbb  and     eax, 0FFFFEBFFh
0x140015cc0  mov     [rsp+98h+var_48], eax
0x140015cc4  and     edx, 0FFFFE9FFh
0x140015cca  mov     [rsp+98h+var_48], edx
0x140015cce  mov     eax, 80h
0x140015cd3  cmovz   edx, eax
0x140015cd6  mov     [rsp+98h+var_48], edx
0x140015cda  test    dil, dil
0x140015cdd  jz      short loc_140015CEA
0x140015cdf  lea     rcx, [rbx+38h]
0x140015ce3  call    RtlWriteULongToUser
0x140015ce8  jmp     short loc_140015CED
0x140015cea  mov     [rbx+38h], edx
0x140015ced  test    dil, dil
0x140015cf0  jz      short loc_140015CFF
0x140015cf2  xor     edx, edx
0x140015cf4  lea     rcx, [rbx+44h]
0x140015cf8  call    RtlWriteULongToUser
0x140015cfd  jmp     short loc_140015D06
0x140015cff  mov     dword ptr [rbx+44h], 0
0x140015d06  test    r15b, r15b
0x140015d09  jnz     short loc_140015D39
0x140015d0b  lea     r15, [rbx+38h]
0x140015d0f  test    dil, dil
0x140015d12  jz      short loc_140015D1E
0x140015d14  mov     rcx, r15
0x140015d17  call    RtlReadULongFromUser
0x140015d1c  jmp     short loc_140015D21
0x140015d1e  mov     eax, [r15]
0x140015d21  btr     eax, 0Eh
0x140015d25  test    dil, dil
0x140015d28  jz      short loc_140015D36
0x140015d2a  mov     edx, eax
0x140015d2c  mov     rcx, r15
0x140015d2f  call    RtlWriteULongToUser
0x140015d34  jmp     short loc_140015D39
0x140015d36  mov     [r15], eax
0x140015d39  lea     rdx, [r14+72h]; Src
0x140015d3d  lea     rcx, [rbx+72h]; void *
0x140015d41  mov     r8d, r13d; Size
0x140015d44  test    dil, dil
0x140015d47  jz      short loc_140015D50
0x140015d49  call    RtlCopyToUser
0x140015d4e  jmp     short loc_140015D55
0x140015d50  call    RtlCopyVolatileMemory
0x140015d55  test    dil, dil
0x140015d58  jz      short loc_140015D66
0x140015d5a  xor     edx, edx
0x140015d5c  mov     rcx, rbx
0x140015d5f  call    RtlWriteULongToUser
0x140015d64  jmp     short loc_140015D6C
0x140015d66  mov     dword ptr [rbx], 0
0x140015d6c  mov     rax, [rsp+98h+arg_48]
0x140015d74  mov     [rax], rbx
0x140015d77  mov     [rsp+98h+var_58], 0
0x140015d7c  lea     ebx, [r13+72h]
0x140015d80  mov     [rsp+98h+var_3C], ebx
0x140015d84  mov     eax, 80000005h
0x140015d89  cmp     ebx, r12d
0x140015d8c  cmovb   esi, eax
0x140015d8f  mov     [rsp+98h+var_40], esi
0x140015d93  mov     rax, [rsp+98h+arg_50]
0x140015d9b  mov     [rax], ebx
0x140015d9d  jmp     short loc_140015DA8
0x140015d9f  mov     esi, 0C00000E8h
0x140015da4  mov     [rsp+98h+var_40], esi
0x140015da8  mov     eax, esi
0x140015daa  add     rsp, 60h
0x140015dae  pop     r15
0x140015db0  pop     r14
0x140015db2  pop     r13
0x140015db4  pop     r12
0x140015db6  pop     rdi
0x140015db7  pop     rsi
0x140015db8  pop     rbx
0x140015db9  retn
0x140034ead  push    rbp
0x140034eaf  sub     rsp, 40h
0x140034eb3  mov     rbp, rdx
0x140034eb6  xor     eax, eax
0x140034eb8  cmp     [rbp+40h], al
0x140034ebb  setnz   al
0x140034ebe  add     rsp, 40h
0x140034ec2  pop     rbp
0x140034ec3  retn
```

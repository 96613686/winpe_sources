# WcMungeDirectoryEnumerateWithoutShortname

- ea: `0x140016aa8`
- end: `0x140016d5f`
- name: `WcMungeDirectoryEnumerateWithoutShortname`
- size: `695`
- prototype: `__int64 __fastcall(int, char, _DWORD *, char, int, unsigned int, unsigned int *, unsigned int, char, unsigned int **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
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
- `0x14001452c`
- `0x140016aa8`

## pseudocode

```c
__int64 __fastcall WcMungeDirectoryEnumerateWithoutShortname(
        int a1,
        char a2,
        _DWORD *a3,
        char a4,
        int a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int a8,
        char a9,
        unsigned int **a10,
        unsigned int *a11)
{
  unsigned int v13; // edi
  unsigned int v14; // ebx
  _UNKNOWN **v15; // rdx
  unsigned int v16; // r13d
  unsigned int v17; // r14d
  int v18; // edx
  unsigned int v19; // edx
  unsigned int *v20; // r14
  int ULongFromUser; // eax
  unsigned int v22; // eax
  void *v23; // rdx
  void *v24; // rcx
  void *v25; // rcx
  unsigned int v27; // [rsp+A0h] [rbp+18h]

  v13 = 0;
  v14 = 0;
  if ( a1 != 60 )
  {
    v15 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 3;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        (_DWORD)v15,
        18,
        10,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        161,
        a1,
        0);
    }
    v13 = -1073741637;
    goto LABEL_50;
  }
  v16 = a3[15];
  v17 = v16 + 88;
  v27 = v16 + 88;
  if ( a8 < v16 + 88 && (a8 < 0x58 || !a2) )
    goto LABEL_50;
  if ( v16 >= a8 - 88 )
    v16 = a8 - 88;
  if ( a9 )
    RtlCopyToUser(a7, a3, 0x58u);
  else
    RtlCopyVolatileMemory(a7, a3, 0x58u);
  v18 = a3[17];
  if ( v18 == a5 )
  {
    v19 = a3[14] & 0xFFFFE9FF;
    if ( !v19 )
      v19 = 128;
LABEL_24:
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v19);
    else
      a7[14] = v19;
    if ( a9 )
      RtlWriteULongToUser(a7 + 17, 0);
    else
      a7[17] = 0;
    goto LABEL_30;
  }
  if ( (a6 & 0xFFF0000) == 0
    && a6 > 2
    && (a6 & 0xC0000000) != 0x40000000
    && (a6 & 0x30000000) != 0x30000000
    && v18 == a6 )
  {
    v19 = a3[14] & 0xFFFFE9FF;
    if ( !v19 )
      v19 = 128;
    goto LABEL_24;
  }
LABEL_30:
  if ( !a4 )
  {
    v20 = a7 + 14;
    if ( a9 )
      ULongFromUser = RtlReadULongFromUser(a7 + 14);
    else
      ULongFromUser = *v20;
    v22 = ULongFromUser & 0xFFFFBFFF;
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v22);
    else
      *v20 = v22;
    v17 = v27;
  }
  v23 = a3 + 22;
  v24 = a7 + 22;
  if ( a9 )
    RtlCopyToUser(v24, v23, v16);
  else
    RtlCopyVolatileMemory(v24, v23, v16);
  if ( !a4 )
  {
    v25 = a7 + 18;
    if ( a9 )
      RtlSetUserMemory(v25, 0xFFu, 0x10u);
    else
      RtlSetVolatileMemory(v25, 255, 0x10u);
  }
  if ( a9 )
    RtlWriteULongToUser(a7, 0);
  else
    *a7 = 0;
  *a10 = a7;
  v14 = v16 + 88;
  if ( v16 + 88 < v17 )
    v13 = -2147483643;
LABEL_50:
  *a11 = v14;
  return v13;
}

```

## disassembly

```asm
0x140016aa8  mov     rax, rsp
0x140016aab  mov     [rax+8], rbx
0x140016aaf  mov     [rax+10h], rsi
0x140016ab3  push    rdi
0x140016ab4  push    r12
0x140016ab6  push    r13
0x140016ab8  push    r14
0x140016aba  push    r15
0x140016abc  sub     rsp, 60h
0x140016ac0  mov     r12b, r9b
0x140016ac3  mov     r15, r8
0x140016ac6  mov     byte ptr [rax-48h], 0
0x140016aca  xor     edi, edi
0x140016acc  xor     ebx, ebx
0x140016ace  cmp     ecx, 3Ch ; '<'
0x140016ad1  jz      short loc_140016B29
0x140016ad3  lea     rdx, WPP_RECORDER_INITIALIZED
0x140016ada  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140016ae1  jz      short loc_140016B1F
0x140016ae3  lea     r9d, [rdi+0Ah]
0x140016ae7  mov     [rax-50h], ecx
0x140016aea  mov     dword ptr [rax-58h], 0A1h
0x140016af1  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140016af8  mov     [rsp+88h+var_60], rax
0x140016afd  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x140016b04  mov     [rsp+88h+var_68], rax
0x140016b09  lea     r8d, [rdi+12h]
0x140016b0d  mov     dl, 3
0x140016b0f  mov     rcx, cs:wil_details_featureDescriptors_a
0x140016b16  mov     rcx, [rcx+40h]
0x140016b1a  call    WPP_RECORDER_SF_sDd
0x140016b1f  mov     edi, 0C00000BBh
0x140016b24  jmp     loc_140016D29
0x140016b29  mov     r13d, [r8+3Ch]
0x140016b2d  lea     r14d, [r13+58h]
0x140016b31  mov     [rsp+88h+arg_10], r14d
0x140016b39  mov     eax, [rsp+88h+arg_38]
0x140016b40  cmp     eax, r14d
0x140016b43  jnb     short loc_140016B56
0x140016b45  cmp     eax, 58h ; 'X'
0x140016b48  jb      loc_140016D2D
0x140016b4e  test    dl, dl
0x140016b50  jz      loc_140016D2D
0x140016b56  add     eax, 0FFFFFFA8h
0x140016b59  cmp     r13d, eax
0x140016b5c  cmovnb  r13d, eax
0x140016b60  mov     [rsp+88h+var_48], 1
0x140016b65  mov     sil, [rsp+88h+arg_40]
0x140016b6d  mov     r8d, 58h ; 'X'; Size
0x140016b73  mov     rdx, r15; Src
0x140016b76  mov     rbx, [rsp+88h+arg_30]
0x140016b7e  mov     rcx, rbx; void *
0x140016b81  test    sil, sil
0x140016b84  jz      short loc_140016B8D
0x140016b86  call    RtlCopyToUser
0x140016b8b  jmp     short loc_140016B92
0x140016b8d  call    RtlCopyVolatileMemory
0x140016b92  mov     edx, [r15+44h]
0x140016b96  cmp     edx, [rsp+88h+arg_20]
0x140016b9d  jnz     short loc_140016BD4
0x140016b9f  mov     edx, [r15+38h]
0x140016ba3  mov     [rsp+88h+var_40], edx
0x140016ba7  mov     eax, edx
0x140016ba9  btr     eax, 0Ah
0x140016bad  mov     [rsp+88h+var_40], eax
0x140016bb1  mov     eax, edx
0x140016bb3  and     eax, 0FFFFEBFFh
0x140016bb8  mov     [rsp+88h+var_40], eax
0x140016bbc  and     edx, 0FFFFE9FFh
0x140016bc2  mov     [rsp+88h+var_40], edx
0x140016bc6  mov     eax, 80h
0x140016bcb  cmovz   edx, eax
0x140016bce  mov     [rsp+88h+var_40], edx
0x140016bd2  jmp     short loc_140016C45
0x140016bd4  mov     ecx, [rsp+88h+arg_28]
0x140016bdb  test    ecx, 0FFF0000h
0x140016be1  jnz     loc_140016C71
0x140016be7  cmp     ecx, 2
0x140016bea  jbe     loc_140016C71
0x140016bf0  mov     eax, ecx
0x140016bf2  and     eax, 0C0000000h
0x140016bf7  cmp     eax, 40000000h
0x140016bfc  jz      short loc_140016C71
0x140016bfe  mov     eax, ecx
0x140016c00  mov     r8d, 30000000h
0x140016c06  and     eax, r8d
0x140016c09  cmp     eax, r8d
0x140016c0c  jz      short loc_140016C71
0x140016c0e  cmp     edx, ecx
0x140016c10  jnz     short loc_140016C71
0x140016c12  mov     edx, [r15+38h]
0x140016c16  mov     [rsp+88h+var_38], edx
0x140016c1a  mov     eax, edx
0x140016c1c  btr     eax, 0Ah
0x140016c20  mov     [rsp+88h+var_38], eax
0x140016c24  mov     eax, edx
0x140016c26  and     eax, 0FFFFEBFFh
0x140016c2b  mov     [rsp+88h+var_38], eax
0x140016c2f  and     edx, 0FFFFE9FFh
0x140016c35  mov     [rsp+88h+var_38], edx
0x140016c39  mov     eax, 80h
0x140016c3e  cmovz   edx, eax
0x140016c41  mov     [rsp+88h+var_38], edx
0x140016c45  test    sil, sil
0x140016c48  jz      short loc_140016C55
0x140016c4a  lea     rcx, [rbx+38h]
0x140016c4e  call    RtlWriteULongToUser
0x140016c53  jmp     short loc_140016C58
0x140016c55  mov     [rbx+38h], edx
0x140016c58  test    sil, sil
0x140016c5b  jz      short loc_140016C6A
0x140016c5d  xor     edx, edx
0x140016c5f  lea     rcx, [rbx+44h]
0x140016c63  call    RtlWriteULongToUser
0x140016c68  jmp     short loc_140016C71
0x140016c6a  mov     dword ptr [rbx+44h], 0
0x140016c71  test    r12b, r12b
0x140016c74  jnz     short loc_140016CAC
0x140016c76  lea     r14, [rbx+38h]
0x140016c7a  test    sil, sil
0x140016c7d  jz      short loc_140016C89
0x140016c7f  mov     rcx, r14
0x140016c82  call    RtlReadULongFromUser
0x140016c87  jmp     short loc_140016C8C
0x140016c89  mov     eax, [r14]
0x140016c8c  btr     eax, 0Eh
0x140016c90  test    sil, sil
0x140016c93  jz      short loc_140016CA1
0x140016c95  mov     edx, eax
0x140016c97  mov     rcx, r14
0x140016c9a  call    RtlWriteULongToUser
0x140016c9f  jmp     short loc_140016CA4
0x140016ca1  mov     [r14], eax
0x140016ca4  mov     r14d, [rsp+88h+arg_10]
0x140016cac  lea     rdx, [r15+58h]; Src
0x140016cb0  lea     rcx, [rbx+58h]; void *
0x140016cb4  mov     r8d, r13d; Size
0x140016cb7  test    sil, sil
0x140016cba  jz      short loc_140016CC3
0x140016cbc  call    RtlCopyToUser
0x140016cc1  jmp     short loc_140016CC8
0x140016cc3  call    RtlCopyVolatileMemory
0x140016cc8  test    r12b, r12b
0x140016ccb  jnz     short loc_140016CEF
0x140016ccd  lea     rcx, [rbx+48h]; void *
0x140016cd1  mov     r8d, 10h; Size
0x140016cd7  test    sil, sil
0x140016cda  jz      short loc_140016CE5
0x140016cdc  mov     dl, 0FFh
0x140016cde  call    RtlSetUserMemory
0x140016ce3  jmp     short loc_140016CEF
0x140016ce5  mov     edx, 0FFh; Val
0x140016cea  call    RtlSetVolatileMemory
0x140016cef  test    sil, sil
0x140016cf2  jz      short loc_140016D00
0x140016cf4  xor     edx, edx
0x140016cf6  mov     rcx, rbx
0x140016cf9  call    RtlWriteULongToUser
0x140016cfe  jmp     short loc_140016D06
0x140016d00  mov     dword ptr [rbx], 0
0x140016d06  mov     rax, [rsp+88h+arg_48]
0x140016d0e  mov     [rax], rbx
0x140016d11  mov     [rsp+88h+var_48], 0
0x140016d16  lea     ebx, [r13+58h]
0x140016d1a  mov     [rsp+88h+var_2C], ebx
0x140016d1e  mov     eax, 80000005h
0x140016d23  cmp     ebx, r14d
0x140016d26  cmovb   edi, eax
0x140016d29  mov     [rsp+88h+var_30], edi
0x140016d2d  mov     rax, [rsp+88h+arg_50]
0x140016d35  mov     [rax], ebx
0x140016d37  jmp     short loc_140016D42
0x140016d39  mov     edi, 0C00000E8h
0x140016d3e  mov     [rsp+88h+var_30], edi
0x140016d42  mov     eax, edi
0x140016d44  lea     r11, [rsp+88h+var_28]
0x140016d49  mov     rbx, [r11+30h]
0x140016d4d  mov     rsi, [r11+38h]
0x140016d51  mov     rsp, r11
0x140016d54  pop     r15
0x140016d56  pop     r14
0x140016d58  pop     r13
0x140016d5a  pop     r12
0x140016d5c  pop     rdi
0x140016d5d  retn
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

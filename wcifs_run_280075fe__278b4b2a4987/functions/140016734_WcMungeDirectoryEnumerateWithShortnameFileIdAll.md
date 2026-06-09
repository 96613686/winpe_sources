# WcMungeDirectoryEnumerateWithShortnameFileIdAll

- ea: `0x140016734`
- end: `0x140016a9f`
- name: `WcMungeDirectoryEnumerateWithShortnameFileIdAll`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140029010`

## callees

- `0x1400020c4`
- `0x140007c90`
- `0x140007cb0`
- `0x14001439c`
- `0x140014400`
- `0x14001443c`
- `0x14001449c`
- `0x1400144e4`
- `0x14001452c`
- `0x140016734`

## pseudocode

```c
__int64 __fastcall WcMungeDirectoryEnumerateWithShortnameFileIdAll(
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
  size_t v17; // r8
  void *v18; // rdx
  void *v19; // rcx
  void *v20; // rcx
  int v21; // edx
  __int64 v22; // rdx
  unsigned int *v23; // r14
  unsigned int ULongFromUser; // eax
  unsigned int v25; // eax
  void *v26; // rdx
  void *v27; // rcx

  v13 = 0;
  v14 = 0;
  if ( a1 != 81 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        18,
        20,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        207,
        a1,
        0);
    v13 = -1073741637;
    goto LABEL_64;
  }
  v15 = *(_DWORD *)(a3 + 60);
  v16 = v15 + 122;
  if ( a8 < v15 + 122 && (a8 < 0x7A || !a2) )
    goto LABEL_64;
  if ( v15 >= a8 - 122 )
    v15 = a8 - 122;
  if ( a9 )
    RtlCopyToUser(a7, (void *)a3, 0x60u);
  else
    RtlCopyVolatileMemory(a7, (const void *)a3, 0x60u);
  if ( !a4 )
  {
    if ( a9 )
      RtlWriteULong64ToUser(a7 + 18, -1);
    else
      *((_QWORD *)a7 + 9) = -1;
    v20 = a7 + 20;
    if ( a9 )
      RtlSetUserMemory(v20);
    else
      RtlSetVolatileMemory(v20, 255, 0x10u);
LABEL_29:
    if ( a9 )
      RtlWriteUCharToUser(a7 + 24, 0);
    else
      *((_BYTE *)a7 + 96) = 0;
    goto LABEL_32;
  }
  if ( *(_BYTE *)(a3 + 96) > 0x18u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        19,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        154,
        *(char *)(a3 + 96),
        1);
    goto LABEL_29;
  }
  if ( a9 )
    RtlWriteUCharToUser(a7 + 24, (unsigned int)*(char *)(a3 + 96));
  else
    *((_BYTE *)a7 + 96) = *(_BYTE *)(a3 + 96);
  v17 = *(char *)(a3 + 96);
  v18 = (void *)(a3 + 98);
  v19 = (char *)a7 + 98;
  if ( a9 )
    RtlCopyToUser(v19, v18, v17);
  else
    RtlCopyVolatileMemory(v19, v18, v17);
LABEL_32:
  v21 = *(_DWORD *)(a3 + 68);
  if ( v21 == a5 )
  {
    v22 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
    if ( (*(_DWORD *)(a3 + 56) & 0xFFFFE9FF) == 0 )
      v22 = 128;
LABEL_43:
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v22);
    else
      a7[14] = v22;
    if ( a9 )
      RtlWriteULongToUser(a7 + 17, 0);
    else
      a7[17] = 0;
    goto LABEL_49;
  }
  if ( (a6 & 0xFFF0000) == 0
    && a6 > 2
    && (a6 & 0xC0000000) != 0x40000000
    && (a6 & 0x30000000) != 0x30000000
    && v21 == a6 )
  {
    v22 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
    if ( (*(_DWORD *)(a3 + 56) & 0xFFFFE9FF) == 0 )
      v22 = 128;
    goto LABEL_43;
  }
LABEL_49:
  if ( !a4 )
  {
    v23 = a7 + 14;
    if ( a9 )
      ULongFromUser = RtlReadULongFromUser(a7 + 14);
    else
      ULongFromUser = *v23;
    v25 = ULongFromUser & 0xFFFFBFFF;
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v25);
    else
      *v23 = v25;
  }
  v26 = (void *)(a3 + 122);
  v27 = (char *)a7 + 122;
  if ( a9 )
    RtlCopyToUser(v27, v26, v15);
  else
    RtlCopyVolatileMemory(v27, v26, v15);
  if ( a9 )
    RtlWriteULongToUser(a7, 0);
  else
    *a7 = 0;
  *a10 = a7;
  v14 = v15 + 122;
  if ( v15 + 122 < v16 )
    v13 = -2147483643;
LABEL_64:
  *a11 = v14;
  return v13;
}

```

## disassembly

```asm
0x140016734  push    rbx
0x140016736  push    rsi
0x140016737  push    rdi
0x140016738  push    r12
0x14001673a  push    r13
0x14001673c  push    r14
0x14001673e  push    r15
0x140016740  sub     rsp, 60h
0x140016744  mov     r14b, r9b
0x140016747  mov     r15, r8
0x14001674a  mov     r8d, ecx
0x14001674d  mov     [rsp+98h+var_58], 0
0x140016752  xor     esi, esi
0x140016754  xor     ebx, ebx
0x140016756  cmp     ecx, 51h ; 'Q'
0x140016759  jz      short loc_1400167B4
0x14001675b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140016762  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140016769  jz      short loc_1400167AA
0x14001676b  lea     r9d, [rsi+14h]
0x14001676f  mov     [rsp+98h+var_60], r8d
0x140016774  mov     [rsp+98h+var_68], 4CFh
0x14001677c  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140016783  mov     [rsp+98h+var_70], rax
0x140016788  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x14001678f  mov     [rsp+98h+var_78], rax
0x140016794  lea     r8d, [rsi+12h]
0x140016798  mov     dl, 3
0x14001679a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167a1  mov     rcx, [rcx+40h]
0x1400167a5  call    WPP_RECORDER_SF_sDd
0x1400167aa  mov     esi, 0C00000BBh
0x1400167af  jmp     loc_140016A73
0x1400167b4  mov     r13d, [r15+3Ch]
0x1400167b8  lea     r12d, [r13+7Ah]
0x1400167bc  mov     eax, [rsp+98h+arg_38]
0x1400167c3  cmp     eax, r12d
0x1400167c6  jnb     short loc_1400167D9
0x1400167c8  cmp     eax, 7Ah ; 'z'
0x1400167cb  jb      loc_140016A77
0x1400167d1  test    dl, dl
0x1400167d3  jz      loc_140016A77
0x1400167d9  add     eax, 0FFFFFF86h
0x1400167dc  cmp     r13d, eax
0x1400167df  cmovnb  r13d, eax
0x1400167e3  mov     [rsp+98h+var_58], 1
0x1400167e8  mov     dil, [rsp+98h+arg_40]
0x1400167f0  mov     r8d, 60h ; '`'; Size
0x1400167f6  mov     rdx, r15; Src
0x1400167f9  mov     rbx, [rsp+98h+arg_30]
0x140016801  mov     rcx, rbx; void *
0x140016804  test    dil, dil
0x140016807  jz      short loc_140016810
0x140016809  call    RtlCopyToUser
0x14001680e  jmp     short loc_140016815
0x140016810  call    RtlCopyVolatileMemory
0x140016815  test    r14b, r14b
0x140016818  jz      loc_1400168B7
0x14001681e  movsx   edx, byte ptr [r15+60h]
0x140016823  cmp     dl, 18h
0x140016826  ja      short loc_140016861
0x140016828  test    dil, dil
0x14001682b  jz      short loc_140016838
0x14001682d  lea     rcx, [rbx+60h]
0x140016831  call    RtlWriteUCharToUser
0x140016836  jmp     short loc_14001683B
0x140016838  mov     [rbx+60h], dl
0x14001683b  movsx   r8, byte ptr [r15+60h]; Size
0x140016840  lea     rdx, [r15+62h]; Src
0x140016844  lea     rcx, [rbx+62h]; void *
0x140016848  test    dil, dil
0x14001684b  jz      short loc_140016857
0x14001684d  call    RtlCopyToUser
0x140016852  jmp     loc_14001690B
0x140016857  call    RtlCopyVolatileMemory
0x14001685c  jmp     loc_14001690B
0x140016861  lea     rcx, WPP_RECORDER_INITIALIZED
0x140016868  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001686f  jz      loc_1400168F5
0x140016875  mov     r9d, 13h
0x14001687b  mov     [rsp+98h+var_60], edx
0x14001687f  mov     [rsp+98h+var_68], 49Ah
0x140016887  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x14001688e  mov     [rsp+98h+var_70], rax
0x140016893  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x14001689a  mov     [rsp+98h+var_78], rax
0x14001689f  lea     r8d, [r9-1]
0x1400168a3  mov     dl, 2
0x1400168a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400168ac  mov     rcx, [rcx+40h]
0x1400168b0  call    WPP_RECORDER_SF_sDd
0x1400168b5  jmp     short loc_1400168F5
0x1400168b7  test    dil, dil
0x1400168ba  jz      short loc_1400168CB
0x1400168bc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400168c0  lea     rcx, [rbx+48h]
0x1400168c4  call    RtlWriteULong64ToUser
0x1400168c9  jmp     short loc_1400168D3
0x1400168cb  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x1400168d3  lea     rcx, [rbx+50h]; void *
0x1400168d7  mov     r8d, 10h; Size
0x1400168dd  test    dil, dil
0x1400168e0  jz      short loc_1400168EB
0x1400168e2  mov     dl, 0FFh
0x1400168e4  call    RtlSetUserMemory
0x1400168e9  jmp     short loc_1400168F5
0x1400168eb  mov     edx, 0FFh; Val
0x1400168f0  call    RtlSetVolatileMemory
0x1400168f5  test    dil, dil
0x1400168f8  jz      short loc_140016907
0x1400168fa  xor     edx, edx
0x1400168fc  lea     rcx, [rbx+60h]
0x140016900  call    RtlWriteUCharToUser
0x140016905  jmp     short loc_14001690B
0x140016907  mov     byte ptr [rbx+60h], 0
0x14001690b  mov     edx, [r15+44h]
0x14001690f  cmp     edx, [rsp+98h+arg_20]
0x140016916  jnz     short loc_14001694D
0x140016918  mov     edx, [r15+38h]
0x14001691c  mov     [rsp+98h+var_50], edx
0x140016920  mov     eax, edx
0x140016922  btr     eax, 0Ah
0x140016926  mov     [rsp+98h+var_50], eax
0x14001692a  mov     eax, edx
0x14001692c  and     eax, 0FFFFEBFFh
0x140016931  mov     [rsp+98h+var_50], eax
0x140016935  and     edx, 0FFFFE9FFh
0x14001693b  mov     [rsp+98h+var_50], edx
0x14001693f  mov     eax, 80h
0x140016944  cmovz   edx, eax
0x140016947  mov     [rsp+98h+var_50], edx
0x14001694b  jmp     short loc_1400169BE
0x14001694d  mov     ecx, [rsp+98h+arg_28]
0x140016954  test    ecx, 0FFF0000h
0x14001695a  jnz     loc_1400169EA
0x140016960  cmp     ecx, 2
0x140016963  jbe     loc_1400169EA
0x140016969  mov     eax, ecx
0x14001696b  and     eax, 0C0000000h
0x140016970  cmp     eax, 40000000h
0x140016975  jz      short loc_1400169EA
0x140016977  mov     eax, ecx
0x140016979  mov     r8d, 30000000h
0x14001697f  and     eax, r8d
0x140016982  cmp     eax, r8d
0x140016985  jz      short loc_1400169EA
0x140016987  cmp     edx, ecx
0x140016989  jnz     short loc_1400169EA
0x14001698b  mov     edx, [r15+38h]
0x14001698f  mov     [rsp+98h+var_48], edx
0x140016993  mov     eax, edx
0x140016995  btr     eax, 0Ah
0x140016999  mov     [rsp+98h+var_48], eax
0x14001699d  mov     eax, edx
0x14001699f  and     eax, 0FFFFEBFFh
0x1400169a4  mov     [rsp+98h+var_48], eax
0x1400169a8  and     edx, 0FFFFE9FFh
0x1400169ae  mov     [rsp+98h+var_48], edx
0x1400169b2  mov     eax, 80h
0x1400169b7  cmovz   edx, eax
0x1400169ba  mov     [rsp+98h+var_48], edx
0x1400169be  test    dil, dil
0x1400169c1  jz      short loc_1400169CE
0x1400169c3  lea     rcx, [rbx+38h]
0x1400169c7  call    RtlWriteULongToUser
0x1400169cc  jmp     short loc_1400169D1
0x1400169ce  mov     [rbx+38h], edx
0x1400169d1  test    dil, dil
0x1400169d4  jz      short loc_1400169E3
0x1400169d6  xor     edx, edx
0x1400169d8  lea     rcx, [rbx+44h]
0x1400169dc  call    RtlWriteULongToUser
0x1400169e1  jmp     short loc_1400169EA
0x1400169e3  mov     dword ptr [rbx+44h], 0
0x1400169ea  test    r14b, r14b
0x1400169ed  jnz     short loc_140016A1D
0x1400169ef  lea     r14, [rbx+38h]
0x1400169f3  test    dil, dil
0x1400169f6  jz      short loc_140016A02
0x1400169f8  mov     rcx, r14
0x1400169fb  call    RtlReadULongFromUser
0x140016a00  jmp     short loc_140016A05
0x140016a02  mov     eax, [r14]
0x140016a05  btr     eax, 0Eh
0x140016a09  test    dil, dil
0x140016a0c  jz      short loc_140016A1A
0x140016a0e  mov     edx, eax
0x140016a10  mov     rcx, r14
0x140016a13  call    RtlWriteULongToUser
0x140016a18  jmp     short loc_140016A1D
0x140016a1a  mov     [r14], eax
0x140016a1d  lea     rdx, [r15+7Ah]; Src
0x140016a21  lea     rcx, [rbx+7Ah]; void *
0x140016a25  mov     r8d, r13d; Size
0x140016a28  test    dil, dil
0x140016a2b  jz      short loc_140016A34
0x140016a2d  call    RtlCopyToUser
0x140016a32  jmp     short loc_140016A39
0x140016a34  call    RtlCopyVolatileMemory
0x140016a39  test    dil, dil
0x140016a3c  jz      short loc_140016A4A
0x140016a3e  xor     edx, edx
0x140016a40  mov     rcx, rbx
0x140016a43  call    RtlWriteULongToUser
0x140016a48  jmp     short loc_140016A50
0x140016a4a  mov     dword ptr [rbx], 0
0x140016a50  mov     rax, [rsp+98h+arg_48]
0x140016a58  mov     [rax], rbx
0x140016a5b  mov     [rsp+98h+var_58], 0
0x140016a60  lea     ebx, [r13+7Ah]
0x140016a64  mov     [rsp+98h+var_3C], ebx
0x140016a68  mov     eax, 80000005h
0x140016a6d  cmp     ebx, r12d
0x140016a70  cmovb   esi, eax
0x140016a73  mov     [rsp+98h+var_40], esi
0x140016a77  mov     rax, [rsp+98h+arg_50]
0x140016a7f  mov     [rax], ebx
0x140016a81  jmp     short loc_140016A8C
0x140016a83  mov     esi, 0C00000E8h
0x140016a88  mov     [rsp+98h+var_40], esi
0x140016a8c  mov     eax, esi
0x140016a8e  add     rsp, 60h
0x140016a92  pop     r15
0x140016a94  pop     r14
0x140016a96  pop     r13
0x140016a98  pop     r12
0x140016a9a  pop     rdi
0x140016a9b  pop     rsi
0x140016a9c  pop     rbx
0x140016a9d  retn
0x140034e5d  push    rbp
0x140034e5f  sub     rsp, 40h
0x140034e63  mov     rbp, rdx
0x140034e66  xor     eax, eax
0x140034e68  cmp     [rbp+40h], al
0x140034e6b  setnz   al
0x140034e6e  add     rsp, 40h
0x140034e72  pop     rbp
0x140034e73  retn
```

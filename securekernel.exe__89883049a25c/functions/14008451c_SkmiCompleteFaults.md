# SkmiCompleteFaults

- ea: `0x14008451c`
- end: `0x1400848d3`
- name: `SkmiCompleteFaults`
- size: `951`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400843c8`
- `0x1400855c0`

## callees

- `0x140008118`
- `0x1400091e0`
- `0x14000b980`
- `0x140014c80`
- `0x1400273c8`
- `0x14002aeac`
- `0x14002f3f8`
- `0x140030f10`
- `0x140039f74`
- `0x14003a790`
- `0x14003a8c8`
- `0x140050ba4`
- `0x14008451c`
- `0x140085e00`
- `0x1400f3620`

## pseudocode

```c
__int64 __fastcall SkmiCompleteFaults(__int64 a1, unsigned int a2, int a3, __int64 a4, __int64 a5, _DWORD *a6)
{
  __int64 v7; // rdx
  __int64 v8; // r10
  int v10; // ebx
  unsigned int v11; // r14d
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r13
  _QWORD *v15; // rsi
  _DWORD *v16; // rdi
  __int64 v17; // rax
  ULONG_PTR v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r8
  __int64 v29; // r8
  unsigned __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v33; // [rsp+20h] [rbp-59h] BYREF
  int v34; // [rsp+28h] [rbp-51h]
  __int64 v35; // [rsp+30h] [rbp-49h]
  __int64 v36; // [rsp+38h] [rbp-41h]
  _DWORD *v37; // [rsp+40h] [rbp-39h]
  __int64 v38; // [rsp+48h] [rbp-31h]
  _QWORD v39[7]; // [rsp+50h] [rbp-29h] BYREF

  v7 = 0;
  v35 = a4;
  v8 = 0;
  v34 = a3;
  v37 = a6;
  if ( a2 )
  {
    do
    {
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 24 * v8) + 16LL) & 0x7000) != 0x5000 )
      {
        v39[v7] = **(_QWORD **)(a1 + 24 * v8 + 8) & 0xFFFFFFFFFFFFFLL;
        v7 = (unsigned int)(v7 + 1);
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < a2 );
    if ( (_DWORD)v7 )
    {
      SkmiClaimPhysicalPages((ULONG_PTR)v39, v7, 3u);
      a4 = v35;
      v10 = 0;
      v11 = 0;
LABEL_8:
      v12 = 0;
      v36 = 0;
      while ( 1 )
      {
        v13 = 3 * v12;
        v14 = *(_QWORD *)(a1 + 8 * v13);
        v15 = *(_QWORD **)(a1 + 8 * v13 + 8);
        v38 = *(_QWORD *)(a1 + 8 * v13 + 16);
        v16 = (_DWORD *)(v14 + 16);
        v17 = *(_QWORD *)(v14 + 16) & 0x7000LL;
        v18 = *v15 & 0xFFFFFFFFFFFFFLL;
        if ( v17 == 0x4000 )
        {
          v10 = SkmiDecryptPrivatePage(a4, v14 + 16, *v15 & 0xFFFFFFFFFFFFFLL);
          *v37 = 1;
          if ( v10 < 0 )
          {
            SKMI_PAGE_SECURITY(520, *v15 & 0xFFFFFFFFFFFFFLL, 0, 0);
            SkmiSecureZeroPhysicalPage(*v15 & 0xFFFFFFFFFFFFFLL);
            SkmiReleasePhysicalPage(*v15 & 0xFFFFFFFFFFFFFLL);
          }
          goto LABEL_18;
        }
        if ( v17 != 20480 )
          break;
        if ( (unsigned int)SkmiIncrementSharedPageReferenceCount(v18) )
        {
          v33 = (32 * (((*v15 & 0xFFFFFFFFFFLL) << 7) | (*v16 >> 5) & 0x1F)) | 0x802;
          SKMI_SWIZZLE_INVALID_PTE(&v33, 0xFFFFFFFFFFLL, v19, v20);
          v21 = v33 | 0x400;
LABEL_17:
          *(_QWORD *)v16 = v21;
          goto LABEL_18;
        }
        SKMI_PAGE_SECURITY(518, *v15 & 0xFFFFFFFFFFFFFLL, 0, 0);
        v10 = -1073741818;
LABEL_18:
        v24 = v38;
        SkmiLockFaultChain(v38);
        if ( (*(_DWORD *)(v14 + 32) & 2) != 0 )
        {
          if ( v10 >= 0 )
            v10 = -1073741802;
          if ( (*(_QWORD *)v16 & 0xC00LL) == 0xC00 )
          {
            v33 = *(_QWORD *)v16;
            SKMI_UNSWIZZLE_INVALID_PTE(&v33);
            SkmiDecrementPageReferenceCount((v33 >> 12) & 0xFFFFFFFFFFLL);
            v33 = 20482;
            SKMI_SWIZZLE_INVALID_PTE(&v33, v25, v26, v27);
            *(_QWORD *)v16 ^= (v33 ^ *(_QWORD *)v16) & 0xFFFFFFFFFFFFFC1FuLL;
          }
        }
        else if ( v10 >= 0 && a5 != 0x10000 )
        {
          v33 = *(_QWORD *)v16;
          SKMI_UNSWIZZLE_INVALID_PTE(&v33);
          v29 = v28 << 45;
          v30 = v33 & 0xFFFFFFFFFF000LL | SkmiProtectionToPte[(v33 >> 5) & 0x1F] & 0xFFF0000000000FDFuLL | 4;
          if ( v34 )
            v30 = v33 & 0xFFFFFFFFFF000LL | SkmiProtectionToPte[(v33 >> 5) & 0x1F] & 0xFFF0000000000FFFuLL | 4;
          v31 = v35;
          *(_QWORD *)v16 = v29 ^ (v29 ^ v30) & 0xFF7FFFFFFFFFFFFFuLL;
          if ( *(_QWORD *)(v31 + 144) != v31 + 144 )
            SkmiModifyBlockedFaultPte(v31, v24, v14);
        }
        SkmiCompleteFaultChain(v24, v14);
        ++v11;
        a4 = v35;
        v12 = ++v36;
        if ( v11 >= a2 )
          return (unsigned int)v10;
      }
      SkmiZeroSinglePage(v18);
      v33 = (32 * (((*v15 & 0xFFFFFFFFFFLL) << 7) | (*v16 >> 5) & 0x1F)) | 0x802;
      SKMI_SWIZZLE_INVALID_PTE(&v33, 0xFFFFFFFFFFLL, v22, v23);
      v21 = v33;
      goto LABEL_17;
    }
  }
  v10 = 0;
  v11 = 0;
  if ( a2 )
    goto LABEL_8;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14008451c  mov     [rsp-8+arg_8], rbx
0x140084521  push    rbp
0x140084522  push    rsi
0x140084523  push    rdi
0x140084524  push    r12
0x140084526  push    r13
0x140084528  push    r14
0x14008452a  push    r15
0x14008452c  lea     rbp, [rsp-17h]
0x140084531  sub     rsp, 90h
0x140084538  mov     rax, cs:__security_cookie
0x14008453f  xor     rax, rsp
0x140084542  mov     [rbp+47h+var_38], rax
0x140084546  mov     rax, [rbp+47h+arg_28]
0x14008454a  mov     r15d, edx
0x14008454d  xor     edx, edx
0x14008454f  mov     [rbp+47h+var_90], r9
0x140084553  xor     r10d, r10d
0x140084556  mov     [rbp+47h+var_98], r8d
0x14008455a  mov     [rbp+47h+var_80], rax
0x14008455e  mov     r12, rcx
0x140084561  mov     r11, 0FFFFFFFFFFFFFh
0x14008456b  test    r15d, r15d
0x14008456e  jz      short loc_1400845CC
0x140084570  lea     r8, [r10+r10*2]
0x140084574  mov     rax, [r12+r8*8]
0x140084578  mov     ecx, [rax+10h]
0x14008457b  and     ecx, 7000h
0x140084581  cmp     rcx, 5000h
0x140084588  jz      short loc_14008459C
0x14008458a  mov     rax, [r12+r8*8+8]
0x14008458f  mov     rcx, [rax]
0x140084592  and     rcx, r11
0x140084595  mov     [rbp+rdx*8+47h+var_70], rcx
0x14008459a  inc     edx
0x14008459c  inc     r10d
0x14008459f  cmp     r10d, r15d
0x1400845a2  jb      short loc_140084570
0x1400845a4  test    edx, edx
0x1400845a6  jz      short loc_1400845CC
0x1400845a8  mov     r8d, 3
0x1400845ae  lea     rcx, [rbp+47h+var_70]
0x1400845b2  call    SkmiClaimPhysicalPages
0x1400845b7  mov     r9, [rbp+47h+var_90]
0x1400845bb  xor     ebx, ebx
0x1400845bd  xor     r14d, r14d
0x1400845c0  mov     r11, 0FFFFFFFFFFFFFh
0x1400845ca  jmp     short loc_1400845DA
0x1400845cc  xor     ebx, ebx
0x1400845ce  xor     r14d, r14d
0x1400845d1  test    r15d, r15d
0x1400845d4  jz      loc_1400848A9
0x1400845da  xor     eax, eax
0x1400845dc  mov     [rbp+47h+var_88], rax
0x1400845e0  lea     rax, [rax+rax*2]
0x1400845e4  mov     rcx, [r12+rax*8+10h]
0x1400845e9  mov     r13, [r12+rax*8]
0x1400845ed  mov     rsi, [r12+rax*8+8]
0x1400845f2  mov     [rbp+47h+var_78], rcx
0x1400845f6  lea     rdi, [r13+10h]
0x1400845fa  mov     rdx, [rdi]
0x1400845fd  mov     rcx, [rsi]
0x140084600  mov     rax, rdx
0x140084603  and     eax, 7000h
0x140084608  and     rcx, r11; BugCheckParameter3
0x14008460b  cmp     rax, 4000h
0x140084611  jnz     short loc_140084684
0x140084613  mov     r8, rcx
0x140084616  mov     rdx, rdi
0x140084619  mov     rcx, r9
0x14008461c  call    SkmiDecryptPrivatePage
0x140084621  mov     ebx, eax
0x140084623  mov     rax, [rbp+47h+var_80]
0x140084627  mov     dword ptr [rax], 1
0x14008462d  test    ebx, ebx
0x14008462f  jns     loc_14008474D
0x140084635  mov     rdx, [rsi]
0x140084638  mov     rax, 0FFFFFFFFFFFFFh
0x140084642  and     rdx, rax
0x140084645  xor     r9d, r9d
0x140084648  xor     r8d, r8d
0x14008464b  mov     ecx, 208h
0x140084650  call    SKMI_PAGE_SECURITY
0x140084655  mov     rcx, [rsi]
0x140084658  mov     rax, 0FFFFFFFFFFFFFh
0x140084662  and     rcx, rax
0x140084665  call    SkmiSecureZeroPhysicalPage
0x14008466a  mov     rcx, [rsi]
0x14008466d  mov     rax, 0FFFFFFFFFFFFFh
0x140084677  and     rcx, rax; BugCheckParameter3
0x14008467a  call    SkmiReleasePhysicalPage
0x14008467f  jmp     loc_14008474D
0x140084684  cmp     rax, 5000h
0x14008468a  jnz     short loc_140084709
0x14008468c  shr     rdx, 5
0x140084690  and     edx, 1Fh
0x140084693  call    SkmiIncrementSharedPageReferenceCount
0x140084698  test    eax, eax
0x14008469a  jnz     short loc_1400846C6
0x14008469c  mov     rdx, [rsi]
0x14008469f  mov     rax, 0FFFFFFFFFFFFFh
0x1400846a9  and     rdx, rax
0x1400846ac  xor     r9d, r9d
0x1400846af  xor     r8d, r8d
0x1400846b2  mov     ecx, 206h
0x1400846b7  call    SKMI_PAGE_SECURITY
0x1400846bc  mov     ebx, 0C0000006h
0x1400846c1  jmp     loc_14008474D
0x1400846c6  mov     ecx, [rdi]
0x1400846c8  mov     rdx, 0FFFFFFFFFFh
0x1400846d2  mov     rax, [rsi]
0x1400846d5  shr     rcx, 5
0x1400846d9  and     rax, rdx
0x1400846dc  and     ecx, 1Fh
0x1400846df  shl     rax, 7
0x1400846e3  or      rcx, rax
0x1400846e6  shl     rcx, 5
0x1400846ea  or      rcx, 802h
0x1400846f1  mov     [rbp+47h+var_A0], rcx
0x1400846f5  lea     rcx, [rbp+47h+var_A0]
0x1400846f9  call    SKMI_SWIZZLE_INVALID_PTE
0x1400846fe  mov     r9, [rbp+47h+var_A0]
0x140084702  bts     r9, 0Ah
0x140084707  jmp     short loc_14008474A
0x140084709  call    SkmiZeroSinglePage
0x14008470e  mov     ecx, [rdi]
0x140084710  mov     rdx, 0FFFFFFFFFFh
0x14008471a  mov     rax, [rsi]
0x14008471d  shr     rcx, 5
0x140084721  and     rax, rdx
0x140084724  and     ecx, 1Fh
0x140084727  shl     rax, 7
0x14008472b  or      rcx, rax
0x14008472e  shl     rcx, 5
0x140084732  or      rcx, 802h
0x140084739  mov     [rbp+47h+var_A0], rcx
0x14008473d  lea     rcx, [rbp+47h+var_A0]
0x140084741  call    SKMI_SWIZZLE_INVALID_PTE
0x140084746  mov     r9, [rbp+47h+var_A0]
0x14008474a  mov     [rdi], r9
0x14008474d  mov     rsi, [rbp+47h+var_78]
0x140084751  mov     rcx, rsi
0x140084754  call    SkmiLockFaultChain
0x140084759  mov     eax, [r13+20h]
0x14008475d  test    al, 2
0x14008475f  jz      short loc_1400847D5
0x140084761  mov     rcx, [rdi]
0x140084764  test    ebx, ebx
0x140084766  mov     eax, 0C0000016h
0x14008476b  mov     edx, 0C00h
0x140084770  cmovns  ebx, eax
0x140084773  mov     rax, rcx
0x140084776  and     rax, rdx
0x140084779  cmp     rax, rdx
0x14008477c  jnz     loc_140084879
0x140084782  mov     [rbp+47h+var_A0], rcx
0x140084786  lea     rcx, [rbp+47h+var_A0]
0x14008478a  call    SKMI_UNSWIZZLE_INVALID_PTE
0x14008478f  mov     rcx, [rbp+47h+var_A0]
0x140084793  mov     rax, 0FFFFFFFFFFh
0x14008479d  shr     rcx, 0Ch
0x1400847a1  and     rcx, rax; BugCheckParameter3
0x1400847a4  call    SkmiDecrementPageReferenceCount
0x1400847a9  lea     rcx, [rbp+47h+var_A0]
0x1400847ad  mov     [rbp+47h+var_A0], 5002h
0x1400847b5  call    SKMI_SWIZZLE_INVALID_PTE
0x1400847ba  mov     rcx, [rdi]
0x1400847bd  mov     rax, rcx
0x1400847c0  xor     rax, [rbp+47h+var_A0]
0x1400847c4  and     rax, 0FFFFFFFFFFFFFC1Fh
0x1400847ca  xor     rax, rcx
0x1400847cd  mov     [rdi], rax
0x1400847d0  jmp     loc_140084879
0x1400847d5  test    ebx, ebx
0x1400847d7  js      loc_140084879
0x1400847dd  cmp     [rbp+47h+arg_20], 10000h
0x1400847e5  jz      loc_140084879
0x1400847eb  mov     r8, [rdi]
0x1400847ee  lea     rcx, [rbp+47h+var_A0]
0x1400847f2  mov     [rbp+47h+var_A0], r8
0x1400847f6  call    SKMI_UNSWIZZLE_INVALID_PTE
0x1400847fb  mov     rcx, [rbp+47h+var_A0]
0x1400847ff  lea     rdx, SkmiProtectionToPte
0x140084806  mov     rax, rcx
0x140084809  shl     r8, 2Dh
0x14008480d  shr     rax, 5
0x140084811  and     eax, 1Fh
0x140084814  mov     rdx, [rdx+rax*8]
0x140084818  mov     rax, 0FFF0000000000FFFh
0x140084822  and     rdx, rax
0x140084825  mov     rax, 0FFFFFFFFFF000h
0x14008482f  and     rcx, rax
0x140084832  or      rdx, rcx
0x140084835  mov     rcx, 0FF7FFFFFFFFFFFFFh
0x14008483f  or      rdx, 4
0x140084843  mov     rax, rdx
0x140084846  and     rax, 0FFFFFFFFFFFFFFDFh
0x14008484a  cmp     [rbp+47h+var_98], 0
0x14008484e  cmovnz  rax, rdx
0x140084852  xor     rax, r8
0x140084855  and     rax, rcx
0x140084858  mov     rcx, [rbp+47h+var_90]
0x14008485c  xor     rax, r8
0x14008485f  mov     [rdi], rax
0x140084862  lea     rax, [rcx+90h]
0x140084869  cmp     [rax], rax
0x14008486c  jz      short loc_140084879
0x14008486e  mov     r8, r13
0x140084871  mov     rdx, rsi
0x140084874  call    SkmiModifyBlockedFaultPte
0x140084879  mov     rdx, r13
0x14008487c  mov     rcx, rsi
0x14008487f  call    SkmiCompleteFaultChain
0x140084884  mov     rax, [rbp+47h+var_88]
0x140084888  inc     r14d
0x14008488b  mov     r9, [rbp+47h+var_90]
0x14008488f  inc     rax
0x140084892  mov     [rbp+47h+var_88], rax
0x140084896  mov     r11, 0FFFFFFFFFFFFFh
0x1400848a0  cmp     r14d, r15d
0x1400848a3  jb      loc_1400845E0
0x1400848a9  mov     eax, ebx
0x1400848ab  mov     rcx, [rbp+47h+var_38]
0x1400848af  xor     rcx, rsp; StackCookie
0x1400848b2  call    __security_check_cookie
0x1400848b7  mov     rbx, [rsp+0C0h+arg_8]
0x1400848bf  add     rsp, 90h
0x1400848c6  pop     r15
0x1400848c8  pop     r14
0x1400848ca  pop     r13
0x1400848cc  pop     r12
0x1400848ce  pop     rdi
0x1400848cf  pop     rsi
0x1400848d0  pop     rbp
0x1400848d1  retn
```

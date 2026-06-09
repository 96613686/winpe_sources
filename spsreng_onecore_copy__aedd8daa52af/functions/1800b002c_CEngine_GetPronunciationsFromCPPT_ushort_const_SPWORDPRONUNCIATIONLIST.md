# CEngine::GetPronunciationsFromCPPT(ushort const *,SPWORDPRONUNCIATIONLIST *)

- ea: `0x1800b002c`
- end: `0x1800b0321`
- name: `?GetPronunciationsFromCPPT@CEngine@@QEAAJPEBGPEAUSPWORDPRONUNCIATIONLIST@@@Z`
- size: `757`
- prototype: `int(CEngine *__hidden this, const unsigned __int16 *, struct SPWORDPRONUNCIATIONLIST *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b30f8`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x180004312`
- `0x18009d728`
- `0x18009dcb8`
- `0x18009deb4`
- `0x1800b002c`
- `0x1800b113c`
- `0x1800c77ac`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b00b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b02d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b00b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b02d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEngine::GetPronunciationsFromCPPT(
        CEngine *this,
        const unsigned __int16 *a2,
        struct SPWORDPRONUNCIATIONLIST *a3)
{
  struct SPWORDPRONUNCIATIONLIST *v3; // r15
  CEngine *v4; // r14
  int v5; // r12d
  BYTE **p_pvBuffer; // rax
  BYTE **v7; // rdi
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  CPPT *v12; // r13
  unsigned int v13; // eax
  unsigned int v14; // esi
  __int64 v15; // r14
  int v16; // ebx
  int v17; // esi
  __int64 v18; // rax
  SPWORDPRONUNCIATION *pFirstWordPronunciation; // rsi
  SPWORDPRONUNCIATION *v20; // r14
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rcx
  int v25; // [rsp+20h] [rbp-E0h] BYREF
  int v26; // [rsp+24h] [rbp-DCh]
  unsigned __int64 v27; // [rsp+28h] [rbp-D8h]
  CEngine *v28; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v29; // [rsp+38h] [rbp-C8h]
  struct SPWORDPRONUNCIATIONLIST *v30; // [rsp+40h] [rbp-C0h]
  void **v31; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h]
  unsigned int v33; // [rsp+60h] [rbp-A0h]
  __int16 v34; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v35; // [rsp+370h] [rbp+270h] BYREF
  char v36[76]; // [rsp+374h] [rbp+274h] BYREF

  v3 = a3;
  v30 = a3;
  v29 = a2;
  v4 = this;
  v28 = this;
  v33 = 0x80000000;
  Src = &v34;
  v5 = 0;
  v34 = 0;
  v31 = &CQuickStringW<384>::`vftable';
  p_pvBuffer = &a3->pvBuffer;
  if ( !a3 )
    goto LABEL_35;
  v7 = &a3->pvBuffer;
  if ( *p_pvBuffer )
  {
    CoTaskMemFree(*p_pvBuffer);
    *v7 = 0;
    a2 = v29;
  }
  if ( !*((_WORD *)v4 + 116) )
  {
LABEL_34:
    p_pvBuffer = v7;
LABEL_35:
    v9 = -2147467259;
LABEL_36:
    if ( *p_pvBuffer )
    {
      CoTaskMemFree(*p_pvBuffer);
      *(_OWORD *)&v3->ulSize = 0;
      v3->pFirstWordPronunciation = 0;
    }
    goto LABEL_38;
  }
  LOWORD(v8) = 0;
  v26 = 0;
  v9 = -2147467259;
  while ( 1 )
  {
    v10 = 2LL * (unsigned __int16)v8;
    v11 = *((_QWORD *)v4 + 31);
    v12 = *(CPPT **)(v11 + 8 * v10);
    if ( v12 )
    {
      v13 = (**(__int64 (__fastcall ***)(_QWORD, const unsigned __int16 *, __int64))v12)(
              *(_QWORD *)(v11 + 8 * v10),
              a2,
              1);
      if ( v13 != -1 )
      {
        v14 = CPPT::LWIDToPWID(v12, v13);
        if ( v14 != -1 )
        {
          v35 = -1;
          memset_0(v36, 0, sizeof(v36));
          v25 = 0;
          v9 = CPPT::PWIDToAllPWIDs(v12, v14, &v35, &v25);
          p_pvBuffer = v7;
          if ( v9 < 0 )
            goto LABEL_36;
          v15 = 0;
          v16 = 0;
          v17 = v25;
          if ( v25 > 0 )
          {
            do
            {
              if ( (int)CPPT::GetPron(v12, *(_DWORD *)&v36[4 * v16 - 4], (CQuickStringTBase *)&v31) >= 0 )
              {
                v18 = -1;
                do
                  ++v18;
                while ( *((_WORD *)Src + v18) );
                v15 += (2 * v18 + 31) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              ++v16;
            }
            while ( v16 < v17 );
            v3 = v30;
          }
          v9 = ReallocSPWORDPRONList(v3, v15);
          p_pvBuffer = v7;
          if ( v9 < 0 )
            goto LABEL_36;
          pFirstWordPronunciation = v3->pFirstWordPronunciation;
          v27 = (unsigned __int64)pFirstWordPronunciation + v15;
          v20 = pFirstWordPronunciation;
          while ( v5 < v25 )
          {
            if ( (int)CPPT::GetPron(v12, *(_DWORD *)&v36[4 * v5 - 4], (CQuickStringTBase *)&v31) >= 0 )
            {
              pFirstWordPronunciation->eLexiconType = eLEXTYPE_PRIVATE1;
              pFirstWordPronunciation->LangID = *((_WORD *)v28 + 232);
              pFirstWordPronunciation->wPronunciationFlags = 0;
              pFirstWordPronunciation->ePartOfSpeech = SPPS_Unknown;
              v21 = -1;
              do
                ++v21;
              while ( *((_WORD *)Src + v21) );
              if ( (unsigned __int64)&pFirstWordPronunciation->szPronunciation[v21 + 1] > v27 )
                goto LABEL_34;
              memcpy_0(pFirstWordPronunciation->szPronunciation, Src, 2 * v21 + 2);
              v22 = -1;
              do
                ++v22;
              while ( pFirstWordPronunciation->szPronunciation[v22] );
              v23 = (unsigned __int64)pFirstWordPronunciation + ((2 * v22 + 31) & 0xFFFFFFFFFFFFFFF8uLL);
              if ( v23 > v27 )
                goto LABEL_34;
              pFirstWordPronunciation->pNextWordPronunciation = (struct SPWORDPRONUNCIATION *)v23;
              v20 = pFirstWordPronunciation;
              pFirstWordPronunciation = (SPWORDPRONUNCIATION *)((char *)pFirstWordPronunciation
                                                              + ((2 * v22 + 31) & 0xFFFFFFFFFFFFFFF8uLL));
            }
            ++v5;
          }
          v5 = 0;
          v20->pNextWordPronunciation = 0;
          v4 = v28;
        }
      }
    }
    HIWORD(v8) = HIWORD(v26);
    LOWORD(v8) = v26 + 1;
    v26 = v8;
    if ( (unsigned __int16)v8 >= *((_WORD *)v4 + 116) )
      break;
    a2 = v29;
  }
  p_pvBuffer = v7;
  if ( v9 < 0 )
    goto LABEL_36;
LABEL_38:
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v31);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800b002c  mov     [rsp-8+arg_18], rbx
0x1800b0031  push    rbp
0x1800b0032  push    rsi
0x1800b0033  push    rdi
0x1800b0034  push    r12
0x1800b0036  push    r13
0x1800b0038  push    r14
0x1800b003a  push    r15
0x1800b003c  lea     rbp, [rsp-2D0h]
0x1800b0044  sub     rsp, 3D0h
0x1800b004b  mov     rax, cs:__security_cookie
0x1800b0052  xor     rax, rsp
0x1800b0055  mov     [rbp+300h+var_40], rax
0x1800b005c  mov     r15, r8
0x1800b005f  mov     [rsp+400h+var_3C0], r8
0x1800b0064  mov     [rsp+400h+var_3C8], rdx
0x1800b0069  mov     r14, rcx
0x1800b006c  mov     [rsp+400h+var_3D0], rcx
0x1800b0071  mov     [rsp+400h+var_3A0], 80000000h
0x1800b0079  lea     rax, [rsp+400h+var_398]
0x1800b007e  mov     [rsp+400h+Src], rax
0x1800b0083  xor     r12d, r12d
0x1800b0086  mov     [rsp+400h+var_398], r12w
0x1800b008c  lea     rax, ??_7?$CQuickStringW@$0BIA@@@6B@; const CQuickStringW<384>::`vftable'
0x1800b0093  mov     [rsp+400h+var_3B0], rax
0x1800b0098  lea     rax, [r8+8]
0x1800b009c  test    r8, r8
0x1800b009f  jz      loc_1800B02CB
0x1800b00a5  mov     rdi, rax
0x1800b00a8  mov     rcx, [rax]; pv
0x1800b00ab  test    rcx, rcx
0x1800b00ae  jz      short loc_1800B00BE
0x1800b00b0  call    cs:__imp_CoTaskMemFree
0x1800b00b6  mov     [rdi], r12
0x1800b00b9  mov     rdx, [rsp+400h+var_3C8]
0x1800b00be  cmp     r12w, [r14+0E8h]
0x1800b00c6  jnb     loc_1800B02C8
0x1800b00cc  mov     eax, r12d
0x1800b00cf  mov     [rsp+400h+var_3DC], eax
0x1800b00d3  mov     ebx, 80004005h
0x1800b00d8  movzx   ecx, ax
0x1800b00db  add     rcx, rcx
0x1800b00de  mov     rax, [r14+0F8h]
0x1800b00e5  mov     r13, [rax+rcx*8]
0x1800b00e9  test    r13, r13
0x1800b00ec  jz      loc_1800B02A0
0x1800b00f2  mov     rax, [r13+0]
0x1800b00f6  mov     r8d, 1
0x1800b00fc  mov     rcx, r13
0x1800b00ff  mov     rax, [rax]
0x1800b0102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0107  cmp     eax, 0FFFFFFFFh
0x1800b010a  jz      loc_1800B02A0
0x1800b0110  mov     edx, eax; unsigned int
0x1800b0112  mov     rcx, r13; this
0x1800b0115  call    ?LWIDToPWID@CPPT@@QEAAII@Z; CPPT::LWIDToPWID(uint)
0x1800b011a  mov     esi, eax
0x1800b011c  cmp     eax, 0FFFFFFFFh
0x1800b011f  jz      loc_1800B02A0
0x1800b0125  mov     [rbp+300h+var_90], 0FFFFFFFFh
0x1800b012f  xor     edx, edx; Val
0x1800b0131  lea     r8d, [rdx+4Ch]; Size
0x1800b0135  lea     rcx, [rbp+300h+var_8C]; void *
0x1800b013c  call    memset_0
0x1800b0141  mov     [rsp+400h+var_3E0], r12d
0x1800b0146  lea     r9, [rsp+400h+var_3E0]; int *
0x1800b014b  lea     r8, [rbp+300h+var_90]; unsigned int *
0x1800b0152  mov     edx, esi; unsigned int
0x1800b0154  mov     rcx, r13; this
0x1800b0157  call    ?PWIDToAllPWIDs@CPPT@@QEAAJIQEAIPEAH@Z; CPPT::PWIDToAllPWIDs(uint,uint * const,int *)
0x1800b015c  mov     ebx, eax
0x1800b015e  mov     rax, rdi
0x1800b0161  test    ebx, ebx
0x1800b0163  js      loc_1800B02D0
0x1800b0169  mov     r14, r12
0x1800b016c  mov     ebx, r12d
0x1800b016f  mov     esi, [rsp+400h+var_3E0]
0x1800b0173  test    esi, esi
0x1800b0175  jle     short loc_1800B01BF
0x1800b0177  movsxd  rdx, ebx
0x1800b017a  lea     r8, [rsp+400h+var_3B0]; CQuickStringTBase *
0x1800b017f  mov     edx, [rbp+rdx*4+300h+var_90]; unsigned int
0x1800b0186  mov     rcx, r13; this
0x1800b0189  call    ?GetPron@CPPT@@QEAAJIPEAV?$CQuickStringW@$0BIA@@@PEA_N@Z; CPPT::GetPron(uint,CQuickStringW<384> *,bool *)
0x1800b018e  test    eax, eax
0x1800b0190  js      short loc_1800B01B4
0x1800b0192  mov     rcx, [rsp+400h+Src]
0x1800b0197  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b019b  inc     rax
0x1800b019e  cmp     [rcx+rax*2], r12w
0x1800b01a3  jnz     short loc_1800B019B
0x1800b01a5  lea     rax, ds:1Fh[rax*2]
0x1800b01ad  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800b01b1  add     r14, rax
0x1800b01b4  inc     ebx
0x1800b01b6  cmp     ebx, esi
0x1800b01b8  jl      short loc_1800B0177
0x1800b01ba  mov     r15, [rsp+400h+var_3C0]
0x1800b01bf  mov     edx, r14d; unsigned int
0x1800b01c2  mov     rcx, r15; struct SPWORDPRONUNCIATIONLIST *
0x1800b01c5  call    ?ReallocSPWORDPRONList@@YAJPEAUSPWORDPRONUNCIATIONLIST@@K@Z; ReallocSPWORDPRONList(SPWORDPRONUNCIATIONLIST *,ulong)
0x1800b01ca  mov     ebx, eax
0x1800b01cc  mov     rax, rdi
0x1800b01cf  test    ebx, ebx
0x1800b01d1  js      loc_1800B02D0
0x1800b01d7  mov     rsi, [r15+10h]
0x1800b01db  lea     rax, [rsi+r14]
0x1800b01df  mov     [rsp+400h+var_3D8], rax
0x1800b01e4  mov     r14, rsi
0x1800b01e7  cmp     r12d, [rsp+400h+var_3E0]
0x1800b01ec  jge     loc_1800B0295
0x1800b01f2  movsxd  rdx, r12d
0x1800b01f5  lea     r8, [rsp+400h+var_3B0]; CQuickStringTBase *
0x1800b01fa  mov     edx, [rbp+rdx*4+300h+var_90]; unsigned int
0x1800b0201  mov     rcx, r13; this
0x1800b0204  call    ?GetPron@CPPT@@QEAAJIPEAV?$CQuickStringW@$0BIA@@@PEA_N@Z; CPPT::GetPron(uint,CQuickStringW<384> *,bool *)
0x1800b0209  xor     ecx, ecx
0x1800b020b  test    eax, eax
0x1800b020d  js      short loc_1800B028D
0x1800b020f  mov     dword ptr [rsi+8], 1000h
0x1800b0216  mov     rax, [rsp+400h+var_3D0]
0x1800b021b  movzx   eax, word ptr [rax+1D0h]
0x1800b0222  mov     [rsi+0Ch], ax
0x1800b0226  mov     [rsi+0Eh], cx
0x1800b022a  mov     [rsi+10h], ecx
0x1800b022d  mov     rdx, [rsp+400h+Src]; Src
0x1800b0232  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b0236  inc     rax
0x1800b0239  cmp     [rdx+rax*2], cx
0x1800b023d  jnz     short loc_1800B0236
0x1800b023f  lea     r8, ds:2[rax*2]; Size
0x1800b0247  lea     rax, [r8+14h]
0x1800b024b  add     rax, rsi
0x1800b024e  cmp     rax, [rsp+400h+var_3D8]
0x1800b0253  ja      short loc_1800B02C8
0x1800b0255  lea     rcx, [rsi+14h]; void *
0x1800b0259  call    memcpy_0
0x1800b025e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b0262  xor     ecx, ecx
0x1800b0264  inc     rax
0x1800b0267  cmp     [rsi+rax*2+14h], cx
0x1800b026c  jnz     short loc_1800B0264
0x1800b026e  lea     rcx, ds:1Fh[rax*2]
0x1800b0276  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800b027a  add     rcx, rsi
0x1800b027d  cmp     rcx, [rsp+400h+var_3D8]
0x1800b0282  ja      short loc_1800B02C8
0x1800b0284  mov     [rsi], rcx
0x1800b0287  mov     r14, rsi
0x1800b028a  mov     rsi, rcx
0x1800b028d  inc     r12d
0x1800b0290  jmp     loc_1800B01E7
0x1800b0295  xor     r12d, r12d
0x1800b0298  mov     [r14], r12
0x1800b029b  mov     r14, [rsp+400h+var_3D0]
0x1800b02a0  mov     eax, [rsp+400h+var_3DC]
0x1800b02a4  inc     ax
0x1800b02a7  mov     [rsp+400h+var_3DC], eax
0x1800b02ab  cmp     ax, [r14+0E8h]
0x1800b02b3  jnb     short loc_1800B02BF
0x1800b02b5  mov     rdx, [rsp+400h+var_3C8]
0x1800b02ba  jmp     loc_1800B00D8
0x1800b02bf  mov     rax, rdi
0x1800b02c2  test    ebx, ebx
0x1800b02c4  jns     short loc_1800B02EB
0x1800b02c6  jmp     short loc_1800B02D0
0x1800b02c8  mov     rax, rdi
0x1800b02cb  mov     ebx, 80004005h
0x1800b02d0  mov     rcx, [rax]; pv
0x1800b02d3  test    rcx, rcx
0x1800b02d6  jz      short loc_1800B02EB
0x1800b02d8  call    cs:__imp_CoTaskMemFree
0x1800b02de  xorps   xmm0, xmm0
0x1800b02e1  xor     eax, eax
0x1800b02e3  movups  xmmword ptr [r15], xmm0
0x1800b02e7  mov     [r15+10h], rax
0x1800b02eb  lea     rcx, [rsp+400h+var_3B0]; this
0x1800b02f0  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x1800b02f5  mov     eax, ebx
0x1800b02f7  mov     rcx, [rbp+300h+var_40]
0x1800b02fe  xor     rcx, rsp; StackCookie
0x1800b0301  call    __security_check_cookie
0x1800b0306  mov     rbx, [rsp+400h+arg_18]
0x1800b030e  add     rsp, 3D0h
0x1800b0315  pop     r15
0x1800b0317  pop     r14
0x1800b0319  pop     r13
0x1800b031b  pop     r12
0x1800b031d  pop     rdi
0x1800b031e  pop     rsi
0x1800b031f  pop     rbp
0x1800b0320  retn
```

# CBlbRestoreAsync::QueryStatus(_BLB_RESTORE_STATUS *)

- ea: `0x140059f80`
- end: `0x14005a35c`
- name: `?QueryStatus@CBlbRestoreAsync@@UEAAJPEAU_BLB_RESTORE_STATUS@@@Z`
- size: `988`
- prototype: `__int64 __fastcall(CBlbRestoreAsync *__hidden this, struct _BLB_RESTORE_STATUS *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140056110`
- `0x140057bf8`
- `0x140059f80`
- `0x14005a370`
- `0x1400889f0`
- `0x140101b64`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14005a010`
- `KERNEL32!EnterCriticalSection` at `0x14005a010`
- `ole32!CoTaskMemAlloc` at `0x14005a025`
- `ole32!CoTaskMemAlloc` at `0x14005a025`
- `ole32!CoTaskMemFree` at `0x14005a167`
- `ole32!CoTaskMemFree` at `0x14005a2c2`
- `ole32!CoTaskMemFree` at `0x14005a2d7`
- `ole32!CoTaskMemFree` at `0x14005a2e9`
- `ole32!CoTaskMemFree` at `0x14005a2fb`
- `ole32!CoTaskMemFree` at `0x14005a30d`
- `ole32!CoTaskMemFree` at `0x14005a167`
- `ole32!CoTaskMemFree` at `0x14005a2c2`
- `ole32!CoTaskMemFree` at `0x14005a2d7`
- `ole32!CoTaskMemFree` at `0x14005a2e9`
- `ole32!CoTaskMemFree` at `0x14005a2fb`
- `ole32!CoTaskMemFree` at `0x14005a30d`

## string_xrefs

- `0x14005a11b`: `base\stor\blb\engine\service\restore.cpp`

## pseudocode

```c
__int64 __fastcall CBlbRestoreAsync::QueryStatus(CBlbRestoreAsync *this, unsigned __int16 **a2)
{
  PVOID *v4; // rcx
  int VolumeFriendlyNameForPublisher; // esi
  SIZE_T v6; // rcx
  char *v7; // rbp
  __int64 i; // r14
  __int64 v9; // r15
  __int64 v10; // rcx
  LPVOID *v11; // r12
  const unsigned __int16 *v12; // rcx
  void *v13; // rcx
  unsigned int CurrentMedia; // eax
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rcx
  _QWORD v19[2]; // [rsp+20h] [rbp-48h] BYREF
  char v20; // [rsp+30h] [rbp-38h]
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF

  v19[1] = this;
  v19[0] = &CBlbObjectLock<CBlbVerifyBackupAsync>::`vftable';
  v20 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    memset_0(a2, 0, 0x58u);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    v6 = 112LL * *((unsigned int *)this + 83);
    v20 = 1;
    v7 = (char *)CoTaskMemAlloc(v6);
    if ( v7 )
    {
      memset_0(v7, 0, 112LL * *((unsigned int *)this + 83));
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 83); i = (unsigned int)(i + 1) )
      {
        v9 = *((_QWORD *)this + 33);
        v10 = 112LL * (unsigned int)i;
        *(_OWORD *)&v7[v10] = *(_OWORD *)(192 * i + v9 + 60);
        *(_DWORD *)&v7[v10 + 16] = *(_DWORD *)(192 * i + v9 + 76);
        *(_OWORD *)&v7[v10 + 20] = *(_OWORD *)(192 * i + v9 + 80);
        *(_DWORD *)&v7[v10 + 36] = *(_DWORD *)(192 * i + v9 + 96);
        *(_QWORD *)&v7[v10 + 48] = *(_QWORD *)(192 * i + v9);
        *(_QWORD *)&v7[v10 + 56] = *(_QWORD *)(192 * i + v9 + 8);
        *(_DWORD *)&v7[v10 + 80] = *(_DWORD *)(192 * i + v9 + 16);
        *(_DWORD *)&v7[v10 + 84] = *(_DWORD *)(192 * i + v9 + 20);
        *(_DWORD *)&v7[v10 + 88] = *(_DWORD *)(192 * i + v9 + 24);
        *(_DWORD *)&v7[v10 + 92] = *(_DWORD *)(192 * i + v9 + 28);
        *(_QWORD *)&v7[v10 + 64] = *(_QWORD *)(192 * i + v9 + 40);
        *(_QWORD *)&v7[v10 + 72] = *(_QWORD *)(192 * i + v9 + 48);
        *(_DWORD *)&v7[v10 + 104] = *(_DWORD *)(192 * i + v9 + 56);
        *(_DWORD *)&v7[v10 + 100] = *(_DWORD *)(192 * i + v9 + 32);
        *(_DWORD *)&v7[v10 + 96] = *(_DWORD *)(192 * i + v9 + 36);
        v11 = (LPVOID *)&v7[v10 + 40];
        if ( !v11 )
          BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0x15Du, "pwszRestoreTargetFriendlyName");
        *v11 = 0;
        v12 = *(const unsigned __int16 **)(192 * i + v9 + 104);
        pv = 0;
        VolumeFriendlyNameForPublisher = BlbutilDuplicateString(v12, (unsigned __int16 **)&pv, 0);
        if ( VolumeFriendlyNameForPublisher < 0 )
        {
          v13 = pv;
        }
        else
        {
          v13 = 0;
          *v11 = pv;
        }
        if ( v13 )
          CoTaskMemFree(v13);
        if ( VolumeFriendlyNameForPublisher < 0 )
          goto LABEL_33;
      }
      *(_OWORD *)a2 = *((_OWORD *)this + 13);
      *((_DWORD *)a2 + 4) = *((_DWORD *)this + 69);
      *((_DWORD *)a2 + 5) = *((_DWORD *)this + 4);
      *((_DWORD *)a2 + 6) = *((_DWORD *)this + 5);
      *((_DWORD *)a2 + 8) = *((_DWORD *)this + 68);
      *((_DWORD *)a2 + 9) = *((_DWORD *)this + 83);
      if ( !*((_QWORD *)this + 38)
        || (CurrentMedia = CBlbRestoreAsync::GetCurrentMedia(this),
            *((_DWORD *)a2 + 7) = CurrentMedia,
            CurrentMedia >= *((_DWORD *)this + 74))
        || (VolumeFriendlyNameForPublisher = BlbutilDuplicateString(
                                               *(const unsigned __int16 **)(32LL * CurrentMedia
                                                                          + *((_QWORD *)this + 38)
                                                                          + 24),
                                               a2 + 5,
                                               0),
            VolumeFriendlyNameForPublisher >= 0) )
      {
        VolumeFriendlyNameForPublisher = BlbutilDuplicateString(*((const unsigned __int16 **)this + 29), a2 + 6, 0);
        if ( VolumeFriendlyNameForPublisher >= 0 )
        {
          VolumeFriendlyNameForPublisher = BlbutilDuplicateString(*((const unsigned __int16 **)this + 30), a2 + 7, 0);
          if ( VolumeFriendlyNameForPublisher >= 0 )
          {
            VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                               *((_QWORD *)this + 29),
                                               *((unsigned int *)this + 81),
                                               a2 + 10);
            if ( VolumeFriendlyNameForPublisher >= 0 )
            {
              a2[8] = (unsigned __int16 *)v7;
              a2[9] = *(unsigned __int16 **)((char *)this + 356);
              CBlbObjectLock<CBlbVerifyBackupAsync>::ReleaseLock(v19);
              goto LABEL_27;
            }
          }
        }
      }
LABEL_33:
      CoTaskMemFree(v7);
    }
    else
    {
      VolumeFriendlyNameForPublisher = -2147024882;
    }
    CoTaskMemFree(a2[5]);
    v16 = a2[6];
    a2[5] = 0;
    CoTaskMemFree(v16);
    v17 = a2[7];
    a2[6] = 0;
    CoTaskMemFree(v17);
    v18 = a2[10];
    a2[7] = 0;
    CoTaskMemFree(v18);
    a2[10] = 0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    VolumeFriendlyNameForPublisher = -2147467261;
  }
  if ( v4 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
    {
      WPP_SF_d(v4[2], 56, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
LABEL_27:
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 4u )
      WPP_SF_(v4[2], 57, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  CBlbObjectLock<CBlbVerifyBackupAsync>::~CBlbObjectLock<CBlbVerifyBackupAsync>(v19);
  return (unsigned int)VolumeFriendlyNameForPublisher;
}

```

## disassembly

```asm
0x140059f80  mov     r11, rsp
0x140059f83  mov     [r11+10h], rbx
0x140059f87  mov     [r11+18h], rbp
0x140059f8b  push    rsi
0x140059f8c  push    rdi
0x140059f8d  push    r12
0x140059f8f  push    r14
0x140059f91  push    r15
0x140059f93  sub     rsp, 40h
0x140059f97  lea     rax, ??_7?$CBlbObjectLock@VCBlbVerifyBackupAsync@@@@6B@; const CBlbObjectLock<CBlbVerifyBackupAsync>::`vftable'
0x140059f9e  mov     [r11-40h], rcx
0x140059fa2  mov     [r11-48h], rax
0x140059fa6  mov     rbx, rdx
0x140059fa9  mov     [rsp+68h+var_38], 0
0x140059fae  mov     rdi, rcx
0x140059fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140059fb8  lea     r15, WPP_GLOBAL_Control
0x140059fbf  cmp     rcx, r15
0x140059fc2  jz      short loc_140059FEF
0x140059fc4  test    dword ptr [rcx+1Ch], 200h
0x140059fcb  jz      short loc_140059FEF
0x140059fcd  cmp     byte ptr [rcx+19h], 4
0x140059fd1  jb      short loc_140059FEF
0x140059fd3  mov     rcx, [rcx+10h]
0x140059fd7  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x140059fde  mov     edx, 37h ; '7'
0x140059fe3  call    WPP_SF_
0x140059fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x140059fef  test    rbx, rbx
0x140059ff2  jnz     short loc_140059FFE
0x140059ff4  mov     esi, 80004003h
0x140059ff9  jmp     loc_14005A322
0x140059ffe  xor     edx, edx; Val
0x14005a000  mov     rcx, rbx; void *
0x14005a003  lea     r8d, [rdx+58h]; Size
0x14005a007  call    memset_0
0x14005a00c  lea     rcx, [rdi+48h]; lpCriticalSection
0x14005a010  call    cs:__imp_EnterCriticalSection
0x14005a016  mov     eax, [rdi+14Ch]
0x14005a01c  imul    rcx, rax, 70h ; 'p'; cb
0x14005a020  mov     [rsp+68h+var_38], 1
0x14005a025  call    cs:__imp_CoTaskMemAlloc
0x14005a02b  mov     rbp, rax
0x14005a02e  test    rax, rax
0x14005a031  jnz     short loc_14005A03D
0x14005a033  mov     esi, 8007000Eh
0x14005a038  jmp     loc_14005A2D3
0x14005a03d  mov     eax, [rdi+14Ch]
0x14005a043  xor     edx, edx; Val
0x14005a045  imul    r8, rax, 70h ; 'p'; Size
0x14005a049  mov     rcx, rbp; void *
0x14005a04c  call    memset_0
0x14005a051  xor     r14d, r14d
0x14005a054  cmp     r14d, [rdi+14Ch]
0x14005a05b  jnb     loc_14005A17D
0x14005a061  mov     r15, [rdi+108h]
0x14005a068  lea     rsi, [r14+r14*2]
0x14005a06c  shl     rsi, 6
0x14005a070  lea     r12, [rbp+28h]
0x14005a074  mov     eax, r14d
0x14005a077  imul    rcx, rax, 70h ; 'p'
0x14005a07b  movups  xmm0, xmmword ptr [rsi+r15+3Ch]
0x14005a081  movdqu  xmmword ptr [rcx+rbp], xmm0
0x14005a086  mov     eax, [rsi+r15+4Ch]
0x14005a08b  mov     [rcx+rbp+10h], eax
0x14005a08f  movups  xmm0, xmmword ptr [rsi+r15+50h]
0x14005a095  movdqu  xmmword ptr [rcx+rbp+14h], xmm0
0x14005a09b  mov     eax, [rsi+r15+60h]
0x14005a0a0  mov     [rcx+rbp+24h], eax
0x14005a0a4  mov     rax, [rsi+r15]
0x14005a0a8  mov     [rcx+rbp+30h], rax
0x14005a0ad  mov     rax, [rsi+r15+8]
0x14005a0b2  mov     [rcx+rbp+38h], rax
0x14005a0b7  mov     eax, [rsi+r15+10h]
0x14005a0bc  mov     [rcx+rbp+50h], eax
0x14005a0c0  mov     eax, [rsi+r15+14h]
0x14005a0c5  mov     [rcx+rbp+54h], eax
0x14005a0c9  mov     eax, [rsi+r15+18h]
0x14005a0ce  mov     [rcx+rbp+58h], eax
0x14005a0d2  mov     eax, [rsi+r15+1Ch]
0x14005a0d7  mov     [rcx+rbp+5Ch], eax
0x14005a0db  mov     rax, [rsi+r15+28h]
0x14005a0e0  mov     [rcx+rbp+40h], rax
0x14005a0e5  mov     rax, [rsi+r15+30h]
0x14005a0ea  mov     [rcx+rbp+48h], rax
0x14005a0ef  mov     eax, [rsi+r15+38h]
0x14005a0f4  mov     [rcx+rbp+68h], eax
0x14005a0f8  mov     eax, [rsi+r15+20h]
0x14005a0fd  mov     [rcx+rbp+64h], eax
0x14005a101  mov     eax, [rsi+r15+24h]
0x14005a106  mov     [rcx+rbp+60h], eax
0x14005a10a  add     r12, rcx
0x14005a10d  jnz     short loc_14005A127
0x14005a10f  lea     r8, aPwszrestoretar_0; "pwszRestoreTargetFriendlyName"
0x14005a116  mov     edx, 15Dh; unsigned int
0x14005a11b  lea     rcx, aBaseStorBlbEng_22; "base\\stor\\blb\\engine\\service\\resto"...
0x14005a122  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14005a127  mov     qword ptr [r12], 0
0x14005a12f  lea     rdx, [rsp+68h+pv]; unsigned __int16 **
0x14005a134  mov     rcx, [rsi+r15+68h]; unsigned __int16 *
0x14005a139  xor     r8d, r8d; unsigned __int64
0x14005a13c  mov     [rsp+68h+pv], 0
0x14005a145  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14005a14a  mov     esi, eax
0x14005a14c  test    eax, eax
0x14005a14e  js      short loc_14005A15D
0x14005a150  mov     rax, [rsp+68h+pv]
0x14005a155  xor     ecx, ecx
0x14005a157  mov     [r12], rax
0x14005a15b  jmp     short loc_14005A162
0x14005a15d  mov     rcx, [rsp+68h+pv]; pv
0x14005a162  test    rcx, rcx
0x14005a165  jz      short loc_14005A16D
0x14005a167  call    cs:__imp_CoTaskMemFree
0x14005a16d  test    esi, esi
0x14005a16f  js      loc_14005A2BF
0x14005a175  inc     r14d
0x14005a178  jmp     loc_14005A054
0x14005a17d  movups  xmm0, xmmword ptr [rdi+0D0h]
0x14005a184  movdqu  xmmword ptr [rbx], xmm0
0x14005a188  mov     eax, [rdi+114h]
0x14005a18e  mov     [rbx+10h], eax
0x14005a191  mov     eax, [rdi+10h]
0x14005a194  mov     [rbx+14h], eax
0x14005a197  mov     eax, [rdi+14h]
0x14005a19a  mov     [rbx+18h], eax
0x14005a19d  mov     eax, [rdi+110h]
0x14005a1a3  mov     [rbx+20h], eax
0x14005a1a6  mov     eax, [rdi+14Ch]
0x14005a1ac  mov     [rbx+24h], eax
0x14005a1af  cmp     qword ptr [rdi+130h], 0
0x14005a1b7  jz      short loc_14005A1F4
0x14005a1b9  mov     rcx, rdi; this
0x14005a1bc  call    ?GetCurrentMedia@CBlbRestoreAsync@@AEAAKXZ; CBlbRestoreAsync::GetCurrentMedia(void)
0x14005a1c1  mov     [rbx+1Ch], eax
0x14005a1c4  cmp     eax, [rdi+128h]
0x14005a1ca  jnb     short loc_14005A1F4
0x14005a1cc  mov     rcx, [rdi+130h]
0x14005a1d3  lea     rdx, [rbx+28h]; unsigned __int16 **
0x14005a1d7  mov     eax, eax
0x14005a1d9  xor     r8d, r8d; unsigned __int64
0x14005a1dc  shl     rax, 5
0x14005a1e0  mov     rcx, [rax+rcx+18h]; unsigned __int16 *
0x14005a1e5  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14005a1ea  mov     esi, eax
0x14005a1ec  test    eax, eax
0x14005a1ee  js      loc_14005A2BF
0x14005a1f4  mov     rcx, [rdi+0E8h]; unsigned __int16 *
0x14005a1fb  lea     rdx, [rbx+30h]; unsigned __int16 **
0x14005a1ff  xor     r8d, r8d; unsigned __int64
0x14005a202  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14005a207  mov     esi, eax
0x14005a209  test    eax, eax
0x14005a20b  js      loc_14005A2BF
0x14005a211  mov     rcx, [rdi+0F0h]; unsigned __int16 *
0x14005a218  lea     rdx, [rbx+38h]; unsigned __int16 **
0x14005a21c  xor     r8d, r8d; unsigned __int64
0x14005a21f  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14005a224  mov     esi, eax
0x14005a226  test    eax, eax
0x14005a228  js      loc_14005A2BF
0x14005a22e  mov     edx, [rdi+144h]
0x14005a234  lea     r8, [rbx+50h]
0x14005a238  mov     rcx, [rdi+0E8h]
0x14005a23f  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAGW4_BLB_MEDIA_TYPE@@AEAPEAG@Z; GetVolumeFriendlyNameForPublisher(ushort *,_BLB_MEDIA_TYPE,ushort * &)
0x14005a244  mov     esi, eax
0x14005a246  test    eax, eax
0x14005a248  js      short loc_14005A2BF
0x14005a24a  mov     [rbx+40h], rbp
0x14005a24e  lea     rcx, [rsp+68h+var_48]
0x14005a253  mov     rax, [rdi+164h]
0x14005a25a  mov     [rbx+48h], rax
0x14005a25e  call    ?ReleaseLock@?$CBlbObjectLock@VCBlbVerifyBackupAsync@@@@UEAAXXZ; CBlbObjectLock<CBlbVerifyBackupAsync>::ReleaseLock(void)
0x14005a263  lea     r15, WPP_GLOBAL_Control
0x14005a26a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a271  cmp     rcx, r15
0x14005a274  jz      short loc_14005A29A
0x14005a276  test    dword ptr [rcx+1Ch], 200h
0x14005a27d  jz      short loc_14005A29A
0x14005a27f  cmp     byte ptr [rcx+19h], 4
0x14005a283  jb      short loc_14005A29A
0x14005a285  mov     rcx, [rcx+10h]
0x14005a289  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005a290  mov     edx, 39h ; '9'
0x14005a295  call    WPP_SF_
0x14005a29a  lea     rcx, [rsp+68h+var_48]
0x14005a29f  call    ??1?$CBlbObjectLock@VCBlbVerifyBackupAsync@@@@UEAA@XZ; CBlbObjectLock<CBlbVerifyBackupAsync>::~CBlbObjectLock<CBlbVerifyBackupAsync>(void)
0x14005a2a4  lea     r11, [rsp+68h+var_28]
0x14005a2a9  mov     eax, esi
0x14005a2ab  mov     rbx, [r11+38h]
0x14005a2af  mov     rbp, [r11+40h]
0x14005a2b3  mov     rsp, r11
0x14005a2b6  pop     r15
0x14005a2b8  pop     r14
0x14005a2ba  pop     r12
0x14005a2bc  pop     rdi
0x14005a2bd  pop     rsi
0x14005a2be  retn
0x14005a2bf  mov     rcx, rbp; pv
0x14005a2c2  call    cs:__imp_CoTaskMemFree
0x14005a2c8  test    esi, esi
0x14005a2ca  jns     short loc_14005A263
0x14005a2cc  lea     r15, WPP_GLOBAL_Control
0x14005a2d3  mov     rcx, [rbx+28h]; pv
0x14005a2d7  call    cs:__imp_CoTaskMemFree
0x14005a2dd  mov     rcx, [rbx+30h]; pv
0x14005a2e1  mov     qword ptr [rbx+28h], 0
0x14005a2e9  call    cs:__imp_CoTaskMemFree
0x14005a2ef  mov     rcx, [rbx+38h]; pv
0x14005a2f3  mov     qword ptr [rbx+30h], 0
0x14005a2fb  call    cs:__imp_CoTaskMemFree
0x14005a301  mov     rcx, [rbx+50h]; pv
0x14005a305  mov     qword ptr [rbx+38h], 0
0x14005a30d  call    cs:__imp_CoTaskMemFree
0x14005a313  mov     qword ptr [rbx+50h], 0
0x14005a31b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a322  cmp     rcx, r15
0x14005a325  jz      loc_14005A29A
0x14005a32b  test    byte ptr [rcx+1Ch], 1
0x14005a32f  jz      loc_14005A271
0x14005a335  cmp     byte ptr [rcx+19h], 2
0x14005a339  jb      loc_14005A271
0x14005a33f  mov     rcx, [rcx+10h]
0x14005a343  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005a34a  mov     edx, 38h ; '8'
0x14005a34f  mov     r9d, esi
0x14005a352  call    WPP_SF_d
0x14005a357  jmp     loc_14005A26A
```

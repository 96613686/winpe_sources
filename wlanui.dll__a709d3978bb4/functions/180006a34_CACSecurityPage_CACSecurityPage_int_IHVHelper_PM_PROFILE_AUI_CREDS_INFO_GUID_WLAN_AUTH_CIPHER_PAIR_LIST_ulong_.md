# CACSecurityPage::CACSecurityPage(int,IHVHelper *,_PM_PROFILE *,_AUI_CREDS_INFO *,_GUID *,_WLAN_AUTH_CIPHER_PAIR_LIST *,ulong,_WL_DISPLAY_PAGES,ulong const *)

- ea: `0x180006a34`
- end: `0x180006ccf`
- name: `??0CACSecurityPage@@QEAA@HPEAVIHVHelper@@PEAU_PM_PROFILE@@PEAU_AUI_CREDS_INFO@@PEAU_GUID@@PEAU_WLAN_AUTH_CIPHER_PAIR_LIST@@KW4_WL_DISPLAY_PAGES@@PEBK@Z`
- size: `667`
- prototype: `CACSecurityPage *__usercall@<rax>(CACSecurityPage *__hidden this@<rcx>, int@<edx>, struct IHVHelper *@<r8>, struct _PM_PROFILE *@<r9>, struct _AUI_CREDS_INFO *, EAP_ERROR *ppEapError, struct _WLAN_AUTH_CIPHER_PAIR_LIST *, unsigned int, enum _WL_DISPLAY_PAGES, const unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000fe78`

## callees

- `0x180006a34`
- `0x180007df0`
- `0x18000824c`
- `0x1800158d8`
- `0x18001bf0a`

## import_xrefs

- `wlanapi!WpDuplicateProfile` at `0x180006b15`
- `wlanapi!WpDuplicateProfile` at `0x180006b15`
- `eappcfg!EapHostPeerGetMethods` at `0x180006c07`
- `eappcfg!EapHostPeerGetMethods` at `0x180006c07`

## pseudocode

```c
CACSecurityPage *__fastcall CACSecurityPage::CACSecurityPage(
        CACSecurityPage *this,
        int a2,
        struct IHVHelper *a3,
        struct _PM_PROFILE *a4,
        struct _AUI_CREDS_INFO *a5,
        EAP_ERROR *ppEapError,
        struct _WLAN_AUTH_CIPHER_PAIR_LIST *a7,
        unsigned int a8,
        enum _WL_DISPLAY_PAGES a9)
{
  struct _WLAN_AUTH_CIPHER_PAIR_LIST *v10; // rax
  _DWORD *v11; // r11
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r9
  unsigned int v16; // ebx
  int v17; // edi
  int v18; // ebp
  unsigned int v19; // r8d
  __int64 v20; // r14
  __int64 v21; // r15
  int v22; // r9d
  int valid; // eax
  EAP_METHOD_INFO_ARRAY pEapMethodInfoArray; // [rsp+20h] [rbp-58h] BYREF
  EAP_METHOD_TYPE eaptype; // [rsp+30h] [rbp-48h] BYREF

  *((_DWORD *)this + 23) = a2;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CACSecurityPage::`vftable';
  *((_QWORD *)this + 2) = ppEapError;
  v10 = a7;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 3) = v10;
  *((_DWORD *)this + 311) = a8;
  *((_QWORD *)this + 156) = a5;
  *((_DWORD *)this + 314) = a9;
  *((_QWORD *)this + 163) = 0x3FF0000000000000LL;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 154) = a3;
  *((_DWORD *)this + 310) = 0;
  *((_QWORD *)this + 166) = 0;
  *((_QWORD *)this + 167) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 168) = 0;
  *((_QWORD *)this + 169) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 328) = 0;
  *((_QWORD *)this + 5) = a4;
  WpDuplicateProfile(a4, (char *)this + 48);
  memset_0((char *)this + 632, 0, 0x230u);
  v11 = (_DWORD *)*((_QWORD *)this + 3);
  v12 = *(_QWORD *)(*((_QWORD *)this + 5) + 552LL);
  v13 = *(_QWORD *)(*(_QWORD *)(v12 + 32) + 424LL);
  ppEapError = 0;
  pEapMethodInfoArray = 0;
  if ( !v11 )
    goto LABEL_35;
  v14 = *(_QWORD *)(v12 + 32);
  v12 = *(unsigned int *)(v14 + 432);
  if ( (_DWORD)v12 )
  {
    if ( !*(_DWORD *)(v14 + 436) )
      goto LABEL_35;
  }
  if ( !v13 )
    goto LABEL_35;
  v15 = *(_QWORD *)(v13 + 24);
  v16 = 0;
  v17 = 1;
  if ( !v15 || (_DWORD)v12 )
    goto LABEL_16;
  v18 = 1;
  v12 = 0;
  if ( *v11 )
  {
    while ( 1 )
    {
      v18 = 1;
      if ( *(_DWORD *)(v13 + 16) )
        break;
LABEL_14:
      v12 = (unsigned int)(v12 + 1);
      if ( (unsigned int)v12 >= *v11 )
        goto LABEL_17;
    }
    v19 = 0;
    while ( v11[2 * (unsigned int)v12 + 1] != *(_DWORD *)(v15 + 8LL * v19)
         || v11[2 * (unsigned int)v12 + 2] != *(_DWORD *)(v15 + 8LL * v19 + 4) )
    {
      if ( ++v19 >= *(_DWORD *)(v13 + 16) )
      {
        v18 = 1;
        goto LABEL_14;
      }
    }
LABEL_16:
    v18 = 0;
  }
LABEL_17:
  if ( *(_DWORD *)(v13 + 32) )
  {
    v20 = *(_QWORD *)(v13 + 48);
    v21 = *(unsigned int *)(v20 + 64);
    if ( EapHostPeerGetMethods(&pEapMethodInfoArray, &ppEapError) )
      goto LABEL_35;
    if ( pEapMethodInfoArray.dwNumberOfMethods )
    {
      v12 = v20 + v21;
      v22 = 0;
      while ( pEapMethodInfoArray.pEapMethods[v22].eaptype.eapType.type != *(_BYTE *)(v20 + v21 + 4)
           || pEapMethodInfoArray.pEapMethods[v22].eaptype.eapType.dwVendorId != *(_DWORD *)(v12 + 8)
           || pEapMethodInfoArray.pEapMethods[v22].eaptype.eapType.dwVendorType != *(_DWORD *)(v12 + 12)
           || pEapMethodInfoArray.pEapMethods[v22].eaptype.dwAuthorId != *(_DWORD *)(v12 + 16) )
      {
        if ( ++v22 >= pEapMethodInfoArray.dwNumberOfMethods )
          goto LABEL_29;
      }
      eaptype = pEapMethodInfoArray.pEapMethods[v22].eaptype;
      valid = OneXIsValidEapTypeForMedia(&eaptype);
      v17 = 0;
      v16 = valid != 0 ? 0x43A1 : 0;
      if ( valid )
        goto LABEL_34;
    }
  }
  else
  {
    v17 = 0;
  }
LABEL_29:
  if ( v18 )
    v16 = 17311;
  if ( v17 )
  {
    v16 = 17312;
LABEL_34:
    CACSecurityPage::DisplayErrorMessage(this, v16, 0);
    goto LABEL_35;
  }
  if ( v16 )
    goto LABEL_34;
LABEL_35:
  wil::details::FreeEapMethodInfoArray((wil::details *)&pEapMethodInfoArray, (struct _EAP_METHOD_INFO_ARRAY *)v12);
  return this;
}

```

## disassembly

```asm
0x180006a34  push    rbx
0x180006a36  push    rbp
0x180006a37  push    rsi
0x180006a38  push    rdi
0x180006a39  push    r12
0x180006a3b  push    r14
0x180006a3d  push    r15
0x180006a3f  sub     rsp, 40h
0x180006a43  xor     r12d, r12d
0x180006a46  mov     [rcx+5Ch], edx
0x180006a49  mov     [rcx+8], r12
0x180006a4d  lea     rax, ??_7CACSecurityPage@@6B@; const CACSecurityPage::`vftable'
0x180006a54  mov     [rcx], rax
0x180006a57  lea     rdx, [rcx+30h]
0x180006a5b  mov     rax, [rsp+78h+ppEapError]
0x180006a63  mov     rsi, rcx
0x180006a66  mov     [rcx+10h], rax
0x180006a6a  mov     rax, [rsp+78h+arg_30]
0x180006a72  mov     [rcx+260h], r12
0x180006a79  mov     [rcx+268h], r12
0x180006a80  mov     [rcx+270h], r12
0x180006a87  mov     [rcx+18h], rax
0x180006a8b  mov     eax, [rsp+78h+arg_38]
0x180006a92  mov     [rcx+4DCh], eax
0x180006a98  mov     rax, [rsp+78h+arg_20]
0x180006aa0  mov     [rcx+4E0h], rax
0x180006aa7  mov     eax, [rsp+78h+arg_40]
0x180006aae  mov     [rcx+4E8h], eax
0x180006ab4  mov     rax, 3FF0000000000000h
0x180006abe  mov     [rcx+518h], rax
0x180006ac5  mov     [rcx+58h], r12d
0x180006ac9  mov     [rcx+4D0h], r8
0x180006ad0  mov     [rcx+4D8h], r12d
0x180006ad7  mov     [rcx+530h], r12
0x180006ade  mov     [rcx+538h], r12
0x180006ae5  mov     [rcx+20h], r12
0x180006ae9  mov     [rcx+540h], r12
0x180006af0  mov     [rcx+548h], r12
0x180006af7  mov     [rcx+40h], r12
0x180006afb  mov     [rcx+48h], r12
0x180006aff  mov     [rcx+50h], r12
0x180006b03  mov     [rcx+38h], r12d
0x180006b07  mov     [rcx+520h], r12d
0x180006b0e  mov     [rcx+28h], r9
0x180006b12  mov     rcx, r9
0x180006b15  call    cs:__imp_WpDuplicateProfile
0x180006b1b  lea     rcx, [rsi+278h]; void *
0x180006b22  xor     edx, edx; Val
0x180006b24  mov     r8d, 230h; Size
0x180006b2a  call    memset_0
0x180006b2f  mov     rax, [rsi+28h]
0x180006b33  xorps   xmm0, xmm0
0x180006b36  mov     r11, [rsi+18h]
0x180006b3a  mov     rdx, [rax+228h]
0x180006b41  mov     rax, [rdx+20h]
0x180006b45  mov     rcx, [rax+1A8h]
0x180006b4c  mov     [rsp+78h+ppEapError], r12
0x180006b54  movups  xmmword ptr [rsp+78h+pEapMethodInfoArray.dwNumberOfMethods], xmm0
0x180006b59  test    r11, r11
0x180006b5c  jz      loc_180006CB3
0x180006b62  mov     rax, [rdx+20h]
0x180006b66  mov     edx, [rax+1B0h]
0x180006b6c  test    edx, edx
0x180006b6e  jz      short loc_180006B7D
0x180006b70  cmp     [rax+1B4h], r12d
0x180006b77  jz      loc_180006CB3
0x180006b7d  test    rcx, rcx
0x180006b80  jz      loc_180006CB3
0x180006b86  mov     r9, [rcx+18h]
0x180006b8a  mov     ebx, r12d
0x180006b8d  mov     edi, 1
0x180006b92  test    r9, r9
0x180006b95  jz      short loc_180006BE1
0x180006b97  test    edx, edx
0x180006b99  jnz     short loc_180006BE1
0x180006b9b  mov     ebp, edi
0x180006b9d  mov     edx, r12d
0x180006ba0  cmp     [r11], r12d
0x180006ba3  jbe     short loc_180006BE4
0x180006ba5  mov     ebp, edi
0x180006ba7  cmp     [rcx+10h], r12d
0x180006bab  jbe     short loc_180006BD8
0x180006bad  mov     r10d, edx
0x180006bb0  mov     r8d, r12d
0x180006bb3  mov     ebp, [r11+r10*8+4]
0x180006bb8  mov     eax, r8d
0x180006bbb  cmp     ebp, [r9+rax*8]
0x180006bbf  jnz     short loc_180006BCD
0x180006bc1  mov     eax, [r9+rax*8+4]
0x180006bc6  cmp     [r11+r10*8+8], eax
0x180006bcb  jz      short loc_180006BE1
0x180006bcd  add     r8d, edi
0x180006bd0  cmp     r8d, [rcx+10h]
0x180006bd4  jb      short loc_180006BB8
0x180006bd6  mov     ebp, edi
0x180006bd8  add     edx, edi
0x180006bda  cmp     edx, [r11]
0x180006bdd  jb      short loc_180006BA5
0x180006bdf  jmp     short loc_180006BE4
0x180006be1  mov     ebp, r12d
0x180006be4  cmp     [rcx+20h], r12d
0x180006be8  jnz     short loc_180006BF2
0x180006bea  mov     edi, r12d
0x180006bed  jmp     loc_180006C8F
0x180006bf2  mov     r14, [rcx+30h]
0x180006bf6  lea     rdx, [rsp+78h+ppEapError]; ppEapError
0x180006bfe  lea     rcx, [rsp+78h+pEapMethodInfoArray]; pEapMethodInfoArray
0x180006c03  mov     r15d, [r14+40h]
0x180006c07  call    cs:__imp_EapHostPeerGetMethods
0x180006c0d  test    eax, eax
0x180006c0f  jnz     loc_180006CB3
0x180006c15  mov     r10d, [rsp+78h+pEapMethodInfoArray.dwNumberOfMethods]
0x180006c1a  test    r10d, r10d
0x180006c1d  jz      short loc_180006C8F
0x180006c1f  mov     r8, [rsp+78h+pEapMethodInfoArray.pEapMethods]
0x180006c24  lea     rdx, [r14+r15]
0x180006c28  mov     r11b, [rdx+4]
0x180006c2c  mov     r9d, r12d
0x180006c2f  mov     eax, r9d
0x180006c32  lea     rcx, [rax+rax*2]
0x180006c36  add     rcx, rcx
0x180006c39  cmp     [r8+rcx*8], r11b
0x180006c3d  jnz     short loc_180006C5D
0x180006c3f  mov     eax, [rdx+8]
0x180006c42  cmp     [r8+rcx*8+4], eax
0x180006c47  jnz     short loc_180006C5D
0x180006c49  mov     eax, [rdx+0Ch]
0x180006c4c  cmp     [r8+rcx*8+8], eax
0x180006c51  jnz     short loc_180006C5D
0x180006c53  mov     eax, [rdx+10h]
0x180006c56  cmp     [r8+rcx*8+0Ch], eax
0x180006c5b  jz      short loc_180006C67
0x180006c5d  add     r9d, edi
0x180006c60  cmp     r9d, r10d
0x180006c63  jb      short loc_180006C2F
0x180006c65  jmp     short loc_180006C8F
0x180006c67  movups  xmm0, xmmword ptr [r8+rcx*8]
0x180006c6c  lea     rcx, [rsp+78h+var_48]
0x180006c71  movdqu  [rsp+78h+var_48], xmm0
0x180006c77  call    OneXIsValidEapTypeForMedia
0x180006c7c  mov     ecx, eax
0x180006c7e  mov     edi, r12d
0x180006c81  neg     ecx
0x180006c83  sbb     ebx, ebx
0x180006c85  and     ebx, 43A1h
0x180006c8b  test    eax, eax
0x180006c8d  jnz     short loc_180006CA6
0x180006c8f  test    ebp, ebp
0x180006c91  mov     eax, 439Fh
0x180006c96  cmovnz  ebx, eax
0x180006c99  test    edi, edi
0x180006c9b  jz      short loc_180006CA2
0x180006c9d  lea     ebx, [rax+1]
0x180006ca0  jmp     short loc_180006CA6
0x180006ca2  test    ebx, ebx
0x180006ca4  jz      short loc_180006CB3
0x180006ca6  xor     r8d, r8d; unsigned int
0x180006ca9  mov     edx, ebx; unsigned int
0x180006cab  mov     rcx, rsi; this
0x180006cae  call    ?DisplayErrorMessage@CACSecurityPage@@AEAAXKK@Z; CACSecurityPage::DisplayErrorMessage(ulong,ulong)
0x180006cb3  lea     rcx, [rsp+78h+pEapMethodInfoArray]; this
0x180006cb8  call    ?FreeEapMethodInfoArray@details@wil@@YAXPEAU_EAP_METHOD_INFO_ARRAY@@@Z; wil::details::FreeEapMethodInfoArray(_EAP_METHOD_INFO_ARRAY *)
0x180006cbd  mov     rax, rsi
0x180006cc0  add     rsp, 40h
0x180006cc4  pop     r15
0x180006cc6  pop     r14
0x180006cc8  pop     r12
0x180006cca  pop     rdi
0x180006ccb  pop     rsi
0x180006ccc  pop     rbp
0x180006ccd  pop     rbx
0x180006cce  retn
```

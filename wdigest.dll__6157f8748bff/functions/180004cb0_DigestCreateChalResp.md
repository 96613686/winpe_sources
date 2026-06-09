# DigestCreateChalResp

- ea: `0x180004cb0`
- end: `0x180006194`
- name: `DigestCreateChalResp`
- size: `5348`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006260`
- `0x18002ea3c`

## callees

- `0x180004cb0`
- `0x1800061a0`
- `0x180006de0`
- `0x180007aa0`
- `0x180009770`
- `0x18000c4c0`
- `0x18000cb00`
- `0x18000d2f0`
- `0x18000eff0`
- `0x180011fec`
- `0x180012c5c`
- `0x180013304`
- `0x1800185b8`
- `0x1800189f8`
- `0x180018b18`
- `0x1800192a8`
- `0x180032ec8`
- `0x1800377bc`
- `0x180038010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180004fbb`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005d35`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005db0`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005e25`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005ea3`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005ebd`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005f1e`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180004fbb`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005d35`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005db0`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005e25`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005ea3`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005ebd`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180005f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005509`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005509`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005561`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005227`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000523e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005227`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000523e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056b1`
- `ntdll!RtlInitString` at `0x180004e11`
- `ntdll!RtlInitString` at `0x180004e11`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180005295`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000530e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180005295`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000530e`

## string_xrefs

- `0x180004f2a`: `digest-uri`
- `0x180005eee`: `,hashed-dirs="%hZ",service-name="%hZ",channel-binding="%hZ"`

## pseudocode

```c
__int64 __fastcall DigestCreateChalResp(__int64 a1, unsigned __int16 *a2, __int64 a3)
{
  int v4; // r13d
  char *v5; // rax
  char *v6; // rbx
  PVOID *v7; // rcx
  char *v8; // rax
  char *v9; // r14
  PVOID *v10; // rdi
  int v11; // eax
  const char *v12; // rdx
  int v13; // r12d
  LPCWCH *v14; // rcx
  UINT v15; // r15d
  int i; // r12d
  HLOCAL *v17; // r15
  HLOCAL *v18; // r8
  int v19; // r10d
  int v20; // r11d
  __int64 v21; // r9
  HLOCAL v22; // rcx
  bool v23; // zf
  const char *v24; // rax
  HLOCAL *v25; // r9
  __int64 v26; // rax
  size_t v27; // rsi
  HLOCAL v28; // rbx
  HLOCAL v29; // rbx
  HLOCAL v30; // rbx
  HLOCAL v31; // rbx
  PVOID *v33; // r8
  __int64 v34; // rdx
  DWORD v35; // edi
  int cbMultiByte; // r12d
  unsigned __int16 v37; // r12
  HLOCAL v38; // rax
  _BYTE *v39; // rdx
  char *v40; // r10
  unsigned __int16 v41; // r8
  unsigned __int16 v42; // r9
  char v43; // al
  void *Memory; // rax
  size_t v45; // r8
  HLOCAL v46; // rdx
  char *v47; // rax
  char *v48; // rax
  int v49; // eax
  int j; // r9d
  char v51; // dl
  __int64 v52; // rdx
  DWORD v53; // eax
  DWORD LastError; // eax
  __int64 v55; // rdx
  int v56; // eax
  int v57; // r8d
  int v58; // eax
  const char *v59; // r8
  int v60; // eax
  const char *v61; // r9
  _QWORD *v62; // rcx
  __int64 v63; // rax
  HLOCAL Src[2]; // [rsp+48h] [rbp-69h] BYREF
  int v65; // [rsp+58h] [rbp-59h] BYREF
  _QWORD v66[2]; // [rsp+60h] [rbp-51h] BYREF
  _STRING DestinationString; // [rsp+70h] [rbp-41h] BYREF
  HLOCAL hMem[2]; // [rsp+80h] [rbp-31h] BYREF
  HLOCAL lpMultiByteStr[2]; // [rsp+90h] [rbp-21h] BYREF
  _QWORD v70[2]; // [rsp+A0h] [rbp-11h] BYREF
  HLOCAL v71[2]; // [rsp+B0h] [rbp-1h] BYREF
  HLOCAL *v74; // [rsp+130h] [rbp+7Fh]
  int v75; // [rsp+130h] [rbp+7Fh]

  v4 = 0;
  v65 = 0;
  DestinationString = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v71 = 0;
  *(_OWORD *)lpMultiByteStr = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
  if ( g_NtDigestState != 1 )
  {
    v47 = (char *)LocalAlloc(0x40u, 0x3001u);
    v6 = v47;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_7;
    WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, 12289, v47);
LABEL_137:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v5 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)&g_LsaFunctions + 40LL))(12289);
  v6 = v5;
  if ( v5 )
    memset_0(v5, 0, 0x3001u);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, 12289, v6);
    goto LABEL_137;
  }
LABEL_7:
  if ( v6 )
  {
    if ( g_NtDigestState == 1 )
    {
      v8 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)&g_LsaFunctions + 40LL))(4097);
      v9 = v8;
      if ( v8 )
        memset_0(v8, 0, 0x1001u);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
LABEL_13:
        if ( !v9 )
        {
          i = -2146893056;
          if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
            goto LABEL_52;
          v52 = 152;
LABEL_182:
          WPP_SF_(v10[2], v52, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
LABEL_183:
          v10 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_52;
        }
        if ( *(_DWORD *)a1 == 4 || *(_DWORD *)a1 == 5 )
          v4 = 1;
        v11 = *(_DWORD *)(a1 + 12);
        switch ( v11 )
        {
          case 4:
            v12 = "auth-conf";
            break;
          case 3:
            v12 = "auth-int";
            break;
          case 2:
            v12 = "auth";
            break;
          default:
LABEL_19:
            v13 = *(_DWORD *)(a1 + 20);
            v14 = (LPCWCH *)a2;
            v15 = 65001;
            if ( v13 != 2 )
              v15 = 28591;
            if ( !a2 )
            {
              i = 0;
              if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
              {
                WPP_SF_(v10[2], 164, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
                v10 = (PVOID *)WPP_GLOBAL_Control;
              }
              v17 = (HLOCAL *)(a1 + 24);
              v18 = (HLOCAL *)(a1 + 40);
              v74 = (HLOCAL *)(a1 + 40);
              goto LABEL_24;
            }
            v33 = &WPP_GLOBAL_Control;
            if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
            {
              WPP_SF_(v10[2], 153, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
              v14 = (LPCWCH *)a2;
              v33 = &WPP_GLOBAL_Control;
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            v34 = *(unsigned __int16 *)v14;
            if ( !(_WORD)v34 )
            {
              v37 = (unsigned __int16)lpMultiByteStr[0];
              LOWORD(v75) = lpMultiByteStr[0];
LABEL_107:
              v38 = Src[1];
              v66[0] = Src[1];
              if ( Src[1] )
              {
                if ( g_NtDigestState == 1 )
                {
                  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x100) != 0 )
                    WPP_SF_q(v10[2], 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, Src[1]);
                  (*(void (__fastcall **)(_QWORD, __int64, PVOID *))(*(_QWORD *)&g_LsaFunctions + 48LL))(
                    v66[0],
                    v34,
                    v33);
                }
                else
                {
                  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x100) != 0 )
                  {
                    WPP_SF_q(v10[2], 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, Src[1]);
                    v38 = (HLOCAL)v66[0];
                  }
                  LocalFree(v38);
                }
                v10 = (PVOID *)WPP_GLOBAL_Control;
                LODWORD(Src[0]) = 0;
                Src[1] = 0;
              }
              if ( !v37 )
                goto LABEL_126;
              if ( v37 > 0x7FFFu )
              {
                i = -1073741811;
              }
              else
              {
                LOWORD(Src[0]) = 0;
                Src[1] = (HLOCAL)DigestAllocateMemory((unsigned __int16)(2 * v75 + 1));
                v39 = Src[1];
                if ( Src[1] )
                {
                  v40 = (char *)lpMultiByteStr[1];
                  v41 = 0;
                  WORD1(Src[0]) = 2 * v75 + 1;
                  v42 = 0;
                  for ( i = 0; v42 < (unsigned __int16)v75; ++v40 )
                  {
                    if ( v41 > 0xFFFDu )
                      break;
                    v43 = *v40;
                    if ( *v40 == 34 || v43 == 92 )
                    {
                      *v39++ = 92;
                      v43 = *v40;
                      v41 += 2;
                    }
                    else
                    {
                      ++v41;
                    }
                    *v39 = v43;
                    ++v42;
                    ++v39;
                  }
                  LOWORD(Src[0]) = v41;
                  v10 = (PVOID *)WPP_GLOBAL_Control;
                  if ( v42 < (unsigned __int16)v75 )
                    i = -1073741811;
                  goto LABEL_125;
                }
                v10 = (PVOID *)WPP_GLOBAL_Control;
                i = -2146893056;
                WORD1(Src[0]) = 0;
              }
              if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
              {
                WPP_SF_d(v10[2], 42, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, (unsigned int)i);
                v10 = (PVOID *)WPP_GLOBAL_Control;
              }
LABEL_125:
              if ( i < 0 )
              {
                if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
                {
                  WPP_SF_d(v10[2], 155, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids, (unsigned int)i);
                  v10 = (PVOID *)WPP_GLOBAL_Control;
                }
                goto LABEL_52;
              }
LABEL_126:
              *(_QWORD *)(a1 + 552) = 0;
              *(_DWORD *)(a1 + 544) = 0;
              if ( !Src[1] )
                goto LABEL_130;
              if ( LOWORD(Src[0]) == 0xFFFF )
              {
                i = -1073741811;
              }
              else
              {
                Memory = (void *)DigestAllocateMemory((unsigned int)LOWORD(Src[0]) + 1);
                *(_QWORD *)(a1 + 552) = Memory;
                if ( Memory )
                {
                  v45 = LOWORD(Src[0]);
                  v46 = Src[1];
                  *(_WORD *)(a1 + 544) = Src[0];
                  *(_WORD *)(a1 + 546) = v45 + 1;
                  memcpy_0(Memory, v46, v45);
                  *(_BYTE *)(LOWORD(Src[0]) + *(_QWORD *)(a1 + 552)) = 0;
LABEL_130:
                  if ( a1 == -24 )
                  {
                    v10 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        157,
                        &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
LABEL_172:
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    goto LABEL_173;
                  }
                  *(_OWORD *)(a1 + 24) = *(_OWORD *)(a1 + 544);
                  if ( *((_QWORD *)a2 + 3) )
                  {
                    i = EncodeUnicodeString(a2 + 8, v15, (__int64)v71, 0);
                    if ( i < 0 )
                    {
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                        goto LABEL_52;
                      v55 = 158;
                      goto LABEL_202;
                    }
                    v56 = BackslashEncodeString(v71, hMem);
                    i = v56;
                    if ( v56 < 0 )
                    {
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_52;
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        159,
                        &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids,
                        (unsigned int)v56);
                      goto LABEL_203;
                    }
                    i = StringDuplicate(a1 + 560, hMem);
                    if ( i < 0 )
                    {
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_52;
                      v55 = 160;
                      goto LABEL_202;
                    }
                    i = StringReference(a1 + 40, a1 + 560);
                    if ( i < 0 )
                    {
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_52;
                      v55 = 161;
                      goto LABEL_202;
                    }
                    v18 = hMem;
                    v74 = hMem;
                  }
                  else
                  {
                    v18 = (HLOCAL *)(a1 + 40);
                    v74 = (HLOCAL *)(a1 + 40);
                    v10 = (PVOID *)WPP_GLOBAL_Control;
                    i = 0;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                      goto LABEL_133;
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
                    v18 = (HLOCAL *)(a1 + 40);
                  }
                  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_133:
                  v17 = Src;
LABEL_24:
                  v19 = *(unsigned __int16 *)(a1 + 976);
                  v20 = *(unsigned __int16 *)(a1 + 88);
                  v21 = *(unsigned __int16 *)(a1 + 56)
                      + 384
                      + *(unsigned __int16 *)(a1 + 248)
                      + v20
                      + *(unsigned __int16 *)(a1 + 72)
                      + (unsigned __int16)_mm_cvtsi128_si32((__m128i)0LL)
                      + DestinationString.Length
                      + *(unsigned __int16 *)(a1 + 152)
                      + v19
                      + *(unsigned __int16 *)v17
                      + *(unsigned __int16 *)v18
                      + (unsigned int)*(unsigned __int16 *)(a1 + 200);
                  if ( (*(_WORD *)(a1 + 4) & 0x100) != 0 )
                    v21 = *(unsigned __int16 *)(a1 + 392)
                        + (_DWORD)v21
                        + *(unsigned __int16 *)(a1 + 376)
                        + (unsigned int)*(unsigned __int16 *)(a1 + 360);
                  if ( (unsigned int)v21 > 0x1000 )
                  {
                    i = -1073741789;
                    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
                      goto LABEL_52;
                    WPP_SF_d(v10[2], 165, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids, v21);
                    goto LABEL_203;
                  }
                  if ( (_WORD)v19 && (_WORD)v20 && *(_WORD *)(a1 + 72) )
                  {
                    if ( g_fParameter_DisableNameValidation )
                    {
LABEL_31:
                      v22 = v17[1];
                      v23 = *(_WORD *)v18 == 0;
                      v66[0] = 0x20000;
                      v24 = "digest-uri";
                      v66[1] = &word_18003B6BE;
                      v25 = (HLOCAL *)v66;
                      if ( v23 )
                      {
                        if ( v4 != 1 )
                          v24 = "uri";
                        if ( v22 )
                          v25 = v17;
                        sprintf_s(
                          v6,
                          0x3001u,
                          "username=\"%hZ\",realm=\"\",nonce=\"%hZ\",%s=\"%hZ\"",
                          v25,
                          a1 + 56,
                          v24,
                          a1 + 152);
                      }
                      else
                      {
                        if ( v4 != 1 )
                          v24 = "uri";
                        if ( v22 )
                          v25 = v17;
                        sprintf_s(
                          v6,
                          0x3001u,
                          "username=\"%hZ\",realm=\"%hZ\",nonce=\"%hZ\",%s=\"%hZ\"",
                          v25,
                          v18,
                          a1 + 56,
                          v24,
                          a1 + 152);
                      }
                      if ( *(_DWORD *)(a1 + 12) != 1 )
                      {
                        sprintf_s(v9, 0x1001u, ",cnonce=\"%hZ\",nc=%hZ", a1 + 72, a1 + 88);
                        _o_strcat_s(v6, 12289, v9);
                      }
                      if ( v4 == 1 )
                      {
                        sprintf_s(v9, 0x1001u, ",response=%hZ", a1 + 976);
                        goto LABEL_41;
                      }
                      v58 = *(_DWORD *)(a1 + 8);
                      switch ( v58 )
                      {
                        case 3:
                          sprintf_s(v9, 0x1001u, ",algorithm=MD5-sess,response=\"%hZ\"", a1 + 976);
                          goto LABEL_41;
                        case 2:
                          sprintf_s(v9, 0x1001u, ",algorithm=MD5,response=\"%hZ\"", a1 + 976);
                          goto LABEL_41;
                        case 1:
                          sprintf_s(v9, 0x1001u, ",response=\"%hZ\"", a1 + 976);
LABEL_41:
                          _o_strcat_s(v6, 12289, v9);
                          if ( DestinationString.Length )
                          {
                            if ( v4 == 1 || (v59 = ",qop=\"%hZ\"", (*(_BYTE *)(a1 + 4) & 0x20) == 0) )
                              v59 = ",qop=%hZ";
                            sprintf_s(v9, 0x1001u, v59, &DestinationString);
                            _o_strcat_s(v6, 12289, v9);
                          }
                          if ( *(_DWORD *)(a1 + 12) == 4 )
                          {
                            v60 = *(_DWORD *)(a1 + 16);
                            switch ( v60 )
                            {
                              case 4:
                                v61 = "rc4";
                                break;
                              case 5:
                                v61 = "rc4-56";
                                break;
                              case 3:
                                v61 = "rc4-40";
                                break;
                              case 1:
                                v61 = "3des";
                                break;
                              case 2:
                                v61 = "des";
                                break;
                              default:
                                goto LABEL_43;
                            }
                            sprintf_s(v9, 0x1001u, ",cipher=%s", v61);
                            _o_strcat_s(v6, 12289, v9);
                          }
LABEL_43:
                          if ( v4 )
                          {
                            if ( (*(_BYTE *)(a1 + 4) & 2) == 0 )
                              goto LABEL_45;
                            if ( *(_WORD *)(a1 + 200) )
                              sprintf_s(v9, 0x1001u, ",authzid=\"%hZ\"", a1 + 200);
                            else
                              sprintf_s(v9, 0x1001u, ",authzid=\"\"");
                          }
                          else
                          {
                            if ( !*(_WORD *)(a1 + 248) )
                              goto LABEL_45;
                            sprintf_s(v9, 0x1001u, ",opaque=\"%hZ\"", a1 + 248);
                          }
                          _o_strcat_s(v6, 12289, v9);
LABEL_45:
                          if ( *(_DWORD *)(a1 + 20) == 2 )
                            _o_strcat_s(v6, 12289, ",charset=utf-8");
                          if ( (*(_WORD *)(a1 + 4) & 0x100) != 0 )
                          {
                            v70[0] = 0x20000;
                            v23 = *(_WORD *)(a1 + 376) == 0;
                            v62 = v70;
                            v70[1] = &word_18003B6BE;
                            if ( !v23 )
                              v62 = (_QWORD *)(a1 + 376);
                            sprintf_s(
                              v9,
                              0x1001u,
                              ",hashed-dirs=\"%hZ\",service-name=\"%hZ\",channel-binding=\"%hZ\"",
                              a1 + 360,
                              v62,
                              a1 + 392);
                            _o_strcat_s(v6, 12289, v9);
                          }
                          v26 = -1;
                          do
                            ++v26;
                          while ( v6[v26] );
                          v27 = (unsigned __int16)v26;
                          if ( (unsigned __int16)v26 > 0x1000u )
                          {
                            i = -1073741789;
                            v10 = (PVOID *)WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                            {
                              goto LABEL_52;
                            }
                            v52 = 170;
                            goto LABEL_182;
                          }
                          if ( *(_DWORD *)a3 )
                          {
                            if ( (unsigned int)(unsigned __int16)v26 > *(_DWORD *)a3 )
                            {
                              i = -1073741789;
                              v10 = (PVOID *)WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                              {
                                goto LABEL_52;
                              }
                              WPP_SF_dd(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                172,
                                &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids,
                                (unsigned __int16)v26,
                                *(_DWORD *)a3);
                              goto LABEL_183;
                            }
                          }
                          else
                          {
                            v63 = DigestAllocateMemory((unsigned __int16)v26);
                            *(_QWORD *)(a3 + 8) = v63;
                            if ( !v63 )
                            {
                              i = -2146893056;
                              v10 = (PVOID *)WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                              {
                                goto LABEL_52;
                              }
                              v52 = 171;
                              goto LABEL_182;
                            }
                            *(_DWORD *)a3 = v27;
                          }
                          memcpy_0(*(void **)(a3 + 8), v6, v27);
                          *(_DWORD *)(a3 + 4) = 2;
                          *(_DWORD *)a3 = v27;
                          v10 = (PVOID *)WPP_GLOBAL_Control;
                          goto LABEL_52;
                      }
                      i = -1073741811;
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_52;
                      v55 = 169;
                      goto LABEL_202;
                    }
                    if ( *(_WORD *)v17 )
                    {
                      if ( !(unsigned int)ValidateDigestName(v17, &v65) )
                      {
                        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
                        {
                          WPP_SF_aZd((unsigned int)v10[2], 167, v57, (_DWORD)v17, v65);
                          v10 = (PVOID *)WPP_GLOBAL_Control;
                        }
LABEL_173:
                        i = -1073741811;
LABEL_52:
                        if ( g_NtDigestState == 1 )
                        {
                          if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x100) != 0 )
                            WPP_SF_q(v10[2], 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v6);
                          (*(void (__fastcall **)(char *))(*(_QWORD *)&g_LsaFunctions + 48LL))(v6);
                        }
                        else
                        {
                          if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x100) != 0 )
                            WPP_SF_q(v10[2], 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v6);
                          LocalFree(v6);
                        }
                        if ( v9 )
                          DigestFreeMemory(v9);
                        goto LABEL_59;
                      }
                      v18 = v74;
                    }
                    v49 = *(unsigned __int16 *)v18;
                    if ( (_WORD)v49 )
                    {
                      for ( j = 0; j < v49; ++j )
                      {
                        v51 = *((_BYTE *)v18[1] + j);
                        if ( v51 > -1 && (unsigned __int8)(v51 - 32) > 0x5Eu )
                        {
                          if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
                          {
                            WPP_SF_aZd((unsigned int)v10[2], 168, (_DWORD)v18, (_DWORD)v18, j);
                            goto LABEL_172;
                          }
                          goto LABEL_173;
                        }
                        v49 = *(unsigned __int16 *)v18;
                      }
                    }
                    goto LABEL_31;
                  }
                  i = -1073741811;
                  if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
                    goto LABEL_52;
                  v55 = 166;
LABEL_202:
                  WPP_SF_(v10[2], v55, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
LABEL_203:
                  v10 = (PVOID *)WPP_GLOBAL_Control;
                  goto LABEL_52;
                }
                i = -2146893056;
                v10 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                  goto LABEL_52;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
LABEL_214:
                  if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
                    goto LABEL_52;
                  v55 = 156;
                  goto LABEL_202;
                }
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
              }
              v10 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_214;
            }
            v35 = 1024;
            if ( v13 == 2 )
              v35 = 0;
            cbMultiByte = WideCharToMultiByte(v15, v35, v14[1], (unsigned int)v34 >> 1, 0, 0, 0, 0);
            if ( cbMultiByte > 0 )
            {
              if ( (_WORD)cbMultiByte == 0xFFFF )
              {
                i = -1073741811;
              }
              else
              {
                lpMultiByteStr[1] = (HLOCAL)DigestAllocateMemory((unsigned __int16)(cbMultiByte + 1));
                if ( lpMultiByteStr[1] )
                {
                  WORD1(lpMultiByteStr[0]) = cbMultiByte + 1;
                  v75 = WideCharToMultiByte(
                          v15,
                          v35,
                          *((LPCWCH *)a2 + 1),
                          *a2 >> 1,
                          (LPSTR)lpMultiByteStr[1],
                          cbMultiByte,
                          0,
                          0);
                  v37 = v75;
                  if ( v75 )
                  {
                    v10 = (PVOID *)WPP_GLOBAL_Control;
                    v33 = &WPP_GLOBAL_Control;
                    goto LABEL_107;
                  }
                  i = -1073741470;
                  LastError = GetLastError();
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      27,
                      WPP_5a1eec0057703498b5d13460810c8614_Traceguids,
                      LastError);
                  StringFree(lpMultiByteStr);
                  goto LABEL_198;
                }
                i = -2146893056;
              }
              v10 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                goto LABEL_52;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_199;
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
              goto LABEL_198;
            }
            i = -1073741470;
            v53 = GetLastError();
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              goto LABEL_52;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_199;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v53);
LABEL_198:
            v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_199:
            if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 2) == 0 )
              goto LABEL_52;
            v55 = 154;
            goto LABEL_202;
        }
        RtlInitString(&DestinationString, v12);
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_19;
      }
      WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, 4097, v9);
    }
    else
    {
      v48 = (char *)LocalAlloc(0x40u, 0x1001u);
      v9 = v48;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        goto LABEL_13;
      WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, 4097, v48);
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  i = -2146893056;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
  {
    WPP_SF_(v7[2], 151, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
LABEL_59:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v28 = hMem[1];
  if ( hMem[1] )
  {
    if ( g_NtDigestState == 1 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 )
        WPP_SF_q(v7[2], 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, hMem[1]);
      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)&g_LsaFunctions + 48LL))(v28);
    }
    else
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 )
        WPP_SF_q(v7[2], 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, hMem[1]);
      LocalFree(v28);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    LODWORD(hMem[0]) = 0;
    hMem[1] = 0;
  }
  v29 = Src[1];
  if ( Src[1] )
  {
    if ( g_NtDigestState == 1 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 )
        WPP_SF_q(v7[2], 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, Src[1]);
      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)&g_LsaFunctions + 48LL))(v29);
    }
    else
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 )
        WPP_SF_q(v7[2], 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, Src[1]);
      LocalFree(v29);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    LODWORD(Src[0]) = 0;
    Src[1] = 0;
  }
  v30 = v71[1];
  if ( v71[1] )
  {
    if ( g_NtDigestState == 1 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 )
        WPP_SF_q(v7[2], 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v71[1]);
      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)&g_LsaFunctions + 48LL))(v30);
    }
    else
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 )
        WPP_SF_q(v7[2], 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v71[1]);
      LocalFree(v30);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v31 = lpMultiByteStr[1];
  if ( lpMultiByteStr[1] )
  {
    if ( g_NtDigestState == 1 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 )
        WPP_SF_q(v7[2], 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, lpMultiByteStr[1]);
      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)&g_LsaFunctions + 48LL))(v31);
    }
    else
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x100) != 0 )
        WPP_SF_q(v7[2], 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, lpMultiByteStr[1]);
      LocalFree(v31);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && *((char *)v7 + 28) < 0 )
    WPP_SF_d(v7[2], 173, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids, (unsigned int)i);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180004cb0  mov     rax, rsp
0x180004cb3  mov     [rax+18h], r8
0x180004cb7  mov     [rax+10h], rdx
0x180004cbb  push    rbp
0x180004cbc  lea     rbp, [rax-5Fh]
0x180004cc0  sub     rsp, 100h
0x180004cc7  mov     [rax+8], rbx
0x180004ccb  xorps   xmm0, xmm0
0x180004cce  mov     [rax-10h], rsi
0x180004cd2  xorps   xmm1, xmm1
0x180004cd5  mov     [rax-18h], rdi
0x180004cd9  mov     rsi, rcx
0x180004cdc  mov     [rax-28h], r13
0x180004ce0  xor     r13d, r13d
0x180004ce3  mov     [rax-38h], r15
0x180004ce7  movaps  xmmword ptr [rax-48h], xmm6
0x180004ceb  xorps   xmm6, xmm6
0x180004cee  mov     [rbp+57h+var_B0], r13d
0x180004cf2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180004cf6  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180004cfa  movups  xmmword ptr [rbp+57h+Src], xmm1
0x180004cfe  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180004d02  movups  xmmword ptr [rbp+57h+var_78], xmm1
0x180004d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d0d  lea     r15, WPP_GLOBAL_Control
0x180004d14  cmp     rcx, r15
0x180004d17  jnz     loc_18000560E
0x180004d1d  cmp     cs:g_NtDigestState, 1
0x180004d24  mov     edi, 100h
0x180004d29  jnz     loc_1800054FF
0x180004d2f  mov     rax, cs:g_LsaFunctions
0x180004d36  mov     ecx, 3001h
0x180004d3b  mov     rax, [rax+28h]
0x180004d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d44  mov     rbx, rax
0x180004d47  test    rax, rax
0x180004d4a  jz      short loc_180004D5C
0x180004d4c  xor     edx, edx; Val
0x180004d4e  mov     r8d, 3001h; Size
0x180004d54  mov     rcx, rax; void *
0x180004d57  call    memset_0
0x180004d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d63  cmp     rcx, r15
0x180004d66  jz      short loc_180004D71
0x180004d68  test    [rcx+1Ch], edi
0x180004d6b  jnz     loc_180005775
0x180004d71  mov     [rsp+100h+var_18], r12
0x180004d79  test    rbx, rbx
0x180004d7c  jz      loc_180005784
0x180004d82  cmp     cs:g_NtDigestState, 1
0x180004d89  mov     [rsp+100h+var_28], r14
0x180004d91  jnz     loc_180005557
0x180004d97  mov     rax, cs:g_LsaFunctions
0x180004d9e  mov     ecx, 1001h
0x180004da3  mov     rax, [rax+28h]
0x180004da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dac  mov     r14, rax
0x180004daf  test    rax, rax
0x180004db2  jz      short loc_180004DC4
0x180004db4  xor     edx, edx; Val
0x180004db6  mov     r8d, 1001h; Size
0x180004dbc  mov     rcx, rax; void *
0x180004dbf  call    memset_0
0x180004dc4  mov     rdi, cs:WPP_GLOBAL_Control
0x180004dcb  cmp     rdi, r15
0x180004dce  jz      short loc_180004DDD
0x180004dd0  test    dword ptr [rdi+1Ch], 100h
0x180004dd7  jnz     loc_1800057B7
0x180004ddd  test    r14, r14
0x180004de0  jz      loc_1800057C6
0x180004de6  mov     eax, [rsi]
0x180004de8  cmp     eax, 4
0x180004deb  jz      loc_180005825
0x180004df1  cmp     eax, 5
0x180004df4  jz      loc_180005825
0x180004dfa  mov     eax, [rsi+0Ch]
0x180004dfd  cmp     eax, 4
0x180004e00  jnz     loc_180005830
0x180004e06  lea     rdx, SourceString; "auth-conf"
0x180004e0d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180004e11  call    cs:__imp_RtlInitString
0x180004e17  mov     rdi, cs:WPP_GLOBAL_Control
0x180004e1e  mov     r12d, [rsi+14h]
0x180004e22  mov     eax, 6FAFh
0x180004e27  mov     rcx, [rbp+57h+arg_8]
0x180004e2b  cmp     r12d, 2
0x180004e2f  mov     r15d, 0FDE9h
0x180004e35  cmovnz  r15d, eax
0x180004e39  test    rcx, rcx
0x180004e3c  jnz     loc_180005249
0x180004e42  xor     r12d, r12d
0x180004e45  lea     rax, WPP_GLOBAL_Control
0x180004e4c  cmp     rdi, rax
0x180004e4f  jnz     loc_180005BF1
0x180004e55  lea     r15, [rsi+18h]
0x180004e59  lea     r8, [r15+10h]
0x180004e5d  mov     [rbp+57h+arg_18], r8
0x180004e61  movzx   eax, word ptr [rsi+98h]
0x180004e68  movzx   r9d, word ptr [rsi+48h]
0x180004e6d  movzx   edx, word ptr [r15]
0x180004e71  movzx   r10d, word ptr [rsi+3D0h]
0x180004e79  movzx   r11d, word ptr [rsi+58h]
0x180004e7e  add     edx, r10d
0x180004e81  add     edx, eax
0x180004e83  movzx   eax, [rbp+57h+DestinationString.Length]
0x180004e87  add     edx, eax
0x180004e89  movd    eax, xmm6
0x180004e8d  movzx   ecx, ax
0x180004e90  movzx   eax, word ptr [rsi+0F8h]
0x180004e97  add     edx, ecx
0x180004e99  add     edx, r9d
0x180004e9c  movzx   r9d, word ptr [rsi+0C8h]
0x180004ea4  add     edx, r11d
0x180004ea7  add     edx, eax
0x180004ea9  movzx   eax, word ptr [r8]
0x180004ead  add     r9d, eax
0x180004eb0  movzx   eax, word ptr [rsi+38h]
0x180004eb4  add     eax, 180h
0x180004eb9  add     r9d, edx
0x180004ebc  add     r9d, eax
0x180004ebf  mov     eax, 100h
0x180004ec4  test    [rsi+4], ax
0x180004ec8  jnz     loc_180005C1C
0x180004ece  cmp     r9d, 1000h
0x180004ed5  ja      loc_180005C3F
0x180004edb  test    r10w, r10w
0x180004edf  jz      loc_180006013
0x180004ee5  test    r11w, r11w
0x180004ee9  jz      loc_180006013
0x180004eef  movzx   eax, word ptr [rsi+48h]
0x180004ef3  test    ax, ax
0x180004ef6  jz      loc_180006013
0x180004efc  cmp     cs:g_fParameter_DisableNameValidation, 0
0x180004f03  jz      loc_180005C64
0x180004f09  movzx   eax, word ptr [r8]
0x180004f0d  lea     rdi, word_18003B6BE
0x180004f14  mov     rcx, [r15+8]
0x180004f18  lea     rdx, aUri; "uri"
0x180004f1f  test    ax, ax
0x180004f22  mov     [rbp+57h+var_A8], 20000h
0x180004f2a  lea     rax, aDigestUri; "digest-uri"
0x180004f31  mov     [rbp+57h+var_A0], rdi
0x180004f35  lea     r9, [rbp+57h+var_A8]
0x180004f39  jz      loc_180005CC7
0x180004f3f  cmp     r13d, 1
0x180004f43  cmovnz  rax, rdx
0x180004f47  test    rcx, rcx
0x180004f4a  lea     rcx, [rsi+98h]
0x180004f51  mov     edx, 3001h; BufferCount
0x180004f56  mov     [rsp+38h], rcx
0x180004f5b  cmovnz  r9, r15
0x180004f5f  mov     [rsp+100h+lpDefaultChar], rax
0x180004f64  mov     rcx, rbx; Buffer
0x180004f67  lea     rax, [rsi+38h]
0x180004f6b  mov     qword ptr [rsp+100h+cbMultiByte], rax
0x180004f70  mov     [rsp+100h+lpMultiByteStr], r8
0x180004f75  lea     r8, Format; "username=\"%hZ\",realm=\"%hZ\",nonce=\""...
0x180004f7c  call    sprintf_s
0x180004f81  cmp     dword ptr [rsi+0Ch], 1
0x180004f85  jnz     loc_180005D09
0x180004f8b  cmp     r13d, 1
0x180004f8f  jnz     loc_180005D40
0x180004f95  lea     r8, aResponseHz; ",response=%hZ"
0x180004f9c  lea     r9, [rsi+3D0h]
0x180004fa3  mov     edx, 1001h; BufferCount
0x180004fa8  mov     rcx, r14; Buffer
0x180004fab  call    sprintf_s
0x180004fb0  mov     r8, r14
0x180004fb3  mov     edx, 3001h
0x180004fb8  mov     rcx, rbx
0x180004fbb  call    cs:__imp__o_strcat_s
0x180004fc1  cmp     [rbp+57h+DestinationString.Length], 0
0x180004fc6  jnz     loc_180005D7A
0x180004fcc  cmp     dword ptr [rsi+0Ch], 4
0x180004fd0  jz      loc_180005DBB
0x180004fd6  test    r13d, r13d
0x180004fd9  jz      loc_180005E30
0x180004fdf  cmp     r13d, 1
0x180004fe3  jz      loc_180005E5B
0x180004fe9  cmp     dword ptr [rsi+14h], 2
0x180004fed  jz      loc_180005EAE
0x180004ff3  mov     ecx, 100h
0x180004ff8  xor     r13d, r13d
0x180004ffb  mov     r15d, 2
0x180005001  test    [rsi+4], cx
0x180005005  jnz     loc_180005EC8
0x18000500b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005012  inc     rax
0x180005015  cmp     byte ptr [rbx+rax], 0
0x180005019  jnz     short loc_180005012
0x18000501b  movzx   esi, ax
0x18000501e  cmp     esi, 1000h
0x180005024  jbe     loc_180005F42
0x18000502a  mov     r12d, 0C0000023h
0x180005030  mov     rdi, cs:WPP_GLOBAL_Control
0x180005037  lea     r15, WPP_GLOBAL_Control
0x18000503e  cmp     rdi, r15
0x180005041  jnz     loc_180005F2E
0x180005047  cmp     cs:g_NtDigestState, 1
0x18000504e  jnz     loc_1800055B3
0x180005054  cmp     rdi, r15
0x180005057  jz      short loc_180005062
0x180005059  test    [rdi+1Ch], ecx
0x18000505c  jnz     loc_180006038
0x180005062  mov     rax, cs:g_LsaFunctions
0x180005069  mov     rcx, rbx
0x18000506c  mov     rax, [rax+30h]
0x180005070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005075  test    r14, r14
0x180005078  jnz     loc_18000607B
0x18000507e  mov     r14, [rsp+100h+var_28]
0x180005086  mov     edi, 100h
0x18000508b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005092  mov     rbx, [rbp+57h+hMem+8]
0x180005096  movaps  xmm6, [rsp+100h+var_48+8]
0x18000509e  mov     rsi, [rsp+0F8h]
0x1800050a6  test    rbx, rbx
0x1800050a9  jz      short loc_1800050EB
0x1800050ab  cmp     cs:g_NtDigestState, 1
0x1800050b2  jnz     loc_1800051ED
0x1800050b8  cmp     rcx, r15
0x1800050bb  jz      short loc_1800050C6
0x1800050bd  test    [rcx+1Ch], edi
0x1800050c0  jnz     loc_180006088
0x1800050c6  mov     rax, cs:g_LsaFunctions
0x1800050cd  mov     rcx, rbx
0x1800050d0  mov     rax, [rax+30h]
0x1800050d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050e0  mov     dword ptr [rbp+57h+hMem], 0
0x1800050e7  mov     [rbp+57h+hMem+8], r13
0x1800050eb  mov     rbx, [rbp+57h+Src+8]
0x1800050ef  test    rbx, rbx
0x1800050f2  jz      short loc_180005134
0x1800050f4  cmp     cs:g_NtDigestState, 1
0x1800050fb  jnz     loc_180005204
0x180005101  cmp     rcx, r15
0x180005104  jz      short loc_18000510F
0x180005106  test    [rcx+1Ch], edi
0x180005109  jnz     loc_1800060CB
0x18000510f  mov     rax, cs:g_LsaFunctions
0x180005116  mov     rcx, rbx
0x180005119  mov     rax, [rax+30h]
0x18000511d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005122  mov     rcx, cs:WPP_GLOBAL_Control
0x180005129  mov     dword ptr [rbp+57h+Src], 0
0x180005130  mov     [rbp+57h+Src+8], r13
0x180005134  mov     rbx, [rbp+57h+var_58+8]
0x180005138  mov     r13, [rsp+100h+var_20]
0x180005140  test    rbx, rbx
0x180005143  jz      short loc_18000517A
0x180005145  cmp     cs:g_NtDigestState, 1
0x18000514c  jnz     loc_18000521B
0x180005152  cmp     rcx, r15
0x180005155  jz      short loc_180005160
0x180005157  test    [rcx+1Ch], edi
0x18000515a  jnz     loc_18000610E
0x180005160  mov     rax, cs:g_LsaFunctions
0x180005167  mov     rcx, rbx
0x18000516a  mov     rax, [rax+30h]
0x18000516e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005173  mov     rcx, cs:WPP_GLOBAL_Control
0x18000517a  mov     rbx, [rbp+57h+var_78+8]
0x18000517e  test    rbx, rbx
0x180005181  jz      short loc_1800051B8
0x180005183  cmp     cs:g_NtDigestState, 1
0x18000518a  jnz     loc_180005232
0x180005190  cmp     rcx, r15
0x180005193  jz      short loc_18000519E
0x180005195  test    [rcx+1Ch], edi
0x180005198  jnz     loc_180006151
0x18000519e  mov     rax, cs:g_LsaFunctions
0x1800051a5  mov     rcx, rbx
0x1800051a8  mov     rax, [rax+30h]
0x1800051ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051b8  mov     rdi, [rsp+100h+var_10]
0x1800051c0  mov     rbx, [rsp+100h+arg_0]
0x1800051c8  cmp     rcx, r15
0x1800051cb  mov     r15, [rsp+100h+var_30]
0x1800051d3  jnz     loc_180005632
0x1800051d9  mov     eax, r12d
0x1800051dc  mov     r12, [rsp+100h+var_18]
0x1800051e4  add     rsp, 100h
0x1800051eb  pop     rbp
0x1800051ec  retn
0x1800051ed  cmp     rcx, r15
0x1800051f0  jnz     loc_1800060A5
0x1800051f6  mov     rcx, rbx; hMem
0x1800051f9  call    cs:__imp_LocalFree
0x1800051ff  jmp     loc_1800050D9
0x180005204  cmp     rcx, r15
0x180005207  jnz     loc_1800060E8
0x18000520d  mov     rcx, rbx; hMem
0x180005210  call    cs:__imp_LocalFree
0x180005216  jmp     loc_180005122
0x18000521b  cmp     rcx, r15
0x18000521e  jnz     loc_18000612B
0x180005224  mov     rcx, rbx; hMem
0x180005227  call    cs:__imp_LocalFree
  ... truncated ...
```

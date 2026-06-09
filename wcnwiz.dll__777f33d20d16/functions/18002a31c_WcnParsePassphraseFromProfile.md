# WcnParsePassphraseFromProfile

- ea: `0x18002a31c`
- end: `0x18002a9aa`
- name: `WcnParsePassphraseFromProfile`
- size: `1678`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800296a4`

## callees

- `0x180002981`
- `0x180003abc`
- `0x18000d630`
- `0x18000e044`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001044c`
- `0x18002a31c`
- `0x18002de1c`
- `0x18002f804`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a84e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a84e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a858`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002a55f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002a55f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a68c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002a68c`
- `KERNEL32!GlobalFree` at `0x18002a598`
- `KERNEL32!GlobalFree` at `0x18002a598`
- `KERNEL32!GlobalAlloc` at `0x18002a4f5`
- `KERNEL32!GlobalAlloc` at `0x18002a4f5`
- `XmlLite!CreateXmlReader` at `0x18002a474`
- `XmlLite!CreateXmlReader` at `0x18002a474`

## string_xrefs

- `0x18002a797`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x18002a38b`: `wszWlanXmlProfile`
- `0x18002a7aa`: `http://www.microsoft.com/networking/WLANAP/profile/v1`

## pseudocode

```c
__int64 __fastcall WcnParsePassphraseFromProfile(unsigned __int16 *a1, __int64 a2)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  const char *v8; // r9
  const char *v10; // rax
  __int64 v11; // r10
  HRESULT v12; // eax
  signed int v13; // ebx
  _BYTE *v14; // r10
  __int64 v15; // rdx
  SIZE_T v16; // rbx
  HGLOBAL v17; // rax
  void *v18; // rdi
  const char *v19; // rax
  __int64 v20; // r10
  __int64 v21; // rdx
  HRESULT v22; // eax
  char v23; // r15
  int v24; // esi
  const wchar_t *v25; // rdi
  int v26; // eax
  unsigned int v27; // eax
  const wchar_t *v28; // rdi
  wchar_t *v29; // rdi
  unsigned int LastError; // ebx
  unsigned int v31; // eax
  __int64 v32; // r10
  unsigned int v33; // eax
  __int64 v34; // r10
  LPSTREAM ppstm; // [rsp+40h] [rbp-10h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-8h] BYREF
  int v37; // [rsp+90h] [rbp+40h] BYREF
  void *ppvObject; // [rsp+A0h] [rbp+50h] BYREF
  LPCWCH lpWideCharStr; // [rsp+A8h] [rbp+58h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 37, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 2u )
      return 2147500035LL;
    v7 = 38;
    v8 = "wszWlanXmlProfile";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v4 + 2), v7, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v8);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 2u )
      return 2147500035LL;
    v7 = 39;
    v8 = "pPassphrase";
    goto LABEL_12;
  }
  lpWideCharStr = 0;
  ppvObject = 0;
  ppstm = 0;
  v37 = 0;
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 6u )
  {
    v10 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 40, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v10);
  }
  v12 = StringCchLengthW(a1, 0xA00000u, (unsigned __int64 *)&lpWideCharStr);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v12 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v16 = 2LL * (_QWORD)lpWideCharStr + 2;
        v17 = GlobalAlloc(0, v16);
        v18 = v17;
        if ( v17 )
        {
          memcpy_0(v17, a1, v16);
          v22 = CreateStreamOnHGlobal(v18, 1, &ppstm);
          v13 = v22;
          if ( v22 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids,
                (unsigned int)v22);
            GlobalFree(v18);
            goto LABEL_97;
          }
          v12 = (*(__int64 (__fastcall **)(void *, LPSTREAM))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
          v13 = v12;
          if ( v12 >= 0 )
          {
            v23 = 0;
            v24 = 0;
            while ( 1 )
            {
              do
              {
                while ( 1 )
                {
                  while ( 1 )
                  {
                    while ( 1 )
                    {
                      while ( 1 )
                      {
                        if ( (*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(
                               ppvObject,
                               &v37) )
                        {
                          if ( v23 )
                          {
                            *(_BYTE *)a2 = 1;
                            goto LABEL_97;
                          }
                          v13 = -2147023728;
                          v14 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                            goto LABEL_102;
                          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v19 = GetIndent(0);
                            v21 = 55;
                            goto LABEL_34;
                          }
                          goto LABEL_98;
                        }
                        if ( v37 != 1 )
                          break;
                        lpWideCharStr = 0;
                        String1 = 0;
                        v12 = (*(__int64 (__fastcall **)(void *, LPCWCH *, _QWORD))(*(_QWORD *)ppvObject + 104LL))(
                                ppvObject,
                                &lpWideCharStr,
                                0);
                        v13 = v12;
                        if ( v12 < 0 )
                        {
                          v14 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                            goto LABEL_102;
                          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v15 = 49;
                            goto LABEL_21;
                          }
                          goto LABEL_98;
                        }
                        v24 = 0;
                        v28 = lpWideCharStr;
                        if ( lpWideCharStr
                          && (!wcscmp_0(lpWideCharStr, L"http://www.microsoft.com/networking/WLAN/profile/v1")
                           || !wcscmp_0(v28, L"http://www.microsoft.com/networking/WLANAP/profile/v1")) )
                        {
                          v12 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                                  ppvObject,
                                  &String1,
                                  0);
                          v13 = v12;
                          if ( v12 < 0 )
                          {
                            v14 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                              goto LABEL_102;
                            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              v15 = 50;
                              goto LABEL_21;
                            }
                            goto LABEL_98;
                          }
                          v29 = String1;
                          if ( String1 )
                          {
                            if ( !wcscmp_0(String1, L"keyType") )
                            {
                              v24 = 1;
                            }
                            else if ( !wcscmp_0(v29, L"protected") )
                            {
                              v24 = 2;
                            }
                            else if ( !wcscmp_0(v29, L"keyMaterial") )
                            {
                              v24 = 3;
                            }
                          }
                        }
                      }
                      if ( v37 == 3 )
                      {
                        lpWideCharStr = 0;
                        v12 = (*(__int64 (__fastcall **)(void *, LPCWCH *, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                                ppvObject,
                                &lpWideCharStr,
                                0);
                        v13 = v12;
                        if ( v12 < 0 )
                        {
                          v14 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                            goto LABEL_102;
                          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v15 = 51;
                            goto LABEL_21;
                          }
                          goto LABEL_98;
                        }
                        v25 = lpWideCharStr;
                        if ( lpWideCharStr )
                          break;
                      }
                    }
                    if ( v24 != 1 )
                      break;
                    if ( wcscmp_0(L"passPhrase", lpWideCharStr) && wcscmp_0(L"networkKey", v25) )
                    {
                      v13 = -2147024846;
                      v14 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                        goto LABEL_102;
                      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v27 = (unsigned int)GetIndent(0);
                        WPP_SF_sS(
                          *(_QWORD *)(v32 + 16),
                          52,
                          (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids,
                          v27,
                          (__int64)v25);
                        goto LABEL_97;
                      }
                      goto LABEL_98;
                    }
                  }
                  if ( v24 != 2 )
                    break;
                  if ( wcscmp_0(L"false", lpWideCharStr) )
                  {
                    v13 = -2147024846;
                    v14 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                      goto LABEL_102;
                    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v19 = GetIndent(0);
                      v21 = 53;
                      goto LABEL_34;
                    }
                    goto LABEL_98;
                  }
                }
              }
              while ( v24 != 3 );
              v26 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, (LPSTR)(a2 + 16), 65, 0, 0);
              if ( !v26 )
                break;
              *(_QWORD *)(a2 + 8) = v26 - 1LL;
              v23 = 1;
            }
            if ( (int)GetLastError() > 0 )
              LastError = (unsigned __int16)GetLastError() | 0x80070000;
            else
              LastError = GetLastError();
            v13 = LastError | 0x80000000;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_102;
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_98;
            v31 = (unsigned int)GetIndent(0);
            WPP_SF_sS(
              *(_QWORD *)(v32 + 16),
              54,
              (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids,
              v31,
              (__int64)lpWideCharStr);
            goto LABEL_97;
          }
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = 48;
              goto LABEL_21;
            }
            goto LABEL_98;
          }
        }
        else
        {
          v13 = -2147024882;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = GetIndent(0);
              v21 = 46;
LABEL_34:
              WPP_SF_s(*(_QWORD *)(v20 + 16), v21, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v19);
              goto LABEL_97;
            }
            goto LABEL_98;
          }
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = 45;
            goto LABEL_21;
          }
          goto LABEL_98;
        }
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 44;
          goto LABEL_21;
        }
LABEL_98:
        if ( v14 != (_BYTE *)&WPP_GLOBAL_Control && (v13 < 0 || v14[25] >= 6u) )
        {
          v33 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v34 + 16), 56, (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v33, v13);
        }
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 43;
LABEL_21:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, (unsigned int)v12);
LABEL_97:
        v14 = WPP_GLOBAL_Control;
        goto LABEL_98;
      }
      goto LABEL_98;
    }
  }
LABEL_102:
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(&ppstm);
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(&ppvObject);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002a31c  push    rbp
0x18002a31e  push    rbx
0x18002a31f  push    rsi
0x18002a320  push    rdi
0x18002a321  push    r13
0x18002a323  push    r14
0x18002a325  push    r15
0x18002a327  mov     rbp, rsp
0x18002a32a  sub     rsp, 50h
0x18002a32e  mov     r14, rdx
0x18002a331  mov     rsi, rcx
0x18002a334  lea     r13, WPP_GLOBAL_Control
0x18002a33b  mov     r10, cs:WPP_GLOBAL_Control
0x18002a342  cmp     r10, r13
0x18002a345  jz      short loc_18002A377
0x18002a347  cmp     byte ptr [r10+19h], 6
0x18002a34c  jb      short loc_18002A377
0x18002a34e  mov     ecx, 1; int
0x18002a353  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a358  mov     edx, 25h ; '%'
0x18002a35d  mov     r9, rax
0x18002a360  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a367  mov     rcx, [r10+10h]
0x18002a36b  call    WPP_SF_s
0x18002a370  mov     r10, cs:WPP_GLOBAL_Control
0x18002a377  test    rsi, rsi
0x18002a37a  jnz     short loc_18002A394
0x18002a37c  cmp     r10, r13
0x18002a37f  jz      short loc_18002A3C0
0x18002a381  cmp     byte ptr [r10+19h], 2
0x18002a386  jb      short loc_18002A3C0
0x18002a388  lea     edx, [rsi+26h]
0x18002a38b  lea     r9, aWszwlanxmlprof; "wszWlanXmlProfile"
0x18002a392  jmp     short loc_18002A3B0
0x18002a394  test    r14, r14
0x18002a397  jnz     short loc_18002A3CA
0x18002a399  cmp     r10, r13
0x18002a39c  jz      short loc_18002A3C0
0x18002a39e  cmp     byte ptr [r10+19h], 2
0x18002a3a3  jb      short loc_18002A3C0
0x18002a3a5  lea     edx, [r14+27h]
0x18002a3a9  lea     r9, aPpassphrase; "pPassphrase"
0x18002a3b0  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a3b7  mov     rcx, [r10+10h]
0x18002a3bb  call    WPP_SF_s
0x18002a3c0  mov     eax, 80004003h
0x18002a3c5  jmp     loc_18002A99B
0x18002a3ca  mov     [rbp+lpWideCharStr], 0
0x18002a3d2  mov     [rbp+ppvObject], 0
0x18002a3da  mov     [rbp+ppstm], 0
0x18002a3e2  mov     [rbp+arg_0], 0
0x18002a3e9  cmp     r10, r13
0x18002a3ec  jz      short loc_18002A417
0x18002a3ee  cmp     byte ptr [r10+19h], 6
0x18002a3f3  jb      short loc_18002A417
0x18002a3f5  mov     ecx, 1; int
0x18002a3fa  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a3ff  mov     edx, 28h ; '('
0x18002a404  mov     r9, rax
0x18002a407  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a40e  mov     rcx, [r10+10h]
0x18002a412  call    WPP_SF_s
0x18002a417  lea     r8, [rbp+lpWideCharStr]; unsigned __int64 *
0x18002a41b  mov     edx, 0A00000h; unsigned __int64
0x18002a420  mov     rcx, rsi; unsigned __int16 *
0x18002a423  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002a428  mov     ebx, eax
0x18002a42a  test    eax, eax
0x18002a42c  jns     short loc_18002A466
0x18002a42e  mov     r10, cs:WPP_GLOBAL_Control
0x18002a435  cmp     r10, r13
0x18002a438  jz      loc_18002A986
0x18002a43e  cmp     byte ptr [r10+19h], 2
0x18002a443  jb      loc_18002A951
0x18002a449  mov     edx, 2Bh ; '+'
0x18002a44e  mov     r9d, eax
0x18002a451  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a458  mov     rcx, [r10+10h]
0x18002a45c  call    WPP_SF_d
0x18002a461  jmp     loc_18002A94A
0x18002a466  xor     r8d, r8d; pMalloc
0x18002a469  lea     rdx, [rbp+ppvObject]; ppvObject
0x18002a46d  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18002a474  call    cs:__imp_CreateXmlReader
0x18002a47a  mov     ebx, eax
0x18002a47c  test    eax, eax
0x18002a47e  jns     short loc_18002A4A2
0x18002a480  mov     r10, cs:WPP_GLOBAL_Control
0x18002a487  cmp     r10, r13
0x18002a48a  jz      loc_18002A986
0x18002a490  cmp     byte ptr [r10+19h], 2
0x18002a495  jb      loc_18002A951
0x18002a49b  mov     edx, 2Ch ; ','
0x18002a4a0  jmp     short loc_18002A44E
0x18002a4a2  mov     rcx, [rbp+ppvObject]
0x18002a4a6  mov     rax, [rcx]
0x18002a4a9  xor     r8d, r8d
0x18002a4ac  lea     edx, [r8+4]
0x18002a4b0  mov     rax, [rax+28h]
0x18002a4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4b9  mov     ebx, eax
0x18002a4bb  test    eax, eax
0x18002a4bd  jns     short loc_18002A4E4
0x18002a4bf  mov     r10, cs:WPP_GLOBAL_Control
0x18002a4c6  cmp     r10, r13
0x18002a4c9  jz      loc_18002A986
0x18002a4cf  cmp     byte ptr [r10+19h], 2
0x18002a4d4  jb      loc_18002A951
0x18002a4da  mov     edx, 2Dh ; '-'
0x18002a4df  jmp     loc_18002A44E
0x18002a4e4  mov     rax, [rbp+lpWideCharStr]
0x18002a4e8  lea     rbx, ds:2[rax*2]
0x18002a4f0  mov     rdx, rbx; dwBytes
0x18002a4f3  xor     ecx, ecx; uFlags
0x18002a4f5  call    cs:__imp_GlobalAlloc
0x18002a4fb  mov     rdi, rax
0x18002a4fe  test    rax, rax
0x18002a501  jnz     short loc_18002A545
0x18002a503  mov     ebx, 8007000Eh
0x18002a508  mov     r10, cs:WPP_GLOBAL_Control
0x18002a50f  cmp     r10, r13
0x18002a512  jz      loc_18002A986
0x18002a518  cmp     byte ptr [r10+19h], 2
0x18002a51d  jb      loc_18002A951
0x18002a523  xor     ecx, ecx; int
0x18002a525  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a52a  lea     edx, [rdi+2Eh]
0x18002a52d  mov     r9, rax
0x18002a530  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a537  mov     rcx, [r10+10h]
0x18002a53b  call    WPP_SF_s
0x18002a540  jmp     loc_18002A94A
0x18002a545  mov     r8, rbx; Size
0x18002a548  mov     rdx, rsi; Src
0x18002a54b  mov     rcx, rdi; void *
0x18002a54e  call    memcpy_0
0x18002a553  lea     r8, [rbp+ppstm]; ppstm
0x18002a557  mov     edx, 1; fDeleteOnRelease
0x18002a55c  mov     rcx, rdi; hGlobal
0x18002a55f  call    cs:__imp_CreateStreamOnHGlobal
0x18002a565  mov     ebx, eax
0x18002a567  test    eax, eax
0x18002a569  jns     short loc_18002A5A3
0x18002a56b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a572  cmp     rcx, r13
0x18002a575  jz      short loc_18002A595
0x18002a577  cmp     byte ptr [rcx+19h], 2
0x18002a57b  jb      short loc_18002A595
0x18002a57d  mov     edx, 2Fh ; '/'
0x18002a582  mov     r9d, eax
0x18002a585  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002a58c  mov     rcx, [rcx+10h]
0x18002a590  call    WPP_SF_d
0x18002a595  mov     rcx, rdi; hMem
0x18002a598  call    cs:__imp_GlobalFree
0x18002a59e  jmp     loc_18002A94A
0x18002a5a3  mov     rcx, [rbp+ppvObject]
0x18002a5a7  mov     rax, [rcx]
0x18002a5aa  mov     rdx, [rbp+ppstm]
0x18002a5ae  mov     rax, [rax+18h]
0x18002a5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5b7  mov     ebx, eax
0x18002a5b9  test    eax, eax
0x18002a5bb  jns     short loc_18002A5E2
0x18002a5bd  mov     r10, cs:WPP_GLOBAL_Control
0x18002a5c4  cmp     r10, r13
0x18002a5c7  jz      loc_18002A986
0x18002a5cd  cmp     byte ptr [r10+19h], 2
0x18002a5d2  jb      loc_18002A951
0x18002a5d8  mov     edx, 30h ; '0'
0x18002a5dd  jmp     loc_18002A44E
0x18002a5e2  xor     r15b, r15b
0x18002a5e5  xor     esi, esi
0x18002a5e7  mov     rcx, [rbp+ppvObject]
0x18002a5eb  mov     rax, [rcx]
0x18002a5ee  lea     rdx, [rbp+arg_0]
0x18002a5f2  mov     rax, [rax+30h]
0x18002a5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5fb  test    eax, eax
0x18002a5fd  jnz     loc_18002A918
0x18002a603  mov     ecx, [rbp+arg_0]
0x18002a606  sub     ecx, 1
0x18002a609  jz      loc_18002A757
0x18002a60f  cmp     ecx, 2
0x18002a612  jnz     short loc_18002A5E7
0x18002a614  mov     [rbp+lpWideCharStr], 0
0x18002a61c  mov     rcx, [rbp+ppvObject]
0x18002a620  mov     rax, [rcx]
0x18002a623  xor     r8d, r8d
0x18002a626  lea     rdx, [rbp+lpWideCharStr]
0x18002a62a  mov     rax, [rax+80h]
0x18002a631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a636  mov     ebx, eax
0x18002a638  test    eax, eax
0x18002a63a  js      loc_18002A8B5
0x18002a640  mov     rdi, [rbp+lpWideCharStr]
0x18002a644  test    rdi, rdi
0x18002a647  jz      short loc_18002A5E7
0x18002a649  mov     ecx, esi
0x18002a64b  sub     ecx, 1
0x18002a64e  jz      loc_18002A6F3
0x18002a654  sub     ecx, 1
0x18002a657  jz      short loc_18002A6AB
0x18002a659  cmp     ecx, 1
0x18002a65c  jnz     short loc_18002A5E7
0x18002a65e  lea     rax, [r14+10h]
0x18002a662  mov     [rsp+50h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18002a66b  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x18002a674  mov     [rsp+50h+cbMultiByte], 41h ; 'A'; cbMultiByte
0x18002a67c  mov     [rsp+50h+lpMultiByteStr], rax; lpMultiByteStr
0x18002a681  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002a685  mov     r8, rdi; lpWideCharStr
0x18002a688  xor     edx, edx; dwFlags
0x18002a68a  xor     ecx, ecx; CodePage
0x18002a68c  call    cs:__imp_WideCharToMultiByte
0x18002a692  test    eax, eax
0x18002a694  jz      loc_18002A844
0x18002a69a  cdqe
0x18002a69c  dec     rax
0x18002a69f  mov     [r14+8], rax
0x18002a6a3  mov     r15b, 1
0x18002a6a6  jmp     loc_18002A5E7
0x18002a6ab  mov     rdx, rdi; String2
0x18002a6ae  lea     rcx, aFalse; "false"
0x18002a6b5  call    wcscmp_0
0x18002a6ba  test    eax, eax
0x18002a6bc  jz      loc_18002A5E7
0x18002a6c2  mov     ebx, 80070032h
0x18002a6c7  mov     r10, cs:WPP_GLOBAL_Control
0x18002a6ce  cmp     r10, r13
0x18002a6d1  jz      loc_18002A986
0x18002a6d7  cmp     byte ptr [r10+19h], 2
0x18002a6dc  jb      loc_18002A951
0x18002a6e2  xor     ecx, ecx; int
0x18002a6e4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a6e9  mov     edx, 35h ; '5'
0x18002a6ee  jmp     loc_18002A52D
0x18002a6f3  mov     rdx, rdi; String2
0x18002a6f6  lea     rcx, aPassphrase; "passPhrase"
0x18002a6fd  call    wcscmp_0
0x18002a702  test    eax, eax
0x18002a704  jz      loc_18002A5E7
0x18002a70a  mov     rdx, rdi; String2
0x18002a70d  lea     rcx, aNetworkkey; "networkKey"
0x18002a714  call    wcscmp_0
0x18002a719  test    eax, eax
0x18002a71b  jz      loc_18002A5E7
0x18002a721  mov     ebx, 80070032h
0x18002a726  mov     r10, cs:WPP_GLOBAL_Control
0x18002a72d  cmp     r10, r13
0x18002a730  jz      loc_18002A986
0x18002a736  cmp     byte ptr [r10+19h], 2
0x18002a73b  jb      loc_18002A951
0x18002a741  xor     ecx, ecx; int
0x18002a743  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002a748  mov     edx, 34h ; '4'
0x18002a74d  mov     [rsp+50h+lpMultiByteStr], rdi
0x18002a752  jmp     loc_18002A89D
0x18002a757  mov     [rbp+lpWideCharStr], 0
0x18002a75f  mov     [rbp+String1], 0
0x18002a767  mov     rcx, [rbp+ppvObject]
0x18002a76b  mov     rax, [rcx]
0x18002a76e  xor     r8d, r8d
0x18002a771  lea     rdx, [rbp+lpWideCharStr]
0x18002a775  mov     rax, [rax+68h]
0x18002a779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a77e  mov     ebx, eax
0x18002a780  test    eax, eax
0x18002a782  js      loc_18002A8FB
0x18002a788  xor     esi, esi
0x18002a78a  mov     rdi, [rbp+lpWideCharStr]
0x18002a78e  test    rdi, rdi
0x18002a791  jz      loc_18002A5E7
0x18002a797  lea     rdx, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/WLA"...
0x18002a79e  mov     rcx, rdi; String1
0x18002a7a1  call    wcscmp_0
0x18002a7a6  test    eax, eax
0x18002a7a8  jz      short loc_18002A7C1
0x18002a7aa  lea     rdx, aHttpWwwMicroso; "http://www.microsoft.com/networking/WLA"...
0x18002a7b1  mov     rcx, rdi; String1
0x18002a7b4  call    wcscmp_0
0x18002a7b9  test    eax, eax
0x18002a7bb  jnz     loc_18002A5E7
0x18002a7c1  mov     rcx, [rbp+ppvObject]
0x18002a7c5  mov     rax, [rcx]
0x18002a7c8  xor     r8d, r8d
0x18002a7cb  lea     rdx, [rbp+String1]
0x18002a7cf  mov     rax, [rax+70h]
0x18002a7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7d8  mov     ebx, eax
0x18002a7da  test    eax, eax
0x18002a7dc  js      loc_18002A8DA
0x18002a7e2  mov     rdi, [rbp+String1]
0x18002a7e6  test    rdi, rdi
0x18002a7e9  jz      loc_18002A5E7
0x18002a7ef  lea     rdx, aKeytype; "keyType"
0x18002a7f6  mov     rcx, rdi; String1
0x18002a7f9  call    wcscmp_0
0x18002a7fe  test    eax, eax
0x18002a800  jnz     short loc_18002A80A
  ... truncated ...
```

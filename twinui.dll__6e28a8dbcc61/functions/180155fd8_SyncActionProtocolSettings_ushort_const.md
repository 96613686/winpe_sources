# SyncActionProtocolSettings(ushort const *)

- ea: `0x180155fd8`
- end: `0x1801563cd`
- name: `?SyncActionProtocolSettings@@YAXPEBG@Z`
- size: `1013`
- prototype: `void __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180150be0`

## callees

- `0x18000b7e8`
- `0x180027ee4`
- `0x180054170`
- `0x180120c80`
- `0x180154df0`
- `0x180155fd8`
- `0x180356ac8`
- `0x18035fea4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180156089`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801560e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801561a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180156248`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801562b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015635a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180156089`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801560e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801561a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180156248`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801562b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015635a`
- `SHELL32!SHCreateAssociationRegistration` at `0x180156014`
- `SHELL32!SHCreateAssociationRegistration` at `0x180156014`

## pseudocode

```c
void __fastcall SyncActionProtocolSettings(LPCWCH lpString2)
{
  GUID **v2; // rbx
  LPCWCH *i; // rdi
  GUID *v4; // rdx
  int DefaultAppId; // eax
  const unsigned __int16 *v6; // rdx
  unsigned __int16 **v7; // r9
  int (* near **v8)(void); // rdi
  wchar_t **v9; // rbx
  WCHAR *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 *v13; // rbx
  unsigned __int16 **v14; // r9
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rbx
  unsigned __int16 **v19; // r9
  HKEY v20; // rcx
  bool v21; // r8
  int v22; // eax
  LPCWCH lpString2a; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+38h] [rbp-41h]
  __int64 v25; // [rsp+40h] [rbp-39h]
  unsigned __int16 *v26; // [rsp+48h] [rbp-31h] BYREF
  __int64 v27; // [rsp+50h] [rbp-29h]
  __int64 v28; // [rsp+58h] [rbp-21h]
  LPCWCH v29; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+68h] [rbp-11h]
  __int64 v31; // [rsp+70h] [rbp-9h]
  LPCWCH lpString1; // [rsp+78h] [rbp-1h] BYREF
  __int64 v33; // [rsp+80h] [rbp+7h]
  __int64 v34; // [rsp+88h] [rbp+Fh]
  unsigned __int16 *v35; // [rsp+90h] [rbp+17h] BYREF
  __int64 v36; // [rsp+98h] [rbp+1Fh]
  __int64 v37; // [rsp+A0h] [rbp+27h]
  void *ppv; // [rsp+E8h] [rbp+6Fh] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  if ( SHCreateAssociationRegistration(&GUID_a357134e_8c1e_4edd_8474_40a80546f54f, &ppv) >= 0 )
  {
    lpString1 = 0;
    v33 = 0;
    v34 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    v33 = -1;
    v34 = -1;
    if ( (int)anonymous_namespace_::GetDefaultAppId(ppv, lpString2, &lpString1) >= 0 )
    {
      v2 = (GUID **)off_1803E1380;
      for ( i = (LPCWCH *)off_1803E1380; i != (LPCWCH *)&`CRunnableTask::QueryInterface'::`2'::qit; ++i )
      {
        if ( CompareStringOrdinal(*i, -1, lpString2, -1, 1) == 2 )
        {
          do
          {
            lpString2a = 0;
            v24 = 0;
            v25 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
            v4 = *v2;
            v24 = -1;
            v25 = -1;
            DefaultAppId = anonymous_namespace_::GetDefaultAppId(ppv, v4, &lpString2a);
            if ( DefaultAppId == -2147023741
              || DefaultAppId >= 0 && CompareStringOrdinal(lpString1, -1, lpString2a, -1, 0) != 2 )
            {
              v26 = 0;
              v27 = 0;
              v28 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
              v6 = (const unsigned __int16 *)*v2;
              v27 = -1;
              v28 = -1;
              if ( (int)ImmersiveAssociationHelpers::GetAppProgIdForProtocol(
                          (ImmersiveAssociationHelpers *)lpString1,
                          v6,
                          (void **)&v26,
                          v7) >= 0 )
                SetDefaultAssociation(v26);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
            ++v2;
          }
          while ( v2 != &`CRunnableTask::QueryInterface'::`2'::qit );
          goto LABEL_41;
        }
      }
      v26 = 0;
      v27 = 0;
      v28 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
      v8 = (int (* near **)(void))off_1804A8000;
      v27 = -1;
      v9 = off_1804A8000;
      v28 = -1;
      v26 = 0;
      while ( 1 )
      {
        v10 = (WCHAR *)lpString1;
        if ( v9 == (wchar_t **)&g_appCrashUIRegisterProc )
          break;
        if ( CompareStringOrdinal(*v9, -1, lpString2, -1, 1) == 2 )
        {
          if ( (int)_AllocString<CTCoAllocPolicy>(v12, v11, v9[1], &v26) >= 0 )
          {
            v29 = 0;
            v30 = 0;
            v31 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
            v13 = v26;
            v30 = -1;
            v31 = -1;
            if ( (int)ImmersiveAssociationHelpers::GetAppProgIdForProtocol(
                        (ImmersiveAssociationHelpers *)v10,
                        v26,
                        (void **)&v29,
                        v14) >= 0 )
            {
              lpString2a = 0;
              v24 = 0;
              v25 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
              v24 = -1;
              v25 = -1;
              v15 = anonymous_namespace_::GetDefaultAppId(ppv, v13, &lpString2a);
              if ( v15 == -2147023741 || v15 >= 0 && CompareStringOrdinal(v10, -1, lpString2a, -1, 0) != 2 )
                SetDefaultAssociation((unsigned __int16 *)v29);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
          }
          break;
        }
        v9 += 4;
      }
      lpString2a = 0;
      v24 = 0;
      v25 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
      v24 = -1;
      v25 = -1;
      lpString2a = 0;
      while ( v8 != &g_appCrashUIRegisterProc )
      {
        if ( CompareStringOrdinal((LPCWCH)v8[1], -1, lpString2, -1, 1) == 2 )
        {
          if ( (int)_AllocString<CTCoAllocPolicy>(v17, v16, *v8, &lpString2a) >= 0 )
          {
            v35 = 0;
            v36 = 0;
            v37 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
            v18 = lpString2a;
            v36 = -1;
            v37 = -1;
            if ( (int)ImmersiveAssociationHelpers::GetAppProgIdForProtocol(
                        (ImmersiveAssociationHelpers *)v10,
                        lpString2a,
                        (void **)&v35,
                        v19) < 0 )
            {
              ClearUserChoice(v20, v18, v21);
            }
            else
            {
              v29 = 0;
              v30 = 0;
              v31 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
              v30 = -1;
              v31 = -1;
              v22 = anonymous_namespace_::GetDefaultAppId(ppv, v18, &v29);
              if ( v22 == -2147023741 || v22 >= 0 && CompareStringOrdinal(v10, -1, v29, -1, 0) != 2 )
                SetDefaultAssociation(v35);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
          }
          break;
        }
        v8 += 4;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
    }
LABEL_41:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
}

```

## disassembly

```asm
0x180155fd8  mov     [rsp-8+arg_0], rbx
0x180155fdd  mov     [rsp-8+arg_10], rsi
0x180155fe2  push    rbp
0x180155fe3  push    rdi
0x180155fe4  push    r12
0x180155fe6  push    r13
0x180155fe8  push    r14
0x180155fea  lea     rbp, [rsp-37h]
0x180155fef  sub     rsp, 0B0h
0x180155ff6  mov     r14, rcx
0x180155ff9  xor     r12d, r12d
0x180155ffc  lea     rcx, [rbp+57h+ppv]
0x180156000  mov     [rbp+57h+ppv], r12
0x180156004  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180156009  lea     rdx, [rbp+57h+ppv]; ppv
0x18015600d  lea     rcx, _GUID_a357134e_8c1e_4edd_8474_40a80546f54f; riid
0x180156014  call    cs:__imp_SHCreateAssociationRegistration
0x18015601a  test    eax, eax
0x18015601c  js      loc_1801563A8
0x180156022  lea     rcx, [rbp+57h+lpString1]
0x180156026  mov     [rbp+57h+lpString1], r12
0x18015602a  mov     [rbp+57h+var_50], r12
0x18015602e  mov     [rbp+57h+var_48], r12
0x180156032  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156037  mov     rcx, [rbp+57h+ppv]
0x18015603b  lea     r8, [rbp+57h+lpString1]
0x18015603f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180156043  mov     rdx, r14
0x180156046  mov     [rbp+57h+var_50], r13
0x18015604a  mov     [rbp+57h+var_48], r13
0x18015604e  call    _anonymous_namespace___GetDefaultAppId
0x180156053  test    eax, eax
0x180156055  js      loc_18015639F
0x18015605b  lea     rbx, off_1803E1380; "Windows.AppointmentsProvider.AddAppoint"...
0x180156062  mov     rdi, rbx
0x180156065  lea     rsi, ?qit@?1??QueryInterface@CRunnableTask@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; QITAB const near * const `CRunnableTask::QueryInterface(_GUID const &,void * *)'::`2'::qit
0x18015606c  cmp     rdi, rsi
0x18015606f  jz      loc_180156151
0x180156075  mov     rcx, [rdi]; lpString1
0x180156078  mov     r9d, r13d; cchCount2
0x18015607b  mov     r8, r14; lpString2
0x18015607e  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x180156086  mov     edx, r13d; cchCount1
0x180156089  call    cs:__imp_CompareStringOrdinal
0x18015608f  cmp     eax, 2
0x180156092  jz      short loc_18015609A
0x180156094  add     rdi, 8
0x180156098  jmp     short loc_18015606C
0x18015609a  lea     rcx, [rbp+57h+lpString2]
0x18015609e  mov     [rbp+57h+lpString2], r12
0x1801560a2  mov     [rbp+57h+var_98], r12
0x1801560a6  mov     [rbp+57h+var_90], r12
0x1801560aa  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801560af  mov     rdx, [rbx]
0x1801560b2  lea     r8, [rbp+57h+lpString2]
0x1801560b6  mov     rcx, [rbp+57h+ppv]
0x1801560ba  mov     [rbp+57h+var_98], r13
0x1801560be  mov     [rbp+57h+var_90], r13
0x1801560c2  call    _anonymous_namespace___GetDefaultAppId
0x1801560c7  cmp     eax, 80070483h
0x1801560cc  jz      short loc_1801560F0
0x1801560ce  test    eax, eax
0x1801560d0  js      short loc_180156136
0x1801560d2  mov     r8, [rbp+57h+lpString2]; lpString2
0x1801560d6  mov     r9d, r13d; cchCount2
0x1801560d9  mov     rcx, [rbp+57h+lpString1]; lpString1
0x1801560dd  mov     edx, r13d; cchCount1
0x1801560e0  mov     [rsp+0D0h+bIgnoreCase], r12d; bIgnoreCase
0x1801560e5  call    cs:__imp_CompareStringOrdinal
0x1801560eb  cmp     eax, 2
0x1801560ee  jz      short loc_180156136
0x1801560f0  lea     rcx, [rbp+57h+var_88]
0x1801560f4  mov     [rbp+57h+var_88], r12
0x1801560f8  mov     [rbp+57h+var_80], r12
0x1801560fc  mov     [rbp+57h+var_78], r12
0x180156100  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156105  mov     rdx, [rbx]; unsigned __int16 *
0x180156108  lea     r8, [rbp+57h+var_88]; void **
0x18015610c  mov     rcx, [rbp+57h+lpString1]; this
0x180156110  mov     [rbp+57h+var_80], r13
0x180156114  mov     [rbp+57h+var_78], r13
0x180156118  call    ?GetAppProgIdForProtocol@ImmersiveAssociationHelpers@@YAJPEBG0PEAPEAG@Z; ImmersiveAssociationHelpers::GetAppProgIdForProtocol(ushort const *,ushort const *,ushort * *)
0x18015611d  test    eax, eax
0x18015611f  js      short loc_18015612D
0x180156121  mov     rdx, [rbx]
0x180156124  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180156128  call    SetDefaultAssociation
0x18015612d  lea     rcx, [rbp+57h+var_88]
0x180156131  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156136  lea     rcx, [rbp+57h+lpString2]
0x18015613a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015613f  add     rbx, 8
0x180156143  cmp     rbx, rsi
0x180156146  jnz     loc_18015609A
0x18015614c  jmp     loc_18015639F
0x180156151  lea     rcx, [rbp+57h+var_88]
0x180156155  mov     [rbp+57h+var_88], r12
0x180156159  mov     [rbp+57h+var_80], r12
0x18015615d  mov     [rbp+57h+var_78], r12
0x180156161  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156166  lea     rdi, off_1804A8000; "Windows.Contact.Call+telephone"
0x18015616d  mov     [rbp+57h+var_80], r13
0x180156171  mov     rbx, rdi
0x180156174  mov     [rbp+57h+var_78], r13
0x180156178  mov     [rbp+57h+var_88], r12
0x18015617c  mov     rsi, [rbp+57h+lpString1]
0x180156180  lea     rax, ?g_appCrashUIRegisterProc@@3PAP6AJXZA; long (*near * g_appCrashUIRegisterProc)(void)
0x180156187  cmp     rbx, rax
0x18015618a  jz      loc_180156271
0x180156190  mov     rcx, [rbx]; lpString1
0x180156193  mov     r9d, r13d; cchCount2
0x180156196  mov     r8, r14; lpString2
0x180156199  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x1801561a1  mov     edx, r13d; cchCount1
0x1801561a4  call    cs:__imp_CompareStringOrdinal
0x1801561aa  cmp     eax, 2
0x1801561ad  jz      short loc_1801561B5
0x1801561af  add     rbx, 20h ; ' '
0x1801561b3  jmp     short loc_18015617C
0x1801561b5  mov     r8, [rbx+8]
0x1801561b9  lea     r9, [rbp+57h+var_88]
0x1801561bd  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1801561c2  test    eax, eax
0x1801561c4  js      loc_180156271
0x1801561ca  lea     rcx, [rbp+57h+var_70]
0x1801561ce  mov     [rbp+57h+var_70], r12
0x1801561d2  mov     [rbp+57h+var_68], r12
0x1801561d6  mov     [rbp+57h+var_60], r12
0x1801561da  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801561df  mov     rbx, [rbp+57h+var_88]
0x1801561e3  lea     r8, [rbp+57h+var_70]; void **
0x1801561e7  mov     rdx, rbx; unsigned __int16 *
0x1801561ea  mov     [rbp+57h+var_68], r13
0x1801561ee  mov     rcx, rsi; this
0x1801561f1  mov     [rbp+57h+var_60], r13
0x1801561f5  call    ?GetAppProgIdForProtocol@ImmersiveAssociationHelpers@@YAJPEBG0PEAPEAG@Z; ImmersiveAssociationHelpers::GetAppProgIdForProtocol(ushort const *,ushort const *,ushort * *)
0x1801561fa  test    eax, eax
0x1801561fc  js      short loc_180156268
0x1801561fe  lea     rcx, [rbp+57h+lpString2]
0x180156202  mov     [rbp+57h+lpString2], r12
0x180156206  mov     [rbp+57h+var_98], r12
0x18015620a  mov     [rbp+57h+var_90], r12
0x18015620e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156213  mov     rcx, [rbp+57h+ppv]
0x180156217  lea     r8, [rbp+57h+lpString2]
0x18015621b  mov     rdx, rbx
0x18015621e  mov     [rbp+57h+var_98], r13
0x180156222  mov     [rbp+57h+var_90], r13
0x180156226  call    _anonymous_namespace___GetDefaultAppId
0x18015622b  cmp     eax, 80070483h
0x180156230  jz      short loc_180156253
0x180156232  test    eax, eax
0x180156234  js      short loc_18015625F
0x180156236  mov     r8, [rbp+57h+lpString2]; lpString2
0x18015623a  mov     r9d, r13d; cchCount2
0x18015623d  mov     edx, r13d; cchCount1
0x180156240  mov     [rsp+0D0h+bIgnoreCase], r12d; bIgnoreCase
0x180156245  mov     rcx, rsi; lpString1
0x180156248  call    cs:__imp_CompareStringOrdinal
0x18015624e  cmp     eax, 2
0x180156251  jz      short loc_18015625F
0x180156253  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180156257  mov     rdx, rbx
0x18015625a  call    SetDefaultAssociation
0x18015625f  lea     rcx, [rbp+57h+lpString2]
0x180156263  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156268  lea     rcx, [rbp+57h+var_70]
0x18015626c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156271  lea     rcx, [rbp+57h+lpString2]
0x180156275  mov     [rbp+57h+lpString2], r12
0x180156279  mov     [rbp+57h+var_98], r12
0x18015627d  mov     [rbp+57h+var_90], r12
0x180156281  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156286  mov     [rbp+57h+var_98], r13
0x18015628a  lea     rbx, ?g_appCrashUIRegisterProc@@3PAP6AJXZA; long (*near * g_appCrashUIRegisterProc)(void)
0x180156291  mov     [rbp+57h+var_90], r13
0x180156295  mov     [rbp+57h+lpString2], r12
0x180156299  cmp     rdi, rbx
0x18015629c  jz      loc_18015638D
0x1801562a2  mov     rcx, [rdi+8]; lpString1
0x1801562a6  mov     r9d, r13d; cchCount2
0x1801562a9  mov     r8, r14; lpString2
0x1801562ac  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x1801562b4  mov     edx, r13d; cchCount1
0x1801562b7  call    cs:__imp_CompareStringOrdinal
0x1801562bd  cmp     eax, 2
0x1801562c0  jz      short loc_1801562C8
0x1801562c2  add     rdi, 20h ; ' '
0x1801562c6  jmp     short loc_180156299
0x1801562c8  mov     r8, [rdi]
0x1801562cb  lea     r9, [rbp+57h+lpString2]
0x1801562cf  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1801562d4  test    eax, eax
0x1801562d6  js      loc_18015638D
0x1801562dc  lea     rcx, [rbp+57h+var_40]
0x1801562e0  mov     [rbp+57h+var_40], r12
0x1801562e4  mov     [rbp+57h+var_38], r12
0x1801562e8  mov     [rbp+57h+var_30], r12
0x1801562ec  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801562f1  mov     rbx, [rbp+57h+lpString2]
0x1801562f5  lea     r8, [rbp+57h+var_40]; void **
0x1801562f9  mov     rdx, rbx; unsigned __int16 *
0x1801562fc  mov     [rbp+57h+var_38], r13
0x180156300  mov     rcx, rsi; this
0x180156303  mov     [rbp+57h+var_30], r13
0x180156307  call    ?GetAppProgIdForProtocol@ImmersiveAssociationHelpers@@YAJPEBG0PEAPEAG@Z; ImmersiveAssociationHelpers::GetAppProgIdForProtocol(ushort const *,ushort const *,ushort * *)
0x18015630c  test    eax, eax
0x18015630e  js      short loc_18015637C
0x180156310  lea     rcx, [rbp+57h+var_70]
0x180156314  mov     [rbp+57h+var_70], r12
0x180156318  mov     [rbp+57h+var_68], r12
0x18015631c  mov     [rbp+57h+var_60], r12
0x180156320  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156325  mov     rcx, [rbp+57h+ppv]
0x180156329  lea     r8, [rbp+57h+var_70]
0x18015632d  mov     rdx, rbx
0x180156330  mov     [rbp+57h+var_68], r13
0x180156334  mov     [rbp+57h+var_60], r13
0x180156338  call    _anonymous_namespace___GetDefaultAppId
0x18015633d  cmp     eax, 80070483h
0x180156342  jz      short loc_180156365
0x180156344  test    eax, eax
0x180156346  js      short loc_180156371
0x180156348  mov     r8, [rbp+57h+var_70]; lpString2
0x18015634c  mov     r9d, r13d; cchCount2
0x18015634f  mov     edx, r13d; cchCount1
0x180156352  mov     [rsp+0D0h+bIgnoreCase], r12d; bIgnoreCase
0x180156357  mov     rcx, rsi; lpString1
0x18015635a  call    cs:__imp_CompareStringOrdinal
0x180156360  cmp     eax, 2
0x180156363  jz      short loc_180156371
0x180156365  mov     rcx, [rbp+57h+var_40]; unsigned __int16 *
0x180156369  mov     rdx, rbx
0x18015636c  call    SetDefaultAssociation
0x180156371  lea     rcx, [rbp+57h+var_70]
0x180156375  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015637a  jmp     short loc_180156384
0x18015637c  mov     rdx, rbx; unsigned __int16 *
0x18015637f  call    ?ClearUserChoice@@YAXPEAUHKEY__@@PEBG_N@Z; ClearUserChoice(HKEY__ *,ushort const *,bool)
0x180156384  lea     rcx, [rbp+57h+var_40]
0x180156388  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015638d  lea     rcx, [rbp+57h+lpString2]
0x180156391  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156396  lea     rcx, [rbp+57h+var_88]
0x18015639a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015639f  lea     rcx, [rbp+57h+lpString1]
0x1801563a3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801563a8  lea     rcx, [rbp+57h+ppv]
0x1801563ac  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801563b1  lea     r11, [rsp+0D0h+var_20]
0x1801563b9  mov     rbx, [r11+30h]
0x1801563bd  mov     rsi, [r11+40h]
0x1801563c1  mov     rsp, r11
0x1801563c4  pop     r14
0x1801563c6  pop     r13
0x1801563c8  pop     r12
0x1801563ca  pop     rdi
0x1801563cb  pop     rbp
0x1801563cc  retn
```

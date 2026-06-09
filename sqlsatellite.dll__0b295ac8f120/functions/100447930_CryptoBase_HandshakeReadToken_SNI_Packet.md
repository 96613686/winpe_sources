# CryptoBase::HandshakeReadToken(SNI_Packet *)

- ea: `0x100447930`
- end: `0x100448054`
- name: `?HandshakeReadToken@CryptoBase@@IEAAKPEAVSNI_Packet@@@Z`
- size: `1828`
- prototype: `unsigned int __fastcall(CryptoBase *__hidden this, struct SNI_Packet *)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100444980`
- `0x100445bc0`
- `0x1004494a0`
- `0x10044f560`

## callees

- `0x10041f180`
- `0x100423750`
- `0x100423ce0`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100447930`
- `0x100486250`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100447ba3`
- `KERNEL32!QueryPerformanceCounter` at `0x100447ba3`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100447b7a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100447b93`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100447c82`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100447cfd`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100447c82`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100447cfd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100447c32`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100447c63`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100447c76`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100447cf1`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100447c32`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100447c63`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100447c76`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100447cf1`

## string_xrefs

- `0x100447958`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100447daf`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100447dc6`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100447e95`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100447eac`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100447f35`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100447f4c`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x10044800f`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100448032`: `sql\common\dk\sni\src\SNI_CryptoBase.cpp`
- `0x100447963`: `CryptoBase::HandshakeReadToken`
- `0x100447da5`: `CryptoBase::HandshakeReadToken`
- `0x100447dcd`: `CryptoBase::HandshakeReadToken`
- `0x100447e8b`: `CryptoBase::HandshakeReadToken`
- `0x100447eb3`: `CryptoBase::HandshakeReadToken`
- `0x100447f2b`: `CryptoBase::HandshakeReadToken`
- `0x100447f53`: `CryptoBase::HandshakeReadToken`
- `0x100448008`: `CryptoBase::HandshakeReadToken`
- `0x10044802b`: `CryptoBase::HandshakeReadToken`
- `0x100447e7e`: `ERR|SNIInvalid Token! tdsLen: %d{DWORD}, m_cReadBuffer: %d{DWORD}, MaxToken: %d{DWORD}, m_cbAuthInPrefix: %d{DWORD}, m_cbAuthInSuffix: %d{DWORD}\n`
- `0x100447f1e`: `ERR|SNIInvalid Token! tdsLen: %d{DWORD}, dwPacketBufSize: %d{DWORD}\n`
- `0x100447d98`: `ERR|SNIInvalid Token! The last ssl packet comes with extra data packet! This should not happen at client side`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CryptoBase::HandshakeReadToken(CryptoBase *this, struct SNI_Packet *a2)
{
  char v3; // al
  unsigned int v4; // r12d
  int v5; // r15d
  unsigned int AsyncTimeout; // edi
  const wchar_t *v7; // r9
  struct SNI_Packet *v8; // rax
  _BYTE *v9; // r14
  unsigned int v10; // esi
  unsigned int v11; // ecx
  SNI_Conn *v12; // rcx
  __int64 *v13; // rcx
  __int64 v14; // r10
  __int64 *v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rax
  LARGE_INTEGER *v19; // rdi
  int v20; // eax
  unsigned int v21; // edx
  unsigned int v22; // ecx
  unsigned __int64 v23; // r15
  _BYTE *v24; // r13
  unsigned __int64 v25; // r12
  void *v26; // rcx
  bool v27; // r15
  unsigned int v28; // esi
  _BYTE *v29; // rdx
  bool v30; // zf
  char v31; // al
  char v32; // al
  int v33; // eax
  char v34; // al
  __int64 v36; // [rsp+20h] [rbp-49h]
  __int64 v37; // [rsp+28h] [rbp-41h]
  __int64 v38; // [rsp+30h] [rbp-39h]
  int v39; // [rsp+50h] [rbp-19h]
  unsigned int v40; // [rsp+54h] [rbp-15h]
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-11h] BYREF
  __int64 v42; // [rsp+60h] [rbp-9h]
  const char *v43; // [rsp+68h] [rbp-1h]
  const char *v44; // [rsp+70h] [rbp+7h]
  int v45; // [rsp+78h] [rbp+Fh]
  struct SNI_Packet *v46; // [rsp+D8h] [rbp+6Fh] BYREF
  size_t Size; // [rsp+E0h] [rbp+77h] BYREF
  int v48; // [rsp+E8h] [rbp+7Fh] BYREF

  v46 = a2;
  v42 = -2;
  v43 = "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp";
  v44 = "CryptoBase::HandshakeReadToken";
  v45 = 3100;
  v3 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
      "CryptoBase::HandshakeReadToken",
      3100,
      L"API|SNI%u#, pPacket: %p{SNI_Packet*}\n",
      *((_DWORD *)this + 11),
      v46);
    v3 = g_XeSniPkg_enabledBitmap;
  }
  v4 = *((_DWORD *)this + 6);
  v40 = v4;
  v5 = 0;
  v39 = 0;
  if ( *((_QWORD *)this + 7) )
  {
    if ( (v3 & 2) != 0 )
    {
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
        "CryptoBase::HandshakeReadToken",
        3115,
        L"ERR|SNIm_LeftOver is not NULL\n");
      v4 = *((_DWORD *)this + 6);
      v3 = g_XeSniPkg_enabledBitmap;
    }
    AsyncTimeout = -2146893048;
    if ( (v3 & 2) != 0 )
    {
      LODWORD(v37) = 0;
      LODWORD(v36) = v4;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
        "CryptoBase::HandshakeReadToken",
        3118,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v36,
        v37,
        -2146893048);
      v4 = *((_DWORD *)this + 6);
    }
    SNISetLastError(v4, 2148074248LL, 50100);
    *((_DWORD *)this + 49) = 23;
LABEL_92:
    *((_DWORD *)this + 48) = 2;
    goto LABEL_93;
  }
  v8 = v46;
LABEL_10:
  v9 = 0;
  v48 = 0;
  while ( 1 )
  {
    v10 = 0;
    if ( v8 )
    {
      v9 = (_BYTE *)(*((_QWORD *)v8 + 21) + *((unsigned int *)v8 + 46));
      v10 = *((_DWORD *)v8 + 44);
      v5 = *((_DWORD *)v8 + 45);
      v39 = v5;
    }
    if ( !*((_DWORD *)this + 17) || v4 == 3 )
      v11 = ~(unsigned __int8)(*((_DWORD *)this + 16) >> 13) & 8;
    else
      v11 = 5;
    if ( v10 > v11 )
    {
      _mm_lfence();
      AsyncTimeout = (*(__int64 (__fastcall **)(_BYTE *, _QWORD, size_t *, int *, int))(*((_QWORD *)this + 25) + 72LL))(
                       v9,
                       v10,
                       &Size,
                       &v48,
                       v5);
      if ( AsyncTimeout == -2146893048 )
      {
        v34 = g_XeSniPkg_enabledBitmap;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v37) = v5;
          LODWORD(v36) = Size;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::HandshakeReadToken",
            3182,
            L"ERR|SNIInvalid Token! tdsLen: %d{DWORD}, dwPacketBufSize: %d{DWORD}\n",
            v36,
            v37);
          v34 = g_XeSniPkg_enabledBitmap;
        }
        if ( (v34 & 2) != 0 )
        {
          LODWORD(v37) = 0;
          LODWORD(v36) = *((_DWORD *)this + 6);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
            "CryptoBase::HandshakeReadToken",
            3183,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v36,
            v37,
            -2146893048);
        }
        SNISetLastError(*((unsigned int *)this + 6), 2148074248LL, 50100);
        *((_DWORD *)this + 49) = 24;
        goto LABEL_92;
      }
      if ( v10 >= (unsigned int)Size )
      {
        v20 = (*(__int64 (__fastcall **)(CryptoBase *))(*(_QWORD *)this + 312LL))(this);
        v21 = Size + *((_DWORD *)this + 34) - v48;
        v22 = *((_DWORD *)this + 44) + v20 + *((_DWORD *)this + 45);
        _mm_lfence();
        if ( v21 > v22 )
        {
          AsyncTimeout = -2146893048;
          v32 = g_XeSniPkg_enabledBitmap;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            v33 = (*(__int64 (__fastcall **)(CryptoBase *))(*(_QWORD *)this + 312LL))(this);
            LODWORD(v37) = *((_DWORD *)this + 34);
            LODWORD(v36) = Size;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::HandshakeReadToken",
              3270,
              L"ERR|SNIInvalid Token! tdsLen: %d{DWORD}, m_cReadBuffer: %d{DWORD}, MaxToken: %d{DWORD}, m_cbAuthInPrefix: "
               "%d{DWORD}, m_cbAuthInSuffix: %d{DWORD}\n",
              v36,
              v37,
              v33,
              *((_DWORD *)this + 44),
              *((_DWORD *)this + 45));
            v32 = g_XeSniPkg_enabledBitmap;
          }
          if ( (v32 & 2) != 0 )
          {
            LODWORD(v38) = -2146893048;
            LODWORD(v37) = 0;
            LODWORD(v36) = *((_DWORD *)this + 6);
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
              "CryptoBase::HandshakeReadToken",
              3271,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v36,
              v37,
              v38);
          }
          SNISetLastError(*((unsigned int *)this + 6), 2148074248LL, 50100);
          *((_DWORD *)this + 49) = 25;
          goto LABEL_92;
        }
        v23 = (unsigned int)(Size - v48);
        v24 = &v9[v48];
        v25 = (unsigned int)Size;
        v26 = (void *)(*((_QWORD *)this + 15) + *((unsigned int *)this + 34));
        if ( (_DWORD)Size != v48 )
        {
          if ( !v26 )
            goto LABEL_42;
          if ( !v24 || (unsigned int)Size < v23 )
          {
            memset_0(v26, 0, (unsigned int)Size);
            if ( v24 )
            {
              if ( v25 >= v23 )
                goto LABEL_50;
              *_errno() = 34;
            }
            else
            {
LABEL_42:
              *_errno() = 22;
            }
            _invalid_parameter_noinfo();
            goto LABEL_50;
          }
          memmove(v26, &v9[v48], (unsigned int)(Size - v48));
        }
LABEL_50:
        *((_DWORD *)this + 34) += Size - v48;
        v4 = v40;
        v27 = (!*((_DWORD *)this + 17) || v40 == 3) && ((*((_DWORD *)this + 16) & 0x10000) != 0 || (v9[1] & 1) != 0);
        v28 = v10 - Size;
        (*(void (__fastcall **)(CryptoBase *, _BYTE *))(*(_QWORD *)this + 344LL))(this, v9);
        if ( v28 )
        {
          if ( v48 )
          {
            v29 = &v9[(unsigned int)Size];
            if ( v9 && v29 )
            {
              memmove(v9, v29, v28);
            }
            else
            {
              *_errno() = 22;
              _invalid_parameter_noinfo();
            }
          }
          *((_DWORD *)v46 + 44) = v28;
          v8 = v46;
          if ( *((_DWORD *)this + 17) && v40 != 3 )
          {
            v5 = v39;
            goto LABEL_10;
          }
        }
        else
        {
          SNIPacketRelease(v46);
          v8 = 0;
          v46 = 0;
          if ( *((_DWORD *)this + 17) )
            goto LABEL_78;
        }
        if ( v28 == (_DWORD)Size || (v30 = !v27, v5 = v39, !v30) )
        {
          if ( v8 )
          {
            _mm_lfence();
            if ( (*(_BYTE *)(*((_QWORD *)this + 4) + 12804LL) & 2) != 0 && (*((_BYTE *)this + 64) & 8) != 0 )
            {
              _mm_lfence();
              AsyncTimeout = -2146893048;
              v31 = g_XeSniPkg_enabledBitmap;
              if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
              {
                SNIXE_SNI_ERROR_ON(
                  "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
                  "CryptoBase::HandshakeReadToken",
                  3328,
                  L"ERR|SNIInvalid Token! The last ssl packet comes with extra data packet! This should not happen at client side");
                v31 = g_XeSniPkg_enabledBitmap;
              }
              if ( (v31 & 2) != 0 )
              {
                _mm_lfence();
                LODWORD(v37) = 0;
                LODWORD(v36) = *((_DWORD *)this + 6);
                SNIXE_SNI_ERROR_ON(
                  "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
                  "CryptoBase::HandshakeReadToken",
                  3329,
                  L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                  v36,
                  v37,
                  -2146893048);
              }
              SNISetLastError(*((unsigned int *)this + 6), 2148074248LL, 50100);
              *((_DWORD *)this + 49) = 26;
              goto LABEL_92;
            }
            v8 = v46;
          }
LABEL_78:
          *((_QWORD *)this + 7) = v8;
          v46 = 0;
          goto LABEL_95;
        }
        goto LABEL_10;
      }
      v8 = v46;
    }
    v12 = (SNI_Conn *)*((_QWORD *)this + 4);
    if ( (*((_BYTE *)v12 + 12804) & 1) != 0 )
    {
      v13 = (__int64 *)*((_QWORD *)this + 1);
      v14 = *v13;
      AsyncTimeout = v8
                   ? (*(__int64 (__fastcall **)(__int64 *, struct SNI_Packet *, _QWORD, __int64))(v14 + 16))(
                       v13,
                       v8,
                       v5 - v10,
                       0xFFFFFFFFLL)
                   : (*(unsigned __int64 (__fastcall **)(__int64 *, struct SNI_Packet **, __int64))(v14 + 224))(
                       v13,
                       &v46,
                       0xFFFFFFFFLL);
    }
    else
    {
      AsyncTimeout = SNI_Conn::StartReadAsyncTimeout(v12);
      if ( AsyncTimeout )
        break;
      v15 = (__int64 *)*((_QWORD *)this + 1);
      v16 = *v15;
      if ( v46 )
        v17 = (*(__int64 (__fastcall **)(__int64 *, struct SNI_Packet *, _QWORD, _QWORD))(v16 + 24))(
                v15,
                v46,
                v5 - v10,
                0);
      else
        v17 = (*(__int64 (__fastcall **)(__int64 *, struct SNI_Packet **, _QWORD))(v16 + 232))(v15, &v46, 0);
      AsyncTimeout = v17;
      v18 = *((_QWORD *)this + 4);
      if ( AsyncTimeout == 997 )
      {
        v46 = 0;
        _InterlockedIncrement((volatile signed __int32 *)(v18 + 12852));
        _InterlockedIncrement((volatile signed __int32 *)(v18 + 12832));
        goto LABEL_93;
      }
      SNI_Conn::TryCancelReadAsyncTimeout(*((SNI_Conn **)this + 4));
    }
    if ( AsyncTimeout )
      break;
    if ( (*((_BYTE *)this + 64) & 8) == 0
      && (_InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 12748LL)),
          CommonGlobalState::m_CollectingStatistics) )
    {
      v19 = (LARGE_INTEGER *)*((_QWORD *)this + 4);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&PerformanceCount);
        v19[1598] = PerformanceCount;
      }
      else
      {
        v19[1598].QuadPart = MEMORY[0x7FFE0008];
      }
      v8 = v46;
    }
    else
    {
      v8 = v46;
    }
  }
  if ( AsyncTimeout != 997 )
  {
    *((_DWORD *)this + 49) = 27;
    goto LABEL_92;
  }
LABEL_93:
  if ( v46 )
    SNIPacketRelease(v46);
LABEL_95:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v36) = AsyncTimeout;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp",
      "CryptoBase::HandshakeReadToken",
      3352,
      L"RET|SNI%d{WINERR}\n",
      v36);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_CryptoBase.cpp", "CryptoBase::HandshakeReadToken", 3100, v7);
  return AsyncTimeout;
}

```

## disassembly

```asm
0x100447930  mov     [rsp-8+arg_8], rdx
0x100447935  push    rbp
0x100447936  push    rbx
0x100447937  push    rsi
0x100447938  push    rdi
0x100447939  push    r12
0x10044793b  push    r13
0x10044793d  push    r14
0x10044793f  push    r15
0x100447941  lea     rbp, [rsp-1Fh]
0x100447946  sub     rsp, 88h
0x10044794d  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x100447955  mov     rbx, rcx
0x100447958  lea     r13, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x10044795f  mov     [rbp+57h+var_58], r13
0x100447963  lea     rsi, aCryptobaseHand_0; "CryptoBase::HandshakeReadToken"
0x10044796a  mov     [rbp+57h+var_50], rsi
0x10044796e  mov     [rbp+57h+var_48], 0C1Ch
0x100447975  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044797b  test    al, 40h
0x10044797d  jz      short loc_1004479AD
0x10044797f  mov     rax, [rbp+57h+arg_8]
0x100447983  mov     [rsp+0C0h+var_98], rax
0x100447988  mov     eax, [rcx+2Ch]
0x10044798b  mov     dword ptr [rsp+0C0h+var_A0], eax
0x10044798f  lea     r9, aApiSniUPpacket_5; "API|SNI%u#, pPacket: %p{SNI_Packet*}\n"
0x100447996  mov     r8d, 0C1Ch; int
0x10044799c  mov     rdx, rsi; char *
0x10044799f  mov     rcx, r13; char *
0x1004479a2  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004479a7  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004479ad  mov     r12d, [rbx+18h]
0x1004479b1  mov     [rbp+57h+var_6C], r12d
0x1004479b5  xor     r15d, r15d
0x1004479b8  mov     [rbp+57h+var_70], r15d
0x1004479bc  cmp     [rbx+38h], r15
0x1004479c0  jz      short loc_100447A3A
0x1004479c2  test    al, 2
0x1004479c4  jz      short loc_1004479E8
0x1004479c6  lea     r9, aErrSnimLeftove; "ERR|SNIm_LeftOver is not NULL\n"
0x1004479cd  mov     r8d, 0C2Bh; int
0x1004479d3  mov     rdx, rsi; char *
0x1004479d6  mov     rcx, r13; char *
0x1004479d9  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004479de  mov     r12d, [rbx+18h]
0x1004479e2  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004479e8  mov     edi, 80090308h
0x1004479ed  test    al, 2
0x1004479ef  jz      short loc_100447A1B
0x1004479f1  mov     dword ptr [rsp+0C0h+var_90], edi
0x1004479f5  mov     dword ptr [rsp+0C0h+var_98], r15d
0x1004479fa  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x1004479ff  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100447a06  mov     r8d, 0C2Eh; int
0x100447a0c  mov     rdx, rsi; char *
0x100447a0f  mov     rcx, r13; char *
0x100447a12  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100447a17  mov     r12d, [rbx+18h]
0x100447a1b  mov     edx, edi
0x100447a1d  mov     r8d, 0C3B4h
0x100447a23  mov     ecx, r12d
0x100447a26  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100447a2b  mov     dword ptr [rbx+0C4h], 17h
0x100447a35  jmp     loc_100447FD6
0x100447a3a  mov     rax, [rbp+57h+arg_8]
0x100447a3e  xchg    ax, ax
0x100447a40  xor     r14d, r14d
0x100447a43  mov     [rbp+57h+arg_18], r14d
0x100447a47  xor     esi, esi
0x100447a49  test    rax, rax
0x100447a4c  jz      short loc_100447A6D
0x100447a4e  mov     r14d, [rax+0B8h]
0x100447a55  add     r14, [rax+0A8h]
0x100447a5c  mov     esi, [rax+0B0h]
0x100447a62  mov     r15d, [rax+0B4h]
0x100447a69  mov     [rbp+57h+var_70], r15d
0x100447a6d  cmp     dword ptr [rbx+44h], 0
0x100447a71  jz      short loc_100447A80
0x100447a73  cmp     r12d, 3
0x100447a77  jz      short loc_100447A80
0x100447a79  mov     ecx, 5
0x100447a7e  jmp     short loc_100447A8B
0x100447a80  mov     ecx, [rbx+40h]
0x100447a83  shr     ecx, 0Dh
0x100447a86  not     ecx
0x100447a88  and     ecx, 8
0x100447a8b  cmp     esi, ecx
0x100447a8d  jbe     short loc_100447AC8
0x100447a8f  lfence
0x100447a92  mov     rax, [rbx+0C8h]
0x100447a99  mov     dword ptr [rsp+0C0h+var_A0], r15d
0x100447a9e  lea     r9, [rbp+57h+arg_18]
0x100447aa2  lea     r8, [rbp+57h+Size]
0x100447aa6  mov     edx, esi
0x100447aa8  mov     rcx, r14
0x100447aab  call    qword ptr [rax+48h]
0x100447aae  mov     edi, eax
0x100447ab0  cmp     eax, 80090308h
0x100447ab5  jz      loc_100447F08
0x100447abb  cmp     esi, dword ptr [rbp+57h+Size]
0x100447abe  jnb     loc_100447BD5
0x100447ac4  mov     rax, [rbp+57h+arg_8]
0x100447ac8  mov     rcx, [rbx+20h]; this
0x100447acc  test    byte ptr [rcx+3204h], 1
0x100447ad3  jz      short loc_100447B0D
0x100447ad5  mov     rcx, [rbx+8]
0x100447ad9  mov     r10, [rcx]
0x100447adc  test    rax, rax
0x100447adf  jz      short loc_100447AF8
0x100447ae1  mov     r8d, r15d
0x100447ae4  sub     r8d, esi
0x100447ae7  mov     r9d, 0FFFFFFFFh
0x100447aed  mov     rdx, rax
0x100447af0  call    qword ptr [r10+10h]
0x100447af4  mov     edi, eax
0x100447af6  jmp     short loc_100447B61
0x100447af8  mov     r8d, 0FFFFFFFFh
0x100447afe  lea     rdx, [rbp+57h+arg_8]
0x100447b02  call    qword ptr [r10+0E0h]
0x100447b09  mov     edi, eax
0x100447b0b  jmp     short loc_100447B61
0x100447b0d  call    ?StartReadAsyncTimeout@SNI_Conn@@QEAAKXZ; SNI_Conn::StartReadAsyncTimeout(void)
0x100447b12  mov     edi, eax
0x100447b14  test    eax, eax
0x100447b16  jnz     loc_100447FC4
0x100447b1c  mov     rcx, [rbx+8]
0x100447b20  mov     rax, [rcx]
0x100447b23  mov     rdx, [rbp+57h+arg_8]
0x100447b27  test    rdx, rdx
0x100447b2a  jz      short loc_100447B3A
0x100447b2c  mov     r8d, r15d
0x100447b2f  sub     r8d, esi
0x100447b32  xor     r9d, r9d
0x100447b35  call    qword ptr [rax+18h]
0x100447b38  jmp     short loc_100447B47
0x100447b3a  xor     r8d, r8d
0x100447b3d  lea     rdx, [rbp+57h+arg_8]
0x100447b41  call    qword ptr [rax+0E8h]
0x100447b47  mov     edi, eax
0x100447b49  mov     rax, [rbx+20h]
0x100447b4d  cmp     edi, 3E5h
0x100447b53  jz      loc_100447FAC
0x100447b59  mov     rcx, rax; this
0x100447b5c  call    ?TryCancelReadAsyncTimeout@SNI_Conn@@QEAAXXZ; SNI_Conn::TryCancelReadAsyncTimeout(void)
0x100447b61  test    edi, edi
0x100447b63  jnz     loc_100447FC4
0x100447b69  test    byte ptr [rbx+40h], 8
0x100447b6d  jnz     short loc_100447B86
0x100447b6f  mov     rax, [rbx+20h]
0x100447b73  lock inc dword ptr [rax+31CCh]
0x100447b7a  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x100447b81  cmp     [rax], dil
0x100447b84  jnz     short loc_100447B8F
0x100447b86  mov     rax, [rbp+57h+arg_8]
0x100447b8a  jmp     loc_100447A47
0x100447b8f  mov     rdi, [rbx+20h]
0x100447b93  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100447b9a  cmp     dword ptr [rax], 0
0x100447b9d  jz      short loc_100447BBD
0x100447b9f  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x100447ba3  call    cs:__imp_QueryPerformanceCounter
0x100447ba9  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x100447bad  mov     [rdi+31F0h], rax
0x100447bb4  mov     rax, [rbp+57h+arg_8]
0x100447bb8  jmp     loc_100447A47
0x100447bbd  mov     rax, ds:7FFE0008h
0x100447bc5  mov     [rdi+31F0h], rax
0x100447bcc  mov     rax, [rbp+57h+arg_8]
0x100447bd0  jmp     loc_100447A47
0x100447bd5  mov     [rbp+57h+arg_0], 0
0x100447bd9  mov     rax, [rbx]
0x100447bdc  mov     rcx, rbx
0x100447bdf  call    qword ptr [rax+138h]
0x100447be5  mov     ecx, [rbx+0B4h]
0x100447beb  add     ecx, eax
0x100447bed  mov     edx, [rbx+88h]
0x100447bf3  sub     edx, [rbp+57h+arg_18]
0x100447bf6  add     edx, dword ptr [rbp+57h+Size]
0x100447bf9  add     ecx, [rbx+0B0h]
0x100447bff  lfence
0x100447c02  cmp     edx, ecx
0x100447c04  ja      loc_100447E3A
0x100447c0a  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x100447c0e  mov     r15d, r8d
0x100447c11  mov     ecx, [rbp+57h+arg_18]
0x100447c14  sub     r15d, ecx
0x100447c17  lea     r13, [r14+rcx]
0x100447c1b  mov     r12d, r8d
0x100447c1e  mov     ecx, [rbx+88h]
0x100447c24  add     rcx, [rbx+78h]; void *
0x100447c28  test    r15, r15
0x100447c2b  jz      short loc_100447C88
0x100447c2d  test    rcx, rcx
0x100447c30  jnz     short loc_100447C40
0x100447c32  call    cs:__imp__errno
0x100447c38  mov     dword ptr [rax], 16h
0x100447c3e  jmp     short loc_100447C82
0x100447c40  test    r13, r13
0x100447c43  jz      short loc_100447C57
0x100447c45  cmp     r12, r15
0x100447c48  jb      short loc_100447C57
0x100447c4a  mov     r8, r15; Size
0x100447c4d  mov     rdx, r13; Src
0x100447c50  call    memmove
0x100447c55  jmp     short loc_100447C88
0x100447c57  xor     edx, edx; Val
0x100447c59  call    memset_0
0x100447c5e  test    r13, r13
0x100447c61  jnz     short loc_100447C71
0x100447c63  call    cs:__imp__errno
0x100447c69  mov     dword ptr [rax], 16h
0x100447c6f  jmp     short loc_100447C82
0x100447c71  cmp     r12, r15
0x100447c74  jnb     short loc_100447C88
0x100447c76  call    cs:__imp__errno
0x100447c7c  mov     dword ptr [rax], 22h ; '"'
0x100447c82  call    cs:__imp__invalid_parameter_noinfo
0x100447c88  mov     eax, dword ptr [rbp+57h+Size]
0x100447c8b  sub     eax, [rbp+57h+arg_18]
0x100447c8e  add     [rbx+88h], eax
0x100447c94  mov     r12d, [rbp+57h+var_6C]
0x100447c98  cmp     dword ptr [rbx+44h], 0
0x100447c9c  jz      short loc_100447CA4
0x100447c9e  cmp     r12d, 3
0x100447ca2  jnz     short loc_100447CBE
0x100447ca4  test    dword ptr [rbx+40h], 10000h
0x100447cab  jnz     short loc_100447CB9
0x100447cad  test    byte ptr [r14+1], 1
0x100447cb2  jnz     short loc_100447CB9
0x100447cb4  xor     r15b, r15b
0x100447cb7  jmp     short loc_100447CC3
0x100447cb9  mov     r15b, 1
0x100447cbc  jmp     short loc_100447CC3
0x100447cbe  movzx   r15d, [rbp+57h+arg_0]
0x100447cc3  mov     r8d, dword ptr [rbp+57h+Size]
0x100447cc7  sub     esi, r8d
0x100447cca  mov     rax, [rbx]
0x100447ccd  mov     rdx, r14
0x100447cd0  mov     rcx, rbx
0x100447cd3  call    qword ptr [rax+158h]
0x100447cd9  test    esi, esi
0x100447cdb  jz      short loc_100447D35
0x100447cdd  cmp     [rbp+57h+arg_18], 0
0x100447ce1  jbe     short loc_100447D12
0x100447ce3  mov     r8d, esi; Size
0x100447ce6  mov     edx, dword ptr [rbp+57h+Size]
0x100447ce9  add     rdx, r14; Src
0x100447cec  test    r14, r14
0x100447cef  jnz     short loc_100447D05
0x100447cf1  call    cs:__imp__errno
0x100447cf7  mov     dword ptr [rax], 16h
0x100447cfd  call    cs:__imp__invalid_parameter_noinfo
0x100447d03  jmp     short loc_100447D12
0x100447d05  test    rdx, rdx
0x100447d08  jz      short loc_100447CF1
0x100447d0a  mov     rcx, r14; void *
0x100447d0d  call    memmove
0x100447d12  mov     rax, [rbp+57h+arg_8]
0x100447d16  mov     [rax+0B0h], esi
0x100447d1c  mov     rax, [rbp+57h+arg_8]
0x100447d20  cmp     dword ptr [rbx+44h], 0
0x100447d24  jz      short loc_100447D4D
0x100447d26  cmp     r12d, 3
0x100447d2a  jz      short loc_100447D4D
0x100447d2c  mov     r15d, [rbp+57h+var_70]
0x100447d30  jmp     loc_100447A40
0x100447d35  mov     rcx, [rbp+57h+arg_8]; struct SNI_Packet *
0x100447d39  call    SNIPacketRelease
0x100447d3e  xor     eax, eax
0x100447d40  mov     [rbp+57h+arg_8], rax
0x100447d44  cmp     [rbx+44h], eax
0x100447d47  jnz     loc_100447E29
0x100447d4d  cmp     esi, dword ptr [rbp+57h+Size]
0x100447d50  jz      short loc_100447D5F
0x100447d52  test    r15b, r15b
0x100447d55  mov     r15d, [rbp+57h+var_70]
0x100447d59  jz      loc_100447A40
0x100447d5f  test    rax, rax
0x100447d62  jz      loc_100447E29
0x100447d68  lfence
0x100447d6b  mov     rax, [rbx+20h]
0x100447d6f  test    byte ptr [rax+3204h], 2
0x100447d76  jz      loc_100447E25
0x100447d7c  test    byte ptr [rbx+40h], 8
0x100447d80  jz      loc_100447E25
0x100447d86  lfence
0x100447d89  mov     edi, 80090308h
0x100447d8e  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100447d94  test    al, 2
0x100447d96  jz      short loc_100447DC6
0x100447d98  lea     r9, aErrSniinvalidT_2; "ERR|SNIInvalid Token! The last ssl pack"...
0x100447d9f  mov     r8d, 0D00h; int
0x100447da5  lea     rsi, aCryptobaseHand_0; "CryptoBase::HandshakeReadToken"
0x100447dac  mov     rdx, rsi; char *
0x100447daf  lea     r13, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
0x100447db6  mov     rcx, r13; char *
0x100447db9  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100447dbe  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100447dc4  jmp     short loc_100447DD4
0x100447dc6  lea     r13, aSqlCommonDkSni_4; "sql\\common\\dk\\sni\\src\\SNI_CryptoBa"...
  ... truncated ...
```

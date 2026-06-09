# Sspi::Decrypt(SNI_Packet * *,SNI_Packet * *)

- ea: `0x10043ef20`
- end: `0x10043fd83`
- name: `?Decrypt@Sspi@@EEAAKPEAPEAVSNI_Packet@@0@Z`
- size: `3683`
- prototype: `unsigned int __fastcall(Sspi *__hidden this, struct SNI_Packet **, struct SNI_Packet **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x10041ec10`
- `0x10041f180`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10043ee10`
- `0x10043ef20`
- `0x100440c30`
- `0x100440f30`
- `0x100486250`

## string_xrefs

- `0x10043ef4b`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f083`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f0da`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f119`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f1d7`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f236`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f275`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f2d7`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f32e`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f33f`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f40f`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f420`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f4de`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f4ef`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f57d`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f58e`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f61d`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f62e`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f6cf`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f6e0`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f7ee`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f7ff`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f8a9`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f8ba`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f95c`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043f96d`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fa5f`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fa70`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fb39`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fb83`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fb94`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fc20`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fc31`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fcbf`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fcd0`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10043fd17`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Sspi::Decrypt(Sspi *this, struct SNI_Packet **a2, struct SNI_Packet **a3)
{
  const wchar_t *v5; // r9
  int v6; // esi
  int v7; // edx
  unsigned int v8; // ebp
  struct SNI_Packet *v9; // rax
  unsigned int v10; // ebx
  unsigned int v11; // r14d
  __int64 v12; // r8
  __int64 v13; // r13
  unsigned int v14; // r10d
  unsigned int v15; // r15d
  unsigned int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // ecx
  unsigned int v20; // ebp
  unsigned int v21; // r15d
  unsigned int v22; // eax
  __int64 v23; // rax
  unsigned int v24; // ecx
  unsigned int v25; // ebp
  __int64 v26; // r15
  unsigned int v27; // ebp
  unsigned int v28; // ebp
  __int64 Ex2; // rax
  struct SNI_Packet **v30; // rcx
  unsigned int v31; // ebp
  const void *v32; // rdx
  struct SNI_Packet *v33; // rbx
  unsigned int *v35; // [rsp+20h] [rbp-A8h]
  unsigned __int8 *v36; // [rsp+28h] [rbp-A0h]
  unsigned int v37[2]; // [rsp+30h] [rbp-98h]
  __int64 v38; // [rsp+60h] [rbp-68h]
  unsigned int v39; // [rsp+D0h] [rbp+8h] BYREF
  struct SNI_Packet **v40; // [rsp+E0h] [rbp+18h]
  unsigned int v41; // [rsp+E8h] [rbp+20h]

  v40 = a3;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::Decrypt",
      475,
      L"API|SNI%u#, ppPacket: %p{SNI_Packet**}, ppLeftOver: %p{SNI_Packet**}\n",
      *((_DWORD *)this + 11),
      a2,
      a3);
  v5 = 0;
  v6 = 0;
  v7 = *(_DWORD *)(*((_QWORD *)this + 25) + 20LL);
  if ( !v7 )
  {
    v8 = 87;
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v35) = 87;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::Decrypt",
        484,
        L"RET|SNI%d{WINERR}\n",
        v35);
    }
    goto LABEL_116;
  }
  v9 = *a2;
  if ( *a2 )
  {
    v10 = 0;
    v11 = 0;
    v39 = 0;
    v12 = 0;
    v38 = 0;
    v13 = *((_QWORD *)v9 + 21) + *((unsigned int *)v9 + 46);
    v14 = *((_DWORD *)v9 + 44);
    v41 = v14;
    v15 = *((_DWORD *)v9 + 45);
    if ( v14 < *((_DWORD *)this + 18) )
    {
      v6 = -2146893032;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        _mm_lfence();
        v37[0] = *((_DWORD *)this + 19);
        LODWORD(v36) = *((_DWORD *)this + 18);
        LODWORD(v35) = v14;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Decrypt",
          532,
          L"SNIcbReceived: %d{DWORD}, m_cbHeaderLength: %d{DWORD}, m_cbTrailerLength: %d{DWORD}, m_cbPaddingLength: %d{DWO"
           "RD}, m_cbSignLength: %d{DWORD}, dwRet: %d{DWORD}\n",
          v35,
          v36,
          *(_QWORD *)v37,
          *((_DWORD *)this + 21),
          *((_DWORD *)this + 20),
          -2146893032);
      }
      goto LABEL_113;
    }
    switch ( v7 )
    {
      case 1:
        v39 = *(_DWORD *)(v13 + 8);
        v12 = *(_QWORD *)(v13 + 16);
        break;
      case 2:
        v12 = *(_QWORD *)(v13 + 8);
        break;
      case 3:
LABEL_22:
        v10 = *(_DWORD *)v13;
        goto LABEL_23;
      default:
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v35) = v7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Decrypt",
            575,
            L"ERR|SNIInvalid crypto mode %d for SSPI provider encountered.\n",
            v35);
        }
        v6 = 87;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          v37[0] = 87;
          LODWORD(v36) = 0;
          LODWORD(v35) = 3;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Decrypt",
            578,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v35,
            v36,
            *(_QWORD *)v37);
        }
        SNISetLastError(3, 87, 50100);
        v12 = 0;
        v14 = v41;
        v5 = 0;
LABEL_23:
        v16 = *((_DWORD *)this + 18);
        if ( v10 < v16 || v10 > v15 )
        {
          v6 = -2146893041;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            v37[0] = -2146893041;
            LODWORD(v36) = 0;
            LODWORD(v35) = 3;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Decrypt",
              587,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v35,
              v36,
              *(_QWORD *)v37);
          }
          SNISetLastError(3, 2148074255LL, 50100);
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v35) = v10;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Decrypt",
              590,
              L"ERR|SNIInvalid total length received in the header: %d.\n",
              v35);
          }
          goto LABEL_113;
        }
        if ( v14 < v10 )
        {
          v6 = -2146893032;
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            _mm_lfence();
            v37[0] = *((_DWORD *)this + 19);
            LODWORD(v36) = *((_DWORD *)this + 18);
            LODWORD(v35) = v14;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Decrypt",
              613,
              L"SNIcbReceived: %d{DWORD}, m_cbHeaderLength: %d{DWORD}, m_cbTrailerLength: %d{DWORD}, m_cbPaddingLength: %d"
               "{DWORD}, m_cbSignLength: %d{DWORD}, cbTotalLength: %d{DWORD}, dwRet: %d{DWORD}\n",
              v35,
              v36,
              *(_QWORD *)v37,
              *((_DWORD *)this + 21),
              *((_DWORD *)this + 20),
              v10,
              -2146893032);
          }
          goto LABEL_113;
        }
        v17 = *((_QWORD *)this + 25);
        if ( *(_DWORD *)(v17 + 20) == 1 )
        {
          v23 = *((_QWORD *)this + 46);
          if ( v23 != v12 )
          {
            v6 = -2146893040;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893040;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                642,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074256LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                646,
                L"ERR|SNIInvalid sequence number detected while decrypting %I64u{ULONGLONG}, expected %I64u{ULONGLONG}.\n",
                v38,
                *((_QWORD *)this + 46));
            goto LABEL_113;
          }
          *((_QWORD *)this + 46) = v23 + 1;
          v24 = *((_DWORD *)this + 19);
          v25 = *((_DWORD *)this + 21) + v24 + v16;
          if ( v25 >= v15 || v11 > v15 - v25 )
          {
            v6 = -2146893041;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893041;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                668,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074255LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              v37[0] = v25;
              LODWORD(v36) = v15;
              LODWORD(v35) = v11;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                675,
                L"ERR|SNIInvalid data length received %d{DWORD}. cbPacketTotalBuffer: %d{DWORD},cbMaxNonDataPart: %d{DWORD}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            goto LABEL_113;
          }
          v26 = v39;
          if ( !v39 || v39 > v24 )
          {
            v6 = -2146893041;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893041;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                686,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074255LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(v36) = *((_DWORD *)this + 19);
              LODWORD(v35) = v26;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                690,
                L"ERR|SNIInvalid trailer length received %d{DWORD}, m_cbTrailerLength: %d{DWORD}.\n",
                v35,
                v36);
            }
            goto LABEL_113;
          }
          _mm_lfence();
          v39 = 0;
          if ( (int)Sspi::ULongAdd3Args(this, *((_DWORD *)this + 18), v11, v26, &v39) < 0 )
          {
            v6 = 534;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = 534;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                702,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 534, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              v37[0] = v11;
              LODWORD(v36) = *((_DWORD *)this + 19);
              LODWORD(v35) = *((_DWORD *)this + 18);
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                712,
                L"ERR|SNIInvalid header, data and trailer sizes. m_cbHeaderLength: %d{DWORD}, m_cbTrailerLength: %d{DWORD}"
                 ", cbDataLength: %d{DWORD}, cbTrailerLength: %d{DWORD}\n",
                v35,
                v36,
                *(_QWORD *)v37,
                v26);
            }
            goto LABEL_113;
          }
          if ( v39 > v10 )
          {
            v6 = -2146893041;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893041;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                721,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074255LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              LODWORD(v36) = v10;
              LODWORD(v35) = v39;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                725,
                L"ERR|SNIInvalid padding length received. Non-padding part of packet: %d{DWORD}, cbTotalLength: %d{DWORD}.\n",
                v35,
                v36);
            }
            goto LABEL_113;
          }
          v27 = v10 - v39;
          if ( v10 - v39 > *((_DWORD *)this + 21) )
          {
            v6 = -2146893041;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893041;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                737,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074255LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              LODWORD(v35) = v27;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                740,
                L"ERR|SNIInvalid padding length received: %d{DWORD}.\n",
                v35);
            }
            goto LABEL_113;
          }
          _mm_lfence();
          v22 = Sspi::DecryptPayload(
                  this,
                  (unsigned __int8 *)(*((unsigned int *)this + 18) + v13),
                  v11,
                  (unsigned __int8 *)(v13 + v11 + (unsigned __int64)*((unsigned int *)this + 18)),
                  v26,
                  (unsigned __int8 *)(v13 + *((unsigned int *)this + 18) + v11 + v26),
                  v27);
        }
        else
        {
          if ( *(_DWORD *)(v17 + 20) != 2 )
          {
            if ( *(_DWORD *)(v17 + 20) == 3 )
            {
              v11 = v10 - v16;
              if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
              {
                _mm_lfence();
                v37[0] = v10;
                LODWORD(v36) = *((_DWORD *)this + 18);
                LODWORD(v35) = v15;
                SNIXE_SNI_TRACE_ON(
                  "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                  "Sspi::Decrypt",
                  631,
                  L"SNIcbPacketTotalBuffer: %d{DWORD}, m_cbHeaderLength: %d{DWORD}, cbTotalLength: %d{DWORD}, cbDataLength: %d{DWORD}\n",
                  v35,
                  v36,
                  *(_QWORD *)v37,
                  v10 - v16);
              }
            }
            else
            {
              if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
              {
                LODWORD(v35) = *(_DWORD *)(v17 + 20);
                SNIXE_SNI_ERROR_ON(
                  "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                  "Sspi::Decrypt",
                  870,
                  L"ERR|SNIInvalid crypto mode %d for SSPI provider encountered.\n",
                  v35);
              }
              v6 = 87;
              if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
              {
                v37[0] = 87;
                LODWORD(v36) = 0;
                LODWORD(v35) = 3;
                SNIXE_SNI_ERROR_ON(
                  "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                  "Sspi::Decrypt",
                  873,
                  L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                  v35,
                  v36,
                  *(_QWORD *)v37);
              }
              SNISetLastError(3, 87, 50100);
            }
            goto LABEL_92;
          }
          v18 = *((_QWORD *)this + 46);
          if ( v18 != v12 )
          {
            v6 = -2146893040;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893040;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                766,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074256LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                770,
                L"ERR|SNIInvalid sequence number detected while decrypting %I64u{ULONGLONG}, expected %I64u{ULONGLONG}.\n",
                v38,
                *((_QWORD *)this + 46));
            goto LABEL_113;
          }
          *((_QWORD *)this + 46) = v18 + 1;
          v19 = *((_DWORD *)this + 20);
          v20 = v19 + v16;
          if ( v19 + v16 >= v15 || v11 > v15 - v20 )
          {
            v6 = -2146893041;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893041;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                793,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074255LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              v37[0] = v20;
              LODWORD(v36) = v15;
              LODWORD(v35) = v11;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                800,
                L"ERR|SNIInvalid data length received %d{DWORD}. cbPacketTotalBuffer: %d{DWORD},cbMaxNonDataPart: %d{DWORD}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            goto LABEL_113;
          }
          v21 = v16 + v11;
          if ( v16 + v11 < v16 )
          {
            v6 = 534;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = 534;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                812,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 534, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              LODWORD(v36) = v11;
              LODWORD(v35) = *((_DWORD *)this + 18);
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                818,
                L"ERR|SNIInvalid header or data length. m_cbHeaderLength: %d{DWORD}, cbDataLength: %d{DWORD}\n",
                v35,
                v36);
            }
            goto LABEL_113;
          }
          if ( v21 > v10 )
          {
            v6 = -2146893041;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893041;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                827,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074255LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              LODWORD(v36) = v10;
              LODWORD(v35) = v21;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                831,
                L"ERR|SNIInvalid sign length received. Non-sign part of packet: %d{DWORD}, cbTotalLength: %d{DWORD}.\n",
                v35,
                v36);
            }
            goto LABEL_113;
          }
          if ( v10 == v21 || v10 - v21 > v19 )
          {
            v6 = -2146893041;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = -2146893041;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                844,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 2148074255LL, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              LODWORD(v36) = *((_DWORD *)this + 20);
              LODWORD(v35) = v10 - v21;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                848,
                L"ERR|SNIInvalid signature length received: %d{DWORD}, m_cbSignLength: %d{DWORD}.\n",
                v35,
                v36);
            }
            goto LABEL_113;
          }
          _mm_lfence();
          v22 = Sspi::VerifySignature(
                  this,
                  (unsigned __int8 *)(*((unsigned int *)this + 18) + v13),
                  v11,
                  (unsigned __int8 *)(v13 + *((unsigned int *)this + 18) + (unsigned __int64)v11),
                  v10 - v21);
        }
        v6 = v22;
        if ( v22 )
          goto LABEL_113;
LABEL_92:
        v28 = v41;
        if ( v10 < v41 )
        {
          Ex2 = SNIPacketAllocateEx2(*((_QWORD *)this + 4), 0);
          v30 = v40;
          *v40 = (struct SNI_Packet *)Ex2;
          if ( !Ex2 )
          {
            v6 = 14;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              v37[0] = 14;
              LODWORD(v36) = 0;
              LODWORD(v35) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Decrypt",
                884,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v35,
                v36,
                *(_QWORD *)v37);
            }
            SNISetLastError(3, 14, 50100);
            goto LABEL_113;
          }
          _mm_lfence();
          v31 = v28 - v10;
          v32 = (const void *)(v13 + v10);
          v33 = *v30;
          memmove((void *)(*((_QWORD *)*v30 + 21) + *((unsigned int *)*v30 + 46)), v32, v31);
          *((_DWORD *)v33 + 44) = v31;
        }
        *((_DWORD *)*a2 + 46) += *((_DWORD *)this + 18);
        *((_DWORD *)*a2 + 44) = v11;
        *((_BYTE *)*a2 + 256) = 0;
        *((_BYTE *)*a2 + 257) = 0;
        *((_DWORD *)*a2 + 60) = 0;
        if ( !*((_DWORD *)*a2 + 44) )
        {
          SNIPacketRelease(*a2);
          *a2 = 0;
          v6 = -2146893032;
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Decrypt",
              911,
              L"SNIReceived empty data buffer\n");
        }
        goto LABEL_113;
    }
    v38 = v12;
    v11 = *(_DWORD *)(v13 + 4);
    goto LABEL_22;
  }
  v6 = -2146893032;
LABEL_113:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v35) = v6;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::Decrypt",
      916,
      L"RET|SNI%d{WINERR}\n",
      v35);
  }
  v8 = v6;
LABEL_116:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", "Sspi::Decrypt", 475, v5);
  return v8;
}

```

## disassembly

```asm
0x10043ef20  mov     rax, rsp
0x10043ef23  mov     [rax+18h], r8
0x10043ef27  push    rbp
0x10043ef28  push    rsi
0x10043ef29  push    rdi
0x10043ef2a  push    r12
0x10043ef2c  push    r13
0x10043ef2e  push    r14
0x10043ef30  push    r15
0x10043ef32  sub     rsp, 90h
0x10043ef39  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x10043ef41  mov     [rax+10h], rbx
0x10043ef45  mov     r12, rdx
0x10043ef48  mov     rdi, rcx
0x10043ef4b  lea     r13, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043ef52  mov     [rax-58h], r13
0x10043ef56  lea     rbx, aSspiDecrypt; "Sspi::Decrypt"
0x10043ef5d  mov     [rax-50h], rbx
0x10043ef61  mov     dword ptr [rax-48h], 1DBh
0x10043ef68  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043ef6f  jz      short loc_10043EF9A
0x10043ef71  mov     qword ptr [rsp+0C8h+var_98], r8
0x10043ef76  mov     [rsp+0C8h+var_A0], rdx
0x10043ef7b  mov     eax, [rcx+2Ch]
0x10043ef7e  mov     dword ptr [rsp+0C8h+var_A8], eax
0x10043ef82  lea     r9, aApiSniUPppacke_1; "API|SNI%u#, ppPacket: %p{SNI_Packet**},"...
0x10043ef89  mov     r8d, 1DBh; int
0x10043ef8f  mov     rdx, rbx; char *
0x10043ef92  mov     rcx, r13; char *
0x10043ef95  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043ef9a  xor     r9d, r9d
0x10043ef9d  mov     esi, r9d
0x10043efa0  mov     rax, [rdi+0C8h]
0x10043efa7  mov     edx, [rax+14h]
0x10043efaa  test    edx, edx
0x10043efac  jnz     short loc_10043EFDF
0x10043efae  lea     ebp, [rdx+57h]
0x10043efb1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043efb8  jz      loc_10043FD4C
0x10043efbe  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x10043efc2  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043efc9  mov     r8d, 1E4h; int
0x10043efcf  mov     rdx, rbx; char *
0x10043efd2  mov     rcx, r13; char *
0x10043efd5  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043efda  jmp     loc_10043FD4C
0x10043efdf  mov     rax, [r12]
0x10043efe3  test    rax, rax
0x10043efe6  jnz     short loc_10043EFF2
0x10043efe8  mov     esi, 80090318h
0x10043efed  jmp     loc_10043FD25
0x10043eff2  mov     ebx, r9d
0x10043eff5  mov     r14d, r9d
0x10043eff8  mov     [rsp+0C8h+arg_0], r9d
0x10043f000  mov     r8, r9
0x10043f003  mov     [rsp+0C8h+var_68], r9
0x10043f008  mov     r13d, [rax+0B8h]
0x10043f00f  add     r13, [rax+0A8h]
0x10043f016  mov     r10d, [rax+0B0h]
0x10043f01d  mov     [rsp+0C8h+arg_18], r10d
0x10043f025  mov     r15d, [rax+0B4h]
0x10043f02c  cmp     r10d, [rdi+48h]
0x10043f030  jnb     short loc_10043F097
0x10043f032  mov     esi, 80090318h
0x10043f037  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f03e  jz      loc_10043FD17
0x10043f044  lfence
0x10043f047  mov     [rsp+0C8h+var_80], esi
0x10043f04b  mov     eax, [rdi+50h]
0x10043f04e  mov     [rsp+0C8h+var_88], eax
0x10043f052  mov     eax, [rdi+54h]
0x10043f055  mov     [rsp+0C8h+var_90], eax
0x10043f059  mov     eax, [rdi+4Ch]
0x10043f05c  mov     [rsp+0C8h+var_98], eax
0x10043f060  mov     eax, [rdi+48h]
0x10043f063  mov     dword ptr [rsp+0C8h+var_A0], eax
0x10043f067  mov     dword ptr [rsp+0C8h+var_A8], r10d
0x10043f06c  lea     r9, aSnicbreceivedD_0; "SNIcbReceived: %d{DWORD}, m_cbHeaderLen"...
0x10043f073  mov     r8d, 214h; int
0x10043f079  lea     rbx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f080  mov     rdx, rbx; char *
0x10043f083  lea     r13, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f08a  mov     rcx, r13; char *
0x10043f08d  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f092  jmp     loc_10043FD25
0x10043f097  mov     ecx, edx
0x10043f099  mov     ebp, 57h ; 'W'
0x10043f09e  sub     ecx, 1
0x10043f0a1  jz      loc_10043F14D
0x10043f0a7  sub     ecx, 1
0x10043f0aa  jz      loc_10043F147
0x10043f0b0  cmp     ecx, 1
0x10043f0b3  jz      loc_10043F165
0x10043f0b9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f0c0  jz      short loc_10043F0E9
0x10043f0c2  mov     dword ptr [rsp+0C8h+var_A8], edx
0x10043f0c6  lea     r9, aErrSniinvalidC; "ERR|SNIInvalid crypto mode %d for SSPI "...
0x10043f0cd  mov     r8d, 23Fh; int
0x10043f0d3  lea     rdx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f0da  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f0e1  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f0e6  xor     r9d, r9d
0x10043f0e9  mov     esi, ebp
0x10043f0eb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f0f2  jz      short loc_10043F125
0x10043f0f4  mov     [rsp+0C8h+var_98], ebp
0x10043f0f8  mov     dword ptr [rsp+0C8h+var_A0], r9d
0x10043f0fd  mov     dword ptr [rsp+0C8h+var_A8], 3
0x10043f105  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043f10c  mov     r8d, 242h; int
0x10043f112  lea     rdx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f119  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f120  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f125  mov     r8d, 0C3B4h
0x10043f12b  mov     edx, ebp
0x10043f12d  mov     ecx, 3
0x10043f132  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043f137  mov     r8, rbx
0x10043f13a  mov     r10d, [rsp+0C8h+arg_18]
0x10043f142  xor     r9d, r9d
0x10043f145  jmp     short loc_10043F169
0x10043f147  mov     r8, [r13+8]
0x10043f14b  jmp     short loc_10043F15C
0x10043f14d  mov     ecx, [r13+8]
0x10043f151  mov     [rsp+0C8h+arg_0], ecx
0x10043f158  mov     r8, [r13+10h]
0x10043f15c  mov     [rsp+0C8h+var_68], r8
0x10043f161  mov     r14d, [r13+4]
0x10043f165  mov     ebx, [r13+0]
0x10043f169  mov     edx, [rdi+48h]
0x10043f16c  cmp     ebx, edx
0x10043f16e  jb      loc_10043FC8C
0x10043f174  cmp     ebx, r15d
0x10043f177  ja      loc_10043FC8C
0x10043f17d  cmp     r10d, ebx
0x10043f180  jnb     short loc_10043F1EB
0x10043f182  mov     esi, 80090318h
0x10043f187  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f18e  jz      loc_10043FD17
0x10043f194  lfence
0x10043f197  mov     [rsp+0C8h+var_78], esi
0x10043f19b  mov     [rsp+0C8h+var_80], ebx
0x10043f19f  mov     eax, [rdi+50h]
0x10043f1a2  mov     [rsp+0C8h+var_88], eax
0x10043f1a6  mov     eax, [rdi+54h]
0x10043f1a9  mov     [rsp+0C8h+var_90], eax
0x10043f1ad  mov     eax, [rdi+4Ch]
0x10043f1b0  mov     [rsp+0C8h+var_98], eax
0x10043f1b4  mov     eax, [rdi+48h]
0x10043f1b7  mov     dword ptr [rsp+0C8h+var_A0], eax
0x10043f1bb  mov     dword ptr [rsp+0C8h+var_A8], r10d
0x10043f1c0  lea     r9, aSnicbreceivedD; "SNIcbReceived: %d{DWORD}, m_cbHeaderLen"...
0x10043f1c7  mov     r8d, 265h; int
0x10043f1cd  lea     rbx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f1d4  mov     rdx, rbx; char *
0x10043f1d7  lea     r13, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f1de  mov     rcx, r13; char *
0x10043f1e1  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f1e6  jmp     loc_10043FD25
0x10043f1eb  mov     rax, [rdi+0C8h]
0x10043f1f2  mov     r10d, [rax+14h]
0x10043f1f6  mov     ecx, r10d
0x10043f1f9  sub     ecx, 1
0x10043f1fc  jz      loc_10043F689
0x10043f202  sub     ecx, 1
0x10043f205  jz      loc_10043F2E8
0x10043f20b  cmp     ecx, 1
0x10043f20e  jz      loc_10043F298
0x10043f214  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f21b  jz      short loc_10043F242
0x10043f21d  mov     dword ptr [rsp+0C8h+var_A8], r10d
0x10043f222  lea     r9, aErrSniinvalidC; "ERR|SNIInvalid crypto mode %d for SSPI "...
0x10043f229  mov     r8d, 366h; int
0x10043f22f  lea     rdx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f236  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f23d  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f242  mov     esi, ebp
0x10043f244  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f24b  jz      short loc_10043F281
0x10043f24d  mov     [rsp+0C8h+var_98], ebp
0x10043f251  mov     dword ptr [rsp+0C8h+var_A0], 0
0x10043f259  mov     dword ptr [rsp+0C8h+var_A8], 3
0x10043f261  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043f268  mov     r8d, 369h; int
0x10043f26e  lea     rdx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f275  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f27c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f281  mov     r8d, 0C3B4h
0x10043f287  mov     edx, ebp
0x10043f289  mov     ecx, 3
0x10043f28e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043f293  jmp     loc_10043F9FF
0x10043f298  mov     r14d, ebx
0x10043f29b  sub     r14d, edx
0x10043f29e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f2a5  jz      loc_10043F9FF
0x10043f2ab  lfence
0x10043f2ae  mov     [rsp+0C8h+var_90], r14d
0x10043f2b3  mov     [rsp+0C8h+var_98], ebx
0x10043f2b7  mov     eax, [rdi+48h]
0x10043f2ba  mov     dword ptr [rsp+0C8h+var_A0], eax
0x10043f2be  mov     dword ptr [rsp+0C8h+var_A8], r15d
0x10043f2c3  lea     r9, aSnicbpackettot; "SNIcbPacketTotalBuffer: %d{DWORD}, m_cb"...
0x10043f2ca  mov     r8d, 277h; int
0x10043f2d0  lea     rdx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f2d7  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f2de  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f2e3  jmp     loc_10043F9FF
0x10043f2e8  mov     rax, [rdi+170h]
0x10043f2ef  cmp     rax, r8
0x10043f2f2  jz      loc_10043F39F
0x10043f2f8  mov     esi, 80090310h
0x10043f2fd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f304  jz      short loc_10043F33F
0x10043f306  mov     [rsp+0C8h+var_98], esi
0x10043f30a  mov     dword ptr [rsp+0C8h+var_A0], r9d
0x10043f30f  mov     dword ptr [rsp+0C8h+var_A8], 3
0x10043f317  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043f31e  mov     r8d, 2FEh; int
0x10043f324  lea     rbx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f32b  mov     rdx, rbx; char *
0x10043f32e  lea     r13, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f335  mov     rcx, r13; char *
0x10043f338  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f33d  jmp     short loc_10043F34D
0x10043f33f  lea     r13, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f346  lea     rbx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f34d  mov     edx, esi
0x10043f34f  mov     ecx, 3
0x10043f354  mov     r8d, 0C3B4h
0x10043f35a  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043f35f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f366  jz      loc_10043FD25
0x10043f36c  mov     rax, [rdi+170h]
0x10043f373  mov     [rsp+0C8h+var_A0], rax
0x10043f378  mov     rax, [rsp+0C8h+var_68]
0x10043f37d  mov     [rsp+0C8h+var_A8], rax
0x10043f382  lea     r9, aErrSniinvalidS; "ERR|SNIInvalid sequence number detected"...
0x10043f389  mov     r8d, 302h; int
0x10043f38f  mov     rdx, rbx; char *
0x10043f392  mov     rcx, r13; char *
0x10043f395  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f39a  jmp     loc_10043FD25
0x10043f39f  inc     rax
0x10043f3a2  mov     [rdi+170h], rax
0x10043f3a9  mov     ecx, [rdi+50h]
0x10043f3ac  lea     ebp, [rcx+rdx]
0x10043f3af  cmp     ebp, r15d
0x10043f3b2  jnb     loc_10043F5E7
0x10043f3b8  mov     eax, r15d
0x10043f3bb  sub     eax, ebp
0x10043f3bd  cmp     r14d, eax
0x10043f3c0  ja      loc_10043F5E7
0x10043f3c6  lea     r15d, [rdx+r14]
0x10043f3ca  cmp     r15d, edx
0x10043f3cd  jb      loc_10043F547
0x10043f3d3  cmp     r15d, ebx
0x10043f3d6  jbe     loc_10043F476
0x10043f3dc  mov     esi, 8009030Fh
0x10043f3e1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f3e8  jz      short loc_10043F420
0x10043f3ea  mov     [rsp+0C8h+var_98], esi
0x10043f3ee  mov     dword ptr [rsp+0C8h+var_A0], r9d
0x10043f3f3  mov     dword ptr [rsp+0C8h+var_A8], 3
0x10043f3fb  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043f402  mov     r8d, 33Bh; int
0x10043f408  lea     rdx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f40f  lea     r13, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f416  mov     rcx, r13; char *
0x10043f419  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f41e  jmp     short loc_10043F427
0x10043f420  lea     r13, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10043f427  mov     edx, esi
0x10043f429  mov     ecx, 3
0x10043f42e  mov     r8d, 0C3B4h
0x10043f434  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043f439  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043f440  jz      loc_10043FD1E
0x10043f446  lfence
0x10043f449  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x10043f44d  mov     dword ptr [rsp+0C8h+var_A8], r15d
0x10043f452  lea     r9, aErrSniinvalidS_0; "ERR|SNIInvalid sign length received. No"...
0x10043f459  mov     r8d, 33Fh; int
0x10043f45f  lea     rbx, aSspiDecrypt; "Sspi::Decrypt"
0x10043f466  mov     rdx, rbx; char *
0x10043f469  mov     rcx, r13; char *
0x10043f46c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043f471  jmp     loc_10043FD25
0x10043f476  mov     ebp, ebx
0x10043f478  sub     ebp, r15d
0x10043f47b  jz      short loc_10043F4A8
0x10043f47d  cmp     ebp, ecx
0x10043f47f  ja      short loc_10043F4A8
0x10043f481  lfence
0x10043f484  mov     eax, [rdi+48h]
0x10043f487  mov     r9d, r14d
0x10043f48a  add     r9, rax
0x10043f48d  add     r9, r13; unsigned __int8 *
0x10043f490  lea     rdx, [rax+r13]; unsigned __int8 *
0x10043f494  mov     dword ptr [rsp+0C8h+var_A8], ebp; unsigned int
  ... truncated ...
```

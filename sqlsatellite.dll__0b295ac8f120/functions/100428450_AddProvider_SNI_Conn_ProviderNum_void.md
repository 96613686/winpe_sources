# AddProvider(SNI_Conn *,ProviderNum,void *)

- ea: `0x100428450`
- end: `0x100428e12`
- name: `?AddProvider@@YAKPEAVSNI_Conn@@W4ProviderNum@@PEAX@Z`
- size: `2498`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x100473a60`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x100422710`
- `0x100428450`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042bd30`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100443830`
- `0x100444090`
- `0x10044adb0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004286d5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100428956`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100428b85`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004286d5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100428956`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100428b85`
- `sqldk!SystemThread_TlsIndex` at `0x100428674`
- `sqldk!SystemThread_TlsIndex` at `0x1004287f4`
- `sqldk!SystemThread_TlsIndex` at `0x1004288f3`
- `sqldk!SystemThread_TlsIndex` at `0x100428b22`
- `sqldk!SystemThread_TlsOffset` at `0x10042867d`
- `sqldk!SystemThread_TlsOffset` at `0x1004287fd`
- `sqldk!SystemThread_TlsOffset` at `0x1004288fc`
- `sqldk!SystemThread_TlsOffset` at `0x100428b2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100428698`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100428818`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100428917`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100428b46`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100428698`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100428818`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100428917`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100428b46`

## string_xrefs

- `0x10042847b`: `sql\common\dk\sni\src\sni.cpp`
- `0x100428a19`: `sql\common\dk\sni\src\smux.cpp`
- `0x100428a00`: `ID|SNI%p{.} created by %u#{SNI_Conn}`
- `0x100428c47`: `ID|SNI%p{.} created by %u#{SNI_Conn}`
- `0x100428bb5`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall AddProvider(__int64 a1, int a2, _DWORD *a3)
{
  __int64 v4; // r14
  SOS_UnfairRecursiveMutexExtendedGuarantee **v6; // rdi
  __int64 i; // rax
  int v8; // ecx
  unsigned int v9; // ebx
  const wchar_t *v10; // r9
  void *v11; // r9
  char v12; // al
  __int64 v13; // rbx
  __int64 v14; // rax
  CryptoBase *v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  struct SNI_Provider *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  CryptoBase *v23; // rax
  const wchar_t *v24; // r9
  SOS_UnfairRecursiveMutexExtendedGuarantee **v25; // rbx
  unsigned int v26; // eax
  char *v28; // [rsp+20h] [rbp-A8h]
  __int64 v29; // [rsp+28h] [rbp-A0h]
  __int64 v30; // [rsp+28h] [rbp-A0h]
  __int64 v31; // [rsp+28h] [rbp-A0h]
  __int64 v32; // [rsp+28h] [rbp-A0h]
  __int64 v33; // [rsp+30h] [rbp-98h]

  v4 = a2;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "AddProvider",
      5893,
      L"API|SNI%u#{SNI_Conn}, pConn: %p{SNI_Conn*}, ProvNum: %d{ProviderNum}, pInfo: %p{LPVOID}\n",
      *(_DWORD *)(a1 + 76),
      a1,
      a2,
      a3,
      -2);
  v6 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
  CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v6);
  for ( i = *(_QWORD *)(a1 + 12616); i; i = *(_QWORD *)(i + 8) )
  {
    v8 = *(_DWORD *)(i + 24);
    if ( (_DWORD)v4 == v8 && v8 == 3 && *(_DWORD *)(i + 48) != 5 )
    {
      v9 = 87;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v33) = 87;
        LODWORD(v29) = 0;
        LODWORD(v28) = 10;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "AddProvider",
          5912,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v28,
          v29,
          v33);
      }
      SNISetLastError(10, 87, 50100);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v28) = 87;
        SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 5913, L"RET|SNI%d{WINERR}\n", v28);
      }
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v6[1]);
      goto LABEL_83;
    }
  }
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v6[1]);
  switch ( (_DWORD)v4 )
  {
    case 3:
      v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v22 = *(_QWORD *)(v21 + 256);
      if ( !v22 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v22 = *(_QWORD *)(v21 + 256);
      }
      v23 = (CryptoBase *)operator new(
                            0x178u,
                            *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v22 + 992) + 56LL) + 8LL),
                            1,
                            "sql\\common\\dk\\sni\\src\\sni.cpp",
                            5928,
                            6u);
      v15 = v23;
      if ( v23 )
      {
        CryptoBase::CryptoBase(v23, (struct SNI_Conn *)a1, a3);
        *(_QWORD *)v15 = &Sspi::`vftable';
        if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
          SNIXE_SNI_ENTER_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Sspi",
            1515,
            L"API|SNIpConn: %p{SNI_Conn*}\n",
            a1);
        *((_DWORD *)v15 + 6) = 3;
        *((_QWORD *)v15 + 43) = 0;
        *((_QWORD *)v15 + 44) = 0;
        *((_QWORD *)v15 + 45) = 1;
        *((_QWORD *)v15 + 46) = 1;
        *((_DWORD *)v15 + 11) = (_DWORD)v15 + 44;
        if ( (g_XeSniPkg_enabledBitmap & 8) != 0 )
          SNIXE_SNI_ALLOCATE_ID_ON(
            (_DWORD)v15 + 44,
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Sspi",
            1526,
            "ID|SNI%p{.} created by %u#{SNI_Conn}",
            v15,
            *(_DWORD *)(a1 + 76));
        if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
          SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", "Sspi::Sspi", 1515, v24);
      }
      else
      {
        v15 = 0;
      }
      if ( v15 )
      {
        v9 = (*(__int64 (__fastcall **)(CryptoBase *))(*(_QWORD *)v15 + 152LL))(v15);
        if ( !v9 )
          goto LABEL_80;
        (**(void (__fastcall ***)(void *, __int64))v15)(v15, 1);
        a3[10] = 0;
        a3[11] = 31;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v28) = v9;
          SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 5946, L"RET|SNI%d{WINERR}\n", v28);
        }
      }
      else
      {
        v9 = 14;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v33) = 14;
          LODWORD(v32) = 0;
          LODWORD(v28) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni.cpp",
            "AddProvider",
            5930,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v28,
            v32,
            v33);
        }
        SNISetLastError(10, 14, 50100);
        a3[10] = 0;
        a3[11] = 30;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v28) = 14;
          SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 5935, L"RET|SNI%d{WINERR}\n", v28);
        }
      }
      break;
    case 5:
      v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v20 = *(_QWORD *)(v19 + 256);
      if ( !v20 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v20 = *(_QWORD *)(v19 + 256);
      }
      v15 = (CryptoBase *)operator new(
                            0x98u,
                            *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v20 + 992) + 56LL) + 8LL),
                            1,
                            "sql\\common\\dk\\sni\\src\\sni.cpp",
                            5955,
                            6u);
      if ( v15 )
      {
        *(_QWORD *)v15 = &SNI_Provider::`vftable';
        *((_QWORD *)v15 + 4) = a1;
        *((_QWORD *)v15 + 5) = 1;
        *((_QWORD *)v15 + 1) = 0;
        *((_QWORD *)v15 + 2) = -1;
        *((_DWORD *)v15 + 6) = 10;
        *(_QWORD *)v15 = &Smux::`vftable';
        *((_DWORD *)v15 + 6) = 5;
        *((_QWORD *)v15 + 6) = 0;
        *((_QWORD *)v15 + 7) = 0;
        *((_QWORD *)v15 + 8) = 0;
        *((_QWORD *)v15 + 9) = 0;
        *((_DWORD *)v15 + 20) = 0;
        *((_QWORD *)v15 + 11) = 0;
        *((_BYTE *)v15 + 104) = *(_BYTE *)(a1 + 12804) & 1;
        *((_QWORD *)v15 + 14) = 0;
        *((_DWORD *)v15 + 30) = 0;
        *((_DWORD *)v15 + 31) = 0;
        *((_QWORD *)v15 + 17) = 0;
        *((_BYTE *)v15 + 144) = 0;
        *((_DWORD *)v15 + 11) = (_DWORD)v15 + 44;
        if ( (g_XeSniPkg_enabledBitmap & 8) != 0 )
          SNIXE_SNI_ALLOCATE_ID_ON(
            (_DWORD)v15 + 44,
            "sql\\common\\dk\\sni\\src\\smux.cpp",
            "Smux::Smux",
            4191,
            "ID|SNI%p{.} created by %u#{SNI_Conn}",
            v15,
            *(_DWORD *)(a1 + 76));
      }
      else
      {
        v15 = 0;
      }
      if ( v15 )
      {
        v9 = (*(__int64 (__fastcall **)(CryptoBase *))(*(_QWORD *)v15 + 152LL))(v15);
        if ( !v9 )
        {
LABEL_60:
          IncrementConnBufSize((struct SNI_Conn *)a1, (struct SNI_PROVIDER_INFO *)((char *)&rgProvInfo + 20 * v4));
          goto LABEL_81;
        }
        (**(void (__fastcall ***)(void *, __int64))v15)(v15, 1);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v28) = v9;
          SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 5967, L"RET|SNI%d{WINERR}\n", v28);
        }
      }
      else
      {
        v9 = 14;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v33) = 14;
          LODWORD(v31) = 0;
          LODWORD(v28) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni.cpp",
            "AddProvider",
            5957,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v28,
            v31,
            v33);
        }
        SNISetLastError(10, 14, 50100);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v28) = 14;
          SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 5959, L"RET|SNI%d{WINERR}\n", v28);
        }
      }
      break;
    case 6:
      v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v17 = *(_QWORD *)(v16 + 256);
      if ( !v17 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v17 = *(_QWORD *)(v16 + 256);
      }
      v18 = SslSubsystem::NewSNIProvider(
              *(SslSubsystem **)(*(_QWORD *)(*(_QWORD *)(v17 + 992) + 56LL) + 8LL),
              (struct IMemObj *)a1,
              (struct SNI_Conn *)a3,
              v11);
      v15 = v18;
      if ( !v18 )
      {
        a3[10] = 0;
        a3[11] = 32;
        v9 = 14;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v28) = 14;
          SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 5981, L"RET|SNI%d{WINERR}\n", v28);
        }
        break;
      }
      v9 = (*(__int64 (__fastcall **)(struct SNI_Provider *))(*(_QWORD *)v18 + 152LL))(v18);
      if ( v9 )
      {
        (**(void (__fastcall ***)(void *, __int64))v15)(v15, 1);
        a3[10] = 0;
        a3[11] = 33;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v28) = v9;
          SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 5992, L"RET|SNI%d{WINERR}\n", v28);
        }
        break;
      }
LABEL_80:
      CryptoBase::DeferIncConnBufSize(v15);
LABEL_81:
      v25 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v25);
      *((_QWORD *)v15 + 1) = *(_QWORD *)(a1 + 12616);
      *(_QWORD *)(a1 + 12616) = v15;
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v25[1]);
      v26 = (*(__int64 (__fastcall **)(CryptoBase *, _DWORD *))(*(_QWORD *)v15 + 208LL))(v15, a3);
      v9 = v26;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v28) = v26;
        SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 6056, L"RET|SNI%d{WINERR}\n", v28);
      }
      break;
    case 8:
      v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v14 = *(_QWORD *)(v13 + 256);
      if ( !v14 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v14 = *(_QWORD *)(v13 + 256);
      }
      v15 = (CryptoBase *)operator new(
                            0x58u,
                            *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v14 + 992) + 56LL) + 8LL),
                            1,
                            "sql\\common\\dk\\sni\\src\\sni.cpp",
                            6001,
                            6u);
      if ( v15 )
      {
        *(_QWORD *)v15 = &SNI_Provider::`vftable';
        *((_QWORD *)v15 + 4) = a1;
        *((_QWORD *)v15 + 5) = 1;
        *((_QWORD *)v15 + 1) = 0;
        *((_QWORD *)v15 + 2) = -1;
        *((_DWORD *)v15 + 6) = 10;
        *(_QWORD *)v15 = &CrTrAdditionalInfoProtocol::`vftable';
      }
      else
      {
        v15 = 0;
      }
      if ( !v15 )
      {
        v9 = 14;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v33) = 14;
          LODWORD(v30) = 0;
          LODWORD(v28) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni.cpp",
            "AddProvider",
            6003,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v28,
            v30,
            v33);
        }
        SNISetLastError(10, 14, 50100);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v28) = 14;
          SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 6005, L"RET|SNI%d{WINERR}\n", v28);
        }
        break;
      }
      v9 = (*(__int64 (__fastcall **)(CryptoBase *))(*(_QWORD *)v15 + 152LL))(v15);
      if ( v9 )
      {
        (**(void (__fastcall ***)(void *, __int64))v15)(v15, 1);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v28) = v9;
          SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 6013, L"RET|SNI%d{WINERR}\n", v28);
        }
        break;
      }
      goto LABEL_60;
    default:
      v12 = g_XeSniPkg_enabledBitmap;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        SNIXE_SNI_ERROR_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 6021, L"ERR|SNIProvNum is unknown\n");
        v12 = g_XeSniPkg_enabledBitmap;
      }
      v9 = 87;
      if ( (v12 & 2) != 0 )
      {
        LODWORD(v33) = 87;
        LODWORD(v29) = 0;
        LODWORD(v28) = 10;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "AddProvider",
          6022,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v28,
          v29,
          v33);
      }
      SNISetLastError(10, 87, 50100);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v28) = 87;
        SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 6024, L"RET|SNI%d{WINERR}\n", v28);
      }
      break;
  }
LABEL_83:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "AddProvider", 5893, v10);
  return v9;
}

```

## disassembly

```asm
0x100428450  mov     rax, rsp
0x100428453  push    rbp
0x100428454  push    rsi
0x100428455  push    rdi
0x100428456  push    r12
0x100428458  push    r13
0x10042845a  push    r14
0x10042845c  push    r15
0x10042845e  sub     rsp, 90h
0x100428465  mov     [rsp+0C8h+var_88], 0FFFFFFFFFFFFFFFEh
0x10042846e  mov     [rax+10h], rbx
0x100428472  mov     rbp, r8
0x100428475  movsxd  r14, edx
0x100428478  mov     rsi, rcx
0x10042847b  lea     r15, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100428482  mov     [rax-68h], r15
0x100428486  lea     r13, aAddprovider; "AddProvider"
0x10042848d  mov     [rax-60h], r13
0x100428491  mov     dword ptr [rax-58h], 1705h
0x100428498  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042849f  jz      short loc_1004284CF
0x1004284a1  mov     [rsp+0C8h+var_90], r8
0x1004284a6  mov     dword ptr [rsp+0C8h+var_98], r14d
0x1004284ab  mov     [rsp+0C8h+var_A0], rcx
0x1004284b0  mov     eax, [rcx+4Ch]
0x1004284b3  mov     dword ptr [rsp+0C8h+var_A8], eax
0x1004284b7  lea     r9, aApiSniUSniConn_2; "API|SNI%u#{SNI_Conn}, pConn: %p{SNI_Con"...
0x1004284be  mov     r8d, 1705h; int
0x1004284c4  mov     rdx, r13; char *
0x1004284c7  mov     rcx, r15; char *
0x1004284ca  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004284cf  mov     rdi, [rsi+40h]
0x1004284d3  mov     [rsp+0C8h+var_78], rdi
0x1004284d8  xor     r12d, r12d
0x1004284db  mov     [rsp+0C8h+var_70], r12d
0x1004284e0  mov     rcx, rdi; this
0x1004284e3  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x1004284e8  mov     [rsp+0C8h+var_70], 1
0x1004284f0  mov     rax, [rsi+3148h]
0x1004284f7  test    rax, rax
0x1004284fa  jz      loc_100428596
0x100428500  mov     ecx, [rax+18h]
0x100428503  cmp     r14d, ecx
0x100428506  jnz     short loc_100428513
0x100428508  cmp     ecx, 3
0x10042850b  jnz     short loc_100428513
0x10042850d  cmp     dword ptr [rax+30h], 5
0x100428511  jnz     short loc_100428519
0x100428513  mov     rax, [rax+8]
0x100428517  jmp     short loc_1004284F7
0x100428519  mov     ebx, 57h ; 'W'
0x10042851e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100428525  jz      short loc_100428550
0x100428527  mov     dword ptr [rsp+0C8h+var_98], ebx
0x10042852b  mov     dword ptr [rsp+0C8h+var_A0], r12d
0x100428530  mov     dword ptr [rsp+0C8h+var_A8], 0Ah
0x100428538  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042853f  mov     r8d, 1718h; int
0x100428545  mov     rdx, r13; char *
0x100428548  mov     rcx, r15; char *
0x10042854b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100428550  mov     r8d, 0C3B4h
0x100428556  mov     edx, ebx
0x100428558  mov     ecx, 0Ah
0x10042855d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100428562  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100428569  jz      short loc_100428588
0x10042856b  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x10042856f  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100428576  mov     r8d, 1719h; int
0x10042857c  mov     rdx, r13; char *
0x10042857f  mov     rcx, r15; char *
0x100428582  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100428587  nop
0x100428588  mov     rcx, [rdi+8]; this
0x10042858c  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100428591  jmp     loc_100428DDB
0x100428596  mov     rcx, [rdi+8]; this
0x10042859a  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x10042859f  mov     ecx, r14d
0x1004285a2  sub     ecx, 3
0x1004285a5  jz      loc_100428B0E
0x1004285ab  sub     ecx, 2
0x1004285ae  jz      loc_1004288DF
0x1004285b4  sub     ecx, 1
0x1004285b7  jz      loc_1004287EB
0x1004285bd  cmp     ecx, 2
0x1004285c0  jz      loc_100428660
0x1004285c6  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004285cc  test    al, 2
0x1004285ce  jz      short loc_1004285EE
0x1004285d0  lea     r9, aErrSniprovnumI; "ERR|SNIProvNum is unknown\n"
0x1004285d7  mov     r8d, 1785h; int
0x1004285dd  mov     rdx, r13; char *
0x1004285e0  mov     rcx, r15; char *
0x1004285e3  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004285e8  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004285ee  mov     ebx, 57h ; 'W'
0x1004285f3  test    al, 2
0x1004285f5  jz      short loc_100428620
0x1004285f7  mov     dword ptr [rsp+0C8h+var_98], ebx
0x1004285fb  mov     dword ptr [rsp+0C8h+var_A0], r12d
0x100428600  mov     dword ptr [rsp+0C8h+var_A8], 0Ah
0x100428608  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042860f  mov     r8d, 1786h; int
0x100428615  mov     rdx, r13; char *
0x100428618  mov     rcx, r15; char *
0x10042861b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100428620  mov     r8d, 0C3B4h
0x100428626  mov     edx, ebx
0x100428628  mov     ecx, 0Ah
0x10042862d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100428632  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100428639  jz      loc_100428DDB
0x10042863f  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x100428643  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10042864a  mov     r8d, 1788h; int
0x100428650  mov     rdx, r13; char *
0x100428653  mov     rcx, r15; char *
0x100428656  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10042865b  jmp     loc_100428DDB
0x100428660  mov     [rsp+0C8h+arg_0], 1771h
0x10042866b  mov     rdx, gs:58h
0x100428674  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10042867b  mov     ecx, [rax]
0x10042867d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100428684  mov     ebx, [rax]
0x100428686  add     rbx, [rdx+rcx*8]
0x10042868a  mov     rax, [rbx+100h]
0x100428691  test    rax, rax
0x100428694  jnz     short loc_1004286A5
0x100428696  xor     ecx, ecx
0x100428698  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042869e  mov     rax, [rbx+100h]
0x1004286a5  mov     rax, [rax+3E0h]
0x1004286ac  mov     rcx, [rax+38h]
0x1004286b0  mov     rdx, [rcx+8]
0x1004286b4  mov     [rsp+0C8h+arg_18], rdx
0x1004286bc  mov     byte ptr [rsp+0C8h+var_A0], 6
0x1004286c1  mov     dword ptr [rsp+0C8h+var_A8], 1771h
0x1004286c9  mov     r9, r15
0x1004286cc  mov     ecx, 58h ; 'X'
0x1004286d1  lea     r8d, [rcx-57h]
0x1004286d5  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004286db  mov     rdi, rax
0x1004286de  mov     [rsp+0C8h+var_80], rax
0x1004286e3  test    rax, rax
0x1004286e6  jz      short loc_10042871D
0x1004286e8  lea     rax, ??_7SNI_Provider@@6B@; const SNI_Provider::`vftable'
0x1004286ef  mov     [rdi], rax
0x1004286f2  mov     [rdi+20h], rsi
0x1004286f6  mov     qword ptr [rdi+28h], 1
0x1004286fe  mov     [rdi+8], r12
0x100428702  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x10042870a  mov     dword ptr [rdi+18h], 0Ah
0x100428711  lea     rax, ??_7CrTrAdditionalInfoProtocol@@6B@; const CrTrAdditionalInfoProtocol::`vftable'
0x100428718  mov     [rdi], rax
0x10042871b  jmp     short loc_100428720
0x10042871d  mov     rdi, r12
0x100428720  test    rdi, rdi
0x100428723  jnz     short loc_10042879A
0x100428725  lea     ebx, [rdi+0Eh]
0x100428728  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042872f  jz      short loc_10042875A
0x100428731  mov     dword ptr [rsp+0C8h+var_98], ebx
0x100428735  mov     dword ptr [rsp+0C8h+var_A0], r12d
0x10042873a  mov     dword ptr [rsp+0C8h+var_A8], 0Ah
0x100428742  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100428749  mov     r8d, 1773h; int
0x10042874f  mov     rdx, r13; char *
0x100428752  mov     rcx, r15; char *
0x100428755  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042875a  mov     r8d, 0C3B4h
0x100428760  mov     edx, ebx
0x100428762  mov     ecx, 0Ah
0x100428767  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042876c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100428773  jz      loc_100428DDB
0x100428779  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x10042877d  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100428784  mov     r8d, 1775h; int
0x10042878a  mov     rdx, r13; char *
0x10042878d  mov     rcx, r15; char *
0x100428790  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100428795  jmp     loc_100428DDB
0x10042879a  mov     rax, [rdi]
0x10042879d  mov     rcx, rdi
0x1004287a0  call    qword ptr [rax+98h]
0x1004287a6  mov     ebx, eax
0x1004287a8  test    eax, eax
0x1004287aa  jz      loc_100428AF2
0x1004287b0  mov     rax, [rdi]
0x1004287b3  mov     edx, 1
0x1004287b8  mov     rcx, rdi
0x1004287bb  call    qword ptr [rax]
0x1004287bd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004287c4  jz      loc_100428DDB
0x1004287ca  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x1004287ce  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004287d5  mov     r8d, 177Dh; int
0x1004287db  mov     rdx, r13; char *
0x1004287de  mov     rcx, r15; char *
0x1004287e1  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004287e6  jmp     loc_100428DDB
0x1004287eb  mov     rdx, gs:58h
0x1004287f4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004287fb  mov     ecx, [rax]
0x1004287fd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100428804  mov     ebx, [rax]
0x100428806  add     rbx, [rdx+rcx*8]
0x10042880a  mov     rax, [rbx+100h]
0x100428811  test    rax, rax
0x100428814  jnz     short loc_100428825
0x100428816  xor     ecx, ecx
0x100428818  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042881e  mov     rax, [rbx+100h]
0x100428825  mov     rax, [rax+3E0h]
0x10042882c  mov     rcx, [rax+38h]
0x100428830  mov     r8, rbp; struct SNI_Conn *
0x100428833  mov     rdx, rsi; struct IMemObj *
0x100428836  mov     rcx, [rcx+8]; this
0x10042883a  call    ?NewSNIProvider@SslSubsystem@@YAPEAVSNI_Provider@@PEAVIMemObj@@PEAVSNI_Conn@@PEAX@Z; SslSubsystem::NewSNIProvider(IMemObj *,SNI_Conn *,void *)
0x10042883f  mov     rdi, rax
0x100428842  test    rax, rax
0x100428845  jnz     short loc_100428883
0x100428847  mov     [rbp+28h], r12d
0x10042884b  mov     dword ptr [rbp+2Ch], 20h ; ' '
0x100428852  lea     ebx, [rax+0Eh]
0x100428855  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042885c  jz      loc_100428DDB
0x100428862  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x100428866  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10042886d  mov     r8d, 175Dh; int
0x100428873  mov     rdx, r13; char *
0x100428876  mov     rcx, r15; char *
0x100428879  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10042887e  jmp     loc_100428DDB
0x100428883  mov     rax, [rax]
0x100428886  mov     rcx, rdi
0x100428889  call    qword ptr [rax+98h]
0x10042888f  mov     ebx, eax
0x100428891  test    eax, eax
0x100428893  jz      loc_100428D63
0x100428899  mov     rax, [rdi]
0x10042889c  mov     edx, 1
0x1004288a1  mov     rcx, rdi
0x1004288a4  call    qword ptr [rax]
0x1004288a6  mov     [rbp+28h], r12d
0x1004288aa  mov     dword ptr [rbp+2Ch], 21h ; '!'
0x1004288b1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004288b8  jz      loc_100428DDB
0x1004288be  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x1004288c2  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004288c9  mov     r8d, 1768h; int
0x1004288cf  mov     rdx, r13; char *
0x1004288d2  mov     rcx, r15; char *
0x1004288d5  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004288da  jmp     loc_100428DDB
0x1004288df  mov     [rsp+0C8h+arg_0], 1743h
0x1004288ea  mov     rdx, gs:58h
0x1004288f3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004288fa  mov     ecx, [rax]
0x1004288fc  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100428903  mov     ebx, [rax]
0x100428905  add     rbx, [rdx+rcx*8]
0x100428909  mov     rax, [rbx+100h]
0x100428910  test    rax, rax
0x100428913  jnz     short loc_100428924
0x100428915  xor     ecx, ecx
0x100428917  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042891d  mov     rax, [rbx+100h]
0x100428924  mov     rax, [rax+3E0h]
0x10042892b  mov     rcx, [rax+38h]
0x10042892f  mov     rdx, [rcx+8]
0x100428933  mov     [rsp+0C8h+arg_18], rdx
0x10042893b  mov     byte ptr [rsp+0C8h+var_A0], 6
0x100428940  mov     dword ptr [rsp+0C8h+var_A8], 1743h
0x100428948  mov     r9, r15
0x10042894b  mov     ecx, 98h
0x100428950  mov     r8d, 1
0x100428956  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10042895c  mov     rdi, rax
0x10042895f  mov     [rsp+0C8h+var_80], rax
0x100428964  test    rax, rax
0x100428967  jz      loc_100428A28
0x10042896d  lea     rax, ??_7SNI_Provider@@6B@; const SNI_Provider::`vftable'
0x100428974  mov     [rdi], rax
0x100428977  mov     [rdi+20h], rsi
0x10042897b  mov     qword ptr [rdi+28h], 1
0x100428983  mov     [rdi+8], r12
0x100428987  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x10042898f  mov     dword ptr [rdi+18h], 0Ah
0x100428996  lea     rax, ??_7Smux@@6B@; const Smux::`vftable'
0x10042899d  mov     [rdi], rax
0x1004289a0  mov     dword ptr [rdi+18h], 5
0x1004289a7  mov     [rdi+30h], r12
0x1004289ab  mov     [rdi+38h], r12
0x1004289af  mov     [rdi+40h], r12
0x1004289b3  mov     [rdi+48h], r12
0x1004289b7  mov     [rdi+50h], r12d
  ... truncated ...
```

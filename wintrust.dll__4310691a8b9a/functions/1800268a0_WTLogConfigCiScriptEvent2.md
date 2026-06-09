# WTLogConfigCiScriptEvent2

- ea: `0x1800268a0`
- end: `0x180026f41`
- name: `WTLogConfigCiScriptEvent2`
- size: `1697`
- prototype: `__int64 __fastcall(__int64, void *, const WCHAR *, __int64, const WCHAR *, __int64, LPCGUID ActivityId)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180026830`

## callees

- `0x18002640c`
- `0x1800268a0`
- `0x180027dac`
- `0x18002cc80`
- `0x18002d060`
- `0x18002d598`
- `0x180042a4c`
- `0x180042b94`
- `0x18004de46`
- `0x18004de6a`
- `0x18004deb0`
- `0x18004df40`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180026de6`
- `msvcrt!_snwprintf_s` at `0x180026de6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026efe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026efe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026c09`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026c09`
- `ntdll!RtlInitUnicodeString` at `0x180026a04`
- `ntdll!RtlInitUnicodeString` at `0x180026c6d`
- `ntdll!RtlInitUnicodeString` at `0x180026e3d`
- `ntdll!RtlInitUnicodeString` at `0x180026e4e`
- `ntdll!RtlInitUnicodeString` at `0x180026a04`
- `ntdll!RtlInitUnicodeString` at `0x180026c6d`
- `ntdll!RtlInitUnicodeString` at `0x180026e3d`
- `ntdll!RtlInitUnicodeString` at `0x180026e4e`
- `CRYPT32!CryptSIPRetrieveSubjectGuidForCatalogFile` at `0x180026a81`
- `CRYPT32!CryptSIPRetrieveSubjectGuidForCatalogFile` at `0x180026a81`

## pseudocode

```c
__int64 __fastcall WTLogConfigCiScriptEvent2(
        __int64 a1,
        void *a2,
        const WCHAR *a3,
        __int64 a4,
        const WCHAR *a5,
        __int64 a6,
        LPCGUID ActivityId)
{
  __int64 result; // rax
  __int128 *v11; // rsi
  int v12; // edi
  __int128 *v13; // rax
  __int64 v14; // rax
  void *v15; // rcx
  int ResourcesFromMsg; // eax
  unsigned int v17; // r8d
  int v18; // r9d
  int v19; // r9d
  int v20; // r9d
  unsigned __int64 v21; // r9
  const WCHAR *v22; // rdx
  const EVENT_DESCRIPTOR *v23; // rdx
  ULONG v24; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  LPVOID lpOutBuffera; // [rsp+20h] [rbp-E0h]
  DWORD nOutBufferSize[2]; // [rsp+28h] [rbp-D8h]
  LPDWORD lpBytesReturned; // [rsp+30h] [rbp-D0h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-C8h]
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v36[2]; // [rsp+70h] [rbp-90h] BYREF
  int InBuffer; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+84h] [rbp-7Ch] BYREF
  _DWORD Buf2[4]; // [rsp+88h] [rbp-78h] BYREF
  DWORD BytesReturned; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  REGHANDLE RegHandle; // [rsp+A8h] [rbp-58h] BYREF
  _WORD v43[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v44; // [rsp+B4h] [rbp-4Ch]
  wchar_t *v45; // [rsp+B8h] [rbp-48h]
  PCWSTR SourceString; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING v48; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING v49; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v50; // [rsp+F8h] [rbp-8h] BYREF
  GUID pgSubject; // [rsp+108h] [rbp+8h] BYREF
  __int128 v52; // [rsp+118h] [rbp+18h] BYREF
  _BYTE OutBuffer[4]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v54; // [rsp+134h] [rbp+34h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  __int64 v56; // [rsp+158h] [rbp+58h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1130h] [rbp+1030h] BYREF
  char v58; // [rsp+1140h] [rbp+1040h] BYREF
  __int128 *v59; // [rsp+1150h] [rbp+1050h]
  __int64 v60; // [rsp+1158h] [rbp+1058h]
  __int128 *v61; // [rsp+1160h] [rbp+1060h]
  __int64 v62; // [rsp+1168h] [rbp+1068h]
  __int64 v63; // [rsp+1170h] [rbp+1070h]
  __int64 v64; // [rsp+1178h] [rbp+1078h]
  __int64 *v65; // [rsp+1180h] [rbp+1080h]
  __int64 v66; // [rsp+1188h] [rbp+1088h]
  __int128 *v67; // [rsp+1190h] [rbp+1090h]
  __int64 v68; // [rsp+1198h] [rbp+1098h]
  __int128 *v69; // [rsp+11A0h] [rbp+10A0h]
  __int64 v70; // [rsp+11A8h] [rbp+10A8h]
  int *v71; // [rsp+11B0h] [rbp+10B0h]
  __int64 v72; // [rsp+11B8h] [rbp+10B8h]
  char v73; // [rsp+11C0h] [rbp+10C0h] BYREF
  char v74; // [rsp+11D0h] [rbp+10D0h] BYREF
  char v75; // [rsp+11E0h] [rbp+10E0h] BYREF
  char v76; // [rsp+11F0h] [rbp+10F0h] BYREF
  char v77; // [rsp+1200h] [rbp+1100h] BYREF
  char v78; // [rsp+1210h] [rbp+1110h] BYREF
  char v79; // [rsp+1220h] [rbp+1120h] BYREF
  char v80; // [rsp+1230h] [rbp+1130h] BYREF
  char v81; // [rsp+1240h] [rbp+1140h] BYREF
  char v82; // [rsp+1250h] [rbp+1150h] BYREF
  char v83; // [rsp+1260h] [rbp+1160h] BYREF
  char v84; // [rsp+1270h] [rbp+1170h] BYREF
  char v85; // [rsp+1280h] [rbp+1180h] BYREF
  char v86; // [rsp+1290h] [rbp+1190h] BYREF
  char v87; // [rsp+12A0h] [rbp+11A0h] BYREF
  char v88; // [rsp+12B0h] [rbp+11B0h] BYREF
  __int128 *v89; // [rsp+12C0h] [rbp+11C0h]
  __int64 v90; // [rsp+12C8h] [rbp+11C8h]
  __int128 v91; // [rsp+12D0h] [rbp+11D0h] BYREF
  __int128 v92; // [rsp+12E0h] [rbp+11E0h]
  __int128 v93; // [rsp+12F0h] [rbp+11F0h] BYREF
  int v94; // [rsp+1300h] [rbp+1200h]
  wchar_t Buffer[8]; // [rsp+1308h] [rbp+1208h] BYREF
  __int128 v96; // [rsp+1318h] [rbp+1218h]
  __int128 v97; // [rsp+1328h] [rbp+1228h]
  wil::details::in1diag3 *retaddr; // [rsp+1378h] [rbp+1278h]

  SourceString = a5;
  RegHandle = 0;
  if ( a6 && ActivityId )
  {
    result = GetEventHandle(&RegHandle);
    if ( (int)result < 0 )
      return result;
    WORD2(v30) = 0;
    LOWORD(v31) = 0;
    v36[0] = 0x20000;
    v36[1] = &qword_180056E08;
    v41 = 0;
    v94 = 0;
    v43[1] = 48;
    v44 = 0;
    v45 = Buffer;
    DestinationString = 0;
    v48 = 0;
    v35 = 0;
    v93 = 0;
    WORD2(v31) = 0;
    v91 = 0;
    LOWORD(v32) = 0;
    v92 = 0;
    WORD2(v32) = 0;
    LOWORD(v33) = 0;
    LOWORD(v30) = 0;
    *(_OWORD *)Buffer = 0;
    Buf2[0] = -566945214;
    v96 = 0;
    Buf2[1] = 298880601;
    v97 = 0;
    Buf2[2] = -1073723508;
    Buf2[3] = -292175281;
    pgSubject = 0;
    WORD2(v33) = 0;
    LOWORD(v34) = 0;
    v49 = 0;
    v50 = 0;
    v52 = 0;
    v38 = WintrustUserWriteabilityCheckWorker(a2);
    RtlInitUnicodeString(&DestinationString, a3);
    EventDataWriteUnicodeString(
      (unsigned int)&UserData,
      (unsigned int)&v58,
      (unsigned int)v36,
      (unsigned int)&DestinationString,
      (__int64)&v30 + 4);
    v11 = *(__int128 **)(a6 + 24);
    v12 = *(_DWORD *)(a6 + 20);
    if ( a2 )
    {
      WintrustGetHash((int)a2, (int)L"SHA1", 20, (int)&v93);
      if ( *(_DWORD *)a6 > 0x50u
        && *(_QWORD *)(a6 + 160)
        && *(_DWORD *)(a6 + 152) == 32
        && CryptSIPRetrieveSubjectGuidForCatalogFile(a3, a2, &pgSubject)
        && !memcmp_0(&pgSubject, Buf2, 0x10u) )
      {
        v13 = *(__int128 **)(a6 + 160);
        v91 = *v13;
        v92 = v13[1];
      }
      else
      {
        WintrustGetHash((int)a2, (int)L"SHA256", 32, (int)&v91);
      }
      if ( !v11 )
      {
        v11 = &v91;
        v12 = 32;
      }
    }
    else if ( !v11 )
    {
      v11 = &v91;
      v12 = 32;
      goto LABEL_19;
    }
    if ( v12 == 20 )
    {
      v59 = v11;
      v60 = 20;
      goto LABEL_20;
    }
    if ( v12 != 32 )
    {
LABEL_20:
      v68 = 20;
      v67 = &v93;
      if ( v12 != 20 )
      {
        v60 = 20;
        v59 = &v93;
      }
      v70 = 32;
      v69 = &v91;
      if ( v12 != 32 )
      {
        v62 = 32;
        v61 = &v91;
      }
      v63 = a6 + 4;
      v64 = 4;
      if ( a2 )
      {
        InBuffer = 196610;
        memset_0(OutBuffer, 0, 0x1000u);
        BytesReturned = 0;
        if ( DeviceIoControl(a2, 0x900EBu, &InBuffer, 4u, OutBuffer, 0x1000u, &BytesReturned, 0) )
        {
          if ( v54 == 2 )
          {
            v14 = v55;
          }
          else
          {
            if ( v54 != 3 )
              goto LABEL_31;
            v14 = v56;
          }
          v41 = v14;
        }
      }
LABEL_31:
      v65 = &v41;
      v66 = 8;
      v71 = &v38;
      v72 = 4;
      RtlInitUnicodeString(&v48, SourceString);
      EventDataWriteUnicodeString(
        (unsigned int)&v73,
        (unsigned int)&v74,
        (unsigned int)v36,
        (unsigned int)&v48,
        (__int64)&v31);
      if ( a1 )
      {
        v15 = *(void **)(a1 + 112);
        if ( v15 )
        {
          ResourcesFromMsg = GetResourcesFromMsg(v15);
          if ( ResourcesFromMsg < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xFA0,
              v17,
              (const char *)(unsigned int)ResourcesFromMsg,
              lpOutBuffer);
        }
      }
      EventDataWriteUnicodeString((unsigned int)&v75, (unsigned int)&v76, (unsigned int)v36, v35, (__int64)&v31 + 4);
      if ( v35 )
        v18 = v35 + 16;
      else
        v18 = 0;
      EventDataWriteUnicodeString((unsigned int)&v77, (unsigned int)&v78, (unsigned int)v36, v18, (__int64)&v32);
      if ( v35 )
        v19 = v35 + 32;
      else
        v19 = 0;
      EventDataWriteUnicodeString((unsigned int)&v79, (unsigned int)&v80, (unsigned int)v36, v19, (__int64)&v32 + 4);
      if ( v35 )
        v20 = v35 + 48;
      else
        v20 = 0;
      EventDataWriteUnicodeString((unsigned int)&v81, (unsigned int)&v82, (unsigned int)v36, v20, (__int64)&v33);
      if ( v35 )
        v21 = *(_QWORD *)(v35 + 64);
      else
        v21 = 0;
      LODWORD(lpOverlapped) = (unsigned __int16)v21;
      LODWORD(lpBytesReturned) = WORD1(v21);
      nOutBufferSize[0] = WORD2(v21);
      LODWORD(lpOutBuffera) = HIWORD(v21);
      LOWORD(v30) = _snwprintf_s(
                      Buffer,
                      0x18u,
                      0xFFFFFFFFFFFFFFFFuLL,
                      L"%hu.%hu.%hu.%hu",
                      lpOutBuffera,
                      *(_QWORD *)nOutBufferSize,
                      lpBytesReturned,
                      lpOverlapped,
                      v30,
                      v31,
                      v32,
                      v33,
                      v34);
      v43[0] = 2 * v30;
      EventDataWriteUnicodeString(
        (unsigned int)&v83,
        (unsigned int)&v84,
        (unsigned int)v36,
        (unsigned int)v43,
        (__int64)&v30);
      if ( *(_DWORD *)a6 > 0xC8u )
      {
        v22 = *(const WCHAR **)(a6 + 192);
        v52 = *(_OWORD *)(a6 + 168);
        RtlInitUnicodeString(&v49, v22);
        RtlInitUnicodeString(&v50, *(PCWSTR *)(a6 + 200));
      }
      EventDataWriteUnicodeString(
        (unsigned int)&v85,
        (unsigned int)&v86,
        (unsigned int)v36,
        (unsigned int)&v49,
        (__int64)&v33 + 4);
      EventDataWriteUnicodeString(
        (unsigned int)&v87,
        (unsigned int)&v88,
        (unsigned int)v36,
        (unsigned int)&v50,
        (__int64)&v34);
      v90 = 16;
      v89 = &v52;
      if ( *(_DWORD *)(a6 + 8) == 3 )
      {
        v23 = (const EVENT_DESCRIPTOR *)WldpScriptFileAudited;
      }
      else
      {
        if ( *(_DWORD *)(a6 + 8) != 2 )
        {
          v23 = &WldpScriptFileAllowed;
          v24 = 21;
          goto LABEL_55;
        }
        v23 = (const EVENT_DESCRIPTOR *)WldpScriptFileDisabled;
      }
      v24 = 26;
LABEL_55:
      EventWriteTransfer(RegHandle, v23, ActivityId, 0, v24, &UserData);
      SIPolicyFreeResources(&v35);
      return 0;
    }
LABEL_19:
    v61 = v11;
    v62 = 32;
    goto LABEL_20;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800268a0  mov     [rsp-8+arg_18], rbx
0x1800268a5  push    rbp
0x1800268a6  push    rsi
0x1800268a7  push    rdi
0x1800268a8  push    r12
0x1800268aa  push    r13
0x1800268ac  push    r14
0x1800268ae  push    r15
0x1800268b0  lea     rbp, [rsp-1240h]
0x1800268b8  mov     eax, 1340h
0x1800268bd  call    _alloca_probe
0x1800268c2  sub     rsp, rax
0x1800268c5  mov     rax, cs:__security_cookie
0x1800268cc  xor     rax, rsp
0x1800268cf  mov     [rbp+1270h+var_38], rax
0x1800268d6  mov     rbx, [rbp+1270h+arg_28]
0x1800268dd  xor     edi, edi
0x1800268df  mov     rax, [rbp+1270h+arg_20]
0x1800268e6  mov     r15, r8
0x1800268e9  mov     r12, [rbp+1270h+ActivityId]
0x1800268f0  mov     r14, rdx
0x1800268f3  mov     [rbp+1270h+SourceString], rax
0x1800268f7  mov     r13, rcx
0x1800268fa  mov     [rbp+1270h+RegHandle], rdi
0x1800268fe  test    rbx, rbx
0x180026901  jz      loc_180026F12
0x180026907  test    r12, r12
0x18002690a  jz      loc_180026F12
0x180026910  lea     rcx, [rbp+1270h+RegHandle]; unsigned __int64 *
0x180026914  call    ?GetEventHandle@@YAJPEA_K@Z; GetEventHandle(unsigned __int64 *)
0x180026919  test    eax, eax
0x18002691b  js      loc_180026F17
0x180026921  xorps   xmm0, xmm0
0x180026924  mov     [rsp+1370h+var_132C], di
0x180026929  xorps   xmm1, xmm1
0x18002692c  mov     word ptr [rsp+1370h+var_1328], di
0x180026931  lea     rax, qword_180056E08
0x180026938  mov     [rsp+1370h+var_1300], 20000h
0x180026941  mov     [rsp+1370h+var_12F8], rax
0x180026946  mov     rcx, r14; Handle
0x180026949  xor     eax, eax
0x18002694b  mov     [rbp+1270h+var_12D0], rdi
0x18002694f  mov     [rbp+1270h+var_70], eax
0x180026955  lea     eax, [rdi+30h]
0x180026958  mov     [rbp+1270h+var_12BE], ax
0x18002695c  xor     eax, eax
0x18002695e  mov     [rbp+1270h+var_12BC], eax
0x180026961  lea     rax, [rbp+1270h+Buffer]
0x180026968  mov     [rbp+1270h+var_12B8], rax
0x18002696c  movups  xmmword ptr [rbp+1270h+DestinationString.Length], xmm0
0x180026970  mov     [rbp+1270h+var_12EC], edi
0x180026973  movups  xmmword ptr [rbp+1270h+var_1298.Length], xmm1
0x180026977  mov     [rsp+1370h+var_1308], rdi
0x18002697c  movups  [rbp+1270h+var_80], xmm0
0x180026983  mov     [rsp+1370h+var_1324], di
0x180026988  movups  [rbp+1270h+var_A0], xmm1
0x18002698f  mov     [rsp+1370h+var_1320], di
0x180026994  movups  [rbp+1270h+var_90], xmm1
0x18002699b  mov     [rsp+1370h+var_131C], di
0x1800269a0  mov     [rsp+1370h+var_1318], di
0x1800269a5  mov     [rsp+1370h+var_1330], di
0x1800269aa  movups  xmmword ptr [rbp+1270h+Buffer], xmm0
0x1800269b1  mov     [rbp+1270h+Buf2], 0DE351A42h
0x1800269b8  movups  [rbp+1270h+var_58], xmm0
0x1800269bf  mov     [rbp+1270h+var_12E4], 11D08E59h
0x1800269c6  movups  [rbp+1270h+var_48], xmm0
0x1800269cd  mov     [rbp+1270h+var_12E0], 0C000478Ch
0x1800269d4  mov     [rbp+1270h+var_12DC], 0EE95C24Fh
0x1800269db  movups  xmmword ptr [rbp+1270h+pgSubject.Data1], xmm0
0x1800269df  mov     [rsp+1370h+var_1314], di
0x1800269e4  mov     word ptr [rsp+1370h+var_1310], di
0x1800269e9  movups  xmmword ptr [rbp+1270h+var_1288.Length], xmm0
0x1800269ed  movups  xmmword ptr [rbp+1270h+var_1278.Length], xmm1
0x1800269f1  movups  [rbp+1270h+var_1258], xmm0
0x1800269f5  call    ?WintrustUserWriteabilityCheckWorker@@YAHPEAX@Z; WintrustUserWriteabilityCheckWorker(void *)
0x1800269fa  mov     rdx, r15; SourceString
0x1800269fd  mov     [rbp+1270h+var_12EC], eax
0x180026a00  lea     rcx, [rbp+1270h+DestinationString]; DestinationString
0x180026a04  call    cs:__imp_RtlInitUnicodeString
0x180026a0a  lea     rax, [rsp+1370h+var_132C]
0x180026a0f  lea     r9, [rbp+1270h+DestinationString]
0x180026a13  mov     [rsp+1370h+lpOutBuffer], rax
0x180026a18  lea     r8, [rsp+1370h+var_1300]
0x180026a1d  lea     rdx, [rbp+1270h+var_230]
0x180026a24  lea     rcx, [rbp+1270h+UserData]
0x180026a2b  call    EventDataWriteUnicodeString
0x180026a30  mov     rsi, [rbx+18h]
0x180026a34  mov     ecx, 20h ; ' '
0x180026a39  mov     edi, [rbx+14h]
0x180026a3c  test    r14, r14
0x180026a3f  jz      loc_180026B0C
0x180026a45  lea     r8d, [rcx-0Ch]
0x180026a49  mov     rcx, r14
0x180026a4c  lea     r9, [rbp+1270h+var_80]
0x180026a53  lea     rdx, aSha1; "SHA1"
0x180026a5a  call    WintrustGetHash
0x180026a5f  cmp     dword ptr [rbx], 50h ; 'P'
0x180026a62  jbe     short loc_180026AC1
0x180026a64  cmp     qword ptr [rbx+0A0h], 0
0x180026a6c  jz      short loc_180026AC1
0x180026a6e  cmp     dword ptr [rbx+98h], 20h ; ' '
0x180026a75  jnz     short loc_180026AC1
0x180026a77  lea     r8, [rbp+1270h+pgSubject]; pgSubject
0x180026a7b  mov     rdx, r14; hFileIn
0x180026a7e  mov     rcx, r15; FileName
0x180026a81  call    cs:__imp_CryptSIPRetrieveSubjectGuidForCatalogFile
0x180026a87  xor     r15d, r15d
0x180026a8a  test    eax, eax
0x180026a8c  jz      short loc_180026AC4
0x180026a8e  lea     r8d, [r15+10h]; Size
0x180026a92  lea     rdx, [rbp+1270h+Buf2]; Buf2
0x180026a96  lea     rcx, [rbp+1270h+pgSubject]; Buf1
0x180026a9a  call    memcmp_0
0x180026a9f  test    eax, eax
0x180026aa1  jnz     short loc_180026AC4
0x180026aa3  mov     rax, [rbx+0A0h]
0x180026aaa  movups  xmm0, xmmword ptr [rax]
0x180026aad  movups  [rbp+1270h+var_A0], xmm0
0x180026ab4  movups  xmm1, xmmword ptr [rax+10h]
0x180026ab8  movups  [rbp+1270h+var_90], xmm1
0x180026abf  jmp     short loc_180026AE0
0x180026ac1  xor     r15d, r15d
0x180026ac4  lea     r9, [rbp+1270h+var_A0]
0x180026acb  mov     r8d, 20h ; ' '
0x180026ad1  lea     rdx, aSha256; "SHA256"
0x180026ad8  mov     rcx, r14
0x180026adb  call    WintrustGetHash
0x180026ae0  mov     ecx, 20h ; ' '
0x180026ae5  test    rsi, rsi
0x180026ae8  jnz     short loc_180026AF3
0x180026aea  lea     rsi, [rbp+1270h+var_A0]
0x180026af1  mov     edi, ecx
0x180026af3  cmp     edi, 14h
0x180026af6  jnz     short loc_180026B1F
0x180026af8  mov     [rbp+1270h+var_220], rsi
0x180026aff  mov     [rbp+1270h+var_218], 14h
0x180026b0a  jmp     short loc_180026B35
0x180026b0c  xor     r15d, r15d
0x180026b0f  test    rsi, rsi
0x180026b12  jnz     short loc_180026AF3
0x180026b14  lea     rsi, [rbp+1270h+var_A0]
0x180026b1b  mov     edi, ecx
0x180026b1d  jmp     short loc_180026B23
0x180026b1f  cmp     edi, ecx
0x180026b21  jnz     short loc_180026B35
0x180026b23  mov     [rbp+1270h+var_210], rsi
0x180026b2a  mov     [rbp+1270h+var_208], 20h ; ' '
0x180026b35  mov     [rbp+1270h+var_1D8], 14h
0x180026b40  lea     rax, [rbp+1270h+var_80]
0x180026b47  mov     [rbp+1270h+var_1E0], rax
0x180026b4e  cmp     edi, 14h
0x180026b51  jz      short loc_180026B6C
0x180026b53  lea     rax, [rbp+1270h+var_80]
0x180026b5a  mov     [rbp+1270h+var_218], 14h
0x180026b65  mov     [rbp+1270h+var_220], rax
0x180026b6c  mov     [rbp+1270h+var_1C8], 20h ; ' '
0x180026b77  lea     rax, [rbp+1270h+var_A0]
0x180026b7e  mov     [rbp+1270h+var_1D0], rax
0x180026b85  cmp     edi, ecx
0x180026b87  jz      short loc_180026BA2
0x180026b89  lea     rax, [rbp+1270h+var_A0]
0x180026b90  mov     [rbp+1270h+var_208], 20h ; ' '
0x180026b9b  mov     [rbp+1270h+var_210], rax
0x180026ba2  lea     rax, [rbx+4]
0x180026ba6  mov     esi, 4
0x180026bab  mov     [rbp+1270h+var_200], rax
0x180026bb2  mov     [rbp+1270h+var_1F8], rsi
0x180026bb9  lea     edi, [rsi-1]
0x180026bbc  test    r14, r14
0x180026bbf  jz      short loc_180026C37
0x180026bc1  mov     edi, 1000h
0x180026bc6  mov     [rbp+1270h+InBuffer], 30002h
0x180026bcd  mov     r8d, edi; Size
0x180026bd0  lea     rcx, [rbp+1270h+OutBuffer]; void *
0x180026bd4  xor     edx, edx; Val
0x180026bd6  call    memset_0
0x180026bdb  mov     [rsp+1370h+lpOverlapped], r15; lpOverlapped
0x180026be0  lea     rax, [rbp+1270h+BytesReturned]
0x180026be4  mov     [rsp+1370h+lpBytesReturned], rax; lpBytesReturned
0x180026be9  lea     r8, [rbp+1270h+InBuffer]; lpInBuffer
0x180026bed  lea     rax, [rbp+1270h+OutBuffer]
0x180026bf1  mov     [rsp+1370h+nOutBufferSize], edi; nOutBufferSize
0x180026bf5  mov     r9d, esi; nInBufferSize
0x180026bf8  mov     [rsp+1370h+lpOutBuffer], rax; lpOutBuffer
0x180026bfd  mov     edx, 900EBh; dwIoControlCode
0x180026c02  mov     [rbp+1270h+BytesReturned], r15d
0x180026c06  mov     rcx, r14; hDevice
0x180026c09  call    cs:__imp_DeviceIoControl
0x180026c0f  lea     r14d, [rsi-2]
0x180026c13  lea     edi, [rsi-1]
0x180026c16  test    eax, eax
0x180026c18  jz      short loc_180026C3D
0x180026c1a  cmp     [rbp+1270h+var_123C], r14w
0x180026c1f  jnz     short loc_180026C2B
0x180026c21  mov     rax, [rbp+1270h+var_1228]
0x180026c25  mov     [rbp+1270h+var_12D0], rax
0x180026c29  jmp     short loc_180026C3D
0x180026c2b  cmp     [rbp+1270h+var_123C], di
0x180026c2f  jnz     short loc_180026C3D
0x180026c31  mov     rax, [rbp+1270h+var_1218]
0x180026c35  jmp     short loc_180026C25
0x180026c37  mov     r14d, 2
0x180026c3d  mov     rdx, [rbp+1270h+SourceString]; SourceString
0x180026c41  lea     rax, [rbp+1270h+var_12D0]
0x180026c45  mov     [rbp+1270h+var_1F0], rax
0x180026c4c  lea     rcx, [rbp+1270h+var_1298]; DestinationString
0x180026c50  lea     rax, [rbp+1270h+var_12EC]
0x180026c54  mov     [rbp+1270h+var_1E8], 8
0x180026c5f  mov     [rbp+1270h+var_1C0], rax
0x180026c66  mov     [rbp+1270h+var_1B8], rsi
0x180026c6d  call    cs:__imp_RtlInitUnicodeString
0x180026c73  lea     rax, [rsp+1370h+var_1328]
0x180026c78  lea     r9, [rbp+1270h+var_1298]
0x180026c7c  mov     [rsp+1370h+lpOutBuffer], rax; int
0x180026c81  lea     r8, [rsp+1370h+var_1300]
0x180026c86  lea     rdx, [rbp+1270h+var_1A0]
0x180026c8d  lea     rcx, [rbp+1270h+var_1B0]
0x180026c94  call    EventDataWriteUnicodeString
0x180026c99  test    r13, r13
0x180026c9c  jz      short loc_180026CC9
0x180026c9e  mov     rcx, [r13+70h]; hCryptMsg
0x180026ca2  test    rcx, rcx
0x180026ca5  jz      short loc_180026CC9
0x180026ca7  lea     rdx, [rsp+1370h+var_1308]
0x180026cac  call    GetResourcesFromMsg
0x180026cb1  test    eax, eax
0x180026cb3  jns     short loc_180026CC9
0x180026cb5  mov     rcx, [rbp+1278h]; this
0x180026cbc  mov     r9d, eax; char *
0x180026cbf  mov     edx, 0FA0h; void *
0x180026cc4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026cc9  mov     r9, [rsp+1370h+var_1308]
0x180026cce  lea     rax, [rsp+1370h+var_1324]
0x180026cd3  lea     r8, [rsp+1370h+var_1300]
0x180026cd8  mov     [rsp+1370h+lpOutBuffer], rax
0x180026cdd  lea     rdx, [rbp+1270h+var_180]
0x180026ce4  lea     rcx, [rbp+1270h+var_190]
0x180026ceb  call    EventDataWriteUnicodeString
0x180026cf0  mov     r9, [rsp+1370h+var_1308]
0x180026cf5  test    r9, r9
0x180026cf8  jnz     short loc_180026CFF
0x180026cfa  mov     r9, r15
0x180026cfd  jmp     short loc_180026D03
0x180026cff  add     r9, 10h
0x180026d03  lea     rax, [rsp+1370h+var_1320]
0x180026d08  lea     r8, [rsp+1370h+var_1300]
0x180026d0d  mov     [rsp+1370h+lpOutBuffer], rax
0x180026d12  lea     rdx, [rbp+1270h+var_160]
0x180026d19  lea     rcx, [rbp+1270h+var_170]
0x180026d20  call    EventDataWriteUnicodeString
0x180026d25  mov     r9, [rsp+1370h+var_1308]
0x180026d2a  test    r9, r9
0x180026d2d  jnz     short loc_180026D34
0x180026d2f  mov     r9, r15
0x180026d32  jmp     short loc_180026D38
0x180026d34  add     r9, 20h ; ' '
0x180026d38  lea     rax, [rsp+1370h+var_131C]
0x180026d3d  lea     r8, [rsp+1370h+var_1300]
0x180026d42  mov     [rsp+1370h+lpOutBuffer], rax
0x180026d47  lea     rdx, [rbp+1270h+var_140]
0x180026d4e  lea     rcx, [rbp+1270h+var_150]
0x180026d55  call    EventDataWriteUnicodeString
0x180026d5a  mov     r9, [rsp+1370h+var_1308]
0x180026d5f  test    r9, r9
0x180026d62  jnz     short loc_180026D69
0x180026d64  mov     r9, r15
0x180026d67  jmp     short loc_180026D6D
0x180026d69  add     r9, 30h ; '0'
0x180026d6d  lea     rax, [rsp+1370h+var_1318]
0x180026d72  lea     r8, [rsp+1370h+var_1300]
0x180026d77  mov     [rsp+1370h+lpOutBuffer], rax
0x180026d7c  lea     rdx, [rbp+1270h+var_120]
0x180026d83  lea     rcx, [rbp+1270h+var_130]
0x180026d8a  call    EventDataWriteUnicodeString
0x180026d8f  mov     r9, [rsp+1370h+var_1308]
0x180026d94  test    r9, r9
0x180026d97  jnz     short loc_180026D9E
0x180026d99  mov     r9, r15
0x180026d9c  jmp     short loc_180026DA2
0x180026d9e  mov     r9, [r9+40h]
0x180026da2  movzx   r8d, r9w
0x180026da6  mov     rax, r9
0x180026da9  mov     dword ptr [rsp+1370h+lpOverlapped], r8d
0x180026dae  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180026db2  shr     rax, 10h
0x180026db6  movzx   edx, ax
0x180026db9  mov     rax, r9
0x180026dbc  mov     dword ptr [rsp+1370h+lpBytesReturned], edx
0x180026dc0  shr     r9, 30h
0x180026dc4  lea     edx, [r8+19h]; BufferCount
0x180026dc8  shr     rax, 20h
0x180026dcc  movzx   ecx, ax
0x180026dcf  mov     [rsp+1370h+nOutBufferSize], ecx
0x180026dd3  lea     rcx, [rbp+1270h+Buffer]; Buffer
0x180026dda  mov     dword ptr [rsp+1370h+lpOutBuffer], r9d
0x180026ddf  lea     r9, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x180026de6  call    cs:__imp__snwprintf_s
0x180026dec  mov     [rsp+1370h+var_1330], ax
0x180026df1  lea     r9, [rbp+1270h+var_12C0]
0x180026df5  add     ax, ax
  ... truncated ...
```

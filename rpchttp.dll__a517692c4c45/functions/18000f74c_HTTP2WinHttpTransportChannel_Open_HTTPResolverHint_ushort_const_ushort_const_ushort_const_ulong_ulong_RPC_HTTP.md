# HTTP2WinHttpTransportChannel::Open(HTTPResolverHint *,ushort * const,ushort * const,ushort * const,ulong,ulong,_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *,ulong,ulong,uchar const *,int,int)

- ea: `0x18000f74c`
- end: `0x1800106b1`
- name: `?Open@HTTP2WinHttpTransportChannel@@QEAAJPEAVHTTPResolverHint@@QEAG11KKPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@KKPEBEHH@Z`
- size: `3941`
- prototype: `__int64 __fastcall(HTTP2WinHttpTransportChannel *this, struct HTTPResolverHint *, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, unsigned int Value, unsigned int Buffer, struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *, DWORD, DWORD AuthScheme, unsigned __int8 *, int, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005d50`

## callees

- `0x180001eb0`
- `0x180001f00`
- `0x180005550`
- `0x18000ee74`
- `0x18000ef2c`
- `0x18000f3fc`
- `0x18000f74c`
- `0x180019260`
- `0x18001ac60`
- `0x18001b930`
- `0x18001e3d4`
- `0x18001e4a4`
- `0x18001e524`
- `0x18001ec64`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x18000f92f`
- `ntdll!RtlIntegerToUnicodeString` at `0x18000f92f`
- `ntdll!_itow_s` at `0x180010128`
- `ntdll!_itow_s` at `0x1800101d3`
- `ntdll!_itow_s` at `0x180010128`
- `ntdll!_itow_s` at `0x1800101d3`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000f8fe`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000fa75`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180010340`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000f8fe`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18000fa75`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180010340`
- `KERNEL32!GetLastError` at `0x18000fab3`
- `KERNEL32!GetLastError` at `0x18000fe99`
- `KERNEL32!GetLastError` at `0x18001005e`
- `KERNEL32!GetLastError` at `0x180010173`
- `KERNEL32!GetLastError` at `0x1800104b8`
- `KERNEL32!GetLastError` at `0x18000fab3`
- `KERNEL32!GetLastError` at `0x18000fe99`
- `KERNEL32!GetLastError` at `0x18001005e`
- `KERNEL32!GetLastError` at `0x180010173`
- `KERNEL32!GetLastError` at `0x1800104b8`
- `KERNEL32!CreateEventW` at `0x1800100bf`
- `KERNEL32!CreateEventW` at `0x1800100bf`
- `KERNEL32!WaitForSingleObject` at `0x1800104cc`
- `KERNEL32!WaitForSingleObject` at `0x1800104cc`
- `KERNEL32!CloseHandle` at `0x180010640`
- `KERNEL32!CloseHandle` at `0x180010640`
- `RPCRT4!I_RpcFree` at `0x18000f964`
- `RPCRT4!I_RpcFree` at `0x18000fa25`
- `RPCRT4!I_RpcFree` at `0x18000faa6`
- `RPCRT4!I_RpcFree` at `0x18000fe8e`
- `RPCRT4!I_RpcFree` at `0x180010031`
- `RPCRT4!I_RpcFree` at `0x18001038f`
- `RPCRT4!I_RpcFree` at `0x18000f964`
- `RPCRT4!I_RpcFree` at `0x18000fa25`
- `RPCRT4!I_RpcFree` at `0x18000faa6`
- `RPCRT4!I_RpcFree` at `0x18000fe8e`
- `RPCRT4!I_RpcFree` at `0x180010031`
- `RPCRT4!I_RpcFree` at `0x18001038f`
- `RPCRT4!I_RpcAllocate` at `0x18000f8cd`
- `RPCRT4!I_RpcAllocate` at `0x18000fa45`
- `RPCRT4!I_RpcAllocate` at `0x1800102ff`
- `RPCRT4!I_RpcAllocate` at `0x18000f8cd`
- `RPCRT4!I_RpcAllocate` at `0x18000fa45`
- `RPCRT4!I_RpcAllocate` at `0x1800102ff`
- `RPCRT4!I_RpcLogEvent` at `0x18000f823`
- `RPCRT4!I_RpcLogEvent` at `0x18000fae1`
- `RPCRT4!I_RpcLogEvent` at `0x18000fc73`
- `RPCRT4!I_RpcLogEvent` at `0x18000fced`
- `RPCRT4!I_RpcLogEvent` at `0x18000fdb0`
- `RPCRT4!I_RpcLogEvent` at `0x18000fe3d`
- `RPCRT4!I_RpcLogEvent` at `0x18000ffc3`
- `RPCRT4!I_RpcLogEvent` at `0x180010151`
- `RPCRT4!I_RpcLogEvent` at `0x1800101f9`
- `RPCRT4!I_RpcLogEvent` at `0x1800102a8`
- `RPCRT4!I_RpcLogEvent` at `0x18001036e`
- `RPCRT4!I_RpcLogEvent` at `0x180010436`
- `RPCRT4!I_RpcLogEvent` at `0x180010483`
- `RPCRT4!I_RpcLogEvent` at `0x1800105d4`
- `RPCRT4!I_RpcLogEvent` at `0x180010635`
- `RPCRT4!I_RpcLogEvent` at `0x18000f823`
- `RPCRT4!I_RpcLogEvent` at `0x18000fae1`
- `RPCRT4!I_RpcLogEvent` at `0x18000fc73`
- `RPCRT4!I_RpcLogEvent` at `0x18000fced`
- `RPCRT4!I_RpcLogEvent` at `0x18000fdb0`
- `RPCRT4!I_RpcLogEvent` at `0x18000fe3d`
- `RPCRT4!I_RpcLogEvent` at `0x18000ffc3`
- `RPCRT4!I_RpcLogEvent` at `0x180010151`
- `RPCRT4!I_RpcLogEvent` at `0x1800101f9`
- `RPCRT4!I_RpcLogEvent` at `0x1800102a8`
- `RPCRT4!I_RpcLogEvent` at `0x18001036e`
- `RPCRT4!I_RpcLogEvent` at `0x180010436`
- `RPCRT4!I_RpcLogEvent` at `0x180010483`
- `RPCRT4!I_RpcLogEvent` at `0x1800105d4`
- `RPCRT4!I_RpcLogEvent` at `0x180010635`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18000f985`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18000f985`
- `WINHTTP!WinHttpSetOption` at `0x18000f9a0`
- `WINHTTP!WinHttpSetOption` at `0x18000f9c8`
- `WINHTTP!WinHttpSetOption` at `0x18000f9ea`
- `WINHTTP!WinHttpSetOption` at `0x18000fba4`
- `WINHTTP!WinHttpSetOption` at `0x18000fc32`
- `WINHTTP!WinHttpSetOption` at `0x18000fd06`
- `WINHTTP!WinHttpSetOption` at `0x180010053`
- `WINHTTP!WinHttpSetOption` at `0x18000f9a0`
- `WINHTTP!WinHttpSetOption` at `0x18000f9c8`
- `WINHTTP!WinHttpSetOption` at `0x18000f9ea`
- `WINHTTP!WinHttpSetOption` at `0x18000fba4`
- `WINHTTP!WinHttpSetOption` at `0x18000fc32`
- `WINHTTP!WinHttpSetOption` at `0x18000fd06`
- `WINHTTP!WinHttpSetOption` at `0x180010053`
- `WINHTTP!WinHttpConnect` at `0x18000fa95`
- `WINHTTP!WinHttpConnect` at `0x18000fa95`
- `WINHTTP!WinHttpOpenRequest` at `0x18000fb54`
- `WINHTTP!WinHttpOpenRequest` at `0x18000fb54`
- `WINHTTP!WinHttpQueryOption` at `0x18000fb77`
- `WINHTTP!WinHttpQueryOption` at `0x18000fb77`
- `WINHTTP!WinHttpOpen` at `0x18000f94d`
- `WINHTTP!WinHttpOpen` at `0x18000f94d`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180010169`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180010211`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800102c0`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180010384`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001044e`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180010169`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180010211`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800102c0`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180010384`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001044e`
- `WINHTTP!WinHttpSendRequest` at `0x1800104a3`
- `WINHTTP!WinHttpSendRequest` at `0x1800104a3`
- `WINHTTP!WinHttpSetCredentials` at `0x18000fe65`
- `WINHTTP!WinHttpSetCredentials` at `0x180010008`
- `WINHTTP!WinHttpSetCredentials` at `0x18000fe65`
- `WINHTTP!WinHttpSetCredentials` at `0x180010008`

## pseudocode

```c
__int64 __fastcall HTTP2WinHttpTransportChannel::Open(
        HTTP2WinHttpTransportChannel *this,
        struct HTTPResolverHint *a2,
        unsigned __int16 *const a3,
        unsigned __int16 *const a4,
        unsigned __int16 *const a5,
        unsigned int Value,
        unsigned int Buffer,
        struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *a8,
        DWORD a9,
        DWORD AuthScheme,
        unsigned __int8 *a11,
        int a12,
        int a13)
{
  struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *v13; // r13
  HTTP2WinHttpTransportChannel *v15; // r14
  HTTP2WinHttpTransportChannel *v16; // r8
  HTTP2Channel *v17; // rbx
  struct HTTP2VirtualConnection *v18; // rax
  int v19; // ecx
  struct HTTPResolverHint *v20; // rbx
  WCHAR *v21; // rdi
  DWORD v22; // r15d
  unsigned int v23; // esi
  __int64 v24; // rax
  __int64 v25; // rbx
  unsigned int v26; // eax
  WCHAR *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rcx
  WCHAR *v31; // rax
  void *v32; // rax
  DWORD v33; // esi
  void *v34; // rcx
  void *v35; // rcx
  LPCWSTR v36; // rax
  int v37; // esi
  unsigned int v38; // eax
  __int64 v39; // rbx
  DWORD LastError; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  DWORD v43; // ebx
  DWORD dwFlags; // eax
  void *v45; // rax
  void *v46; // rcx
  DWORD v47; // r15d
  DWORD v48; // r12d
  BOOL v49; // ecx
  BOOL v50; // eax
  void *v51; // rcx
  LPCWSTR v52; // rdi
  unsigned int v54; // ebx
  __int64 v55; // rdx
  __int64 v56; // rcx
  int v57; // eax
  __int64 v58; // r8
  WCHAR *v59; // rdi
  __int64 v60; // rcx
  BOOL v61; // r13d
  __int64 v62; // rcx
  WCHAR *v63; // rdx
  LPVOID v64; // rcx
  __int64 (__fastcall *v65)(LPVOID, unsigned __int16 **, unsigned __int16 **, LPCWSTR *); // rax
  unsigned int v66; // eax
  void *v67; // rcx
  BOOL v68; // eax
  BOOL v69; // r12d
  __int64 v70; // rcx
  WCHAR *v71; // rax
  DWORD v72; // eax
  HANDLE EventW; // rax
  void *v74; // r13
  void *v75; // rdi
  DWORD v76; // ebx
  int v77; // eax
  __int64 v78; // rdx
  __int64 v79; // rcx
  unsigned int v80; // ecx
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rdx
  RPC_UUID *v84; // rcx
  unsigned __int16 *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rcx
  unsigned int v88; // eax
  WCHAR *v89; // rax
  WCHAR *v90; // r15
  ULONG BytesInMultiByteString; // ebx
  __int64 v92; // rcx
  __int64 v93; // rdx
  BOOL v94; // ebx
  RPC_UUID *v95; // rcx
  unsigned __int16 *v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // rdx
  __int64 v101; // rcx
  DWORD v102; // ebx
  int v103; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v104; // [rsp+44h] [rbp-BCh] BYREF
  int v105; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v106; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR pwszPassword; // [rsp+58h] [rbp-A8h] BYREF
  int v108; // [rsp+60h] [rbp-A0h]
  struct HTTPResolverHint *v109; // [rsp+68h] [rbp-98h]
  unsigned __int16 *Src; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR pwszVerb; // [rsp+78h] [rbp-88h]
  int v112; // [rsp+80h] [rbp-80h] BYREF
  BOOL v113; // [rsp+84h] [rbp-7Ch]
  LPVOID lpBuffer; // [rsp+88h] [rbp-78h] BYREF
  DWORD dwBufferLength; // [rsp+90h] [rbp-70h] BYREF
  __int64 v116; // [rsp+98h] [rbp-68h] BYREF
  RPC_UUID *v117; // [rsp+A0h] [rbp-60h] BYREF
  RPC_UUID *v118; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID lpOptional; // [rsp+B0h] [rbp-50h]
  _UNICODE_STRING String; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR ppwszAcceptTypes[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v122; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR szHeaders[64]; // [rsp+F0h] [rbp-10h] BYREF

  v13 = a8;
  pwszVerb = a3;
  v15 = this;
  lpOptional = a11;
  v16 = this;
  v109 = a2;
  LOBYTE(this) = 50;
  LOBYTE(a2) = 111;
  dwBufferLength = 4;
  *(_OWORD *)ppwszAcceptTypes = 0;
  v106 = 0;
  pwszPassword = 0;
  Src = 0;
  v103 = 0;
  v112 = 0;
  v104 = 0;
  lpBuffer = 0;
  v118 = 0;
  v116 = 0;
  v117 = 0;
  v122 = 0;
  I_RpcLogEvent(this, a2, v16, 18087957, Value, 0, 0);
  v17 = (HTTP2Channel *)*((_QWORD *)v15 + 3);
  *((_QWORD *)v15 + 25) = v13;
  lpBuffer = 0;
  v18 = HTTP2Channel::LockParentPointer(v17);
  if ( !v18 )
  {
    RpcpReportFatalError(21);
    JUMPOUT(0x1800106B0LL);
  }
  v19 = *((_DWORD *)v17 + 17);
  if ( v19 == *((_DWORD *)v18 + 38) || (v108 = 0, v19 == *((_DWORD *)v18 + 39)) )
    v108 = 1;
  HTTP2Channel::UnlockParentPointer(v17);
  if ( !*((_QWORD *)v15 + 7) )
  {
    v20 = v109;
    *((_DWORD *)v15 + 45) = 1;
    if ( *((_DWORD *)v20 + 8) == 1 )
    {
      v21 = 0;
      v22 = 1;
      v23 = 0;
    }
    else
    {
      v24 = *((_QWORD *)v20 + 14);
      v25 = -1;
      do
        ++v25;
      while ( *(_BYTE *)(v24 + v25) );
      v23 = v25 + 7;
      v26 = 2 * (v25 + 7);
      if ( !is_mul_ok((unsigned int)(v25 + 7), 2u) )
        v26 = -1;
      v27 = (WCHAR *)I_RpcAllocate(v26);
      v21 = v27;
      if ( !v27 )
        goto LABEL_17;
      v22 = 3;
      RtlMultiByteToUnicodeN(v27, 2 * (v25 + 1), 0, *((const CHAR **)v109 + 14), v25 + 1);
      v30 = (unsigned int)v25;
      v20 = v109;
      *(_QWORD *)&String.Length = 786432;
      v31 = &v21[v30 + 1];
      v21[v30] = 58;
      LODWORD(v30) = *((unsigned __int16 *)v20 + 60);
      String.Buffer = v31;
      RtlIntegerToUnicodeString(v30, 0, &String);
    }
    v32 = WinHttpOpen(L"MSRPC", v22, v21, 0, 0x10000000u);
    *((_QWORD *)v15 + 7) = v32;
    if ( !v32 )
    {
      if ( v21 )
        I_RpcFree(v21);
LABEL_17:
      v33 = 14;
LABEL_59:
      LOBYTE(v28) = 111;
      LOBYTE(v29) = 50;
      I_RpcLogEvent(v29, v28, v15, 1310741, 14, 0, 0);
      return v33;
    }
    WinHttpSetStatusCallback(v32, WinHttpCallback, 0xFFFFFFFF, 0);
    WinHttpSetOption(*((HINTERNET *)v15 + 7), 3u, &Buffer, 4u);
    v34 = (void *)*((_QWORD *)v15 + 7);
    Buffer = 1800000;
    WinHttpSetOption(v34, 5u, &Buffer, 4u);
    v35 = (void *)*((_QWORD *)v15 + 7);
    Buffer = 1800000;
    WinHttpSetOption(v35, 6u, &Buffer, 4u);
    v36 = InChannelTargetTestOverride;
    if ( !v108 )
      v36 = (LPCWSTR)OutChannelTargetTestOverride;
    if ( v36 )
    {
      v37 = 1;
      v21 = (WCHAR *)v36;
    }
    else
    {
      if ( *((_DWORD *)v20 + 26) + 1 > v23 )
      {
        if ( v21 )
          I_RpcFree(v21);
        v38 = 2 * (*((_DWORD *)v20 + 26) + 1);
        if ( !is_mul_ok((unsigned int)(*((_DWORD *)v20 + 26) + 1), 2u) )
          v38 = -1;
        v21 = (WCHAR *)I_RpcAllocate(v38);
        if ( !v21 )
          goto LABEL_17;
      }
      v39 = *((unsigned int *)v20 + 26);
      v37 = 0;
      RtlMultiByteToUnicodeN(v21, 2 * (v39 + 1), 0, *((const CHAR **)v109 + 12), v39 + 1);
      v21[v39] = 0;
    }
    *((_QWORD *)v15 + 8) = WinHttpConnect(*((HINTERNET *)v15 + 7), v21, *((_WORD *)v109 + 54), 0);
    if ( !v37 )
      I_RpcFree(v21);
    if ( !*((_QWORD *)v15 + 8) )
    {
      LastError = GetLastError();
      v33 = 14;
      LOBYTE(v41) = 111;
      LOBYTE(v42) = 50;
      v43 = LastError;
      I_RpcLogEvent(v42, v41, v15, 1310741, 14, 0, 0);
      if ( v43 == 12005 )
        return 1722;
      return v33;
    }
    ppwszAcceptTypes[1] = 0;
    ppwszAcceptTypes[0] = L"application/rpc";
    *((_QWORD *)v15 + 12) = DuplicateString(a4);
    if ( !v13 || (dwFlags = 8388864, (v13->Flags & 1) == 0) )
      dwFlags = 256;
    v45 = WinHttpOpenRequest(*((HINTERNET *)v15 + 8), pwszVerb, a4, 0, 0, ppwszAcceptTypes, dwFlags);
    *((_QWORD *)v15 + 9) = v45;
    if ( !v45 )
      goto LABEL_17;
    WinHttpQueryOption(v45, 0xCu, (char *)v15 + 48, &dwBufferLength);
    if ( v13 && (v13->Flags & 8) != 0 )
    {
      v46 = (void *)*((_QWORD *)v15 + 9);
      v105 = 4096;
      WinHttpSetOption(v46, 0x1Fu, &v105, 4u);
    }
  }
  v47 = a9;
  v48 = AuthScheme;
  v49 = a9 && (a9 != *((_DWORD *)v15 + 54) || a9 == 1 || a9 == 16 || AuthScheme);
  v105 = v49;
  v50 = AuthScheme && AuthScheme != *((_DWORD *)v15 + 55);
  v113 = v50;
  v33 = 14;
  if ( !v49 && !v50 )
  {
    if ( !a9 && !AuthScheme )
    {
      v51 = (void *)*((_QWORD *)v15 + 9);
      v103 = 0;
      WinHttpSetOption(v51, 0x4Du, &v103, 4u);
    }
LABEL_123:
    EventW = CreateEventW(0, 0, 0, 0);
    v74 = EventW;
    if ( !EventW )
    {
LABEL_178:
      if ( v106 )
        (*((void (**)(void))pRuntimeImportTable + 49))();
      if ( Src )
        (*((void (**)(void))pRuntimeImportTable + 49))();
      if ( pwszPassword )
        (*((void (**)(void))pRuntimeImportTable + 49))();
      return v33;
    }
    v75 = lpOptional;
    v76 = Value;
    *((_QWORD *)v15 + 21) = EventW;
    v77 = *((_DWORD *)v15 + 40);
    if ( v77 == -1
      || Value == v77
      || (wcscpy(szHeaders, (const wchar_t *)&xmmword_1800283A8),
          _itow_s(Value, &szHeaders[15], 0x2Du, 10),
          LOBYTE(v78) = 111,
          LOBYTE(v79) = 50,
          I_RpcLogEvent(v79, v78, *((_QWORD *)v15 + 9), 26148886, -1, 0, 0),
          WinHttpAddRequestHeaders(*((HINTERNET *)v15 + 9), szHeaders, 0xFFFFFFFF, 0x80000000)) )
    {
      v80 = OverrideMinimumConnectionTimeout;
      *((_DWORD *)v15 + 40) = Value;
      if ( !v80
        || (wcscpy(szHeaders, L"Pragma:MinConnimeout="),
            _itow_s(v80 / 0x3E8, &szHeaders[22], 0x26u, 10),
            LOBYTE(v81) = 111,
            LOBYTE(v82) = 50,
            I_RpcLogEvent(v82, v81, *((_QWORD *)v15 + 9), 26148886, -1, 0, 0),
            WinHttpAddRequestHeaders(*((HINTERNET *)v15 + 9), szHeaders, 0xFFFFFFFF, 0x20000000u)) )
      {
        (*((void (__fastcall **)(_QWORD, RPC_UUID **, __int64 *, RPC_UUID **))pRuntimeImportTable + 20))(
          *(_QWORD *)(*((_QWORD *)v15 + 3) + 48LL),
          &v118,
          &v116,
          &v117);
        v84 = v118;
        if ( !v118
          || (wcscpy(szHeaders, L"Pragma:ResourceTypeUuid="),
              v85 = RPC_UUID::ConvertToString(v118, &szHeaders[24]),
              LOBYTE(v86) = 111,
              LOBYTE(v87) = 50,
              *v85 = 0,
              I_RpcLogEvent(v87, v86, *((_QWORD *)v15 + 9), 26148886, -1, 0, 0),
              WinHttpAddRequestHeaders(*((HINTERNET *)v15 + 9), szHeaders, 0xFFFFFFFF, 0x20000000u)) )
        {
          if ( v116 && *(_QWORD *)(v116 + 8) )
          {
            v88 = 2 * (*(_DWORD *)v116 + 8);
            if ( !is_mul_ok((unsigned int)(*(_DWORD *)v116 + 8), 2u) )
              v88 = -1;
            v89 = (WCHAR *)I_RpcAllocate(v88);
            v90 = v89;
            if ( !v89 )
              goto LABEL_177;
            *(_OWORD *)v89 = xmmword_180028328;
            v89[8] = 0;
            BytesInMultiByteString = *(_DWORD *)v116;
            RtlMultiByteToUnicodeN(
              v89 + 8,
              2 * BytesInMultiByteString,
              0,
              *(const CHAR **)(v116 + 8),
              BytesInMultiByteString);
            v92 = BytesInMultiByteString - 1;
            v90[v92 + 8] = 0;
            LOBYTE(v93) = 111;
            LOBYTE(v92) = 50;
            I_RpcLogEvent(v92, v93, *((_QWORD *)v15 + 9), 26148886, -1, 0, 0);
            v94 = WinHttpAddRequestHeaders(*((HINTERNET *)v15 + 9), v90, 0xFFFFFFFF, 0x20000000u);
            I_RpcFree(v90);
            if ( !v94 )
              goto LABEL_127;
            v76 = Value;
            *((_DWORD *)v15 + 56) |= 0x10u;
          }
          if ( v108 && !a13 )
            goto LABEL_144;
          v95 = v117;
          if ( !v117 )
          {
            v95 = (RPC_UUID *)&v122;
            v117 = (RPC_UUID *)&v122;
            v122 = *(_OWORD *)((char *)v109 + 122);
          }
          wcscpy(szHeaders, L"Pragma:SessionId=");
          v96 = RPC_UUID::ConvertToString(v95, &szHeaders[17]);
          LOBYTE(v97) = 111;
          LOBYTE(v98) = 50;
          *v96 = 0;
          I_RpcLogEvent(v98, v97, *((_QWORD *)v15 + 9), 26148886, -1, 0, 0);
          if ( WinHttpAddRequestHeaders(*((HINTERNET *)v15 + 9), szHeaders, 0xFFFFFFFF, 0x20000000u) )
          {
LABEL_144:
            v99 = *((_QWORD *)v15 + 9);
            LOBYTE(v83) = 111;
            LOBYTE(v84) = 50;
            *((_DWORD *)v15 + 45) = 2;
            I_RpcLogEvent(v84, v83, v99, 25559062, v76, 0, 0);
            if ( WinHttpSendRequest(*((HINTERNET *)v15 + 9), 0, 0, v75, v75 != 0 ? Value : 0, v76, (DWORD_PTR)v15) )
            {
              WaitForSingleObject(*((HANDLE *)v15 + 21), 0xFFFFFFFF);
              v102 = *((_DWORD *)v15 + 21);
              *((_DWORD *)v15 + 21) = 1766;
              *((_QWORD *)v15 + 21) = 0;
            }
            else
            {
              *((_QWORD *)v15 + 21) = 0;
              v102 = GetLastError();
            }
            if ( !v102 )
            {
              LOBYTE(v100) = 111;
              LOBYTE(v101) = 50;
              I_RpcLogEvent(v101, v100, v15, 1310741, 0, 0, 0);
              v33 = 0;
              goto LABEL_177;
            }
            if ( v102 > 0x2EEC )
            {
              if ( ((v102 - 12029) & 0xFFFFFFFC) == 0 && v102 != 12031 )
                goto LABEL_163;
              switch ( v102 )
              {
                case 0x2F0Cu:
                  goto LABEL_174;
                case 0x2F78u:
                  v33 = 1728;
                  goto LABEL_175;
                case 0x2F7Cu:
                  goto LABEL_163;
                case 0x2F8Fu:
LABEL_174:
                  v33 = 5;
                  goto LABEL_175;
              }
              if ( v102 + 1073606647 <= 1 )
              {
LABEL_163:
                v33 = 1722;
                goto LABEL_175;
              }
            }
            else
            {
              if ( v102 == 12012 )
                goto LABEL_163;
              if ( v102 <= 0x718 )
              {
                if ( v102 == 1816 || v102 == 8 || v102 == 14 )
                  goto LABEL_175;
                if ( v102 != 50 )
                {
                  if ( v102 == 1450 || v102 == 1455 )
                    goto LABEL_175;
                  goto LABEL_172;
                }
                v33 = 1764;
LABEL_175:
                LOBYTE(v100) = 111;
                LOBYTE(v101) = 50;
                I_RpcLogEvent(v101, v100, v15, 1310741, v33, 0, 0);
                (*((void (__fastcall **)(_QWORD))pRuntimeImportTable + 67))(*((_QWORD *)v15 + 11));
                *((_QWORD *)v15 + 11) = 0;
                CompRpcpErrorAddRecord(0xDu, v33, 0x548u, v102);
                goto LABEL_177;
              }
              switch ( v102 )
              {
                case 0x2EE1u:
                  goto LABEL_175;
                case 0x2EE2u:
                  v33 = 1818;
                  goto LABEL_175;
                case 0x2EE5u:
                case 0x2EE7u:
                  goto LABEL_163;
              }
            }
LABEL_172:
            v33 = v102;
            goto LABEL_175;
          }
        }
      }
    }
LABEL_127:
    v33 = GetLastError();
LABEL_177:
    CloseHandle(v74);
    goto LABEL_178;
  }
  pwszVerb = (LPCWSTR)I_RpcTransGetHttpCredentials(v13);
  v52 = pwszVerb;
  if ( !pwszVerb )
    goto LABEL_59;
  v54 = 0;
  if ( !(unsigned int)HTTP2WinHttpTransportChannel::IsAutoLogonPolicySet(v15) )
  {
    if ( v47 != 1 )
    {
      if ( v47 != 2 && v47 != 16 )
        goto LABEL_73;
      if ( !*(_QWORD *)v52 )
      {
        v54 = IsLanManHashDisabled(&v112);
        if ( v54 )
          goto LABEL_76;
        if ( (v13->Flags & 1) != 0 && v13->ServerCertificateSubject || v112 )
        {
          v57 = 1;
          goto LABEL_66;
        }
        goto LABEL_65;
      }
    }
    if ( *((_QWORD *)v52 + 5) || v48 )
    {
LABEL_65:
      v57 = 2;
LABEL_66:
      v58 = *((_QWORD *)v15 + 9);
      LOBYTE(v55) = 111;
      LOBYTE(v56) = 50;
      v103 = v57;
      I_RpcLogEvent(v56, v55, v58, 26345494, v57, 0, 0);
      WinHttpSetOption(*((HINTERNET *)v15 + 9), 0x4Du, &v103, 4u);
      HTTP2WinHttpTransportChannel::SetAutoLogonPolicySetFlag(v15);
      goto LABEL_67;
    }
LABEL_73:
    v57 = 0;
    goto LABEL_66;
  }
LABEL_67:
  v59 = 0;
  if ( v113 )
  {
    v60 = *((_QWORD *)pwszVerb + 5);
    if ( v60 )
    {
      v54 = (*((__int64 (__fastcall **)(__int64, unsigned __int16 **, unsigned __int16 **, LPCWSTR *))pRuntimeImportTable
             + 48))(
              v60,
              &v106,
              &Src,
              &pwszPassword);
      if ( v54 )
        goto LABEL_70;
      v59 = BuildDomainAndUserName(Src, v106, &v104);
      if ( !v59 )
        goto LABEL_70;
    }
    else
    {
      if ( v48 == 1 )
      {
        v54 = 1729;
        goto LABEL_120;
      }
      v106 = 0;
      pwszPassword = 0;
    }
    LOBYTE(v55) = 111;
    LOBYTE(v60) = 50;
    I_RpcLogEvent(v60, v55, *((_QWORD *)v15 + 9), 26083350, v48, 0, 0);
    v61 = WinHttpSetCredentials(*((HINTERNET *)v15 + 9), 1u, v48, v59, pwszPassword, 0);
    if ( v59 )
    {
      v62 = v104;
      v63 = v59;
      if ( v104 )
      {
        do
        {
          *(_BYTE *)v63 = 0;
          v63 = (WCHAR *)((char *)v63 + 1);
          --v62;
        }
        while ( v62 );
      }
      I_RpcFree(v59);
    }
    if ( !v61 )
      goto LABEL_91;
    *((_DWORD *)v15 + 55) = v48;
  }
  if ( !v105 )
    goto LABEL_120;
  v64 = *(LPVOID *)pwszVerb;
  if ( *(_QWORD *)pwszVerb )
  {
    v65 = (__int64 (__fastcall *)(LPVOID, unsigned __int16 **, unsigned __int16 **, LPCWSTR *))*((_QWORD *)pRuntimeImportTable
                                                                                               + 48);
    if ( ((v47 - 0x20000) & 0xFFFDFFFF) != 0 )
    {
      v54 = v65(v64, &v106, &Src, &pwszPassword);
      if ( v54 )
        goto LABEL_70;
      v59 = BuildDomainAndUserName(Src, v106, &v104);
      if ( !v59 )
        goto LABEL_70;
      goto LABEL_108;
    }
    v66 = v65(v64, &v106, &Src, &pwszPassword);
    v54 = v66;
    if ( v66
      || (v66 = (*((__int64 (__fastcall **)(unsigned __int16 *, LPCWSTR, _QWORD, LPVOID *))pRuntimeImportTable + 23))(
                  v106,
                  pwszPassword,
                  0,
                  &lpBuffer),
          (v54 = v66) != 0) )
    {
      if ( v66 == 1749 )
        goto LABEL_120;
      goto LABEL_70;
    }
  }
  else
  {
    if ( v47 == 1 )
    {
      v54 = 5;
      goto LABEL_120;
    }
    v106 = 0;
    v59 = 0;
    pwszPassword = 0;
  }
  if ( ((v47 - 0x20000) & 0xFFFDFFFF) == 0 )
  {
    if ( !WinHttpSetOption(*((HINTERNET *)v15 + 9), 0x2Fu, lpBuffer, 0x28u) )
    {
      v72 = GetLastError();
      CompRpcpErrorAddRecord(0xEu, v72, 0x546u);
      v54 = 14;
    }
    (*((void (__fastcall **)(LPVOID))pRuntimeImportTable + 22))(lpBuffer);
    goto LABEL_120;
  }
LABEL_108:
  LOBYTE(v55) = 111;
  LOBYTE(v64) = 50;
  I_RpcLogEvent(v64, v55, *((_QWORD *)v15 + 9), 26083350, v47, 0, 0);
  v67 = (void *)*((_QWORD *)v15 + 9);
  if ( v47 == 16 )
    v68 = WinHttpSetCredentials(v67, 0, 0x10u, 0, 0, *(LPVOID *)pwszVerb);
  else
    v68 = WinHttpSetCredentials(v67, 0, v47, v59, pwszPassword, 0);
  v69 = v68;
  if ( v59 )
  {
    v70 = v104;
    v71 = v59;
    if ( v104 )
    {
      do
      {
        *(_BYTE *)v71 = 0;
        v71 = (WCHAR *)((char *)v71 + 1);
        --v70;
      }
      while ( v70 );
    }
    I_RpcFree(v59);
  }
  if ( v69 )
    goto LABEL_120;
LABEL_91:
  GetLastError();
LABEL_70:
  v54 = 14;
LABEL_120:
  I_RpcTransFreeHttpCredentials((struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *)pwszVerb);
  if ( !v54 )
  {
    *((_DWORD *)v15 + 54) = v47;
    goto LABEL_123;
  }
  CompRpcpErrorAddRecord(0xEu, v54, 0x547u);
LABEL_76:
  LOBYTE(v55) = 111;
  LOBYTE(v56) = 50;
  I_RpcLogEvent(v56, v55, v15, 1310741, v54, 0, 0);
  return v54;
}

```

## disassembly

```asm
0x18000f74c  push    rbp
0x18000f74e  push    rbx
0x18000f74f  push    rsi
0x18000f750  push    rdi
0x18000f751  push    r12
0x18000f753  push    r13
0x18000f755  push    r14
0x18000f757  push    r15
0x18000f759  lea     rbp, [rsp-88h]
0x18000f761  sub     rsp, 188h
0x18000f768  mov     rax, cs:__security_cookie
0x18000f76f  xor     rax, rsp
0x18000f772  mov     [rbp+0C0h+var_50], rax
0x18000f776  mov     rax, [rbp+0C0h+arg_50]
0x18000f77d  xorps   xmm0, xmm0
0x18000f780  mov     r13, [rbp+0C0h+arg_38]
0x18000f787  mov     r12, r9
0x18000f78a  mov     [rsp+1C0h+pwszVerb], r8
0x18000f78f  mov     r14, rcx
0x18000f792  mov     [rbp+0C0h+lpOptional], rax
0x18000f796  mov     r8, rcx
0x18000f799  mov     eax, [rbp+0C0h+Value]
0x18000f79f  mov     r9d, 1140015h
0x18000f7a5  mov     [rsp+1C0h+var_158], rdx
0x18000f7aa  mov     cl, 32h ; '2'
0x18000f7ac  mov     [rsp+1C0h+dwFlags], 0
0x18000f7b4  mov     dl, 6Fh ; 'o'
0x18000f7b6  mov     dword ptr [rsp+1C0h+ppwszAcceptTypes], 0
0x18000f7be  mov     [rsp+1C0h+BytesInMultiByteString], eax
0x18000f7c2  mov     [rbp+0C0h+dwBufferLength], 4
0x18000f7c9  movups  xmmword ptr [rbp+0C0h+var_F8], xmm0
0x18000f7cd  mov     [rsp+1C0h+var_170], 0
0x18000f7d6  mov     [rsp+1C0h+pwszPassword], 0
0x18000f7df  mov     [rsp+1C0h+Src], 0
0x18000f7e8  mov     [rsp+1C0h+var_180], 0
0x18000f7f0  mov     [rbp+0C0h+var_140], 0
0x18000f7f7  mov     [rsp+1C0h+var_17C], 0
0x18000f7ff  mov     [rbp+0C0h+lpBuffer], 0
0x18000f807  mov     [rbp+0C0h+var_118], 0
0x18000f80f  mov     [rbp+0C0h+var_128], 0
0x18000f817  mov     [rbp+0C0h+var_120], 0
0x18000f81f  movups  [rbp+0C0h+var_E8], xmm0
0x18000f823  call    cs:__imp_I_RpcLogEvent
0x18000f829  mov     rbx, [r14+18h]
0x18000f82d  mov     rcx, rbx; this
0x18000f830  mov     [r14+0C8h], r13
0x18000f837  mov     [rbp+0C0h+lpBuffer], 0
0x18000f83f  call    ?LockParentPointer@HTTP2Channel@@QEAAPEAVHTTP2VirtualConnection@@XZ; HTTP2Channel::LockParentPointer(void)
0x18000f844  test    rax, rax
0x18000f847  jz      loc_1800106A6
0x18000f84d  mov     ecx, [rbx+44h]
0x18000f850  cmp     ecx, [rax+98h]
0x18000f856  jz      short loc_18000F868
0x18000f858  mov     [rsp+1C0h+var_160], 0
0x18000f860  cmp     ecx, [rax+9Ch]
0x18000f866  jnz     short loc_18000F870
0x18000f868  mov     [rsp+1C0h+var_160], 1
0x18000f870  mov     rcx, rbx; this
0x18000f873  call    ?UnlockParentPointer@HTTP2Channel@@QEAAXXZ; HTTP2Channel::UnlockParentPointer(void)
0x18000f878  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f87c  cmp     qword ptr [r14+38h], 0
0x18000f881  jnz     loc_18000FBAA
0x18000f887  mov     rbx, [rsp+1C0h+var_158]
0x18000f88c  mov     dword ptr [r14+0B4h], 1
0x18000f897  cmp     dword ptr [rbx+20h], 1
0x18000f89b  jnz     short loc_18000F8AA
0x18000f89d  xor     edi, edi
0x18000f89f  lea     r15d, [r8+2]
0x18000f8a3  xor     esi, esi
0x18000f8a5  jmp     loc_18000F935
0x18000f8aa  mov     rax, [rbx+70h]
0x18000f8ae  mov     rbx, r8
0x18000f8b1  inc     rbx
0x18000f8b4  cmp     byte ptr [rax+rbx], 0
0x18000f8b8  jnz     short loc_18000F8B1
0x18000f8ba  lea     esi, [rbx+7]
0x18000f8bd  mov     eax, 2
0x18000f8c2  mov     ecx, esi
0x18000f8c4  mul     rcx
0x18000f8c7  cmovb   rax, r8
0x18000f8cb  mov     ecx, eax; Size
0x18000f8cd  call    cs:__imp_I_RpcAllocate
0x18000f8d3  mov     rdi, rax
0x18000f8d6  test    rax, rax
0x18000f8d9  jz      loc_18000F96A
0x18000f8df  mov     r9, [rsp+1C0h+var_158]
0x18000f8e4  lea     ecx, [rbx+1]
0x18000f8e7  lea     edx, [rcx+rcx]; MaxBytesInUnicodeString
0x18000f8ea  mov     [rsp+1C0h+BytesInMultiByteString], ecx; BytesInMultiByteString
0x18000f8ee  xor     r8d, r8d; BytesInUnicodeString
0x18000f8f1  mov     rcx, rax; UnicodeString
0x18000f8f4  mov     r15d, 3
0x18000f8fa  mov     r9, [r9+70h]; MultiByteString
0x18000f8fe  call    cs:__imp_RtlMultiByteToUnicodeN
0x18000f904  mov     ecx, ebx
0x18000f906  lea     rax, [rdi+2]
0x18000f90a  mov     rbx, [rsp+1C0h+var_158]
0x18000f90f  lea     r8, [rbp+0C0h+String]; String
0x18000f913  xor     edx, edx; Base
0x18000f915  mov     qword ptr [rbp+0C0h+String.Length], 0C0000h
0x18000f91d  lea     rax, [rax+rcx*2]
0x18000f921  mov     word ptr [rdi+rcx*2], 3Ah ; ':'
0x18000f927  movzx   ecx, word ptr [rbx+78h]; Value
0x18000f92b  mov     [rbp+0C0h+String.Buffer], rax
0x18000f92f  call    cs:__imp_RtlIntegerToUnicodeString
0x18000f935  xor     r9d, r9d; pszProxyBypassW
0x18000f938  mov     [rsp+1C0h+BytesInMultiByteString], 10000000h; dwFlags
0x18000f940  mov     r8, rdi; pszProxyW
0x18000f943  lea     rcx, pszAgentW; "MSRPC"
0x18000f94a  mov     edx, r15d; dwAccessType
0x18000f94d  call    cs:__imp_WinHttpOpen
0x18000f953  mov     [r14+38h], rax
0x18000f957  test    rax, rax
0x18000f95a  jnz     short loc_18000F974
0x18000f95c  test    rdi, rdi
0x18000f95f  jz      short loc_18000F96A
0x18000f961  mov     rcx, rdi; Object
0x18000f964  call    cs:__imp_I_RpcFree
0x18000f96a  mov     esi, 0Eh
0x18000f96f  jmp     loc_18000FC52
0x18000f974  xor     r9d, r9d; dwReserved
0x18000f977  lea     rdx, ?WinHttpCallback@@YAXPEAX_KK0K@Z; lpfnInternetCallback
0x18000f97e  or      r8d, 0FFFFFFFFh; dwNotificationFlags
0x18000f982  mov     rcx, rax; hInternet
0x18000f985  call    cs:__imp_WinHttpSetStatusCallback
0x18000f98b  mov     rcx, [r14+38h]; hInternet
0x18000f98f  lea     r8, [rbp+0C0h+Buffer]; lpBuffer
0x18000f996  mov     r9d, 4; dwBufferLength
0x18000f99c  lea     edx, [r9-1]; dwOption
0x18000f9a0  call    cs:__imp_WinHttpSetOption
0x18000f9a6  mov     rcx, [r14+38h]; hInternet
0x18000f9aa  lea     r8, [rbp+0C0h+Buffer]; lpBuffer
0x18000f9b1  mov     r9d, 4; dwBufferLength
0x18000f9b7  mov     r15d, 1B7740h
0x18000f9bd  mov     [rbp+0C0h+Buffer], r15d
0x18000f9c4  lea     edx, [r9+1]; dwOption
0x18000f9c8  call    cs:__imp_WinHttpSetOption
0x18000f9ce  mov     rcx, [r14+38h]; hInternet
0x18000f9d2  lea     r8, [rbp+0C0h+Buffer]; lpBuffer
0x18000f9d9  mov     r9d, 4; dwBufferLength
0x18000f9df  mov     [rbp+0C0h+Buffer], r15d
0x18000f9e6  lea     edx, [r9+2]; dwOption
0x18000f9ea  call    cs:__imp_WinHttpSetOption
0x18000f9f0  cmp     [rsp+1C0h+var_160], 0
0x18000f9f5  mov     rax, cs:?InChannelTargetTestOverride@@3PEAGEA; ushort * InChannelTargetTestOverride
0x18000f9fc  jnz     short loc_18000FA05
0x18000f9fe  mov     rax, cs:?OutChannelTargetTestOverride@@3PEAGEA; ushort * OutChannelTargetTestOverride
0x18000fa05  test    rax, rax
0x18000fa08  jz      short loc_18000FA14
0x18000fa0a  mov     esi, 1
0x18000fa0f  mov     rdi, rax
0x18000fa12  jmp     short loc_18000FA81
0x18000fa14  mov     eax, [rbx+68h]
0x18000fa17  inc     eax
0x18000fa19  cmp     eax, esi
0x18000fa1b  jbe     short loc_18000FA57
0x18000fa1d  test    rdi, rdi
0x18000fa20  jz      short loc_18000FA2B
0x18000fa22  mov     rcx, rdi; Object
0x18000fa25  call    cs:__imp_I_RpcFree
0x18000fa2b  mov     ecx, [rbx+68h]
0x18000fa2e  mov     eax, 2
0x18000fa33  inc     ecx
0x18000fa35  mul     rcx
0x18000fa38  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fa3f  cmovb   rax, rcx
0x18000fa43  mov     ecx, eax; Size
0x18000fa45  call    cs:__imp_I_RpcAllocate
0x18000fa4b  mov     rdi, rax
0x18000fa4e  test    rax, rax
0x18000fa51  jz      loc_18000F96A
0x18000fa57  mov     ebx, [rbx+68h]
0x18000fa5a  xor     r8d, r8d; BytesInUnicodeString
0x18000fa5d  mov     r9, [rsp+1C0h+var_158]
0x18000fa62  mov     rcx, rdi; UnicodeString
0x18000fa65  xor     esi, esi
0x18000fa67  lea     eax, [rbx+1]
0x18000fa6a  mov     r9, [r9+60h]; MultiByteString
0x18000fa6e  lea     edx, [rax+rax]; MaxBytesInUnicodeString
0x18000fa71  mov     [rsp+1C0h+BytesInMultiByteString], eax; BytesInMultiByteString
0x18000fa75  call    cs:__imp_RtlMultiByteToUnicodeN
0x18000fa7b  xor     eax, eax
0x18000fa7d  mov     [rdi+rbx*2], ax
0x18000fa81  mov     rax, [rsp+1C0h+var_158]
0x18000fa86  xor     r9d, r9d; dwReserved
0x18000fa89  mov     rcx, [r14+38h]; hSession
0x18000fa8d  mov     rdx, rdi; pswzServerName
0x18000fa90  movzx   r8d, word ptr [rax+6Ch]; nServerPort
0x18000fa95  call    cs:__imp_WinHttpConnect
0x18000fa9b  mov     [r14+40h], rax
0x18000fa9f  test    esi, esi
0x18000faa1  jnz     short loc_18000FAAC
0x18000faa3  mov     rcx, rdi; Object
0x18000faa6  call    cs:__imp_I_RpcFree
0x18000faac  cmp     qword ptr [r14+40h], 0
0x18000fab1  jnz     short loc_18000FAFA
0x18000fab3  call    cs:__imp_GetLastError
0x18000fab9  mov     [rsp+1C0h+dwFlags], 0
0x18000fac1  mov     esi, 0Eh
0x18000fac6  mov     dword ptr [rsp+1C0h+ppwszAcceptTypes], 0
0x18000face  mov     r9d, 140015h
0x18000fad4  mov     r8, r14
0x18000fad7  mov     [rsp+1C0h+BytesInMultiByteString], esi
0x18000fadb  mov     dl, 6Fh ; 'o'
0x18000fadd  mov     cl, 32h ; '2'
0x18000fadf  mov     ebx, eax
0x18000fae1  call    cs:__imp_I_RpcLogEvent
0x18000fae7  cmp     ebx, 2EE5h
0x18000faed  mov     eax, 6BAh
0x18000faf2  cmovz   esi, eax
0x18000faf5  jmp     loc_18000FC79
0x18000fafa  lea     rax, aApplicationRpc; "application/rpc"
0x18000fb01  mov     [rbp+0C0h+var_F8+8], 0
0x18000fb09  mov     rcx, r12; Src
0x18000fb0c  mov     [rbp+0C0h+var_F8], rax
0x18000fb10  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18000fb15  mov     [r14+60h], rax
0x18000fb19  test    r13, r13
0x18000fb1c  jz      short loc_18000FB2A
0x18000fb1e  test    byte ptr [r13+8], 1
0x18000fb23  mov     eax, 800100h
0x18000fb28  jnz     short loc_18000FB2F
0x18000fb2a  mov     eax, 100h
0x18000fb2f  mov     rdx, [rsp+1C0h+pwszVerb]; pwszVerb
0x18000fb34  xor     r9d, r9d; pwszVersion
0x18000fb37  mov     rcx, [r14+40h]; hConnect
0x18000fb3b  mov     r8, r12; pwszObjectName
0x18000fb3e  mov     [rsp+1C0h+dwFlags], eax; dwFlags
0x18000fb42  lea     rax, [rbp+0C0h+var_F8]
0x18000fb46  mov     [rsp+1C0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x18000fb4b  mov     qword ptr [rsp+1C0h+BytesInMultiByteString], 0; pwszReferrer
0x18000fb54  call    cs:__imp_WinHttpOpenRequest
0x18000fb5a  mov     [r14+48h], rax
0x18000fb5e  test    rax, rax
0x18000fb61  jz      loc_18000F96A
0x18000fb67  lea     r8, [r14+30h]; lpBuffer
0x18000fb6b  mov     edx, 0Ch; dwOption
0x18000fb70  lea     r9, [rbp+0C0h+dwBufferLength]; lpdwBufferLength
0x18000fb74  mov     rcx, rax; hInternet
0x18000fb77  call    cs:__imp_WinHttpQueryOption
0x18000fb7d  test    r13, r13
0x18000fb80  jz      short loc_18000FBAA
0x18000fb82  test    byte ptr [r13+8], 8
0x18000fb87  jz      short loc_18000FBAA
0x18000fb89  mov     rcx, [r14+48h]; hInternet
0x18000fb8d  lea     r8, [rsp+1C0h+var_178]; lpBuffer
0x18000fb92  mov     r9d, 4; dwBufferLength
0x18000fb98  mov     [rsp+1C0h+var_178], 1000h
0x18000fba0  lea     edx, [r9+1Bh]; dwOption
0x18000fba4  call    cs:__imp_WinHttpSetOption
0x18000fbaa  mov     r15d, [rbp+0C0h+arg_40]
0x18000fbb1  mov     r12d, [rbp+0C0h+AuthScheme]
0x18000fbb8  test    r15d, r15d
0x18000fbbb  jz      short loc_18000FBDE
0x18000fbbd  cmp     r15d, [r14+0D8h]
0x18000fbc4  jnz     short loc_18000FBD7
0x18000fbc6  cmp     r15d, 1
0x18000fbca  jz      short loc_18000FBD7
0x18000fbcc  cmp     r15d, 10h
0x18000fbd0  jz      short loc_18000FBD7
0x18000fbd2  test    r12d, r12d
0x18000fbd5  jz      short loc_18000FBDE
0x18000fbd7  mov     ecx, 1
0x18000fbdc  jmp     short loc_18000FBE0
0x18000fbde  xor     ecx, ecx
0x18000fbe0  mov     [rsp+1C0h+var_178], ecx
0x18000fbe4  test    r12d, r12d
0x18000fbe7  jz      short loc_18000FBF9
0x18000fbe9  cmp     r12d, [r14+0DCh]
0x18000fbf0  jz      short loc_18000FBF9
0x18000fbf2  mov     eax, 1
0x18000fbf7  jmp     short loc_18000FBFB
0x18000fbf9  xor     eax, eax
0x18000fbfb  mov     [rbp+0C0h+var_13C], eax
0x18000fbfe  mov     esi, 0Eh
0x18000fc03  test    ecx, ecx
0x18000fc05  jnz     short loc_18000FC3D
0x18000fc07  test    eax, eax
0x18000fc09  jnz     short loc_18000FC3D
0x18000fc0b  test    r15d, r15d
0x18000fc0e  jnz     loc_1800100B5
0x18000fc14  test    r12d, r12d
0x18000fc17  jnz     loc_1800100B5
0x18000fc1d  mov     rcx, [r14+48h]; hInternet
0x18000fc21  lea     r9d, [rax+4]; dwBufferLength
0x18000fc25  lea     r8, [rsp+1C0h+var_180]; lpBuffer
0x18000fc2a  mov     [rsp+1C0h+var_180], r12d
0x18000fc2f  lea     edx, [rax+4Dh]; dwOption
0x18000fc32  call    cs:__imp_WinHttpSetOption
0x18000fc38  jmp     loc_1800100B5
0x18000fc3d  mov     rcx, r13; struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *
0x18000fc40  call    ?I_RpcTransGetHttpCredentials@@YAPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@PEBU1@@Z; I_RpcTransGetHttpCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W const *)
0x18000fc45  mov     [rsp+1C0h+pwszVerb], rax
0x18000fc4a  mov     rdi, rax
0x18000fc4d  test    rax, rax
0x18000fc50  jnz     short loc_18000FC9B
0x18000fc52  mov     [rsp+1C0h+dwFlags], 0
0x18000fc5a  mov     r9d, 140015h
0x18000fc60  mov     dword ptr [rsp+1C0h+ppwszAcceptTypes], 0
0x18000fc68  mov     r8, r14
  ... truncated ...
```

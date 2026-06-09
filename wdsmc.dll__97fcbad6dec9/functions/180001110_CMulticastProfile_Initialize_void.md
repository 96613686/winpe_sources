# CMulticastProfile::Initialize(void)

- ea: `0x180001110`
- end: `0x1800020b5`
- name: `?Initialize@CMulticastProfile@@QEAAKXZ`
- size: `4005`
- prototype: `unsigned int __fastcall(CMulticastProfile *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005e28`

## callees

- `0x180001110`
- `0x18002218c`
- `0x1800221d4`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180002095`
- `ADVAPI32!RegCloseKey` at `0x180002095`
- `ADVAPI32!RegOpenKeyExW` at `0x18000115d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000115d`

## string_xrefs

- `0x180001151`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Protocol`
- `0x18000124e`: `TpMaxRepairs`
- `0x180001294`: `Profile[%s] Transport: Max Repairs=%u`
- `0x180001541`: `TpOpenWindowInterval`
- `0x18000158b`: `Profile[%s] Transport: Open Window Interval=%ums`
- `0x1800015a5`: `TpOpenCacheInterval`
- `0x1800015f3`: `Profile[%s] Transport: Open Cache Interval=%ums`
- `0x18000160d`: `TpCloseCacheInterval`
- `0x180001654`: `Profile[%s] Transport: Close Cache Interval=%ums`
- `0x180001671`: `TpSecurityMode`
- `0x1800016cf`: `Profile[%s] Transport: Security Mode=%u`

## pseudocode

```c
__int64 __fastcall CMulticastProfile::Initialize(CMulticastProfile *this)
{
  unsigned int ValueDwordWithDefault; // ebx
  const char *v3; // rdx
  const char *v4; // rdx
  void (*v5)(const unsigned __int16 *, ...); // rax
  unsigned int v6; // r8d
  unsigned int *v7; // rsi
  const char *v8; // rdx
  unsigned int v9; // r8d
  void (*v10)(const unsigned __int16 *, ...); // rax
  int *v11; // rsi
  const char *v12; // rdx
  int v13; // r8d
  void (*v14)(const unsigned __int16 *, ...); // rax
  int *v15; // rsi
  const char *v16; // rdx
  int v17; // r8d
  void (*v18)(const unsigned __int16 *, ...); // rax
  unsigned int *v19; // r14
  unsigned int v20; // r13d
  const char *v21; // rdx
  unsigned int v22; // ecx
  void (*v23)(const unsigned __int16 *, ...); // rax
  unsigned int v24; // edx
  unsigned int *v25; // r14
  const char *v26; // rdx
  unsigned int v27; // ecx
  void (*v28)(const unsigned __int16 *, ...); // rax
  unsigned int v29; // edx
  int *v30; // rsi
  const char *v31; // rdx
  int v32; // r8d
  void (*v33)(const unsigned __int16 *, ...); // rax
  int *v34; // rsi
  const char *v35; // rdx
  int v36; // r8d
  void (*v37)(const unsigned __int16 *, ...); // rax
  unsigned int *v38; // r14
  const char *v39; // rdx
  unsigned int v40; // r8d
  unsigned int v41; // esi
  void (*v42)(const unsigned __int16 *, ...); // rax
  int *v43; // r14
  const char *v44; // rdx
  int v45; // r8d
  void (*v46)(const unsigned __int16 *, ...); // rax
  int *v47; // r15
  const char *v48; // rdx
  unsigned int v49; // r14d
  void (*v50)(const unsigned __int16 *, ...); // rax
  int v51; // r8d
  unsigned int *v52; // r15
  const char *v53; // rdx
  void (*v54)(const unsigned __int16 *, ...); // rax
  _DWORD *v55; // r14
  const char *v56; // rdx
  __int64 v57; // r8
  const char *v58; // rdx
  const char *v59; // rdx
  const char *v60; // rdx
  const char *v61; // rdx
  const char *v62; // rdx
  unsigned int *v63; // r15
  unsigned int v64; // r14d
  const char *v65; // rdx
  void (*v66)(const unsigned __int16 *, ...); // rax
  const char *v67; // rdx
  const char *v68; // rdx
  const char *v69; // rdx
  unsigned int v70; // r12d
  const char *v71; // rdx
  const char *v72; // rdx
  unsigned int v73; // r14d
  unsigned int v74; // ecx
  unsigned int *v75; // r15
  unsigned int v76; // eax
  const char *v77; // rdx
  void (*v78)(const unsigned __int16 *, ...); // rax
  __int64 v79; // r8
  const wchar_t *v80; // rcx
  unsigned int v81; // eax
  const char *v82; // rdx
  void (*v83)(const unsigned __int16 *, ...); // rax
  unsigned int *v84; // rsi
  const char *v85; // rdx
  unsigned int *v86; // rsi
  unsigned int Value; // eax
  unsigned int *v88; // r14
  const char *v89; // rdx
  unsigned int v90; // r8d
  unsigned int v91; // esi
  void (*v92)(const unsigned __int16 *, ...); // rax
  unsigned int *v93; // r14
  const char *v94; // rdx
  unsigned int v95; // r8d
  void (*v96)(const unsigned __int16 *, ...); // rax
  unsigned int *v97; // r14
  const char *v98; // rdx
  unsigned int v99; // r8d
  void (*v100)(const unsigned __int16 *, ...); // rax
  unsigned int *v101; // r14
  const char *v102; // rdx
  void (*v103)(const unsigned __int16 *, ...); // rax
  int *v104; // rsi
  const char *v105; // rdx
  void (*v106)(const unsigned __int16 *, ...); // rax
  int v107; // r8d
  int *v108; // rsi
  const char *v109; // rdx
  int v110; // r8d
  void (*v111)(const unsigned __int16 *, ...); // rax
  unsigned int *v112; // rsi
  const char *v113; // rdx
  void (*v114)(const unsigned __int16 *, ...); // rax
  unsigned int *v115; // rsi
  const char *v116; // rdx
  void (*v117)(const unsigned __int16 *, ...); // rax
  const char *v118; // rdx
  const char *v119; // rdx
  int v121; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v123; // [rsp+88h] [rbp+48h] BYREF
  unsigned int v124; // [rsp+90h] [rbp+50h] BYREF
  unsigned int v125; // [rsp+98h] [rbp+58h] BYREF

  v124 = 0;
  v125 = 0;
  v123 = 0;
  hKey = 0;
  ValueDwordWithDefault = RegOpenKeyExW(
                            HKEY_LOCAL_MACHINE,
                            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Protocol",
                            0,
                            0x20119u,
                            &hKey);
  if ( !ElValidateWin32(ValueDwordWithDefault, v3, "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp", 0x34u) )
  {
    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                              (CRegKey *)&hKey,
                              L"TpExpWindowSize",
                              2u,
                              (unsigned int *)this);
    if ( !ElValidateWin32(ValueDwordWithDefault, v4, "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp", 0x3Eu) )
    {
      v5 = g_ErrLibTraceFunction;
      v6 = 2;
      if ( *(_DWORD *)this > 2u )
        v6 = *(_DWORD *)this;
      *(_DWORD *)this = v6;
      if ( v5 )
        v5(L"Profile[%s] Transport: Exp Window Size=%u packets.", L"Default");
      v7 = (unsigned int *)((char *)this + 4);
      ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                (CRegKey *)&hKey,
                                L"TpMaxWindowSize",
                                0x1000u,
                                (unsigned int *)this + 1);
      if ( !ElValidateWin32(ValueDwordWithDefault, v8, "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp", 0x4Du) )
      {
        v9 = *v7;
        v10 = g_ErrLibTraceFunction;
        if ( *v7 <= *(_DWORD *)this )
          v9 = *(_DWORD *)this;
        *v7 = v9;
        if ( v10 )
          v10(L"Profile[%s] Transport: Max Window Size=%u packets.", L"Default");
        v11 = (int *)((char *)this + 8);
        ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                  (CRegKey *)&hKey,
                                  L"TpMaxRepairs",
                                  2u,
                                  (unsigned int *)this + 2);
        if ( !ElValidateWin32(ValueDwordWithDefault, v12, "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp", 0x5Cu) )
        {
          v13 = *v11;
          v14 = g_ErrLibTraceFunction;
          if ( !*v11 )
            v13 = 0;
          *v11 = v13;
          if ( v14 )
            v14(L"Profile[%s] Transport: Max Repairs=%u", L"Default");
          v15 = (int *)((char *)this + 12);
          ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                    (CRegKey *)&hKey,
                                    L"TpClientInactiveTimeout",
                                    0xEA60u,
                                    (unsigned int *)this + 3);
          if ( !ElValidateWin32(
                  ValueDwordWithDefault,
                  v16,
                  "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                  0x6Bu) )
          {
            v17 = 60000;
            v18 = g_ErrLibTraceFunction;
            if ( (unsigned int)*v15 > 0xEA60 )
              v17 = *v15;
            *v15 = v17;
            if ( v18 )
              v18(L"Profile[%s] Transport: Client Inactive Timeout=%ums", L"Default");
            v19 = (unsigned int *)((char *)this + 16);
            v20 = 15000;
            ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                      (CRegKey *)&hKey,
                                      L"TpKeepAliveInterval",
                                      0x3A98u,
                                      (unsigned int *)this + 4);
            if ( !ElValidateWin32(
                    ValueDwordWithDefault,
                    v21,
                    "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                    0x7Au) )
            {
              v22 = 15000;
              if ( *v19 > 0x3A98 )
                v22 = *v19;
              v23 = g_ErrLibTraceFunction;
              v24 = *v15 / 3u;
              if ( v24 >= v22 )
                v24 = v22;
              *v19 = v24;
              if ( v23 )
                v23(L"Profile[%s] Transport: Client Keep Alive Interval=%ums", L"Default", v24);
              v25 = (unsigned int *)((char *)this + 20);
              ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                        (CRegKey *)&hKey,
                                        L"TpKickInterval",
                                        0x3A98u,
                                        (unsigned int *)this + 5);
              if ( !ElValidateWin32(
                      ValueDwordWithDefault,
                      v26,
                      "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                      0x90u) )
              {
                v27 = 15000;
                if ( *v25 > 0x3A98 )
                  v27 = *v25;
                v28 = g_ErrLibTraceFunction;
                v29 = *v15 / 3u;
                if ( v29 >= v27 )
                  v29 = v27;
                *v25 = v29;
                if ( v28 )
                  v28(L"Profile[%s] Transport: Kick Interval=%ums", L"Default", v29);
                v30 = (int *)((char *)this + 24);
                ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                          (CRegKey *)&hKey,
                                          L"TpSockSendSize",
                                          0x10u,
                                          (unsigned int *)this + 6);
                if ( !ElValidateWin32(
                        ValueDwordWithDefault,
                        v31,
                        "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                        0xA4u) )
                {
                  v32 = *v30;
                  v33 = g_ErrLibTraceFunction;
                  if ( (unsigned int)*v30 < 0x10 )
                    v32 = 16;
                  *v30 = v32 << 10;
                  if ( v33 )
                    v33(L"Profile[%s] Transport: Socket Send Buffer Size=%u bytes", L"Default");
                  v34 = (int *)((char *)this + 28);
                  ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                            (CRegKey *)&hKey,
                                            L"TpSockRecvSize",
                                            0x10u,
                                            (unsigned int *)this + 7);
                  if ( !ElValidateWin32(
                          ValueDwordWithDefault,
                          v35,
                          "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                          0xB4u) )
                  {
                    v36 = *v34;
                    v37 = g_ErrLibTraceFunction;
                    if ( (unsigned int)*v34 < 0x10 )
                      v36 = 16;
                    *v34 = v36 << 10;
                    if ( v37 )
                      v37(L"Profile[%s] Transport: Socket Recv Buffer Size=%u bytes", L"Default");
                    v38 = (unsigned int *)((char *)this + 32);
                    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                              (CRegKey *)&hKey,
                                              L"TpMulticastTTL",
                                              0x20u,
                                              (unsigned int *)this + 8);
                    if ( !ElValidateWin32(
                            ValueDwordWithDefault,
                            v39,
                            "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                            0xC4u) )
                    {
                      v40 = *v38;
                      v41 = 1;
                      if ( *v38 )
                      {
                        if ( v40 > 0xFF )
                          v40 = 255;
                      }
                      else
                      {
                        v40 = 1;
                      }
                      v42 = g_ErrLibTraceFunction;
                      *v38 = v40;
                      if ( v42 )
                        v42(L"Profile[%s] Transport: Multicast TTL=%u", L"Default");
                      v43 = (int *)((char *)this + 40);
                      ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                (CRegKey *)&hKey,
                                                L"TpOpenWindowInterval",
                                                5u,
                                                (unsigned int *)this + 10);
                      if ( !ElValidateWin32(
                              ValueDwordWithDefault,
                              v44,
                              "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                              0xD3u) )
                      {
                        v45 = 1;
                        v46 = g_ErrLibTraceFunction;
                        if ( (unsigned int)*v43 > 1 )
                          v45 = *v43;
                        *v43 = v45;
                        if ( v46 )
                          v46(L"Profile[%s] Transport: Open Window Interval=%ums", L"Default");
                        v47 = (int *)((char *)this + 44);
                        ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                  (CRegKey *)&hKey,
                                                  L"TpOpenCacheInterval",
                                                  0x50u,
                                                  (unsigned int *)this + 11);
                        if ( !ElValidateWin32(
                                ValueDwordWithDefault,
                                v48,
                                "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                0xE2u) )
                        {
                          v49 = 10;
                          v50 = g_ErrLibTraceFunction;
                          v51 = 10;
                          if ( (unsigned int)*v47 > 0xA )
                            v51 = *v47;
                          *v47 = v51;
                          if ( v50 )
                            v50(L"Profile[%s] Transport: Open Cache Interval=%ums", L"Default");
                          v52 = (unsigned int *)((char *)this + 48);
                          ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                    (CRegKey *)&hKey,
                                                    L"TpCloseCacheInterval",
                                                    0x258u,
                                                    (unsigned int *)this + 12);
                          if ( !ElValidateWin32(
                                  ValueDwordWithDefault,
                                  v53,
                                  "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                  0xF1u) )
                          {
                            v54 = g_ErrLibTraceFunction;
                            if ( *v52 > 0xA )
                              v49 = *v52;
                            *v52 = v49;
                            if ( v54 )
                              v54(L"Profile[%s] Transport: Close Cache Interval=%ums", L"Default", v49);
                            v55 = (_DWORD *)((char *)this + 52);
                            ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                      (CRegKey *)&hKey,
                                                      L"TpSecurityMode",
                                                      0x10001u,
                                                      (unsigned int *)this + 13);
                            if ( !ElValidateWin32(
                                    ValueDwordWithDefault,
                                    v56,
                                    "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                    0x100u) )
                            {
                              v57 = (unsigned int)*v55;
                              if ( (_DWORD)v57 && (_DWORD)v57 != 65537 && (_DWORD)v57 != 131073 )
                              {
                                *v55 = 65537;
                                v57 = 65537;
                              }
                              if ( g_ErrLibTraceFunction )
                                g_ErrLibTraceFunction(L"Profile[%s] Transport: Security Mode=%u", L"Default", v57);
                              ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                        (CRegKey *)&hKey,
                                                        L"TpSecRSAKeyLen",
                                                        0x800u,
                                                        (unsigned int *)this + 14);
                              if ( !ElValidateWin32(
                                      ValueDwordWithDefault,
                                      v58,
                                      "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                      0x11Au) )
                              {
                                if ( g_ErrLibTraceFunction )
                                  g_ErrLibTraceFunction(
                                    L"Profile[%s] Transport: RSA Key Length=%u",
                                    L"Default",
                                    *((unsigned int *)this + 14));
                                ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                          (CRegKey *)&hKey,
                                                          L"TpSecHashAlgId",
                                                          0x800Cu,
                                                          (unsigned int *)this + 15);
                                if ( !ElValidateWin32(
                                        ValueDwordWithDefault,
                                        v59,
                                        "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                        0x128u) )
                                {
                                  if ( g_ErrLibTraceFunction )
                                    g_ErrLibTraceFunction(
                                      L"Profile[%s] Transport: Hash Algorithm=%u",
                                      L"Default",
                                      *((unsigned int *)this + 15));
                                  ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                            (CRegKey *)&hKey,
                                                            L"TpSecHMACAlgId",
                                                            0x8009u,
                                                            (unsigned int *)this + 16);
                                  if ( !ElValidateWin32(
                                          ValueDwordWithDefault,
                                          v60,
                                          "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                          0x136u) )
                                  {
                                    if ( g_ErrLibTraceFunction )
                                      g_ErrLibTraceFunction(
                                        L"Profile[%s] Transport: HMAC Algorithm=%u",
                                        L"Default",
                                        *((unsigned int *)this + 16));
                                    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                              (CRegKey *)&hKey,
                                                              L"TpSecHMACKeyAlgId",
                                                              0x6603u,
                                                              (unsigned int *)this + 17);
                                    if ( !ElValidateWin32(
                                            ValueDwordWithDefault,
                                            v61,
                                            "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                            0x144u) )
                                    {
                                      if ( g_ErrLibTraceFunction )
                                        g_ErrLibTraceFunction(
                                          L"Profile[%s] Transport: HMAC Symmetric Key Algorithm=%u",
                                          L"Default",
                                          *((unsigned int *)this + 17));
                                      ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                (CRegKey *)&hKey,
                                                                L"TpSecHMACKeyLen",
                                                                0,
                                                                (unsigned int *)this + 18);
                                      if ( !ElValidateWin32(
                                              ValueDwordWithDefault,
                                              v62,
                                              "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                              0x152u) )
                                      {
                                        if ( g_ErrLibTraceFunction )
                                          g_ErrLibTraceFunction(
                                            L"Profile[%s] Transport: HMAC Symmetric Key Length=%u",
                                            L"Default",
                                            *((unsigned int *)this + 18));
                                        v63 = (unsigned int *)((char *)this + 36);
                                        v64 = 100;
                                        ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                  (CRegKey *)&hKey,
                                                                  L"TpMaxBandwidth",
                                                                  0x64u,
                                                                  (unsigned int *)this + 9);
                                        if ( !ElValidateWin32(
                                                ValueDwordWithDefault,
                                                v65,
                                                "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                0x160u) )
                                        {
                                          v66 = g_ErrLibTraceFunction;
                                          if ( *v63 < 0x64 )
                                            v64 = *v63;
                                          *v63 = v64;
                                          if ( v66 )
                                            v66(L"Profile[%s] Server: Maximum Bandwidth=%u%%", L"Default", v64);
                                          ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                    (CRegKey *)&hKey,
                                                                    L"TpMaxBwPerSessionGroup",
                                                                    0,
                                                                    (unsigned int *)this + 20);
                                          if ( !ElValidateWin32(
                                                  ValueDwordWithDefault,
                                                  v67,
                                                  "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                  0x16Fu) )
                                          {
                                            if ( g_ErrLibTraceFunction )
                                              g_ErrLibTraceFunction(
                                                L"Profile[%s] Transport: Max Bandwidth Per Session Group=%u",
                                                L"Default",
                                                *((unsigned int *)this + 20));
                                            ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                      (CRegKey *)&hKey,
                                                                      L"TpSlowClientHandling",
                                                                      1u,
                                                                      &v124);
                                            if ( !ElValidateWin32(
                                                    ValueDwordWithDefault,
                                                    v68,
                                                    "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                    0x17Du) )
                                            {
                                              if ( g_ErrLibTraceFunction )
                                                g_ErrLibTraceFunction(
                                                  L"Profile[%s] Transport: Slow Client Handling Policy=%u",
                                                  L"Default",
                                                  v124);
                                              ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                        (CRegKey *)&hKey,
                                                                        L"TpSlowClientFallback",
                                                                        1u,
                                                                        &v125);
                                              if ( !ElValidateWin32(
                                                      ValueDwordWithDefault,
                                                      v69,
                                                      "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                      0x18Bu) )
                                              {
                                                if ( g_ErrLibTraceFunction )
                                                  g_ErrLibTraceFunction(
                                                    L"Profile[%s] Transport: Slow Client Fallback=%u",
                                                    L"Default",
                                                    v125);
                                                v70 = 10000;
                                                ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                          (CRegKey *)&hKey,
                                                                          L"TpSlowClientWaitTime",
                                                                          0x2710u,
                                                                          &v123);
                                                if ( !ElValidateWin32(
                                                        ValueDwordWithDefault,
                                                        v71,
                                                        "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                        0x199u) )
                                                {
                                                  v73 = 500;
                                                  v74 = 500;
                                                  if ( v123 > 0x1F4 )
                                                    v74 = v123;
                                                  v123 = v74;
                                                  if ( g_ErrLibTraceFunction )
                                                  {
                                                    g_ErrLibTraceFunction(
                                                      L"Profile[%s] Transport: Slow Client Wait Time=%u ms",
                                                      L"Default",
                                                      v74);
                                                    v74 = v123;
                                                  }
                                                  v75 = (unsigned int *)((char *)this + 104);
                                                  if ( v124 == 2 )
                                                  {
                                                    v76 = v125;
                                                    *((_DWORD *)this + 25) = v74;
                                                    *v75 = 1;
                                                    *((_DWORD *)this + 22) = 1;
                                                    *((_DWORD *)this + 23) = v76;
                                                    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                              (CRegKey *)&hKey,
                                                                              L"TpAutoKickThreshold",
                                                                              0x40000u,
                                                                              (unsigned int *)this + 24);
                                                    if ( ElValidateWin32(
                                                           ValueDwordWithDefault,
                                                           v77,
                                                           "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                           0x1B2u) )
                                                    {
                                                      goto LABEL_189;
                                                    }
                                                    v78 = g_ErrLibTraceFunction;
                                                    if ( !g_ErrLibTraceFunction )
                                                      goto LABEL_127;
                                                    v79 = *((unsigned int *)this + 24);
                                                    v80 = L"Profile[%s] Transport: Auto Kick Threshold=%u bytes/sec";
LABEL_125:
                                                    v78(v80, L"Default", v79);
LABEL_127:
                                                    v86 = (unsigned int *)((char *)this + 84);
                                                    v121 = 0;
                                                    if ( this == (CMulticastProfile *)-84LL )
                                                    {
                                                      ValueDwordWithDefault = 87;
                                                    }
                                                    else
                                                    {
                                                      Value = CRegKey::GetValue(
                                                                (CRegKey *)&hKey,
                                                                L"TpLowResMonitor",
                                                                4u,
                                                                &v121,
                                                                4u);
                                                      ValueDwordWithDefault = Value;
                                                      if ( Value )
                                                      {
                                                        if ( Value == 2 )
                                                        {
                                                          ValueDwordWithDefault = 0;
                                                          *v86 = 0;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        *v86 = v121 != 0;
                                                      }
                                                    }
                                                    if ( !ElValidateWin32(
                                                            ValueDwordWithDefault,
                                                            v72,
                                                            "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                            0x1EDu) )
                                                    {
                                                      if ( g_ErrLibTraceFunction )
                                                        g_ErrLibTraceFunction(
                                                          L"Profile[%s] Transport: Low Resources Monitor=%u",
                                                          L"Default",
                                                          *v86);
                                                      v88 = (unsigned int *)((char *)this + 120);
                                                      ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                (CRegKey *)&hKey,
                                                                                L"ApBlockSizeV4",
                                                                                0x56Bu,
                                                                                (unsigned int *)this + 30);
                                                      if ( !ElValidateWin32(
                                                              ValueDwordWithDefault,
                                                              v89,
                                                              "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                              0x1FCu) )
                                                      {
                                                        v90 = *v88;
                                                        v91 = 512;
                                                        if ( *v88 >= 0x200 )
                                                        {
                                                          if ( v90 > 0xE800 )
                                                            v90 = 59392;
                                                        }
                                                        else
                                                        {
                                                          v90 = 512;
                                                        }
                                                        v92 = g_ErrLibTraceFunction;
                                                        *v88 = v90;
                                                        if ( v92 )
                                                          v92(
                                                            L"Profile[%s] Application: Block Size (IPv4)=%u bytes",
                                                            L"Default");
                                                        v93 = (unsigned int *)((char *)this + 124);
                                                        ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                  (CRegKey *)&hKey,
                                                                                  L"ApBlockSizeV6",
                                                                                  0x557u,
                                                                                  (unsigned int *)this + 31);
                                                        if ( !ElValidateWin32(
                                                                ValueDwordWithDefault,
                                                                v94,
                                                                "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                0x20Eu) )
                                                        {
                                                          v95 = *v93;
                                                          if ( *v93 >= 0x200 )
                                                          {
                                                            if ( v95 > 0xE800 )
                                                              v95 = 59392;
                                                          }
                                                          else
                                                          {
                                                            v95 = 512;
                                                          }
                                                          v96 = g_ErrLibTraceFunction;
                                                          *v93 = v95;
                                                          if ( v96 )
                                                            v96(
                                                              L"Profile[%s] Application: Block Size (IPv6)=%u bytes",
                                                              L"Default");
                                                          v97 = (unsigned int *)((char *)this + 128);
                                                          ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                    (CRegKey *)&hKey,
                                                                                    L"ApBootBlockSizeV4",
                                                                                    0x400u,
                                                                                    (unsigned int *)this + 32);
                                                          if ( !ElValidateWin32(
                                                                  ValueDwordWithDefault,
                                                                  v98,
                                                                  "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                  0x220u) )
                                                          {
                                                            v99 = *v97;
                                                            if ( *v97 >= 0x200 )
                                                            {
                                                              if ( v99 > 0xE800 )
                                                                v99 = 59392;
                                                            }
                                                            else
                                                            {
                                                              v99 = 512;
                                                            }
                                                            v100 = g_ErrLibTraceFunction;
                                                            *v97 = v99;
                                                            if ( v100 )
                                                              v100(
                                                                L"Profile[%s] Application: Boot Block Size (IPv4)=%u bytes",
                                                                L"Default");
                                                            v101 = (unsigned int *)((char *)this + 132);
                                                            ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                      (CRegKey *)&hKey,
                                                                                      L"ApBootBlockSizeV6",
                                                                                      0x400u,
                                                                                      (unsigned int *)this + 33);
                                                            if ( !ElValidateWin32(
                                                                    ValueDwordWithDefault,
                                                                    v102,
                                                                    "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                    0x232u) )
                                                            {
                                                              if ( *v101 >= 0x200 )
                                                              {
                                                                v91 = *v101;
                                                                if ( *v101 > 0xE800 )
                                                                  v91 = 59392;
                                                              }
                                                              v103 = g_ErrLibTraceFunction;
                                                              *v101 = v91;
                                                              if ( v103 )
                                                                v103(
                                                                  L"Profile[%s] Application: Boot Block Size (IPv6)=%u bytes",
                                                                  L"Default",
                                                                  v91);
                                                              v104 = (int *)((char *)this + 136);
                                                              ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                        (CRegKey *)&hKey,
                                                                                        L"ApInactiveSessionTimeout",
                                                                                        0x493E0u,
                                                                                        (unsigned int *)this + 34);
                                                              if ( !ElValidateWin32(
                                                                      ValueDwordWithDefault,
                                                                      v105,
                                                                      "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                      0x244u) )
                                                              {
                                                                v106 = g_ErrLibTraceFunction;
                                                                v107 = 20000;
                                                                if ( (unsigned int)*v104 > 0x4E20 )
                                                                  v107 = *v104;
                                                                *v104 = v107;
                                                                if ( v106 )
                                                                  v106(
                                                                    L"Profile[%s] Application: Inactive Session Timeout=%ums",
                                                                    L"Default");
                                                                v108 = (int *)((char *)this + 140);
                                                                ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                          (CRegKey *)&hKey,
                                                                                          L"ApInactiveNamespaceTimeout",
                                                                                          0x1B7740u,
                                                                                          (unsigned int *)this + 35);
                                                                if ( !ElValidateWin32(
                                                                        ValueDwordWithDefault,
                                                                        v109,
                                                                        "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                        0x254u) )
                                                                {
                                                                  v110 = 60000;
                                                                  v111 = g_ErrLibTraceFunction;
                                                                  if ( (unsigned int)*v108 > 0xEA60 )
                                                                    v110 = *v108;
                                                                  *v108 = v110;
                                                                  if ( v111 )
                                                                    v111(
                                                                      L"Profile[%s] Application: Inactive Namespace Timeout=%ums",
                                                                      L"Default");
                                                                  v112 = (unsigned int *)((char *)this + 144);
                                                                  ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                            (CRegKey *)&hKey,
                                                                                            L"ApCRRMergeInterval",
                                                                                            0x7530u,
                                                                                            (unsigned int *)this + 36);
                                                                  if ( !ElValidateWin32(
                                                                          ValueDwordWithDefault,
                                                                          v113,
                                                                          "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                          0x264u) )
                                                                  {
                                                                    v114 = g_ErrLibTraceFunction;
                                                                    if ( *v112 > 0x2710 )
                                                                      v70 = *v112;
                                                                    *v112 = v70;
                                                                    if ( v114 )
                                                                      v114(
                                                                        L"Profile[%s] Application: CRR Merge Interval=%ums",
                                                                        L"Default",
                                                                        v70);
                                                                    v115 = (unsigned int *)((char *)this + 148);
                                                                    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                              (CRegKey *)&hKey,
                                                                                              L"ApForceCIRInterval",
                                                                                              0xEA60u,
                                                                                              (unsigned int *)this + 37);
                                                                    if ( !ElValidateWin32(
                                                                            ValueDwordWithDefault,
                                                                            v116,
                                                                            "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                            0x274u) )
                                                                    {
                                                                      v117 = g_ErrLibTraceFunction;
                                                                      if ( *v115 > 0x3A98 )
                                                                        v20 = *v115;
                                                                      *v115 = v20;
                                                                      if ( v117 )
                                                                        v117(
                                                                          L"Profile[%s] Application: Force CIR Interval=%ums",
                                                                          L"Default",
                                                                          v20);
                                                                      ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                                (CRegKey *)&hKey,
                                                                                                L"SrvAllowBootClients",
                                                                                                0,
                                                                                                (unsigned int *)this
                                                                                              + 38);
                                                                      if ( !ElValidateWin32(
                                                                              ValueDwordWithDefault,
                                                                              v118,
                                                                              "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                              0x283u) )
                                                                      {
                                                                        if ( g_ErrLibTraceFunction )
                                                                          g_ErrLibTraceFunction(
                                                                            L"Profile[%s] Server: Allow Boot Clients=%u",
                                                                            L"Default",
                                                                            *((unsigned int *)this + 38));
                                                                        ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                                                  (CRegKey *)&hKey,
                                                                                                  L"TpForceIPv4",
                                                                                                  0,
                                                                                                  (unsigned int *)this
                                                                                                + 19);
                                                                        if ( !ElValidateWin32(
                                                                                ValueDwordWithDefault,
                                                                                v119,
                                                                                "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                                                0x291u)
                                                                          && g_ErrLibTraceFunction )
                                                                        {
                                                                          g_ErrLibTraceFunction(
                                                                            L"Profile[%s] Transport: Force IPv4=%u",
                                                                            L"Default",
                                                                            *((unsigned int *)this + 19));
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                    goto LABEL_189;
                                                  }
                                                  if ( v124 != 3 )
                                                  {
                                                    *((_DWORD *)this + 22) = 0;
                                                    *v75 = 1;
                                                    goto LABEL_127;
                                                  }
                                                  v81 = v125;
                                                  *((_DWORD *)this + 27) = v74;
                                                  *((_DWORD *)this + 29) = v81;
                                                  ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                            (CRegKey *)&hKey,
                                                                            L"TpMultiStreamCount",
                                                                            1u,
                                                                            (unsigned int *)this + 26);
                                                  if ( !ElValidateWin32(
                                                          ValueDwordWithDefault,
                                                          v82,
                                                          "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                          0x1C6u) )
                                                  {
                                                    if ( *v75 )
                                                    {
                                                      v41 = *v75;
                                                      if ( *v75 > 3 )
                                                        v41 = 3;
                                                    }
                                                    v83 = g_ErrLibTraceFunction;
                                                    *v75 = v41;
                                                    if ( v83 )
                                                      v83(L"Profile[%s] Transport: Total Streams=%u", L"Default", v41);
                                                    v84 = (unsigned int *)((char *)this + 112);
                                                    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                                              (CRegKey *)&hKey,
                                                                              L"TpMultistreamDemoteInterval",
                                                                              0x1F4u,
                                                                              (unsigned int *)this + 28);
                                                    if ( !ElValidateWin32(
                                                            ValueDwordWithDefault,
                                                            v85,
                                                            "base\\eco\\wds\\transport\\server\\mc\\mcprofile.cpp",
                                                            0x1D8u) )
                                                    {
                                                      v78 = g_ErrLibTraceFunction;
                                                      if ( *v84 > 0x1F4 )
                                                        v73 = *v84;
                                                      *v84 = v73;
                                                      if ( !v78 )
                                                        goto LABEL_127;
                                                      v79 = v73;
                                                      v80 = L"Profile[%s] Transport: Multistream Demote Interval=%u ms";
                                                      goto LABEL_125;
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_189:
  if ( hKey )
    RegCloseKey(hKey);
  return ValueDwordWithDefault;
}

```

## disassembly

```asm
0x180001110  mov     [rsp-38h+arg_0], rbx
0x180001115  push    rbp
0x180001116  push    rsi
0x180001117  push    rdi
0x180001118  push    r12
0x18000111a  push    r13
0x18000111c  push    r14
0x18000111e  push    r15
0x180001120  mov     rbp, rsp
0x180001123  sub     rsp, 40h
0x180001127  xor     r15d, r15d
0x18000112a  lea     rax, [rbp+hKey]
0x18000112e  mov     rdi, rcx
0x180001131  mov     [rbp+arg_10], r15d
0x180001135  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000113c  mov     [rbp+arg_18], r15d
0x180001140  mov     r9d, 20119h; samDesired
0x180001146  mov     [rbp+arg_8], r15d
0x18000114a  xor     r8d, r8d; ulOptions
0x18000114d  mov     [rbp+hKey], r15
0x180001151  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x180001158  mov     [rsp+40h+phkResult], rax; phkResult
0x18000115d  call    cs:__imp_RegOpenKeyExW
0x180001163  lea     r14, aBaseEcoWdsTran_16; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000116a  mov     ecx, eax; unsigned int
0x18000116c  mov     r8, r14; char *
0x18000116f  lea     r9d, [r15+34h]; unsigned int
0x180001173  mov     ebx, eax
0x180001175  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000117a  test    eax, eax
0x18000117c  jnz     loc_18000208C
0x180001182  lea     r13d, [r15+2]
0x180001186  mov     r9, rdi; unsigned int *
0x180001189  mov     r8d, r13d; unsigned int
0x18000118c  lea     rdx, aTpexpwindowsiz; "TpExpWindowSize"
0x180001193  lea     rcx, [rbp+hKey]; this
0x180001197  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000119c  lea     r9d, [r15+3Eh]; unsigned int
0x1800011a0  mov     r8, r14; char *
0x1800011a3  mov     ecx, eax; unsigned int
0x1800011a5  mov     ebx, eax
0x1800011a7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800011ac  test    eax, eax
0x1800011ae  jnz     loc_18000208C
0x1800011b4  cmp     [rdi], r13d
0x1800011b7  lea     r12, aDefault; "Default"
0x1800011be  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800011c5  mov     r8d, r13d
0x1800011c8  cmova   r8d, [rdi]
0x1800011cc  mov     [rdi], r8d
0x1800011cf  test    rax, rax
0x1800011d2  jz      short loc_1800011E4
0x1800011d4  mov     rdx, r12
0x1800011d7  lea     rcx, aProfileSTransp_1; "Profile[%s] Transport: Exp Window Size="...
0x1800011de  call    cs:__guard_dispatch_icall_fptr
0x1800011e4  lea     rsi, [rdi+4]
0x1800011e8  mov     r8d, 1000h; unsigned int
0x1800011ee  mov     r9, rsi; unsigned int *
0x1800011f1  lea     rdx, aTpmaxwindowsiz; "TpMaxWindowSize"
0x1800011f8  lea     rcx, [rbp+hKey]; this
0x1800011fc  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180001201  mov     r9d, 4Dh ; 'M'; unsigned int
0x180001207  mov     r8, r14; char *
0x18000120a  mov     ecx, eax; unsigned int
0x18000120c  mov     ebx, eax
0x18000120e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001213  test    eax, eax
0x180001215  jnz     loc_18000208C
0x18000121b  mov     r8d, [rsi]
0x18000121e  cmp     r8d, [rdi]
0x180001221  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180001228  cmovbe  r8d, [rdi]
0x18000122c  mov     [rsi], r8d
0x18000122f  test    rax, rax
0x180001232  jz      short loc_180001244
0x180001234  mov     rdx, r12
0x180001237  lea     rcx, aProfileSTransp_14; "Profile[%s] Transport: Max Window Size="...
0x18000123e  call    cs:__guard_dispatch_icall_fptr
0x180001244  lea     rsi, [rdi+8]
0x180001248  mov     r8d, r13d; unsigned int
0x18000124b  mov     r9, rsi; unsigned int *
0x18000124e  lea     rdx, aTpmaxrepairs; "TpMaxRepairs"
0x180001255  lea     rcx, [rbp+hKey]; this
0x180001259  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000125e  mov     r9d, 5Ch ; '\'; unsigned int
0x180001264  mov     r8, r14; char *
0x180001267  mov     ecx, eax; unsigned int
0x180001269  mov     ebx, eax
0x18000126b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001270  test    eax, eax
0x180001272  jnz     loc_18000208C
0x180001278  mov     r8d, [rsi]
0x18000127b  test    r8d, r8d
0x18000127e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180001285  cmovz   r8d, r15d
0x180001289  mov     [rsi], r8d
0x18000128c  test    rax, rax
0x18000128f  jz      short loc_1800012A1
0x180001291  mov     rdx, r12
0x180001294  lea     rcx, aProfileSTransp_3; "Profile[%s] Transport: Max Repairs=%u"
0x18000129b  call    cs:__guard_dispatch_icall_fptr
0x1800012a1  lea     rsi, [rdi+0Ch]
0x1800012a5  mov     r13d, 0EA60h
0x1800012ab  mov     r9, rsi; unsigned int *
0x1800012ae  lea     rdx, aTpclientinacti; "TpClientInactiveTimeout"
0x1800012b5  mov     r8d, r13d; unsigned int
0x1800012b8  lea     rcx, [rbp+hKey]; this
0x1800012bc  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x1800012c1  mov     r9d, 6Bh ; 'k'; unsigned int
0x1800012c7  mov     r8, r14; char *
0x1800012ca  mov     ecx, eax; unsigned int
0x1800012cc  mov     ebx, eax
0x1800012ce  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800012d3  test    eax, eax
0x1800012d5  jnz     loc_18000208C
0x1800012db  cmp     [rsi], r13d
0x1800012de  mov     r8d, r13d
0x1800012e1  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800012e8  cmova   r8d, [rsi]
0x1800012ec  mov     [rsi], r8d
0x1800012ef  test    rax, rax
0x1800012f2  jz      short loc_180001304
0x1800012f4  mov     rdx, r12
0x1800012f7  lea     rcx, aProfileSTransp_11; "Profile[%s] Transport: Client Inactive "...
0x1800012fe  call    cs:__guard_dispatch_icall_fptr
0x180001304  lea     r14, [rdi+10h]
0x180001308  mov     r13d, 3A98h
0x18000130e  mov     r9, r14; unsigned int *
0x180001311  lea     rdx, aTpkeepaliveint; "TpKeepAliveInterval"
0x180001318  mov     r8d, r13d; unsigned int
0x18000131b  lea     rcx, [rbp+hKey]; this
0x18000131f  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180001324  mov     r9d, 7Ah ; 'z'; unsigned int
0x18000132a  lea     r8, aBaseEcoWdsTran_16; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180001331  mov     ecx, eax; unsigned int
0x180001333  mov     ebx, eax
0x180001335  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000133a  test    eax, eax
0x18000133c  jnz     loc_18000208C
0x180001342  cmp     [r14], r13d
0x180001345  mov     eax, 0AAAAAAABh
0x18000134a  mov     ecx, r13d
0x18000134d  cmova   ecx, [r14]
0x180001351  mul     dword ptr [rsi]
0x180001353  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000135a  shr     edx, 1
0x18000135c  cmp     edx, ecx
0x18000135e  cmovnb  edx, ecx
0x180001361  mov     [r14], edx
0x180001364  test    rax, rax
0x180001367  jz      short loc_18000137C
0x180001369  mov     r8d, edx
0x18000136c  lea     rcx, aProfileSTransp_15; "Profile[%s] Transport: Client Keep Aliv"...
0x180001373  mov     rdx, r12
0x180001376  call    cs:__guard_dispatch_icall_fptr
0x18000137c  lea     r14, [rdi+14h]
0x180001380  mov     r8d, r13d; unsigned int
0x180001383  mov     r9, r14; unsigned int *
0x180001386  lea     rdx, aTpkickinterval; "TpKickInterval"
0x18000138d  lea     rcx, [rbp+hKey]; this
0x180001391  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180001396  mov     r9d, 90h; unsigned int
0x18000139c  lea     r8, aBaseEcoWdsTran_16; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800013a3  mov     ecx, eax; unsigned int
0x1800013a5  mov     ebx, eax
0x1800013a7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800013ac  test    eax, eax
0x1800013ae  jnz     loc_18000208C
0x1800013b4  cmp     [r14], r13d
0x1800013b7  mov     eax, 0AAAAAAABh
0x1800013bc  mov     ecx, r13d
0x1800013bf  cmova   ecx, [r14]
0x1800013c3  mul     dword ptr [rsi]
0x1800013c5  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800013cc  shr     edx, 1
0x1800013ce  cmp     edx, ecx
0x1800013d0  cmovnb  edx, ecx
0x1800013d3  mov     [r14], edx
0x1800013d6  test    rax, rax
0x1800013d9  jz      short loc_1800013EE
0x1800013db  mov     r8d, edx
0x1800013de  lea     rcx, aProfileSTransp_2; "Profile[%s] Transport: Kick Interval=%u"...
0x1800013e5  mov     rdx, r12
0x1800013e8  call    cs:__guard_dispatch_icall_fptr
0x1800013ee  lea     rsi, [rdi+18h]
0x1800013f2  mov     r14d, 10h
0x1800013f8  mov     r9, rsi; unsigned int *
0x1800013fb  lea     rdx, aTpsocksendsize; "TpSockSendSize"
0x180001402  mov     r8d, r14d; unsigned int
0x180001405  lea     rcx, [rbp+hKey]; this
0x180001409  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000140e  mov     r9d, 0A4h; unsigned int
0x180001414  lea     r8, aBaseEcoWdsTran_16; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000141b  mov     ecx, eax; unsigned int
0x18000141d  mov     ebx, eax
0x18000141f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001424  test    eax, eax
0x180001426  jnz     loc_18000208C
0x18000142c  mov     r8d, [rsi]
0x18000142f  cmp     r8d, r14d
0x180001432  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180001439  cmovb   r8d, r14d
0x18000143d  shl     r8d, 0Ah
0x180001441  mov     [rsi], r8d
0x180001444  test    rax, rax
0x180001447  jz      short loc_180001459
0x180001449  mov     rdx, r12
0x18000144c  lea     rcx, aProfileSTransp_18; "Profile[%s] Transport: Socket Send Buff"...
0x180001453  call    cs:__guard_dispatch_icall_fptr
0x180001459  lea     rsi, [rdi+1Ch]
0x18000145d  mov     r8d, r14d; unsigned int
0x180001460  mov     r9, rsi; unsigned int *
0x180001463  lea     rdx, aTpsockrecvsize; "TpSockRecvSize"
0x18000146a  lea     rcx, [rbp+hKey]; this
0x18000146e  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180001473  mov     r9d, 0B4h; unsigned int
0x180001479  lea     r8, aBaseEcoWdsTran_16; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180001480  mov     ecx, eax; unsigned int
0x180001482  mov     ebx, eax
0x180001484  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001489  test    eax, eax
0x18000148b  jnz     loc_18000208C
0x180001491  mov     r8d, [rsi]
0x180001494  cmp     r8d, r14d
0x180001497  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000149e  cmovb   r8d, r14d
0x1800014a2  shl     r8d, 0Ah
0x1800014a6  mov     [rsi], r8d
0x1800014a9  test    rax, rax
0x1800014ac  jz      short loc_1800014BE
0x1800014ae  mov     rdx, r12
0x1800014b1  lea     rcx, aProfileSTransp_22; "Profile[%s] Transport: Socket Recv Buff"...
0x1800014b8  call    cs:__guard_dispatch_icall_fptr
0x1800014be  lea     r14, [rdi+20h]
0x1800014c2  mov     r8d, 20h ; ' '; unsigned int
0x1800014c8  mov     r9, r14; unsigned int *
0x1800014cb  lea     rdx, aTpmulticastttl; "TpMulticastTTL"
0x1800014d2  lea     rcx, [rbp+hKey]; this
0x1800014d6  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x1800014db  mov     r9d, 0C4h; unsigned int
0x1800014e1  lea     r8, aBaseEcoWdsTran_16; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800014e8  mov     ecx, eax; unsigned int
0x1800014ea  mov     ebx, eax
0x1800014ec  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800014f1  test    eax, eax
0x1800014f3  jnz     loc_18000208C
0x1800014f9  mov     r8d, [r14]
0x1800014fc  lea     esi, [rax+1]
0x1800014ff  cmp     r8d, esi
0x180001502  jnb     short loc_180001509
0x180001504  mov     r8d, esi
0x180001507  jmp     short loc_180001515
0x180001509  mov     eax, 0FFh
0x18000150e  cmp     r8d, eax
0x180001511  cmova   r8d, eax
0x180001515  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000151c  mov     [r14], r8d
0x18000151f  test    rax, rax
0x180001522  jz      short loc_180001534
0x180001524  mov     rdx, r12
0x180001527  lea     rcx, aProfileSTransp_17; "Profile[%s] Transport: Multicast TTL=%u"
0x18000152e  call    cs:__guard_dispatch_icall_fptr
0x180001534  lea     r14, [rdi+28h]
0x180001538  mov     r8d, 5; unsigned int
0x18000153e  mov     r9, r14; unsigned int *
0x180001541  lea     rdx, aTpopenwindowin; "TpOpenWindowInterval"
0x180001548  lea     rcx, [rbp+hKey]; this
0x18000154c  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180001551  mov     r9d, 0D3h; unsigned int
0x180001557  lea     r8, aBaseEcoWdsTran_16; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000155e  mov     ecx, eax; unsigned int
0x180001560  mov     ebx, eax
0x180001562  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001567  test    eax, eax
0x180001569  jnz     loc_18000208C
0x18000156f  cmp     [r14], esi
0x180001572  mov     r8d, esi
0x180001575  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000157c  cmova   r8d, [r14]
0x180001580  mov     [r14], r8d
0x180001583  test    rax, rax
0x180001586  jz      short loc_180001598
0x180001588  mov     rdx, r12
0x18000158b  lea     rcx, aProfileSTransp_0; "Profile[%s] Transport: Open Window Inte"...
0x180001592  call    cs:__guard_dispatch_icall_fptr
0x180001598  lea     r15, [rdi+2Ch]
0x18000159c  mov     r8d, 50h ; 'P'; unsigned int
0x1800015a2  mov     r9, r15; unsigned int *
0x1800015a5  lea     rdx, aTpopencacheint; "TpOpenCacheInterval"
0x1800015ac  lea     rcx, [rbp+hKey]; this
0x1800015b0  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x1800015b5  mov     r9d, 0E2h; unsigned int
0x1800015bb  lea     r8, aBaseEcoWdsTran_16; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800015c2  mov     ecx, eax; unsigned int
0x1800015c4  mov     ebx, eax
0x1800015c6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800015cb  test    eax, eax
0x1800015cd  jnz     loc_18000208C
0x1800015d3  lea     r14d, [rax+0Ah]
0x1800015d7  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
  ... truncated ...
```

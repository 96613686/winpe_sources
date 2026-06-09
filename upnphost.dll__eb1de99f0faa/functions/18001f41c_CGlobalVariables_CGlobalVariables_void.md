# CGlobalVariables::CGlobalVariables(void)

- ea: `0x18001f41c`
- end: `0x18001fb9c`
- name: `??0CGlobalVariables@@QEAA@XZ`
- size: `1920`
- prototype: `CGlobalVariables *__fastcall(CGlobalVariables *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e5c0`

## callees

- `0x180006168`
- `0x1800062a8`
- `0x18000db4c`
- `0x18001f41c`
- `0x18001fba4`
- `0x18001fc9c`
- `0x18001fd48`
- `0x18001fffc`
- `0x180020034`
- `0x1800200e0`
- `0x18002bb38`
- `0x18002be58`
- `0x180032d48`
- `0x180038a88`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x18003ae80`
- `0x1800430a8`
- `0x18004db8c`
- `0x18004df0c`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f659`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f67d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f659`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f67d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f75b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f92e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f75b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f92e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f7e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f911`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f7e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f911`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f5cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f5cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f4a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f5ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f7a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f4a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f5ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f7a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f712`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f7da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f712`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f7da`

## pseudocode

```c
CGlobalVariables *__fastcall CGlobalVariables::CGlobalVariables(CGlobalVariables *this)
{
  const unsigned __int16 *v2; // rbx
  __int64 v3; // r10
  WCHAR *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r8
  bool v7; // zf
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rax
  __int64 v11; // r9
  WCHAR *v12; // rax
  const wchar_t *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  HKEY v16; // rcx
  void *v17; // rcx
  STRSAFE_PCNZWCH v18; // rcx
  __int64 v19; // rdx
  DWORD v20; // ebx
  const unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // rdx
  BaseHttpListener *v23; // rax
  BaseHttpListener *v24; // rbx
  unsigned __int32 v25; // ecx
  unsigned __int32 v26; // eax
  __int64 v27; // r9
  BaseHttpListener *v28; // rbx
  int v29; // eax
  const char *v30; // rdx
  int v31; // r9d
  int inited; // eax
  HKEY v33; // rcx
  _OWORD *v34; // rbx
  __int64 v35; // rax
  unsigned int v36; // edx
  CVRoots *v37; // rcx
  char *v38; // rax
  unsigned int v39; // edx
  unsigned int v40; // eax
  __int64 v41; // rdx
  SVSThreadPool *v42; // rax
  SVSThreadPool *v43; // rax
  CVRoots *v44; // rcx
  void (__fastcall ***v45)(_QWORD, __int64); // rcx
  void *v46; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int samDesired; // [rsp+28h] [rbp-D8h]
  int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v54; // [rsp+60h] [rbp-A0h] BYREF
  int v55; // [rsp+68h] [rbp-98h]
  void *v56; // [rsp+70h] [rbp-90h]
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  int v58; // [rsp+80h] [rbp-80h]
  void *Block; // [rsp+88h] [rbp-78h]
  HKEY v60; // [rsp+90h] [rbp-70h] BYREF
  char v61[56]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(this, 0, 0x68u);
  v54 = 0;
  v55 = 0;
  v56 = 0;
  hKey = 0;
  v58 = 0;
  Block = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\MICROSOFT\\UPnP Device Host", 0, 0x20019u, &hKey);
  v2 = CReg::ValueSZ((CReg *)&hKey, L"RedirectionKey");
  if ( v2 )
  {
    memset_0(SubKey, 0, 0x20Au);
    v3 = 2147483646;
    v4 = SubKey;
    v5 = 2147483646;
    v6 = 261;
    do
    {
      if ( !v5 )
        break;
      if ( !*v2 )
        break;
      *v4++ = *v2++;
      --v5;
      --v6;
    }
    while ( v6 );
    v7 = v6 == 0;
    v8 = v4 - 1;
    v9 = 261;
    if ( !v7 )
      v8 = v4;
    v10 = SubKey;
    *v8 = 0;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    v11 = (261 - v9) & -(__int64)(v9 != 0);
    if ( v9 )
    {
      v12 = &SubKey[v11];
      v13 = L"\\HTTP Server";
      v14 = 261 - v11;
      if ( 261 != v11 )
      {
        do
        {
          if ( !v3 )
            break;
          if ( !*v13 )
            break;
          *v12++ = *v13++;
          --v3;
          --v14;
        }
        while ( v14 );
      }
      v15 = v12 - 1;
      if ( v14 )
        v15 = v12;
      *v15 = 0;
    }
    dwDisposition = 0;
    RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &v54, &dwDisposition);
  }
  else
  {
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\MICROSOFT\\UPnP Device Host\\HTTP Server", 0, 0x20019u, &v54);
  }
  v16 = v54;
  if ( v54 )
  {
    if ( !g_fFromExe )
    {
      if ( !CReg::ValueDW((CReg *)&v54, L"IsEnabled", 1u) )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        {
          goto LABEL_107;
        }
        v19 = 16;
        goto LABEL_106;
      }
      v16 = v54;
    }
    v20 = 0x2000;
    dwDisposition = 0x2000;
    if ( v16 )
    {
      cbData = 4;
      if ( RegQueryValueExW(v16, L"MaxHeaderSize", 0, 0, (LPBYTE)&dwDisposition, &cbData) )
        dwDisposition = 0x2000;
      else
        v20 = dwDisposition;
    }
    *((_DWORD *)this + 12) = v20;
    *((_DWORD *)this + 6) = InitExtensions((struct CISAPICache **)this + 8, (unsigned int *)this + 18);
    v21 = CReg::ValueSZ((CReg *)&v54, L"DefaultPage");
    *((_QWORD *)this + 4) = MassageMultiString(v21, v22);
    v23 = (BaseHttpListener *)malloc(0x150u);
    v24 = v23;
    if ( v23 )
    {
      BaseHttpListener::BaseHttpListener(v23);
      *(_QWORD *)v24 = &DevHostHttpListener::`vftable';
      *(_QWORD *)this = v24;
      v60 = 0;
      *(_DWORD *)Data = 102400;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\MICROSOFT\\UPnP Device Host\\Devices", 0, 1u, &v60) )
      {
        cbData = 4;
        RegQueryValueExW(v60, L"MaxHttpSize", 0, 0, Data, &cbData);
        RegCloseKey(v60);
      }
      v25 = *(_DWORD *)Data;
      if ( *(_DWORD *)Data <= 0x4000u )
      {
        v25 = 0x4000;
        *(_DWORD *)Data = 0x4000;
      }
      if ( v25 >= 0x1000000 )
      {
        v25 = 0x1000000;
        *(_DWORD *)Data = 0x1000000;
      }
      _InterlockedExchange((volatile __int32 *)(*(_QWORD *)this + 324LL), v25);
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids,
          *(unsigned int *)Data);
      }
      v26 = DwSoapSizeLimit();
      v27 = v26;
      if ( v26 > 0x7FFFFFFF )
        v26 = 0x7FFFFFFF;
      _InterlockedExchange((volatile __int32 *)(*(_QWORD *)this + 320LL), v26);
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids, v27);
      }
      v28 = *(BaseHttpListener **)this;
      v29 = IsProcessRunningInVailContainer();
      inited = BaseHttpListener::InitListening(
                 v28,
                 v30,
                 v29 != 0 ? 5706 : 2869,
                 v31,
                 phkResult,
                 samDesired,
                 lpSecurityAttributes);
      if ( inited < 0 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids,
            (unsigned int)"HTTPD: InitListening Failed",
            inited);
        if ( *(_QWORD *)this )
          (***(void (__fastcall ****)(_QWORD, __int64))this)(*(_QWORD *)this, 1);
        v33 = hKey;
        *(_QWORD *)this = 0;
        if ( v33 )
          RegCloseKey(v33);
        v17 = Block;
        if ( !Block )
          goto LABEL_30;
        goto LABEL_29;
      }
      v34 = malloc(0x38u);
      if ( v34 )
      {
        *v34 = 0;
        v34[1] = 0;
        v34[2] = 0;
        *((_QWORD *)v34 + 6) = 0;
        CVRoots::Init((CVRoots *)v34);
      }
      else
      {
        v34 = 0;
      }
      *((_QWORD *)this + 2) = v34;
      if ( v34 )
      {
        v35 = svsutil_Alloc(2048, g_pvAllocData);
        *((_QWORD *)this + 10) = v35;
        if ( v35 )
        {
          strcpy(v61, "Microsoft-Windows/10.0 UPnP/1.0 UPnP-Device-Host/1.0");
          v38 = (char *)svsutil_Alloc(54, g_pvAllocData);
          *((_QWORD *)this + 7) = v38;
          if ( v38 )
          {
            StringCchCopyA(v38, 0x36u, v61);
            v40 = CReg::ValueDW((CReg *)&v54, L"MaxConnections", 0xAu);
            v41 = g_pvAllocData;
            *((_DWORD *)this + 11) = v40;
            v42 = (SVSThreadPool *)svsutil_Alloc(112, v41);
            if ( v42 )
              v43 = SVSThreadPool::SVSThreadPool(v42, *((_DWORD *)this + 11) + 1);
            else
              v43 = 0;
            *((_QWORD *)this + 11) = v43;
            if ( v43 )
            {
              *((_DWORD *)this + 10) = 1;
LABEL_107:
              CReg::~CReg((CReg *)&hKey);
              CReg::~CReg((CReg *)&v54);
              return this;
            }
          }
          else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids,
              2147942414LL);
          }
          v44 = (CVRoots *)*((_QWORD *)this + 2);
          if ( v44 )
            CVRoots::`scalar deleting destructor'(v44, v39);
          v45 = *(void (__fastcall ****)(_QWORD, __int64))this;
          *((_QWORD *)this + 2) = 0;
          if ( v45 )
            (**v45)(v45, 1);
          v46 = (void *)*((_QWORD *)this + 10);
          *(_QWORD *)this = 0;
          if ( v46 )
            svsutil_Free(v46);
          *((_QWORD *)this + 10) = 0;
          goto LABEL_107;
        }
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids,
            2147942414LL);
        v37 = (CVRoots *)*((_QWORD *)this + 2);
        if ( v37 )
          CVRoots::`scalar deleting destructor'(v37, v36);
        *((_QWORD *)this + 2) = 0;
      }
      else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids, 2147942414LL);
      }
      if ( *(_QWORD *)this )
        (***(void (__fastcall ****)(_QWORD, __int64))this)(*(_QWORD *)this, 1);
      *(_QWORD *)this = 0;
      goto LABEL_107;
    }
    *(_QWORD *)this = 0;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
    {
      goto LABEL_107;
    }
    v19 = 17;
LABEL_106:
    WPP_SF_(*((_QWORD *)v18 + 2), v19, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids);
    goto LABEL_107;
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)((_DWORD)v54 + 15),
      WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids);
    v16 = v54;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v16 = v54;
  }
  if ( !Block )
    goto LABEL_31;
  v17 = Block;
LABEL_29:
  free(v17);
LABEL_30:
  v16 = v54;
LABEL_31:
  if ( v16 )
    RegCloseKey(v16);
  if ( v56 )
    free(v56);
  return this;
}

```

## disassembly

```asm
0x18001f41c  mov     [rsp-8+arg_8], rbx
0x18001f421  mov     [rsp-8+arg_10], rsi
0x18001f426  push    rbp
0x18001f427  push    rdi
0x18001f428  push    r12
0x18001f42a  push    r14
0x18001f42c  push    r15
0x18001f42e  lea     rbp, [rsp-1F0h]
0x18001f436  sub     rsp, 2F0h
0x18001f43d  mov     rax, cs:__security_cookie
0x18001f444  xor     rax, rsp
0x18001f447  mov     [rbp+210h+var_30], rax
0x18001f44e  xor     edx, edx; Val
0x18001f450  mov     rdi, rcx
0x18001f453  lea     r8d, [rdx+68h]; Size
0x18001f457  call    memset_0
0x18001f45c  xor     r14d, r14d
0x18001f45f  lea     rax, [rsp+310h+hKey]
0x18001f464  mov     esi, 20019h
0x18001f469  mov     [rsp+310h+phkResult], rax; phkResult
0x18001f46e  mov     r12, 0FFFFFFFF80000002h
0x18001f475  mov     [rsp+310h+var_2B0], r14
0x18001f47a  mov     r9d, esi; samDesired
0x18001f47d  mov     [rsp+310h+var_2A8], r14d
0x18001f482  mov     rcx, r12; hKey
0x18001f485  mov     [rsp+310h+var_2A0], r14
0x18001f48a  xor     r8d, r8d; ulOptions
0x18001f48d  mov     [rsp+310h+hKey], r14
0x18001f492  lea     rdx, aSoftwareMicros; "SOFTWARE\\MICROSOFT\\UPnP Device Host"
0x18001f499  mov     [rbp+210h+var_290], r14d
0x18001f49d  mov     [rbp+210h+Block], r14
0x18001f4a1  call    cs:__imp_RegOpenKeyExW
0x18001f4a7  lea     rdx, aRedirectionkey; "RedirectionKey"
0x18001f4ae  lea     rcx, [rsp+310h+hKey]; this
0x18001f4b3  call    ?ValueSZ@CReg@@QEAAPEBGPEBG@Z; CReg::ValueSZ(ushort const *)
0x18001f4b8  lea     r15d, [r14+1]
0x18001f4bc  mov     rbx, rax
0x18001f4bf  test    rax, rax
0x18001f4c2  jz      loc_18001F5D3
0x18001f4c8  xor     edx, edx; Val
0x18001f4ca  lea     rcx, [rbp+210h+SubKey]; void *
0x18001f4ce  mov     r8d, 20Ah; Size
0x18001f4d4  call    memset_0
0x18001f4d9  mov     r10d, 7FFFFFFEh
0x18001f4df  lea     rax, [rbp+210h+SubKey]
0x18001f4e3  mov     edx, 105h
0x18001f4e8  mov     ecx, r10d
0x18001f4eb  mov     r8d, edx
0x18001f4ee  test    rcx, rcx
0x18001f4f1  jz      short loc_18001F511
0x18001f4f3  movzx   r9d, word ptr [rbx]
0x18001f4f7  test    r9w, r9w
0x18001f4fb  jz      short loc_18001F511
0x18001f4fd  mov     [rax], r9w
0x18001f501  add     rbx, 2
0x18001f505  add     rax, 2
0x18001f509  sub     rcx, r15
0x18001f50c  sub     r8, r15
0x18001f50f  jnz     short loc_18001F4EE
0x18001f511  test    r8, r8
0x18001f514  lea     rcx, [rax-2]
0x18001f518  mov     r8, rdx
0x18001f51b  cmovnz  rcx, rax
0x18001f51f  lea     rax, [rbp+210h+SubKey]
0x18001f523  mov     [rcx], r14w
0x18001f527  cmp     [rax], r14w
0x18001f52b  jz      short loc_18001F536
0x18001f52d  add     rax, 2
0x18001f531  sub     r8, r15
0x18001f534  jnz     short loc_18001F527
0x18001f536  mov     rcx, rdx
0x18001f539  mov     rax, r8
0x18001f53c  sub     rcx, r8
0x18001f53f  neg     rax
0x18001f542  sbb     r9, r9
0x18001f545  and     r9, rcx
0x18001f548  test    r8, r8
0x18001f54b  jz      short loc_18001F593
0x18001f54d  lea     rax, [rbp+210h+SubKey]
0x18001f551  lea     rax, [rax+r9*2]
0x18001f555  lea     rcx, aHttpServer_0; "\\HTTP Server"
0x18001f55c  sub     rdx, r9
0x18001f55f  jz      short loc_18001F584
0x18001f561  test    r10, r10
0x18001f564  jz      short loc_18001F584
0x18001f566  movzx   r8d, word ptr [rcx]
0x18001f56a  test    r8w, r8w
0x18001f56e  jz      short loc_18001F584
0x18001f570  mov     [rax], r8w
0x18001f574  add     rcx, 2
0x18001f578  add     rax, 2
0x18001f57c  sub     r10, r15
0x18001f57f  sub     rdx, r15
0x18001f582  jnz     short loc_18001F561
0x18001f584  test    rdx, rdx
0x18001f587  lea     rcx, [rax-2]
0x18001f58b  cmovnz  rcx, rax
0x18001f58f  mov     [rcx], r14w
0x18001f593  lea     rax, [rsp+310h+dwDisposition]
0x18001f598  mov     [rsp+310h+dwDisposition], r14d
0x18001f59d  mov     [rsp+310h+lpdwDisposition], rax; lpdwDisposition
0x18001f5a2  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x18001f5a6  lea     rax, [rsp+310h+var_2B0]
0x18001f5ab  xor     r9d, r9d; lpClass
0x18001f5ae  mov     [rsp+310h+var_2D8], rax; phkResult
0x18001f5b3  xor     r8d, r8d; Reserved
0x18001f5b6  mov     [rsp+310h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001f5bb  mov     rcx, r12; hKey
0x18001f5be  mov     [rsp+310h+samDesired], 2001Fh; samDesired
0x18001f5c6  mov     dword ptr [rsp+310h+phkResult], r14d; dwOptions
0x18001f5cb  call    cs:__imp_RegCreateKeyExW
0x18001f5d1  jmp     short loc_18001F5F3
0x18001f5d3  lea     rax, [rsp+310h+var_2B0]
0x18001f5d8  mov     r9d, esi; samDesired
0x18001f5db  xor     r8d, r8d; ulOptions
0x18001f5de  mov     [rsp+310h+phkResult], rax; phkResult
0x18001f5e3  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\MICROSOFT\\UPnP Device Host\\"...
0x18001f5ea  mov     rcx, r12; hKey
0x18001f5ed  call    cs:__imp_RegOpenKeyExW
0x18001f5f3  mov     rcx, [rsp+310h+var_2B0]
0x18001f5f8  test    rcx, rcx
0x18001f5fb  jnz     loc_18001F688
0x18001f601  mov     rax, cs:WPP_GLOBAL_Control
0x18001f608  lea     rsi, WPP_GLOBAL_Control
0x18001f60f  cmp     rax, rsi
0x18001f612  jz      short loc_18001F635
0x18001f614  test    dword ptr [rax+1Ch], 1000h
0x18001f61b  jz      short loc_18001F635
0x18001f61d  lea     edx, [rcx+0Fh]
0x18001f620  mov     rcx, [rax+10h]
0x18001f624  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x18001f62b  call    WPP_SF_
0x18001f630  mov     rcx, [rsp+310h+var_2B0]
0x18001f635  mov     rax, [rsp+310h+hKey]
0x18001f63a  test    rax, rax
0x18001f63d  jz      short loc_18001F64D
0x18001f63f  mov     rcx, rax; hKey
0x18001f642  call    cs:__imp_RegCloseKey
0x18001f648  mov     rcx, [rsp+310h+var_2B0]
0x18001f64d  mov     rax, [rbp+210h+Block]
0x18001f651  test    rax, rax
0x18001f654  jz      short loc_18001F664
0x18001f656  mov     rcx, rax; Block
0x18001f659  call    cs:__imp_free
0x18001f65f  mov     rcx, [rsp+310h+var_2B0]; hKey
0x18001f664  test    rcx, rcx
0x18001f667  jz      short loc_18001F66F
0x18001f669  call    cs:__imp_RegCloseKey
0x18001f66f  mov     rcx, [rsp+310h+var_2A0]; Block
0x18001f674  test    rcx, rcx
0x18001f677  jz      loc_18001FB6E
0x18001f67d  call    cs:__imp_free
0x18001f683  jmp     loc_18001FB6E
0x18001f688  cmp     cs:?g_fFromExe@@3HA, r14d; int g_fFromExe
0x18001f68f  jnz     short loc_18001F6DA
0x18001f691  mov     r8d, r15d; unsigned int
0x18001f694  lea     rdx, aIsenabled; "IsEnabled"
0x18001f69b  lea     rcx, [rsp+310h+var_2B0]; this
0x18001f6a0  call    ?ValueDW@CReg@@QEAAKPEBGK@Z; CReg::ValueDW(ushort const *,ulong)
0x18001f6a5  test    eax, eax
0x18001f6a7  jnz     short loc_18001F6D5
0x18001f6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6b0  lea     rsi, WPP_GLOBAL_Control
0x18001f6b7  cmp     rcx, rsi
0x18001f6ba  jz      loc_18001FB5A
0x18001f6c0  test    dword ptr [rcx+1Ch], 1000h
0x18001f6c7  jz      loc_18001FB5A
0x18001f6cd  lea     edx, [rax+10h]
0x18001f6d0  jmp     loc_18001FB4A
0x18001f6d5  mov     rcx, [rsp+310h+var_2B0]; hKey
0x18001f6da  mov     ebx, 2000h
0x18001f6df  mov     esi, 4
0x18001f6e4  mov     [rsp+310h+dwDisposition], ebx
0x18001f6e8  test    rcx, rcx
0x18001f6eb  jz      short loc_18001F726
0x18001f6ed  lea     rax, [rsp+310h+cbData]
0x18001f6f2  mov     [rsp+310h+cbData], esi
0x18001f6f6  mov     qword ptr [rsp+310h+samDesired], rax; lpcbData
0x18001f6fb  lea     rdx, aMaxheadersize; "MaxHeaderSize"
0x18001f702  lea     rax, [rsp+310h+dwDisposition]
0x18001f707  xor     r9d, r9d; lpType
0x18001f70a  xor     r8d, r8d; lpReserved
0x18001f70d  mov     [rsp+310h+phkResult], rax; lpData
0x18001f712  call    cs:__imp_RegQueryValueExW
0x18001f718  test    eax, eax
0x18001f71a  jz      short loc_18001F722
0x18001f71c  mov     [rsp+310h+dwDisposition], ebx
0x18001f720  jmp     short loc_18001F726
0x18001f722  mov     ebx, [rsp+310h+dwDisposition]
0x18001f726  lea     rdx, [rdi+48h]; unsigned int *
0x18001f72a  mov     [rdi+30h], ebx
0x18001f72d  lea     rcx, [rdi+40h]; struct CISAPICache **
0x18001f731  call    ?InitExtensions@@YAHPEAPEAVCISAPICache@@PEAK@Z; InitExtensions(CISAPICache * *,ulong *)
0x18001f736  lea     rdx, aDefaultpage; "DefaultPage"
0x18001f73d  mov     [rdi+18h], eax
0x18001f740  lea     rcx, [rsp+310h+var_2B0]; this
0x18001f745  call    ?ValueSZ@CReg@@QEAAPEBGPEBG@Z; CReg::ValueSZ(ushort const *)
0x18001f74a  mov     rcx, rax; unsigned __int16 *
0x18001f74d  call    ?MassageMultiString@@YAPEAGPEBG0@Z; MassageMultiString(ushort const *,ushort const *)
0x18001f752  mov     ecx, 150h; Size
0x18001f757  mov     [rdi+20h], rax
0x18001f75b  call    cs:__imp_malloc
0x18001f761  mov     rbx, rax
0x18001f764  test    rax, rax
0x18001f767  jz      loc_18001FB26
0x18001f76d  mov     rcx, rax; this
0x18001f770  call    ??0BaseHttpListener@@QEAA@XZ; BaseHttpListener::BaseHttpListener(void)
0x18001f775  lea     rax, ??_7DevHostHttpListener@@6B@; const DevHostHttpListener::`vftable'
0x18001f77c  mov     r9d, r15d; samDesired
0x18001f77f  mov     [rbx], rax
0x18001f782  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\MICROSOFT\\UPnP Device Host\\"...
0x18001f789  lea     rax, [rbp+210h+var_280]
0x18001f78d  mov     [rdi], rbx
0x18001f790  xor     r8d, r8d; ulOptions
0x18001f793  mov     [rsp+310h+phkResult], rax; phkResult
0x18001f798  mov     rcx, r12; hKey
0x18001f79b  mov     [rbp+210h+var_280], r14
0x18001f79f  mov     dword ptr [rsp+310h+Data], 19000h
0x18001f7a7  call    cs:__imp_RegOpenKeyExW
0x18001f7ad  test    eax, eax
0x18001f7af  jnz     short loc_18001F7EA
0x18001f7b1  mov     rcx, [rbp+210h+var_280]; hKey
0x18001f7b5  lea     rax, [rsp+310h+cbData]
0x18001f7ba  mov     qword ptr [rsp+310h+samDesired], rax; int
0x18001f7bf  lea     rdx, aMaxhttpsize; "MaxHttpSize"
0x18001f7c6  lea     rax, [rsp+310h+Data]
0x18001f7cb  mov     [rsp+310h+cbData], esi
0x18001f7cf  xor     r9d, r9d; lpType
0x18001f7d2  mov     [rsp+310h+phkResult], rax; int
0x18001f7d7  xor     r8d, r8d; lpReserved
0x18001f7da  call    cs:__imp_RegQueryValueExW
0x18001f7e0  mov     rcx, [rbp+210h+var_280]; hKey
0x18001f7e4  call    cs:__imp_RegCloseKey
0x18001f7ea  mov     ecx, dword ptr [rsp+310h+Data]
0x18001f7ee  mov     eax, 4000h
0x18001f7f3  cmp     ecx, eax
0x18001f7f5  ja      short loc_18001F7FD
0x18001f7f7  mov     ecx, eax
0x18001f7f9  mov     dword ptr [rsp+310h+Data], eax
0x18001f7fd  mov     eax, 1000000h
0x18001f802  cmp     ecx, eax
0x18001f804  jb      short loc_18001F80C
0x18001f806  mov     ecx, eax
0x18001f808  mov     dword ptr [rsp+310h+Data], eax
0x18001f80c  mov     rax, [rdi]
0x18001f80f  mov     ebx, 7FFFFFFFh
0x18001f814  cmp     ecx, ebx
0x18001f816  cmova   ecx, ebx
0x18001f819  xchg    ecx, [rax+144h]
0x18001f81f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f826  lea     rsi, WPP_GLOBAL_Control
0x18001f82d  cmp     rcx, rsi
0x18001f830  jz      short loc_18001F855
0x18001f832  test    dword ptr [rcx+1Ch], 1000h
0x18001f839  jz      short loc_18001F855
0x18001f83b  mov     r9d, dword ptr [rsp+310h+Data]
0x18001f840  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x18001f847  mov     rcx, [rcx+10h]
0x18001f84b  mov     edx, 12h
0x18001f850  call    WPP_SF_d
0x18001f855  call    ?DwSoapSizeLimit@@YAKXZ; DwSoapSizeLimit(void)
0x18001f85a  mov     rcx, [rdi]
0x18001f85d  cmp     eax, ebx
0x18001f85f  mov     r9d, eax
0x18001f862  cmova   eax, ebx
0x18001f865  xchg    eax, [rcx+140h]
0x18001f86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f872  cmp     rcx, rsi
0x18001f875  jz      short loc_18001F895
0x18001f877  test    dword ptr [rcx+1Ch], 1000h
0x18001f87e  jz      short loc_18001F895
0x18001f880  mov     rcx, [rcx+10h]
0x18001f884  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x18001f88b  mov     edx, 13h
0x18001f890  call    WPP_SF_d
0x18001f895  mov     rbx, [rdi]
0x18001f898  call    ?IsProcessRunningInVailContainer@@YAHXZ; IsProcessRunningInVailContainer(void)
0x18001f89d  neg     eax
0x18001f89f  mov     rcx, rbx; this
0x18001f8a2  sbb     r8d, r8d
0x18001f8a5  and     r8d, 0B15h
0x18001f8ac  add     r8d, 0B35h; unsigned int
0x18001f8b3  call    ?InitListening@BaseHttpListener@@QEAAJPEBDKHHHH@Z; BaseHttpListener::InitListening(char const *,ulong,int,int,int,int)
0x18001f8b8  test    eax, eax
0x18001f8ba  jns     short loc_18001F929
0x18001f8bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8c3  cmp     rcx, rsi
0x18001f8c6  jz      short loc_18001F8EE
0x18001f8c8  test    [rcx+1Ch], r15b
0x18001f8cc  jz      short loc_18001F8EE
0x18001f8ce  mov     rcx, [rcx+10h]
0x18001f8d2  lea     r9, aHttpdInitliste; "HTTPD: InitListening Failed"
0x18001f8d9  mov     edx, 14h
0x18001f8de  mov     dword ptr [rsp+310h+phkResult], eax
0x18001f8e2  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x18001f8e9  call    WPP_SF_sd
0x18001f8ee  mov     rcx, [rdi]
0x18001f8f1  test    rcx, rcx
0x18001f8f4  jz      short loc_18001F904
0x18001f8f6  mov     rax, [rcx]
  ... truncated ...
```

# CGlobalVariables::CGlobalVariables(void)

- ea: `0x180014580`
- end: `0x180014d55`
- name: `??0CGlobalVariables@@QEAA@XZ`
- size: `2005`
- prototype: `CGlobalVariables *__fastcall(CGlobalVariables *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001363c`

## callees

- `0x180014580`
- `0x180014d5c`
- `0x180014e60`
- `0x180014f18`
- `0x1800151fc`
- `0x180015238`
- `0x1800152ec`
- `0x180018a4c`
- `0x18001aea8`
- `0x1800200f4`
- `0x18002d240`
- `0x18002d588`
- `0x180034bec`
- `0x18003af3c`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x18003d4b0`
- `0x180045b14`
- `0x180051018`
- `0x1800513cc`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800147d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014805`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800147d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014805`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800148ef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180014ae0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800148ef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180014ae0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800147b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800147eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001498a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014abd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800147b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800147eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001498a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014abd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014735`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014735`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014605`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001475d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014941`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014605`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001475d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014941`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800148a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001497a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800148a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001497a`

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
0x180014580  mov     [rsp-8+arg_8], rbx
0x180014585  mov     [rsp-8+arg_10], rsi
0x18001458a  push    rbp
0x18001458b  push    rdi
0x18001458c  push    r12
0x18001458e  push    r14
0x180014590  push    r15
0x180014592  lea     rbp, [rsp-1F0h]
0x18001459a  sub     rsp, 2F0h
0x1800145a1  mov     rax, cs:__security_cookie
0x1800145a8  xor     rax, rsp
0x1800145ab  mov     [rbp+210h+var_30], rax
0x1800145b2  xor     edx, edx; Val
0x1800145b4  mov     rdi, rcx
0x1800145b7  lea     r8d, [rdx+68h]; Size
0x1800145bb  call    memset_0
0x1800145c0  xor     r14d, r14d
0x1800145c3  lea     rax, [rsp+310h+hKey]
0x1800145c8  mov     esi, 20019h
0x1800145cd  mov     [rsp+310h+phkResult], rax; phkResult
0x1800145d2  mov     r12, 0FFFFFFFF80000002h
0x1800145d9  mov     [rsp+310h+var_2B0], r14
0x1800145de  mov     r9d, esi; samDesired
0x1800145e1  mov     [rsp+310h+var_2A8], r14d
0x1800145e6  mov     rcx, r12; hKey
0x1800145e9  mov     [rsp+310h+var_2A0], r14
0x1800145ee  xor     r8d, r8d; ulOptions
0x1800145f1  mov     [rsp+310h+hKey], r14
0x1800145f6  lea     rdx, aSoftwareMicros; "SOFTWARE\\MICROSOFT\\UPnP Device Host"
0x1800145fd  mov     [rbp+210h+var_290], r14d
0x180014601  mov     [rbp+210h+Block], r14
0x180014605  call    cs:__imp_RegOpenKeyExW
0x18001460c  nop     dword ptr [rax+rax+00h]
0x180014611  lea     rdx, aRedirectionkey; "RedirectionKey"
0x180014618  lea     rcx, [rsp+310h+hKey]; this
0x18001461d  call    ?ValueSZ@CReg@@QEAAPEBGPEBG@Z; CReg::ValueSZ(ushort const *)
0x180014622  lea     r15d, [r14+1]
0x180014626  mov     rbx, rax
0x180014629  test    rax, rax
0x18001462c  jz      loc_180014743
0x180014632  xor     edx, edx; Val
0x180014634  lea     rcx, [rbp+210h+SubKey]; void *
0x180014638  mov     r8d, 20Ah; Size
0x18001463e  call    memset_0
0x180014643  mov     r10d, 7FFFFFFEh
0x180014649  lea     rax, [rbp+210h+SubKey]
0x18001464d  mov     edx, 105h
0x180014652  mov     ecx, r10d
0x180014655  mov     r8d, edx
0x180014658  test    rcx, rcx
0x18001465b  jz      short loc_18001467B
0x18001465d  movzx   r9d, word ptr [rbx]
0x180014661  test    r9w, r9w
0x180014665  jz      short loc_18001467B
0x180014667  mov     [rax], r9w
0x18001466b  add     rbx, 2
0x18001466f  add     rax, 2
0x180014673  sub     rcx, r15
0x180014676  sub     r8, r15
0x180014679  jnz     short loc_180014658
0x18001467b  test    r8, r8
0x18001467e  lea     rcx, [rax-2]
0x180014682  mov     r8, rdx
0x180014685  cmovnz  rcx, rax
0x180014689  lea     rax, [rbp+210h+SubKey]
0x18001468d  mov     [rcx], r14w
0x180014691  cmp     [rax], r14w
0x180014695  jz      short loc_1800146A0
0x180014697  add     rax, 2
0x18001469b  sub     r8, r15
0x18001469e  jnz     short loc_180014691
0x1800146a0  mov     rcx, rdx
0x1800146a3  mov     rax, r8
0x1800146a6  sub     rcx, r8
0x1800146a9  neg     rax
0x1800146ac  sbb     r9, r9
0x1800146af  and     r9, rcx
0x1800146b2  test    r8, r8
0x1800146b5  jz      short loc_1800146FD
0x1800146b7  lea     rax, [rbp+210h+SubKey]
0x1800146bb  lea     rax, [rax+r9*2]
0x1800146bf  lea     rcx, aHttpServer_0; "\\HTTP Server"
0x1800146c6  sub     rdx, r9
0x1800146c9  jz      short loc_1800146EE
0x1800146cb  test    r10, r10
0x1800146ce  jz      short loc_1800146EE
0x1800146d0  movzx   r8d, word ptr [rcx]
0x1800146d4  test    r8w, r8w
0x1800146d8  jz      short loc_1800146EE
0x1800146da  mov     [rax], r8w
0x1800146de  add     rcx, 2
0x1800146e2  add     rax, 2
0x1800146e6  sub     r10, r15
0x1800146e9  sub     rdx, r15
0x1800146ec  jnz     short loc_1800146CB
0x1800146ee  test    rdx, rdx
0x1800146f1  lea     rcx, [rax-2]
0x1800146f5  cmovnz  rcx, rax
0x1800146f9  mov     [rcx], r14w
0x1800146fd  lea     rax, [rsp+310h+dwDisposition]
0x180014702  mov     [rsp+310h+dwDisposition], r14d
0x180014707  mov     [rsp+310h+lpdwDisposition], rax; lpdwDisposition
0x18001470c  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x180014710  lea     rax, [rsp+310h+var_2B0]
0x180014715  xor     r9d, r9d; lpClass
0x180014718  mov     [rsp+310h+var_2D8], rax; phkResult
0x18001471d  xor     r8d, r8d; Reserved
0x180014720  mov     [rsp+310h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180014725  mov     rcx, r12; hKey
0x180014728  mov     [rsp+310h+samDesired], 2001Fh; samDesired
0x180014730  mov     dword ptr [rsp+310h+phkResult], r14d; dwOptions
0x180014735  call    cs:__imp_RegCreateKeyExW
0x18001473c  nop     dword ptr [rax+rax+00h]
0x180014741  jmp     short loc_180014769
0x180014743  lea     rax, [rsp+310h+var_2B0]
0x180014748  mov     r9d, esi; samDesired
0x18001474b  xor     r8d, r8d; ulOptions
0x18001474e  mov     [rsp+310h+phkResult], rax; phkResult
0x180014753  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\MICROSOFT\\UPnP Device Host\\"...
0x18001475a  mov     rcx, r12; hKey
0x18001475d  call    cs:__imp_RegOpenKeyExW
0x180014764  nop     dword ptr [rax+rax+00h]
0x180014769  mov     rcx, [rsp+310h+var_2B0]
0x18001476e  test    rcx, rcx
0x180014771  jnz     loc_180014816
0x180014777  mov     rax, cs:WPP_GLOBAL_Control
0x18001477e  lea     rsi, WPP_GLOBAL_Control
0x180014785  cmp     rax, rsi
0x180014788  jz      short loc_1800147AB
0x18001478a  test    dword ptr [rax+1Ch], 1000h
0x180014791  jz      short loc_1800147AB
0x180014793  lea     edx, [rcx+0Fh]
0x180014796  mov     rcx, [rax+10h]
0x18001479a  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x1800147a1  call    WPP_SF_
0x1800147a6  mov     rcx, [rsp+310h+var_2B0]
0x1800147ab  mov     rax, [rsp+310h+hKey]
0x1800147b0  test    rax, rax
0x1800147b3  jz      short loc_1800147C9
0x1800147b5  mov     rcx, rax; hKey
0x1800147b8  call    cs:__imp_RegCloseKey
0x1800147bf  nop     dword ptr [rax+rax+00h]
0x1800147c4  mov     rcx, [rsp+310h+var_2B0]
0x1800147c9  mov     rax, [rbp+210h+Block]
0x1800147cd  test    rax, rax
0x1800147d0  jz      short loc_1800147E6
0x1800147d2  mov     rcx, rax; Block
0x1800147d5  call    cs:__imp_free
0x1800147dc  nop     dword ptr [rax+rax+00h]
0x1800147e1  mov     rcx, [rsp+310h+var_2B0]; hKey
0x1800147e6  test    rcx, rcx
0x1800147e9  jz      short loc_1800147F7
0x1800147eb  call    cs:__imp_RegCloseKey
0x1800147f2  nop     dword ptr [rax+rax+00h]
0x1800147f7  mov     rcx, [rsp+310h+var_2A0]; Block
0x1800147fc  test    rcx, rcx
0x1800147ff  jz      loc_180014D26
0x180014805  call    cs:__imp_free
0x18001480c  nop     dword ptr [rax+rax+00h]
0x180014811  jmp     loc_180014D26
0x180014816  cmp     cs:?g_fFromExe@@3HA, r14d; int g_fFromExe
0x18001481d  jnz     short loc_180014868
0x18001481f  mov     r8d, r15d; unsigned int
0x180014822  lea     rdx, aIsenabled; "IsEnabled"
0x180014829  lea     rcx, [rsp+310h+var_2B0]; this
0x18001482e  call    ?ValueDW@CReg@@QEAAKPEBGK@Z; CReg::ValueDW(ushort const *,ulong)
0x180014833  test    eax, eax
0x180014835  jnz     short loc_180014863
0x180014837  mov     rcx, cs:WPP_GLOBAL_Control
0x18001483e  lea     rsi, WPP_GLOBAL_Control
0x180014845  cmp     rcx, rsi
0x180014848  jz      loc_180014D12
0x18001484e  test    dword ptr [rcx+1Ch], 1000h
0x180014855  jz      loc_180014D12
0x18001485b  lea     edx, [rax+10h]
0x18001485e  jmp     loc_180014D02
0x180014863  mov     rcx, [rsp+310h+var_2B0]; hKey
0x180014868  mov     ebx, 2000h
0x18001486d  mov     esi, 4
0x180014872  mov     [rsp+310h+dwDisposition], ebx
0x180014876  test    rcx, rcx
0x180014879  jz      short loc_1800148BA
0x18001487b  lea     rax, [rsp+310h+cbData]
0x180014880  mov     [rsp+310h+cbData], esi
0x180014884  mov     qword ptr [rsp+310h+samDesired], rax; lpcbData
0x180014889  lea     rdx, aMaxheadersize; "MaxHeaderSize"
0x180014890  lea     rax, [rsp+310h+dwDisposition]
0x180014895  xor     r9d, r9d; lpType
0x180014898  xor     r8d, r8d; lpReserved
0x18001489b  mov     [rsp+310h+phkResult], rax; lpData
0x1800148a0  call    cs:__imp_RegQueryValueExW
0x1800148a7  nop     dword ptr [rax+rax+00h]
0x1800148ac  test    eax, eax
0x1800148ae  jz      short loc_1800148B6
0x1800148b0  mov     [rsp+310h+dwDisposition], ebx
0x1800148b4  jmp     short loc_1800148BA
0x1800148b6  mov     ebx, [rsp+310h+dwDisposition]
0x1800148ba  lea     rdx, [rdi+48h]; unsigned int *
0x1800148be  mov     [rdi+30h], ebx
0x1800148c1  lea     rcx, [rdi+40h]; struct CISAPICache **
0x1800148c5  call    ?InitExtensions@@YAHPEAPEAVCISAPICache@@PEAK@Z; InitExtensions(CISAPICache * *,ulong *)
0x1800148ca  lea     rdx, aDefaultpage; "DefaultPage"
0x1800148d1  mov     [rdi+18h], eax
0x1800148d4  lea     rcx, [rsp+310h+var_2B0]; this
0x1800148d9  call    ?ValueSZ@CReg@@QEAAPEBGPEBG@Z; CReg::ValueSZ(ushort const *)
0x1800148de  mov     rcx, rax; unsigned __int16 *
0x1800148e1  call    ?MassageMultiString@@YAPEAGPEBG0@Z; MassageMultiString(ushort const *,ushort const *)
0x1800148e6  mov     ecx, 150h; Size
0x1800148eb  mov     [rdi+20h], rax
0x1800148ef  call    cs:__imp_malloc
0x1800148f6  nop     dword ptr [rax+rax+00h]
0x1800148fb  mov     rbx, rax
0x1800148fe  test    rax, rax
0x180014901  jz      loc_180014CDE
0x180014907  mov     rcx, rax; this
0x18001490a  call    ??0BaseHttpListener@@QEAA@XZ; BaseHttpListener::BaseHttpListener(void)
0x18001490f  lea     rax, ??_7DevHostHttpListener@@6B@; const DevHostHttpListener::`vftable'
0x180014916  mov     r9d, r15d; samDesired
0x180014919  mov     [rbx], rax
0x18001491c  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\MICROSOFT\\UPnP Device Host\\"...
0x180014923  lea     rax, [rbp+210h+var_280]
0x180014927  mov     [rdi], rbx
0x18001492a  xor     r8d, r8d; ulOptions
0x18001492d  mov     [rsp+310h+phkResult], rax; phkResult
0x180014932  mov     rcx, r12; hKey
0x180014935  mov     [rbp+210h+var_280], r14
0x180014939  mov     dword ptr [rsp+310h+Data], 19000h
0x180014941  call    cs:__imp_RegOpenKeyExW
0x180014948  nop     dword ptr [rax+rax+00h]
0x18001494d  test    eax, eax
0x18001494f  jnz     short loc_180014996
0x180014951  mov     rcx, [rbp+210h+var_280]; hKey
0x180014955  lea     rax, [rsp+310h+cbData]
0x18001495a  mov     qword ptr [rsp+310h+samDesired], rax; int
0x18001495f  lea     rdx, aMaxhttpsize; "MaxHttpSize"
0x180014966  lea     rax, [rsp+310h+Data]
0x18001496b  mov     [rsp+310h+cbData], esi
0x18001496f  xor     r9d, r9d; lpType
0x180014972  mov     [rsp+310h+phkResult], rax; int
0x180014977  xor     r8d, r8d; lpReserved
0x18001497a  call    cs:__imp_RegQueryValueExW
0x180014981  nop     dword ptr [rax+rax+00h]
0x180014986  mov     rcx, [rbp+210h+var_280]; hKey
0x18001498a  call    cs:__imp_RegCloseKey
0x180014991  nop     dword ptr [rax+rax+00h]
0x180014996  mov     ecx, dword ptr [rsp+310h+Data]
0x18001499a  mov     eax, 4000h
0x18001499f  cmp     ecx, eax
0x1800149a1  ja      short loc_1800149A9
0x1800149a3  mov     ecx, eax
0x1800149a5  mov     dword ptr [rsp+310h+Data], eax
0x1800149a9  mov     eax, 1000000h
0x1800149ae  cmp     ecx, eax
0x1800149b0  jb      short loc_1800149B8
0x1800149b2  mov     ecx, eax
0x1800149b4  mov     dword ptr [rsp+310h+Data], eax
0x1800149b8  mov     rax, [rdi]
0x1800149bb  mov     ebx, 7FFFFFFFh
0x1800149c0  cmp     ecx, ebx
0x1800149c2  cmova   ecx, ebx
0x1800149c5  xchg    ecx, [rax+144h]
0x1800149cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149d2  lea     rsi, WPP_GLOBAL_Control
0x1800149d9  cmp     rcx, rsi
0x1800149dc  jz      short loc_180014A01
0x1800149de  test    dword ptr [rcx+1Ch], 1000h
0x1800149e5  jz      short loc_180014A01
0x1800149e7  mov     r9d, dword ptr [rsp+310h+Data]
0x1800149ec  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x1800149f3  mov     rcx, [rcx+10h]
0x1800149f7  mov     edx, 12h
0x1800149fc  call    WPP_SF_d
0x180014a01  call    ?DwSoapSizeLimit@@YAKXZ; DwSoapSizeLimit(void)
0x180014a06  mov     rcx, [rdi]
0x180014a09  cmp     eax, ebx
0x180014a0b  mov     r9d, eax
0x180014a0e  cmova   eax, ebx
0x180014a11  xchg    eax, [rcx+140h]
0x180014a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a1e  cmp     rcx, rsi
0x180014a21  jz      short loc_180014A41
0x180014a23  test    dword ptr [rcx+1Ch], 1000h
0x180014a2a  jz      short loc_180014A41
0x180014a2c  mov     rcx, [rcx+10h]
0x180014a30  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x180014a37  mov     edx, 13h
0x180014a3c  call    WPP_SF_d
0x180014a41  mov     rbx, [rdi]
0x180014a44  call    ?IsProcessRunningInVailContainer@@YAHXZ; IsProcessRunningInVailContainer(void)
0x180014a49  neg     eax
0x180014a4b  mov     rcx, rbx; this
0x180014a4e  sbb     r8d, r8d
0x180014a51  and     r8d, 0B15h
0x180014a58  add     r8d, 0B35h; unsigned int
0x180014a5f  call    ?InitListening@BaseHttpListener@@QEAAJPEBDKHHHH@Z; BaseHttpListener::InitListening(char const *,ulong,int,int,int,int)
0x180014a64  test    eax, eax
0x180014a66  jns     short loc_180014ADB
0x180014a68  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a6f  cmp     rcx, rsi
0x180014a72  jz      short loc_180014A9A
  ... truncated ...
```

# CRegBlob::Init(HKEY__ *,HKEY__ *,ulong,ushort const *,char const *,_FILETIME *,int *)

- ea: `0x180021320`
- end: `0x1800219e9`
- name: `?Init@CRegBlob@@QEAAKPEAUHKEY__@@0KPEBGPEBDPEAU_FILETIME@@PEAH@Z`
- size: `1737`
- prototype: `unsigned int __usercall@<eax>(PHKEY phkResult@<rcx>, HKEY hKey@<rdx>, HKEY@<r8>, unsigned int@<r9d>, const unsigned __int16 *, LPCSTR lpValueName, struct _FILETIME *, int *)`
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fd20`
- `0x18004b358`
- `0x18004b7a8`
- `0x18004c2c0`
- `0x1800aaa7c`

## callees

- `0x180021320`
- `0x180041eb0`
- `0x18004ae54`
- `0x180058f80`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800d187c`
- `0x1800d194c`
- `0x1800da03c`
- `0x1800db6b0`
- `0x1800dc4cc`
- `0x1800dc68c`
- `0x1800dce80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002150b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021998`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002150b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021998`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002176f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002176f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800214e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021540`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800214e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021540`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800215d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021944`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800215d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021944`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x18002163d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x18002163d`
- `ntdll!RtlNtStatusToDosError` at `0x1800218df`
- `ntdll!RtlNtStatusToDosError` at `0x1800218df`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800216d4`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800216d4`

## pseudocode

```c
__int64 __fastcall CRegBlob::Init(
        _DWORD *phkResult,
        HKEY hKey,
        __int64 a3,
        int a4,
        const unsigned __int16 *a5,
        LPCSTR lpValueName,
        struct _FILETIME *a7,
        int *a8)
{
  const CHAR *v10; // rsi
  char v12; // di
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  __int64 v16; // rcx
  const WCHAR *v17; // rbx
  __int64 v18; // rdx
  char *v19; // r8
  char *v20; // rcx
  int v21; // edi
  ULONG Value; // ebx
  int v23; // eax
  struct _FILETIME *v24; // rdi
  DWORD *v25; // rdi
  BYTE *v26; // rax
  LSTATUS v27; // eax
  int ThreadIntegrityLevel; // eax
  char v30; // di
  int v31; // r13d
  LSTATUS v32; // eax
  int v33; // edx
  int v34; // ecx
  int v35; // r8d
  int PersistedStateLocation; // eax
  int v37; // edx
  int v38; // ecx
  int v39; // r8d
  int v40; // esi
  WCHAR *v41; // r8
  unsigned __int64 v42; // rdx
  __int64 v43; // rcx
  const WCHAR *v44; // rax
  WCHAR *v45; // rcx
  LSTATUS Key; // eax
  int v47; // edx
  int v48; // ecx
  int v49; // r8d
  HANDLE v50; // rcx
  HKEY v51; // rax
  WCHAR *lpData; // [rsp+20h] [rbp-E0h]
  unsigned int v54; // [rsp+74h] [rbp-8Ch] BYREF
  LPCSTR v55; // [rsp+78h] [rbp-88h]
  struct _FILETIME *v56; // [rsp+80h] [rbp-80h]
  unsigned int v57; // [rsp+88h] [rbp-78h]
  DWORD cbData; // [rsp+8Ch] [rbp-74h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[60]; // [rsp+A0h] [rbp-60h] BYREF
  char v61; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v62[406]; // [rsp+11Ah] [rbp+1Ah] BYREF

  v10 = lpValueName;
  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internetttings\\");
  v12 = a4;
  v56 = a7;
  v55 = lpValueName;
  cbData = 0;
  ftLastWriteTime = 0;
  v54 = 4096;
  memset_0(v62, 0, 0x18Eu);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qllqqDSsqq(v14, v13, v15, (_DWORD)phkResult, phkResult[2], phkResult[11], (__int64)hKey, a3, v12);
  if ( a8 )
    *a8 = 0;
  if ( hKey == HKEY_LOCAL_MACHINE )
  {
    v57 = 0;
    if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
      WPP_SF_SSSqd(
        v14,
        v13,
        v15,
        (unsigned int)L"InternetSettings",
        (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
        (__int64)L"Connections",
        (__int64)SubKey);
    lpData = SubKey;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"InternetSettings",
                               0,
                               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
                               0);
    v40 = PersistedStateLocation;
    if ( PersistedStateLocation < 0 )
    {
      if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_SSSd(
          v38,
          v37,
          v39,
          (unsigned int)L"InternetSettings",
          (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
          (__int64)L"Connections",
          PersistedStateLocation);
      v21 = HRESULT_FROM_NTSTATUS(v40);
      goto LABEL_58;
    }
    v41 = &SubKey[(unsigned __int64)v57 >> 1];
    v42 = (unsigned __int64)(520 - v57) >> 1;
    *(v41 - 1) = 92;
    if ( v42 )
    {
      v43 = 2147483646;
      v44 = L"Connections";
      do
      {
        if ( !v43 )
          break;
        if ( !*v44 )
          break;
        *v41++ = *v44++;
        --v43;
        --v42;
      }
      while ( v42 );
      v45 = v41 - 1;
      v21 = -2147024774;
      if ( v42 )
      {
        v45 = v41;
        v21 = 0;
      }
      *v45 = 0;
      if ( v21 >= 0 )
      {
        if ( (BYTE3(xmmword_180107A60) & 0x20) == 0 )
        {
LABEL_53:
          v10 = v55;
          goto LABEL_13;
        }
        WPP_SF_SSSS(
          1053,
          13,
          (unsigned int)WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids,
          (unsigned int)L"InternetSettings",
          (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
          (__int64)L"Connections",
          (__int64)SubKey);
LABEL_58:
        if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
          WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v21, lpData);
        goto LABEL_53;
      }
    }
    else
    {
      v21 = -2147024809;
    }
    if ( (BYTE3(xmmword_180107A60) & 0x20) == 0 )
      goto LABEL_53;
    WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v21, SubKey);
    goto LABEL_58;
  }
  v16 = 2147483646;
  v17 = L"Connections";
  v18 = 200;
  v19 = &v61;
  do
  {
    if ( !v16 )
      break;
    if ( !*v17 )
      break;
    *(_WORD *)v19 = *v17++;
    v19 += 2;
    --v16;
    --v18;
  }
  while ( v18 );
  v20 = v19 - 2;
  v21 = -2147024774;
  if ( v18 )
  {
    v20 = v19;
    v21 = 0;
  }
  *(_WORD *)v20 = 0;
LABEL_13:
  if ( v21 < 0 )
  {
    if ( (v21 & 0x1FFF0000) == 0xC0000 )
    {
      Value = (unsigned __int16)v21;
    }
    else if ( (v21 & 0x1FFF0000) == 0x70000 )
    {
      Value = (unsigned __int16)v21;
      if ( !(_WORD)v21 )
        Value = 317;
    }
    else if ( (v21 & 0x10000000) != 0 )
    {
      Value = RtlNtStatusToDosError(v21 & 0xEFFFFFFF);
      if ( Value )
      {
        if ( Value == 317 )
          Value = v21;
      }
      else
      {
        Value = v21;
      }
    }
    else
    {
      Value = v21;
    }
    goto LABEL_29;
  }
  if ( phkResult[2] )
  {
    *((_QWORD *)phkResult + 4) = v10;
    Key = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, a4 | 2, 0, (PHKEY)phkResult, 0);
    Value = Key;
    if ( Key )
    {
      if ( (xmmword_180107A60 & 0x20) == 0 )
        return Value;
      WPP_SF_SqDD(v48, v47, v49, (unsigned int)SubKey, (__int64)hKey, a4 | 2, Key);
    }
    else
    {
      v50 = g_hWxProcessHeap;
      phkResult[10] = 1;
      phkResult[5] = 1024;
      v51 = (HKEY)HeapAlloc(v50, 0, 0x400u);
      *((_QWORD *)phkResult + 3) = v51;
      if ( !v51 )
        Value = 8;
    }
    goto LABEL_29;
  }
  if ( a3 )
  {
    *(_QWORD *)phkResult = a3;
    v23 = 0;
  }
  else
  {
    ThreadIntegrityLevel = WxGetThreadIntegrityLevel(&v54);
    if ( ThreadIntegrityLevel < 0 )
    {
      v27 = WX_WIN32_FROM_HR((unsigned int)ThreadIntegrityLevel);
      goto LABEL_28;
    }
    v30 = v54;
    v31 = a4 | 1;
    if ( v54 < 0x2000 )
      v32 = RegOpenKeyExW(hKey, SubKey, 0, v31, (PHKEY)phkResult);
    else
      v32 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, a4 | 1, 0, (PHKEY)phkResult, 0);
    Value = v32;
    if ( v32 )
    {
      if ( (xmmword_180107A60 & 0x20) == 0 )
        return Value;
      WPP_SF_SqDDD(v34, v33, v35, (unsigned int)SubKey, (__int64)hKey, v31, v30, v32);
      goto LABEL_29;
    }
    v23 = 1;
  }
  v24 = v56;
  phkResult[10] = v23;
  if ( v24 )
  {
    Value = RegQueryInfoKeyA(*(HKEY *)phkResult, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
    if ( !Value && *(__int64 *)&ftLastWriteTime < *(_QWORD *)v24 )
    {
      *a8 = 1;
      goto LABEL_29;
    }
  }
  v25 = phkResult + 5;
  Value = RegQueryValueExA(*(HKEY *)phkResult, v10, 0, 0, 0, phkResult + 5);
  if ( Value )
  {
    *v25 = 0;
    Value = 0;
  }
  if ( !*v25 )
    goto LABEL_29;
  v26 = (BYTE *)HeapAlloc(g_hWxProcessHeap, 0, *v25);
  *((_QWORD *)phkResult + 3) = v26;
  if ( v26 )
  {
    cbData = *v25;
    v27 = RegQueryValueExA(*(HKEY *)phkResult, v10, 0, 0, v26, &cbData);
LABEL_28:
    Value = v27;
    goto LABEL_29;
  }
  Value = 8;
LABEL_29:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 13, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, Value, lpData);
  return Value;
}

```

## disassembly

```asm
0x180021320  push    rbp
0x180021322  push    rbx
0x180021323  push    rsi
0x180021324  push    rdi
0x180021325  push    r12
0x180021327  push    r13
0x180021329  push    r14
0x18002132b  push    r15
0x18002132d  lea     rbp, [rsp-1C8h]
0x180021335  sub     rsp, 2C8h
0x18002133c  mov     rax, cs:__security_cookie
0x180021343  xor     rax, rsp
0x180021346  mov     [rbp+200h+var_50], rax
0x18002134d  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Windows\\CurrentVersion\\I"...
0x180021354  xor     eax, eax
0x180021356  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002135d  mov     r13, r8
0x180021360  mov     rbx, [rbp+200h+arg_30]
0x180021367  mov     r12, rdx
0x18002136a  mov     rsi, [rbp+200h+lpValueName]
0x180021371  mov     r15, rcx
0x180021374  mov     r14, [rbp+200h+arg_38]
0x18002137b  lea     rcx, [rbp+200h+var_1E6]; void *
0x18002137f  movaps  [rbp+200h+var_250], xmm1
0x180021383  xor     edx, edx; Val
0x180021385  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ws\\CurrentVersion\\Internet Settings\\"
0x18002138c  mov     r8d, 18Eh; Size
0x180021392  movaps  xmmword ptr [rbp+200h+SubKey], xmm0
0x180021396  mov     edi, r9d
0x180021399  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Windows\\CurrentVersion\\Internet S"...
0x1800213a0  movaps  [rbp+200h+var_230], xmm1
0x1800213a4  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "n\\Internet Settings\\"
0x1800213ab  movaps  [rbp+200h+var_240], xmm0
0x1800213af  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "ntVersion\\Internet Settings\\"
0x1800213b6  movaps  [rbp+200h+var_210], xmm1
0x1800213ba  movups  xmm1, xmmword ptr cs:aSoftwareMicros+6Ah; "ttings\\"
0x1800213c1  mov     [rsp+300h+var_290], r9d
0x1800213c6  movaps  [rbp+200h+var_220], xmm0
0x1800213ca  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+60h; "et Settings\\"
0x1800213d1  movaps  [rbp+200h+var_200], xmm0
0x1800213d5  movups  [rbp+200h+var_200+0Ah], xmm1
0x1800213d9  mov     [rbp+200h+var_280], rbx
0x1800213dd  mov     [rsp+300h+var_288], rsi
0x1800213e2  mov     [rbp+200h+cbData], eax
0x1800213e5  mov     qword ptr [rbp+200h+ftLastWriteTime.dwLowDateTime], rax
0x1800213e9  mov     [rsp+300h+var_28C], 1000h
0x1800213f1  call    memset_0
0x1800213f6  test    byte ptr cs:xmmword_180107A60, 20h
0x1800213fd  jnz     loc_180021862
0x180021403  test    r14, r14
0x180021406  jz      short loc_18002140F
0x180021408  mov     dword ptr [r14], 0
0x18002140f  cmp     r12, 0FFFFFFFF80000002h
0x180021416  jz      loc_180021688
0x18002141c  mov     ecx, 7FFFFFFEh
0x180021421  lea     rbx, aConnections; "Connections"
0x180021428  mov     edx, 0C8h
0x18002142d  lea     r8, [rbp+200h+var_1E8]
0x180021431  test    rcx, rcx
0x180021434  jz      short loc_180021453
0x180021436  movzx   eax, word ptr [rbx]
0x180021439  test    ax, ax
0x18002143c  jz      short loc_180021453
0x18002143e  mov     [r8], ax
0x180021442  add     rbx, 2
0x180021446  add     r8, 2
0x18002144a  dec     rcx
0x18002144d  sub     rdx, 1
0x180021451  jnz     short loc_180021431
0x180021453  test    rdx, rdx
0x180021456  lea     rcx, [r8-2]
0x18002145a  mov     edi, 8007007Ah
0x18002145f  cmovnz  rcx, r8
0x180021463  xor     eax, eax
0x180021465  test    rdx, rdx
0x180021468  cmovnz  edi, eax
0x18002146b  mov     [rcx], ax
0x18002146e  test    edi, edi
0x180021470  jns     short loc_1800214A1
0x180021472  mov     eax, edi
0x180021474  and     eax, 1FFF0000h
0x180021479  cmp     eax, 0C0000h
0x18002147e  jz      loc_18002157A
0x180021484  cmp     eax, 70000h
0x180021489  jnz     loc_1800218CC
0x18002148f  movzx   ebx, di
0x180021492  mov     eax, 13Dh
0x180021497  test    ebx, ebx
0x180021499  cmovz   ebx, eax
0x18002149c  jmp     loc_180021548
0x1800214a1  cmp     dword ptr [r15+8], 0
0x1800214a6  jnz     loc_180021906
0x1800214ac  test    r13, r13
0x1800214af  jz      loc_18002157F
0x1800214b5  mov     [r15], r13
0x1800214b8  xor     eax, eax
0x1800214ba  mov     rdi, [rbp+200h+var_280]
0x1800214be  mov     [r15+28h], eax
0x1800214c2  test    rdi, rdi
0x1800214c5  jnz     loc_1800215EA
0x1800214cb  mov     rcx, [r15]; hKey
0x1800214ce  lea     rdi, [r15+14h]
0x1800214d2  mov     [rsp+300h+lpcbData], rdi; lpcbData
0x1800214d7  xor     r9d, r9d; lpType
0x1800214da  xor     r8d, r8d; lpReserved
0x1800214dd  mov     [rsp+300h+lpData], 0; lpData
0x1800214e6  mov     rdx, rsi; lpValueName
0x1800214e9  call    cs:__imp_RegQueryValueExA
0x1800214ef  mov     ebx, eax
0x1800214f1  test    eax, eax
0x1800214f3  jnz     loc_18002167B
0x1800214f9  mov     eax, [rdi]
0x1800214fb  test    eax, eax
0x1800214fd  jz      short loc_180021548
0x1800214ff  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180021506  mov     r8d, eax; dwBytes
0x180021509  xor     edx, edx; dwFlags
0x18002150b  call    cs:__imp_HeapAlloc
0x180021511  mov     [r15+18h], rax
0x180021515  mov     rcx, rax
0x180021518  test    rax, rax
0x18002151b  jz      loc_1800219C1
0x180021521  mov     eax, [rdi]
0x180021523  xor     r9d, r9d; lpType
0x180021526  mov     [rbp+200h+cbData], eax
0x180021529  xor     r8d, r8d; lpReserved
0x18002152c  lea     rax, [rbp+200h+cbData]
0x180021530  mov     rdx, rsi; lpValueName
0x180021533  mov     [rsp+300h+lpcbData], rax; lpcbData
0x180021538  mov     [rsp+300h+lpData], rcx; lpData
0x18002153d  mov     rcx, [r15]; hKey
0x180021540  call    cs:__imp_RegQueryValueExA
0x180021546  mov     ebx, eax
0x180021548  test    byte ptr cs:xmmword_180107A60, 20h
0x18002154f  jnz     loc_1800219CB
0x180021555  mov     eax, ebx
0x180021557  mov     rcx, [rbp+200h+var_50]
0x18002155e  xor     rcx, rsp; StackCookie
0x180021561  call    __security_check_cookie
0x180021566  add     rsp, 2C8h
0x18002156d  pop     r15
0x18002156f  pop     r14
0x180021571  pop     r13
0x180021573  pop     r12
0x180021575  pop     rdi
0x180021576  pop     rsi
0x180021577  pop     rbx
0x180021578  pop     rbp
0x180021579  retn
0x18002157a  movzx   ebx, di
0x18002157d  jmp     short loc_180021548
0x18002157f  lea     rcx, [rsp+300h+var_28C]; unsigned int *
0x180021584  call    ?WxGetThreadIntegrityLevel@@YAJPEAK@Z; WxGetThreadIntegrityLevel(ulong *)
0x180021589  test    eax, eax
0x18002158b  js      loc_1800219B5
0x180021591  mov     r13d, [rsp+300h+var_290]
0x180021596  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x18002159a  mov     edi, [rsp+300h+var_28C]
0x18002159e  or      r13d, 1
0x1800215a2  xor     r8d, r8d; ulOptions
0x1800215a5  mov     rcx, r12; hKey
0x1800215a8  cmp     edi, 2000h
0x1800215ae  jb      loc_180021767
0x1800215b4  mov     [rsp+300h+lpdwDisposition], r8; lpdwDisposition
0x1800215b9  xor     r9d, r9d; lpClass
0x1800215bc  mov     [rsp+300h+phkResult], r15; phkResult
0x1800215c1  mov     [rsp+300h+lpSecurityAttributes], r8; lpSecurityAttributes
0x1800215c6  mov     dword ptr [rsp+300h+lpcbData], r13d; samDesired
0x1800215cb  mov     dword ptr [rsp+300h+lpData], r8d; dwOptions
0x1800215d0  call    cs:__imp_RegCreateKeyExW
0x1800215d6  mov     ebx, eax
0x1800215d8  test    eax, eax
0x1800215da  jnz     loc_18002177A
0x1800215e0  mov     eax, 1
0x1800215e5  jmp     loc_1800214BA
0x1800215ea  mov     rcx, [r15]; hKey
0x1800215ed  lea     rax, [rbp+200h+ftLastWriteTime]
0x1800215f1  mov     [rsp+300h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800215f6  xor     r9d, r9d; lpReserved
0x1800215f9  mov     [rsp+300h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180021602  xor     r8d, r8d; lpcchClass
0x180021605  mov     [rsp+300h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18002160e  xor     edx, edx; lpClass
0x180021610  mov     [rsp+300h+lpdwDisposition], 0; lpcbMaxValueNameLen
0x180021619  mov     [rsp+300h+phkResult], 0; lpcValues
0x180021622  mov     [rsp+300h+lpSecurityAttributes], 0; lpcbMaxClassLen
0x18002162b  mov     [rsp+300h+lpcbData], 0; lpcbMaxSubKeyLen
0x180021634  mov     [rsp+300h+lpData], 0; lpcSubKeys
0x18002163d  call    cs:__imp_RegQueryInfoKeyA
0x180021643  mov     ebx, eax
0x180021645  test    eax, eax
0x180021647  jnz     loc_1800214CB
0x18002164d  mov     eax, [rdi]
0x18002164f  mov     edx, [rdi+4]
0x180021652  mov     ecx, [rbp+200h+ftLastWriteTime.dwHighDateTime]
0x180021655  shl     rdx, 20h
0x180021659  or      rdx, rax
0x18002165c  shl     rcx, 20h
0x180021660  mov     eax, [rbp+200h+ftLastWriteTime.dwLowDateTime]
0x180021663  or      rcx, rax
0x180021666  cmp     rcx, rdx
0x180021669  jge     loc_1800214CB
0x18002166f  mov     dword ptr [r14], 1
0x180021676  jmp     loc_180021548
0x18002167b  mov     dword ptr [rdi], 0
0x180021681  xor     ebx, ebx
0x180021683  jmp     loc_1800214F9
0x180021688  mov     [rbp+200h+var_278], 0
0x18002168f  test    byte ptr cs:xmmword_180107A60+3, 20h
0x180021696  lea     rbx, aConnections; "Connections"
0x18002169d  lea     rsi, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800216a4  jnz     loc_1800217A7
0x1800216aa  lea     rax, [rbp+200h+var_278]
0x1800216ae  mov     edi, 208h
0x1800216b3  mov     [rsp+300h+lpSecurityAttributes], rax
0x1800216b8  lea     rcx, aInternetsettin; "InternetSettings"
0x1800216bf  lea     rax, [rbp+200h+SubKey]
0x1800216c3  mov     dword ptr [rsp+300h+lpcbData], edi
0x1800216c7  xor     r9d, r9d
0x1800216ca  mov     [rsp+300h+lpData], rax
0x1800216cf  mov     r8, rsi
0x1800216d2  xor     edx, edx
0x1800216d4  call    cs:__imp_RtlGetPersistedStateLocation
0x1800216da  mov     esi, eax
0x1800216dc  test    eax, eax
0x1800216de  js      loc_18002182D
0x1800216e4  mov     ecx, [rbp+200h+var_278]
0x1800216e7  lea     r8, [rbp+200h+SubKey]
0x1800216eb  sub     edi, ecx
0x1800216ed  mov     eax, ecx
0x1800216ef  shr     rax, 1
0x1800216f2  mov     edx, edi
0x1800216f4  lea     r8, [r8+rax*2]
0x1800216f8  shr     rdx, 1
0x1800216fb  mov     word ptr [r8-2], 5Ch ; '\'
0x180021702  jz      loc_18002189C
0x180021708  mov     ecx, 7FFFFFFEh
0x18002170d  mov     rax, rbx
0x180021710  test    rcx, rcx
0x180021713  jz      short loc_180021734
0x180021715  movzx   r9d, word ptr [rax]
0x180021719  test    r9w, r9w
0x18002171d  jz      short loc_180021734
0x18002171f  mov     [r8], r9w
0x180021723  add     rax, 2
0x180021727  add     r8, 2
0x18002172b  dec     rcx
0x18002172e  sub     rdx, 1
0x180021732  jnz     short loc_180021710
0x180021734  xor     eax, eax
0x180021736  lea     rcx, [r8-2]
0x18002173a  test    rdx, rdx
0x18002173d  mov     edi, 8007007Ah
0x180021742  cmovnz  rcx, r8
0x180021746  cmovnz  edi, eax
0x180021749  mov     [rcx], ax
0x18002174c  test    edi, edi
0x18002174e  js      loc_1800218A1
0x180021754  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18002175b  jnz     short loc_1800217CB
0x18002175d  mov     rsi, [rsp+300h+var_288]
0x180021762  jmp     loc_18002146E
0x180021767  mov     r9d, r13d; samDesired
0x18002176a  mov     [rsp+300h+lpData], r15; phkResult
0x18002176f  call    cs:__imp_RegOpenKeyExW
0x180021775  jmp     loc_1800215D6
0x18002177a  test    byte ptr cs:xmmword_180107A60, 20h
0x180021781  jz      loc_180021555
0x180021787  mov     dword ptr [rsp+300h+phkResult], ebx
0x18002178b  lea     r9, [rbp+200h+SubKey]
0x18002178f  mov     dword ptr [rsp+300h+lpSecurityAttributes], edi
0x180021793  mov     dword ptr [rsp+300h+lpcbData], r13d
0x180021798  mov     [rsp+300h+lpData], r12
0x18002179d  call    WPP_SF_SqDDD
0x1800217a2  jmp     loc_180021548
0x1800217a7  lea     rax, [rbp+200h+SubKey]
0x1800217ab  mov     [rsp+300h+lpSecurityAttributes], rax
0x1800217b0  lea     r9, aInternetsettin; "InternetSettings"
0x1800217b7  mov     [rsp+300h+lpcbData], rbx
0x1800217bc  mov     [rsp+300h+lpData], rsi
0x1800217c1  call    WPP_SF_SSSqd
0x1800217c6  jmp     loc_1800216AA
0x1800217cb  lea     rax, [rbp+200h+SubKey]
0x1800217cf  mov     edx, 0Dh
0x1800217d4  mov     [rsp+300h+lpSecurityAttributes], rax
0x1800217d9  lea     r9, aInternetsettin; "InternetSettings"
0x1800217e0  lea     rax, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800217e7  mov     [rsp+300h+lpcbData], rbx
0x1800217ec  mov     ecx, 41Dh
0x1800217f1  mov     [rsp+300h+lpData], rax
0x1800217f6  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x1800217fd  call    WPP_SF_SSSS
0x180021802  test    byte ptr cs:xmmword_180107A60+3, 20h
0x180021809  jz      loc_18002175D
0x18002180f  mov     edx, 0Eh
0x180021814  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18002181b  mov     ecx, 41Dh
0x180021820  mov     r9d, edi
0x180021823  call    WPP_SF_d
0x180021828  jmp     loc_18002175D
  ... truncated ...
```

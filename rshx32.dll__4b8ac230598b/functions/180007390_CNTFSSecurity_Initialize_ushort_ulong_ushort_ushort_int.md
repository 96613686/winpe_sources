# CNTFSSecurity::Initialize(ushort *,ulong,ushort *,ushort *,int)

- ea: `0x180007390`
- end: `0x18000762a`
- name: `?Initialize@CNTFSSecurity@@UEAAJPEAGK00H@Z`
- size: `666`
- prototype: `__int64 __fastcall(CNTFSSecurity *this, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005fd4`

## callees

- `0x18000554c`
- `0x180007390`
- `0x18000c2c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007482`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800074d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007482`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800074d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007444`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800074b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007589`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007444`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800074b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007589`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007537`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007537`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000756b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800075b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000756b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800075b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800075d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800075eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800075d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800075eb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000742a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000745f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000749b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800074cc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000742a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000745f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000749b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800074cc`

## string_xrefs

- `0x180007500`: `System\CurrentControlSet\Services\NetLogon\Parameters`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::Initialize(
        CNTFSSecurity *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6)
{
  int v8; // r9d
  WCHAR **v9; // rdi
  int v10; // r12d
  HLOCAL *v11; // rsi
  DWORD v12; // eax
  __int64 v13; // r15
  DWORD v14; // r14d
  WCHAR *v15; // rax
  DWORD v16; // eax
  WCHAR *v17; // rcx
  DWORD v18; // eax
  DWORD v19; // edi
  WCHAR *v20; // rax
  HLOCAL *v21; // rdi
  int v22; // esi
  DWORD v23; // eax
  BYTE *v24; // rax
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-10h]
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF

  if ( (a3 & 4) != 0 )
  {
    v8 = a3 | 0x100;
    if ( (a3 & 0x41) != 1 )
      v8 = a3;
    a3 = v8 | 0x4000;
    if ( (v8 & 8) != 0 )
      a3 = v8;
    if ( (a3 & 2) != 0 )
      a3 |= 0x8000u;
  }
  v9 = (WCHAR **)((char *)this + 352);
  v10 = CSecurityInformation::Initialize(this, a2, a3, a4, a5, a6);
  if ( this == (CNTFSSecurity *)-352LL )
    goto LABEL_20;
  v11 = (HLOCAL *)((char *)this + 360);
  if ( this == (CNTFSSecurity *)-360LL )
    goto LABEL_20;
  v12 = ExpandEnvironmentStringsW(Src, 0, 0);
  if ( v12 )
  {
    v13 = v12 + 1;
    v14 = v12 + 1;
    v15 = (WCHAR *)LocalAlloc(0x40u, 2 * v13);
    *v9 = v15;
    if ( v15 )
    {
      v16 = ExpandEnvironmentStringsW(Src, v15, v13);
      v17 = *v9;
      if ( !v16 )
      {
LABEL_15:
        LocalFree(v17);
        *v9 = 0;
        goto LABEL_16;
      }
      if ( (int)StringCchCatW(v17, v14, L"\\") < 0 )
      {
        v17 = *v9;
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  v18 = ExpandEnvironmentStringsW(aSystemroot, 0, 0);
  v19 = v18;
  if ( v18 )
  {
    v20 = (WCHAR *)LocalAlloc(0x40u, 2LL * v18);
    *v11 = v20;
    if ( v20 )
    {
      if ( !ExpandEnvironmentStringsW(aSystemroot, v20, v19) )
      {
        LocalFree(*v11);
        *v11 = 0;
      }
    }
  }
LABEL_20:
  hKey = 0;
  lpSubKey[0] = L"Software\\Policies\\Microsoft\\Netlogon";
  v21 = (HLOCAL *)((char *)this + 368);
  lpSubKey[1] = L"System\\CurrentControlSet\\Services\\NetLogon\\Parameters";
  if ( this == (CNTFSSecurity *)-368LL )
    goto LABEL_32;
  v22 = 0;
  while ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[v22], 0, 1u, &hKey) )
  {
LABEL_29:
    if ( (unsigned int)++v22 >= 2 )
      goto LABEL_32;
  }
  cbData = 0;
  if ( RegQueryValueExW(hKey, L"SysVol", 0, 0, 0, &cbData)
    || (v23 = cbData) == 0
    || (cbData += 2, v24 = (BYTE *)LocalAlloc(0x40u, v23 + 2), (*v21 = v24) == 0) )
  {
LABEL_28:
    RegCloseKey(hKey);
    goto LABEL_29;
  }
  if ( RegQueryValueExW(hKey, L"SysVol", 0, 0, v24, &cbData) )
  {
    LocalFree(*v21);
    *v21 = 0;
    goto LABEL_28;
  }
  RegCloseKey(hKey);
LABEL_32:
  if ( v10 < 0 )
  {
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 7) = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007390  mov     [rsp-28h+arg_8], rbx
0x180007395  mov     [rsp-28h+arg_18], rsi
0x18000739a  push    rbp
0x18000739b  push    rdi
0x18000739c  push    r12
0x18000739e  push    r14
0x1800073a0  push    r15
0x1800073a2  mov     rbp, rsp
0x1800073a5  sub     rsp, 40h
0x1800073a9  mov     r10, r9
0x1800073ac  mov     rbx, rcx
0x1800073af  test    r8b, 4
0x1800073b3  jz      short loc_1800073E3
0x1800073b5  mov     eax, r8d
0x1800073b8  mov     r9d, r8d
0x1800073bb  bts     r9d, 8
0x1800073c0  and     al, 41h
0x1800073c2  cmp     al, 1
0x1800073c4  cmovnz  r9d, r8d
0x1800073c8  mov     r8d, r9d
0x1800073cb  bts     r8d, 0Eh
0x1800073d0  test    r9b, 8
0x1800073d4  cmovnz  r8d, r9d
0x1800073d8  test    r8b, 2
0x1800073dc  jz      short loc_1800073E3
0x1800073de  bts     r8d, 0Fh; unsigned int
0x1800073e3  mov     eax, [rbp+arg_28]
0x1800073e6  mov     r9, r10; unsigned __int16 *
0x1800073e9  mov     dword ptr [rsp+40h+lpcbData], eax; int
0x1800073ed  mov     rax, [rbp+arg_20]
0x1800073f1  mov     [rsp+40h+phkResult], rax; unsigned __int16 *
0x1800073f6  call    ?Initialize@CSecurityInformation@@UEAAJPEAGK00H@Z; CSecurityInformation::Initialize(ushort *,ulong,ushort *,ushort *,int)
0x1800073fb  lea     rdi, [rbx+160h]
0x180007402  mov     r12d, eax
0x180007405  test    rdi, rdi
0x180007408  jz      loc_1800074E6
0x18000740e  lea     rsi, [rbx+168h]
0x180007415  test    rsi, rsi
0x180007418  jz      loc_1800074E6
0x18000741e  xor     r8d, r8d; nSize
0x180007421  lea     rcx, Src; "%SystemDrive%"
0x180007428  xor     edx, edx; lpDst
0x18000742a  call    cs:__imp_ExpandEnvironmentStringsW
0x180007430  test    eax, eax
0x180007432  jz      short loc_18000748F
0x180007434  lea     r15d, [rax+1]
0x180007438  mov     ecx, 40h ; '@'; uFlags
0x18000743d  lea     rdx, [r15+r15]; uBytes
0x180007441  mov     r14d, r15d
0x180007444  call    cs:__imp_LocalAlloc
0x18000744a  mov     [rdi], rax
0x18000744d  test    rax, rax
0x180007450  jz      short loc_18000748F
0x180007452  mov     r8d, r15d; nSize
0x180007455  lea     rcx, Src; "%SystemDrive%"
0x18000745c  mov     rdx, rax; lpDst
0x18000745f  call    cs:__imp_ExpandEnvironmentStringsW
0x180007465  mov     rcx, [rdi]; unsigned __int16 *
0x180007468  test    eax, eax
0x18000746a  jz      short loc_180007482
0x18000746c  lea     r8, asc_1800209A0; "\\"
0x180007473  mov     edx, r14d; unsigned __int64
0x180007476  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000747b  test    eax, eax
0x18000747d  jns     short loc_18000748F
0x18000747f  mov     rcx, [rdi]; hMem
0x180007482  call    cs:__imp_LocalFree
0x180007488  mov     qword ptr [rdi], 0
0x18000748f  xor     r8d, r8d; nSize
0x180007492  lea     rcx, aSystemroot; "%SystemRoot%"
0x180007499  xor     edx, edx; lpDst
0x18000749b  call    cs:__imp_ExpandEnvironmentStringsW
0x1800074a1  mov     edi, eax
0x1800074a3  test    eax, eax
0x1800074a5  jz      short loc_1800074E6
0x1800074a7  mov     edx, edi
0x1800074a9  mov     ecx, 40h ; '@'; uFlags
0x1800074ae  add     rdx, rdx; uBytes
0x1800074b1  call    cs:__imp_LocalAlloc
0x1800074b7  mov     [rsi], rax
0x1800074ba  test    rax, rax
0x1800074bd  jz      short loc_1800074E6
0x1800074bf  mov     r8d, edi; nSize
0x1800074c2  lea     rcx, aSystemroot; "%SystemRoot%"
0x1800074c9  mov     rdx, rax; lpDst
0x1800074cc  call    cs:__imp_ExpandEnvironmentStringsW
0x1800074d2  test    eax, eax
0x1800074d4  jnz     short loc_1800074E6
0x1800074d6  mov     rcx, [rsi]; hMem
0x1800074d9  call    cs:__imp_LocalFree
0x1800074df  mov     qword ptr [rsi], 0
0x1800074e6  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\Netlogon"
0x1800074ed  mov     [rbp+hKey], 0
0x1800074f5  mov     [rbp+lpSubKey], rax
0x1800074f9  lea     rdi, [rbx+170h]
0x180007500  lea     rax, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ne"...
0x180007507  mov     [rbp+var_8], rax
0x18000750b  test    rdi, rdi
0x18000750e  jz      loc_1800075F1
0x180007514  xor     esi, esi
0x180007516  lea     rax, [rbp+hKey]
0x18000751a  movsxd  rdx, esi
0x18000751d  mov     r9d, 1; samDesired
0x180007523  mov     [rsp+40h+phkResult], rax; phkResult
0x180007528  xor     r8d, r8d; ulOptions
0x18000752b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007532  mov     rdx, [rbp+rdx*8+lpSubKey]; lpSubKey
0x180007537  call    cs:__imp_RegOpenKeyExW
0x18000753d  test    eax, eax
0x18000753f  jnz     loc_1800075DA
0x180007545  mov     rcx, [rbp+hKey]; hKey
0x180007549  lea     rdx, ValueName; "SysVol"
0x180007550  mov     [rbp+cbData], eax
0x180007553  xor     r9d, r9d; lpType
0x180007556  lea     rax, [rbp+cbData]
0x18000755a  xor     r8d, r8d; lpReserved
0x18000755d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180007562  mov     [rsp+40h+phkResult], 0; lpData
0x18000756b  call    cs:__imp_RegQueryValueExW
0x180007571  test    eax, eax
0x180007573  jnz     short loc_1800075D0
0x180007575  mov     eax, [rbp+cbData]
0x180007578  test    eax, eax
0x18000757a  jz      short loc_1800075D0
0x18000757c  add     eax, 2
0x18000757f  mov     ecx, 40h ; '@'; uFlags
0x180007584  mov     edx, eax; uBytes
0x180007586  mov     [rbp+cbData], eax
0x180007589  call    cs:__imp_LocalAlloc
0x18000758f  mov     [rdi], rax
0x180007592  test    rax, rax
0x180007595  jz      short loc_1800075D0
0x180007597  lea     rcx, [rbp+cbData]
0x18000759b  xor     r9d, r9d; lpType
0x18000759e  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x1800075a3  lea     rdx, ValueName; "SysVol"
0x1800075aa  mov     rcx, [rbp+hKey]; hKey
0x1800075ae  xor     r8d, r8d; lpReserved
0x1800075b1  mov     [rsp+40h+phkResult], rax; lpData
0x1800075b6  call    cs:__imp_RegQueryValueExW
0x1800075bc  test    eax, eax
0x1800075be  jz      short loc_1800075E7
0x1800075c0  mov     rcx, [rdi]; hMem
0x1800075c3  call    cs:__imp_LocalFree
0x1800075c9  mov     qword ptr [rdi], 0
0x1800075d0  mov     rcx, [rbp+hKey]; hKey
0x1800075d4  call    cs:__imp_RegCloseKey
0x1800075da  inc     esi
0x1800075dc  cmp     esi, 2
0x1800075df  jb      loc_180007516
0x1800075e5  jmp     short loc_1800075F1
0x1800075e7  mov     rcx, [rbp+hKey]; hKey
0x1800075eb  call    cs:__imp_RegCloseKey
0x1800075f1  test    r12d, r12d
0x1800075f4  jns     short loc_18000760E
0x1800075f6  mov     qword ptr [rbx+48h], 0
0x1800075fe  mov     qword ptr [rbx+50h], 0
0x180007606  mov     qword ptr [rbx+38h], 0
0x18000760e  lea     r11, [rsp+40h+var_s0]
0x180007613  mov     eax, r12d
0x180007616  mov     rbx, [r11+38h]
0x18000761a  mov     rsi, [r11+48h]
0x18000761e  mov     rsp, r11
0x180007621  pop     r15
0x180007623  pop     r14
0x180007625  pop     r12
0x180007627  pop     rdi
0x180007628  pop     rbp
0x180007629  retn
```

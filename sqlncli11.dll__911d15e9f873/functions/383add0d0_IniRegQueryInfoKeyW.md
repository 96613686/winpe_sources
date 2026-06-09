# IniRegQueryInfoKeyW

- ea: `0x383add0d0`
- end: `0x383add57b`
- name: `IniRegQueryInfoKeyW`
- size: `1195`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPDWORD lpcSubKeys, LPDWORD lpcbMaxSubKeyLen, LPDWORD lpcbMaxClassLen, LPDWORD lpcValues, LPDWORD, LPDWORD, LPDWORD, PFILETIME)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x383891780`

## callees

- `0x383adcd50`
- `0x383add0d0`
- `0x383add590`
- `0x383add760`
- `0x383add980`

## import_xrefs

- `MSVCR100!wcschr` at `0x383add412`
- `MSVCR100!wcschr` at `0x383add412`
- `KERNEL32!SetLastError` at `0x383add2c6`
- `KERNEL32!SetLastError` at `0x383add345`
- `KERNEL32!SetLastError` at `0x383add47f`
- `KERNEL32!SetLastError` at `0x383add4e8`
- `KERNEL32!SetLastError` at `0x383add2c6`
- `KERNEL32!SetLastError` at `0x383add345`
- `KERNEL32!SetLastError` at `0x383add47f`
- `KERNEL32!SetLastError` at `0x383add4e8`
- `KERNEL32!CompareStringW` at `0x383add3fe`
- `KERNEL32!CompareStringW` at `0x383add3fe`
- `KERNEL32!HeapFree` at `0x383add2bd`
- `KERNEL32!HeapFree` at `0x383add457`
- `KERNEL32!HeapFree` at `0x383add476`
- `KERNEL32!HeapFree` at `0x383add2bd`
- `KERNEL32!HeapFree` at `0x383add457`
- `KERNEL32!HeapFree` at `0x383add476`
- `KERNEL32!GetProcessHeap` at `0x383add2af`
- `KERNEL32!GetProcessHeap` at `0x383add447`
- `KERNEL32!GetProcessHeap` at `0x383add468`
- `KERNEL32!GetProcessHeap` at `0x383add2af`
- `KERNEL32!GetProcessHeap` at `0x383add447`
- `KERNEL32!GetProcessHeap` at `0x383add468`
- `KERNEL32!DebugBreak` at `0x383add103`
- `KERNEL32!DebugBreak` at `0x383add10e`
- `KERNEL32!DebugBreak` at `0x383add11f`
- `KERNEL32!DebugBreak` at `0x383add12a`
- `KERNEL32!DebugBreak` at `0x383add13b`
- `KERNEL32!DebugBreak` at `0x383add14c`
- `KERNEL32!DebugBreak` at `0x383add103`
- `KERNEL32!DebugBreak` at `0x383add10e`
- `KERNEL32!DebugBreak` at `0x383add11f`
- `KERNEL32!DebugBreak` at `0x383add12a`
- `KERNEL32!DebugBreak` at `0x383add13b`
- `KERNEL32!DebugBreak` at `0x383add14c`
- `ADVAPI32!RegEnumKeyExW` at `0x383add4a6`
- `ADVAPI32!RegEnumKeyExW` at `0x383add4a6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x383add569`
- `ADVAPI32!RegQueryInfoKeyW` at `0x383add569`
- `ADVAPI32!RegEnumValueW` at `0x383add2f1`
- `ADVAPI32!RegEnumValueW` at `0x383add2f1`

## pseudocode

```c
LSTATUS __fastcall IniRegQueryInfoKeyW(
        HKEY hKey,
        WCHAR *a2,
        DWORD *a3,
        DWORD *a4,
        LPDWORD lpcSubKeys,
        LPDWORD lpcbMaxSubKeyLen,
        LPDWORD lpcbMaxClassLen,
        LPDWORD lpcValues,
        LPDWORD lpcbMaxValueNameLen,
        LPDWORD lpcbMaxValueLen,
        LPDWORD lpcbSecurityDescriptor,
        PFILETIME lpftLastWriteTime)
{
  HKEY v14; // r12
  LPDWORD v15; // rbx
  LPDWORD v16; // rdx
  LPDWORD v17; // r14
  DWORD j; // ebx
  const WCHAR *v20; // rax
  _WORD *v21; // rax
  void *v22; // rdi
  const WCHAR *v23; // rdx
  WCHAR v24; // cx
  LSTATUS v25; // r12d
  int v26; // r8d
  const WCHAR *v27; // r10
  __int64 v28; // rax
  DWORD v29; // r9d
  HANDLE v30; // rax
  DWORD v31; // ecx
  DWORD v32; // ecx
  DWORD i; // r13d
  __int64 Path; // rax
  WCHAR *v35; // r15
  __int64 v36; // rsi
  LSTATUS v37; // r12d
  const WCHAR *RawString; // rax
  const WCHAR *v39; // rdi
  int v40; // r14d
  __int64 v41; // rbx
  int v42; // eax
  __int64 v43; // rax
  bool v44; // zf
  HANDLE ProcessHeap; // rax
  HANDLE v46; // rax
  DWORD v47; // ecx
  DWORD cchValueName[2]; // [rsp+60h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-30h] BYREF

  v14 = hKey;
  if ( !dword_383B1F178 )
    return RegQueryInfoKeyW(
             hKey,
             a2,
             a3,
             a4,
             lpcSubKeys,
             lpcbMaxSubKeyLen,
             lpcbMaxClassLen,
             lpcValues,
             lpcbMaxValueNameLen,
             lpcbMaxValueLen,
             lpcbSecurityDescriptor,
             lpftLastWriteTime);
  if ( a2 )
    DebugBreak();
  if ( a3 )
    DebugBreak();
  if ( lpcbMaxClassLen )
    DebugBreak();
  if ( a4 )
    DebugBreak();
  if ( lpcbSecurityDescriptor )
    DebugBreak();
  if ( lpftLastWriteTime )
    DebugBreak();
  v15 = lpcSubKeys;
  v16 = lpcbMaxSubKeyLen;
  if ( lpcSubKeys )
  {
    *lpcSubKeys = 0;
    if ( !lpcbMaxSubKeyLen )
    {
LABEL_55:
      for ( i = 0; ; ++i )
      {
        cbData = 0;
        if ( !dword_383B1F178 )
        {
          v37 = RegEnumKeyExW(v14, i, 0, &cbData, 0, 0, 0, 0);
          goto LABEL_78;
        }
        Path = IniRegMakePath(v14, &WideCharStr);
        v35 = (WCHAR *)Path;
        if ( !Path )
        {
          SetLastError(8u);
          return 8;
        }
        v36 = -1;
        do
          ++v36;
        while ( *(_WORD *)(Path + 2 * v36) );
        v37 = 259;
        RawString = (const WCHAR *)IniRegGetRawString(0, 0);
        *(_QWORD *)cchValueName = RawString;
        v39 = RawString;
        if ( !RawString )
        {
          v37 = 8;
          goto LABEL_76;
        }
        v40 = 0;
        if ( !*RawString )
          goto LABEL_74;
        while ( 1 )
        {
          v41 = -1;
          do
            ++v41;
          while ( v39[v41] );
          v42 = v36;
          if ( (unsigned int)v41 < (unsigned int)v36 )
            v42 = v41;
          if ( CompareStringW(0x400u, 1u, v35, v36, v39, v42) != 2 || wcschr(&v39[(unsigned int)v36], 0x5Cu) )
            goto LABEL_70;
          if ( v40 == i )
            break;
          ++v40;
LABEL_70:
          v43 = (unsigned int)(v41 + 1);
          v44 = v39[v43] == 0;
          v39 += v43;
          if ( v44 )
            goto LABEL_73;
        }
        cbData = v41 - v36;
        v37 = 0;
LABEL_73:
        v15 = lpcSubKeys;
LABEL_74:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, *(LPVOID *)cchValueName);
LABEL_76:
        v46 = GetProcessHeap();
        HeapFree(v46, 0, v35);
        SetLastError(v37);
LABEL_78:
        if ( v37 )
          return v37;
        if ( v15 )
          ++*v15;
        if ( lpcbMaxSubKeyLen )
        {
          v47 = cbData;
          if ( *lpcbMaxSubKeyLen > cbData )
            v47 = *lpcbMaxSubKeyLen;
          *lpcbMaxSubKeyLen = v47;
        }
        v14 = hKey;
      }
    }
LABEL_54:
    *lpcbMaxSubKeyLen = 0;
    goto LABEL_55;
  }
  if ( lpcbMaxSubKeyLen )
    goto LABEL_54;
  if ( lpcValues )
  {
    *lpcValues = 0;
    if ( !lpcbMaxValueNameLen )
      goto LABEL_22;
  }
  else if ( !lpcbMaxValueNameLen )
  {
    v17 = lpcbMaxValueLen;
    if ( !lpcbMaxValueLen )
      return 0;
    goto LABEL_23;
  }
  *lpcbMaxValueNameLen = 0;
LABEL_22:
  v17 = lpcbMaxValueLen;
  if ( lpcbMaxValueLen )
LABEL_23:
    *v17 = 0;
  for ( j = 0; ; ++j )
  {
    cchValueName[0] = 0;
    cbData = 0;
    if ( !dword_383B1F178 )
    {
      v25 = RegEnumValueW(v14, j, 0, cchValueName, 0, 0, 0, &cbData);
      goto LABEL_39;
    }
    v20 = (const WCHAR *)IniRegPathFromHKEY(v14, v16);
    v21 = (_WORD *)IniRegGetRawString(v20, 0);
    v22 = v21;
    v23 = v21;
    if ( !v21 )
      break;
    v24 = *v21;
    v25 = 259;
    v26 = 0;
    if ( *v21 )
    {
      while ( 1 )
      {
        v27 = v23;
        v28 = -1;
        do
          ++v28;
        while ( v23[v28] );
        v29 = v28;
        if ( v24 == 64 && !v23[1] )
        {
          v27 = &WideCharStr;
          v29 = 0;
        }
        if ( v26 == j )
          break;
        ++v26;
        v23 += (unsigned int)(v28 + 1);
        v24 = *v23;
        if ( !*v23 )
          goto LABEL_37;
      }
      cchValueName[0] = v29;
      v25 = IniRegQueryValueExW(hKey, v27, 0, 0, 0, &cbData);
    }
LABEL_37:
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v22);
    SetLastError(v25);
LABEL_39:
    if ( v25 )
      return v25;
    if ( lpcValues )
      ++*lpcValues;
    if ( lpcbMaxValueNameLen )
    {
      v31 = cchValueName[0];
      if ( *lpcbMaxValueNameLen > cchValueName[0] )
        v31 = *lpcbMaxValueNameLen;
      *lpcbMaxValueNameLen = v31;
    }
    if ( v17 )
    {
      v32 = cbData;
      if ( *v17 > cbData )
        v32 = *v17;
      *v17 = v32;
    }
    v14 = hKey;
  }
  v25 = 8;
  SetLastError(8u);
  return v25;
}

```

## disassembly

```asm
0x383add0d0  mov     [rsp+arg_0], rcx
0x383add0d5  push    rbx
0x383add0d6  push    rdi
0x383add0d7  push    r12
0x383add0d9  sub     rsp, 80h
0x383add0e0  cmp     cs:dword_383B1F178, 0
0x383add0e7  mov     rdi, r9
0x383add0ea  mov     rbx, r8
0x383add0ed  mov     r12, rcx
0x383add0f0  jz      loc_383ADD501
0x383add0f6  mov     [rsp+98h+arg_8], rbp
0x383add0fe  test    rdx, rdx
0x383add101  jz      short loc_383ADD109
0x383add103  call    cs:__imp_DebugBreak
0x383add109  test    rbx, rbx
0x383add10c  jz      short loc_383ADD114
0x383add10e  call    cs:__imp_DebugBreak
0x383add114  cmp     [rsp+98h+lpcbMaxClassLen], 0
0x383add11d  jz      short loc_383ADD125
0x383add11f  call    cs:__imp_DebugBreak
0x383add125  test    rdi, rdi
0x383add128  jz      short loc_383ADD130
0x383add12a  call    cs:__imp_DebugBreak
0x383add130  cmp     [rsp+98h+arg_50], 0
0x383add139  jz      short loc_383ADD141
0x383add13b  call    cs:__imp_DebugBreak
0x383add141  cmp     [rsp+98h+arg_58], 0
0x383add14a  jz      short loc_383ADD152
0x383add14c  call    cs:__imp_DebugBreak
0x383add152  mov     rbx, [rsp+98h+lpcSubKeys]
0x383add15a  mov     rdx, [rsp+98h+lpcbMaxSubKeyLen]
0x383add162  mov     [rsp+98h+arg_10], rsi
0x383add16a  xor     ebp, ebp
0x383add16c  mov     [rsp+98h+var_20], r14
0x383add171  mov     [rsp+98h+var_28], r15
0x383add176  test    rbx, rbx
0x383add179  jnz     loc_383ADD353
0x383add17f  test    rdx, rdx
0x383add182  jnz     loc_383ADD35A
0x383add188  mov     r15, [rsp+98h+lpcValues]
0x383add190  mov     rsi, [rsp+98h+arg_40]
0x383add198  test    r15, r15
0x383add19b  jnz     short loc_383ADD1D7
0x383add19d  test    rsi, rsi
0x383add1a0  jnz     short loc_383ADD1DF
0x383add1a2  mov     r14, [rsp+98h+arg_48]
0x383add1aa  test    r14, r14
0x383add1ad  jnz     short loc_383ADD1EE
0x383add1af  xor     eax, eax
0x383add1b1  mov     r14, [rsp+98h+var_20]
0x383add1b6  mov     rsi, [rsp+98h+arg_10]
0x383add1be  mov     r15, [rsp+98h+var_28]
0x383add1c3  mov     rbp, [rsp+98h+arg_8]
0x383add1cb  add     rsp, 80h
0x383add1d2  pop     r12
0x383add1d4  pop     rdi
0x383add1d5  pop     rbx
0x383add1d6  retn
0x383add1d7  mov     [r15], ebp
0x383add1da  test    rsi, rsi
0x383add1dd  jz      short loc_383ADD1E1
0x383add1df  mov     [rsi], ebp
0x383add1e1  mov     r14, [rsp+98h+arg_48]
0x383add1e9  test    r14, r14
0x383add1ec  jz      short loc_383ADD1F1
0x383add1ee  mov     [r14], ebp
0x383add1f1  mov     ebx, ebp
0x383add1f3  nop     word ptr [rax+rax]
0x383add1f8  cmp     cs:dword_383B1F178, ebp
0x383add1fe  mov     [rsp+98h+cchValueName], ebp
0x383add202  mov     [rsp+98h+cbData], ebp
0x383add206  mov     rcx, r12; hKey
0x383add209  jz      loc_383ADD2CE
0x383add20f  call    IniRegPathFromHKEY
0x383add214  xor     edx, edx; lpKeyName
0x383add216  mov     rcx, rax; lpAppName
0x383add219  call    IniRegGetRawString
0x383add21e  mov     rdi, rax
0x383add221  mov     rdx, rax
0x383add224  test    rax, rax
0x383add227  jz      loc_383ADD33C
0x383add22d  movzx   ecx, word ptr [rax]
0x383add230  mov     r12d, 103h
0x383add236  mov     r8d, ebp
0x383add239  test    cx, cx
0x383add23c  jz      short loc_383ADD2AF
0x383add23e  xchg    ax, ax
0x383add240  mov     r10, rdx
0x383add243  or      rax, 0FFFFFFFFFFFFFFFFh
0x383add247  inc     rax
0x383add24a  cmp     [rdx+rax*2], bp
0x383add24e  jnz     short loc_383ADD247
0x383add250  mov     r9d, eax
0x383add253  cmp     cx, 40h ; '@'
0x383add257  jnz     short loc_383ADD269
0x383add259  cmp     [rdx+2], bp
0x383add25d  jnz     short loc_383ADD269
0x383add25f  lea     r10, WideCharStr
0x383add266  mov     r9d, ebp
0x383add269  cmp     r8d, ebx
0x383add26c  jz      short loc_383ADD282
0x383add26e  lea     ecx, [rax+1]
0x383add271  inc     r8d
0x383add274  lea     rdx, [rdx+rcx*2]
0x383add278  movzx   ecx, word ptr [rdx]
0x383add27b  test    cx, cx
0x383add27e  jnz     short loc_383ADD240
0x383add280  jmp     short loc_383ADD2AF
0x383add282  mov     rcx, [rsp+98h+arg_0]
0x383add28a  lea     rax, [rsp+98h+cbData]
0x383add28f  mov     [rsp+98h+cchValueName], r9d
0x383add294  mov     [rsp+98h+lpType], rax
0x383add299  xor     r9d, r9d
0x383add29c  xor     r8d, r8d
0x383add29f  mov     rdx, r10
0x383add2a2  mov     [rsp+98h+lpReserved], rbp
0x383add2a7  call    IniRegQueryValueExW
0x383add2ac  mov     r12d, eax
0x383add2af  call    cs:__imp_GetProcessHeap
0x383add2b5  mov     r8, rdi; lpMem
0x383add2b8  xor     edx, edx; dwFlags
0x383add2ba  mov     rcx, rax; hHeap
0x383add2bd  call    cs:__imp_HeapFree
0x383add2c3  mov     ecx, r12d; dwErrCode
0x383add2c6  call    cs:__imp_SetLastError
0x383add2cc  jmp     short loc_383ADD2FA
0x383add2ce  lea     rax, [rsp+98h+cbData]
0x383add2d3  lea     r9, [rsp+98h+cchValueName]; lpcchValueName
0x383add2d8  xor     r8d, r8d; lpValueName
0x383add2db  mov     [rsp+98h+lpcbData], rax; lpcbData
0x383add2e0  mov     [rsp+98h+lpData], rbp; lpData
0x383add2e5  mov     edx, ebx; dwIndex
0x383add2e7  mov     [rsp+98h+lpType], rbp; lpType
0x383add2ec  mov     [rsp+98h+lpReserved], rbp; lpReserved
0x383add2f1  call    cs:__imp_RegEnumValueW
0x383add2f7  mov     r12d, eax
0x383add2fa  test    r12d, r12d
0x383add2fd  jnz     short loc_383ADD34B
0x383add2ff  test    r15, r15
0x383add302  jz      short loc_383ADD307
0x383add304  inc     dword ptr [r15]
0x383add307  test    rsi, rsi
0x383add30a  jz      short loc_383ADD319
0x383add30c  mov     eax, [rsi]
0x383add30e  mov     ecx, [rsp+98h+cchValueName]
0x383add312  cmp     eax, ecx
0x383add314  cmova   ecx, eax
0x383add317  mov     [rsi], ecx
0x383add319  test    r14, r14
0x383add31c  jz      short loc_383ADD32D
0x383add31e  mov     eax, [r14]
0x383add321  mov     ecx, [rsp+98h+cbData]
0x383add325  cmp     eax, ecx
0x383add327  cmova   ecx, eax
0x383add32a  mov     [r14], ecx
0x383add32d  mov     r12, [rsp+98h+arg_0]
0x383add335  inc     ebx
0x383add337  jmp     loc_383ADD1F8
0x383add33c  mov     r12d, 8
0x383add342  mov     ecx, r12d; dwErrCode
0x383add345  call    cs:__imp_SetLastError
0x383add34b  mov     eax, r12d
0x383add34e  jmp     loc_383ADD1B1
0x383add353  mov     [rbx], ebp
0x383add355  test    rdx, rdx
0x383add358  jz      short loc_383ADD35C
0x383add35a  mov     [rdx], ebp
0x383add35c  mov     [rsp+98h+arg_18], r13
0x383add364  mov     r14d, 8
0x383add36a  mov     r13d, ebp
0x383add36d  nop     dword ptr [rax]
0x383add370  cmp     cs:dword_383B1F178, ebp
0x383add376  mov     [rsp+98h+cbData], ebp
0x383add37a  mov     rcx, r12; hKey
0x383add37d  jz      loc_383ADD487
0x383add383  lea     rdx, WideCharStr
0x383add38a  call    IniRegMakePath
0x383add38f  mov     r15, rax
0x383add392  test    rax, rax
0x383add395  jz      loc_383ADD4E5
0x383add39b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x383add39f  nop
0x383add3a0  inc     rsi
0x383add3a3  cmp     [rax+rsi*2], bp
0x383add3a7  jnz     short loc_383ADD3A0
0x383add3a9  xor     edx, edx; lpKeyName
0x383add3ab  xor     ecx, ecx; lpAppName
0x383add3ad  mov     r12d, 103h
0x383add3b3  call    IniRegGetRawString
0x383add3b8  mov     qword ptr [rsp+98h+cchValueName], rax
0x383add3bd  mov     rdi, rax
0x383add3c0  test    rax, rax
0x383add3c3  jz      loc_383ADD465
0x383add3c9  mov     r14d, ebp
0x383add3cc  cmp     [rax], bp
0x383add3cf  jz      short loc_383ADD447
0x383add3d1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x383add3d5  inc     rbx
0x383add3d8  cmp     [rdi+rbx*2], bp
0x383add3dc  jnz     short loc_383ADD3D5
0x383add3de  mov     eax, esi
0x383add3e0  cmp     ebx, esi
0x383add3e2  mov     r9d, esi; cchCount1
0x383add3e5  cmovb   eax, ebx
0x383add3e8  mov     r8, r15; lpString1
0x383add3eb  mov     edx, 1; dwCmpFlags
0x383add3f0  mov     dword ptr [rsp+98h+lpType], eax; cchCount2
0x383add3f4  mov     ecx, 400h; Locale
0x383add3f9  mov     [rsp+98h+lpReserved], rdi; lpString2
0x383add3fe  call    cs:__imp_CompareStringW
0x383add404  cmp     eax, 2
0x383add407  jnz     short loc_383ADD429
0x383add409  lea     edx, [rax+5Ah]; Ch
0x383add40c  mov     eax, esi
0x383add40e  lea     rcx, [rdi+rax*2]; Str
0x383add412  call    cs:__imp_wcschr
0x383add418  test    rax, rax
0x383add41b  jnz     short loc_383ADD429
0x383add41d  mov     eax, ebx
0x383add41f  sub     eax, esi
0x383add421  cmp     r14d, r13d
0x383add424  jz      short loc_383ADD438
0x383add426  inc     r14d
0x383add429  lea     eax, [rbx+1]
0x383add42c  cmp     [rdi+rax*2], bp
0x383add430  lea     rdi, [rdi+rax*2]
0x383add434  jnz     short loc_383ADD3D1
0x383add436  jmp     short loc_383ADD43F
0x383add438  mov     [rsp+98h+cbData], eax
0x383add43c  mov     r12d, ebp
0x383add43f  mov     rbx, [rsp+98h+lpcSubKeys]
0x383add447  call    cs:__imp_GetProcessHeap
0x383add44d  mov     r8, qword ptr [rsp+98h+cchValueName]; lpMem
0x383add452  xor     edx, edx; dwFlags
0x383add454  mov     rcx, rax; hHeap
0x383add457  call    cs:__imp_HeapFree
0x383add45d  mov     r14d, 8
0x383add463  jmp     short loc_383ADD468
0x383add465  mov     r12d, r14d
0x383add468  call    cs:__imp_GetProcessHeap
0x383add46e  mov     r8, r15; lpMem
0x383add471  xor     edx, edx; dwFlags
0x383add473  mov     rcx, rax; hHeap
0x383add476  call    cs:__imp_HeapFree
0x383add47c  mov     ecx, r12d; dwErrCode
0x383add47f  call    cs:__imp_SetLastError
0x383add485  jmp     short loc_383ADD4AF
0x383add487  mov     [rsp+98h+lpcbData], rbp; lpftLastWriteTime
0x383add48c  mov     [rsp+98h+lpData], rbp; lpcchClass
0x383add491  lea     r9, [rsp+98h+cbData]; lpcchName
0x383add496  xor     r8d, r8d; lpName
0x383add499  mov     edx, r13d; dwIndex
0x383add49c  mov     [rsp+98h+lpType], rbp; lpClass
0x383add4a1  mov     [rsp+98h+lpReserved], rbp; lpReserved
0x383add4a6  call    cs:__imp_RegEnumKeyExW
0x383add4ac  mov     r12d, eax
0x383add4af  test    r12d, r12d
0x383add4b2  jnz     short loc_383ADD4F1
0x383add4b4  test    rbx, rbx
0x383add4b7  jz      short loc_383ADD4BB
0x383add4b9  inc     dword ptr [rbx]
0x383add4bb  mov     rdx, [rsp+98h+lpcbMaxSubKeyLen]
0x383add4c3  test    rdx, rdx
0x383add4c6  jz      short loc_383ADD4D5
0x383add4c8  mov     eax, [rdx]
0x383add4ca  mov     ecx, [rsp+98h+cbData]
0x383add4ce  cmp     eax, ecx
0x383add4d0  cmova   ecx, eax
0x383add4d3  mov     [rdx], ecx
0x383add4d5  mov     r12, [rsp+98h+arg_0]
0x383add4dd  inc     r13d
0x383add4e0  jmp     loc_383ADD370
0x383add4e5  mov     ecx, r14d; dwErrCode
0x383add4e8  call    cs:__imp_SetLastError
0x383add4ee  mov     r12d, r14d
0x383add4f1  mov     r13, [rsp+98h+arg_18]
0x383add4f9  mov     eax, r12d
0x383add4fc  jmp     loc_383ADD1B1
0x383add501  mov     rax, [rsp+98h+arg_58]
0x383add509  mov     [rsp+98h+lpftLastWriteTime], rax; lpftLastWriteTime
0x383add50e  mov     rax, [rsp+98h+arg_50]
0x383add516  mov     [rsp+98h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x383add51b  mov     rax, [rsp+98h+arg_48]
0x383add523  mov     [rsp+98h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x383add528  mov     rax, [rsp+98h+arg_40]
0x383add530  mov     [rsp+98h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x383add535  mov     rax, [rsp+98h+lpcValues]
0x383add53d  mov     [rsp+98h+lpcbData], rax; lpcValues
0x383add542  mov     rax, [rsp+98h+lpcbMaxClassLen]
0x383add54a  mov     [rsp+98h+lpData], rax; lpcbMaxClassLen
0x383add54f  mov     rax, [rsp+98h+lpcbMaxSubKeyLen]
0x383add557  mov     [rsp+98h+lpType], rax; lpcbMaxSubKeyLen
0x383add55c  mov     rax, [rsp+98h+lpcSubKeys]
0x383add564  mov     [rsp+98h+lpReserved], rax; lpcSubKeys
0x383add569  call    cs:__imp_RegQueryInfoKeyW
0x383add56f  add     rsp, 80h
0x383add576  pop     r12
0x383add578  pop     rdi
0x383add579  pop     rbx
0x383add57a  retn
  ... truncated ...
```

# DeleteTaskNotification(ushort const *)

- ea: `0x180001760`
- end: `0x180001af8`
- name: `?DeleteTaskNotification@@YAJPEBG@Z`
- size: `920`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001760`
- `0x180001b00`
- `0x180003320`
- `0x1800040c0`
- `0x180011e6c`
- `0x180011e90`
- `0x1800139fc`
- `0x18002af48`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `msvcrt!wcschr` at `0x1800017aa`
- `msvcrt!wcschr` at `0x180001837`
- `msvcrt!wcschr` at `0x1800017aa`
- `msvcrt!wcschr` at `0x180001837`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800017c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800017c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a72`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180001a61`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180001a61`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=2
__int64 __fastcall DeleteTaskNotification(const unsigned __int16 *a1)
{
  __int64 result; // rax
  const wchar_t *v2; // rdi
  CompatibilityAdapter *v3; // rbx
  unsigned int v4; // edx
  const wchar_t *v5; // rbx
  __int64 v6; // r10
  __int64 v7; // rax
  __int64 v8; // r8
  OLECHAR *p_psz; // r9
  wchar_t v10; // cx
  OLECHAR *v11; // rcx
  __int64 v12; // r8
  OLECHAR *v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // r9
  wchar_t *v16; // rdx
  wchar_t v17; // ax
  wchar_t *v18; // rcx
  OLECHAR *v19; // rbx
  OLECHAR *v20; // rax
  int v21; // edx
  signed int LastError; // eax
  unsigned __int64 v23; // rcx
  int v24; // ecx
  int v25; // edx
  unsigned __int64 v26; // [rsp+30h] [rbp-448h] BYREF
  OLECHAR psz; // [rsp+40h] [rbp-438h] BYREF
  _BYTE v28[526]; // [rsp+42h] [rbp-436h] BYREF
  WCHAR FileName[264]; // [rsp+250h] [rbp-228h] BYREF

  LODWORD(v26) = 0;
  if ( !a1 )
    return 0;
  v2 = a1 + 1;
  if ( *a1 != 92 )
    v2 = a1;
  if ( wcschr(v2, 0x5Cu) )
    return 0;
  EnterCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  v3 = CompatibilityAdapter::g_pAdapter;
  LeaveCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  if ( !v3 )
    return 2147549183LL;
  memset_0(&psz, 0, 0x20Au);
  if ( !v2 )
  {
    v4 = -2147024809;
    LODWORD(v26) = -2147024809;
    return v4;
  }
  v5 = v2 + 1;
  if ( *v2 != 92 )
    v5 = v2;
  if ( wcschr(v5, 0x5Cu) )
  {
    v4 = -2147024809;
    LODWORD(v26) = -2147024809;
    return v4;
  }
  v6 = 2147483646;
  v7 = 2147483646;
  v8 = 261;
  p_psz = &psz;
  do
  {
    if ( !v7 )
      break;
    v10 = *v5;
    if ( !*v5 )
      break;
    ++v5;
    *p_psz++ = v10;
    --v7;
    --v8;
  }
  while ( v8 );
  v4 = -2147024774;
  if ( v8 )
    v4 = 0;
  v11 = p_psz - 1;
  if ( v8 )
    v11 = p_psz;
  *v11 = 0;
  if ( !v8 )
  {
    LODWORD(v26) = v4;
    return v4;
  }
  v12 = 261;
  v13 = &psz;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v4 = -2147024809;
  if ( v12 )
    v4 = 0;
  v14 = 261 - v12;
  if ( v12 )
  {
    v15 = L".job";
    v16 = (wchar_t *)&v28[2 * v14 - 2];
    if ( v14 != 261 )
    {
      do
      {
        if ( !v6 )
          break;
        v17 = *v15;
        if ( !*v15 )
          break;
        ++v15;
        *v16++ = v17;
        --v6;
        --v12;
      }
      while ( v12 );
    }
    v18 = v16 - 1;
    if ( v12 )
      v18 = v16;
    *v18 = 0;
    v4 = -2147024774;
    if ( v12 )
      v4 = 0;
  }
  LODWORD(v26) = v4;
  if ( (v4 & 0x80000000) != 0 )
    return v4;
  memset_0(FileName, 0, 0x20Au);
  if ( !g_TasksFolderInfo
    || *g_TasksFolderInfo
    && FileName != g_TasksFolderInfo
    && (int)StringCchCopyW(FileName, 0x105u, (unsigned __int16 *)g_TasksFolderInfo) < 0 )
  {
    goto LABEL_50;
  }
  if ( !psz )
    goto LABEL_55;
  v26 = 0;
  if ( (int)StringCchLengthW(FileName, 0x105u, &v26) >= 0 )
  {
    v19 = &psz;
    if ( *(_WORD *)&v28[2 * v26 + 524] == 92 )
    {
      v20 = (OLECHAR *)v28;
      if ( psz != 92 )
        v20 = &psz;
      v19 = v20;
    }
    else if ( psz != 92 && (int)StringCchCatW(FileName, 0x105u, L"\\") < 0 )
    {
      goto LABEL_50;
    }
    if ( (int)StringCchCatW(FileName, 0x105u, v19) >= 0 )
    {
LABEL_55:
      LODWORD(v26) = 0;
      result = SignatureStore::Delete(&psz);
      LODWORD(v26) = result;
      if ( (int)result < 0 )
        return result;
      if ( DeletionGuard::IsGuarded(v2) )
      {
        if ( GetFileAttributesW(FileName) == -1 )
        {
          LastError = GetLastError();
          v23 = (unsigned int)LastError;
          if ( LastError > 0 )
            v23 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v23 = 0;
        }
        LODWORD(v26) = v23;
        if ( !tsched::IsErrorNotFound((tsched *)v23, v21) )
        {
          if ( v24 >= 0 )
            LODWORD(v26) = -2147024864;
          return (unsigned int)v26;
        }
      }
      else
      {
        LODWORD(v26) = DeleteFileWithRetry(FileName);
        if ( !tsched::IsErrorNotFound((tsched *)(unsigned int)v26, v25) )
          return (unsigned int)v26;
      }
      LODWORD(v26) = 0;
      return (unsigned int)v26;
    }
  }
LABEL_50:
  LODWORD(v26) = -2147024809;
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180001760  mov     [rsp+arg_8], rbx
0x180001765  mov     [rsp+arg_10], rsi
0x18000176a  push    rdi
0x18000176b  sub     rsp, 470h
0x180001772  mov     rax, cs:__security_cookie
0x180001779  xor     rax, rsp
0x18000177c  mov     [rsp+478h+var_18], rax
0x180001784  xor     esi, esi
0x180001786  mov     dword ptr [rsp+478h+var_448], esi
0x18000178a  test    rcx, rcx
0x18000178d  jnz     short loc_180001796
0x18000178f  xor     eax, eax
0x180001791  jmp     loc_180001AD2
0x180001796  lea     rdi, [rcx+2]
0x18000179a  cmp     word ptr [rcx], 5Ch ; '\'
0x18000179e  cmovnz  rdi, rcx
0x1800017a2  mov     edx, 5Ch ; '\'; Ch
0x1800017a7  mov     rcx, rdi; Str
0x1800017aa  call    cs:__imp_wcschr
0x1800017b1  nop     dword ptr [rax+rax+00h]
0x1800017b6  test    rax, rax
0x1800017b9  jz      short loc_1800017C2
0x1800017bb  xor     eax, eax
0x1800017bd  jmp     loc_180001AD2
0x1800017c2  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800017c9  call    cs:__imp_EnterCriticalSection
0x1800017d0  nop     dword ptr [rax+rax+00h]
0x1800017d5  mov     rbx, cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x1800017dc  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800017e3  call    cs:__imp_LeaveCriticalSection
0x1800017ea  nop     dword ptr [rax+rax+00h]
0x1800017ef  test    rbx, rbx
0x1800017f2  jnz     short loc_1800017FE
0x1800017f4  mov     eax, 8000FFFFh
0x1800017f9  jmp     loc_180001AD2
0x1800017fe  xor     edx, edx; Val
0x180001800  mov     r8d, 20Ah; Size
0x180001806  lea     rcx, [rsp+478h+psz]; void *
0x18000180b  call    memset_0
0x180001810  test    rdi, rdi
0x180001813  jnz     short loc_180001823
0x180001815  mov     edx, 80070057h
0x18000181a  mov     dword ptr [rsp+478h+var_448], edx
0x18000181e  jmp     loc_18000193F
0x180001823  lea     rbx, [rdi+2]
0x180001827  cmp     word ptr [rdi], 5Ch ; '\'
0x18000182b  cmovnz  rbx, rdi
0x18000182f  mov     edx, 5Ch ; '\'; Ch
0x180001834  mov     rcx, rbx; Str
0x180001837  call    cs:__imp_wcschr
0x18000183e  nop     dword ptr [rax+rax+00h]
0x180001843  test    rax, rax
0x180001846  jz      short loc_180001856
0x180001848  mov     edx, 80070057h
0x18000184d  mov     dword ptr [rsp+478h+var_448], edx
0x180001851  jmp     loc_18000193F
0x180001856  mov     r10d, 7FFFFFFEh
0x18000185c  mov     eax, r10d
0x18000185f  mov     r8d, 105h
0x180001865  lea     r9, [rsp+478h+psz]
0x18000186a  test    rax, rax
0x18000186d  jz      short loc_18000188C
0x18000186f  movzx   ecx, word ptr [rbx]
0x180001872  test    cx, cx
0x180001875  jz      short loc_18000188C
0x180001877  add     rbx, 2
0x18000187b  mov     [r9], cx
0x18000187f  add     r9, 2
0x180001883  dec     rax
0x180001886  sub     r8, 1
0x18000188a  jnz     short loc_18000186A
0x18000188c  mov     edx, 8007007Ah
0x180001891  test    r8, r8
0x180001894  cmovnz  edx, esi
0x180001897  lea     rcx, [r9-2]
0x18000189b  cmovnz  rcx, r9
0x18000189f  mov     [rcx], si
0x1800018a2  jnz     short loc_1800018AD
0x1800018a4  mov     dword ptr [rsp+478h+var_448], edx
0x1800018a8  jmp     loc_18000193F
0x1800018ad  mov     r8d, 105h
0x1800018b3  lea     rax, [rsp+478h+psz]
0x1800018b8  cmp     word ptr [rax], 0
0x1800018bc  jz      short loc_1800018C8
0x1800018be  add     rax, 2
0x1800018c2  sub     r8, 1
0x1800018c6  jnz     short loc_1800018B8
0x1800018c8  mov     edx, 80070057h
0x1800018cd  test    r8, r8
0x1800018d0  cmovnz  edx, esi
0x1800018d3  mov     ecx, 105h
0x1800018d8  sub     rcx, r8
0x1800018db  test    r8, r8
0x1800018de  cmovz   rcx, rsi
0x1800018e2  jz      short loc_180001937
0x1800018e4  lea     r9, aJob; ".job"
0x1800018eb  mov     r8d, 105h
0x1800018f1  sub     r8, rcx
0x1800018f4  lea     rdx, [rsp+478h+psz]
0x1800018f9  lea     rdx, [rdx+rcx*2]
0x1800018fd  jz      short loc_180001921
0x1800018ff  test    r10, r10
0x180001902  jz      short loc_180001921
0x180001904  movzx   eax, word ptr [r9]
0x180001908  test    ax, ax
0x18000190b  jz      short loc_180001921
0x18000190d  add     r9, 2
0x180001911  mov     [rdx], ax
0x180001914  add     rdx, 2
0x180001918  dec     r10
0x18000191b  sub     r8, 1
0x18000191f  jnz     short loc_1800018FF
0x180001921  lea     rcx, [rdx-2]
0x180001925  test    r8, r8
0x180001928  cmovnz  rcx, rdx
0x18000192c  mov     [rcx], si
0x18000192f  mov     edx, 8007007Ah
0x180001934  cmovnz  edx, esi
0x180001937  mov     dword ptr [rsp+478h+var_448], edx
0x18000193b  test    edx, edx
0x18000193d  jns     short loc_180001946
0x18000193f  mov     eax, edx
0x180001941  jmp     loc_180001AD2
0x180001946  xor     edx, edx; Val
0x180001948  mov     r8d, 20Ah; Size
0x18000194e  lea     rcx, [rsp+478h+FileName]; void *
0x180001956  call    memset_0
0x18000195b  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180001962  test    r8, r8
0x180001965  jz      loc_1800019FB
0x18000196b  cmp     word ptr [r8], 0
0x180001970  jz      short loc_180001995
0x180001972  lea     rax, [rsp+478h+FileName]
0x18000197a  cmp     rax, r8
0x18000197d  jz      short loc_180001995
0x18000197f  mov     edx, 105h; unsigned __int64
0x180001984  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x18000198c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001991  test    eax, eax
0x180001993  js      short loc_1800019FB
0x180001995  cmp     [rsp+478h+psz], 0
0x18000199b  jz      loc_180001A33
0x1800019a1  mov     [rsp+478h+var_448], rsi
0x1800019a6  lea     r8, [rsp+478h+var_448]; unsigned __int64 *
0x1800019ab  mov     edx, 105h; unsigned __int64
0x1800019b0  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x1800019b8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800019bd  test    eax, eax
0x1800019bf  js      short loc_1800019FB
0x1800019c1  lea     rbx, [rsp+478h+psz]
0x1800019c6  mov     rax, [rsp+478h+var_448]
0x1800019cb  cmp     [rsp+rax*2+478h+var_22A], 5Ch ; '\'
0x1800019d4  jz      short loc_180001A08
0x1800019d6  cmp     [rsp+478h+psz], 5Ch ; '\'
0x1800019dc  jz      short loc_180001A1A
0x1800019de  lea     r8, asc_1800516CC; "\\"
0x1800019e5  mov     edx, 105h; unsigned __int64
0x1800019ea  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x1800019f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800019f7  test    eax, eax
0x1800019f9  jns     short loc_180001A1A
0x1800019fb  mov     dword ptr [rsp+478h+var_448], 80070057h
0x180001a03  jmp     loc_180001ACE
0x180001a08  lea     rax, [rsp+478h+var_436]
0x180001a0d  cmp     [rsp+478h+psz], 5Ch ; '\'
0x180001a13  cmovnz  rax, rbx
0x180001a17  mov     rbx, rax
0x180001a1a  mov     r8, rbx; unsigned __int16 *
0x180001a1d  mov     edx, 105h; unsigned __int64
0x180001a22  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x180001a2a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180001a2f  test    eax, eax
0x180001a31  js      short loc_1800019FB
0x180001a33  mov     dword ptr [rsp+478h+var_448], esi
0x180001a37  lea     rcx, [rsp+478h+psz]; psz
0x180001a3c  call    ?Delete@SignatureStore@@SAJPEBG@Z; SignatureStore::Delete(ushort const *)
0x180001a41  mov     dword ptr [rsp+478h+var_448], eax
0x180001a45  test    eax, eax
0x180001a47  js      loc_180001AD2
0x180001a4d  mov     rcx, rdi; unsigned __int16 *
0x180001a50  call    ?IsGuarded@DeletionGuard@@SA_NPEBG@Z; DeletionGuard::IsGuarded(ushort const *)
0x180001a55  lea     rcx, [rsp+478h+FileName]; lpFileName
0x180001a5d  test    al, al
0x180001a5f  jz      short loc_180001AAC
0x180001a61  call    cs:__imp_GetFileAttributesW
0x180001a68  nop     dword ptr [rax+rax+00h]
0x180001a6d  cmp     eax, 0FFFFFFFFh
0x180001a70  jnz     short loc_180001A8F
0x180001a72  call    cs:__imp_GetLastError
0x180001a79  nop     dword ptr [rax+rax+00h]
0x180001a7e  mov     ecx, eax
0x180001a80  test    eax, eax
0x180001a82  jle     short loc_180001A91
0x180001a84  movzx   ecx, ax
0x180001a87  or      ecx, 80070000h
0x180001a8d  jmp     short loc_180001A91
0x180001a8f  mov     ecx, esi; this
0x180001a91  mov     dword ptr [rsp+478h+var_448], ecx
0x180001a95  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180001a9a  test    al, al
0x180001a9c  jnz     short loc_180001AC0
0x180001a9e  test    ecx, ecx
0x180001aa0  js      short loc_180001AC4
0x180001aa2  mov     dword ptr [rsp+478h+var_448], 80070020h
0x180001aaa  jmp     short loc_180001AC4
0x180001aac  call    ?DeleteFileWithRetry@@YAJPEBG@Z; DeleteFileWithRetry(ushort const *)
0x180001ab1  mov     dword ptr [rsp+478h+var_448], eax
0x180001ab5  mov     ecx, eax; this
0x180001ab7  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180001abc  test    al, al
0x180001abe  jz      short loc_180001AC4
0x180001ac0  mov     dword ptr [rsp+478h+var_448], esi
0x180001ac4  jmp     loc_180001A03
0x180001ac9  jmp     loc_180001A03
0x180001ace  mov     eax, dword ptr [rsp+478h+var_448]
0x180001ad2  mov     rcx, [rsp+478h+var_18]
0x180001ada  xor     rcx, rsp; StackCookie
0x180001add  call    __security_check_cookie
0x180001ae2  lea     r11, [rsp+478h+var_8]
0x180001aea  mov     rbx, [r11+18h]
0x180001aee  mov     rsi, [r11+20h]
0x180001af2  mov     rsp, r11
0x180001af5  pop     rdi
0x180001af6  retn
```

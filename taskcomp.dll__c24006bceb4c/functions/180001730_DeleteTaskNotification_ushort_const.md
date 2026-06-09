# DeleteTaskNotification(ushort const *)

- ea: `0x180001730`
- end: `0x180001aa0`
- name: `?DeleteTaskNotification@@YAJPEBG@Z`
- size: `880`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001730`
- `0x180001ab0`
- `0x1800031a0`
- `0x180003ef0`
- `0x1800113cc`
- `0x1800113f0`
- `0x180012e24`
- `0x18002957c`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!wcschr` at `0x18000177a`
- `msvcrt!wcschr` at `0x1800017f5`
- `msvcrt!wcschr` at `0x18000177a`
- `msvcrt!wcschr` at `0x1800017f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001793`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180001a15`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180001a15`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
    && (int)StringCchCopyW(FileName, 0x105u, g_TasksFolderInfo) < 0 )
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
0x180001730  mov     [rsp+arg_8], rbx
0x180001735  mov     [rsp+arg_10], rsi
0x18000173a  push    rdi
0x18000173b  sub     rsp, 470h
0x180001742  mov     rax, cs:__security_cookie
0x180001749  xor     rax, rsp
0x18000174c  mov     [rsp+478h+var_18], rax
0x180001754  xor     esi, esi
0x180001756  mov     dword ptr [rsp+478h+var_448], esi
0x18000175a  test    rcx, rcx
0x18000175d  jnz     short loc_180001766
0x18000175f  xor     eax, eax
0x180001761  jmp     loc_180001A7A
0x180001766  lea     rdi, [rcx+2]
0x18000176a  cmp     word ptr [rcx], 5Ch ; '\'
0x18000176e  cmovnz  rdi, rcx
0x180001772  mov     edx, 5Ch ; '\'; Ch
0x180001777  mov     rcx, rdi; Str
0x18000177a  call    cs:__imp_wcschr
0x180001780  test    rax, rax
0x180001783  jz      short loc_18000178C
0x180001785  xor     eax, eax
0x180001787  jmp     loc_180001A7A
0x18000178c  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001793  call    cs:__imp_EnterCriticalSection
0x180001799  mov     rbx, cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x1800017a0  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800017a7  call    cs:__imp_LeaveCriticalSection
0x1800017ad  test    rbx, rbx
0x1800017b0  jnz     short loc_1800017BC
0x1800017b2  mov     eax, 8000FFFFh
0x1800017b7  jmp     loc_180001A7A
0x1800017bc  xor     edx, edx; Val
0x1800017be  mov     r8d, 20Ah; Size
0x1800017c4  lea     rcx, [rsp+478h+psz]; void *
0x1800017c9  call    memset_0
0x1800017ce  test    rdi, rdi
0x1800017d1  jnz     short loc_1800017E1
0x1800017d3  mov     edx, 80070057h
0x1800017d8  mov     dword ptr [rsp+478h+var_448], edx
0x1800017dc  jmp     loc_1800018F7
0x1800017e1  lea     rbx, [rdi+2]
0x1800017e5  cmp     word ptr [rdi], 5Ch ; '\'
0x1800017e9  cmovnz  rbx, rdi
0x1800017ed  mov     edx, 5Ch ; '\'; Ch
0x1800017f2  mov     rcx, rbx; Str
0x1800017f5  call    cs:__imp_wcschr
0x1800017fb  test    rax, rax
0x1800017fe  jz      short loc_18000180E
0x180001800  mov     edx, 80070057h
0x180001805  mov     dword ptr [rsp+478h+var_448], edx
0x180001809  jmp     loc_1800018F7
0x18000180e  mov     r10d, 7FFFFFFEh
0x180001814  mov     eax, r10d
0x180001817  mov     r8d, 105h
0x18000181d  lea     r9, [rsp+478h+psz]
0x180001822  test    rax, rax
0x180001825  jz      short loc_180001844
0x180001827  movzx   ecx, word ptr [rbx]
0x18000182a  test    cx, cx
0x18000182d  jz      short loc_180001844
0x18000182f  add     rbx, 2
0x180001833  mov     [r9], cx
0x180001837  add     r9, 2
0x18000183b  dec     rax
0x18000183e  sub     r8, 1
0x180001842  jnz     short loc_180001822
0x180001844  mov     edx, 8007007Ah
0x180001849  test    r8, r8
0x18000184c  cmovnz  edx, esi
0x18000184f  lea     rcx, [r9-2]
0x180001853  cmovnz  rcx, r9
0x180001857  mov     [rcx], si
0x18000185a  jnz     short loc_180001865
0x18000185c  mov     dword ptr [rsp+478h+var_448], edx
0x180001860  jmp     loc_1800018F7
0x180001865  mov     r8d, 105h
0x18000186b  lea     rax, [rsp+478h+psz]
0x180001870  cmp     word ptr [rax], 0
0x180001874  jz      short loc_180001880
0x180001876  add     rax, 2
0x18000187a  sub     r8, 1
0x18000187e  jnz     short loc_180001870
0x180001880  mov     edx, 80070057h
0x180001885  test    r8, r8
0x180001888  cmovnz  edx, esi
0x18000188b  mov     ecx, 105h
0x180001890  sub     rcx, r8
0x180001893  test    r8, r8
0x180001896  cmovz   rcx, rsi
0x18000189a  jz      short loc_1800018EF
0x18000189c  lea     r9, aJob; ".job"
0x1800018a3  mov     r8d, 105h
0x1800018a9  sub     r8, rcx
0x1800018ac  lea     rdx, [rsp+478h+psz]
0x1800018b1  lea     rdx, [rdx+rcx*2]
0x1800018b5  jz      short loc_1800018D9
0x1800018b7  test    r10, r10
0x1800018ba  jz      short loc_1800018D9
0x1800018bc  movzx   eax, word ptr [r9]
0x1800018c0  test    ax, ax
0x1800018c3  jz      short loc_1800018D9
0x1800018c5  add     r9, 2
0x1800018c9  mov     [rdx], ax
0x1800018cc  add     rdx, 2
0x1800018d0  dec     r10
0x1800018d3  sub     r8, 1
0x1800018d7  jnz     short loc_1800018B7
0x1800018d9  lea     rcx, [rdx-2]
0x1800018dd  test    r8, r8
0x1800018e0  cmovnz  rcx, rdx
0x1800018e4  mov     [rcx], si
0x1800018e7  mov     edx, 8007007Ah
0x1800018ec  cmovnz  edx, esi
0x1800018ef  mov     dword ptr [rsp+478h+var_448], edx
0x1800018f3  test    edx, edx
0x1800018f5  jns     short loc_1800018FE
0x1800018f7  mov     eax, edx
0x1800018f9  jmp     loc_180001A7A
0x1800018fe  xor     edx, edx; Val
0x180001900  mov     r8d, 20Ah; Size
0x180001906  lea     rcx, [rsp+478h+FileName]; void *
0x18000190e  call    memset_0
0x180001913  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x18000191a  test    r8, r8
0x18000191d  jz      loc_1800019B3
0x180001923  cmp     word ptr [r8], 0
0x180001928  jz      short loc_18000194D
0x18000192a  lea     rax, [rsp+478h+FileName]
0x180001932  cmp     rax, r8
0x180001935  jz      short loc_18000194D
0x180001937  mov     edx, 105h; unsigned __int64
0x18000193c  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x180001944  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001949  test    eax, eax
0x18000194b  js      short loc_1800019B3
0x18000194d  cmp     [rsp+478h+psz], 0
0x180001953  jz      loc_1800019EB
0x180001959  mov     [rsp+478h+var_448], rsi
0x18000195e  lea     r8, [rsp+478h+var_448]; unsigned __int64 *
0x180001963  mov     edx, 105h; unsigned __int64
0x180001968  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x180001970  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180001975  test    eax, eax
0x180001977  js      short loc_1800019B3
0x180001979  lea     rbx, [rsp+478h+psz]
0x18000197e  mov     rax, [rsp+478h+var_448]
0x180001983  cmp     [rsp+rax*2+478h+var_22A], 5Ch ; '\'
0x18000198c  jz      short loc_1800019C0
0x18000198e  cmp     [rsp+478h+psz], 5Ch ; '\'
0x180001994  jz      short loc_1800019D2
0x180001996  lea     r8, asc_18004F6BC; "\\"
0x18000199d  mov     edx, 105h; unsigned __int64
0x1800019a2  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x1800019aa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800019af  test    eax, eax
0x1800019b1  jns     short loc_1800019D2
0x1800019b3  mov     dword ptr [rsp+478h+var_448], 80070057h
0x1800019bb  jmp     loc_180001A76
0x1800019c0  lea     rax, [rsp+478h+var_436]
0x1800019c5  cmp     [rsp+478h+psz], 5Ch ; '\'
0x1800019cb  cmovnz  rax, rbx
0x1800019cf  mov     rbx, rax
0x1800019d2  mov     r8, rbx; unsigned __int16 *
0x1800019d5  mov     edx, 105h; unsigned __int64
0x1800019da  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x1800019e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800019e7  test    eax, eax
0x1800019e9  js      short loc_1800019B3
0x1800019eb  mov     dword ptr [rsp+478h+var_448], esi
0x1800019ef  lea     rcx, [rsp+478h+psz]; psz
0x1800019f4  call    ?Delete@SignatureStore@@SAJPEBG@Z; SignatureStore::Delete(ushort const *)
0x1800019f9  mov     dword ptr [rsp+478h+var_448], eax
0x1800019fd  test    eax, eax
0x1800019ff  js      short loc_180001A7A
0x180001a01  mov     rcx, rdi; unsigned __int16 *
0x180001a04  call    ?IsGuarded@DeletionGuard@@SA_NPEBG@Z; DeletionGuard::IsGuarded(ushort const *)
0x180001a09  lea     rcx, [rsp+478h+FileName]; lpFileName
0x180001a11  test    al, al
0x180001a13  jz      short loc_180001A54
0x180001a15  call    cs:__imp_GetFileAttributesW
0x180001a1b  cmp     eax, 0FFFFFFFFh
0x180001a1e  jnz     short loc_180001A37
0x180001a20  call    cs:__imp_GetLastError
0x180001a26  mov     ecx, eax
0x180001a28  test    eax, eax
0x180001a2a  jle     short loc_180001A39
0x180001a2c  movzx   ecx, ax
0x180001a2f  or      ecx, 80070000h
0x180001a35  jmp     short loc_180001A39
0x180001a37  mov     ecx, esi; this
0x180001a39  mov     dword ptr [rsp+478h+var_448], ecx
0x180001a3d  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180001a42  test    al, al
0x180001a44  jnz     short loc_180001A68
0x180001a46  test    ecx, ecx
0x180001a48  js      short loc_180001A6C
0x180001a4a  mov     dword ptr [rsp+478h+var_448], 80070020h
0x180001a52  jmp     short loc_180001A6C
0x180001a54  call    ?DeleteFileWithRetry@@YAJPEBG@Z; DeleteFileWithRetry(ushort const *)
0x180001a59  mov     dword ptr [rsp+478h+var_448], eax
0x180001a5d  mov     ecx, eax; this
0x180001a5f  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180001a64  test    al, al
0x180001a66  jz      short loc_180001A6C
0x180001a68  mov     dword ptr [rsp+478h+var_448], esi
0x180001a6c  jmp     loc_1800019BB
0x180001a71  jmp     loc_1800019BB
0x180001a76  mov     eax, dword ptr [rsp+478h+var_448]
0x180001a7a  mov     rcx, [rsp+478h+var_18]
0x180001a82  xor     rcx, rsp; StackCookie
0x180001a85  call    __security_check_cookie
0x180001a8a  lea     r11, [rsp+478h+var_8]
0x180001a92  mov     rbx, [r11+18h]
0x180001a96  mov     rsi, [r11+20h]
0x180001a9a  mov     rsp, r11
0x180001a9d  pop     rdi
0x180001a9e  retn
```

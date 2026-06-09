# QMRUtil::CreateSecuredClientCacheKey(_GUID const &,HKEY__ * *)

- ea: `0x1801204c0`
- end: `0x1801206e5`
- name: `?CreateSecuredClientCacheKey@QMRUtil@@YAJAEBU_GUID@@PEAPEAUHKEY__@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(const struct _GUID *this, const struct _GUID *, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800de5ac`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x1800549f4`
- `0x180113ae8`
- `0x1801204c0`
- `0x180131d70`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180120575`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180120575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120562`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180120655`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180120655`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120695`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120695`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180120631`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180120631`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180120543`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180120543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012056d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801206b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012056d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801206b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QMRUtil::CreateSecuredClientCacheKey(const struct _GUID *this, const struct _GUID *a2, HKEY *a3)
{
  const char *v6; // r9
  BOOL v7; // r12d
  PSECURITY_DESCRIPTOR v8; // r15
  PSECURITY_DESCRIPTOR v9; // r14
  DWORD LastError; // ebx
  unsigned int v11; // edi
  int ClientCacheRegPath; // eax
  WCHAR *v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // rdx
  HKEY v16; // rcx
  HKEY v17; // rax
  DWORD dwOptions; // [rsp+20h] [rbp-69h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-69h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR *p_pSecurityDescriptor; // [rsp+58h] [rbp-31h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-29h] BYREF
  char v23; // [rsp+68h] [rbp-21h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-1h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\QMRUtil.cpp",
      (const char *)0x80004003LL,
      dwOptions);
    return 2147500035LL;
  }
  *(_QWORD *)&a2->Data1 = 0;
  pSecurityDescriptor = 0;
  p_pSecurityDescriptor = &pSecurityDescriptor;
  SecurityDescriptor = 0;
  v23 = 1;
  v7 = ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)(A;;GR;;;BA)", 1u, &SecurityDescriptor, 0);
  if ( v23 )
  {
    v8 = SecurityDescriptor;
    v9 = *p_pSecurityDescriptor;
    if ( *p_pSecurityDescriptor )
    {
      LastError = GetLastError();
      LocalFree(v9);
      SetLastError(LastError);
    }
    *p_pSecurityDescriptor = v8;
  }
  if ( v7 )
  {
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
    lpSubKey = 0;
    ClientCacheRegPath = GetClientCacheRegPath(this, (wchar_t **)&lpSubKey);
    v11 = ClientCacheRegPath;
    v13 = (WCHAR *)lpSubKey;
    if ( ClientCacheRegPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\QMRUtil.cpp",
        (const char *)(unsigned int)ClientCacheRegPath,
        dwOptions);
LABEL_20:
      if ( v13 )
        SusFree(v13);
      goto LABEL_22;
    }
    hKey = 0;
    dwDisposition = 0;
    v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x60006u, &SecurityAttributes, &hKey, &dwDisposition);
    if ( v14 )
    {
      v15 = 141;
    }
    else
    {
      if ( dwDisposition != 2 || (v14 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor)) == 0 )
      {
        v17 = hKey;
        v16 = 0;
        hKey = 0;
        *(_QWORD *)&a2->Data1 = v17;
        v11 = 0;
LABEL_18:
        if ( v16 )
        {
          RegCloseKey(v16);
          hKey = 0;
        }
        goto LABEL_20;
      }
      v15 = 147;
    }
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v15,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\QMRUtil.cpp",
            (const char *)v14,
            dwOptionsa);
    v16 = hKey;
    goto LABEL_18;
  }
  v11 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x77,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\QMRUtil.cpp",
          v6);
LABEL_22:
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  return v11;
}

```

## disassembly

```asm
0x1801204c0  mov     [rsp-8+arg_10], rbx
0x1801204c5  push    rbp
0x1801204c6  push    rsi
0x1801204c7  push    rdi
0x1801204c8  push    r12
0x1801204ca  push    r13
0x1801204cc  push    r14
0x1801204ce  push    r15
0x1801204d0  lea     rbp, [rsp-27h]
0x1801204d5  sub     rsp, 0B0h
0x1801204dc  mov     rax, cs:__security_cookie
0x1801204e3  xor     rax, rsp
0x1801204e6  mov     [rbp+57h+var_40], rax
0x1801204ea  mov     rsi, rdx
0x1801204ed  mov     r13, rcx
0x1801204f0  xor     r14d, r14d
0x1801204f3  test    rdx, rdx
0x1801204f6  jnz     short loc_18012051A
0x1801204f8  mov     rcx, [rbp+5Fh]; this
0x1801204fc  mov     ebx, 80004003h
0x180120501  mov     r9d, ebx; char *
0x180120504  lea     r8, aCW1SSrcClientL_43; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18012050b  lea     edx, [rsi+67h]; void *
0x18012050e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180120513  mov     eax, ebx
0x180120515  jmp     loc_1801206BE
0x18012051a  mov     [rdx], r14
0x18012051d  mov     [rbp+57h+pSecurityDescriptor], r14
0x180120521  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180120525  mov     [rbp+57h+var_88], rax
0x180120529  mov     [rbp+57h+SecurityDescriptor], r14
0x18012052d  mov     [rbp+57h+var_78], 1
0x180120531  xor     r9d, r9d; SecurityDescriptorSize
0x180120534  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180120538  lea     edx, [r9+1]; StringSDRevision
0x18012053c  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;GR;;;BA)"
0x180120543  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180120549  mov     r12d, eax
0x18012054c  cmp     [rbp+57h+var_78], r14b
0x180120550  jz      short loc_180120581
0x180120552  mov     r15, [rbp+57h+SecurityDescriptor]
0x180120556  mov     rdi, [rbp+57h+var_88]
0x18012055a  mov     r14, [rdi]
0x18012055d  test    r14, r14
0x180120560  jz      short loc_18012057B
0x180120562  call    cs:__imp_GetLastError
0x180120568  mov     ebx, eax
0x18012056a  mov     rcx, r14; hMem
0x18012056d  call    cs:__imp_LocalFree
0x180120573  mov     ecx, ebx; dwErrCode
0x180120575  call    cs:__imp_SetLastError
0x18012057b  mov     [rdi], r15
0x18012057e  xor     r14d, r14d
0x180120581  test    r12d, r12d
0x180120584  jnz     short loc_1801205A2
0x180120586  mov     rcx, [rbp+5Fh]; this
0x18012058a  lea     r8, aCW1SSrcClientL_43; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180120591  lea     edx, [r12+77h]; void *
0x180120596  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012059b  mov     edi, eax
0x18012059d  jmp     loc_1801206AD
0x1801205a2  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1801205aa  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x1801205b2  mov     rax, [rbp+57h+pSecurityDescriptor]
0x1801205b6  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1801205ba  mov     [rbp+57h+lpSubKey], r14
0x1801205be  lea     rdx, [rbp+57h+lpSubKey]; wchar_t **
0x1801205c2  mov     rcx, r13; struct _GUID *
0x1801205c5  call    ?GetClientCacheRegPath@@YAJAEBU_GUID@@PEAPEA_W@Z; GetClientCacheRegPath(_GUID const &,wchar_t * *)
0x1801205ca  mov     edi, eax
0x1801205cc  mov     rbx, [rbp+57h+lpSubKey]
0x1801205d0  test    eax, eax
0x1801205d2  jns     short loc_1801205F1
0x1801205d4  mov     rcx, [rbp+5Fh]; this
0x1801205d8  mov     r9d, eax; char *
0x1801205db  lea     r8, aCW1SSrcClientL_43; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801205e2  mov     edx, 80h; void *
0x1801205e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801205ec  jmp     loc_18012069F
0x1801205f1  mov     [rbp+57h+hKey], r14
0x1801205f5  mov     [rbp+57h+dwDisposition], r14d
0x1801205f9  lea     rax, [rbp+57h+dwDisposition]
0x1801205fd  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x180120602  lea     rax, [rbp+57h+hKey]
0x180120606  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18012060b  lea     rax, [rbp+57h+SecurityAttributes]
0x18012060f  mov     [rsp+0E0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180120614  mov     [rsp+0E0h+samDesired], 60006h; samDesired
0x18012061c  mov     [rsp+0E0h+dwOptions], r14d; unsigned int
0x180120621  xor     r9d, r9d; lpClass
0x180120624  xor     r8d, r8d; Reserved
0x180120627  mov     rdx, rbx; lpSubKey
0x18012062a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180120631  call    cs:__imp_RegCreateKeyExW
0x180120637  test    eax, eax
0x180120639  jz      short loc_180120642
0x18012063b  mov     edx, 8Dh
0x180120640  jmp     short loc_180120664
0x180120642  cmp     [rbp+57h+dwDisposition], 2
0x180120646  jnz     short loc_18012067F
0x180120648  mov     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18012064c  mov     edx, 4; SecurityInformation
0x180120651  mov     rcx, [rbp+57h+hKey]; hKey
0x180120655  call    cs:__imp_RegSetKeySecurity
0x18012065b  test    eax, eax
0x18012065d  jz      short loc_18012067F
0x18012065f  mov     edx, 93h; void *
0x180120664  mov     rcx, [rbp+5Fh]; this
0x180120668  mov     r9d, eax; char *
0x18012066b  lea     r8, aCW1SSrcClientL_43; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180120672  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180120677  mov     edi, eax
0x180120679  mov     rcx, [rbp+57h+hKey]
0x18012067d  jmp     short loc_180120690
0x18012067f  mov     rax, [rbp+57h+hKey]
0x180120683  mov     rcx, r14; hKey
0x180120686  mov     [rbp+57h+hKey], rcx
0x18012068a  mov     [rsi], rax
0x18012068d  mov     edi, r14d
0x180120690  test    rcx, rcx
0x180120693  jz      short loc_18012069F
0x180120695  call    cs:__imp_RegCloseKey
0x18012069b  mov     [rbp+57h+hKey], r14
0x18012069f  test    rbx, rbx
0x1801206a2  jz      short loc_1801206AD
0x1801206a4  mov     rcx, rbx; lpMem
0x1801206a7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801206ac  nop
0x1801206ad  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x1801206b1  test    rcx, rcx
0x1801206b4  jz      short loc_1801206BC
0x1801206b6  call    cs:__imp_LocalFree
0x1801206bc  mov     eax, edi
0x1801206be  mov     rcx, [rbp+57h+var_40]
0x1801206c2  xor     rcx, rsp; StackCookie
0x1801206c5  call    __security_check_cookie
0x1801206ca  mov     rbx, [rsp+0E0h+arg_10]
0x1801206d2  add     rsp, 0B0h
0x1801206d9  pop     r15
0x1801206db  pop     r14
0x1801206dd  pop     r13
0x1801206df  pop     r12
0x1801206e1  pop     rdi
0x1801206e2  pop     rsi
0x1801206e3  pop     rbp
0x1801206e4  retn
```

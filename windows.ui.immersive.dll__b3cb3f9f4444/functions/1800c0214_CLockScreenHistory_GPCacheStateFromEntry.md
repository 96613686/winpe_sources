# CLockScreenHistory::_GPCacheStateFromEntry

- ea: `0x1800c0214`
- end: `0x1800c03c0`
- name: `CLockScreenHistory::_GPCacheStateFromEntry`
- size: `428`
- prototype: `__int64 __fastcall(CLockScreenHistory *this, CLockScreenHistory::CLockScreenHistoryEntry *, LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c0768`

## callees

- `0x18000af00`
- `0x1800162f0`
- `0x18002fdac`
- `0x18004ca2c`
- `0x180054130`
- `0x1800bad94`
- `0x1800c0214`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c0354`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c0354`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800c0383`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800c0383`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800c026d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800c02b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800c026d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800c02b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLockScreenHistory::_GPCacheStateFromEntry(
        CLockScreenHistory *this,
        CLockScreenHistory::CLockScreenHistoryEntry *a2,
        LPCWCH lpString1,
        _DWORD *a4)
{
  __int64 v8; // rdx
  FILETIME FileTime1; // [rsp+30h] [rbp-D0h] BYREF
  LPCWCH lpString2; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C0h]
  __int64 v13; // [rsp+48h] [rbp-B8h]
  __int128 FileInformation; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime2[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+70h] [rbp-90h]
  _OWORD v17[2]; // [rsp+78h] [rbp-88h] BYREF
  int v18; // [rsp+98h] [rbp-68h]
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  *a4 = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime2[0].dwLowDateTime = 0;
  v16 = 0;
  if ( GetFileAttributesExW(lpString1, GetFileExInfoStandard, &FileInformation) )
    *a4 |= 1u;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  if ( (int)StringCchCopyW(FileName, 0x104u, (const unsigned __int16 *)a2 + 289) >= 0
    && GetFileAttributesExW(FileName, GetFileExInfoStandard, v17) )
  {
    *a4 |= 2u;
  }
  lpString2 = 0;
  v12 = 0;
  v13 = 0;
  FileTime1 = 0;
  if ( (*(_BYTE *)a4 & 3) == 3 )
  {
    if ( (int)CLockScreenHistory::_EnsureCurrentUserSid(this) < 0
      || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2),
          v12 = -1,
          v13 = -1,
          (int)ReadSystemDataRegistryStringForUser(*(_QWORD *)this, v8, (char *)a2 + 386) < 0)
      || CompareStringOrdinal(lpString1, -1, lpString2, -1, 1) != 2
      || (int)CLockScreenHistory::CLockScreenHistoryEntry::ReadGPImageModifiedTime(a2, *(void **)this, &FileTime1) < 0
      || CompareFileTime(&FileTime1, (const FILETIME *)&FileTime2[0].dwHighDateTime) )
    {
      *a4 |= 4u;
    }
  }
  return Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2);
}

```

## disassembly

```asm
0x1800c0214  push    rbp
0x1800c0216  push    rbx
0x1800c0217  push    rsi
0x1800c0218  push    rdi
0x1800c0219  push    r12
0x1800c021b  push    r14
0x1800c021d  lea     rbp, [rsp-1C8h]
0x1800c0225  sub     rsp, 2C8h
0x1800c022c  mov     rax, cs:__security_cookie
0x1800c0233  xor     rax, rsp
0x1800c0236  mov     [rbp+1F0h+var_40], rax
0x1800c023d  mov     rbx, r9
0x1800c0240  mov     r14, r8
0x1800c0243  mov     rsi, rdx
0x1800c0246  mov     rdi, rcx
0x1800c0249  mov     dword ptr [r9], 0
0x1800c0250  xorps   xmm0, xmm0
0x1800c0253  xor     eax, eax
0x1800c0255  movups  [rsp+2F0h+FileInformation], xmm0
0x1800c025a  movups  xmmword ptr [rsp+2F0h+FileTime2.dwLowDateTime], xmm0
0x1800c025f  mov     [rsp+2F0h+var_280], eax
0x1800c0263  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x1800c0268  xor     edx, edx; fInfoLevelId
0x1800c026a  mov     rcx, r14; lpFileName
0x1800c026d  call    cs:__imp_GetFileAttributesExW
0x1800c0274  nop     dword ptr [rax+rax+00h]
0x1800c0279  test    eax, eax
0x1800c027b  jz      short loc_1800C0280
0x1800c027d  or      dword ptr [rbx], 1
0x1800c0280  xorps   xmm0, xmm0
0x1800c0283  xor     eax, eax
0x1800c0285  movups  [rsp+2F0h+var_278], xmm0
0x1800c028a  movups  [rbp+1F0h+var_268], xmm0
0x1800c028e  mov     [rbp+1F0h+var_258], eax
0x1800c0291  lea     r8, [rsi+242h]; unsigned __int16 *
0x1800c0298  mov     edx, 104h; unsigned __int64
0x1800c029d  lea     rcx, [rbp+1F0h+FileName]; unsigned __int16 *
0x1800c02a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c02a6  test    eax, eax
0x1800c02a8  js      short loc_1800C02C8
0x1800c02aa  lea     r8, [rsp+2F0h+var_278]; lpFileInformation
0x1800c02af  xor     edx, edx; fInfoLevelId
0x1800c02b1  lea     rcx, [rbp+1F0h+FileName]; lpFileName
0x1800c02b5  call    cs:__imp_GetFileAttributesExW
0x1800c02bc  nop     dword ptr [rax+rax+00h]
0x1800c02c1  test    eax, eax
0x1800c02c3  jz      short loc_1800C02C8
0x1800c02c5  or      dword ptr [rbx], 2
0x1800c02c8  mov     [rsp+2F0h+lpString2], 0
0x1800c02d1  mov     [rsp+2F0h+var_2B0], 0
0x1800c02da  mov     [rsp+2F0h+var_2A8], 0
0x1800c02e3  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], 0
0x1800c02ec  mov     eax, [rbx]
0x1800c02ee  and     eax, 3
0x1800c02f1  cmp     al, 3
0x1800c02f3  jnz     loc_1800C0396
0x1800c02f9  mov     rcx, rdi; this
0x1800c02fc  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x1800c0301  test    eax, eax
0x1800c0303  js      loc_1800C0393
0x1800c0309  lea     rcx, [rsp+2F0h+lpString2]
0x1800c030e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c0313  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800c0317  mov     [rsp+2F0h+var_2B0], r12
0x1800c031c  mov     [rsp+2F0h+var_2A8], r12
0x1800c0321  lea     r8, [rsi+182h]
0x1800c0328  lea     rax, [rsp+2F0h+lpString2]
0x1800c032d  mov     qword ptr [rsp+2F0h+bIgnoreCase], rax
0x1800c0332  mov     rcx, [rdi]
0x1800c0335  call    ?ReadSystemDataRegistryStringForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@PEAPEAG@Z; ReadSystemDataRegistryStringForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ushort * *)
0x1800c033a  test    eax, eax
0x1800c033c  js      short loc_1800C0393
0x1800c033e  mov     [rsp+2F0h+bIgnoreCase], 1; bIgnoreCase
0x1800c0346  mov     r9d, r12d; cchCount2
0x1800c0349  mov     r8, [rsp+2F0h+lpString2]; lpString2
0x1800c034e  mov     edx, r12d; cchCount1
0x1800c0351  mov     rcx, r14; lpString1
0x1800c0354  call    cs:__imp_CompareStringOrdinal
0x1800c035b  nop     dword ptr [rax+rax+00h]
0x1800c0360  cmp     eax, 2
0x1800c0363  jnz     short loc_1800C0393
0x1800c0365  lea     r8, [rsp+2F0h+FileTime1]; struct _FILETIME *
0x1800c036a  mov     rdx, [rdi]; void *
0x1800c036d  mov     rcx, rsi; this
0x1800c0370  call    ?ReadGPImageModifiedTime@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJPEAXPEAU_FILETIME@@@Z; CLockScreenHistory::CLockScreenHistoryEntry::ReadGPImageModifiedTime(void *,_FILETIME *)
0x1800c0375  test    eax, eax
0x1800c0377  js      short loc_1800C0393
0x1800c0379  lea     rdx, [rsp+2F0h+FileTime2.dwHighDateTime]; lpFileTime2
0x1800c037e  lea     rcx, [rsp+2F0h+FileTime1]; lpFileTime1
0x1800c0383  call    cs:__imp_CompareFileTime
0x1800c038a  nop     dword ptr [rax+rax+00h]
0x1800c038f  test    eax, eax
0x1800c0391  jz      short loc_1800C0396
0x1800c0393  or      dword ptr [rbx], 4
0x1800c0396  lea     rcx, [rsp+2F0h+lpString2]
0x1800c039b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c03a0  mov     rcx, [rbp+1F0h+var_40]
0x1800c03a7  xor     rcx, rsp; StackCookie
0x1800c03aa  call    __security_check_cookie
0x1800c03af  add     rsp, 2C8h
0x1800c03b6  pop     r14
0x1800c03b8  pop     r12
0x1800c03ba  pop     rdi
0x1800c03bb  pop     rsi
0x1800c03bc  pop     rbx
0x1800c03bd  pop     rbp
0x1800c03be  retn
```

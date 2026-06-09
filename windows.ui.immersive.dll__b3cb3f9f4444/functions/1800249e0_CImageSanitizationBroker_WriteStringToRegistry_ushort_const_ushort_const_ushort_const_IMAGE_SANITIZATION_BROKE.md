# CImageSanitizationBroker::WriteStringToRegistry(ushort const *,ushort const *,ushort const *,IMAGE_SANITIZATION_BROKER_REGISTRY_FLAGS)

- ea: `0x1800249e0`
- end: `0x180024cbd`
- name: `?WriteStringToRegistry@CImageSanitizationBroker@@UEAAJPEBG00W4IMAGE_SANITIZATION_BROKER_REGISTRY_FLAGS@@@Z`
- size: `733`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const unsigned __int16 *, const unsigned __int16 *, char)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000da00`
- `0x180013f14`
- `0x1800249e0`
- `0x18002576c`
- `0x18002b438`
- `0x18003039c`
- `0x18003d244`
- `0x180054130`
- `0x1800d8ad8`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024a4c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024a75`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024aa6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024a4c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024a75`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024aa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024c75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024c75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024c64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024c64`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180024afe`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180024afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c84`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024bca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024bca`

## string_xrefs

- `0x180024bee`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CImageSanitizationBroker::WriteStringToRegistry(
        __int64 a1,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        char a5)
{
  unsigned int v6; // esi
  unsigned __int64 v7; // rdi
  int RegKeyWithSDDL; // ebx
  unsigned __int64 v11; // rbx
  LPWSTR v12; // rdi
  HRESULT v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  void *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  char hKey; // [rsp+40h] [rbp-C0h]
  void *ppInterface; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v23[264]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  v7 = -1;
  while ( 1 )
  {
    RegKeyWithSDDL = -2147024809;
    if ( v6 >= 0xB )
      return (unsigned int)RegKeyWithSDDL;
    if ( CompareStringOrdinal(a2, -1, off_180135790[v6], -1, 0) == 2 )
    {
      if ( CompareStringOrdinal(a2, -1, L"LockScreen\\Creative", -1, 0) == 2 )
      {
        v11 = 0x8000;
      }
      else
      {
        v11 = 1024;
        if ( CompareStringOrdinal(a2, -1, L"LanguageProfile", -1, 0) == 2 )
          v11 = 4096;
      }
      do
        ++v7;
      while ( a4[v7] );
      if ( v7 > v11 )
        return (unsigned int)-2147024809;
      StringSid[0] = 0;
      v12 = 0;
      hKey = 0;
      ppInterface = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppInterface);
      v13 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
      RegKeyWithSDDL = v13;
      if ( v13 != -2147417833 )
      {
        if ( !v13 )
        {
          if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
            goto LABEL_18;
          RegKeyWithSDDL = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
          if ( RegKeyWithSDDL >= 0 )
          {
            hKey = 1;
            goto LABEL_18;
          }
LABEL_19:
          if ( hKey )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
          v16 = ppInterface;
          if ( ppInterface )
          {
            ppInterface = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
          }
          if ( RegKeyWithSDDL >= 0 )
          {
            if ( (a5 & 2) != 0 )
            {
              RegKeyWithSDDL = _WriteSystemDataRegistryStringForUser(v12, a2, a3);
            }
            else
            {
              StringSid[0] = 0;
              if ( ConvertSidToStringSidW(v12, StringSid)
                || (RegKeyWithSDDL = ResultFromKnownLastError(), RegKeyWithSDDL >= 0) )
              {
                RegKeyWithSDDL = StringCchPrintfW(
                                   v23,
                                   0x104u,
                                   L"%s\\%s\\%s\\%s",
                                   L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                                   StringSid[0],
                                   L"AnyoneRead",
                                   a2);
                if ( RegKeyWithSDDL >= 0 )
                {
                  RegKeyWithSDDL = _CreateRegKeyWithSDDL(v18, v17, v23);
                  if ( RegKeyWithSDDL >= 0 )
                  {
                    RegKeyWithSDDL = SHRegSetString(0, 0, a3, a4);
                    RegCloseKey(0);
                  }
                }
                LocalFree(StringSid[0]);
              }
            }
            CoTaskMemFree(v12);
          }
          return (unsigned int)RegKeyWithSDDL;
        }
        if ( v13 < 0 )
          goto LABEL_19;
      }
LABEL_18:
      v15 = SHGetUserSidFallbackForImpersonation(v14, StringSid);
      v12 = StringSid[0];
      RegKeyWithSDDL = v15;
      goto LABEL_19;
    }
    ++v6;
  }
}

```

## disassembly

```asm
0x1800249e0  mov     [rsp-8+arg_0], rbx
0x1800249e5  push    rbp
0x1800249e6  push    rsi
0x1800249e7  push    rdi
0x1800249e8  push    r12
0x1800249ea  push    r13
0x1800249ec  push    r14
0x1800249ee  push    r15
0x1800249f0  lea     rbp, [rsp-180h]
0x1800249f8  sub     rsp, 280h
0x1800249ff  mov     rax, cs:__security_cookie
0x180024a06  xor     rax, rsp
0x180024a09  mov     [rbp+1B0h+var_40], rax
0x180024a10  xor     r13d, r13d
0x180024a13  mov     r15, r9
0x180024a16  mov     esi, r13d
0x180024a19  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180024a1d  mov     r12, r8
0x180024a20  mov     r14, rdx
0x180024a23  mov     ebx, 80070057h
0x180024a28  cmp     esi, 0Bh
0x180024a2b  jnb     loc_180024C90
0x180024a31  lea     rax, off_180135790; "LockScreen"
0x180024a38  movsxd  r8, esi
0x180024a3b  mov     r9d, edi; cchCount2
0x180024a3e  mov     [rsp+2B0h+bIgnoreCase], r13d; bIgnoreCase
0x180024a43  mov     edx, edi; cchCount1
0x180024a45  mov     rcx, r14; lpString1
0x180024a48  mov     r8, [rax+r8*8]; lpString2
0x180024a4c  call    cs:__imp_CompareStringOrdinal
0x180024a53  nop     dword ptr [rax+rax+00h]
0x180024a58  cmp     eax, 2
0x180024a5b  jz      short loc_180024A61
0x180024a5d  inc     esi
0x180024a5f  jmp     short loc_180024A23
0x180024a61  mov     r9d, edi; cchCount2
0x180024a64  mov     [rsp+2B0h+bIgnoreCase], r13d; bIgnoreCase
0x180024a69  lea     r8, aLockscreenCrea; "LockScreen\\Creative"
0x180024a70  mov     edx, edi; cchCount1
0x180024a72  mov     rcx, r14; lpString1
0x180024a75  call    cs:__imp_CompareStringOrdinal
0x180024a7c  nop     dword ptr [rax+rax+00h]
0x180024a81  cmp     eax, 2
0x180024a84  jnz     short loc_180024A8D
0x180024a86  mov     ebx, 8000h
0x180024a8b  jmp     short loc_180024ABD
0x180024a8d  mov     r9d, edi; cchCount2
0x180024a90  mov     [rsp+2B0h+bIgnoreCase], r13d; bIgnoreCase
0x180024a95  lea     r8, aLanguageprofil; "LanguageProfile"
0x180024a9c  mov     edx, edi; cchCount1
0x180024a9e  mov     rcx, r14; lpString1
0x180024aa1  mov     ebx, 400h
0x180024aa6  call    cs:__imp_CompareStringOrdinal
0x180024aad  nop     dword ptr [rax+rax+00h]
0x180024ab2  cmp     eax, 2
0x180024ab5  mov     ecx, 1000h
0x180024aba  cmovz   ebx, ecx
0x180024abd  inc     rdi
0x180024ac0  cmp     [r15+rdi*2], r13w
0x180024ac5  jnz     short loc_180024ABD
0x180024ac7  cmp     rdi, rbx
0x180024aca  jbe     short loc_180024AD6
0x180024acc  mov     ebx, 80070057h
0x180024ad1  jmp     loc_180024C90
0x180024ad6  lea     rcx, [rsp+2B0h+ppInterface]
0x180024adb  mov     [rsp+2B0h+StringSid], r13
0x180024ae0  mov     rdi, r13
0x180024ae3  mov     byte ptr [rsp+2B0h+hKey], r13b
0x180024ae8  mov     [rsp+2B0h+ppInterface], r13
0x180024aed  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180024af2  lea     rdx, [rsp+2B0h+ppInterface]; ppInterface
0x180024af7  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180024afe  call    cs:__imp_CoGetCallContext
0x180024b05  nop     dword ptr [rax+rax+00h]
0x180024b0a  mov     ebx, eax
0x180024b0c  cmp     eax, 80010117h
0x180024b11  jz      short loc_180024B4C
0x180024b13  test    eax, eax
0x180024b15  jnz     short loc_180024B4A
0x180024b17  mov     rcx, [rsp+2B0h+ppInterface]
0x180024b1c  mov     rax, [rcx]
0x180024b1f  mov     rax, [rax+30h]
0x180024b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b28  test    eax, eax
0x180024b2a  jnz     short loc_180024B4C
0x180024b2c  mov     rcx, [rsp+2B0h+ppInterface]
0x180024b31  mov     rax, [rcx]
0x180024b34  mov     rax, [rax+20h]
0x180024b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b3d  mov     ebx, eax
0x180024b3f  test    eax, eax
0x180024b41  js      short loc_180024B5D
0x180024b43  mov     byte ptr [rsp+2B0h+hKey], 1
0x180024b48  jmp     short loc_180024B4C
0x180024b4a  js      short loc_180024B5D
0x180024b4c  lea     rdx, [rsp+2B0h+StringSid]
0x180024b51  call    SHGetUserSidFallbackForImpersonation
0x180024b56  mov     rdi, [rsp+2B0h+StringSid]
0x180024b5b  mov     ebx, eax
0x180024b5d  cmp     byte ptr [rsp+2B0h+hKey], r13b
0x180024b62  jz      short loc_180024B75
0x180024b64  mov     rcx, [rsp+2B0h+ppInterface]
0x180024b69  mov     rax, [rcx]
0x180024b6c  mov     rax, [rax+28h]
0x180024b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b75  mov     rcx, [rsp+2B0h+ppInterface]
0x180024b7a  test    rcx, rcx
0x180024b7d  jz      short loc_180024B90
0x180024b7f  mov     [rsp+2B0h+ppInterface], r13
0x180024b84  mov     rax, [rcx]
0x180024b87  mov     rax, [rax+10h]
0x180024b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b90  test    ebx, ebx
0x180024b92  js      loc_180024C90
0x180024b98  test    [rbp+1B0h+arg_20], 2
0x180024b9f  mov     rcx, rdi; Sid
0x180024ba2  jz      short loc_180024BC0
0x180024ba4  mov     byte ptr [rsp+2B0h+var_288], 1
0x180024ba9  mov     r8, r12
0x180024bac  mov     rdx, r14
0x180024baf  mov     qword ptr [rsp+2B0h+bIgnoreCase], r15
0x180024bb4  call    ?_WriteSystemDataRegistryStringForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@1_N@Z; _WriteSystemDataRegistryStringForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ushort const *,bool)
0x180024bb9  mov     ebx, eax
0x180024bbb  jmp     loc_180024C81
0x180024bc0  lea     rdx, [rsp+2B0h+StringSid]; StringSid
0x180024bc5  mov     [rsp+2B0h+StringSid], r13
0x180024bca  call    cs:__imp_ConvertSidToStringSidW
0x180024bd1  nop     dword ptr [rax+rax+00h]
0x180024bd6  test    eax, eax
0x180024bd8  jnz     short loc_180024BE9
0x180024bda  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180024bdf  mov     ebx, eax
0x180024be1  test    eax, eax
0x180024be3  js      loc_180024C81
0x180024be9  mov     rcx, [rsp+2B0h+StringSid]
0x180024bee  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180024bf5  mov     rax, cs:off_1800EE7D8; "AnyoneRead"
0x180024bfc  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180024c03  mov     [rsp+2B0h+var_280], r14
0x180024c08  mov     edx, 104h; unsigned __int64
0x180024c0d  mov     [rsp+2B0h+var_288], rax
0x180024c12  mov     qword ptr [rsp+2B0h+bIgnoreCase], rcx
0x180024c17  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180024c1c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024c21  mov     ebx, eax
0x180024c23  test    eax, eax
0x180024c25  js      short loc_180024C70
0x180024c27  lea     rax, [rsp+2B0h+hKey]
0x180024c2c  mov     [rsp+2B0h+hKey], r13
0x180024c31  mov     [rsp+2B0h+var_288], rax
0x180024c36  lea     r8, [rsp+2B0h+var_250]
0x180024c3b  mov     byte ptr [rsp+2B0h+bIgnoreCase], r13b
0x180024c40  call    ?_CreateRegKeyWithSDDL@@YAJPEAUHKEY__@@PEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@_NPEAPEAU1@@Z; _CreateRegKeyWithSDDL(HKEY__ *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,bool,HKEY__ * *)
0x180024c45  mov     ebx, eax
0x180024c47  test    eax, eax
0x180024c49  js      short loc_180024C70
0x180024c4b  mov     rcx, [rsp+2B0h+hKey]; HKEY
0x180024c50  mov     r9, r15; unsigned __int16 *
0x180024c53  mov     r8, r12; unsigned __int16 *
0x180024c56  xor     edx, edx; unsigned __int16 *
0x180024c58  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180024c5d  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180024c62  mov     ebx, eax
0x180024c64  call    cs:__imp_RegCloseKey
0x180024c6b  nop     dword ptr [rax+rax+00h]
0x180024c70  mov     rcx, [rsp+2B0h+StringSid]; hMem
0x180024c75  call    cs:__imp_LocalFree
0x180024c7c  nop     dword ptr [rax+rax+00h]
0x180024c81  mov     rcx, rdi; pv
0x180024c84  call    cs:__imp_CoTaskMemFree
0x180024c8b  nop     dword ptr [rax+rax+00h]
0x180024c90  mov     eax, ebx
0x180024c92  mov     rcx, [rbp+1B0h+var_40]
0x180024c99  xor     rcx, rsp; StackCookie
0x180024c9c  call    __security_check_cookie
0x180024ca1  mov     rbx, [rsp+2B0h+arg_0]
0x180024ca9  add     rsp, 280h
0x180024cb0  pop     r15
0x180024cb2  pop     r14
0x180024cb4  pop     r13
0x180024cb6  pop     r12
0x180024cb8  pop     rdi
0x180024cb9  pop     rsi
0x180024cba  pop     rbp
0x180024cbb  retn
```

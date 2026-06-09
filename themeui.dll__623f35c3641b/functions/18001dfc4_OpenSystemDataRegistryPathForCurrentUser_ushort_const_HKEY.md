# OpenSystemDataRegistryPathForCurrentUser(ushort const *,HKEY__ * *)

- ea: `0x18001dfc4`
- end: `0x18001e0df`
- name: `?OpenSystemDataRegistryPathForCurrentUser@@YAJPEBGPEAPEAUHKEY__@@@Z`
- size: `283`
- prototype: `int(const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001d990`

## callees

- `0x1800089c0`
- `0x18001dfc4`
- `0x18001e0e8`
- `0x180030f64`
- `0x1800358c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e0b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e091`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e091`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e01d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e01d`

## string_xrefs

- `0x18001e043`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall OpenSystemDataRegistryPathForCurrentUser(const unsigned __int16 *a1, HKEY *a2)
{
  signed int CurrentUserSid; // ebx
  LSTATUS v4; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp-238h] BYREF
  PSID Sid; // [rsp+48h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF

  *a2 = 0;
  Sid = 0;
  CurrentUserSid = GetCurrentUserSid(&Sid);
  if ( CurrentUserSid >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) || (CurrentUserSid = ResultFromKnownLastError(), CurrentUserSid >= 0) )
    {
      CurrentUserSid = StringCchPrintfW(
                         SubKey,
                         0x104u,
                         L"%s\\%s\\%s\\%s",
                         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                         StringSid,
                         L"AnyoneRead",
                         L"Colors");
      if ( CurrentUserSid >= 0 )
      {
        v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, a2);
        CurrentUserSid = v4;
        if ( v4 > 0 )
          CurrentUserSid = (unsigned __int16)v4 | 0x80070000;
      }
      LocalFree(StringSid);
    }
    LocalFree(Sid);
  }
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x18001dfc4  mov     [rsp+arg_0], rbx
0x18001dfc9  push    rdi
0x18001dfca  sub     rsp, 270h
0x18001dfd1  mov     rax, cs:__security_cookie
0x18001dfd8  xor     rax, rsp
0x18001dfdb  mov     [rsp+278h+var_18], rax
0x18001dfe3  lea     rcx, [rsp+278h+Sid]; void **
0x18001dfe8  mov     qword ptr [rdx], 0
0x18001dfef  mov     rdi, rdx
0x18001dff2  mov     [rsp+278h+Sid], 0
0x18001dffb  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18001e000  mov     ebx, eax
0x18001e002  test    eax, eax
0x18001e004  js      loc_18001E0BC
0x18001e00a  mov     rcx, [rsp+278h+Sid]; Sid
0x18001e00f  lea     rdx, [rsp+278h+StringSid]; StringSid
0x18001e014  mov     [rsp+278h+StringSid], 0
0x18001e01d  call    cs:__imp_ConvertSidToStringSidW
0x18001e023  test    eax, eax
0x18001e025  jnz     short loc_18001E032
0x18001e027  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e02c  mov     ebx, eax
0x18001e02e  test    eax, eax
0x18001e030  js      short loc_18001E0B1
0x18001e032  mov     rcx, [rsp+278h+StringSid]
0x18001e037  lea     rax, aColors; "Colors"
0x18001e03e  mov     [rsp+278h+var_248], rax
0x18001e043  lea     r9, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001e04a  mov     rax, cs:off_18006EB68; "AnyoneRead"
0x18001e051  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18001e058  mov     [rsp+278h+var_250], rax
0x18001e05d  mov     edx, 104h; unsigned __int64
0x18001e062  mov     [rsp+278h+phkResult], rcx
0x18001e067  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18001e06c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e071  mov     ebx, eax
0x18001e073  test    eax, eax
0x18001e075  js      short loc_18001E0A6
0x18001e077  mov     r9d, 20019h; samDesired
0x18001e07d  mov     [rsp+278h+phkResult], rdi; phkResult
0x18001e082  xor     r8d, r8d; ulOptions
0x18001e085  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18001e08a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e091  call    cs:__imp_RegOpenKeyExW
0x18001e097  mov     ebx, eax
0x18001e099  test    eax, eax
0x18001e09b  jle     short loc_18001E0A6
0x18001e09d  movzx   ebx, ax
0x18001e0a0  or      ebx, 80070000h
0x18001e0a6  mov     rcx, [rsp+278h+StringSid]; hMem
0x18001e0ab  call    cs:__imp_LocalFree
0x18001e0b1  mov     rcx, [rsp+278h+Sid]; hMem
0x18001e0b6  call    cs:__imp_LocalFree
0x18001e0bc  mov     eax, ebx
0x18001e0be  mov     rcx, [rsp+278h+var_18]
0x18001e0c6  xor     rcx, rsp; StackCookie
0x18001e0c9  call    __security_check_cookie
0x18001e0ce  mov     rbx, [rsp+278h+arg_0]
0x18001e0d6  add     rsp, 270h
0x18001e0dd  pop     rdi
0x18001e0de  retn
```

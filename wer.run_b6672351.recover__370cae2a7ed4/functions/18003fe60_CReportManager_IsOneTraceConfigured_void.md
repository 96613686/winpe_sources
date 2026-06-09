# CReportManager::IsOneTraceConfigured(void)

- ea: `0x18003fe60`
- end: `0x180040035`
- name: `?IsOneTraceConfigured@CReportManager@@SAHXZ`
- size: `469`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a0f8`

## callees

- `0x18003fe60`
- `0x180053300`
- `0x1800787f0`
- `0x1800788ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003ff03`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003ff03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040002`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040002`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fec1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fec1`

## pseudocode

```c
__int64 CReportManager::IsOneTraceConfigured(void)
{
  DWORD v0; // r14d
  unsigned int v1; // r15d
  unsigned __int64 v2; // rbx
  WCHAR *v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rdi
  char *v6; // rsi
  WCHAR *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rbx
  DWORD cchName[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[1032]; // [rsp+50h] [rbp-B0h] BYREF

  cchName[0] = 0;
  hKey = 0;
  v0 = 0;
  v1 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting\\DynamicEtwSessions",
          0,
          0x20119u,
          &hKey) )
  {
    while ( 1 )
    {
      cchName[0] = 1025;
      if ( RegEnumKeyExW(hKey, v0, Name, cchName, 0, 0, 0, 0) )
        break;
      v2 = -1;
      do
        ++v2;
      while ( Name[v2] );
      if ( v2 >= 8 )
      {
        v3 = Name;
        while ( 1 )
        {
          v4 = tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::find(
                 v3,
                 ((char *)cchName + 2 * v2 + 2 - (char *)v3) >> 1,
                 L"OneTrace");
          v5 = v4;
          if ( !v4 )
            break;
          v3 = (WCHAR *)(v4 + 2);
          if ( !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                                v4 + 2,
                                L"neTrace",
                                7) )
          {
            if ( (v5 - (__int64)Name) >> 1 != -1 )
            {
LABEL_16:
              v1 = 1;
              goto LABEL_17;
            }
            break;
          }
        }
        if ( v2 >= 9 )
        {
          v6 = (char *)cchName + 2 * v2;
          v7 = Name;
          while ( 1 )
          {
            v8 = tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::find(
                   v7,
                   (v6 - (char *)v7) >> 1,
                   L"One Trace");
            v9 = v8;
            if ( !v8 )
              break;
            v7 = (WCHAR *)(v8 + 2);
            if ( !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                                  v8 + 2,
                                  L"ne Trace",
                                  8) )
            {
              if ( (v9 - (__int64)Name) >> 1 != -1 )
                goto LABEL_16;
              break;
            }
          }
        }
      }
      ++v0;
    }
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18003fe60  push    rbp
0x18003fe62  push    rbx
0x18003fe63  push    rsi
0x18003fe64  push    rdi
0x18003fe65  push    r12
0x18003fe67  push    r13
0x18003fe69  push    r14
0x18003fe6b  push    r15
0x18003fe6d  lea     rbp, [rsp-778h]
0x18003fe75  sub     rsp, 878h
0x18003fe7c  mov     rax, cs:__security_cookie
0x18003fe83  xor     rax, rsp
0x18003fe86  mov     [rbp+7B0h+var_50], rax
0x18003fe8d  xor     r13d, r13d
0x18003fe90  lea     rax, [rsp+8B0h+hKey]
0x18003fe95  mov     r9d, 20119h; samDesired
0x18003fe9b  mov     [rsp+8B0h+cchName], r13d
0x18003fea0  xor     r8d, r8d; ulOptions
0x18003fea3  mov     [rsp+8B0h+hKey], r13
0x18003fea8  lea     rdx, aSoftwareMicros_30; "Software\\Microsoft\\Windows\\Windows E"...
0x18003feaf  mov     [rsp+8B0h+phkResult], rax; phkResult
0x18003feb4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003febb  mov     r14d, r13d
0x18003febe  mov     r15d, r13d
0x18003fec1  call    cs:__imp_RegOpenKeyExW
0x18003fec8  nop     dword ptr [rax+rax+00h]
0x18003fecd  test    eax, eax
0x18003fecf  jnz     loc_18003FFF8
0x18003fed5  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18003feda  lea     r9, [rsp+8B0h+cchName]; lpcchName
0x18003fedf  mov     [rsp+8B0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18003fee4  lea     r8, [rsp+8B0h+Name]; lpName
0x18003fee9  mov     [rsp+8B0h+lpcchClass], r13; lpcchClass
0x18003feee  mov     edx, r14d; dwIndex
0x18003fef1  mov     [rsp+8B0h+lpClass], r13; lpClass
0x18003fef6  mov     [rsp+8B0h+phkResult], r13; lpReserved
0x18003fefb  mov     [rsp+8B0h+cchName], 401h
0x18003ff03  call    cs:__imp_RegEnumKeyExW
0x18003ff0a  nop     dword ptr [rax+rax+00h]
0x18003ff0f  test    eax, eax
0x18003ff11  jnz     loc_18003FFF8
0x18003ff17  lea     rax, [rsp+8B0h+Name]
0x18003ff1c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003ff20  inc     rbx
0x18003ff23  cmp     [rax+rbx*2], r13w
0x18003ff28  jnz     short loc_18003FF20
0x18003ff2a  cmp     rbx, 8
0x18003ff2e  jb      loc_18003FFEA
0x18003ff34  lea     r12, [rsp+rbx*2+8B0h+cchName+2]
0x18003ff39  lea     rsi, [rsp+8B0h+Name]
0x18003ff3e  mov     rdx, r12
0x18003ff41  lea     r8, aOnetrace; "OneTrace"
0x18003ff48  sub     rdx, rsi
0x18003ff4b  mov     rcx, rsi
0x18003ff4e  sar     rdx, 1
0x18003ff51  call    ?find@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAPEB_WPEB_W_KAEB_W@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::find(wchar_t const *,unsigned __int64,wchar_t const &)
0x18003ff56  mov     rdi, rax
0x18003ff59  test    rax, rax
0x18003ff5c  jz      short loc_18003FF8C
0x18003ff5e  lea     rsi, [rax+2]
0x18003ff62  mov     r8d, 7
0x18003ff68  mov     rcx, rsi
0x18003ff6b  lea     rdx, aOnetrace+2; "neTrace"
0x18003ff72  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x18003ff77  test    eax, eax
0x18003ff79  jnz     short loc_18003FF3E
0x18003ff7b  lea     rax, [rsp+8B0h+Name]
0x18003ff80  sub     rdi, rax
0x18003ff83  sar     rdi, 1
0x18003ff86  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003ff8a  jnz     short loc_18003FFF2
0x18003ff8c  cmp     rbx, 9
0x18003ff90  jb      short loc_18003FFEA
0x18003ff92  lea     rsi, [rsp+rbx*2+8B0h+cchName]
0x18003ff97  lea     rdi, [rsp+8B0h+Name]
0x18003ff9c  mov     rdx, rsi
0x18003ff9f  lea     r8, aOneTrace; "One Trace"
0x18003ffa6  sub     rdx, rdi
0x18003ffa9  mov     rcx, rdi
0x18003ffac  sar     rdx, 1
0x18003ffaf  call    ?find@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAPEB_WPEB_W_KAEB_W@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::find(wchar_t const *,unsigned __int64,wchar_t const &)
0x18003ffb4  mov     rbx, rax
0x18003ffb7  test    rax, rax
0x18003ffba  jz      short loc_18003FFEA
0x18003ffbc  lea     rdi, [rax+2]
0x18003ffc0  mov     r8d, 8
0x18003ffc6  mov     rcx, rdi
0x18003ffc9  lea     rdx, aOneTrace+2; "ne Trace"
0x18003ffd0  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x18003ffd5  test    eax, eax
0x18003ffd7  jnz     short loc_18003FF9C
0x18003ffd9  lea     rax, [rsp+8B0h+Name]
0x18003ffde  sub     rbx, rax
0x18003ffe1  sar     rbx, 1
0x18003ffe4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003ffe8  jnz     short loc_18003FFF2
0x18003ffea  inc     r14d
0x18003ffed  jmp     loc_18003FED5
0x18003fff2  mov     r15d, 1
0x18003fff8  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18003fffd  test    rcx, rcx
0x180040000  jz      short loc_18004000E
0x180040002  call    cs:__imp_RegCloseKey
0x180040009  nop     dword ptr [rax+rax+00h]
0x18004000e  mov     eax, r15d
0x180040011  mov     rcx, [rbp+7B0h+var_50]
0x180040018  xor     rcx, rsp; StackCookie
0x18004001b  call    __security_check_cookie
0x180040020  add     rsp, 878h
0x180040027  pop     r15
0x180040029  pop     r14
0x18004002b  pop     r13
0x18004002d  pop     r12
0x18004002f  pop     rdi
0x180040030  pop     rsi
0x180040031  pop     rbx
0x180040032  pop     rbp
0x180040033  retn
```

# CleanupSpaceFreedLogs

- ea: `0x18002fa54`
- end: `0x18002fb8f`
- name: `CleanupSpaceFreedLogs`
- size: `315`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002fe70`
- `0x180030b04`

## callees

- `0x18000d030`
- `0x18002fa54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002fb45`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002fb45`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002fb38`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002fb38`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002fb5e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002fb5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002faa1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002faa1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002fadc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002fadc`

## pseudocode

```c
__int64 __fastcall CleanupSpaceFreedLogs(HKEY hKey)
{
  DWORD v2; // edi
  unsigned __int64 v3; // rax
  unsigned int v4; // r14d
  LSTATUS v5; // ebx
  unsigned int v6; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF

  cchValueName = 0;
  v2 = 0;
  SystemTimeAsFileTime = 0;
  SystemTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = SystemTimeAsFileTime.dwLowDateTime
     + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32)
     - 25920000000000LL;
  SystemTimeAsFileTime.dwLowDateTime += 127631360;
  SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v3);
  FileTimeToSystemTime(&SystemTimeAsFileTime, &SystemTime);
  v4 = SystemTime.wDay + 100 * (SystemTime.wMonth + 100 * SystemTime.wYear);
  while ( 1 )
  {
    cchValueName = 260;
    v5 = RegEnumValueW(hKey, v2, ValueName, &cchValueName, 0, 0, 0, 0);
    v6 = _o__wtoi(ValueName);
    if ( v5 )
      break;
    ++v2;
    if ( v6 <= v4 )
      RegDeleteValueW(hKey, ValueName);
  }
  return 0;
}

```

## disassembly

```asm
0x18002fa54  mov     [rsp-8+arg_8], rbx
0x18002fa59  mov     [rsp-8+arg_10], rsi
0x18002fa5e  push    rbp
0x18002fa5f  push    rdi
0x18002fa60  push    r14
0x18002fa62  lea     rbp, [rsp-180h]
0x18002fa6a  sub     rsp, 280h
0x18002fa71  mov     rax, cs:__security_cookie
0x18002fa78  xor     rax, rsp
0x18002fa7b  mov     [rbp+190h+var_20], rax
0x18002fa82  mov     rsi, rcx
0x18002fa85  mov     [rsp+290h+cchValueName], 0
0x18002fa8d  xorps   xmm0, xmm0
0x18002fa90  lea     rcx, [rsp+290h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002fa95  xor     edi, edi
0x18002fa97  mov     qword ptr [rsp+290h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18002fa9c  movups  xmmword ptr [rsp+290h+SystemTime.wYear], xmm0
0x18002faa1  call    cs:__imp_GetSystemTimeAsFileTime
0x18002faa7  mov     ecx, [rsp+290h+SystemTimeAsFileTime.dwLowDateTime]
0x18002faab  mov     rdx, 0FFFFE86D079B8000h
0x18002fab5  mov     eax, [rsp+290h+SystemTimeAsFileTime.dwHighDateTime]
0x18002fab9  shl     rax, 20h
0x18002fabd  add     rax, rdx
0x18002fac0  lea     rdx, [rsp+290h+SystemTime]; lpSystemTime
0x18002fac5  add     rax, rcx
0x18002fac8  mov     rcx, rax
0x18002facb  mov     [rsp+290h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18002facf  shr     rcx, 20h
0x18002fad3  mov     [rsp+290h+SystemTimeAsFileTime.dwHighDateTime], ecx
0x18002fad7  lea     rcx, [rsp+290h+SystemTimeAsFileTime]; lpFileTime
0x18002fadc  call    cs:__imp_FileTimeToSystemTime
0x18002fae2  movzx   eax, [rsp+290h+SystemTime.wYear]
0x18002fae7  imul    ecx, eax, 64h ; 'd'
0x18002faea  movzx   eax, [rsp+290h+SystemTime.wMonth]
0x18002faef  add     ecx, eax
0x18002faf1  movzx   eax, [rsp+290h+SystemTime.wDay]
0x18002faf6  imul    r14d, ecx, 64h ; 'd'
0x18002fafa  add     r14d, eax
0x18002fafd  mov     [rsp+290h+lpcbData], 0; lpcbData
0x18002fb06  lea     r9, [rsp+290h+cchValueName]; lpcchValueName
0x18002fb0b  mov     [rsp+290h+lpData], 0; lpData
0x18002fb14  lea     r8, [rsp+290h+ValueName]; lpValueName
0x18002fb19  mov     [rsp+290h+lpType], 0; lpType
0x18002fb22  mov     edx, edi; dwIndex
0x18002fb24  mov     rcx, rsi; hKey
0x18002fb27  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18002fb30  mov     [rsp+290h+cchValueName], 104h
0x18002fb38  call    cs:__imp_RegEnumValueW
0x18002fb3e  lea     rcx, [rsp+290h+ValueName]
0x18002fb43  mov     ebx, eax
0x18002fb45  call    cs:__imp__o__wtoi
0x18002fb4b  test    ebx, ebx
0x18002fb4d  jnz     short loc_18002FB66
0x18002fb4f  inc     edi
0x18002fb51  cmp     eax, r14d
0x18002fb54  ja      short loc_18002FAFD
0x18002fb56  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x18002fb5b  mov     rcx, rsi; hKey
0x18002fb5e  call    cs:__imp_RegDeleteValueW
0x18002fb64  jmp     short loc_18002FAFD
0x18002fb66  xor     eax, eax
0x18002fb68  mov     rcx, [rbp+190h+var_20]
0x18002fb6f  xor     rcx, rsp; StackCookie
0x18002fb72  call    __security_check_cookie
0x18002fb77  lea     r11, [rsp+290h+var_10]
0x18002fb7f  mov     rbx, [r11+28h]
0x18002fb83  mov     rsi, [r11+30h]
0x18002fb87  mov     rsp, r11
0x18002fb8a  pop     r14
0x18002fb8c  pop     rdi
0x18002fb8d  pop     rbp
0x18002fb8e  retn
```

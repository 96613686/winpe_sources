# SHAcctAccountName2DataFileName(ushort const *,ushort *,ulong)

- ea: `0x18000e6ec`
- end: `0x18000e814`
- name: `?SHAcctAccountName2DataFileName@@YAJPEBGPEAGK@Z`
- size: `296`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e8b4`

## callees

- `0x180009190`
- `0x18000b828`
- `0x18000bcc0`
- `0x18000c240`
- `0x18000e6ec`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000e798`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000e798`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18000e74c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18000e74c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e7af`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e7af`

## pseudocode

```c
__int64 __fastcall SHAcctAccountName2DataFileName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 result; // rax
  PWSTR v4; // rbx
  DWORD nSize; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[20]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszStart[520]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String2[256]; // [rsp+460h] [rbp+360h] BYREF

  result = 2147942487LL;
  if ( a1 )
  {
    result = StringCchCopyW(pszStart, 0x201u, a1);
    if ( (int)result >= 0 )
    {
      v4 = StrChrW(pszStart, 0x5Cu);
      if ( v4 )
      {
        result = StringCchCopyNW(String2, 0x100u, pszStart, v4 - pszStart);
        if ( (int)result < 0 )
          return result;
        nSize = 16;
        if ( !GetComputerNameW(Buffer, &nSize) )
        {
          result = ResultFromKnownLastError();
LABEL_10:
          if ( (int)result < 0 )
            return result;
          return StringCchCopyW(a2, 0x104u, pszStart);
        }
        if ( !lstrcmpiW(Buffer, String2) )
        {
          result = StringCchCopyW(pszStart, 0x201u, v4 + 1);
          goto LABEL_10;
        }
        *v4 = 43;
      }
      return StringCchCopyW(a2, 0x104u, pszStart);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e6ec  mov     [rsp-8+arg_10], rbx
0x18000e6f1  mov     [rsp-8+arg_18], rdi
0x18000e6f6  push    rbp
0x18000e6f7  lea     rbp, [rsp-570h]
0x18000e6ff  sub     rsp, 670h
0x18000e706  mov     rax, cs:__security_cookie
0x18000e70d  xor     rax, rsp
0x18000e710  mov     [rbp+570h+var_10], rax
0x18000e717  mov     rdi, rdx
0x18000e71a  mov     eax, 80070057h
0x18000e71f  test    rcx, rcx
0x18000e722  jz      loc_18000E7F0
0x18000e728  mov     r8, rcx; unsigned __int16 *
0x18000e72b  mov     edx, 201h; unsigned __int64
0x18000e730  lea     rcx, [rsp+670h+pszStart]; unsigned __int16 *
0x18000e735  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e73a  test    eax, eax
0x18000e73c  js      loc_18000E7F0
0x18000e742  mov     edx, 5Ch ; '\'; wMatch
0x18000e747  lea     rcx, [rsp+670h+pszStart]; pszStart
0x18000e74c  call    cs:__imp_StrChrW
0x18000e752  mov     rbx, rax
0x18000e755  test    rax, rax
0x18000e758  jz      loc_18000E7DE
0x18000e75e  lea     rax, [rsp+670h+pszStart]
0x18000e763  mov     r9, rbx
0x18000e766  sub     r9, rax
0x18000e769  lea     r8, [rsp+670h+pszStart]; unsigned __int16 *
0x18000e76e  sar     r9, 1; unsigned __int64
0x18000e771  lea     rcx, [rbp+570h+String2]; unsigned __int16 *
0x18000e778  mov     edx, 100h; unsigned __int64
0x18000e77d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000e782  test    eax, eax
0x18000e784  js      short loc_18000E7F0
0x18000e786  lea     rdx, [rsp+670h+nSize]; nSize
0x18000e78b  mov     [rsp+670h+nSize], 10h
0x18000e793  lea     rcx, [rsp+670h+Buffer]; lpBuffer
0x18000e798  call    cs:__imp_GetComputerNameW
0x18000e79e  cmp     eax, 1
0x18000e7a1  jnz     short loc_18000E7D5
0x18000e7a3  lea     rdx, [rbp+570h+String2]; lpString2
0x18000e7aa  lea     rcx, [rsp+670h+Buffer]; lpString1
0x18000e7af  call    cs:__imp_lstrcmpiW
0x18000e7b5  test    eax, eax
0x18000e7b7  jnz     short loc_18000E7CE
0x18000e7b9  lea     r8, [rbx+2]; unsigned __int16 *
0x18000e7bd  mov     edx, 201h; unsigned __int64
0x18000e7c2  lea     rcx, [rsp+670h+pszStart]; unsigned __int16 *
0x18000e7c7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e7cc  jmp     short loc_18000E7DA
0x18000e7ce  mov     word ptr [rbx], 2Bh ; '+'
0x18000e7d3  jmp     short loc_18000E7DE
0x18000e7d5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000e7da  test    eax, eax
0x18000e7dc  js      short loc_18000E7F0
0x18000e7de  lea     r8, [rsp+670h+pszStart]; unsigned __int16 *
0x18000e7e3  mov     edx, 104h; unsigned __int64
0x18000e7e8  mov     rcx, rdi; unsigned __int16 *
0x18000e7eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e7f0  mov     rcx, [rbp+570h+var_10]
0x18000e7f7  xor     rcx, rsp; StackCookie
0x18000e7fa  call    __security_check_cookie
0x18000e7ff  lea     r11, [rsp+670h+var_s0]
0x18000e807  mov     rbx, [r11+20h]
0x18000e80b  mov     rdi, [r11+28h]
0x18000e80f  mov     rsp, r11
0x18000e812  pop     rbp
0x18000e813  retn
```

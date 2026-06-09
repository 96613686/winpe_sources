# SHParseUserName

- ea: `0x180015d58`
- end: `0x180015e30`
- name: `SHParseUserName`
- size: `216`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d838`

## callees

- `0x180002610`
- `0x18000a1c8`
- `0x180015bdc`
- `0x180015d58`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180015d8e`
- `SHLWAPI!StrChrW` at `0x180015d8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180015de4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180015de4`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180015df7`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180015df7`

## pseudocode

```c
__int64 __fastcall SHParseUserName(unsigned __int16 *a1, unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4)
{
  int v7; // ebx
  PWSTR v8; // rax
  PWSTR v9; // rdi
  unsigned __int64 v10; // rdx
  DWORD nSize; // [rsp+20h] [rbp-58h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-50h] BYREF

  v7 = -2147467259;
  if ( a1 )
  {
    v8 = StrChrW(a1, 0x5Cu);
    v9 = v8;
    if ( v8 )
    {
      v7 = StringCchCopyW(a4, 0x101u, v8 + 1);
      if ( v7 >= 0 )
      {
        v7 = StringCchCopyNW(a2, v10, a1, v9 - a1);
        if ( v7 >= 0 )
        {
          nSize = 16;
          if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) && !lstrcmpiW(Buffer, a2) )
            goto LABEL_9;
        }
      }
    }
    else
    {
      v7 = StringCchCopyW(a4, 0x101u, a1);
      if ( v7 >= 0 )
LABEL_9:
        *a2 = 0;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015d58  push    rbx
0x180015d5a  push    rbp
0x180015d5b  push    rsi
0x180015d5c  push    rdi
0x180015d5d  push    r14
0x180015d5f  sub     rsp, 50h
0x180015d63  mov     rax, cs:__security_cookie
0x180015d6a  xor     rax, rsp
0x180015d6d  mov     [rsp+78h+var_30], rax
0x180015d72  mov     r14, r9
0x180015d75  mov     rsi, rdx
0x180015d78  mov     rbp, rcx
0x180015d7b  mov     ebx, 80004005h
0x180015d80  test    rcx, rcx
0x180015d83  jz      loc_180015E16
0x180015d89  mov     edx, 5Ch ; '\'; wMatch
0x180015d8e  call    cs:__imp_StrChrW
0x180015d94  mov     edx, 101h; unsigned __int64
0x180015d99  mov     rcx, r14; unsigned __int16 *
0x180015d9c  mov     rdi, rax
0x180015d9f  test    rax, rax
0x180015da2  jz      short loc_180015E03
0x180015da4  lea     r8, [rax+2]; unsigned __int16 *
0x180015da8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015dad  mov     ebx, eax
0x180015daf  test    eax, eax
0x180015db1  js      short loc_180015E16
0x180015db3  sub     rdi, rbp
0x180015db6  mov     r8, rbp; unsigned __int16 *
0x180015db9  sar     rdi, 1
0x180015dbc  mov     rcx, rsi; unsigned __int16 *
0x180015dbf  mov     r9, rdi; unsigned __int64
0x180015dc2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180015dc7  mov     ebx, eax
0x180015dc9  test    eax, eax
0x180015dcb  js      short loc_180015E16
0x180015dcd  lea     r8, [rsp+78h+nSize]; nSize
0x180015dd2  mov     [rsp+78h+nSize], 10h
0x180015dda  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x180015ddf  mov     ecx, 4; NameType
0x180015de4  call    cs:__imp_GetComputerNameExW
0x180015dea  cmp     eax, 1
0x180015ded  jnz     short loc_180015E16
0x180015def  mov     rdx, rsi; lpString2
0x180015df2  lea     rcx, [rsp+78h+Buffer]; lpString1
0x180015df7  call    cs:__imp_lstrcmpiW
0x180015dfd  test    eax, eax
0x180015dff  jnz     short loc_180015E16
0x180015e01  jmp     short loc_180015E11
0x180015e03  mov     r8, rbp; unsigned __int16 *
0x180015e06  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015e0b  mov     ebx, eax
0x180015e0d  test    eax, eax
0x180015e0f  js      short loc_180015E16
0x180015e11  xor     eax, eax
0x180015e13  mov     [rsi], ax
0x180015e16  mov     eax, ebx
0x180015e18  mov     rcx, [rsp+78h+var_30]
0x180015e1d  xor     rcx, rsp; StackCookie
0x180015e20  call    __security_check_cookie
0x180015e25  add     rsp, 50h
0x180015e29  pop     r14
0x180015e2b  pop     rdi
0x180015e2c  pop     rsi
0x180015e2d  pop     rbp
0x180015e2e  pop     rbx
0x180015e2f  retn
```

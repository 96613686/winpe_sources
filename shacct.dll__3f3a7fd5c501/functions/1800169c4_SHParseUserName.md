# SHParseUserName

- ea: `0x1800169c4`
- end: `0x180016aa2`
- name: `SHParseUserName`
- size: `222`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013770`
- `0x1800149b0`

## callees

- `0x180009190`
- `0x18000b828`
- `0x18000c240`
- `0x1800169c4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180016a56`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180016a56`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800169fd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800169fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180016a69`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180016a69`

## pseudocode

```c
__int64 __fastcall SHParseUserName(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3, unsigned __int16 *a4)
{
  int v8; // ebx
  PWSTR v9; // rax
  __int64 v10; // r11
  DWORD nSize; // [rsp+20h] [rbp-58h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-50h] BYREF

  v8 = -2147467259;
  if ( a1 )
  {
    v9 = StrChrW(a1, 0x5Cu);
    if ( v9 )
    {
      v8 = StringCchCopyW(a4, 0x101u, v9 + 1);
      if ( v8 >= 0 )
      {
        v8 = StringCchCopyNW(a2, a3, a1, (v10 - (__int64)a1) >> 1);
        if ( v8 >= 0 )
        {
          nSize = 16;
          if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) && !lstrcmpiW(Buffer, a2) )
            goto LABEL_9;
        }
      }
    }
    else
    {
      v8 = StringCchCopyW(a4, 0x101u, a1);
      if ( v8 >= 0 )
LABEL_9:
        *a2 = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800169c4  push    rbx
0x1800169c6  push    rbp
0x1800169c7  push    rsi
0x1800169c8  push    rdi
0x1800169c9  push    r14
0x1800169cb  sub     rsp, 50h
0x1800169cf  mov     rax, cs:__security_cookie
0x1800169d6  xor     rax, rsp
0x1800169d9  mov     [rsp+78h+var_30], rax
0x1800169de  mov     r14d, r8d
0x1800169e1  mov     rbp, r9
0x1800169e4  mov     rdi, rdx
0x1800169e7  mov     rsi, rcx
0x1800169ea  mov     ebx, 80004005h
0x1800169ef  test    rcx, rcx
0x1800169f2  jz      loc_180016A88
0x1800169f8  mov     edx, 5Ch ; '\'; wMatch
0x1800169fd  call    cs:__imp_StrChrW
0x180016a03  mov     edx, 101h; unsigned __int64
0x180016a08  mov     rcx, rbp; unsigned __int16 *
0x180016a0b  mov     r11, rax
0x180016a0e  test    rax, rax
0x180016a11  jz      short loc_180016A75
0x180016a13  lea     r8, [rax+2]; unsigned __int16 *
0x180016a17  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016a1c  mov     ebx, eax
0x180016a1e  test    eax, eax
0x180016a20  js      short loc_180016A88
0x180016a22  sub     r11, rsi
0x180016a25  mov     edx, r14d; unsigned __int64
0x180016a28  sar     r11, 1
0x180016a2b  mov     r8, rsi; unsigned __int16 *
0x180016a2e  mov     r9, r11; unsigned __int64
0x180016a31  mov     rcx, rdi; unsigned __int16 *
0x180016a34  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180016a39  mov     ebx, eax
0x180016a3b  test    eax, eax
0x180016a3d  js      short loc_180016A88
0x180016a3f  lea     r8, [rsp+78h+nSize]; nSize
0x180016a44  mov     [rsp+78h+nSize], 10h
0x180016a4c  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x180016a51  mov     ecx, 4; NameType
0x180016a56  call    cs:__imp_GetComputerNameExW
0x180016a5c  cmp     eax, 1
0x180016a5f  jnz     short loc_180016A88
0x180016a61  mov     rdx, rdi; lpString2
0x180016a64  lea     rcx, [rsp+78h+Buffer]; lpString1
0x180016a69  call    cs:__imp_lstrcmpiW
0x180016a6f  test    eax, eax
0x180016a71  jnz     short loc_180016A88
0x180016a73  jmp     short loc_180016A83
0x180016a75  mov     r8, rsi; unsigned __int16 *
0x180016a78  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016a7d  mov     ebx, eax
0x180016a7f  test    eax, eax
0x180016a81  js      short loc_180016A88
0x180016a83  xor     eax, eax
0x180016a85  mov     [rdi], ax
0x180016a88  mov     eax, ebx
0x180016a8a  mov     rcx, [rsp+78h+var_30]
0x180016a8f  xor     rcx, rsp; StackCookie
0x180016a92  call    __security_check_cookie
0x180016a97  add     rsp, 50h
0x180016a9b  pop     r14
0x180016a9d  pop     rdi
0x180016a9e  pop     rsi
0x180016a9f  pop     rbp
0x180016aa0  pop     rbx
0x180016aa1  retn
```

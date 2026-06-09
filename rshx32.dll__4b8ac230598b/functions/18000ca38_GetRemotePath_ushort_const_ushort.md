# GetRemotePath(ushort const *,ushort * *)

- ea: `0x18000ca38`
- end: `0x18000cbf4`
- name: `?GetRemotePath@@YAJPEBGPEAPEAG@Z`
- size: `444`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009148`

## callees

- `0x18000554c`
- `0x180005610`
- `0x18000ca38`
- `0x18001654c`
- `0x1800165e4`
- `0x18001d370`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x18000cbba`
- `SHLWAPI!PathIsUNCW` at `0x18000cbba`
- `SHLWAPI!PathRemoveBackslashW` at `0x18000cbe9`
- `SHLWAPI!PathRemoveBackslashW` at `0x18000cbe9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000caee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000caee`
- `KERNEL32!lstrlenW` at `0x18000cac5`
- `KERNEL32!lstrlenW` at `0x18000cad6`
- `KERNEL32!lstrlenW` at `0x18000cac5`
- `KERNEL32!lstrlenW` at `0x18000cad6`
- `MPR!WNetGetConnectionW` at `0x18000cab4`
- `MPR!WNetGetConnectionW` at `0x18000cb74`
- `MPR!WNetGetConnectionW` at `0x18000cab4`
- `MPR!WNetGetConnectionW` at `0x18000cb74`

## pseudocode

```c
__int64 __fastcall GetRemotePath(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  WCHAR v5; // ax
  signed int ConnectionW; // ebx
  const unsigned __int16 *v7; // r14
  int v8; // eax
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  bool v11; // sf
  signed int v12; // eax
  int v13; // eax
  DWORD nLength; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR LocalName; // [rsp+24h] [rbp-DCh] BYREF
  int v16; // [rsp+26h] [rbp-DAh]
  WCHAR RemoteName[264]; // [rsp+30h] [rbp-D0h] BYREF

  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  if ( a1[1] != 58 )
  {
    ConnectionW = -2147024735;
    if ( !PathIsUNCW(a1) )
      goto LABEL_8;
    v13 = LocalAllocString(a2, a1);
    goto LABEL_24;
  }
  v5 = *a1;
  v16 = 58;
  LocalName = v5;
  nLength = 260;
  ConnectionW = WNetGetConnectionW(&LocalName, RemoteName, &nLength);
  if ( ConnectionW )
  {
    if ( ConnectionW == 2250 )
    {
      ConnectionW = 1;
      goto LABEL_27;
    }
    if ( ConnectionW != 234 )
    {
      v11 = ConnectionW < 0;
      if ( ConnectionW <= 0 )
        goto LABEL_26;
      ConnectionW = (unsigned __int16)ConnectionW | 0x80070000;
LABEL_25:
      v11 = ConnectionW < 0;
LABEL_26:
      if ( v11 )
        goto LABEL_8;
LABEL_27:
      if ( *a2 )
        PathRemoveBackslashW(*a2);
      return (unsigned int)ConnectionW;
    }
  }
  else
  {
    nLength = lstrlenW(RemoteName);
  }
  v7 = a1 + 2;
  v8 = lstrlenW(a1 + 2);
  v9 = nLength + v8 + 1;
  v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v9);
  *a2 = v10;
  if ( v10 )
  {
    if ( ConnectionW == 234 )
    {
      v12 = WNetGetConnectionW(&LocalName, v10, &nLength);
      ConnectionW = v12;
      if ( v12 > 0 )
        ConnectionW = (unsigned __int16)v12 | 0x80070000;
      if ( ConnectionW < 0 )
        goto LABEL_8;
    }
    else
    {
      StringCchCopyW(v10, v9, RemoteName);
    }
    v13 = StringCchCatW(*a2, v9, v7);
LABEL_24:
    ConnectionW = v13;
    goto LABEL_25;
  }
  ConnectionW = -2147024882;
LABEL_8:
  LocalFreeString(a2);
  return (unsigned int)ConnectionW;
}

```

## disassembly

```asm
0x18000ca38  mov     [rsp-8+arg_10], rbx
0x18000ca3d  mov     [rsp-8+arg_18], rsi
0x18000ca42  push    rbp
0x18000ca43  push    rdi
0x18000ca44  push    r14
0x18000ca46  lea     rbp, [rsp-150h]
0x18000ca4e  sub     rsp, 250h
0x18000ca55  mov     rax, cs:__security_cookie
0x18000ca5c  xor     rax, rsp
0x18000ca5f  mov     [rbp+160h+var_20], rax
0x18000ca66  mov     rdi, rdx
0x18000ca69  mov     rsi, rcx
0x18000ca6c  test    rdx, rdx
0x18000ca6f  jnz     short loc_18000CA7B
0x18000ca71  mov     eax, 80070057h
0x18000ca76  jmp     loc_18000CB0B
0x18000ca7b  mov     ecx, 3Ah ; ':'
0x18000ca80  mov     qword ptr [rdx], 0
0x18000ca87  cmp     [rsi+2], cx
0x18000ca8b  jnz     loc_18000CBB2
0x18000ca91  movzx   eax, word ptr [rsi]
0x18000ca94  lea     r8, [rsp+260h+nLength]; lpnLength
0x18000ca99  mov     [rsp+260h+var_23A], ecx
0x18000ca9d  lea     rdx, [rsp+260h+RemoteName]; lpRemoteName
0x18000caa2  lea     rcx, [rsp+260h+LocalName]; lpLocalName
0x18000caa7  mov     [rsp+260h+LocalName], ax
0x18000caac  mov     [rsp+260h+nLength], 104h
0x18000cab4  call    cs:__imp_WNetGetConnectionW
0x18000caba  mov     ebx, eax
0x18000cabc  test    eax, eax
0x18000cabe  jnz     short loc_18000CB32
0x18000cac0  lea     rcx, [rsp+260h+RemoteName]; lpString
0x18000cac5  call    cs:__imp_lstrlenW
0x18000cacb  mov     [rsp+260h+nLength], eax
0x18000cacf  lea     r14, [rsi+4]
0x18000cad3  mov     rcx, r14; lpString
0x18000cad6  call    cs:__imp_lstrlenW
0x18000cadc  lea     ecx, [rax+1]
0x18000cadf  add     ecx, [rsp+260h+nLength]
0x18000cae3  mov     esi, ecx
0x18000cae5  lea     rdx, [rcx+rcx]; uBytes
0x18000cae9  mov     ecx, 40h ; '@'; uFlags
0x18000caee  call    cs:__imp_LocalAlloc
0x18000caf4  mov     [rdi], rax
0x18000caf7  test    rax, rax
0x18000cafa  jnz     short loc_18000CB5F
0x18000cafc  mov     ebx, 8007000Eh
0x18000cb01  mov     rcx, rdi; unsigned __int16 **
0x18000cb04  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x18000cb09  mov     eax, ebx
0x18000cb0b  mov     rcx, [rbp+160h+var_20]
0x18000cb12  xor     rcx, rsp; StackCookie
0x18000cb15  call    __security_check_cookie
0x18000cb1a  lea     r11, [rsp+260h+var_10]
0x18000cb22  mov     rbx, [r11+30h]
0x18000cb26  mov     rsi, [r11+38h]
0x18000cb2a  mov     rsp, r11
0x18000cb2d  pop     r14
0x18000cb2f  pop     rdi
0x18000cb30  pop     rbp
0x18000cb31  retn
0x18000cb32  cmp     ebx, 8CAh
0x18000cb38  jnz     short loc_18000CB44
0x18000cb3a  mov     ebx, 1
0x18000cb3f  jmp     loc_18000CBDD
0x18000cb44  cmp     ebx, 0EAh
0x18000cb4a  jz      short loc_18000CACF
0x18000cb4c  test    ebx, ebx
0x18000cb4e  jle     loc_18000CBD7
0x18000cb54  movzx   ebx, bx
0x18000cb57  or      ebx, 80070000h
0x18000cb5d  jmp     short loc_18000CBD5
0x18000cb5f  cmp     ebx, 0EAh
0x18000cb65  jnz     short loc_18000CB92
0x18000cb67  lea     r8, [rsp+260h+nLength]; lpnLength
0x18000cb6c  mov     rdx, rax; lpRemoteName
0x18000cb6f  lea     rcx, [rsp+260h+LocalName]; lpLocalName
0x18000cb74  call    cs:__imp_WNetGetConnectionW
0x18000cb7a  mov     ebx, eax
0x18000cb7c  test    eax, eax
0x18000cb7e  jle     short loc_18000CB89
0x18000cb80  movzx   ebx, ax
0x18000cb83  or      ebx, 80070000h
0x18000cb89  test    ebx, ebx
0x18000cb8b  jns     short loc_18000CBA2
0x18000cb8d  jmp     loc_18000CB01
0x18000cb92  lea     r8, [rsp+260h+RemoteName]; unsigned __int16 *
0x18000cb97  mov     rdx, rsi; unsigned __int64
0x18000cb9a  mov     rcx, rax; unsigned __int16 *
0x18000cb9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cba2  mov     rcx, [rdi]; unsigned __int16 *
0x18000cba5  mov     r8, r14; unsigned __int16 *
0x18000cba8  mov     rdx, rsi; unsigned __int64
0x18000cbab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cbb0  jmp     short loc_18000CBD3
0x18000cbb2  mov     rcx, rsi; pszPath
0x18000cbb5  mov     ebx, 800700A1h
0x18000cbba  call    cs:__imp_PathIsUNCW
0x18000cbc0  test    eax, eax
0x18000cbc2  jz      loc_18000CB01
0x18000cbc8  mov     rdx, rsi; unsigned __int16 *
0x18000cbcb  mov     rcx, rdi; unsigned __int16 **
0x18000cbce  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x18000cbd3  mov     ebx, eax
0x18000cbd5  test    ebx, ebx
0x18000cbd7  js      loc_18000CB01
0x18000cbdd  mov     rcx, [rdi]; pszPath
0x18000cbe0  test    rcx, rcx
0x18000cbe3  jz      loc_18000CB09
0x18000cbe9  call    cs:__imp_PathRemoveBackslashW
0x18000cbef  jmp     loc_18000CB09
```

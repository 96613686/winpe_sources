# DecodeCacheFilenameForDisplay(ushort *,ulong,ulong)

- ea: `0x180015cbc`
- end: `0x180015d99`
- name: `?DecodeCacheFilenameForDisplay@@YAXPEAGKK@Z`
- size: `221`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d5d8`

## callees

- `0x180008320`
- `0x18000be40`
- `0x18000bf34`
- `0x180015cbc`
- `0x180026218`
- `0x18002732c`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x180015d08`
- `SHLWAPI!PathFindExtensionW` at `0x180015d08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180015d2a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180015d2a`

## pseudocode

```c
void __fastcall DecodeCacheFilenameForDisplay(unsigned __int16 *a1)
{
  LPWSTR ExtensionW; // rax
  unsigned __int16 *v3; // rdi
  int v4; // r9d
  unsigned int v5; // [rsp+20h] [rbp-478h]
  unsigned int v6[4]; // [rsp+30h] [rbp-468h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-458h] BYREF
  unsigned __int16 v8[264]; // [rsp+250h] [rbp-248h] BYREF

  StringCchCopyW(v8, 0x104u, a1);
  StringCchCopyW(pszPath, 0x104u, a1);
  ExtensionW = PathFindExtensionW(pszPath);
  v3 = ExtensionW;
  if ( ExtensionW && *ExtensionW == 46 )
  {
    *ExtensionW = 0;
    v6[0] = lstrlenW(pszPath) + 1;
    if ( (int)_PrepareURLForDisplayUTF8W(pszPath, a1, v6, v4, v5) < 0 || (*v3 = 46, StringCchCatW(a1, 0x104u, v3) < 0) )
      StringCchCopyW(a1, 0x104u, v8);
    else
      CleanupControlChars(a1);
  }
}

```

## disassembly

```asm
0x180015cbc  push    rbx
0x180015cbe  push    rbp
0x180015cbf  push    rsi
0x180015cc0  push    rdi
0x180015cc1  sub     rsp, 478h
0x180015cc8  mov     rax, cs:__security_cookie
0x180015ccf  xor     rax, rsp
0x180015cd2  mov     [rsp+498h+var_38], rax
0x180015cda  mov     rbx, rcx
0x180015cdd  mov     r8, rcx; unsigned __int16 *
0x180015ce0  mov     ebp, 104h
0x180015ce5  lea     rcx, [rsp+498h+var_248]; unsigned __int16 *
0x180015ced  mov     edx, ebp; unsigned __int64
0x180015cef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015cf4  mov     r8, rbx; unsigned __int16 *
0x180015cf7  lea     rcx, [rsp+498h+pszPath]; unsigned __int16 *
0x180015cfc  mov     edx, ebp; unsigned __int64
0x180015cfe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015d03  lea     rcx, [rsp+498h+pszPath]; pszPath
0x180015d08  call    cs:__imp_PathFindExtensionW
0x180015d0e  mov     rdi, rax
0x180015d11  test    rax, rax
0x180015d14  jz      short loc_180015D7D
0x180015d16  mov     esi, 2Eh ; '.'
0x180015d1b  cmp     [rax], si
0x180015d1e  jnz     short loc_180015D7D
0x180015d20  xor     ecx, ecx
0x180015d22  mov     [rax], cx
0x180015d25  lea     rcx, [rsp+498h+pszPath]; lpString
0x180015d2a  call    cs:__imp_lstrlenW
0x180015d30  lea     r8, [rsp+498h+var_468]; unsigned int *
0x180015d35  mov     rdx, rbx; unsigned __int16 *
0x180015d38  inc     eax
0x180015d3a  lea     rcx, [rsp+498h+pszPath]; unsigned __int16 *
0x180015d3f  mov     [rsp+498h+var_468], eax
0x180015d43  call    ?_PrepareURLForDisplayUTF8W@@YAJPEBGPEAGPEAKHI@Z; _PrepareURLForDisplayUTF8W(ushort const *,ushort *,ulong *,int,uint)
0x180015d48  test    eax, eax
0x180015d4a  js      short loc_180015D6A
0x180015d4c  mov     r8, rdi; unsigned __int16 *
0x180015d4f  mov     [rdi], si
0x180015d52  mov     edx, ebp; unsigned __int64
0x180015d54  mov     rcx, rbx; unsigned __int16 *
0x180015d57  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015d5c  test    eax, eax
0x180015d5e  js      short loc_180015D6A
0x180015d60  mov     rcx, rbx; unsigned __int16 *
0x180015d63  call    ?CleanupControlChars@@YAXPEAG@Z; CleanupControlChars(ushort *)
0x180015d68  jmp     short loc_180015D7D
0x180015d6a  lea     r8, [rsp+498h+var_248]; unsigned __int16 *
0x180015d72  mov     rdx, rbp; unsigned __int64
0x180015d75  mov     rcx, rbx; unsigned __int16 *
0x180015d78  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015d7d  mov     rcx, [rsp+498h+var_38]
0x180015d85  xor     rcx, rsp; StackCookie
0x180015d88  call    __security_check_cookie
0x180015d8d  add     rsp, 478h
0x180015d94  pop     rdi
0x180015d95  pop     rsi
0x180015d96  pop     rbp
0x180015d97  pop     rbx
0x180015d98  retn
```

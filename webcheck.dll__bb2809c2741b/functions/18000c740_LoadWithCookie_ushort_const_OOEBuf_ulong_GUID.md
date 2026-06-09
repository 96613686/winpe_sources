# LoadWithCookie(ushort const *,OOEBuf *,ulong *,_GUID *)

- ea: `0x18000c740`
- end: `0x18000c79d`
- name: `?LoadWithCookie@@YAJPEBGPEAUOOEBuf@@PEAKPEAU_GUID@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(PCWSTR psz2, struct OOEBuf *, unsigned int *, struct _GUID *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004ef0`
- `0x18000e28c`
- `0x18000e500`
- `0x180015fd0`
- `0x18001fba0`

## callees

- `0x18000c740`
- `0x18000e150`

## import_xrefs

- `SHLWAPI!UrlCompareW` at `0x18000c77b`
- `SHLWAPI!UrlCompareW` at `0x18000c77b`

## pseudocode

```c
__int64 __fastcall LoadWithCookie(PCWSTR psz2, struct OOEBuf *a2, unsigned int *a3, struct _GUID *a4)
{
  int OOEntryInfo; // ebx

  OOEntryInfo = LoadOOEntryInfo(a2);
  if ( OOEntryInfo >= 0 && psz2 && UrlCompareW((PCWSTR)a2 + 278, psz2, 1) )
    return (unsigned int)-2147467259;
  return (unsigned int)OOEntryInfo;
}

```

## disassembly

```asm
0x18000c740  mov     [rsp+arg_0], rbx
0x18000c745  mov     [rsp+arg_8], rsi
0x18000c74a  push    rdi
0x18000c74b  sub     rsp, 20h
0x18000c74f  mov     rsi, rdx
0x18000c752  mov     rdi, rcx
0x18000c755  mov     rcx, rsi; struct OOEBuf *
0x18000c758  mov     rdx, r9
0x18000c75b  call    LoadOOEntryInfo
0x18000c760  mov     ebx, eax
0x18000c762  test    eax, eax
0x18000c764  js      short loc_18000C78B
0x18000c766  test    rdi, rdi
0x18000c769  jz      short loc_18000C78B
0x18000c76b  lea     rcx, [rsi+22Ch]; psz1
0x18000c772  mov     r8d, 1; fIgnoreSlash
0x18000c778  mov     rdx, rdi; psz2
0x18000c77b  call    cs:__imp_UrlCompareW
0x18000c781  test    eax, eax
0x18000c783  mov     ecx, 80004005h
0x18000c788  cmovnz  ebx, ecx
0x18000c78b  mov     rsi, [rsp+28h+arg_8]
0x18000c790  mov     eax, ebx
0x18000c792  mov     rbx, [rsp+28h+arg_0]
0x18000c797  add     rsp, 20h
0x18000c79b  pop     rdi
0x18000c79c  retn
```

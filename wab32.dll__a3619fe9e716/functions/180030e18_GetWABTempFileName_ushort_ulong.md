# GetWABTempFileName(ushort *,ulong)

- ea: `0x180030e18`
- end: `0x180030eb9`
- name: `?GetWABTempFileName@@YAXPEAGK@Z`
- size: `161`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030300`

## callees

- `0x1800045e4`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x180030e47`
- `KERNEL32!GetTempPathW` at `0x180030e47`
- `KERNEL32!GetTempFileNameW` at `0x180030e85`
- `KERNEL32!GetTempFileNameW` at `0x180030e85`
- `USER32!LoadStringW` at `0x180030e67`
- `USER32!LoadStringW` at `0x180030e67`

## pseudocode

```c
void __fastcall GetWABTempFileName(unsigned __int16 *a1)
{
  WCHAR Buffer[264]; // [rsp+20h] [rbp-648h] BYREF
  WCHAR PrefixString[264]; // [rsp+230h] [rbp-438h] BYREF
  WCHAR TempFileName[264]; // [rsp+440h] [rbp-228h] BYREF

  Buffer[0] = 0;
  GetTempPathW(0x104u, Buffer);
  LoadStringW(hinstMapiX, 1u, PrefixString, 260);
  GetTempFileNameW(Buffer, PrefixString, 0, TempFileName);
  StringCchCopyW(a1, 0x104u, TempFileName);
}

```

## disassembly

```asm
0x180030e18  push    rbx
0x180030e1a  sub     rsp, 660h
0x180030e21  mov     rax, cs:__security_cookie
0x180030e28  xor     rax, rsp
0x180030e2b  mov     [rsp+668h+var_18], rax
0x180030e33  mov     rbx, rcx
0x180030e36  lea     rdx, [rsp+668h+Buffer]; lpBuffer
0x180030e3b  xor     eax, eax
0x180030e3d  mov     ecx, 104h; nBufferLength
0x180030e42  mov     [rsp+668h+Buffer], ax
0x180030e47  call    cs:__imp_GetTempPathW
0x180030e4d  mov     rcx, cs:hinstMapiX; hInstance
0x180030e54  lea     r8, [rsp+668h+PrefixString]; lpBuffer
0x180030e5c  mov     r9d, 104h; cchBufferMax
0x180030e62  mov     edx, 1; uID
0x180030e67  call    cs:__imp_LoadStringW
0x180030e6d  lea     r9, [rsp+668h+TempFileName]; lpTempFileName
0x180030e75  xor     r8d, r8d; uUnique
0x180030e78  lea     rdx, [rsp+668h+PrefixString]; lpPrefixString
0x180030e80  lea     rcx, [rsp+668h+Buffer]; lpPathName
0x180030e85  call    cs:__imp_GetTempFileNameW
0x180030e8b  lea     r8, [rsp+668h+TempFileName]; unsigned __int16 *
0x180030e93  mov     edx, 104h; unsigned __int64
0x180030e98  mov     rcx, rbx; unsigned __int16 *
0x180030e9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030ea0  mov     rcx, [rsp+668h+var_18]
0x180030ea8  xor     rcx, rsp; StackCookie
0x180030eab  call    __security_check_cookie
0x180030eb0  add     rsp, 660h
0x180030eb7  pop     rbx
0x180030eb8  retn
```

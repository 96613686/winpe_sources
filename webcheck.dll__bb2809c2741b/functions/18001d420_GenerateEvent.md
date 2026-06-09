# _GenerateEvent

- ea: `0x18001d420`
- end: `0x18001d4d6`
- name: `_GenerateEvent`
- size: `182`
- prototype: `__int64 __fastcall(LONG wEventId, LPCITEMIDLIST pidl2)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a7fc`
- `0x18000e500`
- `0x18000f2c0`
- `0x180015fd0`
- `0x1800170c8`
- `0x1800173f0`

## callees

- `0x18001bbd8`
- `0x18001bc9c`
- `0x18001d420`
- `0x180029280`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18001d493`
- `SHELL32!SHChangeNotify` at `0x18001d4a6`
- `SHELL32!SHChangeNotify` at `0x18001d493`
- `SHELL32!SHChangeNotify` at `0x18001d4a6`
- `SHELL32!__imp_ILCombine` at `0x18001d47b`
- `SHELL32!__imp_ILCombine` at `0x18001d47b`
- `SHELL32!__imp_ILFree` at `0x18001d4af`
- `SHELL32!__imp_ILFree` at `0x18001d4af`

## pseudocode

```c
void __fastcall GenerateEvent(LONG wEventId, LPCITEMIDLIST pidl2)
{
  const ITEMIDLIST *v4; // rcx
  struct _ITEMIDLIST **v5; // rdx
  LPITEMIDLIST v6; // rax
  ITEMIDLIST *v7; // rbx
  WCHAR pszPathOut[264]; // [rsp+20h] [rbp-228h] BYREF

  v4 = pidl1;
  if ( pidl1
    || (unsigned int)GetSubscriptionFolderPath(pszPathOut)
    && (int)ConvertPathToPidl(pszPathOut, v5) >= 0
    && (v4 = pidl1) != 0 )
  {
    v6 = ILCombine(v4, pidl2);
    v7 = v6;
    if ( v6 )
    {
      SHChangeNotify(wEventId, 0, v6, 0);
      SHChangeNotify(0, 0x1000u, 0, 0);
      ILFree(v7);
    }
  }
}

```

## disassembly

```asm
0x18001d420  mov     [rsp+arg_10], rbx
0x18001d425  push    rdi
0x18001d426  sub     rsp, 240h
0x18001d42d  mov     rax, cs:__security_cookie
0x18001d434  xor     rax, rsp
0x18001d437  mov     [rsp+248h+var_18], rax
0x18001d43f  mov     edi, ecx
0x18001d441  mov     rbx, rdx
0x18001d444  mov     rcx, cs:pidl1
0x18001d44b  test    rcx, rcx
0x18001d44e  jnz     short loc_18001D478
0x18001d450  lea     rcx, [rsp+248h+pszPathOut]; pszPathOut
0x18001d455  call    ?GetSubscriptionFolderPath@@YAHPEAGK@Z; GetSubscriptionFolderPath(ushort *,ulong)
0x18001d45a  test    eax, eax
0x18001d45c  jz      short loc_18001D4B5
0x18001d45e  lea     rcx, [rsp+248h+pszPathOut]; unsigned __int16 *
0x18001d463  call    ?ConvertPathToPidl@@YAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; ConvertPathToPidl(ushort const *,_ITEMIDLIST * *)
0x18001d468  test    eax, eax
0x18001d46a  js      short loc_18001D4B5
0x18001d46c  mov     rcx, cs:pidl1; pidl1
0x18001d473  test    rcx, rcx
0x18001d476  jz      short loc_18001D4B5
0x18001d478  mov     rdx, rbx; pidl2
0x18001d47b  call    cs:__imp_ILCombine
0x18001d481  mov     rbx, rax
0x18001d484  test    rax, rax
0x18001d487  jz      short loc_18001D4B5
0x18001d489  xor     r9d, r9d; dwItem2
0x18001d48c  mov     r8, rax; dwItem1
0x18001d48f  xor     edx, edx; uFlags
0x18001d491  mov     ecx, edi; wEventId
0x18001d493  call    cs:__imp_SHChangeNotify
0x18001d499  xor     r9d, r9d; dwItem2
0x18001d49c  xor     r8d, r8d; dwItem1
0x18001d49f  mov     edx, 1000h; uFlags
0x18001d4a4  xor     ecx, ecx; wEventId
0x18001d4a6  call    cs:__imp_SHChangeNotify
0x18001d4ac  mov     rcx, rbx; pidl
0x18001d4af  call    cs:__imp_ILFree
0x18001d4b5  mov     rcx, [rsp+248h+var_18]
0x18001d4bd  xor     rcx, rsp; StackCookie
0x18001d4c0  call    __security_check_cookie
0x18001d4c5  mov     rbx, [rsp+248h+arg_10]
0x18001d4cd  add     rsp, 240h
0x18001d4d4  pop     rdi
0x18001d4d5  retn
```

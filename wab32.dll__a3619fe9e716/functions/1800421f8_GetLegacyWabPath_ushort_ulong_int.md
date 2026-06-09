# GetLegacyWabPath(ushort *,ulong,int)

- ea: `0x1800421f8`
- end: `0x1800422b2`
- name: `?GetLegacyWabPath@@YAJPEAGKH@Z`
- size: `186`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002ff20`

## callees

- `0x1800045e4`
- `0x1800421f8`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x18004225f`
- `SHLWAPI!PathAppendW` at `0x18004225f`
- `SHELL32!SHGetFolderPathW` at `0x18004223e`
- `SHELL32!SHGetFolderPathW` at `0x18004223e`
- `KERNEL32!GetFileAttributesW` at `0x18004226a`
- `KERNEL32!GetFileAttributesW` at `0x18004226a`

## pseudocode

```c
__int64 __fastcall GetLegacyWabPath(unsigned __int16 *a1)
{
  HRESULT v2; // eax
  int v3; // ecx
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(FileName, 0, 0x208u);
  v2 = SHGetFolderPathW(0, 26, 0, 0, FileName);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 >= 0 )
      return (unsigned int)-2147418113;
  }
  else
  {
    PathAppendW(FileName, L"Microsoft\\Address Book\\");
    if ( GetFileAttributesW(FileName) == -1 )
    {
      return 1;
    }
    else
    {
      v3 = StringCchCopyW(a1, 0x104u, FileName);
      if ( v3 >= 0 )
        return 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800421f8  push    rbx
0x1800421fa  sub     rsp, 250h
0x180042201  mov     rax, cs:__security_cookie
0x180042208  xor     rax, rsp
0x18004220b  mov     [rsp+258h+var_18], rax
0x180042213  mov     rbx, rcx
0x180042216  xor     edx, edx; Val
0x180042218  lea     rcx, [rsp+258h+FileName]; void *
0x18004221d  mov     r8d, 208h; Size
0x180042223  call    memset_0
0x180042228  xor     r9d, r9d; dwFlags
0x18004222b  lea     rax, [rsp+258h+FileName]
0x180042230  xor     r8d, r8d; hToken
0x180042233  mov     [rsp+258h+pszPath], rax; pszPath
0x180042238  xor     ecx, ecx; hwnd
0x18004223a  lea     edx, [r9+1Ah]; csidl
0x18004223e  call    cs:__imp_SHGetFolderPathW
0x180042244  mov     ecx, eax
0x180042246  test    eax, eax
0x180042248  jz      short loc_180042253
0x18004224a  js      short loc_180042297
0x18004224c  mov     ecx, 8000FFFFh
0x180042251  jmp     short loc_180042297
0x180042253  lea     rdx, aMicrosoftAddre; "Microsoft\\Address Book\\"
0x18004225a  lea     rcx, [rsp+258h+FileName]; pszPath
0x18004225f  call    cs:__imp_PathAppendW
0x180042265  lea     rcx, [rsp+258h+FileName]; lpFileName
0x18004226a  call    cs:__imp_GetFileAttributesW
0x180042270  cmp     eax, 0FFFFFFFFh
0x180042273  jnz     short loc_18004227C
0x180042275  mov     ecx, 1
0x18004227a  jmp     short loc_180042297
0x18004227c  lea     r8, [rsp+258h+FileName]; unsigned __int16 *
0x180042281  mov     edx, 104h; unsigned __int64
0x180042286  mov     rcx, rbx; unsigned __int16 *
0x180042289  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004228e  mov     ecx, eax
0x180042290  xor     eax, eax
0x180042292  test    ecx, ecx
0x180042294  cmovns  ecx, eax
0x180042297  mov     eax, ecx
0x180042299  mov     rcx, [rsp+258h+var_18]
0x1800422a1  xor     rcx, rsp; StackCookie
0x1800422a4  call    __security_check_cookie
0x1800422a9  add     rsp, 250h
0x1800422b0  pop     rbx
0x1800422b1  retn
```

# CUrlDownload_BSC::OnStopBinding(long,ushort const *)

- ea: `0x180007ce0`
- end: `0x180007de2`
- name: `?OnStopBinding@CUrlDownload_BSC@@UEAAJJPEBG@Z`
- size: `258`
- prototype: `__int64 __fastcall(CUrlDownload_BSC *__hidden this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x180003950`
- `0x18000601c`
- `0x180007ce0`
- `0x180027384`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180007d87`
- `KERNEL32!CopyFileW` at `0x180007d87`
- `SHLWAPI!PathFindFileNameW` at `0x180007d4d`
- `SHLWAPI!PathFindFileNameW` at `0x180007d4d`
- `SHLWAPI!PathIsDirectoryW` at `0x180007d3e`
- `SHLWAPI!PathIsDirectoryW` at `0x180007d3e`

## pseudocode

```c
__int64 __fastcall CUrlDownload_BSC::OnStopBinding(CUrlDownload_BSC *this, int a2, const unsigned __int16 *a3)
{
  CUrlDownload *v4; // rcx
  struct IStream *v5; // r8
  const unsigned __int16 *v6; // r8
  const WCHAR *FileNameW; // rax
  size_t v8; // rdx
  WCHAR *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  ULONG v13; // [rsp+20h] [rbp-448h]
  WCHAR pszPath[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR pszPathOut[264]; // [rsp+240h] [rbp-228h] BYREF

  v4 = (CUrlDownload *)*((_QWORD *)this + 10);
  if ( v4 )
  {
    if ( (*((_BYTE *)this + 68) & 1) != 0 )
      v5 = (struct IStream *)*((_QWORD *)this + 5);
    else
      v5 = 0;
    CUrlDownload::BSC_OnStopBinding(v4, a2, v5);
  }
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 7);
  if ( v6 && *((_QWORD *)this + 6) )
  {
    StringCchCopyW(pszPath, 0x104u, v6);
    if ( PathIsDirectoryW(*((LPCWSTR *)this + 6)) )
    {
      FileNameW = PathFindFileNameW(pszPath);
      if ( !FileNameW )
        goto LABEL_13;
      PathCchCombineEx(pszPathOut, v8, *((PCWSTR *)this + 6), FileNameW, v13);
      v9 = pszPathOut;
    }
    else
    {
      v9 = (WCHAR *)*((_QWORD *)this + 6);
      if ( !v9 )
        goto LABEL_13;
    }
    CopyFileW(pszPath, v9, 0);
  }
LABEL_13:
  v10 = *((_QWORD *)this + 5);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 5) = 0;
  }
  v11 = *((_QWORD *)this + 4);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)this + 4) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180007ce0  push    rbx
0x180007ce2  sub     rsp, 460h
0x180007ce9  mov     rax, cs:__security_cookie
0x180007cf0  xor     rax, rsp
0x180007cf3  mov     [rsp+468h+var_18], rax
0x180007cfb  mov     rbx, rcx
0x180007cfe  mov     rcx, [rcx+50h]; this
0x180007d02  test    rcx, rcx
0x180007d05  jz      short loc_180007D1B
0x180007d07  test    byte ptr [rbx+44h], 1
0x180007d0b  jz      short loc_180007D13
0x180007d0d  mov     r8, [rbx+28h]
0x180007d11  jmp     short loc_180007D16
0x180007d13  xor     r8d, r8d; struct IStream *
0x180007d16  call    ?BSC_OnStopBinding@CUrlDownload@@IEAAXJPEAUIStream@@@Z; CUrlDownload::BSC_OnStopBinding(long,IStream *)
0x180007d1b  mov     r8, [rbx+38h]; unsigned __int16 *
0x180007d1f  test    r8, r8
0x180007d22  jz      short loc_180007D8D
0x180007d24  cmp     qword ptr [rbx+30h], 0
0x180007d29  jz      short loc_180007D8D
0x180007d2b  mov     edx, 104h; unsigned __int64
0x180007d30  lea     rcx, [rsp+468h+pszPath]; unsigned __int16 *
0x180007d35  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007d3a  mov     rcx, [rbx+30h]; pszPath
0x180007d3e  call    cs:__imp_PathIsDirectoryW
0x180007d44  test    eax, eax
0x180007d46  jz      short loc_180007D76
0x180007d48  lea     rcx, [rsp+468h+pszPath]; pszPath
0x180007d4d  call    cs:__imp_PathFindFileNameW
0x180007d53  test    rax, rax
0x180007d56  jz      short loc_180007D8D
0x180007d58  mov     r8, [rbx+30h]; pszPathIn
0x180007d5c  lea     rcx, [rsp+468h+pszPathOut]; pszPathOut
0x180007d64  mov     r9, rax; pszMore
0x180007d67  call    PathCchCombineEx
0x180007d6c  lea     rdx, [rsp+468h+pszPathOut]
0x180007d74  jmp     short loc_180007D7F
0x180007d76  mov     rdx, [rbx+30h]; lpNewFileName
0x180007d7a  test    rdx, rdx
0x180007d7d  jz      short loc_180007D8D
0x180007d7f  xor     r8d, r8d; bFailIfExists
0x180007d82  lea     rcx, [rsp+468h+pszPath]; lpExistingFileName
0x180007d87  call    cs:__imp_CopyFileW
0x180007d8d  mov     rcx, [rbx+28h]
0x180007d91  test    rcx, rcx
0x180007d94  jz      short loc_180007DAA
0x180007d96  mov     rax, [rcx]
0x180007d99  mov     rax, [rax+10h]
0x180007d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da2  mov     qword ptr [rbx+28h], 0
0x180007daa  mov     rcx, [rbx+20h]
0x180007dae  test    rcx, rcx
0x180007db1  jz      short loc_180007DC7
0x180007db3  mov     rax, [rcx]
0x180007db6  mov     rax, [rax+10h]
0x180007dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dbf  mov     qword ptr [rbx+20h], 0
0x180007dc7  xor     eax, eax
0x180007dc9  mov     rcx, [rsp+468h+var_18]
0x180007dd1  xor     rcx, rsp; StackCookie
0x180007dd4  call    __security_check_cookie
0x180007dd9  add     rsp, 460h
0x180007de0  pop     rbx
0x180007de1  retn
```

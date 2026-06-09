# CDataDirectoryPolicy::ApplyPolicy(int *,int *)

- ea: `0x180012a30`
- end: `0x180012b67`
- name: `?ApplyPolicy@CDataDirectoryPolicy@@UEAAJPEAH0@Z`
- size: `311`
- prototype: `__int64 __fastcall(CDataDirectoryPolicy *__hidden this, int *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000564c`
- `0x180012a30`
- `0x180014374`
- `0x18001a828`
- `0x18001cb38`

## import_xrefs

- `SHLWAPI!PathRemoveBackslashW` at `0x180012aa4`
- `SHLWAPI!PathRemoveBackslashW` at `0x180012aa4`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012aaf`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012aaf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012ade`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012b16`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012ade`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012b16`

## string_xrefs

- `0x180012a76`: `DataDirectory`

## pseudocode

```c
__int64 __fastcall CDataDirectoryPolicy::ApplyPolicy(CDataDirectoryPolicy *this, int *a2, int *a3)
{
  CRegValue *v3; // rbx
  __int64 result; // rax
  const WCHAR *lpString2; // rax
  __int64 v8; // rdx
  LPWSTR pszPath; // [rsp+50h] [rbp+8h] BYREF

  v3 = (CDataDirectoryPolicy *)((char *)this + 56);
  *a2 = 0;
  *a3 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    if ( !*(_DWORD *)v3 )
    {
      pszPath = 0;
      result = GetRegDwordOrString(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows Search",
                 L"DataDirectory",
                 1u,
                 0,
                 &pszPath);
      if ( (int)result < 0 )
        return result;
      PathRemoveBackslashW(pszPath);
      PathRemoveFileSpecW(pszPath);
      if ( *((_DWORD *)this + 4) )
        lpString2 = (const WCHAR *)*((_QWORD *)this + 6);
      else
        lpString2 = 0;
      if ( CompareStringW(0x7Fu, 1u, pszPath, -1, lpString2, -1) != 2 )
        *a2 = 1;
      operator delete(pszPath);
      goto LABEL_16;
    }
    if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)this + 11), -1, *((PCNZWCH *)this + 6), -1) == 2 )
      return 0;
  }
  else
  {
    result = 0;
    if ( !*(_DWORD *)v3 )
      return result;
  }
  if ( !*((_DWORD *)this + 4) )
    return CRegValue::Delete(v3);
  *a2 = 1;
LABEL_16:
  if ( *((_DWORD *)this + 4) )
    v8 = *((_QWORD *)this + 6);
  else
    v8 = 0;
  return CTRegValue<unsigned short *>::Set(v3, v8);
}

```

## disassembly

```asm
0x180012a30  mov     r11, rsp
0x180012a33  mov     [r11+10h], rbx
0x180012a37  mov     [r11+18h], rbp
0x180012a3b  push    rdi
0x180012a3c  push    r14
0x180012a3e  push    r15
0x180012a40  sub     rsp, 30h
0x180012a44  xor     ebp, ebp
0x180012a46  lea     rbx, [rcx+38h]
0x180012a4a  mov     [rdx], ebp
0x180012a4c  mov     r14, rdx
0x180012a4f  mov     [r8], ebp
0x180012a52  mov     rdi, rcx
0x180012a55  lea     r15d, [rbp+1]
0x180012a59  cmp     [rcx+10h], ebp
0x180012a5c  jz      loc_180012B25
0x180012a62  cmp     [rbx], ebp
0x180012a64  jnz     loc_180012AF8
0x180012a6a  lea     rax, [r11+8]
0x180012a6e  mov     [r11+8], rbp
0x180012a72  mov     [r11-20h], rax
0x180012a76  lea     r8, aDatadirectory; "DataDirectory"
0x180012a7d  mov     r9d, r15d; unsigned int
0x180012a80  mov     [r11-28h], rbp
0x180012a84  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Search"
0x180012a8b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180012a92  call    ?GetRegDwordOrString@@YAJPEAUHKEY__@@PEBG1KPEAKPEAPEAG@Z; GetRegDwordOrString(HKEY__ *,ushort const *,ushort const *,ulong,ulong *,ushort * *)
0x180012a97  test    eax, eax
0x180012a99  js      loc_180012B53
0x180012a9f  mov     rcx, [rsp+48h+pszPath]; pszPath
0x180012aa4  call    cs:__imp_PathRemoveBackslashW
0x180012aaa  mov     rcx, [rsp+48h+pszPath]; pszPath
0x180012aaf  call    cs:__imp_PathRemoveFileSpecW
0x180012ab5  cmp     [rdi+10h], ebp
0x180012ab8  jz      short loc_180012AC0
0x180012aba  mov     rax, [rdi+30h]
0x180012abe  jmp     short loc_180012AC3
0x180012ac0  mov     rax, rbp
0x180012ac3  mov     r8, [rsp+48h+pszPath]; lpString1
0x180012ac8  or      r9d, 0FFFFFFFFh; cchCount1
0x180012acc  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180012ad1  mov     edx, r15d; dwCmpFlags
0x180012ad4  mov     ecx, 7Fh; Locale
0x180012ad9  mov     [rsp+48h+lpString2], rax; lpString2
0x180012ade  call    cs:__imp_CompareStringW
0x180012ae4  cmp     eax, 2
0x180012ae7  jz      short loc_180012AEC
0x180012ae9  mov     [r14], r15d
0x180012aec  mov     rcx, [rsp+48h+pszPath]; lpMem
0x180012af1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012af6  jmp     short loc_180012B3D
0x180012af8  mov     rax, [rcx+30h]
0x180012afc  or      r9d, 0FFFFFFFFh; cchCount1
0x180012b00  mov     r8, [rbx+20h]; lpString1
0x180012b04  mov     edx, r15d; dwCmpFlags
0x180012b07  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180012b0c  mov     ecx, 7Fh; Locale
0x180012b11  mov     [rsp+48h+lpString2], rax; lpString2
0x180012b16  call    cs:__imp_CompareStringW
0x180012b1c  cmp     eax, 2
0x180012b1f  jnz     short loc_180012B2B
0x180012b21  mov     eax, ebp
0x180012b23  jmp     short loc_180012B53
0x180012b25  mov     eax, ebp
0x180012b27  cmp     [rbx], ebp
0x180012b29  jz      short loc_180012B53
0x180012b2b  cmp     [rdi+10h], ebp
0x180012b2e  jnz     short loc_180012B3A
0x180012b30  mov     rcx, rbx; this
0x180012b33  call    ?Delete@CRegValue@@QEAAJXZ; CRegValue::Delete(void)
0x180012b38  jmp     short loc_180012B53
0x180012b3a  mov     [r14], r15d
0x180012b3d  cmp     [rdi+10h], ebp
0x180012b40  jz      short loc_180012B48
0x180012b42  mov     rdx, [rdi+30h]
0x180012b46  jmp     short loc_180012B4B
0x180012b48  mov     rdx, rbp
0x180012b4b  mov     rcx, rbx
0x180012b4e  call    ?Set@?$CTRegValue@PEAG@@QEAAJQEAG@Z; CTRegValue<ushort *>::Set(ushort * const)
0x180012b53  mov     rbx, [rsp+48h+arg_8]
0x180012b58  mov     rbp, [rsp+48h+arg_10]
0x180012b5d  add     rsp, 30h
0x180012b61  pop     r15
0x180012b63  pop     r14
0x180012b65  pop     rdi
0x180012b66  retn
```

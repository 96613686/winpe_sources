# CZipFolder::_AssocCreate(CArchiveIDList const *,_GUID const &,void * *)

- ea: `0x180013904`
- end: `0x1800139f3`
- name: `?_AssocCreate@CZipFolder@@AEAAJPEBVCArchiveIDList@@AEBU_GUID@@PEAPEAX@Z`
- size: `239`
- prototype: `__int64 __fastcall(CZipFolder *this, const struct CArchiveIDList *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012de0`

## callees

- `0x18000f5f0`
- `0x180013904`
- `0x180036f50`

## import_xrefs

- `SHELL32!AssocCreateForClasses` at `0x1800139ae`
- `SHELL32!AssocCreateForClasses` at `0x1800139ae`
- `SHLWAPI!PathFindExtensionW` at `0x180013972`
- `SHLWAPI!PathFindExtensionW` at `0x180013972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139cb`

## pseudocode

```c
__int64 __fastcall CZipFolder::_AssocCreate(
        CZipFolder *this,
        const struct CArchiveIDList *a2,
        const struct _GUID *a3,
        void **a4)
{
  bool v5; // zf
  WCHAR *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  LPWSTR ExtensionW; // rax
  ULONG v11; // edx
  LPCWSTR pszPath[2]; // [rsp+20h] [rbp-50h] BYREF
  _BYTE rgClasses[32]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-20h]

  *a4 = 0;
  v5 = (*((_BYTE *)a2 + 32) & 0x10) == 0;
  memset(rgClasses, 0, sizeof(rgClasses));
  v15 = 0;
  *(_OWORD *)pszPath = 0;
  if ( !v5 )
  {
    v7 = (WCHAR *)pszPath[0];
    *(_DWORD *)rgClasses = 8;
    goto LABEL_8;
  }
  v8 = CTempAlignedString::Set((CTempAlignedString *)pszPath, (const unsigned __int16 *)a2 + 46);
  v7 = (WCHAR *)pszPath[0];
  v9 = v8;
  if ( v8 >= 0 )
  {
    ExtensionW = PathFindExtensionW(pszPath[0]);
    if ( ExtensionW && *ExtensionW )
    {
      v11 = 2;
      *(_QWORD *)&rgClasses[16] = ExtensionW;
      *(_DWORD *)rgClasses = 2;
      *(_DWORD *)&rgClasses[24] = 9;
LABEL_9:
      v9 = AssocCreateForClasses((const ASSOCIATIONELEMENT *)rgClasses, v11, a3, a4);
      goto LABEL_10;
    }
    *(_DWORD *)rgClasses = 9;
LABEL_8:
    v11 = 1;
    goto LABEL_9;
  }
LABEL_10:
  if ( v7 != pszPath[1] && v7 != &psz )
    LocalFree(v7);
  return v9;
}

```

## disassembly

```asm
0x180013904  mov     [rsp-28h+arg_0], rbx
0x180013909  push    rbp
0x18001390a  push    rsi
0x18001390b  push    rdi
0x18001390c  push    r14
0x18001390e  push    r15
0x180013910  mov     rbp, rsp
0x180013913  sub     rsp, 70h
0x180013917  mov     rax, cs:__security_cookie
0x18001391e  xor     rax, rsp
0x180013921  mov     [rbp+var_10], rax
0x180013925  xorps   xmm0, xmm0
0x180013928  xor     r15d, r15d
0x18001392b  mov     [r9], r15
0x18001392e  mov     rsi, r9
0x180013931  test    byte ptr [rdx+20h], 10h
0x180013935  mov     r14, r8
0x180013938  movups  xmmword ptr [rbp+rgClasses], xmm0
0x18001393c  movups  xmmword ptr [rbp+rgClasses+10h], xmm0
0x180013940  movups  [rbp+var_20], xmm0
0x180013944  movdqu  xmmword ptr [rbp+pszPath], xmm0
0x180013949  jz      short loc_180013958
0x18001394b  mov     rbx, [rbp+pszPath]
0x18001394f  mov     dword ptr [rbp+rgClasses], 8
0x180013956  jmp     short loc_18001399F
0x180013958  add     rdx, 5Ch ; '\'; unsigned __int16 *
0x18001395c  lea     rcx, [rbp+pszPath]; this
0x180013960  call    ?Set@CTempAlignedString@@QEAAJPEFBG@Z; CTempAlignedString::Set(ushort const *)
0x180013965  mov     rbx, [rbp+pszPath]
0x180013969  mov     edi, eax
0x18001396b  test    eax, eax
0x18001396d  js      short loc_1800139B6
0x18001396f  mov     rcx, rbx; pszPath
0x180013972  call    cs:__imp_PathFindExtensionW
0x180013978  test    rax, rax
0x18001397b  jz      short loc_180013998
0x18001397d  cmp     [rax], r15w
0x180013981  jz      short loc_180013998
0x180013983  mov     edx, 2
0x180013988  mov     qword ptr [rbp+rgClasses+10h], rax
0x18001398c  mov     dword ptr [rbp+rgClasses], edx
0x18001398f  mov     dword ptr [rbp+rgClasses+18h], 9
0x180013996  jmp     short loc_1800139A4
0x180013998  mov     dword ptr [rbp+rgClasses], 9
0x18001399f  mov     edx, 1; cClasses
0x1800139a4  mov     r9, rsi; ppv
0x1800139a7  lea     rcx, [rbp+rgClasses]; rgClasses
0x1800139ab  mov     r8, r14; riid
0x1800139ae  call    cs:__imp_AssocCreateForClasses
0x1800139b4  mov     edi, eax
0x1800139b6  cmp     rbx, [rbp+pszPath+8]
0x1800139ba  jz      short loc_1800139D1
0x1800139bc  lea     rax, psz
0x1800139c3  cmp     rbx, rax
0x1800139c6  jz      short loc_1800139D1
0x1800139c8  mov     rcx, rbx; hMem
0x1800139cb  call    cs:__imp_LocalFree
0x1800139d1  mov     eax, edi
0x1800139d3  mov     rcx, [rbp+var_10]
0x1800139d7  xor     rcx, rsp; StackCookie
0x1800139da  call    __security_check_cookie
0x1800139df  mov     rbx, [rsp+70h+arg_0]
0x1800139e7  add     rsp, 70h
0x1800139eb  pop     r15
0x1800139ed  pop     r14
0x1800139ef  pop     rdi
0x1800139f0  pop     rsi
0x1800139f1  pop     rbp
0x1800139f2  retn
```

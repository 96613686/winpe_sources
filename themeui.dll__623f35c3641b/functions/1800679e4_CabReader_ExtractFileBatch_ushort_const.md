# CabReader::ExtractFileBatch(ushort const *)

- ea: `0x1800679e4`
- end: `0x180067b32`
- name: `?ExtractFileBatch@CabReader@@QEAAJPEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(CabReader *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180062f3c`
- `0x180065a90`

## callees

- `0x18000ab10`
- `0x1800179e0`
- `0x1800358c0`
- `0x1800679e4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180067ae8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180067ae8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180067ad9`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180067ad9`
- `Cabinet!__imp_FDICopy` at `0x180067a7c`
- `Cabinet!__imp_FDICopy` at `0x180067a7c`

## pseudocode

```c
__int64 __fastcall CabReader::ExtractFileBatch(CabReader *this, const unsigned __int16 *a2)
{
  int v4; // edi
  void *v5; // rcx
  unsigned int i; // esi
  PVOID Ptr; // rax
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return (unsigned int)-2147467261;
  v4 = StringCchCopyW((unsigned __int16 *)this + 530, 0x104u, a2);
  if ( v4 >= 0 )
  {
    v5 = *(void **)this;
    *((_QWORD *)this + 263) = CabReader::FdiCopyFileBatch;
    *((_DWORD *)this + 530) = 0;
    *((_BYTE *)this + 2144) = 0;
    if ( FDICopy(v5, (LPSTR)this + 280, (LPSTR)this + 20, 0, (PFNFDINOTIFY)CabReader::FdiCabNotify, 0, this) )
    {
      v4 = 0;
      if ( !*((_BYTE *)this + 2144) )
        return (unsigned int)v4;
    }
    else
    {
      v4 = -2147467259;
    }
    for ( i = 0; i < *((_DWORD *)this + 530); ++i )
    {
      Ptr = g_pfn_DPA_GetPtr(*((HDPA *)this + 264), i);
      if ( Ptr
        && *((_DWORD *)Ptr + 133)
        && *((_DWORD *)Ptr + 134)
        && PathCchCombine(pszPathOut, 0x104u, a2, (PCWSTR)Ptr + 2) >= 0 )
      {
        DeleteFileW(pszPathOut);
      }
    }
    if ( *((_BYTE *)this + 2144) )
      return (unsigned int)-2147023673;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800679e4  mov     [rsp+arg_10], rbx
0x1800679e9  push    rbp
0x1800679ea  push    rsi
0x1800679eb  push    rdi
0x1800679ec  sub     rsp, 260h
0x1800679f3  mov     rax, cs:__security_cookie
0x1800679fa  xor     rax, rsp
0x1800679fd  mov     [rsp+278h+var_28], rax
0x180067a05  mov     rbp, rdx
0x180067a08  mov     rbx, rcx
0x180067a0b  test    rdx, rdx
0x180067a0e  jz      loc_180067B08
0x180067a14  mov     r8, rdx; unsigned __int16 *
0x180067a17  add     rcx, 424h; unsigned __int16 *
0x180067a1e  mov     edx, 104h; unsigned __int64
0x180067a23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180067a28  mov     edi, eax
0x180067a2a  test    eax, eax
0x180067a2c  js      loc_180067B0D
0x180067a32  mov     rcx, [rbx]; hfdi
0x180067a35  lea     rax, ?FdiCopyFileBatch@CabReader@@CA_JPEAUFDINOTIFICATION@@@Z; CabReader::FdiCopyFileBatch(FDINOTIFICATION *)
0x180067a3c  mov     [rbx+838h], rax
0x180067a43  lea     r8, [rbx+14h]; pszCabPath
0x180067a47  lea     rax, ?FdiCabNotify@CabReader@@CA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; CabReader::FdiCabNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x180067a4e  mov     [rsp+278h+pvUser], rbx; pvUser
0x180067a53  lea     rdx, [rbx+118h]; pszCabinet
0x180067a5a  mov     [rsp+278h+pfnfdid], 0; pfnfdid
0x180067a63  xor     r9d, r9d; flags
0x180067a66  mov     [rsp+278h+pfnfdin], rax; pfnfdin
0x180067a6b  mov     dword ptr [rbx+848h], 0
0x180067a75  mov     byte ptr [rbx+860h], 0
0x180067a7c  call    cs:__imp_FDICopy
0x180067a82  test    eax, eax
0x180067a84  jz      short loc_180067A93
0x180067a86  xor     edi, edi
0x180067a88  cmp     [rbx+860h], dil
0x180067a8f  jz      short loc_180067B0D
0x180067a91  jmp     short loc_180067A98
0x180067a93  mov     edi, 80004005h
0x180067a98  xor     esi, esi
0x180067a9a  cmp     [rbx+848h], esi
0x180067aa0  jbe     short loc_180067AF8
0x180067aa2  mov     rcx, [rbx+840h]; hdpa
0x180067aa9  mov     edx, esi; i
0x180067aab  call    cs:g_pfn_DPA_GetPtr
0x180067ab1  test    rax, rax
0x180067ab4  jz      short loc_180067AEE
0x180067ab6  cmp     dword ptr [rax+214h], 0
0x180067abd  jz      short loc_180067AEE
0x180067abf  cmp     dword ptr [rax+218h], 0
0x180067ac6  jz      short loc_180067AEE
0x180067ac8  lea     r9, [rax+4]; pszMore
0x180067acc  mov     r8, rbp; pszPathIn
0x180067acf  mov     edx, 104h; cchPathOut
0x180067ad4  lea     rcx, [rsp+278h+pszPathOut]; pszPathOut
0x180067ad9  call    cs:__imp_PathCchCombine
0x180067adf  test    eax, eax
0x180067ae1  js      short loc_180067AEE
0x180067ae3  lea     rcx, [rsp+278h+pszPathOut]; lpFileName
0x180067ae8  call    cs:__imp_DeleteFileW
0x180067aee  inc     esi
0x180067af0  cmp     esi, [rbx+848h]
0x180067af6  jb      short loc_180067AA2
0x180067af8  cmp     byte ptr [rbx+860h], 0
0x180067aff  jz      short loc_180067B0D
0x180067b01  mov     edi, 800704C7h
0x180067b06  jmp     short loc_180067B0D
0x180067b08  mov     edi, 80004003h
0x180067b0d  mov     eax, edi
0x180067b0f  mov     rcx, [rsp+278h+var_28]
0x180067b17  xor     rcx, rsp; StackCookie
0x180067b1a  call    __security_check_cookie
0x180067b1f  mov     rbx, [rsp+278h+arg_10]
0x180067b27  add     rsp, 260h
0x180067b2e  pop     rdi
0x180067b2f  pop     rsi
0x180067b30  pop     rbp
0x180067b31  retn
```

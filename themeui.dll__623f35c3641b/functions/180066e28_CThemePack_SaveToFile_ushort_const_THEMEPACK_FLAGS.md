# CThemePack::SaveToFile(ushort const *,THEMEPACK_FLAGS)

- ea: `0x180066e28`
- end: `0x180066fc8`
- name: `?SaveToFile@CThemePack@@QEAAJPEBGW4THEMEPACK_FLAGS@@@Z`
- size: `416`
- prototype: `int __high(const unsigned __int16 *, enum THEMEPACK_FLAGS)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180062c40`
- `0x180064a10`

## callees

- `0x18000ab10`
- `0x1800179e0`
- `0x180066e28`
- `0x18006919c`
- `0x180069318`
- `0x1800693c4`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180066ea6`
- `SHLWAPI!PathFindFileNameW` at `0x180066ea6`
- `SHLWAPI!StrTrimW` at `0x180066ed3`
- `SHLWAPI!StrTrimW` at `0x180066ed3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180066fa5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180066fa5`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x180066ee8`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x180066ee8`

## pseudocode

```c
__int64 __fastcall CThemePack::SaveToFile(__int64 a1, const unsigned __int16 *a2, unsigned int a3)
{
  CabWriter *v5; // r14
  int Cab; // edi
  struct _DPA *v7; // rcx
  int v8; // esi
  char *Ptr; // rdi
  WCHAR *v10; // r15
  const unsigned __int16 *FileNameW; // rax
  int i; // edi
  PVOID v13; // r15
  unsigned int (__fastcall *v14)(__int64, _QWORD, _QWORD, _QWORD); // rax
  __int64 v15; // rcx

  if ( a2 )
  {
    *(_DWORD *)(a1 + 2028) = 0;
    v5 = (CabWriter *)(a1 + 104);
    Cab = CabWriter::CreateCab(a1 + 104, a2, (a3 >> 1) & 2 | ((a3 & 3) != 0));
    if ( Cab >= 0 )
    {
      v7 = *(struct _DPA **)a1;
      if ( *(_QWORD *)a1 )
      {
        v8 = *(_DWORD *)v7;
        if ( *(int *)v7 > 0 )
        {
          Ptr = (char *)g_pfn_DPA_GetPtr(v7, 0);
          v10 = (WCHAR *)(Ptr + 528);
          FileNameW = PathFindFileNameW(a2);
          if ( (int)StringCchCopyW((unsigned __int16 *)Ptr + 264, 0x104u, FileNameW) >= 0 )
          {
            *((_WORD *)Ptr + 273) = 0;
            StrTrimW(v10, L" ");
            if ( PathCchRenameExtension(v10, 0x104u, L".theme") >= 0
              && CabWriter::AddFileWithNameInCab(v5, (const unsigned __int16 *)Ptr + 4, v10) >= 0 )
            {
              *((_DWORD *)Ptr + 262) = 1;
            }
          }
          for ( i = 1; i < v8; ++i )
          {
            if ( *(_DWORD *)(a1 + 2028) )
              break;
            v13 = g_pfn_DPA_GetPtr(*(HDPA *)a1, i);
            if ( CabWriter::AddFileWithNameInCab(
                   v5,
                   (const unsigned __int16 *)v13 + 4,
                   (const unsigned __int16 *)v13 + 264) >= 0 )
              *((_DWORD *)v13 + 262) = 1;
          }
          Cab = CabWriter::CloseCab(v5);
          v14 = *(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(a1 + 2008);
          if ( v14 )
          {
            v15 = Cab < 0 ? 6LL : 5LL;
            if ( v14(v15, 0, 0, *(_QWORD *)(a1 + 2016)) == -1 )
              *(_DWORD *)(a1 + 2028) = 1;
          }
          if ( *(_DWORD *)(a1 + 2028) && Cab >= 0 )
            DeleteFileW(a2);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)Cab;
}

```

## disassembly

```asm
0x180066e28  push    rbx
0x180066e2a  push    rbp
0x180066e2b  push    rsi
0x180066e2c  push    rdi
0x180066e2d  push    r14
0x180066e2f  push    r15
0x180066e31  sub     rsp, 38h
0x180066e35  mov     eax, r8d
0x180066e38  mov     rbp, rdx
0x180066e3b  mov     rbx, rcx
0x180066e3e  test    rdx, rdx
0x180066e41  jz      loc_180066FB4
0x180066e47  test    al, 3
0x180066e49  mov     dword ptr [rcx+7ECh], 0
0x180066e53  mov     r8d, 0
0x180066e59  lea     r14, [rcx+68h]
0x180066e5d  setnz   r8b
0x180066e61  mov     rcx, r14
0x180066e64  shr     eax, 1
0x180066e66  and     eax, 2
0x180066e69  or      r8d, eax
0x180066e6c  call    ?CreateCab@CabWriter@@QEAAJPEBGW4CAB_OPTIONS@@KK@Z; CabWriter::CreateCab(ushort const *,CAB_OPTIONS,ulong,ulong)
0x180066e71  mov     edi, eax
0x180066e73  test    eax, eax
0x180066e75  js      loc_180066FB9
0x180066e7b  mov     rcx, [rbx]; hdpa
0x180066e7e  test    rcx, rcx
0x180066e81  jz      loc_180066FB9
0x180066e87  mov     esi, [rcx]
0x180066e89  test    esi, esi
0x180066e8b  jle     loc_180066FB9
0x180066e91  xor     edx, edx; i
0x180066e93  call    cs:g_pfn_DPA_GetPtr
0x180066e99  mov     rcx, rbp; pszPath
0x180066e9c  mov     rdi, rax
0x180066e9f  lea     r15, [rax+210h]
0x180066ea6  call    cs:__imp_PathFindFileNameW
0x180066eac  mov     edx, 104h; unsigned __int64
0x180066eb1  mov     rcx, r15; unsigned __int16 *
0x180066eb4  mov     r8, rax; unsigned __int16 *
0x180066eb7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180066ebc  test    eax, eax
0x180066ebe  js      short loc_180066F0F
0x180066ec0  xor     ecx, ecx
0x180066ec2  lea     rdx, pszTrimChars; " "
0x180066ec9  mov     [rdi+222h], cx
0x180066ed0  mov     rcx, r15; psz
0x180066ed3  call    cs:__imp_StrTrimW
0x180066ed9  lea     r8, aTheme; ".theme"
0x180066ee0  mov     edx, 104h; cchPath
0x180066ee5  mov     rcx, r15; pszPath
0x180066ee8  call    cs:__imp_PathCchRenameExtension
0x180066eee  test    eax, eax
0x180066ef0  js      short loc_180066F0F
0x180066ef2  lea     rdx, [rdi+8]; unsigned __int16 *
0x180066ef6  mov     r8, r15; unsigned __int16 *
0x180066ef9  mov     rcx, r14; this
0x180066efc  call    ?AddFileWithNameInCab@CabWriter@@QEAAJPEBG0@Z; CabWriter::AddFileWithNameInCab(ushort const *,ushort const *)
0x180066f01  test    eax, eax
0x180066f03  js      short loc_180066F0F
0x180066f05  mov     dword ptr [rdi+418h], 1
0x180066f0f  mov     edi, 1
0x180066f14  cmp     esi, edi
0x180066f16  jle     short loc_180066F58
0x180066f18  cmp     dword ptr [rbx+7ECh], 0
0x180066f1f  jnz     short loc_180066F58
0x180066f21  mov     rcx, [rbx]; hdpa
0x180066f24  movsxd  rdx, edi; i
0x180066f27  call    cs:g_pfn_DPA_GetPtr
0x180066f2d  mov     rcx, r14; this
0x180066f30  mov     r15, rax
0x180066f33  lea     r8, [rax+210h]; unsigned __int16 *
0x180066f3a  lea     rdx, [rax+8]; unsigned __int16 *
0x180066f3e  call    ?AddFileWithNameInCab@CabWriter@@QEAAJPEBG0@Z; CabWriter::AddFileWithNameInCab(ushort const *,ushort const *)
0x180066f43  test    eax, eax
0x180066f45  js      short loc_180066F52
0x180066f47  mov     dword ptr [r15+418h], 1
0x180066f52  inc     edi
0x180066f54  cmp     edi, esi
0x180066f56  jl      short loc_180066F18
0x180066f58  mov     rcx, r14; this
0x180066f5b  call    ?CloseCab@CabWriter@@QEAAJXZ; CabWriter::CloseCab(void)
0x180066f60  mov     edi, eax
0x180066f62  mov     rax, [rbx+7D8h]
0x180066f69  test    rax, rax
0x180066f6c  jz      short loc_180066F95
0x180066f6e  mov     r9, [rbx+7E0h]
0x180066f75  xor     r8d, r8d
0x180066f78  xor     edx, edx
0x180066f7a  test    edi, edi
0x180066f7c  js      short loc_180066FAD
0x180066f7e  lea     ecx, [rdx+5]
0x180066f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f86  cmp     eax, 0FFFFFFFFh
0x180066f89  jnz     short loc_180066F95
0x180066f8b  mov     dword ptr [rbx+7ECh], 1
0x180066f95  cmp     dword ptr [rbx+7ECh], 0
0x180066f9c  jz      short loc_180066FB9
0x180066f9e  test    edi, edi
0x180066fa0  js      short loc_180066FB9
0x180066fa2  mov     rcx, rbp; lpFileName
0x180066fa5  call    cs:__imp_DeleteFileW
0x180066fab  jmp     short loc_180066FB9
0x180066fad  mov     ecx, 6
0x180066fb2  jmp     short loc_180066F81
0x180066fb4  mov     edi, 80004005h
0x180066fb9  mov     eax, edi
0x180066fbb  add     rsp, 38h
0x180066fbf  pop     r15
0x180066fc1  pop     r14
0x180066fc3  pop     rdi
0x180066fc4  pop     rsi
0x180066fc5  pop     rbp
0x180066fc6  pop     rbx
0x180066fc7  retn
```

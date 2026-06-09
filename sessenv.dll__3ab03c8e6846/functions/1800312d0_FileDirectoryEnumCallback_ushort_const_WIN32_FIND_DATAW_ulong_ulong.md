# FileDirectoryEnumCallback(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x1800312d0`
- end: `0x180031442`
- name: `?FileDirectoryEnumCallback@@YAEPEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `370`
- prototype: `char __fastcall(wchar_t *Source, struct _WIN32_FIND_DATAW *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180043c58`

## callees

- `0x180003f30`
- `0x18001ad2c`
- `0x18001ad38`
- `0x1800312d0`
- `0x180043c58`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003131d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003131d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031428`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031428`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180031371`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180031371`

## string_xrefs

- `0x1800313d9`: `ChildFileDirectoryName : %ws`
- `0x1800313fc`: `ChildFileDirectoryName : %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall FileDirectoryEnumCallback(wchar_t *Source, struct _WIN32_FIND_DATAW *a2, int a3)
{
  __int64 v5; // rcx
  __int64 v7; // rax
  WCHAR *cFileName; // rbx
  unsigned int v9; // r15d
  wchar_t *v10; // rax
  wchar_t *v11; // rdi
  char v12; // si
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  int v16; // ecx
  int v17; // eax
  __int64 v19; // [rsp+78h] [rbp+10h]

  v5 = -1;
  v7 = -1;
  do
    ++v7;
  while ( Source[v7] );
  cFileName = a2->cFileName;
  do
    ++v5;
  while ( cFileName[v5] );
  v9 = v5 + v7 + 2;
  v10 = (wchar_t *)LocalAlloc(0, 2LL * v9);
  v11 = v10;
  if ( !v10 )
    return 0;
  v12 = 1;
  wcscpy_s(v10, v9, Source);
  wcscat_s(v11, v9, L"\\");
  wcscat_s(v11, v9, cFileName);
  if ( CompareFileTime(&LastModifiedTime, &a2->ftLastAccessTime) == -1 )
    LastModifiedTime = a2->ftLastAccessTime;
  if ( (a2->dwFileAttributes & 0x10) != 0 )
  {
    v13 = *cFileName;
    v14 = 46 - v13;
    if ( v13 == 46 )
      v14 = -cFileName[1];
    if ( v14 )
    {
      v15 = *cFileName;
      v16 = 46 - v15;
      if ( v15 == 46 )
      {
        v17 = cFileName[1];
        v16 = 46 - v17;
        if ( v17 == 46 )
          v16 = -cFileName[2];
      }
      if ( v16 && (a2->dwFileAttributes & 0x400) == 0 )
      {
        _DbgPrintMessage(1, "ChildFileDirectoryName : %ws", v11);
        v12 = EnumerateDirectory(v11, a3 + 1);
      }
    }
  }
  else
  {
    LODWORD(v19) = a2->nFileSizeLow;
    HIDWORD(v19) = a2->nFileSizeHigh;
    UserProfileSize += v19;
    _DbgPrintMessage(1, "ChildFileDirectoryName : %ws", v11);
  }
  LocalFree(v11);
  return v12;
}

```

## disassembly

```asm
0x1800312d0  push    rbx
0x1800312d2  push    rbp
0x1800312d3  push    rsi
0x1800312d4  push    rdi
0x1800312d5  push    r12
0x1800312d7  push    r13
0x1800312d9  push    r14
0x1800312db  push    r15
0x1800312dd  sub     rsp, 28h
0x1800312e1  mov     rbp, rcx
0x1800312e4  mov     r13d, r8d
0x1800312e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800312eb  mov     r14, rdx
0x1800312ee  mov     rax, rcx
0x1800312f1  xor     r12d, r12d
0x1800312f4  inc     rax
0x1800312f7  cmp     [rbp+rax*2+0], r12w
0x1800312fd  jnz     short loc_1800312F4
0x1800312ff  lea     rbx, [rdx+2Ch]
0x180031303  inc     rcx
0x180031306  cmp     [rbx+rcx*2], r12w
0x18003130b  jnz     short loc_180031303
0x18003130d  lea     r15, [rax+2]
0x180031311  add     r15, rcx
0x180031314  xor     ecx, ecx; uFlags
0x180031316  mov     r15d, r15d
0x180031319  lea     rdx, [r15+r15]; uBytes
0x18003131d  call    cs:__imp_LocalAlloc
0x180031323  mov     rdi, rax
0x180031326  test    rax, rax
0x180031329  jnz     short loc_180031333
0x18003132b  mov     sil, r12b
0x18003132e  jmp     loc_18003142E
0x180031333  mov     r8, rbp; Source
0x180031336  mov     rdx, r15; SizeInWords
0x180031339  mov     rcx, rdi; Destination
0x18003133c  mov     esi, 1
0x180031341  call    wcscpy_s
0x180031346  lea     r8, Source; "\\"
0x18003134d  mov     rdx, r15; SizeInWords
0x180031350  mov     rcx, rdi; Destination
0x180031353  call    wcscat_s
0x180031358  mov     r8, rbx; Source
0x18003135b  mov     rdx, r15; SizeInWords
0x18003135e  mov     rcx, rdi; Destination
0x180031361  call    wcscat_s
0x180031366  lea     rdx, [r14+0Ch]; lpFileTime2
0x18003136a  lea     rcx, ?LastModifiedTime@@3U_FILETIME@@A; lpFileTime1
0x180031371  call    cs:__imp_CompareFileTime
0x180031377  cmp     eax, 0FFFFFFFFh
0x18003137a  jnz     short loc_180031387
0x18003137c  mov     rax, [r14+0Ch]
0x180031380  mov     qword ptr cs:?LastModifiedTime@@3U_FILETIME@@A.dwLowDateTime, rax; _FILETIME LastModifiedTime ...
0x180031387  mov     edx, [r14]
0x18003138a  test    dl, 10h
0x18003138d  jz      short loc_1800313F8
0x18003138f  movzx   eax, word ptr [rbx]
0x180031392  mov     r8d, 2Eh ; '.'
0x180031398  mov     ecx, r8d
0x18003139b  sub     ecx, eax
0x18003139d  jnz     short loc_1800313A9
0x18003139f  movzx   eax, word ptr [rbx+2]
0x1800313a3  movzx   ecx, r12w
0x1800313a7  sub     ecx, eax
0x1800313a9  test    ecx, ecx
0x1800313ab  jz      short loc_180031425
0x1800313ad  movzx   eax, word ptr [rbx]
0x1800313b0  mov     ecx, r8d
0x1800313b3  sub     ecx, eax
0x1800313b5  jnz     short loc_1800313CC
0x1800313b7  movzx   eax, word ptr [rbx+2]
0x1800313bb  mov     ecx, r8d
0x1800313be  sub     ecx, eax
0x1800313c0  jnz     short loc_1800313CC
0x1800313c2  movzx   eax, word ptr [rbx+4]
0x1800313c6  movzx   ecx, r12w
0x1800313ca  sub     ecx, eax
0x1800313cc  test    ecx, ecx
0x1800313ce  jz      short loc_180031425
0x1800313d0  bt      edx, 0Ah
0x1800313d4  jb      short loc_180031425
0x1800313d6  mov     r8, rdi
0x1800313d9  lea     rdx, aChildfiledirec; "ChildFileDirectoryName : %ws"
0x1800313e0  mov     ecx, esi; int
0x1800313e2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800313e7  lea     edx, [r13+1]; unsigned int
0x1800313eb  mov     rcx, rdi; Source
0x1800313ee  call    EnumerateDirectory
0x1800313f3  mov     sil, al
0x1800313f6  jmp     short loc_180031425
0x1800313f8  mov     eax, [r14+20h]
0x1800313fc  lea     rdx, aChildfiledirec; "ChildFileDirectoryName : %ws"
0x180031403  mov     dword ptr [rsp+68h+arg_8], eax
0x180031407  mov     r8, rdi
0x18003140a  mov     eax, [r14+1Ch]
0x18003140e  mov     ecx, esi; int
0x180031410  mov     dword ptr [rsp+68h+arg_8+4], eax
0x180031414  mov     rax, [rsp+68h+arg_8]
0x180031419  add     cs:?UserProfileSize@@3_KA, rax; unsigned __int64 UserProfileSize
0x180031420  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031425  mov     rcx, rdi; hMem
0x180031428  call    cs:__imp_LocalFree
0x18003142e  mov     al, sil
0x180031431  add     rsp, 28h
0x180031435  pop     r15
0x180031437  pop     r14
0x180031439  pop     r13
0x18003143b  pop     r12
0x18003143d  pop     rdi
0x18003143e  pop     rsi
0x18003143f  pop     rbp
0x180031440  pop     rbx
0x180031441  retn
```

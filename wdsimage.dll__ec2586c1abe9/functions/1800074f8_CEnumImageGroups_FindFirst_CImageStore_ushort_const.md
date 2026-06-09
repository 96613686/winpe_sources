# CEnumImageGroups::FindFirst(CImageStore *,ushort const *)

- ea: `0x1800074f8`
- end: `0x18000771a`
- name: `?FindFirst@CEnumImageGroups@@QEAAJPEAVCImageStore@@PEBG@Z`
- size: `546`
- prototype: `__int64 __fastcall(CEnumImageGroups *__hidden this, struct CImageStore *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007aa0`

## callees

- `0x1800073c0`
- `0x1800074f8`
- `0x1800079c8`
- `0x18000fee5`
- `0x18000ff10`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800076c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800076df`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800076c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800076df`
- `msvcrt!_wcsicmp` at `0x1800075f5`
- `msvcrt!_wcsicmp` at `0x180007611`
- `msvcrt!_wcsicmp` at `0x1800075f5`
- `msvcrt!_wcsicmp` at `0x180007611`
- `KERNEL32!FindClose` at `0x1800076ad`
- `KERNEL32!FindClose` at `0x1800076ad`
- `KERNEL32!FindNextFileW` at `0x180007688`
- `KERNEL32!FindNextFileW` at `0x180007688`
- `KERNEL32!FindFirstFileW` at `0x18000759c`
- `KERNEL32!FindFirstFileW` at `0x18000759c`
- `KERNEL32!GetLastError` at `0x1800075b1`
- `KERNEL32!GetLastError` at `0x1800075b1`
- `WdsCommonLib!ConcatenatePaths` at `0x180007571`
- `WdsCommonLib!ConcatenatePaths` at `0x180007571`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180007632`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180007632`

## pseudocode

```c
__int64 __fastcall CEnumImageGroups::FindFirst(
        CEnumImageGroups *this,
        struct CImageStore *a2,
        const unsigned __int16 *a3)
{
  HANDLE FirstFileW; // rsi
  const wchar_t *v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  LPCWSTR lpFileName; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v21; // [rsp+28h] [rbp-D8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF

  lpFileName = 0;
  v21 = 0;
  FirstFileW = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  *((_QWORD *)this + 3) = a2;
  (**(void (__fastcall ***)(struct CImageStore *))a2)(a2);
  v7 = L"*";
  if ( a3 )
    v7 = a3;
  v8 = (unsigned int)ConcatenatePaths(*((_QWORD *)a2 + 3), v7, &lpFileName);
  if ( (unsigned int)ElValidateWin32_2(v8, v9, v10, 68) )
  {
LABEL_24:
    if ( (int)v8 > 0 )
      LODWORD(v8) = (unsigned __int16)v8 | 0x80070000;
LABEL_18:
    FindClose(FirstFileW);
    goto LABEL_19;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      if ( _wcsicmp(FindFileData.cFileName, L".")
        && _wcsicmp(FindFileData.cFileName, L"..")
        && (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        v8 = DuplicateStringW(FindFileData.cFileName, &v21);
        if ( (unsigned int)ElValidateWin32_2(v8, v15, v16, 102) )
          goto LABEL_24;
        v8 = (unsigned int)CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem((char *)this + 32, v21);
        if ( (unsigned int)ElValidateWin32_2(v8, v17, v18, 105) )
          goto LABEL_24;
        v21 = 0;
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    LODWORD(v8) = 0;
    if ( !*((_DWORD *)this + 11) )
      LODWORD(v8) = -1056833018;
    goto LABEL_18;
  }
  LastError = GetLastError();
  v14 = ElValidateWin32_2(LastError, v12, v13, 76);
  LODWORD(v8) = v14;
  if ( v14 > 0 )
    LODWORD(v8) = (unsigned __int16)v14 | 0x80070000;
  if ( (int)v8 >= 0 )
    LODWORD(v8) = -2147467259;
LABEL_19:
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
  if ( v21 )
    operator delete(v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800074f8  push    rbp
0x1800074fa  push    rbx
0x1800074fb  push    rsi
0x1800074fc  push    rdi
0x1800074fd  push    r14
0x1800074ff  lea     rbp, [rsp-190h]
0x180007507  sub     rsp, 290h
0x18000750e  mov     rax, cs:__security_cookie
0x180007515  xor     rax, rsp
0x180007518  mov     [rbp+1B0h+var_30], rax
0x18000751f  and     [rsp+2B0h+lpFileName], 0
0x180007525  mov     rbx, r8
0x180007528  and     [rsp+2B0h+var_288], 0
0x18000752e  mov     rdi, rdx
0x180007531  mov     r14, rcx
0x180007534  xor     edx, edx; Val
0x180007536  mov     r8d, 250h; Size
0x18000753c  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x180007541  xor     esi, esi
0x180007543  call    memset_0
0x180007548  mov     [r14+18h], rdi
0x18000754c  mov     rcx, rdi
0x18000754f  mov     rax, [rdi]
0x180007552  mov     rax, [rax]
0x180007555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000755a  mov     rcx, [rdi+18h]
0x18000755e  lea     rdx, asc_1800140D4; "*"
0x180007565  test    rbx, rbx
0x180007568  lea     r8, [rsp+2B0h+lpFileName]
0x18000756d  cmovnz  rdx, rbx
0x180007571  call    cs:__imp_ConcatenatePaths
0x180007578  nop     dword ptr [rax+rax+00h]
0x18000757d  mov     ecx, eax
0x18000757f  lea     r9d, [rsi+44h]
0x180007583  mov     ebx, eax
0x180007585  call    ElValidateWin32_2
0x18000758a  test    eax, eax
0x18000758c  jnz     loc_18000770B
0x180007592  mov     rcx, [rsp+2B0h+lpFileName]; lpFileName
0x180007597  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x18000759c  call    cs:__imp_FindFirstFileW
0x1800075a3  nop     dword ptr [rax+rax+00h]
0x1800075a8  mov     rsi, rax
0x1800075ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800075af  jnz     short loc_1800075E9
0x1800075b1  call    cs:__imp_GetLastError
0x1800075b8  nop     dword ptr [rax+rax+00h]
0x1800075bd  mov     ecx, eax
0x1800075bf  lea     r9d, [rsi+4Dh]
0x1800075c3  call    ElValidateWin32_2
0x1800075c8  mov     ebx, eax
0x1800075ca  test    eax, eax
0x1800075cc  jle     short loc_1800075D7
0x1800075ce  movzx   ebx, ax
0x1800075d1  or      ebx, 80070000h
0x1800075d7  test    ebx, ebx
0x1800075d9  js      loc_1800076B9
0x1800075df  mov     ebx, 80004005h
0x1800075e4  jmp     loc_1800076B9
0x1800075e9  lea     rdx, asc_180014108; "."
0x1800075f0  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; String1
0x1800075f5  call    cs:__imp__wcsicmp
0x1800075fc  nop     dword ptr [rax+rax+00h]
0x180007601  test    eax, eax
0x180007603  jz      short loc_180007680
0x180007605  lea     rdx, asc_18001410C; ".."
0x18000760c  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; String1
0x180007611  call    cs:__imp__wcsicmp
0x180007618  nop     dword ptr [rax+rax+00h]
0x18000761d  test    eax, eax
0x18000761f  jz      short loc_180007680
0x180007621  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x180007626  jz      short loc_180007680
0x180007628  lea     rdx, [rsp+2B0h+var_288]
0x18000762d  lea     rcx, [rsp+2B0h+FindFileData.cFileName]
0x180007632  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180007639  nop     dword ptr [rax+rax+00h]
0x18000763e  mov     ecx, eax
0x180007640  mov     r9d, 66h ; 'f'
0x180007646  mov     ebx, eax
0x180007648  call    ElValidateWin32_2
0x18000764d  test    eax, eax
0x18000764f  jnz     loc_18000770B
0x180007655  mov     rdx, [rsp+2B0h+var_288]
0x18000765a  lea     rcx, [r14+20h]
0x18000765e  call    ?AddItem@?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAAKPEAUWdsImgParentImage@@@Z; CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(WdsImgParentImage *)
0x180007663  mov     r9d, 69h ; 'i'
0x180007669  mov     ecx, eax
0x18000766b  mov     ebx, eax
0x18000766d  call    ElValidateWin32_2
0x180007672  test    eax, eax
0x180007674  jnz     loc_18000770B
0x18000767a  and     [rsp+2B0h+var_288], 0
0x180007680  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x180007685  mov     rcx, rsi; hFindFile
0x180007688  call    cs:__imp_FindNextFileW
0x18000768f  nop     dword ptr [rax+rax+00h]
0x180007694  test    eax, eax
0x180007696  jnz     loc_1800075E9
0x18000769c  xor     ebx, ebx
0x18000769e  mov     eax, 0C1020206h
0x1800076a3  cmp     [r14+2Ch], ebx
0x1800076a7  cmovz   ebx, eax
0x1800076aa  mov     rcx, rsi; hFindFile
0x1800076ad  call    cs:__imp_FindClose
0x1800076b4  nop     dword ptr [rax+rax+00h]
0x1800076b9  mov     rcx, [rsp+2B0h+lpFileName]
0x1800076be  test    rcx, rcx
0x1800076c1  jz      short loc_1800076D5
0x1800076c3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800076ca  nop     dword ptr [rax+rax+00h]
0x1800076cf  and     [rsp+2B0h+lpFileName], 0
0x1800076d5  mov     rcx, [rsp+2B0h+var_288]
0x1800076da  test    rcx, rcx
0x1800076dd  jz      short loc_1800076EB
0x1800076df  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800076e6  nop     dword ptr [rax+rax+00h]
0x1800076eb  mov     eax, ebx
0x1800076ed  mov     rcx, [rbp+1B0h+var_30]
0x1800076f4  xor     rcx, rsp; StackCookie
0x1800076f7  call    __security_check_cookie
0x1800076fc  add     rsp, 290h
0x180007703  pop     r14
0x180007705  pop     rdi
0x180007706  pop     rsi
0x180007707  pop     rbx
0x180007708  pop     rbp
0x180007709  retn
0x18000770b  test    ebx, ebx
0x18000770d  jle     short loc_1800076AA
0x18000770f  movzx   ebx, bx
0x180007712  or      ebx, 80070000h
0x180007718  jmp     short loc_1800076AA
```

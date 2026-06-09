# CEnumImages::Search(ushort const *)

- ea: `0x18000844c`
- end: `0x1800086de`
- name: `?Search@CEnumImages@@AEAAJPEBG@Z`
- size: `658`
- prototype: `__int64 __fastcall(CEnumImages *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007fd4`
- `0x18000844c`

## callees

- `0x1800073c0`
- `0x18000844c`
- `0x1800086e4`
- `0x180008748`
- `0x18000b108`
- `0x18000fee5`
- `0x18000ff10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800085c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000868d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800086a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800085c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000868d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800086a9`
- `KERNEL32!FindClose` at `0x180008677`
- `KERNEL32!FindClose` at `0x180008677`
- `KERNEL32!FindNextFileW` at `0x1800085da`
- `KERNEL32!FindNextFileW` at `0x1800085da`
- `KERNEL32!FindFirstFileW` at `0x1800084ea`
- `KERNEL32!FindFirstFileW` at `0x1800084ea`
- `KERNEL32!GetLastError` at `0x1800084ff`
- `KERNEL32!GetLastError` at `0x1800084ff`
- `WdsCommonLib!WdsIsPseudoDirectory` at `0x180008552`
- `WdsCommonLib!WdsIsPseudoDirectory` at `0x180008552`
- `WdsCommonLib!ConcatenatePaths` at `0x1800084a8`
- `WdsCommonLib!ConcatenatePaths` at `0x18000856f`
- `WdsCommonLib!ConcatenatePaths` at `0x18000860e`
- `WdsCommonLib!ConcatenatePaths` at `0x1800084a8`
- `WdsCommonLib!ConcatenatePaths` at `0x18000856f`
- `WdsCommonLib!ConcatenatePaths` at `0x18000860e`

## pseudocode

```c
__int64 __fastcall CEnumImages::Search(CEnumImages *this, const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  HANDLE FirstFileW; // rsi
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  unsigned int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int16 *v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned __int16 *v25; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF

  LODWORD(v4) = 0;
  lpFileName = 0;
  v25 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = (unsigned int)ConcatenatePaths(a2, *((_QWORD *)this + 7), &lpFileName);
  if ( (unsigned int)ElValidateWin32_3(v5, v6, v7, 478) )
  {
    if ( (int)v5 > 0 )
      LODWORD(v4) = (unsigned __int16)v5 | 0x80070000;
    else
      LODWORD(v4) = v5;
    goto LABEL_31;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v12 = ElValidateWin32_3(LastError, v10, v11, 486);
    LODWORD(v4) = v12;
    if ( v12 > 0 )
      LODWORD(v4) = (unsigned __int16)v12 | 0x80070000;
    if ( (int)v4 >= 0 )
      LODWORD(v4) = -2147467259;
    goto LABEL_31;
  }
  while ( 1 )
  {
    v13 = *((_DWORD *)this + 12);
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( (v13 & 1) != 0 && !(unsigned int)WdsIsPseudoDirectory(FindFileData.cFileName) )
      {
        v4 = (unsigned int)ConcatenatePaths(a2, FindFileData.cFileName, &v25);
        if ( (unsigned int)ElValidateWin32_3(v4, v14, v15, 503) )
        {
          if ( (int)v4 <= 0 )
            goto LABEL_30;
          LODWORD(v4) = (unsigned __int16)v4;
          goto LABEL_29;
        }
        v4 = (unsigned int)CEnumImages::Search(this, v25);
        if ( (int)ElValidateHr_4(v4, v16, v17, 509) < 0 )
          goto LABEL_30;
      }
      goto LABEL_15;
    }
    if ( (unsigned int)CImage::IsValidImage(FindFileData.cFileName, v13) )
      break;
LABEL_15:
    v18 = v25;
LABEL_16:
    if ( v18 )
    {
      operator delete(v18);
      v25 = 0;
    }
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_30;
  }
  v19 = (unsigned int)ConcatenatePaths(a2, FindFileData.cFileName, &v25);
  if ( !(unsigned int)ElValidateWin32_3(v19, v20, v21, 518) )
  {
    v19 = (unsigned int)CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem((char *)this + 24, v25);
    if ( !(unsigned int)ElValidateWin32_3(v19, v22, v23, 521) )
    {
      v18 = 0;
      v25 = 0;
      goto LABEL_16;
    }
  }
  if ( (int)v19 <= 0 )
  {
    LODWORD(v4) = v19;
    goto LABEL_30;
  }
  LODWORD(v4) = (unsigned __int16)v19;
LABEL_29:
  LODWORD(v4) = v4 | 0x80070000;
LABEL_30:
  FindClose(FirstFileW);
LABEL_31:
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
  if ( v25 )
    operator delete(v25);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000844c  mov     [rsp-8+arg_10], rbx
0x180008451  push    rbp
0x180008452  push    rsi
0x180008453  push    rdi
0x180008454  push    r14
0x180008456  push    r15
0x180008458  lea     rbp, [rsp-190h]
0x180008460  sub     rsp, 290h
0x180008467  mov     rax, cs:__security_cookie
0x18000846e  xor     rax, rsp
0x180008471  mov     [rbp+1B0h+var_30], rax
0x180008478  mov     r15, rdx
0x18000847b  mov     r14, rcx
0x18000847e  xor     ebx, ebx
0x180008480  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x180008485  and     [rsp+2B0h+lpFileName], rbx
0x18000848a  xor     edx, edx; Val
0x18000848c  and     [rsp+2B0h+var_290], rbx
0x180008491  mov     r8d, 250h; Size
0x180008497  call    memset_0
0x18000849c  mov     rdx, [r14+38h]
0x1800084a0  lea     r8, [rsp+2B0h+lpFileName]
0x1800084a5  mov     rcx, r15
0x1800084a8  call    cs:__imp_ConcatenatePaths
0x1800084af  nop     dword ptr [rax+rax+00h]
0x1800084b4  mov     ecx, eax
0x1800084b6  mov     r9d, 1DEh
0x1800084bc  mov     edi, eax
0x1800084be  call    ElValidateWin32_3
0x1800084c3  test    eax, eax
0x1800084c5  jz      short loc_1800084E0
0x1800084c7  test    edi, edi
0x1800084c9  jg      short loc_1800084D2
0x1800084cb  mov     ebx, edi
0x1800084cd  jmp     loc_180008683
0x1800084d2  movzx   ebx, di
0x1800084d5  or      ebx, 80070000h
0x1800084db  jmp     loc_180008683
0x1800084e0  mov     rcx, [rsp+2B0h+lpFileName]; lpFileName
0x1800084e5  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1800084ea  call    cs:__imp_FindFirstFileW
0x1800084f1  nop     dword ptr [rax+rax+00h]
0x1800084f6  mov     rsi, rax
0x1800084f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800084fd  jnz     short loc_180008539
0x1800084ff  call    cs:__imp_GetLastError
0x180008506  nop     dword ptr [rax+rax+00h]
0x18000850b  mov     ecx, eax
0x18000850d  mov     r9d, 1E6h
0x180008513  call    ElValidateWin32_3
0x180008518  mov     ebx, eax
0x18000851a  test    eax, eax
0x18000851c  jle     short loc_180008527
0x18000851e  movzx   ebx, ax
0x180008521  or      ebx, 80070000h
0x180008527  test    ebx, ebx
0x180008529  js      loc_180008683
0x18000852f  mov     ebx, 80004005h
0x180008534  jmp     loc_180008683
0x180008539  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x18000853e  mov     edx, [r14+30h]; unsigned int
0x180008542  jz      loc_1800085F3
0x180008548  test    dl, 1
0x18000854b  jz      short loc_1800085B6
0x18000854d  lea     rcx, [rsp+2B0h+FindFileData.cFileName]
0x180008552  call    cs:__imp_WdsIsPseudoDirectory
0x180008559  nop     dword ptr [rax+rax+00h]
0x18000855e  test    eax, eax
0x180008560  jnz     short loc_1800085B6
0x180008562  lea     r8, [rsp+2B0h+var_290]
0x180008567  mov     rcx, r15
0x18000856a  lea     rdx, [rsp+2B0h+FindFileData.cFileName]
0x18000856f  call    cs:__imp_ConcatenatePaths
0x180008576  nop     dword ptr [rax+rax+00h]
0x18000857b  mov     ecx, eax
0x18000857d  mov     r9d, 1F7h
0x180008583  mov     ebx, eax
0x180008585  call    ElValidateWin32_3
0x18000858a  test    eax, eax
0x18000858c  jnz     loc_18000865A
0x180008592  mov     rdx, [rsp+2B0h+var_290]; unsigned __int16 *
0x180008597  mov     rcx, r14; this
0x18000859a  call    ?Search@CEnumImages@@AEAAJPEBG@Z; CEnumImages::Search(ushort const *)
0x18000859f  mov     r9d, 1FDh
0x1800085a5  mov     ecx, eax
0x1800085a7  mov     ebx, eax
0x1800085a9  call    ElValidateHr_4
0x1800085ae  test    eax, eax
0x1800085b0  js      loc_180008674
0x1800085b6  mov     rcx, [rsp+2B0h+var_290]
0x1800085bb  test    rcx, rcx
0x1800085be  jz      short loc_1800085D2
0x1800085c0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800085c7  nop     dword ptr [rax+rax+00h]
0x1800085cc  and     [rsp+2B0h+var_290], 0
0x1800085d2  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1800085d7  mov     rcx, rsi; hFindFile
0x1800085da  call    cs:__imp_FindNextFileW
0x1800085e1  nop     dword ptr [rax+rax+00h]
0x1800085e6  test    eax, eax
0x1800085e8  jnz     loc_180008539
0x1800085ee  jmp     loc_180008674
0x1800085f3  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; unsigned __int16 *
0x1800085f8  call    ?IsValidImage@CImage@@SAHPEBGK@Z; CImage::IsValidImage(ushort const *,ulong)
0x1800085fd  test    eax, eax
0x1800085ff  jz      short loc_1800085B6
0x180008601  lea     r8, [rsp+2B0h+var_290]
0x180008606  mov     rcx, r15
0x180008609  lea     rdx, [rsp+2B0h+FindFileData.cFileName]
0x18000860e  call    cs:__imp_ConcatenatePaths
0x180008615  nop     dword ptr [rax+rax+00h]
0x18000861a  mov     ecx, eax
0x18000861c  mov     r9d, 206h
0x180008622  mov     edi, eax
0x180008624  call    ElValidateWin32_3
0x180008629  test    eax, eax
0x18000862b  jnz     short loc_180008663
0x18000862d  mov     rdx, [rsp+2B0h+var_290]
0x180008632  lea     rcx, [r14+18h]
0x180008636  call    ?AddItem@?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAAKPEAUWdsImgParentImage@@@Z; CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(WdsImgParentImage *)
0x18000863b  mov     r9d, 209h
0x180008641  mov     ecx, eax
0x180008643  mov     edi, eax
0x180008645  call    ElValidateWin32_3
0x18000864a  test    eax, eax
0x18000864c  jnz     short loc_180008663
0x18000864e  xor     ecx, ecx
0x180008650  mov     [rsp+2B0h+var_290], rcx
0x180008655  jmp     loc_1800085BB
0x18000865a  test    ebx, ebx
0x18000865c  jle     short loc_180008674
0x18000865e  movzx   ebx, bx
0x180008661  jmp     short loc_18000866E
0x180008663  test    edi, edi
0x180008665  jg      short loc_18000866B
0x180008667  mov     ebx, edi
0x180008669  jmp     short loc_180008674
0x18000866b  movzx   ebx, di
0x18000866e  or      ebx, 80070000h
0x180008674  mov     rcx, rsi; hFindFile
0x180008677  call    cs:__imp_FindClose
0x18000867e  nop     dword ptr [rax+rax+00h]
0x180008683  mov     rcx, [rsp+2B0h+lpFileName]
0x180008688  test    rcx, rcx
0x18000868b  jz      short loc_18000869F
0x18000868d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008694  nop     dword ptr [rax+rax+00h]
0x180008699  and     [rsp+2B0h+lpFileName], 0
0x18000869f  mov     rcx, [rsp+2B0h+var_290]
0x1800086a4  test    rcx, rcx
0x1800086a7  jz      short loc_1800086B5
0x1800086a9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800086b0  nop     dword ptr [rax+rax+00h]
0x1800086b5  mov     eax, ebx
0x1800086b7  mov     rcx, [rbp+1B0h+var_30]
0x1800086be  xor     rcx, rsp; StackCookie
0x1800086c1  call    __security_check_cookie
0x1800086c6  mov     rbx, [rsp+2B0h+arg_10]
0x1800086ce  add     rsp, 290h
0x1800086d5  pop     r15
0x1800086d7  pop     r14
0x1800086d9  pop     rdi
0x1800086da  pop     rsi
0x1800086db  pop     rbp
0x1800086dc  retn
```

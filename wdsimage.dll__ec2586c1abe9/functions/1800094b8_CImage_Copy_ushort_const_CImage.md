# CImage::Copy(ushort const *,CImage * *)

- ea: `0x1800094b8`
- end: `0x1800096b7`
- name: `?Copy@CImage@@QEAAJPEBGPEAPEAV1@@Z`
- size: `511`
- prototype: `__int64 __fastcall(CImage *__hidden this, const unsigned __int16 *, struct CImage **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004230`

## callees

- `0x180001588`
- `0x1800039a8`
- `0x1800094b8`
- `0x18000ae64`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009664`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000967e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009664`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000967e`
- `KERNEL32!CopyFileW` at `0x1800095b0`
- `KERNEL32!CopyFileW` at `0x1800095b0`
- `KERNEL32!GetFileAttributesW` at `0x180009570`
- `KERNEL32!GetFileAttributesW` at `0x180009570`
- `KERNEL32!GetLastError` at `0x1800095c0`
- `KERNEL32!GetLastError` at `0x1800095c0`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x18000950d`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x18000950d`
- `WdsCommonLib!ConcatenatePaths` at `0x18000954d`
- `WdsCommonLib!ConcatenatePaths` at `0x18000954d`

## pseudocode

```c
__int64 __fastcall CImage::Copy(CImage *this, const unsigned __int16 *a2, struct CImage **a3)
{
  struct CImage *v3; // rdi
  __int64 ParentFolderPathOfFile; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  CImage *v17; // rax
  CImage *v18; // rax
  __int64 v19; // rdx
  LPCWSTR lpFileName; // [rsp+50h] [rbp+30h] BYREF
  void *v22; // [rsp+68h] [rbp+48h] BYREF

  v3 = 0;
  v22 = 0;
  lpFileName = 0;
  if ( *((_DWORD *)this + 7) == 2
    || (LODWORD(ParentFolderPathOfFile) = -1056832994,
        (int)ElValidateHr_5(3238134302LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1800) >= 0) )
  {
    ParentFolderPathOfFile = (unsigned int)WdsGetParentFolderPathOfFile(*((_QWORD *)this + 11), &v22);
    if ( (unsigned int)ElValidateWin32_4(ParentFolderPathOfFile, v8, v9, 1807)
      || (ParentFolderPathOfFile = (unsigned int)ConcatenatePaths(v22, a2, &lpFileName),
          (unsigned int)ElValidateWin32_4(ParentFolderPathOfFile, v10, v11, 1813)) )
    {
      if ( (int)ParentFolderPathOfFile > 0 )
        LODWORD(ParentFolderPathOfFile) = (unsigned __int16)ParentFolderPathOfFile | 0x80070000;
    }
    else if ( GetFileAttributesW(lpFileName) == -1
           || (LODWORD(ParentFolderPathOfFile) = -1056833014,
               (int)ElValidateHr_5(3238134282LL, v12, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1821) >= 0) )
    {
      if ( CopyFileW(*((LPCWSTR *)this + 11), lpFileName, 1) )
      {
        v17 = (CImage *)operator new(0x190u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 && (v18 = CImage::CImage(v17), (v3 = v18) != 0) )
        {
          ParentFolderPathOfFile = (unsigned int)CImage::Initialize(v18, lpFileName, *((_DWORD *)this + 33), 0x120u);
          if ( (int)ElValidateHr_5(ParentFolderPathOfFile, v19, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1844) >= 0 )
          {
            *a3 = v3;
            v3 = 0;
          }
        }
        else
        {
          LODWORD(ParentFolderPathOfFile) = -2147024882;
        }
      }
      else
      {
        LastError = GetLastError();
        v16 = ElValidateWin32_4(LastError, v14, v15, 1829);
        LODWORD(ParentFolderPathOfFile) = v16;
        if ( v16 > 0 )
          LODWORD(ParentFolderPathOfFile) = (unsigned __int16)v16 | 0x80070000;
        if ( (int)ParentFolderPathOfFile >= 0 )
          LODWORD(ParentFolderPathOfFile) = -2147467259;
      }
    }
  }
  if ( v22 )
  {
    operator delete(v22);
    v22 = 0;
  }
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
  if ( v3 )
    (*(void (__fastcall **)(struct CImage *))(*(_QWORD *)v3 + 8LL))(v3);
  return (unsigned int)ParentFolderPathOfFile;
}

```

## disassembly

```asm
0x1800094b8  mov     [rsp-28h+arg_8], rbx
0x1800094bd  push    rbp
0x1800094be  push    rsi
0x1800094bf  push    rdi
0x1800094c0  push    r14
0x1800094c2  push    r15
0x1800094c4  mov     rbp, rsp
0x1800094c7  sub     rsp, 20h
0x1800094cb  xor     edi, edi
0x1800094cd  mov     r15, r8
0x1800094d0  and     [rbp+arg_18], rdi
0x1800094d4  mov     rsi, rdx
0x1800094d7  and     [rbp+lpFileName], rdi
0x1800094db  mov     r14, rcx
0x1800094de  cmp     dword ptr [rcx+1Ch], 2
0x1800094e2  jz      short loc_180009505
0x1800094e4  mov     ebx, 0C102021Eh
0x1800094e9  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x1800094f0  mov     ecx, ebx
0x1800094f2  mov     r9d, 708h
0x1800094f8  call    ElValidateHr_5
0x1800094fd  test    eax, eax
0x1800094ff  js      loc_18000965B
0x180009505  mov     rcx, [r14+58h]
0x180009509  lea     rdx, [rbp+arg_18]
0x18000950d  call    cs:__imp_WdsGetParentFolderPathOfFile
0x180009514  nop     dword ptr [rax+rax+00h]
0x180009519  mov     ecx, eax
0x18000951b  mov     r9d, 70Fh
0x180009521  mov     ebx, eax
0x180009523  call    ElValidateWin32_4
0x180009528  test    eax, eax
0x18000952a  jz      short loc_180009542
0x18000952c  test    ebx, ebx
0x18000952e  jle     loc_18000965B
0x180009534  movzx   ebx, bx
0x180009537  or      ebx, 80070000h
0x18000953d  jmp     loc_18000965B
0x180009542  mov     rcx, [rbp+arg_18]
0x180009546  lea     r8, [rbp+lpFileName]
0x18000954a  mov     rdx, rsi
0x18000954d  call    cs:__imp_ConcatenatePaths
0x180009554  nop     dword ptr [rax+rax+00h]
0x180009559  mov     ecx, eax
0x18000955b  mov     r9d, 715h
0x180009561  mov     ebx, eax
0x180009563  call    ElValidateWin32_4
0x180009568  test    eax, eax
0x18000956a  jnz     short loc_18000952C
0x18000956c  mov     rcx, [rbp+lpFileName]; lpFileName
0x180009570  call    cs:__imp_GetFileAttributesW
0x180009577  nop     dword ptr [rax+rax+00h]
0x18000957c  cmp     eax, 0FFFFFFFFh
0x18000957f  jz      short loc_1800095A2
0x180009581  mov     ebx, 0C102020Ah
0x180009586  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000958d  mov     ecx, ebx
0x18000958f  mov     r9d, 71Dh
0x180009595  call    ElValidateHr_5
0x18000959a  test    eax, eax
0x18000959c  js      loc_18000965B
0x1800095a2  mov     rdx, [rbp+lpFileName]; lpNewFileName
0x1800095a6  mov     r8d, 1; bFailIfExists
0x1800095ac  mov     rcx, [r14+58h]; lpExistingFileName
0x1800095b0  call    cs:__imp_CopyFileW
0x1800095b7  nop     dword ptr [rax+rax+00h]
0x1800095bc  test    eax, eax
0x1800095be  jnz     short loc_1800095F3
0x1800095c0  call    cs:__imp_GetLastError
0x1800095c7  nop     dword ptr [rax+rax+00h]
0x1800095cc  mov     ecx, eax
0x1800095ce  mov     r9d, 725h
0x1800095d4  call    ElValidateWin32_4
0x1800095d9  mov     ebx, eax
0x1800095db  test    eax, eax
0x1800095dd  jle     short loc_1800095E8
0x1800095df  movzx   ebx, ax
0x1800095e2  or      ebx, 80070000h
0x1800095e8  test    ebx, ebx
0x1800095ea  js      short loc_18000965B
0x1800095ec  mov     ebx, 80004005h
0x1800095f1  jmp     short loc_18000965B
0x1800095f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800095fa  mov     ecx, 190h; unsigned __int64
0x1800095ff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009604  test    rax, rax
0x180009607  jz      short loc_180009656
0x180009609  mov     rcx, rax; this
0x18000960c  call    ??0CImage@@QEAA@XZ; CImage::CImage(void)
0x180009611  mov     rsi, rax
0x180009614  mov     rdi, rax
0x180009617  test    rax, rax
0x18000961a  jz      short loc_180009656
0x18000961c  mov     r8d, [r14+84h]; unsigned int
0x180009623  mov     r9d, 120h; unsigned int
0x180009629  mov     rdx, [rbp+lpFileName]; unsigned __int16 *
0x18000962d  mov     rcx, rax; this
0x180009630  call    ?Initialize@CImage@@QEAAJPEBGKK@Z; CImage::Initialize(ushort const *,ulong,ulong)
0x180009635  mov     r9d, 734h
0x18000963b  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009642  mov     ecx, eax
0x180009644  mov     ebx, eax
0x180009646  call    ElValidateHr_5
0x18000964b  test    eax, eax
0x18000964d  js      short loc_18000965B
0x18000964f  mov     [r15], rdi
0x180009652  xor     edi, edi
0x180009654  jmp     short loc_18000965B
0x180009656  mov     ebx, 8007000Eh
0x18000965b  mov     rcx, [rbp+arg_18]
0x18000965f  test    rcx, rcx
0x180009662  jz      short loc_180009675
0x180009664  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000966b  nop     dword ptr [rax+rax+00h]
0x180009670  and     [rbp+arg_18], 0
0x180009675  mov     rcx, [rbp+lpFileName]
0x180009679  test    rcx, rcx
0x18000967c  jz      short loc_18000968F
0x18000967e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009685  nop     dword ptr [rax+rax+00h]
0x18000968a  and     [rbp+lpFileName], 0
0x18000968f  test    rdi, rdi
0x180009692  jz      short loc_1800096A3
0x180009694  mov     rax, [rdi]
0x180009697  mov     rcx, rdi
0x18000969a  mov     rax, [rax+8]
0x18000969e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a3  mov     eax, ebx
0x1800096a5  mov     rbx, [rsp+20h+arg_8]
0x1800096aa  add     rsp, 20h
0x1800096ae  pop     r15
0x1800096b0  pop     r14
0x1800096b2  pop     rdi
0x1800096b3  pop     rsi
0x1800096b4  pop     rbp
0x1800096b5  retn
```

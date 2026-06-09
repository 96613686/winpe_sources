# CMetaStoreUtils::DeleteFilesInDirectory(ushort const *,int)

- ea: `0x1800d73ec`
- end: `0x1800d7781`
- name: `?DeleteFilesInDirectory@CMetaStoreUtils@@SAJPEBGH@Z`
- size: `917`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800d73ec`
- `0x1800e9a58`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180006ed0`
- `0x180006f5c`
- `0x18001133c`
- `0x18002dad0`
- `0x1800ad07c`
- `0x1800d3488`
- `0x1800d73ec`

## import_xrefs

- `KERNEL32!FindClose` at `0x1800d7711`
- `KERNEL32!FindClose` at `0x1800d7711`
- `KERNEL32!RemoveDirectoryW` at `0x1800d75f4`
- `KERNEL32!RemoveDirectoryW` at `0x1800d75f4`
- `KERNEL32!FindNextFileW` at `0x1800d7689`
- `KERNEL32!FindNextFileW` at `0x1800d7689`
- `KERNEL32!DeleteFileW` at `0x1800d762f`
- `KERNEL32!DeleteFileW` at `0x1800d762f`
- `KERNEL32!FindFirstFileExW` at `0x1800d74d5`
- `KERNEL32!FindFirstFileExW` at `0x1800d74d5`
- `KERNEL32!GetLastError` at `0x1800d75fe`
- `KERNEL32!GetLastError` at `0x1800d7639`
- `KERNEL32!GetLastError` at `0x1800d76ac`
- `KERNEL32!GetLastError` at `0x1800d75fe`
- `KERNEL32!GetLastError` at `0x1800d7639`
- `KERNEL32!GetLastError` at `0x1800d76ac`

## pseudocode

```c
__int64 __fastcall CMetaStoreUtils::DeleteFilesInDirectory(unsigned __int16 *a1, int a2)
{
  __int64 v2; // r14
  signed int v4; // esi
  const unsigned __int16 *v5; // r8
  const WCHAR *v6; // rdi
  __int64 v7; // r11
  HANDLE v8; // r15
  __int64 v9; // rax
  unsigned __int64 v10; // r15
  unsigned __int16 *v11; // rbx
  signed int LastError; // eax
  _QWORD *v13; // rcx
  int v14; // edx
  signed int v15; // eax
  BOOL NextFileW; // ebx
  signed int v17; // eax
  int v19; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpPathName; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-B8h]
  HANDLE hFindFile; // [rsp+50h] [rbp-B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  lpFileName = 0;
  v2 = -1;
  v23 = a1;
  do
    ++v2;
  while ( a1[v2] );
  v4 = _AllocArray<unsigned short,CTCoAllocPolicy>(a1, 1, v2 + 3, &lpFileName);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fbe311bd82113ee81e8806f10330c179_Traceguids);
  }
  else
  {
    v5 = a1;
    v6 = lpFileName;
    StringCchCopyW((unsigned __int16 *)lpFileName, v2 + 3, v5);
    v19 = 0;
    if ( v6[v2 - 1] != 92 && v6[v2 - 1] != 47 )
    {
      v19 = 1;
      v7 = v2 + 1;
      v6[v2] = 92;
    }
    *(_DWORD *)&v6[v7] = 42;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    hFindFile = FindFirstFileExW(v6, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
    v8 = hFindFile;
    if ( hFindFile != (HANDLE)-1LL )
    {
      while ( 1 )
      {
        if ( v4 < 0 )
          goto LABEL_41;
        lpPathName = 0;
        v9 = -1;
        do
          ++v9;
        while ( FindFileData.cFileName[v9] );
        v10 = v2 + v9 + 2;
        v4 = _AllocArray<unsigned short,CTCoAllocPolicy>(FindFileData.cFileName, 1, v10, &lpPathName);
        if ( v4 >= 0 )
        {
          v11 = (unsigned __int16 *)lpPathName;
          StringCchCopyW((unsigned __int16 *)lpPathName, v10, v23);
          if ( v19 )
            *(_DWORD *)&v11[v2] = 92;
          StringCchCatW(v11, v10, FindFileData.cFileName);
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            if ( !a2
              || FindFileData.cFileName[0] == 46
              && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
            {
              goto LABEL_37;
            }
            v4 = CMetaStoreUtils::DeleteFilesInDirectory(v11, 1);
            if ( v4 < 0 || RemoveDirectoryW(v11) )
              goto LABEL_37;
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_37;
            v14 = 11;
          }
          else
          {
            if ( DeleteFileW(v11) )
              goto LABEL_37;
            v15 = GetLastError();
            v4 = v15;
            if ( v15 > 0 )
              v4 = (unsigned __int16)v15 | 0x80070000;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_37;
            v14 = 12;
          }
          WPP_SF_Sd(v13[2], v14, (unsigned int)WPP_fbe311bd82113ee81e8806f10330c179_Traceguids, (_DWORD)v11, v4);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fbe311bd82113ee81e8806f10330c179_Traceguids);
        }
LABEL_37:
        v8 = hFindFile;
        NextFileW = FindNextFileW(hFindFile, &FindFileData);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpPathName);
        if ( !NextFileW )
        {
          if ( v4 < 0 )
            goto LABEL_41;
          break;
        }
      }
    }
    v17 = GetLastError();
    v4 = v17;
    if ( v17 > 0 )
      v4 = (unsigned __int16)v17 | 0x80070000;
LABEL_41:
    if ( ((v4 + 2147024894) & 0xFFFFFFEE) != 0 || v4 == -2147024877 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_fbe311bd82113ee81e8806f10330c179_Traceguids,
          (_DWORD)v6,
          v4);
    }
    else
    {
      v4 = 0;
    }
    if ( v8 != (HANDLE)-1LL )
      FindClose(v8);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpFileName);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800d73ec  mov     [rsp-8+arg_8], rbx
0x1800d73f1  mov     [rsp-8+arg_10], rsi
0x1800d73f6  push    rbp
0x1800d73f7  push    rdi
0x1800d73f8  push    r12
0x1800d73fa  push    r14
0x1800d73fc  push    r15
0x1800d73fe  lea     rbp, [rsp-1C0h]
0x1800d7406  sub     rsp, 2C0h
0x1800d740d  mov     rax, cs:__security_cookie
0x1800d7414  xor     rax, rsp
0x1800d7417  mov     [rbp+1E0h+var_30], rax
0x1800d741e  xor     r15d, r15d
0x1800d7421  mov     [rsp+2E0h+var_2AC], edx
0x1800d7425  mov     [rsp+2E0h+lpFileName], r15
0x1800d742a  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800d742e  mov     rdi, rcx
0x1800d7431  mov     [rsp+2E0h+var_298], rcx
0x1800d7436  inc     r14
0x1800d7439  cmp     [rcx+r14*2], r15w
0x1800d743e  jnz     short loc_1800D7436
0x1800d7440  lea     r9, [rsp+2E0h+lpFileName]
0x1800d7445  mov     edx, 1
0x1800d744a  lea     r8, [r14+3]
0x1800d744e  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800d7453  mov     esi, eax
0x1800d7455  test    eax, eax
0x1800d7457  js      loc_1800D7719
0x1800d745d  mov     r8, rdi; unsigned __int16 *
0x1800d7460  lea     rdx, [r14+3]; unsigned __int64
0x1800d7464  mov     rdi, [rsp+2E0h+lpFileName]
0x1800d7469  mov     r11, r14
0x1800d746c  mov     rcx, rdi; unsigned __int16 *
0x1800d746f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d7474  xor     ebx, ebx
0x1800d7476  mov     [rsp+2E0h+var_2B0], ebx
0x1800d747a  lea     eax, [rbx+5Ch]
0x1800d747d  cmp     [rdi+r14*2-2], ax
0x1800d7483  jz      short loc_1800D749F
0x1800d7485  cmp     word ptr [rdi+r14*2-2], 2Fh ; '/'
0x1800d748c  jz      short loc_1800D749F
0x1800d748e  mov     [rsp+2E0h+var_2B0], 1
0x1800d7496  lea     r11, [r14+1]
0x1800d749a  mov     [rdi+r14*2], ax
0x1800d749f  xor     edx, edx; Val
0x1800d74a1  mov     dword ptr [rdi+r11*2], 2Ah ; '*'
0x1800d74a9  mov     r8d, 250h; Size
0x1800d74af  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x1800d74b4  call    memset_0
0x1800d74b9  xor     r9d, r9d; fSearchOp
0x1800d74bc  mov     [rsp+2E0h+dwAdditionalFlags], 2; dwAdditionalFlags
0x1800d74c4  lea     r8, [rsp+2E0h+FindFileData]; lpFindFileData
0x1800d74c9  mov     [rsp+2E0h+lpSearchFilter], rbx; lpSearchFilter
0x1800d74ce  mov     rcx, rdi; lpFileName
0x1800d74d1  lea     edx, [r9+1]; fInfoLevelId
0x1800d74d5  call    cs:__imp_FindFirstFileExW
0x1800d74db  mov     [rsp+2E0h+hFindFile], rax
0x1800d74e0  mov     r15, rax
0x1800d74e3  lea     r12, WPP_GLOBAL_Control
0x1800d74ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d74ee  jz      loc_1800D76AC
0x1800d74f4  test    esi, esi
0x1800d74f6  js      loc_1800D76C1
0x1800d74fc  mov     [rsp+2E0h+lpPathName], rbx
0x1800d7501  lea     rcx, [rbp+1E0h+var_254]
0x1800d7505  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d7509  inc     rax
0x1800d750c  cmp     [rcx+rax*2], bx
0x1800d7510  jnz     short loc_1800D7509
0x1800d7512  lea     r15, [rax+2]
0x1800d7516  mov     edx, 1
0x1800d751b  add     r15, r14
0x1800d751e  lea     r9, [rsp+2E0h+lpPathName]
0x1800d7523  mov     r8, r15
0x1800d7526  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800d752b  mov     esi, eax
0x1800d752d  test    eax, eax
0x1800d752f  jns     short loc_1800D7568
0x1800d7531  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7538  cmp     rcx, r12
0x1800d753b  jz      loc_1800D767C
0x1800d7541  test    byte ptr [rcx+1Ch], 1
0x1800d7545  jz      loc_1800D767C
0x1800d754b  mov     rcx, [rcx+10h]
0x1800d754f  lea     r8, WPP_fbe311bd82113ee81e8806f10330c179_Traceguids
0x1800d7556  mov     edx, 0Ah
0x1800d755b  mov     r9d, eax
0x1800d755e  call    WPP_SF_d
0x1800d7563  jmp     loc_1800D767C
0x1800d7568  mov     rbx, [rsp+2E0h+lpPathName]
0x1800d756d  mov     rdx, r15; unsigned __int64
0x1800d7570  mov     r8, [rsp+2E0h+var_298]; unsigned __int16 *
0x1800d7575  mov     rcx, rbx; unsigned __int16 *
0x1800d7578  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d757d  cmp     [rsp+2E0h+var_2B0], 0
0x1800d7582  jz      short loc_1800D758C
0x1800d7584  mov     dword ptr [rbx+r14*2], 5Ch ; '\'
0x1800d758c  lea     r8, [rbp+1E0h+var_254]; unsigned __int16 *
0x1800d7590  mov     rdx, r15; unsigned __int64
0x1800d7593  mov     rcx, rbx; unsigned __int16 *
0x1800d7596  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d759b  test    [rsp+2E0h+FindFileData], 10h
0x1800d75a0  jz      loc_1800D762C
0x1800d75a6  xor     r15d, r15d
0x1800d75a9  cmp     [rsp+2E0h+var_2AC], r15d
0x1800d75ae  jz      loc_1800D767C
0x1800d75b4  lea     ecx, [r15+2Eh]
0x1800d75b8  cmp     cx, [rbp+1E0h+var_254]
0x1800d75bc  jnz     short loc_1800D75DA
0x1800d75be  cmp     r15w, [rbp+1E0h+var_252]
0x1800d75c3  jz      loc_1800D767C
0x1800d75c9  cmp     cx, [rbp+1E0h+var_252]
0x1800d75cd  jnz     short loc_1800D75DA
0x1800d75cf  cmp     r15w, [rbp+1E0h+var_250]
0x1800d75d4  jz      loc_1800D767C
0x1800d75da  mov     edx, 1; int
0x1800d75df  mov     rcx, rbx; unsigned __int16 *
0x1800d75e2  call    ?DeleteFilesInDirectory@CMetaStoreUtils@@SAJPEBGH@Z; CMetaStoreUtils::DeleteFilesInDirectory(ushort const *,int)
0x1800d75e7  mov     esi, eax
0x1800d75e9  test    eax, eax
0x1800d75eb  js      loc_1800D767C
0x1800d75f1  mov     rcx, rbx; lpPathName
0x1800d75f4  call    cs:__imp_RemoveDirectoryW
0x1800d75fa  test    eax, eax
0x1800d75fc  jnz     short loc_1800D767C
0x1800d75fe  call    cs:__imp_GetLastError
0x1800d7604  mov     esi, eax
0x1800d7606  test    eax, eax
0x1800d7608  jle     short loc_1800D7613
0x1800d760a  movzx   esi, ax
0x1800d760d  or      esi, 80070000h
0x1800d7613  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d761a  cmp     rcx, r12
0x1800d761d  jz      short loc_1800D767C
0x1800d761f  test    byte ptr [rcx+1Ch], 1
0x1800d7623  jz      short loc_1800D767C
0x1800d7625  mov     edx, 0Bh
0x1800d762a  jmp     short loc_1800D7665
0x1800d762c  mov     rcx, rbx; lpFileName
0x1800d762f  call    cs:__imp_DeleteFileW
0x1800d7635  test    eax, eax
0x1800d7637  jnz     short loc_1800D767C
0x1800d7639  call    cs:__imp_GetLastError
0x1800d763f  mov     esi, eax
0x1800d7641  test    eax, eax
0x1800d7643  jle     short loc_1800D764E
0x1800d7645  movzx   esi, ax
0x1800d7648  or      esi, 80070000h
0x1800d764e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7655  cmp     rcx, r12
0x1800d7658  jz      short loc_1800D767C
0x1800d765a  test    byte ptr [rcx+1Ch], 1
0x1800d765e  jz      short loc_1800D767C
0x1800d7660  mov     edx, 0Ch
0x1800d7665  mov     rcx, [rcx+10h]
0x1800d7669  lea     r8, WPP_fbe311bd82113ee81e8806f10330c179_Traceguids
0x1800d7670  mov     r9, rbx
0x1800d7673  mov     dword ptr [rsp+2E0h+lpSearchFilter], esi
0x1800d7677  call    WPP_SF_Sd
0x1800d767c  mov     r15, [rsp+2E0h+hFindFile]
0x1800d7681  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x1800d7686  mov     rcx, r15; hFindFile
0x1800d7689  call    cs:__imp_FindNextFileW
0x1800d768f  lea     rcx, [rsp+2E0h+lpPathName]
0x1800d7694  mov     ebx, eax
0x1800d7696  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800d769b  test    ebx, ebx
0x1800d769d  mov     ebx, 0
0x1800d76a2  jnz     loc_1800D74F4
0x1800d76a8  test    esi, esi
0x1800d76aa  js      short loc_1800D76C1
0x1800d76ac  call    cs:__imp_GetLastError
0x1800d76b2  mov     esi, eax
0x1800d76b4  test    eax, eax
0x1800d76b6  jle     short loc_1800D76C1
0x1800d76b8  movzx   esi, ax
0x1800d76bb  or      esi, 80070000h
0x1800d76c1  lea     eax, [rsi+7FF8FFFEh]
0x1800d76c7  test    eax, 0FFFFFFEEh
0x1800d76cc  jnz     short loc_1800D76DA
0x1800d76ce  cmp     esi, 80070013h
0x1800d76d4  jz      short loc_1800D76DA
0x1800d76d6  mov     esi, ebx
0x1800d76d8  jmp     short loc_1800D7708
0x1800d76da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d76e1  cmp     rcx, r12
0x1800d76e4  jz      short loc_1800D7708
0x1800d76e6  test    byte ptr [rcx+1Ch], 1
0x1800d76ea  jz      short loc_1800D7708
0x1800d76ec  mov     rcx, [rcx+10h]
0x1800d76f0  lea     r8, WPP_fbe311bd82113ee81e8806f10330c179_Traceguids
0x1800d76f7  mov     edx, 0Dh
0x1800d76fc  mov     dword ptr [rsp+2E0h+lpSearchFilter], esi
0x1800d7700  mov     r9, rdi
0x1800d7703  call    WPP_SF_Sd
0x1800d7708  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800d770c  jz      short loc_1800D774A
0x1800d770e  mov     rcx, r15; hFindFile
0x1800d7711  call    cs:__imp_FindClose
0x1800d7717  jmp     short loc_1800D774A
0x1800d7719  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7720  lea     r12, WPP_GLOBAL_Control
0x1800d7727  cmp     rcx, r12
0x1800d772a  jz      short loc_1800D774A
0x1800d772c  test    byte ptr [rcx+1Ch], 1
0x1800d7730  jz      short loc_1800D774A
0x1800d7732  mov     rcx, [rcx+10h]
0x1800d7736  lea     r8, WPP_fbe311bd82113ee81e8806f10330c179_Traceguids
0x1800d773d  mov     edx, 0Eh
0x1800d7742  mov     r9d, eax
0x1800d7745  call    WPP_SF_d
0x1800d774a  lea     rcx, [rsp+2E0h+lpFileName]
0x1800d774f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800d7754  mov     eax, esi
0x1800d7756  mov     rcx, [rbp+1E0h+var_30]
0x1800d775d  xor     rcx, rsp; StackCookie
0x1800d7760  call    __security_check_cookie
0x1800d7765  lea     r11, [rsp+2E0h+var_20]
0x1800d776d  mov     rbx, [r11+38h]
0x1800d7771  mov     rsi, [r11+40h]
0x1800d7775  mov     rsp, r11
0x1800d7778  pop     r15
0x1800d777a  pop     r14
0x1800d777c  pop     r12
0x1800d777e  pop     rdi
0x1800d777f  pop     rbp
0x1800d7780  retn
```

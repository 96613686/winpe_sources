# ResetTracingDirectory

- ea: `0x1800baa3c`
- end: `0x1800bacec`
- name: `ResetTracingDirectory`
- size: `688`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800ba448`

## callees

- `0x18002cd80`
- `0x18002d720`
- `0x1800ba23c`
- `0x1800ba6b4`
- `0x1800baa3c`
- `0x1800bad2c`
- `0x1800bad78`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bac9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bacba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bac9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bacba`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800bac72`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800bac72`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800bab06`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800bab06`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800bab40`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800bacac`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800bab40`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800bacac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800bac07`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800bac7c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800bac07`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800bac7c`

## pseudocode

```c
__int64 __fastcall ResetTracingDirectory(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int *v3; // r12
  __int64 v5; // r15
  unsigned int v6; // eax
  WCHAR *v7; // r14
  unsigned int v8; // ebx
  __int64 v9; // rdi
  int v10; // r13d
  unsigned int v11; // esi
  int v12; // edx
  int v13; // ecx
  unsigned int v14; // ebx
  unsigned int v15; // r14d
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 FirstFile; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  unsigned int *v24; // [rsp+68h] [rbp-98h]
  _BYTE FindFileData[44]; // [rsp+70h] [rbp-90h] BYREF
  char v26[548]; // [rsp+9Ch] [rbp-64h] BYREF
  WCHAR FileName[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v28[528]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v3 = a3;
  v24 = a3;
  v22 = a2;
  v5 = a1;
  v23 = a1;
  v17 = 0;
  v18 = 0;
  lpFileName = 0;
  hMem = 0;
  memset_0(FindFileData, 0, 0x250u);
  if ( v3 )
    *v3 = 0;
  v6 = BuildCurrentLogFilePath(v5, a2, &lpFileName);
  v7 = (WCHAR *)lpFileName;
  v8 = v6;
  if ( v6 )
  {
    FirstFile = (__int64)FindFirstFileExW(lpFileName, FindExInfoBasic, FindFileData, FindExSearchNameMatch, 0, 0);
    v9 = FirstFile;
    if ( FirstFile == -1 )
    {
      v10 = 0;
    }
    else
    {
      if ( (int)RtlStringCchCopyW(v28, 260, v26) < 0 )
      {
        v8 = 0;
LABEL_29:
        FindClose((HANDLE)v9);
        goto LABEL_30;
      }
      v10 = 1;
      FindClose((HANDLE)v9);
      v9 = -1;
      FirstFile = -1;
    }
    v8 = QueryAndSortOldLogFiles(
           v5,
           a2,
           (unsigned __int64)v28 & -(__int64)(v10 != 0),
           (unsigned int)&v18,
           (__int64)&v17,
           (__int64)&hMem);
    if ( v8 )
    {
      v11 = v17;
      v12 = *(_DWORD *)(v5 + 36);
      v13 = *(_DWORD *)(v5 + 40);
      if ( v10 && v13 )
        --v13;
      if ( v17 > v13 + v12 )
      {
        v17 = 0;
        v14 = v11 - v13 - v12;
        if ( v11 - v13 != v12 )
        {
          v15 = v17;
          do
          {
            if ( (int)RtlStringCchPrintfW(FileName) >= 0 )
            {
              DeleteFileW(FileName);
              --v11;
            }
            ++v15;
          }
          while ( v15 < v14 );
          v9 = FirstFile;
          v7 = (WCHAR *)lpFileName;
          v5 = v23;
          v3 = v24;
        }
      }
      if ( v10 && (int)RtlStringCchPrintfW(FileName) >= 0 )
      {
        if ( *(_DWORD *)(v5 + 40) )
        {
          MoveFileW(v7, FileName);
          ++v11;
        }
        else
        {
          DeleteFileW(v7);
        }
      }
      v8 = 1;
      if ( v3 )
        *v3 = v11;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      if ( v9 != -1 )
        goto LABEL_29;
    }
  }
LABEL_30:
  if ( v7 )
    LocalFree(v7);
  return v8;
}

```

## disassembly

```asm
0x1800baa3c  mov     [rsp-8+arg_18], rbx
0x1800baa41  push    rbp
0x1800baa42  push    rsi
0x1800baa43  push    rdi
0x1800baa44  push    r12
0x1800baa46  push    r13
0x1800baa48  push    r14
0x1800baa4a  push    r15
0x1800baa4c  lea     rbp, [rsp-5F0h]
0x1800baa54  sub     rsp, 6F0h
0x1800baa5b  mov     rax, cs:__security_cookie
0x1800baa62  xor     rax, rsp
0x1800baa65  mov     [rbp+620h+var_40], rax
0x1800baa6c  mov     r12, r8
0x1800baa6f  mov     [rsp+720h+var_6B8], r8
0x1800baa74  mov     rsi, rdx
0x1800baa77  mov     [rsp+720h+var_6C8], rdx
0x1800baa7c  mov     r15, rcx
0x1800baa7f  mov     [rsp+720h+var_6C0], rcx
0x1800baa84  xor     edx, edx; Val
0x1800baa86  mov     [rsp+720h+var_6F0], 0
0x1800baa8e  mov     r8d, 250h; Size
0x1800baa94  mov     [rsp+720h+var_6EC], 0
0x1800baa9c  lea     rcx, [rsp+720h+FindFileData]; void *
0x1800baaa1  mov     [rsp+720h+lpFileName], 0
0x1800baaaa  mov     [rsp+720h+hMem], 0
0x1800baab3  call    memset_0
0x1800baab8  test    r12, r12
0x1800baabb  jz      short loc_1800BAAC5
0x1800baabd  mov     dword ptr [r12], 0
0x1800baac5  lea     r8, [rsp+720h+lpFileName]
0x1800baaca  mov     rdx, rsi
0x1800baacd  mov     rcx, r15
0x1800baad0  call    BuildCurrentLogFilePath
0x1800baad5  mov     r14, [rsp+720h+lpFileName]
0x1800baada  mov     ebx, eax
0x1800baadc  test    eax, eax
0x1800baade  jz      loc_1800BACB2
0x1800baae4  xor     r9d, r9d; fSearchOp
0x1800baae7  mov     [rsp+720h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1800baaef  lea     r8, [rsp+720h+FindFileData]; lpFindFileData
0x1800baaf4  mov     [rsp+720h+lpSearchFilter], 0; lpSearchFilter
0x1800baafd  mov     rcx, r14; lpFileName
0x1800bab00  lea     ebx, [r9+1]
0x1800bab04  mov     edx, ebx; fInfoLevelId
0x1800bab06  call    cs:__imp_FindFirstFileExW
0x1800bab0c  mov     [rsp+720h+var_6D0], rax
0x1800bab11  mov     rdi, rax
0x1800bab14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bab18  jz      short loc_1800BAB51
0x1800bab1a  lea     r8, [rbp+620h+var_684]
0x1800bab1e  mov     edx, 104h
0x1800bab23  lea     rcx, [rbp+620h+var_250]
0x1800bab2a  call    RtlStringCchCopyW
0x1800bab2f  test    eax, eax
0x1800bab31  jns     short loc_1800BAB3A
0x1800bab33  xor     ebx, ebx
0x1800bab35  jmp     loc_1800BACA9
0x1800bab3a  mov     rcx, rdi; hFindFile
0x1800bab3d  mov     r13d, ebx
0x1800bab40  call    cs:__imp_FindClose
0x1800bab46  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800bab4a  mov     [rsp+720h+var_6D0], rdi
0x1800bab4f  jmp     short loc_1800BAB54
0x1800bab51  xor     r13d, r13d
0x1800bab54  mov     eax, r13d
0x1800bab57  lea     r9, [rsp+720h+var_6EC]
0x1800bab5c  neg     eax
0x1800bab5e  mov     rdx, rsi
0x1800bab61  lea     rax, [rbp+620h+var_250]
0x1800bab68  mov     rcx, r15
0x1800bab6b  sbb     r8, r8
0x1800bab6e  and     r8, rax
0x1800bab71  lea     rax, [rsp+720h+hMem]
0x1800bab76  mov     qword ptr [rsp+720h+dwAdditionalFlags], rax
0x1800bab7b  lea     rax, [rsp+720h+var_6F0]
0x1800bab80  mov     [rsp+720h+lpSearchFilter], rax
0x1800bab85  call    QueryAndSortOldLogFiles
0x1800bab8a  mov     ebx, eax
0x1800bab8c  test    eax, eax
0x1800bab8e  jz      loc_1800BAC90
0x1800bab94  mov     esi, [rsp+720h+var_6F0]
0x1800bab98  mov     edx, [r15+24h]
0x1800bab9c  mov     ecx, [r15+28h]
0x1800baba0  test    r13d, r13d
0x1800baba3  jz      short loc_1800BABAB
0x1800baba5  test    ecx, ecx
0x1800baba7  jz      short loc_1800BABAB
0x1800baba9  dec     ecx
0x1800babab  lea     eax, [rcx+rdx]
0x1800babae  cmp     esi, eax
0x1800babb0  jbe     short loc_1800BAC2B
0x1800babb2  mov     ebx, esi
0x1800babb4  mov     [rsp+720h+var_6F0], 0
0x1800babbc  sub     ebx, ecx
0x1800babbe  sub     ebx, edx
0x1800babc0  jz      short loc_1800BAC2B
0x1800babc2  mov     r14d, [rsp+720h+var_6F0]
0x1800babc7  mov     r12d, edx
0x1800babca  mov     r15, [rsp+720h+hMem]
0x1800babcf  mov     rdi, [rsp+720h+var_6C8]
0x1800babd4  lea     eax, [r12+r14]
0x1800babd8  mov     r9, rdi
0x1800babdb  mov     rax, [r15+rax*8]
0x1800babdf  lea     r8, aSS_1; "%s\\%s"
0x1800babe6  mov     edx, 104h
0x1800babeb  mov     [rsp+720h+lpSearchFilter], rax
0x1800babf0  lea     rcx, [rbp+620h+FileName]; Buffer
0x1800babf7  call    RtlStringCchPrintfW
0x1800babfc  test    eax, eax
0x1800babfe  js      short loc_1800BAC0F
0x1800bac00  lea     rcx, [rbp+620h+FileName]; lpFileName
0x1800bac07  call    cs:__imp_DeleteFileW
0x1800bac0d  dec     esi
0x1800bac0f  inc     r14d
0x1800bac12  cmp     r14d, ebx
0x1800bac15  jb      short loc_1800BABD4
0x1800bac17  mov     rdi, [rsp+720h+var_6D0]
0x1800bac1c  mov     r14, [rsp+720h+lpFileName]
0x1800bac21  mov     r15, [rsp+720h+var_6C0]
0x1800bac26  mov     r12, [rsp+720h+var_6B8]
0x1800bac2b  test    r13d, r13d
0x1800bac2e  jz      short loc_1800BAC82
0x1800bac30  mov     eax, [rsp+720h+var_6EC]
0x1800bac34  lea     r8, aSS08xEtl; "%s\\%s%08x.etl"
0x1800bac3b  mov     r9, [rsp+720h+var_6C8]
0x1800bac40  lea     rcx, [rbp+620h+FileName]; Buffer
0x1800bac47  mov     [rsp+720h+dwAdditionalFlags], eax
0x1800bac4b  mov     edx, 104h
0x1800bac50  mov     rax, [r15]
0x1800bac53  mov     [rsp+720h+lpSearchFilter], rax
0x1800bac58  call    RtlStringCchPrintfW
0x1800bac5d  test    eax, eax
0x1800bac5f  js      short loc_1800BAC82
0x1800bac61  cmp     dword ptr [r15+28h], 0
0x1800bac66  mov     rcx, r14; lpFileName
0x1800bac69  jbe     short loc_1800BAC7C
0x1800bac6b  lea     rdx, [rbp+620h+FileName]; lpNewFileName
0x1800bac72  call    cs:__imp_MoveFileW
0x1800bac78  inc     esi
0x1800bac7a  jmp     short loc_1800BAC82
0x1800bac7c  call    cs:__imp_DeleteFileW
0x1800bac82  mov     ebx, 1
0x1800bac87  test    r12, r12
0x1800bac8a  jz      short loc_1800BAC90
0x1800bac8c  mov     [r12], esi
0x1800bac90  mov     rax, [rsp+720h+hMem]
0x1800bac95  test    rax, rax
0x1800bac98  jz      short loc_1800BACB2
0x1800bac9a  mov     rcx, rax; hMem
0x1800bac9d  call    cs:__imp_LocalFree
0x1800baca3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800baca7  jz      short loc_1800BACB2
0x1800baca9  mov     rcx, rdi; hFindFile
0x1800bacac  call    cs:__imp_FindClose
0x1800bacb2  test    r14, r14
0x1800bacb5  jz      short loc_1800BACC0
0x1800bacb7  mov     rcx, r14; hMem
0x1800bacba  call    cs:__imp_LocalFree
0x1800bacc0  mov     eax, ebx
0x1800bacc2  mov     rcx, [rbp+620h+var_40]
0x1800bacc9  xor     rcx, rsp; StackCookie
0x1800baccc  call    __security_check_cookie
0x1800bacd1  mov     rbx, [rsp+720h+arg_18]
0x1800bacd9  add     rsp, 6F0h
0x1800bace0  pop     r15
0x1800bace2  pop     r14
0x1800bace4  pop     r13
0x1800bace6  pop     r12
0x1800bace8  pop     rdi
0x1800bace9  pop     rsi
0x1800bacea  pop     rbp
0x1800baceb  retn
```

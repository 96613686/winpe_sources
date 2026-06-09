# WdsCopyFileEx

- ea: `0x1800394a8`
- end: `0x1800396e0`
- name: `WdsCopyFileEx`
- size: `568`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPCWSTR pszSrc@<rcx>, STRSAFE_LPCWSTR@<rdx>, DWORD dwMilliseconds, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180038b44`

## callees

- `0x180038c34`
- `0x180039394`
- `0x1800394a8`
- `0x1800396e8`
- `0x18003c464`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800395fd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800395fd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180039619`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180039619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039699`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800396b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039699`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800396b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800396a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800396c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800396a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800396c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800394e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039693`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800394e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003956f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003956f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039668`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180039556`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180039556`

## string_xrefs

- `0x180039637`: `WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x`
- `0x1800395ce`: `WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms`
- `0x180039671`: `WdsCopyFileEx: Failed to delete %s. GLE = 0x%x`

## pseudocode

```c
__int64 WdsCopyFileEx(
        STRSAFE_LPCWSTR pszSrc,
        STRSAFE_LPCWSTR a2,
        DWORD (__stdcall *a3)(LARGE_INTEGER TotalFileSize, LARGE_INTEGER TotalBytesTransferred, LARGE_INTEGER StreamSize, LARGE_INTEGER StreamBytesTransferred, DWORD dwStreamNumber, DWORD dwCallbackReason, HANDLE hSourceFile, HANDLE hDestinationFile, LPVOID lpData),
        void *a4,
        ...)
{
  char v4; // bl
  unsigned int v8; // edi
  DWORD v9; // r15d
  void *v10; // r13
  void *v11; // rbp
  unsigned int v12; // r14d
  DWORD LastError; // eax
  int v14; // r11d
  DWORD v15; // edi
  DWORD v16; // ebx
  DWORD v17; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  LPBOOL pbCancel; // [rsp+20h] [rbp-58h]
  LPBOOL pbCancela; // [rsp+20h] [rbp-58h]
  __int64 dwCopyFlags; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]
  __int64 dwMilliseconds; // [rsp+A0h] [rbp+28h] BYREF
  va_list dwMillisecondsa; // [rsp+A0h] [rbp+28h]
  __int64 v28; // [rsp+A8h] [rbp+30h] BYREF
  va_list va1; // [rsp+A8h] [rbp+30h]
  va_list va2; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(dwMillisecondsa, a4);
  dwMilliseconds = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v28 = va_arg(va2, _QWORD);
  v4 = v28;
  if ( (v28 & 0xFFFFFFE0) != 0 )
  {
    SetLastError(0x57u);
    return 0;
  }
  else
  {
    v8 = 0;
    v9 = v28 & 1 | 0x1000;
    if ( (v28 & 8) == 0 )
      v9 = v28 & 1;
    v10 = (void *)PrepareUnicodePathEx(pszSrc);
    if ( v10 )
    {
      v11 = (void *)PrepareUnicodePathEx(a2);
      if ( v11 )
      {
        v12 = 0;
        while ( 1 )
        {
          v8 = CopyFileExW(pszSrc, a2, a3, a4, 0, v9);
          if ( v8 )
            break;
          if ( (v4 & 2) == 0 )
            goto LABEL_26;
          LastError = GetLastError();
          LODWORD(v28) = v8;
          LODWORD(dwMilliseconds) = v8;
          ++v12;
          if ( (unsigned int)WdsGetCopyRetryData(LastError, (__int64 *)va1, (__int64 *)dwMillisecondsa) )
          {
            if ( v12 >= (unsigned int)v28 )
              goto LABEL_26;
            v15 = dwMilliseconds;
          }
          else
          {
            if ( v12 >= 2 )
              goto LABEL_26;
            v15 = 3000;
          }
          LODWORD(v23) = v15;
          LODWORD(dwCopyFlags) = v14;
          LibLog(
            &g_WdsLibLog,
            0x4000000,
            L"WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms",
            pszSrc,
            a2,
            dwCopyFlags,
            v23);
          if ( v15 )
            Sleep(v15);
        }
        if ( (v4 & 4) != 0 )
        {
          v8 = SetFileAttributesW(a2, 0x80u);
          if ( !v8 )
          {
            v16 = GetLastError();
            if ( !v16 )
              v16 = 31;
            LODWORD(pbCancel) = v16;
            LibLog(
              &g_WdsLibLog,
              0x2000000,
              L"WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x",
              a2,
              pbCancel);
            if ( !DeleteFileEx2((__int64)a2, 0) )
            {
              v17 = GetLastError();
              if ( !v17 )
                v17 = 31;
              LODWORD(pbCancela) = v17;
              LibLog(&g_WdsLibLog, 0x2000000, L"WdsCopyFileEx: Failed to delete %s. GLE = 0x%x", a2, pbCancela);
            }
            SetLastError(v16);
          }
        }
      }
LABEL_26:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
      if ( v11 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v11);
      }
    }
    return v8;
  }
}

```

## disassembly

```asm
0x1800394a8  mov     [rsp+arg_0], rbx
0x1800394ad  mov     [rsp+lpData], r9
0x1800394b2  mov     [rsp+lpProgressRoutine], r8
0x1800394b7  push    rbp
0x1800394b8  push    rsi
0x1800394b9  push    rdi
0x1800394ba  push    r12
0x1800394bc  push    r13
0x1800394be  push    r14
0x1800394c0  push    r15
0x1800394c2  sub     rsp, 40h
0x1800394c6  mov     ebx, dword ptr [rsp+78h+arg_28]
0x1800394cd  mov     rsi, rdx
0x1800394d0  mov     r12, rcx
0x1800394d3  test    ebx, 0FFFFFFE0h
0x1800394d9  jz      short loc_1800394ED
0x1800394db  mov     ecx, 57h ; 'W'; dwErrCode
0x1800394e0  call    cs:__imp_SetLastError
0x1800394e6  xor     eax, eax
0x1800394e8  jmp     loc_1800396C8
0x1800394ed  mov     ecx, ebx
0x1800394ef  xor     edi, edi
0x1800394f1  and     ecx, 1
0x1800394f4  mov     r15d, ecx
0x1800394f7  bts     r15d, 0Ch
0x1800394fc  test    bl, 8
0x1800394ff  cmovz   r15d, ecx
0x180039503  xor     edx, edx
0x180039505  mov     rcx, r12; pszSrc
0x180039508  call    PrepareUnicodePathEx
0x18003950d  mov     r13, rax
0x180039510  test    rax, rax
0x180039513  jz      loc_1800396C6
0x180039519  xor     edx, edx
0x18003951b  mov     rcx, rsi; pszSrc
0x18003951e  call    PrepareUnicodePathEx
0x180039523  mov     rbp, rax
0x180039526  test    rax, rax
0x180039529  jz      loc_180039699
0x18003952f  xor     r14d, r14d
0x180039532  mov     r9, [rsp+78h+lpData]; lpData
0x18003953a  mov     rdx, rsi; lpNewFileName
0x18003953d  mov     r8, [rsp+78h+lpProgressRoutine]; lpProgressRoutine
0x180039545  mov     rcx, r12; lpExistingFileName
0x180039548  mov     dword ptr [rsp+78h+dwCopyFlags], r15d; dwCopyFlags
0x18003954d  mov     [rsp+78h+pbCancel], 0; pbCancel
0x180039556  call    cs:__imp_CopyFileExW
0x18003955c  mov     edi, eax
0x18003955e  test    eax, eax
0x180039560  jnz     loc_180039608
0x180039566  test    bl, 2
0x180039569  jz      loc_180039699
0x18003956f  call    cs:__imp_GetLastError
0x180039575  lea     r8, [rsp+78h+dwMilliseconds]
0x18003957d  mov     dword ptr [rsp+78h+arg_28], edi
0x180039584  mov     ecx, eax
0x180039586  mov     dword ptr [rsp+78h+dwMilliseconds], edi
0x18003958d  lea     rdx, [rsp+78h+arg_28]
0x180039595  mov     r11d, eax
0x180039598  inc     r14d
0x18003959b  call    WdsGetCopyRetryData
0x1800395a0  test    eax, eax
0x1800395a2  jz      short loc_1800395BB
0x1800395a4  cmp     r14d, dword ptr [rsp+78h+arg_28]
0x1800395ac  jnb     loc_180039699
0x1800395b2  mov     edi, dword ptr [rsp+78h+dwMilliseconds]
0x1800395b9  jmp     short loc_1800395CA
0x1800395bb  cmp     r14d, 2
0x1800395bf  jnb     loc_180039699
0x1800395c5  mov     edi, 0BB8h
0x1800395ca  mov     dword ptr [rsp+78h+var_48], edi
0x1800395ce  lea     r8, aWdscopyfileexF_0; "WdsCopyFileEx: Failed to copy [%s] to ["...
0x1800395d5  mov     dword ptr [rsp+78h+dwCopyFlags], r11d
0x1800395da  lea     rcx, g_WdsLibLog
0x1800395e1  mov     r9, r12
0x1800395e4  mov     [rsp+78h+pbCancel], rsi
0x1800395e9  mov     edx, 4000000h
0x1800395ee  call    LibLog
0x1800395f3  test    edi, edi
0x1800395f5  jz      loc_180039532
0x1800395fb  mov     ecx, edi; dwMilliseconds
0x1800395fd  call    cs:__imp_Sleep
0x180039603  jmp     loc_180039532
0x180039608  test    bl, 4
0x18003960b  jz      loc_180039699
0x180039611  mov     edx, 80h; dwFileAttributes
0x180039616  mov     rcx, rsi; lpFileName
0x180039619  call    cs:__imp_SetFileAttributesW
0x18003961f  mov     edi, eax
0x180039621  test    eax, eax
0x180039623  jnz     short loc_180039699
0x180039625  call    cs:__imp_GetLastError
0x18003962b  lea     r15d, [rdi+1Fh]
0x18003962f  mov     r14d, 2000000h
0x180039635  test    eax, eax
0x180039637  lea     r8, aWdscopyfileexF_1; "WdsCopyFileEx: Failed to strip file att"...
0x18003963e  mov     ebx, eax
0x180039640  lea     rcx, g_WdsLibLog
0x180039647  cmovz   ebx, r15d
0x18003964b  mov     r9, rsi
0x18003964e  mov     edx, r14d
0x180039651  mov     dword ptr [rsp+78h+pbCancel], ebx
0x180039655  call    LibLog
0x18003965a  xor     edx, edx
0x18003965c  mov     rcx, rsi
0x18003965f  call    DeleteFileEx2
0x180039664  test    eax, eax
0x180039666  jnz     short loc_180039691
0x180039668  call    cs:__imp_GetLastError
0x18003966e  mov     r9, rsi
0x180039671  lea     r8, aWdscopyfileexF; "WdsCopyFileEx: Failed to delete %s. GLE"...
0x180039678  test    eax, eax
0x18003967a  lea     rcx, g_WdsLibLog
0x180039681  mov     edx, r14d
0x180039684  cmovz   eax, r15d
0x180039688  mov     dword ptr [rsp+78h+pbCancel], eax
0x18003968c  call    LibLog
0x180039691  mov     ecx, ebx; dwErrCode
0x180039693  call    cs:__imp_SetLastError
0x180039699  call    cs:__imp_GetProcessHeap
0x18003969f  mov     r8, r13; lpMem
0x1800396a2  xor     edx, edx; dwFlags
0x1800396a4  mov     rcx, rax; hHeap
0x1800396a7  call    cs:__imp_HeapFree
0x1800396ad  test    rbp, rbp
0x1800396b0  jz      short loc_1800396C6
0x1800396b2  call    cs:__imp_GetProcessHeap
0x1800396b8  mov     r8, rbp; lpMem
0x1800396bb  xor     edx, edx; dwFlags
0x1800396bd  mov     rcx, rax; hHeap
0x1800396c0  call    cs:__imp_HeapFree
0x1800396c6  mov     eax, edi
0x1800396c8  mov     rbx, [rsp+78h+arg_0]
0x1800396d0  add     rsp, 40h
0x1800396d4  pop     r15
0x1800396d6  pop     r14
0x1800396d8  pop     r13
0x1800396da  pop     r12
0x1800396dc  pop     rdi
0x1800396dd  pop     rsi
0x1800396de  pop     rbp
0x1800396df  retn
```

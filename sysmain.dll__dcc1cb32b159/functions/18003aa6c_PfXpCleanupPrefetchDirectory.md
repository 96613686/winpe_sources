# PfXpCleanupPrefetchDirectory

- ea: `0x18003aa6c`
- end: `0x18003af43`
- name: `PfXpCleanupPrefetchDirectory`
- size: `1239`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022058`
- `0x180033740`
- `0x180094350`

## callees

- `0x180019bf8`
- `0x180023e88`
- `0x18003aa6c`
- `0x18003b0a8`
- `0x18003bafc`
- `0x1800624c8`
- `0x18006fd9c`
- `0x180073038`
- `0x180094e94`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!qsort` at `0x18003adbd`
- `msvcrt!qsort` at `0x18003adbd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003aafd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003aafd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003ae8e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003ae8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ab08`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ab08`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003ad6e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003aef9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003ad6e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18003aef9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ac31`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ae06`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ac31`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ae06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aec6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aee3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aec6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aee3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003abc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ad05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003abc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ad05`

## pseudocode

```c
__int64 __fastcall PfXpCleanupPrefetchDirectory(__int64 a1, __int64 a2)
{
  unsigned int v4; // r15d
  unsigned int *v5; // rsi
  void *v6; // r14
  struct _FILETIME v7; // rbx
  int v8; // eax
  unsigned __int64 v9; // r12
  unsigned int started; // edi
  unsigned int *v11; // rax
  unsigned int NextScenarioFileInfo; // eax
  int v13; // eax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // r8
  bool v17; // cf
  unsigned int v18; // ecx
  int v19; // eax
  void *v20; // rcx
  wchar_t *v21; // rax
  __int64 v22; // r11
  unsigned __int64 v23; // rcx
  unsigned int v24; // ebx
  size_t v25; // rcx
  unsigned int v26; // r12d
  __int64 v27; // rbx
  unsigned int v28; // edi
  unsigned int i; // ebx
  void *v30; // r8
  unsigned int v32; // [rsp+34h] [rbp-CCh]
  unsigned int v33; // [rsp+34h] [rbp-CCh]
  size_t v34; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+50h] [rbp-B0h]
  int v36; // [rsp+54h] [rbp-ACh]
  __int64 v37; // [rsp+58h] [rbp-A8h]
  size_t cbDest; // [rsp+60h] [rbp-A0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+80h] [rbp-80h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName; // [rsp+2E0h] [rbp+1E0h]
  __int64 v45; // [rsp+2E8h] [rbp+1E8h]
  int v46; // [rsp+2F0h] [rbp+1F0h]
  __int64 v47; // [rsp+2F8h] [rbp+1F8h]
  __int64 v48; // [rsp+300h] [rbp+200h]

  v40 = a1;
  memset_0(&FindFileData, 0, 0x288u);
  v37 = 0xFFFFFFFFLL;
  v4 = 0;
  SystemTimeAsFileTime = 0;
  v5 = 0;
  v34 = 0;
  v6 = 0;
  LODWORD(v41) = 0;
  v36 = 0;
  if ( a1 )
  {
    v36 = 1;
    RtlAcquireSRWLockExclusive(&qword_1800D3C30);
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v7 = SystemTimeAsFileTime;
  lpFileName = 0;
  v45 = 0;
  v46 = 0;
  v48 = 0;
  v47 = -1;
  if ( a2 )
  {
    v8 = *(_DWORD *)(a2 + 368);
    v9 = *(_QWORD *)(a2 + 376);
  }
  else
  {
    v8 = 512;
    v9 = 0x1000000;
  }
  v32 = v8;
  started = PfXpCountFilesInDirectory((PCWSTR)(*(_QWORD *)&PfSvcGlobals + 888LL));
  if ( !started )
  {
    started = PfXpStartScenarioFileCursor(&FindFileData, (STRSAFE_LPCWSTR)(*(_QWORD *)&PfSvcGlobals + 888LL));
    if ( started )
    {
LABEL_38:
      qword_1800D3C40 = 0;
      dword_1800D3C38 = 0;
      goto LABEL_39;
    }
    v11 = (unsigned int *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0);
    v5 = v11;
    if ( !v11 )
    {
LABEL_9:
      started = 8;
      goto LABEL_38;
    }
    memset_0(v11, 0, 0);
    v35 = 0;
    started = PfXpTaskCheckContinue(v40);
    if ( started )
      goto LABEL_38;
    NextScenarioFileInfo = PfXpGetNextScenarioFileInfo(&FindFileData);
    started = NextScenarioFileInfo;
    if ( NextScenarioFileInfo != 18 )
    {
      if ( NextScenarioFileInfo )
        goto LABEL_38;
      if ( (unsigned int)v45 <= 0x32 )
      {
        v13 = PfXpScenarioOpen(lpFileName, 2, &v34);
        v6 = (void *)v34;
        if ( !v13 )
        {
          v14 = *(_QWORD *)(v34 + 128);
          if ( *(_QWORD *)&v7 <= v14 )
            LODWORD(v15) = 0;
          else
            v15 = (*(_QWORD *)&v7 - v14) / 0x861C46800LL;
          v16 = (unsigned __int64)*(unsigned int *)(v34 + 200) << 8;
          if ( (_DWORD)v15 )
            v16 /= (unsigned int)v15;
          v17 = (*(_DWORD *)(v34 + 208) & 3) != 0;
          v42 = 0;
          v19 = -1;
          if ( v16 < 0xFFFFFFFF )
            v19 = v16;
          v18 = *v5 & 0x7FFFFFFF | (v17 ? 0x80000000 : 0);
          *v5 = v18 ^ (v18 ^ v19) & 0x7FFFFFFF;
          v20 = *(void **)(*(_QWORD *)&PfSvcGlobals + 88LL);
          cbDest = (unsigned int)(2 * HIDWORD(v45) + 2);
          v21 = (wchar_t *)HeapAlloc(v20, 0, cbDest);
          *(_QWORD *)((char *)v5 + v42 + 8) = v21;
          if ( !v21 )
            goto LABEL_9;
          StringCbCopyW(v21, cbDest, lpFileName);
          *(unsigned int *)((char *)v5 + v22 + 16) = v15;
          v23 = (unsigned __int64)FindFileData.nFileSizeHigh << 32;
          *(_QWORD *)((char *)v5 + v22 + 24) = v23;
          *(_QWORD *)((char *)v5 + v22 + 24) = v23 + FindFileData.nFileSizeLow;
          v4 = 1;
        }
      }
      else
      {
        DeleteFileW(lpFileName);
      }
      ++v35;
      if ( v6 )
      {
        VirtualFree(v6, 0, 0x8000u);
        v6 = 0;
        v34 = 0;
      }
    }
    v24 = v32 >> 1;
    v33 = v24;
    cbDest = v9 >> 1;
    if ( v4 > v24 )
    {
      qsort(v5, v4, 0x20u, PfXpCompareScenarioAgeInfo);
      v25 = 0;
      v26 = 0;
      while ( 1 )
      {
        v34 = v25;
        if ( v26 >= v4 || v4 - v26 <= v24 && v25 <= cbDest )
          break;
        started = PfXpTaskCheckContinue(v40);
        if ( started )
          goto LABEL_38;
        v27 = 8LL * v26;
        v28 = v5[v27 + 4];
        DeleteFileW(*(LPCWSTR *)&v5[v27 + 2]);
        ++v26;
        v25 = v34 - *(_QWORD *)&v5[v27 + 6];
        v24 = v33;
        if ( (unsigned int)v37 < v28 )
          v28 = v37;
        v37 = v28;
      }
      started = PfXpCountFilesInDirectory((PCWSTR)(*(_QWORD *)&PfSvcGlobals + 888LL));
      v41 = 0;
    }
    else
    {
      started = 0;
    }
    goto LABEL_38;
  }
LABEL_39:
  if ( v36 )
    RtlReleaseSRWLockExclusive(&qword_1800D3C30);
  PfXpCleanupScenarioFileCursor(&FindFileData);
  if ( v5 )
  {
    for ( i = 0; i < v4; ++i )
    {
      v30 = *(void **)&v5[8 * i + 2];
      if ( v30 )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v30);
    }
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v5);
  }
  if ( v6 )
    VirtualFree(v6, 0, 0x8000u);
  PfXpLogCleanupPrefetchDir(0, 0, v41, v37, started);
  return started;
}

```

## disassembly

```asm
0x18003aa6c  push    rbp
0x18003aa6e  push    rbx
0x18003aa6f  push    rsi
0x18003aa70  push    rdi
0x18003aa71  push    r12
0x18003aa73  push    r13
0x18003aa75  push    r14
0x18003aa77  push    r15
0x18003aa79  lea     rbp, [rsp-238h]
0x18003aa81  sub     rsp, 338h
0x18003aa88  mov     rax, cs:__security_cookie
0x18003aa8f  xor     rax, rsp
0x18003aa92  mov     [rbp+270h+var_50], rax
0x18003aa99  mov     rdi, rdx
0x18003aa9c  mov     [rsp+370h+var_300], rcx
0x18003aaa1  mov     rbx, rcx
0x18003aaa4  xor     edx, edx; Val
0x18003aaa6  lea     rcx, [rbp+270h+FindFileData]; void *
0x18003aaaa  mov     r8d, 288h; Size
0x18003aab0  call    memset_0
0x18003aab5  xor     r13d, r13d
0x18003aab8  mov     eax, 0FFFFFFFFh
0x18003aabd  mov     [rsp+370h+var_318], rax
0x18003aac2  mov     r15d, r13d
0x18003aac5  mov     qword ptr [rsp+370h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18003aaca  mov     esi, r13d
0x18003aacd  mov     [rsp+370h+var_328], r13
0x18003aad2  mov     r14d, r13d
0x18003aad5  mov     [rsp+370h+var_340], r13d
0x18003aada  mov     [rsp+370h+var_338], r13
0x18003aadf  mov     dword ptr [rsp+370h+var_2F8], r13d
0x18003aae4  mov     [rsp+370h+var_31C], r13d
0x18003aae9  test    rbx, rbx
0x18003aaec  jz      short loc_18003AB03
0x18003aaee  lea     rcx, qword_1800D3C30
0x18003aaf5  mov     [rsp+370h+var_31C], 1
0x18003aafd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003ab03  lea     rcx, [rsp+370h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003ab08  call    cs:__imp_GetSystemTimeAsFileTime
0x18003ab0e  mov     rbx, qword ptr [rsp+370h+SystemTimeAsFileTime.dwLowDateTime]
0x18003ab13  mov     [rbp+270h+lpFileName], r13
0x18003ab1a  mov     [rbp+270h+var_88], r13
0x18003ab21  mov     [rbp+270h+var_80], r13d
0x18003ab28  mov     [rbp+270h+var_70], r13
0x18003ab2f  mov     [rbp+270h+var_78], 0FFFFFFFFFFFFFFFFh
0x18003ab3a  test    rdi, rdi
0x18003ab3d  jz      short loc_18003AB4E
0x18003ab3f  mov     eax, [rdi+170h]
0x18003ab45  mov     r12, [rdi+178h]
0x18003ab4c  jmp     short loc_18003AB59
0x18003ab4e  mov     eax, 200h
0x18003ab53  mov     r12d, 1000000h
0x18003ab59  mov     rcx, cs:PfSvcGlobals
0x18003ab60  lea     r9, [rsp+370h+var_338]
0x18003ab65  add     rcx, 378h; DosPathName
0x18003ab6c  mov     [rsp+370h+var_33C], eax
0x18003ab70  lea     r8, [rsp+370h+var_340]
0x18003ab75  call    PfXpCountFilesInDirectory
0x18003ab7a  mov     edi, eax
0x18003ab7c  test    eax, eax
0x18003ab7e  jnz     loc_18003AE7B
0x18003ab84  mov     rdx, cs:PfSvcGlobals
0x18003ab8b  lea     rcx, [rbp+270h+FindFileData]; lpFindFileData
0x18003ab8f  add     rdx, 378h; pszSrc
0x18003ab96  call    PfXpStartScenarioFileCursor
0x18003ab9b  mov     r13d, [rsp+370h+var_340]
0x18003aba0  mov     edi, eax
0x18003aba2  test    eax, eax
0x18003aba4  jnz     loc_18003AE67
0x18003abaa  mov     rcx, cs:PfSvcGlobals
0x18003abb1  mov     eax, r13d
0x18003abb4  shl     eax, 5
0x18003abb7  xor     edx, edx; dwFlags
0x18003abb9  mov     r8d, eax; dwBytes
0x18003abbc  mov     edi, eax
0x18003abbe  mov     rcx, [rcx+58h]; hHeap
0x18003abc2  call    cs:__imp_HeapAlloc
0x18003abc8  mov     rsi, rax
0x18003abcb  test    rax, rax
0x18003abce  jnz     short loc_18003ABDA
0x18003abd0  mov     edi, 8
0x18003abd5  jmp     loc_18003AE67
0x18003abda  mov     r8, rdi; Size
0x18003abdd  xor     edx, edx; Val
0x18003abdf  mov     rcx, rsi; void *
0x18003abe2  call    memset_0
0x18003abe7  mov     [rsp+370h+var_330], r14d
0x18003abec  mov     [rsp+370h+var_320], r14d
0x18003abf1  mov     rcx, [rsp+370h+var_300]
0x18003abf6  call    PfXpTaskCheckContinue
0x18003abfb  mov     edi, eax
0x18003abfd  test    eax, eax
0x18003abff  jnz     loc_18003AE67
0x18003ac05  lea     rcx, [rbp+270h+FindFileData]; lpFindFileData
0x18003ac09  call    PfXpGetNextScenarioFileInfo
0x18003ac0e  mov     edi, eax
0x18003ac10  cmp     eax, 12h
0x18003ac13  jz      loc_18003AD85
0x18003ac19  test    eax, eax
0x18003ac1b  jnz     loc_18003AE67
0x18003ac21  cmp     dword ptr [rbp+270h+var_88], 32h ; '2'
0x18003ac28  mov     rcx, [rbp+270h+lpFileName]; lpFileName
0x18003ac2f  jbe     short loc_18003AC3C
0x18003ac31  call    cs:__imp_DeleteFileW
0x18003ac37  jmp     loc_18003AD54
0x18003ac3c  lea     r8, [rsp+370h+var_328]
0x18003ac41  mov     edx, 2
0x18003ac46  call    PfXpScenarioOpen
0x18003ac4b  mov     r14, [rsp+370h+var_328]
0x18003ac50  test    eax, eax
0x18003ac52  jnz     loc_18003AD54
0x18003ac58  mov     rcx, [r14+80h]
0x18003ac5f  cmp     rbx, rcx
0x18003ac62  jbe     short loc_18003AC7E
0x18003ac64  mov     rax, rbx
0x18003ac67  xor     edx, edx
0x18003ac69  sub     rax, rcx
0x18003ac6c  mov     rcx, 861C46800h
0x18003ac76  div     rcx
0x18003ac79  mov     rdi, rax
0x18003ac7c  jmp     short loc_18003AC80
0x18003ac7e  xor     edi, edi
0x18003ac80  mov     r8d, [r14+0C8h]
0x18003ac87  shl     r8, 8
0x18003ac8b  test    edi, edi
0x18003ac8d  jz      short loc_18003AC9C
0x18003ac8f  mov     rax, r8
0x18003ac92  mov     ecx, edi
0x18003ac94  xor     edx, edx
0x18003ac96  div     rcx
0x18003ac99  mov     r8, rax
0x18003ac9c  mov     eax, [r14+0D0h]
0x18003aca3  mov     r10d, 7FFFFFFFh
0x18003aca9  mov     edx, [rsp+370h+var_330]
0x18003acad  and     al, 3
0x18003acaf  shl     rdx, 5
0x18003acb3  mov     r9d, 0FFFFFFFFh
0x18003acb9  neg     al
0x18003acbb  mov     [rbp+270h+var_2F0], rdx
0x18003acbf  sbb     ecx, ecx
0x18003acc1  mov     eax, [rdx+rsi]
0x18003acc4  and     ecx, 80000000h
0x18003acca  and     eax, r10d
0x18003accd  or      ecx, eax
0x18003accf  mov     eax, r9d
0x18003acd2  cmp     r8, r9
0x18003acd5  cmovb   rax, r8
0x18003acd9  xor     eax, ecx
0x18003acdb  and     eax, r10d
0x18003acde  xor     eax, ecx
0x18003ace0  mov     [rdx+rsi], eax
0x18003ace3  xor     edx, edx; dwFlags
0x18003ace5  mov     eax, dword ptr [rbp+270h+var_88+4]
0x18003aceb  mov     rcx, cs:PfSvcGlobals
0x18003acf2  lea     eax, ds:2[rax*2]
0x18003acf9  mov     rcx, [rcx+58h]; hHeap
0x18003acfd  mov     r8d, eax; dwBytes
0x18003ad00  mov     [rsp+370h+cbDest], rax
0x18003ad05  call    cs:__imp_HeapAlloc
0x18003ad0b  mov     r11, [rbp+270h+var_2F0]
0x18003ad0f  mov     [r11+rsi+8], rax
0x18003ad14  test    rax, rax
0x18003ad17  jz      loc_18003ABD0
0x18003ad1d  mov     r8, [rbp+270h+lpFileName]; pszSrc
0x18003ad24  mov     rcx, rax; pszDest
0x18003ad27  mov     rdx, [rsp+370h+cbDest]; cbDest
0x18003ad2c  call    StringCbCopyW
0x18003ad31  inc     [rsp+370h+var_330]
0x18003ad35  mov     [r11+rsi+10h], edi
0x18003ad3a  mov     ecx, [rbp+270h+FindFileData.nFileSizeHigh]
0x18003ad3d  shl     rcx, 20h
0x18003ad41  mov     [r11+rsi+18h], rcx
0x18003ad46  mov     eax, [rbp+270h+FindFileData.nFileSizeLow]
0x18003ad49  add     rax, rcx
0x18003ad4c  mov     [r11+rsi+18h], rax
0x18003ad51  inc     r15d
0x18003ad54  mov     edi, [rsp+370h+var_320]
0x18003ad58  inc     edi
0x18003ad5a  mov     [rsp+370h+var_320], edi
0x18003ad5e  test    r14, r14
0x18003ad61  jz      short loc_18003AD7C
0x18003ad63  xor     edx, edx; dwSize
0x18003ad65  mov     r8d, 8000h; dwFreeType
0x18003ad6b  mov     rcx, r14; lpAddress
0x18003ad6e  call    cs:__imp_VirtualFree
0x18003ad74  xor     r14d, r14d
0x18003ad77  mov     [rsp+370h+var_328], r14
0x18003ad7c  cmp     edi, r13d
0x18003ad7f  jb      loc_18003ABF1
0x18003ad85  mov     ebx, [rsp+370h+var_33C]
0x18003ad89  shr     ebx, 1
0x18003ad8b  shr     r12, 1
0x18003ad8e  mov     [rsp+370h+var_33C], ebx
0x18003ad92  mov     [rsp+370h+cbDest], r12
0x18003ad97  cmp     r15d, ebx
0x18003ad9a  ja      short loc_18003ADAA
0x18003ad9c  cmp     [rsp+370h+var_338], r12
0x18003ada1  ja      short loc_18003ADAA
0x18003ada3  xor     edi, edi
0x18003ada5  jmp     loc_18003AE67
0x18003adaa  mov     edx, r15d; NumOfElements
0x18003adad  lea     r9, PfXpCompareScenarioAgeInfo; CompareFunction
0x18003adb4  mov     r8d, 20h ; ' '; SizeOfElements
0x18003adba  mov     rcx, rsi; Base
0x18003adbd  call    cs:__imp_qsort
0x18003adc3  mov     rcx, [rsp+370h+var_338]
0x18003adc8  xor     r12d, r12d
0x18003adcb  mov     [rsp+370h+var_328], rcx
0x18003add0  cmp     r12d, r15d
0x18003add3  jnb     short loc_18003AE30
0x18003add5  mov     eax, r15d
0x18003add8  sub     eax, r12d
0x18003addb  cmp     eax, ebx
0x18003addd  ja      short loc_18003ADE6
0x18003addf  cmp     rcx, [rsp+370h+cbDest]
0x18003ade4  jbe     short loc_18003AE30
0x18003ade6  mov     rcx, [rsp+370h+var_300]
0x18003adeb  call    PfXpTaskCheckContinue
0x18003adf0  mov     edi, eax
0x18003adf2  test    eax, eax
0x18003adf4  jnz     short loc_18003AE67
0x18003adf6  mov     ebx, r12d
0x18003adf9  shl     rbx, 5
0x18003adfd  mov     rcx, [rbx+rsi+8]; lpFileName
0x18003ae02  mov     edi, [rbx+rsi+10h]
0x18003ae06  call    cs:__imp_DeleteFileW
0x18003ae0c  mov     rax, [rsp+370h+var_318]
0x18003ae11  inc     r12d
0x18003ae14  mov     rcx, [rsp+370h+var_328]
0x18003ae19  sub     rcx, [rbx+rsi+18h]
0x18003ae1e  mov     ebx, [rsp+370h+var_33C]
0x18003ae22  cmp     eax, edi
0x18003ae24  cmovb   edi, eax
0x18003ae27  mov     eax, edi
0x18003ae29  mov     [rsp+370h+var_318], rax
0x18003ae2e  jmp     short loc_18003ADCB
0x18003ae30  mov     rcx, cs:PfSvcGlobals
0x18003ae37  lea     r9, [rsp+370h+var_338]
0x18003ae3c  mov     rbx, [rsp+370h+var_338]
0x18003ae41  lea     r8, [rsp+370h+var_340]
0x18003ae46  add     rcx, 378h; DosPathName
0x18003ae4d  call    PfXpCountFilesInDirectory
0x18003ae52  sub     rbx, [rsp+370h+var_338]
0x18003ae57  mov     edi, eax
0x18003ae59  mov     r13d, [rsp+370h+var_340]
0x18003ae5e  shr     rbx, 0Ah
0x18003ae62  mov     [rsp+370h+var_2F8], rbx
0x18003ae67  mov     eax, dword ptr [rsp+370h+var_338]
0x18003ae6b  mov     cs:qword_1800D3C40, rax
0x18003ae72  mov     cs:dword_1800D3C38, r13d
0x18003ae79  jmp     short loc_18003AE80
0x18003ae7b  mov     r13d, [rsp+370h+var_340]
0x18003ae80  cmp     [rsp+370h+var_31C], 0
0x18003ae85  jz      short loc_18003AE94
0x18003ae87  lea     rcx, qword_1800D3C30
0x18003ae8e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003ae94  lea     rcx, [rbp+270h+FindFileData]
0x18003ae98  call    PfXpCleanupScenarioFileCursor
0x18003ae9d  test    rsi, rsi
0x18003aea0  jz      short loc_18003AEE9
0x18003aea2  xor     ebx, ebx
0x18003aea4  test    r15d, r15d
0x18003aea7  jz      short loc_18003AED3
0x18003aea9  mov     eax, ebx
0x18003aeab  shl     rax, 5
0x18003aeaf  mov     r8, [rax+rsi+8]; lpMem
0x18003aeb4  test    r8, r8
0x18003aeb7  jz      short loc_18003AECC
0x18003aeb9  mov     rcx, cs:PfSvcGlobals
0x18003aec0  xor     edx, edx; dwFlags
0x18003aec2  mov     rcx, [rcx+58h]; hHeap
0x18003aec6  call    cs:__imp_HeapFree
0x18003aecc  inc     ebx
0x18003aece  cmp     ebx, r15d
0x18003aed1  jb      short loc_18003AEA9
0x18003aed3  mov     rcx, cs:PfSvcGlobals
0x18003aeda  mov     r8, rsi; lpMem
0x18003aedd  xor     edx, edx; dwFlags
0x18003aedf  mov     rcx, [rcx+58h]; hHeap
0x18003aee3  call    cs:__imp_HeapFree
0x18003aee9  test    r14, r14
0x18003aeec  jz      short loc_18003AEFF
0x18003aeee  xor     edx, edx; dwSize
0x18003aef0  mov     r8d, 8000h; dwFreeType
0x18003aef6  mov     rcx, r14; lpAddress
0x18003aef9  call    cs:__imp_VirtualFree
0x18003aeff  mov     rdx, [rsp+370h+var_338]
0x18003af04  mov     ecx, r13d
0x18003af07  mov     r9d, dword ptr [rsp+370h+var_318]
0x18003af0c  mov     r8d, dword ptr [rsp+370h+var_2F8]
0x18003af11  shr     rdx, 0Ah
0x18003af15  mov     [rsp+370h+var_350], edi
0x18003af19  call    PfXpLogCleanupPrefetchDir
0x18003af1e  mov     eax, edi
0x18003af20  mov     rcx, [rbp+270h+var_50]
0x18003af27  xor     rcx, rsp; StackCookie
0x18003af2a  call    __security_check_cookie
0x18003af2f  add     rsp, 338h
0x18003af36  pop     r15
0x18003af38  pop     r14
  ... truncated ...
```

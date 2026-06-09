# __delayLoadHelper2

- ea: `0x180068aa0`
- end: `0x180068f6a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000254f`

## callees

- `0x1800689b8`
- `0x180068aa0`
- `0x180068fe6`
- `0x18006f010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180068bcc`
- `KERNEL32!RaiseException` at `0x180068d18`
- `KERNEL32!RaiseException` at `0x180068e94`
- `KERNEL32!RaiseException` at `0x180068bcc`
- `KERNEL32!RaiseException` at `0x180068d18`
- `KERNEL32!RaiseException` at `0x180068e94`
- `KERNEL32!FreeLibrary` at `0x180068d7c`
- `KERNEL32!FreeLibrary` at `0x180068d7c`
- `KERNEL32!GetProcessHeap` at `0x180068d3f`
- `KERNEL32!GetProcessHeap` at `0x180068d3f`
- `KERNEL32!GetProcAddress` at `0x180068df9`
- `KERNEL32!GetProcAddress` at `0x180068df9`
- `KERNEL32!HeapAlloc` at `0x180068d51`
- `KERNEL32!HeapAlloc` at `0x180068d51`
- `KERNEL32!GetLastError` at `0x180068c93`
- `KERNEL32!GetLastError` at `0x180068e0b`
- `KERNEL32!GetLastError` at `0x180068c93`
- `KERNEL32!GetLastError` at `0x180068e0b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068b11`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068bb8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068d03`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068e7f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068edc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068f52`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068b11`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068bb8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068d03`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068e7f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068edc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180068f52`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068ae7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068b97`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068cde`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068e5a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068ead`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068f2d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068ae7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068b97`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068cde`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068e5a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068ead`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180068f2d`
- `KERNEL32!LoadLibraryExA` at `0x180068c81`
- `KERNEL32!LoadLibraryExA` at `0x180068c81`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile signed __int64 *v4; // r15
  DWORD dwTimeStamp; // ecx
  char *v6; // r12
  int v7; // eax
  HMODULE Library; // rbx
  __int64 v10; // rcx
  PfnDliHook v11; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v13; // r15
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v15; // rax
  __int64 v16; // rcx
  struct DelayLoadInfo v17; // [rsp+20h] [rbp-50h] BYREF
  DWORD v18; // [rsp+B0h] [rbp+40h]
  __int64 flOldProtect; // [rsp+B8h] [rbp+48h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+50h] BYREF

  *(&v17.cb + 1) = 0;
  memset_0(&v17, 0, 0x44u);
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  v4 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v6 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v17.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  v7 = a1->grAttrs & 1;
  v18 = dwTimeStamp;
  v17.cb = 72;
  v17.pidd = a1;
  v17.ppfn = a2;
  v17.dlp.fImportByName = 0;
  memset(&v17.dlp.szProcName, 0, 28);
  if ( !(_BYTE)v7 )
  {
    Arguments = (ULONG_PTR)&v17;
    LODWORD(flOldProtect) = 0;
    AcquireSRWLockExclusive(&DloadSrwLock);
    if ( !--DloadSectionLockCount )
      DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
    ReleaseSRWLockExclusive(&DloadSrwLock);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v4;
  v10 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3) + a1->rvaINT;
  flOldProtect = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v17.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + v10) >= 0LL;
  if ( v17.dlp.fImportByName )
    v17.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v10);
  else
    v17.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + v10);
  v11 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v17), v11 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v11 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(1, &v17)) == 0 )
      {
        Library = LoadLibraryExA(v17.szDll, 0, 0);
        if ( !Library )
        {
          v17.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v17)) == 0 )
          {
            Arguments = (ULONG_PTR)&v17;
            LODWORD(flOldProtect) = 0;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v17.pfnCur;
          }
        }
      }
      v13 = _InterlockedCompareExchange64(v4, (signed __int64)Library, 0);
      if ( v13 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v13 )
          Library = (HMODULE)v13;
      }
      else if ( Library != (HMODULE)-1LL )
      {
        if ( a1->rvaUnloadIAT )
        {
          ProcessHeap = GetProcessHeap();
          v15 = (struct UnloadInfo *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          if ( v15 )
          {
            v15->pidd = a1;
            v15->puiNext = _puiHead;
            _puiHead = v15;
          }
        }
      }
      v11 = _pfnDliNotifyHook2;
    }
    v17.hmodCur = Library;
    if ( v11 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(2, &v17);
      v11 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v16 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v16) != 17744)
        || *(_DWORD *)((char *)Library + v16 + 8) != v18
        || Library != *(HMODULE *)((char *)Library + v16 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v6[flOldProtect]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v17.dlp.szProcName);
        if ( !ProcAddress )
        {
          v17.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v17)) == 0 )
          {
            Arguments = (ULONG_PTR)&v17;
            LODWORD(flOldProtect) = 0;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( ++DloadSectionLockCount == 1 )
              DloadProtectSection(4u, &DloadSectionOldProtection);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            ProcAddress = v17.pfnCur;
          }
        }
        v11 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v11 )
  {
    v17.dwLastError = 0;
    v17.hmodCur = Library;
    v17.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(5, &v17);
  }
  LODWORD(flOldProtect) = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  return ProcAddress;
}

```

## disassembly

```asm
0x180068aa0  push    rbp
0x180068aa2  push    rbx
0x180068aa3  push    rsi
0x180068aa4  push    rdi
0x180068aa5  push    r12
0x180068aa7  push    r13
0x180068aa9  push    r15
0x180068aab  mov     rbp, rsp
0x180068aae  sub     rsp, 70h
0x180068ab2  xor     eax, eax
0x180068ab4  mov     r13, rdx
0x180068ab7  mov     rsi, rcx
0x180068aba  mov     [rbp+var_4C], eax
0x180068abd  xor     edx, edx; Val
0x180068abf  lea     rcx, [rbp+var_50]; void *
0x180068ac3  lea     r8d, [rax+44h]; Size
0x180068ac7  call    memset_0
0x180068acc  test    cs:dword_180070A70, 1000h
0x180068ad6  lea     rbx, DloadSrwLock
0x180068add  mov     edi, 1
0x180068ae2  jz      short loc_180068B17
0x180068ae4  mov     rcx, rbx; SRWLock
0x180068ae7  call    cs:__imp_AcquireSRWLockExclusive
0x180068aed  mov     eax, cs:DloadSectionLockCount
0x180068af3  add     eax, edi
0x180068af5  mov     cs:DloadSectionLockCount, eax
0x180068afb  cmp     eax, edi
0x180068afd  jnz     short loc_180068B0E
0x180068aff  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180068b06  lea     ecx, [rdi+3]; flNewProtect
0x180068b09  call    DloadProtectSection
0x180068b0e  mov     rcx, rbx; SRWLock
0x180068b11  call    cs:__imp_ReleaseSRWLockExclusive
0x180068b17  mov     eax, [rsi+4]
0x180068b1a  lea     rdx, __ImageBase
0x180068b21  mov     r15d, [rsi+8]
0x180068b25  add     rax, rdx
0x180068b28  mov     r12d, [rsi+14h]
0x180068b2c  add     r15, rdx
0x180068b2f  mov     ecx, [rsi+1Ch]
0x180068b32  add     r12, rdx
0x180068b35  mov     [rbp+lpLibFileName], rax
0x180068b39  mov     eax, [rsi]
0x180068b3b  and     eax, edi
0x180068b3d  mov     [rbp+arg_0], ecx
0x180068b40  mov     [rbp+var_50], 48h ; 'H'
0x180068b47  mov     [rbp+var_48], rsi
0x180068b4b  mov     [rbp+var_40], r13
0x180068b4f  mov     [rbp+var_30], 0
0x180068b56  mov     [rbp+lpProcName], 0
0x180068b5e  mov     [rbp+var_20], 0
0x180068b66  mov     [rbp+var_18], 0
0x180068b6e  mov     [rbp+var_10], 0
0x180068b75  test    al, al
0x180068b77  jnz     short loc_180068BD9
0x180068b79  test    cs:dword_180070A70, 1000h
0x180068b83  lea     rax, [rbp+var_50]
0x180068b87  mov     [rbp+Arguments], rax
0x180068b8b  mov     dword ptr [rbp+flOldProtect], 0
0x180068b92  jz      short loc_180068BBE
0x180068b94  mov     rcx, rbx; SRWLock
0x180068b97  call    cs:__imp_AcquireSRWLockExclusive
0x180068b9d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180068ba4  jnz     short loc_180068BB5
0x180068ba6  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180068bac  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180068bb0  call    DloadProtectSection
0x180068bb5  mov     rcx, rbx; SRWLock
0x180068bb8  call    cs:__imp_ReleaseSRWLockExclusive
0x180068bbe  lea     r9, [rbp+Arguments]; lpArguments
0x180068bc2  mov     r8d, edi; nNumberOfArguments
0x180068bc5  xor     edx, edx; dwExceptionFlags
0x180068bc7  mov     ecx, 0C06D0057h; dwExceptionCode
0x180068bcc  call    cs:__imp_RaiseException
0x180068bd2  xor     eax, eax
0x180068bd4  jmp     loc_180068F5B
0x180068bd9  mov     eax, [rsi+0Ch]
0x180068bdc  mov     rcx, r13
0x180068bdf  mov     rbx, [r15]
0x180068be2  sub     rcx, rax
0x180068be5  sub     rcx, rdx
0x180068be8  sar     rcx, 3
0x180068bec  mov     eax, ecx
0x180068bee  mov     ecx, [rsi+10h]
0x180068bf1  shl     rax, 3
0x180068bf5  add     rcx, rax
0x180068bf8  mov     [rbp+flOldProtect], rax
0x180068bfc  xor     eax, eax
0x180068bfe  cmp     [rcx+rdx], rax
0x180068c02  setnl   al
0x180068c05  mov     [rbp+var_30], eax
0x180068c08  test    eax, eax
0x180068c0a  jz      short loc_180068C1F
0x180068c0c  mov     eax, [rcx+rdx]
0x180068c0f  lea     rdx, word_180000002
0x180068c16  add     rax, rdx
0x180068c19  mov     [rbp+lpProcName], rax
0x180068c1d  jmp     short loc_180068C26
0x180068c1f  movzx   eax, word ptr [rcx+rdx]
0x180068c23  mov     dword ptr [rbp+lpProcName], eax
0x180068c26  mov     rax, cs:__pfnDliNotifyHook2
0x180068c2d  xor     edi, edi
0x180068c2f  test    rax, rax
0x180068c32  jz      short loc_180068C52
0x180068c34  lea     rdx, [rbp+var_50]
0x180068c38  xor     ecx, ecx
0x180068c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c3f  mov     rdi, rax
0x180068c42  test    rax, rax
0x180068c45  mov     rax, cs:__pfnDliNotifyHook2
0x180068c4c  jnz     loc_180068EF1
0x180068c52  test    rbx, rbx
0x180068c55  jnz     loc_180068D90
0x180068c5b  test    rax, rax
0x180068c5e  jz      short loc_180068C78
0x180068c60  lea     rdx, [rbp+var_50]
0x180068c64  lea     ecx, [rbx+1]
0x180068c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c6c  mov     rbx, rax
0x180068c6f  test    rax, rax
0x180068c72  jnz     loc_180068D27
0x180068c78  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180068c7c  xor     r8d, r8d; dwFlags
0x180068c7f  xor     edx, edx; hFile
0x180068c81  call    cs:__imp_LoadLibraryExA
0x180068c87  mov     rbx, rax
0x180068c8a  test    rax, rax
0x180068c8d  jnz     loc_180068D27
0x180068c93  call    cs:__imp_GetLastError
0x180068c99  mov     [rbp+var_10], eax
0x180068c9c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180068ca3  test    rax, rax
0x180068ca6  jz      short loc_180068CBC
0x180068ca8  lea     rdx, [rbp+var_50]
0x180068cac  lea     ecx, [rbx+3]
0x180068caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068cb4  mov     rbx, rax
0x180068cb7  test    rax, rax
0x180068cba  jnz     short loc_180068D27
0x180068cbc  test    cs:dword_180070A70, 1000h
0x180068cc6  lea     rax, [rbp+var_50]
0x180068cca  mov     [rbp+Arguments], rax
0x180068cce  mov     dword ptr [rbp+flOldProtect], 0
0x180068cd5  jz      short loc_180068D09
0x180068cd7  lea     rcx, DloadSrwLock; SRWLock
0x180068cde  call    cs:__imp_AcquireSRWLockExclusive
0x180068ce4  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180068ceb  jnz     short loc_180068CFC
0x180068ced  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180068cf3  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180068cf7  call    DloadProtectSection
0x180068cfc  lea     rcx, DloadSrwLock; SRWLock
0x180068d03  call    cs:__imp_ReleaseSRWLockExclusive
0x180068d09  xor     edx, edx; dwExceptionFlags
0x180068d0b  lea     r9, [rbp+Arguments]; lpArguments
0x180068d0f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180068d14  lea     r8d, [rdx+1]; nNumberOfArguments
0x180068d18  call    cs:__imp_RaiseException
0x180068d1e  mov     rax, [rbp+var_18]
0x180068d22  jmp     loc_180068F5B
0x180068d27  xor     eax, eax
0x180068d29  lock cmpxchg [r15], rbx
0x180068d2e  mov     r15, rax
0x180068d31  jnz     short loc_180068D73
0x180068d33  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180068d37  jz      short loc_180068D89
0x180068d39  cmp     dword ptr [rsi+18h], 0
0x180068d3d  jz      short loc_180068D89
0x180068d3f  call    cs:__imp_GetProcessHeap
0x180068d45  mov     edx, 8; dwFlags
0x180068d4a  mov     rcx, rax; hHeap
0x180068d4d  lea     r8d, [rdx+8]; dwBytes
0x180068d51  call    cs:__imp_HeapAlloc
0x180068d57  test    rax, rax
0x180068d5a  jz      short loc_180068D89
0x180068d5c  mov     [rax+8], rsi
0x180068d60  mov     rcx, cs:__puiHead
0x180068d67  mov     [rax], rcx
0x180068d6a  mov     cs:__puiHead, rax
0x180068d71  jmp     short loc_180068D89
0x180068d73  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180068d77  jz      short loc_180068D82
0x180068d79  mov     rcx, rbx; hLibModule
0x180068d7c  call    cs:__imp_FreeLibrary
0x180068d82  cmp     rbx, r15
0x180068d85  cmovnz  rbx, r15
0x180068d89  mov     rax, cs:__pfnDliNotifyHook2
0x180068d90  mov     [rbp+var_20], rbx
0x180068d94  test    rax, rax
0x180068d97  jz      short loc_180068DB1
0x180068d99  lea     rdx, [rbp+var_50]
0x180068d9d  mov     ecx, 2
0x180068da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068da7  mov     rdi, rax
0x180068daa  mov     rax, cs:__pfnDliNotifyHook2
0x180068db1  test    rdi, rdi
0x180068db4  jnz     loc_180068EED
0x180068dba  cmp     [rsi+14h], edi
0x180068dbd  jz      short loc_180068DF2
0x180068dbf  cmp     [rsi+1Ch], edi
0x180068dc2  jz      short loc_180068DF2
0x180068dc4  movsxd  rcx, dword ptr [rbx+3Ch]
0x180068dc8  cmp     dword ptr [rcx+rbx], 4550h
0x180068dcf  jnz     short loc_180068DF2
0x180068dd1  mov     edx, [rbp+arg_0]
0x180068dd4  cmp     [rcx+rbx+8], edx
0x180068dd8  jnz     short loc_180068DF2
0x180068dda  cmp     rbx, [rcx+rbx+30h]
0x180068ddf  jnz     short loc_180068DF2
0x180068de1  mov     rdi, [rbp+flOldProtect]
0x180068de5  mov     rdi, [rdi+r12]
0x180068de9  test    rdi, rdi
0x180068dec  jnz     loc_180068EED
0x180068df2  mov     rdx, [rbp+lpProcName]; lpProcName
0x180068df6  mov     rcx, rbx; hModule
0x180068df9  call    cs:__imp_GetProcAddress
0x180068dff  mov     rdi, rax
0x180068e02  test    rax, rax
0x180068e05  jnz     loc_180068EE6
0x180068e0b  call    cs:__imp_GetLastError
0x180068e11  mov     [rbp+var_10], eax
0x180068e14  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180068e1b  test    rax, rax
0x180068e1e  jz      short loc_180068E38
0x180068e20  lea     rdx, [rbp+var_50]
0x180068e24  lea     ecx, [rdi+4]
0x180068e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068e2c  mov     rdi, rax
0x180068e2f  test    rax, rax
0x180068e32  jnz     loc_180068EE6
0x180068e38  test    cs:dword_180070A70, 1000h
0x180068e42  lea     rax, [rbp+var_50]
0x180068e46  mov     [rbp+Arguments], rax
0x180068e4a  mov     dword ptr [rbp+flOldProtect], 0
0x180068e51  jz      short loc_180068E85
0x180068e53  lea     rcx, DloadSrwLock; SRWLock
0x180068e5a  call    cs:__imp_AcquireSRWLockExclusive
0x180068e60  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180068e67  jnz     short loc_180068E78
0x180068e69  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180068e6f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180068e73  call    DloadProtectSection
0x180068e78  lea     rcx, DloadSrwLock; SRWLock
0x180068e7f  call    cs:__imp_ReleaseSRWLockExclusive
0x180068e85  xor     edx, edx; dwExceptionFlags
0x180068e87  lea     r9, [rbp+Arguments]; lpArguments
0x180068e8b  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180068e90  lea     r8d, [rdx+1]; nNumberOfArguments
0x180068e94  call    cs:__imp_RaiseException
0x180068e9a  test    cs:dword_180070A70, 1000h
0x180068ea4  jz      short loc_180068EE2
0x180068ea6  lea     rcx, DloadSrwLock; SRWLock
0x180068ead  call    cs:__imp_AcquireSRWLockExclusive
0x180068eb3  mov     eax, cs:DloadSectionLockCount
0x180068eb9  inc     eax
0x180068ebb  mov     cs:DloadSectionLockCount, eax
0x180068ec1  cmp     eax, 1
0x180068ec4  jnz     short loc_180068ED5
0x180068ec6  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180068ecd  lea     ecx, [rax+3]; flNewProtect
0x180068ed0  call    DloadProtectSection
0x180068ed5  lea     rcx, DloadSrwLock; SRWLock
0x180068edc  call    cs:__imp_ReleaseSRWLockExclusive
0x180068ee2  mov     rdi, [rbp+var_18]
0x180068ee6  mov     rax, cs:__pfnDliNotifyHook2
0x180068eed  mov     [r13+0], rdi
0x180068ef1  test    rax, rax
0x180068ef4  jz      short loc_180068F13
0x180068ef6  lea     rdx, [rbp+var_50]
0x180068efa  mov     [rbp+var_10], 0
0x180068f01  mov     ecx, 5
0x180068f06  mov     [rbp+var_20], rbx
0x180068f0a  mov     [rbp+var_18], rdi
0x180068f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f13  test    cs:dword_180070A70, 1000h
0x180068f1d  mov     dword ptr [rbp+flOldProtect], 0
0x180068f24  jz      short loc_180068F58
0x180068f26  lea     rcx, DloadSrwLock; SRWLock
0x180068f2d  call    cs:__imp_AcquireSRWLockExclusive
0x180068f33  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180068f3a  jnz     short loc_180068F4B
0x180068f3c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180068f42  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180068f46  call    DloadProtectSection
0x180068f4b  lea     rcx, DloadSrwLock; SRWLock
0x180068f52  call    cs:__imp_ReleaseSRWLockExclusive
0x180068f58  mov     rax, rdi
0x180068f5b  add     rsp, 70h
0x180068f5f  pop     r15
0x180068f61  pop     r13
0x180068f63  pop     r12
0x180068f65  pop     rdi
0x180068f66  pop     rsi
0x180068f67  pop     rbx
0x180068f68  pop     rbp
0x180068f69  retn
```

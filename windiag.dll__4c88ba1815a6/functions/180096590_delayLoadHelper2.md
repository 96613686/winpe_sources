# __delayLoadHelper2

- ea: `0x180096590`
- end: `0x180096a5a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800057a0`
- `0x18000582b`
- `0x1800058ec`

## callees

- `0x1800054e4`
- `0x1800964a8`
- `0x180096590`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800968e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800968e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009686c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009686c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180096771`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180096771`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800965d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096687`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800967ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009694a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009699d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096a1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800965d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096687`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800967ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009694a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009699d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096a1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096601`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800966a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800967f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009696f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800969cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096a42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096601`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800966a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800967f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009696f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800969cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096a42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180096841`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180096841`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009682f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009682f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800966bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180096808`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180096984`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800966bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180096808`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180096984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968fb`

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
  v4 = (volatile signed __int64 *)((char *)&_ImageBase.unused + a1->rvaHmod);
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
  v17.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase.unused + v10) >= 0LL;
  if ( v17.dlp.fImportByName )
    v17.dlp.szProcName = (char *)&_ImageBase.unused + *(unsigned int *)((char *)&_ImageBase.unused + v10) + 2;
  else
    v17.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase.unused + v10);
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
0x180096590  push    rbp
0x180096592  push    rbx
0x180096593  push    rsi
0x180096594  push    rdi
0x180096595  push    r12
0x180096597  push    r13
0x180096599  push    r15
0x18009659b  mov     rbp, rsp
0x18009659e  sub     rsp, 70h
0x1800965a2  xor     eax, eax
0x1800965a4  mov     r13, rdx
0x1800965a7  mov     rsi, rcx
0x1800965aa  mov     [rbp+var_4C], eax
0x1800965ad  xor     edx, edx; Val
0x1800965af  lea     rcx, [rbp+var_50]; void *
0x1800965b3  lea     r8d, [rax+44h]; Size
0x1800965b7  call    memset_0
0x1800965bc  test    cs:dword_18009F0A0, 1000h
0x1800965c6  lea     rbx, DloadSrwLock
0x1800965cd  mov     edi, 1
0x1800965d2  jz      short loc_180096607
0x1800965d4  mov     rcx, rbx; SRWLock
0x1800965d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800965dd  mov     eax, cs:DloadSectionLockCount
0x1800965e3  add     eax, edi
0x1800965e5  mov     cs:DloadSectionLockCount, eax
0x1800965eb  cmp     eax, edi
0x1800965ed  jnz     short loc_1800965FE
0x1800965ef  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800965f6  lea     ecx, [rdi+3]; flNewProtect
0x1800965f9  call    DloadProtectSection
0x1800965fe  mov     rcx, rbx; SRWLock
0x180096601  call    cs:__imp_ReleaseSRWLockExclusive
0x180096607  mov     eax, [rsi+4]
0x18009660a  lea     rdx, __ImageBase
0x180096611  mov     r15d, [rsi+8]
0x180096615  add     rax, rdx
0x180096618  mov     r12d, [rsi+14h]
0x18009661c  add     r15, rdx
0x18009661f  mov     ecx, [rsi+1Ch]
0x180096622  add     r12, rdx
0x180096625  mov     [rbp+lpLibFileName], rax
0x180096629  mov     eax, [rsi]
0x18009662b  and     eax, edi
0x18009662d  mov     [rbp+arg_0], ecx
0x180096630  mov     [rbp+var_50], 48h ; 'H'
0x180096637  mov     [rbp+var_48], rsi
0x18009663b  mov     [rbp+var_40], r13
0x18009663f  mov     [rbp+var_30], 0
0x180096646  mov     [rbp+lpProcName], 0
0x18009664e  mov     [rbp+var_20], 0
0x180096656  mov     [rbp+var_18], 0
0x18009665e  mov     [rbp+var_10], 0
0x180096665  test    al, al
0x180096667  jnz     short loc_1800966C9
0x180096669  test    cs:dword_18009F0A0, 1000h
0x180096673  lea     rax, [rbp+var_50]
0x180096677  mov     [rbp+Arguments], rax
0x18009667b  mov     dword ptr [rbp+flOldProtect], 0
0x180096682  jz      short loc_1800966AE
0x180096684  mov     rcx, rbx; SRWLock
0x180096687  call    cs:__imp_AcquireSRWLockExclusive
0x18009668d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180096694  jnz     short loc_1800966A5
0x180096696  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18009669c  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800966a0  call    DloadProtectSection
0x1800966a5  mov     rcx, rbx; SRWLock
0x1800966a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800966ae  lea     r9, [rbp+Arguments]; lpArguments
0x1800966b2  mov     r8d, edi; nNumberOfArguments
0x1800966b5  xor     edx, edx; dwExceptionFlags
0x1800966b7  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800966bc  call    cs:__imp_RaiseException
0x1800966c2  xor     eax, eax
0x1800966c4  jmp     loc_180096A4B
0x1800966c9  mov     eax, [rsi+0Ch]
0x1800966cc  mov     rcx, r13
0x1800966cf  mov     rbx, [r15]
0x1800966d2  sub     rcx, rax
0x1800966d5  sub     rcx, rdx
0x1800966d8  sar     rcx, 3
0x1800966dc  mov     eax, ecx
0x1800966de  mov     ecx, [rsi+10h]
0x1800966e1  shl     rax, 3
0x1800966e5  add     rcx, rax
0x1800966e8  mov     [rbp+flOldProtect], rax
0x1800966ec  xor     eax, eax
0x1800966ee  cmp     [rcx+rdx], rax
0x1800966f2  setnl   al
0x1800966f5  mov     [rbp+var_30], eax
0x1800966f8  test    eax, eax
0x1800966fa  jz      short loc_18009670F
0x1800966fc  mov     eax, [rcx+rdx]
0x1800966ff  lea     rdx, __ImageBase.unused+2
0x180096706  add     rax, rdx
0x180096709  mov     [rbp+lpProcName], rax
0x18009670d  jmp     short loc_180096716
0x18009670f  movzx   eax, word ptr [rcx+rdx]
0x180096713  mov     dword ptr [rbp+lpProcName], eax
0x180096716  mov     rax, cs:__pfnDliNotifyHook2
0x18009671d  xor     edi, edi
0x18009671f  test    rax, rax
0x180096722  jz      short loc_180096742
0x180096724  lea     rdx, [rbp+var_50]
0x180096728  xor     ecx, ecx
0x18009672a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009672f  mov     rdi, rax
0x180096732  test    rax, rax
0x180096735  mov     rax, cs:__pfnDliNotifyHook2
0x18009673c  jnz     loc_1800969E1
0x180096742  test    rbx, rbx
0x180096745  jnz     loc_180096880
0x18009674b  test    rax, rax
0x18009674e  jz      short loc_180096768
0x180096750  lea     rdx, [rbp+var_50]
0x180096754  lea     ecx, [rbx+1]
0x180096757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009675c  mov     rbx, rax
0x18009675f  test    rax, rax
0x180096762  jnz     loc_180096817
0x180096768  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18009676c  xor     r8d, r8d; dwFlags
0x18009676f  xor     edx, edx; hFile
0x180096771  call    cs:__imp_LoadLibraryExA
0x180096777  mov     rbx, rax
0x18009677a  test    rax, rax
0x18009677d  jnz     loc_180096817
0x180096783  call    cs:__imp_GetLastError
0x180096789  mov     [rbp+var_10], eax
0x18009678c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180096793  test    rax, rax
0x180096796  jz      short loc_1800967AC
0x180096798  lea     rdx, [rbp+var_50]
0x18009679c  lea     ecx, [rbx+3]
0x18009679f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800967a4  mov     rbx, rax
0x1800967a7  test    rax, rax
0x1800967aa  jnz     short loc_180096817
0x1800967ac  test    cs:dword_18009F0A0, 1000h
0x1800967b6  lea     rax, [rbp+var_50]
0x1800967ba  mov     [rbp+Arguments], rax
0x1800967be  mov     dword ptr [rbp+flOldProtect], 0
0x1800967c5  jz      short loc_1800967F9
0x1800967c7  lea     rcx, DloadSrwLock; SRWLock
0x1800967ce  call    cs:__imp_AcquireSRWLockExclusive
0x1800967d4  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800967db  jnz     short loc_1800967EC
0x1800967dd  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800967e3  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800967e7  call    DloadProtectSection
0x1800967ec  lea     rcx, DloadSrwLock; SRWLock
0x1800967f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800967f9  xor     edx, edx; dwExceptionFlags
0x1800967fb  lea     r9, [rbp+Arguments]; lpArguments
0x1800967ff  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180096804  lea     r8d, [rdx+1]; nNumberOfArguments
0x180096808  call    cs:__imp_RaiseException
0x18009680e  mov     rax, [rbp+var_18]
0x180096812  jmp     loc_180096A4B
0x180096817  xor     eax, eax
0x180096819  lock cmpxchg [r15], rbx
0x18009681e  mov     r15, rax
0x180096821  jnz     short loc_180096863
0x180096823  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180096827  jz      short loc_180096879
0x180096829  cmp     dword ptr [rsi+18h], 0
0x18009682d  jz      short loc_180096879
0x18009682f  call    cs:__imp_GetProcessHeap
0x180096835  mov     edx, 8; dwFlags
0x18009683a  mov     rcx, rax; hHeap
0x18009683d  lea     r8d, [rdx+8]; dwBytes
0x180096841  call    cs:__imp_HeapAlloc
0x180096847  test    rax, rax
0x18009684a  jz      short loc_180096879
0x18009684c  mov     [rax+8], rsi
0x180096850  mov     rcx, cs:__puiHead
0x180096857  mov     [rax], rcx
0x18009685a  mov     cs:__puiHead, rax
0x180096861  jmp     short loc_180096879
0x180096863  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180096867  jz      short loc_180096872
0x180096869  mov     rcx, rbx; hLibModule
0x18009686c  call    cs:__imp_FreeLibrary
0x180096872  cmp     rbx, r15
0x180096875  cmovnz  rbx, r15
0x180096879  mov     rax, cs:__pfnDliNotifyHook2
0x180096880  mov     [rbp+var_20], rbx
0x180096884  test    rax, rax
0x180096887  jz      short loc_1800968A1
0x180096889  lea     rdx, [rbp+var_50]
0x18009688d  mov     ecx, 2
0x180096892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096897  mov     rdi, rax
0x18009689a  mov     rax, cs:__pfnDliNotifyHook2
0x1800968a1  test    rdi, rdi
0x1800968a4  jnz     loc_1800969DD
0x1800968aa  cmp     [rsi+14h], edi
0x1800968ad  jz      short loc_1800968E2
0x1800968af  cmp     [rsi+1Ch], edi
0x1800968b2  jz      short loc_1800968E2
0x1800968b4  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800968b8  cmp     dword ptr [rcx+rbx], 4550h
0x1800968bf  jnz     short loc_1800968E2
0x1800968c1  mov     edx, [rbp+arg_0]
0x1800968c4  cmp     [rcx+rbx+8], edx
0x1800968c8  jnz     short loc_1800968E2
0x1800968ca  cmp     rbx, [rcx+rbx+30h]
0x1800968cf  jnz     short loc_1800968E2
0x1800968d1  mov     rdi, [rbp+flOldProtect]
0x1800968d5  mov     rdi, [rdi+r12]
0x1800968d9  test    rdi, rdi
0x1800968dc  jnz     loc_1800969DD
0x1800968e2  mov     rdx, [rbp+lpProcName]; lpProcName
0x1800968e6  mov     rcx, rbx; hModule
0x1800968e9  call    cs:__imp_GetProcAddress
0x1800968ef  mov     rdi, rax
0x1800968f2  test    rax, rax
0x1800968f5  jnz     loc_1800969D6
0x1800968fb  call    cs:__imp_GetLastError
0x180096901  mov     [rbp+var_10], eax
0x180096904  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18009690b  test    rax, rax
0x18009690e  jz      short loc_180096928
0x180096910  lea     rdx, [rbp+var_50]
0x180096914  lea     ecx, [rdi+4]
0x180096917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009691c  mov     rdi, rax
0x18009691f  test    rax, rax
0x180096922  jnz     loc_1800969D6
0x180096928  test    cs:dword_18009F0A0, 1000h
0x180096932  lea     rax, [rbp+var_50]
0x180096936  mov     [rbp+Arguments], rax
0x18009693a  mov     dword ptr [rbp+flOldProtect], 0
0x180096941  jz      short loc_180096975
0x180096943  lea     rcx, DloadSrwLock; SRWLock
0x18009694a  call    cs:__imp_AcquireSRWLockExclusive
0x180096950  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180096957  jnz     short loc_180096968
0x180096959  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18009695f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180096963  call    DloadProtectSection
0x180096968  lea     rcx, DloadSrwLock; SRWLock
0x18009696f  call    cs:__imp_ReleaseSRWLockExclusive
0x180096975  xor     edx, edx; dwExceptionFlags
0x180096977  lea     r9, [rbp+Arguments]; lpArguments
0x18009697b  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180096980  lea     r8d, [rdx+1]; nNumberOfArguments
0x180096984  call    cs:__imp_RaiseException
0x18009698a  test    cs:dword_18009F0A0, 1000h
0x180096994  jz      short loc_1800969D2
0x180096996  lea     rcx, DloadSrwLock; SRWLock
0x18009699d  call    cs:__imp_AcquireSRWLockExclusive
0x1800969a3  mov     eax, cs:DloadSectionLockCount
0x1800969a9  inc     eax
0x1800969ab  mov     cs:DloadSectionLockCount, eax
0x1800969b1  cmp     eax, 1
0x1800969b4  jnz     short loc_1800969C5
0x1800969b6  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800969bd  lea     ecx, [rax+3]; flNewProtect
0x1800969c0  call    DloadProtectSection
0x1800969c5  lea     rcx, DloadSrwLock; SRWLock
0x1800969cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800969d2  mov     rdi, [rbp+var_18]
0x1800969d6  mov     rax, cs:__pfnDliNotifyHook2
0x1800969dd  mov     [r13+0], rdi
0x1800969e1  test    rax, rax
0x1800969e4  jz      short loc_180096A03
0x1800969e6  lea     rdx, [rbp+var_50]
0x1800969ea  mov     [rbp+var_10], 0
0x1800969f1  mov     ecx, 5
0x1800969f6  mov     [rbp+var_20], rbx
0x1800969fa  mov     [rbp+var_18], rdi
0x1800969fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096a03  test    cs:dword_18009F0A0, 1000h
0x180096a0d  mov     dword ptr [rbp+flOldProtect], 0
0x180096a14  jz      short loc_180096A48
0x180096a16  lea     rcx, DloadSrwLock; SRWLock
0x180096a1d  call    cs:__imp_AcquireSRWLockExclusive
0x180096a23  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180096a2a  jnz     short loc_180096A3B
0x180096a2c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180096a32  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180096a36  call    DloadProtectSection
0x180096a3b  lea     rcx, DloadSrwLock; SRWLock
0x180096a42  call    cs:__imp_ReleaseSRWLockExclusive
0x180096a48  mov     rax, rdi
0x180096a4b  add     rsp, 70h
0x180096a4f  pop     r15
0x180096a51  pop     r13
0x180096a53  pop     r12
0x180096a55  pop     rdi
0x180096a56  pop     rsi
0x180096a57  pop     rbx
0x180096a58  pop     rbp
0x180096a59  retn
```

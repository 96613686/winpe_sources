# __delayLoadHelper2

- ea: `0x140014f70`
- end: `0x14001543a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002956`
- `0x1400029f3`
- `0x140002aa2`

## callees

- `0x1400028b8`
- `0x140014e80`
- `0x140014f70`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140015163`
- `KERNEL32!GetLastError` at `0x1400152db`
- `KERNEL32!GetLastError` at `0x140015163`
- `KERNEL32!GetLastError` at `0x1400152db`
- `KERNEL32!HeapAlloc` at `0x140015221`
- `KERNEL32!HeapAlloc` at `0x140015221`
- `KERNEL32!GetProcAddress` at `0x1400152c9`
- `KERNEL32!GetProcAddress` at `0x1400152c9`
- `KERNEL32!GetProcessHeap` at `0x14001520f`
- `KERNEL32!GetProcessHeap` at `0x14001520f`
- `KERNEL32!RaiseException` at `0x14001509c`
- `KERNEL32!RaiseException` at `0x1400151e8`
- `KERNEL32!RaiseException` at `0x140015364`
- `KERNEL32!RaiseException` at `0x14001509c`
- `KERNEL32!RaiseException` at `0x1400151e8`
- `KERNEL32!RaiseException` at `0x140015364`
- `KERNEL32!FreeLibrary` at `0x14001524c`
- `KERNEL32!FreeLibrary` at `0x14001524c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140014fb7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015067`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400151ae`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001532a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001537d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400153fd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140014fb7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015067`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400151ae`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001532a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001537d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400153fd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140014fe1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140015088`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400151d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001534f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400153ac`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140015422`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140014fe1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140015088`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400151d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001534f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400153ac`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140015422`
- `KERNEL32!LoadLibraryExA` at `0x140015151`
- `KERNEL32!LoadLibraryExA` at `0x140015151`

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
    v17.dlp.szProcName = (char *)&word_140000002 + *(unsigned int *)((char *)&_ImageBase + v10);
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
0x140014f70  push    rbp
0x140014f72  push    rbx
0x140014f73  push    rsi
0x140014f74  push    rdi
0x140014f75  push    r12
0x140014f77  push    r13
0x140014f79  push    r15
0x140014f7b  mov     rbp, rsp
0x140014f7e  sub     rsp, 70h
0x140014f82  xor     eax, eax
0x140014f84  mov     r13, rdx
0x140014f87  mov     rsi, rcx
0x140014f8a  mov     [rbp+var_4C], eax
0x140014f8d  xor     edx, edx; Val
0x140014f8f  lea     rcx, [rbp+var_50]; void *
0x140014f93  lea     r8d, [rax+44h]; Size
0x140014f97  call    memset_0
0x140014f9c  test    cs:dword_140017090, 1000h
0x140014fa6  lea     rbx, DloadSrwLock
0x140014fad  mov     edi, 1
0x140014fb2  jz      short loc_140014FE7
0x140014fb4  mov     rcx, rbx; SRWLock
0x140014fb7  call    cs:__imp_AcquireSRWLockExclusive
0x140014fbd  mov     eax, cs:DloadSectionLockCount
0x140014fc3  add     eax, edi
0x140014fc5  mov     cs:DloadSectionLockCount, eax
0x140014fcb  cmp     eax, edi
0x140014fcd  jnz     short loc_140014FDE
0x140014fcf  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x140014fd6  lea     ecx, [rdi+3]; flNewProtect
0x140014fd9  call    DloadProtectSection
0x140014fde  mov     rcx, rbx; SRWLock
0x140014fe1  call    cs:__imp_ReleaseSRWLockExclusive
0x140014fe7  mov     eax, [rsi+4]
0x140014fea  lea     rdx, __ImageBase
0x140014ff1  mov     r15d, [rsi+8]
0x140014ff5  add     rax, rdx
0x140014ff8  mov     r12d, [rsi+14h]
0x140014ffc  add     r15, rdx
0x140014fff  mov     ecx, [rsi+1Ch]
0x140015002  add     r12, rdx
0x140015005  mov     [rbp+lpLibFileName], rax
0x140015009  mov     eax, [rsi]
0x14001500b  and     eax, edi
0x14001500d  mov     [rbp+arg_0], ecx
0x140015010  mov     [rbp+var_50], 48h ; 'H'
0x140015017  mov     [rbp+var_48], rsi
0x14001501b  mov     [rbp+var_40], r13
0x14001501f  mov     [rbp+var_30], 0
0x140015026  mov     [rbp+lpProcName], 0
0x14001502e  mov     [rbp+var_20], 0
0x140015036  mov     [rbp+var_18], 0
0x14001503e  mov     [rbp+var_10], 0
0x140015045  test    al, al
0x140015047  jnz     short loc_1400150A9
0x140015049  test    cs:dword_140017090, 1000h
0x140015053  lea     rax, [rbp+var_50]
0x140015057  mov     [rbp+Arguments], rax
0x14001505b  mov     dword ptr [rbp+flOldProtect], 0
0x140015062  jz      short loc_14001508E
0x140015064  mov     rcx, rbx; SRWLock
0x140015067  call    cs:__imp_AcquireSRWLockExclusive
0x14001506d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x140015074  jnz     short loc_140015085
0x140015076  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x14001507c  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x140015080  call    DloadProtectSection
0x140015085  mov     rcx, rbx; SRWLock
0x140015088  call    cs:__imp_ReleaseSRWLockExclusive
0x14001508e  lea     r9, [rbp+Arguments]; lpArguments
0x140015092  mov     r8d, edi; nNumberOfArguments
0x140015095  xor     edx, edx; dwExceptionFlags
0x140015097  mov     ecx, 0C06D0057h; dwExceptionCode
0x14001509c  call    cs:__imp_RaiseException
0x1400150a2  xor     eax, eax
0x1400150a4  jmp     loc_14001542B
0x1400150a9  mov     eax, [rsi+0Ch]
0x1400150ac  mov     rcx, r13
0x1400150af  mov     rbx, [r15]
0x1400150b2  sub     rcx, rax
0x1400150b5  sub     rcx, rdx
0x1400150b8  sar     rcx, 3
0x1400150bc  mov     eax, ecx
0x1400150be  mov     ecx, [rsi+10h]
0x1400150c1  shl     rax, 3
0x1400150c5  add     rcx, rax
0x1400150c8  mov     [rbp+flOldProtect], rax
0x1400150cc  xor     eax, eax
0x1400150ce  cmp     [rcx+rdx], rax
0x1400150d2  setnl   al
0x1400150d5  mov     [rbp+var_30], eax
0x1400150d8  test    eax, eax
0x1400150da  jz      short loc_1400150EF
0x1400150dc  mov     eax, [rcx+rdx]
0x1400150df  lea     rdx, word_140000002
0x1400150e6  add     rax, rdx
0x1400150e9  mov     [rbp+lpProcName], rax
0x1400150ed  jmp     short loc_1400150F6
0x1400150ef  movzx   eax, word ptr [rcx+rdx]
0x1400150f3  mov     dword ptr [rbp+lpProcName], eax
0x1400150f6  mov     rax, cs:__pfnDliNotifyHook2
0x1400150fd  xor     edi, edi
0x1400150ff  test    rax, rax
0x140015102  jz      short loc_140015122
0x140015104  lea     rdx, [rbp+var_50]
0x140015108  xor     ecx, ecx
0x14001510a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001510f  mov     rdi, rax
0x140015112  test    rax, rax
0x140015115  mov     rax, cs:__pfnDliNotifyHook2
0x14001511c  jnz     loc_1400153C1
0x140015122  test    rbx, rbx
0x140015125  jnz     loc_140015260
0x14001512b  test    rax, rax
0x14001512e  jz      short loc_140015148
0x140015130  lea     rdx, [rbp+var_50]
0x140015134  lea     ecx, [rbx+1]
0x140015137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001513c  mov     rbx, rax
0x14001513f  test    rax, rax
0x140015142  jnz     loc_1400151F7
0x140015148  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x14001514c  xor     r8d, r8d; dwFlags
0x14001514f  xor     edx, edx; hFile
0x140015151  call    cs:__imp_LoadLibraryExA
0x140015157  mov     rbx, rax
0x14001515a  test    rax, rax
0x14001515d  jnz     loc_1400151F7
0x140015163  call    cs:__imp_GetLastError
0x140015169  mov     [rbp+var_10], eax
0x14001516c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x140015173  test    rax, rax
0x140015176  jz      short loc_14001518C
0x140015178  lea     rdx, [rbp+var_50]
0x14001517c  lea     ecx, [rbx+3]
0x14001517f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015184  mov     rbx, rax
0x140015187  test    rax, rax
0x14001518a  jnz     short loc_1400151F7
0x14001518c  test    cs:dword_140017090, 1000h
0x140015196  lea     rax, [rbp+var_50]
0x14001519a  mov     [rbp+Arguments], rax
0x14001519e  mov     dword ptr [rbp+flOldProtect], 0
0x1400151a5  jz      short loc_1400151D9
0x1400151a7  lea     rcx, DloadSrwLock; SRWLock
0x1400151ae  call    cs:__imp_AcquireSRWLockExclusive
0x1400151b4  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1400151bb  jnz     short loc_1400151CC
0x1400151bd  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1400151c3  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1400151c7  call    DloadProtectSection
0x1400151cc  lea     rcx, DloadSrwLock; SRWLock
0x1400151d3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400151d9  xor     edx, edx; dwExceptionFlags
0x1400151db  lea     r9, [rbp+Arguments]; lpArguments
0x1400151df  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1400151e4  lea     r8d, [rdx+1]; nNumberOfArguments
0x1400151e8  call    cs:__imp_RaiseException
0x1400151ee  mov     rax, [rbp+var_18]
0x1400151f2  jmp     loc_14001542B
0x1400151f7  xor     eax, eax
0x1400151f9  lock cmpxchg [r15], rbx
0x1400151fe  mov     r15, rax
0x140015201  jnz     short loc_140015243
0x140015203  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140015207  jz      short loc_140015259
0x140015209  cmp     dword ptr [rsi+18h], 0
0x14001520d  jz      short loc_140015259
0x14001520f  call    cs:__imp_GetProcessHeap
0x140015215  mov     edx, 8; dwFlags
0x14001521a  mov     rcx, rax; hHeap
0x14001521d  lea     r8d, [rdx+8]; dwBytes
0x140015221  call    cs:__imp_HeapAlloc
0x140015227  test    rax, rax
0x14001522a  jz      short loc_140015259
0x14001522c  mov     [rax+8], rsi
0x140015230  mov     rcx, cs:__puiHead
0x140015237  mov     [rax], rcx
0x14001523a  mov     cs:__puiHead, rax
0x140015241  jmp     short loc_140015259
0x140015243  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140015247  jz      short loc_140015252
0x140015249  mov     rcx, rbx; hLibModule
0x14001524c  call    cs:__imp_FreeLibrary
0x140015252  cmp     rbx, r15
0x140015255  cmovnz  rbx, r15
0x140015259  mov     rax, cs:__pfnDliNotifyHook2
0x140015260  mov     [rbp+var_20], rbx
0x140015264  test    rax, rax
0x140015267  jz      short loc_140015281
0x140015269  lea     rdx, [rbp+var_50]
0x14001526d  mov     ecx, 2
0x140015272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015277  mov     rdi, rax
0x14001527a  mov     rax, cs:__pfnDliNotifyHook2
0x140015281  test    rdi, rdi
0x140015284  jnz     loc_1400153BD
0x14001528a  cmp     [rsi+14h], edi
0x14001528d  jz      short loc_1400152C2
0x14001528f  cmp     [rsi+1Ch], edi
0x140015292  jz      short loc_1400152C2
0x140015294  movsxd  rcx, dword ptr [rbx+3Ch]
0x140015298  cmp     dword ptr [rcx+rbx], 4550h
0x14001529f  jnz     short loc_1400152C2
0x1400152a1  mov     edx, [rbp+arg_0]
0x1400152a4  cmp     [rcx+rbx+8], edx
0x1400152a8  jnz     short loc_1400152C2
0x1400152aa  cmp     rbx, [rcx+rbx+30h]
0x1400152af  jnz     short loc_1400152C2
0x1400152b1  mov     rdi, [rbp+flOldProtect]
0x1400152b5  mov     rdi, [rdi+r12]
0x1400152b9  test    rdi, rdi
0x1400152bc  jnz     loc_1400153BD
0x1400152c2  mov     rdx, [rbp+lpProcName]; lpProcName
0x1400152c6  mov     rcx, rbx; hModule
0x1400152c9  call    cs:__imp_GetProcAddress
0x1400152cf  mov     rdi, rax
0x1400152d2  test    rax, rax
0x1400152d5  jnz     loc_1400153B6
0x1400152db  call    cs:__imp_GetLastError
0x1400152e1  mov     [rbp+var_10], eax
0x1400152e4  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1400152eb  test    rax, rax
0x1400152ee  jz      short loc_140015308
0x1400152f0  lea     rdx, [rbp+var_50]
0x1400152f4  lea     ecx, [rdi+4]
0x1400152f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152fc  mov     rdi, rax
0x1400152ff  test    rax, rax
0x140015302  jnz     loc_1400153B6
0x140015308  test    cs:dword_140017090, 1000h
0x140015312  lea     rax, [rbp+var_50]
0x140015316  mov     [rbp+Arguments], rax
0x14001531a  mov     dword ptr [rbp+flOldProtect], 0
0x140015321  jz      short loc_140015355
0x140015323  lea     rcx, DloadSrwLock; SRWLock
0x14001532a  call    cs:__imp_AcquireSRWLockExclusive
0x140015330  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x140015337  jnz     short loc_140015348
0x140015339  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x14001533f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x140015343  call    DloadProtectSection
0x140015348  lea     rcx, DloadSrwLock; SRWLock
0x14001534f  call    cs:__imp_ReleaseSRWLockExclusive
0x140015355  xor     edx, edx; dwExceptionFlags
0x140015357  lea     r9, [rbp+Arguments]; lpArguments
0x14001535b  mov     ecx, 0C06D007Fh; dwExceptionCode
0x140015360  lea     r8d, [rdx+1]; nNumberOfArguments
0x140015364  call    cs:__imp_RaiseException
0x14001536a  test    cs:dword_140017090, 1000h
0x140015374  jz      short loc_1400153B2
0x140015376  lea     rcx, DloadSrwLock; SRWLock
0x14001537d  call    cs:__imp_AcquireSRWLockExclusive
0x140015383  mov     eax, cs:DloadSectionLockCount
0x140015389  inc     eax
0x14001538b  mov     cs:DloadSectionLockCount, eax
0x140015391  cmp     eax, 1
0x140015394  jnz     short loc_1400153A5
0x140015396  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x14001539d  lea     ecx, [rax+3]; flNewProtect
0x1400153a0  call    DloadProtectSection
0x1400153a5  lea     rcx, DloadSrwLock; SRWLock
0x1400153ac  call    cs:__imp_ReleaseSRWLockExclusive
0x1400153b2  mov     rdi, [rbp+var_18]
0x1400153b6  mov     rax, cs:__pfnDliNotifyHook2
0x1400153bd  mov     [r13+0], rdi
0x1400153c1  test    rax, rax
0x1400153c4  jz      short loc_1400153E3
0x1400153c6  lea     rdx, [rbp+var_50]
0x1400153ca  mov     [rbp+var_10], 0
0x1400153d1  mov     ecx, 5
0x1400153d6  mov     [rbp+var_20], rbx
0x1400153da  mov     [rbp+var_18], rdi
0x1400153de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400153e3  test    cs:dword_140017090, 1000h
0x1400153ed  mov     dword ptr [rbp+flOldProtect], 0
0x1400153f4  jz      short loc_140015428
0x1400153f6  lea     rcx, DloadSrwLock; SRWLock
0x1400153fd  call    cs:__imp_AcquireSRWLockExclusive
0x140015403  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x14001540a  jnz     short loc_14001541B
0x14001540c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x140015412  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x140015416  call    DloadProtectSection
0x14001541b  lea     rcx, DloadSrwLock; SRWLock
0x140015422  call    cs:__imp_ReleaseSRWLockExclusive
0x140015428  mov     rax, rdi
0x14001542b  add     rsp, 70h
0x14001542f  pop     r15
0x140015431  pop     r13
0x140015433  pop     r12
0x140015435  pop     rdi
0x140015436  pop     rsi
0x140015437  pop     rbx
0x140015438  pop     rbp
0x140015439  retn
```

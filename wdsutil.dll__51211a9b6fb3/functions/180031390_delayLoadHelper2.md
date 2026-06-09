# __delayLoadHelper2

- ea: `0x180031390`
- end: `0x1800318df`
- name: `__delayLoadHelper2`
- size: `1359`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000252c`

## callees

- `0x1800312a0`
- `0x180031390`
- `0x1800319ae`
- `0x180034010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18003158f`
- `KERNEL32!LoadLibraryExA` at `0x18003158f`
- `KERNEL32!GetLastError` at `0x1800315a7`
- `KERNEL32!GetLastError` at `0x18003174f`
- `KERNEL32!GetLastError` at `0x1800315a7`
- `KERNEL32!GetLastError` at `0x18003174f`
- `KERNEL32!HeapAlloc` at `0x180031683`
- `KERNEL32!HeapAlloc` at `0x180031683`
- `KERNEL32!GetProcessHeap` at `0x18003166b`
- `KERNEL32!GetProcessHeap` at `0x18003166b`
- `KERNEL32!RaiseException` at `0x1800314d4`
- `KERNEL32!RaiseException` at `0x18003163e`
- `KERNEL32!RaiseException` at `0x1800317ea`
- `KERNEL32!RaiseException` at `0x1800314d4`
- `KERNEL32!RaiseException` at `0x18003163e`
- `KERNEL32!RaiseException` at `0x1800317ea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180031407`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800314ba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180031623`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800317cf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003183e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800318c0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180031407`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800314ba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180031623`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800317cf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003183e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800318c0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800313d7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180031493`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800315f8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800317a4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180031809`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180031895`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800313d7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180031493`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800315f8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800317a4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180031809`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180031895`
- `KERNEL32!GetProcAddress` at `0x180031737`
- `KERNEL32!GetProcAddress` at `0x180031737`
- `KERNEL32!FreeLibrary` at `0x1800316b4`
- `KERNEL32!FreeLibrary` at `0x1800316b4`

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
0x180031390  push    rbp
0x180031392  push    rbx
0x180031393  push    rsi
0x180031394  push    rdi
0x180031395  push    r12
0x180031397  push    r13
0x180031399  push    r15
0x18003139b  mov     rbp, rsp
0x18003139e  sub     rsp, 70h
0x1800313a2  xor     eax, eax
0x1800313a4  mov     r13, rdx
0x1800313a7  mov     rsi, rcx
0x1800313aa  mov     [rbp+var_4C], eax
0x1800313ad  xor     edx, edx; Val
0x1800313af  lea     rcx, [rbp+var_50]; void *
0x1800313b3  lea     r8d, [rax+44h]; Size
0x1800313b7  call    memset_0
0x1800313bc  test    cs:dword_180035A70, 1000h
0x1800313c6  lea     rbx, DloadSrwLock
0x1800313cd  mov     edi, 1
0x1800313d2  jz      short loc_180031413
0x1800313d4  mov     rcx, rbx; SRWLock
0x1800313d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800313de  nop     dword ptr [rax+rax+00h]
0x1800313e3  mov     eax, cs:DloadSectionLockCount
0x1800313e9  add     eax, edi
0x1800313eb  mov     cs:DloadSectionLockCount, eax
0x1800313f1  cmp     eax, edi
0x1800313f3  jnz     short loc_180031404
0x1800313f5  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800313fc  lea     ecx, [rdi+3]; flNewProtect
0x1800313ff  call    DloadProtectSection
0x180031404  mov     rcx, rbx; SRWLock
0x180031407  call    cs:__imp_ReleaseSRWLockExclusive
0x18003140e  nop     dword ptr [rax+rax+00h]
0x180031413  mov     eax, [rsi+4]
0x180031416  lea     rdx, __ImageBase
0x18003141d  mov     r15d, [rsi+8]
0x180031421  add     rax, rdx
0x180031424  mov     r12d, [rsi+14h]
0x180031428  add     r15, rdx
0x18003142b  mov     ecx, [rsi+1Ch]
0x18003142e  add     r12, rdx
0x180031431  mov     [rbp+lpLibFileName], rax
0x180031435  mov     eax, [rsi]
0x180031437  and     eax, edi
0x180031439  mov     [rbp+arg_0], ecx
0x18003143c  mov     [rbp+var_50], 48h ; 'H'
0x180031443  mov     [rbp+var_48], rsi
0x180031447  mov     [rbp+var_40], r13
0x18003144b  mov     [rbp+var_30], 0
0x180031452  mov     [rbp+lpProcName], 0
0x18003145a  mov     [rbp+var_20], 0
0x180031462  mov     [rbp+var_18], 0
0x18003146a  mov     [rbp+var_10], 0
0x180031471  test    al, al
0x180031473  jnz     short loc_1800314E7
0x180031475  test    cs:dword_180035A70, 1000h
0x18003147f  lea     rax, [rbp+var_50]
0x180031483  mov     [rbp+Arguments], rax
0x180031487  mov     dword ptr [rbp+flOldProtect], 0
0x18003148e  jz      short loc_1800314C6
0x180031490  mov     rcx, rbx; SRWLock
0x180031493  call    cs:__imp_AcquireSRWLockExclusive
0x18003149a  nop     dword ptr [rax+rax+00h]
0x18003149f  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800314a6  jnz     short loc_1800314B7
0x1800314a8  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800314ae  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800314b2  call    DloadProtectSection
0x1800314b7  mov     rcx, rbx; SRWLock
0x1800314ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800314c1  nop     dword ptr [rax+rax+00h]
0x1800314c6  lea     r9, [rbp+Arguments]; lpArguments
0x1800314ca  mov     r8d, edi; nNumberOfArguments
0x1800314cd  xor     edx, edx; dwExceptionFlags
0x1800314cf  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800314d4  call    cs:__imp_RaiseException
0x1800314db  nop     dword ptr [rax+rax+00h]
0x1800314e0  xor     eax, eax
0x1800314e2  jmp     loc_1800318CF
0x1800314e7  mov     eax, [rsi+0Ch]
0x1800314ea  mov     rcx, r13
0x1800314ed  mov     rbx, [r15]
0x1800314f0  sub     rcx, rax
0x1800314f3  sub     rcx, rdx
0x1800314f6  sar     rcx, 3
0x1800314fa  mov     eax, ecx
0x1800314fc  mov     ecx, [rsi+10h]
0x1800314ff  shl     rax, 3
0x180031503  add     rcx, rax
0x180031506  mov     [rbp+flOldProtect], rax
0x18003150a  xor     eax, eax
0x18003150c  cmp     [rcx+rdx], rax
0x180031510  setnl   al
0x180031513  mov     [rbp+var_30], eax
0x180031516  test    eax, eax
0x180031518  jz      short loc_18003152D
0x18003151a  mov     eax, [rcx+rdx]
0x18003151d  lea     rdx, word_180000002
0x180031524  add     rax, rdx
0x180031527  mov     [rbp+lpProcName], rax
0x18003152b  jmp     short loc_180031534
0x18003152d  movzx   eax, word ptr [rcx+rdx]
0x180031531  mov     dword ptr [rbp+lpProcName], eax
0x180031534  mov     rax, cs:__pfnDliNotifyHook2
0x18003153b  xor     edi, edi
0x18003153d  test    rax, rax
0x180031540  jz      short loc_180031560
0x180031542  lea     rdx, [rbp+var_50]
0x180031546  xor     ecx, ecx
0x180031548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003154d  mov     rdi, rax
0x180031550  test    rax, rax
0x180031553  mov     rax, cs:__pfnDliNotifyHook2
0x18003155a  jnz     loc_180031859
0x180031560  test    rbx, rbx
0x180031563  jnz     loc_1800316CE
0x180031569  test    rax, rax
0x18003156c  jz      short loc_180031586
0x18003156e  lea     rdx, [rbp+var_50]
0x180031572  lea     ecx, [rbx+1]
0x180031575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003157a  mov     rbx, rax
0x18003157d  test    rax, rax
0x180031580  jnz     loc_180031653
0x180031586  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18003158a  xor     r8d, r8d; dwFlags
0x18003158d  xor     edx, edx; hFile
0x18003158f  call    cs:__imp_LoadLibraryExA
0x180031596  nop     dword ptr [rax+rax+00h]
0x18003159b  mov     rbx, rax
0x18003159e  test    rax, rax
0x1800315a1  jnz     loc_180031653
0x1800315a7  call    cs:__imp_GetLastError
0x1800315ae  nop     dword ptr [rax+rax+00h]
0x1800315b3  mov     [rbp+var_10], eax
0x1800315b6  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800315bd  test    rax, rax
0x1800315c0  jz      short loc_1800315D6
0x1800315c2  lea     rdx, [rbp+var_50]
0x1800315c6  lea     ecx, [rbx+3]
0x1800315c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315ce  mov     rbx, rax
0x1800315d1  test    rax, rax
0x1800315d4  jnz     short loc_180031653
0x1800315d6  test    cs:dword_180035A70, 1000h
0x1800315e0  lea     rax, [rbp+var_50]
0x1800315e4  mov     [rbp+Arguments], rax
0x1800315e8  mov     dword ptr [rbp+flOldProtect], 0
0x1800315ef  jz      short loc_18003162F
0x1800315f1  lea     rcx, DloadSrwLock; SRWLock
0x1800315f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800315ff  nop     dword ptr [rax+rax+00h]
0x180031604  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18003160b  jnz     short loc_18003161C
0x18003160d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180031613  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180031617  call    DloadProtectSection
0x18003161c  lea     rcx, DloadSrwLock; SRWLock
0x180031623  call    cs:__imp_ReleaseSRWLockExclusive
0x18003162a  nop     dword ptr [rax+rax+00h]
0x18003162f  xor     edx, edx; dwExceptionFlags
0x180031631  lea     r9, [rbp+Arguments]; lpArguments
0x180031635  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18003163a  lea     r8d, [rdx+1]; nNumberOfArguments
0x18003163e  call    cs:__imp_RaiseException
0x180031645  nop     dword ptr [rax+rax+00h]
0x18003164a  mov     rax, [rbp+var_18]
0x18003164e  jmp     loc_1800318CF
0x180031653  xor     eax, eax
0x180031655  lock cmpxchg [r15], rbx
0x18003165a  mov     r15, rax
0x18003165d  jnz     short loc_1800316AB
0x18003165f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180031663  jz      short loc_1800316C7
0x180031665  cmp     dword ptr [rsi+18h], 0
0x180031669  jz      short loc_1800316C7
0x18003166b  call    cs:__imp_GetProcessHeap
0x180031672  nop     dword ptr [rax+rax+00h]
0x180031677  mov     edx, 8; dwFlags
0x18003167c  mov     rcx, rax; hHeap
0x18003167f  lea     r8d, [rdx+8]; dwBytes
0x180031683  call    cs:__imp_HeapAlloc
0x18003168a  nop     dword ptr [rax+rax+00h]
0x18003168f  test    rax, rax
0x180031692  jz      short loc_1800316C7
0x180031694  mov     [rax+8], rsi
0x180031698  mov     rcx, cs:__puiHead
0x18003169f  mov     [rax], rcx
0x1800316a2  mov     cs:__puiHead, rax
0x1800316a9  jmp     short loc_1800316C7
0x1800316ab  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800316af  jz      short loc_1800316C0
0x1800316b1  mov     rcx, rbx; hLibModule
0x1800316b4  call    cs:__imp_FreeLibrary
0x1800316bb  nop     dword ptr [rax+rax+00h]
0x1800316c0  cmp     rbx, r15
0x1800316c3  cmovnz  rbx, r15
0x1800316c7  mov     rax, cs:__pfnDliNotifyHook2
0x1800316ce  mov     [rbp+var_20], rbx
0x1800316d2  test    rax, rax
0x1800316d5  jz      short loc_1800316EF
0x1800316d7  lea     rdx, [rbp+var_50]
0x1800316db  mov     ecx, 2
0x1800316e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800316e5  mov     rdi, rax
0x1800316e8  mov     rax, cs:__pfnDliNotifyHook2
0x1800316ef  test    rdi, rdi
0x1800316f2  jnz     loc_180031855
0x1800316f8  cmp     [rsi+14h], edi
0x1800316fb  jz      short loc_180031730
0x1800316fd  cmp     [rsi+1Ch], edi
0x180031700  jz      short loc_180031730
0x180031702  movsxd  rcx, dword ptr [rbx+3Ch]
0x180031706  cmp     dword ptr [rcx+rbx], 4550h
0x18003170d  jnz     short loc_180031730
0x18003170f  mov     edx, [rbp+arg_0]
0x180031712  cmp     [rcx+rbx+8], edx
0x180031716  jnz     short loc_180031730
0x180031718  cmp     rbx, [rcx+rbx+30h]
0x18003171d  jnz     short loc_180031730
0x18003171f  mov     rdi, [rbp+flOldProtect]
0x180031723  mov     rdi, [rdi+r12]
0x180031727  test    rdi, rdi
0x18003172a  jnz     loc_180031855
0x180031730  mov     rdx, [rbp+lpProcName]; lpProcName
0x180031734  mov     rcx, rbx; hModule
0x180031737  call    cs:__imp_GetProcAddress
0x18003173e  nop     dword ptr [rax+rax+00h]
0x180031743  mov     rdi, rax
0x180031746  test    rax, rax
0x180031749  jnz     loc_18003184E
0x18003174f  call    cs:__imp_GetLastError
0x180031756  nop     dword ptr [rax+rax+00h]
0x18003175b  mov     [rbp+var_10], eax
0x18003175e  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180031765  test    rax, rax
0x180031768  jz      short loc_180031782
0x18003176a  lea     rdx, [rbp+var_50]
0x18003176e  lea     ecx, [rdi+4]
0x180031771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031776  mov     rdi, rax
0x180031779  test    rax, rax
0x18003177c  jnz     loc_18003184E
0x180031782  test    cs:dword_180035A70, 1000h
0x18003178c  lea     rax, [rbp+var_50]
0x180031790  mov     [rbp+Arguments], rax
0x180031794  mov     dword ptr [rbp+flOldProtect], 0
0x18003179b  jz      short loc_1800317DB
0x18003179d  lea     rcx, DloadSrwLock; SRWLock
0x1800317a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800317ab  nop     dword ptr [rax+rax+00h]
0x1800317b0  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800317b7  jnz     short loc_1800317C8
0x1800317b9  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800317bf  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800317c3  call    DloadProtectSection
0x1800317c8  lea     rcx, DloadSrwLock; SRWLock
0x1800317cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800317d6  nop     dword ptr [rax+rax+00h]
0x1800317db  xor     edx, edx; dwExceptionFlags
0x1800317dd  lea     r9, [rbp+Arguments]; lpArguments
0x1800317e1  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800317e6  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800317ea  call    cs:__imp_RaiseException
0x1800317f1  nop     dword ptr [rax+rax+00h]
0x1800317f6  test    cs:dword_180035A70, 1000h
0x180031800  jz      short loc_18003184A
0x180031802  lea     rcx, DloadSrwLock; SRWLock
0x180031809  call    cs:__imp_AcquireSRWLockExclusive
0x180031810  nop     dword ptr [rax+rax+00h]
0x180031815  mov     eax, cs:DloadSectionLockCount
0x18003181b  inc     eax
0x18003181d  mov     cs:DloadSectionLockCount, eax
0x180031823  cmp     eax, 1
0x180031826  jnz     short loc_180031837
0x180031828  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18003182f  lea     ecx, [rax+3]; flNewProtect
0x180031832  call    DloadProtectSection
0x180031837  lea     rcx, DloadSrwLock; SRWLock
0x18003183e  call    cs:__imp_ReleaseSRWLockExclusive
0x180031845  nop     dword ptr [rax+rax+00h]
0x18003184a  mov     rdi, [rbp+var_18]
0x18003184e  mov     rax, cs:__pfnDliNotifyHook2
0x180031855  mov     [r13+0], rdi
0x180031859  test    rax, rax
0x18003185c  jz      short loc_18003187B
0x18003185e  lea     rdx, [rbp+var_50]
0x180031862  mov     [rbp+var_10], 0
0x180031869  mov     ecx, 5
0x18003186e  mov     [rbp+var_20], rbx
0x180031872  mov     [rbp+var_18], rdi
0x180031876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003187b  test    cs:dword_180035A70, 1000h
0x180031885  mov     dword ptr [rbp+flOldProtect], 0
0x18003188c  jz      short loc_1800318CC
0x18003188e  lea     rcx, DloadSrwLock; SRWLock
0x180031895  call    cs:__imp_AcquireSRWLockExclusive
0x18003189c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

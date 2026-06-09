# __delayLoadHelper2

- ea: `0x180011470`
- end: `0x1800119be`
- name: `__delayLoadHelper2`
- size: `1358`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f30`
- `0x18000c63c`

## callees

- `0x180011368`
- `0x180011470`
- `0x180013010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800115b5`
- `KERNEL32!RaiseException` at `0x18001170f`
- `KERNEL32!RaiseException` at `0x1800118c1`
- `KERNEL32!RaiseException` at `0x1800115b5`
- `KERNEL32!RaiseException` at `0x18001170f`
- `KERNEL32!RaiseException` at `0x1800118c1`
- `KERNEL32!GetLastError` at `0x18001167b`
- `KERNEL32!GetLastError` at `0x180011829`
- `KERNEL32!GetLastError` at `0x18001167b`
- `KERNEL32!GetLastError` at `0x180011829`
- `KERNEL32!GetProcAddress` at `0x180011811`
- `KERNEL32!GetProcAddress` at `0x180011811`
- `KERNEL32!FreeLibrary` at `0x180011786`
- `KERNEL32!FreeLibrary` at `0x180011786`
- `KERNEL32!GetProcessHeap` at `0x18001173d`
- `KERNEL32!GetProcessHeap` at `0x18001173d`
- `KERNEL32!HeapAlloc` at `0x180011755`
- `KERNEL32!HeapAlloc` at `0x180011755`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800114b4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011574`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800116c9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001187b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800118e0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011969`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800114b4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011574`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800116c9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001187b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800118e0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011969`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800114e4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001159b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800116f4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800118a6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011915`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011994`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800114e4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001159b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800116f4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800118a6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011915`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011994`
- `KERNEL32!LoadLibraryExA` at `0x180011663`
- `KERNEL32!LoadLibraryExA` at `0x180011663`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, char *a2)
{
  const CHAR *v4; // rax
  char *v5; // r8
  volatile signed __int64 *v6; // r15
  __int64 rvaINT; // rdx
  char *v8; // rcx
  char *v9; // rdx
  HMODULE Library; // rbx
  __int64 v12; // r12
  __int64 (__fastcall *v13)(__int64, _DWORD *); // r8
  FARPROC ProcAddress; // rdi
  __int64 v15; // rax
  signed __int64 v16; // r15
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  _DWORD v21[2]; // [rsp+20h] [rbp-50h] BYREF
  const ImgDelayDescr *v22; // [rsp+28h] [rbp-48h]
  char *v23; // [rsp+30h] [rbp-40h]
  LPCSTR lpLibFileName; // [rsp+38h] [rbp-38h]
  BOOL v25; // [rsp+40h] [rbp-30h]
  int v26; // [rsp+44h] [rbp-2Ch]
  LPCSTR lpProcName; // [rsp+48h] [rbp-28h]
  HMODULE v28; // [rsp+50h] [rbp-20h]
  INT_PTR (__stdcall *v29)(); // [rsp+58h] [rbp-18h]
  DWORD LastError; // [rsp+60h] [rbp-10h]
  DWORD flOldProtect; // [rsp+A0h] [rbp+30h] BYREF
  ULONG_PTR Arguments; // [rsp+A8h] [rbp+38h] BYREF

  v26 = 0;
  v21[1] = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  v4 = (char *)&_ImageBase + a1->rvaDLLName;
  v5 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  rvaINT = a1->rvaINT;
  v8 = (char *)&_ImageBase + a1->rvaIAT;
  v25 = 0;
  v9 = (char *)&_ImageBase + rvaINT;
  lpProcName = 0;
  v28 = 0;
  v29 = 0;
  LastError = 0;
  lpLibFileName = v4;
  LODWORD(v4) = a1->grAttrs & 1;
  Arguments = (ULONG_PTR)v5;
  flOldProtect = a1->dwTimeStamp;
  v21[0] = 72;
  v22 = a1;
  v23 = a2;
  if ( !(_BYTE)v4 )
  {
    flOldProtect = 0;
    Arguments = (ULONG_PTR)v21;
    AcquireSRWLockExclusive(&DloadSrwLock);
    if ( !--DloadSectionLockCount )
      DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
    ReleaseSRWLockExclusive(&DloadSrwLock);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v6;
  v12 = (a2 - v8) >> 3;
  v25 = *(_QWORD *)&v9[8 * (unsigned int)v12] >= 0LL;
  if ( v25 )
    lpProcName = (char *)&word_180000002 + *(unsigned int *)&v9[8 * (unsigned int)v12];
  else
    LODWORD(lpProcName) = *(unsigned __int16 *)&v9[8 * (unsigned int)v12];
  v13 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
  ProcAddress = 0;
  if ( !_pfnDefaultDliFailureHook2
    || (v15 = _pfnDefaultDliFailureHook2(0, v21),
        v13 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2,
        (ProcAddress = (FARPROC)v15) == 0) )
  {
    if ( !Library )
    {
      if ( !v13 || (Library = (HMODULE)v13(1, v21)) == 0 )
      {
        Library = LoadLibraryExA(lpLibFileName, 0, 0);
        if ( !Library )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, v21)) == 0 )
          {
            flOldProtect = 0;
            Arguments = (ULONG_PTR)v21;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v29;
          }
        }
      }
      v16 = _InterlockedCompareExchange64(v6, (signed __int64)Library, 0);
      if ( v16 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v16 )
          Library = (HMODULE)v16;
      }
      else if ( Library != (HMODULE)-1LL )
      {
        if ( a1->rvaUnloadIAT )
        {
          ProcessHeap = GetProcessHeap();
          v18 = (struct UnloadInfo *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          if ( v18 )
          {
            v18->pidd = a1;
            v18->puiNext = _puiHead;
            _puiHead = v18;
          }
        }
      }
      v13 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
    }
    v28 = Library;
    if ( v13 )
    {
      v19 = v13(2, v21);
      v13 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
      ProcAddress = (FARPROC)v19;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v20 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v20) != 17744)
        || *(_DWORD *)((char *)Library + v20 + 8) != flOldProtect
        || Library != *(HMODULE *)((char *)Library + v20 + 48)
        || (ProcAddress = *(FARPROC *)(Arguments + 8LL * (unsigned int)v12)) == 0 )
      {
        ProcAddress = GetProcAddress(Library, lpProcName);
        if ( !ProcAddress )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (ProcAddress = (FARPROC)_pfnDefaultDliFailureHook2(4, v21)) == 0 )
          {
            flOldProtect = 0;
            Arguments = (ULONG_PTR)v21;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( ++DloadSectionLockCount == 1 )
              DloadProtectSection(4u, &DloadSectionOldProtection);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            ProcAddress = v29;
          }
        }
        v13 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
      }
    }
    *(_QWORD *)a2 = ProcAddress;
  }
  if ( v13 )
  {
    LastError = 0;
    v28 = Library;
    v29 = ProcAddress;
    v13(5, v21);
  }
  flOldProtect = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  return ProcAddress;
}

```

## disassembly

```asm
0x180011470  mov     [rsp-28h+arg_10], rbx
0x180011475  mov     [rsp-28h+arg_18], rdi
0x18001147a  push    rbp
0x18001147b  push    r12
0x18001147d  push    r13
0x18001147f  push    r14
0x180011481  push    r15
0x180011483  mov     rbp, rsp
0x180011486  sub     rsp, 70h
0x18001148a  xor     eax, eax
0x18001148c  lea     rbx, DloadSrwLock
0x180011493  and     [rbp+var_2C], eax
0x180011496  mov     r13, rdx
0x180011499  mov     [rbp+var_4C], eax
0x18001149c  mov     r14, rcx
0x18001149f  and     [rbp+var_4C], eax
0x1800114a2  test    cs:dword_1800140A0, 1000h
0x1800114ac  lea     edi, [rax+1]
0x1800114af  jz      short loc_1800114F0
0x1800114b1  mov     rcx, rbx; SRWLock
0x1800114b4  call    cs:__imp_AcquireSRWLockExclusive
0x1800114bb  nop     dword ptr [rax+rax+00h]
0x1800114c0  mov     eax, cs:DloadSectionLockCount
0x1800114c6  add     eax, edi
0x1800114c8  mov     cs:DloadSectionLockCount, eax
0x1800114ce  cmp     eax, edi
0x1800114d0  jnz     short loc_1800114E1
0x1800114d2  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800114d9  lea     ecx, [rdi+3]; flNewProtect
0x1800114dc  call    DloadProtectSection
0x1800114e1  mov     rcx, rbx; SRWLock
0x1800114e4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800114eb  nop     dword ptr [rax+rax+00h]
0x1800114f0  mov     eax, [r14+4]
0x1800114f4  lea     r9, __ImageBase
0x1800114fb  mov     r8d, [r14+14h]
0x1800114ff  add     rax, r9
0x180011502  mov     r15d, [r14+8]
0x180011506  add     r8, r9
0x180011509  mov     ecx, [r14+0Ch]
0x18001150d  add     r15, r9
0x180011510  mov     edx, [r14+10h]
0x180011514  add     rcx, r9
0x180011517  and     [rbp+var_30], 0
0x18001151b  add     rdx, r9
0x18001151e  and     [rbp+lpProcName], 0
0x180011523  and     [rbp+var_20], 0
0x180011528  and     [rbp+var_18], 0
0x18001152d  and     [rbp+var_10], 0
0x180011531  mov     [rbp+lpLibFileName], rax
0x180011535  mov     eax, [r14]
0x180011538  and     eax, edi
0x18001153a  mov     [rbp+Arguments], r8
0x18001153e  mov     r8d, [r14+1Ch]
0x180011542  mov     [rbp+flOldProtect], r8d
0x180011546  mov     [rbp+var_50], 48h ; 'H'
0x18001154d  mov     [rbp+var_48], r14
0x180011551  mov     [rbp+var_40], r13
0x180011555  test    al, al
0x180011557  jnz     short loc_1800115C8
0x180011559  and     [rbp+flOldProtect], 0
0x18001155d  lea     rax, [rbp+var_50]
0x180011561  test    cs:dword_1800140A0, 1000h
0x18001156b  mov     [rbp+Arguments], rax
0x18001156f  jz      short loc_1800115A7
0x180011571  mov     rcx, rbx; SRWLock
0x180011574  call    cs:__imp_AcquireSRWLockExclusive
0x18001157b  nop     dword ptr [rax+rax+00h]
0x180011580  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180011587  jnz     short loc_180011598
0x180011589  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18001158f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180011593  call    DloadProtectSection
0x180011598  mov     rcx, rbx; SRWLock
0x18001159b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800115a2  nop     dword ptr [rax+rax+00h]
0x1800115a7  lea     r9, [rbp+Arguments]; lpArguments
0x1800115ab  mov     r8d, edi; nNumberOfArguments
0x1800115ae  xor     edx, edx; dwExceptionFlags
0x1800115b0  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800115b5  call    cs:__imp_RaiseException
0x1800115bc  nop     dword ptr [rax+rax+00h]
0x1800115c1  xor     eax, eax
0x1800115c3  jmp     loc_1800119A3
0x1800115c8  mov     rbx, [r15]
0x1800115cb  xor     eax, eax
0x1800115cd  mov     r12, r13
0x1800115d0  sub     r12, rcx
0x1800115d3  sar     r12, 3
0x1800115d7  mov     ecx, r12d
0x1800115da  cmp     [rdx+rcx*8], rax
0x1800115de  setnl   al
0x1800115e1  mov     [rbp+var_30], eax
0x1800115e4  test    eax, eax
0x1800115e6  jz      short loc_1800115FB
0x1800115e8  mov     eax, [rdx+rcx*8]
0x1800115eb  lea     rdx, word_180000002
0x1800115f2  add     rax, rdx
0x1800115f5  mov     [rbp+lpProcName], rax
0x1800115f9  jmp     short loc_180011602
0x1800115fb  movzx   eax, word ptr [rdx+rcx*8]
0x1800115ff  mov     dword ptr [rbp+lpProcName], eax
0x180011602  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180011609  xor     edi, edi
0x18001160b  test    r8, r8
0x18001160e  jz      short loc_180011631
0x180011610  lea     rdx, [rbp+var_50]
0x180011614  xor     ecx, ecx
0x180011616  mov     rax, r8
0x180011619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001161e  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180011625  mov     rdi, rax
0x180011628  test    rax, rax
0x18001162b  jnz     loc_180011930
0x180011631  test    rbx, rbx
0x180011634  jnz     loc_1800117A0
0x18001163a  test    r8, r8
0x18001163d  jz      short loc_18001165A
0x18001163f  lea     rdx, [rbp+var_50]
0x180011643  mov     rax, r8
0x180011646  lea     ecx, [rbx+1]
0x180011649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001164e  mov     rbx, rax
0x180011651  test    rax, rax
0x180011654  jnz     loc_180011724
0x18001165a  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001165e  xor     r8d, r8d; dwFlags
0x180011661  xor     edx, edx; hFile
0x180011663  call    cs:__imp_LoadLibraryExA
0x18001166a  nop     dword ptr [rax+rax+00h]
0x18001166f  mov     rbx, rax
0x180011672  test    rax, rax
0x180011675  jnz     loc_180011724
0x18001167b  call    cs:__imp_GetLastError
0x180011682  nop     dword ptr [rax+rax+00h]
0x180011687  mov     [rbp+var_10], eax
0x18001168a  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180011691  test    rax, rax
0x180011694  jz      short loc_1800116AA
0x180011696  lea     rdx, [rbp+var_50]
0x18001169a  lea     ecx, [rbx+3]
0x18001169d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a2  mov     rbx, rax
0x1800116a5  test    rax, rax
0x1800116a8  jnz     short loc_180011724
0x1800116aa  and     [rbp+flOldProtect], 0
0x1800116ae  lea     rax, [rbp+var_50]
0x1800116b2  test    cs:dword_1800140A0, 1000h
0x1800116bc  mov     [rbp+Arguments], rax
0x1800116c0  jz      short loc_180011700
0x1800116c2  lea     rcx, DloadSrwLock; SRWLock
0x1800116c9  call    cs:__imp_AcquireSRWLockExclusive
0x1800116d0  nop     dword ptr [rax+rax+00h]
0x1800116d5  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800116dc  jnz     short loc_1800116ED
0x1800116de  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800116e4  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800116e8  call    DloadProtectSection
0x1800116ed  lea     rcx, DloadSrwLock; SRWLock
0x1800116f4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800116fb  nop     dword ptr [rax+rax+00h]
0x180011700  xor     edx, edx; dwExceptionFlags
0x180011702  lea     r9, [rbp+Arguments]; lpArguments
0x180011706  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18001170b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001170f  call    cs:__imp_RaiseException
0x180011716  nop     dword ptr [rax+rax+00h]
0x18001171b  mov     rax, [rbp+var_18]
0x18001171f  jmp     loc_1800119A3
0x180011724  xor     eax, eax
0x180011726  lock cmpxchg [r15], rbx
0x18001172b  mov     r15, rax
0x18001172e  jnz     short loc_18001177D
0x180011730  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011734  jz      short loc_180011799
0x180011736  cmp     dword ptr [r14+18h], 0
0x18001173b  jz      short loc_180011799
0x18001173d  call    cs:__imp_GetProcessHeap
0x180011744  nop     dword ptr [rax+rax+00h]
0x180011749  mov     edx, 8; dwFlags
0x18001174e  mov     rcx, rax; hHeap
0x180011751  lea     r8d, [rdx+8]; dwBytes
0x180011755  call    cs:__imp_HeapAlloc
0x18001175c  nop     dword ptr [rax+rax+00h]
0x180011761  test    rax, rax
0x180011764  jz      short loc_180011799
0x180011766  mov     [rax+8], r14
0x18001176a  mov     rcx, cs:__puiHead
0x180011771  mov     [rax], rcx
0x180011774  mov     cs:__puiHead, rax
0x18001177b  jmp     short loc_180011799
0x18001177d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011781  jz      short loc_180011792
0x180011783  mov     rcx, rbx; hLibModule
0x180011786  call    cs:__imp_FreeLibrary
0x18001178d  nop     dword ptr [rax+rax+00h]
0x180011792  cmp     rbx, r15
0x180011795  cmovnz  rbx, r15
0x180011799  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800117a0  mov     [rbp+var_20], rbx
0x1800117a4  test    r8, r8
0x1800117a7  jz      short loc_1800117C4
0x1800117a9  lea     rdx, [rbp+var_50]
0x1800117ad  mov     ecx, 2
0x1800117b2  mov     rax, r8
0x1800117b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117ba  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800117c1  mov     rdi, rax
0x1800117c4  test    rdi, rdi
0x1800117c7  jnz     loc_18001192C
0x1800117cd  cmp     [r14+14h], edi
0x1800117d1  jz      short loc_18001180A
0x1800117d3  cmp     [r14+1Ch], edi
0x1800117d7  jz      short loc_18001180A
0x1800117d9  movsxd  rax, dword ptr [rbx+3Ch]
0x1800117dd  cmp     dword ptr [rax+rbx], 4550h
0x1800117e4  jnz     short loc_18001180A
0x1800117e6  mov     ecx, [rbp+flOldProtect]
0x1800117e9  cmp     [rax+rbx+8], ecx
0x1800117ed  jnz     short loc_18001180A
0x1800117ef  cmp     rbx, [rax+rbx+30h]
0x1800117f4  jnz     short loc_18001180A
0x1800117f6  mov     rdi, [rbp+Arguments]
0x1800117fa  mov     eax, r12d
0x1800117fd  mov     rdi, [rdi+rax*8]
0x180011801  test    rdi, rdi
0x180011804  jnz     loc_18001192C
0x18001180a  mov     rdx, [rbp+lpProcName]; lpProcName
0x18001180e  mov     rcx, rbx; hModule
0x180011811  call    cs:__imp_GetProcAddress
0x180011818  nop     dword ptr [rax+rax+00h]
0x18001181d  mov     rdi, rax
0x180011820  test    rax, rax
0x180011823  jnz     loc_180011925
0x180011829  call    cs:__imp_GetLastError
0x180011830  nop     dword ptr [rax+rax+00h]
0x180011835  mov     [rbp+var_10], eax
0x180011838  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001183f  test    rax, rax
0x180011842  jz      short loc_18001185C
0x180011844  lea     rdx, [rbp+var_50]
0x180011848  lea     ecx, [rdi+4]
0x18001184b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011850  mov     rdi, rax
0x180011853  test    rax, rax
0x180011856  jnz     loc_180011925
0x18001185c  and     [rbp+flOldProtect], 0
0x180011860  lea     rax, [rbp+var_50]
0x180011864  test    cs:dword_1800140A0, 1000h
0x18001186e  mov     [rbp+Arguments], rax
0x180011872  jz      short loc_1800118B2
0x180011874  lea     rcx, DloadSrwLock; SRWLock
0x18001187b  call    cs:__imp_AcquireSRWLockExclusive
0x180011882  nop     dword ptr [rax+rax+00h]
0x180011887  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18001188e  jnz     short loc_18001189F
0x180011890  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180011896  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18001189a  call    DloadProtectSection
0x18001189f  lea     rcx, DloadSrwLock; SRWLock
0x1800118a6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800118ad  nop     dword ptr [rax+rax+00h]
0x1800118b2  xor     edx, edx; dwExceptionFlags
0x1800118b4  lea     r9, [rbp+Arguments]; lpArguments
0x1800118b8  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800118bd  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800118c1  call    cs:__imp_RaiseException
0x1800118c8  nop     dword ptr [rax+rax+00h]
0x1800118cd  test    cs:dword_1800140A0, 1000h
0x1800118d7  jz      short loc_180011921
0x1800118d9  lea     rcx, DloadSrwLock; SRWLock
0x1800118e0  call    cs:__imp_AcquireSRWLockExclusive
0x1800118e7  nop     dword ptr [rax+rax+00h]
0x1800118ec  mov     eax, cs:DloadSectionLockCount
0x1800118f2  inc     eax
0x1800118f4  mov     cs:DloadSectionLockCount, eax
0x1800118fa  cmp     eax, 1
0x1800118fd  jnz     short loc_18001190E
0x1800118ff  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180011906  lea     ecx, [rax+3]; flNewProtect
0x180011909  call    DloadProtectSection
0x18001190e  lea     rcx, DloadSrwLock; SRWLock
0x180011915  call    cs:__imp_ReleaseSRWLockExclusive
0x18001191c  nop     dword ptr [rax+rax+00h]
0x180011921  mov     rdi, [rbp+var_18]
0x180011925  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001192c  mov     [r13+0], rdi
0x180011930  test    r8, r8
0x180011933  jz      short loc_180011952
0x180011935  and     [rbp+var_10], 0
0x180011939  lea     rdx, [rbp+var_50]
0x18001193d  mov     ecx, 5
0x180011942  mov     [rbp+var_20], rbx
0x180011946  mov     rax, r8
0x180011949  mov     [rbp+var_18], rdi
0x18001194d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011952  and     [rbp+flOldProtect], 0
0x180011956  test    cs:dword_1800140A0, 1000h
0x180011960  jz      short loc_1800119A0
0x180011962  lea     rcx, DloadSrwLock; SRWLock
  ... truncated ...
```

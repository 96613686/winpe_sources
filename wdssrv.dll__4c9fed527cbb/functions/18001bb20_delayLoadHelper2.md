# __delayLoadHelper2

- ea: `0x18001bb20`
- end: `0x18001c06e`
- name: `__delayLoadHelper2`
- size: `1358`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f96`
- `0x18001ba10`

## callees

- `0x18001b910`
- `0x18001bb20`
- `0x18001d010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18001bc65`
- `KERNEL32!RaiseException` at `0x18001bdbf`
- `KERNEL32!RaiseException` at `0x18001bf71`
- `KERNEL32!RaiseException` at `0x18001bc65`
- `KERNEL32!RaiseException` at `0x18001bdbf`
- `KERNEL32!RaiseException` at `0x18001bf71`
- `KERNEL32!LoadLibraryExA` at `0x18001bd13`
- `KERNEL32!LoadLibraryExA` at `0x18001bd13`
- `KERNEL32!GetLastError` at `0x18001bd2b`
- `KERNEL32!GetLastError` at `0x18001bed9`
- `KERNEL32!GetLastError` at `0x18001bd2b`
- `KERNEL32!GetLastError` at `0x18001bed9`
- `KERNEL32!GetProcessHeap` at `0x18001bded`
- `KERNEL32!GetProcessHeap` at `0x18001bded`
- `KERNEL32!HeapAlloc` at `0x18001be05`
- `KERNEL32!HeapAlloc` at `0x18001be05`
- `KERNEL32!GetProcAddress` at `0x18001bec1`
- `KERNEL32!GetProcAddress` at `0x18001bec1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bb64`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bc24`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bd79`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bf2b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bf90`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001c019`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bb64`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bc24`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bd79`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bf2b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001bf90`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001c019`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bb94`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bc4b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bda4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bf56`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bfc5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c044`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bb94`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bc4b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bda4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bf56`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bfc5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001c044`
- `KERNEL32!FreeLibrary` at `0x18001be36`
- `KERNEL32!FreeLibrary` at `0x18001be36`

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
0x18001bb20  mov     [rsp-28h+arg_10], rbx
0x18001bb25  mov     [rsp-28h+arg_18], rdi
0x18001bb2a  push    rbp
0x18001bb2b  push    r12
0x18001bb2d  push    r13
0x18001bb2f  push    r14
0x18001bb31  push    r15
0x18001bb33  mov     rbp, rsp
0x18001bb36  sub     rsp, 70h
0x18001bb3a  xor     eax, eax
0x18001bb3c  lea     rbx, DloadSrwLock
0x18001bb43  and     [rbp+var_2C], eax
0x18001bb46  mov     r13, rdx
0x18001bb49  mov     [rbp+var_4C], eax
0x18001bb4c  mov     r14, rcx
0x18001bb4f  and     [rbp+var_4C], eax
0x18001bb52  test    cs:dword_18001E0A0, 1000h
0x18001bb5c  lea     edi, [rax+1]
0x18001bb5f  jz      short loc_18001BBA0
0x18001bb61  mov     rcx, rbx; SRWLock
0x18001bb64  call    cs:__imp_AcquireSRWLockExclusive
0x18001bb6b  nop     dword ptr [rax+rax+00h]
0x18001bb70  mov     eax, cs:DloadSectionLockCount
0x18001bb76  add     eax, edi
0x18001bb78  mov     cs:DloadSectionLockCount, eax
0x18001bb7e  cmp     eax, edi
0x18001bb80  jnz     short loc_18001BB91
0x18001bb82  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18001bb89  lea     ecx, [rdi+3]; flNewProtect
0x18001bb8c  call    DloadProtectSection
0x18001bb91  mov     rcx, rbx; SRWLock
0x18001bb94  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bb9b  nop     dword ptr [rax+rax+00h]
0x18001bba0  mov     eax, [r14+4]
0x18001bba4  lea     r9, __ImageBase
0x18001bbab  mov     r8d, [r14+14h]
0x18001bbaf  add     rax, r9
0x18001bbb2  mov     r15d, [r14+8]
0x18001bbb6  add     r8, r9
0x18001bbb9  mov     ecx, [r14+0Ch]
0x18001bbbd  add     r15, r9
0x18001bbc0  mov     edx, [r14+10h]
0x18001bbc4  add     rcx, r9
0x18001bbc7  and     [rbp+var_30], 0
0x18001bbcb  add     rdx, r9
0x18001bbce  and     [rbp+lpProcName], 0
0x18001bbd3  and     [rbp+var_20], 0
0x18001bbd8  and     [rbp+var_18], 0
0x18001bbdd  and     [rbp+var_10], 0
0x18001bbe1  mov     [rbp+lpLibFileName], rax
0x18001bbe5  mov     eax, [r14]
0x18001bbe8  and     eax, edi
0x18001bbea  mov     [rbp+Arguments], r8
0x18001bbee  mov     r8d, [r14+1Ch]
0x18001bbf2  mov     [rbp+flOldProtect], r8d
0x18001bbf6  mov     [rbp+var_50], 48h ; 'H'
0x18001bbfd  mov     [rbp+var_48], r14
0x18001bc01  mov     [rbp+var_40], r13
0x18001bc05  test    al, al
0x18001bc07  jnz     short loc_18001BC78
0x18001bc09  and     [rbp+flOldProtect], 0
0x18001bc0d  lea     rax, [rbp+var_50]
0x18001bc11  test    cs:dword_18001E0A0, 1000h
0x18001bc1b  mov     [rbp+Arguments], rax
0x18001bc1f  jz      short loc_18001BC57
0x18001bc21  mov     rcx, rbx; SRWLock
0x18001bc24  call    cs:__imp_AcquireSRWLockExclusive
0x18001bc2b  nop     dword ptr [rax+rax+00h]
0x18001bc30  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18001bc37  jnz     short loc_18001BC48
0x18001bc39  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18001bc3f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18001bc43  call    DloadProtectSection
0x18001bc48  mov     rcx, rbx; SRWLock
0x18001bc4b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bc52  nop     dword ptr [rax+rax+00h]
0x18001bc57  lea     r9, [rbp+Arguments]; lpArguments
0x18001bc5b  mov     r8d, edi; nNumberOfArguments
0x18001bc5e  xor     edx, edx; dwExceptionFlags
0x18001bc60  mov     ecx, 0C06D0057h; dwExceptionCode
0x18001bc65  call    cs:__imp_RaiseException
0x18001bc6c  nop     dword ptr [rax+rax+00h]
0x18001bc71  xor     eax, eax
0x18001bc73  jmp     loc_18001C053
0x18001bc78  mov     rbx, [r15]
0x18001bc7b  xor     eax, eax
0x18001bc7d  mov     r12, r13
0x18001bc80  sub     r12, rcx
0x18001bc83  sar     r12, 3
0x18001bc87  mov     ecx, r12d
0x18001bc8a  cmp     [rdx+rcx*8], rax
0x18001bc8e  setnl   al
0x18001bc91  mov     [rbp+var_30], eax
0x18001bc94  test    eax, eax
0x18001bc96  jz      short loc_18001BCAB
0x18001bc98  mov     eax, [rdx+rcx*8]
0x18001bc9b  lea     rdx, word_180000002
0x18001bca2  add     rax, rdx
0x18001bca5  mov     [rbp+lpProcName], rax
0x18001bca9  jmp     short loc_18001BCB2
0x18001bcab  movzx   eax, word ptr [rdx+rcx*8]
0x18001bcaf  mov     dword ptr [rbp+lpProcName], eax
0x18001bcb2  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001bcb9  xor     edi, edi
0x18001bcbb  test    r8, r8
0x18001bcbe  jz      short loc_18001BCE1
0x18001bcc0  lea     rdx, [rbp+var_50]
0x18001bcc4  xor     ecx, ecx
0x18001bcc6  mov     rax, r8
0x18001bcc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcce  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001bcd5  mov     rdi, rax
0x18001bcd8  test    rax, rax
0x18001bcdb  jnz     loc_18001BFE0
0x18001bce1  test    rbx, rbx
0x18001bce4  jnz     loc_18001BE50
0x18001bcea  test    r8, r8
0x18001bced  jz      short loc_18001BD0A
0x18001bcef  lea     rdx, [rbp+var_50]
0x18001bcf3  mov     rax, r8
0x18001bcf6  lea     ecx, [rbx+1]
0x18001bcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcfe  mov     rbx, rax
0x18001bd01  test    rax, rax
0x18001bd04  jnz     loc_18001BDD4
0x18001bd0a  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001bd0e  xor     r8d, r8d; dwFlags
0x18001bd11  xor     edx, edx; hFile
0x18001bd13  call    cs:__imp_LoadLibraryExA
0x18001bd1a  nop     dword ptr [rax+rax+00h]
0x18001bd1f  mov     rbx, rax
0x18001bd22  test    rax, rax
0x18001bd25  jnz     loc_18001BDD4
0x18001bd2b  call    cs:__imp_GetLastError
0x18001bd32  nop     dword ptr [rax+rax+00h]
0x18001bd37  mov     [rbp+var_10], eax
0x18001bd3a  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001bd41  test    rax, rax
0x18001bd44  jz      short loc_18001BD5A
0x18001bd46  lea     rdx, [rbp+var_50]
0x18001bd4a  lea     ecx, [rbx+3]
0x18001bd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd52  mov     rbx, rax
0x18001bd55  test    rax, rax
0x18001bd58  jnz     short loc_18001BDD4
0x18001bd5a  and     [rbp+flOldProtect], 0
0x18001bd5e  lea     rax, [rbp+var_50]
0x18001bd62  test    cs:dword_18001E0A0, 1000h
0x18001bd6c  mov     [rbp+Arguments], rax
0x18001bd70  jz      short loc_18001BDB0
0x18001bd72  lea     rcx, DloadSrwLock; SRWLock
0x18001bd79  call    cs:__imp_AcquireSRWLockExclusive
0x18001bd80  nop     dword ptr [rax+rax+00h]
0x18001bd85  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18001bd8c  jnz     short loc_18001BD9D
0x18001bd8e  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18001bd94  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18001bd98  call    DloadProtectSection
0x18001bd9d  lea     rcx, DloadSrwLock; SRWLock
0x18001bda4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bdab  nop     dword ptr [rax+rax+00h]
0x18001bdb0  xor     edx, edx; dwExceptionFlags
0x18001bdb2  lea     r9, [rbp+Arguments]; lpArguments
0x18001bdb6  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18001bdbb  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001bdbf  call    cs:__imp_RaiseException
0x18001bdc6  nop     dword ptr [rax+rax+00h]
0x18001bdcb  mov     rax, [rbp+var_18]
0x18001bdcf  jmp     loc_18001C053
0x18001bdd4  xor     eax, eax
0x18001bdd6  lock cmpxchg [r15], rbx
0x18001bddb  mov     r15, rax
0x18001bdde  jnz     short loc_18001BE2D
0x18001bde0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001bde4  jz      short loc_18001BE49
0x18001bde6  cmp     dword ptr [r14+18h], 0
0x18001bdeb  jz      short loc_18001BE49
0x18001bded  call    cs:__imp_GetProcessHeap
0x18001bdf4  nop     dword ptr [rax+rax+00h]
0x18001bdf9  mov     edx, 8; dwFlags
0x18001bdfe  mov     rcx, rax; hHeap
0x18001be01  lea     r8d, [rdx+8]; dwBytes
0x18001be05  call    cs:__imp_HeapAlloc
0x18001be0c  nop     dword ptr [rax+rax+00h]
0x18001be11  test    rax, rax
0x18001be14  jz      short loc_18001BE49
0x18001be16  mov     [rax+8], r14
0x18001be1a  mov     rcx, cs:__puiHead
0x18001be21  mov     [rax], rcx
0x18001be24  mov     cs:__puiHead, rax
0x18001be2b  jmp     short loc_18001BE49
0x18001be2d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001be31  jz      short loc_18001BE42
0x18001be33  mov     rcx, rbx; hLibModule
0x18001be36  call    cs:__imp_FreeLibrary
0x18001be3d  nop     dword ptr [rax+rax+00h]
0x18001be42  cmp     rbx, r15
0x18001be45  cmovnz  rbx, r15
0x18001be49  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001be50  mov     [rbp+var_20], rbx
0x18001be54  test    r8, r8
0x18001be57  jz      short loc_18001BE74
0x18001be59  lea     rdx, [rbp+var_50]
0x18001be5d  mov     ecx, 2
0x18001be62  mov     rax, r8
0x18001be65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be6a  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001be71  mov     rdi, rax
0x18001be74  test    rdi, rdi
0x18001be77  jnz     loc_18001BFDC
0x18001be7d  cmp     [r14+14h], edi
0x18001be81  jz      short loc_18001BEBA
0x18001be83  cmp     [r14+1Ch], edi
0x18001be87  jz      short loc_18001BEBA
0x18001be89  movsxd  rax, dword ptr [rbx+3Ch]
0x18001be8d  cmp     dword ptr [rax+rbx], 4550h
0x18001be94  jnz     short loc_18001BEBA
0x18001be96  mov     ecx, [rbp+flOldProtect]
0x18001be99  cmp     [rax+rbx+8], ecx
0x18001be9d  jnz     short loc_18001BEBA
0x18001be9f  cmp     rbx, [rax+rbx+30h]
0x18001bea4  jnz     short loc_18001BEBA
0x18001bea6  mov     rdi, [rbp+Arguments]
0x18001beaa  mov     eax, r12d
0x18001bead  mov     rdi, [rdi+rax*8]
0x18001beb1  test    rdi, rdi
0x18001beb4  jnz     loc_18001BFDC
0x18001beba  mov     rdx, [rbp+lpProcName]; lpProcName
0x18001bebe  mov     rcx, rbx; hModule
0x18001bec1  call    cs:__imp_GetProcAddress
0x18001bec8  nop     dword ptr [rax+rax+00h]
0x18001becd  mov     rdi, rax
0x18001bed0  test    rax, rax
0x18001bed3  jnz     loc_18001BFD5
0x18001bed9  call    cs:__imp_GetLastError
0x18001bee0  nop     dword ptr [rax+rax+00h]
0x18001bee5  mov     [rbp+var_10], eax
0x18001bee8  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001beef  test    rax, rax
0x18001bef2  jz      short loc_18001BF0C
0x18001bef4  lea     rdx, [rbp+var_50]
0x18001bef8  lea     ecx, [rdi+4]
0x18001befb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf00  mov     rdi, rax
0x18001bf03  test    rax, rax
0x18001bf06  jnz     loc_18001BFD5
0x18001bf0c  and     [rbp+flOldProtect], 0
0x18001bf10  lea     rax, [rbp+var_50]
0x18001bf14  test    cs:dword_18001E0A0, 1000h
0x18001bf1e  mov     [rbp+Arguments], rax
0x18001bf22  jz      short loc_18001BF62
0x18001bf24  lea     rcx, DloadSrwLock; SRWLock
0x18001bf2b  call    cs:__imp_AcquireSRWLockExclusive
0x18001bf32  nop     dword ptr [rax+rax+00h]
0x18001bf37  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18001bf3e  jnz     short loc_18001BF4F
0x18001bf40  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18001bf46  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18001bf4a  call    DloadProtectSection
0x18001bf4f  lea     rcx, DloadSrwLock; SRWLock
0x18001bf56  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bf5d  nop     dword ptr [rax+rax+00h]
0x18001bf62  xor     edx, edx; dwExceptionFlags
0x18001bf64  lea     r9, [rbp+Arguments]; lpArguments
0x18001bf68  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18001bf6d  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001bf71  call    cs:__imp_RaiseException
0x18001bf78  nop     dword ptr [rax+rax+00h]
0x18001bf7d  test    cs:dword_18001E0A0, 1000h
0x18001bf87  jz      short loc_18001BFD1
0x18001bf89  lea     rcx, DloadSrwLock; SRWLock
0x18001bf90  call    cs:__imp_AcquireSRWLockExclusive
0x18001bf97  nop     dword ptr [rax+rax+00h]
0x18001bf9c  mov     eax, cs:DloadSectionLockCount
0x18001bfa2  inc     eax
0x18001bfa4  mov     cs:DloadSectionLockCount, eax
0x18001bfaa  cmp     eax, 1
0x18001bfad  jnz     short loc_18001BFBE
0x18001bfaf  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18001bfb6  lea     ecx, [rax+3]; flNewProtect
0x18001bfb9  call    DloadProtectSection
0x18001bfbe  lea     rcx, DloadSrwLock; SRWLock
0x18001bfc5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bfcc  nop     dword ptr [rax+rax+00h]
0x18001bfd1  mov     rdi, [rbp+var_18]
0x18001bfd5  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001bfdc  mov     [r13+0], rdi
0x18001bfe0  test    r8, r8
0x18001bfe3  jz      short loc_18001C002
0x18001bfe5  and     [rbp+var_10], 0
0x18001bfe9  lea     rdx, [rbp+var_50]
0x18001bfed  mov     ecx, 5
0x18001bff2  mov     [rbp+var_20], rbx
0x18001bff6  mov     rax, r8
0x18001bff9  mov     [rbp+var_18], rdi
0x18001bffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c002  and     [rbp+flOldProtect], 0
0x18001c006  test    cs:dword_18001E0A0, 1000h
0x18001c010  jz      short loc_18001C050
0x18001c012  lea     rcx, DloadSrwLock; SRWLock
  ... truncated ...
```

# __delayLoadHelper2

- ea: `0x140025fd0`
- end: `0x140026345`
- name: `__delayLoadHelper2`
- size: `885`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400030d2`
- `0x1400031b2`
- `0x14000325b`

## callees

- `0x140002fa0`
- `0x140025d4c`
- `0x140025f6c`
- `0x140025fd0`
- `0x140029010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x140026136`
- `KERNEL32!LoadLibraryExA` at `0x140026136`
- `KERNEL32!FreeLibrary` at `0x14002620b`
- `KERNEL32!FreeLibrary` at `0x14002620b`
- `KERNEL32!GetLastError` at `0x14002614a`
- `KERNEL32!GetLastError` at `0x14002629e`
- `KERNEL32!GetLastError` at `0x14002614a`
- `KERNEL32!GetLastError` at `0x14002629e`
- `KERNEL32!HeapAlloc` at `0x1400261da`
- `KERNEL32!HeapAlloc` at `0x1400261da`
- `KERNEL32!GetProcAddress` at `0x14002628a`
- `KERNEL32!GetProcAddress` at `0x14002628a`
- `KERNEL32!GetProcessHeap` at `0x1400261c2`
- `KERNEL32!GetProcessHeap` at `0x1400261c2`
- `KERNEL32!RaiseException` at `0x14002607f`
- `KERNEL32!RaiseException` at `0x140026195`
- `KERNEL32!RaiseException` at `0x1400262e9`
- `KERNEL32!RaiseException` at `0x14002607f`
- `KERNEL32!RaiseException` at `0x140026195`
- `KERNEL32!RaiseException` at `0x1400262e9`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  unsigned __int64 v5; // rdx
  volatile signed __int64 *v6; // r14
  __int64 dwTimeStamp; // rcx
  char *v8; // r15
  DWORD grAttrs; // eax
  HMODULE Library; // rbx
  __int64 v12; // r13
  PUnloadInfo v13; // rcx
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v16; // r14
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  struct DelayLoadInfo v22; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+48h] BYREF

  *(&v22.cb + 1) = 0;
  memset_0(&v22, 0, 0x44u);
  ((void (*)(void))DloadAcquireSectionWriteAccess)();
  v5 = (unsigned __int64)&_ImageBase;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase.unused + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v8 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v22.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v22.cb = 72;
  v22.pidd = a1;
  v22.ppfn = a2;
  v22.dlp.fImportByName = 0;
  memset(&v22.dlp.szProcName, 0, 28);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v22;
    DloadReleaseSectionWriteAccess(dwTimeStamp, &_ImageBase, v4);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v6;
  v12 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v13 = (PUnloadInfo)(v12 + a1->rvaINT);
  v22.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase.unused + (_QWORD)v13) >= 0LL;
  if ( v22.dlp.fImportByName )
  {
    v5 = (unsigned __int64)&_ImageBase.unused + 2;
    v22.dlp.szProcName = (char *)&_ImageBase.unused + *(unsigned int *)((char *)&_ImageBase.unused + (_QWORD)v13) + 2;
  }
  else
  {
    v22.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase.unused + (_QWORD)v13);
  }
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v22), v14 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(1, &v22)) == 0 )
      {
        Library = LoadLibraryExA(v22.szDll, 0, 0);
        if ( !Library )
        {
          v22.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v22)) == 0 )
          {
            Arguments = (ULONG_PTR)&v22;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v22.pfnCur;
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
            v13 = _puiHead;
            v18->puiNext = _puiHead;
            _puiHead = v18;
          }
        }
      }
      v14 = _pfnDliNotifyHook2;
    }
    v22.hmodCur = Library;
    if ( v14 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(2, &v22);
      v14 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v13 = (PUnloadInfo)*((int *)Library + 15), *(_DWORD *)((char *)Library + (_QWORD)v13) != 17744)
        || (v5 = (unsigned int)Arguments, *(_DWORD *)((char *)Library + (_QWORD)v13 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + (_QWORD)v13 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v8[v12]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v22.dlp.szProcName);
        if ( !ProcAddress )
        {
          v22.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v22)) == 0 )
          {
            Arguments = (ULONG_PTR)&v22;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            DloadAcquireSectionWriteAccess(v20, v19, v21);
            ProcAddress = v22.pfnCur;
          }
        }
        v14 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v14 )
  {
    v22.dwLastError = 0;
    v22.hmodCur = Library;
    v22.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(5, &v22);
  }
  DloadReleaseSectionWriteAccess(v13, v5, v4);
  return ProcAddress;
}

```

## disassembly

```asm
0x140025fd0  push    rbp
0x140025fd2  push    rbx
0x140025fd3  push    rsi
0x140025fd4  push    rdi
0x140025fd5  push    r12
0x140025fd7  push    r13
0x140025fd9  push    r14
0x140025fdb  push    r15
0x140025fdd  mov     rbp, rsp
0x140025fe0  sub     rsp, 78h
0x140025fe4  xor     eax, eax
0x140025fe6  mov     r12, rdx
0x140025fe9  mov     rsi, rcx
0x140025fec  mov     [rbp+var_54], eax
0x140025fef  xor     edx, edx; Val
0x140025ff1  lea     rcx, [rbp+var_58]; void *
0x140025ff5  lea     r8d, [rax+44h]; Size
0x140025ff9  call    memset_0
0x140025ffe  call    DloadAcquireSectionWriteAccess
0x140026003  mov     eax, [rsi+4]
0x140026006  lea     rdx, __ImageBase
0x14002600d  mov     r14d, [rsi+8]
0x140026011  add     rax, rdx
0x140026014  mov     r15d, [rsi+14h]
0x140026018  add     r14, rdx
0x14002601b  mov     ecx, [rsi+1Ch]
0x14002601e  add     r15, rdx
0x140026021  mov     [rbp+lpLibFileName], rax
0x140026025  mov     eax, [rsi]
0x140026027  mov     dword ptr [rbp+Arguments], ecx
0x14002602a  mov     [rbp+var_58], 48h ; 'H'
0x140026031  mov     [rbp+var_50], rsi
0x140026035  mov     [rbp+var_48], r12
0x140026039  mov     [rbp+var_38], 0
0x140026040  mov     [rbp+lpProcName], 0
0x140026048  mov     [rbp+var_28], 0
0x140026050  mov     [rbp+var_20], 0
0x140026058  mov     [rbp+var_18], 0
0x14002605f  test    al, 1
0x140026061  jnz     short loc_140026092
0x140026063  lea     rax, [rbp+var_58]
0x140026067  mov     [rbp+Arguments], rax
0x14002606b  call    DloadReleaseSectionWriteAccess
0x140026070  xor     edx, edx; dwExceptionFlags
0x140026072  lea     r9, [rbp+Arguments]; lpArguments
0x140026076  mov     ecx, 0C06D0057h; dwExceptionCode
0x14002607b  lea     r8d, [rdx+1]; nNumberOfArguments
0x14002607f  call    cs:__imp_RaiseException
0x140026086  nop     dword ptr [rax+rax+00h]
0x14002608b  xor     eax, eax
0x14002608d  jmp     loc_140026333
0x140026092  mov     eax, [rsi+0Ch]
0x140026095  mov     rcx, r12
0x140026098  mov     rbx, [r14]
0x14002609b  sub     rcx, rax
0x14002609e  sub     rcx, rdx
0x1400260a1  sar     rcx, 3
0x1400260a5  mov     eax, ecx
0x1400260a7  mov     ecx, [rsi+10h]
0x1400260aa  lea     r13, ds:0[rax*8]
0x1400260b2  xor     eax, eax
0x1400260b4  add     rcx, r13
0x1400260b7  cmp     [rcx+rdx], rax
0x1400260bb  setnl   al
0x1400260be  mov     [rbp+var_38], eax
0x1400260c1  test    eax, eax
0x1400260c3  jz      short loc_1400260D8
0x1400260c5  mov     eax, [rcx+rdx]
0x1400260c8  lea     rdx, __ImageBase.unused+2
0x1400260cf  add     rax, rdx
0x1400260d2  mov     [rbp+lpProcName], rax
0x1400260d6  jmp     short loc_1400260DF
0x1400260d8  movzx   eax, word ptr [rcx+rdx]
0x1400260dc  mov     dword ptr [rbp+lpProcName], eax
0x1400260df  mov     rax, cs:__pfnDliNotifyHook2
0x1400260e6  xor     edi, edi
0x1400260e8  test    rax, rax
0x1400260eb  jz      short loc_14002610B
0x1400260ed  lea     rdx, [rbp+var_58]
0x1400260f1  xor     ecx, ecx
0x1400260f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400260f8  mov     rdi, rax
0x1400260fb  test    rax, rax
0x1400260fe  mov     rax, cs:__pfnDliNotifyHook2
0x140026105  jnz     loc_140026309
0x14002610b  test    rbx, rbx
0x14002610e  jnz     loc_140026225
0x140026114  test    rax, rax
0x140026117  jz      short loc_14002612D
0x140026119  lea     rdx, [rbp+var_58]
0x14002611d  lea     ecx, [rbx+1]
0x140026120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026125  mov     rbx, rax
0x140026128  test    rax, rax
0x14002612b  jnz     short loc_1400261AA
0x14002612d  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x140026131  xor     r8d, r8d; dwFlags
0x140026134  xor     edx, edx; hFile
0x140026136  call    cs:__imp_LoadLibraryExA
0x14002613d  nop     dword ptr [rax+rax+00h]
0x140026142  mov     rbx, rax
0x140026145  test    rax, rax
0x140026148  jnz     short loc_1400261AA
0x14002614a  call    cs:__imp_GetLastError
0x140026151  nop     dword ptr [rax+rax+00h]
0x140026156  mov     [rbp+var_18], eax
0x140026159  mov     rax, cs:__pfnDefaultDliFailureHook2
0x140026160  test    rax, rax
0x140026163  jz      short loc_140026179
0x140026165  lea     rdx, [rbp+var_58]
0x140026169  lea     ecx, [rbx+3]
0x14002616c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026171  mov     rbx, rax
0x140026174  test    rax, rax
0x140026177  jnz     short loc_1400261AA
0x140026179  lea     rax, [rbp+var_58]
0x14002617d  mov     [rbp+Arguments], rax
0x140026181  call    DloadReleaseSectionWriteAccess
0x140026186  xor     edx, edx; dwExceptionFlags
0x140026188  lea     r9, [rbp+Arguments]; lpArguments
0x14002618c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x140026191  lea     r8d, [rdx+1]; nNumberOfArguments
0x140026195  call    cs:__imp_RaiseException
0x14002619c  nop     dword ptr [rax+rax+00h]
0x1400261a1  mov     rax, [rbp+var_20]
0x1400261a5  jmp     loc_140026333
0x1400261aa  xor     eax, eax
0x1400261ac  lock cmpxchg [r14], rbx
0x1400261b1  mov     r14, rax
0x1400261b4  jnz     short loc_140026202
0x1400261b6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400261ba  jz      short loc_14002621E
0x1400261bc  cmp     dword ptr [rsi+18h], 0
0x1400261c0  jz      short loc_14002621E
0x1400261c2  call    cs:__imp_GetProcessHeap
0x1400261c9  nop     dword ptr [rax+rax+00h]
0x1400261ce  mov     edx, 8; dwFlags
0x1400261d3  mov     rcx, rax; hHeap
0x1400261d6  lea     r8d, [rdx+8]; dwBytes
0x1400261da  call    cs:__imp_HeapAlloc
0x1400261e1  nop     dword ptr [rax+rax+00h]
0x1400261e6  test    rax, rax
0x1400261e9  jz      short loc_14002621E
0x1400261eb  mov     [rax+8], rsi
0x1400261ef  mov     rcx, cs:__puiHead
0x1400261f6  mov     [rax], rcx
0x1400261f9  mov     cs:__puiHead, rax
0x140026200  jmp     short loc_14002621E
0x140026202  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140026206  jz      short loc_140026217
0x140026208  mov     rcx, rbx; hLibModule
0x14002620b  call    cs:__imp_FreeLibrary
0x140026212  nop     dword ptr [rax+rax+00h]
0x140026217  cmp     rbx, r14
0x14002621a  cmovnz  rbx, r14
0x14002621e  mov     rax, cs:__pfnDliNotifyHook2
0x140026225  mov     [rbp+var_28], rbx
0x140026229  test    rax, rax
0x14002622c  jz      short loc_140026246
0x14002622e  lea     rdx, [rbp+var_58]
0x140026232  mov     ecx, 2
0x140026237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002623c  mov     rdi, rax
0x14002623f  mov     rax, cs:__pfnDliNotifyHook2
0x140026246  test    rdi, rdi
0x140026249  jnz     loc_140026305
0x14002624f  cmp     [rsi+14h], edi
0x140026252  jz      short loc_140026283
0x140026254  cmp     [rsi+1Ch], edi
0x140026257  jz      short loc_140026283
0x140026259  movsxd  rcx, dword ptr [rbx+3Ch]
0x14002625d  cmp     dword ptr [rcx+rbx], 4550h
0x140026264  jnz     short loc_140026283
0x140026266  mov     edx, dword ptr [rbp+Arguments]
0x140026269  cmp     [rcx+rbx+8], edx
0x14002626d  jnz     short loc_140026283
0x14002626f  cmp     rbx, [rcx+rbx+30h]
0x140026274  jnz     short loc_140026283
0x140026276  mov     rdi, [r15+r13]
0x14002627a  test    rdi, rdi
0x14002627d  jnz     loc_140026305
0x140026283  mov     rdx, [rbp+lpProcName]; lpProcName
0x140026287  mov     rcx, rbx; hModule
0x14002628a  call    cs:__imp_GetProcAddress
0x140026291  nop     dword ptr [rax+rax+00h]
0x140026296  mov     rdi, rax
0x140026299  test    rax, rax
0x14002629c  jnz     short loc_1400262FE
0x14002629e  call    cs:__imp_GetLastError
0x1400262a5  nop     dword ptr [rax+rax+00h]
0x1400262aa  mov     [rbp+var_18], eax
0x1400262ad  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1400262b4  test    rax, rax
0x1400262b7  jz      short loc_1400262CD
0x1400262b9  lea     rdx, [rbp+var_58]
0x1400262bd  lea     ecx, [rdi+4]
0x1400262c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400262c5  mov     rdi, rax
0x1400262c8  test    rax, rax
0x1400262cb  jnz     short loc_1400262FE
0x1400262cd  lea     rax, [rbp+var_58]
0x1400262d1  mov     [rbp+Arguments], rax
0x1400262d5  call    DloadReleaseSectionWriteAccess
0x1400262da  xor     edx, edx; dwExceptionFlags
0x1400262dc  lea     r9, [rbp+Arguments]; lpArguments
0x1400262e0  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1400262e5  lea     r8d, [rdx+1]; nNumberOfArguments
0x1400262e9  call    cs:__imp_RaiseException
0x1400262f0  nop     dword ptr [rax+rax+00h]
0x1400262f5  call    DloadAcquireSectionWriteAccess
0x1400262fa  mov     rdi, [rbp+var_20]
0x1400262fe  mov     rax, cs:__pfnDliNotifyHook2
0x140026305  mov     [r12], rdi
0x140026309  test    rax, rax
0x14002630c  jz      short loc_14002632B
0x14002630e  lea     rdx, [rbp+var_58]
0x140026312  mov     [rbp+var_18], 0
0x140026319  mov     ecx, 5
0x14002631e  mov     [rbp+var_28], rbx
0x140026322  mov     [rbp+var_20], rdi
0x140026326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002632b  call    DloadReleaseSectionWriteAccess
0x140026330  mov     rax, rdi
0x140026333  add     rsp, 78h
0x140026337  pop     r15
0x140026339  pop     r14
0x14002633b  pop     r13
0x14002633d  pop     r12
0x14002633f  pop     rdi
0x140026340  pop     rsi
0x140026341  pop     rbx
0x140026342  pop     rbp
0x140026343  retn
```

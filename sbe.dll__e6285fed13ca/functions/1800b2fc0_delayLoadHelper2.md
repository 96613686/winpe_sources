# __delayLoadHelper2

- ea: `0x1800b2fc0`
- end: `0x1800b32dc`
- name: `__delayLoadHelper2`
- size: `796`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800027f6`
- `0x1800028b7`

## callees

- `0x18000256c`
- `0x18005fb24`
- `0x1800b2d68`
- `0x1800b2f68`
- `0x1800b2fc0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x1800b3120`
- `KERNEL32!LoadLibraryExA` at `0x1800b3120`
- `KERNEL32!GetProcAddress` at `0x1800b3240`
- `KERNEL32!GetProcAddress` at `0x1800b3240`
- `KERNEL32!GetLastError` at `0x1800b312e`
- `KERNEL32!GetLastError` at `0x1800b324e`
- `KERNEL32!GetLastError` at `0x1800b312e`
- `KERNEL32!GetLastError` at `0x1800b324e`
- `KERNEL32!RaiseException` at `0x1800b306f`
- `KERNEL32!RaiseException` at `0x1800b3167`
- `KERNEL32!RaiseException` at `0x1800b3287`
- `KERNEL32!RaiseException` at `0x1800b306f`
- `KERNEL32!RaiseException` at `0x1800b3167`
- `KERNEL32!RaiseException` at `0x1800b3287`
- `KERNEL32!FreeLibrary` at `0x1800b31cb`
- `KERNEL32!FreeLibrary` at `0x1800b31cb`
- `KERNEL32!GetProcessHeap` at `0x1800b318e`
- `KERNEL32!GetProcessHeap` at `0x1800b318e`
- `KERNEL32!HeapAlloc` at `0x1800b31a0`
- `KERNEL32!HeapAlloc` at `0x1800b31a0`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  __int16 *v5; // rdx
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
  DelayLoadInfo v22; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+48h] BYREF

  *(&v22.cb + 1) = 0;
  memset_0(&v22, 0, 0x44u);
  ((void (*)(void))DloadAcquireSectionWriteAccess)();
  v5 = &_ImageBase;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
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
  v22.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + (_QWORD)v13) >= 0LL;
  if ( v22.dlp.fImportByName )
  {
    v5 = &word_180000002;
    v22.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + (_QWORD)v13);
  }
  else
  {
    v22.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + (_QWORD)v13);
  }
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v22), v14 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, DelayLoadInfo *))v14)(1, &v22)) == 0 )
      {
        Library = LoadLibraryExA(v22.szDll, 0, 0);
        if ( !Library )
        {
          v22.dwLastError = GetLastError();
          Library = (HMODULE)SBE_DelayLoadFailureHook(3, &v22);
          if ( !Library )
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
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, DelayLoadInfo *))v14)(2, &v22);
      v14 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v13 = (PUnloadInfo)*((int *)Library + 15), *(_DWORD *)((char *)Library + (_QWORD)v13) != 17744)
        || (v5 = (__int16 *)(unsigned int)Arguments, *(_DWORD *)((char *)Library + (_QWORD)v13 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + (_QWORD)v13 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v8[v12]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v22.dlp.szProcName);
        if ( !ProcAddress )
        {
          v22.dwLastError = GetLastError();
          ProcAddress = SBE_DelayLoadFailureHook(4, &v22);
          if ( !ProcAddress )
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
    ((void (__fastcall *)(__int64, DelayLoadInfo *))v14)(5, &v22);
  }
  DloadReleaseSectionWriteAccess(v13, v5, v4);
  return ProcAddress;
}

```

## disassembly

```asm
0x1800b2fc0  push    rbp
0x1800b2fc2  push    rbx
0x1800b2fc3  push    rsi
0x1800b2fc4  push    rdi
0x1800b2fc5  push    r12
0x1800b2fc7  push    r13
0x1800b2fc9  push    r14
0x1800b2fcb  push    r15
0x1800b2fcd  mov     rbp, rsp
0x1800b2fd0  sub     rsp, 78h
0x1800b2fd4  xor     eax, eax
0x1800b2fd6  mov     r12, rdx
0x1800b2fd9  mov     rsi, rcx
0x1800b2fdc  mov     dword ptr [rbp+var_58+4], eax
0x1800b2fdf  xor     edx, edx; Val
0x1800b2fe1  lea     rcx, [rbp+var_58]; void *
0x1800b2fe5  lea     r8d, [rax+44h]; Size
0x1800b2fe9  call    memset_0
0x1800b2fee  call    DloadAcquireSectionWriteAccess
0x1800b2ff3  mov     eax, [rsi+4]
0x1800b2ff6  lea     rdx, __ImageBase
0x1800b2ffd  mov     r14d, [rsi+8]
0x1800b3001  add     rax, rdx
0x1800b3004  mov     r15d, [rsi+14h]
0x1800b3008  add     r14, rdx
0x1800b300b  mov     ecx, [rsi+1Ch]
0x1800b300e  add     r15, rdx
0x1800b3011  mov     [rbp+var_58.szDll], rax
0x1800b3015  mov     eax, [rsi]
0x1800b3017  mov     dword ptr [rbp+Arguments], ecx
0x1800b301a  mov     [rbp+var_58.cb], 48h ; 'H'
0x1800b3021  mov     [rbp+var_58.pidd], rsi
0x1800b3025  mov     [rbp+var_58.ppfn], r12
0x1800b3029  mov     [rbp+var_58.dlp.fImportByName], 0
0x1800b3030  mov     qword ptr [rbp+var_58.dlp.8], 0
0x1800b3038  mov     [rbp+var_58.hmodCur], 0
0x1800b3040  mov     [rbp+var_58.pfnCur], 0
0x1800b3048  mov     [rbp+var_58.dwLastError], 0
0x1800b304f  test    al, 1
0x1800b3051  jnz     short loc_1800B307C
0x1800b3053  lea     rax, [rbp+var_58]
0x1800b3057  mov     [rbp+Arguments], rax
0x1800b305b  call    DloadReleaseSectionWriteAccess
0x1800b3060  xor     edx, edx; dwExceptionFlags
0x1800b3062  lea     r9, [rbp+Arguments]; lpArguments
0x1800b3066  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800b306b  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800b306f  call    cs:__imp_RaiseException
0x1800b3075  xor     eax, eax
0x1800b3077  jmp     loc_1800B32CB
0x1800b307c  mov     eax, [rsi+0Ch]
0x1800b307f  mov     rcx, r12
0x1800b3082  mov     rbx, [r14]
0x1800b3085  sub     rcx, rax
0x1800b3088  sub     rcx, rdx
0x1800b308b  sar     rcx, 3
0x1800b308f  mov     eax, ecx
0x1800b3091  mov     ecx, [rsi+10h]
0x1800b3094  lea     r13, ds:0[rax*8]
0x1800b309c  xor     eax, eax
0x1800b309e  add     rcx, r13
0x1800b30a1  cmp     [rcx+rdx], rax
0x1800b30a5  setnl   al
0x1800b30a8  mov     [rbp+var_58.dlp.fImportByName], eax
0x1800b30ab  test    eax, eax
0x1800b30ad  jz      short loc_1800B30C2
0x1800b30af  mov     eax, [rcx+rdx]
0x1800b30b2  lea     rdx, word_180000002
0x1800b30b9  add     rax, rdx
0x1800b30bc  mov     qword ptr [rbp+var_58.dlp.8], rax
0x1800b30c0  jmp     short loc_1800B30C9
0x1800b30c2  movzx   eax, word ptr [rcx+rdx]
0x1800b30c6  mov     dword ptr [rbp+var_58.dlp.8], eax
0x1800b30c9  mov     rax, cs:__pfnDliNotifyHook2
0x1800b30d0  xor     edi, edi
0x1800b30d2  test    rax, rax
0x1800b30d5  jz      short loc_1800B30F5
0x1800b30d7  lea     rdx, [rbp+var_58]
0x1800b30db  xor     ecx, ecx
0x1800b30dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b30e2  mov     rdi, rax
0x1800b30e5  test    rax, rax
0x1800b30e8  mov     rax, cs:__pfnDliNotifyHook2
0x1800b30ef  jnz     loc_1800B32A1
0x1800b30f5  test    rbx, rbx
0x1800b30f8  jnz     loc_1800B31DF
0x1800b30fe  test    rax, rax
0x1800b3101  jz      short loc_1800B3117
0x1800b3103  lea     rdx, [rbp+var_58]
0x1800b3107  lea     ecx, [rbx+1]
0x1800b310a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b310f  mov     rbx, rax
0x1800b3112  test    rax, rax
0x1800b3115  jnz     short loc_1800B3176
0x1800b3117  mov     rcx, [rbp+var_58.szDll]; lpLibFileName
0x1800b311b  xor     r8d, r8d; dwFlags
0x1800b311e  xor     edx, edx; hFile
0x1800b3120  call    cs:__imp_LoadLibraryExA
0x1800b3126  mov     rbx, rax
0x1800b3129  test    rax, rax
0x1800b312c  jnz     short loc_1800B3176
0x1800b312e  call    cs:__imp_GetLastError
0x1800b3134  lea     rdx, [rbp+var_58]; struct DelayLoadInfo *
0x1800b3138  mov     [rbp+var_58.dwLastError], eax
0x1800b313b  lea     ecx, [rbx+3]; unsigned int
0x1800b313e  call    ?SBE_DelayLoadFailureHook@@YAP6A_JXZIPEAUDelayLoadInfo@@@Z; SBE_DelayLoadFailureHook(uint,DelayLoadInfo *)
0x1800b3143  mov     rbx, rax
0x1800b3146  test    rax, rax
0x1800b3149  jnz     short loc_1800B3176
0x1800b314b  lea     rax, [rbp+var_58]
0x1800b314f  mov     [rbp+Arguments], rax
0x1800b3153  call    DloadReleaseSectionWriteAccess
0x1800b3158  lea     r9, [rbp+Arguments]; lpArguments
0x1800b315c  xor     edx, edx; dwExceptionFlags
0x1800b315e  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800b3163  lea     r8d, [rbx+1]; nNumberOfArguments
0x1800b3167  call    cs:__imp_RaiseException
0x1800b316d  mov     rax, [rbp+var_58.pfnCur]
0x1800b3171  jmp     loc_1800B32CB
0x1800b3176  xor     eax, eax
0x1800b3178  lock cmpxchg [r14], rbx
0x1800b317d  mov     r14, rax
0x1800b3180  jnz     short loc_1800B31C2
0x1800b3182  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b3186  jz      short loc_1800B31D8
0x1800b3188  cmp     dword ptr [rsi+18h], 0
0x1800b318c  jz      short loc_1800B31D8
0x1800b318e  call    cs:__imp_GetProcessHeap
0x1800b3194  mov     edx, 8; dwFlags
0x1800b3199  mov     rcx, rax; hHeap
0x1800b319c  lea     r8d, [rdx+8]; dwBytes
0x1800b31a0  call    cs:__imp_HeapAlloc
0x1800b31a6  test    rax, rax
0x1800b31a9  jz      short loc_1800B31D8
0x1800b31ab  mov     [rax+8], rsi
0x1800b31af  mov     rcx, cs:__puiHead
0x1800b31b6  mov     [rax], rcx
0x1800b31b9  mov     cs:__puiHead, rax
0x1800b31c0  jmp     short loc_1800B31D8
0x1800b31c2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b31c6  jz      short loc_1800B31D1
0x1800b31c8  mov     rcx, rbx; hLibModule
0x1800b31cb  call    cs:__imp_FreeLibrary
0x1800b31d1  cmp     rbx, r14
0x1800b31d4  cmovnz  rbx, r14
0x1800b31d8  mov     rax, cs:__pfnDliNotifyHook2
0x1800b31df  mov     [rbp+var_58.hmodCur], rbx
0x1800b31e3  test    rax, rax
0x1800b31e6  jz      short loc_1800B3200
0x1800b31e8  lea     rdx, [rbp+var_58]
0x1800b31ec  mov     ecx, 2
0x1800b31f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b31f6  mov     rdi, rax
0x1800b31f9  mov     rax, cs:__pfnDliNotifyHook2
0x1800b3200  test    rdi, rdi
0x1800b3203  jnz     loc_1800B329D
0x1800b3209  cmp     [rsi+14h], edi
0x1800b320c  jz      short loc_1800B3239
0x1800b320e  cmp     [rsi+1Ch], edi
0x1800b3211  jz      short loc_1800B3239
0x1800b3213  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800b3217  cmp     dword ptr [rcx+rbx], 4550h
0x1800b321e  jnz     short loc_1800B3239
0x1800b3220  mov     edx, dword ptr [rbp+Arguments]
0x1800b3223  cmp     [rcx+rbx+8], edx
0x1800b3227  jnz     short loc_1800B3239
0x1800b3229  cmp     rbx, [rcx+rbx+30h]
0x1800b322e  jnz     short loc_1800B3239
0x1800b3230  mov     rdi, [r15+r13]
0x1800b3234  test    rdi, rdi
0x1800b3237  jnz     short loc_1800B329D
0x1800b3239  mov     rdx, qword ptr [rbp+var_58.dlp.8]; lpProcName
0x1800b323d  mov     rcx, rbx; hModule
0x1800b3240  call    cs:__imp_GetProcAddress
0x1800b3246  mov     rdi, rax
0x1800b3249  test    rax, rax
0x1800b324c  jnz     short loc_1800B3296
0x1800b324e  call    cs:__imp_GetLastError
0x1800b3254  lea     rdx, [rbp+var_58]; struct DelayLoadInfo *
0x1800b3258  mov     [rbp+var_58.dwLastError], eax
0x1800b325b  lea     ecx, [rdi+4]; unsigned int
0x1800b325e  call    ?SBE_DelayLoadFailureHook@@YAP6A_JXZIPEAUDelayLoadInfo@@@Z; SBE_DelayLoadFailureHook(uint,DelayLoadInfo *)
0x1800b3263  mov     rdi, rax
0x1800b3266  test    rax, rax
0x1800b3269  jnz     short loc_1800B3296
0x1800b326b  lea     rax, [rbp+var_58]
0x1800b326f  mov     [rbp+Arguments], rax
0x1800b3273  call    DloadReleaseSectionWriteAccess
0x1800b3278  lea     r9, [rbp+Arguments]; lpArguments
0x1800b327c  xor     edx, edx; dwExceptionFlags
0x1800b327e  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800b3283  lea     r8d, [rdi+1]; nNumberOfArguments
0x1800b3287  call    cs:__imp_RaiseException
0x1800b328d  call    DloadAcquireSectionWriteAccess
0x1800b3292  mov     rdi, [rbp+var_58.pfnCur]
0x1800b3296  mov     rax, cs:__pfnDliNotifyHook2
0x1800b329d  mov     [r12], rdi
0x1800b32a1  test    rax, rax
0x1800b32a4  jz      short loc_1800B32C3
0x1800b32a6  lea     rdx, [rbp+var_58]
0x1800b32aa  mov     [rbp+var_58.dwLastError], 0
0x1800b32b1  mov     ecx, 5
0x1800b32b6  mov     [rbp+var_58.hmodCur], rbx
0x1800b32ba  mov     [rbp+var_58.pfnCur], rdi
0x1800b32be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b32c3  call    DloadReleaseSectionWriteAccess
0x1800b32c8  mov     rax, rdi
0x1800b32cb  add     rsp, 78h
0x1800b32cf  pop     r15
0x1800b32d1  pop     r14
0x1800b32d3  pop     r13
0x1800b32d5  pop     r12
0x1800b32d7  pop     rdi
0x1800b32d8  pop     rsi
0x1800b32d9  pop     rbx
0x1800b32da  pop     rbp
0x1800b32db  retn
```

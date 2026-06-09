# __delayLoadHelper2

- ea: `0x180047340`
- end: `0x18004763a`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180042153`
- `0x1800421f0`
- `0x18004228d`
- `0x180042318`
- `0x180047855`

## callees

- `0x180046df8`
- `0x180046eec`
- `0x180047290`
- `0x180047340`
- `0x180047a50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047502`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047502`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004756b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004756b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180047491`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180047491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004749f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004749f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047579`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800473ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800474e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800475bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800473ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800474e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800475bf`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile __int64 *v4; // r14
  char *v5; // rdx
  char *v6; // rcx
  char *v7; // r13
  DWORD grAttrs; // eax
  HMODULE Library; // rbx
  __int64 v11; // r12
  bool v12; // zf
  PfnDliHook v13; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  __int64 v15; // rax
  struct DelayLoadInfo v16; // [rsp+30h] [rbp-50h] BYREF
  ULONG_PTR Arguments; // [rsp+B0h] [rbp+30h] BYREF

  DloadAcquireSectionWriteAccess();
  v4 = (volatile __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  v5 = (char *)&_ImageBase + a1->rvaIAT;
  v6 = (char *)&_ImageBase + a1->rvaINT;
  v7 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v16.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = a1->dwTimeStamp;
  v16.cb = 72;
  v16.pidd = a1;
  v16.ppfn = a2;
  memset(&v16.dlp, 0, 36);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v16;
    DloadReleaseSectionWriteAccess();
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v4;
  v11 = (unsigned int)(((char *)a2 - v5) >> 3);
  v12 = *(__int64 *)&v6[8 * v11] < 0;
  v16.dlp.fImportByName = *(_QWORD *)&v6[8 * v11] >= 0LL;
  if ( v12 )
    v16.dlp.dwOrdinal = *(unsigned __int16 *)&v6[8 * v11];
  else
    v16.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)&v6[8 * v11];
  v13 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( _pfnDliNotifyHook2 )
  {
    ProcAddress = _pfnDliNotifyHook2(0, &v16);
    if ( ProcAddress )
      goto LABEL_33;
    v13 = _pfnDliNotifyHook2;
  }
  if ( !Library )
  {
    if ( !v13 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v13)(1, &v16)) == 0 )
    {
      Library = LoadLibraryExA(v16.szDll, 0, 0);
      if ( !Library )
      {
        v16.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (Library = (HMODULE)_pfnDliFailureHook2(3u, &v16)) == 0 )
        {
          Arguments = (ULONG_PTR)&v16;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007E, 0, 1u, &Arguments);
          return v16.pfnCur;
        }
      }
    }
    if ( (HMODULE)_InterlockedExchange64(v4, (__int64)Library) == Library )
      FreeLibrary(Library);
    v13 = _pfnDliNotifyHook2;
  }
  v16.hmodCur = Library;
  if ( v13 )
    ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v13)(2, &v16);
  if ( !ProcAddress )
  {
    if ( !a1->rvaBoundIAT
      || !a1->dwTimeStamp
      || (v15 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v15) != 17744)
      || *(_DWORD *)((char *)Library + v15 + 8) != (_DWORD)Arguments
      || Library != *(HMODULE *)((char *)Library + v15 + 48)
      || (ProcAddress = *(INT_PTR (__stdcall **)())&v7[8 * v11]) == 0 )
    {
      ProcAddress = GetProcAddress(Library, v16.dlp.szProcName);
      if ( !ProcAddress )
      {
        v16.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (ProcAddress = _pfnDliFailureHook2(4u, &v16)) == 0 )
        {
          Arguments = (ULONG_PTR)&v16;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007F, 0, 1u, &Arguments);
          DloadAcquireSectionWriteAccess();
          ProcAddress = v16.pfnCur;
        }
      }
    }
  }
  GuardedWrite____delayLoadHelper2_::_2_::_lambda_1___(a2, 8u);
LABEL_33:
  if ( _pfnDliNotifyHook2 )
  {
    v16.dwLastError = 0;
    v16.hmodCur = Library;
    v16.pfnCur = ProcAddress;
    _pfnDliNotifyHook2(5u, &v16);
  }
  DloadReleaseSectionWriteAccess();
  return ProcAddress;
}

```

## disassembly

```asm
0x180047340  mov     [rsp-28h+arg_8], rbx
0x180047345  mov     [rsp-28h+arg_10], rsi
0x18004734a  mov     [rsp-28h+arg_18], rdi
0x18004734f  push    rbp
0x180047350  push    r12
0x180047352  push    r13
0x180047354  push    r14
0x180047356  push    r15
0x180047358  mov     rbp, rsp
0x18004735b  sub     rsp, 80h
0x180047362  mov     r15, rdx
0x180047365  mov     rsi, rcx
0x180047368  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18004736d  mov     eax, [rsi+4]
0x180047370  lea     r8, __ImageBase
0x180047377  mov     r14d, [rsi+8]
0x18004737b  add     rax, r8
0x18004737e  mov     edx, [rsi+0Ch]
0x180047381  add     r14, r8
0x180047384  mov     ecx, [rsi+10h]
0x180047387  add     rdx, r8
0x18004738a  mov     r13d, [rsi+14h]
0x18004738e  add     rcx, r8
0x180047391  add     r13, r8
0x180047394  mov     [rbp+lpLibFileName], rax
0x180047398  mov     eax, [rsi]
0x18004739a  xorps   xmm0, xmm0
0x18004739d  mov     r8d, [rsi+1Ch]
0x1800473a1  mov     dword ptr [rbp+Arguments], r8d
0x1800473a5  mov     [rbp+var_50], 48h ; 'H'
0x1800473ac  mov     [rbp+var_48], rsi
0x1800473b0  mov     [rbp+var_40], r15
0x1800473b4  mov     [rbp+var_20], 0
0x1800473bc  mov     [rbp+var_18], 0
0x1800473c4  mov     [rbp+var_10], 0
0x1800473cb  movups  xmmword ptr [rbp+lpProcName], xmm0
0x1800473cf  test    al, 1
0x1800473d1  jnz     short loc_1800473FC
0x1800473d3  lea     rax, [rbp+var_50]
0x1800473d7  mov     [rbp+Arguments], rax
0x1800473db  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1800473e0  xor     edx, edx; dwExceptionFlags
0x1800473e2  lea     r9, [rbp+Arguments]; lpArguments
0x1800473e6  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800473eb  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800473ef  call    cs:__imp_RaiseException
0x1800473f5  xor     eax, eax
0x1800473f7  jmp     loc_180047619
0x1800473fc  mov     rbx, [r14]
0x1800473ff  mov     r12, r15
0x180047402  sub     r12, rdx
0x180047405  sar     r12, 3
0x180047409  mov     r12d, r12d
0x18004740c  mov     rax, [rcx+r12*8]
0x180047410  shr     rax, 3Fh
0x180047414  xor     eax, 1
0x180047417  mov     dword ptr [rbp+lpProcName], eax
0x18004741a  jz      short loc_180047430
0x18004741c  mov     eax, [rcx+r12*8]
0x180047420  lea     rcx, word_180000002
0x180047427  add     rax, rcx
0x18004742a  mov     [rbp+lpProcName+8], rax
0x18004742e  jmp     short loc_180047438
0x180047430  movzx   eax, word ptr [rcx+r12*8]
0x180047435  mov     dword ptr [rbp+lpProcName+8], eax
0x180047438  mov     rax, cs:__pfnDliNotifyHook2
0x18004743f  xor     edi, edi
0x180047441  test    rax, rax
0x180047444  jz      short loc_180047465
0x180047446  lea     rdx, [rbp+var_50]
0x18004744a  xor     ecx, ecx
0x18004744c  call    cs:__guard_dispatch_icall_fptr
0x180047452  mov     rdi, rax
0x180047455  test    rax, rax
0x180047458  jnz     loc_1800475E7
0x18004745e  mov     rax, cs:__pfnDliNotifyHook2
0x180047465  test    rbx, rbx
0x180047468  jnz     loc_18004750F
0x18004746e  test    rax, rax
0x180047471  jz      short loc_180047488
0x180047473  lea     rdx, [rbp+var_50]
0x180047477  lea     ecx, [rbx+1]
0x18004747a  call    cs:__guard_dispatch_icall_fptr
0x180047480  mov     rbx, rax
0x180047483  test    rax, rax
0x180047486  jnz     short loc_1800474F4
0x180047488  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18004748c  xor     r8d, r8d; dwFlags
0x18004748f  xor     edx, edx; hFile
0x180047491  call    cs:__imp_LoadLibraryExA
0x180047497  mov     rbx, rax
0x18004749a  test    rax, rax
0x18004749d  jnz     short loc_1800474F4
0x18004749f  call    cs:__imp_GetLastError
0x1800474a5  mov     [rbp+var_10], eax
0x1800474a8  mov     rax, cs:__pfnDliFailureHook2
0x1800474af  test    rax, rax
0x1800474b2  jz      short loc_1800474C9
0x1800474b4  lea     rdx, [rbp+var_50]
0x1800474b8  lea     ecx, [rbx+3]
0x1800474bb  call    cs:__guard_dispatch_icall_fptr
0x1800474c1  mov     rbx, rax
0x1800474c4  test    rax, rax
0x1800474c7  jnz     short loc_1800474F4
0x1800474c9  lea     rax, [rbp+var_50]
0x1800474cd  mov     [rbp+Arguments], rax
0x1800474d1  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1800474d6  xor     edx, edx; dwExceptionFlags
0x1800474d8  lea     r9, [rbp+Arguments]; lpArguments
0x1800474dc  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800474e1  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800474e5  call    cs:__imp_RaiseException
0x1800474eb  mov     rax, [rbp+var_18]
0x1800474ef  jmp     loc_180047619
0x1800474f4  mov     rax, rbx
0x1800474f7  xchg    rax, [r14]
0x1800474fa  cmp     rax, rbx
0x1800474fd  jnz     short loc_180047508
0x1800474ff  mov     rcx, rbx; hLibModule
0x180047502  call    cs:__imp_FreeLibrary
0x180047508  mov     rax, cs:__pfnDliNotifyHook2
0x18004750f  mov     [rbp+var_20], rbx
0x180047513  test    rax, rax
0x180047516  jz      short loc_18004752A
0x180047518  lea     rdx, [rbp+var_50]
0x18004751c  mov     ecx, 2
0x180047521  call    cs:__guard_dispatch_icall_fptr
0x180047527  mov     rdi, rax
0x18004752a  test    rdi, rdi
0x18004752d  jnz     loc_1800475CE
0x180047533  cmp     [rsi+14h], edi
0x180047536  jz      short loc_180047564
0x180047538  cmp     [rsi+1Ch], edi
0x18004753b  jz      short loc_180047564
0x18004753d  movsxd  rax, dword ptr [rbx+3Ch]
0x180047541  cmp     dword ptr [rax+rbx], 4550h
0x180047548  jnz     short loc_180047564
0x18004754a  mov     ecx, dword ptr [rbp+Arguments]
0x18004754d  cmp     [rax+rbx+8], ecx
0x180047551  jnz     short loc_180047564
0x180047553  cmp     rbx, [rax+rbx+30h]
0x180047558  jnz     short loc_180047564
0x18004755a  mov     rdi, [r13+r12*8+0]
0x18004755f  test    rdi, rdi
0x180047562  jnz     short loc_1800475CE
0x180047564  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x180047568  mov     rcx, rbx; hModule
0x18004756b  call    cs:__imp_GetProcAddress
0x180047571  mov     rdi, rax
0x180047574  test    rax, rax
0x180047577  jnz     short loc_1800475CE
0x180047579  call    cs:__imp_GetLastError
0x18004757f  mov     [rbp+var_10], eax
0x180047582  mov     rax, cs:__pfnDliFailureHook2
0x180047589  test    rax, rax
0x18004758c  jz      short loc_1800475A3
0x18004758e  lea     rdx, [rbp+var_50]
0x180047592  lea     ecx, [rdi+4]
0x180047595  call    cs:__guard_dispatch_icall_fptr
0x18004759b  mov     rdi, rax
0x18004759e  test    rax, rax
0x1800475a1  jnz     short loc_1800475CE
0x1800475a3  lea     rax, [rbp+var_50]
0x1800475a7  mov     [rbp+Arguments], rax
0x1800475ab  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1800475b0  xor     edx, edx; dwExceptionFlags
0x1800475b2  lea     r9, [rbp+Arguments]; lpArguments
0x1800475b6  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800475bb  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800475bf  call    cs:__imp_RaiseException
0x1800475c5  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1800475ca  mov     rdi, [rbp+var_18]
0x1800475ce  lea     r8, [rbp+var_60]
0x1800475d2  mov     [rbp+var_60], r15
0x1800475d6  mov     edx, 8; dwSize
0x1800475db  mov     [rbp+var_58], rdi
0x1800475df  mov     rcx, r15; lpAddress
0x1800475e2  call    GuardedWrite____delayLoadHelper2____2____lambda_1___
0x1800475e7  mov     rax, cs:__pfnDliNotifyHook2
0x1800475ee  test    rax, rax
0x1800475f1  jz      short loc_180047611
0x1800475f3  lea     rdx, [rbp+var_50]
0x1800475f7  mov     [rbp+var_10], 0
0x1800475fe  mov     ecx, 5
0x180047603  mov     [rbp+var_20], rbx
0x180047607  mov     [rbp+var_18], rdi
0x18004760b  call    cs:__guard_dispatch_icall_fptr
0x180047611  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180047616  mov     rax, rdi
0x180047619  lea     r11, [rsp+80h+var_s0]
0x180047621  mov     rbx, [r11+38h]
0x180047625  mov     rsi, [r11+40h]
0x180047629  mov     rdi, [r11+48h]
0x18004762d  mov     rsp, r11
0x180047630  pop     r15
0x180047632  pop     r14
0x180047634  pop     r13
0x180047636  pop     r12
0x180047638  pop     rbp
0x180047639  retn
```

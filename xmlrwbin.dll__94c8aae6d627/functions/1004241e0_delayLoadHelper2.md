# __delayLoadHelper2

- ea: `0x1004241e0`
- end: `0x1004244b2`
- name: `__delayLoadHelper2`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x100423d49`

## callees

- `0x100423e10`
- `0x100424138`
- `0x1004241e0`
- `0x100424580`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100424332`
- `KERNEL32!GetLastError` at `0x10042440c`
- `KERNEL32!GetLastError` at `0x100424332`
- `KERNEL32!GetLastError` at `0x10042440c`
- `KERNEL32!FreeLibrary` at `0x100424395`
- `KERNEL32!FreeLibrary` at `0x100424395`
- `KERNEL32!GetProcAddress` at `0x1004243fe`
- `KERNEL32!GetProcAddress` at `0x1004243fe`
- `KERNEL32!RaiseException` at `0x100424282`
- `KERNEL32!RaiseException` at `0x100424378`
- `KERNEL32!RaiseException` at `0x100424452`
- `KERNEL32!RaiseException` at `0x100424282`
- `KERNEL32!RaiseException` at `0x100424378`
- `KERNEL32!RaiseException` at `0x100424452`
- `KERNEL32!LoadLibraryExA` at `0x100424324`
- `KERNEL32!LoadLibraryExA` at `0x100424324`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile __int64 *v4; // r14
  char *v5; // r9
  char *v6; // rcx
  char *v7; // r13
  DWORD dwTimeStamp; // edx
  DWORD grAttrs; // eax
  HMODULE Library; // rdi
  __int64 v12; // r15
  bool v13; // zf
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rbx
  __int64 v16; // rax
  struct DelayLoadInfo v17; // [rsp+20h] [rbp-50h] BYREF
  ULONG_PTR Arguments; // [rsp+A0h] [rbp+30h] BYREF

  DloadAcquireSectionWriteAccess();
  v4 = (volatile __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  v5 = (char *)&_ImageBase + a1->rvaIAT;
  v6 = (char *)&_ImageBase + a1->rvaINT;
  v7 = (char *)&_ImageBase + a1->rvaBoundIAT;
  dwTimeStamp = a1->dwTimeStamp;
  v17.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v17.cb = 72;
  v17.pidd = a1;
  v17.ppfn = a2;
  memset(&v17.dlp, 0, 36);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v17;
    DloadReleaseSectionWriteAccess();
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v4;
  v12 = (unsigned int)(((char *)a2 - v5) >> 3);
  v13 = *(__int64 *)&v6[8 * v12] < 0;
  v17.dlp.fImportByName = *(_QWORD *)&v6[8 * v12] >= 0LL;
  if ( v13 )
    v17.dlp.dwOrdinal = *(unsigned __int16 *)&v6[8 * v12];
  else
    v17.dlp.szProcName = (char *)&word_100400002 + *(unsigned int *)&v6[8 * v12];
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( _pfnDliNotifyHook2 )
  {
    ProcAddress = _pfnDliNotifyHook2(0, &v17);
    if ( ProcAddress )
      goto LABEL_33;
    v14 = _pfnDliNotifyHook2;
  }
  if ( !Library )
  {
    if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(1, &v17)) == 0 )
    {
      Library = LoadLibraryExA(v17.szDll, 0, 0);
      if ( !Library )
      {
        v17.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (Library = (HMODULE)_pfnDliFailureHook2(3u, &v17)) == 0 )
        {
          Arguments = (ULONG_PTR)&v17;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007E, 0, 1u, &Arguments);
          return v17.pfnCur;
        }
      }
    }
    if ( (HMODULE)_InterlockedExchange64(v4, (__int64)Library) == Library )
      FreeLibrary(Library);
    v14 = _pfnDliNotifyHook2;
  }
  v17.hmodCur = Library;
  if ( v14 )
    ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(2, &v17);
  if ( !ProcAddress )
  {
    if ( !a1->rvaBoundIAT
      || !a1->dwTimeStamp
      || (v16 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v16) != 17744)
      || *(_DWORD *)((char *)Library + v16 + 8) != (_DWORD)Arguments
      || Library != *(HMODULE *)((char *)Library + v16 + 48)
      || (ProcAddress = *(INT_PTR (__stdcall **)())&v7[8 * v12]) == 0 )
    {
      ProcAddress = GetProcAddress(Library, v17.dlp.szProcName);
      if ( !ProcAddress )
      {
        v17.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (ProcAddress = _pfnDliFailureHook2(4u, &v17)) == 0 )
        {
          Arguments = (ULONG_PTR)&v17;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007F, 0, 1u, &Arguments);
          DloadAcquireSectionWriteAccess();
          ProcAddress = v17.pfnCur;
        }
      }
    }
  }
  *a2 = ProcAddress;
LABEL_33:
  if ( _pfnDliNotifyHook2 )
  {
    v17.dwLastError = 0;
    v17.hmodCur = Library;
    v17.pfnCur = ProcAddress;
    _pfnDliNotifyHook2(5u, &v17);
  }
  DloadReleaseSectionWriteAccess();
  return ProcAddress;
}

```

## disassembly

```asm
0x1004241e0  mov     [rsp-28h+arg_8], rbx
0x1004241e5  mov     [rsp-28h+arg_10], rsi
0x1004241ea  mov     [rsp-28h+arg_18], rdi
0x1004241ef  push    rbp
0x1004241f0  push    r12
0x1004241f2  push    r13
0x1004241f4  push    r14
0x1004241f6  push    r15
0x1004241f8  mov     rbp, rsp
0x1004241fb  sub     rsp, 70h
0x1004241ff  mov     r12, rdx
0x100424202  mov     rsi, rcx
0x100424205  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x10042420a  mov     eax, [rsi+4]
0x10042420d  lea     rdx, __ImageBase
0x100424214  mov     r14d, [rsi+8]
0x100424218  add     rax, rdx
0x10042421b  mov     r9d, [rsi+0Ch]
0x10042421f  add     r14, rdx
0x100424222  mov     ecx, [rsi+10h]
0x100424225  add     r9, rdx
0x100424228  mov     r13d, [rsi+14h]
0x10042422c  add     rcx, rdx
0x10042422f  and     [rbp+var_20], 0
0x100424234  add     r13, rdx
0x100424237  and     [rbp+var_18], 0
0x10042423c  xorps   xmm0, xmm0
0x10042423f  and     [rbp+var_10], 0
0x100424243  mov     edx, [rsi+1Ch]
0x100424246  mov     [rbp+lpLibFileName], rax
0x10042424a  mov     eax, [rsi]
0x10042424c  mov     dword ptr [rbp+Arguments], edx
0x10042424f  mov     [rbp+var_50], 48h ; 'H'
0x100424256  mov     [rbp+var_48], rsi
0x10042425a  mov     [rbp+var_40], r12
0x10042425e  movups  xmmword ptr [rbp+lpProcName], xmm0
0x100424262  test    al, 1
0x100424264  jnz     short loc_10042428F
0x100424266  lea     rax, [rbp+var_50]
0x10042426a  mov     [rbp+Arguments], rax
0x10042426e  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100424273  xor     edx, edx; dwExceptionFlags
0x100424275  lea     r9, [rbp+Arguments]; lpArguments
0x100424279  mov     ecx, 0C06D0057h; dwExceptionCode
0x10042427e  lea     r8d, [rdx+1]; nNumberOfArguments
0x100424282  call    cs:__imp_RaiseException
0x100424288  xor     eax, eax
0x10042428a  jmp     loc_100424494
0x10042428f  mov     rdi, [r14]
0x100424292  mov     r15, r12
0x100424295  sub     r15, r9
0x100424298  sar     r15, 3
0x10042429c  mov     r15d, r15d
0x10042429f  mov     rax, [rcx+r15*8]
0x1004242a3  shr     rax, 3Fh
0x1004242a7  xor     eax, 1
0x1004242aa  mov     dword ptr [rbp+lpProcName], eax
0x1004242ad  jz      short loc_1004242C3
0x1004242af  mov     eax, [rcx+r15*8]
0x1004242b3  lea     rcx, word_100400002
0x1004242ba  add     rax, rcx
0x1004242bd  mov     [rbp+lpProcName+8], rax
0x1004242c1  jmp     short loc_1004242CB
0x1004242c3  movzx   eax, word ptr [rcx+r15*8]
0x1004242c8  mov     dword ptr [rbp+lpProcName+8], eax
0x1004242cb  mov     rax, cs:__pfnDliNotifyHook2
0x1004242d2  xor     ebx, ebx
0x1004242d4  test    rax, rax
0x1004242d7  jz      short loc_1004242F8
0x1004242d9  lea     rdx, [rbp+var_50]
0x1004242dd  xor     ecx, ecx
0x1004242df  call    cs:__guard_dispatch_icall_fptr
0x1004242e5  mov     rbx, rax
0x1004242e8  test    rax, rax
0x1004242eb  jnz     loc_100424465
0x1004242f1  mov     rax, cs:__pfnDliNotifyHook2
0x1004242f8  test    rdi, rdi
0x1004242fb  jnz     loc_1004243A2
0x100424301  test    rax, rax
0x100424304  jz      short loc_10042431B
0x100424306  lea     rdx, [rbp+var_50]
0x10042430a  lea     ecx, [rdi+1]
0x10042430d  call    cs:__guard_dispatch_icall_fptr
0x100424313  mov     rdi, rax
0x100424316  test    rax, rax
0x100424319  jnz     short loc_100424387
0x10042431b  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x10042431f  xor     r8d, r8d; dwFlags
0x100424322  xor     edx, edx; hFile
0x100424324  call    cs:__imp_LoadLibraryExA
0x10042432a  mov     rdi, rax
0x10042432d  test    rax, rax
0x100424330  jnz     short loc_100424387
0x100424332  call    cs:__imp_GetLastError
0x100424338  mov     [rbp+var_10], eax
0x10042433b  mov     rax, cs:__pfnDliFailureHook2
0x100424342  test    rax, rax
0x100424345  jz      short loc_10042435C
0x100424347  lea     rdx, [rbp+var_50]
0x10042434b  lea     ecx, [rdi+3]
0x10042434e  call    cs:__guard_dispatch_icall_fptr
0x100424354  mov     rdi, rax
0x100424357  test    rax, rax
0x10042435a  jnz     short loc_100424387
0x10042435c  lea     rax, [rbp+var_50]
0x100424360  mov     [rbp+Arguments], rax
0x100424364  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100424369  xor     edx, edx; dwExceptionFlags
0x10042436b  lea     r9, [rbp+Arguments]; lpArguments
0x10042436f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x100424374  lea     r8d, [rdx+1]; nNumberOfArguments
0x100424378  call    cs:__imp_RaiseException
0x10042437e  mov     rax, [rbp+var_18]
0x100424382  jmp     loc_100424494
0x100424387  mov     rax, rdi
0x10042438a  xchg    rax, [r14]
0x10042438d  cmp     rax, rdi
0x100424390  jnz     short loc_10042439B
0x100424392  mov     rcx, rdi; hLibModule
0x100424395  call    cs:__imp_FreeLibrary
0x10042439b  mov     rax, cs:__pfnDliNotifyHook2
0x1004243a2  mov     [rbp+var_20], rdi
0x1004243a6  test    rax, rax
0x1004243a9  jz      short loc_1004243BD
0x1004243ab  lea     rdx, [rbp+var_50]
0x1004243af  mov     ecx, 2
0x1004243b4  call    cs:__guard_dispatch_icall_fptr
0x1004243ba  mov     rbx, rax
0x1004243bd  test    rbx, rbx
0x1004243c0  jnz     loc_100424461
0x1004243c6  cmp     [rsi+14h], ebx
0x1004243c9  jz      short loc_1004243F7
0x1004243cb  cmp     [rsi+1Ch], ebx
0x1004243ce  jz      short loc_1004243F7
0x1004243d0  movsxd  rax, dword ptr [rdi+3Ch]
0x1004243d4  cmp     dword ptr [rax+rdi], 4550h
0x1004243db  jnz     short loc_1004243F7
0x1004243dd  mov     ecx, dword ptr [rbp+Arguments]
0x1004243e0  cmp     [rax+rdi+8], ecx
0x1004243e4  jnz     short loc_1004243F7
0x1004243e6  cmp     rdi, [rax+rdi+30h]
0x1004243eb  jnz     short loc_1004243F7
0x1004243ed  mov     rbx, [r13+r15*8+0]
0x1004243f2  test    rbx, rbx
0x1004243f5  jnz     short loc_100424461
0x1004243f7  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x1004243fb  mov     rcx, rdi; hModule
0x1004243fe  call    cs:__imp_GetProcAddress
0x100424404  mov     rbx, rax
0x100424407  test    rax, rax
0x10042440a  jnz     short loc_100424461
0x10042440c  call    cs:__imp_GetLastError
0x100424412  mov     [rbp+var_10], eax
0x100424415  mov     rax, cs:__pfnDliFailureHook2
0x10042441c  test    rax, rax
0x10042441f  jz      short loc_100424436
0x100424421  lea     rdx, [rbp+var_50]
0x100424425  lea     ecx, [rbx+4]
0x100424428  call    cs:__guard_dispatch_icall_fptr
0x10042442e  mov     rbx, rax
0x100424431  test    rax, rax
0x100424434  jnz     short loc_100424461
0x100424436  lea     rax, [rbp+var_50]
0x10042443a  mov     [rbp+Arguments], rax
0x10042443e  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100424443  xor     edx, edx; dwExceptionFlags
0x100424445  lea     r9, [rbp+Arguments]; lpArguments
0x100424449  mov     ecx, 0C06D007Fh; dwExceptionCode
0x10042444e  lea     r8d, [rdx+1]; nNumberOfArguments
0x100424452  call    cs:__imp_RaiseException
0x100424458  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x10042445d  mov     rbx, [rbp+var_18]
0x100424461  mov     [r12], rbx
0x100424465  mov     rax, cs:__pfnDliNotifyHook2
0x10042446c  test    rax, rax
0x10042446f  jz      short loc_10042448C
0x100424471  and     [rbp+var_10], 0
0x100424475  lea     rdx, [rbp+var_50]
0x100424479  mov     ecx, 5
0x10042447e  mov     [rbp+var_20], rdi
0x100424482  mov     [rbp+var_18], rbx
0x100424486  call    cs:__guard_dispatch_icall_fptr
0x10042448c  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100424491  mov     rax, rbx
0x100424494  lea     r11, [rsp+70h+var_s0]
0x100424499  mov     rbx, [r11+38h]
0x10042449d  mov     rsi, [r11+40h]
0x1004244a1  mov     rdi, [r11+48h]
0x1004244a5  mov     rsp, r11
0x1004244a8  pop     r15
0x1004244aa  pop     r14
0x1004244ac  pop     r13
0x1004244ae  pop     r12
0x1004244b0  pop     rbp
0x1004244b1  retn
```

# __delayLoadHelper2

- ea: `0x10045149c`
- end: `0x10045176e`
- name: `__delayLoadHelper2`
- size: `722`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x100450f8e`
- `0x100451041`
- `0x100451a00`
- `0x100451a8f`
- `0x100451cd0`
- `0x100451d95`
- `0x100451e41`
- `0x100451f72`
- `0x1004520ac`
- `0x10045213b`
- `0x1004522bc`
- `0x100452447`

## callees

- `0x100402f10`
- `0x1004510d4`
- `0x100451400`
- `0x10045149c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1004516ba`
- `KERNEL32!GetProcAddress` at `0x1004516ba`
- `KERNEL32!FreeLibrary` at `0x100451651`
- `KERNEL32!FreeLibrary` at `0x100451651`
- `KERNEL32!RaiseException` at `0x10045153e`
- `KERNEL32!RaiseException` at `0x100451634`
- `KERNEL32!RaiseException` at `0x10045170e`
- `KERNEL32!RaiseException` at `0x10045153e`
- `KERNEL32!RaiseException` at `0x100451634`
- `KERNEL32!RaiseException` at `0x10045170e`
- `KERNEL32!GetLastError` at `0x1004515ee`
- `KERNEL32!GetLastError` at `0x1004516c8`
- `KERNEL32!GetLastError` at `0x1004515ee`
- `KERNEL32!GetLastError` at `0x1004516c8`
- `KERNEL32!LoadLibraryExA` at `0x1004515e0`
- `KERNEL32!LoadLibraryExA` at `0x1004515e0`

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
  v4 = (volatile __int64 *)((char *)&CTypeInfo::tiBit + a1->rvaHmod);
  v5 = (char *)&CTypeInfo::tiBit + a1->rvaIAT;
  v6 = (char *)&CTypeInfo::tiBit + a1->rvaINT;
  v7 = (char *)&CTypeInfo::tiBit + a1->rvaBoundIAT;
  dwTimeStamp = a1->dwTimeStamp;
  v17.szDll = (char *)&CTypeInfo::tiBit + a1->rvaDLLName;
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
0x10045149c  mov     [rsp-28h+arg_8], rbx
0x1004514a1  mov     [rsp-28h+arg_10], rsi
0x1004514a6  mov     [rsp-28h+arg_18], rdi
0x1004514ab  push    rbp
0x1004514ac  push    r12
0x1004514ae  push    r13
0x1004514b0  push    r14
0x1004514b2  push    r15
0x1004514b4  mov     rbp, rsp
0x1004514b7  sub     rsp, 70h
0x1004514bb  mov     r12, rdx
0x1004514be  mov     rsi, rcx
0x1004514c1  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1004514c6  mov     eax, [rsi+4]
0x1004514c9  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004514d0  mov     r14d, [rsi+8]
0x1004514d4  add     rax, rdx
0x1004514d7  mov     r9d, [rsi+0Ch]
0x1004514db  add     r14, rdx
0x1004514de  mov     ecx, [rsi+10h]
0x1004514e1  add     r9, rdx
0x1004514e4  mov     r13d, [rsi+14h]
0x1004514e8  add     rcx, rdx
0x1004514eb  and     [rbp+var_20], 0
0x1004514f0  add     r13, rdx
0x1004514f3  and     [rbp+var_18], 0
0x1004514f8  xorps   xmm0, xmm0
0x1004514fb  and     [rbp+var_10], 0
0x1004514ff  mov     edx, [rsi+1Ch]
0x100451502  mov     [rbp+lpLibFileName], rax
0x100451506  mov     eax, [rsi]
0x100451508  mov     dword ptr [rbp+Arguments], edx
0x10045150b  mov     [rbp+var_50], 48h ; 'H'
0x100451512  mov     [rbp+var_48], rsi
0x100451516  mov     [rbp+var_40], r12
0x10045151a  movups  xmmword ptr [rbp+lpProcName], xmm0
0x10045151e  test    al, 1
0x100451520  jnz     short loc_10045154B
0x100451522  lea     rax, [rbp+var_50]
0x100451526  mov     [rbp+Arguments], rax
0x10045152a  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x10045152f  xor     edx, edx; dwExceptionFlags
0x100451531  lea     r9, [rbp+Arguments]; lpArguments
0x100451535  mov     ecx, 0C06D0057h; dwExceptionCode
0x10045153a  lea     r8d, [rdx+1]; nNumberOfArguments
0x10045153e  call    cs:__imp_RaiseException
0x100451544  xor     eax, eax
0x100451546  jmp     loc_100451750
0x10045154b  mov     rdi, [r14]
0x10045154e  mov     r15, r12
0x100451551  sub     r15, r9
0x100451554  sar     r15, 3
0x100451558  mov     r15d, r15d
0x10045155b  mov     rax, [rcx+r15*8]
0x10045155f  shr     rax, 3Fh
0x100451563  xor     eax, 1
0x100451566  mov     dword ptr [rbp+lpProcName], eax
0x100451569  jz      short loc_10045157F
0x10045156b  mov     eax, [rcx+r15*8]
0x10045156f  lea     rcx, word_100400002
0x100451576  add     rax, rcx
0x100451579  mov     [rbp+lpProcName+8], rax
0x10045157d  jmp     short loc_100451587
0x10045157f  movzx   eax, word ptr [rcx+r15*8]
0x100451584  mov     dword ptr [rbp+lpProcName+8], eax
0x100451587  mov     rax, cs:__pfnDliNotifyHook2
0x10045158e  xor     ebx, ebx
0x100451590  test    rax, rax
0x100451593  jz      short loc_1004515B4
0x100451595  lea     rdx, [rbp+var_50]
0x100451599  xor     ecx, ecx
0x10045159b  call    cs:__guard_dispatch_icall_fptr
0x1004515a1  mov     rbx, rax
0x1004515a4  test    rax, rax
0x1004515a7  jnz     loc_100451721
0x1004515ad  mov     rax, cs:__pfnDliNotifyHook2
0x1004515b4  test    rdi, rdi
0x1004515b7  jnz     loc_10045165E
0x1004515bd  test    rax, rax
0x1004515c0  jz      short loc_1004515D7
0x1004515c2  lea     rdx, [rbp+var_50]
0x1004515c6  lea     ecx, [rdi+1]
0x1004515c9  call    cs:__guard_dispatch_icall_fptr
0x1004515cf  mov     rdi, rax
0x1004515d2  test    rax, rax
0x1004515d5  jnz     short loc_100451643
0x1004515d7  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1004515db  xor     r8d, r8d; dwFlags
0x1004515de  xor     edx, edx; hFile
0x1004515e0  call    cs:__imp_LoadLibraryExA
0x1004515e6  mov     rdi, rax
0x1004515e9  test    rax, rax
0x1004515ec  jnz     short loc_100451643
0x1004515ee  call    cs:__imp_GetLastError
0x1004515f4  mov     [rbp+var_10], eax
0x1004515f7  mov     rax, cs:__pfnDliFailureHook2
0x1004515fe  test    rax, rax
0x100451601  jz      short loc_100451618
0x100451603  lea     rdx, [rbp+var_50]
0x100451607  lea     ecx, [rdi+3]
0x10045160a  call    cs:__guard_dispatch_icall_fptr
0x100451610  mov     rdi, rax
0x100451613  test    rax, rax
0x100451616  jnz     short loc_100451643
0x100451618  lea     rax, [rbp+var_50]
0x10045161c  mov     [rbp+Arguments], rax
0x100451620  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100451625  xor     edx, edx; dwExceptionFlags
0x100451627  lea     r9, [rbp+Arguments]; lpArguments
0x10045162b  mov     ecx, 0C06D007Eh; dwExceptionCode
0x100451630  lea     r8d, [rdx+1]; nNumberOfArguments
0x100451634  call    cs:__imp_RaiseException
0x10045163a  mov     rax, [rbp+var_18]
0x10045163e  jmp     loc_100451750
0x100451643  mov     rax, rdi
0x100451646  xchg    rax, [r14]
0x100451649  cmp     rax, rdi
0x10045164c  jnz     short loc_100451657
0x10045164e  mov     rcx, rdi; hLibModule
0x100451651  call    cs:__imp_FreeLibrary
0x100451657  mov     rax, cs:__pfnDliNotifyHook2
0x10045165e  mov     [rbp+var_20], rdi
0x100451662  test    rax, rax
0x100451665  jz      short loc_100451679
0x100451667  lea     rdx, [rbp+var_50]
0x10045166b  mov     ecx, 2
0x100451670  call    cs:__guard_dispatch_icall_fptr
0x100451676  mov     rbx, rax
0x100451679  test    rbx, rbx
0x10045167c  jnz     loc_10045171D
0x100451682  cmp     [rsi+14h], ebx
0x100451685  jz      short loc_1004516B3
0x100451687  cmp     [rsi+1Ch], ebx
0x10045168a  jz      short loc_1004516B3
0x10045168c  movsxd  rax, dword ptr [rdi+3Ch]
0x100451690  cmp     dword ptr [rax+rdi], 4550h
0x100451697  jnz     short loc_1004516B3
0x100451699  mov     ecx, dword ptr [rbp+Arguments]
0x10045169c  cmp     [rax+rdi+8], ecx
0x1004516a0  jnz     short loc_1004516B3
0x1004516a2  cmp     rdi, [rax+rdi+30h]
0x1004516a7  jnz     short loc_1004516B3
0x1004516a9  mov     rbx, [r13+r15*8+0]
0x1004516ae  test    rbx, rbx
0x1004516b1  jnz     short loc_10045171D
0x1004516b3  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x1004516b7  mov     rcx, rdi; hModule
0x1004516ba  call    cs:__imp_GetProcAddress
0x1004516c0  mov     rbx, rax
0x1004516c3  test    rax, rax
0x1004516c6  jnz     short loc_10045171D
0x1004516c8  call    cs:__imp_GetLastError
0x1004516ce  mov     [rbp+var_10], eax
0x1004516d1  mov     rax, cs:__pfnDliFailureHook2
0x1004516d8  test    rax, rax
0x1004516db  jz      short loc_1004516F2
0x1004516dd  lea     rdx, [rbp+var_50]
0x1004516e1  lea     ecx, [rbx+4]
0x1004516e4  call    cs:__guard_dispatch_icall_fptr
0x1004516ea  mov     rbx, rax
0x1004516ed  test    rax, rax
0x1004516f0  jnz     short loc_10045171D
0x1004516f2  lea     rax, [rbp+var_50]
0x1004516f6  mov     [rbp+Arguments], rax
0x1004516fa  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1004516ff  xor     edx, edx; dwExceptionFlags
0x100451701  lea     r9, [rbp+Arguments]; lpArguments
0x100451705  mov     ecx, 0C06D007Fh; dwExceptionCode
0x10045170a  lea     r8d, [rdx+1]; nNumberOfArguments
0x10045170e  call    cs:__imp_RaiseException
0x100451714  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x100451719  mov     rbx, [rbp+var_18]
0x10045171d  mov     [r12], rbx
0x100451721  mov     rax, cs:__pfnDliNotifyHook2
0x100451728  test    rax, rax
0x10045172b  jz      short loc_100451748
0x10045172d  and     [rbp+var_10], 0
0x100451731  lea     rdx, [rbp+var_50]
0x100451735  mov     ecx, 5
0x10045173a  mov     [rbp+var_20], rdi
0x10045173e  mov     [rbp+var_18], rbx
0x100451742  call    cs:__guard_dispatch_icall_fptr
0x100451748  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x10045174d  mov     rax, rbx
0x100451750  lea     r11, [rsp+70h+var_s0]
0x100451755  mov     rbx, [r11+38h]
0x100451759  mov     rsi, [r11+40h]
0x10045175d  mov     rdi, [r11+48h]
0x100451761  mov     rsp, r11
0x100451764  pop     r15
0x100451766  pop     r14
0x100451768  pop     r13
0x10045176a  pop     r12
0x10045176c  pop     rbp
0x10045176d  retn
```

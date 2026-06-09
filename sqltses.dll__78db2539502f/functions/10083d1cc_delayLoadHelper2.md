# __delayLoadHelper2

- ea: `0x10083d1cc`
- end: `0x10083d49e`
- name: `__delayLoadHelper2`
- size: `722`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10083cb5e`
- `0x10083cc80`
- `0x10083cd33`

## callees

- `0x100404740`
- `0x10083ce08`
- `0x10083d130`
- `0x10083d1cc`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x10083d3ea`
- `KERNEL32!GetProcAddress` at `0x10083d3ea`
- `KERNEL32!GetLastError` at `0x10083d31e`
- `KERNEL32!GetLastError` at `0x10083d3f8`
- `KERNEL32!GetLastError` at `0x10083d31e`
- `KERNEL32!GetLastError` at `0x10083d3f8`
- `KERNEL32!RaiseException` at `0x10083d26e`
- `KERNEL32!RaiseException` at `0x10083d364`
- `KERNEL32!RaiseException` at `0x10083d43e`
- `KERNEL32!RaiseException` at `0x10083d26e`
- `KERNEL32!RaiseException` at `0x10083d364`
- `KERNEL32!RaiseException` at `0x10083d43e`
- `KERNEL32!FreeLibrary` at `0x10083d381`
- `KERNEL32!FreeLibrary` at `0x10083d381`
- `KERNEL32!LoadLibraryExA` at `0x10083d310`
- `KERNEL32!LoadLibraryExA` at `0x10083d310`

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
0x10083d1cc  mov     [rsp-28h+arg_8], rbx
0x10083d1d1  mov     [rsp-28h+arg_10], rsi
0x10083d1d6  mov     [rsp-28h+arg_18], rdi
0x10083d1db  push    rbp
0x10083d1dc  push    r12
0x10083d1de  push    r13
0x10083d1e0  push    r14
0x10083d1e2  push    r15
0x10083d1e4  mov     rbp, rsp
0x10083d1e7  sub     rsp, 70h
0x10083d1eb  mov     r12, rdx
0x10083d1ee  mov     rsi, rcx
0x10083d1f1  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x10083d1f6  mov     eax, [rsi+4]
0x10083d1f9  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10083d200  mov     r14d, [rsi+8]
0x10083d204  add     rax, rdx
0x10083d207  mov     r9d, [rsi+0Ch]
0x10083d20b  add     r14, rdx
0x10083d20e  mov     ecx, [rsi+10h]
0x10083d211  add     r9, rdx
0x10083d214  mov     r13d, [rsi+14h]
0x10083d218  add     rcx, rdx
0x10083d21b  and     [rbp+var_20], 0
0x10083d220  add     r13, rdx
0x10083d223  and     [rbp+var_18], 0
0x10083d228  xorps   xmm0, xmm0
0x10083d22b  and     [rbp+var_10], 0
0x10083d22f  mov     edx, [rsi+1Ch]
0x10083d232  mov     [rbp+lpLibFileName], rax
0x10083d236  mov     eax, [rsi]
0x10083d238  mov     dword ptr [rbp+Arguments], edx
0x10083d23b  mov     [rbp+var_50], 48h ; 'H'
0x10083d242  mov     [rbp+var_48], rsi
0x10083d246  mov     [rbp+var_40], r12
0x10083d24a  movups  xmmword ptr [rbp+lpProcName], xmm0
0x10083d24e  test    al, 1
0x10083d250  jnz     short loc_10083D27B
0x10083d252  lea     rax, [rbp+var_50]
0x10083d256  mov     [rbp+Arguments], rax
0x10083d25a  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x10083d25f  xor     edx, edx; dwExceptionFlags
0x10083d261  lea     r9, [rbp+Arguments]; lpArguments
0x10083d265  mov     ecx, 0C06D0057h; dwExceptionCode
0x10083d26a  lea     r8d, [rdx+1]; nNumberOfArguments
0x10083d26e  call    cs:__imp_RaiseException
0x10083d274  xor     eax, eax
0x10083d276  jmp     loc_10083D480
0x10083d27b  mov     rdi, [r14]
0x10083d27e  mov     r15, r12
0x10083d281  sub     r15, r9
0x10083d284  sar     r15, 3
0x10083d288  mov     r15d, r15d
0x10083d28b  mov     rax, [rcx+r15*8]
0x10083d28f  shr     rax, 3Fh
0x10083d293  xor     eax, 1
0x10083d296  mov     dword ptr [rbp+lpProcName], eax
0x10083d299  jz      short loc_10083D2AF
0x10083d29b  mov     eax, [rcx+r15*8]
0x10083d29f  lea     rcx, word_100400002
0x10083d2a6  add     rax, rcx
0x10083d2a9  mov     [rbp+lpProcName+8], rax
0x10083d2ad  jmp     short loc_10083D2B7
0x10083d2af  movzx   eax, word ptr [rcx+r15*8]
0x10083d2b4  mov     dword ptr [rbp+lpProcName+8], eax
0x10083d2b7  mov     rax, cs:__pfnDliNotifyHook2
0x10083d2be  xor     ebx, ebx
0x10083d2c0  test    rax, rax
0x10083d2c3  jz      short loc_10083D2E4
0x10083d2c5  lea     rdx, [rbp+var_50]
0x10083d2c9  xor     ecx, ecx
0x10083d2cb  call    cs:__guard_dispatch_icall_fptr
0x10083d2d1  mov     rbx, rax
0x10083d2d4  test    rax, rax
0x10083d2d7  jnz     loc_10083D451
0x10083d2dd  mov     rax, cs:__pfnDliNotifyHook2
0x10083d2e4  test    rdi, rdi
0x10083d2e7  jnz     loc_10083D38E
0x10083d2ed  test    rax, rax
0x10083d2f0  jz      short loc_10083D307
0x10083d2f2  lea     rdx, [rbp+var_50]
0x10083d2f6  lea     ecx, [rdi+1]
0x10083d2f9  call    cs:__guard_dispatch_icall_fptr
0x10083d2ff  mov     rdi, rax
0x10083d302  test    rax, rax
0x10083d305  jnz     short loc_10083D373
0x10083d307  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x10083d30b  xor     r8d, r8d; dwFlags
0x10083d30e  xor     edx, edx; hFile
0x10083d310  call    cs:__imp_LoadLibraryExA
0x10083d316  mov     rdi, rax
0x10083d319  test    rax, rax
0x10083d31c  jnz     short loc_10083D373
0x10083d31e  call    cs:__imp_GetLastError
0x10083d324  mov     [rbp+var_10], eax
0x10083d327  mov     rax, cs:__pfnDliFailureHook2
0x10083d32e  test    rax, rax
0x10083d331  jz      short loc_10083D348
0x10083d333  lea     rdx, [rbp+var_50]
0x10083d337  lea     ecx, [rdi+3]
0x10083d33a  call    cs:__guard_dispatch_icall_fptr
0x10083d340  mov     rdi, rax
0x10083d343  test    rax, rax
0x10083d346  jnz     short loc_10083D373
0x10083d348  lea     rax, [rbp+var_50]
0x10083d34c  mov     [rbp+Arguments], rax
0x10083d350  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x10083d355  xor     edx, edx; dwExceptionFlags
0x10083d357  lea     r9, [rbp+Arguments]; lpArguments
0x10083d35b  mov     ecx, 0C06D007Eh; dwExceptionCode
0x10083d360  lea     r8d, [rdx+1]; nNumberOfArguments
0x10083d364  call    cs:__imp_RaiseException
0x10083d36a  mov     rax, [rbp+var_18]
0x10083d36e  jmp     loc_10083D480
0x10083d373  mov     rax, rdi
0x10083d376  xchg    rax, [r14]
0x10083d379  cmp     rax, rdi
0x10083d37c  jnz     short loc_10083D387
0x10083d37e  mov     rcx, rdi; hLibModule
0x10083d381  call    cs:__imp_FreeLibrary
0x10083d387  mov     rax, cs:__pfnDliNotifyHook2
0x10083d38e  mov     [rbp+var_20], rdi
0x10083d392  test    rax, rax
0x10083d395  jz      short loc_10083D3A9
0x10083d397  lea     rdx, [rbp+var_50]
0x10083d39b  mov     ecx, 2
0x10083d3a0  call    cs:__guard_dispatch_icall_fptr
0x10083d3a6  mov     rbx, rax
0x10083d3a9  test    rbx, rbx
0x10083d3ac  jnz     loc_10083D44D
0x10083d3b2  cmp     [rsi+14h], ebx
0x10083d3b5  jz      short loc_10083D3E3
0x10083d3b7  cmp     [rsi+1Ch], ebx
0x10083d3ba  jz      short loc_10083D3E3
0x10083d3bc  movsxd  rax, dword ptr [rdi+3Ch]
0x10083d3c0  cmp     dword ptr [rax+rdi], 4550h
0x10083d3c7  jnz     short loc_10083D3E3
0x10083d3c9  mov     ecx, dword ptr [rbp+Arguments]
0x10083d3cc  cmp     [rax+rdi+8], ecx
0x10083d3d0  jnz     short loc_10083D3E3
0x10083d3d2  cmp     rdi, [rax+rdi+30h]
0x10083d3d7  jnz     short loc_10083D3E3
0x10083d3d9  mov     rbx, [r13+r15*8+0]
0x10083d3de  test    rbx, rbx
0x10083d3e1  jnz     short loc_10083D44D
0x10083d3e3  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x10083d3e7  mov     rcx, rdi; hModule
0x10083d3ea  call    cs:__imp_GetProcAddress
0x10083d3f0  mov     rbx, rax
0x10083d3f3  test    rax, rax
0x10083d3f6  jnz     short loc_10083D44D
0x10083d3f8  call    cs:__imp_GetLastError
0x10083d3fe  mov     [rbp+var_10], eax
0x10083d401  mov     rax, cs:__pfnDliFailureHook2
0x10083d408  test    rax, rax
0x10083d40b  jz      short loc_10083D422
0x10083d40d  lea     rdx, [rbp+var_50]
0x10083d411  lea     ecx, [rbx+4]
0x10083d414  call    cs:__guard_dispatch_icall_fptr
0x10083d41a  mov     rbx, rax
0x10083d41d  test    rax, rax
0x10083d420  jnz     short loc_10083D44D
0x10083d422  lea     rax, [rbp+var_50]
0x10083d426  mov     [rbp+Arguments], rax
0x10083d42a  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x10083d42f  xor     edx, edx; dwExceptionFlags
0x10083d431  lea     r9, [rbp+Arguments]; lpArguments
0x10083d435  mov     ecx, 0C06D007Fh; dwExceptionCode
0x10083d43a  lea     r8d, [rdx+1]; nNumberOfArguments
0x10083d43e  call    cs:__imp_RaiseException
0x10083d444  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x10083d449  mov     rbx, [rbp+var_18]
0x10083d44d  mov     [r12], rbx
0x10083d451  mov     rax, cs:__pfnDliNotifyHook2
0x10083d458  test    rax, rax
0x10083d45b  jz      short loc_10083D478
0x10083d45d  and     [rbp+var_10], 0
0x10083d461  lea     rdx, [rbp+var_50]
0x10083d465  mov     ecx, 5
0x10083d46a  mov     [rbp+var_20], rdi
0x10083d46e  mov     [rbp+var_18], rbx
0x10083d472  call    cs:__guard_dispatch_icall_fptr
0x10083d478  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x10083d47d  mov     rax, rbx
0x10083d480  lea     r11, [rsp+70h+var_s0]
0x10083d485  mov     rbx, [r11+38h]
0x10083d489  mov     rsi, [r11+40h]
0x10083d48d  mov     rdi, [r11+48h]
0x10083d491  mov     rsp, r11
0x10083d494  pop     r15
0x10083d496  pop     r14
0x10083d498  pop     r13
0x10083d49a  pop     r12
0x10083d49c  pop     rbp
0x10083d49d  retn
```

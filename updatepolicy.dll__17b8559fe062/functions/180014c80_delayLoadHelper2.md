# __delayLoadHelper2

- ea: `0x180014c80`
- end: `0x180014f7a`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e98c`
- `0x18000ea17`
- `0x18000eaa2`
- `0x18000eb7c`
- `0x180014f7a`
- `0x180015029`

## callees

- `0x180014738`
- `0x18001482c`
- `0x180014bd0`
- `0x180014c80`
- `0x180015450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014d2f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014e25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014eff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014d2f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014e25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014eff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180014dd1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180014dd1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014e42`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014e42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014eab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014eab`

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
0x180014c80  mov     [rsp-28h+arg_8], rbx
0x180014c85  mov     [rsp-28h+arg_10], rsi
0x180014c8a  mov     [rsp-28h+arg_18], rdi
0x180014c8f  push    rbp
0x180014c90  push    r12
0x180014c92  push    r13
0x180014c94  push    r14
0x180014c96  push    r15
0x180014c98  mov     rbp, rsp
0x180014c9b  sub     rsp, 80h
0x180014ca2  mov     r15, rdx
0x180014ca5  mov     rsi, rcx
0x180014ca8  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x180014cad  mov     eax, [rsi+4]
0x180014cb0  lea     r8, __ImageBase
0x180014cb7  mov     r14d, [rsi+8]
0x180014cbb  add     rax, r8
0x180014cbe  mov     edx, [rsi+0Ch]
0x180014cc1  add     r14, r8
0x180014cc4  mov     ecx, [rsi+10h]
0x180014cc7  add     rdx, r8
0x180014cca  mov     r13d, [rsi+14h]
0x180014cce  add     rcx, r8
0x180014cd1  add     r13, r8
0x180014cd4  mov     [rbp+lpLibFileName], rax
0x180014cd8  mov     eax, [rsi]
0x180014cda  xorps   xmm0, xmm0
0x180014cdd  mov     r8d, [rsi+1Ch]
0x180014ce1  mov     dword ptr [rbp+Arguments], r8d
0x180014ce5  mov     [rbp+var_50], 48h ; 'H'
0x180014cec  mov     [rbp+var_48], rsi
0x180014cf0  mov     [rbp+var_40], r15
0x180014cf4  mov     [rbp+var_20], 0
0x180014cfc  mov     [rbp+var_18], 0
0x180014d04  mov     [rbp+var_10], 0
0x180014d0b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x180014d0f  test    al, 1
0x180014d11  jnz     short loc_180014D3C
0x180014d13  lea     rax, [rbp+var_50]
0x180014d17  mov     [rbp+Arguments], rax
0x180014d1b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180014d20  xor     edx, edx; dwExceptionFlags
0x180014d22  lea     r9, [rbp+Arguments]; lpArguments
0x180014d26  mov     ecx, 0C06D0057h; dwExceptionCode
0x180014d2b  lea     r8d, [rdx+1]; nNumberOfArguments
0x180014d2f  call    cs:__imp_RaiseException
0x180014d35  xor     eax, eax
0x180014d37  jmp     loc_180014F59
0x180014d3c  mov     rbx, [r14]
0x180014d3f  mov     r12, r15
0x180014d42  sub     r12, rdx
0x180014d45  sar     r12, 3
0x180014d49  mov     r12d, r12d
0x180014d4c  mov     rax, [rcx+r12*8]
0x180014d50  shr     rax, 3Fh
0x180014d54  xor     eax, 1
0x180014d57  mov     dword ptr [rbp+lpProcName], eax
0x180014d5a  jz      short loc_180014D70
0x180014d5c  mov     eax, [rcx+r12*8]
0x180014d60  lea     rcx, word_180000002
0x180014d67  add     rax, rcx
0x180014d6a  mov     [rbp+lpProcName+8], rax
0x180014d6e  jmp     short loc_180014D78
0x180014d70  movzx   eax, word ptr [rcx+r12*8]
0x180014d75  mov     dword ptr [rbp+lpProcName+8], eax
0x180014d78  mov     rax, cs:__pfnDliNotifyHook2
0x180014d7f  xor     edi, edi
0x180014d81  test    rax, rax
0x180014d84  jz      short loc_180014DA5
0x180014d86  lea     rdx, [rbp+var_50]
0x180014d8a  xor     ecx, ecx
0x180014d8c  call    cs:__guard_dispatch_icall_fptr
0x180014d92  mov     rdi, rax
0x180014d95  test    rax, rax
0x180014d98  jnz     loc_180014F27
0x180014d9e  mov     rax, cs:__pfnDliNotifyHook2
0x180014da5  test    rbx, rbx
0x180014da8  jnz     loc_180014E4F
0x180014dae  test    rax, rax
0x180014db1  jz      short loc_180014DC8
0x180014db3  lea     rdx, [rbp+var_50]
0x180014db7  lea     ecx, [rbx+1]
0x180014dba  call    cs:__guard_dispatch_icall_fptr
0x180014dc0  mov     rbx, rax
0x180014dc3  test    rax, rax
0x180014dc6  jnz     short loc_180014E34
0x180014dc8  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180014dcc  xor     r8d, r8d; dwFlags
0x180014dcf  xor     edx, edx; hFile
0x180014dd1  call    cs:__imp_LoadLibraryExA
0x180014dd7  mov     rbx, rax
0x180014dda  test    rax, rax
0x180014ddd  jnz     short loc_180014E34
0x180014ddf  call    cs:__imp_GetLastError
0x180014de5  mov     [rbp+var_10], eax
0x180014de8  mov     rax, cs:__pfnDliFailureHook2
0x180014def  test    rax, rax
0x180014df2  jz      short loc_180014E09
0x180014df4  lea     rdx, [rbp+var_50]
0x180014df8  lea     ecx, [rbx+3]
0x180014dfb  call    cs:__guard_dispatch_icall_fptr
0x180014e01  mov     rbx, rax
0x180014e04  test    rax, rax
0x180014e07  jnz     short loc_180014E34
0x180014e09  lea     rax, [rbp+var_50]
0x180014e0d  mov     [rbp+Arguments], rax
0x180014e11  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180014e16  xor     edx, edx; dwExceptionFlags
0x180014e18  lea     r9, [rbp+Arguments]; lpArguments
0x180014e1c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180014e21  lea     r8d, [rdx+1]; nNumberOfArguments
0x180014e25  call    cs:__imp_RaiseException
0x180014e2b  mov     rax, [rbp+var_18]
0x180014e2f  jmp     loc_180014F59
0x180014e34  mov     rax, rbx
0x180014e37  xchg    rax, [r14]
0x180014e3a  cmp     rax, rbx
0x180014e3d  jnz     short loc_180014E48
0x180014e3f  mov     rcx, rbx; hLibModule
0x180014e42  call    cs:__imp_FreeLibrary
0x180014e48  mov     rax, cs:__pfnDliNotifyHook2
0x180014e4f  mov     [rbp+var_20], rbx
0x180014e53  test    rax, rax
0x180014e56  jz      short loc_180014E6A
0x180014e58  lea     rdx, [rbp+var_50]
0x180014e5c  mov     ecx, 2
0x180014e61  call    cs:__guard_dispatch_icall_fptr
0x180014e67  mov     rdi, rax
0x180014e6a  test    rdi, rdi
0x180014e6d  jnz     loc_180014F0E
0x180014e73  cmp     [rsi+14h], edi
0x180014e76  jz      short loc_180014EA4
0x180014e78  cmp     [rsi+1Ch], edi
0x180014e7b  jz      short loc_180014EA4
0x180014e7d  movsxd  rax, dword ptr [rbx+3Ch]
0x180014e81  cmp     dword ptr [rax+rbx], 4550h
0x180014e88  jnz     short loc_180014EA4
0x180014e8a  mov     ecx, dword ptr [rbp+Arguments]
0x180014e8d  cmp     [rax+rbx+8], ecx
0x180014e91  jnz     short loc_180014EA4
0x180014e93  cmp     rbx, [rax+rbx+30h]
0x180014e98  jnz     short loc_180014EA4
0x180014e9a  mov     rdi, [r13+r12*8+0]
0x180014e9f  test    rdi, rdi
0x180014ea2  jnz     short loc_180014F0E
0x180014ea4  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x180014ea8  mov     rcx, rbx; hModule
0x180014eab  call    cs:__imp_GetProcAddress
0x180014eb1  mov     rdi, rax
0x180014eb4  test    rax, rax
0x180014eb7  jnz     short loc_180014F0E
0x180014eb9  call    cs:__imp_GetLastError
0x180014ebf  mov     [rbp+var_10], eax
0x180014ec2  mov     rax, cs:__pfnDliFailureHook2
0x180014ec9  test    rax, rax
0x180014ecc  jz      short loc_180014EE3
0x180014ece  lea     rdx, [rbp+var_50]
0x180014ed2  lea     ecx, [rdi+4]
0x180014ed5  call    cs:__guard_dispatch_icall_fptr
0x180014edb  mov     rdi, rax
0x180014ede  test    rax, rax
0x180014ee1  jnz     short loc_180014F0E
0x180014ee3  lea     rax, [rbp+var_50]
0x180014ee7  mov     [rbp+Arguments], rax
0x180014eeb  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180014ef0  xor     edx, edx; dwExceptionFlags
0x180014ef2  lea     r9, [rbp+Arguments]; lpArguments
0x180014ef6  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180014efb  lea     r8d, [rdx+1]; nNumberOfArguments
0x180014eff  call    cs:__imp_RaiseException
0x180014f05  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x180014f0a  mov     rdi, [rbp+var_18]
0x180014f0e  lea     r8, [rbp+var_60]
0x180014f12  mov     [rbp+var_60], r15
0x180014f16  mov     edx, 8; dwSize
0x180014f1b  mov     [rbp+var_58], rdi
0x180014f1f  mov     rcx, r15; lpAddress
0x180014f22  call    GuardedWrite____delayLoadHelper2____2____lambda_1___
0x180014f27  mov     rax, cs:__pfnDliNotifyHook2
0x180014f2e  test    rax, rax
0x180014f31  jz      short loc_180014F51
0x180014f33  lea     rdx, [rbp+var_50]
0x180014f37  mov     [rbp+var_10], 0
0x180014f3e  mov     ecx, 5
0x180014f43  mov     [rbp+var_20], rbx
0x180014f47  mov     [rbp+var_18], rdi
0x180014f4b  call    cs:__guard_dispatch_icall_fptr
0x180014f51  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x180014f56  mov     rax, rdi
0x180014f59  lea     r11, [rsp+80h+var_s0]
0x180014f61  mov     rbx, [r11+38h]
0x180014f65  mov     rsi, [r11+40h]
0x180014f69  mov     rdi, [r11+48h]
0x180014f6d  mov     rsp, r11
0x180014f70  pop     r15
0x180014f72  pop     r14
0x180014f74  pop     r13
0x180014f76  pop     r12
0x180014f78  pop     rbp
0x180014f79  retn
```

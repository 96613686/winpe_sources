# __delayLoadHelper2

- ea: `0x100614cfc`
- end: `0x100614fce`
- name: `__delayLoadHelper2`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10061463d`

## callees

- `0x100420a40`
- `0x10061492c`
- `0x100614c60`
- `0x100614cfc`

## import_xrefs

- `KERNEL32!RaiseException` at `0x100614d9e`
- `KERNEL32!RaiseException` at `0x100614e94`
- `KERNEL32!RaiseException` at `0x100614f6e`
- `KERNEL32!RaiseException` at `0x100614d9e`
- `KERNEL32!RaiseException` at `0x100614e94`
- `KERNEL32!RaiseException` at `0x100614f6e`
- `KERNEL32!FreeLibrary` at `0x100614eb1`
- `KERNEL32!FreeLibrary` at `0x100614eb1`
- `KERNEL32!GetProcAddress` at `0x100614f1a`
- `KERNEL32!GetProcAddress` at `0x100614f1a`
- `KERNEL32!GetLastError` at `0x100614e4e`
- `KERNEL32!GetLastError` at `0x100614f28`
- `KERNEL32!GetLastError` at `0x100614e4e`
- `KERNEL32!GetLastError` at `0x100614f28`
- `KERNEL32!LoadLibraryExA` at `0x100614e40`
- `KERNEL32!LoadLibraryExA` at `0x100614e40`

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
  v4 = (volatile __int64 *)((char *)&_NULL_IMPORT_DESCRIPTOR.unused + a1->rvaHmod);
  v5 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaIAT;
  v6 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaINT;
  v7 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaBoundIAT;
  dwTimeStamp = a1->dwTimeStamp;
  v17.szDll = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaDLLName;
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
    v17.dlp.szProcName = (char *)&_NULL_IMPORT_DESCRIPTOR.unused + *(unsigned int *)&v6[8 * v12] + 2;
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
0x100614cfc  mov     [rsp-28h+arg_8], rbx
0x100614d01  mov     [rsp-28h+arg_10], rsi
0x100614d06  mov     [rsp-28h+arg_18], rdi
0x100614d0b  push    rbp
0x100614d0c  push    r12
0x100614d0e  push    r13
0x100614d10  push    r14
0x100614d12  push    r15
0x100614d14  mov     rbp, rsp
0x100614d17  sub     rsp, 70h
0x100614d1b  mov     r12, rdx
0x100614d1e  mov     rsi, rcx
0x100614d21  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x100614d26  mov     eax, [rsi+4]
0x100614d29  lea     rdx, __NULL_IMPORT_DESCRIPTOR
0x100614d30  mov     r14d, [rsi+8]
0x100614d34  add     rax, rdx
0x100614d37  mov     r9d, [rsi+0Ch]
0x100614d3b  add     r14, rdx
0x100614d3e  mov     ecx, [rsi+10h]
0x100614d41  add     r9, rdx
0x100614d44  mov     r13d, [rsi+14h]
0x100614d48  add     rcx, rdx
0x100614d4b  and     [rbp+var_20], 0
0x100614d50  add     r13, rdx
0x100614d53  and     [rbp+var_18], 0
0x100614d58  xorps   xmm0, xmm0
0x100614d5b  and     [rbp+var_10], 0
0x100614d5f  mov     edx, [rsi+1Ch]
0x100614d62  mov     [rbp+lpLibFileName], rax
0x100614d66  mov     eax, [rsi]
0x100614d68  mov     dword ptr [rbp+Arguments], edx
0x100614d6b  mov     [rbp+var_50], 48h ; 'H'
0x100614d72  mov     [rbp+var_48], rsi
0x100614d76  mov     [rbp+var_40], r12
0x100614d7a  movups  xmmword ptr [rbp+lpProcName], xmm0
0x100614d7e  test    al, 1
0x100614d80  jnz     short loc_100614DAB
0x100614d82  lea     rax, [rbp+var_50]
0x100614d86  mov     [rbp+Arguments], rax
0x100614d8a  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100614d8f  xor     edx, edx; dwExceptionFlags
0x100614d91  lea     r9, [rbp+Arguments]; lpArguments
0x100614d95  mov     ecx, 0C06D0057h; dwExceptionCode
0x100614d9a  lea     r8d, [rdx+1]; nNumberOfArguments
0x100614d9e  call    cs:__imp_RaiseException
0x100614da4  xor     eax, eax
0x100614da6  jmp     loc_100614FB0
0x100614dab  mov     rdi, [r14]
0x100614dae  mov     r15, r12
0x100614db1  sub     r15, r9
0x100614db4  sar     r15, 3
0x100614db8  mov     r15d, r15d
0x100614dbb  mov     rax, [rcx+r15*8]
0x100614dbf  shr     rax, 3Fh
0x100614dc3  xor     eax, 1
0x100614dc6  mov     dword ptr [rbp+lpProcName], eax
0x100614dc9  jz      short loc_100614DDF
0x100614dcb  mov     eax, [rcx+r15*8]
0x100614dcf  lea     rcx, __NULL_IMPORT_DESCRIPTOR.unused+2
0x100614dd6  add     rax, rcx
0x100614dd9  mov     [rbp+lpProcName+8], rax
0x100614ddd  jmp     short loc_100614DE7
0x100614ddf  movzx   eax, word ptr [rcx+r15*8]
0x100614de4  mov     dword ptr [rbp+lpProcName+8], eax
0x100614de7  mov     rax, cs:__pfnDliNotifyHook2
0x100614dee  xor     ebx, ebx
0x100614df0  test    rax, rax
0x100614df3  jz      short loc_100614E14
0x100614df5  lea     rdx, [rbp+var_50]
0x100614df9  xor     ecx, ecx
0x100614dfb  call    cs:__guard_dispatch_icall_fptr
0x100614e01  mov     rbx, rax
0x100614e04  test    rax, rax
0x100614e07  jnz     loc_100614F81
0x100614e0d  mov     rax, cs:__pfnDliNotifyHook2
0x100614e14  test    rdi, rdi
0x100614e17  jnz     loc_100614EBE
0x100614e1d  test    rax, rax
0x100614e20  jz      short loc_100614E37
0x100614e22  lea     rdx, [rbp+var_50]
0x100614e26  lea     ecx, [rdi+1]
0x100614e29  call    cs:__guard_dispatch_icall_fptr
0x100614e2f  mov     rdi, rax
0x100614e32  test    rax, rax
0x100614e35  jnz     short loc_100614EA3
0x100614e37  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x100614e3b  xor     r8d, r8d; dwFlags
0x100614e3e  xor     edx, edx; hFile
0x100614e40  call    cs:__imp_LoadLibraryExA
0x100614e46  mov     rdi, rax
0x100614e49  test    rax, rax
0x100614e4c  jnz     short loc_100614EA3
0x100614e4e  call    cs:__imp_GetLastError
0x100614e54  mov     [rbp+var_10], eax
0x100614e57  mov     rax, cs:__pfnDliFailureHook2
0x100614e5e  test    rax, rax
0x100614e61  jz      short loc_100614E78
0x100614e63  lea     rdx, [rbp+var_50]
0x100614e67  lea     ecx, [rdi+3]
0x100614e6a  call    cs:__guard_dispatch_icall_fptr
0x100614e70  mov     rdi, rax
0x100614e73  test    rax, rax
0x100614e76  jnz     short loc_100614EA3
0x100614e78  lea     rax, [rbp+var_50]
0x100614e7c  mov     [rbp+Arguments], rax
0x100614e80  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100614e85  xor     edx, edx; dwExceptionFlags
0x100614e87  lea     r9, [rbp+Arguments]; lpArguments
0x100614e8b  mov     ecx, 0C06D007Eh; dwExceptionCode
0x100614e90  lea     r8d, [rdx+1]; nNumberOfArguments
0x100614e94  call    cs:__imp_RaiseException
0x100614e9a  mov     rax, [rbp+var_18]
0x100614e9e  jmp     loc_100614FB0
0x100614ea3  mov     rax, rdi
0x100614ea6  xchg    rax, [r14]
0x100614ea9  cmp     rax, rdi
0x100614eac  jnz     short loc_100614EB7
0x100614eae  mov     rcx, rdi; hLibModule
0x100614eb1  call    cs:__imp_FreeLibrary
0x100614eb7  mov     rax, cs:__pfnDliNotifyHook2
0x100614ebe  mov     [rbp+var_20], rdi
0x100614ec2  test    rax, rax
0x100614ec5  jz      short loc_100614ED9
0x100614ec7  lea     rdx, [rbp+var_50]
0x100614ecb  mov     ecx, 2
0x100614ed0  call    cs:__guard_dispatch_icall_fptr
0x100614ed6  mov     rbx, rax
0x100614ed9  test    rbx, rbx
0x100614edc  jnz     loc_100614F7D
0x100614ee2  cmp     [rsi+14h], ebx
0x100614ee5  jz      short loc_100614F13
0x100614ee7  cmp     [rsi+1Ch], ebx
0x100614eea  jz      short loc_100614F13
0x100614eec  movsxd  rax, dword ptr [rdi+3Ch]
0x100614ef0  cmp     dword ptr [rax+rdi], 4550h
0x100614ef7  jnz     short loc_100614F13
0x100614ef9  mov     ecx, dword ptr [rbp+Arguments]
0x100614efc  cmp     [rax+rdi+8], ecx
0x100614f00  jnz     short loc_100614F13
0x100614f02  cmp     rdi, [rax+rdi+30h]
0x100614f07  jnz     short loc_100614F13
0x100614f09  mov     rbx, [r13+r15*8+0]
0x100614f0e  test    rbx, rbx
0x100614f11  jnz     short loc_100614F7D
0x100614f13  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x100614f17  mov     rcx, rdi; hModule
0x100614f1a  call    cs:__imp_GetProcAddress
0x100614f20  mov     rbx, rax
0x100614f23  test    rax, rax
0x100614f26  jnz     short loc_100614F7D
0x100614f28  call    cs:__imp_GetLastError
0x100614f2e  mov     [rbp+var_10], eax
0x100614f31  mov     rax, cs:__pfnDliFailureHook2
0x100614f38  test    rax, rax
0x100614f3b  jz      short loc_100614F52
0x100614f3d  lea     rdx, [rbp+var_50]
0x100614f41  lea     ecx, [rbx+4]
0x100614f44  call    cs:__guard_dispatch_icall_fptr
0x100614f4a  mov     rbx, rax
0x100614f4d  test    rax, rax
0x100614f50  jnz     short loc_100614F7D
0x100614f52  lea     rax, [rbp+var_50]
0x100614f56  mov     [rbp+Arguments], rax
0x100614f5a  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100614f5f  xor     edx, edx; dwExceptionFlags
0x100614f61  lea     r9, [rbp+Arguments]; lpArguments
0x100614f65  mov     ecx, 0C06D007Fh; dwExceptionCode
0x100614f6a  lea     r8d, [rdx+1]; nNumberOfArguments
0x100614f6e  call    cs:__imp_RaiseException
0x100614f74  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x100614f79  mov     rbx, [rbp+var_18]
0x100614f7d  mov     [r12], rbx
0x100614f81  mov     rax, cs:__pfnDliNotifyHook2
0x100614f88  test    rax, rax
0x100614f8b  jz      short loc_100614FA8
0x100614f8d  and     [rbp+var_10], 0
0x100614f91  lea     rdx, [rbp+var_50]
0x100614f95  mov     ecx, 5
0x100614f9a  mov     [rbp+var_20], rdi
0x100614f9e  mov     [rbp+var_18], rbx
0x100614fa2  call    cs:__guard_dispatch_icall_fptr
0x100614fa8  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100614fad  mov     rax, rbx
0x100614fb0  lea     r11, [rsp+70h+var_s0]
0x100614fb5  mov     rbx, [r11+38h]
0x100614fb9  mov     rsi, [r11+40h]
0x100614fbd  mov     rdi, [r11+48h]
0x100614fc1  mov     rsp, r11
0x100614fc4  pop     r15
0x100614fc6  pop     r14
0x100614fc8  pop     r13
0x100614fca  pop     r12
0x100614fcc  pop     rbp
0x100614fcd  retn
```

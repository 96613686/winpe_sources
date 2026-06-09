# __delayLoadHelper2

- ea: `0x100439a10`
- end: `0x100439ce2`
- name: `__delayLoadHelper2`
- size: `722`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1004395c9`
- `0x100439cf4`

## callees

- `0x100439648`
- `0x100439970`
- `0x100439a10`
- `0x100439df0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100439b62`
- `KERNEL32!GetLastError` at `0x100439c3c`
- `KERNEL32!GetLastError` at `0x100439b62`
- `KERNEL32!GetLastError` at `0x100439c3c`
- `KERNEL32!FreeLibrary` at `0x100439bc5`
- `KERNEL32!FreeLibrary` at `0x100439bc5`
- `KERNEL32!GetProcAddress` at `0x100439c2e`
- `KERNEL32!GetProcAddress` at `0x100439c2e`
- `KERNEL32!RaiseException` at `0x100439ab2`
- `KERNEL32!RaiseException` at `0x100439ba8`
- `KERNEL32!RaiseException` at `0x100439c82`
- `KERNEL32!RaiseException` at `0x100439ab2`
- `KERNEL32!RaiseException` at `0x100439ba8`
- `KERNEL32!RaiseException` at `0x100439c82`
- `KERNEL32!LoadLibraryExA` at `0x100439b54`
- `KERNEL32!LoadLibraryExA` at `0x100439b54`

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
0x100439a10  mov     [rsp-28h+arg_8], rbx
0x100439a15  mov     [rsp-28h+arg_10], rsi
0x100439a1a  mov     [rsp-28h+arg_18], rdi
0x100439a1f  push    rbp
0x100439a20  push    r12
0x100439a22  push    r13
0x100439a24  push    r14
0x100439a26  push    r15
0x100439a28  mov     rbp, rsp
0x100439a2b  sub     rsp, 70h
0x100439a2f  mov     r12, rdx
0x100439a32  mov     rsi, rcx
0x100439a35  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x100439a3a  mov     eax, [rsi+4]
0x100439a3d  lea     rdx, __ImageBase
0x100439a44  mov     r14d, [rsi+8]
0x100439a48  add     rax, rdx
0x100439a4b  mov     r9d, [rsi+0Ch]
0x100439a4f  add     r14, rdx
0x100439a52  mov     ecx, [rsi+10h]
0x100439a55  add     r9, rdx
0x100439a58  mov     r13d, [rsi+14h]
0x100439a5c  add     rcx, rdx
0x100439a5f  and     [rbp+var_20], 0
0x100439a64  add     r13, rdx
0x100439a67  and     [rbp+var_18], 0
0x100439a6c  xorps   xmm0, xmm0
0x100439a6f  and     [rbp+var_10], 0
0x100439a73  mov     edx, [rsi+1Ch]
0x100439a76  mov     [rbp+lpLibFileName], rax
0x100439a7a  mov     eax, [rsi]
0x100439a7c  mov     dword ptr [rbp+Arguments], edx
0x100439a7f  mov     [rbp+var_50], 48h ; 'H'
0x100439a86  mov     [rbp+var_48], rsi
0x100439a8a  mov     [rbp+var_40], r12
0x100439a8e  movups  xmmword ptr [rbp+lpProcName], xmm0
0x100439a92  test    al, 1
0x100439a94  jnz     short loc_100439ABF
0x100439a96  lea     rax, [rbp+var_50]
0x100439a9a  mov     [rbp+Arguments], rax
0x100439a9e  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100439aa3  xor     edx, edx; dwExceptionFlags
0x100439aa5  lea     r9, [rbp+Arguments]; lpArguments
0x100439aa9  mov     ecx, 0C06D0057h; dwExceptionCode
0x100439aae  lea     r8d, [rdx+1]; nNumberOfArguments
0x100439ab2  call    cs:__imp_RaiseException
0x100439ab8  xor     eax, eax
0x100439aba  jmp     loc_100439CC4
0x100439abf  mov     rdi, [r14]
0x100439ac2  mov     r15, r12
0x100439ac5  sub     r15, r9
0x100439ac8  sar     r15, 3
0x100439acc  mov     r15d, r15d
0x100439acf  mov     rax, [rcx+r15*8]
0x100439ad3  shr     rax, 3Fh
0x100439ad7  xor     eax, 1
0x100439ada  mov     dword ptr [rbp+lpProcName], eax
0x100439add  jz      short loc_100439AF3
0x100439adf  mov     eax, [rcx+r15*8]
0x100439ae3  lea     rcx, word_100400002
0x100439aea  add     rax, rcx
0x100439aed  mov     [rbp+lpProcName+8], rax
0x100439af1  jmp     short loc_100439AFB
0x100439af3  movzx   eax, word ptr [rcx+r15*8]
0x100439af8  mov     dword ptr [rbp+lpProcName+8], eax
0x100439afb  mov     rax, cs:__pfnDliNotifyHook2
0x100439b02  xor     ebx, ebx
0x100439b04  test    rax, rax
0x100439b07  jz      short loc_100439B28
0x100439b09  lea     rdx, [rbp+var_50]
0x100439b0d  xor     ecx, ecx
0x100439b0f  call    cs:__guard_dispatch_icall_fptr
0x100439b15  mov     rbx, rax
0x100439b18  test    rax, rax
0x100439b1b  jnz     loc_100439C95
0x100439b21  mov     rax, cs:__pfnDliNotifyHook2
0x100439b28  test    rdi, rdi
0x100439b2b  jnz     loc_100439BD2
0x100439b31  test    rax, rax
0x100439b34  jz      short loc_100439B4B
0x100439b36  lea     rdx, [rbp+var_50]
0x100439b3a  lea     ecx, [rdi+1]
0x100439b3d  call    cs:__guard_dispatch_icall_fptr
0x100439b43  mov     rdi, rax
0x100439b46  test    rax, rax
0x100439b49  jnz     short loc_100439BB7
0x100439b4b  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x100439b4f  xor     r8d, r8d; dwFlags
0x100439b52  xor     edx, edx; hFile
0x100439b54  call    cs:__imp_LoadLibraryExA
0x100439b5a  mov     rdi, rax
0x100439b5d  test    rax, rax
0x100439b60  jnz     short loc_100439BB7
0x100439b62  call    cs:__imp_GetLastError
0x100439b68  mov     [rbp+var_10], eax
0x100439b6b  mov     rax, cs:__pfnDliFailureHook2
0x100439b72  test    rax, rax
0x100439b75  jz      short loc_100439B8C
0x100439b77  lea     rdx, [rbp+var_50]
0x100439b7b  lea     ecx, [rdi+3]
0x100439b7e  call    cs:__guard_dispatch_icall_fptr
0x100439b84  mov     rdi, rax
0x100439b87  test    rax, rax
0x100439b8a  jnz     short loc_100439BB7
0x100439b8c  lea     rax, [rbp+var_50]
0x100439b90  mov     [rbp+Arguments], rax
0x100439b94  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100439b99  xor     edx, edx; dwExceptionFlags
0x100439b9b  lea     r9, [rbp+Arguments]; lpArguments
0x100439b9f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x100439ba4  lea     r8d, [rdx+1]; nNumberOfArguments
0x100439ba8  call    cs:__imp_RaiseException
0x100439bae  mov     rax, [rbp+var_18]
0x100439bb2  jmp     loc_100439CC4
0x100439bb7  mov     rax, rdi
0x100439bba  xchg    rax, [r14]
0x100439bbd  cmp     rax, rdi
0x100439bc0  jnz     short loc_100439BCB
0x100439bc2  mov     rcx, rdi; hLibModule
0x100439bc5  call    cs:__imp_FreeLibrary
0x100439bcb  mov     rax, cs:__pfnDliNotifyHook2
0x100439bd2  mov     [rbp+var_20], rdi
0x100439bd6  test    rax, rax
0x100439bd9  jz      short loc_100439BED
0x100439bdb  lea     rdx, [rbp+var_50]
0x100439bdf  mov     ecx, 2
0x100439be4  call    cs:__guard_dispatch_icall_fptr
0x100439bea  mov     rbx, rax
0x100439bed  test    rbx, rbx
0x100439bf0  jnz     loc_100439C91
0x100439bf6  cmp     [rsi+14h], ebx
0x100439bf9  jz      short loc_100439C27
0x100439bfb  cmp     [rsi+1Ch], ebx
0x100439bfe  jz      short loc_100439C27
0x100439c00  movsxd  rax, dword ptr [rdi+3Ch]
0x100439c04  cmp     dword ptr [rax+rdi], 4550h
0x100439c0b  jnz     short loc_100439C27
0x100439c0d  mov     ecx, dword ptr [rbp+Arguments]
0x100439c10  cmp     [rax+rdi+8], ecx
0x100439c14  jnz     short loc_100439C27
0x100439c16  cmp     rdi, [rax+rdi+30h]
0x100439c1b  jnz     short loc_100439C27
0x100439c1d  mov     rbx, [r13+r15*8+0]
0x100439c22  test    rbx, rbx
0x100439c25  jnz     short loc_100439C91
0x100439c27  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x100439c2b  mov     rcx, rdi; hModule
0x100439c2e  call    cs:__imp_GetProcAddress
0x100439c34  mov     rbx, rax
0x100439c37  test    rax, rax
0x100439c3a  jnz     short loc_100439C91
0x100439c3c  call    cs:__imp_GetLastError
0x100439c42  mov     [rbp+var_10], eax
0x100439c45  mov     rax, cs:__pfnDliFailureHook2
0x100439c4c  test    rax, rax
0x100439c4f  jz      short loc_100439C66
0x100439c51  lea     rdx, [rbp+var_50]
0x100439c55  lea     ecx, [rbx+4]
0x100439c58  call    cs:__guard_dispatch_icall_fptr
0x100439c5e  mov     rbx, rax
0x100439c61  test    rax, rax
0x100439c64  jnz     short loc_100439C91
0x100439c66  lea     rax, [rbp+var_50]
0x100439c6a  mov     [rbp+Arguments], rax
0x100439c6e  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100439c73  xor     edx, edx; dwExceptionFlags
0x100439c75  lea     r9, [rbp+Arguments]; lpArguments
0x100439c79  mov     ecx, 0C06D007Fh; dwExceptionCode
0x100439c7e  lea     r8d, [rdx+1]; nNumberOfArguments
0x100439c82  call    cs:__imp_RaiseException
0x100439c88  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x100439c8d  mov     rbx, [rbp+var_18]
0x100439c91  mov     [r12], rbx
0x100439c95  mov     rax, cs:__pfnDliNotifyHook2
0x100439c9c  test    rax, rax
0x100439c9f  jz      short loc_100439CBC
0x100439ca1  and     [rbp+var_10], 0
0x100439ca5  lea     rdx, [rbp+var_50]
0x100439ca9  mov     ecx, 5
0x100439cae  mov     [rbp+var_20], rdi
0x100439cb2  mov     [rbp+var_18], rbx
0x100439cb6  call    cs:__guard_dispatch_icall_fptr
0x100439cbc  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x100439cc1  mov     rax, rbx
0x100439cc4  lea     r11, [rsp+70h+var_s0]
0x100439cc9  mov     rbx, [r11+38h]
0x100439ccd  mov     rsi, [r11+40h]
0x100439cd1  mov     rdi, [r11+48h]
0x100439cd5  mov     rsp, r11
0x100439cd8  pop     r15
0x100439cda  pop     r14
0x100439cdc  pop     r13
0x100439cde  pop     r12
0x100439ce0  pop     rbp
0x100439ce1  retn
```

# __delayLoadHelper2

- ea: `0x180015ba0`
- end: `0x180015f1d`
- name: `__delayLoadHelper2`
- size: `893`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b10`
- `0x180015acc`

## callees

- `0x1800157f8`
- `0x180015a6c`
- `0x180015ba0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180015d0e`
- `KERNEL32!GetLastError` at `0x180015e69`
- `KERNEL32!GetLastError` at `0x180015d0e`
- `KERNEL32!GetLastError` at `0x180015e69`
- `KERNEL32!HeapAlloc` at `0x180015d9e`
- `KERNEL32!HeapAlloc` at `0x180015d9e`
- `KERNEL32!GetProcessHeap` at `0x180015d86`
- `KERNEL32!GetProcessHeap` at `0x180015d86`
- `KERNEL32!LoadLibraryExA` at `0x180015cfa`
- `KERNEL32!LoadLibraryExA` at `0x180015cfa`
- `KERNEL32!RaiseException` at `0x180015c50`
- `KERNEL32!RaiseException` at `0x180015d59`
- `KERNEL32!RaiseException` at `0x180015eb4`
- `KERNEL32!RaiseException` at `0x180015c50`
- `KERNEL32!RaiseException` at `0x180015d59`
- `KERNEL32!RaiseException` at `0x180015eb4`
- `KERNEL32!FreeLibrary` at `0x180015dcf`
- `KERNEL32!FreeLibrary` at `0x180015dcf`
- `KERNEL32!GetProcAddress` at `0x180015e55`
- `KERNEL32!GetProcAddress` at `0x180015e55`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, char *a2)
{
  const CHAR *v4; // rax
  volatile signed __int64 *v5; // r15
  char *v6; // rcx
  __int64 rvaBoundIAT; // r13
  __int16 *v8; // rdx
  char *v9; // r13
  __int64 dwTimeStamp; // r8
  HMODULE Library; // rbx
  __int64 v13; // r14
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64, _DWORD *); // r8
  FARPROC ProcAddress; // rdi
  __int64 v18; // rax
  __int64 v19; // r8
  signed __int64 v20; // r15
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  _DWORD v29[2]; // [rsp+20h] [rbp-50h] BYREF
  const ImgDelayDescr *v30; // [rsp+28h] [rbp-48h]
  char *v31; // [rsp+30h] [rbp-40h]
  LPCSTR lpLibFileName; // [rsp+38h] [rbp-38h]
  BOOL v33; // [rsp+40h] [rbp-30h]
  int v34; // [rsp+44h] [rbp-2Ch]
  LPCSTR lpProcName; // [rsp+48h] [rbp-28h]
  HMODULE v36; // [rsp+50h] [rbp-20h]
  INT_PTR (__stdcall *v37)(); // [rsp+58h] [rbp-18h]
  DWORD LastError; // [rsp+60h] [rbp-10h]
  ULONG_PTR Arguments; // [rsp+A0h] [rbp+30h] BYREF

  v34 = 0;
  v29[1] = 0;
  ((void (*)(void))DloadAcquireSectionWriteAccess)();
  v4 = (char *)&_ImageBase + a1->rvaDLLName;
  v5 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  v6 = (char *)&_ImageBase + a1->rvaIAT;
  rvaBoundIAT = a1->rvaBoundIAT;
  v8 = (__int16 *)((char *)&_ImageBase + a1->rvaINT);
  v33 = 0;
  v9 = (char *)&_ImageBase + rvaBoundIAT;
  lpProcName = 0;
  v36 = 0;
  v37 = 0;
  LastError = 0;
  dwTimeStamp = a1->dwTimeStamp;
  lpLibFileName = v4;
  LODWORD(v4) = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v29[0] = 72;
  v30 = a1;
  v31 = a2;
  if ( ((unsigned __int8)v4 & 1) == 0 )
  {
    Arguments = (ULONG_PTR)v29;
    DloadReleaseSectionWriteAccess(v6, v8, dwTimeStamp);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v5;
  v13 = (a2 - v6) >> 3;
  v14 = (unsigned int)v13;
  v33 = *(_QWORD *)&v8[4 * (unsigned int)v13] >= 0LL;
  if ( v33 )
  {
    v15 = *(unsigned int *)&v8[4 * (unsigned int)v13];
    v8 = &word_180000002;
    lpProcName = (char *)&word_180000002 + v15;
  }
  else
  {
    LODWORD(lpProcName) = (unsigned __int16)v8[4 * (unsigned int)v13];
  }
  v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
  ProcAddress = 0;
  if ( !_pfnDefaultDliFailureHook2
    || (v18 = _pfnDefaultDliFailureHook2(0, v29),
        v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2,
        (ProcAddress = (FARPROC)v18) == 0) )
  {
    if ( !Library )
    {
      if ( !v16 || (Library = (HMODULE)v16(1, v29)) == 0 )
      {
        Library = LoadLibraryExA(lpLibFileName, 0, 0);
        if ( !Library )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, v29)) == 0 )
          {
            Arguments = (ULONG_PTR)v29;
            DloadReleaseSectionWriteAccess(v14, v8, v19);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v37;
          }
        }
      }
      v20 = _InterlockedCompareExchange64(v5, (signed __int64)Library, 0);
      if ( v20 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v20 )
          Library = (HMODULE)v20;
      }
      else if ( Library != (HMODULE)-1LL )
      {
        if ( a1->rvaUnloadIAT )
        {
          ProcessHeap = GetProcessHeap();
          v22 = (struct UnloadInfo *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          if ( v22 )
          {
            v22->pidd = a1;
            v14 = (unsigned __int64)_puiHead;
            v22->puiNext = _puiHead;
            _puiHead = v22;
          }
        }
      }
      v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
    }
    v36 = Library;
    if ( v16 )
    {
      v23 = v16(2, v29);
      v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
      ProcAddress = (FARPROC)v23;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v24 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v24) != 17744)
        || (v14 = (unsigned int)Arguments, *(_DWORD *)((char *)Library + v24 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + v24 + 48)
        || (ProcAddress = *(FARPROC *)&v9[8 * (unsigned int)v13]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, lpProcName);
        if ( !ProcAddress )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (ProcAddress = (FARPROC)_pfnDefaultDliFailureHook2(4, v29)) == 0 )
          {
            Arguments = (ULONG_PTR)v29;
            DloadReleaseSectionWriteAccess(v14, v8, v25);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            DloadAcquireSectionWriteAccess(v27, v26, v28);
            ProcAddress = v37;
          }
        }
        v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
      }
    }
    *(_QWORD *)a2 = ProcAddress;
  }
  if ( v16 )
  {
    LastError = 0;
    v36 = Library;
    v37 = ProcAddress;
    v16(5, v29);
  }
  DloadReleaseSectionWriteAccess(v14, v8, v16);
  return ProcAddress;
}

```

## disassembly

```asm
0x180015ba0  mov     [rsp-28h+arg_8], rbx
0x180015ba5  mov     [rsp-28h+arg_10], rsi
0x180015baa  mov     [rsp-28h+arg_18], rdi
0x180015baf  push    rbp
0x180015bb0  push    r12
0x180015bb2  push    r13
0x180015bb4  push    r14
0x180015bb6  push    r15
0x180015bb8  mov     rbp, rsp
0x180015bbb  sub     rsp, 70h
0x180015bbf  xor     eax, eax
0x180015bc1  mov     r12, rdx
0x180015bc4  and     [rbp+var_2C], eax
0x180015bc7  mov     rsi, rcx
0x180015bca  mov     [rbp+var_4C], eax
0x180015bcd  and     [rbp+var_4C], eax
0x180015bd0  call    DloadAcquireSectionWriteAccess
0x180015bd5  mov     eax, [rsi+4]
0x180015bd8  lea     r8, __ImageBase
0x180015bdf  mov     r15d, [rsi+8]
0x180015be3  add     rax, r8
0x180015be6  mov     ecx, [rsi+0Ch]
0x180015be9  add     r15, r8
0x180015bec  mov     edx, [rsi+10h]
0x180015bef  add     rcx, r8
0x180015bf2  mov     r13d, [rsi+14h]
0x180015bf6  add     rdx, r8
0x180015bf9  and     [rbp+var_30], 0
0x180015bfd  add     r13, r8
0x180015c00  and     [rbp+lpProcName], 0
0x180015c05  and     [rbp+var_20], 0
0x180015c0a  and     [rbp+var_18], 0
0x180015c0f  and     [rbp+var_10], 0
0x180015c13  mov     r8d, [rsi+1Ch]
0x180015c17  mov     [rbp+lpLibFileName], rax
0x180015c1b  mov     eax, [rsi]
0x180015c1d  mov     dword ptr [rbp+Arguments], r8d
0x180015c21  mov     [rbp+var_50], 48h ; 'H'
0x180015c28  mov     [rbp+var_48], rsi
0x180015c2c  mov     [rbp+var_40], r12
0x180015c30  test    al, 1
0x180015c32  jnz     short loc_180015C63
0x180015c34  lea     rax, [rbp+var_50]
0x180015c38  mov     [rbp+Arguments], rax
0x180015c3c  call    DloadReleaseSectionWriteAccess
0x180015c41  xor     edx, edx; dwExceptionFlags
0x180015c43  lea     r9, [rbp+Arguments]; lpArguments
0x180015c47  mov     ecx, 0C06D0057h; dwExceptionCode
0x180015c4c  lea     r8d, [rdx+1]; nNumberOfArguments
0x180015c50  call    cs:__imp_RaiseException
0x180015c57  nop     dword ptr [rax+rax+00h]
0x180015c5c  xor     eax, eax
0x180015c5e  jmp     loc_180015EFE
0x180015c63  mov     rbx, [r15]
0x180015c66  xor     eax, eax
0x180015c68  mov     r14, r12
0x180015c6b  sub     r14, rcx
0x180015c6e  sar     r14, 3
0x180015c72  mov     ecx, r14d
0x180015c75  cmp     [rdx+rcx*8], rax
0x180015c79  setnl   al
0x180015c7c  mov     [rbp+var_30], eax
0x180015c7f  test    eax, eax
0x180015c81  jz      short loc_180015C96
0x180015c83  mov     eax, [rdx+rcx*8]
0x180015c86  lea     rdx, word_180000002
0x180015c8d  add     rax, rdx
0x180015c90  mov     [rbp+lpProcName], rax
0x180015c94  jmp     short loc_180015C9D
0x180015c96  movzx   eax, word ptr [rdx+rcx*8]
0x180015c9a  mov     dword ptr [rbp+lpProcName], eax
0x180015c9d  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180015ca4  xor     edi, edi
0x180015ca6  test    r8, r8
0x180015ca9  jz      short loc_180015CCC
0x180015cab  lea     rdx, [rbp+var_50]
0x180015caf  xor     ecx, ecx
0x180015cb1  mov     rax, r8
0x180015cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cb9  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180015cc0  mov     rdi, rax
0x180015cc3  test    rax, rax
0x180015cc6  jnz     loc_180015ED4
0x180015ccc  test    rbx, rbx
0x180015ccf  jnz     loc_180015DE9
0x180015cd5  test    r8, r8
0x180015cd8  jz      short loc_180015CF1
0x180015cda  lea     rdx, [rbp+var_50]
0x180015cde  mov     rax, r8
0x180015ce1  lea     ecx, [rbx+1]
0x180015ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce9  mov     rbx, rax
0x180015cec  test    rax, rax
0x180015cef  jnz     short loc_180015D6E
0x180015cf1  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180015cf5  xor     r8d, r8d; dwFlags
0x180015cf8  xor     edx, edx; hFile
0x180015cfa  call    cs:__imp_LoadLibraryExA
0x180015d01  nop     dword ptr [rax+rax+00h]
0x180015d06  mov     rbx, rax
0x180015d09  test    rax, rax
0x180015d0c  jnz     short loc_180015D6E
0x180015d0e  call    cs:__imp_GetLastError
0x180015d15  nop     dword ptr [rax+rax+00h]
0x180015d1a  mov     [rbp+var_10], eax
0x180015d1d  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180015d24  test    rax, rax
0x180015d27  jz      short loc_180015D3D
0x180015d29  lea     rdx, [rbp+var_50]
0x180015d2d  lea     ecx, [rbx+3]
0x180015d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d35  mov     rbx, rax
0x180015d38  test    rax, rax
0x180015d3b  jnz     short loc_180015D6E
0x180015d3d  lea     rax, [rbp+var_50]
0x180015d41  mov     [rbp+Arguments], rax
0x180015d45  call    DloadReleaseSectionWriteAccess
0x180015d4a  xor     edx, edx; dwExceptionFlags
0x180015d4c  lea     r9, [rbp+Arguments]; lpArguments
0x180015d50  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180015d55  lea     r8d, [rdx+1]; nNumberOfArguments
0x180015d59  call    cs:__imp_RaiseException
0x180015d60  nop     dword ptr [rax+rax+00h]
0x180015d65  mov     rax, [rbp+var_18]
0x180015d69  jmp     loc_180015EFE
0x180015d6e  xor     eax, eax
0x180015d70  lock cmpxchg [r15], rbx
0x180015d75  mov     r15, rax
0x180015d78  jnz     short loc_180015DC6
0x180015d7a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180015d7e  jz      short loc_180015DE2
0x180015d80  cmp     dword ptr [rsi+18h], 0
0x180015d84  jz      short loc_180015DE2
0x180015d86  call    cs:__imp_GetProcessHeap
0x180015d8d  nop     dword ptr [rax+rax+00h]
0x180015d92  mov     edx, 8; dwFlags
0x180015d97  mov     rcx, rax; hHeap
0x180015d9a  lea     r8d, [rdx+8]; dwBytes
0x180015d9e  call    cs:__imp_HeapAlloc
0x180015da5  nop     dword ptr [rax+rax+00h]
0x180015daa  test    rax, rax
0x180015dad  jz      short loc_180015DE2
0x180015daf  mov     [rax+8], rsi
0x180015db3  mov     rcx, cs:__puiHead
0x180015dba  mov     [rax], rcx
0x180015dbd  mov     cs:__puiHead, rax
0x180015dc4  jmp     short loc_180015DE2
0x180015dc6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180015dca  jz      short loc_180015DDB
0x180015dcc  mov     rcx, rbx; hLibModule
0x180015dcf  call    cs:__imp_FreeLibrary
0x180015dd6  nop     dword ptr [rax+rax+00h]
0x180015ddb  cmp     rbx, r15
0x180015dde  cmovnz  rbx, r15
0x180015de2  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180015de9  mov     [rbp+var_20], rbx
0x180015ded  test    r8, r8
0x180015df0  jz      short loc_180015E0D
0x180015df2  lea     rdx, [rbp+var_50]
0x180015df6  mov     ecx, 2
0x180015dfb  mov     rax, r8
0x180015dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e03  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180015e0a  mov     rdi, rax
0x180015e0d  test    rdi, rdi
0x180015e10  jnz     loc_180015ED0
0x180015e16  cmp     [rsi+14h], edi
0x180015e19  jz      short loc_180015E4E
0x180015e1b  cmp     [rsi+1Ch], edi
0x180015e1e  jz      short loc_180015E4E
0x180015e20  movsxd  rax, dword ptr [rbx+3Ch]
0x180015e24  cmp     dword ptr [rax+rbx], 4550h
0x180015e2b  jnz     short loc_180015E4E
0x180015e2d  mov     ecx, dword ptr [rbp+Arguments]
0x180015e30  cmp     [rax+rbx+8], ecx
0x180015e34  jnz     short loc_180015E4E
0x180015e36  cmp     rbx, [rax+rbx+30h]
0x180015e3b  jnz     short loc_180015E4E
0x180015e3d  mov     eax, r14d
0x180015e40  mov     rdi, [r13+rax*8+0]
0x180015e45  test    rdi, rdi
0x180015e48  jnz     loc_180015ED0
0x180015e4e  mov     rdx, [rbp+lpProcName]; lpProcName
0x180015e52  mov     rcx, rbx; hModule
0x180015e55  call    cs:__imp_GetProcAddress
0x180015e5c  nop     dword ptr [rax+rax+00h]
0x180015e61  mov     rdi, rax
0x180015e64  test    rax, rax
0x180015e67  jnz     short loc_180015EC9
0x180015e69  call    cs:__imp_GetLastError
0x180015e70  nop     dword ptr [rax+rax+00h]
0x180015e75  mov     [rbp+var_10], eax
0x180015e78  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180015e7f  test    rax, rax
0x180015e82  jz      short loc_180015E98
0x180015e84  lea     rdx, [rbp+var_50]
0x180015e88  lea     ecx, [rdi+4]
0x180015e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e90  mov     rdi, rax
0x180015e93  test    rax, rax
0x180015e96  jnz     short loc_180015EC9
0x180015e98  lea     rax, [rbp+var_50]
0x180015e9c  mov     [rbp+Arguments], rax
0x180015ea0  call    DloadReleaseSectionWriteAccess
0x180015ea5  xor     edx, edx; dwExceptionFlags
0x180015ea7  lea     r9, [rbp+Arguments]; lpArguments
0x180015eab  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180015eb0  lea     r8d, [rdx+1]; nNumberOfArguments
0x180015eb4  call    cs:__imp_RaiseException
0x180015ebb  nop     dword ptr [rax+rax+00h]
0x180015ec0  call    DloadAcquireSectionWriteAccess
0x180015ec5  mov     rdi, [rbp+var_18]
0x180015ec9  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180015ed0  mov     [r12], rdi
0x180015ed4  test    r8, r8
0x180015ed7  jz      short loc_180015EF6
0x180015ed9  and     [rbp+var_10], 0
0x180015edd  lea     rdx, [rbp+var_50]
0x180015ee1  mov     ecx, 5
0x180015ee6  mov     [rbp+var_20], rbx
0x180015eea  mov     rax, r8
0x180015eed  mov     [rbp+var_18], rdi
0x180015ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ef6  call    DloadReleaseSectionWriteAccess
0x180015efb  mov     rax, rdi
0x180015efe  lea     r11, [rsp+70h+var_s0]
0x180015f03  mov     rbx, [r11+38h]
0x180015f07  mov     rsi, [r11+40h]
0x180015f0b  mov     rdi, [r11+48h]
0x180015f0f  mov     rsp, r11
0x180015f12  pop     r15
0x180015f14  pop     r14
0x180015f16  pop     r13
0x180015f18  pop     r12
0x180015f1a  pop     rbp
0x180015f1b  retn
```

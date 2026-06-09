# CRWLock2T<CEmptyType>::Init(void)

- ea: `0x180003ed8`
- end: `0x180004054`
- name: `?Init@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ`
- size: `380`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180019b4c`
- `0x18001b530`
- `0x18001b6cc`
- `0x18001b864`
- `0x18001ba44`
- `0x18001e0a8`
- `0x180020e90`
- `0x180038f90`

## callees

- `0x180003520`
- `0x180003ed8`
- `0x180004288`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004024`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004038`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004024`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004038`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003ef2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003ef2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003f96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fa6`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180003f47`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180003f47`

## pseudocode

```c
__int64 __fastcall CRWLock2T<CEmptyType>::Init(__int64 a1)
{
  HANDLE EventW; // rbp
  void *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // esi
  void *v6; // rbx
  HANDLE SemaphoreW; // r15
  signed int v8; // eax
  signed int v9; // eax
  void *v10; // rcx
  void *v11; // rcx

  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    v3 = 0;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    v6 = 0;
    goto LABEL_25;
  }
  SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
  if ( !SemaphoreW )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    v3 = 0;
LABEL_13:
    v6 = EventW;
    goto LABEL_25;
  }
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 8), 0) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    v3 = SemaphoreW;
    goto LABEL_13;
  }
  *(_DWORD *)a1 = 1;
  v5 = 0;
  v10 = *(void **)(a1 + 48);
  v6 = 0;
  if ( v10 )
    CloseHandle(v10);
  *(_QWORD *)(a1 + 48) = EventW;
  v3 = 0;
  v11 = *(void **)(a1 + 56);
  if ( v11 )
    CloseHandle(v11);
  *(_QWORD *)(a1 + 56) = SemaphoreW;
LABEL_25:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v3 )
    CloseHandle(v3);
  if ( v6 )
    CloseHandle(v6);
  return v5;
}

```

## disassembly

```asm
0x180003ed8  push    rbx
0x180003eda  push    rbp
0x180003edb  push    rsi
0x180003edc  push    rdi
0x180003edd  push    r14
0x180003edf  push    r15
0x180003ee1  sub     rsp, 28h
0x180003ee5  mov     r14, rcx
0x180003ee8  xor     r9d, r9d; lpName
0x180003eeb  xor     ecx, ecx; lpEventAttributes
0x180003eed  xor     r8d, r8d; bInitialState
0x180003ef0  xor     edx, edx; bManualReset
0x180003ef2  call    cs:__imp_CreateEventW
0x180003ef9  nop     dword ptr [rax+rax+00h]
0x180003efe  mov     rbp, rax
0x180003f01  test    rax, rax
0x180003f04  jnz     short loc_180003F3A
0x180003f06  xor     edi, edi
0x180003f08  call    cs:__imp_GetLastError
0x180003f0f  nop     dword ptr [rax+rax+00h]
0x180003f14  mov     esi, eax
0x180003f16  test    eax, eax
0x180003f18  jnz     short loc_180003F21
0x180003f1a  mov     esi, 80004005h
0x180003f1f  jmp     short loc_180003F2C
0x180003f21  jle     short loc_180003F2C
0x180003f23  movzx   esi, ax
0x180003f26  or      esi, 80070000h
0x180003f2c  mov     ecx, esi
0x180003f2e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003f33  xor     ebx, ebx
0x180003f35  jmp     loc_180004015
0x180003f3a  xor     r9d, r9d; lpName
0x180003f3d  xor     edx, edx; lInitialCount
0x180003f3f  xor     ecx, ecx; lpSemaphoreAttributes
0x180003f41  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180003f47  call    cs:__imp_CreateSemaphoreW
0x180003f4e  nop     dword ptr [rax+rax+00h]
0x180003f53  mov     r15, rax
0x180003f56  test    rax, rax
0x180003f59  jnz     short loc_180003F90
0x180003f5b  call    cs:__imp_GetLastError
0x180003f62  nop     dword ptr [rax+rax+00h]
0x180003f67  mov     esi, eax
0x180003f69  test    eax, eax
0x180003f6b  jnz     short loc_180003F74
0x180003f6d  mov     esi, 80004005h
0x180003f72  jmp     short loc_180003F7F
0x180003f74  jle     short loc_180003F7F
0x180003f76  movzx   esi, ax
0x180003f79  or      esi, 80070000h
0x180003f7f  mov     ecx, esi
0x180003f81  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003f86  xor     edi, edi
0x180003f88  mov     rbx, rbp
0x180003f8b  jmp     loc_180004015
0x180003f90  lea     rcx, [r14+8]; lpCriticalSection
0x180003f94  xor     edx, edx; dwSpinCount
0x180003f96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003f9d  nop     dword ptr [rax+rax+00h]
0x180003fa2  test    eax, eax
0x180003fa4  jnz     short loc_180003FD6
0x180003fa6  call    cs:__imp_GetLastError
0x180003fad  nop     dword ptr [rax+rax+00h]
0x180003fb2  mov     esi, eax
0x180003fb4  test    eax, eax
0x180003fb6  jnz     short loc_180003FBF
0x180003fb8  mov     esi, 80004005h
0x180003fbd  jmp     short loc_180003FCA
0x180003fbf  jle     short loc_180003FCA
0x180003fc1  movzx   esi, ax
0x180003fc4  or      esi, 80070000h
0x180003fca  mov     ecx, esi
0x180003fcc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003fd1  mov     rdi, r15
0x180003fd4  jmp     short loc_180003F88
0x180003fd6  mov     dword ptr [r14], 1
0x180003fdd  xor     esi, esi
0x180003fdf  mov     rcx, [r14+30h]; hObject
0x180003fe3  xor     ebx, ebx
0x180003fe5  test    rcx, rcx
0x180003fe8  jz      short loc_180003FF6
0x180003fea  call    cs:__imp_CloseHandle
0x180003ff1  nop     dword ptr [rax+rax+00h]
0x180003ff6  mov     [r14+30h], rbp
0x180003ffa  xor     edi, edi
0x180003ffc  mov     rcx, [r14+38h]; hObject
0x180004000  test    rcx, rcx
0x180004003  jz      short loc_180004011
0x180004005  call    cs:__imp_CloseHandle
0x18000400c  nop     dword ptr [rax+rax+00h]
0x180004011  mov     [r14+38h], r15
0x180004015  mov     ecx, esi
0x180004017  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000401c  test    rdi, rdi
0x18000401f  jz      short loc_180004030
0x180004021  mov     rcx, rdi; hObject
0x180004024  call    cs:__imp_CloseHandle
0x18000402b  nop     dword ptr [rax+rax+00h]
0x180004030  test    rbx, rbx
0x180004033  jz      short loc_180004044
0x180004035  mov     rcx, rbx; hObject
0x180004038  call    cs:__imp_CloseHandle
0x18000403f  nop     dword ptr [rax+rax+00h]
0x180004044  mov     eax, esi
0x180004046  add     rsp, 28h
0x18000404a  pop     r15
0x18000404c  pop     r14
0x18000404e  pop     rdi
0x18000404f  pop     rsi
0x180004050  pop     rbp
0x180004051  pop     rbx
0x180004052  retn
```

# CSafeThreadsInfo::Initialize(ulong (*)(void *),void *,int)

- ea: `0x180038d30`
- end: `0x180038eb1`
- name: `?Initialize@CSafeThreadsInfo@@AEAAJP6AKPEAX@Z0H@Z`
- size: `385`
- prototype: `__int64 __fastcall(CSafeThreadsInfo *__hidden this, unsigned int (*)(void *), void *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180039a0c`

## callees

- `0x180003520`
- `0x180004288`
- `0x180038d30`
- `0x18003c560`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038e4e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038e4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180038dd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180038dd7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038e36`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e63`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180038d82`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180038d82`

## pseudocode

```c
__int64 __fastcall CSafeThreadsInfo::Initialize(CSafeThreadsInfo *this, unsigned int (*a2)(void *), void *a3, int a4)
{
  signed int LastError; // eax
  unsigned int v6; // edi
  unsigned int v7; // ebx
  __int64 v8; // rcx
  DWORD ModuleFileNameW; // eax
  signed int v10; // eax
  HMODULE Library; // rax
  HMODULE v12; // rcx
  HMODULE v13; // r14
  signed int v14; // eax
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+20h] [rbp-278h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-248h] BYREF

  *(_OWORD *)&Buffer.BaseAddress = 0;
  *((_QWORD *)this + 2) = a3;
  *(_OWORD *)&Buffer.AllocationProtect = 0;
  *((_QWORD *)this + 1) = CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::ThreadProc;
  *(_OWORD *)&Buffer.State = 0;
  *((_DWORD *)this + 8) = a4;
  if ( !VirtualQuery(
          CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::ThreadProc,
          &Buffer,
          0x30u) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    v7 = v6;
    v8 = v6;
    goto LABEL_7;
  }
  ModuleFileNameW = GetModuleFileNameW((HMODULE)Buffer.AllocationBase, Filename, 0x104u);
  Filename[259] = 0;
  if ( !ModuleFileNameW )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    if ( (v7 & 0x80000000) != 0 )
      goto LABEL_17;
LABEL_19:
    Library = LoadLibraryExW(Filename, 0, 0);
    v12 = (HMODULE)*((_QWORD *)this + 3);
    v13 = Library;
    if ( v12 )
      FreeLibrary(v12);
    if ( v13 )
    {
      *((_QWORD *)this + 3) = v13;
      goto LABEL_27;
    }
    *((_QWORD *)this + 3) = 0;
    v14 = GetLastError();
    v7 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    goto LABEL_17;
  }
  if ( ModuleFileNameW < 0x104 )
  {
    v7 = 0;
    goto LABEL_19;
  }
  v7 = -2147024774;
LABEL_17:
  v8 = v7;
LABEL_7:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
LABEL_27:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return v7;
}

```

## disassembly

```asm
0x180038d30  push    rbx
0x180038d32  push    rbp
0x180038d33  push    rdi
0x180038d34  push    r14
0x180038d36  sub     rsp, 278h
0x180038d3d  mov     rax, cs:__security_cookie
0x180038d44  xor     rax, rsp
0x180038d47  mov     [rsp+298h+var_38], rax
0x180038d4f  mov     rbp, rcx
0x180038d52  lea     rdx, [rsp+298h+Buffer]; lpBuffer
0x180038d57  xorps   xmm0, xmm0
0x180038d5a  lea     rcx, ?ThreadProc@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@CAKPEAX@Z; lpAddress
0x180038d61  movups  xmmword ptr [rsp+298h+Buffer.BaseAddress], xmm0
0x180038d66  mov     [rbp+10h], r8
0x180038d6a  mov     r8d, 30h ; '0'; dwLength
0x180038d70  movups  xmmword ptr [rsp+298h+Buffer.AllocationProtect], xmm0
0x180038d75  mov     [rbp+8], rcx
0x180038d79  movups  xmmword ptr [rsp+298h+Buffer.State], xmm0
0x180038d7e  mov     [rbp+20h], r9d
0x180038d82  call    cs:__imp_VirtualQuery
0x180038d89  nop     dword ptr [rax+rax+00h]
0x180038d8e  test    rax, rax
0x180038d91  jnz     short loc_180038DC5
0x180038d93  call    cs:__imp_GetLastError
0x180038d9a  nop     dword ptr [rax+rax+00h]
0x180038d9f  mov     edi, eax
0x180038da1  test    eax, eax
0x180038da3  jnz     short loc_180038DAC
0x180038da5  mov     edi, 80004005h
0x180038daa  jmp     short loc_180038DB7
0x180038dac  jle     short loc_180038DB7
0x180038dae  movzx   edi, ax
0x180038db1  or      edi, 80070000h
0x180038db7  mov     ebx, edi
0x180038db9  mov     ecx, edi
0x180038dbb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038dc0  jmp     loc_180038E8A
0x180038dc5  mov     rcx, [rsp+298h+Buffer.AllocationBase]; hModule
0x180038dca  lea     rdx, [rsp+298h+Filename]; lpFilename
0x180038dcf  mov     ebx, 104h
0x180038dd4  mov     r8d, ebx; nSize
0x180038dd7  call    cs:__imp_GetModuleFileNameW
0x180038dde  nop     dword ptr [rax+rax+00h]
0x180038de3  xor     ecx, ecx
0x180038de5  mov     edi, 80004005h
0x180038dea  mov     [rsp+298h+var_42], cx
0x180038df2  test    eax, eax
0x180038df4  jnz     short loc_180038E1D
0x180038df6  call    cs:__imp_GetLastError
0x180038dfd  nop     dword ptr [rax+rax+00h]
0x180038e02  mov     ebx, eax
0x180038e04  test    eax, eax
0x180038e06  jnz     short loc_180038E0C
0x180038e08  mov     ebx, edi
0x180038e0a  jmp     short loc_180038E17
0x180038e0c  jle     short loc_180038E17
0x180038e0e  movzx   ebx, ax
0x180038e11  or      ebx, 80070000h
0x180038e17  test    ebx, ebx
0x180038e19  jns     short loc_180038E2C
0x180038e1b  jmp     short loc_180038E26
0x180038e1d  cmp     eax, ebx
0x180038e1f  jb      short loc_180038E2A
0x180038e21  mov     ebx, 8007007Ah
0x180038e26  mov     ecx, ebx
0x180038e28  jmp     short loc_180038DBB
0x180038e2a  xor     ebx, ebx
0x180038e2c  xor     r8d, r8d; dwFlags
0x180038e2f  lea     rcx, [rsp+298h+Filename]; lpLibFileName
0x180038e34  xor     edx, edx; hFile
0x180038e36  call    cs:__imp_LoadLibraryExW
0x180038e3d  nop     dword ptr [rax+rax+00h]
0x180038e42  mov     rcx, [rbp+18h]; hLibModule
0x180038e46  mov     r14, rax
0x180038e49  test    rcx, rcx
0x180038e4c  jz      short loc_180038E5A
0x180038e4e  call    cs:__imp_FreeLibrary
0x180038e55  nop     dword ptr [rax+rax+00h]
0x180038e5a  test    r14, r14
0x180038e5d  jnz     short loc_180038E86
0x180038e5f  mov     [rbp+18h], r14
0x180038e63  call    cs:__imp_GetLastError
0x180038e6a  nop     dword ptr [rax+rax+00h]
0x180038e6f  mov     ebx, eax
0x180038e71  test    eax, eax
0x180038e73  jnz     short loc_180038E79
0x180038e75  mov     ebx, edi
0x180038e77  jmp     short loc_180038E26
0x180038e79  jle     short loc_180038E26
0x180038e7b  movzx   ebx, ax
0x180038e7e  or      ebx, 80070000h
0x180038e84  jmp     short loc_180038E26
0x180038e86  mov     [rbp+18h], r14
0x180038e8a  mov     ecx, ebx
0x180038e8c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038e91  mov     eax, ebx
0x180038e93  mov     rcx, [rsp+298h+var_38]
0x180038e9b  xor     rcx, rsp; StackCookie
0x180038e9e  call    __security_check_cookie
0x180038ea3  add     rsp, 278h
0x180038eaa  pop     r14
0x180038eac  pop     rdi
0x180038ead  pop     rbp
0x180038eae  pop     rbx
0x180038eaf  retn
```

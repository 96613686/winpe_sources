# WscRemediateProduct(CThirdPartyManager *,RemediationAction,ushort const *,ushort const *,ulong,int *)

- ea: `0x18003dfd4`
- end: `0x18003e139`
- name: `?WscRemediateProduct@@YAJPEAVCThirdPartyManager@@W4RemediationAction@@PEBG2KPEAH@Z`
- size: `357`
- prototype: `__int64 __fastcall(__int64, int, __int64, const WCHAR *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003c5ec`

## callees

- `0x18003de58`
- `0x18003dfd4`
- `0x18003fbf2`

## import_xrefs

- `msvcrt!free` at `0x18003e121`
- `msvcrt!free` at `0x18003e121`
- `msvcrt!malloc` at `0x18003e03d`
- `msvcrt!malloc` at `0x18003e03d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003e0c2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003e0c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e0e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e0f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e0e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e0f3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003e061`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003e061`

## pseudocode

```c
__int64 __fastcall WscRemediateProduct(__int64 a1, int a2, __int64 a3, const WCHAR *a4, unsigned int a5, __int64 a6)
{
  unsigned int v10; // ebx
  WCHAR *v11; // rsi
  unsigned int v12; // ebx
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  signed int LastError; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-A8h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( a2 )
  {
    if ( a2 != 1 )
      return (unsigned int)-2147024736;
    v11 = (WCHAR *)L" /disable";
    v12 = 0;
  }
  else
  {
    v11 = L" /enable";
    v12 = 4096;
  }
  v13 = (WCHAR *)malloc(0x208u);
  v14 = v13;
  if ( v13 )
  {
    if ( ExpandEnvironmentStringsW(a4, v13, 0x104u) < 0x104 )
    {
      StartupInfo.cb = 104;
      if ( CreateProcessW(v14, v11, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
        v10 = WaitForProductState(a1, a3, v12, a5, a6);
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v10 = -2147024774;
    }
    free(v14);
  }
  else
  {
    return (unsigned int)-2147024888;
  }
  return v10;
}

```

## disassembly

```asm
0x18003dfd4  push    rbx
0x18003dfd6  push    rbp
0x18003dfd7  push    rsi
0x18003dfd8  push    rdi
0x18003dfd9  push    r14
0x18003dfdb  push    r15
0x18003dfdd  sub     rsp, 0E8h
0x18003dfe4  mov     ebx, edx
0x18003dfe6  mov     r14, r8
0x18003dfe9  xor     edx, edx; Val
0x18003dfeb  mov     r15, rcx
0x18003dfee  lea     rcx, [rsp+118h+StartupInfo]; void *
0x18003dff3  mov     rbp, r9
0x18003dff6  lea     r8d, [rdx+68h]; Size
0x18003dffa  call    memset_0
0x18003dfff  xor     eax, eax
0x18003e001  xorps   xmm0, xmm0
0x18003e004  mov     qword ptr [rsp+118h+ProcessInformation.dwProcessId], rax
0x18003e009  movups  xmmword ptr [rsp+118h+ProcessInformation.hProcess], xmm0
0x18003e00e  test    ebx, ebx
0x18003e010  jz      short loc_18003E02C
0x18003e012  cmp     ebx, 1
0x18003e015  jz      short loc_18003E021
0x18003e017  mov     ebx, 800700A0h
0x18003e01c  jmp     loc_18003E127
0x18003e021  lea     rsi, CommandLine; " /disable"
0x18003e028  xor     ebx, ebx
0x18003e02a  jmp     short loc_18003E038
0x18003e02c  lea     rsi, aEnable; " /enable"
0x18003e033  mov     ebx, 1000h
0x18003e038  mov     ecx, 208h; Size
0x18003e03d  call    cs:__imp_malloc
0x18003e043  mov     rdi, rax
0x18003e046  test    rax, rax
0x18003e049  jnz     short loc_18003E055
0x18003e04b  mov     ebx, 80070008h
0x18003e050  jmp     loc_18003E127
0x18003e055  mov     r8d, 104h; nSize
0x18003e05b  mov     rdx, rdi; lpDst
0x18003e05e  mov     rcx, rbp; lpSrc
0x18003e061  call    cs:__imp_ExpandEnvironmentStringsW
0x18003e067  cmp     eax, 104h
0x18003e06c  jb      short loc_18003E078
0x18003e06e  mov     ebx, 8007007Ah
0x18003e073  jmp     loc_18003E11E
0x18003e078  lea     rax, [rsp+118h+ProcessInformation]
0x18003e07d  mov     [rsp+118h+StartupInfo.cb], 68h ; 'h'
0x18003e085  mov     [rsp+118h+lpProcessInformation], rax; lpProcessInformation
0x18003e08a  xor     r9d, r9d; lpThreadAttributes
0x18003e08d  lea     rax, [rsp+118h+StartupInfo]
0x18003e092  xor     r8d, r8d; lpProcessAttributes
0x18003e095  mov     [rsp+118h+lpStartupInfo], rax; lpStartupInfo
0x18003e09a  mov     rdx, rsi; lpCommandLine
0x18003e09d  mov     [rsp+118h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18003e0a6  mov     rcx, rdi; lpApplicationName
0x18003e0a9  mov     [rsp+118h+lpEnvironment], 0; lpEnvironment
0x18003e0b2  mov     [rsp+118h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x18003e0ba  mov     [rsp+118h+bInheritHandles], 0; bInheritHandles
0x18003e0c2  call    cs:__imp_CreateProcessW
0x18003e0c8  test    eax, eax
0x18003e0ca  jnz     short loc_18003E0E3
0x18003e0cc  call    cs:__imp_GetLastError
0x18003e0d2  mov     ebx, eax
0x18003e0d4  test    eax, eax
0x18003e0d6  jle     short loc_18003E11E
0x18003e0d8  movzx   ebx, ax
0x18003e0db  or      ebx, 80070000h
0x18003e0e1  jmp     short loc_18003E11E
0x18003e0e3  mov     rcx, [rsp+118h+ProcessInformation.hProcess]; hObject
0x18003e0e8  call    cs:__imp_CloseHandle
0x18003e0ee  mov     rcx, [rsp+118h+ProcessInformation.hThread]; hObject
0x18003e0f3  call    cs:__imp_CloseHandle
0x18003e0f9  mov     rax, [rsp+118h+arg_28]
0x18003e101  mov     r8d, ebx
0x18003e104  mov     r9d, [rsp+118h+arg_20]
0x18003e10c  mov     rdx, r14
0x18003e10f  mov     rcx, r15
0x18003e112  mov     qword ptr [rsp+118h+bInheritHandles], rax
0x18003e117  call    ?WaitForProductState@@YAKPEAVCThirdPartyManager@@PEBGW4ProductState@@KPEAH@Z; WaitForProductState(CThirdPartyManager *,ushort const *,ProductState,ulong,int *)
0x18003e11c  mov     ebx, eax
0x18003e11e  mov     rcx, rdi; Block
0x18003e121  call    cs:__imp_free
0x18003e127  mov     eax, ebx
0x18003e129  add     rsp, 0E8h
0x18003e130  pop     r15
0x18003e132  pop     r14
0x18003e134  pop     rdi
0x18003e135  pop     rsi
0x18003e136  pop     rbp
0x18003e137  pop     rbx
0x18003e138  retn
```

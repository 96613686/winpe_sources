# PER_CPU<_RTL_SRWLOCK>::GetProcessorInformation(ulong *,ulong *)

- ea: `0x180012d44`
- end: `0x180012f81`
- name: `?GetProcessorInformation@?$PER_CPU@U_RTL_SRWLOCK@@@@CAJPEAK0@Z`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800131f0`

## callees

- `0x180012d44`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ede`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012d9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012d9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012d7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012d7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012de4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012e97`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012de4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012e97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f60`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180012f3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180012f3c`

## pseudocode

```c
__int64 __fastcall PER_CPU<_RTL_SRWLOCK>::GetProcessorInformation(_DWORD *a1, DWORD *a2)
{
  unsigned __int16 *v3; // rbx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v7)(__int64, unsigned __int16 *, SIZE_T *); // rsi
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v10; // rax
  HANDLE v11; // rax
  HANDLE v12; // rax
  signed int LastError; // eax
  unsigned int v14; // edi
  unsigned int v15; // ebx
  HANDLE v16; // rax
  unsigned __int16 *v17; // rax
  signed int v18; // eax
  unsigned int v19; // r8d
  DWORD v20; // edx
  unsigned int i; // r9d
  DWORD v22; // eax
  HANDLE v23; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-30h] BYREF
  SIZE_T dwBytes; // [rsp+90h] [rbp+40h] BYREF

  v3 = 0;
  LODWORD(dwBytes) = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  ModuleHandleW = GetModuleHandleW(L"kernel32");
  if ( !ModuleHandleW
    || (ProcAddress = GetProcAddress(ModuleHandleW, "GetLogicalProcessorInformationEx"),
        (v7 = (unsigned int (__fastcall *)(__int64, unsigned __int16 *, SIZE_T *))ProcAddress) == 0) )
  {
LABEL_29:
    GetSystemInfo(&SystemInfo);
    v14 = 0;
    *a2 = SystemInfo.dwNumberOfProcessors;
    *a1 = 64;
    goto LABEL_30;
  }
  if ( ((unsigned int (__fastcall *)(__int64, _QWORD, SIZE_T *))ProcAddress)(2, 0, &dwBytes) )
    goto LABEL_9;
  if ( GetLastError() != 122 )
    goto LABEL_9;
  if ( !(_DWORD)dwBytes )
    goto LABEL_9;
  v8 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v8);
  v3 = v10;
  if ( !v10 )
    goto LABEL_9;
  if ( !v7(2, v10, &dwBytes) )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v3);
    v3 = 0;
    goto LABEL_9;
  }
  if ( v3[5] <= 0x40u )
  {
LABEL_9:
    *a1 = 64;
    if ( !v3 )
      goto LABEL_11;
    goto LABEL_10;
  }
  *a1 = v3[5];
LABEL_10:
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v3);
  v3 = 0;
LABEL_11:
  LODWORD(dwBytes) = 0;
  if ( v7(4, v3, &dwBytes) )
  {
LABEL_22:
    if ( v3 )
    {
      v19 = v3[5];
      if ( v3[5] )
      {
        v20 = *((unsigned __int8 *)v3 + 32);
        for ( i = 1; i < v19; v20 = v22 )
        {
          v22 = LOBYTE(v3[24 * i + 16]);
          if ( v22 <= v20 )
            v22 = v20;
          ++i;
        }
        *a2 = v20;
        v14 = 0;
        goto LABEL_31;
      }
    }
    goto LABEL_29;
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError > 0 )
    v14 = (unsigned __int16)LastError | 0x80070000;
  if ( v14 != -2147024774 )
  {
LABEL_30:
    if ( !v3 )
      return v14;
LABEL_31:
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v3);
    return v14;
  }
  v15 = dwBytes;
  v16 = GetProcessHeap();
  v17 = (unsigned __int16 *)HeapAlloc(v16, 8u, v15);
  v3 = v17;
  if ( v17 )
  {
    if ( !v7(4, v17, &dwBytes) )
    {
      v18 = GetLastError();
      v14 = v18;
      if ( v18 > 0 )
        v14 = (unsigned __int16)v18 | 0x80070000;
      goto LABEL_31;
    }
    goto LABEL_22;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180012d44  mov     [rsp-28h+arg_0], rbx
0x180012d49  mov     [rsp-28h+arg_8], rsi
0x180012d4e  push    rbp
0x180012d4f  push    rdi
0x180012d50  push    r13
0x180012d52  push    r14
0x180012d54  push    r15
0x180012d56  mov     rbp, rsp
0x180012d59  sub     rsp, 50h
0x180012d5d  xorps   xmm0, xmm0
0x180012d60  mov     r14, rcx
0x180012d63  xor     ebx, ebx
0x180012d65  lea     rcx, aKernel32; "kernel32"
0x180012d6c  mov     dword ptr [rbp+dwBytes], ebx
0x180012d6f  mov     r15, rdx
0x180012d72  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180012d76  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180012d7a  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180012d7e  call    cs:__imp_GetModuleHandleW
0x180012d84  lea     r13d, [rbx+40h]
0x180012d88  test    rax, rax
0x180012d8b  jz      loc_180012F38
0x180012d91  lea     rdx, aGetlogicalproc; "GetLogicalProcessorInformationEx"
0x180012d98  mov     rcx, rax; hModule
0x180012d9b  call    cs:__imp_GetProcAddress
0x180012da1  mov     rsi, rax
0x180012da4  test    rax, rax
0x180012da7  jz      loc_180012F38
0x180012dad  lea     edi, [rbx+2]
0x180012db0  xor     edx, edx
0x180012db2  mov     ecx, edi
0x180012db4  lea     r8, [rbp+dwBytes]
0x180012db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dbd  test    eax, eax
0x180012dbf  jnz     short loc_180012E21
0x180012dc1  call    cs:__imp_GetLastError
0x180012dc7  cmp     eax, 7Ah ; 'z'
0x180012dca  jnz     short loc_180012E21
0x180012dcc  mov     eax, dword ptr [rbp+dwBytes]
0x180012dcf  test    eax, eax
0x180012dd1  jz      short loc_180012E21
0x180012dd3  mov     ebx, eax
0x180012dd5  call    cs:__imp_GetProcessHeap
0x180012ddb  mov     r8d, ebx; dwBytes
0x180012dde  lea     edx, [rdi+6]; dwFlags
0x180012de1  mov     rcx, rax; hHeap
0x180012de4  call    cs:__imp_HeapAlloc
0x180012dea  mov     rbx, rax
0x180012ded  test    rax, rax
0x180012df0  jz      short loc_180012E21
0x180012df2  mov     rdx, rax
0x180012df5  lea     r8, [rbp+dwBytes]
0x180012df9  mov     rax, rsi
0x180012dfc  mov     ecx, edi
0x180012dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e03  test    eax, eax
0x180012e05  jnz     loc_180012EAF
0x180012e0b  call    cs:__imp_GetProcessHeap
0x180012e11  mov     r8, rbx; lpMem
0x180012e14  xor     edx, edx; dwFlags
0x180012e16  mov     rcx, rax; hHeap
0x180012e19  call    cs:__imp_HeapFree
0x180012e1f  xor     ebx, ebx
0x180012e21  mov     [r14], r13d
0x180012e24  test    rbx, rbx
0x180012e27  jz      short loc_180012E3F
0x180012e29  call    cs:__imp_GetProcessHeap
0x180012e2f  mov     r8, rbx; lpMem
0x180012e32  xor     edx, edx; dwFlags
0x180012e34  mov     rcx, rax; hHeap
0x180012e37  call    cs:__imp_HeapFree
0x180012e3d  xor     ebx, ebx
0x180012e3f  lea     r8, [rbp+dwBytes]
0x180012e43  mov     dword ptr [rbp+dwBytes], 0
0x180012e4a  mov     rdx, rbx
0x180012e4d  mov     ecx, 4
0x180012e52  mov     rax, rsi
0x180012e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e5a  test    eax, eax
0x180012e5c  jnz     loc_180012EF5
0x180012e62  call    cs:__imp_GetLastError
0x180012e68  mov     edi, eax
0x180012e6a  test    eax, eax
0x180012e6c  jle     short loc_180012E77
0x180012e6e  movzx   edi, ax
0x180012e71  or      edi, 80070000h
0x180012e77  cmp     edi, 8007007Ah
0x180012e7d  jnz     loc_180012F4D
0x180012e83  mov     ebx, dword ptr [rbp+dwBytes]
0x180012e86  call    cs:__imp_GetProcessHeap
0x180012e8c  mov     r8d, ebx; dwBytes
0x180012e8f  mov     edx, 8; dwFlags
0x180012e94  mov     rcx, rax; hHeap
0x180012e97  call    cs:__imp_HeapAlloc
0x180012e9d  mov     rbx, rax
0x180012ea0  test    rax, rax
0x180012ea3  jnz     short loc_180012EC6
0x180012ea5  mov     edi, 8007000Eh
0x180012eaa  jmp     loc_180012F66
0x180012eaf  cmp     [rbx+0Ah], r13w
0x180012eb4  jbe     loc_180012E21
0x180012eba  movzx   eax, word ptr [rbx+0Ah]
0x180012ebe  mov     [r14], eax
0x180012ec1  jmp     loc_180012E29
0x180012ec6  mov     rdx, rax
0x180012ec9  lea     r8, [rbp+dwBytes]
0x180012ecd  mov     rax, rsi
0x180012ed0  mov     ecx, 4
0x180012ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eda  test    eax, eax
0x180012edc  jnz     short loc_180012EF5
0x180012ede  call    cs:__imp_GetLastError
0x180012ee4  mov     edi, eax
0x180012ee6  test    eax, eax
0x180012ee8  jle     short loc_180012F52
0x180012eea  movzx   edi, ax
0x180012eed  or      edi, 80070000h
0x180012ef3  jmp     short loc_180012F52
0x180012ef5  test    rbx, rbx
0x180012ef8  jz      short loc_180012F38
0x180012efa  movzx   r8d, word ptr [rbx+0Ah]
0x180012eff  test    r8d, r8d
0x180012f02  jz      short loc_180012F38
0x180012f04  movzx   edx, byte ptr [rbx+20h]
0x180012f08  mov     r9d, 1
0x180012f0e  cmp     r8d, r9d
0x180012f11  jbe     short loc_180012F31
0x180012f13  mov     eax, r9d
0x180012f16  lea     rcx, [rax+rax*2]
0x180012f1a  add     rcx, rcx
0x180012f1d  movzx   eax, byte ptr [rbx+rcx*8+20h]
0x180012f22  cmp     eax, edx
0x180012f24  cmovbe  eax, edx
0x180012f27  inc     r9d
0x180012f2a  mov     edx, eax
0x180012f2c  cmp     r9d, r8d
0x180012f2f  jb      short loc_180012F13
0x180012f31  mov     [r15], edx
0x180012f34  xor     edi, edi
0x180012f36  jmp     short loc_180012F52
0x180012f38  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180012f3c  call    cs:__imp_GetSystemInfo
0x180012f42  mov     eax, [rbp+SystemInfo.dwNumberOfProcessors]
0x180012f45  xor     edi, edi
0x180012f47  mov     [r15], eax
0x180012f4a  mov     [r14], r13d
0x180012f4d  test    rbx, rbx
0x180012f50  jz      short loc_180012F66
0x180012f52  call    cs:__imp_GetProcessHeap
0x180012f58  mov     r8, rbx; lpMem
0x180012f5b  xor     edx, edx; dwFlags
0x180012f5d  mov     rcx, rax; hHeap
0x180012f60  call    cs:__imp_HeapFree
0x180012f66  lea     r11, [rsp+50h+var_s0]
0x180012f6b  mov     eax, edi
0x180012f6d  mov     rbx, [r11+30h]
0x180012f71  mov     rsi, [r11+38h]
0x180012f75  mov     rsp, r11
0x180012f78  pop     r15
0x180012f7a  pop     r14
0x180012f7c  pop     r13
0x180012f7e  pop     rdi
0x180012f7f  pop     rbp
0x180012f80  retn
```

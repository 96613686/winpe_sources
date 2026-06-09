# _resetstkoflw_static

- ea: `0x18005b8d4`
- end: `0x18005ba26`
- name: `_resetstkoflw_static`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180019688`

## callees

- `0x18003d270`
- `0x18005b8d4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18005b958`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18005b958`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18005b96d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18005b96d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18005b9ec`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18005b9ec`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18005b93f`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18005b93f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18005ba0c`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18005ba0c`

## pseudocode

```c
_BOOL8 resetstkoflw_static()
{
  char *AllocationBase; // r15
  __int64 dwPageSize; // rdi
  ULONG v2; // ebx
  unsigned int v3; // edx
  ULONG v4; // ecx
  unsigned int v5; // eax
  unsigned int v6; // ecx
  unsigned int v8; // eax
  unsigned int v9; // esi
  char *v10; // rbx
  _BYTE Address[16]; // [rsp+10h] [rbp-10h] BYREF
  ULONG StackSizeInBytes; // [rsp+20h] [rbp+0h] BYREF
  DWORD flOldProtect; // [rsp+24h] [rbp+4h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+28h] [rbp+8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp+38h] BYREF

  flOldProtect = 0;
  memset(&Buffer, 0, sizeof(Buffer));
  StackSizeInBytes = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( !VirtualQuery(Address, &Buffer, 0x30u) )
    return 0;
  AllocationBase = (char *)Buffer.AllocationBase;
  GetSystemInfo(&SystemInfo);
  dwPageSize = SystemInfo.dwPageSize;
  v2 = 0;
  if ( SetThreadStackGuarantee(&StackSizeInBytes) && StackSizeInBytes )
    v2 = StackSizeInBytes;
  v3 = dwPageSize - 1;
  v4 = dwPageSize - 1 + v2;
  if ( v4 < v2 )
    return 0;
  v5 = v4 & ~v3;
  if ( v5 )
  {
    v6 = v5 + dwPageSize;
    if ( v5 + (unsigned int)dwPageSize < v5 )
      return 0;
  }
  else
  {
    v6 = 0;
  }
  v8 = 3 * dwPageSize;
  if ( v6 >= 3 * (int)dwPageSize )
    v8 = v6;
  v9 = v8;
  v10 = (char *)(((unsigned __int64)Address & ~(unsigned __int64)v3) - v8);
  if ( v10 < &AllocationBase[dwPageSize] || !VirtualAlloc(v10, v8, 0x1000u, 4u) )
    return 0;
  return VirtualProtect(v10, v9, 0x104u, &flOldProtect);
}

```

## disassembly

```asm
0x18005b8d4  push    rbp
0x18005b8d6  push    rbx
0x18005b8d7  push    rsi
0x18005b8d8  push    rdi
0x18005b8d9  push    r14
0x18005b8db  push    r15
0x18005b8dd  sub     rsp, 98h
0x18005b8e4  lea     rbp, [rsp+20h]
0x18005b8e9  mov     rax, cs:__security_cookie
0x18005b8f0  xor     rax, rbp
0x18005b8f3  mov     [rbp+0A0h+var_38], rax
0x18005b8f7  mov     eax, [rsp+0C0h+var_C0]
0x18005b8fa  xorps   xmm0, xmm0
0x18005b8fd  xorps   xmm1, xmm1
0x18005b900  mov     [rbp+0A0h+flOldProtect], 0
0x18005b907  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18005b90b  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18005b912  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18005b916  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18005b91a  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18005b91e  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18005b922  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18005b926  sub     rsp, 10h
0x18005b92a  lea     r14, [rsp+0D0h+Address]
0x18005b92f  mov     eax, [r14]
0x18005b932  mov     r8d, 30h ; '0'; dwLength
0x18005b938  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18005b93c  mov     rcx, r14; lpAddress
0x18005b93f  call    cs:__imp_VirtualQuery
0x18005b946  nop     dword ptr [rax+rax+00h]
0x18005b94b  test    rax, rax
0x18005b94e  jz      short loc_18005B99F
0x18005b950  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18005b954  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18005b958  call    cs:__imp_GetSystemInfo
0x18005b95f  nop     dword ptr [rax+rax+00h]
0x18005b964  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18005b967  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18005b96b  xor     ebx, ebx
0x18005b96d  call    cs:__imp_SetThreadStackGuarantee
0x18005b974  nop     dword ptr [rax+rax+00h]
0x18005b979  cmp     eax, 1
0x18005b97c  jnz     short loc_18005B986
0x18005b97e  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18005b981  test    eax, eax
0x18005b983  cmovnz  ebx, eax
0x18005b986  lea     edx, [rdi-1]
0x18005b989  lea     ecx, [rdx+rbx]
0x18005b98c  cmp     ecx, ebx
0x18005b98e  jb      short loc_18005B99F
0x18005b990  mov     eax, edx
0x18005b992  not     eax
0x18005b994  and     eax, ecx
0x18005b996  jz      short loc_18005B9BB
0x18005b998  lea     ecx, [rax+rdi]
0x18005b99b  cmp     ecx, eax
0x18005b99d  jnb     short loc_18005B9BD
0x18005b99f  xor     eax, eax
0x18005b9a1  mov     rcx, [rbp+0A0h+var_38]
0x18005b9a5  xor     rcx, rbp; StackCookie
0x18005b9a8  call    __security_check_cookie
0x18005b9ad  lea     rsp, [rbp+78h]
0x18005b9b1  pop     r15
0x18005b9b3  pop     r14
0x18005b9b5  pop     rdi
0x18005b9b6  pop     rsi
0x18005b9b7  pop     rbx
0x18005b9b8  pop     rbp
0x18005b9b9  retn
0x18005b9bb  mov     ecx, eax
0x18005b9bd  lea     eax, [rdi+rdi*2]
0x18005b9c0  mov     ebx, edx
0x18005b9c2  cmp     ecx, eax
0x18005b9c4  not     rbx
0x18005b9c7  cmovnb  eax, ecx
0x18005b9ca  and     rbx, r14
0x18005b9cd  mov     esi, eax
0x18005b9cf  lea     rax, [r15+rdi]
0x18005b9d3  sub     rbx, rsi
0x18005b9d6  cmp     rbx, rax
0x18005b9d9  jb      short loc_18005B99F
0x18005b9db  mov     r9d, 4; flProtect
0x18005b9e1  mov     r8d, 1000h; flAllocationType
0x18005b9e7  mov     edx, esi; dwSize
0x18005b9e9  mov     rcx, rbx; lpAddress
0x18005b9ec  call    cs:__imp_VirtualAlloc
0x18005b9f3  nop     dword ptr [rax+rax+00h]
0x18005b9f8  test    rax, rax
0x18005b9fb  jz      short loc_18005B99F
0x18005b9fd  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18005ba01  mov     r8d, 104h; flNewProtect
0x18005ba07  mov     edx, esi; dwSize
0x18005ba09  mov     rcx, rbx; lpAddress
0x18005ba0c  call    cs:__imp_VirtualProtect
0x18005ba13  nop     dword ptr [rax+rax+00h]
0x18005ba18  xor     ecx, ecx
0x18005ba1a  test    eax, eax
0x18005ba1c  setnz   cl
0x18005ba1f  mov     eax, ecx
0x18005ba21  jmp     loc_18005B9A1
```

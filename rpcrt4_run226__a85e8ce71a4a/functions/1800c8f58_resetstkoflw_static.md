# _resetstkoflw_static

- ea: `0x1800c8f58`
- end: `0x1800c9088`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005ceb0`

## callees

- `0x1800c8f58`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800c905d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800c905d`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800c8fc3`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800c8fc3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800c9077`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800c9077`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800c8fe5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800c8fe5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800c8fd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800c8fd6`

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
  struct _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp+38h] BYREF

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
0x1800c8f58  push    rbp
0x1800c8f5a  push    rbx
0x1800c8f5b  push    rsi
0x1800c8f5c  push    rdi
0x1800c8f5d  push    r14
0x1800c8f5f  push    r15
0x1800c8f61  sub     rsp, 98h
0x1800c8f68  lea     rbp, [rsp+20h]
0x1800c8f6d  mov     rax, cs:__security_cookie
0x1800c8f74  xor     rax, rbp
0x1800c8f77  mov     [rbp+0A0h+var_38], rax
0x1800c8f7b  mov     eax, [rsp+0C0h+var_C0]
0x1800c8f7e  xorps   xmm0, xmm0
0x1800c8f81  xorps   xmm1, xmm1
0x1800c8f84  mov     [rbp+0A0h+flOldProtect], 0
0x1800c8f8b  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x1800c8f8f  mov     [rbp+0A0h+StackSizeInBytes], 0
0x1800c8f96  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x1800c8f9a  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x1800c8f9e  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800c8fa2  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800c8fa6  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800c8faa  sub     rsp, 10h
0x1800c8fae  lea     r14, [rsp+0D0h+Address]
0x1800c8fb3  mov     eax, [r14]
0x1800c8fb6  mov     r8d, 30h ; '0'; dwLength
0x1800c8fbc  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800c8fc0  mov     rcx, r14; lpAddress
0x1800c8fc3  call    cs:__imp_VirtualQuery
0x1800c8fc9  test    rax, rax
0x1800c8fcc  jz      short loc_1800C9011
0x1800c8fce  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x1800c8fd2  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x1800c8fd6  call    cs:__imp_GetSystemInfo
0x1800c8fdc  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800c8fdf  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800c8fe3  xor     ebx, ebx
0x1800c8fe5  call    cs:__imp_SetThreadStackGuarantee
0x1800c8feb  cmp     eax, 1
0x1800c8fee  jnz     short loc_1800C8FF8
0x1800c8ff0  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x1800c8ff3  test    eax, eax
0x1800c8ff5  cmovnz  ebx, eax
0x1800c8ff8  lea     edx, [rdi-1]
0x1800c8ffb  lea     ecx, [rdx+rbx]
0x1800c8ffe  cmp     ecx, ebx
0x1800c9000  jb      short loc_1800C9011
0x1800c9002  mov     eax, edx
0x1800c9004  not     eax
0x1800c9006  and     eax, ecx
0x1800c9008  jz      short loc_1800C902C
0x1800c900a  lea     ecx, [rax+rdi]
0x1800c900d  cmp     ecx, eax
0x1800c900f  jnb     short loc_1800C902E
0x1800c9011  xor     eax, eax
0x1800c9013  mov     rcx, [rbp+0A0h+var_38]
0x1800c9017  xor     rcx, rbp; StackCookie
0x1800c901a  call    __security_check_cookie
0x1800c901f  lea     rsp, [rbp+78h]
0x1800c9023  pop     r15
0x1800c9025  pop     r14
0x1800c9027  pop     rdi
0x1800c9028  pop     rsi
0x1800c9029  pop     rbx
0x1800c902a  pop     rbp
0x1800c902b  retn
0x1800c902c  mov     ecx, eax
0x1800c902e  lea     eax, [rdi+rdi*2]
0x1800c9031  mov     ebx, edx
0x1800c9033  cmp     ecx, eax
0x1800c9035  not     rbx
0x1800c9038  cmovnb  eax, ecx
0x1800c903b  and     rbx, r14
0x1800c903e  mov     esi, eax
0x1800c9040  lea     rax, [r15+rdi]
0x1800c9044  sub     rbx, rsi
0x1800c9047  cmp     rbx, rax
0x1800c904a  jb      short loc_1800C9011
0x1800c904c  mov     r9d, 4; flProtect
0x1800c9052  mov     r8d, 1000h; flAllocationType
0x1800c9058  mov     edx, esi; dwSize
0x1800c905a  mov     rcx, rbx; lpAddress
0x1800c905d  call    cs:__imp_VirtualAlloc
0x1800c9063  test    rax, rax
0x1800c9066  jz      short loc_1800C9011
0x1800c9068  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1800c906c  mov     r8d, 104h; flNewProtect
0x1800c9072  mov     edx, esi; dwSize
0x1800c9074  mov     rcx, rbx; lpAddress
0x1800c9077  call    cs:__imp_VirtualProtect
0x1800c907d  xor     ecx, ecx
0x1800c907f  test    eax, eax
0x1800c9081  setnz   cl
0x1800c9084  mov     eax, ecx
0x1800c9086  jmp     short loc_1800C9013
```

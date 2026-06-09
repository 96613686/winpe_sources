# _resetstkoflw_static

- ea: `0x18001bf74`
- end: `0x18001c0a4`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bf4c`

## callees

- `0x18000b550`
- `0x18001bf74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001c001`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001c001`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001bff2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001bff2`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001bfdf`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001bfdf`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001c079`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001c079`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001c093`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001c093`

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
0x18001bf74  push    rbp
0x18001bf76  push    rbx
0x18001bf77  push    rsi
0x18001bf78  push    rdi
0x18001bf79  push    r14
0x18001bf7b  push    r15
0x18001bf7d  sub     rsp, 98h
0x18001bf84  lea     rbp, [rsp+20h]
0x18001bf89  mov     rax, cs:__security_cookie
0x18001bf90  xor     rax, rbp
0x18001bf93  mov     [rbp+0A0h+var_38], rax
0x18001bf97  mov     eax, [rsp+0C0h+var_C0]
0x18001bf9a  xorps   xmm0, xmm0
0x18001bf9d  xorps   xmm1, xmm1
0x18001bfa0  mov     [rbp+0A0h+flOldProtect], 0
0x18001bfa7  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001bfab  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18001bfb2  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001bfb6  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001bfba  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001bfbe  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18001bfc2  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18001bfc6  sub     rsp, 10h
0x18001bfca  lea     r14, [rsp+0D0h+Address]
0x18001bfcf  mov     eax, [r14]
0x18001bfd2  mov     r8d, 30h ; '0'; dwLength
0x18001bfd8  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001bfdc  mov     rcx, r14; lpAddress
0x18001bfdf  call    cs:__imp_VirtualQuery
0x18001bfe5  test    rax, rax
0x18001bfe8  jz      short loc_18001C02D
0x18001bfea  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18001bfee  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18001bff2  call    cs:__imp_GetSystemInfo
0x18001bff8  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18001bffb  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001bfff  xor     ebx, ebx
0x18001c001  call    cs:__imp_SetThreadStackGuarantee
0x18001c007  cmp     eax, 1
0x18001c00a  jnz     short loc_18001C014
0x18001c00c  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18001c00f  test    eax, eax
0x18001c011  cmovnz  ebx, eax
0x18001c014  lea     edx, [rdi-1]
0x18001c017  lea     ecx, [rdx+rbx]
0x18001c01a  cmp     ecx, ebx
0x18001c01c  jb      short loc_18001C02D
0x18001c01e  mov     eax, edx
0x18001c020  not     eax
0x18001c022  and     eax, ecx
0x18001c024  jz      short loc_18001C048
0x18001c026  lea     ecx, [rax+rdi]
0x18001c029  cmp     ecx, eax
0x18001c02b  jnb     short loc_18001C04A
0x18001c02d  xor     eax, eax
0x18001c02f  mov     rcx, [rbp+0A0h+var_38]
0x18001c033  xor     rcx, rbp; StackCookie
0x18001c036  call    __security_check_cookie
0x18001c03b  lea     rsp, [rbp+78h]
0x18001c03f  pop     r15
0x18001c041  pop     r14
0x18001c043  pop     rdi
0x18001c044  pop     rsi
0x18001c045  pop     rbx
0x18001c046  pop     rbp
0x18001c047  retn
0x18001c048  mov     ecx, eax
0x18001c04a  lea     eax, [rdi+rdi*2]
0x18001c04d  mov     ebx, edx
0x18001c04f  cmp     ecx, eax
0x18001c051  not     rbx
0x18001c054  cmovnb  eax, ecx
0x18001c057  and     rbx, r14
0x18001c05a  mov     esi, eax
0x18001c05c  lea     rax, [r15+rdi]
0x18001c060  sub     rbx, rsi
0x18001c063  cmp     rbx, rax
0x18001c066  jb      short loc_18001C02D
0x18001c068  mov     r9d, 4; flProtect
0x18001c06e  mov     r8d, 1000h; flAllocationType
0x18001c074  mov     edx, esi; dwSize
0x18001c076  mov     rcx, rbx; lpAddress
0x18001c079  call    cs:__imp_VirtualAlloc
0x18001c07f  test    rax, rax
0x18001c082  jz      short loc_18001C02D
0x18001c084  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001c088  mov     r8d, 104h; flNewProtect
0x18001c08e  mov     edx, esi; dwSize
0x18001c090  mov     rcx, rbx; lpAddress
0x18001c093  call    cs:__imp_VirtualProtect
0x18001c099  xor     ecx, ecx
0x18001c09b  test    eax, eax
0x18001c09d  setnz   cl
0x18001c0a0  mov     eax, ecx
0x18001c0a2  jmp     short loc_18001C02F
```

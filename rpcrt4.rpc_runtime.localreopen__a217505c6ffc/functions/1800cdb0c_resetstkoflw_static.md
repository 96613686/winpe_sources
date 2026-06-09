# _resetstkoflw_static

- ea: `0x1800cdb0c`
- end: `0x1800cdc5e`
- name: `_resetstkoflw_static`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006d460`

## callees

- `0x1800cdb0c`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800cdc24`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800cdc24`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800cdb77`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800cdb77`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800cdc44`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800cdc44`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800cdba5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800cdba5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800cdb90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800cdb90`

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
0x1800cdb0c  push    rbp
0x1800cdb0e  push    rbx
0x1800cdb0f  push    rsi
0x1800cdb10  push    rdi
0x1800cdb11  push    r14
0x1800cdb13  push    r15
0x1800cdb15  sub     rsp, 98h
0x1800cdb1c  lea     rbp, [rsp+20h]
0x1800cdb21  mov     rax, cs:__security_cookie
0x1800cdb28  xor     rax, rbp
0x1800cdb2b  mov     [rbp+0A0h+var_38], rax
0x1800cdb2f  mov     eax, [rsp+0C0h+var_C0]
0x1800cdb32  xorps   xmm0, xmm0
0x1800cdb35  xorps   xmm1, xmm1
0x1800cdb38  mov     [rbp+0A0h+flOldProtect], 0
0x1800cdb3f  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x1800cdb43  mov     [rbp+0A0h+StackSizeInBytes], 0
0x1800cdb4a  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x1800cdb4e  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x1800cdb52  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800cdb56  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800cdb5a  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800cdb5e  sub     rsp, 10h
0x1800cdb62  lea     r14, [rsp+0D0h+Address]
0x1800cdb67  mov     eax, [r14]
0x1800cdb6a  mov     r8d, 30h ; '0'; dwLength
0x1800cdb70  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800cdb74  mov     rcx, r14; lpAddress
0x1800cdb77  call    cs:__imp_VirtualQuery
0x1800cdb7e  nop     dword ptr [rax+rax+00h]
0x1800cdb83  test    rax, rax
0x1800cdb86  jz      short loc_1800CDBD7
0x1800cdb88  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x1800cdb8c  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x1800cdb90  call    cs:__imp_GetSystemInfo
0x1800cdb97  nop     dword ptr [rax+rax+00h]
0x1800cdb9c  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800cdb9f  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800cdba3  xor     ebx, ebx
0x1800cdba5  call    cs:__imp_SetThreadStackGuarantee
0x1800cdbac  nop     dword ptr [rax+rax+00h]
0x1800cdbb1  cmp     eax, 1
0x1800cdbb4  jnz     short loc_1800CDBBE
0x1800cdbb6  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x1800cdbb9  test    eax, eax
0x1800cdbbb  cmovnz  ebx, eax
0x1800cdbbe  lea     edx, [rdi-1]
0x1800cdbc1  lea     ecx, [rdx+rbx]
0x1800cdbc4  cmp     ecx, ebx
0x1800cdbc6  jb      short loc_1800CDBD7
0x1800cdbc8  mov     eax, edx
0x1800cdbca  not     eax
0x1800cdbcc  and     eax, ecx
0x1800cdbce  jz      short loc_1800CDBF3
0x1800cdbd0  lea     ecx, [rax+rdi]
0x1800cdbd3  cmp     ecx, eax
0x1800cdbd5  jnb     short loc_1800CDBF5
0x1800cdbd7  xor     eax, eax
0x1800cdbd9  mov     rcx, [rbp+0A0h+var_38]
0x1800cdbdd  xor     rcx, rbp; StackCookie
0x1800cdbe0  call    __security_check_cookie
0x1800cdbe5  lea     rsp, [rbp+78h]
0x1800cdbe9  pop     r15
0x1800cdbeb  pop     r14
0x1800cdbed  pop     rdi
0x1800cdbee  pop     rsi
0x1800cdbef  pop     rbx
0x1800cdbf0  pop     rbp
0x1800cdbf1  retn
0x1800cdbf3  mov     ecx, eax
0x1800cdbf5  lea     eax, [rdi+rdi*2]
0x1800cdbf8  mov     ebx, edx
0x1800cdbfa  cmp     ecx, eax
0x1800cdbfc  not     rbx
0x1800cdbff  cmovnb  eax, ecx
0x1800cdc02  and     rbx, r14
0x1800cdc05  mov     esi, eax
0x1800cdc07  lea     rax, [r15+rdi]
0x1800cdc0b  sub     rbx, rsi
0x1800cdc0e  cmp     rbx, rax
0x1800cdc11  jb      short loc_1800CDBD7
0x1800cdc13  mov     r9d, 4; flProtect
0x1800cdc19  mov     r8d, 1000h; flAllocationType
0x1800cdc1f  mov     edx, esi; dwSize
0x1800cdc21  mov     rcx, rbx; lpAddress
0x1800cdc24  call    cs:__imp_VirtualAlloc
0x1800cdc2b  nop     dword ptr [rax+rax+00h]
0x1800cdc30  test    rax, rax
0x1800cdc33  jz      short loc_1800CDBD7
0x1800cdc35  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1800cdc39  mov     r8d, 104h; flNewProtect
0x1800cdc3f  mov     edx, esi; dwSize
0x1800cdc41  mov     rcx, rbx; lpAddress
0x1800cdc44  call    cs:__imp_VirtualProtect
0x1800cdc4b  nop     dword ptr [rax+rax+00h]
0x1800cdc50  xor     ecx, ecx
0x1800cdc52  test    eax, eax
0x1800cdc54  setnz   cl
0x1800cdc57  mov     eax, ecx
0x1800cdc59  jmp     loc_1800CDBD9
```

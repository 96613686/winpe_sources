# _resetstkoflw_static

- ea: `0x180088660`
- end: `0x180088790`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001db60`

## callees

- `0x1800597b0`
- `0x180088660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800886ed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800886ed`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800886cb`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800886cb`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18008877f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18008877f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180088765`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180088765`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800886de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800886de`

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
0x180088660  push    rbp
0x180088662  push    rbx
0x180088663  push    rsi
0x180088664  push    rdi
0x180088665  push    r14
0x180088667  push    r15
0x180088669  sub     rsp, 98h
0x180088670  lea     rbp, [rsp+20h]
0x180088675  mov     rax, cs:__security_cookie
0x18008867c  xor     rax, rbp
0x18008867f  mov     [rbp+0A0h+var_38], rax
0x180088683  mov     eax, [rsp+0C0h+var_C0]
0x180088686  xorps   xmm0, xmm0
0x180088689  xorps   xmm1, xmm1
0x18008868c  mov     [rbp+0A0h+flOldProtect], 0
0x180088693  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180088697  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18008869e  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x1800886a2  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x1800886a6  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800886aa  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800886ae  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800886b2  sub     rsp, 10h
0x1800886b6  lea     r14, [rsp+0D0h+Address]
0x1800886bb  mov     eax, [r14]
0x1800886be  mov     r8d, 30h ; '0'; dwLength
0x1800886c4  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800886c8  mov     rcx, r14; lpAddress
0x1800886cb  call    cs:__imp_VirtualQuery
0x1800886d1  test    rax, rax
0x1800886d4  jz      short loc_180088719
0x1800886d6  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x1800886da  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x1800886de  call    cs:__imp_GetSystemInfo
0x1800886e4  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800886e7  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800886eb  xor     ebx, ebx
0x1800886ed  call    cs:__imp_SetThreadStackGuarantee
0x1800886f3  cmp     eax, 1
0x1800886f6  jnz     short loc_180088700
0x1800886f8  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x1800886fb  test    eax, eax
0x1800886fd  cmovnz  ebx, eax
0x180088700  lea     edx, [rdi-1]
0x180088703  lea     ecx, [rdx+rbx]
0x180088706  cmp     ecx, ebx
0x180088708  jb      short loc_180088719
0x18008870a  mov     eax, edx
0x18008870c  not     eax
0x18008870e  and     eax, ecx
0x180088710  jz      short loc_180088734
0x180088712  lea     ecx, [rax+rdi]
0x180088715  cmp     ecx, eax
0x180088717  jnb     short loc_180088736
0x180088719  xor     eax, eax
0x18008871b  mov     rcx, [rbp+0A0h+var_38]
0x18008871f  xor     rcx, rbp; StackCookie
0x180088722  call    __security_check_cookie
0x180088727  lea     rsp, [rbp+78h]
0x18008872b  pop     r15
0x18008872d  pop     r14
0x18008872f  pop     rdi
0x180088730  pop     rsi
0x180088731  pop     rbx
0x180088732  pop     rbp
0x180088733  retn
0x180088734  mov     ecx, eax
0x180088736  lea     eax, [rdi+rdi*2]
0x180088739  mov     ebx, edx
0x18008873b  cmp     ecx, eax
0x18008873d  not     rbx
0x180088740  cmovnb  eax, ecx
0x180088743  and     rbx, r14
0x180088746  mov     esi, eax
0x180088748  lea     rax, [r15+rdi]
0x18008874c  sub     rbx, rsi
0x18008874f  cmp     rbx, rax
0x180088752  jb      short loc_180088719
0x180088754  mov     r9d, 4; flProtect
0x18008875a  mov     r8d, 1000h; flAllocationType
0x180088760  mov     edx, esi; dwSize
0x180088762  mov     rcx, rbx; lpAddress
0x180088765  call    cs:__imp_VirtualAlloc
0x18008876b  test    rax, rax
0x18008876e  jz      short loc_180088719
0x180088770  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180088774  mov     r8d, 104h; flNewProtect
0x18008877a  mov     edx, esi; dwSize
0x18008877c  mov     rcx, rbx; lpAddress
0x18008877f  call    cs:__imp_VirtualProtect
0x180088785  xor     ecx, ecx
0x180088787  test    eax, eax
0x180088789  setnz   cl
0x18008878c  mov     eax, ecx
0x18008878e  jmp     short loc_18008871B
```

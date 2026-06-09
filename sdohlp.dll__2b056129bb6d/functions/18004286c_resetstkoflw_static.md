# _resetstkoflw_static

- ea: `0x18004286c`
- end: `0x18004299c`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180042844`

## callees

- `0x18004286c`
- `0x180055030`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x1800428ea`
- `KERNEL32!GetSystemInfo` at `0x1800428ea`
- `KERNEL32!VirtualQuery` at `0x1800428d7`
- `KERNEL32!VirtualQuery` at `0x1800428d7`
- `KERNEL32!VirtualProtect` at `0x18004298b`
- `KERNEL32!VirtualProtect` at `0x18004298b`
- `KERNEL32!VirtualAlloc` at `0x180042971`
- `KERNEL32!VirtualAlloc` at `0x180042971`
- `KERNEL32!SetThreadStackGuarantee` at `0x1800428f9`
- `KERNEL32!SetThreadStackGuarantee` at `0x1800428f9`

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
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+28h] [rbp+8h] BYREF
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
0x18004286c  push    rbp
0x18004286e  push    rbx
0x18004286f  push    rsi
0x180042870  push    rdi
0x180042871  push    r14
0x180042873  push    r15
0x180042875  sub     rsp, 98h
0x18004287c  lea     rbp, [rsp+20h]
0x180042881  mov     rax, cs:__security_cookie
0x180042888  xor     rax, rbp
0x18004288b  mov     [rbp+0A0h+var_38], rax
0x18004288f  mov     eax, [rsp+0C0h+var_C0]
0x180042892  xorps   xmm0, xmm0
0x180042895  xorps   xmm1, xmm1
0x180042898  mov     [rbp+0A0h+flOldProtect], 0
0x18004289f  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x1800428a3  mov     [rbp+0A0h+StackSizeInBytes], 0
0x1800428aa  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x1800428ae  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x1800428b2  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800428b6  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800428ba  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800428be  sub     rsp, 10h
0x1800428c2  lea     r14, [rsp+0D0h+Address]
0x1800428c7  mov     eax, [r14]
0x1800428ca  mov     r8d, 30h ; '0'; dwLength
0x1800428d0  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800428d4  mov     rcx, r14; lpAddress
0x1800428d7  call    cs:__imp_VirtualQuery
0x1800428dd  test    rax, rax
0x1800428e0  jz      short loc_180042925
0x1800428e2  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x1800428e6  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x1800428ea  call    cs:__imp_GetSystemInfo
0x1800428f0  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800428f3  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800428f7  xor     ebx, ebx
0x1800428f9  call    cs:__imp_SetThreadStackGuarantee
0x1800428ff  cmp     eax, 1
0x180042902  jnz     short loc_18004290C
0x180042904  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180042907  test    eax, eax
0x180042909  cmovnz  ebx, eax
0x18004290c  lea     edx, [rdi-1]
0x18004290f  lea     ecx, [rdx+rbx]
0x180042912  cmp     ecx, ebx
0x180042914  jb      short loc_180042925
0x180042916  mov     eax, edx
0x180042918  not     eax
0x18004291a  and     eax, ecx
0x18004291c  jz      short loc_180042940
0x18004291e  lea     ecx, [rax+rdi]
0x180042921  cmp     ecx, eax
0x180042923  jnb     short loc_180042942
0x180042925  xor     eax, eax
0x180042927  mov     rcx, [rbp+0A0h+var_38]
0x18004292b  xor     rcx, rbp; StackCookie
0x18004292e  call    __security_check_cookie
0x180042933  lea     rsp, [rbp+78h]
0x180042937  pop     r15
0x180042939  pop     r14
0x18004293b  pop     rdi
0x18004293c  pop     rsi
0x18004293d  pop     rbx
0x18004293e  pop     rbp
0x18004293f  retn
0x180042940  mov     ecx, eax
0x180042942  lea     eax, [rdi+rdi*2]
0x180042945  mov     ebx, edx
0x180042947  cmp     ecx, eax
0x180042949  not     rbx
0x18004294c  cmovnb  eax, ecx
0x18004294f  and     rbx, r14
0x180042952  mov     esi, eax
0x180042954  lea     rax, [r15+rdi]
0x180042958  sub     rbx, rsi
0x18004295b  cmp     rbx, rax
0x18004295e  jb      short loc_180042925
0x180042960  mov     r9d, 4; flProtect
0x180042966  mov     r8d, 1000h; flAllocationType
0x18004296c  mov     edx, esi; dwSize
0x18004296e  mov     rcx, rbx; lpAddress
0x180042971  call    cs:__imp_VirtualAlloc
0x180042977  test    rax, rax
0x18004297a  jz      short loc_180042925
0x18004297c  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180042980  mov     r8d, 104h; flNewProtect
0x180042986  mov     edx, esi; dwSize
0x180042988  mov     rcx, rbx; lpAddress
0x18004298b  call    cs:__imp_VirtualProtect
0x180042991  xor     ecx, ecx
0x180042993  test    eax, eax
0x180042995  setnz   cl
0x180042998  mov     eax, ecx
0x18004299a  jmp     short loc_180042927
```

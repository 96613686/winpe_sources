# DmpCopyMemorySafely(void *,void const *,unsigned __int64)

- ea: `0x1004815a0`
- end: `0x100481727`
- name: `?DmpCopyMemorySafely@@YAJPEAXPEBX_K@Z`
- size: `391`
- prototype: `__int64 __fastcall(void *lpBuffer, LPCVOID lpBaseAddress, SIZE_T nSize)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1004681c0`
- `0x100482e80`

## callees

- `0x1004815a0`

## import_xrefs

- `KERNEL32!ReadProcessMemory` at `0x1004816e5`
- `KERNEL32!ReadProcessMemory` at `0x1004816e5`
- `KERNEL32!VirtualQuery` at `0x10048164f`
- `KERNEL32!VirtualQuery` at `0x10048164f`
- `KERNEL32!GetCurrentProcess` at `0x1004815fe`
- `KERNEL32!GetCurrentProcess` at `0x1004816c6`
- `KERNEL32!GetCurrentProcess` at `0x1004815fe`
- `KERNEL32!GetCurrentProcess` at `0x1004816c6`
- `KERNEL32!GetLastError` at `0x100481702`
- `KERNEL32!GetLastError` at `0x100481702`

## pseudocode

```c
signed int __fastcall DmpCopyMemorySafely(void *lpBuffer, char *lpBaseAddress, SIZE_T nSize)
{
  unsigned __int64 v6; // rbx
  SIZE_T v7; // rsi
  char *v8; // rdi
  HANDLE CurrentProcess; // rax
  SIZE_T v10; // rax
  signed int result; // eax
  HANDLE v12; // rax
  unsigned __int64 v13; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int64 v14; // [rsp+38h] [rbp-60h]
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+40h] [rbp-58h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+A8h] [rbp+10h] BYREF

  NumberOfBytesRead = 0;
  if ( !lpBaseAddress || !lpBuffer || !nSize )
    return -2147024809;
  v6 = (unsigned __int64)lpBaseAddress;
  v7 = nSize;
  v8 = lpBaseAddress;
  while ( 1 )
  {
    do
    {
      if ( s_QueryWorkingSetExRoutine )
      {
        v13 = v6;
        CurrentProcess = GetCurrentProcess();
        if ( s_QueryWorkingSetExRoutine(CurrentProcess, &v13, 0x10u) )
        {
          if ( (v14 & 1) != 0 )
          {
            if ( ((v14 >> 4) & 0xEE) == 0 )
              return -2147023898;
            v6 = s_dwPageSize + (~(unsigned __int64)(s_dwPageSize - 1) & v6);
            goto LABEL_15;
          }
        }
      }
      if ( VirtualQuery((LPCVOID)v6, &Buffer, 0x30u) != 48 )
        return -2147023898;
      v6 = (unsigned __int64)Buffer.BaseAddress + Buffer.RegionSize;
    }
    while ( (char *)Buffer.BaseAddress + Buffer.RegionSize <= v8 );
    if ( Buffer.State != 4096 || (Buffer.Protect & 0xEE) == 0 || (Buffer.Protect & 0x100) != 0 )
      return -2147023898;
LABEL_15:
    v10 = v6 - (_QWORD)v8;
    if ( v6 - (unsigned __int64)v8 >= v7 )
      v10 = v7;
    v8 += v10;
    v7 -= v10;
    if ( !v7 )
      break;
    if ( v6 > (unsigned __int64)v8 )
      return -2147023898;
  }
  v12 = GetCurrentProcess();
  if ( ReadProcessMemory(v12, lpBaseAddress, lpBuffer, nSize, &NumberOfBytesRead) )
  {
    result = -2147024597;
    if ( NumberOfBytesRead == nSize )
      return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1004815a0  mov     rax, rsp
0x1004815a3  push    rbp
0x1004815a4  push    r12
0x1004815a6  push    r14
0x1004815a8  push    r15
0x1004815aa  sub     rsp, 78h
0x1004815ae  xor     r12d, r12d
0x1004815b1  mov     rbp, r8
0x1004815b4  mov     [rax+10h], r12
0x1004815b8  mov     r14, rdx
0x1004815bb  mov     r15, rcx
0x1004815be  test    rdx, rdx
0x1004815c1  jz      loc_100481716
0x1004815c7  test    rcx, rcx
0x1004815ca  jz      loc_100481716
0x1004815d0  test    r8, r8
0x1004815d3  jz      loc_100481716
0x1004815d9  mov     [rax+8], rbx
0x1004815dd  mov     rbx, rdx
0x1004815e0  mov     [rax+18h], rsi
0x1004815e4  mov     rsi, r8
0x1004815e7  mov     [rax-28h], rdi
0x1004815eb  mov     rdi, rdx
0x1004815ee  xchg    ax, ax
0x1004815f0  cmp     cs:?s_QueryWorkingSetExRoutine@@3P6AHPEAX0K@ZEA, r12; int (*s_QueryWorkingSetExRoutine)(void *,void *,ulong)
0x1004815f7  jz      short loc_100481641
0x1004815f9  mov     [rsp+98h+var_68], rbx
0x1004815fe  call    cs:__imp_GetCurrentProcess
0x100481604  mov     r8d, 10h
0x10048160a  lea     rdx, [rsp+98h+var_68]
0x10048160f  mov     rcx, rax
0x100481612  call    cs:?s_QueryWorkingSetExRoutine@@3P6AHPEAX0K@ZEA; int (*s_QueryWorkingSetExRoutine)(void *,void *,ulong)
0x100481618  test    eax, eax
0x10048161a  jz      short loc_100481641
0x10048161c  mov     rax, [rsp+98h+var_60]
0x100481621  test    al, 1
0x100481623  jz      short loc_100481641
0x100481625  shr     rax, 4
0x100481629  test    al, 0EEh
0x10048162b  jz      short loc_1004816A0
0x10048162d  mov     edx, cs:?s_dwPageSize@@3KA; ulong s_dwPageSize
0x100481633  lea     ecx, [rdx-1]
0x100481636  not     rcx
0x100481639  and     rbx, rcx
0x10048163c  add     rbx, rdx
0x10048163f  jmp     short loc_100481682
0x100481641  mov     r8d, 30h ; '0'; dwLength
0x100481647  lea     rdx, [rsp+98h+Buffer]; lpBuffer
0x10048164c  mov     rcx, rbx; lpAddress
0x10048164f  call    cs:__imp_VirtualQuery
0x100481655  cmp     rax, 30h ; '0'
0x100481659  jnz     short loc_1004816A0
0x10048165b  mov     rbx, [rsp+98h+Buffer.RegionSize]
0x100481660  add     rbx, [rsp+98h+Buffer.BaseAddress]
0x100481665  cmp     rbx, rdi
0x100481668  jbe     short loc_1004815F0
0x10048166a  cmp     [rsp+98h+Buffer.State], 1000h
0x100481672  jnz     short loc_1004816A0
0x100481674  mov     eax, [rsp+98h+Buffer.Protect]
0x100481678  test    al, 0EEh
0x10048167a  jz      short loc_1004816A0
0x10048167c  bt      eax, 8
0x100481680  jb      short loc_1004816A0
0x100481682  mov     rax, rbx
0x100481685  sub     rax, rdi
0x100481688  cmp     rax, rsi
0x10048168b  cmovnb  rax, rsi
0x10048168f  add     rdi, rax
0x100481692  sub     rsi, rax
0x100481695  jz      short loc_1004816C6
0x100481697  cmp     rbx, rdi
0x10048169a  jbe     loc_1004815F0
0x1004816a0  mov     eax, 800703E6h
0x1004816a5  mov     rsi, [rsp+98h+arg_10]
0x1004816ad  mov     rbx, [rsp+98h+arg_0]
0x1004816b5  mov     rdi, [rsp+98h+var_28]
0x1004816ba  add     rsp, 78h
0x1004816be  pop     r15
0x1004816c0  pop     r14
0x1004816c2  pop     r12
0x1004816c4  pop     rbp
0x1004816c5  retn
0x1004816c6  call    cs:__imp_GetCurrentProcess
0x1004816cc  mov     r9, rbp; nSize
0x1004816cf  mov     r8, r15; lpBuffer
0x1004816d2  mov     rcx, rax; hProcess
0x1004816d5  mov     rdx, r14; lpBaseAddress
0x1004816d8  lea     rax, [rsp+98h+NumberOfBytesRead]
0x1004816e0  mov     [rsp+98h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1004816e5  call    cs:__imp_ReadProcessMemory
0x1004816eb  test    eax, eax
0x1004816ed  jz      short loc_100481702
0x1004816ef  cmp     [rsp+98h+NumberOfBytesRead], rbp
0x1004816f7  mov     eax, 8007012Bh
0x1004816fc  cmovz   eax, r12d
0x100481700  jmp     short loc_1004816A5
0x100481702  call    cs:__imp_GetLastError
0x100481708  test    eax, eax
0x10048170a  jle     short loc_1004816A5
0x10048170c  movzx   eax, ax
0x10048170f  or      eax, 80070000h
0x100481714  jmp     short loc_1004816A5
0x100481716  mov     eax, 80070057h
0x10048171b  add     rsp, 78h
0x10048171f  pop     r15
0x100481721  pop     r14
0x100481723  pop     r12
0x100481725  pop     rbp
0x100481726  retn
```

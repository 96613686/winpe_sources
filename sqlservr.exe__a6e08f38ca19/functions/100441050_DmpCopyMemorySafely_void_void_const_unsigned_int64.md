# DmpCopyMemorySafely(void *,void const *,unsigned __int64)

- ea: `0x100441050`
- end: `0x1004411d8`
- name: `?DmpCopyMemorySafely@@YAJPEAXPEBX_K@Z`
- size: `392`
- prototype: `__int64 __fastcall(void *lpBuffer, LPCVOID lpBaseAddress, SIZE_T nSize)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1004044e0`
- `0x100442be0`

## callees

- `0x100441050`

## import_xrefs

- `KERNEL32!ReadProcessMemory` at `0x100441195`
- `KERNEL32!ReadProcessMemory` at `0x100441195`
- `KERNEL32!GetLastError` at `0x1004411b2`
- `KERNEL32!GetLastError` at `0x1004411b2`
- `KERNEL32!GetCurrentProcess` at `0x1004410ae`
- `KERNEL32!GetCurrentProcess` at `0x100441176`
- `KERNEL32!GetCurrentProcess` at `0x1004410ae`
- `KERNEL32!GetCurrentProcess` at `0x100441176`
- `KERNEL32!VirtualQuery` at `0x1004410ff`
- `KERNEL32!VirtualQuery` at `0x1004410ff`

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
0x100441050  mov     rax, rsp
0x100441053  push    rbp
0x100441054  push    r12
0x100441056  push    r14
0x100441058  push    r15
0x10044105a  sub     rsp, 78h
0x10044105e  xor     r12d, r12d
0x100441061  mov     rbp, r8
0x100441064  mov     [rax+10h], r12
0x100441068  mov     r14, rdx
0x10044106b  mov     r15, rcx
0x10044106e  test    rdx, rdx
0x100441071  jz      loc_1004411C7
0x100441077  test    rcx, rcx
0x10044107a  jz      loc_1004411C7
0x100441080  test    r8, r8
0x100441083  jz      loc_1004411C7
0x100441089  mov     [rax+8], rbx
0x10044108d  mov     rbx, rdx
0x100441090  mov     [rax+18h], rsi
0x100441094  mov     rsi, r8
0x100441097  mov     [rax-28h], rdi
0x10044109b  mov     rdi, rdx
0x10044109e  xchg    ax, ax
0x1004410a0  cmp     cs:?s_QueryWorkingSetExRoutine@@3P6AHPEAX0K@ZEA, r12; int (*s_QueryWorkingSetExRoutine)(void *,void *,ulong)
0x1004410a7  jz      short loc_1004410F1
0x1004410a9  mov     [rsp+98h+var_68], rbx
0x1004410ae  call    cs:__imp_GetCurrentProcess
0x1004410b4  mov     r8d, 10h
0x1004410ba  lea     rdx, [rsp+98h+var_68]
0x1004410bf  mov     rcx, rax
0x1004410c2  call    cs:?s_QueryWorkingSetExRoutine@@3P6AHPEAX0K@ZEA; int (*s_QueryWorkingSetExRoutine)(void *,void *,ulong)
0x1004410c8  test    eax, eax
0x1004410ca  jz      short loc_1004410F1
0x1004410cc  mov     rax, [rsp+98h+var_60]
0x1004410d1  test    al, 1
0x1004410d3  jz      short loc_1004410F1
0x1004410d5  shr     rax, 4
0x1004410d9  test    al, 0EEh
0x1004410db  jz      short loc_100441150
0x1004410dd  mov     edx, cs:?s_dwPageSize@@3KA; ulong s_dwPageSize
0x1004410e3  lea     ecx, [rdx-1]
0x1004410e6  not     rcx
0x1004410e9  and     rbx, rcx
0x1004410ec  add     rbx, rdx
0x1004410ef  jmp     short loc_100441132
0x1004410f1  mov     r8d, 30h ; '0'; dwLength
0x1004410f7  lea     rdx, [rsp+98h+Buffer]; lpBuffer
0x1004410fc  mov     rcx, rbx; lpAddress
0x1004410ff  call    cs:__imp_VirtualQuery
0x100441105  cmp     rax, 30h ; '0'
0x100441109  jnz     short loc_100441150
0x10044110b  mov     rbx, [rsp+98h+Buffer.RegionSize]
0x100441110  add     rbx, [rsp+98h+Buffer.BaseAddress]
0x100441115  cmp     rbx, rdi
0x100441118  jbe     short loc_1004410A0
0x10044111a  cmp     [rsp+98h+Buffer.State], 1000h
0x100441122  jnz     short loc_100441150
0x100441124  mov     eax, [rsp+98h+Buffer.Protect]
0x100441128  test    al, 0EEh
0x10044112a  jz      short loc_100441150
0x10044112c  bt      eax, 8
0x100441130  jb      short loc_100441150
0x100441132  mov     rax, rbx
0x100441135  sub     rax, rdi
0x100441138  cmp     rax, rsi
0x10044113b  cmovnb  rax, rsi
0x10044113f  add     rdi, rax
0x100441142  sub     rsi, rax
0x100441145  jz      short loc_100441176
0x100441147  cmp     rbx, rdi
0x10044114a  jbe     loc_1004410A0
0x100441150  mov     eax, 800703E6h
0x100441155  mov     rsi, [rsp+98h+arg_10]
0x10044115d  mov     rbx, [rsp+98h+arg_0]
0x100441165  mov     rdi, [rsp+98h+var_28]
0x10044116a  add     rsp, 78h
0x10044116e  pop     r15
0x100441170  pop     r14
0x100441172  pop     r12
0x100441174  pop     rbp
0x100441175  retn
0x100441176  call    cs:__imp_GetCurrentProcess
0x10044117c  mov     r9, rbp; nSize
0x10044117f  mov     r8, r15; lpBuffer
0x100441182  mov     rcx, rax; hProcess
0x100441185  mov     rdx, r14; lpBaseAddress
0x100441188  lea     rax, [rsp+98h+NumberOfBytesRead]
0x100441190  mov     [rsp+98h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x100441195  call    cs:__imp_ReadProcessMemory
0x10044119b  test    eax, eax
0x10044119d  jz      short loc_1004411B2
0x10044119f  cmp     [rsp+98h+NumberOfBytesRead], rbp
0x1004411a7  mov     eax, 8007012Bh
0x1004411ac  cmovz   eax, r12d
0x1004411b0  jmp     short loc_100441155
0x1004411b2  call    cs:__imp_GetLastError
0x1004411b8  test    eax, eax
0x1004411ba  jle     short loc_100441155
0x1004411bc  movzx   eax, ax
0x1004411bf  or      eax, 80070000h
0x1004411c4  jmp     short loc_100441155
0x1004411c7  mov     eax, 80070057h
0x1004411cc  add     rsp, 78h
0x1004411d0  pop     r15
0x1004411d2  pop     r14
0x1004411d4  pop     r12
0x1004411d6  pop     rbp
0x1004411d7  retn
```

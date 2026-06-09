# DetourTransactionAbort

- ea: `0x10043de70`
- end: `0x10043dfa7`
- name: `DetourTransactionAbort`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10043cc10`
- `0x10043dfb0`

## callees

- `0x10043de70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10043df1e`
- `KERNEL32!HeapFree` at `0x10043df1e`
- `KERNEL32!GetProcessHeap` at `0x10043df10`
- `KERNEL32!GetProcessHeap` at `0x10043df10`
- `KERNEL32!VirtualProtect` at `0x10043dec5`
- `KERNEL32!VirtualProtect` at `0x10043df63`
- `KERNEL32!VirtualProtect` at `0x10043dec5`
- `KERNEL32!VirtualProtect` at `0x10043df63`
- `KERNEL32!FlushInstructionCache` at `0x10043df75`
- `KERNEL32!FlushInstructionCache` at `0x10043df75`
- `KERNEL32!GetCurrentThreadId` at `0x10043de74`
- `KERNEL32!GetCurrentThreadId` at `0x10043de74`
- `KERNEL32!GetCurrentProcess` at `0x10043df33`
- `KERNEL32!GetCurrentProcess` at `0x10043df33`

## pseudocode

```c
__int64 DetourTransactionAbort()
{
  __int64 result; // rax
  LPVOID v1; // rbx
  __int64 v2; // rdx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE CurrentProcess; // rax
  _QWORD *v6; // rbx
  void *v7; // rdi
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1004D3F60 != GetCurrentThreadId() )
    return 4317;
  v1 = lpMem;
  if ( lpMem )
  {
    do
    {
      VirtualProtect(
        *((LPVOID *)v1 + 3),
        *(unsigned __int8 *)(*((_QWORD *)v1 + 4) + 62LL),
        *((_DWORD *)v1 + 10),
        &flOldProtect);
      if ( !*((_DWORD *)v1 + 2) )
      {
        v2 = *((_QWORD *)v1 + 4);
        if ( v2 )
        {
          *(_OWORD *)v2 = 0;
          *(_OWORD *)(v2 + 16) = 0;
          *(_OWORD *)(v2 + 32) = 0;
          *(_OWORD *)(v2 + 48) = 0;
          *(_OWORD *)(v2 + 64) = 0;
          *(_OWORD *)(v2 + 80) = 0;
          *(_QWORD *)(v2 + 72) = *(_QWORD *)((v2 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
          *(_QWORD *)((v2 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v2;
          *((_QWORD *)v1 + 4) = 0;
        }
      }
      v3 = *(void **)v1;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
      v1 = v3;
    }
    while ( v3 );
  }
  lpMem = 0;
  CurrentProcess = GetCurrentProcess();
  v6 = lpBaseAddress;
  v7 = CurrentProcess;
  if ( lpBaseAddress )
  {
    do
    {
      VirtualProtect(v6, 0x10000u, 0x20u, &flOldProtect);
      FlushInstructionCache(v7, v6, 0x10000u);
      v6 = (_QWORD *)v6[1];
    }
    while ( v6 );
  }
  result = 0;
  qword_1004D3F80 = 0;
  dword_1004D3F60 = 0;
  return result;
}

```

## disassembly

```asm
0x10043de70  sub     rsp, 28h
0x10043de74  call    cs:__imp_GetCurrentThreadId
0x10043de7a  cmp     cs:dword_1004D3F60, eax
0x10043de80  jz      short loc_10043DE8C
0x10043de82  mov     eax, 10DDh
0x10043de87  add     rsp, 28h
0x10043de8b  retn
0x10043de8c  mov     [rsp+28h+arg_8], rbx
0x10043de91  mov     rbx, cs:lpMem
0x10043de98  mov     [rsp+28h+arg_10], rsi
0x10043de9d  xor     esi, esi
0x10043de9f  mov     [rsp+28h+var_8], rdi
0x10043dea4  test    rbx, rbx
0x10043dea7  jz      loc_10043DF2C
0x10043dead  nop     dword ptr [rax]
0x10043deb0  mov     rax, [rbx+20h]
0x10043deb4  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x10043deb9  mov     r8d, [rbx+28h]; flNewProtect
0x10043debd  mov     rcx, [rbx+18h]; lpAddress
0x10043dec1  movzx   edx, byte ptr [rax+3Eh]; dwSize
0x10043dec5  call    cs:__imp_VirtualProtect
0x10043decb  cmp     [rbx+8], esi
0x10043dece  jnz     short loc_10043DF0D
0x10043ded0  mov     rdx, [rbx+20h]
0x10043ded4  test    rdx, rdx
0x10043ded7  jz      short loc_10043DF0D
0x10043ded9  xorps   xmm0, xmm0
0x10043dedc  mov     rcx, rdx
0x10043dedf  movups  xmmword ptr [rdx], xmm0
0x10043dee2  and     rcx, 0FFFFFFFFFFFF0000h
0x10043dee9  movups  xmmword ptr [rdx+10h], xmm0
0x10043deed  movups  xmmword ptr [rdx+20h], xmm0
0x10043def1  movups  xmmword ptr [rdx+30h], xmm0
0x10043def5  movups  xmmword ptr [rdx+40h], xmm0
0x10043def9  movups  xmmword ptr [rdx+50h], xmm0
0x10043defd  mov     rax, [rcx+10h]
0x10043df01  mov     [rdx+48h], rax
0x10043df05  mov     [rcx+10h], rdx
0x10043df09  mov     [rbx+20h], rsi
0x10043df0d  mov     rdi, [rbx]
0x10043df10  call    cs:__imp_GetProcessHeap
0x10043df16  mov     r8, rbx; lpMem
0x10043df19  xor     edx, edx; dwFlags
0x10043df1b  mov     rcx, rax; hHeap
0x10043df1e  call    cs:__imp_HeapFree
0x10043df24  mov     rbx, rdi
0x10043df27  test    rdi, rdi
0x10043df2a  jnz     short loc_10043DEB0
0x10043df2c  mov     cs:lpMem, rsi
0x10043df33  call    cs:__imp_GetCurrentProcess
0x10043df39  mov     rbx, cs:lpBaseAddress
0x10043df40  mov     rdi, rax
0x10043df43  test    rbx, rbx
0x10043df46  jz      short loc_10043DF84
0x10043df48  nop     dword ptr [rax+rax]
0x10043df4c  nop     dword ptr [rax+00h]
0x10043df50  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x10043df55  mov     edx, 10000h; dwSize
0x10043df5a  mov     r8d, 20h ; ' '; flNewProtect
0x10043df60  mov     rcx, rbx; lpAddress
0x10043df63  call    cs:__imp_VirtualProtect
0x10043df69  mov     r8d, 10000h; dwSize
0x10043df6f  mov     rdx, rbx; lpBaseAddress
0x10043df72  mov     rcx, rdi; hProcess
0x10043df75  call    cs:__imp_FlushInstructionCache
0x10043df7b  mov     rbx, [rbx+8]
0x10043df7f  test    rbx, rbx
0x10043df82  jnz     short loc_10043DF50
0x10043df84  mov     rdi, [rsp+28h+var_8]
0x10043df89  xor     eax, eax
0x10043df8b  mov     rbx, [rsp+28h+arg_8]
0x10043df90  mov     cs:qword_1004D3F80, rsi
0x10043df97  mov     cs:dword_1004D3F60, esi
0x10043df9d  mov     rsi, [rsp+28h+arg_10]
0x10043dfa2  add     rsp, 28h
0x10043dfa6  retn
```

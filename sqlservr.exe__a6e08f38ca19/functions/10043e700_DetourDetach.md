# DetourDetach

- ea: `0x10043e700`
- end: `0x10043e88a`
- name: `DetourDetach`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10043cc10`

## callees

- `0x10043dcf0`
- `0x10043e700`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10043e866`
- `KERNEL32!HeapFree` at `0x10043e866`
- `KERNEL32!GetProcessHeap` at `0x10043e785`
- `KERNEL32!GetProcessHeap` at `0x10043e858`
- `KERNEL32!GetProcessHeap` at `0x10043e785`
- `KERNEL32!GetProcessHeap` at `0x10043e858`
- `KERNEL32!VirtualProtect` at `0x10043e803`
- `KERNEL32!VirtualProtect` at `0x10043e803`
- `KERNEL32!HeapAlloc` at `0x10043e794`
- `KERNEL32!HeapAlloc` at `0x10043e794`
- `KERNEL32!GetLastError` at `0x10043e80d`
- `KERNEL32!GetLastError` at `0x10043e80d`
- `KERNEL32!GetCurrentThreadId` at `0x10043e710`
- `KERNEL32!GetCurrentThreadId` at `0x10043e710`

## pseudocode

```c
__int64 __fastcall DetourDetach(_QWORD *a1, __int64 a2)
{
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  void *v10; // rbp
  SIZE_T v11; // rdx
  DWORD LastError; // edi
  HANDLE v13; // rax
  DWORD flOldProtect; // [rsp+40h] [rbp+18h] BYREF

  if ( dword_1004D3F60 != GetCurrentThreadId() )
    return 4317;
  result = (unsigned int)dword_1004D3F5C;
  if ( !dword_1004D3F5C )
  {
    if ( !a2 )
      return 87;
    if ( !a1 )
      return 6;
    if ( !*a1 )
    {
      dword_1004D3F5C = 6;
      qword_1004D3F70 = (__int64)a1;
      return 6;
    }
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 0, 0x30u);
    if ( v6 )
    {
      v7 = DetourCodeFromPointer(*a1, 0);
      v8 = DetourCodeFromPointer(a2, 0);
      v9 = *(unsigned __int8 *)(v7 + 62);
      v10 = (void *)(*(_QWORD *)(v7 + 72) - v9);
      if ( (_BYTE)v9 && (v11 = *(unsigned __int8 *)(v7 + 62), v9 <= 0x1E) && *(_QWORD *)(v7 + 80) == v8 )
      {
        _mm_lfence();
        flOldProtect = 0;
        if ( VirtualProtect(v10, v11, 0x40u, &flOldProtect) )
        {
          v6[2] = 1;
          *((_QWORD *)v6 + 2) = a1;
          *((_QWORD *)v6 + 4) = v7;
          *((_QWORD *)v6 + 3) = v10;
          v6[10] = flOldProtect;
          *(_QWORD *)v6 = lpMem;
          result = 0;
          lpMem = v6;
          return result;
        }
        LastError = GetLastError();
      }
      else
      {
        LastError = 9;
        if ( dword_1004A3834 )
          goto LABEL_21;
      }
    }
    else
    {
      v6 = 0;
      LastError = 8;
    }
    dword_1004D3F5C = LastError;
    if ( !v6 )
    {
LABEL_22:
      qword_1004D3F70 = (__int64)a1;
      return LastError;
    }
LABEL_21:
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v6);
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x10043e700  mov     [rsp+arg_18], rbp
0x10043e705  push    rsi
0x10043e706  sub     rsp, 20h
0x10043e70a  mov     rbp, rdx
0x10043e70d  mov     rsi, rcx
0x10043e710  call    cs:__imp_GetCurrentThreadId
0x10043e716  cmp     cs:dword_1004D3F60, eax
0x10043e71c  jz      short loc_10043E72E
0x10043e71e  mov     eax, 10DDh
0x10043e723  mov     rbp, [rsp+28h+arg_18]
0x10043e728  add     rsp, 20h
0x10043e72c  pop     rsi
0x10043e72d  retn
0x10043e72e  mov     eax, cs:dword_1004D3F5C
0x10043e734  test    eax, eax
0x10043e736  jnz     loc_10043E87F
0x10043e73c  test    rbp, rbp
0x10043e73f  jnz     short loc_10043E74F
0x10043e741  lea     eax, [rbp+57h]
0x10043e744  mov     rbp, [rsp+28h+arg_18]
0x10043e749  add     rsp, 20h
0x10043e74d  pop     rsi
0x10043e74e  retn
0x10043e74f  test    rsi, rsi
0x10043e752  jz      short loc_10043E76B
0x10043e754  cmp     qword ptr [rsi], 0
0x10043e758  jnz     short loc_10043E77B
0x10043e75a  mov     cs:dword_1004D3F5C, 6
0x10043e764  mov     cs:qword_1004D3F70, rsi
0x10043e76b  mov     eax, 6
0x10043e770  mov     rbp, [rsp+28h+arg_18]
0x10043e775  add     rsp, 20h
0x10043e779  pop     rsi
0x10043e77a  retn
0x10043e77b  mov     [rsp+28h+arg_0], rbx
0x10043e780  mov     [rsp+28h+arg_8], rdi
0x10043e785  call    cs:__imp_GetProcessHeap
0x10043e78b  xor     edx, edx; dwFlags
0x10043e78d  mov     rcx, rax; hHeap
0x10043e790  lea     r8d, [rdx+30h]; dwBytes
0x10043e794  call    cs:__imp_HeapAlloc
0x10043e79a  mov     rbx, rax
0x10043e79d  test    rax, rax
0x10043e7a0  jz      loc_10043E846
0x10043e7a6  mov     rcx, [rsi]
0x10043e7a9  xor     edx, edx
0x10043e7ab  call    DetourCodeFromPointer
0x10043e7b0  xor     edx, edx
0x10043e7b2  mov     rcx, rbp
0x10043e7b5  mov     rdi, rax
0x10043e7b8  call    DetourCodeFromPointer
0x10043e7bd  movzx   ecx, byte ptr [rdi+3Eh]
0x10043e7c1  mov     rbp, [rdi+48h]
0x10043e7c5  sub     rbp, rcx
0x10043e7c8  test    cl, cl
0x10043e7ca  jz      short loc_10043E7DA
0x10043e7cc  mov     edx, ecx; dwSize
0x10043e7ce  cmp     rcx, 1Eh
0x10043e7d2  ja      short loc_10043E7DA
0x10043e7d4  cmp     [rdi+50h], rax
0x10043e7d8  jz      short loc_10043E7EA
0x10043e7da  cmp     cs:dword_1004A3834, 0
0x10043e7e1  mov     edi, 9
0x10043e7e6  jnz     short loc_10043E858
0x10043e7e8  jmp     short loc_10043E84D
0x10043e7ea  lfence
0x10043e7ed  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x10043e7f2  mov     [rsp+28h+flOldProtect], 0
0x10043e7fa  mov     r8d, 40h ; '@'; flNewProtect
0x10043e800  mov     rcx, rbp; lpAddress
0x10043e803  call    cs:__imp_VirtualProtect
0x10043e809  test    eax, eax
0x10043e80b  jnz     short loc_10043E817
0x10043e80d  call    cs:__imp_GetLastError
0x10043e813  mov     edi, eax
0x10043e815  jmp     short loc_10043E84D
0x10043e817  mov     dword ptr [rbx+8], 1
0x10043e81e  mov     [rbx+10h], rsi
0x10043e822  mov     [rbx+20h], rdi
0x10043e826  mov     [rbx+18h], rbp
0x10043e82a  mov     eax, [rsp+28h+flOldProtect]
0x10043e82e  mov     [rbx+28h], eax
0x10043e831  mov     rax, cs:lpMem
0x10043e838  mov     [rbx], rax
0x10043e83b  xor     eax, eax
0x10043e83d  mov     cs:lpMem, rbx
0x10043e844  jmp     short loc_10043E875
0x10043e846  xor     ebx, ebx
0x10043e848  mov     edi, 8
0x10043e84d  mov     cs:dword_1004D3F5C, edi
0x10043e853  test    rbx, rbx
0x10043e856  jz      short loc_10043E86C
0x10043e858  call    cs:__imp_GetProcessHeap
0x10043e85e  mov     r8, rbx; lpMem
0x10043e861  xor     edx, edx; dwFlags
0x10043e863  mov     rcx, rax; hHeap
0x10043e866  call    cs:__imp_HeapFree
0x10043e86c  mov     cs:qword_1004D3F70, rsi
0x10043e873  mov     eax, edi
0x10043e875  mov     rbx, [rsp+28h+arg_0]
0x10043e87a  mov     rdi, [rsp+28h+arg_8]
0x10043e87f  mov     rbp, [rsp+28h+arg_18]
0x10043e884  add     rsp, 20h
0x10043e888  pop     rsi
0x10043e889  retn
```

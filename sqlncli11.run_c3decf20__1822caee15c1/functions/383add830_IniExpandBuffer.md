# IniExpandBuffer

- ea: `0x383add830`
- end: `0x383add95f`
- name: `IniExpandBuffer`
- size: `303`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x383addad0`

## callees

- `0x3838427d0`
- `0x383add830`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x383add8f0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x383add8f0`
- `KERNEL32!CompareStringW` at `0x383add8bd`
- `KERNEL32!CompareStringW` at `0x383add8bd`
- `KERNEL32!HeapAlloc` at `0x383add878`
- `KERNEL32!HeapAlloc` at `0x383add92a`
- `KERNEL32!HeapAlloc` at `0x383add878`
- `KERNEL32!HeapAlloc` at `0x383add92a`
- `KERNEL32!HeapFree` at `0x383add911`
- `KERNEL32!HeapFree` at `0x383add911`
- `KERNEL32!GetProcessHeap` at `0x383add86a`
- `KERNEL32!GetProcessHeap` at `0x383add903`
- `KERNEL32!GetProcessHeap` at `0x383add91c`
- `KERNEL32!GetProcessHeap` at `0x383add86a`
- `KERNEL32!GetProcessHeap` at `0x383add903`
- `KERNEL32!GetProcessHeap` at `0x383add91c`

## pseudocode

```c
LPVOID __fastcall IniExpandBuffer(LPCWSTR lpSrc)
{
  int v2; // r15d
  __int64 v3; // rbx
  signed int v4; // esi
  HANDLE ProcessHeap; // rax
  LPVOID result; // rax
  void *v7; // rbp
  signed int v8; // edi
  bool v9; // cc
  HANDLE v10; // rax
  HANDLE v11; // rax

  v2 = 128;
  v3 = -1;
  do
    ++v3;
  while ( lpSrc[v3] );
  v4 = v3 + 128;
  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 0, 2LL * (unsigned int)(v3 + 128));
  v7 = result;
  while ( result )
  {
    if ( CompareStringW(0x400u, 1u, lpSrc, v3, (PCNZWCH)sub_383ADD960, 5) == 2 )
    {
      v8 = dword_383B2BE00;
      v9 = dword_383B2BE00 <= v4;
      if ( dword_383B2BE00 > (unsigned int)v4 )
        goto LABEL_9;
      memcpy(v7, byte_383B2C020, (unsigned int)(2 * dword_383B2BE00));
    }
    else
    {
      v8 = ExpandEnvironmentStringsW(lpSrc, (LPWSTR)v7, v4);
    }
    v9 = v8 <= v4;
LABEL_9:
    if ( v9 )
      return v7;
    v2 *= 2;
    v4 = v3 + v2;
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v7);
    v11 = GetProcessHeap();
    result = HeapAlloc(v11, 0, 2LL * (unsigned int)(v3 + v2));
    v7 = result;
  }
  return result;
}

```

## disassembly

```asm
0x383add830  mov     [rsp+arg_8], rbx
0x383add835  mov     [rsp+arg_10], rbp
0x383add83a  mov     [rsp+arg_18], rsi
0x383add83f  push    rdi
0x383add840  push    r14
0x383add842  push    r15
0x383add844  sub     rsp, 30h
0x383add848  mov     r14, rcx
0x383add84b  mov     r15d, 80h
0x383add851  or      rbx, 0FFFFFFFFFFFFFFFFh
0x383add855  inc     rbx
0x383add858  cmp     word ptr [rcx+rbx*2], 0
0x383add85d  jnz     short loc_383ADD855
0x383add85f  lea     esi, [rbx+80h]
0x383add865  mov     edi, esi
0x383add867  add     rdi, rdi
0x383add86a  call    cs:__imp_GetProcessHeap
0x383add870  mov     r8, rdi; dwBytes
0x383add873  mov     rcx, rax; hHeap
0x383add876  xor     edx, edx; dwFlags
0x383add878  call    cs:__imp_HeapAlloc
0x383add87e  mov     rbp, rax
0x383add881  test    rax, rax
0x383add884  jz      loc_383ADD946
0x383add88a  mov     [rsp+48h+arg_0], r12
0x383add88f  lea     r12, sub_383ADD960
0x383add896  nop     word ptr [rax+rax+00000000h]
0x383add8a0  mov     r9d, ebx; cchCount1
0x383add8a3  mov     r8, r14; lpString1
0x383add8a6  mov     edx, 1; dwCmpFlags
0x383add8ab  mov     ecx, 400h; Locale
0x383add8b0  mov     [rsp+48h+cchCount2], 5; cchCount2
0x383add8b8  mov     [rsp+48h+lpString2], r12; lpString2
0x383add8bd  call    cs:__imp_CompareStringW
0x383add8c3  cmp     eax, 2
0x383add8c6  jnz     short loc_383ADD8E7
0x383add8c8  mov     edi, cs:dword_383B2BE00
0x383add8ce  cmp     edi, esi
0x383add8d0  ja      short loc_383ADD8FA
0x383add8d2  lea     r8d, [rdi+rdi]; Size
0x383add8d6  lea     rdx, byte_383B2C020; Src
0x383add8dd  mov     rcx, rbp; void *
0x383add8e0  call    memcpy
0x383add8e5  jmp     short loc_383ADD8F8
0x383add8e7  mov     r8d, esi; nSize
0x383add8ea  mov     rdx, rbp; lpDst
0x383add8ed  mov     rcx, r14; lpSrc
0x383add8f0  call    cs:__imp_ExpandEnvironmentStringsW
0x383add8f6  mov     edi, eax
0x383add8f8  cmp     edi, esi
0x383add8fa  jle     short loc_383ADD93E
0x383add8fc  add     r15d, r15d
0x383add8ff  lea     esi, [rbx+r15]
0x383add903  call    cs:__imp_GetProcessHeap
0x383add909  mov     r8, rbp; lpMem
0x383add90c  mov     rcx, rax; hHeap
0x383add90f  xor     edx, edx; dwFlags
0x383add911  call    cs:__imp_HeapFree
0x383add917  mov     edi, esi
0x383add919  add     rdi, rdi
0x383add91c  call    cs:__imp_GetProcessHeap
0x383add922  mov     r8, rdi; dwBytes
0x383add925  mov     rcx, rax; hHeap
0x383add928  xor     edx, edx; dwFlags
0x383add92a  call    cs:__imp_HeapAlloc
0x383add930  mov     rbp, rax
0x383add933  test    rax, rax
0x383add936  jnz     loc_383ADD8A0
0x383add93c  jmp     short loc_383ADD941
0x383add93e  mov     rax, rbp
0x383add941  mov     r12, [rsp+48h+arg_0]
0x383add946  mov     rbx, [rsp+48h+arg_8]
0x383add94b  mov     rbp, [rsp+48h+arg_10]
0x383add950  mov     rsi, [rsp+48h+arg_18]
0x383add955  add     rsp, 30h
0x383add959  pop     r15
0x383add95b  pop     r14
0x383add95d  pop     rdi
0x383add95e  retn
```

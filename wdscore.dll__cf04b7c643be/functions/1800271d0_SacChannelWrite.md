# SacChannelWrite

- ea: `0x1800271d0`
- end: `0x180027304`
- name: `SacChannelWrite`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027178`

## callees

- `0x1800271d0`
- `0x1800274c6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027239`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027239`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800272db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029908`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800272db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029908`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800272c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800298f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800272c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800298f4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800272a3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800272a3`

## pseudocode

```c
__int64 __fastcall SacChannelWrite(__int64 a1, const void *a2, unsigned int a3)
{
  size_t v3; // r14
  void *v6; // rdi
  void *v7; // rsi
  unsigned int v8; // ebx
  DWORD v9; // r12d
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // rax
  HANDLE v12; // rax
  DWORD BytesReturned; // [rsp+98h] [rbp+20h] BYREF

  v3 = a3;
  BytesReturned = 0;
  v6 = 0;
  v7 = *(void **)(a1 + 16);
  if ( v7
    && v7 != (void *)-1LL
    && a2
    && a3
    && (v9 = a3 + 28, ProcessHeap = GetProcessHeap(), v11 = HeapAlloc(ProcessHeap, 8u, v9), (v6 = v11) != 0) )
  {
    *(_OWORD *)v11 = *(_OWORD *)a1;
    v11[6] = v3;
    memcpy_0(v11 + 7, a2, v3);
    v8 = DeviceIoControl(v7, 0x22800Cu, v6, v9, 0, 0, &BytesReturned, 0);
  }
  else
  {
    v8 = 0;
  }
  if ( v6 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v6);
  }
  return v8;
}

```

## disassembly

```asm
0x1800271d0  mov     rax, rsp
0x1800271d3  mov     [rax+8], rbx
0x1800271d7  mov     [rax+10h], rsi
0x1800271db  push    rdi
0x1800271dc  push    r12
0x1800271de  push    r13
0x1800271e0  push    r14
0x1800271e2  push    r15
0x1800271e4  sub     rsp, 50h
0x1800271e8  mov     r14d, r8d
0x1800271eb  mov     r15, rdx
0x1800271ee  mov     r13, rcx
0x1800271f1  mov     dword ptr [rax+20h], 0
0x1800271f8  xor     edi, edi
0x1800271fa  mov     [rax-30h], rdi
0x1800271fe  mov     rsi, [rcx+10h]
0x180027202  test    rsi, rsi
0x180027205  jnz     short loc_18002720E
0x180027207  xor     ebx, ebx
0x180027209  jmp     loc_1800272C2
0x18002720e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180027212  jz      short loc_180027207
0x180027214  test    r15, r15
0x180027217  jz      short loc_180027207
0x180027219  test    r8d, r8d
0x18002721c  jz      short loc_180027207
0x18002721e  lea     r12d, [r14+1Ch]
0x180027222  call    cs:__imp_GetProcessHeap
0x180027229  nop     dword ptr [rax+rax+00h]
0x18002722e  mov     rcx, rax; hHeap
0x180027231  mov     r8d, r12d; dwBytes
0x180027234  mov     edx, 8; dwFlags
0x180027239  call    cs:__imp_HeapAlloc
0x180027240  nop     dword ptr [rax+rax+00h]
0x180027245  mov     rdi, rax
0x180027248  mov     [rsp+78h+var_30], rax
0x18002724d  test    rax, rax
0x180027250  jz      short loc_180027207
0x180027252  movups  xmm0, xmmword ptr [r13+0]
0x180027257  movdqu  xmmword ptr [rax], xmm0
0x18002725b  mov     [rax+18h], r14d
0x18002725f  lea     rcx, [rax+1Ch]; void *
0x180027263  mov     r8, r14; Size
0x180027266  mov     rdx, r15; Src
0x180027269  call    memcpy_0
0x18002726e  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180027277  lea     rax, [rsp+78h+BytesReturned]
0x18002727f  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x180027284  mov     [rsp+78h+nOutBufferSize], 0; nOutBufferSize
0x18002728c  mov     [rsp+78h+lpOutBuffer], 0; lpOutBuffer
0x180027295  mov     r9d, r12d; nInBufferSize
0x180027298  mov     r8, rdi; lpInBuffer
0x18002729b  mov     edx, 22800Ch; dwIoControlCode
0x1800272a0  mov     rcx, rsi; hDevice
0x1800272a3  call    cs:__imp_DeviceIoControl
0x1800272aa  nop     dword ptr [rax+rax+00h]
0x1800272af  mov     ebx, eax
0x1800272b1  mov     [rsp+78h+var_38], eax
0x1800272b5  jmp     short loc_1800272C2
0x1800272b7  xor     ebx, ebx
0x1800272b9  mov     [rsp+78h+var_38], ebx
0x1800272bd  mov     rdi, [rsp+78h+var_30]
0x1800272c2  test    rdi, rdi
0x1800272c5  jz      short loc_1800272E7
0x1800272c7  call    cs:__imp_GetProcessHeap
0x1800272ce  nop     dword ptr [rax+rax+00h]
0x1800272d3  mov     rcx, rax; hHeap
0x1800272d6  mov     r8, rdi; lpMem
0x1800272d9  xor     edx, edx; dwFlags
0x1800272db  call    cs:__imp_HeapFree
0x1800272e2  nop     dword ptr [rax+rax+00h]
0x1800272e7  mov     eax, ebx
0x1800272e9  lea     r11, [rsp+78h+var_28]
0x1800272ee  mov     rbx, [r11+30h]
0x1800272f2  mov     rsi, [r11+38h]
0x1800272f6  mov     rsp, r11
0x1800272f9  pop     r15
0x1800272fb  pop     r14
0x1800272fd  pop     r13
0x1800272ff  pop     r12
0x180027301  pop     rdi
0x180027302  retn
0x1800298e1  push    rbx
0x1800298e3  push    rbp
0x1800298e4  sub     rsp, 48h
0x1800298e8  mov     rbp, rdx
0x1800298eb  mov     rbx, [rbp+48h]
0x1800298ef  test    rbx, rbx
0x1800298f2  jz      short loc_180029915
0x1800298f4  call    cs:__imp_GetProcessHeap
0x1800298fb  nop     dword ptr [rax+rax+00h]
0x180029900  mov     rcx, rax; hHeap
0x180029903  mov     r8, rbx; lpMem
0x180029906  xor     edx, edx; dwFlags
0x180029908  call    cs:__imp_HeapFree
0x18002990f  nop     dword ptr [rax+rax+00h]
0x180029914  nop
0x180029915  add     rsp, 48h
0x180029919  pop     rbp
0x18002991a  pop     rbx
0x18002991b  retn
```

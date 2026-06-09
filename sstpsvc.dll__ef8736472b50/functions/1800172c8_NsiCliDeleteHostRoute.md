# NsiCliDeleteHostRoute

- ea: `0x1800172c8`
- end: `0x180017463`
- name: `NsiCliDeleteHostRoute`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016a10`

## callees

- `0x180016be0`
- `0x1800172c8`
- `0x18001765c`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800173f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017419`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001743a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800173f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017419`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001743a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800173e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017405`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017425`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800173e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017405`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017425`

## pseudocode

```c
__int64 __fastcall NsiCliDeleteHostRoute(__int64 a1, int a2)
{
  __int64 result; // rax
  void *v3; // rdi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  LPVOID lpMem; // [rsp+78h] [rbp-41h] BYREF
  LPVOID v9; // [rsp+80h] [rbp-39h] BYREF
  LPVOID v10; // [rsp+88h] [rbp-31h]
  _OWORD v11[5]; // [rsp+90h] [rbp-29h] BYREF

  lpMem = 0;
  v9 = 0;
  memset(v11, 0, 29);
  v10 = 0;
  memset(&v11[2], 0, 48);
  result = AllocateAndGetTable((unsigned int)&NPI_MS_IPV4_MODULEID, a2, (unsigned int)&lpMem, 48, (__int64)&v9);
  if ( !(_DWORD)result )
  {
    v3 = lpMem;
    v4 = v9;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v4);
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v10);
    return 1168;
  }
  return result;
}

```

## disassembly

```asm
0x1800172c8  push    rbp
0x1800172ca  push    rbx
0x1800172cb  push    rsi
0x1800172cc  push    rdi
0x1800172cd  push    r14
0x1800172cf  lea     rbp, [rsp-37h]
0x1800172d4  sub     rsp, 0F0h
0x1800172db  mov     rax, cs:__security_cookie
0x1800172e2  xor     rax, rsp
0x1800172e5  mov     [rbp+57h+var_30], rax
0x1800172e9  xorps   xmm0, xmm0
0x1800172ec  lea     r8, [rbp+57h+lpMem]
0x1800172f0  xor     ebx, ebx
0x1800172f2  xor     eax, eax
0x1800172f4  lea     rax, [rbp+57h+var_A0]
0x1800172f8  mov     [rbp+57h+lpMem], rbx
0x1800172fc  mov     [rsp+110h+var_B0], rax
0x180017301  mov     r14d, ecx
0x180017304  lea     rax, [rbp+57h+var_88]
0x180017308  mov     [rsp+110h+var_D8], 14h
0x180017310  mov     [rsp+110h+var_E0], rax
0x180017315  lea     r9d, [rbx+30h]
0x180017319  lea     rax, [rbp+57h+var_90]
0x18001731d  mov     [rbp+57h+var_90], rbx
0x180017321  movups  [rbp+57h+var_80], xmm0
0x180017325  lea     rcx, NPI_MS_IPV4_MODULEID
0x18001732c  mov     [rsp+110h+var_F0], rax
0x180017331  mov     [rbp+57h+var_88], rbx
0x180017335  mov     [rbp+57h+var_A0], ebx
0x180017338  movups  [rbp+57h+var_60], xmm0
0x18001733c  movups  [rbp+57h+var_50], xmm0
0x180017340  movups  [rbp+57h+var_40], xmm0
0x180017344  movups  [rbp+57h+var_80+0Dh], xmm0
0x180017348  call    AllocateAndGetTable
0x18001734d  test    eax, eax
0x18001734f  jnz     loc_180017448
0x180017355  mov     rdi, [rbp+57h+lpMem]
0x180017359  mov     ecx, ebx
0x18001735b  mov     rbx, [rbp+57h+var_90]
0x18001735f  mov     esi, 490h
0x180017364  cmp     ecx, [rbp+57h+var_A0]
0x180017367  jnb     short loc_1800173E5
0x180017369  mov     eax, ecx
0x18001736b  lea     rdx, [rax+rax*2]
0x18001736f  add     rdx, rdx
0x180017372  cmp     [rdi+rdx*8+4], r14d
0x180017377  jnz     short loc_18001738B
0x180017379  shl     rax, 5
0x18001737d  cmp     dword ptr [rax+rbx+10h], 3
0x180017382  jnz     short loc_18001738B
0x180017384  cmp     dword ptr [rax+rbx+0Ch], 1
0x180017389  jz      short loc_18001738F
0x18001738b  inc     ecx
0x18001738d  jmp     short loc_180017364
0x18001738f  movups  xmm0, xmmword ptr [rdi+rdx*8]
0x180017393  mov     [rsp+110h+var_D8], 3
0x18001739b  lea     r9, [rbp+57h+var_60]
0x18001739f  movups  [rbp+57h+var_60], xmm0
0x1800173a3  movups  xmm1, xmmword ptr [rdi+rdx*8+10h]
0x1800173a8  movups  [rbp+57h+var_50], xmm1
0x1800173ac  movups  xmm0, xmmword ptr [rdi+rdx*8+20h]
0x1800173b1  lea     rdx, NPI_MS_IPV4_MODULEID
0x1800173b8  movups  [rbp+57h+var_40], xmm0
0x1800173bc  movups  xmm1, xmmword ptr [rax+rbx]
0x1800173c0  movups  [rbp+57h+var_80], xmm1
0x1800173c4  movups  xmm0, xmmword ptr [rax+rbx+10h]
0x1800173c9  lea     rax, [rbp+57h+var_80]
0x1800173cd  mov     [rsp+110h+var_E8], rax
0x1800173d2  movups  [rbp+57h+var_70], xmm0
0x1800173d6  mov     dword ptr [rsp+110h+var_F0], 30h ; '0'
0x1800173de  call    SetAllParameters
0x1800173e3  mov     esi, eax
0x1800173e5  call    cs:__imp_GetProcessHeap
0x1800173ec  nop     dword ptr [rax+rax+00h]
0x1800173f1  mov     r8, rdi; lpMem
0x1800173f4  xor     edx, edx; dwFlags
0x1800173f6  mov     rcx, rax; hHeap
0x1800173f9  call    cs:__imp_HeapFree
0x180017400  nop     dword ptr [rax+rax+00h]
0x180017405  call    cs:__imp_GetProcessHeap
0x18001740c  nop     dword ptr [rax+rax+00h]
0x180017411  mov     r8, rbx; lpMem
0x180017414  xor     edx, edx; dwFlags
0x180017416  mov     rcx, rax; hHeap
0x180017419  call    cs:__imp_HeapFree
0x180017420  nop     dword ptr [rax+rax+00h]
0x180017425  call    cs:__imp_GetProcessHeap
0x18001742c  nop     dword ptr [rax+rax+00h]
0x180017431  mov     r8, [rbp+57h+var_88]; lpMem
0x180017435  xor     edx, edx; dwFlags
0x180017437  mov     rcx, rax; hHeap
0x18001743a  call    cs:__imp_HeapFree
0x180017441  nop     dword ptr [rax+rax+00h]
0x180017446  mov     eax, esi
0x180017448  mov     rcx, [rbp+57h+var_30]
0x18001744c  xor     rcx, rsp; StackCookie
0x18001744f  call    __security_check_cookie
0x180017454  add     rsp, 0F0h
0x18001745b  pop     r14
0x18001745d  pop     rdi
0x18001745e  pop     rsi
0x18001745f  pop     rbx
0x180017460  pop     rbp
0x180017461  retn
```

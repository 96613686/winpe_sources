# NsiCliDeleteHostV6Route

- ea: `0x18001746c`
- end: `0x180017654`
- name: `NsiCliDeleteHostV6Route`
- size: `488`
- prototype: `__int64 __fastcall(void *Source2)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016a10`

## callees

- `0x180016be0`
- `0x18001746c`
- `0x18001765c`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800175e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017603`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017624`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800175e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017603`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017624`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800175cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800175ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001760f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800175cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800175ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001760f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180017537`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180017537`

## pseudocode

```c
__int64 __fastcall NsiCliDeleteHostV6Route(void *Source2)
{
  int v1; // edx
  __int64 result; // rax
  void *v3; // r14
  void *v4; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v9; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v10; // [rsp+88h] [rbp-78h]
  _OWORD v11[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v12; // [rsp+B0h] [rbp-50h] BYREF

  lpMem = 0;
  v9 = 0;
  v10 = 0;
  memset_0(&v12, 0, 0x48u);
  memset(v11, 0, 29);
  result = AllocateAndGetTable((unsigned int)&NPI_MS_IPV6_MODULEID, v1, (unsigned int)&lpMem, 72, (__int64)&v9);
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
0x18001746c  push    rbp
0x18001746e  push    rbx
0x18001746f  push    rsi
0x180017470  push    rdi
0x180017471  push    r12
0x180017473  push    r13
0x180017475  push    r14
0x180017477  push    r15
0x180017479  lea     rbp, [rsp-18h]
0x18001747e  sub     rsp, 118h
0x180017485  mov     rax, cs:__security_cookie
0x18001748c  xor     rax, rsp
0x18001748f  mov     [rbp+50h+var_50], rax
0x180017493  xor     edi, edi
0x180017495  mov     r13, rcx
0x180017498  xor     edx, edx; Val
0x18001749a  mov     [rsp+150h+lpMem], rdi
0x18001749f  lea     rcx, [rbp+50h+var_A0]; void *
0x1800174a3  mov     [rbp+50h+var_D0], rdi
0x1800174a7  mov     [rbp+50h+var_C8], rdi
0x1800174ab  lea     ebx, [rdi+48h]
0x1800174ae  mov     [rsp+150h+var_E0], edi
0x1800174b2  mov     r8d, ebx; Size
0x1800174b5  call    memset_0
0x1800174ba  xor     eax, eax
0x1800174bc  lea     r8, [rsp+150h+lpMem]
0x1800174c1  xorps   xmm0, xmm0
0x1800174c4  lea     rax, [rsp+150h+var_E0]
0x1800174c9  mov     [rsp+150h+var_F0], rax
0x1800174ce  lea     rcx, NPI_MS_IPV6_MODULEID
0x1800174d5  lea     rax, [rbp+50h+var_C8]
0x1800174d9  mov     [rsp+150h+var_118], 20h ; ' '
0x1800174e1  mov     [rsp+150h+var_120], rax
0x1800174e6  mov     r9d, ebx
0x1800174e9  lea     rax, [rbp+50h+var_D0]
0x1800174ed  movups  [rbp+50h+var_C0], xmm0
0x1800174f1  mov     [rsp+150h+var_130], rax
0x1800174f6  movups  [rbp+50h+var_C0+0Dh], xmm0
0x1800174fa  call    AllocateAndGetTable
0x1800174ff  test    eax, eax
0x180017501  jnz     loc_180017633
0x180017507  mov     r14, [rsp+150h+lpMem]
0x18001750c  mov     r12d, 490h
0x180017512  mov     rsi, [rbp+50h+var_D0]
0x180017516  cmp     edi, [rsp+150h+var_E0]
0x18001751a  jnb     loc_1800175CF
0x180017520  mov     ebx, edi
0x180017522  lea     rcx, [r14+4]
0x180017526  mov     r8d, 10h; Length
0x18001752c  mov     rdx, r13; Source2
0x18001752f  lea     r15, [rbx+rbx*8]
0x180017533  lea     rcx, [rcx+r15*8]; Source1
0x180017537  call    cs:__imp_RtlCompareMemory
0x18001753e  nop     dword ptr [rax+rax+00h]
0x180017543  cmp     rax, 10h
0x180017547  jnz     short loc_18001755B
0x180017549  shl     rbx, 5
0x18001754d  cmp     dword ptr [rbx+rsi+10h], 3
0x180017552  jnz     short loc_18001755B
0x180017554  cmp     dword ptr [rbx+rsi+0Ch], 1
0x180017559  jz      short loc_18001755F
0x18001755b  inc     edi
0x18001755d  jmp     short loc_180017516
0x18001755f  movups  xmm0, xmmword ptr [r14+r15*8]
0x180017564  lea     rax, [rbp+50h+var_C0]
0x180017568  mov     [rsp+150h+var_118], 3
0x180017570  mov     [rsp+150h+var_128], rax
0x180017575  lea     r9, [rbp+50h+var_A0]
0x180017579  movaps  [rbp+50h+var_A0], xmm0
0x18001757d  lea     rdx, NPI_MS_IPV6_MODULEID
0x180017584  movups  xmm1, xmmword ptr [r14+r15*8+10h]
0x18001758a  mov     dword ptr [rsp+150h+var_130], 48h ; 'H'
0x180017592  movaps  [rbp+50h+var_90], xmm1
0x180017596  movups  xmm0, xmmword ptr [r14+r15*8+20h]
0x18001759c  movaps  [rbp+50h+var_80], xmm0
0x1800175a0  movups  xmm1, xmmword ptr [r14+r15*8+30h]
0x1800175a6  movaps  [rbp+50h+var_70], xmm1
0x1800175aa  movsd   xmm0, qword ptr [r14+r15*8+40h]
0x1800175b1  movsd   [rbp+50h+var_60], xmm0
0x1800175b6  movups  xmm1, xmmword ptr [rbx+rsi]
0x1800175ba  movups  [rbp+50h+var_C0], xmm1
0x1800175be  movups  xmm0, xmmword ptr [rbx+rsi+10h]
0x1800175c3  movups  [rbp+50h+var_B0], xmm0
0x1800175c7  call    SetAllParameters
0x1800175cc  mov     r12d, eax
0x1800175cf  call    cs:__imp_GetProcessHeap
0x1800175d6  nop     dword ptr [rax+rax+00h]
0x1800175db  mov     r8, r14; lpMem
0x1800175de  xor     edx, edx; dwFlags
0x1800175e0  mov     rcx, rax; hHeap
0x1800175e3  call    cs:__imp_HeapFree
0x1800175ea  nop     dword ptr [rax+rax+00h]
0x1800175ef  call    cs:__imp_GetProcessHeap
0x1800175f6  nop     dword ptr [rax+rax+00h]
0x1800175fb  mov     r8, rsi; lpMem
0x1800175fe  xor     edx, edx; dwFlags
0x180017600  mov     rcx, rax; hHeap
0x180017603  call    cs:__imp_HeapFree
0x18001760a  nop     dword ptr [rax+rax+00h]
0x18001760f  call    cs:__imp_GetProcessHeap
0x180017616  nop     dword ptr [rax+rax+00h]
0x18001761b  mov     r8, [rbp+50h+var_C8]; lpMem
0x18001761f  xor     edx, edx; dwFlags
0x180017621  mov     rcx, rax; hHeap
0x180017624  call    cs:__imp_HeapFree
0x18001762b  nop     dword ptr [rax+rax+00h]
0x180017630  mov     eax, r12d
0x180017633  mov     rcx, [rbp+50h+var_50]
0x180017637  xor     rcx, rsp; StackCookie
0x18001763a  call    __security_check_cookie
0x18001763f  add     rsp, 118h
0x180017646  pop     r15
0x180017648  pop     r14
0x18001764a  pop     r13
0x18001764c  pop     r12
0x18001764e  pop     rdi
0x18001764f  pop     rsi
0x180017650  pop     rbx
0x180017651  pop     rbp
0x180017652  retn
```

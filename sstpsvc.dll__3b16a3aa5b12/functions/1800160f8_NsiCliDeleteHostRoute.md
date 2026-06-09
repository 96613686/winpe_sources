# NsiCliDeleteHostRoute

- ea: `0x1800160f8`
- end: `0x18001626e`
- name: `NsiCliDeleteHostRoute`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800158e0`

## callees

- `0x180015a98`
- `0x1800160f8`
- `0x180016438`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001624c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001624c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016215`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001623d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016215`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001623d`

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
0x1800160f8  push    rbp
0x1800160fa  push    rbx
0x1800160fb  push    rsi
0x1800160fc  push    rdi
0x1800160fd  push    r14
0x1800160ff  lea     rbp, [rsp-37h]
0x180016104  sub     rsp, 0F0h
0x18001610b  mov     rax, cs:__security_cookie
0x180016112  xor     rax, rsp
0x180016115  mov     [rbp+57h+var_30], rax
0x180016119  xorps   xmm0, xmm0
0x18001611c  lea     r8, [rbp+57h+lpMem]
0x180016120  xor     ebx, ebx
0x180016122  xor     eax, eax
0x180016124  lea     rax, [rbp+57h+var_A0]
0x180016128  mov     [rbp+57h+lpMem], rbx
0x18001612c  mov     [rsp+110h+var_B0], rax
0x180016131  mov     r14d, ecx
0x180016134  lea     rax, [rbp+57h+var_88]
0x180016138  mov     [rsp+110h+var_D8], 14h
0x180016140  mov     [rsp+110h+var_E0], rax
0x180016145  lea     r9d, [rbx+30h]
0x180016149  lea     rax, [rbp+57h+var_90]
0x18001614d  mov     [rbp+57h+var_90], rbx
0x180016151  movups  [rbp+57h+var_80], xmm0
0x180016155  lea     rcx, NPI_MS_IPV4_MODULEID
0x18001615c  mov     [rsp+110h+var_F0], rax
0x180016161  mov     [rbp+57h+var_88], rbx
0x180016165  mov     [rbp+57h+var_A0], ebx
0x180016168  movups  [rbp+57h+var_60], xmm0
0x18001616c  movups  [rbp+57h+var_50], xmm0
0x180016170  movups  [rbp+57h+var_40], xmm0
0x180016174  movups  [rbp+57h+var_80+0Dh], xmm0
0x180016178  call    AllocateAndGetTable
0x18001617d  test    eax, eax
0x18001617f  jnz     loc_180016254
0x180016185  mov     rdi, [rbp+57h+lpMem]
0x180016189  mov     ecx, ebx
0x18001618b  mov     rbx, [rbp+57h+var_90]
0x18001618f  mov     esi, 490h
0x180016194  cmp     ecx, [rbp+57h+var_A0]
0x180016197  jnb     short loc_180016215
0x180016199  mov     eax, ecx
0x18001619b  lea     rdx, [rax+rax*2]
0x18001619f  add     rdx, rdx
0x1800161a2  cmp     [rdi+rdx*8+4], r14d
0x1800161a7  jnz     short loc_1800161BB
0x1800161a9  shl     rax, 5
0x1800161ad  cmp     dword ptr [rax+rbx+10h], 3
0x1800161b2  jnz     short loc_1800161BB
0x1800161b4  cmp     dword ptr [rax+rbx+0Ch], 1
0x1800161b9  jz      short loc_1800161BF
0x1800161bb  inc     ecx
0x1800161bd  jmp     short loc_180016194
0x1800161bf  movups  xmm0, xmmword ptr [rdi+rdx*8]
0x1800161c3  mov     [rsp+110h+var_D8], 3
0x1800161cb  lea     r9, [rbp+57h+var_60]
0x1800161cf  movups  [rbp+57h+var_60], xmm0
0x1800161d3  movups  xmm1, xmmword ptr [rdi+rdx*8+10h]
0x1800161d8  movups  [rbp+57h+var_50], xmm1
0x1800161dc  movups  xmm0, xmmword ptr [rdi+rdx*8+20h]
0x1800161e1  lea     rdx, NPI_MS_IPV4_MODULEID
0x1800161e8  movups  [rbp+57h+var_40], xmm0
0x1800161ec  movups  xmm1, xmmword ptr [rax+rbx]
0x1800161f0  movups  [rbp+57h+var_80], xmm1
0x1800161f4  movups  xmm0, xmmword ptr [rax+rbx+10h]
0x1800161f9  lea     rax, [rbp+57h+var_80]
0x1800161fd  mov     [rsp+110h+var_E8], rax
0x180016202  movups  [rbp+57h+var_70], xmm0
0x180016206  mov     dword ptr [rsp+110h+var_F0], 30h ; '0'
0x18001620e  call    SetAllParameters
0x180016213  mov     esi, eax
0x180016215  call    cs:__imp_GetProcessHeap
0x18001621b  mov     r8, rdi; lpMem
0x18001621e  xor     edx, edx; dwFlags
0x180016220  mov     rcx, rax; hHeap
0x180016223  call    cs:__imp_HeapFree
0x180016229  call    cs:__imp_GetProcessHeap
0x18001622f  mov     r8, rbx; lpMem
0x180016232  xor     edx, edx; dwFlags
0x180016234  mov     rcx, rax; hHeap
0x180016237  call    cs:__imp_HeapFree
0x18001623d  call    cs:__imp_GetProcessHeap
0x180016243  mov     r8, [rbp+57h+var_88]; lpMem
0x180016247  xor     edx, edx; dwFlags
0x180016249  mov     rcx, rax; hHeap
0x18001624c  call    cs:__imp_HeapFree
0x180016252  mov     eax, esi
0x180016254  mov     rcx, [rbp+57h+var_30]
0x180016258  xor     rcx, rsp; StackCookie
0x18001625b  call    __security_check_cookie
0x180016260  add     rsp, 0F0h
0x180016267  pop     r14
0x180016269  pop     rdi
0x18001626a  pop     rsi
0x18001626b  pop     rbx
0x18001626c  pop     rbp
0x18001626d  retn
```

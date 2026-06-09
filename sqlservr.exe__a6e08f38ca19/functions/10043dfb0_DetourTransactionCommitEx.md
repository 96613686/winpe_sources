# DetourTransactionCommitEx

- ea: `0x10043dfb0`
- end: `0x10043e2ad`
- name: `DetourTransactionCommitEx`
- size: `765`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10043cc10`
- `0x10043d2c0`

## callees

- `0x100402880`
- `0x10043de70`
- `0x10043dfb0`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10043e16a`
- `KERNEL32!HeapFree` at `0x10043e16a`
- `KERNEL32!GetProcessHeap` at `0x10043e15c`
- `KERNEL32!GetProcessHeap` at `0x10043e15c`
- `KERNEL32!VirtualProtect` at `0x10043e0f5`
- `KERNEL32!VirtualProtect` at `0x10043e253`
- `KERNEL32!VirtualProtect` at `0x10043e0f5`
- `KERNEL32!VirtualProtect` at `0x10043e253`
- `KERNEL32!FlushInstructionCache` at `0x10043e10b`
- `KERNEL32!FlushInstructionCache` at `0x10043e265`
- `KERNEL32!FlushInstructionCache` at `0x10043e10b`
- `KERNEL32!FlushInstructionCache` at `0x10043e265`
- `KERNEL32!GetCurrentThreadId` at `0x10043dfc8`
- `KERNEL32!GetCurrentThreadId` at `0x10043dfc8`
- `KERNEL32!GetCurrentProcess` at `0x10043e0c1`
- `KERNEL32!GetCurrentProcess` at `0x10043e21c`
- `KERNEL32!GetCurrentProcess` at `0x10043e0c1`
- `KERNEL32!GetCurrentProcess` at `0x10043e21c`
- `KERNEL32!VirtualFree` at `0x10043e201`
- `KERNEL32!VirtualFree` at `0x10043e201`

## pseudocode

```c
__int64 __fastcall DetourTransactionCommitEx(_QWORD *a1)
{
  LPVOID v3; // rbx
  int i; // esi
  __int64 v5; // rdx
  __int64 v6; // rdx
  int v7; // ecx
  void *v8; // rcx
  __int64 v9; // r9
  size_t v10; // r8
  HANDLE CurrentProcess; // rax
  LPVOID v12; // rdi
  void *v13; // rbp
  __int64 v14; // rdx
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v17; // rcx
  LPCVOID *v18; // rbx
  unsigned int v19; // r8d
  unsigned __int64 *v20; // rdx
  unsigned __int64 v21; // rax
  HANDLE v22; // rax
  _QWORD *v23; // rbx
  void *v24; // rdi
  DWORD flOldProtect[4]; // [rsp+20h] [rbp-28h] BYREF

  if ( a1 )
    *a1 = qword_1004D3F70;
  if ( dword_1004D3F60 != GetCurrentThreadId() )
    return 4317;
  if ( dword_1004D3F5C )
  {
    DetourTransactionAbort();
    return (unsigned int)dword_1004D3F5C;
  }
  else
  {
    v3 = lpMem;
    for ( i = 0; v3; v3 = *(LPVOID *)v3 )
    {
      v5 = *((_QWORD *)v3 + 4);
      if ( *((_DWORD *)v3 + 2) )
      {
        memmove(*((void **)v3 + 3), (const void *)(v5 + 32), *(unsigned __int8 *)(v5 + 62));
        **((_QWORD **)v3 + 2) = *((_QWORD *)v3 + 3);
      }
      else
      {
        *(_WORD *)(v5 + 88) = 9727;
        *(_DWORD *)(v5 + 90) = -14;
        v6 = *((_QWORD *)v3 + 3);
        v7 = *((_QWORD *)v3 + 4) + 88;
        *(_BYTE *)v6 = -23;
        *(_DWORD *)(v6 + 1) = v7 - (v6 + 5);
        v8 = (void *)(v6 + 5);
        v9 = *((_QWORD *)v3 + 4);
        v10 = *(_QWORD *)(v9 + 72) - (v6 + 5);
        if ( (unsigned __int64)(v6 + 5) > *(_QWORD *)(v9 + 72) )
          v10 = 0;
        if ( v10 )
        {
          LOBYTE(v6) = -52;
          memset_0(v8, v6, v10);
          v9 = *((_QWORD *)v3 + 4);
        }
        **((_QWORD **)v3 + 2) = v9;
      }
    }
    CurrentProcess = GetCurrentProcess();
    v12 = lpMem;
    v13 = CurrentProcess;
    if ( lpMem )
    {
      do
      {
        VirtualProtect(
          *((LPVOID *)v12 + 3),
          *(unsigned __int8 *)(*((_QWORD *)v12 + 4) + 62LL),
          *((_DWORD *)v12 + 10),
          flOldProtect);
        FlushInstructionCache(v13, *((LPCVOID *)v12 + 3), *(unsigned __int8 *)(*((_QWORD *)v12 + 4) + 62LL));
        if ( *((_DWORD *)v12 + 2) )
        {
          v14 = *((_QWORD *)v12 + 4);
          if ( v14 )
          {
            *(_OWORD *)v14 = 0;
            i = 1;
            *(_OWORD *)(v14 + 16) = 0;
            *(_OWORD *)(v14 + 32) = 0;
            *(_OWORD *)(v14 + 48) = 0;
            *(_OWORD *)(v14 + 64) = 0;
            *(_OWORD *)(v14 + 80) = 0;
            *(_QWORD *)(v14 + 72) = *(_QWORD *)((v14 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
            *(_QWORD *)((v14 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v14;
            *((_QWORD *)v12 + 4) = 0;
          }
        }
        v15 = *(void **)v12;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
        v12 = v15;
      }
      while ( v15 );
    }
    lpMem = 0;
    if ( i )
    {
      if ( !dword_1004A3AB4 )
      {
        v17 = lpBaseAddress;
        v18 = &lpBaseAddress;
        if ( lpBaseAddress )
        {
          do
          {
            if ( *(_DWORD *)v17 == 1383232612 )
            {
              v19 = 0;
              v20 = v17 + 21;
              while ( 1 )
              {
                v21 = *v20;
                if ( *v20 )
                {
                  if ( v21 < (unsigned __int64)v17 || v21 >= (unsigned __int64)(v17 + 0x2000) )
                    break;
                }
                ++v19;
                v20 += 12;
                if ( v19 >= 0x2A9 )
                {
                  *v18 = (LPCVOID)v17[1];
                  VirtualFree(v17, 0, 0x8000u);
                  qword_1004D3F68 = 0;
                  goto LABEL_32;
                }
              }
            }
            v18 = (LPCVOID *)(v17 + 1);
LABEL_32:
            v17 = *v18;
          }
          while ( *v18 );
        }
      }
    }
    v22 = GetCurrentProcess();
    v23 = lpBaseAddress;
    v24 = v22;
    if ( lpBaseAddress )
    {
      do
      {
        VirtualProtect(v23, 0x10000u, 0x20u, flOldProtect);
        FlushInstructionCache(v24, v23, 0x10000u);
        v23 = (_QWORD *)v23[1];
      }
      while ( v23 );
    }
    qword_1004D3F80 = 0;
    dword_1004D3F60 = 0;
    if ( a1 )
      *a1 = qword_1004D3F70;
    return (unsigned int)dword_1004D3F5C;
  }
}

```

## disassembly

```asm
0x10043dfb0  push    r14
0x10043dfb2  sub     rsp, 40h
0x10043dfb6  mov     r14, rcx
0x10043dfb9  test    rcx, rcx
0x10043dfbc  jz      short loc_10043DFC8
0x10043dfbe  mov     rax, cs:qword_1004D3F70
0x10043dfc5  mov     [rcx], rax
0x10043dfc8  call    cs:__imp_GetCurrentThreadId
0x10043dfce  cmp     cs:dword_1004D3F60, eax
0x10043dfd4  jz      short loc_10043DFE2
0x10043dfd6  mov     eax, 10DDh
0x10043dfdb  add     rsp, 40h
0x10043dfdf  pop     r14
0x10043dfe1  retn
0x10043dfe2  cmp     cs:dword_1004D3F5C, 0
0x10043dfe9  jz      short loc_10043DFFD
0x10043dfeb  call    DetourTransactionAbort
0x10043dff0  mov     eax, cs:dword_1004D3F5C
0x10043dff6  add     rsp, 40h
0x10043dffa  pop     r14
0x10043dffc  retn
0x10043dffd  mov     [rsp+48h+arg_8], rbx
0x10043e002  mov     rbx, cs:lpMem
0x10043e009  mov     [rsp+48h+arg_10], rbp
0x10043e00e  mov     [rsp+48h+arg_18], rsi
0x10043e013  mov     [rsp+48h+var_10], rdi
0x10043e018  mov     [rsp+48h+var_18], r15
0x10043e01d  xor     r15d, r15d
0x10043e020  mov     esi, r15d
0x10043e023  test    rbx, rbx
0x10043e026  jz      loc_10043E0C1
0x10043e02c  nop     dword ptr [rax]
0x10043e02f  nop
0x10043e030  mov     rdx, [rbx+20h]
0x10043e034  cmp     [rbx+8], r15d
0x10043e038  jz      short loc_10043E059
0x10043e03a  movzx   r8d, byte ptr [rdx+3Eh]; Size
0x10043e03f  add     rdx, 20h ; ' '; Src
0x10043e043  mov     rcx, [rbx+18h]; void *
0x10043e047  call    memmove
0x10043e04c  mov     rcx, [rbx+10h]
0x10043e050  mov     rax, [rbx+18h]
0x10043e054  mov     [rcx], rax
0x10043e057  jmp     short loc_10043E0B5
0x10043e059  mov     word ptr [rdx+58h], 25FFh
0x10043e05f  lea     rcx, [rdx+58h]
0x10043e063  lea     rax, [rcx+6]
0x10043e067  sub     edx, eax
0x10043e069  add     edx, 50h ; 'P'
0x10043e06c  mov     [rcx+2], edx
0x10043e06f  mov     rdx, [rbx+18h]
0x10043e073  mov     rcx, [rbx+20h]
0x10043e077  add     rcx, 58h ; 'X'
0x10043e07b  mov     byte ptr [rdx], 0E9h
0x10043e07e  lea     rax, [rdx+5]
0x10043e082  sub     ecx, eax
0x10043e084  mov     [rdx+1], ecx
0x10043e087  lea     rcx, [rdx+5]; void *
0x10043e08b  mov     r9, [rbx+20h]
0x10043e08f  mov     r8, [r9+48h]
0x10043e093  sub     r8, rcx
0x10043e096  cmp     rcx, [r9+48h]
0x10043e09a  cmova   r8, r15; Size
0x10043e09e  test    r8, r8
0x10043e0a1  jz      short loc_10043E0AE
0x10043e0a3  mov     dl, 0CCh; Val
0x10043e0a5  call    memset_0
0x10043e0aa  mov     r9, [rbx+20h]
0x10043e0ae  mov     rax, [rbx+10h]
0x10043e0b2  mov     [rax], r9
0x10043e0b5  mov     rbx, [rbx]
0x10043e0b8  test    rbx, rbx
0x10043e0bb  jnz     loc_10043E030
0x10043e0c1  call    cs:__imp_GetCurrentProcess
0x10043e0c7  mov     rdi, cs:lpMem
0x10043e0ce  mov     rbp, rax
0x10043e0d1  test    rdi, rdi
0x10043e0d4  jz      loc_10043E17C
0x10043e0da  nop     word ptr [rax+rax]
0x10043e0df  nop
0x10043e0e0  mov     rcx, [rdi+20h]
0x10043e0e4  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x10043e0e9  mov     r8d, [rdi+28h]; flNewProtect
0x10043e0ed  movzx   edx, byte ptr [rcx+3Eh]; dwSize
0x10043e0f1  mov     rcx, [rdi+18h]; lpAddress
0x10043e0f5  call    cs:__imp_VirtualProtect
0x10043e0fb  mov     rax, [rdi+20h]
0x10043e0ff  mov     rcx, rbp; hProcess
0x10043e102  mov     rdx, [rdi+18h]; lpBaseAddress
0x10043e106  movzx   r8d, byte ptr [rax+3Eh]; dwSize
0x10043e10b  call    cs:__imp_FlushInstructionCache
0x10043e111  cmp     [rdi+8], r15d
0x10043e115  jz      short loc_10043E159
0x10043e117  mov     rdx, [rdi+20h]
0x10043e11b  test    rdx, rdx
0x10043e11e  jz      short loc_10043E159
0x10043e120  xorps   xmm0, xmm0
0x10043e123  mov     rcx, rdx
0x10043e126  movups  xmmword ptr [rdx], xmm0
0x10043e129  and     rcx, 0FFFFFFFFFFFF0000h
0x10043e130  mov     esi, 1
0x10043e135  movups  xmmword ptr [rdx+10h], xmm0
0x10043e139  movups  xmmword ptr [rdx+20h], xmm0
0x10043e13d  movups  xmmword ptr [rdx+30h], xmm0
0x10043e141  movups  xmmword ptr [rdx+40h], xmm0
0x10043e145  movups  xmmword ptr [rdx+50h], xmm0
0x10043e149  mov     rax, [rcx+10h]
0x10043e14d  mov     [rdx+48h], rax
0x10043e151  mov     [rcx+10h], rdx
0x10043e155  mov     [rdi+20h], r15
0x10043e159  mov     rbx, [rdi]
0x10043e15c  call    cs:__imp_GetProcessHeap
0x10043e162  mov     r8, rdi; lpMem
0x10043e165  xor     edx, edx; dwFlags
0x10043e167  mov     rcx, rax; hHeap
0x10043e16a  call    cs:__imp_HeapFree
0x10043e170  mov     rdi, rbx
0x10043e173  test    rbx, rbx
0x10043e176  jnz     loc_10043E0E0
0x10043e17c  mov     rbp, [rsp+48h+arg_10]
0x10043e181  test    esi, esi
0x10043e183  mov     rsi, [rsp+48h+arg_18]
0x10043e188  mov     cs:lpMem, r15
0x10043e18f  jz      loc_10043E21C
0x10043e195  cmp     cs:dword_1004A3AB4, r15d
0x10043e19c  jnz     short loc_10043E21C
0x10043e19e  mov     rcx, cs:lpBaseAddress; lpAddress
0x10043e1a5  lea     rbx, lpBaseAddress
0x10043e1ac  test    rcx, rcx
0x10043e1af  jz      short loc_10043E21C
0x10043e1b1  cmp     dword ptr [rcx], 52727464h
0x10043e1b7  jnz     short loc_10043E210
0x10043e1b9  lea     r9, [rcx+10000h]
0x10043e1c0  mov     r8d, r15d
0x10043e1c3  lea     rdx, [rcx+0A8h]
0x10043e1ca  nop     word ptr [rax+rax+00h]
0x10043e1d0  mov     rax, [rdx]
0x10043e1d3  test    rax, rax
0x10043e1d6  jz      short loc_10043E1E2
0x10043e1d8  cmp     rax, rcx
0x10043e1db  jb      short loc_10043E210
0x10043e1dd  cmp     rax, r9
0x10043e1e0  jnb     short loc_10043E210
0x10043e1e2  inc     r8d
0x10043e1e5  add     rdx, 60h ; '`'
0x10043e1e9  cmp     r8d, 2A9h
0x10043e1f0  jb      short loc_10043E1D0
0x10043e1f2  mov     rax, [rcx+8]
0x10043e1f6  xor     edx, edx; dwSize
0x10043e1f8  mov     r8d, 8000h; dwFreeType
0x10043e1fe  mov     [rbx], rax
0x10043e201  call    cs:__imp_VirtualFree
0x10043e207  mov     cs:qword_1004D3F68, r15
0x10043e20e  jmp     short loc_10043E214
0x10043e210  lea     rbx, [rcx+8]
0x10043e214  mov     rcx, [rbx]
0x10043e217  test    rcx, rcx
0x10043e21a  jnz     short loc_10043E1B1
0x10043e21c  call    cs:__imp_GetCurrentProcess
0x10043e222  mov     rbx, cs:lpBaseAddress
0x10043e229  mov     rdi, rax
0x10043e22c  test    rbx, rbx
0x10043e22f  jz      short loc_10043E274
0x10043e231  nop     dword ptr [rax+00h]
0x10043e235  nop     word ptr [rax+rax+00000000h]
0x10043e240  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x10043e245  mov     edx, 10000h; dwSize
0x10043e24a  mov     r8d, 20h ; ' '; flNewProtect
0x10043e250  mov     rcx, rbx; lpAddress
0x10043e253  call    cs:__imp_VirtualProtect
0x10043e259  mov     r8d, 10000h; dwSize
0x10043e25f  mov     rdx, rbx; lpBaseAddress
0x10043e262  mov     rcx, rdi; hProcess
0x10043e265  call    cs:__imp_FlushInstructionCache
0x10043e26b  mov     rbx, [rbx+8]
0x10043e26f  test    rbx, rbx
0x10043e272  jnz     short loc_10043E240
0x10043e274  mov     rdi, [rsp+48h+var_10]
0x10043e279  mov     rbx, [rsp+48h+arg_8]
0x10043e27e  mov     cs:qword_1004D3F80, r15
0x10043e285  mov     cs:dword_1004D3F60, r15d
0x10043e28c  mov     r15, [rsp+48h+var_18]
0x10043e291  test    r14, r14
0x10043e294  jz      short loc_10043E2A0
0x10043e296  mov     rax, cs:qword_1004D3F70
0x10043e29d  mov     [r14], rax
0x10043e2a0  mov     eax, cs:dword_1004D3F5C
0x10043e2a6  add     rsp, 40h
0x10043e2aa  pop     r14
0x10043e2ac  retn
```

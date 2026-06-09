# CreateDest

- ea: `0x180009ef0`
- end: `0x180009fef`
- name: `CreateDest`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b440`

## callees

- `0x180009ef0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180009f6a`
- `KERNEL32!HeapAlloc` at `0x180009f6a`
- `KERNEL32!GetProcessHeap` at `0x180009f59`
- `KERNEL32!GetProcessHeap` at `0x180009f59`

## pseudocode

```c
__int64 __fastcall CreateDest(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v3; // ebp
  unsigned __int64 v7; // r10
  unsigned __int64 v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // rdi
  HANDLE ProcessHeap; // rax
  char *v12; // rax
  char *v13; // rdx
  __int64 v15; // r8
  _QWORD *v16; // rax
  __int64 v17; // rcx

  v3 = *(_DWORD *)(a1 + 44);
  *a3 = 0;
  v7 = 24LL * (v3 - 1);
  if ( v7 > 0xFFFFFFFF )
    return 534;
  v8 = 8LL * *(unsigned int *)(a1 + 312);
  if ( v8 > 0xFFFFFFFF )
    return 534;
  v9 = v8 + v7;
  if ( (int)v8 + (int)v7 < (unsigned int)v7 || v9 + 152 < v9 )
    return 534;
  v10 = v9 + 152;
  ProcessHeap = GetProcessHeap();
  v12 = (char *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v10);
  v13 = v12;
  if ( !v12 )
    return 8;
  _InterlockedIncrement((volatile signed __int32 *)v12);
  *((_QWORD *)v12 + 1) = 0;
  v15 = 0;
  *((_QWORD *)v12 + 15) = a1;
  v16 = v12 + 56;
  v16[1] = v16;
  for ( *v16 = v16; (unsigned int)v15 < v3; *(_QWORD *)&v13[8 * v17 + 128] = 0 )
  {
    v17 = 3 * v15;
    v15 = (unsigned int)(v15 + 1);
  }
  *((_DWORD *)v13 + 13) = 0;
  *a3 = v13;
  *((_QWORD *)v13 + 9) = &v13[v10 - v8];
  *((_OWORD *)v13 + 5) = *(_OWORD *)a2;
  *((_DWORD *)v13 + 24) = *(_DWORD *)(a2 + 16);
  return 0;
}

```

## disassembly

```asm
0x180009ef0  push    rbx
0x180009ef2  push    rbp
0x180009ef3  push    rsi
0x180009ef4  push    rdi
0x180009ef5  push    r14
0x180009ef7  push    r15
0x180009ef9  sub     rsp, 28h
0x180009efd  mov     ebp, [rcx+2Ch]
0x180009f00  mov     r15, r8
0x180009f03  mov     r14, rdx
0x180009f06  mov     qword ptr [r8], 0
0x180009f0d  mov     rsi, rcx
0x180009f10  lea     eax, [rbp-1]
0x180009f13  lea     r10, [rax+rax*2]
0x180009f17  mov     eax, 0FFFFFFFFh
0x180009f1c  shl     r10, 3
0x180009f20  cmp     r10, rax
0x180009f23  ja      loc_180009FDD
0x180009f29  mov     ebx, [rcx+138h]
0x180009f2f  shl     rbx, 3
0x180009f33  cmp     rbx, rax
0x180009f36  ja      loc_180009FDD
0x180009f3c  lea     eax, [rbx+r10]
0x180009f40  cmp     eax, r10d
0x180009f43  jb      loc_180009FDD
0x180009f49  lea     ecx, [rax+98h]
0x180009f4f  cmp     ecx, eax
0x180009f51  jb      loc_180009FDD
0x180009f57  mov     edi, ecx
0x180009f59  call    cs:__imp_GetProcessHeap
0x180009f5f  mov     r8d, edi; dwBytes
0x180009f62  mov     edx, 8; dwFlags
0x180009f67  mov     rcx, rax; hHeap
0x180009f6a  call    cs:__imp_HeapAlloc
0x180009f70  mov     rdx, rax
0x180009f73  test    rax, rax
0x180009f76  jnz     short loc_180009F7D
0x180009f78  lea     eax, [rdx+8]
0x180009f7b  jmp     short loc_180009FE2
0x180009f7d  lock inc dword ptr [rax]
0x180009f80  mov     qword ptr [rax+8], 0
0x180009f88  xor     r8d, r8d
0x180009f8b  mov     [rax+78h], rsi
0x180009f8f  add     rax, 38h ; '8'
0x180009f93  mov     [rax+8], rax
0x180009f97  mov     [rax], rax
0x180009f9a  test    ebp, ebp
0x180009f9c  jz      short loc_180009FB6
0x180009f9e  lea     rcx, [r8+r8*2]
0x180009fa2  inc     r8d
0x180009fa5  mov     qword ptr [rdx+rcx*8+80h], 0
0x180009fb1  cmp     r8d, ebp
0x180009fb4  jb      short loc_180009F9E
0x180009fb6  sub     rdi, rbx
0x180009fb9  mov     dword ptr [rdx+34h], 0
0x180009fc0  add     rdi, rdx
0x180009fc3  mov     [r15], rdx
0x180009fc6  mov     [rdx+48h], rdi
0x180009fca  movups  xmm0, xmmword ptr [r14]
0x180009fce  movups  xmmword ptr [rdx+50h], xmm0
0x180009fd2  mov     eax, [r14+10h]
0x180009fd6  mov     [rdx+60h], eax
0x180009fd9  xor     eax, eax
0x180009fdb  jmp     short loc_180009FE2
0x180009fdd  mov     eax, 216h
0x180009fe2  add     rsp, 28h
0x180009fe6  pop     r15
0x180009fe8  pop     r14
0x180009fea  pop     rdi
0x180009feb  pop     rsi
0x180009fec  pop     rbp
0x180009fed  pop     rbx
0x180009fee  retn
```

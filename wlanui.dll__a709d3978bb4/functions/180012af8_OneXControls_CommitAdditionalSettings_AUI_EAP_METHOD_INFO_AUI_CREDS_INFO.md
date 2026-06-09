# OneXControls::CommitAdditionalSettings(_AUI_EAP_METHOD_INFO *,_AUI_CREDS_INFO *)

- ea: `0x180012af8`
- end: `0x180012d15`
- name: `?CommitAdditionalSettings@OneXControls@@QEAAJPEAU_AUI_EAP_METHOD_INFO@@PEAU_AUI_CREDS_INFO@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(OneXControls *__hidden this, struct _AUI_EAP_METHOD_INFO *, struct _AUI_CREDS_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009380`

## callees

- `0x180001e26`
- `0x180012af8`
- `0x18001befe`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x180012c2a`
- `ntdll!WinSqmIncrementDWORD` at `0x180012c2a`
- `KERNEL32!HeapAlloc` at `0x180012c9a`
- `KERNEL32!HeapAlloc` at `0x180012cb8`
- `KERNEL32!HeapAlloc` at `0x180012c9a`
- `KERNEL32!HeapAlloc` at `0x180012cb8`
- `KERNEL32!GetProcessHeap` at `0x180012bd2`
- `KERNEL32!GetProcessHeap` at `0x180012c88`
- `KERNEL32!GetProcessHeap` at `0x180012ca7`
- `KERNEL32!GetProcessHeap` at `0x180012bd2`
- `KERNEL32!GetProcessHeap` at `0x180012c88`
- `KERNEL32!GetProcessHeap` at `0x180012ca7`
- `KERNEL32!HeapFree` at `0x180012be0`
- `KERNEL32!HeapFree` at `0x180012be0`

## pseudocode

```c
__int64 __fastcall OneXControls::CommitAdditionalSettings(
        OneXControls *this,
        struct _AUI_EAP_METHOD_INFO *a2,
        struct _AUI_CREDS_INFO *a3)
{
  __int64 v3; // rbx
  __int64 v7; // rbp
  __int64 v8; // rdx
  unsigned int v9; // ecx
  bool v10; // zf
  int v11; // eax
  _BYTE *v12; // rax
  __int64 v13; // rcx
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v16; // ebx
  _DWORD *v17; // r8
  _DWORD *v18; // rdx
  unsigned int v20; // ebx
  HANDLE v21; // rax
  LPVOID v22; // rax
  unsigned int v23; // ebx
  HANDLE v24; // rax
  LPVOID v25; // rax
  size_t v26; // r8
  void *v27; // rcx

  v3 = *((_QWORD *)this + 5);
  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 72) + 552LL) + 32LL) + 424LL) + 48LL);
  if ( a3 )
  {
    if ( !a2
      || (v8 = *((_QWORD *)this + 10)) == 0
      || (v9 = *((_DWORD *)a2 + 2), v9 != *(_DWORD *)(v8 + 8))
      || **(_QWORD **)a2 != **(_QWORD **)v8
      || *(_QWORD *)(*(_QWORD *)a2 + 8LL) != *(_QWORD *)(*(_QWORD *)v8 + 8LL)
      || (v10 = memcmp_0(*((const void **)a2 + 2), *(const void **)(v8 + 16), v9) == 0, v11 = 1, !v10) )
    {
      v11 = 0;
    }
    if ( (*((_BYTE *)this + 48) & 2) != 0
      && (*((_DWORD *)this + 27) || !*((_DWORD *)this + 13) || *((_DWORD *)this + 14) != 2 || *(_DWORD *)(v3 + 64)) )
    {
      v12 = (_BYTE *)*((_QWORD *)a3 + 6);
      *((_DWORD *)a3 + 1) = 1;
      *((_DWORD *)a3 + 10) = 0;
      if ( v12 )
      {
        v13 = 16;
        do
        {
          *v12++ = 0;
          --v13;
        }
        while ( v13 );
        v14 = (void *)*((_QWORD *)a3 + 6);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v14);
      }
      *((_QWORD *)a3 + 6) = 0;
    }
    else if ( *((_DWORD *)this + 22) && v11 )
    {
      *((_DWORD *)a3 + 1) = 1;
      *((_DWORD *)a3 + 10) = *((_DWORD *)this + 17);
      *((_DWORD *)a3 + 6) = *((_DWORD *)a2 + 2);
      v20 = (2580 * *((_DWORD *)this + 17)) & 0xFFFFFFF0;
      v21 = GetProcessHeap();
      v22 = HeapAlloc(v21, 8u, v20 + 16);
      v23 = *((_DWORD *)a3 + 6);
      *((_QWORD *)a3 + 6) = v22;
      v24 = GetProcessHeap();
      v25 = HeapAlloc(v24, 8u, v23);
      *((_QWORD *)a3 + 4) = v25;
      if ( !*((_QWORD *)a3 + 6) || !v25 )
        return (unsigned int)-2147024882;
      memcpy_0(*((void **)a3 + 6), *((const void **)this + 9), ((2580 * *((_DWORD *)this + 17)) & 0xFFFFFFF0) + 16);
      v26 = *((unsigned int *)a3 + 6);
      v27 = (void *)*((_QWORD *)a3 + 4);
      *(_OWORD *)((char *)a3 + 8) = *(_OWORD *)*(_QWORD *)a2;
      memcpy_0(v27, *((const void **)a2 + 2), v26);
    }
  }
  v16 = 0;
  if ( !*(_DWORD *)(*((_QWORD *)this + 5) + 56LL) )
  {
    if ( *((_DWORD *)this + 27)
      || (v17 = (_DWORD *)(v7 + 8),
          v18 = (_DWORD *)((char *)this + 52),
          ((*(_DWORD *)(v7 + 8) >> 2) & 1) != *((_DWORD *)this + 13))
      || *v18 && *(_DWORD *)(v7 + 20) != *((_DWORD *)this + 14) )
    {
      WinSqmIncrementDWORD(0, 6149, 1);
      v17 = (_DWORD *)(v7 + 8);
      v18 = (_DWORD *)((char *)this + 52);
    }
    *v17 ^= (*v17 ^ (4 * *v18)) & 4;
    if ( *v18 )
      *(_DWORD *)(v7 + 20) = *((_DWORD *)this + 14);
  }
  return v16;
}

```

## disassembly

```asm
0x180012af8  push    rbx
0x180012afa  push    rbp
0x180012afb  push    rsi
0x180012afc  push    rdi
0x180012afd  push    r12
0x180012aff  push    r14
0x180012b01  sub     rsp, 28h
0x180012b05  mov     rbx, [rcx+28h]
0x180012b09  xor     r12d, r12d
0x180012b0c  mov     rsi, r8
0x180012b0f  mov     r14, rdx
0x180012b12  mov     rdi, rcx
0x180012b15  mov     rax, [rbx+48h]
0x180012b19  mov     r9, [rax+228h]
0x180012b20  mov     rax, [r9+20h]
0x180012b24  mov     r9, [rax+1A8h]
0x180012b2b  mov     rbp, [r9+30h]
0x180012b2f  test    r8, r8
0x180012b32  jz      loc_180012BEA
0x180012b38  test    rdx, rdx
0x180012b3b  jz      short loc_180012B80
0x180012b3d  mov     rdx, [rcx+50h]
0x180012b41  test    rdx, rdx
0x180012b44  jz      short loc_180012B80
0x180012b46  mov     ecx, [r14+8]
0x180012b4a  cmp     ecx, [rdx+8]
0x180012b4d  jnz     short loc_180012B80
0x180012b4f  mov     r8, [r14]
0x180012b52  mov     r9, [rdx]
0x180012b55  mov     rax, [r8]
0x180012b58  cmp     rax, [r9]
0x180012b5b  jnz     short loc_180012B80
0x180012b5d  mov     rax, [r8+8]
0x180012b61  cmp     rax, [r9+8]
0x180012b65  jnz     short loc_180012B80
0x180012b67  mov     rdx, [rdx+10h]; Buf2
0x180012b6b  mov     r8d, ecx; Size
0x180012b6e  mov     rcx, [r14+10h]; Buf1
0x180012b72  call    memcmp_0
0x180012b77  test    eax, eax
0x180012b79  lea     eax, [r12+1]
0x180012b7e  jz      short loc_180012B83
0x180012b80  mov     eax, r12d
0x180012b83  test    byte ptr [rdi+30h], 2
0x180012b87  jz      loc_180012C60
0x180012b8d  cmp     [rdi+6Ch], r12d
0x180012b91  jnz     short loc_180012BA9
0x180012b93  cmp     [rdi+34h], r12d
0x180012b97  jz      short loc_180012BA9
0x180012b99  cmp     dword ptr [rdi+38h], 2
0x180012b9d  jnz     short loc_180012BA9
0x180012b9f  cmp     [rbx+40h], r12d
0x180012ba3  jz      loc_180012C60
0x180012ba9  mov     rax, [rsi+30h]
0x180012bad  mov     dword ptr [rsi+4], 1
0x180012bb4  mov     [rsi+28h], r12d
0x180012bb8  test    rax, rax
0x180012bbb  jz      short loc_180012BE6
0x180012bbd  mov     ecx, 10h
0x180012bc2  mov     [rax], r12b
0x180012bc5  inc     rax
0x180012bc8  sub     rcx, 1
0x180012bcc  jnz     short loc_180012BC2
0x180012bce  mov     rbx, [rsi+30h]
0x180012bd2  call    cs:__imp_GetProcessHeap
0x180012bd8  mov     r8, rbx; lpMem
0x180012bdb  xor     edx, edx; dwFlags
0x180012bdd  mov     rcx, rax; hHeap
0x180012be0  call    cs:__imp_HeapFree
0x180012be6  mov     [rsi+30h], r12
0x180012bea  mov     rax, [rdi+28h]
0x180012bee  mov     ebx, r12d
0x180012bf1  cmp     [rax+38h], r12d
0x180012bf5  jnz     short loc_180012C51
0x180012bf7  cmp     [rdi+6Ch], r12d
0x180012bfb  jnz     short loc_180012C1F
0x180012bfd  lea     r8, [rbp+8]
0x180012c01  mov     eax, [r8]
0x180012c04  lea     rdx, [rdi+34h]
0x180012c08  shr     eax, 2
0x180012c0b  and     eax, 1
0x180012c0e  cmp     eax, [rdx]
0x180012c10  jnz     short loc_180012C1F
0x180012c12  cmp     [rdx], r12d
0x180012c15  jz      short loc_180012C38
0x180012c17  mov     eax, [rdi+38h]
0x180012c1a  cmp     [rbp+14h], eax
0x180012c1d  jz      short loc_180012C38
0x180012c1f  xor     ecx, ecx
0x180012c21  mov     edx, 1805h
0x180012c26  lea     r8d, [rcx+1]
0x180012c2a  call    cs:__imp_WinSqmIncrementDWORD
0x180012c30  lea     r8, [rbp+8]
0x180012c34  lea     rdx, [rdi+34h]
0x180012c38  mov     ecx, [rdx]
0x180012c3a  shl     ecx, 2
0x180012c3d  xor     ecx, [r8]
0x180012c40  and     ecx, 4
0x180012c43  xor     [r8], ecx
0x180012c46  cmp     [rdx], r12d
0x180012c49  jz      short loc_180012C51
0x180012c4b  mov     ecx, [rdi+38h]
0x180012c4e  mov     [rbp+14h], ecx
0x180012c51  mov     eax, ebx
0x180012c53  add     rsp, 28h
0x180012c57  pop     r14
0x180012c59  pop     r12
0x180012c5b  pop     rdi
0x180012c5c  pop     rsi
0x180012c5d  pop     rbp
0x180012c5e  pop     rbx
0x180012c5f  retn
0x180012c60  cmp     [rdi+58h], r12d
0x180012c64  jz      short loc_180012BEA
0x180012c66  test    eax, eax
0x180012c68  jz      short loc_180012BEA
0x180012c6a  mov     dword ptr [rsi+4], 1
0x180012c71  mov     eax, [rdi+44h]
0x180012c74  mov     [rsi+28h], eax
0x180012c77  mov     eax, [r14+8]
0x180012c7b  mov     [rsi+18h], eax
0x180012c7e  imul    ebx, [rdi+44h], 0A14h
0x180012c85  and     ebx, 0FFFFFFF0h
0x180012c88  call    cs:__imp_GetProcessHeap
0x180012c8e  lea     r8d, [rbx+10h]; dwBytes
0x180012c92  mov     edx, 8; dwFlags
0x180012c97  mov     rcx, rax; hHeap
0x180012c9a  call    cs:__imp_HeapAlloc
0x180012ca0  mov     ebx, [rsi+18h]
0x180012ca3  mov     [rsi+30h], rax
0x180012ca7  call    cs:__imp_GetProcessHeap
0x180012cad  mov     r8d, ebx; dwBytes
0x180012cb0  mov     edx, 8; dwFlags
0x180012cb5  mov     rcx, rax; hHeap
0x180012cb8  call    cs:__imp_HeapAlloc
0x180012cbe  mov     [rsi+20h], rax
0x180012cc2  cmp     [rsi+30h], r12
0x180012cc6  jz      short loc_180012D0B
0x180012cc8  test    rax, rax
0x180012ccb  jz      short loc_180012D0B
0x180012ccd  imul    r8d, [rdi+44h], 0A14h
0x180012cd5  mov     rdx, [rdi+48h]; Src
0x180012cd9  mov     rcx, [rsi+30h]; void *
0x180012cdd  and     r8d, 0FFFFFFF0h
0x180012ce1  add     r8d, 10h; Size
0x180012ce5  call    memcpy_0
0x180012cea  mov     rax, [r14]
0x180012ced  mov     r8d, [rsi+18h]; Size
0x180012cf1  mov     rcx, [rsi+20h]; void *
0x180012cf5  movups  xmm0, xmmword ptr [rax]
0x180012cf8  movdqu  xmmword ptr [rsi+8], xmm0
0x180012cfd  mov     rdx, [r14+10h]; Src
0x180012d01  call    memcpy_0
0x180012d06  jmp     loc_180012BEA
0x180012d0b  mov     ebx, 8007000Eh
0x180012d10  jmp     loc_180012C51
```

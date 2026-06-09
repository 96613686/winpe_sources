# CreatetCall

- ea: `0x180003b0c`
- end: `0x180003d83`
- name: `CreatetCall`
- size: `631`
- prototype: `__int64 __fastcall(_QWORD *, int, __int64, const void **, unsigned int *, _DWORD *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180003d8c`
- `0x180017be0`

## callees

- `0x180003b0c`
- `0x18000443c`
- `0x18001f6c4`
- `0x18002ba2c`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e2f0`
- `0x18003fb7c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180003bc6`
- `KERNEL32!HeapAlloc` at `0x180003bc6`

## string_xrefs

- `0x180003b30`: `CreatetCall: enter, ptLine=%p`
- `0x180003c90`: `CreatetCall: calling NewObject ptCall %p`
- `0x180003cb6`: `CreatetCall: NewObject returned 0x%lx`
- `0x180003d56`: `CreatetCall: exit, new ptCall=%p`

## pseudocode

```c
__int64 __fastcall CreatetCall(_QWORD *a1, int a2, __int64 a3, const void **a4, unsigned int *a5, _DWORD *a6, int a7)
{
  unsigned int v10; // ebx
  unsigned int v12; // eax
  unsigned int v14; // ebx
  unsigned int v15; // ebp
  int *v16; // rax
  int *v17; // rbx
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // edx
  char *v21; // rcx
  unsigned int v22; // edx
  char *v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned int v30; // [rsp+20h] [rbp-48h] BYREF
  __int64 v31[8]; // [rsp+28h] [rbp-40h] BYREF

  v30 = 0;
  v10 = 0;
  a7 = 0;
  v31[0] = 0;
  TRACELogPrint(524290, "CreatetCall: enter, ptLine=%p", a1);
  if ( a5 )
  {
    if ( (int)DWordAdd3(a5[16], a5[14], a5[18], &a7) < 0 )
      return 2147483716LL;
    v10 = a7;
  }
  if ( v10 )
  {
    v12 = v10;
    v10 += 16;
    if ( v10 < v12 )
    {
      a7 = -1;
      return 2147483716LL;
    }
  }
  v14 = v10 + 624;
  v15 = 624;
  if ( v14 < 0x270 )
    return 2147483716LL;
  v16 = (int *)HeapAlloc(ghTapisrvHeap, 8u, v14);
  v17 = v16;
  if ( !v16 )
    return 2147483716LL;
  if ( a2 )
  {
    v16[8] = 3;
    v16[18] = 1;
    v16[14] = 0x8000;
    *((_QWORD *)v16 + 5) = a3;
    v18 = 1280724553;
  }
  else
  {
    v18 = 1279345481;
  }
  *v17 = v18;
  if ( a5 )
  {
    v19 = a5[14];
    if ( v19 )
    {
      v17[22] = v19;
      *((_QWORD *)v17 + 12) = v17 + 156;
      memcpy_0(v17 + 156, (char *)a5 + a5[15], v19);
      v15 = ((v17[22] + 8) & 0xFFFFFFF8) + 624;
    }
    v20 = a5[16];
    if ( v20 )
    {
      v17[26] = v20;
      v21 = (char *)v17 + v15;
      *((_QWORD *)v17 + 14) = v21;
      memcpy_0(v21, (char *)a5 + a5[17], v20);
      v15 += (v17[26] + 8) & 0xFFFFFFF8;
    }
    v22 = a5[18];
    if ( v22 )
    {
      v17[30] = v22;
      v23 = (char *)v17 + v15;
      *((_QWORD *)v17 + 16) = v23;
      memcpy_0(v23, (char *)a5 + a5[19], v22);
    }
  }
  TRACELogPrint(262146, "CreatetCall: calling NewObject ptCall %p", v17);
  v25 = NewObject(v24, v17, 0);
  v17[12] = v25;
  TRACELogPrint(524290, "CreatetCall: NewObject returned 0x%lx", v25);
  *a6 = v17[12];
  if ( !v17[12] )
  {
    ServerFree(v17);
    return 2147483716LL;
  }
  if ( (unsigned int)WaitForExclusivetLineAccess(a1, v31, &v30) )
  {
    *((_QWORD *)v17 + 2) = a1;
    *((_QWORD *)v17 + 3) = a1[24];
    v27 = a1[31];
    *((_QWORD *)v17 + 19) = v27;
    if ( v27 )
      *(_QWORD *)(v27 + 144) = v17;
    v28 = v30;
    v29 = v31[0];
    a1[31] = v17;
    MyReleaseMutex(v29, v28);
    *a4 = v17;
    ++dword_1800518B4;
    LODWORD(qword_1800518C0) = qword_1800518C0 + 1;
    if ( a2 )
      *v17 = 1280065859;
    TRACELogPrint(524290, "CreatetCall: exit, new ptCall=%p", *a4);
    return 0;
  }
  else
  {
    DereferenceObject(v26, (unsigned int)v17[12], 1);
    return 2147483720LL;
  }
}

```

## disassembly

```asm
0x180003b0c  mov     rax, rsp
0x180003b0f  push    rbx
0x180003b10  push    rbp
0x180003b11  push    rsi
0x180003b12  push    rdi
0x180003b13  push    r12
0x180003b15  push    r14
0x180003b17  push    r15
0x180003b19  sub     rsp, 30h
0x180003b1d  mov     r15, r8
0x180003b20  mov     dword ptr [rax-48h], 0
0x180003b27  mov     r8, rcx
0x180003b2a  mov     r12d, edx
0x180003b2d  mov     rsi, rcx
0x180003b30  lea     rdx, aCreatetcallEnt; "CreatetCall: enter, ptLine=%p"
0x180003b37  xor     ebx, ebx
0x180003b39  mov     ecx, 80002h
0x180003b3e  mov     r14, r9
0x180003b41  mov     [rax+38h], ebx
0x180003b44  mov     [rax-40h], rbx
0x180003b48  call    TRACELogPrint
0x180003b4d  mov     rdi, [rsp+68h+arg_20]
0x180003b55  test    rdi, rdi
0x180003b58  jz      short loc_180003B7C
0x180003b5a  mov     ecx, [rdi+40h]
0x180003b5d  lea     r9, [rsp+68h+arg_30]
0x180003b65  mov     r8d, [rdi+48h]
0x180003b69  mov     edx, [rdi+38h]
0x180003b6c  call    DWordAdd3
0x180003b71  test    eax, eax
0x180003b73  js      short loc_180003B94
0x180003b75  mov     ebx, [rsp+68h+arg_30]
0x180003b7c  test    ebx, ebx
0x180003b7e  jz      short loc_180003BA8
0x180003b80  mov     eax, ebx
0x180003b82  add     ebx, 10h
0x180003b85  cmp     ebx, eax
0x180003b87  jnb     short loc_180003BA8
0x180003b89  mov     [rsp+68h+arg_30], 0FFFFFFFFh
0x180003b94  mov     eax, 80000044h
0x180003b99  add     rsp, 30h
0x180003b9d  pop     r15
0x180003b9f  pop     r14
0x180003ba1  pop     r12
0x180003ba3  pop     rdi
0x180003ba4  pop     rsi
0x180003ba5  pop     rbp
0x180003ba6  pop     rbx
0x180003ba7  retn
0x180003ba8  add     ebx, 270h
0x180003bae  mov     ebp, 270h
0x180003bb3  cmp     ebx, ebp
0x180003bb5  jb      short loc_180003B94
0x180003bb7  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180003bbe  mov     edx, 8; dwFlags
0x180003bc3  mov     r8d, ebx; dwBytes
0x180003bc6  call    cs:__imp_HeapAlloc
0x180003bcc  mov     rbx, rax
0x180003bcf  test    rax, rax
0x180003bd2  jz      short loc_180003B94
0x180003bd4  test    r12d, r12d
0x180003bd7  jz      short loc_180003BF9
0x180003bd9  mov     dword ptr [rax+20h], 3
0x180003be0  mov     dword ptr [rax+48h], 1
0x180003be7  mov     dword ptr [rax+38h], 8000h
0x180003bee  mov     [rax+28h], r15
0x180003bf2  mov     eax, 4C564E49h
0x180003bf7  jmp     short loc_180003BFE
0x180003bf9  mov     eax, 4C414349h
0x180003bfe  mov     [rbx], eax
0x180003c00  test    rdi, rdi
0x180003c03  jz      loc_180003C8D
0x180003c09  mov     eax, [rdi+38h]
0x180003c0c  mov     r15d, 0FFFFFFF8h
0x180003c12  test    eax, eax
0x180003c14  jz      short loc_180003C3D
0x180003c16  lea     rcx, [rbx+270h]; void *
0x180003c1d  mov     [rbx+58h], eax
0x180003c20  mov     [rbx+60h], rcx
0x180003c24  mov     r8d, eax; Size
0x180003c27  mov     edx, [rdi+3Ch]
0x180003c2a  add     rdx, rdi; Src
0x180003c2d  call    memcpy_0
0x180003c32  mov     eax, [rbx+58h]
0x180003c35  add     eax, 8
0x180003c38  and     eax, r15d
0x180003c3b  add     ebp, eax
0x180003c3d  mov     edx, [rdi+40h]
0x180003c40  test    edx, edx
0x180003c42  jz      short loc_180003C69
0x180003c44  mov     [rbx+68h], edx
0x180003c47  mov     r8d, edx; Size
0x180003c4a  mov     ecx, ebp
0x180003c4c  add     rcx, rbx; void *
0x180003c4f  mov     [rbx+70h], rcx
0x180003c53  mov     edx, [rdi+44h]
0x180003c56  add     rdx, rdi; Src
0x180003c59  call    memcpy_0
0x180003c5e  mov     eax, [rbx+68h]
0x180003c61  add     eax, 8
0x180003c64  and     eax, r15d
0x180003c67  add     ebp, eax
0x180003c69  mov     edx, [rdi+48h]
0x180003c6c  test    edx, edx
0x180003c6e  jz      short loc_180003C8D
0x180003c70  mov     [rbx+78h], edx
0x180003c73  mov     r8d, edx; Size
0x180003c76  mov     ecx, ebp
0x180003c78  add     rcx, rbx; void *
0x180003c7b  mov     [rbx+80h], rcx
0x180003c82  mov     edx, [rdi+4Ch]
0x180003c85  add     rdx, rdi; Src
0x180003c88  call    memcpy_0
0x180003c8d  mov     r8, rbx
0x180003c90  lea     rdx, aCreatetcallCal; "CreatetCall: calling NewObject ptCall %"...
0x180003c97  mov     ecx, 40002h
0x180003c9c  call    TRACELogPrint
0x180003ca1  xor     r8d, r8d
0x180003ca4  mov     rdx, rbx
0x180003ca7  call    NewObject
0x180003cac  mov     edi, 80002h
0x180003cb1  mov     [rbx+30h], eax
0x180003cb4  mov     ecx, edi
0x180003cb6  lea     rdx, aCreatetcallNew; "CreatetCall: NewObject returned 0x%lx"
0x180003cbd  mov     r8d, eax
0x180003cc0  call    TRACELogPrint
0x180003cc5  mov     rax, [rsp+68h+arg_28]
0x180003ccd  mov     ecx, [rbx+30h]
0x180003cd0  mov     [rax], ecx
0x180003cd2  cmp     dword ptr [rbx+30h], 0
0x180003cd6  jnz     short loc_180003CE5
0x180003cd8  mov     rcx, rbx; lpMem
0x180003cdb  call    ServerFree
0x180003ce0  jmp     loc_180003B94
0x180003ce5  lea     r8, [rsp+68h+var_48]
0x180003cea  mov     rcx, rsi
0x180003ced  lea     rdx, [rsp+68h+var_40]
0x180003cf2  call    WaitForExclusivetLineAccess
0x180003cf7  test    eax, eax
0x180003cf9  jz      short loc_180003D6B
0x180003cfb  mov     [rbx+10h], rsi
0x180003cff  mov     rax, [rsi+0C0h]
0x180003d06  mov     [rbx+18h], rax
0x180003d0a  mov     rax, [rsi+0F8h]
0x180003d11  mov     [rbx+98h], rax
0x180003d18  test    rax, rax
0x180003d1b  jz      short loc_180003D24
0x180003d1d  mov     [rax+90h], rbx
0x180003d24  mov     edx, [rsp+68h+var_48]
0x180003d28  mov     rcx, [rsp+68h+var_40]
0x180003d2d  mov     [rsi+0F8h], rbx
0x180003d34  call    MyReleaseMutex
0x180003d39  mov     [r14], rbx
0x180003d3c  inc     cs:dword_1800518B4
0x180003d42  inc     dword ptr cs:qword_1800518C0
0x180003d48  test    r12d, r12d
0x180003d4b  jz      short loc_180003D53
0x180003d4d  mov     dword ptr [rbx], 4C4C4143h
0x180003d53  mov     r8, [r14]
0x180003d56  lea     rdx, aCreatetcallExi; "CreatetCall: exit, new ptCall=%p"
0x180003d5d  mov     ecx, edi
0x180003d5f  call    TRACELogPrint
0x180003d64  xor     eax, eax
0x180003d66  jmp     loc_180003B99
0x180003d6b  mov     edx, [rbx+30h]
0x180003d6e  mov     r8d, 1
0x180003d74  call    DereferenceObject
0x180003d79  mov     eax, 80000048h
0x180003d7e  jmp     loc_180003B99
```

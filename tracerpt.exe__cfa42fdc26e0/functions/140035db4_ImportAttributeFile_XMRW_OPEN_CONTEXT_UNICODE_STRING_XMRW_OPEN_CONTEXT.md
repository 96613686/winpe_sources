# ImportAttributeFile(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_XMRW_OPEN_CONTEXT *)

- ea: `0x140035db4`
- end: `0x140035f41`
- name: `?ImportAttributeFile@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@0@Z`
- size: `397`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140035f48`

## callees

- `0x140035db4`
- `0x14003694c`
- `0x140037f9c`
- `0x14003809c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140035e96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140035e96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035e15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035e88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035e15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035e88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140035e29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140035e29`

## pseudocode

```c
__int64 __fastcall ImportAttributeFile(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _XMRW_OPEN_CONTEXT *a3)
{
  __int64 v3; // r14
  __int64 v6; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rdi
  _WORD *v10; // r8
  PWSTR Buffer; // rcx
  __int64 v12; // rdx
  unsigned __int64 v13; // rax
  _WORD *v14; // rcx
  HANDLE v15; // rax
  _QWORD *v16; // rcx
  unsigned int v17; // edi
  unsigned int v18; // [rsp+60h] [rbp+8h] BYREF

  v3 = *((_QWORD *)a1 + 8);
  v18 = 0;
  if ( v3 )
  {
    v6 = *((_QWORD *)a1 + 3);
    if ( *((_QWORD *)a3 + 2) )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v6 + 168LL))(*((_QWORD *)a1 + 3), &v18);
      PrintMessage(0x409u, v18);
      return 3221745153LL;
    }
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 8u, 0x218u);
    if ( !v9 )
      return 8;
    v10 = v9 + 2;
    Buffer = a2->Buffer;
    v12 = 260;
    v13 = (unsigned __int64)a2->Length >> 1;
    do
    {
      if ( !v13 )
        break;
      if ( !*Buffer )
        break;
      *v10++ = *Buffer++;
      --v13;
      --v12;
    }
    while ( v12 );
    v14 = v10 - 1;
    if ( v12 )
      v14 = v10;
    *v14 = 0;
    if ( !v12 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v9);
      return 1359;
    }
    v16 = *(_QWORD **)(v3 + 40);
    if ( *v16 != v3 + 32 )
      __fastfail(3u);
    v9[1] = v16;
    *v9 = v3 + 32;
    *v16 = v9;
    *(_QWORD *)(v3 + 40) = v9;
    v17 = XmRWOpenFile((LPCWSTR)v9 + 8, a3);
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 168LL))(v6, &v18);
      PrintMessage(0x40Au, v18, a2);
      return v17;
    }
    v17 = XmRWWalk(a3);
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 168LL))(v6, &v18);
      PrintMessage(0x40Cu, v18, a2);
      return v17;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140035db4  push    rbx
0x140035db6  push    rbp
0x140035db7  push    rsi
0x140035db8  push    rdi
0x140035db9  push    r14
0x140035dbb  push    r15
0x140035dbd  sub     rsp, 28h
0x140035dc1  mov     r14, [rcx+40h]
0x140035dc5  xor     r15d, r15d
0x140035dc8  mov     [rsp+58h+arg_0], r15d
0x140035dcd  mov     rsi, r8
0x140035dd0  mov     rbp, rdx
0x140035dd3  test    r14, r14
0x140035dd6  jz      loc_140035F32
0x140035ddc  mov     rbx, [rcx+18h]
0x140035de0  cmp     [r8+10h], r15
0x140035de4  jz      short loc_140035E15
0x140035de6  mov     rax, [rbx]
0x140035de9  lea     rdx, [rsp+58h+arg_0]
0x140035dee  mov     rcx, rbx
0x140035df1  mov     rax, [rax+0A8h]
0x140035df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035dfd  mov     edx, [rsp+58h+arg_0]
0x140035e01  mov     ecx, 409h; unsigned int
0x140035e06  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140035e0b  mov     eax, 0C007EE01h
0x140035e10  jmp     loc_140035F34
0x140035e15  call    cs:__imp_GetProcessHeap
0x140035e1b  mov     edx, 8; dwFlags
0x140035e20  mov     r8d, 218h; dwBytes
0x140035e26  mov     rcx, rax; hHeap
0x140035e29  call    cs:__imp_HeapAlloc
0x140035e2f  mov     rdi, rax
0x140035e32  test    rax, rax
0x140035e35  jnz     short loc_140035E3F
0x140035e37  lea     eax, [rdi+8]
0x140035e3a  jmp     loc_140035F34
0x140035e3f  movzx   eax, word ptr [rbp+0]
0x140035e43  lea     r8, [rdi+10h]
0x140035e47  mov     rcx, [rbp+8]
0x140035e4b  mov     edx, 104h
0x140035e50  shr     rax, 1
0x140035e53  test    rax, rax
0x140035e56  jz      short loc_140035E77
0x140035e58  movzx   r9d, word ptr [rcx]
0x140035e5c  test    r9w, r9w
0x140035e60  jz      short loc_140035E77
0x140035e62  mov     [r8], r9w
0x140035e66  add     rcx, 2
0x140035e6a  add     r8, 2
0x140035e6e  dec     rax
0x140035e71  sub     rdx, 1
0x140035e75  jnz     short loc_140035E53
0x140035e77  test    rdx, rdx
0x140035e7a  lea     rcx, [r8-2]
0x140035e7e  cmovnz  rcx, r8
0x140035e82  mov     [rcx], r15w
0x140035e86  jnz     short loc_140035EA6
0x140035e88  call    cs:__imp_GetProcessHeap
0x140035e8e  mov     r8, rdi; lpMem
0x140035e91  xor     edx, edx; dwFlags
0x140035e93  mov     rcx, rax; hHeap
0x140035e96  call    cs:__imp_HeapFree
0x140035e9c  mov     eax, 54Fh
0x140035ea1  jmp     loc_140035F34
0x140035ea6  lea     rax, [r14+20h]
0x140035eaa  mov     rcx, [rax+8]
0x140035eae  cmp     [rcx], rax
0x140035eb1  jz      short loc_140035EBA
0x140035eb3  mov     ecx, 3
0x140035eb8  int     29h; Win8: RtlFailFast(ecx)
0x140035eba  mov     [rdi+8], rcx
0x140035ebe  mov     rdx, rsi; struct _XMRW_OPEN_CONTEXT *
0x140035ec1  mov     [rdi], rax
0x140035ec4  mov     [rcx], rdi
0x140035ec7  lea     rcx, [rdi+10h]; lpSrc
0x140035ecb  mov     [rax+8], rdi
0x140035ecf  call    ?XmRWOpenFile@@YAKPEAGPEAU_XMRW_OPEN_CONTEXT@@@Z; XmRWOpenFile(ushort *,_XMRW_OPEN_CONTEXT *)
0x140035ed4  mov     edi, eax
0x140035ed6  test    eax, eax
0x140035ed8  jz      short loc_140035F06
0x140035eda  mov     rdx, [rbx]
0x140035edd  mov     rcx, rbx
0x140035ee0  mov     rax, [rdx+0A8h]
0x140035ee7  lea     rdx, [rsp+58h+arg_0]
0x140035eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035ef1  mov     ecx, 40Ah; unsigned int
0x140035ef6  mov     edx, [rsp+58h+arg_0]
0x140035efa  mov     r8, rbp
0x140035efd  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140035f02  mov     eax, edi
0x140035f04  jmp     short loc_140035F34
0x140035f06  mov     rcx, rsi; struct _XMRW_OPEN_CONTEXT *
0x140035f09  call    ?XmRWWalk@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z; XmRWWalk(_XMRW_OPEN_CONTEXT *)
0x140035f0e  mov     edi, eax
0x140035f10  test    eax, eax
0x140035f12  jz      short loc_140035F32
0x140035f14  mov     rcx, [rbx]
0x140035f17  lea     rdx, [rsp+58h+arg_0]
0x140035f1c  mov     rax, [rcx+0A8h]
0x140035f23  mov     rcx, rbx
0x140035f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035f2b  mov     ecx, 40Ch
0x140035f30  jmp     short loc_140035EF6
0x140035f32  xor     eax, eax
0x140035f34  add     rsp, 28h
0x140035f38  pop     r15
0x140035f3a  pop     r14
0x140035f3c  pop     rdi
0x140035f3d  pop     rsi
0x140035f3e  pop     rbp
0x140035f3f  pop     rbx
0x140035f40  retn
```

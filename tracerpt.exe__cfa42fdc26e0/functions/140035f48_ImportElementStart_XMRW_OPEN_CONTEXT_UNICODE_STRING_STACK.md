# ImportElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140035f48`
- end: `0x14003610d`
- name: `?ImportElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140032dcc`

## callees

- `0x140016808`
- `0x140035db4`
- `0x140035f48`
- `0x14003694c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035fd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035fd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140035fe3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140035fe3`

## pseudocode

```c
__int64 __fastcall ImportElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  __int64 v2; // r14
  __int64 v4; // rsi
  _QWORD *v5; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rax
  __int64 result; // rax
  __int64 v9; // rcx
  WCHAR *v10; // [rsp+20h] [rbp-40h] BYREF
  WCHAR *v11; // [rsp+28h] [rbp-38h] BYREF
  struct _UNICODE_STRING v12; // [rsp+30h] [rbp-30h]
  struct _UNICODE_STRING v13; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v14; // [rsp+50h] [rbp-10h] BYREF
  int v15; // [rsp+90h] [rbp+30h] BYREF
  int v16; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v17; // [rsp+A8h] [rbp+48h] BYREF

  v2 = *((_QWORD *)a1 + 8);
  v10 = 0;
  v15 = 0;
  v17 = 0;
  v12 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  if ( *((_BYTE *)a1 + 120) )
    return 0;
  if ( *((_DWORD *)a1 + 12) != 2 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  v13 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v13, L"Report", 0) )
    return 0;
  v5 = (_QWORD *)*((_QWORD *)a1 + 14);
  if ( !v5 )
  {
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 8u, 0x98u);
    v5 = v7;
    if ( !v7 )
      return 8;
    *((_QWORD *)a1 + 14) = v7;
  }
  v5[8] = v2;
  *((_BYTE *)v5 + 120) = 1;
  while ( 1 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
    if ( (_DWORD)result )
      break;
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v10, &v15);
    v9 = *((_QWORD *)a1 + 3);
    v12.Buffer = v10;
    v11 = 0;
    v12.MaximumLength = 2 * v15;
    v12.Length = 2 * v15;
    v16 = 0;
    v13 = 0;
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v9 + 128LL))(v9, &v11, &v16);
    v13.Buffer = v11;
    v14 = v12;
    v13.MaximumLength = 2 * v16;
    v13.Length = 2 * v16;
    if ( EqualString(&v14, L"file", 0) )
    {
      result = ImportAttributeFile(a1, &v13, (struct _XMRW_OPEN_CONTEXT *)v5);
      if ( (_DWORD)result )
        return result;
    }
  }
  if ( (int)result >= 0 )
  {
    if ( !v5[2] )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v17);
      PrintMessage(0x3F6u, v17);
      return 3221745169LL;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140035f48  push    rbp
0x140035f4a  push    rbx
0x140035f4b  push    rsi
0x140035f4c  push    rdi
0x140035f4d  push    r14
0x140035f4f  mov     rbp, rsp
0x140035f52  sub     rsp, 60h
0x140035f56  mov     r14, [rcx+40h]
0x140035f5a  xorps   xmm0, xmm0
0x140035f5d  mov     [rbp+var_40], 0
0x140035f65  mov     rbx, rcx
0x140035f68  mov     [rbp+arg_0], 0
0x140035f6f  mov     [rbp+arg_18], 0
0x140035f76  movups  [rbp+var_30], xmm0
0x140035f7a  test    r14, r14
0x140035f7d  jz      loc_140036100
0x140035f83  test    rdx, rdx
0x140035f86  jz      loc_140036100
0x140035f8c  cmp     byte ptr [rcx+78h], 0
0x140035f90  jnz     loc_140036100
0x140035f96  cmp     dword ptr [rcx+30h], 2
0x140035f9a  jnz     loc_140036100
0x140035fa0  movups  xmm0, xmmword ptr [rdx+8]
0x140035fa4  mov     rsi, [rcx+18h]
0x140035fa8  lea     rdx, aReport; "Report"
0x140035faf  xor     r8d, r8d; unsigned __int8
0x140035fb2  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING
0x140035fb6  movdqu  xmmword ptr [rbp+var_20.Length], xmm0
0x140035fbb  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140035fc0  test    al, al
0x140035fc2  jz      loc_140036100
0x140035fc8  mov     rdi, [rbx+70h]
0x140035fcc  test    rdi, rdi
0x140035fcf  jnz     short loc_140035FFD
0x140035fd1  call    cs:__imp_GetProcessHeap
0x140035fd7  lea     edx, [rdi+8]; dwFlags
0x140035fda  mov     r8d, 98h; dwBytes
0x140035fe0  mov     rcx, rax; hHeap
0x140035fe3  call    cs:__imp_HeapAlloc
0x140035fe9  mov     rdi, rax
0x140035fec  test    rax, rax
0x140035fef  jnz     short loc_140035FF9
0x140035ff1  lea     eax, [rdi+8]
0x140035ff4  jmp     loc_140036102
0x140035ff9  mov     [rbx+70h], rax
0x140035ffd  mov     [rdi+40h], r14
0x140036001  mov     byte ptr [rdi+78h], 1
0x140036005  jmp     loc_1400360B6
0x14003600a  inc     dword ptr [rbx+2Ch]
0x14003600d  lea     r8, [rbp+arg_0]
0x140036011  mov     rax, [rsi]
0x140036014  lea     rdx, [rbp+var_40]
0x140036018  mov     rcx, rsi
0x14003601b  mov     rax, [rax+70h]
0x14003601f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036024  mov     rax, [rbp+var_40]
0x140036028  lea     r8, [rbp+arg_10]
0x14003602c  mov     rcx, [rbx+18h]
0x140036030  lea     rdx, [rbp+var_38]
0x140036034  mov     qword ptr [rbp+var_30+8], rax
0x140036038  xorps   xmm0, xmm0
0x14003603b  movzx   eax, word ptr [rbp+arg_0]
0x14003603f  add     ax, ax
0x140036042  mov     [rbp+var_38], 0
0x14003604a  mov     word ptr [rbp+var_30+2], ax
0x14003604e  mov     word ptr [rbp+var_30], ax
0x140036052  mov     [rbp+arg_10], 0
0x140036059  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14003605d  mov     rax, [rcx]
0x140036060  mov     rax, [rax+80h]
0x140036067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003606c  mov     rax, [rbp+var_38]
0x140036070  lea     rdx, aFile; "file"
0x140036077  movaps  xmm0, [rbp+var_30]
0x14003607b  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003607f  mov     [rbp+var_20.Buffer], rax
0x140036083  xor     r8d, r8d; unsigned __int8
0x140036086  movzx   eax, word ptr [rbp+arg_10]
0x14003608a  add     ax, ax
0x14003608d  movdqa  xmmword ptr [rbp+var_10.Length], xmm0
0x140036092  mov     [rbp+var_20.MaximumLength], ax
0x140036096  mov     [rbp+var_20.Length], ax
0x14003609a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003609f  test    al, al
0x1400360a1  jz      short loc_1400360B6
0x1400360a3  mov     r8, rdi; struct _XMRW_OPEN_CONTEXT *
0x1400360a6  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x1400360aa  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x1400360ad  call    ?ImportAttributeFile@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@0@Z; ImportAttributeFile(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_XMRW_OPEN_CONTEXT *)
0x1400360b2  test    eax, eax
0x1400360b4  jnz     short loc_140036102
0x1400360b6  mov     rax, [rsi]
0x1400360b9  mov     rcx, rsi
0x1400360bc  mov     rax, [rax+48h]
0x1400360c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400360c5  test    eax, eax
0x1400360c7  jz      loc_14003600A
0x1400360cd  js      short loc_140036102
0x1400360cf  cmp     qword ptr [rdi+10h], 0
0x1400360d4  jnz     short loc_140036100
0x1400360d6  mov     rax, [rsi]
0x1400360d9  lea     rdx, [rbp+arg_18]
0x1400360dd  mov     rcx, rsi
0x1400360e0  mov     rax, [rax+0A8h]
0x1400360e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400360ec  mov     edx, [rbp+arg_18]
0x1400360ef  mov     ecx, 3F6h; unsigned int
0x1400360f4  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400360f9  mov     eax, 0C007EE11h
0x1400360fe  jmp     short loc_140036102
0x140036100  xor     eax, eax
0x140036102  add     rsp, 60h
0x140036106  pop     r14
0x140036108  pop     rdi
0x140036109  pop     rsi
0x14003610a  pop     rbx
0x14003610b  pop     rbp
0x14003610c  retn
```

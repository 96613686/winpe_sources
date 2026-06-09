# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(ulong,_CVDD *,ulong *)

- ea: `0x18001c398`
- end: `0x18001c53f`
- name: `?RemovePIIFromCvDD@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAT_CVDD@@PEAK@Z`
- size: `423`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, union _CVDD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016698`

## callees

- `0x180001d72`
- `0x18001c398`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        unsigned int a2,
        union _CVDD *a3,
        unsigned int *a4)
{
  unsigned int v7; // esi
  char *v8; // rbx
  char *v9; // rdi
  char *v10; // rax
  int v11; // ebx
  char *v12; // rdi
  char *v13; // rax
  void *v14; // rcx
  char *v15; // rdx
  char *v16; // rax
  int v17; // ebx

  v7 = 0;
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    if ( a4[v7] < 4 )
      goto LABEL_31;
    if ( a4[v7] > 0x628 )
      return 2147549183LL;
    v8 = (char *)a3 + 1576 * v7;
    switch ( *(_DWORD *)v8 )
    {
      case 1:
      case 2:
        v14 = v8 + 16;
        v15 = 0;
        v16 = v8 + 16;
        if ( v8 + 16 < v8 + 1576 )
        {
          do
          {
            if ( !*(_WORD *)v16 )
              break;
            if ( *(_WORD *)v16 == 92 )
              v15 = v16;
            v16 += 2;
          }
          while ( v16 < v8 + 1576 );
          if ( v15 )
          {
            v17 = 2 * ((v15 - v8 - 16) >> 1) + 2;
            memmove_0(v14, v15 + 2, (unsigned int)(1560 - v17));
            a4[v7] -= v17;
          }
        }
        break;
      case 3:
LABEL_9:
        v9 = 0;
        v10 = v8 + 24;
        if ( v8 + 24 >= v8 + 804 )
          break;
        do
        {
          if ( !*v10 )
            break;
          if ( *v10 == 92 )
            v9 = v10;
          ++v10;
        }
        while ( v10 < v8 + 804 );
        if ( !v9 )
          break;
        memmove_0(v8 + 24, v9 + 1, (unsigned int)((_DWORD)v8 - (_DWORD)v9 + 803));
        v11 = (_DWORD)v8 - (_DWORD)v9 + 23;
        goto LABEL_16;
      case 0x3031424E:
        v12 = 0;
        v13 = v8 + 16;
        if ( v8 + 16 >= v8 + 276 )
          break;
        do
        {
          if ( !*v13 )
            break;
          if ( *v13 == 92 )
            v12 = v13;
          ++v13;
        }
        while ( v13 < v8 + 276 );
        if ( !v12 )
          break;
        memmove_0(v8 + 16, v12 + 1, (unsigned int)((_DWORD)v8 - (_DWORD)v12 + 275));
        v11 = (_DWORD)v8 - (_DWORD)v12 + 15;
LABEL_16:
        a4[v7] += v11;
        break;
      case 0x53445352:
        goto LABEL_9;
    }
LABEL_31:
    if ( ++v7 >= a2 )
      return 0;
  }
}

```

## disassembly

```asm
0x18001c398  push    rbx
0x18001c39a  push    rbp
0x18001c39b  push    rsi
0x18001c39c  push    rdi
0x18001c39d  push    r12
0x18001c39f  push    r13
0x18001c3a1  push    r14
0x18001c3a3  push    r15
0x18001c3a5  sub     rsp, 28h
0x18001c3a9  xor     r13d, r13d
0x18001c3ac  mov     r14, r9
0x18001c3af  mov     r12, r8
0x18001c3b2  mov     r15d, edx
0x18001c3b5  mov     esi, r13d
0x18001c3b8  test    edx, edx
0x18001c3ba  jz      loc_18001C524
0x18001c3c0  mov     ebp, esi
0x18001c3c2  cmp     dword ptr [r14+rbp*4], 4
0x18001c3c7  jb      loc_18001C519
0x18001c3cd  cmp     dword ptr [r14+rbp*4], 628h
0x18001c3d5  ja      loc_18001C538
0x18001c3db  imul    rbx, rbp, 628h
0x18001c3e2  add     rbx, r12
0x18001c3e5  mov     ecx, [rbx]
0x18001c3e7  sub     ecx, 1
0x18001c3ea  jz      loc_18001C4BD
0x18001c3f0  sub     ecx, 1
0x18001c3f3  jz      loc_18001C4BD
0x18001c3f9  sub     ecx, 1
0x18001c3fc  jz      short loc_18001C412
0x18001c3fe  sub     ecx, 3031424Bh
0x18001c404  jz      short loc_18001C46D
0x18001c406  cmp     ecx, 23131104h
0x18001c40c  jnz     loc_18001C519
0x18001c412  lea     rcx, [rbx+18h]; void *
0x18001c416  mov     rdi, r13
0x18001c419  lea     rdx, [rcx+30Ch]
0x18001c420  mov     rax, rcx
0x18001c423  cmp     rcx, rdx
0x18001c426  jnb     loc_18001C519
0x18001c42c  cmp     [rax], r13b
0x18001c42f  jz      short loc_18001C440
0x18001c431  cmp     byte ptr [rax], 5Ch ; '\'
0x18001c434  cmovz   rdi, rax
0x18001c438  inc     rax
0x18001c43b  cmp     rax, rdx
0x18001c43e  jb      short loc_18001C42C
0x18001c440  test    rdi, rdi
0x18001c443  jz      loc_18001C519
0x18001c449  mov     r8d, ebx
0x18001c44c  lea     rdx, [rdi+1]; Src
0x18001c450  sub     r8d, edi
0x18001c453  add     r8d, 323h; Size
0x18001c45a  call    memmove_0
0x18001c45f  sub     ebx, edi
0x18001c461  add     ebx, 17h
0x18001c464  add     [r14+rbp*4], ebx
0x18001c468  jmp     loc_18001C519
0x18001c46d  lea     rcx, [rbx+10h]; void *
0x18001c471  mov     rdi, r13
0x18001c474  lea     rdx, [rcx+104h]
0x18001c47b  mov     rax, rcx
0x18001c47e  cmp     rcx, rdx
0x18001c481  jnb     loc_18001C519
0x18001c487  cmp     [rax], r13b
0x18001c48a  jz      short loc_18001C49B
0x18001c48c  cmp     byte ptr [rax], 5Ch ; '\'
0x18001c48f  cmovz   rdi, rax
0x18001c493  inc     rax
0x18001c496  cmp     rax, rdx
0x18001c499  jb      short loc_18001C487
0x18001c49b  test    rdi, rdi
0x18001c49e  jz      short loc_18001C519
0x18001c4a0  mov     r8d, ebx
0x18001c4a3  lea     rdx, [rdi+1]; Src
0x18001c4a7  sub     r8d, edi
0x18001c4aa  add     r8d, 113h; Size
0x18001c4b1  call    memmove_0
0x18001c4b6  sub     ebx, edi
0x18001c4b8  add     ebx, 0Fh
0x18001c4bb  jmp     short loc_18001C464
0x18001c4bd  lea     rcx, [rbx+10h]; void *
0x18001c4c1  mov     rdx, r13
0x18001c4c4  lea     r8, [rcx+618h]
0x18001c4cb  mov     rax, rcx
0x18001c4ce  cmp     rcx, r8
0x18001c4d1  jnb     short loc_18001C519
0x18001c4d3  cmp     [rax], r13w
0x18001c4d7  jz      short loc_18001C4EA
0x18001c4d9  cmp     word ptr [rax], 5Ch ; '\'
0x18001c4dd  cmovz   rdx, rax
0x18001c4e1  add     rax, 2
0x18001c4e5  cmp     rax, r8
0x18001c4e8  jb      short loc_18001C4D3
0x18001c4ea  test    rdx, rdx
0x18001c4ed  jz      short loc_18001C519
0x18001c4ef  mov     rax, rdx
0x18001c4f2  mov     r8d, 618h
0x18001c4f8  sub     rax, rbx
0x18001c4fb  add     rdx, 2; Src
0x18001c4ff  sub     rax, 10h
0x18001c503  sar     rax, 1
0x18001c506  lea     ebx, ds:2[rax*2]
0x18001c50d  sub     r8d, ebx; Size
0x18001c510  call    memmove_0
0x18001c515  sub     [r14+rbp*4], ebx
0x18001c519  inc     esi
0x18001c51b  cmp     esi, r15d
0x18001c51e  jb      loc_18001C3C0
0x18001c524  xor     eax, eax
0x18001c526  add     rsp, 28h
0x18001c52a  pop     r15
0x18001c52c  pop     r14
0x18001c52e  pop     r13
0x18001c530  pop     r12
0x18001c532  pop     rdi
0x18001c533  pop     rsi
0x18001c534  pop     rbp
0x18001c535  pop     rbx
0x18001c536  retn
0x18001c538  mov     eax, 8000FFFFh
0x18001c53d  jmp     short loc_18001C526
```

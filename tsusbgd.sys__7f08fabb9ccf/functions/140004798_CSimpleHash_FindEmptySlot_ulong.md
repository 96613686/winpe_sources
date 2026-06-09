# CSimpleHash::FindEmptySlot(ulong *)

- ea: `0x140004798`
- end: `0x140004891`
- name: `?FindEmptySlot@CSimpleHash@@AEAAJPEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(CSimpleHash *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000464c`

## callees

- `0x140004798`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140004819`
- `ntoskrnl!ExAllocatePool2` at `0x140004819`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000486a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000486a`

## pseudocode

```c
__int64 __fastcall CSimpleHash::FindEmptySlot(CSimpleHash *this, unsigned int *a2)
{
  unsigned int v2; // r8d
  PVOID *v3; // rsi
  __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned int v8; // ebp
  __int64 result; // rax
  __int64 v10; // rax
  __int64 Pool2; // r15
  unsigned int i; // edx
  __int64 v13; // rcx
  __int64 j; // r8

  v2 = *(_DWORD *)this;
  v3 = (PVOID *)((char *)this + 8);
  if ( *(_DWORD *)this )
  {
    v6 = *((_QWORD *)this + 2);
    v7 = 0;
    while ( *((_QWORD *)*v3 + v7) != v6 )
    {
      v7 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v7 >= v2 )
        goto LABEL_5;
    }
    goto LABEL_20;
  }
LABEL_5:
  LODWORD(v7) = -1;
  v8 = (v2 >> 2) + v2 + 1;
  if ( v2 >> 2 )
    v8 = (v2 >> 2) + v2;
  if ( v8 != -1 )
  {
    v10 = 8LL * v8;
    if ( !is_mul_ok(v8, 8u) )
      v10 = -1;
    Pool2 = ExAllocatePool2(256, v10, 1917088324);
    if ( Pool2 )
    {
      for ( i = *(_DWORD *)this; i < v8; ++i )
      {
        v13 = i;
        *(_QWORD *)(Pool2 + 8 * v13) = *((_QWORD *)this + 2);
      }
      LODWORD(v7) = *(_DWORD *)this;
      for ( j = 0; (unsigned int)j < *(_DWORD *)this; LODWORD(v7) = *(_DWORD *)this )
      {
        *(_QWORD *)(Pool2 + 8 * j) = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * j);
        j = (unsigned int)(j + 1);
      }
      if ( *v3 )
        ExFreePoolWithTag(*v3, 0);
      *v3 = (PVOID)Pool2;
      *(_DWORD *)this = v8;
LABEL_20:
      result = 0;
      goto LABEL_21;
    }
  }
  result = 3221225495LL;
LABEL_21:
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x140004798  push    rbx
0x14000479a  push    rbp
0x14000479b  push    rsi
0x14000479c  push    rdi
0x14000479d  push    r12
0x14000479f  push    r14
0x1400047a1  push    r15
0x1400047a3  sub     rsp, 20h
0x1400047a7  mov     r8d, [rcx]
0x1400047aa  lea     rsi, [rcx+8]
0x1400047ae  mov     r12, rdx
0x1400047b1  mov     rdi, rcx
0x1400047b4  test    r8d, r8d
0x1400047b7  jz      short loc_1400047D3
0x1400047b9  mov     rcx, [rcx+10h]
0x1400047bd  xor     ebx, ebx
0x1400047bf  mov     rdx, [rsi]
0x1400047c2  cmp     [rdx+rbx*8], rcx
0x1400047c6  jz      loc_14000487B
0x1400047cc  inc     ebx
0x1400047ce  cmp     ebx, r8d
0x1400047d1  jb      short loc_1400047C2
0x1400047d3  or      ebx, 0FFFFFFFFh
0x1400047d6  mov     ecx, r8d
0x1400047d9  shr     ecx, 2
0x1400047dc  test    ecx, ecx
0x1400047de  lea     eax, [rcx+r8]
0x1400047e2  lea     ebp, [rax+1]
0x1400047e5  cmovnz  ebp, eax
0x1400047e8  cmp     ebp, ebx
0x1400047ea  jb      short loc_1400047F6
0x1400047ec  mov     eax, 0C0000017h
0x1400047f1  jmp     loc_14000487D
0x1400047f6  mov     ecx, ebp
0x1400047f8  mov     eax, 8
0x1400047fd  mul     rcx
0x140004800  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140004807  mov     r8d, 72447244h
0x14000480d  cmovb   rax, rcx
0x140004811  mov     ecx, 100h
0x140004816  mov     rdx, rax
0x140004819  call    cs:__imp_ExAllocatePool2
0x140004820  nop     dword ptr [rax+rax+00h]
0x140004825  mov     r15, rax
0x140004828  test    rax, rax
0x14000482b  jz      short loc_1400047EC
0x14000482d  mov     edx, [rdi]
0x14000482f  jmp     short loc_14000483D
0x140004831  mov     rax, [rdi+10h]
0x140004835  mov     ecx, edx
0x140004837  inc     edx
0x140004839  mov     [r15+rcx*8], rax
0x14000483d  cmp     edx, ebp
0x14000483f  jb      short loc_140004831
0x140004841  mov     ebx, [rdi]
0x140004843  xor     r8d, r8d
0x140004846  test    ebx, ebx
0x140004848  jz      short loc_140004860
0x14000484a  mov     rax, [rdi+8]
0x14000484e  mov     rcx, [rax+r8*8]
0x140004852  mov     [r15+r8*8], rcx
0x140004856  inc     r8d
0x140004859  mov     ebx, [rdi]
0x14000485b  cmp     r8d, ebx
0x14000485e  jb      short loc_14000484A
0x140004860  mov     rcx, [rsi]; P
0x140004863  test    rcx, rcx
0x140004866  jz      short loc_140004876
0x140004868  xor     edx, edx; Tag
0x14000486a  call    cs:__imp_ExFreePoolWithTag
0x140004871  nop     dword ptr [rax+rax+00h]
0x140004876  mov     [rsi], r15
0x140004879  mov     [rdi], ebp
0x14000487b  xor     eax, eax
0x14000487d  mov     [r12], ebx
0x140004881  add     rsp, 20h
0x140004885  pop     r15
0x140004887  pop     r14
0x140004889  pop     r12
0x14000488b  pop     rdi
0x14000488c  pop     rsi
0x14000488d  pop     rbp
0x14000488e  pop     rbx
0x14000488f  retn
```

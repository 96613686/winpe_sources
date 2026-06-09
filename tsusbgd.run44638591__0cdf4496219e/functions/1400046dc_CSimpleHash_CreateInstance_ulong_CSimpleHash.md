# CSimpleHash::CreateInstance(ulong,CSimpleHash * *)

- ea: `0x1400046dc`
- end: `0x140004791`
- name: `?CreateInstance@CSimpleHash@@SAJKPEAPEAV1@@Z`
- size: `181`
- prototype: `__int64 __fastcall(unsigned int, struct CSimpleHash **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001464`

## callees

- `0x1400046dc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400046f9`
- `ntoskrnl!ExAllocatePool2` at `0x140004737`
- `ntoskrnl!ExAllocatePool2` at `0x1400046f9`
- `ntoskrnl!ExAllocatePool2` at `0x140004737`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004774`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004774`

## pseudocode

```c
__int64 __fastcall CSimpleHash::CreateInstance(__int64 a1, struct CSimpleHash **a2)
{
  __int64 Pool2; // rax
  _QWORD *v4; // rbx
  __int64 v5; // rax
  __int64 i; // r8

  Pool2 = ExAllocatePool2(256, 32, 1917088324);
  v4 = (_QWORD *)Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  *(_QWORD *)(Pool2 + 8) = 0;
  *(_BYTE *)(Pool2 + 24) = 0;
  *(_DWORD *)Pool2 = 10;
  *(_QWORD *)(Pool2 + 16) = 0;
  v5 = ExAllocatePool2(256, 80, 1917088324);
  v4[1] = v5;
  if ( !v5 )
  {
    ExFreePoolWithTag(v4, 0);
    return 3221225495LL;
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)v4; i = (unsigned int)(i + 1) )
    *(_QWORD *)(v4[1] + 8 * i) = v4[2];
  *a2 = (struct CSimpleHash *)v4;
  return 0;
}

```

## disassembly

```asm
0x1400046dc  mov     [rsp+arg_0], rbx
0x1400046e1  push    rdi
0x1400046e2  sub     rsp, 20h
0x1400046e6  mov     rdi, rdx
0x1400046e9  mov     ecx, 100h
0x1400046ee  mov     edx, 20h ; ' '
0x1400046f3  mov     r8d, 72447244h
0x1400046f9  call    cs:__imp_ExAllocatePool2
0x140004700  nop     dword ptr [rax+rax+00h]
0x140004705  mov     rbx, rax
0x140004708  test    rax, rax
0x14000470b  jz      short loc_140004780
0x14000470d  mov     qword ptr [rax+8], 0
0x140004715  mov     edx, 50h ; 'P'
0x14000471a  mov     byte ptr [rax+18h], 0
0x14000471e  mov     ecx, 100h
0x140004723  mov     r8d, 72447244h
0x140004729  mov     dword ptr [rax], 0Ah
0x14000472f  mov     qword ptr [rax+10h], 0
0x140004737  call    cs:__imp_ExAllocatePool2
0x14000473e  nop     dword ptr [rax+rax+00h]
0x140004743  mov     [rbx+8], rax
0x140004747  test    rax, rax
0x14000474a  jz      short loc_14000476F
0x14000474c  xor     r8d, r8d
0x14000474f  cmp     [rbx], r8d
0x140004752  jbe     short loc_140004768
0x140004754  mov     rcx, [rbx+8]
0x140004758  mov     rax, [rbx+10h]
0x14000475c  mov     [rcx+r8*8], rax
0x140004760  inc     r8d
0x140004763  cmp     r8d, [rbx]
0x140004766  jb      short loc_140004754
0x140004768  mov     [rdi], rbx
0x14000476b  xor     eax, eax
0x14000476d  jmp     short loc_140004785
0x14000476f  xor     edx, edx; Tag
0x140004771  mov     rcx, rbx; P
0x140004774  call    cs:__imp_ExFreePoolWithTag
0x14000477b  nop     dword ptr [rax+rax+00h]
0x140004780  mov     eax, 0C0000017h
0x140004785  mov     rbx, [rsp+28h+arg_0]
0x14000478a  add     rsp, 20h
0x14000478e  pop     rdi
0x14000478f  retn
```

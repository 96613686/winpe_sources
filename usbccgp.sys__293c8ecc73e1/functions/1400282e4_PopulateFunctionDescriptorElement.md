# PopulateFunctionDescriptorElement

- ea: `0x1400282e4`
- end: `0x1400283a6`
- name: `PopulateFunctionDescriptorElement`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400281ac`

## callees

- `0x140026e14`
- `0x1400278dc`
- `0x140027968`
- `0x1400282e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140028328`
- `ntoskrnl!ExAllocatePool2` at `0x140028328`

## pseudocode

```c
__int64 __fastcall PopulateFunctionDescriptorElement(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rbx
  char v7; // si
  __int64 v8; // r8
  __int64 v9; // rdx
  _QWORD *Pool2; // rax
  _QWORD *v11; // rdx
  _QWORD *v12; // rcx
  int v13; // ebx

  v3 = (_QWORD *)(a2 + 16);
  v7 = CountListEntries(a2 + 16);
  *(_DWORD *)(v8 + 64) = 0;
  v9 = (unsigned __int8)(v7 + 1);
  *(_BYTE *)(v8 + 1) = v9;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 8 * v9, 1130525525);
  a3[1] = Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
LABEL_11:
    DestroyFunctionDescriptorElement(a3);
    return (unsigned int)v13;
  }
  v11 = (_QWORD *)*v3;
  *Pool2 = *(_QWORD *)(a2 + 32);
  v12 = Pool2 + 1;
  if ( v7 )
  {
    while ( v11 != v3 )
    {
      *v12++ = v11[4];
      v11 = (_QWORD *)*v11;
      if ( !--v7 )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    if ( v11 == v3 )
    {
      v13 = BuildIds(a1, a2, a3);
      goto LABEL_8;
    }
  }
  v13 = -1073741595;
LABEL_8:
  if ( v13 < 0 )
    goto LABEL_11;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400282e4  push    rbx
0x1400282e6  push    rbp
0x1400282e7  push    rsi
0x1400282e8  push    rdi
0x1400282e9  push    r14
0x1400282eb  sub     rsp, 20h
0x1400282ef  lea     rbx, [rdx+10h]
0x1400282f3  mov     r14, rcx
0x1400282f6  mov     rcx, rbx
0x1400282f9  mov     rdi, r8
0x1400282fc  mov     rbp, rdx
0x1400282ff  call    CountListEntries
0x140028304  mov     sil, al
0x140028307  mov     dword ptr [r8+40h], 0
0x14002830f  mov     ecx, 40h ; '@'
0x140028314  lea     eax, [rsi+1]
0x140028317  movzx   edx, al
0x14002831a  mov     [r8+1], dl
0x14002831e  mov     r8d, 43627355h
0x140028324  shl     rdx, 3
0x140028328  call    cs:__imp_ExAllocatePool2
0x14002832f  nop     dword ptr [rax+rax+00h]
0x140028334  mov     [rdi+8], rax
0x140028338  test    rax, rax
0x14002833b  jz      short loc_14002838B
0x14002833d  mov     rcx, [rbp+20h]
0x140028341  mov     rdx, [rbx]
0x140028344  mov     [rax], rcx
0x140028347  lea     rcx, [rax+8]
0x14002834b  test    sil, sil
0x14002834e  jz      short loc_140028369
0x140028350  cmp     rdx, rbx
0x140028353  jz      short loc_140028380
0x140028355  mov     rax, [rdx+20h]
0x140028359  mov     [rcx], rax
0x14002835c  add     rcx, 8
0x140028360  mov     rdx, [rdx]
0x140028363  add     sil, 0FFh
0x140028367  jnz     short loc_140028350
0x140028369  cmp     rdx, rbx
0x14002836c  jnz     short loc_140028380
0x14002836e  mov     r8, rdi
0x140028371  mov     rdx, rbp
0x140028374  mov     rcx, r14
0x140028377  call    BuildIds
0x14002837c  mov     ebx, eax
0x14002837e  jmp     short loc_140028385
0x140028380  mov     ebx, 0C00000E5h
0x140028385  test    ebx, ebx
0x140028387  jns     short loc_140028398
0x140028389  jmp     short loc_140028390
0x14002838b  mov     ebx, 0C000009Ah
0x140028390  mov     rcx, rdi; void *
0x140028393  call    DestroyFunctionDescriptorElement
0x140028398  mov     eax, ebx
0x14002839a  add     rsp, 20h
0x14002839e  pop     r14
0x1400283a0  pop     rdi
0x1400283a1  pop     rsi
0x1400283a2  pop     rbp
0x1400283a3  pop     rbx
0x1400283a4  retn
```

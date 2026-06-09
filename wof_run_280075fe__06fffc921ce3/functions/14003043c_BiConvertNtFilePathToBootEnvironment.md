# BiConvertNtFilePathToBootEnvironment

- ea: `0x14003043c`
- end: `0x140030522`
- name: `BiConvertNtFilePathToBootEnvironment`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002fc98`

## callees

- `0x14000da0d`
- `0x1400116c0`
- `0x14002fc98`
- `0x14003043c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003049b`
- `ntoskrnl!ExAllocatePool2` at `0x14003049b`

## pseudocode

```c
__int64 __fastcall BiConvertNtFilePathToBootEnvironment(__int64 a1, __int64 a2, _WORD *a3, unsigned int a4, _QWORD *a5)
{
  int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // esi
  unsigned int v9; // ebp
  _DWORD *Pool2; // rax
  _DWORD *v11; // rbx
  void *Src; // [rsp+20h] [rbp-38h] BYREF

  Src = 0;
  v6 = BiConvertNtDeviceToBootEnvironment(a1, a2, a4, &Src);
  if ( v6 >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
    v9 = v8 + *((_DWORD *)Src + 2) + 12;
    Pool2 = (_DWORD *)ExAllocatePool2(258, v9, 1262764866);
    v11 = Pool2;
    if ( Pool2 )
    {
      *Pool2 = 1;
      Pool2[2] = 5;
      Pool2[1] = v9;
      memmove(Pool2 + 3, Src, *((unsigned int *)Src + 2));
      memmove((char *)v11 + *((unsigned int *)Src + 2) + 12, a3, v8);
      *a5 = v11;
      v6 = 0;
    }
    else
    {
      v6 = -1073741670;
    }
  }
  if ( Src )
    ExFreePoolWithTag_0(Src, 0x4B444342u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003043c  push    rbx
0x14003043e  push    rbp
0x14003043f  push    rsi
0x140030440  push    rdi
0x140030441  push    r14
0x140030443  sub     rsp, 30h
0x140030447  mov     eax, r9d
0x14003044a  mov     rdi, r8
0x14003044d  xor     r14d, r14d
0x140030450  lea     r9, [rsp+58h+Src]
0x140030455  mov     r8d, eax
0x140030458  mov     [rsp+58h+Src], r14
0x14003045d  call    BiConvertNtDeviceToBootEnvironment
0x140030462  mov     ebx, eax
0x140030464  test    eax, eax
0x140030466  js      loc_140030500
0x14003046c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140030470  inc     rax
0x140030473  cmp     [rdi+rax*2], r14w
0x140030478  jnz     short loc_140030470
0x14003047a  lea     esi, ds:2[rax*2]
0x140030481  mov     ecx, 102h
0x140030486  mov     rax, [rsp+58h+Src]
0x14003048b  mov     r8d, 4B444342h
0x140030491  mov     ebp, [rax+8]
0x140030494  add     ebp, 0Ch
0x140030497  add     ebp, esi
0x140030499  mov     edx, ebp
0x14003049b  call    cs:__imp_ExAllocatePool2
0x1400304a2  nop     dword ptr [rax+rax+00h]
0x1400304a7  mov     rbx, rax
0x1400304aa  test    rax, rax
0x1400304ad  jnz     short loc_1400304B6
0x1400304af  mov     ebx, 0C000009Ah
0x1400304b4  jmp     short loc_140030500
0x1400304b6  mov     dword ptr [rax], 1
0x1400304bc  lea     rcx, [rax+0Ch]; void *
0x1400304c0  mov     dword ptr [rax+8], 5
0x1400304c7  mov     [rax+4], ebp
0x1400304ca  mov     rdx, [rsp+58h+Src]; Src
0x1400304cf  mov     r8d, [rdx+8]; Size
0x1400304d3  call    memmove
0x1400304d8  mov     rax, [rsp+58h+Src]
0x1400304dd  mov     rdx, rdi; Src
0x1400304e0  mov     r8d, esi; Size
0x1400304e3  mov     ecx, [rax+8]
0x1400304e6  add     rcx, 0Ch
0x1400304ea  add     rcx, rbx; void *
0x1400304ed  call    memmove
0x1400304f2  mov     rax, [rsp+58h+arg_20]
0x1400304fa  mov     [rax], rbx
0x1400304fd  mov     ebx, r14d
0x140030500  mov     rcx, [rsp+58h+Src]; P
0x140030505  test    rcx, rcx
0x140030508  jz      short loc_140030514
0x14003050a  mov     edx, 4B444342h; Tag
0x14003050f  call    ExFreePoolWithTag_0
0x140030514  mov     eax, ebx
0x140030516  add     rsp, 30h
0x14003051a  pop     r14
0x14003051c  pop     rdi
0x14003051d  pop     rsi
0x14003051e  pop     rbp
0x14003051f  pop     rbx
0x140030520  retn
```

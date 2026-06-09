# RecordStartFailData

- ea: `0x14000f664`
- end: `0x14000f7f8`
- name: `RecordStartFailData`
- size: `404`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fb68`
- `0x140011280`
- `0x140023214`
- `0x140023938`
- `0x140026b6c`
- `0x140028f7c`
- `0x14002977c`
- `0x14002b010`
- `0x14002b3bc`
- `0x14002c430`
- `0x14002c8e4`

## callees

- `0x14000f664`
- `0x140014e00`
- `0x140015100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f736`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f781`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f736`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f781`
- `ntoskrnl!ExAllocatePool2` at `0x14000f6d4`
- `ntoskrnl!ExAllocatePool2` at `0x14000f6d4`

## pseudocode

```c
void __fastcall RecordStartFailData(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        void *Src,
        size_t Size)
{
  int v9; // ebx
  int *v10; // rax
  int v11; // ecx
  unsigned int v12; // r14d
  unsigned int *Pool2; // rax
  unsigned int *v14; // rdi
  unsigned int v15; // r15d
  unsigned int *v16; // rcx
  _DWORD *v17; // rsi
  __int64 v18; // rax

  v9 = Size + 36;
  if ( (((_BYTE)Size + 36) & 7) != 0 )
    v9 = v9 - (((_BYTE)Size + 36) & 7) + 8;
  v10 = *(int **)(a1 + 1144);
  if ( v10 )
    v11 = *v10;
  else
    v11 = 16;
  v12 = v11 + v9;
  if ( (unsigned int)(v11 + v9) >= 0x34 )
  {
    Pool2 = (unsigned int *)ExAllocatePool2(64, v12, 1130525525);
    v14 = Pool2;
    if ( Pool2 )
    {
      v15 = v12;
      memset(Pool2, 0, v12);
      v16 = *(unsigned int **)(a1 + 1144);
      v17 = v14 + 4;
      if ( v16 )
      {
        if ( *v16 <= v12 )
        {
          memmove(v14, *(const void **)(a1 + 1144), *v16);
          v16 = *(unsigned int **)(a1 + 1144);
          v18 = *v16;
          v15 = v12 - v18;
          v17 = (unsigned int *)((char *)v14 + v18);
        }
        ExFreePoolWithTag(v16, 0x43627355u);
        *(_QWORD *)(a1 + 1144) = 0;
      }
      else
      {
        v15 = v12 - 16;
      }
      v14[2] = a3;
      *v14 = v12;
      v14[1] = a2;
      v14[3] = 0;
      if ( v15 >= 0x24 )
      {
        *v17 = 1131573829;
        *((_QWORD *)v17 + 1) = *(_QWORD *)(a1 + 32);
        v17[4] = a4;
        v17[5] = a5;
        v17[6] = a2;
        v17[7] = Size;
        v17[1] = v9;
        if ( Src )
        {
          if ( v15 - 36 >= (unsigned int)Size )
            memmove(v17 + 8, Src, (unsigned int)Size);
        }
        *(_QWORD *)(a1 + 1144) = v14;
      }
      else
      {
        *(_QWORD *)(a1 + 1144) = 0;
        ExFreePoolWithTag(v14, 0x43627355u);
      }
    }
  }
}

```

## disassembly

```asm
0x14000f664  mov     [rsp+arg_0], rbx
0x14000f669  mov     [rsp+arg_18], r9d
0x14000f66e  mov     [rsp+arg_10], r8d
0x14000f673  push    rbp
0x14000f674  push    rsi
0x14000f675  push    rdi
0x14000f676  push    r12
0x14000f678  push    r13
0x14000f67a  push    r14
0x14000f67c  push    r15
0x14000f67e  sub     rsp, 20h
0x14000f682  mov     r13d, dword ptr [rsp+58h+Size]
0x14000f68a  mov     r12d, edx
0x14000f68d  mov     rbp, rcx
0x14000f690  lea     ebx, [r13+24h]
0x14000f694  mov     eax, ebx
0x14000f696  and     eax, 7
0x14000f699  jz      short loc_14000F6A0
0x14000f69b  sub     ebx, eax
0x14000f69d  add     ebx, 8
0x14000f6a0  mov     rax, [rcx+478h]
0x14000f6a7  test    rax, rax
0x14000f6aa  jz      short loc_14000F6B0
0x14000f6ac  mov     ecx, [rax]
0x14000f6ae  jmp     short loc_14000F6B5
0x14000f6b0  mov     ecx, 10h
0x14000f6b5  lea     r14d, [rcx+rbx]
0x14000f6b9  cmp     r14d, 34h ; '4'
0x14000f6bd  jb      loc_14000F7E2
0x14000f6c3  mov     r8d, 43627355h
0x14000f6c9  mov     edx, r14d
0x14000f6cc  mov     ecx, 40h ; '@'
0x14000f6d1  mov     esi, r14d
0x14000f6d4  call    cs:__imp_ExAllocatePool2
0x14000f6db  nop     dword ptr [rax+rax+00h]
0x14000f6e0  mov     rdi, rax
0x14000f6e3  test    rax, rax
0x14000f6e6  jz      loc_14000F7E2
0x14000f6ec  mov     r8d, esi; Size
0x14000f6ef  xor     edx, edx; Val
0x14000f6f1  mov     rcx, rax; void *
0x14000f6f4  mov     r15d, r14d
0x14000f6f7  call    memset
0x14000f6fc  mov     rcx, [rbp+478h]
0x14000f703  lea     rsi, [rdi+10h]
0x14000f707  test    rcx, rcx
0x14000f70a  jz      short loc_14000F74F
0x14000f70c  mov     eax, [rcx]
0x14000f70e  cmp     eax, r14d
0x14000f711  ja      short loc_14000F731
0x14000f713  mov     rdx, rcx; Src
0x14000f716  mov     r8d, eax; Size
0x14000f719  mov     rcx, rdi; void *
0x14000f71c  call    memmove
0x14000f721  mov     rcx, [rbp+478h]; P
0x14000f728  mov     eax, [rcx]
0x14000f72a  sub     r15d, eax
0x14000f72d  lea     rsi, [rdi+rax]
0x14000f731  mov     edx, 43627355h; Tag
0x14000f736  call    cs:__imp_ExFreePoolWithTag
0x14000f73d  nop     dword ptr [rax+rax+00h]
0x14000f742  mov     qword ptr [rbp+478h], 0
0x14000f74d  jmp     short loc_14000F753
0x14000f74f  add     r15d, 0FFFFFFF0h
0x14000f753  mov     eax, [rsp+58h+arg_10]
0x14000f757  mov     [rdi+8], eax
0x14000f75a  mov     [rdi], r14d
0x14000f75d  mov     [rdi+4], r12d
0x14000f761  mov     dword ptr [rdi+0Ch], 0
0x14000f768  cmp     r15d, 24h ; '$'
0x14000f76c  jnb     short loc_14000F78F
0x14000f76e  mov     edx, 43627355h; Tag
0x14000f773  mov     qword ptr [rbp+478h], 0
0x14000f77e  mov     rcx, rdi; P
0x14000f781  call    cs:__imp_ExFreePoolWithTag
0x14000f788  nop     dword ptr [rax+rax+00h]
0x14000f78d  jmp     short loc_14000F7E2
0x14000f78f  mov     rdx, [rsp+58h+Src]; Src
0x14000f797  mov     dword ptr [rsi], 43727245h
0x14000f79d  mov     rax, [rbp+20h]
0x14000f7a1  mov     [rsi+8], rax
0x14000f7a5  mov     eax, [rsp+58h+arg_18]
0x14000f7a9  mov     [rsi+10h], eax
0x14000f7ac  mov     eax, [rsp+58h+arg_20]
0x14000f7b3  mov     [rsi+14h], eax
0x14000f7b6  mov     [rsi+18h], r12d
0x14000f7ba  mov     [rsi+1Ch], r13d
0x14000f7be  mov     [rsi+4], ebx
0x14000f7c1  test    rdx, rdx
0x14000f7c4  jz      short loc_14000F7DB
0x14000f7c6  lea     eax, [r15-24h]
0x14000f7ca  cmp     eax, r13d
0x14000f7cd  jb      short loc_14000F7DB
0x14000f7cf  mov     r8, r13; Size
0x14000f7d2  lea     rcx, [rsi+20h]; void *
0x14000f7d6  call    memmove
0x14000f7db  mov     [rbp+478h], rdi
0x14000f7e2  mov     rbx, [rsp+58h+arg_0]
0x14000f7e7  add     rsp, 20h
0x14000f7eb  pop     r15
0x14000f7ed  pop     r14
0x14000f7ef  pop     r13
0x14000f7f1  pop     r12
0x14000f7f3  pop     rdi
0x14000f7f4  pop     rsi
0x14000f7f5  pop     rbp
0x14000f7f6  retn
```

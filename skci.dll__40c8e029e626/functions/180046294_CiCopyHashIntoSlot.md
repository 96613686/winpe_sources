# CiCopyHashIntoSlot

- ea: `0x180046294`
- end: `0x18004634a`
- name: `CiCopyHashIntoSlot`
- size: `182`
- prototype: `bool __fastcall(int, const void *, unsigned int, char *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012660`

## callees

- `0x18003392c`
- `0x180046294`

## pseudocode

```c
bool __fastcall CiCopyHashIntoSlot(int a1, const void *a2, unsigned int a3, char *a4, __int64 a5)
{
  char v6; // bl
  int v7; // ecx
  char v8; // r10
  int v9; // ecx
  int v10; // ecx
  char v11; // bl
  bool v12; // si
  char *v13; // rcx
  __int64 v14; // rcx
  bool result; // al

  v6 = *a4;
  *(_DWORD *)a5 = a1;
  v7 = a1 - 32772;
  if ( !v7 )
  {
    v14 = 1;
    *(_DWORD *)(a5 + 4) = 20;
    v8 = 1;
    goto LABEL_10;
  }
  v8 = 8;
  v9 = v7 - 8;
  if ( !v9 )
  {
    *(_DWORD *)(a5 + 4) = 32;
    v8 = 2;
    v14 = 21;
    goto LABEL_10;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    *(_DWORD *)(a5 + 4) = 48;
    v8 = 4;
    v14 = 53;
    goto LABEL_10;
  }
  if ( v10 == 1 )
  {
    *(_DWORD *)(a5 + 4) = 64;
    v14 = 101;
LABEL_10:
    v13 = &a4[v14];
    v11 = v8 | v6;
    *(_QWORD *)(a5 + 8) = v13;
    v12 = v11 == *a4;
    goto LABEL_11;
  }
  v11 = 0;
  v12 = 0;
  *(_OWORD *)a5 = 0;
  v13 = 0;
LABEL_11:
  memcpy_0(v13, a2, a3);
  result = v12;
  *a4 = v11;
  return result;
}

```

## disassembly

```asm
0x180046294  mov     [rsp+arg_0], rbx
0x180046299  mov     [rsp+arg_8], rsi
0x18004629e  push    rdi
0x18004629f  sub     rsp, 20h
0x1800462a3  mov     rax, [rsp+28h+arg_20]
0x1800462a8  mov     rdi, r9
0x1800462ab  mov     bl, [r9]
0x1800462ae  mov     [rax], ecx
0x1800462b0  sub     ecx, 8004h
0x1800462b6  jz      short loc_18004630C
0x1800462b8  mov     r10d, 8
0x1800462be  sub     ecx, r10d
0x1800462c1  jz      short loc_1800462FB
0x1800462c3  sub     ecx, 1
0x1800462c6  jz      short loc_1800462EA
0x1800462c8  cmp     ecx, 1
0x1800462cb  jz      short loc_1800462DC
0x1800462cd  xor     bl, bl
0x1800462cf  xorps   xmm0, xmm0
0x1800462d2  xor     sil, sil
0x1800462d5  movups  xmmword ptr [rax], xmm0
0x1800462d8  xor     ecx, ecx
0x1800462da  jmp     short loc_18004632C
0x1800462dc  mov     dword ptr [rax+4], 40h ; '@'
0x1800462e3  mov     ecx, 65h ; 'e'
0x1800462e8  jmp     short loc_18004631B
0x1800462ea  mov     dword ptr [rax+4], 30h ; '0'
0x1800462f1  mov     r10b, 4
0x1800462f4  mov     ecx, 35h ; '5'
0x1800462f9  jmp     short loc_18004631B
0x1800462fb  mov     dword ptr [rax+4], 20h ; ' '
0x180046302  mov     r10b, 2
0x180046305  mov     ecx, 15h
0x18004630a  jmp     short loc_18004631B
0x18004630c  mov     ecx, 1
0x180046311  mov     dword ptr [rax+4], 14h
0x180046318  mov     r10b, cl
0x18004631b  add     rcx, rdi; void *
0x18004631e  or      bl, r10b
0x180046321  mov     [rax+8], rcx
0x180046325  cmp     bl, [r9]
0x180046328  setz    sil
0x18004632c  mov     r8d, r8d; MaxCount
0x18004632f  call    memcpy_0
0x180046334  mov     al, sil
0x180046337  mov     [rdi], bl
0x180046339  mov     rsi, [rsp+28h+arg_8]
0x18004633e  mov     rbx, [rsp+28h+arg_0]
0x180046343  add     rsp, 20h
0x180046347  pop     rdi
0x180046348  retn
```

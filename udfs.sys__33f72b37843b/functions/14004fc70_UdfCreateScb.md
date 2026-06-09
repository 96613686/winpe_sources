# UdfCreateScb

- ea: `0x14004fc70`
- end: `0x14004ffb6`
- name: `UdfCreateScb`
- size: `838`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140014cb8`
- `0x14002e4fc`
- `0x1400312c0`
- `0x140033548`
- `0x140034450`
- `0x14003d334`
- `0x14004d700`
- `0x14004e020`
- `0x140050224`

## callees

- `0x140004340`
- `0x14001c080`
- `0x14002f938`
- `0x14004fc70`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14004fd3d`
- `ntoskrnl!KeBugCheckEx` at `0x14004fd3d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004fdcf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004fdcf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005a7e2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005a7e2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005a815`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005a815`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004fd50`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004fe1e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004fe7d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004fd50`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004fe1e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004fe7d`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14004fcee`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14004fcee`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14004fdb7`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14004fdb7`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14005a7bd`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14005a7bd`

## pseudocode

```c
_QWORD *__fastcall UdfCreateScb(__int64 a1, __int64 a2, unsigned __int16 a3, __int64 a4, _BYTE *a5)
{
  int v6; // r15d
  _BYTE *v9; // r12
  _QWORD *v10; // rdi
  _QWORD *v11; // rax
  _WORD *v12; // r14
  PVOID *v13; // rsi
  _OWORD *v14; // rax
  _QWORD *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  void *v18; // rcx
  _BYTE v20[7]; // [rsp+31h] [rbp-47h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-40h]
  _QWORD v22[2]; // [rsp+40h] [rbp-38h] BYREF
  __int16 v24; // [rsp+8Ch] [rbp+14h]

  v24 = WORD2(a2);
  v6 = a3;
  v21 = 0;
  v9 = v20;
  if ( a5 )
    v9 = a5;
  v22[1] = 0;
  v10 = 0;
  v22[0] = a2;
  v11 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(*(_QWORD *)(a1 + 16) + 1736LL), v22);
  if ( v11 )
    v10 = (_QWORD *)v11[1];
  if ( v10 )
  {
    *v9 = 1;
    return v10;
  }
  if ( v6 == 2355 )
  {
    v12 = ExAllocateFromPagedLookasideList(&UdfScbIndexLookasideList);
    memset(v12, 0, 0x230u);
    v12[1] = 560;
    *((_QWORD *)v12 + 68) = v12 + 268;
    *((_QWORD *)v12 + 67) = v12 + 268;
    v16 = *(_QWORD *)(a1 + 16);
    if ( (*(_DWORD *)(v16 + 48) & 0x4000000) != 0 )
    {
      v13 = (PVOID *)v12;
      v10 = v12;
      if ( v24 == *(_WORD *)(*(_QWORD *)(v16 + 16) + 84LL) )
        *((_DWORD *)v12 + 53) |= 0x8000000u;
      goto LABEL_11;
    }
  }
  else
  {
    if ( v6 != 2356 )
      KeBugCheckEx(0x9Bu, 0x130EA9u, 0, 0, 0);
    v12 = ExAllocateFromPagedLookasideList(&UdfScbDataLookasideList);
    memset(v12, 0, 0x200u);
    v12[1] = 512;
  }
  v10 = v12;
  v13 = (PVOID *)v12;
LABEL_11:
  *v12 = v6;
  v10[23] = a2;
  v10[21] = v10 + 20;
  v10[20] = v10 + 20;
  v10[16] = v10 + 15;
  v10[15] = v10 + 15;
  if ( (_WORD)v6 == 2356 )
    FsRtlInitializeOplock(v13 + 11);
  v14 = ExAllocateFromNPagedLookasideList(&UdfScbNonPagedLookasideList);
  v10[53] = v14;
  *v14 = 0;
  v14[1] = 0;
  *(_WORD *)v10[53] = 2357;
  *(_WORD *)(v10[53] + 2LL) = 32;
  if ( a4 )
  {
    v10[17] = a4;
  }
  else
  {
    v15 = ExAllocateFromPagedLookasideList(&UdfFcbLookasideList);
    v21 = v15;
    memset(v15, 0, 0x68u);
    *(_DWORD *)v15 = 6818108;
    v15[5] = v15 + 4;
    v15[4] = v15 + 4;
    v15[10] = UdfCreateFcbNonPaged();
    v15[1] = *(_QWORD *)(a1 + 16);
    v10[17] = v15;
  }
  v10[1] = *(_QWORD *)(v10[17] + 80LL) + 8LL;
  v10[2] = *(_QWORD *)(v10[17] + 80LL) + 112LL;
  v10[19] = v10 + 18;
  v10[18] = v10 + 18;
  v17 = *(_QWORD *)(v10[17] + 80LL);
  *((_BYTE *)v13 + 4) |= 0x40u;
  *((_BYTE *)v13 + 6) |= 2u;
  *((_BYTE *)v13 + 7) = *((_BYTE *)v13 + 7) & 0xF | 0x50;
  v13[8] = v13 + 7;
  v13[7] = v13 + 7;
  v18 = (void *)(v17 + 272);
  if ( v18 )
    v13[6] = v18;
  v13[9] = 0;
  v13[10] = 0;
  v13[11] = 0;
  v13[12] = 0;
  *((_DWORD *)v13 + 26) = 0;
  v13[14] = 0;
  if ( v10[17] != -88 )
    v10[10] = v10[17] + 88LL;
  *v9 = 0;
  return v10;
}

```

## disassembly

```asm
0x14004fc70  mov     r11, rsp
0x14004fc73  mov     [r11+18h], rbx
0x14004fc77  mov     [r11+20h], rsi
0x14004fc7b  mov     [rsp+arg_8], rdx
0x14004fc80  mov     [r11+8], rcx
0x14004fc84  push    rdi
0x14004fc85  push    r12
0x14004fc87  push    r13
0x14004fc89  push    r14
0x14004fc8b  push    r15
0x14004fc8d  sub     rsp, 50h
0x14004fc91  mov     r13, r9
0x14004fc94  movzx   r15d, r8w
0x14004fc98  mov     rbx, rdx
0x14004fc9b  mov     rsi, rcx
0x14004fc9e  xor     r14d, r14d
0x14004fca1  mov     [r11-40h], r14
0x14004fca5  mov     [r11-48h], r14b
0x14004fca9  lea     r12, [r11-47h]
0x14004fcad  mov     rax, [rsp+78h+arg_20]
0x14004fcb5  test    rax, rax
0x14004fcb8  cmovnz  r12, rax
0x14004fcbc  mov     [r11-30h], r14
0x14004fcc0  mov     edi, r14d
0x14004fcc3  mov     [rsp+78h+var_38], ebx
0x14004fcc7  mov     rax, rdx
0x14004fcca  shr     rax, 20h
0x14004fcce  mov     [rsp+78h+var_34], ax
0x14004fcd3  mov     rax, rdx
0x14004fcd6  shr     rax, 30h
0x14004fcda  mov     [rsp+78h+var_32], ax
0x14004fcdf  mov     rcx, [rcx+10h]
0x14004fce3  add     rcx, 6C8h; Table
0x14004fcea  lea     rdx, [r11-38h]; Buffer
0x14004fcee  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14004fcf5  nop     dword ptr [rax+rax+00h]
0x14004fcfa  test    rax, rax
0x14004fcfd  jz      short loc_14004FD03
0x14004fcff  mov     rdi, [rax+8]
0x14004fd03  mov     [rsp+78h+arg_20], rdi
0x14004fd0b  test    rdi, rdi
0x14004fd0e  jnz     loc_14004FF93
0x14004fd14  mov     ecx, r15d
0x14004fd17  sub     ecx, 933h
0x14004fd1d  jz      loc_14004FE76
0x14004fd23  cmp     ecx, 1
0x14004fd26  jz      short loc_14004FD49
0x14004fd28  mov     [rsp+78h+BugCheckParameter4], r14; BugCheckParameter4
0x14004fd2d  xor     r9d, r9d; BugCheckParameter3
0x14004fd30  xor     r8d, r8d; BugCheckParameter2
0x14004fd33  mov     edx, 130EA9h; BugCheckParameter1
0x14004fd38  mov     ecx, 9Bh; BugCheckCode
0x14004fd3d  call    cs:__imp_KeBugCheckEx
0x14004fd49  lea     rcx, UdfScbDataLookasideList; Lookaside
0x14004fd50  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14004fd57  nop     dword ptr [rax+rax+00h]
0x14004fd5c  mov     r14, rax
0x14004fd5f  mov     [rsp+78h+arg_20], rax
0x14004fd67  mov     edi, 200h
0x14004fd6c  mov     r8d, edi; Size
0x14004fd6f  xor     edx, edx; Val
0x14004fd71  mov     rcx, rax; void *
0x14004fd74  call    memset
0x14004fd79  mov     [r14+2], di
0x14004fd7e  mov     rdi, r14
0x14004fd81  mov     rsi, r14
0x14004fd84  mov     [r14], r15w
0x14004fd88  mov     [rdi+0B8h], rbx
0x14004fd8f  lea     rax, [rdi+0A0h]
0x14004fd96  mov     [rax+8], rax
0x14004fd9a  mov     [rax], rax
0x14004fd9d  lea     rax, [rdi+78h]
0x14004fda1  mov     [rax+8], rax
0x14004fda5  mov     [rax], rax
0x14004fda8  mov     eax, 934h
0x14004fdad  cmp     ax, r15w
0x14004fdb1  jnz     short loc_14004FDC8
0x14004fdb3  lea     rcx, [rsi+58h]; Oplock
0x14004fdb7  call    cs:__imp_FsRtlInitializeOplock
0x14004fdbe  nop     dword ptr [rax+rax+00h]
0x14004fdc3  mov     [rsp+78h+var_48], 1
0x14004fdc8  lea     rcx, UdfScbNonPagedLookasideList; Lookaside
0x14004fdcf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004fdd6  nop     dword ptr [rax+rax+00h]
0x14004fddb  mov     [rdi+1A8h], rax
0x14004fde2  xorps   xmm0, xmm0
0x14004fde5  movups  xmmword ptr [rax], xmm0
0x14004fde8  movups  xmmword ptr [rax+10h], xmm0
0x14004fdec  mov     rax, [rdi+1A8h]
0x14004fdf3  mov     ecx, 935h
0x14004fdf8  mov     [rax], cx
0x14004fdfb  mov     rax, [rdi+1A8h]
0x14004fe02  mov     ecx, 20h ; ' '
0x14004fe07  mov     [rax+2], cx
0x14004fe0b  xor     r15d, r15d
0x14004fe0e  test    r13, r13
0x14004fe11  jnz     loc_14004FEF4
0x14004fe17  lea     rcx, UdfFcbLookasideList; Lookaside
0x14004fe1e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14004fe25  nop     dword ptr [rax+rax+00h]
0x14004fe2a  mov     rbx, rax
0x14004fe2d  mov     [rsp+78h+var_40], rax
0x14004fe32  xor     edx, edx; Val
0x14004fe34  lea     r8d, [r15+68h]; Size
0x14004fe38  mov     rcx, rax; void *
0x14004fe3b  call    memset
0x14004fe40  mov     dword ptr [rbx], 68093Ch
0x14004fe46  lea     rcx, [rbx+20h]
0x14004fe4a  mov     [rcx+8], rcx
0x14004fe4e  mov     [rcx], rcx
0x14004fe51  call    UdfCreateFcbNonPaged
0x14004fe56  mov     [rbx+50h], rax
0x14004fe5a  mov     rax, [rsp+78h+arg_0]
0x14004fe62  mov     rax, [rax+10h]
0x14004fe66  mov     [rbx+8], rax
0x14004fe6a  mov     [rdi+88h], rbx
0x14004fe71  jmp     loc_14004FEFB
0x14004fe76  lea     rcx, UdfScbIndexLookasideList; Lookaside
0x14004fe7d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14004fe84  nop     dword ptr [rax+rax+00h]
0x14004fe89  mov     r14, rax
0x14004fe8c  mov     [rsp+78h+arg_20], rax
0x14004fe94  mov     edi, 230h
0x14004fe99  mov     r8d, edi; Size
0x14004fe9c  xor     edx, edx; Val
0x14004fe9e  mov     rcx, rax; void *
0x14004fea1  call    memset
0x14004fea6  mov     [r14+2], di
0x14004feab  lea     rax, [r14+218h]
0x14004feb2  mov     [rax+8], rax
0x14004feb6  mov     [rax], rax
0x14004feb9  mov     rdx, [rsi+10h]
0x14004febd  test    dword ptr [rdx+30h], 4000000h
0x14004fec4  jz      loc_14004FD7E
0x14004feca  movzx   ecx, word ptr [rsp+78h+arg_8+4]
0x14004fed2  mov     rax, [rdx+10h]
0x14004fed6  mov     rsi, r14
0x14004fed9  mov     rdi, r14
0x14004fedc  cmp     cx, [rax+54h]
0x14004fee0  jnz     loc_14004FD84
0x14004fee6  bts     dword ptr [r14+0D4h], 1Bh
0x14004feef  jmp     loc_14004FD84
0x14004fef4  mov     [rdi+88h], r13
0x14004fefb  mov     rax, [rdi+88h]
0x14004ff02  mov     rcx, [rax+50h]
0x14004ff06  add     rcx, 8
0x14004ff0a  mov     [rdi+8], rcx
0x14004ff0e  mov     rax, [rdi+88h]
0x14004ff15  mov     rcx, [rax+50h]
0x14004ff19  add     rcx, 70h ; 'p'
0x14004ff1d  mov     [rdi+10h], rcx
0x14004ff21  lea     rax, [rdi+90h]
0x14004ff28  mov     [rax+8], rax
0x14004ff2c  mov     [rax], rax
0x14004ff2f  mov     rax, [rdi+88h]
0x14004ff36  mov     rcx, [rax+50h]
0x14004ff3a  or      byte ptr [rsi+4], 40h
0x14004ff3e  or      byte ptr [rsi+6], 2
0x14004ff42  mov     al, [rsi+7]
0x14004ff45  and     al, 0Fh
0x14004ff47  or      al, 50h
0x14004ff49  mov     [rsi+7], al
0x14004ff4c  lea     rax, [rsi+38h]
0x14004ff50  mov     [rax+8], rax
0x14004ff54  mov     [rax], rax
0x14004ff57  add     rcx, 110h
0x14004ff5e  jz      short loc_14004FF64
0x14004ff60  mov     [rsi+30h], rcx
0x14004ff64  mov     [rsi+48h], r15
0x14004ff68  mov     [rsi+50h], r15
0x14004ff6c  mov     [rsi+58h], r15
0x14004ff70  mov     [rsi+60h], r15
0x14004ff74  mov     [rsi+68h], r15d
0x14004ff78  mov     [rsi+70h], r15
0x14004ff7c  mov     rax, [rdi+88h]
0x14004ff83  add     rax, 58h ; 'X'
0x14004ff87  jz      short loc_14004FF8D
0x14004ff89  mov     [rdi+50h], rax
0x14004ff8d  mov     [r12], r15b
0x14004ff91  jmp     short loc_14004FF98
0x14004ff93  mov     byte ptr [r12], 1
0x14004ff98  mov     rax, rdi
0x14004ff9b  lea     r11, [rsp+78h+var_28]
0x14004ffa0  mov     rbx, [r11+40h]
0x14004ffa4  mov     rsi, [r11+48h]
0x14004ffa8  mov     rsp, r11
0x14004ffab  pop     r15
0x14004ffad  pop     r14
0x14004ffaf  pop     r13
0x14004ffb1  pop     r12
0x14004ffb3  pop     rdi
0x14004ffb4  retn
0x14005a796  push    rbx
0x14005a798  push    rbp
0x14005a799  sub     rsp, 38h
0x14005a79d  mov     rbp, rdx
0x14005a7a0  movzx   eax, cl
0x14005a7a3  test    cl, cl
0x14005a7a5  jz      short loc_14005A822
0x14005a7a7  mov     rbx, [rbp+0A0h]
0x14005a7ae  test    rbx, rbx
0x14005a7b1  jz      short loc_14005A822
0x14005a7b3  cmp     byte ptr [rbp+30h], 0
0x14005a7b7  jz      short loc_14005A7CA
0x14005a7b9  lea     rcx, [rbx+58h]; Oplock
0x14005a7bd  call    cs:__imp_FsRtlUninitializeOplock
0x14005a7c4  nop     dword ptr [rax+rax+00h]
0x14005a7c9  nop
0x14005a7ca  cmp     qword ptr [rbx+1A8h], 0
0x14005a7d2  jz      short loc_14005A7F9
0x14005a7d4  mov     rdx, [rbx+1A8h]; Entry
0x14005a7db  lea     rcx, UdfScbNonPagedLookasideList; Lookaside
0x14005a7e2  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005a7e9  nop     dword ptr [rax+rax+00h]
0x14005a7ee  mov     qword ptr [rbx+1A8h], 0
0x14005a7f9  lea     rcx, [rbp+0A0h]
0x14005a800  call    UdfFreePool
0x14005a805  mov     rdx, [rbp+38h]; Entry
0x14005a809  test    rdx, rdx
0x14005a80c  jz      short loc_14005A822
0x14005a80e  lea     rcx, UdfFcbLookasideList; Lookaside
0x14005a815  call    cs:__imp_ExFreeToPagedLookasideList
0x14005a81c  nop     dword ptr [rax+rax+00h]
0x14005a821  nop
0x14005a822  add     rsp, 38h
0x14005a826  pop     rbp
0x14005a827  pop     rbx
0x14005a828  retn
```

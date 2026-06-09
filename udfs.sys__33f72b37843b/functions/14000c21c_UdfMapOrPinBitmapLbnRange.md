# UdfMapOrPinBitmapLbnRange

- ea: `0x14000c21c`
- end: `0x14000c365`
- name: `UdfMapOrPinBitmapLbnRange`
- size: `329`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c4fc`
- `0x14000e438`
- `0x140010dd0`
- `0x140010f38`
- `0x140039938`
- `0x140048c24`

## callees

- `0x14000c21c`
- `0x14000e5d8`

## import_xrefs

- `ntoskrnl!CcPinRead` at `0x14000c2d1`
- `ntoskrnl!CcPinRead` at `0x14000c2d1`
- `ntoskrnl!RtlInitializeBitMap` at `0x14000c345`
- `ntoskrnl!RtlInitializeBitMap` at `0x14000c345`

## pseudocode

```c
void __fastcall UdfMapOrPinBitmapLbnRange(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v3; // rdi
  ULONG v4; // r14d
  int v5; // r8d
  __int64 v6; // rsi
  __int64 v7; // rcx
  ULONG *v8; // rdx
  ULONG v9; // r8d
  DWORD v10; // ecx
  union _LARGE_INTEGER FileOffset; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  v4 = 0x2000;
  FileOffset.QuadPart = 0;
  v5 = (a3 >> 3) + 24;
  if ( *(_DWORD *)(v3 + 88) )
    v4 = *(_DWORD *)(v3 + 88);
  v6 = 200LL * (int)a2;
  v7 = v5 & -v4;
  FileOffset.LowPart = v7;
  if ( *(_DWORD *)(v6 + v3 + 528) != (_DWORD)v7 || !*(_QWORD *)(v6 + v3 + 504) )
  {
    *(_DWORD *)(v6 + v3 + 528) = v7;
    UdfUnpinCurrentBitmapPage(v7, v3, a2);
    CcPinRead(
      *(PFILE_OBJECT *)(*(_QWORD *)(v6 + v3 + 488) + 504LL),
      &FileOffset,
      v4,
      1u,
      (PVOID *)(v6 + v3 + 504),
      (PVOID *)(v6 + v3 + 512));
    v8 = *(ULONG **)(v6 + v3 + 512);
    v9 = 8 * v4;
    *(_DWORD *)(v6 + v3 + 524) = 8 * v4;
    v10 = 8 * FileOffset.LowPart;
    *(_DWORD *)(v6 + v3 + 520) = 8 * FileOffset.LowPart;
    if ( FileOffset.LowPart )
    {
      v10 -= 192;
      *(_DWORD *)(v6 + v3 + 520) = v10;
    }
    else
    {
      v8 += 6;
      v9 -= 192;
    }
    if ( v9 >= *(_DWORD *)(v6 + v3 + 664) - v10 )
      v9 = *(_DWORD *)(v6 + v3 + 664) - v10;
    *(_DWORD *)(v6 + v3 + 524) = v9;
    RtlInitializeBitMap((PRTL_BITMAP)(v6 + v3 + 536), v8, v9);
  }
}

```

## disassembly

```asm
0x14000c21c  mov     [rsp+arg_8], rbx
0x14000c221  mov     [rsp+arg_10], rbp
0x14000c226  push    rsi
0x14000c227  push    rdi
0x14000c228  push    r14
0x14000c22a  sub     rsp, 30h
0x14000c22e  mov     rdi, [rcx+10h]
0x14000c232  mov     r14d, 2000h
0x14000c238  mov     qword ptr [rsp+48h+FileOffset], 0
0x14000c241  shr     r8d, 3
0x14000c245  add     r8d, 18h
0x14000c249  mov     eax, [rdi+58h]
0x14000c24c  lea     rbp, [rdi+1F8h]
0x14000c253  test    eax, eax
0x14000c255  mov     dword ptr [rsp+48h+FileOffset+4], 0
0x14000c25d  cmovnz  r14d, eax
0x14000c261  movsxd  rax, edx
0x14000c264  imul    rsi, rax, 0C8h
0x14000c26b  mov     ecx, r14d
0x14000c26e  neg     ecx
0x14000c270  add     rbp, rsi
0x14000c273  and     ecx, r8d
0x14000c276  mov     dword ptr [rsp+48h+FileOffset], ecx
0x14000c27a  cmp     [rsi+rdi+210h], ecx
0x14000c281  jnz     short loc_14000C28E
0x14000c283  cmp     qword ptr [rbp+0], 0
0x14000c288  jnz     loc_14000C351
0x14000c28e  mov     r8d, edx
0x14000c291  mov     [rsi+rdi+210h], ecx
0x14000c298  mov     rdx, rdi
0x14000c29b  call    UdfUnpinCurrentBitmapPage
0x14000c2a0  mov     rcx, [rsi+rdi+1E8h]
0x14000c2a8  lea     rbx, [rdi+200h]
0x14000c2af  add     rbx, rsi
0x14000c2b2  lea     rdx, [rsp+48h+FileOffset]; FileOffset
0x14000c2b7  mov     [rsp+48h+Buffer], rbx; Buffer
0x14000c2bc  mov     r9d, 1; Flags
0x14000c2c2  mov     r8d, r14d; Length
0x14000c2c5  mov     [rsp+48h+Bcb], rbp; Bcb
0x14000c2ca  mov     rcx, [rcx+1F8h]; FileObject
0x14000c2d1  call    cs:__imp_CcPinRead
0x14000c2d8  nop     dword ptr [rax+rax+00h]
0x14000c2dd  mov     rdx, [rbx]; BitMapBuffer
0x14000c2e0  lea     r8d, ds:0[r14*8]
0x14000c2e8  mov     [rsi+rdi+20Ch], r8d
0x14000c2f0  mov     eax, dword ptr [rsp+48h+FileOffset]
0x14000c2f4  lea     ecx, ds:0[rax*8]
0x14000c2fb  mov     [rsi+rdi+208h], ecx
0x14000c302  cmp     dword ptr [rsp+48h+FileOffset], 0
0x14000c307  jnz     short loc_14000C316
0x14000c309  add     rdx, 18h
0x14000c30d  add     r8d, 0FFFFFF40h
0x14000c314  jmp     short loc_14000C323
0x14000c316  add     ecx, 0FFFFFF40h
0x14000c31c  mov     [rsi+rdi+208h], ecx
0x14000c323  mov     eax, [rsi+rdi+298h]
0x14000c32a  sub     eax, ecx
0x14000c32c  lea     rcx, [rdi+218h]
0x14000c333  cmp     r8d, eax
0x14000c336  cmovnb  r8d, eax; SizeOfBitMap
0x14000c33a  add     rcx, rsi; BitMapHeader
0x14000c33d  mov     [rsi+rdi+20Ch], r8d
0x14000c345  call    cs:__imp_RtlInitializeBitMap
0x14000c34c  nop     dword ptr [rax+rax+00h]
0x14000c351  mov     rbx, [rsp+48h+arg_8]
0x14000c356  mov     rbp, [rsp+48h+arg_10]
0x14000c35b  add     rsp, 30h
0x14000c35f  pop     r14
0x14000c361  pop     rdi
0x14000c362  pop     rsi
0x14000c363  retn
```

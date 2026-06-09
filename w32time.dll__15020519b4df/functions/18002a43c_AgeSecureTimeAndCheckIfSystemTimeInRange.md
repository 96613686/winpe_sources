# AgeSecureTimeAndCheckIfSystemTimeInRange

- ea: `0x18002a43c`
- end: `0x18002a646`
- name: `AgeSecureTimeAndCheckIfSystemTimeInRange`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002a3b4`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18002a43c`
- `0x18002a64c`
- `0x18002d0e4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a475`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a475`

## string_xrefs

- `0x18002a5f8`: `Secure Time value is invalid.  Not using it for time comparisons.\n`
- `0x18002a613`: `Secure Time value is of low confidence and cannot be used for time comparisons.\n`

## pseudocode

```c
__int64 __fastcall AgeSecureTimeAndCheckIfSystemTimeInRange(_DWORD *a1, __int64 a2, _DWORD *a3)
{
  ULONGLONG TickCount64; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r8
  ULONGLONG v9; // rcx
  double v10; // xmm0_8
  __int64 v11; // r10
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r9
  unsigned __int64 v14; // r11
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // r11
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  unsigned int v19; // r9d
  unsigned __int64 v21; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp+20h] BYREF

  *a3 = 0;
  if ( !(unsigned int)IsSecureTimeValid(a2) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(1003) )
      FileLogAdd(L"Secure Time value is invalid.  Not using it for time comparisons.\n");
    return 2147500037LL;
  }
  if ( *(_DWORD *)(a2 + 32) < 6u )
  {
    if ( (unsigned __int8)FileLogAllowEntry(1003) )
      FileLogAdd(L"Secure Time value is of low confidence and cannot be used for time comparisons.\n");
    return 2147500037LL;
  }
  TickCount64 = GetTickCount64();
  v7 = *(_QWORD *)(a2 + 8);
  v8 = -1;
  v9 = TickCount64 - *(_QWORD *)a2;
  *(_QWORD *)a2 = TickCount64;
  v10 = (double)(int)v9 * 10000.0;
  v11 = (unsigned int)(int)v10;
  if ( (int)v10 )
  {
    v12 = -1;
    if ( v7 + v11 >= v7 )
      v12 = v7 + v11;
    v13 = -v11;
  }
  else
  {
    v13 = -v11;
    if ( v7 < -v11 )
      v12 = 0;
    else
      v12 = v7 + v11;
  }
  v14 = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 8) = v12;
  if ( (int)v10 )
  {
    v15 = -1;
    if ( v14 + v11 >= v14 )
      v15 = v14 + v11;
  }
  else if ( v14 < v13 )
  {
    v15 = 0;
  }
  else
  {
    v15 = v14 - v13;
  }
  v16 = *(_QWORD *)(a2 + 24);
  *(_QWORD *)(a2 + 16) = v15;
  if ( (int)v10 )
  {
    v17 = -1;
    if ( v16 + v11 >= v16 )
      v17 = v16 + v11;
  }
  else if ( v16 < v13 )
  {
    v17 = 0;
  }
  else
  {
    v17 = v16 - v13;
  }
  *(_QWORD *)(a2 + 24) = v17;
  if ( v12 < 0x7DBA821800LL )
    v18 = 0;
  else
    v18 = v12 - 540000000000LL;
  v21 = v18;
  v19 = a1[1];
  if ( v15 + 540000000000LL >= v15 )
    v8 = v15 + 540000000000LL;
  v22 = v8;
  if ( (__PAIR64__(v19, *a1) >= v18 || (unsigned __int8)FileTimeGreaterThanComparator(a1, &v21))
    && (__PAIR64__(v19, *a1) < v8 || !(unsigned __int8)FileTimeGreaterThanComparator(a1, &v22)) )
  {
    *a3 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a43c  mov     [rsp+arg_0], rbx
0x18002a441  mov     [rsp+arg_8], rsi
0x18002a446  push    rdi
0x18002a447  sub     rsp, 20h
0x18002a44b  mov     rdi, rcx
0x18002a44e  mov     dword ptr [r8], 0
0x18002a455  mov     rcx, rdx
0x18002a458  mov     rsi, r8
0x18002a45b  mov     rbx, rdx
0x18002a45e  call    IsSecureTimeValid
0x18002a463  test    eax, eax
0x18002a465  jz      loc_18002A56B
0x18002a46b  cmp     dword ptr [rbx+20h], 6
0x18002a46f  jb      loc_18002A601
0x18002a475  call    cs:__imp_GetTickCount64
0x18002a47c  nop     dword ptr [rax+rax+00h]
0x18002a481  mov     rdx, [rbx+8]
0x18002a485  xorps   xmm0, xmm0
0x18002a488  mov     rcx, rax
0x18002a48b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a48f  sub     rcx, [rbx]
0x18002a492  mov     [rbx], rax
0x18002a495  cvtsi2sd xmm0, rcx
0x18002a49a  mulsd   xmm0, cs:__real@40c3880000000000
0x18002a4a2  cvttsd2si r10, xmm0
0x18002a4a7  mov     r9, r10
0x18002a4aa  test    r10, r10
0x18002a4ad  jle     loc_18002A58F
0x18002a4b3  lea     rcx, [rdx+r10]
0x18002a4b7  mov     rax, r8
0x18002a4ba  cmp     rcx, rdx
0x18002a4bd  cmovnb  rax, rcx
0x18002a4c1  neg     r9
0x18002a4c4  mov     r11, [rbx+10h]
0x18002a4c8  mov     [rbx+8], rax
0x18002a4cc  test    r10, r10
0x18002a4cf  jle     loc_18002A5A2
0x18002a4d5  lea     rcx, [r11+r10]
0x18002a4d9  mov     rdx, r8
0x18002a4dc  cmp     rcx, r11
0x18002a4df  cmovnb  rdx, rcx
0x18002a4e3  mov     r11, [rbx+18h]
0x18002a4e7  mov     [rbx+10h], rdx
0x18002a4eb  test    r10, r10
0x18002a4ee  jle     loc_18002A5B2
0x18002a4f4  lea     r9, [r11+r10]
0x18002a4f8  mov     rcx, r8
0x18002a4fb  cmp     r9, r11
0x18002a4fe  cmovnb  rcx, r9
0x18002a502  mov     r9, 7DBA821800h
0x18002a50c  mov     [rbx+18h], rcx
0x18002a510  cmp     rax, r9
0x18002a513  jb      loc_18002A5F1
0x18002a519  mov     rcx, 0FFFFFF82457DE800h
0x18002a523  add     rcx, rax
0x18002a526  lea     rax, [rdx+r9]
0x18002a52a  mov     [rsp+28h+arg_10], rcx
0x18002a52f  mov     r9d, [rdi+4]
0x18002a533  cmp     rax, rdx
0x18002a536  cmovnb  r8, rax
0x18002a53a  mov     rax, rcx
0x18002a53d  shr     rax, 20h
0x18002a541  mov     [rsp+28h+arg_18], r8
0x18002a546  cmp     r9d, eax
0x18002a549  jb      loc_18002A62C
0x18002a54f  jz      loc_18002A624
0x18002a555  mov     rax, r8
0x18002a558  shr     rax, 20h
0x18002a55c  cmp     r9d, eax
0x18002a55f  jnb     short loc_18002A5C2
0x18002a561  mov     dword ptr [rsi], 1
0x18002a567  xor     eax, eax
0x18002a569  jmp     short loc_18002A57E
0x18002a56b  mov     ecx, 3EBh
0x18002a570  call    FileLogAllowEntry
0x18002a575  test    al, al
0x18002a577  jnz     short loc_18002A5F8
0x18002a579  mov     eax, 80004005h
0x18002a57e  mov     rbx, [rsp+28h+arg_0]
0x18002a583  mov     rsi, [rsp+28h+arg_8]
0x18002a588  add     rsp, 20h
0x18002a58c  pop     rdi
0x18002a58d  retn
0x18002a58f  neg     r9
0x18002a592  cmp     rdx, r9
0x18002a595  jb      short loc_18002A5DC
0x18002a597  mov     rax, rdx
0x18002a59a  sub     rax, r9
0x18002a59d  jmp     loc_18002A4C4
0x18002a5a2  cmp     r11, r9
0x18002a5a5  jb      short loc_18002A5E3
0x18002a5a7  mov     rdx, r11
0x18002a5aa  sub     rdx, r9
0x18002a5ad  jmp     loc_18002A4E3
0x18002a5b2  cmp     r11, r9
0x18002a5b5  jb      short loc_18002A5EA
0x18002a5b7  mov     rcx, r11
0x18002a5ba  sub     rcx, r9
0x18002a5bd  jmp     loc_18002A502
0x18002a5c2  jnz     short loc_18002A5C9
0x18002a5c4  cmp     [rdi], r8d
0x18002a5c7  jb      short loc_18002A561
0x18002a5c9  lea     rdx, [rsp+28h+arg_18]
0x18002a5ce  mov     rcx, rdi
0x18002a5d1  call    FileTimeGreaterThanComparator
0x18002a5d6  test    al, al
0x18002a5d8  jnz     short loc_18002A567
0x18002a5da  jmp     short loc_18002A561
0x18002a5dc  xor     eax, eax
0x18002a5de  jmp     loc_18002A4C4
0x18002a5e3  xor     edx, edx
0x18002a5e5  jmp     loc_18002A4E3
0x18002a5ea  xor     ecx, ecx
0x18002a5ec  jmp     loc_18002A502
0x18002a5f1  xor     ecx, ecx
0x18002a5f3  jmp     loc_18002A526
0x18002a5f8  lea     rcx, aSecureTimeValu; "Secure Time value is invalid.  Not usin"...
0x18002a5ff  jmp     short loc_18002A61A
0x18002a601  mov     ecx, 3EBh
0x18002a606  call    FileLogAllowEntry
0x18002a60b  test    al, al
0x18002a60d  jz      loc_18002A579
0x18002a613  lea     rcx, aSecureTimeValu_0; "Secure Time value is of low confidence "...
0x18002a61a  call    FileLogAdd
0x18002a61f  jmp     loc_18002A579
0x18002a624  cmp     [rdi], ecx
0x18002a626  jnb     loc_18002A555
0x18002a62c  lea     rdx, [rsp+28h+arg_10]
0x18002a631  mov     rcx, rdi
0x18002a634  call    FileTimeGreaterThanComparator
0x18002a639  test    al, al
0x18002a63b  jz      loc_18002A567
0x18002a641  jmp     loc_18002A555
```

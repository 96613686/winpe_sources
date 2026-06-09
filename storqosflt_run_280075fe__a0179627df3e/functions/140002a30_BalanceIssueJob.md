# BalanceIssueJob

- ea: `0x140002a30`
- end: `0x140002be1`
- name: `BalanceIssueJob`
- size: `433`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400027e0`
- `0x140005384`
- `0x140005414`

## callees

- `0x140002a30`
- `0x140003de0`

## pseudocode

```c
void __fastcall BalanceIssueJob(__int64 a1, __int64 a2)
{
  _QWORD *v4; // r11
  _QWORD *v5; // rdx
  _QWORD *v6; // r9
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // r10
  __int64 v10; // rdi
  __int64 v11; // rdi
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx

  if ( !*(_BYTE *)(a1 + 132) )
  {
    v4 = *(_QWORD **)(a1 + 40);
    v5 = (_QWORD *)v4[17];
    if ( (_QWORD *)*v5 != v4 + 16 )
      __fastfail(3u);
    v6 = (_QWORD *)*v4;
    *(_QWORD *)(a1 + 80) = v4 + 16;
    *(_QWORD *)(a1 + 88) = v5;
    *v5 = a1 + 80;
    v4[17] = a1 + 80;
    v6[117] += *(_QWORD *)(a1 + 152);
    v7 = *(_QWORD *)(a1 + 152);
    *(_BYTE *)(a1 + 131) = 1;
    if ( v7 )
    {
      v8 = v4[20];
      v9 = (unsigned __int64)(v6[123] * v7) / v4[59];
      if ( v9 > 0x3FFFFFFFFFFFFFFFLL )
        v9 = 0x3FFFFFFFFFFFFFFFLL;
      if ( v8 < 0 )
      {
        v11 = v4[20];
        v12 = v6[123] * v6[125] / v4[59];
        v13 = v4[21];
        v14 = v6[118];
        v15 = v12 - v11;
        if ( v12 - v11 > 0x3FFFFFFFFFFFFFFFLL )
          v15 = 0x3FFFFFFFFFFFFFFFLL;
        if ( v14 > v13 && v14 - v13 > 0xEE6B2800 )
          v13 = v14 - 4000000000u;
        v4[21] = v13 + v15;
        v8 = v11 + v15;
      }
      v10 = v4[22];
      v4[20] = v8 - v9;
      if ( v10 > 0 )
      {
        v4[22] = v10 - ((unsigned __int64)((1LL << dword_14000D2A4) - 1 + *(_QWORD *)(a1 + 144)) >> dword_14000D2A4);
        v4[23] += (unsigned __int64)((1LL << dword_14000D2A4) - 1 + *(_QWORD *)(a1 + 144)) >> dword_14000D2A4;
      }
    }
    if ( *(_BYTE *)(a1 + 124) )
      SqospQueueJobForDispatch(a1, a2);
  }
}

```

## disassembly

```asm
0x140002a30  push    rbx
0x140002a32  sub     rsp, 20h
0x140002a36  cmp     byte ptr [rcx+84h], 0
0x140002a3d  mov     rbx, rdx
0x140002a40  mov     r8, rcx
0x140002a43  jnz     loc_140002B02
0x140002a49  mov     r11, [rcx+28h]
0x140002a4d  lea     rcx, [r11+80h]
0x140002a54  mov     rdx, [rcx+8]
0x140002a58  cmp     [rdx], rcx
0x140002a5b  jnz     loc_140002B09
0x140002a61  mov     r9, [r11]
0x140002a64  lea     rax, [r8+50h]
0x140002a68  mov     [rax], rcx
0x140002a6b  mov     [rax+8], rdx
0x140002a6f  mov     [rdx], rax
0x140002a72  mov     [rcx+8], rax
0x140002a76  mov     rax, [r8+98h]
0x140002a7d  add     [r9+3A8h], rax
0x140002a84  mov     rax, [r8+98h]
0x140002a8b  mov     byte ptr [r8+83h], 1
0x140002a93  test    rax, rax
0x140002a96  jz      short loc_140002AF7
0x140002a98  imul    rax, [r9+3D8h]
0x140002aa0  mov     rcx, [r11+0A0h]
0x140002aa7  xor     edx, edx
0x140002aa9  div     qword ptr [r11+1D8h]
0x140002ab0  mov     [rsp+28h+arg_0], rsi
0x140002ab5  mov     rsi, 3FFFFFFFFFFFFFFFh
0x140002abf  cmp     rax, rsi
0x140002ac2  mov     [rsp+28h+arg_8], rdi
0x140002ac7  mov     r10, rax
0x140002aca  cmova   r10, rsi
0x140002ace  test    rcx, rcx
0x140002ad1  js      short loc_140002B10
0x140002ad3  mov     rdi, [r11+0B0h]
0x140002ada  sub     rcx, r10
0x140002add  mov     rsi, [rsp+28h+arg_0]
0x140002ae2  mov     [r11+0A0h], rcx
0x140002ae9  test    rdi, rdi
0x140002aec  jg      loc_140002B80
0x140002af2  mov     rdi, [rsp+28h+arg_8]
0x140002af7  cmp     byte ptr [r8+7Ch], 0
0x140002afc  jnz     loc_140002BD1
0x140002b02  add     rsp, 20h
0x140002b06  pop     rbx
0x140002b07  retn
0x140002b09  mov     ecx, 3
0x140002b0e  int     29h; Win8: RtlFailFast(ecx)
0x140002b10  mov     rax, [r9+3E8h]
0x140002b17  xor     edx, edx
0x140002b19  imul    rax, [r9+3D8h]
0x140002b21  mov     rdi, [r11+0A0h]
0x140002b28  div     qword ptr [r11+1D8h]
0x140002b2f  mov     rcx, [r11+0A8h]
0x140002b36  mov     r9, [r9+3B0h]
0x140002b3d  mov     rdx, rax
0x140002b40  sub     rdx, rdi
0x140002b43  cmp     rdx, rsi
0x140002b46  cmovg   rdx, rsi
0x140002b4a  cmp     r9, rcx
0x140002b4d  jbe     short loc_140002B6C
0x140002b4f  mov     rax, r9
0x140002b52  mov     esi, 0EE6B2800h
0x140002b57  sub     rax, rcx
0x140002b5a  cmp     rax, rsi
0x140002b5d  jbe     short loc_140002B6C
0x140002b5f  mov     rcx, 0FFFFFFFF1194D800h
0x140002b69  add     rcx, r9
0x140002b6c  lea     rax, [rcx+rdx]
0x140002b70  mov     [r11+0A8h], rax
0x140002b77  lea     rcx, [rdi+rdx]
0x140002b7b  jmp     loc_140002AD3
0x140002b80  mov     ecx, cs:dword_14000D2A4
0x140002b86  mov     r10d, 1
0x140002b8c  mov     r9, [r8+90h]
0x140002b93  mov     edx, r10d
0x140002b96  shl     rdx, cl
0x140002b99  dec     rdx
0x140002b9c  add     r9, rdx
0x140002b9f  shr     r9, cl
0x140002ba2  sub     rdi, r9
0x140002ba5  mov     [r11+0B0h], rdi
0x140002bac  mov     ecx, cs:dword_14000D2A4
0x140002bb2  mov     rdx, [r8+90h]
0x140002bb9  shl     r10, cl
0x140002bbc  dec     r10
0x140002bbf  add     rdx, r10
0x140002bc2  shr     rdx, cl
0x140002bc5  add     [r11+0B8h], rdx
0x140002bcc  jmp     loc_140002AF2
0x140002bd1  mov     rdx, rbx
0x140002bd4  mov     rcx, r8
0x140002bd7  call    SqospQueueJobForDispatch
0x140002bdc  jmp     loc_140002B02
```

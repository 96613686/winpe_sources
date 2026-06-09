# CopyForgottenTables

- ea: `0x1800281d0`
- end: `0x18002837f`
- name: `CopyForgottenTables`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800285cc`

## callees

- `0x18000fd44`
- `0x1800134a0`
- `0x180015190`
- `0x1800164a0`
- `0x1800164e0`
- `0x18001d598`
- `0x1800281d0`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall CopyForgottenTables(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v3; // esi
  unsigned __int16 v7; // di
  __int64 v9; // rbx
  unsigned __int16 v10; // r14
  __int64 v11; // rcx
  unsigned __int16 i; // si
  unsigned int v13; // r8d
  _WORD v14[2]; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+44h] [rbp-2Ch] BYREF
  char v16; // [rsp+48h] [rbp-28h]
  int v17; // [rsp+4Ch] [rbp-24h] BYREF
  __int64 v18; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+58h] [rbp-18h]

  v3 = *(_DWORD *)(a2 + 12);
  v18 = 0;
  v19 = 0;
  v15 = 0;
  v16 = 0;
  v14[0] = 0;
  v17 = 0;
  if ( (unsigned __int16)ReadGeneric(
                           (__int64 *)a2,
                           (__int64)&v18,
                           0xCu,
                           (unsigned __int8 *)OFFSET_TABLE_CONTROL,
                           v3,
                           v14) )
    return 1005;
  v7 = WORD2(v18);
  if ( WORD2(v18) > 0x3E8u )
    return 1006;
  v9 = Mem_Alloc(16LL * WORD2(v18));
  if ( !v9 )
    return 1005;
  v10 = ReadGenericRepeat((__int64 *)a2, v9, (unsigned __int8 *)&DIRECTORY_CONTROL, v3 + v14[0], &v17, v7, 0x10u);
  v11 = v9;
  if ( !v10 )
  {
    SortByOffset(v9, v7);
    for ( i = 0; i < v7; ++i )
    {
      if ( *(_DWORD *)(v9 + 16LL * i + 12) )
        break;
      if ( *(_DWORD *)(v9 + 16LL * i + 8) )
        break;
      v13 = *(_DWORD *)(v9 + 16LL * i);
      if ( v13 != 16843009 )
      {
        v16 = 0;
        v15 = HIBYTE(v13) | ((BYTE2(v13) | ((BYTE1(v13) | ((unsigned __int8)v13 << 8)) << 8)) << 8);
        v10 = CopyTableOver((_QWORD *)a2, a1, (__int64)&v15, a3);
        if ( v10 )
          break;
      }
    }
    v11 = v9;
  }
  Mem_Free(v11);
  return v10;
}

```

## disassembly

```asm
0x1800281d0  mov     [rsp-38h+arg_18], rbx
0x1800281d5  push    rbp
0x1800281d6  push    rsi
0x1800281d7  push    rdi
0x1800281d8  push    r12
0x1800281da  push    r13
0x1800281dc  push    r14
0x1800281de  push    r15
0x1800281e0  mov     rbp, rsp
0x1800281e3  sub     rsp, 70h
0x1800281e7  mov     rax, cs:__security_cookie
0x1800281ee  xor     rax, rsp
0x1800281f1  mov     [rbp+var_10], rax
0x1800281f5  mov     esi, [rdx+0Ch]
0x1800281f8  lea     r9, OFFSET_TABLE_CONTROL
0x1800281ff  xor     eax, eax
0x180028201  mov     r15, rdx
0x180028204  mov     r13, r8
0x180028207  mov     [rbp+var_20], rax
0x18002820b  mov     [rbp+var_18], eax
0x18002820e  lea     rdx, [rbp+var_20]
0x180028212  mov     [rbp+var_2C], eax
0x180028215  mov     r12, rcx
0x180028218  lea     r8d, [rax+0Ch]
0x18002821c  mov     [rbp+var_28], al
0x18002821f  lea     rax, [rbp+var_30]
0x180028223  xor     r14d, r14d
0x180028226  mov     [rsp+70h+var_48], rax
0x18002822b  mov     rcx, r15
0x18002822e  mov     dword ptr [rsp+70h+var_50], esi
0x180028232  mov     [rbp+var_30], r14w
0x180028237  mov     [rbp+var_24], r14d
0x18002823b  call    ReadGeneric
0x180028240  test    ax, ax
0x180028243  jnz     loc_180028356
0x180028249  movzx   edi, word ptr [rbp+var_20+4]
0x18002824d  mov     eax, 3E8h
0x180028252  cmp     di, ax
0x180028255  jbe     short loc_180028261
0x180028257  mov     eax, 3EEh
0x18002825c  jmp     loc_18002835B
0x180028261  mov     rcx, rdi
0x180028264  shl     rcx, 4; Size
0x180028268  call    Mem_Alloc
0x18002826d  mov     rbx, rax
0x180028270  test    rax, rax
0x180028273  jz      loc_180028356
0x180028279  movzx   r9d, [rbp+var_30]
0x18002827e  lea     rax, [rbp+var_24]
0x180028282  mov     [rsp+70h+var_40], 10h
0x180028289  lea     r8, DIRECTORY_CONTROL
0x180028290  add     r9d, esi
0x180028293  mov     word ptr [rsp+70h+var_48], di
0x180028298  mov     rdx, rbx
0x18002829b  mov     [rsp+70h+var_50], rax
0x1800282a0  mov     rcx, r15
0x1800282a3  call    ReadGenericRepeat
0x1800282a8  movzx   r14d, ax
0x1800282ac  mov     rcx, rbx
0x1800282af  test    ax, ax
0x1800282b2  jz      short loc_1800282C2
0x1800282b4  call    Mem_Free
0x1800282b9  movzx   eax, r14w
0x1800282bd  jmp     loc_18002835B
0x1800282c2  movzx   edx, di
0x1800282c5  call    SortByOffset
0x1800282ca  xor     r9d, r9d
0x1800282cd  mov     esi, r9d
0x1800282d0  cmp     r9w, di
0x1800282d4  jnb     short loc_18002834E
0x1800282d6  movzx   eax, si
0x1800282d9  add     rax, rax
0x1800282dc  cmp     [rbx+rax*8+0Ch], r9d
0x1800282e1  jnz     short loc_18002834E
0x1800282e3  cmp     [rbx+rax*8+8], r9d
0x1800282e8  jnz     short loc_18002834E
0x1800282ea  mov     r8d, [rbx+rax*8]
0x1800282ee  cmp     r8d, 1010101h
0x1800282f5  jz      short loc_180028346
0x1800282f7  movzx   edx, r8b
0x1800282fb  mov     ecx, r8d
0x1800282fe  shl     edx, 8
0x180028301  mov     eax, r8d
0x180028304  shr     eax, 8
0x180028307  movzx   eax, al
0x18002830a  or      edx, eax
0x18002830c  shr     ecx, 10h
0x18002830f  shl     edx, 8
0x180028312  movzx   eax, cl
0x180028315  mov     rcx, r15
0x180028318  or      edx, eax
0x18002831a  shr     r8d, 18h
0x18002831e  shl     edx, 8
0x180028321  or      edx, r8d
0x180028324  mov     [rbp+var_28], r9b
0x180028328  mov     [rbp+var_2C], edx
0x18002832b  lea     r8, [rbp+var_2C]
0x18002832f  mov     rdx, r12
0x180028332  mov     r9, r13
0x180028335  call    CopyTableOver
0x18002833a  xor     r9d, r9d
0x18002833d  movzx   r14d, ax
0x180028341  test    ax, ax
0x180028344  jnz     short loc_18002834E
0x180028346  inc     si
0x180028349  cmp     si, di
0x18002834c  jb      short loc_1800282D6
0x18002834e  mov     rcx, rbx
0x180028351  jmp     loc_1800282B4
0x180028356  mov     eax, 3EDh
0x18002835b  mov     rcx, [rbp+var_10]
0x18002835f  xor     rcx, rsp; StackCookie
0x180028362  call    __security_check_cookie
0x180028367  mov     rbx, [rsp+70h+arg_18]
0x18002836f  add     rsp, 70h
0x180028373  pop     r15
0x180028375  pop     r14
0x180028377  pop     r13
0x180028379  pop     r12
0x18002837b  pop     rdi
0x18002837c  pop     rsi
0x18002837d  pop     rbp
0x18002837e  retn
```

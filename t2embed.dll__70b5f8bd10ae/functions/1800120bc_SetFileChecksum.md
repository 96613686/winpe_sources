# SetFileChecksum

- ea: `0x1800120bc`
- end: `0x1800121dd`
- name: `SetFileChecksum`
- size: `289`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180016770`
- `0x18001b538`
- `0x1800285cc`

## callees

- `0x180011640`
- `0x1800120bc`
- `0x1800134b4`
- `0x180015190`
- `0x180017de0`
- `0x18002a590`

## pseudocode

```c
__int16 __fastcall SetFileChecksum(__int64 *a1, unsigned int a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  _WORD v7[2]; // [rsp+30h] [rbp-50h] BYREF
  int v8; // [rsp+34h] [rbp-4Ch] BYREF
  _OWORD v9[3]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v10; // [rsp+68h] [rbp-18h]

  v8 = 0;
  memset(v9, 0, sizeof(v9));
  v10 = 0;
  v7[0] = 0;
  v4 = TTTableOffset(a1, "head");
  v5 = v4;
  if ( v4 )
  {
    LOWORD(v4) = ReadGeneric(a1, (__int64)v9, 0x36u, (unsigned __int8 *)HEAD_CONTROL, v4, v7);
    if ( !(_WORD)v4 )
    {
      DWORD2(v9[0]) = 0;
      LOWORD(v4) = WriteGeneric((__int64)a1, (__int64)v9, 0x36u, (unsigned __int8 *)HEAD_CONTROL, v5, v7);
      if ( !(_WORD)v4 )
      {
        LOWORD(v4) = CalcChecksum(a1, 0, a2, &v8);
        if ( !(_WORD)v4 )
        {
          DWORD2(v9[0]) = -1313820742 - v8;
          LOWORD(v4) = WriteGeneric((__int64)a1, (__int64)v9, 0x36u, (unsigned __int8 *)HEAD_CONTROL, v5, v7);
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800120bc  mov     [rsp-18h+arg_10], rbx
0x1800120c1  mov     [rsp-18h+arg_18], rsi
0x1800120c6  push    rbp
0x1800120c7  push    rdi
0x1800120c8  push    r14
0x1800120ca  mov     rbp, rsp
0x1800120cd  sub     rsp, 80h
0x1800120d4  mov     rax, cs:__security_cookie
0x1800120db  xor     rax, rsp
0x1800120de  mov     [rbp+var_10], rax
0x1800120e2  xorps   xmm0, xmm0
0x1800120e5  mov     esi, edx
0x1800120e7  xor     r14d, r14d
0x1800120ea  lea     rdx, aHead; "head"
0x1800120f1  xor     eax, eax
0x1800120f3  mov     [rbp+var_4C], r14d
0x1800120f7  movups  [rbp+var_48], xmm0
0x1800120fb  mov     [rbp+var_18], rax
0x1800120ff  mov     rbx, rcx
0x180012102  movups  [rbp+var_38], xmm0
0x180012106  mov     [rbp+var_50], r14w
0x18001210b  movups  [rbp+var_28], xmm0
0x18001210f  call    TTTableOffset
0x180012114  mov     edi, eax
0x180012116  test    eax, eax
0x180012118  jz      short loc_180012170
0x18001211a  lea     rax, [rbp+var_50]
0x18001211e  mov     rcx, rbx
0x180012121  mov     [rsp+80h+var_58], rax
0x180012126  lea     r8d, [r14+36h]
0x18001212a  lea     r9, HEAD_CONTROL
0x180012131  mov     [rsp+80h+var_60], edi
0x180012135  lea     rdx, [rbp+var_48]
0x180012139  call    ReadGeneric
0x18001213e  test    ax, ax
0x180012141  jnz     short loc_180012170
0x180012143  lea     rax, [rbp+var_50]
0x180012147  mov     dword ptr [rbp+var_48+8], r14d
0x18001214b  mov     [rsp+80h+var_58], rax
0x180012150  lea     r8d, [r14+36h]
0x180012154  lea     r9, HEAD_CONTROL
0x18001215b  mov     [rsp+80h+var_60], edi
0x18001215f  lea     rdx, [rbp+var_48]
0x180012163  mov     rcx, rbx
0x180012166  call    WriteGeneric
0x18001216b  test    ax, ax
0x18001216e  jz      short loc_180012194
0x180012170  mov     rcx, [rbp+var_10]
0x180012174  xor     rcx, rsp; StackCookie
0x180012177  call    __security_check_cookie
0x18001217c  lea     r11, [rsp+80h+var_s0]
0x180012184  mov     rbx, [r11+30h]
0x180012188  mov     rsi, [r11+38h]
0x18001218c  mov     rsp, r11
0x18001218f  pop     r14
0x180012191  pop     rdi
0x180012192  pop     rbp
0x180012193  retn
0x180012194  lea     r9, [rbp+var_4C]
0x180012198  mov     r8d, esi
0x18001219b  xor     edx, edx
0x18001219d  mov     rcx, rbx
0x1800121a0  call    CalcChecksum
0x1800121a5  test    ax, ax
0x1800121a8  jnz     short loc_180012170
0x1800121aa  mov     eax, 0B1B0AFBAh
0x1800121af  lea     r9, HEAD_CONTROL
0x1800121b6  sub     eax, [rbp+var_4C]
0x1800121b9  lea     rdx, [rbp+var_48]
0x1800121bd  mov     dword ptr [rbp+var_48+8], eax
0x1800121c0  mov     r8d, 36h ; '6'
0x1800121c6  lea     rax, [rbp+var_50]
0x1800121ca  mov     rcx, rbx
0x1800121cd  mov     [rsp+80h+var_58], rax
0x1800121d2  mov     [rsp+80h+var_60], edi
0x1800121d6  call    WriteGeneric
0x1800121db  jmp     short loc_180012170
```

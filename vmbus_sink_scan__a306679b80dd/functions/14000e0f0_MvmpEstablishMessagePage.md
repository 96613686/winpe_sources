# MvmpEstablishMessagePage

- ea: `0x14000e0f0`
- end: `0x14000e30e`
- name: `MvmpEstablishMessagePage`
- size: `542`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d300`
- `0x14000d410`
- `0x14000d620`
- `0x14000d704`
- `0x14000d910`
- `0x14000da50`

## callees

- `0x14000b350`
- `0x14000e0f0`
- `0x14000e314`
- `0x14000eaa8`

## pseudocode

```c
char __fastcall MvmpEstablishMessagePage(__int64 a1, __int64 a2, char a3)
{
  int v6; // ebp
  __int64 VpRegister; // rbx
  __int64 v9; // rax
  bool v10; // zf
  __int64 v11; // rdi
  int v12; // ebx
  unsigned int v13; // ecx
  int v14; // ebx
  unsigned int v15; // ebp
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rdx
  int v20; // eax

  if ( a3 )
  {
    v6 = 5;
    while ( 1 )
    {
      VpRegister = MvmpGetVpRegister(a1, 0, (unsigned int)(v6 + 1073741968), 1);
      if ( (VpRegister & 0x10000) != 0 )
        break;
      if ( (unsigned int)++v6 >= 0x10 )
      {
        if ( v6 != 16 )
          break;
        *(_DWORD *)(a1 + 208) = 6;
        return 0;
      }
    }
  }
  else
  {
    v6 = 2;
    VpRegister = MvmpGetVpRegister(a1, 0, 1073741970, 1);
  }
  v9 = MvmpGetVpRegister(a1, a2, 1073741955, 2);
  v10 = *(_QWORD *)(a1 + 40) == 0;
  v11 = v9;
  *(_QWORD *)(a1 + 200) = v9;
  if ( !v10 || (v9 & 1) != 0 )
  {
    v10 = *(_BYTE *)(a1 + 184) == 0;
    *(_QWORD *)(a1 + 96) = VpRegister;
    *(_DWORD *)(a1 + 92) = v6;
    if ( v10 )
      v12 = VpRegister & 0xFFFDFF00 | 0x20031;
    else
      v12 = VpRegister & 0xFFF9FFFF | 0x40000;
    v13 = v12 & 0xFFEFFFFF;
    v14 = v12 | 0x100000;
    v15 = v6 + 1073741968;
    if ( *(_DWORD *)(a1 + 216) != 2 )
      v14 = v13;
    MvmpSetVpRegister(a1, 0, v15, v14 & 0xFFFEFFFF, 1);
    if ( *(_DWORD *)(a1 + 216) == 2 )
    {
      v16 = MvmpGetVpRegister(a1, a2, v15, 0);
      *(_QWORD *)(a1 + 192) = v16;
      MvmpSetVpRegister(a1, a2, v15, v16 & 0xFFF8FFFF | 0x40000, 0);
    }
    if ( *(_BYTE *)(a1 + 185) || (v11 & 1) != 0 && (a3 || !*(_QWORD *)(a1 + 40)) )
    {
      if ( *(_BYTE *)(a1 + 189) )
      {
        if ( *(_QWORD *)(a1 + 32) )
        {
LABEL_30:
          MvmpSetVpRegister(a1, a2, 1073741955, v11 | 1, 2);
          v20 = MvmpGetVpRegister(a1, a2, 1073741952, 2);
          if ( (v20 & 1) == 0 )
            MvmpSetVpRegister(a1, a2, 1073741952, v20 | 1, 2);
          return 1;
        }
        v18 = *(_QWORD *)(a1 + 56);
        v19 = *(_QWORD *)(a1 + 80);
      }
      else
      {
        v18 = 0;
        v19 = 0;
      }
      v17 = MvmMapPage(v11 & 0xFFFFFFFFFFFFF000uLL, v19, v18);
    }
    else
    {
      v11 ^= (*(_QWORD *)(a1 + 48) ^ v11) & 0xFFFFFFFFFFFFF000uLL;
      v17 = *(_QWORD *)(a1 + 40);
    }
    *(_QWORD *)(a1 + 32) = v17;
    goto LABEL_30;
  }
  *(_DWORD *)(a1 + 208) = 7;
  return 0;
}

```

## disassembly

```asm
0x14000e0f0  push    rbx
0x14000e0f2  push    rbp
0x14000e0f3  push    rsi
0x14000e0f4  push    rdi
0x14000e0f5  push    r13
0x14000e0f7  push    r14
0x14000e0f9  push    r15
0x14000e0fb  sub     rsp, 30h
0x14000e0ff  mov     r15b, r8b
0x14000e102  mov     r14, rdx
0x14000e105  mov     rsi, rcx
0x14000e108  mov     r13d, 2
0x14000e10e  test    r8b, r8b
0x14000e111  jz      short loc_14000E150
0x14000e113  lea     ebp, [r13+3]
0x14000e117  xor     edx, edx
0x14000e119  lea     r8d, [rbp+40000090h]
0x14000e120  mov     rcx, rsi
0x14000e123  lea     r9d, [rdx+1]
0x14000e127  call    MvmpGetVpRegister
0x14000e12c  mov     rbx, rax
0x14000e12f  bt      rax, 10h
0x14000e134  jb      short loc_14000E167
0x14000e136  inc     ebp
0x14000e138  cmp     ebp, 10h
0x14000e13b  jb      short loc_14000E117
0x14000e13d  jnz     short loc_14000E167
0x14000e13f  mov     dword ptr [rsi+0D0h], 6
0x14000e149  xor     al, al
0x14000e14b  jmp     loc_14000E2FE
0x14000e150  xor     edx, edx
0x14000e152  mov     r8d, 40000092h
0x14000e158  mov     ebp, r13d
0x14000e15b  lea     r9d, [rdx+1]
0x14000e15f  call    MvmpGetVpRegister
0x14000e164  mov     rbx, rax
0x14000e167  mov     r9d, r13d
0x14000e16a  mov     r8d, 40000083h
0x14000e170  mov     rdx, r14
0x14000e173  mov     rcx, rsi
0x14000e176  call    MvmpGetVpRegister
0x14000e17b  cmp     qword ptr [rsi+28h], 0
0x14000e180  mov     rdi, rax
0x14000e183  mov     [rsi+0C8h], rax
0x14000e18a  jnz     short loc_14000E19E
0x14000e18c  test    dil, 1
0x14000e190  jnz     short loc_14000E19E
0x14000e192  mov     dword ptr [rsi+0D0h], 7
0x14000e19c  jmp     short loc_14000E149
0x14000e19e  cmp     byte ptr [rsi+0B8h], 0
0x14000e1a5  mov     [rsi+60h], rbx
0x14000e1a9  mov     [rsi+5Ch], ebp
0x14000e1ac  jz      short loc_14000E1BA
0x14000e1ae  btr     rbx, 11h
0x14000e1b3  bts     rbx, 12h
0x14000e1b8  jmp     short loc_14000E1C8
0x14000e1ba  and     rbx, 0FFFFFFFFFFFFFF31h
0x14000e1c1  or      rbx, 20031h
0x14000e1c8  mov     rcx, rbx
0x14000e1cb  mov     [rsp+68h+var_48], 1
0x14000e1d3  btr     rcx, 14h
0x14000e1d8  bts     rbx, 14h
0x14000e1dd  add     ebp, 40000090h
0x14000e1e3  cmp     [rsi+0D8h], r13d
0x14000e1ea  mov     r8d, ebp
0x14000e1ed  cmovnz  rbx, rcx
0x14000e1f1  xor     edx, edx
0x14000e1f3  btr     rbx, 10h
0x14000e1f8  mov     rcx, rsi
0x14000e1fb  mov     r9, rbx
0x14000e1fe  call    MvmpSetVpRegister
0x14000e203  cmp     [rsi+0D8h], r13d
0x14000e20a  jnz     short loc_14000E248
0x14000e20c  xor     r9d, r9d
0x14000e20f  mov     r8d, ebp
0x14000e212  mov     rdx, r14
0x14000e215  mov     rcx, rsi
0x14000e218  call    MvmpGetVpRegister
0x14000e21d  mov     [rsi+0C0h], rax
0x14000e224  mov     r8d, ebp
0x14000e227  and     rax, 0FFFFFFFFFFFCFFFFh
0x14000e22d  mov     [rsp+68h+var_48], 0
0x14000e235  bts     rax, 12h
0x14000e23a  mov     rdx, r14
0x14000e23d  mov     r9, rax
0x14000e240  mov     rcx, rsi
0x14000e243  call    MvmpSetVpRegister
0x14000e248  cmp     byte ptr [rsi+0B9h], 0
0x14000e24f  jnz     short loc_14000E279
0x14000e251  test    dil, 1
0x14000e255  jz      short loc_14000E263
0x14000e257  test    r15b, r15b
0x14000e25a  jnz     short loc_14000E279
0x14000e25c  cmp     qword ptr [rsi+28h], 0
0x14000e261  jz      short loc_14000E279
0x14000e263  mov     rax, rdi
0x14000e266  xor     rax, [rsi+30h]
0x14000e26a  and     rax, 0FFFFFFFFFFFFF000h
0x14000e270  xor     rdi, rax
0x14000e273  mov     rax, [rsi+28h]
0x14000e277  jmp     short loc_14000E2A7
0x14000e279  mov     rcx, rdi
0x14000e27c  and     rcx, 0FFFFFFFFFFFFF000h
0x14000e283  cmp     byte ptr [rsi+0BDh], 0
0x14000e28a  jnz     short loc_14000E293
0x14000e28c  xor     r8d, r8d
0x14000e28f  xor     edx, edx
0x14000e291  jmp     short loc_14000E2A2
0x14000e293  cmp     qword ptr [rsi+20h], 0
0x14000e298  jnz     short loc_14000E2AB
0x14000e29a  mov     r8, [rsi+38h]
0x14000e29e  mov     rdx, [rsi+50h]
0x14000e2a2  call    MvmMapPage
0x14000e2a7  mov     [rsi+20h], rax
0x14000e2ab  or      rdi, 1
0x14000e2af  mov     [rsp+68h+var_48], r13d
0x14000e2b4  mov     r9, rdi
0x14000e2b7  mov     r8d, 40000083h
0x14000e2bd  mov     rdx, r14
0x14000e2c0  mov     rcx, rsi
0x14000e2c3  call    MvmpSetVpRegister
0x14000e2c8  mov     ebx, 40000080h
0x14000e2cd  mov     r9d, r13d
0x14000e2d0  mov     r8d, ebx
0x14000e2d3  mov     rdx, r14
0x14000e2d6  mov     rcx, rsi
0x14000e2d9  call    MvmpGetVpRegister
0x14000e2de  test    al, 1
0x14000e2e0  jnz     short loc_14000E2FC
0x14000e2e2  or      rax, 1
0x14000e2e6  mov     [rsp+68h+var_48], r13d
0x14000e2eb  mov     r9, rax
0x14000e2ee  mov     r8d, ebx
0x14000e2f1  mov     rdx, r14
0x14000e2f4  mov     rcx, rsi
0x14000e2f7  call    MvmpSetVpRegister
0x14000e2fc  mov     al, 1
0x14000e2fe  add     rsp, 30h
0x14000e302  pop     r15
0x14000e304  pop     r14
0x14000e306  pop     r13
0x14000e308  pop     rdi
0x14000e309  pop     rsi
0x14000e30a  pop     rbp
0x14000e30b  pop     rbx
0x14000e30c  retn
```

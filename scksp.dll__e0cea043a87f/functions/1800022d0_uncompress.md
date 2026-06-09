# uncompress

- ea: `0x1800022d0`
- end: `0x180002440`
- name: `uncompress`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180036d3c`

## callees

- `0x1800022d0`
- `0x180002450`
- `0x180003ce0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall uncompress(char *a1, _DWORD *a2, unsigned __int8 *a3, unsigned int a4)
{
  unsigned __int64 v4; // r14
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebx
  char *v8; // rbp
  int v9; // eax
  unsigned __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r15
  unsigned __int8 *v15; // [rsp+20h] [rbp-88h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-80h]
  char *v17; // [rsp+30h] [rbp-78h]
  int i; // [rsp+38h] [rbp-70h]
  __int64 v19; // [rsp+50h] [rbp-58h]
  __int64 v20; // [rsp+58h] [rbp-50h]
  __int64 v21; // [rsp+60h] [rbp-48h]
  char v22; // [rsp+70h] [rbp-38h] BYREF

  v4 = (unsigned int)*a2;
  v6 = a4;
  if ( (!a4 || a3) && (!*a2 || a1) )
  {
    if ( *a2 )
    {
      v8 = a1;
    }
    else
    {
      v8 = &v22;
      if ( a1 )
        v8 = a1;
    }
    v15 = a3;
    v16 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v7 = inflateInit_(&v15, "1.3.2", 88);
    if ( !v7 )
    {
      v9 = 0;
      v17 = v8;
      v10 = v4;
      for ( i = 0; ; v9 = i )
      {
        if ( !v9 )
        {
          v11 = (unsigned int)v10;
          if ( v10 > 0xFFFFFFFF )
            v11 = 0xFFFFFFFFLL;
          i = v11;
          v10 -= v11;
        }
        if ( !v16 )
        {
          v12 = (unsigned int)v6;
          if ( v6 > 0xFFFFFFFF )
            v12 = 0xFFFFFFFFLL;
          v16 = v12;
          v6 -= v12;
        }
        v7 = inflate(&v15, 0);
        if ( v7 )
          break;
      }
      v13 = v16;
      LODWORD(v4) = v4 - (v10 + i);
      inflateEnd(&v15);
      if ( v7 == 1 )
      {
        v7 = 0;
      }
      else if ( v7 == 2 || v7 == -5 && !(v13 + v6) )
      {
        v7 = -3;
      }
    }
  }
  else
  {
    v7 = -2;
  }
  *a2 = v4;
  return v7;
}

```

## disassembly

```asm
0x1800022d0  push    rbx
0x1800022d2  push    rsi
0x1800022d3  push    r12
0x1800022d5  push    r14
0x1800022d7  sub     rsp, 88h
0x1800022de  mov     r14d, [rdx]
0x1800022e1  mov     r12, rdx
0x1800022e4  mov     esi, r9d
0x1800022e7  test    r9d, r9d
0x1800022ea  jz      short loc_1800022F1
0x1800022ec  test    r8, r8
0x1800022ef  jz      short loc_1800022FB
0x1800022f1  test    r14, r14
0x1800022f4  jz      short loc_180002305
0x1800022f6  test    rcx, rcx
0x1800022f9  jnz     short loc_180002305
0x1800022fb  mov     ebx, 0FFFFFFFEh
0x180002300  jmp     loc_18000242C
0x180002305  mov     [rsp+0A8h+arg_0], rbp
0x18000230d  mov     [rsp+0A8h+arg_10], r13
0x180002315  test    r14, r14
0x180002318  jnz     short loc_180002328
0x18000231a  test    rcx, rcx
0x18000231d  lea     rbp, [rsp+0A8h+var_38]
0x180002322  cmovnz  rbp, rcx
0x180002326  jmp     short loc_18000232B
0x180002328  mov     rbp, rcx
0x18000232b  xor     r13d, r13d
0x18000232e  mov     [rsp+0A8h+var_88], r8
0x180002333  mov     r8d, 58h ; 'X'
0x180002339  mov     [rsp+0A8h+var_80], r13d
0x18000233e  lea     rdx, a132; "1.3.2"
0x180002345  mov     [rsp+0A8h+var_58], r13
0x18000234a  lea     rcx, [rsp+0A8h+var_88]
0x18000234f  mov     [rsp+0A8h+var_50], r13
0x180002354  mov     [rsp+0A8h+var_48], r13
0x180002359  call    inflateInit_
0x18000235e  mov     ebx, eax
0x180002360  test    eax, eax
0x180002362  jnz     loc_18000241C
0x180002368  mov     [rsp+0A8h+arg_8], rdi
0x180002370  mov     eax, r13d
0x180002373  mov     [rsp+0A8h+var_78], rbp
0x180002378  mov     rdi, r14
0x18000237b  mov     [rsp+0A8h+var_70], eax
0x18000237f  mov     ebp, 0FFFFFFFFh
0x180002384  mov     [rsp+0A8h+var_28], r15
0x18000238c  nop     dword ptr [rax+00h]
0x180002390  test    eax, eax
0x180002392  jnz     short loc_1800023A3
0x180002394  cmp     rdi, rbp
0x180002397  mov     eax, edi
0x180002399  cmova   eax, ebp
0x18000239c  mov     [rsp+0A8h+var_70], eax
0x1800023a0  sub     rdi, rax
0x1800023a3  cmp     [rsp+0A8h+var_80], r13d
0x1800023a8  jnz     short loc_1800023B9
0x1800023aa  cmp     rsi, rbp
0x1800023ad  mov     eax, esi
0x1800023af  cmova   eax, ebp
0x1800023b2  mov     [rsp+0A8h+var_80], eax
0x1800023b6  sub     rsi, rax
0x1800023b9  xor     edx, edx
0x1800023bb  lea     rcx, [rsp+0A8h+var_88]
0x1800023c0  call    inflate
0x1800023c5  mov     ebx, eax
0x1800023c7  test    eax, eax
0x1800023c9  jnz     short loc_1800023D1
0x1800023cb  mov     eax, [rsp+0A8h+var_70]
0x1800023cf  jmp     short loc_180002390
0x1800023d1  mov     eax, [rsp+0A8h+var_70]
0x1800023d5  lea     rcx, [rsp+0A8h+var_88]
0x1800023da  mov     r15d, [rsp+0A8h+var_80]
0x1800023df  add     rax, rdi
0x1800023e2  sub     r14, rax
0x1800023e5  call    inflateEnd
0x1800023ea  mov     rdi, [rsp+0A8h+arg_8]
0x1800023f2  cmp     ebx, 1
0x1800023f5  jnz     short loc_1800023FC
0x1800023f7  mov     ebx, r13d
0x1800023fa  jmp     short loc_180002414
0x1800023fc  cmp     ebx, 2
0x1800023ff  jz      short loc_18000240F
0x180002401  cmp     ebx, 0FFFFFFFBh
0x180002404  jnz     short loc_180002414
0x180002406  lea     rax, [r15+rsi]
0x18000240a  test    rax, rax
0x18000240d  jnz     short loc_180002414
0x18000240f  mov     ebx, 0FFFFFFFDh
0x180002414  mov     r15, [rsp+0A8h+var_28]
0x18000241c  mov     rbp, [rsp+0A8h+arg_0]
0x180002424  mov     r13, [rsp+0A8h+arg_10]
0x18000242c  mov     [r12], r14d
0x180002430  mov     eax, ebx
0x180002432  add     rsp, 88h
0x180002439  pop     r14
0x18000243b  pop     r12
0x18000243d  pop     rsi
0x18000243e  pop     rbx
0x18000243f  retn
```

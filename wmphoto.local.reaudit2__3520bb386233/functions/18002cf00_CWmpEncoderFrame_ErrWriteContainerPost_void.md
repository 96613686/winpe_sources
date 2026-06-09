# CWmpEncoderFrame::ErrWriteContainerPost(void)

- ea: `0x18002cf00`
- end: `0x18002d192`
- name: `?ErrWriteContainerPost@CWmpEncoderFrame@@IEAAJXZ`
- size: `658`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180029930`
- `0x18002c260`

## callees

- `0x18002cf00`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::ErrWriteContainerPost(CWmpEncoderFrame *this)
{
  char *v1; // rsi
  __int64 (__fastcall *v3)(char *, __int64 *); // rax
  int v4; // ebx
  int v5; // r14d
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  __int64 result; // rax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int128 v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-20h]
  __int128 v17; // [rsp+48h] [rbp-18h] BYREF
  __int64 v18; // [rsp+58h] [rbp-8h]
  __int64 v19; // [rsp+90h] [rbp+30h] BYREF
  __int64 v20; // [rsp+98h] [rbp+38h] BYREF

  v1 = (char *)this + 152;
  v3 = (__int64 (__fastcall *)(char *, __int64 *))*((_QWORD *)this + 31);
  v4 = 0;
  v19 = 0;
  v20 = 0;
  v5 = v3((char *)this + 152, &v20);
  if ( v5 >= 0 )
  {
    v6 = *((_QWORD *)this + 8317);
    v18 = 0;
    v16 = 0;
    v17 = 0;
    WORD4(v17) = -17216;
    v7 = *((_DWORD *)this + 32);
    v15 = 0;
    DWORD2(v15) = v7;
    LOWORD(v17) = 18;
    LOWORD(v15) = 19;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v6 + 72LL))(v6, 0, &v17, &v15);
    if ( v4 >= 0 )
    {
      v8 = *((_QWORD *)this + 8317);
      v18 = 0;
      v16 = 0;
      v17 = 0;
      LOWORD(v17) = 18;
      WORD4(v17) = -17215;
      v9 = *((_DWORD *)this + 33);
      v15 = 0;
      DWORD2(v15) = v9;
      LOWORD(v15) = 19;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v8 + 72LL))(
             v8,
             0,
             &v17,
             &v15);
      if ( v4 >= 0 )
      {
        if ( !*((_BYTE *)this + 96) )
          goto LABEL_20;
        v11 = *((_QWORD *)this + 8317);
        v18 = 0;
        v16 = 0;
        v17 = 0;
        LOWORD(v17) = 18;
        WORD4(v17) = -17214;
        v12 = *((_DWORD *)this + 34);
        v15 = 0;
        DWORD2(v15) = v12;
        LOWORD(v15) = 19;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v11 + 72LL))(
               v11,
               0,
               &v17,
               &v15);
        if ( v4 >= 0 )
        {
          v13 = *((_QWORD *)this + 8317);
          v18 = 0;
          v16 = 0;
          v17 = 0;
          LOWORD(v17) = 18;
          WORD4(v17) = -17213;
          v14 = *((_DWORD *)this + 35);
          v15 = 0;
          DWORD2(v15) = v14;
          LOWORD(v15) = 19;
          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v13 + 72LL))(
                 v13,
                 0,
                 &v17,
                 &v15);
          if ( v4 >= 0 )
          {
LABEL_20:
            v5 = (*((__int64 (__fastcall **)(char *, _QWORD))v1 + 11))(v1, *((unsigned int *)this + 16629));
            if ( v5 >= 0 )
            {
              v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 8317))(
                     *((_QWORD *)this + 8317),
                     &IID_IPersistStream,
                     &v19);
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v19 + 48LL))(
                       v19,
                       *(_QWORD *)v1,
                       1);
                if ( v4 >= 0 )
                {
                  v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 8317) + 40LL))(
                         *((_QWORD *)this + 8317),
                         (char *)this + 66520);
                  if ( v4 >= 0 )
                    v5 = (*((__int64 (__fastcall **)(char *, __int64))v1 + 11))(v1, v20);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  result = 0xFFFFFFFFLL;
  if ( !v4 )
    return (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x18002cf00  mov     [rsp-28h+arg_10], rbx
0x18002cf05  mov     [rsp-28h+arg_18], rsi
0x18002cf0a  push    rbp
0x18002cf0b  push    rdi
0x18002cf0c  push    r12
0x18002cf0e  push    r13
0x18002cf10  push    r14
0x18002cf12  mov     rbp, rsp
0x18002cf15  sub     rsp, 60h
0x18002cf19  lea     rsi, [rcx+98h]
0x18002cf20  mov     rdi, rcx
0x18002cf23  mov     rax, [rsi+60h]
0x18002cf27  lea     rdx, [rbp+arg_8]
0x18002cf2b  xor     ebx, ebx
0x18002cf2d  mov     rcx, rsi
0x18002cf30  mov     [rbp+arg_0], rbx
0x18002cf34  mov     [rbp+arg_8], rbx
0x18002cf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf3d  mov     r14d, eax
0x18002cf40  test    eax, eax
0x18002cf42  js      loc_18002D021
0x18002cf48  mov     rcx, [rdi+103E8h]
0x18002cf4f  lea     r12d, [rbx+12h]
0x18002cf53  xor     eax, eax
0x18002cf55  lea     r13d, [rbx+13h]
0x18002cf59  mov     [rbp+var_8], rax
0x18002cf5d  lea     r9, [rbp+var_30]
0x18002cf61  mov     [rbp+var_20], rax
0x18002cf65  lea     r8, [rbp+var_18]
0x18002cf69  mov     eax, 0BCC0h
0x18002cf6e  xorps   xmm0, xmm0
0x18002cf71  movups  [rbp+var_18], xmm0
0x18002cf75  mov     word ptr [rbp+var_18+8], ax
0x18002cf79  xor     edx, edx
0x18002cf7b  mov     eax, [rdi+80h]
0x18002cf81  xorps   xmm1, xmm1
0x18002cf84  movups  [rbp+var_30], xmm1
0x18002cf88  mov     dword ptr [rbp+var_30+8], eax
0x18002cf8b  mov     word ptr [rbp+var_18], r12w
0x18002cf90  mov     word ptr [rbp+var_30], r13w
0x18002cf95  mov     rax, [rcx]
0x18002cf98  mov     rax, [rax+48h]
0x18002cf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfa1  mov     ebx, eax
0x18002cfa3  test    eax, eax
0x18002cfa5  js      short loc_18002D021
0x18002cfa7  mov     rcx, [rdi+103E8h]
0x18002cfae  lea     r9, [rbp+var_30]
0x18002cfb2  xor     eax, eax
0x18002cfb4  lea     r8, [rbp+var_18]
0x18002cfb8  mov     [rbp+var_8], rax
0x18002cfbc  xorps   xmm0, xmm0
0x18002cfbf  mov     [rbp+var_20], rax
0x18002cfc3  xorps   xmm1, xmm1
0x18002cfc6  movups  [rbp+var_18], xmm0
0x18002cfca  mov     eax, 0BCC1h
0x18002cfcf  mov     word ptr [rbp+var_18], r12w
0x18002cfd4  mov     word ptr [rbp+var_18+8], ax
0x18002cfd8  xor     edx, edx
0x18002cfda  mov     eax, [rdi+84h]
0x18002cfe0  movups  [rbp+var_30], xmm1
0x18002cfe4  mov     dword ptr [rbp+var_30+8], eax
0x18002cfe7  mov     word ptr [rbp+var_30], r13w
0x18002cfec  mov     rax, [rcx]
0x18002cfef  mov     rax, [rax+48h]
0x18002cff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cff8  mov     ebx, eax
0x18002cffa  test    eax, eax
0x18002cffc  js      short loc_18002D021
0x18002cffe  cmp     byte ptr [rdi+60h], 0
0x18002d002  jnz     loc_18002D0D7
0x18002d008  mov     edx, [rdi+103D4h]
0x18002d00e  mov     rcx, rsi
0x18002d011  mov     rax, [rsi+58h]
0x18002d015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d01a  mov     r14d, eax
0x18002d01d  test    eax, eax
0x18002d01f  jns     short loc_18002D059
0x18002d021  mov     rcx, [rbp+arg_0]
0x18002d025  test    rcx, rcx
0x18002d028  jz      short loc_18002D036
0x18002d02a  mov     rax, [rcx]
0x18002d02d  mov     rax, [rax+10h]
0x18002d031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d036  or      eax, 0FFFFFFFFh
0x18002d039  lea     r11, [rsp+60h+var_s0]
0x18002d03e  mov     rsi, [r11+48h]
0x18002d042  test    ebx, ebx
0x18002d044  mov     rbx, [r11+40h]
0x18002d048  cmovz   eax, r14d
0x18002d04c  mov     rsp, r11
0x18002d04f  pop     r14
0x18002d051  pop     r13
0x18002d053  pop     r12
0x18002d055  pop     rdi
0x18002d056  pop     rbp
0x18002d057  retn
0x18002d059  mov     rcx, [rdi+103E8h]
0x18002d060  lea     r8, [rbp+arg_0]
0x18002d064  lea     rdx, IID_IPersistStream
0x18002d06b  mov     rax, [rcx]
0x18002d06e  mov     rax, [rax]
0x18002d071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d076  mov     ebx, eax
0x18002d078  test    eax, eax
0x18002d07a  js      short loc_18002D021
0x18002d07c  mov     rcx, [rbp+arg_0]
0x18002d080  mov     r8d, 1
0x18002d086  mov     rdx, [rsi]
0x18002d089  mov     rax, [rcx]
0x18002d08c  mov     rax, [rax+30h]
0x18002d090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d095  mov     ebx, eax
0x18002d097  test    eax, eax
0x18002d099  js      short loc_18002D021
0x18002d09b  mov     rcx, [rdi+103E8h]
0x18002d0a2  lea     rdx, [rdi+103D8h]
0x18002d0a9  mov     rax, [rcx]
0x18002d0ac  mov     rax, [rax+28h]
0x18002d0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b5  mov     ebx, eax
0x18002d0b7  test    eax, eax
0x18002d0b9  js      loc_18002D021
0x18002d0bf  mov     rdx, [rbp+arg_8]
0x18002d0c3  mov     rcx, rsi
0x18002d0c6  mov     rax, [rsi+58h]
0x18002d0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0cf  mov     r14d, eax
0x18002d0d2  jmp     loc_18002D021
0x18002d0d7  mov     rcx, [rdi+103E8h]
0x18002d0de  lea     r9, [rbp+var_30]
0x18002d0e2  xor     eax, eax
0x18002d0e4  lea     r8, [rbp+var_18]
0x18002d0e8  mov     [rbp+var_8], rax
0x18002d0ec  xorps   xmm0, xmm0
0x18002d0ef  mov     [rbp+var_20], rax
0x18002d0f3  xorps   xmm1, xmm1
0x18002d0f6  movups  [rbp+var_18], xmm0
0x18002d0fa  mov     eax, 0BCC2h
0x18002d0ff  mov     word ptr [rbp+var_18], r12w
0x18002d104  mov     word ptr [rbp+var_18+8], ax
0x18002d108  xor     edx, edx
0x18002d10a  mov     eax, [rdi+88h]
0x18002d110  movups  [rbp+var_30], xmm1
0x18002d114  mov     dword ptr [rbp+var_30+8], eax
0x18002d117  mov     word ptr [rbp+var_30], r13w
0x18002d11c  mov     rax, [rcx]
0x18002d11f  mov     rax, [rax+48h]
0x18002d123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d128  mov     ebx, eax
0x18002d12a  test    eax, eax
0x18002d12c  js      loc_18002D021
0x18002d132  mov     rcx, [rdi+103E8h]
0x18002d139  lea     r9, [rbp+var_30]
0x18002d13d  xor     eax, eax
0x18002d13f  lea     r8, [rbp+var_18]
0x18002d143  mov     [rbp+var_8], rax
0x18002d147  xorps   xmm0, xmm0
0x18002d14a  mov     [rbp+var_20], rax
0x18002d14e  xorps   xmm1, xmm1
0x18002d151  movups  [rbp+var_18], xmm0
0x18002d155  mov     eax, 0BCC3h
0x18002d15a  mov     word ptr [rbp+var_18], r12w
0x18002d15f  mov     word ptr [rbp+var_18+8], ax
0x18002d163  xor     edx, edx
0x18002d165  mov     eax, [rdi+8Ch]
0x18002d16b  movups  [rbp+var_30], xmm1
0x18002d16f  mov     dword ptr [rbp+var_30+8], eax
0x18002d172  mov     word ptr [rbp+var_30], r13w
0x18002d177  mov     rax, [rcx]
0x18002d17a  mov     rax, [rax+48h]
0x18002d17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d183  mov     ebx, eax
0x18002d185  test    eax, eax
0x18002d187  js      loc_18002D021
0x18002d18d  jmp     loc_18002D008
```

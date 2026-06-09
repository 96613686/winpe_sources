# GetDestInfo

- ea: `0x180006e38`
- end: `0x180006fc1`
- name: `GetDestInfo`
- size: `393`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a20`
- `0x1800064f0`
- `0x180007050`
- `0x18000a370`
- `0x18000a5b0`
- `0x18000a670`

## callees

- `0x180006e38`

## pseudocode

```c
__int64 __fastcall GetDestInfo(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  int v7; // r12d
  __int64 v8; // r9
  unsigned int v9; // r8d
  __int64 result; // rax
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rbx
  int v13; // ebp
  __int64 **v14; // r11
  __int64 *i; // rcx
  __int64 v16; // r13
  unsigned int v17; // r9d
  __int64 v18; // r15
  unsigned int v19; // esi
  unsigned int v20; // edi

  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 40LL) & a4;
  *(_QWORD *)a5 = a2 ^ 0x7754DF32;
  _InterlockedIncrement((volatile signed __int32 *)a2);
  v8 = 0;
  v9 = v7;
  *(_OWORD *)(a5 + 8) = *(_OWORD *)(a2 + 80);
  *(_DWORD *)(a5 + 24) = *(_DWORD *)(a2 + 96);
  *(_QWORD *)(a5 + 28) = *(_QWORD *)(a2 + 100);
  result = *(unsigned int *)(a2 + 112);
  v11 = 0;
  *(_DWORD *)(a5 + 36) = result;
  if ( v7 )
  {
    do
    {
      if ( (unsigned int)v11 >= 0x20 )
        break;
      if ( (v9 & 1) != 0 )
      {
        v12 = *(volatile signed __int32 **)(a2 + 24LL * *(unsigned int *)(*(_QWORD *)(a1 + 16) + 4 * v11 + 176) + 136);
        result = 5 * v8;
        *(_OWORD *)(a5 + 8 * result + 48) = 0;
        *(_OWORD *)(a5 + 8 * result + 64) = 0;
        *(_QWORD *)(a5 + 8 * result + 80) = 0;
        *(_DWORD *)(a5 + 8 * result + 48) = v11;
        if ( v12 )
        {
          result = 5 * v8;
          *(_QWORD *)(a5 + 40 * v8 + 80) = (unsigned __int64)v12 ^ 0x7754DF32;
          _InterlockedIncrement(v12);
        }
        v8 = (unsigned int)(v8 + 1);
      }
      v11 = (unsigned int)(v11 + 1);
      v9 >>= 1;
    }
    while ( v9 );
  }
  *(_DWORD *)(a5 + 40) = v8;
  if ( (v7 & *(_DWORD *)(a2 + 112)) != 0 )
  {
    if ( a3 == -1 )
      a3 = *(_DWORD *)(a1 + 8);
    v13 = 0;
    v14 = (__int64 **)(a2 + 56);
    for ( i = *v14; i != (__int64 *)v14; i = (__int64 *)*i )
    {
      v16 = i[6];
      if ( !a3 || *(_DWORD *)((i[6] ^ 0x7754DF32) + 8) == a3 )
      {
        v17 = *((_DWORD *)i + 19);
        if ( (v17 & v7) != 0 )
        {
          v18 = 0;
          v19 = 0;
          v20 = v7;
          if ( v7 )
          {
            do
            {
              if ( v19 >= 0x20 )
                break;
              if ( (v20 & 1) != 0 )
              {
                if ( (v17 & 1) != 0 )
                {
                  ++*(_DWORD *)(a5 + 40 * v18 + 52);
                  if ( !_bittest(&v13, v19) )
                  {
                    *(_QWORD *)(a5 + 40 * v18 + 56) = (unsigned __int64)(i - 1) ^ 0x7754DF32;
                    _InterlockedIncrement((volatile signed __int32 *)i - 2);
                    *(_QWORD *)(a5 + 40 * v18 + 64) = v16;
                    _InterlockedIncrement((volatile signed __int32 *)(v16 ^ 0x7754DF32));
                    result = *((unsigned __int16 *)i + 33);
                    *(_DWORD *)(a5 + 40 * v18 + 72) = result;
                  }
                }
                v18 = (unsigned int)(v18 + 1);
              }
              v17 >>= 1;
              ++v19;
              v20 >>= 1;
            }
            while ( v20 );
          }
          v13 |= *((_DWORD *)i + 19);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006e38  push    rbx
0x180006e3a  push    rbp
0x180006e3b  push    rsi
0x180006e3c  push    rdi
0x180006e3d  push    r12
0x180006e3f  push    r13
0x180006e41  push    r14
0x180006e43  push    r15
0x180006e45  mov     rax, [rcx+10h]
0x180006e49  mov     r12d, r9d
0x180006e4c  mov     r10, [rsp+40h+arg_20]
0x180006e51  mov     r15d, 7754DF32h
0x180006e57  mov     r14d, r8d
0x180006e5a  mov     r11, rdx
0x180006e5d  mov     rsi, rcx
0x180006e60  and     r12d, [rax+28h]
0x180006e64  mov     rax, rdx
0x180006e67  xor     rax, r15
0x180006e6a  mov     [r10], rax
0x180006e6d  lock inc dword ptr [rdx]
0x180006e70  movups  xmm0, xmmword ptr [rdx+50h]
0x180006e74  xor     r9d, r9d
0x180006e77  mov     r8d, r12d
0x180006e7a  movups  xmmword ptr [r10+8], xmm0
0x180006e7f  mov     eax, [rdx+60h]
0x180006e82  mov     [r10+18h], eax
0x180006e86  mov     rax, [rdx+64h]
0x180006e8a  mov     [r10+1Ch], rax
0x180006e8e  mov     eax, [rdx+70h]
0x180006e91  xor     edx, edx
0x180006e93  mov     [r10+24h], eax
0x180006e97  test    r12d, r12d
0x180006e9a  jz      short loc_180006EFE
0x180006e9c  cmp     edx, 20h ; ' '
0x180006e9f  jnb     short loc_180006EFE
0x180006ea1  test    r8b, 1
0x180006ea5  jz      short loc_180006EF7
0x180006ea7  mov     rax, [rsi+10h]
0x180006eab  xorps   xmm0, xmm0
0x180006eae  mov     ecx, [rax+rdx*4+0B0h]
0x180006eb5  lea     rax, [rcx+rcx*2]
0x180006eb9  xor     ecx, ecx
0x180006ebb  mov     rbx, [r11+rax*8+88h]
0x180006ec3  lea     rax, [r9+r9*4]
0x180006ec7  movups  xmmword ptr [r10+rax*8+30h], xmm0
0x180006ecd  movups  xmmword ptr [r10+rax*8+40h], xmm0
0x180006ed3  mov     [r10+rax*8+50h], rcx
0x180006ed8  mov     [r10+rax*8+30h], edx
0x180006edd  test    rbx, rbx
0x180006ee0  jz      short loc_180006EF4
0x180006ee2  mov     rcx, rbx
0x180006ee5  lea     rax, [r9+r9*4]
0x180006ee9  xor     rcx, r15
0x180006eec  mov     [r10+rax*8+50h], rcx
0x180006ef1  lock inc dword ptr [rbx]
0x180006ef4  inc     r9d
0x180006ef7  inc     edx
0x180006ef9  shr     r8d, 1
0x180006efc  jnz     short loc_180006E9C
0x180006efe  mov     [r10+28h], r9d
0x180006f02  test    [r11+70h], r12d
0x180006f06  jz      loc_180006FB4
0x180006f0c  cmp     r14d, 0FFFFFFFFh
0x180006f10  jnz     short loc_180006F16
0x180006f12  mov     r14d, [rsi+8]
0x180006f16  xor     ebp, ebp
0x180006f18  add     r11, 38h ; '8'
0x180006f1c  mov     rcx, [r11]
0x180006f1f  jmp     loc_180006FAB
0x180006f24  mov     r13, [rcx+30h]
0x180006f28  mov     r8, r13
0x180006f2b  xor     r8, r15
0x180006f2e  test    r14d, r14d
0x180006f31  jz      short loc_180006F39
0x180006f33  cmp     [r8+8], r14d
0x180006f37  jnz     short loc_180006FA8
0x180006f39  mov     r9d, [rcx+4Ch]
0x180006f3d  test    r12d, r9d
0x180006f40  jz      short loc_180006FA8
0x180006f42  xor     r15d, r15d
0x180006f45  xor     esi, esi
0x180006f47  mov     edi, r12d
0x180006f4a  test    r12d, r12d
0x180006f4d  jz      short loc_180006F9F
0x180006f4f  cmp     esi, 20h ; ' '
0x180006f52  jnb     short loc_180006F9F
0x180006f54  test    dil, 1
0x180006f58  jz      short loc_180006F96
0x180006f5a  test    r9b, 1
0x180006f5e  jz      short loc_180006F93
0x180006f60  lea     rbx, [r15+r15*4]
0x180006f64  inc     dword ptr [r10+rbx*8+34h]
0x180006f69  bt      ebp, esi
0x180006f6c  jb      short loc_180006F93
0x180006f6e  lea     rax, [rcx-8]
0x180006f72  xor     rax, 7754DF32h
0x180006f78  mov     [r10+rbx*8+38h], rax
0x180006f7d  lock inc dword ptr [rcx-8]
0x180006f81  mov     [r10+rbx*8+40h], r13
0x180006f86  lock inc dword ptr [r8]
0x180006f8a  movzx   eax, word ptr [rcx+42h]
0x180006f8e  mov     [r10+rbx*8+48h], eax
0x180006f93  inc     r15d
0x180006f96  shr     r9d, 1
0x180006f99  inc     esi
0x180006f9b  shr     edi, 1
0x180006f9d  jnz     short loc_180006F4F
0x180006f9f  or      ebp, [rcx+4Ch]
0x180006fa2  mov     r15d, 7754DF32h
0x180006fa8  mov     rcx, [rcx]
0x180006fab  cmp     rcx, r11
0x180006fae  jnz     loc_180006F24
0x180006fb4  pop     r15
0x180006fb6  pop     r14
0x180006fb8  pop     r13
0x180006fba  pop     r12
0x180006fbc  pop     rdi
0x180006fbd  pop     rsi
0x180006fbe  pop     rbp
0x180006fbf  pop     rbx
0x180006fc0  retn
```

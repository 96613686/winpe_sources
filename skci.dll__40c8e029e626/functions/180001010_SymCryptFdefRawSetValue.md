# SymCryptFdefRawSetValue

- ea: `0x180001010`
- end: `0x1800010f2`
- name: `SymCryptFdefRawSetValue`
- size: `226`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180023390`
- `0x180023e94`
- `0x180024be8`
- `0x180025554`
- `0x1800255cc`
- `0x180026024`
- `0x180026108`
- `0x180027604`
- `0x180027e64`
- `0x1800282c0`
- `0x180029548`

## callees

- `0x180001010`

## pseudocode

```c
__int64 __fastcall SymCryptFdefRawSetValue(unsigned __int8 *a1, __int64 a2, int a3, __int64 a4, int a5)
{
  unsigned __int8 *v6; // r10
  int v7; // r8d
  __int64 v9; // r9
  __int64 i; // r8
  int v11; // ecx
  unsigned __int8 *v12; // rbx
  int v13; // ecx
  int v14; // eax

  v6 = a1;
  v7 = a3 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 32782;
    v9 = -1;
    v6 = &a1[a2 - 1];
  }
  else
  {
    v9 = 1;
  }
  for ( i = 0; (unsigned int)i < 16 * a5; i = (unsigned int)(i + 1) )
  {
    if ( a2 )
    {
      v11 = *v6;
      v6 += v9;
      if ( --a2 )
      {
        v12 = &v6[v9];
        v11 |= *v6 << 8;
        if ( --a2 )
        {
          v6 = &v12[v9];
          if ( --a2 )
          {
            --a2;
            v6 += v9;
            v11 |= (*v12 << 16) | (v12[v9] << 24);
          }
          else
          {
            v11 |= *v12 << 16;
          }
        }
        else
        {
          v6 += v9;
        }
      }
    }
    else
    {
      v11 = 0;
    }
    *(_DWORD *)(a4 + 4 * i) = v11;
  }
  v13 = 0;
  if ( !a2 )
    return 0;
  do
  {
    v14 = *v6;
    v6 += v9;
    v13 |= v14;
    --a2;
  }
  while ( a2 );
  if ( v13 )
    return 32781;
  else
    return 0;
}

```

## disassembly

```asm
0x180001010  push    rsi
0x180001012  mov     rsi, r9
0x180001015  mov     r10, rcx
0x180001018  sub     r8d, 1
0x18000101c  jz      short loc_18000103D
0x18000101e  cmp     r8d, 1
0x180001022  jz      short loc_18000102E
0x180001024  mov     eax, 800Eh
0x180001029  jmp     loc_1800010EF
0x18000102e  dec     r10
0x180001031  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180001038  add     r10, rdx
0x18000103b  jmp     short loc_180001043
0x18000103d  mov     r9d, 1
0x180001043  mov     [rsp+8+arg_8], rdi
0x180001048  xor     r8d, r8d
0x18000104b  mov     edi, [rsp+8+arg_20]
0x18000104f  shl     edi, 4
0x180001052  test    edi, edi
0x180001054  jz      short loc_1800010C7
0x180001056  mov     [rsp+8+arg_0], rbx
0x18000105b  nop     dword ptr [rax+rax+00h]
0x180001060  test    rdx, rdx
0x180001063  jz      short loc_1800010B4
0x180001065  movzx   ecx, byte ptr [r10]
0x180001069  add     r10, r9
0x18000106c  sub     rdx, 1
0x180001070  jz      short loc_1800010B6
0x180001072  movzx   eax, byte ptr [r10]
0x180001076  lea     rbx, [r9+r10]
0x18000107a  shl     eax, 8
0x18000107d  or      ecx, eax
0x18000107f  sub     rdx, 1
0x180001083  jz      short loc_1800010AF
0x180001085  movzx   eax, byte ptr [rbx]
0x180001088  lea     r11, [rbx+r9]
0x18000108c  shl     eax, 10h
0x18000108f  mov     r10, r11
0x180001092  or      eax, ecx
0x180001094  sub     rdx, 1
0x180001098  jz      short loc_1800010AB
0x18000109a  movzx   ecx, byte ptr [r11]
0x18000109e  dec     rdx
0x1800010a1  shl     ecx, 18h
0x1800010a4  add     r10, r9
0x1800010a7  or      ecx, eax
0x1800010a9  jmp     short loc_1800010B6
0x1800010ab  mov     ecx, eax
0x1800010ad  jmp     short loc_1800010B6
0x1800010af  mov     r10, rbx
0x1800010b2  jmp     short loc_1800010B6
0x1800010b4  xor     ecx, ecx
0x1800010b6  mov     [rsi+r8*4], ecx
0x1800010ba  inc     r8d
0x1800010bd  cmp     r8d, edi
0x1800010c0  jb      short loc_180001060
0x1800010c2  mov     rbx, [rsp+8+arg_0]
0x1800010c7  mov     rdi, [rsp+8+arg_8]
0x1800010cc  xor     ecx, ecx
0x1800010ce  test    rdx, rdx
0x1800010d1  jz      short loc_1800010ED
0x1800010d3  movzx   eax, byte ptr [r10]
0x1800010d7  add     r10, r9
0x1800010da  or      ecx, eax
0x1800010dc  sub     rdx, 1
0x1800010e0  jnz     short loc_1800010D3
0x1800010e2  test    ecx, ecx
0x1800010e4  jz      short loc_1800010ED
0x1800010e6  mov     eax, 800Dh
0x1800010eb  jmp     short loc_1800010EF
0x1800010ed  xor     eax, eax
0x1800010ef  pop     rsi
0x1800010f0  retn
```

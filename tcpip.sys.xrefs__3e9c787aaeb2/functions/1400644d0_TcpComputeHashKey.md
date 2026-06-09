# TcpComputeHashKey

- ea: `0x1400644d0`
- end: `0x14006468a`
- name: `TcpComputeHashKey`
- size: `442`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140030160`
- `0x140063f2c`
- `0x1400641dc`
- `0x140064690`
- `0x1400653e0`
- `0x140133ce0`
- `0x140162c4c`

## callees

- `0x1400644d0`

## import_xrefs

- `NETIO!RtlComputeToeplitzHash` at `0x140064512`
- `NETIO!RtlComputeToeplitzHash` at `0x140064545`
- `NETIO!RtlComputeToeplitzHash` at `0x14006456d`
- `NETIO!RtlComputeToeplitzHash` at `0x1400645a7`
- `NETIO!RtlComputeToeplitzHash` at `0x1400645ba`
- `NETIO!RtlComputeToeplitzHash` at `0x1400645e9`
- `NETIO!RtlComputeToeplitzHash` at `0x14006463d`
- `NETIO!RtlComputeToeplitzHash` at `0x140064670`
- `NETIO!RtlComputeToeplitzHash` at `0x140064512`
- `NETIO!RtlComputeToeplitzHash` at `0x140064545`
- `NETIO!RtlComputeToeplitzHash` at `0x14006456d`
- `NETIO!RtlComputeToeplitzHash` at `0x1400645a7`
- `NETIO!RtlComputeToeplitzHash` at `0x1400645ba`
- `NETIO!RtlComputeToeplitzHash` at `0x1400645e9`
- `NETIO!RtlComputeToeplitzHash` at `0x14006463d`
- `NETIO!RtlComputeToeplitzHash` at `0x140064670`

## pseudocode

```c
__int64 __fastcall TcpComputeHashKey(__int64 a1, __int64 a2, __int64 a3, __int16 a4, __int16 a5, __int16 a6)
{
  __int64 v6; // rdi
  __int64 v9; // r8
  int v10; // ebx
  int v11; // eax
  __int64 v12; // r9
  int v13; // ebx
  __int16 v15; // si
  __int64 v16; // r9
  int v17; // eax
  __int64 v18; // r9
  __int16 v19; // [rsp+40h] [rbp+8h] BYREF
  __int16 v20; // [rsp+58h] [rbp+20h] BYREF

  v20 = a4;
  v6 = *(_QWORD *)(a2 + 48);
  if ( !v6 )
    LODWORD(v6) = RtlComputeToeplitzHash(
                    TcpToeplitzHashContext,
                    **(_QWORD **)(a2 + 16),
                    *(unsigned __int16 *)(a1 + 72),
                    *(unsigned __int16 *)(a1 + 72));
  v9 = *(unsigned __int16 *)(a1 + 72);
  if ( *(_WORD *)(a1 + 24) == 23 )
  {
    v10 = v6 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, a3, v9, 0);
    if ( (_BYTE)a6 )
    {
      v11 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v20, 2, 32);
      v12 = 34;
      goto LABEL_6;
    }
  }
  else
  {
    v10 = v6 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, a3, v9, 0);
    if ( (_BYTE)a6 )
    {
      v11 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v20, 2, 8);
      v12 = 10;
LABEL_6:
      v13 = v10 ^ v11 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, &a5, 2, v12);
      return v13 | 0x80000000;
    }
  }
  v15 = *(_WORD *)(a1 + 24);
  v19 = a5;
  v16 = 32;
  a6 = v20;
  if ( v15 != 23 )
    v16 = 8;
  v17 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &a6, 2, v16);
  v18 = 34;
  if ( v15 != 23 )
    v18 = 10;
  v13 = (v17 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, &v19, 2, v18)) & 0x7FFFFFC0 ^ v10;
  return v13 | 0x80000000;
}

```

## disassembly

```asm
0x1400644d0  mov     [rsp+arg_8], rbx
0x1400644d5  mov     [rsp+arg_18], r9w
0x1400644db  push    rbp
0x1400644dc  push    rsi
0x1400644dd  push    rdi
0x1400644de  sub     rsp, 20h
0x1400644e2  mov     rdi, [rdx+30h]
0x1400644e6  mov     rbp, r8
0x1400644e9  mov     rsi, rcx
0x1400644ec  test    rdi, rdi
0x1400644ef  jz      loc_140064591
0x1400644f5  movzx   r8d, word ptr [rsi+48h]
0x1400644fa  lea     rcx, TcpToeplitzHashContext
0x140064501  xor     r9d, r9d
0x140064504  mov     rdx, rbp
0x140064507  cmp     word ptr [rsi+18h], 17h
0x14006450c  jz      loc_1400645BA
0x140064512  call    cs:__imp_RtlComputeToeplitzHash
0x140064519  nop     dword ptr [rax+rax+00h]
0x14006451e  mov     ebx, eax
0x140064520  xor     ebx, edi
0x140064522  cmp     byte ptr [rsp+38h+arg_28], 0
0x140064527  jz      loc_140064600
0x14006452d  mov     r9d, 8
0x140064533  lea     rdx, [rsp+38h+arg_18]
0x140064538  mov     r8d, 2
0x14006453e  lea     rcx, TcpToeplitzHashContext
0x140064545  call    cs:__imp_RtlComputeToeplitzHash
0x14006454c  nop     dword ptr [rax+rax+00h]
0x140064551  mov     r9d, 0Ah
0x140064557  mov     edi, eax
0x140064559  lea     rdx, [rsp+38h+arg_20]
0x14006455e  mov     r8d, 2
0x140064564  lea     rcx, TcpToeplitzHashContext
0x14006456b  xor     edi, ebx
0x14006456d  call    cs:__imp_RtlComputeToeplitzHash
0x140064574  nop     dword ptr [rax+rax+00h]
0x140064579  mov     ebx, eax
0x14006457b  xor     ebx, edi
0x14006457d  bts     ebx, 1Fh
0x140064581  mov     eax, ebx
0x140064583  mov     rbx, [rsp+38h+arg_8]
0x140064588  add     rsp, 20h
0x14006458c  pop     rdi
0x14006458d  pop     rsi
0x14006458e  pop     rbp
0x14006458f  retn
0x140064591  movzx   r8d, word ptr [rcx+48h]
0x140064596  lea     rcx, TcpToeplitzHashContext
0x14006459d  mov     rdx, [rdx+10h]
0x1400645a1  mov     r9d, r8d
0x1400645a4  mov     rdx, [rdx]
0x1400645a7  call    cs:__imp_RtlComputeToeplitzHash
0x1400645ae  nop     dword ptr [rax+rax+00h]
0x1400645b3  mov     edi, eax
0x1400645b5  jmp     loc_1400644F5
0x1400645ba  call    cs:__imp_RtlComputeToeplitzHash
0x1400645c1  nop     dword ptr [rax+rax+00h]
0x1400645c6  mov     ebx, eax
0x1400645c8  xor     ebx, edi
0x1400645ca  cmp     byte ptr [rsp+38h+arg_28], 0
0x1400645cf  jz      short loc_140064600
0x1400645d1  mov     r9d, 20h ; ' '
0x1400645d7  lea     rdx, [rsp+38h+arg_18]
0x1400645dc  mov     r8d, 2
0x1400645e2  lea     rcx, TcpToeplitzHashContext
0x1400645e9  call    cs:__imp_RtlComputeToeplitzHash
0x1400645f0  nop     dword ptr [rax+rax+00h]
0x1400645f5  mov     r9d, 22h ; '"'
0x1400645fb  jmp     loc_140064557
0x140064600  movzx   eax, [rsp+38h+arg_20]
0x140064605  lea     rdx, [rsp+38h+arg_28]
0x14006460a  movzx   esi, word ptr [rsi+18h]
0x14006460e  lea     rcx, TcpToeplitzHashContext
0x140064615  mov     [rsp+38h+arg_0], ax
0x14006461a  mov     r9d, 20h ; ' '
0x140064620  movzx   eax, [rsp+38h+arg_18]
0x140064625  cmp     si, 17h
0x140064629  mov     [rsp+38h+arg_28], ax
0x14006462e  mov     r8d, 2
0x140064634  mov     eax, 8
0x140064639  cmovnz  r9d, eax
0x14006463d  call    cs:__imp_RtlComputeToeplitzHash
0x140064644  nop     dword ptr [rax+rax+00h]
0x140064649  mov     r9d, 22h ; '"'
0x14006464f  lea     rdx, [rsp+38h+arg_0]
0x140064654  mov     edi, eax
0x140064656  lea     rcx, TcpToeplitzHashContext
0x14006465d  mov     eax, 0Ah
0x140064662  cmp     si, 17h
0x140064666  mov     r8d, 2
0x14006466c  cmovnz  r9d, eax
0x140064670  call    cs:__imp_RtlComputeToeplitzHash
0x140064677  nop     dword ptr [rax+rax+00h]
0x14006467c  xor     eax, edi
0x14006467e  and     eax, 7FFFFFC0h
0x140064683  xor     ebx, eax
0x140064685  jmp     loc_14006457D
```

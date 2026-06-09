# WMSDKRESIZER::Reset(void)

- ea: `0x1800123a0`
- end: `0x1800125a9`
- name: `?Reset@WMSDKRESIZER@@QEAAHXZ`
- size: `521`
- prototype: `__int64 __fastcall(WMSDKRESIZER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180013420`
- `0x180013a00`

## callees

- `0x1800123a0`

## pseudocode

```c
__int64 __fastcall WMSDKRESIZER::Reset(WMSDKRESIZER *this)
{
  bool v1; // zf
  int v3; // r9d
  int v4; // r10d
  int v5; // edi
  int v6; // eax
  int v7; // ebx
  int *v8; // rdx
  int v9; // eax
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  __int64 v14; // r10
  int v15; // eax
  int v16; // ebx
  int v17; // edx
  int v18; // ecx
  int v19; // eax
  int v20; // ecx
  __int64 v21; // rax
  int v22; // edx
  int v23; // r10d
  int v24; // r11d
  __int64 result; // rax
  int v26; // edx
  int v27; // r10d
  int v28; // eax

  v1 = *((_DWORD *)this + 271) == 0;
  v3 = *((_DWORD *)this + 11);
  v4 = *((_DWORD *)this + 7);
  *((_DWORD *)this + 272) = 0;
  if ( v1 )
  {
    v5 = *((_DWORD *)this + 12);
    if ( *((_DWORD *)this + 6) == v5 && v4 == *((_DWORD *)this + 13) )
    {
      v6 = 2;
    }
    else
    {
      *((_DWORD *)this + 272) = 1;
      v6 = 3;
    }
    v7 = *((_DWORD *)this + 14);
    v8 = (int *)((char *)this + 60);
    if ( *((_DWORD *)this + 10) != v7 || v3 != *v8 )
      *((_DWORD *)this + 272) = v6;
    v9 = -v5;
    if ( v5 > 0 )
      v9 = v5;
    if ( *((_DWORD *)this + 6) == v9 )
    {
      v10 = *((_DWORD *)this + 13);
      v11 = -v10;
      if ( v10 > 0 )
        v11 = v10;
      if ( v4 == v11 )
      {
        v12 = -v7;
        if ( v7 > 0 )
          v12 = v7;
        if ( *((_DWORD *)this + 10) == v12 )
        {
          v13 = -*v8;
          if ( *v8 > 0 )
            v13 = *v8;
          if ( v3 == v13 )
            *((_DWORD *)this + 272) = 0;
        }
      }
    }
    *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) = v4;
  }
  else
  {
    *((_DWORD *)this + 272) = 3;
    *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) = v4 / 2;
    v3 /= 2;
  }
  *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) = *((_DWORD *)this + 6);
  v14 = *((_QWORD *)this + 1);
  v15 = *(_DWORD *)(v14 + 16);
  v16 = *(_DWORD *)(v14 + 8);
  v17 = *(_DWORD *)(v14 + 4);
  v18 = *(unsigned __int16 *)(v14 + 14);
  if ( v15 == 1448433993 || v15 == 808596553 || v15 == 842094169 || v15 == 842094158 || v15 == 825316942 )
    v19 = v16 * v17 * v18 / 8;
  else
    v19 = 4 * v16 * ((v17 * v18 / 8 + 3) / 4);
  v20 = -v19;
  if ( v19 > 0 )
    v20 = v19;
  *(_DWORD *)(v14 + 20) = v20;
  if ( !*((_DWORD *)this + 270) || *(_DWORD *)this == 4 )
  {
    v26 = *((_DWORD *)this + 10);
    v27 = *((_DWORD *)this + 6);
    v28 = -*(_DWORD *)(*((_QWORD *)this + 1) + 8LL);
    if ( *(int *)(*((_QWORD *)this + 1) + 8LL) > 0 )
      v28 = *(_DWORD *)(*((_QWORD *)this + 1) + 8LL);
    if ( v3 < 0 )
      v3 = -v3;
    *((_DWORD *)this + 196) = v28;
    result = 1;
    *((_DWORD *)this + 195) = v27;
    *((_DWORD *)this + 197) = v26;
    *((_DWORD *)this + 198) = v3;
  }
  else
  {
    v21 = *((_QWORD *)this + 1);
    v22 = *((_DWORD *)this + 10);
    v23 = -*((_DWORD *)this + 6);
    if ( *((int *)this + 6) > 0 )
      v23 = *((_DWORD *)this + 6);
    v24 = -*(_DWORD *)(v21 + 8);
    if ( *(int *)(v21 + 8) > 0 )
      v24 = *(_DWORD *)(v21 + 8);
    if ( v22 < 0 )
      v22 = -v22;
    if ( v3 < 0 )
      v3 = -v3;
    *((_DWORD *)this + 246) = v23;
    result = 1;
    *((_DWORD *)this + 247) = v24;
    *((_DWORD *)this + 248) = v22;
    *((_DWORD *)this + 249) = v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800123a0  sub     rsp, 8
0x1800123a4  cmp     dword ptr [rcx+43Ch], 0
0x1800123ab  mov     r8, rcx
0x1800123ae  mov     r9d, [rcx+2Ch]
0x1800123b2  mov     r10d, [rcx+1Ch]
0x1800123b6  mov     [rsp+8+arg_0], rbx
0x1800123bb  mov     dword ptr [rcx+440h], 0
0x1800123c5  jnz     loc_180012457
0x1800123cb  mov     [rsp+8+var_8], rdi
0x1800123cf  mov     edi, [rcx+30h]
0x1800123d2  cmp     [rcx+18h], edi
0x1800123d5  jnz     short loc_1800123E4
0x1800123d7  cmp     r10d, [rcx+34h]
0x1800123db  jnz     short loc_1800123E4
0x1800123dd  mov     eax, 2
0x1800123e2  jmp     short loc_1800123F3
0x1800123e4  mov     dword ptr [rcx+440h], 1
0x1800123ee  mov     eax, 3
0x1800123f3  mov     ebx, [rcx+38h]
0x1800123f6  lea     rdx, [rcx+3Ch]
0x1800123fa  cmp     [rcx+28h], ebx
0x1800123fd  jnz     short loc_180012404
0x1800123ff  cmp     r9d, [rdx]
0x180012402  jz      short loc_18001240A
0x180012404  mov     [rcx+440h], eax
0x18001240a  mov     eax, edi
0x18001240c  neg     eax
0x18001240e  cmovs   eax, edi
0x180012411  mov     rdi, [rsp+8+var_8]
0x180012415  cmp     [rcx+18h], eax
0x180012418  jnz     short loc_18001244D
0x18001241a  mov     eax, [rcx+34h]
0x18001241d  mov     ecx, eax
0x18001241f  neg     ecx
0x180012421  cmovs   ecx, eax
0x180012424  cmp     r10d, ecx
0x180012427  jnz     short loc_18001244D
0x180012429  mov     eax, ebx
0x18001242b  neg     eax
0x18001242d  cmovs   eax, ebx
0x180012430  cmp     [r8+28h], eax
0x180012434  jnz     short loc_18001244D
0x180012436  mov     ecx, [rdx]
0x180012438  neg     ecx
0x18001243a  cmovs   ecx, [rdx]
0x18001243d  cmp     r9d, ecx
0x180012440  jnz     short loc_18001244D
0x180012442  mov     dword ptr [r8+440h], 0
0x18001244d  mov     rax, [r8+8]
0x180012451  mov     [rax+8], r10d
0x180012455  jmp     short loc_18001247B
0x180012457  mov     dword ptr [rcx+440h], 3
0x180012461  mov     eax, r10d
0x180012464  mov     rcx, [rcx+8]
0x180012468  cdq
0x180012469  sub     eax, edx
0x18001246b  sar     eax, 1
0x18001246d  mov     [rcx+8], eax
0x180012470  mov     eax, r9d
0x180012473  cdq
0x180012474  sub     eax, edx
0x180012476  sar     eax, 1
0x180012478  mov     r9d, eax
0x18001247b  mov     rdx, [r8+8]
0x18001247f  mov     ecx, [r8+18h]
0x180012483  mov     [rdx+4], ecx
0x180012486  mov     r10, [r8+8]
0x18001248a  mov     eax, [r10+10h]
0x18001248e  mov     ebx, [r10+8]
0x180012492  mov     edx, [r10+4]
0x180012496  movzx   ecx, word ptr [r10+0Eh]
0x18001249b  cmp     eax, 56555949h
0x1800124a0  jz      short loc_1800124E0
0x1800124a2  cmp     eax, 30323449h
0x1800124a7  jz      short loc_1800124E0
0x1800124a9  cmp     eax, 32315659h
0x1800124ae  jz      short loc_1800124E0
0x1800124b0  cmp     eax, 3231564Eh
0x1800124b5  jz      short loc_1800124E0
0x1800124b7  cmp     eax, 3131564Eh
0x1800124bc  jz      short loc_1800124E0
0x1800124be  imul    ecx, edx
0x1800124c1  mov     eax, ecx
0x1800124c3  cdq
0x1800124c4  and     edx, 7
0x1800124c7  add     eax, edx
0x1800124c9  sar     eax, 3
0x1800124cc  add     eax, 3
0x1800124cf  cdq
0x1800124d0  and     edx, 3
0x1800124d3  add     eax, edx
0x1800124d5  sar     eax, 2
0x1800124d8  imul    eax, ebx
0x1800124db  shl     eax, 2
0x1800124de  jmp     short loc_1800124F1
0x1800124e0  imul    ecx, edx
0x1800124e3  imul    ecx, ebx
0x1800124e6  mov     eax, ecx
0x1800124e8  cdq
0x1800124e9  and     edx, 7
0x1800124ec  add     eax, edx
0x1800124ee  sar     eax, 3
0x1800124f1  mov     rbx, [rsp+8+arg_0]
0x1800124f6  mov     ecx, eax
0x1800124f8  neg     ecx
0x1800124fa  cmovs   ecx, eax
0x1800124fd  mov     [r10+14h], ecx
0x180012501  cmp     dword ptr [r8+438h], 0
0x180012509  jz      short loc_180012565
0x18001250b  cmp     dword ptr [r8], 4
0x18001250f  jz      short loc_180012565
0x180012511  mov     rax, [r8+8]
0x180012515  mov     r10d, [r8+18h]
0x180012519  mov     edx, [r8+28h]
0x18001251d  neg     r10d
0x180012520  cmovs   r10d, [r8+18h]
0x180012525  mov     r11d, [rax+8]
0x180012529  neg     r11d
0x18001252c  cmovs   r11d, [rax+8]
0x180012531  test    edx, edx
0x180012533  jns     short loc_180012537
0x180012535  neg     edx
0x180012537  test    r9d, r9d
0x18001253a  jns     short loc_18001253F
0x18001253c  neg     r9d
0x18001253f  mov     [r8+3D8h], r10d
0x180012546  mov     eax, 1
0x18001254b  mov     [r8+3DCh], r11d
0x180012552  mov     [r8+3E0h], edx
0x180012559  mov     [r8+3E4h], r9d
0x180012560  add     rsp, 8
0x180012564  retn
0x180012565  mov     rax, [r8+8]
0x180012569  mov     edx, [r8+28h]
0x18001256d  mov     r10d, [r8+18h]
0x180012571  mov     ecx, [rax+8]
0x180012574  mov     eax, ecx
0x180012576  neg     eax
0x180012578  cmovs   eax, ecx
0x18001257b  test    r9d, r9d
0x18001257e  jns     short loc_180012583
0x180012580  neg     r9d
0x180012583  mov     [r8+310h], eax
0x18001258a  mov     eax, 1
0x18001258f  mov     [r8+30Ch], r10d
0x180012596  mov     [r8+314h], edx
0x18001259d  mov     [r8+318h], r9d
0x1800125a4  add     rsp, 8
0x1800125a8  retn
```

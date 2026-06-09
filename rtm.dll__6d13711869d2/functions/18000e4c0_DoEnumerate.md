# DoEnumerate

- ea: `0x18000e4c0`
- end: `0x18000e761`
- name: `DoEnumerate`
- size: `673`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f780`
- `0x18000fa20`
- `0x18000fcb0`
- `0x180010ab0`

## callees

- `0x18000e4c0`
- `0x18001163c`
- `0x180011800`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall DoEnumerate(__int64 a1, __int64 *a2, int a3)
{
  __int64 **i; // rdi
  __int64 **v7; // rsi
  __int64 v8; // rdx
  __int64 *v9; // rcx
  __int64 *v10; // rdx
  __int64 **v11; // rax
  __int64 *v12; // rdx
  __int64 *v13; // rcx
  __int64 result; // rax
  int v15; // eax
  __int64 *v16; // rax
  __int64 **v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 **v20; // rcx
  __int64 *v21; // rcx
  __int64 *v22; // rdx
  __int64 **v23; // rax
  __int64 **v24; // rdx
  __int64 *v25; // rcx

  do
  {
LABEL_1:
    for ( i = (__int64 **)a2[2 * *((int *)a2 + 17) + 1]; ; i = (__int64 **)i[1] )
    {
      if ( i == (__int64 **)a2[9] )
      {
        if ( *((_DWORD *)a2 + 17)
          || (*((_BYTE *)a2 + 100) & 1) != 0
          || a2[10] == *(_QWORD *)(a1 + 256) + 32LL * (*(_DWORD *)(a1 + 276) - 1) )
        {
          return 259;
        }
        v16 = (__int64 *)*a2;
        if ( *(__int64 **)(*a2 + 8) != a2 )
          goto LABEL_43;
        v17 = (__int64 **)a2[1];
        if ( *v17 != a2 )
          goto LABEL_43;
        *v17 = v16;
        v16[1] = (__int64)v17;
        LeaveSyncList(a1, a2[10]);
        a2[10] += 32;
        v18 = a2[10];
        a2[9] = v18 + 16;
        if ( !DoEnterSyncList(a1, v18, 1) )
        {
          a2[1] = (__int64)a2;
          *a2 = (__int64)a2;
          return 1450;
        }
        v19 = a2[9];
        v20 = *(__int64 ***)(v19 + 8);
        if ( *v20 != (__int64 *)v19 )
          goto LABEL_43;
        *a2 = v19;
        a2[1] = (__int64)v20;
        *v20 = a2;
        *(_QWORD *)(v19 + 8) = a2;
        goto LABEL_1;
      }
      v7 = &i[-2 * *((int *)a2 + 17)];
      if ( ((_DWORD)v7[8] & 1) == 0 && (a3 == -5 || ((_DWORD)v7[8] & 4) == a3) )
        break;
LABEL_28:
      ;
    }
    if ( !*((_DWORD *)a2 + 17) )
      goto LABEL_20;
    v8 = a2[11];
    if ( (__int64 *)v8 == v7[9] )
      goto LABEL_20;
    if ( v8 )
      LeaveSyncList(a1, v8);
    a2[11] = (__int64)v7[9];
    if ( DoEnterSyncList(a1, (__int64)v7[9], 0) )
    {
LABEL_20:
      if ( *((_DWORD *)a2 + 17) <= 1u
        && ((*((_BYTE *)a2 + 100) & 4) == 0 || *((_DWORD *)a2 + 28) == *((_DWORD *)v7 + 23)) )
      {
        if ( (*((_BYTE *)a2 + 100) & 1) != 0
          && (v15 = (*(__int64 (__fastcall **)(__int64 *, __int64))(a1 + 288))(a2 + 17, (__int64)v7 + 116)) != 0 )
        {
          if ( v15 > 0 && !*((_DWORD *)a2 + 17) )
            return 259;
        }
        else if ( (*((_BYTE *)a2 + 100) & 8) == 0 || ((_BYTE)v7[8] & 2) != 0 )
        {
          v21 = &a2[2 * *((int *)a2 + 17)];
          v22 = (__int64 *)*v21;
          if ( *(__int64 **)(*v21 + 8) == v21 )
          {
            v23 = (__int64 **)v21[1];
            if ( *v23 == v21 )
            {
              *v23 = v22;
              v22[1] = (__int64)v23;
              v24 = (__int64 **)i[1];
              if ( *v24 == (__int64 *)i )
              {
                v25 = &a2[2 * *((int *)a2 + 17)];
                result = 0;
                *v25 = (__int64)i;
                v25[1] = (__int64)v24;
                *v24 = v25;
                i[1] = v25;
                return result;
              }
            }
          }
LABEL_43:
          __fastfail(3u);
        }
      }
      goto LABEL_28;
    }
    v9 = &a2[2 * *((int *)a2 + 17)];
    v10 = (__int64 *)*v9;
    if ( *(__int64 **)(*v9 + 8) != v9 )
      goto LABEL_43;
    v11 = (__int64 **)v9[1];
    if ( *v11 != v9 )
      goto LABEL_43;
    *v11 = v10;
    v10[1] = (__int64)v11;
    v12 = *i;
    if ( (__int64 **)(*i)[1] != i )
      goto LABEL_43;
    v13 = &a2[2 * *((int *)a2 + 17)];
    *v13 = (__int64)v12;
    v13[1] = (__int64)i;
    v12[1] = (__int64)v13;
    *i = v13;
    LeaveSyncList(a1, a2[10]);
    if ( !DoEnterSyncList(a1, a2[11], 1) )
      goto LABEL_16;
  }
  while ( DoEnterSyncList(a1, a2[10], 1) );
  LeaveSyncList(a1, a2[11]);
LABEL_16:
  a2[11] = 0;
  return 1450;
}

```

## disassembly

```asm
0x18000e4c0  push    rbx
0x18000e4c2  push    rbp
0x18000e4c3  push    rsi
0x18000e4c4  push    rdi
0x18000e4c5  push    r14
0x18000e4c7  sub     rsp, 20h
0x18000e4cb  mov     r14d, r8d
0x18000e4ce  mov     rbx, rdx
0x18000e4d1  mov     rbp, rcx
0x18000e4d4  movsxd  rax, dword ptr [rbx+44h]
0x18000e4d8  add     rax, rax
0x18000e4db  mov     rdi, [rbx+rax*8+8]
0x18000e4e0  jmp     loc_18000E662
0x18000e4e5  movsxd  rax, dword ptr [rbx+44h]
0x18000e4e9  mov     rsi, rdi
0x18000e4ec  shl     rax, 4
0x18000e4f0  sub     rsi, rax
0x18000e4f3  mov     eax, [rsi+40h]
0x18000e4f6  test    al, 1
0x18000e4f8  jnz     loc_18000E65E
0x18000e4fe  cmp     r14d, 0FFFFFFFBh
0x18000e502  jz      short loc_18000E510
0x18000e504  and     eax, 4
0x18000e507  cmp     eax, r14d
0x18000e50a  jnz     loc_18000E65E
0x18000e510  cmp     dword ptr [rbx+44h], 0
0x18000e514  jz      loc_18000E5F7
0x18000e51a  mov     rdx, [rbx+58h]
0x18000e51e  cmp     rdx, [rsi+48h]
0x18000e522  jz      loc_18000E5F7
0x18000e528  test    rdx, rdx
0x18000e52b  jz      short loc_18000E535
0x18000e52d  mov     rcx, rbp
0x18000e530  call    LeaveSyncList
0x18000e535  mov     rax, [rsi+48h]
0x18000e539  xor     r8d, r8d
0x18000e53c  mov     [rbx+58h], rax
0x18000e540  mov     rcx, rbp
0x18000e543  mov     rdx, [rsi+48h]
0x18000e547  call    DoEnterSyncList
0x18000e54c  test    al, al
0x18000e54e  jnz     loc_18000E5F7
0x18000e554  movsxd  rcx, dword ptr [rbx+44h]
0x18000e558  shl     rcx, 4
0x18000e55c  add     rcx, rbx
0x18000e55f  mov     rdx, [rcx]
0x18000e562  cmp     [rdx+8], rcx
0x18000e566  jnz     loc_18000E75A
0x18000e56c  mov     rax, [rcx+8]
0x18000e570  cmp     [rax], rcx
0x18000e573  jnz     loc_18000E75A
0x18000e579  mov     [rax], rdx
0x18000e57c  mov     [rdx+8], rax
0x18000e580  mov     rdx, [rdi]
0x18000e583  cmp     [rdx+8], rdi
0x18000e587  jnz     loc_18000E75A
0x18000e58d  movsxd  rcx, dword ptr [rbx+44h]
0x18000e591  shl     rcx, 4
0x18000e595  add     rcx, rbx
0x18000e598  mov     [rcx], rdx
0x18000e59b  mov     [rcx+8], rdi
0x18000e59f  mov     [rdx+8], rcx
0x18000e5a3  mov     [rdi], rcx
0x18000e5a6  mov     rcx, rbp
0x18000e5a9  mov     rdx, [rbx+50h]
0x18000e5ad  call    LeaveSyncList
0x18000e5b2  mov     rdx, [rbx+58h]
0x18000e5b6  mov     r8b, 1
0x18000e5b9  mov     rcx, rbp
0x18000e5bc  call    DoEnterSyncList
0x18000e5c1  test    al, al
0x18000e5c3  jz      short loc_18000E5E8
0x18000e5c5  mov     rdx, [rbx+50h]
0x18000e5c9  mov     r8b, 1
0x18000e5cc  mov     rcx, rbp
0x18000e5cf  call    DoEnterSyncList
0x18000e5d4  test    al, al
0x18000e5d6  jnz     loc_18000E4D4
0x18000e5dc  mov     rdx, [rbx+58h]
0x18000e5e0  mov     rcx, rbp
0x18000e5e3  call    LeaveSyncList
0x18000e5e8  mov     qword ptr [rbx+58h], 0
0x18000e5f0  mov     eax, 5AAh
0x18000e5f5  jmp     short loc_18000E63F
0x18000e5f7  mov     ecx, [rbx+44h]
0x18000e5fa  test    ecx, ecx
0x18000e5fc  jz      short loc_18000E603
0x18000e5fe  cmp     ecx, 1
0x18000e601  jnz     short loc_18000E65E
0x18000e603  test    byte ptr [rbx+64h], 4
0x18000e607  jz      short loc_18000E611
0x18000e609  mov     eax, [rsi+5Ch]
0x18000e60c  cmp     [rbx+70h], eax
0x18000e60f  jnz     short loc_18000E65E
0x18000e611  test    byte ptr [rbx+64h], 1
0x18000e615  jz      short loc_18000E64A
0x18000e617  mov     rax, [rbp+120h]
0x18000e61e  lea     rdx, [rsi+74h]
0x18000e622  lea     rcx, [rbx+88h]
0x18000e629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e62e  test    eax, eax
0x18000e630  jz      short loc_18000E64A
0x18000e632  jle     short loc_18000E65E
0x18000e634  cmp     dword ptr [rbx+44h], 0
0x18000e638  jnz     short loc_18000E65E
0x18000e63a  mov     eax, 103h
0x18000e63f  add     rsp, 20h
0x18000e643  pop     r14
0x18000e645  pop     rdi
0x18000e646  pop     rsi
0x18000e647  pop     rbp
0x18000e648  pop     rbx
0x18000e649  retn
0x18000e64a  test    byte ptr [rbx+64h], 8
0x18000e64e  jz      loc_18000E701
0x18000e654  test    byte ptr [rsi+40h], 2
0x18000e658  jnz     loc_18000E701
0x18000e65e  mov     rdi, [rdi+8]
0x18000e662  cmp     rdi, [rbx+48h]
0x18000e666  jnz     loc_18000E4E5
0x18000e66c  cmp     dword ptr [rbx+44h], 0
0x18000e670  jnz     short loc_18000E63A
0x18000e672  test    byte ptr [rbx+64h], 1
0x18000e676  jnz     short loc_18000E63A
0x18000e678  mov     eax, [rbp+114h]
0x18000e67e  dec     eax
0x18000e680  movsxd  rcx, eax
0x18000e683  shl     rcx, 5
0x18000e687  add     rcx, [rbp+100h]
0x18000e68e  cmp     [rbx+50h], rcx
0x18000e692  jz      short loc_18000E63A
0x18000e694  mov     rax, [rbx]
0x18000e697  cmp     [rax+8], rbx
0x18000e69b  jnz     loc_18000E75A
0x18000e6a1  mov     rcx, [rbx+8]
0x18000e6a5  cmp     [rcx], rbx
0x18000e6a8  jnz     loc_18000E75A
0x18000e6ae  mov     [rcx], rax
0x18000e6b1  mov     [rax+8], rcx
0x18000e6b5  mov     rcx, rbp
0x18000e6b8  mov     rdx, [rbx+50h]
0x18000e6bc  call    LeaveSyncList
0x18000e6c1  add     qword ptr [rbx+50h], 20h ; ' '
0x18000e6c6  mov     r8b, 1
0x18000e6c9  mov     rdx, [rbx+50h]
0x18000e6cd  mov     rcx, rbp
0x18000e6d0  lea     rax, [rdx+10h]
0x18000e6d4  mov     [rbx+48h], rax
0x18000e6d8  call    DoEnterSyncList
0x18000e6dd  test    al, al
0x18000e6df  jz      short loc_18000E74E
0x18000e6e1  mov     rax, [rbx+48h]
0x18000e6e5  mov     rcx, [rax+8]
0x18000e6e9  cmp     [rcx], rax
0x18000e6ec  jnz     short loc_18000E75A
0x18000e6ee  mov     [rbx], rax
0x18000e6f1  mov     [rbx+8], rcx
0x18000e6f5  mov     [rcx], rbx
0x18000e6f8  mov     [rax+8], rbx
0x18000e6fc  jmp     loc_18000E4D4
0x18000e701  movsxd  rcx, dword ptr [rbx+44h]
0x18000e705  shl     rcx, 4
0x18000e709  add     rcx, rbx
0x18000e70c  mov     rdx, [rcx]
0x18000e70f  cmp     [rdx+8], rcx
0x18000e713  jnz     short loc_18000E75A
0x18000e715  mov     rax, [rcx+8]
0x18000e719  cmp     [rax], rcx
0x18000e71c  jnz     short loc_18000E75A
0x18000e71e  mov     [rax], rdx
0x18000e721  mov     [rdx+8], rax
0x18000e725  mov     rdx, [rdi+8]
0x18000e729  cmp     [rdx], rdi
0x18000e72c  jnz     short loc_18000E75A
0x18000e72e  movsxd  rcx, dword ptr [rbx+44h]
0x18000e732  shl     rcx, 4
0x18000e736  add     rcx, rbx
0x18000e739  xor     eax, eax
0x18000e73b  mov     [rcx], rdi
0x18000e73e  mov     [rcx+8], rdx
0x18000e742  mov     [rdx], rcx
0x18000e745  mov     [rdi+8], rcx
0x18000e749  jmp     loc_18000E63F
0x18000e74e  mov     [rbx+8], rbx
0x18000e752  mov     [rbx], rbx
0x18000e755  jmp     loc_18000E5F0
0x18000e75a  mov     ecx, 3
0x18000e75f  int     29h; Win8: RtlFailFast(ecx)
```

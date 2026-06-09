# TTDirectoryEntryOffset

- ea: `0x1800153d0`
- end: `0x180015695`
- name: `TTDirectoryEntryOffset`
- size: `709`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800119f8`
- `0x180013514`
- `0x180014cd4`

## callees

- `0x180015190`
- `0x1800153d0`
- `0x18001cd3c`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall TTDirectoryEntryOffset(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // edi
  unsigned __int8 v4; // al
  unsigned int v5; // r10d
  unsigned __int16 v6; // r13
  unsigned __int16 v7; // r15
  __int64 v8; // r8
  unsigned __int16 v9; // r12
  unsigned __int16 v10; // si
  unsigned __int16 i; // r14
  char v12; // dl
  unsigned int v13; // ecx
  unsigned int v15; // r9d
  __int64 v16; // rcx
  int v17; // edx
  unsigned __int16 v18; // r8
  unsigned int v19; // ecx
  __int64 v20; // rax
  unsigned __int16 v21; // dx
  __int16 v22; // ax
  int v23; // r8d
  unsigned __int16 v24; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v25; // [rsp+38h] [rbp-40h]
  __int128 v26; // [rsp+40h] [rbp-38h] BYREF
  __int64 v27; // [rsp+50h] [rbp-28h] BYREF
  int v28; // [rsp+58h] [rbp-20h]

  v2 = *(_DWORD *)(a1 + 12);
  v25 = a2;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  v26 = 0;
  if ( (unsigned __int16)ReadGeneric(
                           (__int64 *)a1,
                           (__int64)&v27,
                           0xCu,
                           (unsigned __int8 *)OFFSET_TABLE_CONTROL,
                           v2,
                           &v24) )
    return 0xFFFFFFFFLL;
  v4 = DIRECTORY_NO_XLATE_CONTROL[0];
  v5 = v2 + v24;
  v6 = WORD2(v27);
  v7 = 0;
  LOBYTE(v24) = DIRECTORY_NO_XLATE_CONTROL[0];
  while ( v7 < v6 )
  {
    v8 = v5;
    v9 = v4;
    v10 = 0;
    for ( i = 1; i <= v9; ++i )
    {
      v12 = DIRECTORY_NO_XLATE_CONTROL[i];
      if ( (v12 & 7) == 1 )
      {
        if ( (unsigned __int64)v10 + 1 > 0x10 )
          return 0xFFFFFFFFLL;
        if ( (v12 & 0x10) != 0 )
        {
          *((_BYTE *)&v26 + v10) = 0;
        }
        else
        {
          if ( (unsigned __int16)ReadByte(a1, (char *)&v26 + v10, v8) )
            return 0xFFFFFFFFLL;
          v8 = (unsigned int)(v23 + 1);
        }
        v22 = 1;
      }
      else if ( (DIRECTORY_NO_XLATE_CONTROL[i] & 7) == 2 )
      {
        if ( (unsigned __int64)v10 + 2 > 0x10 )
          return 0xFFFFFFFFLL;
        if ( (v12 & 0x10) != 0 )
        {
          v21 = 0;
        }
        else
        {
          if ( (v12 & 0x20) != 0 )
          {
            if ( !*(_QWORD *)a1 )
              return 0xFFFFFFFFLL;
            v13 = v8 + 2;
            if ( (int)v8 + 2 < (unsigned int)v8 || v13 > *(_DWORD *)(a1 + 8) )
              return 0xFFFFFFFFLL;
            v21 = *(_WORD *)((unsigned int)v8 + *(_QWORD *)a1);
          }
          else
          {
            if ( !*(_QWORD *)a1 )
              return 0xFFFFFFFFLL;
            v13 = v8 + 2;
            if ( (int)v8 + 2 < (unsigned int)v8 || v13 > *(_DWORD *)(a1 + 8) )
              return 0xFFFFFFFFLL;
            v21 = _byteswap_ushort(*(_WORD *)((unsigned int)v8 + *(_QWORD *)a1));
          }
          v8 = v13;
        }
        *(_WORD *)((char *)&v26 + v10) = v21;
        v22 = 2;
      }
      else
      {
        if ( (DIRECTORY_NO_XLATE_CONTROL[i] & 7) != 4 || (unsigned __int64)v10 + 4 > 0x10 )
          return 0xFFFFFFFFLL;
        if ( (v12 & 0x10) != 0 )
        {
          v17 = 0;
        }
        else if ( (v12 & 0x20) != 0 )
        {
          if ( !*(_QWORD *)a1 )
            return 0xFFFFFFFFLL;
          v19 = v8 + 4;
          if ( (int)v8 + 4 < (unsigned int)v8 || v19 > *(_DWORD *)(a1 + 8) )
            return 0xFFFFFFFFLL;
          v20 = (unsigned int)v8;
          v8 = v19;
          v17 = *(_DWORD *)(v20 + *(_QWORD *)a1);
        }
        else
        {
          if ( !*(_QWORD *)a1 )
            return 0xFFFFFFFFLL;
          v15 = v8 + 4;
          if ( (int)v8 + 4 < (unsigned int)v8 || v15 > *(_DWORD *)(a1 + 8) )
            return 0xFFFFFFFFLL;
          v16 = (unsigned int)v8;
          v8 = v15;
          v17 = *(unsigned __int8 *)(v16 + *(_QWORD *)a1 + 3)
              | ((*(unsigned __int8 *)(v16 + *(_QWORD *)a1 + 2)
                | (((*(unsigned __int8 *)(v16 + *(_QWORD *)a1) << 8) | *(unsigned __int8 *)(v16 + *(_QWORD *)a1 + 1)) << 8)) << 8);
        }
        v22 = 4;
        *(_DWORD *)((char *)&v26 + v10) = v17;
      }
      v10 += v22;
    }
    if ( v10 < 0x10u )
      return 0xFFFFFFFFLL;
    v18 = v8 - v5;
    if ( *v25 == (_DWORD)v26 )
      return v5;
    v5 += v18;
    v4 = v24;
    ++v7;
  }
  return 0;
}

```

## disassembly

```asm
0x1800153d0  push    rbp
0x1800153d2  push    rbx
0x1800153d3  push    rsi
0x1800153d4  push    rdi
0x1800153d5  push    r12
0x1800153d7  push    r13
0x1800153d9  push    r14
0x1800153db  push    r15
0x1800153dd  mov     rbp, rsp
0x1800153e0  sub     rsp, 78h
0x1800153e4  mov     rax, cs:__security_cookie
0x1800153eb  xor     rax, rsp
0x1800153ee  mov     [rbp+var_18], rax
0x1800153f2  mov     edi, [rcx+0Ch]
0x1800153f5  lea     r9, OFFSET_TABLE_CONTROL
0x1800153fc  xor     eax, eax
0x1800153fe  mov     [rbp+var_40], rdx
0x180015402  mov     [rbp+var_48], ax
0x180015406  lea     rdx, [rbp+var_28]
0x18001540a  mov     [rbp+var_28], rax
0x18001540e  xorps   xmm0, xmm0
0x180015411  mov     [rbp+var_20], eax
0x180015414  mov     rbx, rcx
0x180015417  lea     r8d, [rax+0Ch]
0x18001541b  lea     rax, [rbp+var_48]
0x18001541f  mov     [rsp+78h+var_50], rax
0x180015424  mov     [rsp+78h+var_58], edi
0x180015428  movups  [rbp+var_38], xmm0
0x18001542c  call    ReadGeneric
0x180015431  xor     r9d, r9d
0x180015434  test    ax, ax
0x180015437  jnz     loc_1800154E1
0x18001543d  movzx   r10d, [rbp+var_48]
0x180015442  lea     r11d, [r9+10h]
0x180015446  mov     al, cs:DIRECTORY_NO_XLATE_CONTROL
0x18001544c  add     r10d, edi
0x18001544f  movzx   r13d, word ptr [rbp+var_28+4]
0x180015454  lea     edi, [r9+1]
0x180015458  mov     r15d, r9d
0x18001545b  mov     byte ptr [rbp+var_48], al
0x18001545e  cmp     r15w, r13w
0x180015462  jnb     loc_18001568E
0x180015468  mov     r8d, r10d
0x18001546b  movzx   r12d, al
0x18001546f  mov     esi, r9d
0x180015472  movzx   r14d, di
0x180015476  cmp     r14w, r12w
0x18001547a  ja      loc_180015572
0x180015480  lea     rcx, DIRECTORY_NO_XLATE_CONTROL
0x180015487  movzx   eax, r14w
0x18001548b  movzx   edx, byte ptr [rax+rcx]
0x18001548f  mov     ecx, edx
0x180015491  and     ecx, 7
0x180015494  sub     ecx, 1
0x180015497  jz      loc_1800155ED
0x18001549d  sub     ecx, 1
0x1800154a0  jnz     short loc_180015501
0x1800154a2  movzx   ecx, si
0x1800154a5  lea     rax, [rcx+2]
0x1800154a9  cmp     rax, r11
0x1800154ac  ja      short loc_1800154E1
0x1800154ae  lea     r11, [rbp+var_38]
0x1800154b2  add     r11, rcx
0x1800154b5  test    dl, 10h
0x1800154b8  jnz     loc_1800155CF
0x1800154be  test    dl, 20h
0x1800154c1  jnz     loc_18001560C
0x1800154c7  mov     r9, [rbx]
0x1800154ca  test    r9, r9
0x1800154cd  jz      short loc_1800154E1
0x1800154cf  lea     ecx, [r8+2]
0x1800154d3  cmp     ecx, r8d
0x1800154d6  jb      short loc_1800154E1
0x1800154d8  cmp     ecx, [rbx+8]
0x1800154db  jbe     loc_18001566E
0x1800154e1  or      eax, 0FFFFFFFFh
0x1800154e4  mov     rcx, [rbp+var_18]
0x1800154e8  xor     rcx, rsp; StackCookie
0x1800154eb  call    __security_check_cookie
0x1800154f0  add     rsp, 78h
0x1800154f4  pop     r15
0x1800154f6  pop     r14
0x1800154f8  pop     r13
0x1800154fa  pop     r12
0x1800154fc  pop     rdi
0x1800154fd  pop     rsi
0x1800154fe  pop     rbx
0x1800154ff  pop     rbp
0x180015500  retn
0x180015501  cmp     ecx, 2
0x180015504  jnz     short loc_1800154E1
0x180015506  movzx   ecx, si
0x180015509  lea     rax, [rcx+4]
0x18001550d  cmp     rax, r11
0x180015510  ja      short loc_1800154E1
0x180015512  lea     rdi, [rbp+var_38]
0x180015516  add     rdi, rcx
0x180015519  test    r11b, dl
0x18001551c  jnz     loc_180015637
0x180015522  test    dl, 20h
0x180015525  jnz     short loc_1800155A2
0x180015527  mov     r11, [rbx]
0x18001552a  test    r11, r11
0x18001552d  jz      short loc_1800154E1
0x18001552f  lea     r9d, [r8+4]
0x180015533  cmp     r9d, r8d
0x180015536  jb      short loc_1800154E1
0x180015538  cmp     r9d, [rbx+8]
0x18001553c  ja      short loc_1800154E1
0x18001553e  mov     ecx, r8d
0x180015541  mov     r8d, r9d
0x180015544  movzx   eax, byte ptr [rcx+r11]
0x180015549  movzx   edx, byte ptr [rcx+r11+1]
0x18001554f  shl     eax, 8
0x180015552  or      edx, eax
0x180015554  movzx   eax, byte ptr [rcx+r11+2]
0x18001555a  shl     edx, 8
0x18001555d  or      edx, eax
0x18001555f  movzx   eax, byte ptr [rcx+r11+3]
0x180015565  shl     edx, 8
0x180015568  or      edx, eax
0x18001556a  xor     r9d, r9d
0x18001556d  jmp     loc_18001563A
0x180015572  cmp     si, r11w
0x180015576  jb      loc_1800154E1
0x18001557c  mov     rcx, [rbp+var_40]
0x180015580  sub     r8w, r10w
0x180015584  mov     eax, dword ptr [rbp+var_38]
0x180015587  cmp     [rcx], eax
0x180015589  jz      loc_180015666
0x18001558f  movzx   eax, r8w
0x180015593  add     r10d, eax
0x180015596  mov     al, byte ptr [rbp+var_48]
0x180015599  add     r15w, di
0x18001559d  jmp     loc_18001545E
0x1800155a2  mov     rdx, [rbx]
0x1800155a5  test    rdx, rdx
0x1800155a8  jz      loc_1800154E1
0x1800155ae  lea     ecx, [r8+4]
0x1800155b2  cmp     ecx, r8d
0x1800155b5  jb      loc_1800154E1
0x1800155bb  cmp     ecx, [rbx+8]
0x1800155be  ja      loc_1800154E1
0x1800155c4  mov     eax, r8d
0x1800155c7  mov     r8d, ecx
0x1800155ca  mov     edx, [rax+rdx]
0x1800155cd  jmp     short loc_18001563A
0x1800155cf  mov     edx, r9d
0x1800155d2  mov     [r11], dx
0x1800155d6  mov     eax, 2
0x1800155db  add     r14w, di
0x1800155df  mov     r11d, 10h
0x1800155e5  add     si, ax
0x1800155e8  jmp     loc_180015476
0x1800155ed  movzx   ecx, si
0x1800155f0  lea     rax, [rcx+1]
0x1800155f4  cmp     rax, r11
0x1800155f7  ja      loc_1800154E1
0x1800155fd  test    r11b, dl
0x180015600  jz      short loc_180015646
0x180015602  mov     byte ptr [rbp+rcx+var_38], r9b
0x180015607  movzx   eax, di
0x18001560a  jmp     short loc_1800155DB
0x18001560c  mov     rdx, [rbx]
0x18001560f  test    rdx, rdx
0x180015612  jz      loc_1800154E1
0x180015618  lea     ecx, [r8+2]
0x18001561c  cmp     ecx, r8d
0x18001561f  jb      loc_1800154E1
0x180015625  cmp     ecx, [rbx+8]
0x180015628  ja      loc_1800154E1
0x18001562e  mov     eax, r8d
0x180015631  movzx   edx, word ptr [rax+rdx]
0x180015635  jmp     short loc_180015686
0x180015637  mov     edx, r9d
0x18001563a  mov     eax, 4
0x18001563f  mov     [rdi], edx
0x180015641  lea     edi, [rax-3]
0x180015644  jmp     short loc_1800155DB
0x180015646  lea     rdx, [rbp+var_38]
0x18001564a  add     rdx, rcx
0x18001564d  mov     rcx, rbx
0x180015650  call    ReadByte
0x180015655  xor     r9d, r9d
0x180015658  test    ax, ax
0x18001565b  jnz     loc_1800154E1
0x180015661  add     r8d, edi
0x180015664  jmp     short loc_180015607
0x180015666  mov     eax, r10d
0x180015669  jmp     loc_1800154E4
0x18001566e  mov     eax, r8d
0x180015671  movzx   edx, byte ptr [rax+r9+1]
0x180015677  movzx   eax, byte ptr [rax+r9]
0x18001567c  shl     ax, 8
0x180015680  or      dx, ax
0x180015683  xor     r9d, r9d
0x180015686  mov     r8d, ecx
0x180015689  jmp     loc_1800155D2
0x18001568e  xor     eax, eax
0x180015690  jmp     loc_1800154E4
```

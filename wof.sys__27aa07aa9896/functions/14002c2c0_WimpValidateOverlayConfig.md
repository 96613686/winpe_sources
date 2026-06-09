# WimpValidateOverlayConfig

- ea: `0x14002c2c0`
- end: `0x14002c556`
- name: `WimpValidateOverlayConfig`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14003c5c8`

## callees

- `0x14000ff38`
- `0x140010078`
- `0x1400100cc`
- `0x140010138`
- `0x1400101bc`
- `0x14002c2c0`
- `0x14002c55c`

## pseudocode

```c
__int64 __fastcall WimpValidateOverlayConfig(_DWORD *a1, unsigned int a2)
{
  unsigned int v2; // ebx
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rbx
  int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r10
  unsigned int v11; // r11d
  unsigned int i; // r11d
  __int64 v13; // rax
  __int64 v14; // rbp
  __int64 v15; // r14
  unsigned int v16; // esi
  __int64 v17; // r8
  unsigned int v18; // r11d

  if ( *a1 == 1715695447 )
  {
    if ( a1[1] == 1 )
    {
      v5 = (unsigned int)a1[2];
      if ( (unsigned int)v5 < 0x28 )
      {
        v2 = -1073741116;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
            (unsigned int)v5,
            -1073741116);
        return v2;
      }
      v6 = (unsigned int)a1[3];
      if ( (_DWORD)v6 )
      {
        if ( (unsigned int)v6 > 0x100 )
        {
          v2 = -1073741116;
          v3 = WPP_GLOBAL_Control;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v4 = 13;
            goto LABEL_5;
          }
          return v2;
        }
        v7 = v6 * v5;
        if ( !is_mul_ok(v6, v5) )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_dd(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
              (unsigned int)v5,
              -1073741675);
          return (unsigned int)-1073741116;
        }
        if ( !(unsigned __int8)WimpValidateRange(a1, a2, a1 + 6, v6 * v5) )
        {
          v2 = -1073741116;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_ddd(WPP_GLOBAL_Control->AttachedDevice, v8, v9, v11, v7);
          return v2;
        }
        for ( i = 0; i < (unsigned int)v6; i = v18 + 1 )
        {
          v13 = i * (unsigned int)v5;
          v14 = v13;
          v15 = *(unsigned int *)(v10 + v13 + 32);
          v16 = *(_DWORD *)(v10 + v13 + 36);
          if ( !(unsigned __int8)WimpValidateRange(v10, v8, v15 + v10, v16) )
          {
            v2 = -1073741116;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_diddd(WPP_GLOBAL_Control->AttachedDevice, v8, v17, v18, *(_QWORD *)(v10 + v14 + 24), v16, v15);
            return v2;
          }
          if ( v16 < 0xC || *(_DWORD *)(v17 + 8) < v16 )
          {
            v2 = -1073741116;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_didd(WPP_GLOBAL_Control->AttachedDevice, v8, v17, v18, *(_QWORD *)(v10 + v14 + 24), v16);
            return v2;
          }
        }
      }
      return 0;
    }
    v2 = -1073741116;
    v3 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v4 = 11;
      goto LABEL_5;
    }
  }
  else
  {
    v2 = -1073741116;
    v3 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v4 = 10;
LABEL_5:
      WPP_SF_Dd(v3->AttachedDevice, v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14002c2c0  mov     [rsp+arg_8], rbx
0x14002c2c5  mov     [rsp+arg_10], rbp
0x14002c2ca  push    rsi
0x14002c2cb  push    rdi
0x14002c2cc  push    r14
0x14002c2ce  sub     rsp, 40h
0x14002c2d2  mov     r9d, [rcx]
0x14002c2d5  mov     r8d, 66436F57h
0x14002c2db  mov     r11d, edx
0x14002c2de  mov     r10, rcx
0x14002c2e1  cmp     r9d, r8d
0x14002c2e4  jz      short loc_14002C31C
0x14002c2e6  mov     ebx, 0C00002C4h
0x14002c2eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c2f2  test    dword ptr [rcx+2Ch], 400h
0x14002c2f9  jz      loc_14002C540
0x14002c2ff  cmp     byte ptr [rcx+29h], 2
0x14002c303  jb      loc_14002C540
0x14002c309  mov     edx, 0Ah
0x14002c30e  mov     rcx, [rcx+18h]
0x14002c312  call    WPP_SF_Dd
0x14002c317  jmp     loc_14002C540
0x14002c31c  mov     r9d, [rcx+4]
0x14002c320  cmp     r9d, 1
0x14002c324  jz      short loc_14002C350
0x14002c326  mov     ebx, 0C00002C4h
0x14002c32b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c332  test    dword ptr [rcx+2Ch], 400h
0x14002c339  jz      loc_14002C540
0x14002c33f  cmp     byte ptr [rcx+29h], 2
0x14002c343  jb      loc_14002C540
0x14002c349  mov     edx, 0Bh
0x14002c34e  jmp     short loc_14002C30E
0x14002c350  mov     edi, [rcx+8]
0x14002c353  cmp     edi, 28h ; '('
0x14002c356  jnb     short loc_14002C39C
0x14002c358  mov     ebx, 0C00002C4h
0x14002c35d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c364  test    dword ptr [rcx+2Ch], 400h
0x14002c36b  jz      loc_14002C540
0x14002c371  cmp     byte ptr [rcx+29h], 2
0x14002c375  jb      loc_14002C540
0x14002c37b  mov     rcx, [rcx+18h]
0x14002c37f  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002c386  mov     edx, 0Ch
0x14002c38b  mov     dword ptr [rsp+58h+var_38], ebx
0x14002c38f  mov     r9d, edi
0x14002c392  call    WPP_SF_dd
0x14002c397  jmp     loc_14002C540
0x14002c39c  mov     ebx, [rcx+0Ch]
0x14002c39f  test    ebx, ebx
0x14002c3a1  jz      loc_14002C53E
0x14002c3a7  cmp     ebx, 100h
0x14002c3ad  jbe     short loc_14002C3DF
0x14002c3af  mov     ebx, 0C00002C4h
0x14002c3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c3bb  test    dword ptr [rcx+2Ch], 400h
0x14002c3c2  jz      loc_14002C540
0x14002c3c8  cmp     byte ptr [rcx+29h], 2
0x14002c3cc  jb      loc_14002C540
0x14002c3d2  mov     edx, 0Dh
0x14002c3d7  mov     r9d, r8d
0x14002c3da  jmp     loc_14002C30E
0x14002c3df  mov     rax, rdi
0x14002c3e2  mov     [rsp+58h+arg_0], 0
0x14002c3eb  mul     rbx
0x14002c3ee  mov     rsi, rax
0x14002c3f1  test    rdx, rdx
0x14002c3f4  jnz     loc_14002C501
0x14002c3fa  mov     rdx, r11
0x14002c3fd  lea     r8, [rcx+18h]
0x14002c401  mov     r9, rax
0x14002c404  call    WimpValidateRange
0x14002c409  test    al, al
0x14002c40b  jnz     short loc_14002C445
0x14002c40d  mov     ebx, 0C00002C4h
0x14002c412  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c419  test    dword ptr [rcx+2Ch], 400h
0x14002c420  jz      loc_14002C540
0x14002c426  cmp     byte ptr [rcx+29h], 2
0x14002c42a  jb      loc_14002C540
0x14002c430  mov     rcx, [rcx+18h]
0x14002c434  mov     r9d, r11d
0x14002c437  mov     dword ptr [rsp+58h+var_38], esi
0x14002c43b  call    WPP_SF_ddd
0x14002c440  jmp     loc_14002C540
0x14002c445  xor     r11d, r11d
0x14002c448  cmp     r11d, ebx
0x14002c44b  jnb     loc_14002C53E
0x14002c451  mov     eax, edi
0x14002c453  mov     rcx, r10
0x14002c456  imul    eax, r11d
0x14002c45a  mov     ebp, eax
0x14002c45c  mov     r14d, [r10+rax+20h]
0x14002c461  mov     esi, [r10+rax+24h]
0x14002c466  mov     r9d, esi
0x14002c469  lea     r8, [r14+r10]
0x14002c46d  call    WimpValidateRange
0x14002c472  test    al, al
0x14002c474  jz      short loc_14002C4C5
0x14002c476  cmp     esi, 0Ch
0x14002c479  jb      short loc_14002C486
0x14002c47b  cmp     [r8+8], esi
0x14002c47f  jb      short loc_14002C486
0x14002c481  inc     r11d
0x14002c484  jmp     short loc_14002C448
0x14002c486  mov     ebx, 0C00002C4h
0x14002c48b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c492  test    dword ptr [rcx+2Ch], 400h
0x14002c499  jz      loc_14002C540
0x14002c49f  cmp     byte ptr [rcx+29h], 2
0x14002c4a3  jb      loc_14002C540
0x14002c4a9  mov     rax, [r10+rbp+18h]
0x14002c4ae  mov     r9d, r11d
0x14002c4b1  mov     rcx, [rcx+18h]
0x14002c4b5  mov     [rsp+58h+var_30], esi
0x14002c4b9  mov     [rsp+58h+var_38], rax
0x14002c4be  call    WPP_SF_didd
0x14002c4c3  jmp     short loc_14002C540
0x14002c4c5  mov     ebx, 0C00002C4h
0x14002c4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c4d1  test    dword ptr [rcx+2Ch], 400h
0x14002c4d8  jz      short loc_14002C540
0x14002c4da  cmp     byte ptr [rcx+29h], 2
0x14002c4de  jb      short loc_14002C540
0x14002c4e0  mov     rax, [r10+rbp+18h]
0x14002c4e5  mov     r9d, r11d
0x14002c4e8  mov     rcx, [rcx+18h]
0x14002c4ec  mov     [rsp+58h+var_28], r14d
0x14002c4f1  mov     [rsp+58h+var_30], esi
0x14002c4f5  mov     [rsp+58h+var_38], rax
0x14002c4fa  call    WPP_SF_diddd
0x14002c4ff  jmp     short loc_14002C540
0x14002c501  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c508  test    dword ptr [rcx+2Ch], 400h
0x14002c50f  jz      short loc_14002C537
0x14002c511  cmp     byte ptr [rcx+29h], 2
0x14002c515  jb      short loc_14002C537
0x14002c517  mov     rcx, [rcx+18h]
0x14002c51b  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002c522  mov     edx, 0Eh
0x14002c527  mov     dword ptr [rsp+58h+var_38], 0C0000095h
0x14002c52f  mov     r9d, edi
0x14002c532  call    WPP_SF_dd
0x14002c537  mov     ebx, 0C00002C4h
0x14002c53c  jmp     short loc_14002C540
0x14002c53e  xor     ebx, ebx
0x14002c540  mov     rbp, [rsp+58h+arg_10]
0x14002c545  mov     eax, ebx
0x14002c547  mov     rbx, [rsp+58h+arg_8]
0x14002c54c  add     rsp, 40h
0x14002c550  pop     r14
0x14002c552  pop     rdi
0x14002c553  pop     rsi
0x14002c554  retn
```

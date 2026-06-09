# WimpValidateOverlayConfig

- ea: `0x14002c270`
- end: `0x14002c506`
- name: `WimpValidateOverlayConfig`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14003c578`

## callees

- `0x14000ff38`
- `0x140010078`
- `0x1400100cc`
- `0x140010138`
- `0x1400101bc`
- `0x14002c270`
- `0x14002c50c`

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
0x14002c270  mov     [rsp+arg_8], rbx
0x14002c275  mov     [rsp+arg_10], rbp
0x14002c27a  push    rsi
0x14002c27b  push    rdi
0x14002c27c  push    r14
0x14002c27e  sub     rsp, 40h
0x14002c282  mov     r9d, [rcx]
0x14002c285  mov     r8d, 66436F57h
0x14002c28b  mov     r11d, edx
0x14002c28e  mov     r10, rcx
0x14002c291  cmp     r9d, r8d
0x14002c294  jz      short loc_14002C2CC
0x14002c296  mov     ebx, 0C00002C4h
0x14002c29b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c2a2  test    dword ptr [rcx+2Ch], 400h
0x14002c2a9  jz      loc_14002C4F0
0x14002c2af  cmp     byte ptr [rcx+29h], 2
0x14002c2b3  jb      loc_14002C4F0
0x14002c2b9  mov     edx, 0Ah
0x14002c2be  mov     rcx, [rcx+18h]
0x14002c2c2  call    WPP_SF_Dd
0x14002c2c7  jmp     loc_14002C4F0
0x14002c2cc  mov     r9d, [rcx+4]
0x14002c2d0  cmp     r9d, 1
0x14002c2d4  jz      short loc_14002C300
0x14002c2d6  mov     ebx, 0C00002C4h
0x14002c2db  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c2e2  test    dword ptr [rcx+2Ch], 400h
0x14002c2e9  jz      loc_14002C4F0
0x14002c2ef  cmp     byte ptr [rcx+29h], 2
0x14002c2f3  jb      loc_14002C4F0
0x14002c2f9  mov     edx, 0Bh
0x14002c2fe  jmp     short loc_14002C2BE
0x14002c300  mov     edi, [rcx+8]
0x14002c303  cmp     edi, 28h ; '('
0x14002c306  jnb     short loc_14002C34C
0x14002c308  mov     ebx, 0C00002C4h
0x14002c30d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c314  test    dword ptr [rcx+2Ch], 400h
0x14002c31b  jz      loc_14002C4F0
0x14002c321  cmp     byte ptr [rcx+29h], 2
0x14002c325  jb      loc_14002C4F0
0x14002c32b  mov     rcx, [rcx+18h]
0x14002c32f  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002c336  mov     edx, 0Ch
0x14002c33b  mov     dword ptr [rsp+58h+var_38], ebx
0x14002c33f  mov     r9d, edi
0x14002c342  call    WPP_SF_dd
0x14002c347  jmp     loc_14002C4F0
0x14002c34c  mov     ebx, [rcx+0Ch]
0x14002c34f  test    ebx, ebx
0x14002c351  jz      loc_14002C4EE
0x14002c357  cmp     ebx, 100h
0x14002c35d  jbe     short loc_14002C38F
0x14002c35f  mov     ebx, 0C00002C4h
0x14002c364  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c36b  test    dword ptr [rcx+2Ch], 400h
0x14002c372  jz      loc_14002C4F0
0x14002c378  cmp     byte ptr [rcx+29h], 2
0x14002c37c  jb      loc_14002C4F0
0x14002c382  mov     edx, 0Dh
0x14002c387  mov     r9d, r8d
0x14002c38a  jmp     loc_14002C2BE
0x14002c38f  mov     rax, rdi
0x14002c392  mov     [rsp+58h+arg_0], 0
0x14002c39b  mul     rbx
0x14002c39e  mov     rsi, rax
0x14002c3a1  test    rdx, rdx
0x14002c3a4  jnz     loc_14002C4B1
0x14002c3aa  mov     rdx, r11
0x14002c3ad  lea     r8, [rcx+18h]
0x14002c3b1  mov     r9, rax
0x14002c3b4  call    WimpValidateRange
0x14002c3b9  test    al, al
0x14002c3bb  jnz     short loc_14002C3F5
0x14002c3bd  mov     ebx, 0C00002C4h
0x14002c3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c3c9  test    dword ptr [rcx+2Ch], 400h
0x14002c3d0  jz      loc_14002C4F0
0x14002c3d6  cmp     byte ptr [rcx+29h], 2
0x14002c3da  jb      loc_14002C4F0
0x14002c3e0  mov     rcx, [rcx+18h]
0x14002c3e4  mov     r9d, r11d
0x14002c3e7  mov     dword ptr [rsp+58h+var_38], esi
0x14002c3eb  call    WPP_SF_ddd
0x14002c3f0  jmp     loc_14002C4F0
0x14002c3f5  xor     r11d, r11d
0x14002c3f8  cmp     r11d, ebx
0x14002c3fb  jnb     loc_14002C4EE
0x14002c401  mov     eax, edi
0x14002c403  mov     rcx, r10
0x14002c406  imul    eax, r11d
0x14002c40a  mov     ebp, eax
0x14002c40c  mov     r14d, [r10+rax+20h]
0x14002c411  mov     esi, [r10+rax+24h]
0x14002c416  mov     r9d, esi
0x14002c419  lea     r8, [r14+r10]
0x14002c41d  call    WimpValidateRange
0x14002c422  test    al, al
0x14002c424  jz      short loc_14002C475
0x14002c426  cmp     esi, 0Ch
0x14002c429  jb      short loc_14002C436
0x14002c42b  cmp     [r8+8], esi
0x14002c42f  jb      short loc_14002C436
0x14002c431  inc     r11d
0x14002c434  jmp     short loc_14002C3F8
0x14002c436  mov     ebx, 0C00002C4h
0x14002c43b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c442  test    dword ptr [rcx+2Ch], 400h
0x14002c449  jz      loc_14002C4F0
0x14002c44f  cmp     byte ptr [rcx+29h], 2
0x14002c453  jb      loc_14002C4F0
0x14002c459  mov     rax, [r10+rbp+18h]
0x14002c45e  mov     r9d, r11d
0x14002c461  mov     rcx, [rcx+18h]
0x14002c465  mov     [rsp+58h+var_30], esi
0x14002c469  mov     [rsp+58h+var_38], rax
0x14002c46e  call    WPP_SF_didd
0x14002c473  jmp     short loc_14002C4F0
0x14002c475  mov     ebx, 0C00002C4h
0x14002c47a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c481  test    dword ptr [rcx+2Ch], 400h
0x14002c488  jz      short loc_14002C4F0
0x14002c48a  cmp     byte ptr [rcx+29h], 2
0x14002c48e  jb      short loc_14002C4F0
0x14002c490  mov     rax, [r10+rbp+18h]
0x14002c495  mov     r9d, r11d
0x14002c498  mov     rcx, [rcx+18h]
0x14002c49c  mov     [rsp+58h+var_28], r14d
0x14002c4a1  mov     [rsp+58h+var_30], esi
0x14002c4a5  mov     [rsp+58h+var_38], rax
0x14002c4aa  call    WPP_SF_diddd
0x14002c4af  jmp     short loc_14002C4F0
0x14002c4b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c4b8  test    dword ptr [rcx+2Ch], 400h
0x14002c4bf  jz      short loc_14002C4E7
0x14002c4c1  cmp     byte ptr [rcx+29h], 2
0x14002c4c5  jb      short loc_14002C4E7
0x14002c4c7  mov     rcx, [rcx+18h]
0x14002c4cb  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002c4d2  mov     edx, 0Eh
0x14002c4d7  mov     dword ptr [rsp+58h+var_38], 0C0000095h
0x14002c4df  mov     r9d, edi
0x14002c4e2  call    WPP_SF_dd
0x14002c4e7  mov     ebx, 0C00002C4h
0x14002c4ec  jmp     short loc_14002C4F0
0x14002c4ee  xor     ebx, ebx
0x14002c4f0  mov     rbp, [rsp+58h+arg_10]
0x14002c4f5  mov     eax, ebx
0x14002c4f7  mov     rbx, [rsp+58h+arg_8]
0x14002c4fc  add     rsp, 40h
0x14002c500  pop     r14
0x14002c502  pop     rdi
0x14002c503  pop     rsi
0x14002c504  retn
```

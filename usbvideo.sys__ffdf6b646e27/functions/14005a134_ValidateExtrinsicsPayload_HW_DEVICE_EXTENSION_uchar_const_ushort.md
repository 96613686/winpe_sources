# ValidateExtrinsicsPayload(_HW_DEVICE_EXTENSION *,uchar const *,ushort)

- ea: `0x14005a134`
- end: `0x14005a372`
- name: `?ValidateExtrinsicsPayload@@YAJPEAU_HW_DEVICE_EXTENSION@@PEBEG@Z`
- size: `574`
- prototype: `__int64 __fastcall(struct _HW_DEVICE_EXTENSION *, const unsigned __int8 *, unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140056780`
- `0x14005a790`

## callees

- `0x1400051e4`
- `0x140019cd4`
- `0x14001b118`
- `0x14005a134`
- `0x14005c6d0`

## pseudocode

```c
__int64 __fastcall ValidateExtrinsicsPayload(
        struct _HW_DEVICE_EXTENSION *a1,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  unsigned int v3; // r13d
  int v4; // r14d
  int v5; // r9d
  const unsigned __int8 *v6; // rdi
  unsigned int v7; // r12d
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned __int8 v11; // r11
  unsigned __int64 v12; // rsi
  const unsigned __int8 *v13; // rdi
  unsigned int i; // ebx
  unsigned __int64 v15; // rbp
  int v16; // edx
  int v17; // eax
  int v19; // [rsp+20h] [rbp-58h]
  struct _HW_DEVICE_EXTENSION *v20; // [rsp+80h] [rbp+8h]

  v20 = a1;
  v3 = -1073741436;
  v4 = a3;
  v5 = *(unsigned __int8 *)(*((_QWORD *)a1 + 4) + 4LL);
  v6 = &a2[2 * a3];
  v7 = *v6;
  if ( v7 <= 2 * v5 )
  {
    if ( a3 < 0x35u )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a3, 53);
      return v3;
    }
    v11 = 2;
    v12 = (unsigned __int64)&v6[a3];
    v13 = v6 + 1;
    for ( i = 0; ; ++i )
    {
      if ( (int)i >= (int)v7 )
        return 0;
      if ( (unsigned __int64)(v13 + 8) > v12 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < v11 )
          return v3;
        v9 = 29;
        v19 = v4;
        goto LABEL_35;
      }
      v15 = *((unsigned __int16 *)v13 + 1);
      if ( (unsigned __int64)&v13[v15 + 4] > v12 )
        break;
      if ( !IsValidInterfaceNumber(a1, *v13) )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < v11 )
          return v3;
        v17 = v16;
        v9 = 31;
LABEL_28:
        v19 = v17;
LABEL_35:
        v10 = i;
        goto LABEL_5;
      }
      if ( v13[1] >= v11 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < v11 )
          return v3;
        v17 = v13[1];
        v9 = 32;
        goto LABEL_28;
      }
      if ( v15 < 44 * (unsigned __int64)*((unsigned int *)v13 + 1) + 4 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= v11 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, i);
        return v3;
      }
      a1 = v20;
      v13 += v15 + 4;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= v11 )
      WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v19 = v5;
      v9 = 27;
      v10 = *v6;
LABEL_5:
      WPP_SF_dd(v8->AttachedDevice, v9, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v10, v19);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14005a134  mov     [rsp+arg_0], rcx
0x14005a139  push    rbx
0x14005a13a  push    rbp
0x14005a13b  push    rsi
0x14005a13c  push    rdi
0x14005a13d  push    r12
0x14005a13f  push    r13
0x14005a141  push    r14
0x14005a143  push    r15
0x14005a145  sub     rsp, 38h
0x14005a149  mov     rax, [rcx+20h]
0x14005a14d  mov     r13d, 0C0000184h
0x14005a153  movzx   r14d, r8w
0x14005a157  movzx   r9d, byte ptr [rax+4]
0x14005a15c  lea     edi, [r14+r14]
0x14005a160  add     rdi, rdx
0x14005a163  lea     eax, [r9+r9]
0x14005a167  movzx   r12d, byte ptr [rdi]
0x14005a16b  cmp     r12d, eax
0x14005a16e  jbe     short loc_14005A1B6
0x14005a170  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a177  lea     rax, WPP_GLOBAL_Control
0x14005a17e  cmp     rcx, rax
0x14005a181  jz      loc_14005A35D
0x14005a187  mov     r11b, 2
0x14005a18a  cmp     [rcx+29h], r11b
0x14005a18e  jb      loc_14005A35D
0x14005a194  mov     [rsp+78h+var_58], r9d
0x14005a199  mov     edx, 1Bh
0x14005a19e  mov     r9d, r12d
0x14005a1a1  mov     rcx, [rcx+18h]
0x14005a1a5  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a1ac  call    WPP_SF_dd
0x14005a1b1  jmp     loc_14005A35D
0x14005a1b6  mov     r9d, 35h ; '5'
0x14005a1bc  cmp     r8w, r9w
0x14005a1c0  jnb     short loc_14005A1F4
0x14005a1c2  mov     rcx, cs:WPP_GLOBAL_Control; struct _HW_DEVICE_EXTENSION *
0x14005a1c9  lea     rax, WPP_GLOBAL_Control
0x14005a1d0  cmp     rcx, rax
0x14005a1d3  jz      loc_14005A35D
0x14005a1d9  mov     r11b, 2
0x14005a1dc  cmp     [rcx+29h], r11b
0x14005a1e0  jb      loc_14005A35D
0x14005a1e6  lea     edx, [r9-19h]
0x14005a1ea  mov     [rsp+78h+var_58], r9d
0x14005a1ef  mov     r9d, r14d
0x14005a1f2  jmp     short loc_14005A1A1
0x14005a1f4  movzx   esi, r8w
0x14005a1f8  mov     r11b, 2
0x14005a1fb  add     rsi, rdi
0x14005a1fe  inc     rdi
0x14005a201  xor     ebx, ebx
0x14005a203  cmp     ebx, r12d
0x14005a206  jge     loc_14005A35A
0x14005a20c  lea     rax, [rdi+8]
0x14005a210  cmp     rax, rsi
0x14005a213  ja      loc_14005A32F
0x14005a219  movzx   ebp, word ptr [rdi+2]
0x14005a21d  lea     r15, [rbp+4]
0x14005a221  add     r15, rdi
0x14005a224  cmp     r15, rsi
0x14005a227  ja      loc_14005A2F3
0x14005a22d  movzx   edx, byte ptr [rdi]; unsigned __int8
0x14005a230  call    ?IsValidInterfaceNumber@@YAEPEAU_HW_DEVICE_EXTENSION@@E@Z; IsValidInterfaceNumber(_HW_DEVICE_EXTENSION *,uchar)
0x14005a235  test    al, al
0x14005a237  jz      loc_14005A2CD
0x14005a23d  movzx   edx, byte ptr [rdi+1]
0x14005a241  cmp     dl, r11b
0x14005a244  jnb     short loc_14005A2A3
0x14005a246  mov     eax, [rdi+4]
0x14005a249  imul    rcx, rax, 2Ch ; ','
0x14005a24d  add     rcx, 4
0x14005a251  cmp     rbp, rcx
0x14005a254  jb      short loc_14005A265
0x14005a256  mov     rcx, [rsp+78h+arg_0]
0x14005a25e  mov     rdi, r15
0x14005a261  inc     ebx
0x14005a263  jmp     short loc_14005A203
0x14005a265  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a26c  lea     rax, WPP_GLOBAL_Control
0x14005a273  cmp     rcx, rax
0x14005a276  jz      loc_14005A35D
0x14005a27c  cmp     [rcx+29h], r11b
0x14005a280  jb      loc_14005A35D
0x14005a286  mov     rcx, [rcx+18h]
0x14005a28a  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a291  mov     edx, 21h ; '!'
0x14005a296  mov     r9d, ebx
0x14005a299  call    WPP_SF_d
0x14005a29e  jmp     loc_14005A35D
0x14005a2a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a2aa  lea     rax, WPP_GLOBAL_Control
0x14005a2b1  cmp     rcx, rax
0x14005a2b4  jz      loc_14005A35D
0x14005a2ba  cmp     [rcx+29h], r11b
0x14005a2be  jb      loc_14005A35D
0x14005a2c4  mov     eax, edx
0x14005a2c6  mov     edx, 20h ; ' '
0x14005a2cb  jmp     short loc_14005A2ED
0x14005a2cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a2d4  lea     rax, WPP_GLOBAL_Control
0x14005a2db  cmp     rcx, rax
0x14005a2de  jz      short loc_14005A35D
0x14005a2e0  cmp     [rcx+29h], r11b
0x14005a2e4  jb      short loc_14005A35D
0x14005a2e6  mov     eax, edx
0x14005a2e8  mov     edx, 1Fh
0x14005a2ed  mov     [rsp+78h+var_58], eax
0x14005a2f1  jmp     short loc_14005A352
0x14005a2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a2fa  lea     rax, WPP_GLOBAL_Control
0x14005a301  cmp     rcx, rax
0x14005a304  jz      short loc_14005A35D
0x14005a306  cmp     [rcx+29h], r11b
0x14005a30a  jb      short loc_14005A35D
0x14005a30c  mov     rcx, [rcx+18h]
0x14005a310  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a317  mov     edx, 1Eh
0x14005a31c  mov     [rsp+78h+var_50], ebp
0x14005a320  mov     r9d, ebx
0x14005a323  mov     [rsp+78h+var_58], r14d
0x14005a328  call    WPP_SF_ddD
0x14005a32d  jmp     short loc_14005A35D
0x14005a32f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a336  lea     rax, WPP_GLOBAL_Control
0x14005a33d  cmp     rcx, rax
0x14005a340  jz      short loc_14005A35D
0x14005a342  cmp     [rcx+29h], r11b
0x14005a346  jb      short loc_14005A35D
0x14005a348  mov     edx, 1Dh
0x14005a34d  mov     [rsp+78h+var_58], r14d
0x14005a352  mov     r9d, ebx
0x14005a355  jmp     loc_14005A1A1
0x14005a35a  xor     r13d, r13d
0x14005a35d  mov     eax, r13d
0x14005a360  add     rsp, 38h
0x14005a364  pop     r15
0x14005a366  pop     r14
0x14005a368  pop     r13
0x14005a36a  pop     r12
0x14005a36c  pop     rdi
0x14005a36d  pop     rsi
0x14005a36e  pop     rbp
0x14005a36f  pop     rbx
0x14005a370  retn
```

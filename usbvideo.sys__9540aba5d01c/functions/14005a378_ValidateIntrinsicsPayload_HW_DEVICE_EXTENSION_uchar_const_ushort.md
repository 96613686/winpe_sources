# ValidateIntrinsicsPayload(_HW_DEVICE_EXTENSION *,uchar const *,ushort)

- ea: `0x14005a378`
- end: `0x14005a5b6`
- name: `?ValidateIntrinsicsPayload@@YAJPEAU_HW_DEVICE_EXTENSION@@PEBEG@Z`
- size: `574`
- prototype: `__int64 __fastcall(struct _HW_DEVICE_EXTENSION *, const unsigned __int8 *, unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140058d20`
- `0x14005b260`

## callees

- `0x1400051e4`
- `0x140019cd4`
- `0x14001b118`
- `0x14005a378`
- `0x14005c6d0`

## pseudocode

```c
__int64 __fastcall ValidateIntrinsicsPayload(
        struct _HW_DEVICE_EXTENSION *a1,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  unsigned int v3; // r13d
  int v4; // r15d
  int v5; // r9d
  const unsigned __int8 *v6; // rdi
  unsigned int v7; // esi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned __int16 v11; // dx
  unsigned __int8 v12; // r11
  unsigned __int64 v13; // r14
  const unsigned __int8 *v14; // rdi
  unsigned int i; // ebx
  unsigned __int64 v16; // rbp
  int v17; // edx
  int v18; // eax
  int v20; // [rsp+20h] [rbp-58h]
  struct _HW_DEVICE_EXTENSION *v21; // [rsp+80h] [rbp+8h]

  v21 = a1;
  v3 = -1073741436;
  v4 = a3;
  v5 = *(unsigned __int8 *)(*((_QWORD *)a1 + 4) + 4LL);
  v6 = &a2[2 * a3];
  v7 = *v6;
  if ( v7 <= 2 * v5 )
  {
    v11 = 52 * v7 + 1;
    if ( a3 < v11 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a3, v11);
      return v3;
    }
    v12 = 2;
    v13 = (unsigned __int64)&v6[a3];
    v14 = v6 + 1;
    for ( i = 0; ; ++i )
    {
      if ( (int)i >= (int)v7 )
        return 0;
      if ( (unsigned __int64)(v14 + 8) > v13 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < v12 )
          return v3;
        v9 = 37;
        v20 = v4;
        goto LABEL_35;
      }
      v16 = *((unsigned __int16 *)v14 + 1);
      if ( (unsigned __int64)&v14[v16 + 4] > v13 )
        break;
      if ( !IsValidInterfaceNumber(a1, *v14) )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < v12 )
          return v3;
        v18 = v17;
        v9 = 39;
LABEL_28:
        v20 = v18;
LABEL_35:
        v10 = i;
        goto LABEL_5;
      }
      if ( v14[1] >= v12 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < v12 )
          return v3;
        v18 = v14[1];
        v9 = 40;
        goto LABEL_28;
      }
      if ( v16 < 44 * (unsigned __int64)*((unsigned int *)v14 + 1) + 4 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= v12 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, i);
        return v3;
      }
      a1 = v21;
      v14 += v16 + 4;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= v12 )
      WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v20 = v5;
      v9 = 35;
      v10 = *v6;
LABEL_5:
      WPP_SF_dd(v8->AttachedDevice, v9, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v10, v20);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14005a378  mov     [rsp+arg_0], rcx
0x14005a37d  push    rbx
0x14005a37e  push    rbp
0x14005a37f  push    rsi
0x14005a380  push    rdi
0x14005a381  push    r12
0x14005a383  push    r13
0x14005a385  push    r14
0x14005a387  push    r15
0x14005a389  sub     rsp, 38h
0x14005a38d  mov     rax, [rcx+20h]
0x14005a391  mov     r13d, 0C0000184h
0x14005a397  movzx   r15d, r8w
0x14005a39b  movzx   r9d, byte ptr [rax+4]
0x14005a3a0  lea     edi, [r15+r15]
0x14005a3a4  add     rdi, rdx
0x14005a3a7  lea     eax, [r9+r9]
0x14005a3ab  movzx   esi, byte ptr [rdi]
0x14005a3ae  cmp     esi, eax
0x14005a3b0  jbe     short loc_14005A3F8
0x14005a3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a3b9  lea     rax, WPP_GLOBAL_Control
0x14005a3c0  cmp     rcx, rax
0x14005a3c3  jz      loc_14005A5A1
0x14005a3c9  mov     r11b, 2
0x14005a3cc  cmp     [rcx+29h], r11b
0x14005a3d0  jb      loc_14005A5A1
0x14005a3d6  mov     [rsp+78h+var_58], r9d
0x14005a3db  mov     edx, 23h ; '#'
0x14005a3e0  mov     r9d, esi
0x14005a3e3  mov     rcx, [rcx+18h]
0x14005a3e7  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a3ee  call    WPP_SF_dd
0x14005a3f3  jmp     loc_14005A5A1
0x14005a3f8  imul    edx, esi, 34h ; '4'
0x14005a3fb  inc     dx
0x14005a3fe  cmp     r8w, dx
0x14005a402  jnb     short loc_14005A439
0x14005a404  mov     rcx, cs:WPP_GLOBAL_Control; struct _HW_DEVICE_EXTENSION *
0x14005a40b  lea     rax, WPP_GLOBAL_Control
0x14005a412  cmp     rcx, rax
0x14005a415  jz      loc_14005A5A1
0x14005a41b  mov     r11b, 2
0x14005a41e  cmp     [rcx+29h], r11b
0x14005a422  jb      loc_14005A5A1
0x14005a428  movzx   eax, dx
0x14005a42b  mov     r9d, r15d
0x14005a42e  mov     [rsp+78h+var_58], eax
0x14005a432  mov     edx, 24h ; '$'
0x14005a437  jmp     short loc_14005A3E3
0x14005a439  movzx   r14d, r8w
0x14005a43d  mov     r11b, 2
0x14005a440  add     r14, rdi
0x14005a443  inc     rdi
0x14005a446  xor     ebx, ebx
0x14005a448  cmp     ebx, esi
0x14005a44a  jge     loc_14005A59E
0x14005a450  lea     rax, [rdi+8]
0x14005a454  cmp     rax, r14
0x14005a457  ja      loc_14005A573
0x14005a45d  movzx   ebp, word ptr [rdi+2]
0x14005a461  lea     r12, [rbp+4]
0x14005a465  add     r12, rdi
0x14005a468  cmp     r12, r14
0x14005a46b  ja      loc_14005A537
0x14005a471  movzx   edx, byte ptr [rdi]; unsigned __int8
0x14005a474  call    ?IsValidInterfaceNumber@@YAEPEAU_HW_DEVICE_EXTENSION@@E@Z; IsValidInterfaceNumber(_HW_DEVICE_EXTENSION *,uchar)
0x14005a479  test    al, al
0x14005a47b  jz      loc_14005A511
0x14005a481  movzx   edx, byte ptr [rdi+1]
0x14005a485  cmp     dl, r11b
0x14005a488  jnb     short loc_14005A4E7
0x14005a48a  mov     eax, [rdi+4]
0x14005a48d  imul    rcx, rax, 2Ch ; ','
0x14005a491  add     rcx, 4
0x14005a495  cmp     rbp, rcx
0x14005a498  jb      short loc_14005A4A9
0x14005a49a  mov     rcx, [rsp+78h+arg_0]
0x14005a4a2  mov     rdi, r12
0x14005a4a5  inc     ebx
0x14005a4a7  jmp     short loc_14005A448
0x14005a4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a4b0  lea     rax, WPP_GLOBAL_Control
0x14005a4b7  cmp     rcx, rax
0x14005a4ba  jz      loc_14005A5A1
0x14005a4c0  cmp     [rcx+29h], r11b
0x14005a4c4  jb      loc_14005A5A1
0x14005a4ca  mov     rcx, [rcx+18h]
0x14005a4ce  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a4d5  mov     edx, 29h ; ')'
0x14005a4da  mov     r9d, ebx
0x14005a4dd  call    WPP_SF_d
0x14005a4e2  jmp     loc_14005A5A1
0x14005a4e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a4ee  lea     rax, WPP_GLOBAL_Control
0x14005a4f5  cmp     rcx, rax
0x14005a4f8  jz      loc_14005A5A1
0x14005a4fe  cmp     [rcx+29h], r11b
0x14005a502  jb      loc_14005A5A1
0x14005a508  mov     eax, edx
0x14005a50a  mov     edx, 28h ; '('
0x14005a50f  jmp     short loc_14005A531
0x14005a511  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a518  lea     rax, WPP_GLOBAL_Control
0x14005a51f  cmp     rcx, rax
0x14005a522  jz      short loc_14005A5A1
0x14005a524  cmp     [rcx+29h], r11b
0x14005a528  jb      short loc_14005A5A1
0x14005a52a  mov     eax, edx
0x14005a52c  mov     edx, 27h ; '''
0x14005a531  mov     [rsp+78h+var_58], eax
0x14005a535  jmp     short loc_14005A596
0x14005a537  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a53e  lea     rax, WPP_GLOBAL_Control
0x14005a545  cmp     rcx, rax
0x14005a548  jz      short loc_14005A5A1
0x14005a54a  cmp     [rcx+29h], r11b
0x14005a54e  jb      short loc_14005A5A1
0x14005a550  mov     rcx, [rcx+18h]
0x14005a554  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a55b  mov     edx, 26h ; '&'
0x14005a560  mov     [rsp+78h+var_50], ebp
0x14005a564  mov     r9d, ebx
0x14005a567  mov     [rsp+78h+var_58], r15d
0x14005a56c  call    WPP_SF_ddD
0x14005a571  jmp     short loc_14005A5A1
0x14005a573  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a57a  lea     rax, WPP_GLOBAL_Control
0x14005a581  cmp     rcx, rax
0x14005a584  jz      short loc_14005A5A1
0x14005a586  cmp     [rcx+29h], r11b
0x14005a58a  jb      short loc_14005A5A1
0x14005a58c  mov     edx, 25h ; '%'
0x14005a591  mov     [rsp+78h+var_58], r15d
0x14005a596  mov     r9d, ebx
0x14005a599  jmp     loc_14005A3E3
0x14005a59e  xor     r13d, r13d
0x14005a5a1  mov     eax, r13d
0x14005a5a4  add     rsp, 38h
0x14005a5a8  pop     r15
0x14005a5aa  pop     r14
0x14005a5ac  pop     r13
0x14005a5ae  pop     r12
0x14005a5b0  pop     rdi
0x14005a5b1  pop     rsi
0x14005a5b2  pop     rbp
0x14005a5b3  pop     rbx
0x14005a5b4  retn
```

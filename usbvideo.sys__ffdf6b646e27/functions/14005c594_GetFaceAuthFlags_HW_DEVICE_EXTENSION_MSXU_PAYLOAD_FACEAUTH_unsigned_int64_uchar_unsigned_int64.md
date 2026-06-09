# GetFaceAuthFlags(_HW_DEVICE_EXTENSION *,_MSXU_PAYLOAD_FACEAUTH *,unsigned __int64,uchar,unsigned __int64 *)

- ea: `0x14005c594`
- end: `0x14005c695`
- name: `?GetFaceAuthFlags@@YAJPEAU_HW_DEVICE_EXTENSION@@PEAU_MSXU_PAYLOAD_FACEAUTH@@_KEPEA_K@Z`
- size: `257`
- prototype: `int(struct _HW_DEVICE_EXTENSION *, struct _MSXU_PAYLOAD_FACEAUTH *, unsigned __int64, unsigned __int8, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14005c1d0`
- `0x14005c860`

## callees

- `0x140004bac`
- `0x14005c594`
- `0x14005c6d0`

## pseudocode

```c
__int64 __fastcall GetFaceAuthFlags(
        struct _HW_DEVICE_EXTENSION *a1,
        struct _MSXU_PAYLOAD_FACEAUTH *a2,
        unsigned __int64 a3,
        unsigned __int8 a4,
        unsigned __int64 *a5)
{
  unsigned int v8; // esi
  __int64 v9; // r11
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  char v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rax

  v8 = -1073741811;
  *a5 = 0;
  if ( *(_BYTE *)a2 && *(_BYTE *)a2 <= *(_BYTE *)(*((_QWORD *)a1 + 4) + 4LL) && IsValidInterfaceNumber(a1, a4) )
  {
    if ( a3 >= 8 * v9 + 1 )
    {
      v12 = 0;
      if ( (_BYTE)v9 )
      {
        do
        {
          if ( *((_BYTE *)a2 + 8 * v12 + 1) == a4 )
          {
            v13 = *((_BYTE *)a2 + 8 * v12 + 2);
            v14 = v13 & 1 | 2LL;
            if ( (v13 & 2) == 0 )
              v14 = *((_BYTE *)a2 + 8 * v12 + 2) & 1;
            v15 = v14 | 4;
            if ( (v13 & 4) == 0 )
              v15 = v14;
            v8 = 0;
            *a5 = v15;
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (int)v12 < (int)v9 );
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v11 = 11;
LABEL_20:
        WPP_SF_(v10->AttachedDevice, v11, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v11 = 10;
      goto LABEL_20;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14005c594  push    rbx
0x14005c596  push    rbp
0x14005c597  push    rsi
0x14005c598  push    rdi
0x14005c599  push    r14
0x14005c59b  sub     rsp, 20h
0x14005c59f  mov     r14, [rsp+48h+arg_20]
0x14005c5a4  mov     dil, r9b
0x14005c5a7  mov     rbp, r8
0x14005c5aa  mov     rbx, rdx
0x14005c5ad  mov     esi, 0C000000Dh
0x14005c5b2  mov     qword ptr [r14], 0
0x14005c5b9  movzx   r11d, byte ptr [rdx]
0x14005c5bd  cmp     r11b, 1
0x14005c5c1  jb      loc_14005C659
0x14005c5c7  mov     rax, [rcx+20h]
0x14005c5cb  cmp     r11b, [rax+4]
0x14005c5cf  ja      loc_14005C659
0x14005c5d5  mov     dl, r9b; unsigned __int8
0x14005c5d8  call    ?IsValidInterfaceNumber@@YAEPEAU_HW_DEVICE_EXTENSION@@E@Z; IsValidInterfaceNumber(_HW_DEVICE_EXTENSION *,uchar)
0x14005c5dd  test    al, al
0x14005c5df  jz      short loc_14005C659
0x14005c5e1  lea     rax, ds:1[r11*8]
0x14005c5e9  cmp     rbp, rax
0x14005c5ec  jnb     short loc_14005C612
0x14005c5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c5f5  lea     rax, WPP_GLOBAL_Control
0x14005c5fc  cmp     rcx, rax
0x14005c5ff  jz      loc_14005C687
0x14005c605  cmp     byte ptr [rcx+29h], 2
0x14005c609  jb      short loc_14005C687
0x14005c60b  mov     edx, 0Bh
0x14005c610  jmp     short loc_14005C677
0x14005c612  xor     r9d, r9d
0x14005c615  test    r11b, r11b
0x14005c618  jz      short loc_14005C687
0x14005c61a  cmp     [rbx+r9*8+1], dil
0x14005c61f  jnz     short loc_14005C64F
0x14005c621  movzx   r8d, byte ptr [rbx+r9*8+2]
0x14005c627  mov     ecx, r8d
0x14005c62a  and     ecx, 1
0x14005c62d  mov     edx, ecx
0x14005c62f  or      rdx, 2
0x14005c633  test    r8b, 2
0x14005c637  cmovz   rdx, rcx
0x14005c63b  mov     rax, rdx
0x14005c63e  or      rax, 4
0x14005c642  test    r8b, 4
0x14005c646  cmovz   rax, rdx
0x14005c64a  xor     esi, esi
0x14005c64c  mov     [r14], rax
0x14005c64f  inc     r9d
0x14005c652  cmp     r9d, r11d
0x14005c655  jl      short loc_14005C61A
0x14005c657  jmp     short loc_14005C687
0x14005c659  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c660  lea     rax, WPP_GLOBAL_Control
0x14005c667  cmp     rcx, rax
0x14005c66a  jz      short loc_14005C687
0x14005c66c  cmp     byte ptr [rcx+29h], 2
0x14005c670  jb      short loc_14005C687
0x14005c672  mov     edx, 0Ah
0x14005c677  mov     rcx, [rcx+18h]
0x14005c67b  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c682  call    WPP_SF_
0x14005c687  mov     eax, esi
0x14005c689  add     rsp, 20h
0x14005c68d  pop     r14
0x14005c68f  pop     rdi
0x14005c690  pop     rsi
0x14005c691  pop     rbp
0x14005c692  pop     rbx
0x14005c693  retn
```

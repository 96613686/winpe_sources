# ProcessOptions

- ea: `0x1400124cc`
- end: `0x140012d6f`
- name: `ProcessOptions`
- size: `2211`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x14000ec50`
- `0x14000f2d8`
- `0x140010ae4`
- `0x140012efc`

## callees

- `0x140005038`
- `0x140005068`
- `0x1400050ac`
- `0x140005168`
- `0x140012424`
- `0x1400124cc`
- `0x1400151b0`
- `0x140015644`

## pseudocode

```c
__int64 __fastcall ProcessOptions(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r14
  unsigned int v6; // r11d
  unsigned __int16 v7; // r8
  unsigned int v8; // esi
  unsigned int v9; // edi
  int v10; // r13d
  unsigned __int8 *v11; // r10
  unsigned int v12; // ebp
  __int64 v13; // r9
  int v14; // r8d
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // edi
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  unsigned int v26; // edi
  unsigned int v27; // esi
  unsigned int v28; // edi
  unsigned __int32 v29; // edi
  unsigned __int32 v30; // r14d
  unsigned __int32 v31; // esi
  unsigned int v32; // edi
  unsigned __int32 v33; // edi
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  __int64 v39; // rax
  PDEVICE_OBJECT v40; // rcx
  __int64 v41; // rdx
  int v42; // esi
  int v44; // [rsp+40h] [rbp-68h]
  unsigned int v45; // [rsp+44h] [rbp-64h]
  unsigned int v46; // [rsp+48h] [rbp-60h]
  unsigned __int16 v47; // [rsp+4Ch] [rbp-5Ch]
  char *v48; // [rsp+50h] [rbp-58h]
  unsigned int v49; // [rsp+58h] [rbp-50h]

  v5 = a4;
  v6 = a3;
  v7 = 0;
  v47 = 0;
  *(_WORD *)(a4 + 2) = 0;
  *(_DWORD *)(a4 + 4) = 0;
  if ( a2 > 4 )
  {
    v7 = __ROR2__(*(_WORD *)(a1 + 2), 8);
    v47 = v7;
  }
  if ( a2 < 8 || *(_BYTE *)a1 || *(_BYTE *)(a1 + 1) != 4 || (v44 = v7, a2 < v7) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_ddddD(WPP_GLOBAL_Control->AttachedDevice);
    return 3221225473LL;
  }
  v8 = 0;
  v9 = a2 - 4;
  v10 = 0;
  v45 = a2 - 4;
  v46 = 0;
  v11 = (unsigned __int8 *)(a1 + 4);
  v12 = 0;
  while ( 1 )
  {
    v13 = v11[1];
    v48 = (char *)v11;
    if ( (unsigned int)v13 > v9 || !(_BYTE)v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v13, v9, v8);
      goto LABEL_146;
    }
    v14 = *v11;
    v15 = v14 & 0x7F;
    if ( v15 == 127 )
      goto LABEL_98;
    if ( v15 > 0xA )
    {
      v34 = v15 - 11;
      if ( !v34 )
        goto LABEL_98;
      v35 = v34 - 1;
      if ( !v35 )
        goto LABEL_98;
      v36 = v35 - 1;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( v38 )
          {
            if ( v38 - 1 <= 1 )
            {
LABEL_98:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_DDd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  35,
                  WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
                  v6,
                  v14 & 0xFFFFFF7F,
                  v13);
              }
              v10 |= 0x80000000;
              goto LABEL_102;
            }
LABEL_134:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              WPP_SF_DDd(
                WPP_GLOBAL_Control->AttachedDevice,
                36,
                WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
                v6,
                v14 & 0xFFFFFF7F,
                v13);
            }
LABEL_146:
            v12 = -1073741823;
LABEL_147:
            v42 = v44;
            goto LABEL_148;
          }
          if ( (_BYTE)v13 != 4 )
          {
            v12 = -1073741823;
            v40 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              return v12;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
              goto LABEL_147;
            v41 = 26;
LABEL_130:
            WPP_SF_Dd(v40->AttachedDevice, v41, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v13, 4);
            goto LABEL_102;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids);
          }
          v10 |= 0x80u;
        }
        else
        {
          if ( (_BYTE)v13 != 4 )
          {
            v12 = -1073741823;
            v40 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              return v12;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
              goto LABEL_147;
            v41 = 24;
            goto LABEL_130;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids);
          }
          v10 |= 0x40u;
        }
      }
      else
      {
        if ( (_BYTE)v13 != 4 )
        {
          v12 = -1073741823;
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return v12;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
            goto LABEL_147;
          v41 = 22;
          goto LABEL_130;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids);
        }
        v10 |= 0x20u;
      }
    }
    else
    {
      if ( v15 == 10 )
      {
        if ( (_BYTE)v13 == 8 )
        {
          v32 = *((_DWORD *)v11 + 1);
          if ( v32 )
          {
            v33 = _byteswap_ulong(v32);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v33);
            }
            if ( v33 > 0x80 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v33);
              }
              v12 = -1073741823;
            }
            *(_BYTE *)(v5 + 29) = v33;
            v10 |= 0x800u;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, 0);
            }
            v12 = -1073741823;
          }
          goto LABEL_27;
        }
        v12 = -1073741823;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return v12;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
          goto LABEL_147;
        v25 = 34;
        goto LABEL_47;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        if ( (_BYTE)v13 != 16 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v13, 16);
          }
          v12 = -1073741823;
          goto LABEL_102;
        }
        v27 = *((_DWORD *)v11 + 2);
        v28 = *((_DWORD *)v11 + 3);
        v49 = *((_DWORD *)v11 + 1);
        if ( (v11[2] & 4) != 0 )
        {
          *(_DWORD *)(v5 + 16) = v49;
          *(_DWORD *)(v5 + 20) = v27;
          *(_DWORD *)(v5 + 24) = v28;
          *(_BYTE *)(v5 + 30) = v11[3];
          goto LABEL_58;
        }
        v29 = _byteswap_ulong(v28);
        v30 = _byteswap_ulong(v49);
        v31 = _byteswap_ulong(v27);
        if ( v29 && v31 <= v29 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v31, v29);
          }
          *(_DWORD *)(a4 + 16) = v30;
          v5 = a4;
          *(_DWORD *)(a4 + 20) = v31;
          *(_DWORD *)(a4 + 24) = v29;
LABEL_58:
          v10 |= 1u;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v31, v29);
          }
          v5 = a4;
          v12 = -1073741823;
        }
        v9 = v45;
        v8 = v46;
        goto LABEL_102;
      }
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              v21 = v20 - 2;
              if ( v21 )
              {
                v22 = v21 - 1;
                if ( v22 )
                {
                  if ( v22 != 1 )
                    goto LABEL_134;
                  if ( (_BYTE)v13 == 8 )
                  {
                    v23 = *((_DWORD *)v11 + 1);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        29,
                        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
                        _byteswap_ulong(v23));
                    }
                    v10 |= 0x400u;
LABEL_26:
                    *(_BYTE *)(v5 + 28) = _byteswap_ulong(v23);
LABEL_27:
                    v9 = v45;
                    goto LABEL_102;
                  }
                  v12 = -1073741823;
                  v24 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    return v12;
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
                    goto LABEL_147;
                  v25 = 30;
                }
                else
                {
                  if ( (_BYTE)v13 == 8 )
                  {
                    v23 = *((_DWORD *)v11 + 1);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                    {
                      WPP_SF_Dd(
                        WPP_GLOBAL_Control->AttachedDevice,
                        27,
                        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
                        v11[3],
                        _byteswap_ulong(v23));
                      v11 = (unsigned __int8 *)v48;
                    }
                    v10 |= 0x200u;
                    *(_BYTE *)(v5 + 31) = v11[3];
                    goto LABEL_26;
                  }
                  v12 = -1073741823;
                  v24 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    return v12;
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
                    goto LABEL_147;
                  v25 = 28;
                }
                goto LABEL_47;
              }
            }
          }
          goto LABEL_98;
        }
        if ( (_BYTE)v13 == 8 )
        {
          v26 = *((_DWORD *)v11 + 1);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              19,
              WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
              _byteswap_ulong(v26));
          }
          *(_DWORD *)(v5 + 12) = _byteswap_ulong(v26);
          v10 |= 8u;
          goto LABEL_27;
        }
        v12 = -1073741823;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return v12;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
          goto LABEL_147;
        v25 = 20;
LABEL_47:
        WPP_SF_Dd(v24->AttachedDevice, v25, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v13, 8);
        goto LABEL_102;
      }
      if ( v6 - 8 > 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_DDq(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
            v6,
            v13,
            v5);
        goto LABEL_146;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
          (unsigned int)(((int)v13 - 4) / 4));
        v11 = (unsigned __int8 *)v48;
      }
      if ( !a5 )
        goto LABEL_146;
      v12 = ProcessNakOption(v11, a5);
      if ( !v12 )
      {
        v10 |= 4u;
        goto LABEL_103;
      }
    }
LABEL_102:
    if ( (v12 & 0x80000000) != 0 )
      goto LABEL_147;
LABEL_103:
    v46 = ++v8;
    v39 = (unsigned __int8)v48[1];
    v9 -= v39;
    v45 = v9;
    if ( *v48 < 0 || v9 < 4 )
      break;
    v6 = a3;
    v11 = (unsigned __int8 *)&v48[v39];
  }
  v42 = v44;
  if ( v44 + v9 == a2 )
  {
    *(_WORD *)(v5 + 2) = v47;
    *(_DWORD *)(v5 + 4) = v10;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v9, v44, a2);
    v12 = -1073741306;
  }
LABEL_148:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v46, v42);
  return v12;
}

```

## disassembly

```asm
0x1400124cc  mov     [rsp+arg_18], r9
0x1400124d1  mov     [rsp+arg_10], r8d
0x1400124d6  mov     [rsp+arg_8], edx
0x1400124da  push    rbx
0x1400124db  push    rbp
0x1400124dc  push    rsi
0x1400124dd  push    rdi
0x1400124de  push    r12
0x1400124e0  push    r13
0x1400124e2  push    r14
0x1400124e4  sub     rsp, 70h
0x1400124e8  xor     eax, eax
0x1400124ea  mov     r14, r9
0x1400124ed  mov     r9d, edx
0x1400124f0  mov     r11d, r8d
0x1400124f3  xor     r8d, r8d
0x1400124f6  mov     [rsp+0A8h+var_5C], r8d
0x1400124fb  lea     edx, [rax+4]
0x1400124fe  mov     [r14+2], ax
0x140012503  mov     [r14+4], eax
0x140012507  cmp     r9d, edx
0x14001250a  jbe     short loc_14001251B
0x14001250c  movzx   r8d, word ptr [rcx+2]
0x140012511  ror     r8w, 8
0x140012516  mov     [rsp+0A8h+var_5C], r8d
0x14001251b  cmp     r9d, 8
0x14001251f  jb      loc_140012D1E
0x140012525  cmp     [rcx], al
0x140012527  jnz     loc_140012D1E
0x14001252d  cmp     [rcx+1], dl
0x140012530  jnz     loc_140012D1E
0x140012536  movzx   esi, r8w
0x14001253a  mov     [rsp+0A8h+var_68], esi
0x14001253e  cmp     r9d, esi
0x140012541  jb      loc_140012D1E
0x140012547  xor     esi, esi
0x140012549  lea     edi, [r9-4]
0x14001254d  xor     r13d, r13d
0x140012550  mov     [rsp+0A8h+var_64], edi
0x140012554  mov     [rsp+0A8h+var_60], esi
0x140012558  lea     r10, [rcx+4]
0x14001255c  xor     ebp, ebp
0x14001255e  lea     rbx, WPP_GLOBAL_Control
0x140012565  mov     r12d, 0C0000001h
0x14001256b  movzx   r9d, byte ptr [r10+1]
0x140012570  mov     [rsp+0A8h+var_58], r10
0x140012575  cmp     r9d, edi
0x140012578  ja      loc_140012CB2
0x14001257e  test    r9b, r9b
0x140012581  jz      loc_140012CB2
0x140012587  movzx   r8d, byte ptr [r10]
0x14001258b  mov     ecx, r8d
0x14001258e  btr     ecx, 7
0x140012592  cmp     ecx, 7Fh
0x140012595  jz      loc_140012A2A
0x14001259b  cmp     ecx, 0Ah
0x14001259e  ja      loc_1400129F7
0x1400125a4  jz      loc_140012919
0x1400125aa  sub     ecx, 1
0x1400125ad  jz      loc_1400127ED
0x1400125b3  sub     ecx, 1
0x1400125b6  jz      loc_14001276F
0x1400125bc  sub     ecx, 1
0x1400125bf  jz      loc_1400126E8
0x1400125c5  sub     ecx, 1
0x1400125c8  jz      loc_140012A2A
0x1400125ce  sub     ecx, 1
0x1400125d1  jz      loc_140012A2A
0x1400125d7  sub     ecx, 2
0x1400125da  jz      loc_140012A2A
0x1400125e0  sub     ecx, 1
0x1400125e3  jz      loc_14001266D
0x1400125e9  cmp     ecx, 1
0x1400125ec  jnz     loc_140012C0D
0x1400125f2  cmp     r9b, 8
0x1400125f6  jnz     short loc_140012645
0x1400125f8  mov     edi, [r10+4]
0x1400125fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140012603  cmp     rcx, rbx
0x140012606  jz      short loc_14001262A
0x140012608  mov     eax, [rcx+2Ch]
0x14001260b  test    al, 20h
0x14001260d  jz      short loc_14001262A
0x14001260f  mov     rcx, [rcx+18h]
0x140012613  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14001261a  mov     r9d, edi
0x14001261d  mov     edx, 1Dh
0x140012622  bswap   r9d
0x140012625  call    WPP_SF_d
0x14001262a  bts     r13d, 0Ah
0x14001262f  bswap   edi
0x140012631  mov     al, dil
0x140012634  mov     [rsp+0A8h+var_50], edi
0x140012638  mov     [r14+1Ch], al
0x14001263c  mov     edi, [rsp+0A8h+var_64]
0x140012640  jmp     loc_140012A69
0x140012645  mov     ebp, r12d
0x140012648  mov     rcx, cs:WPP_GLOBAL_Control
0x14001264f  cmp     rcx, rbx
0x140012652  jz      loc_140012D1A
0x140012658  mov     eax, [rcx+2Ch]
0x14001265b  test    al, 2
0x14001265d  jz      loc_140012CE5
0x140012663  mov     edx, 1Eh
0x140012668  jmp     loc_140012752
0x14001266d  cmp     r9b, 8
0x140012671  jnz     short loc_1400126C3
0x140012673  mov     edi, [r10+4]
0x140012677  mov     rcx, cs:WPP_GLOBAL_Control
0x14001267e  cmp     rcx, rbx
0x140012681  jz      short loc_1400126B1
0x140012683  mov     eax, [rcx+2Ch]
0x140012686  test    al, 20h
0x140012688  jz      short loc_1400126B1
0x14001268a  movzx   r9d, byte ptr [r10+3]
0x14001268f  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140012696  mov     rcx, [rcx+18h]
0x14001269a  mov     eax, edi
0x14001269c  bswap   eax
0x14001269e  mov     edx, 1Bh
0x1400126a3  mov     [rsp+0A8h+var_88], eax
0x1400126a7  call    WPP_SF_Dd
0x1400126ac  mov     r10, [rsp+0A8h+var_58]
0x1400126b1  mov     al, [r10+3]
0x1400126b5  bts     r13d, 9
0x1400126ba  mov     [r14+1Fh], al
0x1400126be  jmp     loc_14001262F
0x1400126c3  mov     ebp, r12d
0x1400126c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126cd  cmp     rcx, rbx
0x1400126d0  jz      loc_140012D1A
0x1400126d6  mov     eax, [rcx+2Ch]
0x1400126d9  test    al, 2
0x1400126db  jz      loc_140012CE5
0x1400126e1  mov     edx, 1Ch
0x1400126e6  jmp     short loc_140012752
0x1400126e8  cmp     r9b, 8
0x1400126ec  jnz     short loc_14001272F
0x1400126ee  mov     edi, [r10+4]
0x1400126f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126f9  cmp     rcx, rbx
0x1400126fc  jz      short loc_140012720
0x1400126fe  mov     eax, [rcx+2Ch]
0x140012701  test    al, 20h
0x140012703  jz      short loc_140012720
0x140012705  mov     rcx, [rcx+18h]
0x140012709  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140012710  mov     r9d, edi
0x140012713  mov     edx, 13h
0x140012718  bswap   r9d
0x14001271b  call    WPP_SF_d
0x140012720  bswap   edi
0x140012722  mov     [r14+0Ch], edi
0x140012726  or      r13d, 8
0x14001272a  jmp     loc_14001263C
0x14001272f  mov     ebp, r12d
0x140012732  mov     rcx, cs:WPP_GLOBAL_Control
0x140012739  cmp     rcx, rbx
0x14001273c  jz      loc_140012D1A
0x140012742  mov     eax, [rcx+2Ch]
0x140012745  test    al, 2
0x140012747  jz      loc_140012CE5
0x14001274d  mov     edx, 14h
0x140012752  mov     [rsp+0A8h+var_88], 8
0x14001275a  mov     rcx, [rcx+18h]
0x14001275e  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140012765  call    WPP_SF_Dd
0x14001276a  jmp     loc_140012A69
0x14001276f  lea     eax, [r11-8]
0x140012773  cmp     eax, 2
0x140012776  ja      loc_140012BCB
0x14001277c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012783  cmp     rcx, rbx
0x140012786  jz      short loc_1400127B9
0x140012788  mov     eax, [rcx+2Ch]
0x14001278b  test    al, 20h
0x14001278d  jz      short loc_1400127B9
0x14001278f  mov     rcx, [rcx+18h]
0x140012793  lea     eax, [r9-4]
0x140012797  mov     r8d, 4
0x14001279d  cdq
0x14001279e  idiv    r8d
0x1400127a1  lea     edx, [r8+0Ah]
0x1400127a5  mov     r9d, eax
0x1400127a8  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x1400127af  call    WPP_SF_d
0x1400127b4  mov     r10, [rsp+0A8h+var_58]
0x1400127b9  cmp     [rsp+0A8h+arg_20], 0
0x1400127c2  jz      loc_140012CE2
0x1400127c8  mov     rdx, [rsp+0A8h+arg_20]
0x1400127d0  mov     rcx, r10
0x1400127d3  call    ProcessNakOption
0x1400127d8  mov     ebp, eax
0x1400127da  test    eax, eax
0x1400127dc  jnz     loc_140012A69
0x1400127e2  lea     edx, [rax+4]
0x1400127e5  or      r13d, edx
0x1400127e8  jmp     loc_140012A76
0x1400127ed  mov     r8d, 10h
0x1400127f3  cmp     r9b, r8b
0x1400127f6  jnz     loc_1400128E4
0x1400127fc  mov     al, [r10+4]
0x140012800  mov     esi, [r10+8]
0x140012804  mov     edi, [r10+0Ch]
0x140012808  mov     byte ptr [rsp+0A8h+var_50], al
0x14001280c  movzx   eax, word ptr [r10+5]
0x140012811  mov     word ptr [rsp+0A8h+var_50+1], ax
0x140012816  mov     al, [r10+7]
0x14001281a  mov     byte ptr [rsp+0A8h+var_50+3], al
0x14001281e  test    [r10+2], dl
0x140012822  jz      short loc_14001284D
0x140012824  mov     eax, [rsp+0A8h+var_50]
0x140012828  mov     [r14+10h], eax
0x14001282c  mov     [r14+14h], esi
0x140012830  mov     [r14+18h], edi
0x140012834  mov     al, [r10+3]
0x140012838  mov     [r14+1Eh], al
0x14001283c  or      r13d, 1
0x140012840  mov     edi, [rsp+0A8h+var_64]
0x140012844  mov     esi, [rsp+0A8h+var_60]
0x140012848  jmp     loc_140012A69
0x14001284d  mov     r14d, [rsp+0A8h+var_50]
0x140012852  bswap   edi
0x140012854  bswap   r14d
0x140012857  bswap   esi
0x140012859  test    edi, edi
0x14001285b  jz      short loc_1400128A5
0x14001285d  cmp     esi, edi
0x14001285f  ja      short loc_1400128A5
0x140012861  mov     rcx, cs:WPP_GLOBAL_Control
0x140012868  cmp     rcx, rbx
0x14001286b  jz      short loc_14001288E
0x14001286d  mov     eax, [rcx+2Ch]
0x140012870  test    al, 20h
0x140012872  jz      short loc_14001288E
0x140012874  mov     rcx, [rcx+18h]
0x140012878  mov     edx, r8d
0x14001287b  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140012882  mov     [rsp+0A8h+var_88], edi
0x140012886  mov     r9d, esi
0x140012889  call    WPP_SF_Dd
0x14001288e  mov     rax, [rsp+0A8h+arg_18]
0x140012896  mov     [rax+10h], r14d
0x14001289a  mov     r14, rax
0x14001289d  mov     [rax+14h], esi
0x1400128a0  mov     [rax+18h], edi
0x1400128a3  jmp     short loc_14001283C
0x1400128a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400128ac  cmp     rcx, rbx
0x1400128af  jz      short loc_1400128D4
0x1400128b1  mov     eax, [rcx+2Ch]
0x1400128b4  test    al, 2
0x1400128b6  jz      short loc_1400128D4
0x1400128b8  mov     rcx, [rcx+18h]
0x1400128bc  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x1400128c3  mov     edx, 11h
0x1400128c8  mov     [rsp+0A8h+var_88], edi
0x1400128cc  mov     r9d, esi
0x1400128cf  call    WPP_SF_Dd
0x1400128d4  mov     r14, [rsp+0A8h+arg_18]
0x1400128dc  mov     ebp, r12d
0x1400128df  jmp     loc_140012840
0x1400128e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400128eb  cmp     rcx, rbx
0x1400128ee  jz      short loc_140012911
0x1400128f0  mov     eax, [rcx+2Ch]
0x1400128f3  test    al, 2
0x1400128f5  jz      short loc_140012911
0x1400128f7  mov     rcx, [rcx+18h]
0x1400128fb  mov     edx, 12h
0x140012900  mov     [rsp+0A8h+var_88], r8d
0x140012905  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14001290c  call    WPP_SF_Dd
0x140012911  mov     ebp, r12d
0x140012914  jmp     loc_140012A69
0x140012919  cmp     r9b, 8
0x14001291d  jnz     loc_1400129CF
0x140012923  mov     edi, [r10+4]
0x140012927  test    edi, edi
0x140012929  jz      short loc_14001299C
0x14001292b  bswap   edi
0x14001292d  mov     rcx, cs:WPP_GLOBAL_Control
0x140012934  cmp     rcx, rbx
0x140012937  jz      short loc_140012958
0x140012939  mov     eax, [rcx+2Ch]
0x14001293c  test    al, 20h
0x14001293e  jz      short loc_140012958
0x140012940  mov     rcx, [rcx+18h]
0x140012944  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14001294b  mov     edx, 1Fh
0x140012950  mov     r9d, edi
0x140012953  call    WPP_SF_d
0x140012958  cmp     edi, 80h
0x14001295e  jbe     short loc_14001298E
0x140012960  mov     rcx, cs:WPP_GLOBAL_Control
0x140012967  cmp     rcx, rbx
0x14001296a  jz      short loc_14001298B
0x14001296c  mov     eax, [rcx+2Ch]
0x14001296f  test    al, 2
0x140012971  jz      short loc_14001298B
  ... truncated ...
```

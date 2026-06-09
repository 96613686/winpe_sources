# DumpAndValidateFormatUncompressed

- ea: `0x140032dcc`
- end: `0x1400333c2`
- name: `DumpAndValidateFormatUncompressed`
- size: `1526`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002f590`
- `0x14002f8cc`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x1400053fc`
- `0x14001b118`
- `0x14001b15c`
- `0x14001b708`
- `0x14001d120`
- `0x14002d844`
- `0x140032dcc`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateFormatUncompressed(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rsi
  __int64 v4; // rax
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  unsigned __int8 v8; // dl
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned __int8 v12; // di
  unsigned __int8 *v13; // rbx
  int v14; // r8d
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdx

  v2 = a2;
  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > v2 || v2 - (unsigned __int64)a1 < *a1 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 322;
LABEL_103:
      WPP_SF_(v5->AttachedDevice, v6, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
      return 3221225473LL;
    }
    LOBYTE(v4) = *a1;
  }
  else
  {
    v4 = *a1;
    if ( &a1[v4] <= a1 || (unsigned __int64)&a1[v4] > v2 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 323;
      goto LABEL_103;
    }
  }
  if ( (_BYTE)v4 != 27 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 324;
    goto LABEL_103;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 325, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 326, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 327, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, *a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 328, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[1]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 329, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[2]);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  330,
                  WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                  a1[3]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    331,
                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    a1[4]);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  {
                    WPP_SF_DDDDDDDDDDD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      332,
                      (unsigned int)WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                      *(_DWORD *)(a1 + 5),
                      *(_WORD *)(a1 + 9),
                      *(_WORD *)(a1 + 11),
                      a1[13],
                      a1[14],
                      a1[15],
                      a1[16],
                      a1[17],
                      a1[18],
                      a1[19],
                      a1[20]);
                    v2 = a2;
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        333,
                        WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                        a1[21]);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          334,
                          WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                          a1[22]);
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            335,
                            WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                            a1[23]);
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              336,
                              WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                              a1[24]);
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          {
                            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                337,
                                WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                                a1[25]);
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                338,
                                WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                                a1[26]);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( !a1[3] )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 339;
    goto LABEL_103;
  }
  v7 = a1[4];
  if ( !(_BYTE)v7 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 340;
    goto LABEL_103;
  }
  if ( !a1[21] )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 341;
    goto LABEL_103;
  }
  v8 = a1[22];
  if ( !v8 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 342;
    goto LABEL_103;
  }
  if ( v8 <= (unsigned __int8)v7 )
  {
    v12 = 0;
    v13 = &a1[*a1];
    while ( (unsigned __int64)(v13 + 26) < v2 )
    {
      v14 = a1[4];
      if ( v12 >= (unsigned __int8)v14 )
        break;
      v15 = v13[2];
      if ( (_BYTE)v15 == 5 && (v16 = SizeOfVideoFrameUncompressed(v13, *v13), v17 == v16) )
      {
        if ( (unsigned __int64)&v13[v17] > v2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_qqq(
              WPP_GLOBAL_Control->AttachedDevice,
              344,
              WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
              v13,
              &v13[v17],
              v2);
          return 3221225473LL;
        }
        ++v12;
        v13 += v17;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_DDDD(
            WPP_GLOBAL_Control->AttachedDevice,
            345,
            WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
            v15,
            *v13,
            v12,
            v14);
        if ( v13[2] != 7 )
          return 3221225473LL;
        v18 = SizeOfVideoFrameUncompressed(v13, *v13);
        if ( v19 != v18 )
          return 3221225473LL;
        ++v12;
        v13 += v19;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 346, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
      }
    }
    v7 = a1[4];
    if ( v12 >= (unsigned __int8)v7 )
      return 0;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = v12;
      v11 = 347;
      goto LABEL_98;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = a1[22];
      v11 = 343;
LABEL_98:
      WPP_SF_dd(v9->AttachedDevice, v11, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, v10, v7);
    }
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x140032dcc  mov     [rsp+arg_8], rdx
0x140032dd1  push    rbx
0x140032dd2  push    rbp
0x140032dd3  push    rsi
0x140032dd4  push    rdi
0x140032dd5  push    r12
0x140032dd7  push    r13
0x140032dd9  push    r14
0x140032ddb  push    r15
0x140032ddd  sub     rsp, 78h
0x140032de1  mov     rsi, rdx
0x140032de4  mov     r13, rcx
0x140032de7  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x140032dec  test    eax, eax
0x140032dee  jnz     short loc_140032E2E
0x140032df0  movzx   eax, byte ptr [r13+0]
0x140032df5  lea     rcx, [rax+r13]
0x140032df9  cmp     rcx, r13
0x140032dfc  jbe     short loc_140032E03
0x140032dfe  cmp     rcx, rsi
0x140032e01  jbe     short loc_140032E4D
0x140032e03  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e0a  lea     r15, WPP_GLOBAL_Control
0x140032e11  cmp     rcx, r15
0x140032e14  jz      loc_1400333AB
0x140032e1a  cmp     byte ptr [rcx+29h], 2
0x140032e1e  jb      loc_1400333AB
0x140032e24  mov     edx, 143h
0x140032e29  jmp     loc_14003339B
0x140032e2e  cmp     r13, rsi
0x140032e31  ja      loc_14003337D
0x140032e37  movzx   ecx, byte ptr [r13+0]
0x140032e3c  mov     rax, rsi
0x140032e3f  sub     rax, r13
0x140032e42  cmp     rax, rcx
0x140032e45  jb      loc_14003337D
0x140032e4b  mov     al, cl
0x140032e4d  cmp     al, 1Bh
0x140032e4f  jz      short loc_140032E7C
0x140032e51  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e58  lea     r15, WPP_GLOBAL_Control
0x140032e5f  cmp     rcx, r15
0x140032e62  jz      loc_1400333AB
0x140032e68  cmp     byte ptr [rcx+29h], 2
0x140032e6c  jb      loc_1400333AB
0x140032e72  mov     edx, 144h
0x140032e77  jmp     loc_14003339B
0x140032e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e83  lea     r15, WPP_GLOBAL_Control
0x140032e8a  lea     r12, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140032e91  mov     bpl, 5
0x140032e94  cmp     rcx, r15
0x140032e97  jz      loc_14003314B
0x140032e9d  cmp     [rcx+29h], bpl
0x140032ea1  jb      short loc_140032EB4
0x140032ea3  mov     rcx, [rcx+18h]
0x140032ea7  mov     edx, 145h
0x140032eac  mov     r8, r12
0x140032eaf  call    WPP_SF_
0x140032eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ebb  cmp     rcx, r15
0x140032ebe  jz      loc_14003314B
0x140032ec4  cmp     [rcx+29h], bpl
0x140032ec8  jb      short loc_140032EDE
0x140032eca  mov     rcx, [rcx+18h]
0x140032ece  mov     edx, 146h
0x140032ed3  mov     r9, r13
0x140032ed6  mov     r8, r12
0x140032ed9  call    WPP_SF_q
0x140032ede  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ee5  cmp     rcx, r15
0x140032ee8  jz      loc_14003314B
0x140032eee  cmp     [rcx+29h], bpl
0x140032ef2  jb      short loc_140032F0A
0x140032ef4  movzx   r9d, byte ptr [r13+0]
0x140032ef9  mov     edx, 147h
0x140032efe  mov     rcx, [rcx+18h]
0x140032f02  mov     r8, r12
0x140032f05  call    WPP_SF_d
0x140032f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f11  cmp     rcx, r15
0x140032f14  jz      loc_14003314B
0x140032f1a  cmp     [rcx+29h], bpl
0x140032f1e  jb      short loc_140032F36
0x140032f20  movzx   r9d, byte ptr [r13+1]
0x140032f25  mov     edx, 148h
0x140032f2a  mov     rcx, [rcx+18h]
0x140032f2e  mov     r8, r12
0x140032f31  call    WPP_SF_d
0x140032f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f3d  cmp     rcx, r15
0x140032f40  jz      loc_14003314B
0x140032f46  cmp     [rcx+29h], bpl
0x140032f4a  jb      short loc_140032F62
0x140032f4c  movzx   r9d, byte ptr [r13+2]
0x140032f51  mov     edx, 149h
0x140032f56  mov     rcx, [rcx+18h]
0x140032f5a  mov     r8, r12
0x140032f5d  call    WPP_SF_d
0x140032f62  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f69  cmp     rcx, r15
0x140032f6c  jz      loc_14003314B
0x140032f72  cmp     [rcx+29h], bpl
0x140032f76  jb      short loc_140032F8E
0x140032f78  movzx   r9d, byte ptr [r13+3]
0x140032f7d  mov     edx, 14Ah
0x140032f82  mov     rcx, [rcx+18h]
0x140032f86  mov     r8, r12
0x140032f89  call    WPP_SF_d
0x140032f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f95  cmp     rcx, r15
0x140032f98  jz      loc_14003314B
0x140032f9e  cmp     [rcx+29h], bpl
0x140032fa2  jb      short loc_140032FBA
0x140032fa4  movzx   r9d, byte ptr [r13+4]
0x140032fa9  mov     edx, 14Bh
0x140032fae  mov     rcx, [rcx+18h]
0x140032fb2  mov     r8, r12
0x140032fb5  call    WPP_SF_d
0x140032fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140032fc1  cmp     rcx, r15
0x140032fc4  jz      loc_14003314B
0x140032fca  cmp     [rcx+29h], bpl
0x140032fce  jb      short loc_14003304F
0x140032fd0  movzx   r8d, byte ptr [r13+13h]
0x140032fd5  mov     edx, 14Ch
0x140032fda  movzx   r9d, byte ptr [r13+12h]
0x140032fdf  movzx   eax, byte ptr [r13+14h]
0x140032fe4  movzx   r10d, byte ptr [r13+11h]
0x140032fe9  movzx   r11d, byte ptr [r13+10h]
0x140032fee  movzx   ebx, byte ptr [r13+0Fh]
0x140032ff3  movzx   edi, byte ptr [r13+0Eh]
0x140032ff8  movzx   esi, byte ptr [r13+0Dh]
0x140032ffd  movzx   ebp, word ptr [r13+0Bh]
0x140033002  movzx   r14d, word ptr [r13+9]
0x140033007  mov     rcx, [rcx+18h]
0x14003300b  mov     [rsp+0B8h+var_50], eax
0x14003300f  mov     [rsp+0B8h+var_58], r8d
0x140033014  mov     r8, r12
0x140033017  mov     [rsp+0B8h+var_60], r9d
0x14003301c  mov     r9d, [r13+5]
0x140033020  mov     [rsp+0B8h+var_68], r10d
0x140033025  mov     [rsp+0B8h+var_70], r11d
0x14003302a  mov     [rsp+0B8h+var_78], ebx
0x14003302e  mov     [rsp+0B8h+var_80], edi
0x140033032  mov     [rsp+0B8h+var_88], esi
0x140033036  mov     dword ptr [rsp+0B8h+var_90], ebp
0x14003303a  mov     dword ptr [rsp+0B8h+var_98], r14d
0x14003303f  call    WPP_SF_DDDDDDDDDDD
0x140033044  mov     rsi, [rsp+0B8h+arg_8]
0x14003304c  mov     bpl, 5
0x14003304f  mov     rcx, cs:WPP_GLOBAL_Control
0x140033056  cmp     rcx, r15
0x140033059  jz      loc_14003314B
0x14003305f  cmp     [rcx+29h], bpl
0x140033063  jb      short loc_14003307B
0x140033065  movzx   r9d, byte ptr [r13+15h]
0x14003306a  mov     edx, 14Dh
0x14003306f  mov     rcx, [rcx+18h]
0x140033073  mov     r8, r12
0x140033076  call    WPP_SF_d
0x14003307b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033082  cmp     rcx, r15
0x140033085  jz      loc_14003314B
0x14003308b  cmp     [rcx+29h], bpl
0x14003308f  jb      short loc_1400330A7
0x140033091  movzx   r9d, byte ptr [r13+16h]
0x140033096  mov     edx, 14Eh
0x14003309b  mov     rcx, [rcx+18h]
0x14003309f  mov     r8, r12
0x1400330a2  call    WPP_SF_d
0x1400330a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400330ae  cmp     rcx, r15
0x1400330b1  jz      loc_14003314B
0x1400330b7  cmp     [rcx+29h], bpl
0x1400330bb  jb      short loc_1400330D3
0x1400330bd  movzx   r9d, byte ptr [r13+17h]
0x1400330c2  mov     edx, 14Fh
0x1400330c7  mov     rcx, [rcx+18h]
0x1400330cb  mov     r8, r12
0x1400330ce  call    WPP_SF_d
0x1400330d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400330da  cmp     rcx, r15
0x1400330dd  jz      short loc_14003314B
0x1400330df  cmp     [rcx+29h], bpl
0x1400330e3  jb      short loc_1400330FB
0x1400330e5  movzx   r9d, byte ptr [r13+18h]
0x1400330ea  mov     edx, 150h
0x1400330ef  mov     rcx, [rcx+18h]
0x1400330f3  mov     r8, r12
0x1400330f6  call    WPP_SF_d
0x1400330fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140033102  cmp     rcx, r15
0x140033105  jz      short loc_14003314B
0x140033107  cmp     [rcx+29h], bpl
0x14003310b  jb      short loc_140033123
0x14003310d  movzx   r9d, byte ptr [r13+19h]
0x140033112  mov     edx, 151h
0x140033117  mov     rcx, [rcx+18h]
0x14003311b  mov     r8, r12
0x14003311e  call    WPP_SF_d
0x140033123  mov     rcx, cs:WPP_GLOBAL_Control
0x14003312a  cmp     rcx, r15
0x14003312d  jz      short loc_14003314B
0x14003312f  cmp     [rcx+29h], bpl
0x140033133  jb      short loc_14003314B
0x140033135  movzx   r9d, byte ptr [r13+1Ah]
0x14003313a  mov     edx, 152h
0x14003313f  mov     rcx, [rcx+18h]
0x140033143  mov     r8, r12
0x140033146  call    WPP_SF_d
0x14003314b  cmp     byte ptr [r13+3], 0
0x140033150  jnz     short loc_140033179
0x140033152  mov     rcx, cs:WPP_GLOBAL_Control
0x140033159  cmp     rcx, r15
0x14003315c  jz      loc_1400333AB
0x140033162  cmp     byte ptr [rcx+29h], 2
0x140033166  jb      loc_1400333AB
0x14003316c  mov     edx, 153h
0x140033171  mov     r8, r12
0x140033174  jmp     loc_1400333A2
0x140033179  movzx   eax, byte ptr [r13+4]
0x14003317e  test    al, al
0x140033180  jnz     short loc_1400331A3
0x140033182  mov     rcx, cs:WPP_GLOBAL_Control
0x140033189  cmp     rcx, r15
0x14003318c  jz      loc_1400333AB
0x140033192  cmp     byte ptr [rcx+29h], 2
0x140033196  jb      loc_1400333AB
0x14003319c  mov     edx, 154h
0x1400331a1  jmp     short loc_140033171
0x1400331a3  cmp     byte ptr [r13+15h], 0
0x1400331a8  jnz     short loc_1400331CB
0x1400331aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331b1  cmp     rcx, r15
0x1400331b4  jz      loc_1400333AB
0x1400331ba  cmp     byte ptr [rcx+29h], 2
0x1400331be  jb      loc_1400333AB
0x1400331c4  mov     edx, 155h
0x1400331c9  jmp     short loc_140033171
0x1400331cb  movzx   edx, byte ptr [r13+16h]
0x1400331d0  test    dl, dl
0x1400331d2  jnz     short loc_1400331F8
0x1400331d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331db  cmp     rcx, r15
0x1400331de  jz      loc_1400333AB
0x1400331e4  cmp     byte ptr [rcx+29h], 2
0x1400331e8  jb      loc_1400333AB
0x1400331ee  mov     edx, 156h
0x1400331f3  jmp     loc_140033171
0x1400331f8  cmp     dl, al
0x1400331fa  jbe     short loc_140033223
0x1400331fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140033203  cmp     rcx, r15
0x140033206  jz      loc_1400333AB
0x14003320c  cmp     byte ptr [rcx+29h], 2
0x140033210  jb      loc_1400333AB
0x140033216  mov     r9d, edx
0x140033219  mov     edx, 157h
0x14003321e  jmp     loc_140033367
0x140033223  movzx   ebx, byte ptr [r13+0]
0x140033228  xor     dil, dil
0x14003322b  add     rbx, r13
0x14003322e  lea     rax, [rbx+1Ah]
0x140033232  cmp     rax, rsi
0x140033235  jnb     loc_140033342
0x14003323b  movzx   r8d, byte ptr [r13+4]
0x140033240  cmp     dil, r8b
0x140033243  jnb     loc_140033342
0x140033249  movzx   r9d, byte ptr [rbx+2]
0x14003324e  cmp     r9b, bpl
0x140033251  jnz     short loc_140033278
0x140033253  movzx   edx, byte ptr [rbx]
0x140033256  mov     rcx, rbx
0x140033259  call    SizeOfVideoFrameUncompressed
0x14003325e  cmp     rdx, rax
0x140033261  jnz     short loc_140033278
0x140033263  lea     rax, [rdx+rbx]
0x140033267  cmp     rax, rsi
0x14003326a  ja      loc_140033308
0x140033270  inc     dil
0x140033273  mov     rbx, rax
0x140033276  jmp     short loc_14003322E
0x140033278  mov     rcx, cs:WPP_GLOBAL_Control
0x14003327f  cmp     rcx, r15
0x140033282  jz      short loc_1400332B4
0x140033284  cmp     byte ptr [rcx+29h], 2
0x140033288  jb      short loc_1400332B4
0x14003328a  movzx   r10d, byte ptr [rbx]
0x14003328e  mov     eax, r8d
0x140033291  mov     rcx, [rcx+18h]
0x140033295  mov     edx, 159h
0x14003329a  mov     [rsp+0B8h+var_88], eax
0x14003329e  movzx   r8d, dil
0x1400332a2  mov     dword ptr [rsp+0B8h+var_90], r8d
0x1400332a7  mov     r8, r12
0x1400332aa  mov     dword ptr [rsp+0B8h+var_98], r10d
0x1400332af  call    WPP_SF_DDDD
0x1400332b4  cmp     byte ptr [rbx+2], 7
0x1400332b8  jnz     loc_1400333AB
  ... truncated ...
```

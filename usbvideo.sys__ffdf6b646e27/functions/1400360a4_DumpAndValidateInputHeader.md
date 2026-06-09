# DumpAndValidateInputHeader

- ea: `0x1400360a4`
- end: `0x140036675`
- name: `DumpAndValidateInputHeader`
- size: `1489`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14002f590`
- `0x14002f8cc`

## callees

- `0x140004bac`
- `0x14001b118`
- `0x14001b15c`
- `0x1400360a4`
- `0x140038ae4`
- `0x140040a30`

## import_xrefs

- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x1400361b8`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x1400361b8`

## pseudocode

```c
__int64 __fastcall DumpAndValidateInputHeader(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int IsEnabledNoReportingNoInline; // eax
  unsigned __int64 v9; // rcx
  unsigned __int16 v10; // dx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned __int8 *v13; // rcx
  unsigned __int8 *v14; // r14
  __int64 v15; // rbp
  __int64 v16; // r9
  __int64 v17; // rdx
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  _DWORD v21[4]; // [rsp+20h] [rbp-58h] BYREF

  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > a2 || (v4 = *a1, v5 = a2 - (_QWORD)a1, a2 - (unsigned __int64)a1 < v4) )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v7 = 255;
      goto LABEL_116;
    }
  }
  else
  {
    v4 = *a1;
    if ( &a1[v4] <= a1 || (unsigned __int64)&a1[v4] > a2 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v7 = 256;
        goto LABEL_116;
      }
      return 3221225473LL;
    }
    v5 = a2 - (_QWORD)a1;
  }
  if ( (unsigned __int8)v4 < 0xDu || (unsigned __int8)v4 != a1[3] * (unsigned __int64)a1[12] + 13 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v7 = 257;
    goto LABEL_116;
  }
  IsEnabledNoReportingNoInline = Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline();
  v9 = *((unsigned __int16 *)a1 + 2);
  v10 = *a1;
  if ( IsEnabledNoReportingNoInline )
  {
    if ( (unsigned __int16)v9 < v10 || v5 < v9 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_19;
      v12 = 258;
LABEL_18:
      WPP_SF_(v11->AttachedDevice, v12, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
LABEL_19:
      v21[0] = 52848518;
      v21[1] = 6;
      v21[2] = -1073741823;
      RtlLogUnexpectedCodepath(v21);
      return 3221225473LL;
    }
  }
  else if ( (unsigned __int16)v9 < v10 || (v13 = &a1[v9], v13 <= a1) || (unsigned __int64)v13 > a2 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_19;
    v12 = 259;
    goto LABEL_18;
  }
  v14 = a1 + 13;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 260, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 261, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 262, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, *a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 263, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[1]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 264, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[2]);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  265,
                  WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                  a1[3]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    266,
                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    *((unsigned __int16 *)a1 + 2));
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      267,
                      WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                      a1[6]);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        268,
                        WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                        a1[7]);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          269,
                          WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                          a1[8]);
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            270,
                            WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                            a1[9]);
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              271,
                              WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                              a1[10]);
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          {
                            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                272,
                                WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                                a1[11]);
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                273,
                                WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                                a1[12]);
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
  while ( v14 < &a1[*a1] )
  {
    v15 = a1[12];
    v16 = 0;
    LODWORD(v17) = a1[12];
    if ( a1[12] )
    {
      do
      {
        v17 = (unsigned int)(v17 - 1);
        v16 = (unsigned int)v14[v17] | ((_DWORD)v16 << 8);
      }
      while ( (_DWORD)v17 );
    }
    switch ( (_BYTE)v15 )
    {
      case 1:
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v19 = 274;
LABEL_84:
          WPP_SF_d(v18->AttachedDevice, v19, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, v16);
        }
        break;
      case 2:
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v19 = 275;
          goto LABEL_84;
        }
        break;
      case 3:
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v19 = 276;
          goto LABEL_84;
        }
        break;
      case 4:
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v19 = 277;
          goto LABEL_84;
        }
        break;
      case 0:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 278, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
        goto LABEL_90;
    }
    v14 += v15;
  }
LABEL_90:
  if ( a1[3] )
  {
    if ( a1[6] )
    {
      if ( a1[8] )
      {
        if ( a1[9] <= 3u )
          return 0;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225473LL;
        v7 = 282;
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225473LL;
        v7 = 281;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v7 = 280;
    }
LABEL_116:
    WPP_SF_(v6->AttachedDevice, v7, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    return 3221225473LL;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v7 = 279;
    goto LABEL_116;
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400360a4  push    rbx
0x1400360a6  push    rbp
0x1400360a7  push    rsi
0x1400360a8  push    rdi
0x1400360a9  push    r14
0x1400360ab  push    r15
0x1400360ad  sub     rsp, 48h
0x1400360b1  mov     rax, cs:__security_cookie
0x1400360b8  xor     rax, rsp
0x1400360bb  mov     [rsp+78h+var_48], rax
0x1400360c0  mov     rdi, rdx
0x1400360c3  mov     rsi, rcx
0x1400360c6  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x1400360cb  test    eax, eax
0x1400360cd  jnz     short loc_140036113
0x1400360cf  movzx   edx, byte ptr [rsi]
0x1400360d2  lea     rax, [rdx+rsi]
0x1400360d6  cmp     rax, rsi
0x1400360d9  jbe     short loc_1400360E8
0x1400360db  cmp     rax, rdi
0x1400360de  ja      short loc_1400360E8
0x1400360e0  mov     rbx, rdi
0x1400360e3  sub     rbx, rsi
0x1400360e6  jmp     short loc_14003612E
0x1400360e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400360ef  lea     rbx, WPP_GLOBAL_Control
0x1400360f6  cmp     rcx, rbx
0x1400360f9  jz      loc_140036655
0x1400360ff  cmp     byte ptr [rcx+29h], 2
0x140036103  jb      loc_140036655
0x140036109  mov     edx, 100h
0x14003610e  jmp     loc_140036645
0x140036113  cmp     rsi, rdi
0x140036116  ja      loc_140036627
0x14003611c  movzx   edx, byte ptr [rsi]
0x14003611f  mov     rbx, rdi
0x140036122  sub     rbx, rsi
0x140036125  cmp     rbx, rdx
0x140036128  jb      loc_140036627
0x14003612e  cmp     dl, 0Dh
0x140036131  jb      loc_140036607
0x140036137  movzx   eax, byte ptr [rsi+3]
0x14003613b  movzx   ecx, byte ptr [rsi+0Ch]
0x14003613f  imul    rcx, rax
0x140036143  movzx   eax, dl
0x140036146  add     rcx, 0Dh
0x14003614a  cmp     rax, rcx
0x14003614d  jnz     loc_140036607
0x140036153  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x140036158  movzx   ecx, word ptr [rsi+4]
0x14003615c  movzx   edx, byte ptr [rsi]
0x14003615f  test    eax, eax
0x140036161  jz      short loc_1400361C9
0x140036163  cmp     cx, dx
0x140036166  jb      short loc_14003616D
0x140036168  cmp     rbx, rcx
0x14003616b  jnb     short loc_1400361E7
0x14003616d  mov     rcx, cs:WPP_GLOBAL_Control
0x140036174  lea     rbx, WPP_GLOBAL_Control
0x14003617b  cmp     rcx, rbx
0x14003617e  jz      short loc_14003619B
0x140036180  cmp     byte ptr [rcx+29h], 2
0x140036184  jb      short loc_14003619B
0x140036186  mov     edx, 102h
0x14003618b  mov     rcx, [rcx+18h]
0x14003618f  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140036196  call    WPP_SF_
0x14003619b  lea     rcx, [rsp+78h+var_58]
0x1400361a0  mov     [rsp+78h+var_58], 3266786h
0x1400361a8  mov     [rsp+78h+var_54], 6
0x1400361b0  mov     [rsp+78h+var_50], 0C0000001h
0x1400361b8  call    cs:__imp_RtlLogUnexpectedCodepath
0x1400361bf  nop     dword ptr [rax+rax+00h]
0x1400361c4  jmp     loc_140036655
0x1400361c9  cmp     cx, dx
0x1400361cc  jb      loc_1400365DC
0x1400361d2  add     rcx, rsi
0x1400361d5  cmp     rcx, rsi
0x1400361d8  jbe     loc_1400365DC
0x1400361de  cmp     rcx, rdi
0x1400361e1  ja      loc_1400365DC
0x1400361e7  lea     r14, [rsi+0Dh]
0x1400361eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400361f2  lea     rbx, WPP_GLOBAL_Control
0x1400361f9  lea     rdi, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140036200  mov     r15b, 5
0x140036203  cmp     rcx, rbx
0x140036206  jz      loc_140036450
0x14003620c  cmp     [rcx+29h], r15b
0x140036210  jb      short loc_140036223
0x140036212  mov     rcx, [rcx+18h]
0x140036216  mov     edx, 104h
0x14003621b  mov     r8, rdi
0x14003621e  call    WPP_SF_
0x140036223  mov     rcx, cs:WPP_GLOBAL_Control
0x14003622a  cmp     rcx, rbx
0x14003622d  jz      loc_140036450
0x140036233  cmp     [rcx+29h], r15b
0x140036237  jb      short loc_14003624D
0x140036239  mov     rcx, [rcx+18h]
0x14003623d  mov     edx, 105h
0x140036242  mov     r9, rsi
0x140036245  mov     r8, rdi
0x140036248  call    WPP_SF_q
0x14003624d  mov     rcx, cs:WPP_GLOBAL_Control
0x140036254  cmp     rcx, rbx
0x140036257  jz      loc_140036450
0x14003625d  cmp     [rcx+29h], r15b
0x140036261  jb      short loc_140036278
0x140036263  movzx   r9d, byte ptr [rsi]
0x140036267  mov     edx, 106h
0x14003626c  mov     rcx, [rcx+18h]
0x140036270  mov     r8, rdi
0x140036273  call    WPP_SF_d
0x140036278  mov     rcx, cs:WPP_GLOBAL_Control
0x14003627f  cmp     rcx, rbx
0x140036282  jz      loc_140036450
0x140036288  cmp     [rcx+29h], r15b
0x14003628c  jb      short loc_1400362A4
0x14003628e  movzx   r9d, byte ptr [rsi+1]
0x140036293  mov     edx, 107h
0x140036298  mov     rcx, [rcx+18h]
0x14003629c  mov     r8, rdi
0x14003629f  call    WPP_SF_d
0x1400362a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400362ab  cmp     rcx, rbx
0x1400362ae  jz      loc_140036450
0x1400362b4  cmp     [rcx+29h], r15b
0x1400362b8  jb      short loc_1400362D0
0x1400362ba  movzx   r9d, byte ptr [rsi+2]
0x1400362bf  mov     edx, 108h
0x1400362c4  mov     rcx, [rcx+18h]
0x1400362c8  mov     r8, rdi
0x1400362cb  call    WPP_SF_d
0x1400362d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400362d7  cmp     rcx, rbx
0x1400362da  jz      loc_140036450
0x1400362e0  cmp     [rcx+29h], r15b
0x1400362e4  jb      short loc_1400362FC
0x1400362e6  movzx   r9d, byte ptr [rsi+3]
0x1400362eb  mov     edx, 109h
0x1400362f0  mov     rcx, [rcx+18h]
0x1400362f4  mov     r8, rdi
0x1400362f7  call    WPP_SF_d
0x1400362fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140036303  cmp     rcx, rbx
0x140036306  jz      loc_140036450
0x14003630c  cmp     [rcx+29h], r15b
0x140036310  jb      short loc_140036328
0x140036312  movzx   r9d, word ptr [rsi+4]
0x140036317  mov     edx, 10Ah
0x14003631c  mov     rcx, [rcx+18h]
0x140036320  mov     r8, rdi
0x140036323  call    WPP_SF_d
0x140036328  mov     rcx, cs:WPP_GLOBAL_Control
0x14003632f  cmp     rcx, rbx
0x140036332  jz      loc_140036450
0x140036338  cmp     [rcx+29h], r15b
0x14003633c  jb      short loc_140036354
0x14003633e  movzx   r9d, byte ptr [rsi+6]
0x140036343  mov     edx, 10Bh
0x140036348  mov     rcx, [rcx+18h]
0x14003634c  mov     r8, rdi
0x14003634f  call    WPP_SF_d
0x140036354  mov     rcx, cs:WPP_GLOBAL_Control
0x14003635b  cmp     rcx, rbx
0x14003635e  jz      loc_140036450
0x140036364  cmp     [rcx+29h], r15b
0x140036368  jb      short loc_140036380
0x14003636a  movzx   r9d, byte ptr [rsi+7]
0x14003636f  mov     edx, 10Ch
0x140036374  mov     rcx, [rcx+18h]
0x140036378  mov     r8, rdi
0x14003637b  call    WPP_SF_d
0x140036380  mov     rcx, cs:WPP_GLOBAL_Control
0x140036387  cmp     rcx, rbx
0x14003638a  jz      loc_140036450
0x140036390  cmp     [rcx+29h], r15b
0x140036394  jb      short loc_1400363AC
0x140036396  movzx   r9d, byte ptr [rsi+8]
0x14003639b  mov     edx, 10Dh
0x1400363a0  mov     rcx, [rcx+18h]
0x1400363a4  mov     r8, rdi
0x1400363a7  call    WPP_SF_d
0x1400363ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400363b3  cmp     rcx, rbx
0x1400363b6  jz      loc_140036450
0x1400363bc  cmp     [rcx+29h], r15b
0x1400363c0  jb      short loc_1400363D8
0x1400363c2  movzx   r9d, byte ptr [rsi+9]
0x1400363c7  mov     edx, 10Eh
0x1400363cc  mov     rcx, [rcx+18h]
0x1400363d0  mov     r8, rdi
0x1400363d3  call    WPP_SF_d
0x1400363d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400363df  cmp     rcx, rbx
0x1400363e2  jz      short loc_140036450
0x1400363e4  cmp     [rcx+29h], r15b
0x1400363e8  jb      short loc_140036400
0x1400363ea  movzx   r9d, byte ptr [rsi+0Ah]
0x1400363ef  mov     edx, 10Fh
0x1400363f4  mov     rcx, [rcx+18h]
0x1400363f8  mov     r8, rdi
0x1400363fb  call    WPP_SF_d
0x140036400  mov     rcx, cs:WPP_GLOBAL_Control
0x140036407  cmp     rcx, rbx
0x14003640a  jz      short loc_140036450
0x14003640c  cmp     [rcx+29h], r15b
0x140036410  jb      short loc_140036428
0x140036412  movzx   r9d, byte ptr [rsi+0Bh]
0x140036417  mov     edx, 110h
0x14003641c  mov     rcx, [rcx+18h]
0x140036420  mov     r8, rdi
0x140036423  call    WPP_SF_d
0x140036428  mov     rcx, cs:WPP_GLOBAL_Control
0x14003642f  cmp     rcx, rbx
0x140036432  jz      short loc_140036450
0x140036434  cmp     [rcx+29h], r15b
0x140036438  jb      short loc_140036450
0x14003643a  movzx   r9d, byte ptr [rsi+0Ch]
0x14003643f  mov     edx, 111h
0x140036444  mov     rcx, [rcx+18h]
0x140036448  mov     r8, rdi
0x14003644b  call    WPP_SF_d
0x140036450  movzx   eax, byte ptr [rsi]
0x140036453  add     rax, rsi
0x140036456  cmp     r14, rax
0x140036459  jnb     loc_140036536
0x14003645f  movzx   ebp, byte ptr [rsi+0Ch]
0x140036463  xor     r9d, r9d
0x140036466  mov     edx, ebp
0x140036468  test    ebp, ebp
0x14003646a  jz      short loc_14003647E
0x14003646c  dec     edx
0x14003646e  shl     r9d, 8
0x140036472  movzx   ecx, byte ptr [rdx+r14]
0x140036477  or      r9d, ecx
0x14003647a  test    edx, edx
0x14003647c  jnz     short loc_14003646C
0x14003647e  cmp     bpl, 1
0x140036482  jnz     short loc_14003649D
0x140036484  mov     rcx, cs:WPP_GLOBAL_Control
0x14003648b  cmp     rcx, rbx
0x14003648e  jz      short loc_14003650B
0x140036490  cmp     [rcx+29h], r15b
0x140036494  jb      short loc_14003650B
0x140036496  mov     edx, 112h
0x14003649b  jmp     short loc_1400364F8
0x14003649d  cmp     bpl, 2
0x1400364a1  jnz     short loc_1400364BC
0x1400364a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400364aa  cmp     rcx, rbx
0x1400364ad  jz      short loc_14003650B
0x1400364af  cmp     [rcx+29h], r15b
0x1400364b3  jb      short loc_14003650B
0x1400364b5  mov     edx, 113h
0x1400364ba  jmp     short loc_1400364F8
0x1400364bc  cmp     bpl, 3
0x1400364c0  jnz     short loc_1400364DB
0x1400364c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400364c9  cmp     rcx, rbx
0x1400364cc  jz      short loc_14003650B
0x1400364ce  cmp     [rcx+29h], r15b
0x1400364d2  jb      short loc_14003650B
0x1400364d4  mov     edx, 114h
0x1400364d9  jmp     short loc_1400364F8
0x1400364db  cmp     bpl, 4
0x1400364df  jnz     short loc_140036506
0x1400364e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400364e8  cmp     rcx, rbx
0x1400364eb  jz      short loc_14003650B
0x1400364ed  cmp     [rcx+29h], r15b
0x1400364f1  jb      short loc_14003650B
0x1400364f3  mov     edx, 115h
0x1400364f8  mov     rcx, [rcx+18h]
0x1400364fc  mov     r8, rdi
0x1400364ff  call    WPP_SF_d
0x140036504  jmp     short loc_14003650B
0x140036506  test    bpl, bpl
0x140036509  jz      short loc_140036513
0x14003650b  add     r14, rbp
0x14003650e  jmp     loc_140036450
0x140036513  mov     rcx, cs:WPP_GLOBAL_Control
0x14003651a  cmp     rcx, rbx
0x14003651d  jz      short loc_140036536
0x14003651f  cmp     [rcx+29h], r15b
0x140036523  jb      short loc_140036536
0x140036525  mov     rcx, [rcx+18h]
0x140036529  mov     edx, 116h
0x14003652e  mov     r8, rdi
0x140036531  call    WPP_SF_
0x140036536  cmp     byte ptr [rsi+3], 0
0x14003653a  jnz     short loc_140036563
0x14003653c  mov     rcx, cs:WPP_GLOBAL_Control
0x140036543  cmp     rcx, rbx
0x140036546  jz      loc_140036655
0x14003654c  cmp     byte ptr [rcx+29h], 2
0x140036550  jb      loc_140036655
0x140036556  mov     edx, 117h
0x14003655b  mov     r8, rdi
  ... truncated ...
```

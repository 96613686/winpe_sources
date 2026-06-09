# DumpAndValidateFrameUncompressed

- ea: `0x140034b88`
- end: `0x1400351d2`
- name: `DumpAndValidateFrameUncompressed`
- size: `1610`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002f590`
- `0x14002f8cc`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x14001b118`
- `0x14001b15c`
- `0x14001b708`
- `0x140034b88`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateFrameUncompressed(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int64 v4; // rdx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned __int8 v8; // dl
  unsigned __int8 v9; // bp
  unsigned __int8 v10; // r8
  unsigned int v11; // eax
  unsigned int v12; // ecx
  unsigned int v13; // r8d
  unsigned __int8 i; // al
  unsigned int v15; // edx

  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > a2 || (v4 = *a1, a2 - (unsigned __int64)a1 < v4) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 348;
      goto LABEL_130;
    }
  }
  else
  {
    v4 = *a1;
    if ( &a1[v4] <= a1 || (unsigned __int64)&a1[v4] > a2 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 349;
      goto LABEL_130;
    }
  }
  if ( (unsigned __int8)v4 >= 0x1Au )
  {
    v7 = SizeOfVideoFrameUncompressed(a1, v4);
    if ( v8 == v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 351, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 352, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 353, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, *a1);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  354,
                  WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                  a1[1]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    355,
                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    a1[2]);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      356,
                      WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                      a1[3]);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        357,
                        WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                        a1[4]);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          358,
                          WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                          *(unsigned __int16 *)(a1 + 5));
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            359,
                            WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                            *(unsigned __int16 *)(a1 + 7));
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              360,
                              WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                              *(unsigned int *)(a1 + 9));
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          {
                            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                361,
                                WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                                *(unsigned int *)(a1 + 13));
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            {
                              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  362,
                                  WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                                  *(unsigned int *)(a1 + 17));
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              {
                                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                                  WPP_SF_d(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    363,
                                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                                    *(unsigned int *)(a1 + 21));
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                                {
                                  WPP_SF_d(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    364,
                                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                                    a1[25]);
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
      if ( a1[25] )
      {
        v9 = 0;
        do
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_dd(
              WPP_GLOBAL_Control->AttachedDevice,
              368,
              WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
              (unsigned int)v9 + 1,
              *(_DWORD *)&a1[4 * v9 + 26]);
          ++v9;
        }
        while ( v9 < a1[25] );
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            365,
            WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
            *(unsigned int *)(a1 + 26));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              366,
              WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
              *(unsigned int *)(a1 + 30));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              367,
              WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
              *(unsigned int *)(a1 + 34));
        }
      }
      if ( !a1[3] )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225473LL;
        v6 = 369;
        goto LABEL_130;
      }
      if ( !*(_WORD *)(a1 + 5) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225473LL;
        v6 = 370;
        goto LABEL_130;
      }
      if ( !*(_WORD *)(a1 + 7) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225473LL;
        v6 = 371;
        goto LABEL_130;
      }
      if ( !*(_DWORD *)(a1 + 9) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225473LL;
        v6 = 372;
        goto LABEL_130;
      }
      if ( !*(_DWORD *)(a1 + 13) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225473LL;
        v6 = 373;
        goto LABEL_130;
      }
      if ( !*(_DWORD *)(a1 + 21) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225473LL;
        v6 = 374;
        goto LABEL_130;
      }
      v10 = a1[25];
      if ( v10 )
      {
        for ( i = 0; i < v10; ++i )
        {
          v15 = *(_DWORD *)&a1[4 * i + 26];
          if ( !v15 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v6 = 379;
              goto LABEL_130;
            }
            return 3221225473LL;
          }
          if ( i && v15 <= *(_DWORD *)&a1[4 * i + 22] )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v6 = 380;
              goto LABEL_130;
            }
            return 3221225473LL;
          }
        }
      }
      else
      {
        v11 = *(_DWORD *)(a1 + 30);
        if ( !v11 || (v12 = *(_DWORD *)(a1 + 26)) == 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            return 3221225473LL;
          v6 = 375;
          goto LABEL_130;
        }
        v13 = *(_DWORD *)(a1 + 34);
        if ( v13 )
        {
          if ( v11 <= v12 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              return 3221225473LL;
            v6 = 377;
            goto LABEL_130;
          }
          if ( (v11 - v12) % v13 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
              return 3221225473LL;
            v6 = 378;
            goto LABEL_130;
          }
        }
        else if ( v12 != v11 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            return 3221225473LL;
          v6 = 376;
          goto LABEL_130;
        }
      }
      return 0;
    }
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    return 3221225473LL;
  v6 = 350;
LABEL_130:
  WPP_SF_(v5->AttachedDevice, v6, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
  return 3221225473LL;
}

```

## disassembly

```asm
0x140034b88  push    rbx
0x140034b8a  push    rbp
0x140034b8b  push    rsi
0x140034b8c  push    rdi
0x140034b8d  push    r14
0x140034b8f  push    r15
0x140034b91  sub     rsp, 38h
0x140034b95  mov     rbx, rdx
0x140034b98  mov     rdi, rcx
0x140034b9b  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x140034ba0  xor     r15d, r15d
0x140034ba3  test    eax, eax
0x140034ba5  jnz     short loc_140034BE3
0x140034ba7  movzx   edx, byte ptr [rdi]
0x140034baa  lea     rax, [rdx+rdi]
0x140034bae  cmp     rax, rdi
0x140034bb1  jbe     short loc_140034BB8
0x140034bb3  cmp     rax, rbx
0x140034bb6  jbe     short loc_140034BFB
0x140034bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140034bbf  lea     rbx, WPP_GLOBAL_Control
0x140034bc6  cmp     rcx, rbx
0x140034bc9  jz      loc_1400351BF
0x140034bcf  cmp     byte ptr [rcx+29h], 2
0x140034bd3  jb      loc_1400351BF
0x140034bd9  mov     edx, 15Dh
0x140034bde  jmp     loc_1400351AF
0x140034be3  cmp     rdi, rbx
0x140034be6  ja      loc_140035191
0x140034bec  movzx   edx, byte ptr [rdi]
0x140034bef  sub     rbx, rdi
0x140034bf2  cmp     rbx, rdx
0x140034bf5  jb      loc_140035191
0x140034bfb  cmp     dl, 1Ah
0x140034bfe  jb      loc_140035171
0x140034c04  mov     rcx, rdi
0x140034c07  call    SizeOfVideoFrameUncompressed
0x140034c0c  movzx   ecx, dl
0x140034c0f  cmp     rcx, rax
0x140034c12  jnz     loc_140035171
0x140034c18  mov     rcx, cs:WPP_GLOBAL_Control
0x140034c1f  lea     rbx, WPP_GLOBAL_Control
0x140034c26  lea     rsi, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140034c2d  mov     r14b, 5
0x140034c30  cmp     rcx, rbx
0x140034c33  jz      loc_140034E79
0x140034c39  cmp     [rcx+29h], r14b
0x140034c3d  jb      short loc_140034C50
0x140034c3f  mov     rcx, [rcx+18h]
0x140034c43  mov     edx, 15Fh
0x140034c48  mov     r8, rsi
0x140034c4b  call    WPP_SF_
0x140034c50  mov     rcx, cs:WPP_GLOBAL_Control
0x140034c57  cmp     rcx, rbx
0x140034c5a  jz      loc_140034E79
0x140034c60  cmp     [rcx+29h], r14b
0x140034c64  jb      short loc_140034C7A
0x140034c66  mov     rcx, [rcx+18h]
0x140034c6a  mov     edx, 160h
0x140034c6f  mov     r9, rdi
0x140034c72  mov     r8, rsi
0x140034c75  call    WPP_SF_q
0x140034c7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034c81  cmp     rcx, rbx
0x140034c84  jz      loc_140034E79
0x140034c8a  cmp     [rcx+29h], r14b
0x140034c8e  jb      short loc_140034CA5
0x140034c90  movzx   r9d, byte ptr [rdi]
0x140034c94  mov     edx, 161h
0x140034c99  mov     rcx, [rcx+18h]
0x140034c9d  mov     r8, rsi
0x140034ca0  call    WPP_SF_d
0x140034ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x140034cac  cmp     rcx, rbx
0x140034caf  jz      loc_140034E79
0x140034cb5  cmp     [rcx+29h], r14b
0x140034cb9  jb      short loc_140034CD1
0x140034cbb  movzx   r9d, byte ptr [rdi+1]
0x140034cc0  mov     edx, 162h
0x140034cc5  mov     rcx, [rcx+18h]
0x140034cc9  mov     r8, rsi
0x140034ccc  call    WPP_SF_d
0x140034cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140034cd8  cmp     rcx, rbx
0x140034cdb  jz      loc_140034E79
0x140034ce1  cmp     [rcx+29h], r14b
0x140034ce5  jb      short loc_140034CFD
0x140034ce7  movzx   r9d, byte ptr [rdi+2]
0x140034cec  mov     edx, 163h
0x140034cf1  mov     rcx, [rcx+18h]
0x140034cf5  mov     r8, rsi
0x140034cf8  call    WPP_SF_d
0x140034cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d04  cmp     rcx, rbx
0x140034d07  jz      loc_140034E79
0x140034d0d  cmp     [rcx+29h], r14b
0x140034d11  jb      short loc_140034D29
0x140034d13  movzx   r9d, byte ptr [rdi+3]
0x140034d18  mov     edx, 164h
0x140034d1d  mov     rcx, [rcx+18h]
0x140034d21  mov     r8, rsi
0x140034d24  call    WPP_SF_d
0x140034d29  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d30  cmp     rcx, rbx
0x140034d33  jz      loc_140034E79
0x140034d39  cmp     [rcx+29h], r14b
0x140034d3d  jb      short loc_140034D55
0x140034d3f  movzx   r9d, byte ptr [rdi+4]
0x140034d44  mov     edx, 165h
0x140034d49  mov     rcx, [rcx+18h]
0x140034d4d  mov     r8, rsi
0x140034d50  call    WPP_SF_d
0x140034d55  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d5c  cmp     rcx, rbx
0x140034d5f  jz      loc_140034E79
0x140034d65  cmp     [rcx+29h], r14b
0x140034d69  jb      short loc_140034D81
0x140034d6b  movzx   r9d, word ptr [rdi+5]
0x140034d70  mov     edx, 166h
0x140034d75  mov     rcx, [rcx+18h]
0x140034d79  mov     r8, rsi
0x140034d7c  call    WPP_SF_d
0x140034d81  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d88  cmp     rcx, rbx
0x140034d8b  jz      loc_140034E79
0x140034d91  cmp     [rcx+29h], r14b
0x140034d95  jb      short loc_140034DAD
0x140034d97  movzx   r9d, word ptr [rdi+7]
0x140034d9c  mov     edx, 167h
0x140034da1  mov     rcx, [rcx+18h]
0x140034da5  mov     r8, rsi
0x140034da8  call    WPP_SF_d
0x140034dad  mov     rcx, cs:WPP_GLOBAL_Control
0x140034db4  cmp     rcx, rbx
0x140034db7  jz      loc_140034E79
0x140034dbd  cmp     [rcx+29h], r14b
0x140034dc1  jb      short loc_140034DD8
0x140034dc3  mov     r9d, [rdi+9]
0x140034dc7  mov     edx, 168h
0x140034dcc  mov     rcx, [rcx+18h]
0x140034dd0  mov     r8, rsi
0x140034dd3  call    WPP_SF_d
0x140034dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140034ddf  cmp     rcx, rbx
0x140034de2  jz      loc_140034E79
0x140034de8  cmp     [rcx+29h], r14b
0x140034dec  jb      short loc_140034E03
0x140034dee  mov     r9d, [rdi+0Dh]
0x140034df2  mov     edx, 169h
0x140034df7  mov     rcx, [rcx+18h]
0x140034dfb  mov     r8, rsi
0x140034dfe  call    WPP_SF_d
0x140034e03  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e0a  cmp     rcx, rbx
0x140034e0d  jz      short loc_140034E79
0x140034e0f  cmp     [rcx+29h], r14b
0x140034e13  jb      short loc_140034E2A
0x140034e15  mov     r9d, [rdi+11h]
0x140034e19  mov     edx, 16Ah
0x140034e1e  mov     rcx, [rcx+18h]
0x140034e22  mov     r8, rsi
0x140034e25  call    WPP_SF_d
0x140034e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e31  cmp     rcx, rbx
0x140034e34  jz      short loc_140034E79
0x140034e36  cmp     [rcx+29h], r14b
0x140034e3a  jb      short loc_140034E51
0x140034e3c  mov     r9d, [rdi+15h]
0x140034e40  mov     edx, 16Bh
0x140034e45  mov     rcx, [rcx+18h]
0x140034e49  mov     r8, rsi
0x140034e4c  call    WPP_SF_d
0x140034e51  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e58  cmp     rcx, rbx
0x140034e5b  jz      short loc_140034E79
0x140034e5d  cmp     [rcx+29h], r14b
0x140034e61  jb      short loc_140034E79
0x140034e63  movzx   r9d, byte ptr [rdi+19h]
0x140034e68  mov     edx, 16Ch
0x140034e6d  mov     rcx, [rcx+18h]
0x140034e71  mov     r8, rsi
0x140034e74  call    WPP_SF_d
0x140034e79  mov     al, [rdi+19h]
0x140034e7c  test    al, al
0x140034e7e  jnz     short loc_140034EFF
0x140034e80  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e87  cmp     rcx, rbx
0x140034e8a  jz      loc_140034F45
0x140034e90  cmp     [rcx+29h], r14b
0x140034e94  jb      short loc_140034EAB
0x140034e96  mov     r9d, [rdi+1Ah]
0x140034e9a  mov     edx, 16Dh
0x140034e9f  mov     rcx, [rcx+18h]
0x140034ea3  mov     r8, rsi
0x140034ea6  call    WPP_SF_d
0x140034eab  mov     rcx, cs:WPP_GLOBAL_Control
0x140034eb2  cmp     rcx, rbx
0x140034eb5  jz      loc_140034F45
0x140034ebb  cmp     [rcx+29h], r14b
0x140034ebf  jb      short loc_140034ED6
0x140034ec1  mov     r9d, [rdi+1Eh]
0x140034ec5  mov     edx, 16Eh
0x140034eca  mov     rcx, [rcx+18h]
0x140034ece  mov     r8, rsi
0x140034ed1  call    WPP_SF_d
0x140034ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x140034edd  cmp     rcx, rbx
0x140034ee0  jz      short loc_140034F45
0x140034ee2  cmp     [rcx+29h], r14b
0x140034ee6  jb      short loc_140034F45
0x140034ee8  mov     r9d, [rdi+22h]
0x140034eec  mov     edx, 16Fh
0x140034ef1  mov     rcx, [rcx+18h]
0x140034ef5  mov     r8, rsi
0x140034ef8  call    WPP_SF_d
0x140034efd  jmp     short loc_140034F45
0x140034eff  mov     bpl, r15b
0x140034f02  test    al, al
0x140034f04  jz      short loc_140034F45
0x140034f06  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f0d  cmp     rcx, rbx
0x140034f10  jz      short loc_140034F3C
0x140034f12  cmp     [rcx+29h], r14b
0x140034f16  jb      short loc_140034F3C
0x140034f18  mov     rcx, [rcx+18h]
0x140034f1c  mov     edx, 170h
0x140034f21  movzx   eax, bpl
0x140034f25  mov     r8, rsi
0x140034f28  movzx   r9d, bpl
0x140034f2c  inc     r9d
0x140034f2f  mov     eax, [rdi+rax*4+1Ah]
0x140034f33  mov     [rsp+68h+var_48], eax
0x140034f37  call    WPP_SF_dd
0x140034f3c  inc     bpl
0x140034f3f  cmp     bpl, [rdi+19h]
0x140034f43  jb      short loc_140034F06
0x140034f45  cmp     [rdi+3], r15b
0x140034f49  jnz     short loc_140034F72
0x140034f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f52  cmp     rcx, rbx
0x140034f55  jz      loc_1400351BF
0x140034f5b  cmp     byte ptr [rcx+29h], 2
0x140034f5f  jb      loc_1400351BF
0x140034f65  mov     edx, 171h
0x140034f6a  mov     r8, rsi
0x140034f6d  jmp     loc_1400351B6
0x140034f72  cmp     [rdi+5], r15w
0x140034f77  jnz     short loc_140034F9A
0x140034f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f80  cmp     rcx, rbx
0x140034f83  jz      loc_1400351BF
0x140034f89  cmp     byte ptr [rcx+29h], 2
0x140034f8d  jb      loc_1400351BF
0x140034f93  mov     edx, 172h
0x140034f98  jmp     short loc_140034F6A
0x140034f9a  cmp     [rdi+7], r15w
0x140034f9f  jnz     short loc_140034FC2
0x140034fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140034fa8  cmp     rcx, rbx
0x140034fab  jz      loc_1400351BF
0x140034fb1  cmp     byte ptr [rcx+29h], 2
0x140034fb5  jb      loc_1400351BF
0x140034fbb  mov     edx, 173h
0x140034fc0  jmp     short loc_140034F6A
0x140034fc2  cmp     [rdi+9], r15d
0x140034fc6  jnz     short loc_140034FE9
0x140034fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140034fcf  cmp     rcx, rbx
0x140034fd2  jz      loc_1400351BF
0x140034fd8  cmp     byte ptr [rcx+29h], 2
0x140034fdc  jb      loc_1400351BF
0x140034fe2  mov     edx, 174h
0x140034fe7  jmp     short loc_140034F6A
0x140034fe9  cmp     [rdi+0Dh], r15d
0x140034fed  jnz     short loc_140035013
0x140034fef  mov     rcx, cs:WPP_GLOBAL_Control
0x140034ff6  cmp     rcx, rbx
0x140034ff9  jz      loc_1400351BF
0x140034fff  cmp     byte ptr [rcx+29h], 2
0x140035003  jb      loc_1400351BF
0x140035009  mov     edx, 175h
0x14003500e  jmp     loc_140034F6A
0x140035013  cmp     [rdi+15h], r15d
0x140035017  jnz     short loc_14003503D
0x140035019  mov     rcx, cs:WPP_GLOBAL_Control
0x140035020  cmp     rcx, rbx
0x140035023  jz      loc_1400351BF
0x140035029  cmp     byte ptr [rcx+29h], 2
0x14003502d  jb      loc_1400351BF
0x140035033  mov     edx, 176h
0x140035038  jmp     loc_140034F6A
0x14003503d  mov     r8b, [rdi+19h]
0x140035041  test    r8b, r8b
0x140035044  jnz     loc_140035114
0x14003504a  mov     eax, [rdi+1Eh]
0x14003504d  test    eax, eax
0x14003504f  jz      loc_1400350F0
0x140035055  mov     ecx, [rdi+1Ah]
0x140035058  test    ecx, ecx
0x14003505a  jz      loc_1400350F0
  ... truncated ...
```

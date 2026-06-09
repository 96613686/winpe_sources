# DumpAndValidateConfigDescriptor

- ea: `0x140030208`
- end: `0x1400304a3`
- name: `DumpAndValidateConfigDescriptor`
- size: `667`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x14002f2e0`
- `0x14002f3e8`

## callees

- `0x140004bac`
- `0x14001b118`
- `0x14001b15c`
- `0x140030208`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateConfigDescriptor(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int64 v4; // rax
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx

  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > a2 || (v4 = *a1, a2 - (unsigned __int64)a1 < v4) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 210;
LABEL_47:
      WPP_SF_(v5->AttachedDevice, v6, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
      return 3221225473LL;
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
      v6 = 211;
      goto LABEL_47;
    }
  }
  if ( (_BYTE)v4 != 9 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 212;
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 213, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 214, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 215, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, *a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 216, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[1]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                217,
                WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                *((unsigned __int16 *)a1 + 1));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  218,
                  WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                  a1[4]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    219,
                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    a1[5]);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      220,
                      WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                      a1[6]);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        221,
                        WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                        a1[7]);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        222,
                        WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                        a1[8]);
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
  return 0;
}

```

## disassembly

```asm
0x140030208  mov     [rsp+arg_0], rbx
0x14003020d  mov     [rsp+arg_8], rsi
0x140030212  push    rdi
0x140030213  sub     rsp, 20h
0x140030217  mov     rbx, rdx
0x14003021a  mov     rsi, rcx
0x14003021d  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x140030222  test    eax, eax
0x140030224  jz      short loc_140030261
0x140030226  cmp     rsi, rbx
0x140030229  ja      short loc_140030236
0x14003022b  movzx   eax, byte ptr [rsi]
0x14003022e  sub     rbx, rsi
0x140030231  cmp     rbx, rax
0x140030234  jnb     short loc_14003027A
0x140030236  mov     rcx, cs:WPP_GLOBAL_Control
0x14003023d  lea     rbx, WPP_GLOBAL_Control
0x140030244  cmp     rcx, rbx
0x140030247  jz      loc_14003048D
0x14003024d  cmp     byte ptr [rcx+29h], 2
0x140030251  jb      loc_14003048D
0x140030257  mov     edx, 0D2h
0x14003025c  jmp     loc_14003047D
0x140030261  movzx   eax, byte ptr [rsi]
0x140030264  lea     rcx, [rax+rsi]
0x140030268  cmp     rcx, rsi
0x14003026b  jbe     loc_14003045F
0x140030271  cmp     rcx, rbx
0x140030274  ja      loc_14003045F
0x14003027a  cmp     al, 9
0x14003027c  jz      short loc_1400302A9
0x14003027e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030285  lea     rbx, WPP_GLOBAL_Control
0x14003028c  cmp     rcx, rbx
0x14003028f  jz      loc_14003048D
0x140030295  cmp     byte ptr [rcx+29h], 2
0x140030299  jb      loc_14003048D
0x14003029f  mov     edx, 0D4h
0x1400302a4  jmp     loc_14003047D
0x1400302a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400302b0  lea     rbx, WPP_GLOBAL_Control
0x1400302b7  cmp     rcx, rbx
0x1400302ba  jz      loc_14003045B
0x1400302c0  cmp     byte ptr [rcx+29h], 5
0x1400302c4  lea     rdi, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400302cb  jb      short loc_1400302DE
0x1400302cd  mov     rcx, [rcx+18h]
0x1400302d1  mov     edx, 0D5h
0x1400302d6  mov     r8, rdi
0x1400302d9  call    WPP_SF_
0x1400302de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400302e5  cmp     rcx, rbx
0x1400302e8  jz      loc_14003045B
0x1400302ee  cmp     byte ptr [rcx+29h], 5
0x1400302f2  jb      short loc_140030308
0x1400302f4  mov     rcx, [rcx+18h]
0x1400302f8  mov     edx, 0D6h
0x1400302fd  mov     r9, rsi
0x140030300  mov     r8, rdi
0x140030303  call    WPP_SF_q
0x140030308  mov     rcx, cs:WPP_GLOBAL_Control
0x14003030f  cmp     rcx, rbx
0x140030312  jz      loc_14003045B
0x140030318  cmp     byte ptr [rcx+29h], 5
0x14003031c  jb      short loc_140030333
0x14003031e  movzx   r9d, byte ptr [rsi]
0x140030322  mov     edx, 0D7h
0x140030327  mov     rcx, [rcx+18h]
0x14003032b  mov     r8, rdi
0x14003032e  call    WPP_SF_d
0x140030333  mov     rcx, cs:WPP_GLOBAL_Control
0x14003033a  cmp     rcx, rbx
0x14003033d  jz      loc_14003045B
0x140030343  cmp     byte ptr [rcx+29h], 5
0x140030347  jb      short loc_14003035F
0x140030349  movzx   r9d, byte ptr [rsi+1]
0x14003034e  mov     edx, 0D8h
0x140030353  mov     rcx, [rcx+18h]
0x140030357  mov     r8, rdi
0x14003035a  call    WPP_SF_d
0x14003035f  mov     rcx, cs:WPP_GLOBAL_Control
0x140030366  cmp     rcx, rbx
0x140030369  jz      loc_14003045B
0x14003036f  cmp     byte ptr [rcx+29h], 5
0x140030373  jb      short loc_14003038B
0x140030375  movzx   r9d, word ptr [rsi+2]
0x14003037a  mov     edx, 0D9h
0x14003037f  mov     rcx, [rcx+18h]
0x140030383  mov     r8, rdi
0x140030386  call    WPP_SF_d
0x14003038b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030392  cmp     rcx, rbx
0x140030395  jz      loc_14003045B
0x14003039b  cmp     byte ptr [rcx+29h], 5
0x14003039f  jb      short loc_1400303B7
0x1400303a1  movzx   r9d, byte ptr [rsi+4]
0x1400303a6  mov     edx, 0DAh
0x1400303ab  mov     rcx, [rcx+18h]
0x1400303af  mov     r8, rdi
0x1400303b2  call    WPP_SF_d
0x1400303b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400303be  cmp     rcx, rbx
0x1400303c1  jz      loc_14003045B
0x1400303c7  cmp     byte ptr [rcx+29h], 5
0x1400303cb  jb      short loc_1400303E3
0x1400303cd  movzx   r9d, byte ptr [rsi+5]
0x1400303d2  mov     edx, 0DBh
0x1400303d7  mov     rcx, [rcx+18h]
0x1400303db  mov     r8, rdi
0x1400303de  call    WPP_SF_d
0x1400303e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400303ea  cmp     rcx, rbx
0x1400303ed  jz      short loc_14003045B
0x1400303ef  cmp     byte ptr [rcx+29h], 5
0x1400303f3  jb      short loc_14003040B
0x1400303f5  movzx   r9d, byte ptr [rsi+6]
0x1400303fa  mov     edx, 0DCh
0x1400303ff  mov     rcx, [rcx+18h]
0x140030403  mov     r8, rdi
0x140030406  call    WPP_SF_d
0x14003040b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030412  cmp     rcx, rbx
0x140030415  jz      short loc_14003045B
0x140030417  cmp     byte ptr [rcx+29h], 5
0x14003041b  jb      short loc_140030433
0x14003041d  movzx   r9d, byte ptr [rsi+7]
0x140030422  mov     edx, 0DDh
0x140030427  mov     rcx, [rcx+18h]
0x14003042b  mov     r8, rdi
0x14003042e  call    WPP_SF_d
0x140030433  mov     rcx, cs:WPP_GLOBAL_Control
0x14003043a  cmp     rcx, rbx
0x14003043d  jz      short loc_14003045B
0x14003043f  cmp     byte ptr [rcx+29h], 5
0x140030443  jb      short loc_14003045B
0x140030445  movzx   r9d, byte ptr [rsi+8]
0x14003044a  mov     edx, 0DEh
0x14003044f  mov     rcx, [rcx+18h]
0x140030453  mov     r8, rdi
0x140030456  call    WPP_SF_d
0x14003045b  xor     eax, eax
0x14003045d  jmp     short loc_140030492
0x14003045f  mov     rcx, cs:WPP_GLOBAL_Control
0x140030466  lea     rbx, WPP_GLOBAL_Control
0x14003046d  cmp     rcx, rbx
0x140030470  jz      short loc_14003048D
0x140030472  cmp     byte ptr [rcx+29h], 2
0x140030476  jb      short loc_14003048D
0x140030478  mov     edx, 0D3h
0x14003047d  mov     rcx, [rcx+18h]
0x140030481  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140030488  call    WPP_SF_
0x14003048d  mov     eax, 0C0000001h
0x140030492  mov     rbx, [rsp+28h+arg_0]
0x140030497  mov     rsi, [rsp+28h+arg_8]
0x14003049c  add     rsp, 20h
0x1400304a0  pop     rdi
0x1400304a1  retn
```

# DumpAndValidateExtensionUnit

- ea: `0x140030704`
- end: `0x140030aea`
- name: `DumpAndValidateExtensionUnit`
- size: `998`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x14002f590`
- `0x14002f8cc`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x14001b118`
- `0x14001b15c`
- `0x14002d844`
- `0x140030704`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateExtensionUnit(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int64 v4; // rax
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned __int8 *v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rbx
  __int64 i; // r9

  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > a2 || (v4 = *a1, a2 - (unsigned __int64)a1 < v4) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 160;
LABEL_69:
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
      v6 = 161;
      goto LABEL_69;
    }
  }
  if ( (unsigned __int8)v4 < 0x16u
    || ((v7 = a1[21], v8 = &a1[v7 + 22], v8 < a1 + 22) || v8 >= &a1[(unsigned __int8)v4]
      ? (v9 = 0)
      : (v9 = v7 + *v8 + 24LL),
        (unsigned __int8)v4 != v9) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 162;
    goto LABEL_69;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 164, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 165, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, *a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[1]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[2]);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  168,
                  WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                  a1[3]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_DDDDDDDDDDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    169,
                    (unsigned int)WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    *((_DWORD *)a1 + 1),
                    *((_WORD *)a1 + 4),
                    *((_WORD *)a1 + 5),
                    a1[12],
                    a1[13],
                    a1[14],
                    a1[15],
                    a1[16],
                    a1[17],
                    a1[18],
                    a1[19]);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      170,
                      WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                      a1[20]);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      171,
                      WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                      a1[21]);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  LOBYTE(v10) = a1[21];
  v11 = 0;
  if ( (_BYTE)v10 )
  {
    do
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          172,
          WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
          (unsigned int)v11,
          a1[v11 + 22]);
      v10 = a1[21];
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (unsigned int)v11 < v10 );
  }
  if ( !a1[3] )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 173;
    goto LABEL_69;
  }
  if ( !(_BYTE)v10 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 174;
    goto LABEL_69;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= (unsigned __int8)v10 )
      return 0;
    if ( !a1[i + 22] )
      break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      175,
      WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
      (unsigned int)(i + 1));
  return 3221225473LL;
}

```

## disassembly

```asm
0x140030704  push    rbx
0x140030706  push    rbp
0x140030707  push    rsi
0x140030708  push    rdi
0x140030709  push    r12
0x14003070b  push    r13
0x14003070d  push    r14
0x14003070f  push    r15
0x140030711  sub     rsp, 78h
0x140030715  mov     rbx, rdx
0x140030718  mov     r15, rcx
0x14003071b  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x140030720  test    eax, eax
0x140030722  jnz     short loc_140030761
0x140030724  movzx   eax, byte ptr [r15]
0x140030728  lea     rcx, [rax+r15]
0x14003072c  cmp     rcx, r15
0x14003072f  jbe     short loc_140030736
0x140030731  cmp     rcx, rbx
0x140030734  jbe     short loc_14003077A
0x140030736  mov     rcx, cs:WPP_GLOBAL_Control
0x14003073d  lea     r12, WPP_GLOBAL_Control
0x140030744  cmp     rcx, r12
0x140030747  jz      loc_140030AD3
0x14003074d  cmp     byte ptr [rcx+29h], 2
0x140030751  jb      loc_140030AD3
0x140030757  mov     edx, 0A1h
0x14003075c  jmp     loc_140030AC3
0x140030761  cmp     r15, rbx
0x140030764  ja      loc_140030AA5
0x14003076a  movzx   eax, byte ptr [r15]
0x14003076e  sub     rbx, r15
0x140030771  cmp     rbx, rax
0x140030774  jb      loc_140030AA5
0x14003077a  cmp     al, 16h
0x14003077c  jb      loc_140030A85
0x140030782  movzx   r8d, byte ptr [r15+15h]
0x140030787  lea     rcx, [r15+16h]
0x14003078b  movzx   edx, al
0x14003078e  add     rcx, r8
0x140030791  lea     rax, [r15+16h]
0x140030795  cmp     rcx, rax
0x140030798  jb      short loc_1400307AF
0x14003079a  lea     rax, [rdx+r15]
0x14003079e  cmp     rcx, rax
0x1400307a1  jnb     short loc_1400307AF
0x1400307a3  movzx   ecx, byte ptr [rcx]
0x1400307a6  add     rcx, 18h
0x1400307aa  add     rcx, r8
0x1400307ad  jmp     short loc_1400307B1
0x1400307af  xor     ecx, ecx
0x1400307b1  cmp     rdx, rcx
0x1400307b4  jnz     loc_140030A85
0x1400307ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307c1  lea     r12, WPP_GLOBAL_Control
0x1400307c8  lea     r13, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400307cf  mov     dil, 5
0x1400307d2  cmp     rcx, r12
0x1400307d5  jz      loc_1400309A8
0x1400307db  cmp     [rcx+29h], dil
0x1400307df  jb      short loc_1400307F2
0x1400307e1  mov     rcx, [rcx+18h]
0x1400307e5  mov     edx, 0A3h
0x1400307ea  mov     r8, r13
0x1400307ed  call    WPP_SF_
0x1400307f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307f9  cmp     rcx, r12
0x1400307fc  jz      loc_1400309A8
0x140030802  cmp     [rcx+29h], dil
0x140030806  jb      short loc_14003081C
0x140030808  mov     rcx, [rcx+18h]
0x14003080c  mov     edx, 0A4h
0x140030811  mov     r9, r15
0x140030814  mov     r8, r13
0x140030817  call    WPP_SF_q
0x14003081c  mov     rcx, cs:WPP_GLOBAL_Control
0x140030823  cmp     rcx, r12
0x140030826  jz      loc_1400309A8
0x14003082c  cmp     [rcx+29h], dil
0x140030830  jb      short loc_140030847
0x140030832  movzx   r9d, byte ptr [r15]
0x140030836  mov     edx, 0A5h
0x14003083b  mov     rcx, [rcx+18h]
0x14003083f  mov     r8, r13
0x140030842  call    WPP_SF_d
0x140030847  mov     rcx, cs:WPP_GLOBAL_Control
0x14003084e  cmp     rcx, r12
0x140030851  jz      loc_1400309A8
0x140030857  cmp     [rcx+29h], dil
0x14003085b  jb      short loc_140030873
0x14003085d  movzx   r9d, byte ptr [r15+1]
0x140030862  mov     edx, 0A6h
0x140030867  mov     rcx, [rcx+18h]
0x14003086b  mov     r8, r13
0x14003086e  call    WPP_SF_d
0x140030873  mov     rcx, cs:WPP_GLOBAL_Control
0x14003087a  cmp     rcx, r12
0x14003087d  jz      loc_1400309A8
0x140030883  cmp     [rcx+29h], dil
0x140030887  jb      short loc_14003089F
0x140030889  movzx   r9d, byte ptr [r15+2]
0x14003088e  mov     edx, 0A7h
0x140030893  mov     rcx, [rcx+18h]
0x140030897  mov     r8, r13
0x14003089a  call    WPP_SF_d
0x14003089f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400308a6  cmp     rcx, r12
0x1400308a9  jz      loc_1400309A8
0x1400308af  cmp     [rcx+29h], dil
0x1400308b3  jb      short loc_1400308CB
0x1400308b5  movzx   r9d, byte ptr [r15+3]
0x1400308ba  mov     edx, 0A8h
0x1400308bf  mov     rcx, [rcx+18h]
0x1400308c3  mov     r8, r13
0x1400308c6  call    WPP_SF_d
0x1400308cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400308d2  cmp     rcx, r12
0x1400308d5  jz      loc_1400309A8
0x1400308db  cmp     [rcx+29h], dil
0x1400308df  jb      short loc_140030958
0x1400308e1  movzx   r8d, byte ptr [r15+12h]
0x1400308e6  mov     edx, 0A9h
0x1400308eb  movzx   r9d, byte ptr [r15+11h]
0x1400308f0  movzx   eax, byte ptr [r15+13h]
0x1400308f5  movzx   r10d, byte ptr [r15+10h]
0x1400308fa  movzx   r11d, byte ptr [r15+0Fh]
0x1400308ff  movzx   ebx, byte ptr [r15+0Eh]
0x140030904  movzx   edi, byte ptr [r15+0Dh]
0x140030909  movzx   esi, byte ptr [r15+0Ch]
0x14003090e  movzx   ebp, word ptr [r15+0Ah]
0x140030913  movzx   r14d, word ptr [r15+8]
0x140030918  mov     rcx, [rcx+18h]
0x14003091c  mov     [rsp+0B8h+var_50], eax
0x140030920  mov     [rsp+0B8h+var_58], r8d
0x140030925  mov     r8, r13
0x140030928  mov     [rsp+0B8h+var_60], r9d
0x14003092d  mov     r9d, [r15+4]
0x140030931  mov     [rsp+0B8h+var_68], r10d
0x140030936  mov     [rsp+0B8h+var_70], r11d
0x14003093b  mov     [rsp+0B8h+var_78], ebx
0x14003093f  mov     [rsp+0B8h+var_80], edi
0x140030943  mov     [rsp+0B8h+var_88], esi
0x140030947  mov     [rsp+0B8h+var_90], ebp
0x14003094b  mov     [rsp+0B8h+var_98], r14d
0x140030950  call    WPP_SF_DDDDDDDDDDD
0x140030955  mov     dil, 5
0x140030958  mov     rcx, cs:WPP_GLOBAL_Control
0x14003095f  cmp     rcx, r12
0x140030962  jz      short loc_1400309A8
0x140030964  cmp     [rcx+29h], dil
0x140030968  jb      short loc_140030980
0x14003096a  movzx   r9d, byte ptr [r15+14h]
0x14003096f  mov     edx, 0AAh
0x140030974  mov     rcx, [rcx+18h]
0x140030978  mov     r8, r13
0x14003097b  call    WPP_SF_d
0x140030980  mov     rcx, cs:WPP_GLOBAL_Control
0x140030987  cmp     rcx, r12
0x14003098a  jz      short loc_1400309A8
0x14003098c  cmp     [rcx+29h], dil
0x140030990  jb      short loc_1400309A8
0x140030992  movzx   r9d, byte ptr [r15+15h]
0x140030997  mov     edx, 0ABh
0x14003099c  mov     rcx, [rcx+18h]
0x1400309a0  mov     r8, r13
0x1400309a3  call    WPP_SF_d
0x1400309a8  mov     al, [r15+15h]
0x1400309ac  xor     ebx, ebx
0x1400309ae  test    al, al
0x1400309b0  jz      short loc_1400309EE
0x1400309b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400309b9  cmp     rcx, r12
0x1400309bc  jz      short loc_1400309E3
0x1400309be  cmp     [rcx+29h], dil
0x1400309c2  jb      short loc_1400309E3
0x1400309c4  movzx   r8d, byte ptr [rbx+r15+16h]
0x1400309ca  mov     edx, 0ACh
0x1400309cf  mov     rcx, [rcx+18h]
0x1400309d3  mov     r9d, ebx
0x1400309d6  mov     [rsp+0B8h+var_98], r8d
0x1400309db  mov     r8, r13
0x1400309de  call    WPP_SF_dd
0x1400309e3  movzx   eax, byte ptr [r15+15h]
0x1400309e8  inc     ebx
0x1400309ea  cmp     ebx, eax
0x1400309ec  jb      short loc_1400309B2
0x1400309ee  cmp     byte ptr [r15+3], 0
0x1400309f3  jnz     short loc_140030A1C
0x1400309f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400309fc  cmp     rcx, r12
0x1400309ff  jz      loc_140030AD3
0x140030a05  cmp     byte ptr [rcx+29h], 2
0x140030a09  jb      loc_140030AD3
0x140030a0f  mov     edx, 0ADh
0x140030a14  mov     r8, r13
0x140030a17  jmp     loc_140030ACA
0x140030a1c  test    al, al
0x140030a1e  jnz     short loc_140030A41
0x140030a20  mov     rcx, cs:WPP_GLOBAL_Control
0x140030a27  cmp     rcx, r12
0x140030a2a  jz      loc_140030AD3
0x140030a30  cmp     byte ptr [rcx+29h], 2
0x140030a34  jb      loc_140030AD3
0x140030a3a  mov     edx, 0AEh
0x140030a3f  jmp     short loc_140030A14
0x140030a41  xor     r9d, r9d
0x140030a44  movzx   ecx, al
0x140030a47  cmp     r9d, ecx
0x140030a4a  jnb     short loc_140030A81
0x140030a4c  cmp     byte ptr [r9+r15+16h], 0
0x140030a52  jz      short loc_140030A59
0x140030a54  inc     r9d
0x140030a57  jmp     short loc_140030A47
0x140030a59  mov     rcx, cs:WPP_GLOBAL_Control
0x140030a60  cmp     rcx, r12
0x140030a63  jz      short loc_140030AD3
0x140030a65  cmp     byte ptr [rcx+29h], 2
0x140030a69  jb      short loc_140030AD3
0x140030a6b  mov     rcx, [rcx+18h]
0x140030a6f  inc     r9d
0x140030a72  mov     edx, 0AFh
0x140030a77  mov     r8, r13
0x140030a7a  call    WPP_SF_d
0x140030a7f  jmp     short loc_140030AD3
0x140030a81  xor     eax, eax
0x140030a83  jmp     short loc_140030AD8
0x140030a85  mov     rcx, cs:WPP_GLOBAL_Control
0x140030a8c  lea     r12, WPP_GLOBAL_Control
0x140030a93  cmp     rcx, r12
0x140030a96  jz      short loc_140030AD3
0x140030a98  cmp     byte ptr [rcx+29h], 2
0x140030a9c  jb      short loc_140030AD3
0x140030a9e  mov     edx, 0A2h
0x140030aa3  jmp     short loc_140030AC3
0x140030aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140030aac  lea     r12, WPP_GLOBAL_Control
0x140030ab3  cmp     rcx, r12
0x140030ab6  jz      short loc_140030AD3
0x140030ab8  cmp     byte ptr [rcx+29h], 2
0x140030abc  jb      short loc_140030AD3
0x140030abe  mov     edx, 0A0h
0x140030ac3  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140030aca  mov     rcx, [rcx+18h]
0x140030ace  call    WPP_SF_
0x140030ad3  mov     eax, 0C0000001h
0x140030ad8  add     rsp, 78h
0x140030adc  pop     r15
0x140030ade  pop     r14
0x140030ae0  pop     r13
0x140030ae2  pop     r12
0x140030ae4  pop     rdi
0x140030ae5  pop     rsi
0x140030ae6  pop     rbp
0x140030ae7  pop     rbx
0x140030ae8  retn
```

# DumpAndValidateEndpointDescriptor

- ea: `0x1400304ac`
- end: `0x1400306fe`
- name: `DumpAndValidateEndpointDescriptor`
- size: `594`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14002f2e0`
- `0x14002f3e8`

## callees

- `0x140004bac`
- `0x14001b118`
- `0x14001b15c`
- `0x1400304ac`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateEndpointDescriptor(unsigned __int8 *a1, unsigned __int64 a2)
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
      v6 = 223;
LABEL_41:
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
      v6 = 224;
      goto LABEL_41;
    }
  }
  if ( (_BYTE)v4 != 7 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 225;
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 226, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 227, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 228, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, *a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 229, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[1]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 230, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[2]);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  231,
                  WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                  a1[3]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    232,
                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    *((unsigned __int16 *)a1 + 2));
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    233,
                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    a1[6]);
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
0x1400304ac  mov     [rsp+arg_0], rbx
0x1400304b1  push    rsi
0x1400304b2  sub     rsp, 20h
0x1400304b6  mov     rbx, rdx
0x1400304b9  mov     rsi, rcx
0x1400304bc  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x1400304c1  test    eax, eax
0x1400304c3  jz      short loc_140030500
0x1400304c5  cmp     rsi, rbx
0x1400304c8  ja      short loc_1400304D5
0x1400304ca  movzx   eax, byte ptr [rsi]
0x1400304cd  sub     rbx, rsi
0x1400304d0  cmp     rbx, rax
0x1400304d3  jnb     short loc_140030519
0x1400304d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400304dc  lea     rbx, WPP_GLOBAL_Control
0x1400304e3  cmp     rcx, rbx
0x1400304e6  jz      loc_1400306ED
0x1400304ec  cmp     byte ptr [rcx+29h], 2
0x1400304f0  jb      loc_1400306ED
0x1400304f6  mov     edx, 0DFh
0x1400304fb  jmp     loc_1400306DD
0x140030500  movzx   eax, byte ptr [rsi]
0x140030503  lea     rcx, [rax+rsi]
0x140030507  cmp     rcx, rsi
0x14003050a  jbe     loc_1400306BF
0x140030510  cmp     rcx, rbx
0x140030513  ja      loc_1400306BF
0x140030519  cmp     al, 7
0x14003051b  jz      short loc_140030548
0x14003051d  mov     rcx, cs:WPP_GLOBAL_Control
0x140030524  lea     rbx, WPP_GLOBAL_Control
0x14003052b  cmp     rcx, rbx
0x14003052e  jz      loc_1400306ED
0x140030534  cmp     byte ptr [rcx+29h], 2
0x140030538  jb      loc_1400306ED
0x14003053e  mov     edx, 0E1h
0x140030543  jmp     loc_1400306DD
0x140030548  mov     rcx, cs:WPP_GLOBAL_Control
0x14003054f  lea     rbx, WPP_GLOBAL_Control
0x140030556  cmp     rcx, rbx
0x140030559  jz      loc_1400306BB
0x14003055f  cmp     byte ptr [rcx+29h], 5
0x140030563  jb      short loc_14003057A
0x140030565  mov     rcx, [rcx+18h]
0x140030569  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140030570  mov     edx, 0E2h
0x140030575  call    WPP_SF_
0x14003057a  mov     rcx, cs:WPP_GLOBAL_Control
0x140030581  cmp     rcx, rbx
0x140030584  jz      loc_1400306BB
0x14003058a  cmp     byte ptr [rcx+29h], 5
0x14003058e  jb      short loc_1400305A8
0x140030590  mov     rcx, [rcx+18h]
0x140030594  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14003059b  mov     edx, 0E3h
0x1400305a0  mov     r9, rsi
0x1400305a3  call    WPP_SF_q
0x1400305a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400305af  cmp     rcx, rbx
0x1400305b2  jz      loc_1400306BB
0x1400305b8  cmp     byte ptr [rcx+29h], 5
0x1400305bc  jb      short loc_1400305D7
0x1400305be  movzx   r9d, byte ptr [rsi]
0x1400305c2  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400305c9  mov     rcx, [rcx+18h]
0x1400305cd  mov     edx, 0E4h
0x1400305d2  call    WPP_SF_d
0x1400305d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400305de  cmp     rcx, rbx
0x1400305e1  jz      loc_1400306BB
0x1400305e7  cmp     byte ptr [rcx+29h], 5
0x1400305eb  jb      short loc_140030607
0x1400305ed  movzx   r9d, byte ptr [rsi+1]
0x1400305f2  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400305f9  mov     rcx, [rcx+18h]
0x1400305fd  mov     edx, 0E5h
0x140030602  call    WPP_SF_d
0x140030607  mov     rcx, cs:WPP_GLOBAL_Control
0x14003060e  cmp     rcx, rbx
0x140030611  jz      loc_1400306BB
0x140030617  cmp     byte ptr [rcx+29h], 5
0x14003061b  jb      short loc_140030637
0x14003061d  movzx   r9d, byte ptr [rsi+2]
0x140030622  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140030629  mov     rcx, [rcx+18h]
0x14003062d  mov     edx, 0E6h
0x140030632  call    WPP_SF_d
0x140030637  mov     rcx, cs:WPP_GLOBAL_Control
0x14003063e  cmp     rcx, rbx
0x140030641  jz      short loc_1400306BB
0x140030643  cmp     byte ptr [rcx+29h], 5
0x140030647  jb      short loc_140030663
0x140030649  movzx   r9d, byte ptr [rsi+3]
0x14003064e  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140030655  mov     rcx, [rcx+18h]
0x140030659  mov     edx, 0E7h
0x14003065e  call    WPP_SF_d
0x140030663  mov     rcx, cs:WPP_GLOBAL_Control
0x14003066a  cmp     rcx, rbx
0x14003066d  jz      short loc_1400306BB
0x14003066f  cmp     byte ptr [rcx+29h], 5
0x140030673  jb      short loc_14003068F
0x140030675  movzx   r9d, word ptr [rsi+4]
0x14003067a  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140030681  mov     rcx, [rcx+18h]
0x140030685  mov     edx, 0E8h
0x14003068a  call    WPP_SF_d
0x14003068f  mov     rcx, cs:WPP_GLOBAL_Control
0x140030696  cmp     rcx, rbx
0x140030699  jz      short loc_1400306BB
0x14003069b  cmp     byte ptr [rcx+29h], 5
0x14003069f  jb      short loc_1400306BB
0x1400306a1  movzx   r9d, byte ptr [rsi+6]
0x1400306a6  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400306ad  mov     rcx, [rcx+18h]
0x1400306b1  mov     edx, 0E9h
0x1400306b6  call    WPP_SF_d
0x1400306bb  xor     eax, eax
0x1400306bd  jmp     short loc_1400306F2
0x1400306bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400306c6  lea     rbx, WPP_GLOBAL_Control
0x1400306cd  cmp     rcx, rbx
0x1400306d0  jz      short loc_1400306ED
0x1400306d2  cmp     byte ptr [rcx+29h], 2
0x1400306d6  jb      short loc_1400306ED
0x1400306d8  mov     edx, 0E0h
0x1400306dd  mov     rcx, [rcx+18h]
0x1400306e1  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400306e8  call    WPP_SF_
0x1400306ed  mov     eax, 0C0000001h
0x1400306f2  mov     rbx, [rsp+28h+arg_0]
0x1400306f7  add     rsp, 20h
0x1400306fb  pop     rsi
0x1400306fc  retn
```

# DumpAndValidateInterfaceDescriptor

- ea: `0x140037068`
- end: `0x140037407`
- name: `DumpAndValidateInterfaceDescriptor`
- size: `927`
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
- `0x140037068`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateInterfaceDescriptor(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int64 v4; // rax
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  unsigned __int8 v9; // al
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx

  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > a2 || (v4 = *a1, a2 - (unsigned __int64)a1 < v4) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 234;
      goto LABEL_78;
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
      v6 = 235;
      goto LABEL_78;
    }
  }
  if ( (_BYTE)v4 != 9 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 236;
    goto LABEL_78;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 237, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 238, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 239, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, *a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 240, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[1]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 241, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[2]);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  242,
                  WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                  a1[3]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    243,
                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    a1[4]);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    244,
                    WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                    a1[5]);
              }
            }
          }
        }
      }
    }
  }
  if ( a1[5] == 14 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_48;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      goto LABEL_45;
    v8 = 245;
    goto LABEL_44;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_48;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v8 = 246;
LABEL_44:
    WPP_SF_(v7->AttachedDevice, v8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
  }
LABEL_45:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 247, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[6]);
LABEL_48:
  v9 = a1[6];
  if ( v9 == 1 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_66;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      goto LABEL_60;
    v11 = 248;
    goto LABEL_59;
  }
  if ( v9 == 2 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_66;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      goto LABEL_60;
    v11 = 249;
    goto LABEL_59;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_66;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v11 = 250;
LABEL_59:
    WPP_SF_(v10->AttachedDevice, v11, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
  }
LABEL_60:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 251, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[7]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 252, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[8]);
  }
LABEL_66:
  if ( a1[5] != 14 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 253;
    goto LABEL_78;
  }
  if ( (unsigned __int8)(a1[6] - 1) <= 1u )
    return 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v6 = 254;
LABEL_78:
    WPP_SF_(v5->AttachedDevice, v6, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x140037068  push    rbx
0x14003706a  push    rbp
0x14003706b  push    rsi
0x14003706c  push    rdi
0x14003706d  sub     rsp, 28h
0x140037071  mov     rbx, rdx
0x140037074  mov     rsi, rcx
0x140037077  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x14003707c  test    eax, eax
0x14003707e  jz      short loc_1400370BB
0x140037080  cmp     rsi, rbx
0x140037083  ja      short loc_140037090
0x140037085  movzx   eax, byte ptr [rsi]
0x140037088  sub     rbx, rsi
0x14003708b  cmp     rbx, rax
0x14003708e  jnb     short loc_1400370D4
0x140037090  mov     rcx, cs:WPP_GLOBAL_Control
0x140037097  lea     rbx, WPP_GLOBAL_Control
0x14003709e  cmp     rcx, rbx
0x1400370a1  jz      loc_1400373F8
0x1400370a7  cmp     byte ptr [rcx+29h], 2
0x1400370ab  jb      loc_1400373F8
0x1400370b1  mov     edx, 0EAh
0x1400370b6  jmp     loc_1400373E8
0x1400370bb  movzx   eax, byte ptr [rsi]
0x1400370be  lea     rcx, [rax+rsi]
0x1400370c2  cmp     rcx, rsi
0x1400370c5  jbe     loc_1400373CA
0x1400370cb  cmp     rcx, rbx
0x1400370ce  ja      loc_1400373CA
0x1400370d4  cmp     al, 9
0x1400370d6  jz      short loc_140037103
0x1400370d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400370df  lea     rbx, WPP_GLOBAL_Control
0x1400370e6  cmp     rcx, rbx
0x1400370e9  jz      loc_1400373F8
0x1400370ef  cmp     byte ptr [rcx+29h], 2
0x1400370f3  jb      loc_1400373F8
0x1400370f9  mov     edx, 0ECh
0x1400370fe  jmp     loc_1400373E8
0x140037103  mov     rcx, cs:WPP_GLOBAL_Control
0x14003710a  lea     rbx, WPP_GLOBAL_Control
0x140037111  lea     rdi, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140037118  mov     bpl, 5
0x14003711b  cmp     rcx, rbx
0x14003711e  jz      loc_140037260
0x140037124  cmp     [rcx+29h], bpl
0x140037128  jb      short loc_14003713B
0x14003712a  mov     rcx, [rcx+18h]
0x14003712e  mov     edx, 0EDh
0x140037133  mov     r8, rdi
0x140037136  call    WPP_SF_
0x14003713b  mov     rcx, cs:WPP_GLOBAL_Control
0x140037142  cmp     rcx, rbx
0x140037145  jz      loc_140037260
0x14003714b  cmp     [rcx+29h], bpl
0x14003714f  jb      short loc_140037165
0x140037151  mov     rcx, [rcx+18h]
0x140037155  mov     edx, 0EEh
0x14003715a  mov     r9, rsi
0x14003715d  mov     r8, rdi
0x140037160  call    WPP_SF_q
0x140037165  mov     rcx, cs:WPP_GLOBAL_Control
0x14003716c  cmp     rcx, rbx
0x14003716f  jz      loc_140037260
0x140037175  cmp     [rcx+29h], bpl
0x140037179  jb      short loc_140037190
0x14003717b  movzx   r9d, byte ptr [rsi]
0x14003717f  mov     edx, 0EFh
0x140037184  mov     rcx, [rcx+18h]
0x140037188  mov     r8, rdi
0x14003718b  call    WPP_SF_d
0x140037190  mov     rcx, cs:WPP_GLOBAL_Control
0x140037197  cmp     rcx, rbx
0x14003719a  jz      loc_140037260
0x1400371a0  cmp     [rcx+29h], bpl
0x1400371a4  jb      short loc_1400371BC
0x1400371a6  movzx   r9d, byte ptr [rsi+1]
0x1400371ab  mov     edx, 0F0h
0x1400371b0  mov     rcx, [rcx+18h]
0x1400371b4  mov     r8, rdi
0x1400371b7  call    WPP_SF_d
0x1400371bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371c3  cmp     rcx, rbx
0x1400371c6  jz      loc_140037260
0x1400371cc  cmp     [rcx+29h], bpl
0x1400371d0  jb      short loc_1400371E8
0x1400371d2  movzx   r9d, byte ptr [rsi+2]
0x1400371d7  mov     edx, 0F1h
0x1400371dc  mov     rcx, [rcx+18h]
0x1400371e0  mov     r8, rdi
0x1400371e3  call    WPP_SF_d
0x1400371e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371ef  cmp     rcx, rbx
0x1400371f2  jz      short loc_140037260
0x1400371f4  cmp     [rcx+29h], bpl
0x1400371f8  jb      short loc_140037210
0x1400371fa  movzx   r9d, byte ptr [rsi+3]
0x1400371ff  mov     edx, 0F2h
0x140037204  mov     rcx, [rcx+18h]
0x140037208  mov     r8, rdi
0x14003720b  call    WPP_SF_d
0x140037210  mov     rcx, cs:WPP_GLOBAL_Control
0x140037217  cmp     rcx, rbx
0x14003721a  jz      short loc_140037260
0x14003721c  cmp     [rcx+29h], bpl
0x140037220  jb      short loc_140037238
0x140037222  movzx   r9d, byte ptr [rsi+4]
0x140037227  mov     edx, 0F3h
0x14003722c  mov     rcx, [rcx+18h]
0x140037230  mov     r8, rdi
0x140037233  call    WPP_SF_d
0x140037238  mov     rcx, cs:WPP_GLOBAL_Control
0x14003723f  cmp     rcx, rbx
0x140037242  jz      short loc_140037260
0x140037244  cmp     [rcx+29h], bpl
0x140037248  jb      short loc_140037260
0x14003724a  movzx   r9d, byte ptr [rsi+5]
0x14003724f  mov     edx, 0F4h
0x140037254  mov     rcx, [rcx+18h]
0x140037258  mov     r8, rdi
0x14003725b  call    WPP_SF_d
0x140037260  cmp     byte ptr [rsi+5], 0Eh
0x140037264  jnz     short loc_14003727F
0x140037266  mov     rcx, cs:WPP_GLOBAL_Control
0x14003726d  cmp     rcx, rbx
0x140037270  jz      short loc_1400372CA
0x140037272  cmp     [rcx+29h], bpl
0x140037276  jb      short loc_1400372A2
0x140037278  mov     edx, 0F5h
0x14003727d  jmp     short loc_140037296
0x14003727f  mov     rcx, cs:WPP_GLOBAL_Control
0x140037286  cmp     rcx, rbx
0x140037289  jz      short loc_1400372CA
0x14003728b  cmp     [rcx+29h], bpl
0x14003728f  jb      short loc_1400372A2
0x140037291  mov     edx, 0F6h
0x140037296  mov     rcx, [rcx+18h]
0x14003729a  mov     r8, rdi
0x14003729d  call    WPP_SF_
0x1400372a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400372a9  cmp     rcx, rbx
0x1400372ac  jz      short loc_1400372CA
0x1400372ae  cmp     [rcx+29h], bpl
0x1400372b2  jb      short loc_1400372CA
0x1400372b4  movzx   r9d, byte ptr [rsi+6]
0x1400372b9  mov     edx, 0F7h
0x1400372be  mov     rcx, [rcx+18h]
0x1400372c2  mov     r8, rdi
0x1400372c5  call    WPP_SF_d
0x1400372ca  mov     al, [rsi+6]
0x1400372cd  cmp     al, 1
0x1400372cf  jnz     short loc_1400372EE
0x1400372d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400372d8  cmp     rcx, rbx
0x1400372db  jz      loc_140037382
0x1400372e1  cmp     [rcx+29h], bpl
0x1400372e5  jb      short loc_140037332
0x1400372e7  mov     edx, 0F8h
0x1400372ec  jmp     short loc_140037326
0x1400372ee  cmp     al, 2
0x1400372f0  jnz     short loc_14003730F
0x1400372f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400372f9  cmp     rcx, rbx
0x1400372fc  jz      loc_140037382
0x140037302  cmp     [rcx+29h], bpl
0x140037306  jb      short loc_140037332
0x140037308  mov     edx, 0F9h
0x14003730d  jmp     short loc_140037326
0x14003730f  mov     rcx, cs:WPP_GLOBAL_Control
0x140037316  cmp     rcx, rbx
0x140037319  jz      short loc_140037382
0x14003731b  cmp     [rcx+29h], bpl
0x14003731f  jb      short loc_140037332
0x140037321  mov     edx, 0FAh
0x140037326  mov     rcx, [rcx+18h]
0x14003732a  mov     r8, rdi
0x14003732d  call    WPP_SF_
0x140037332  mov     rcx, cs:WPP_GLOBAL_Control
0x140037339  cmp     rcx, rbx
0x14003733c  jz      short loc_140037382
0x14003733e  cmp     [rcx+29h], bpl
0x140037342  jb      short loc_14003735A
0x140037344  movzx   r9d, byte ptr [rsi+7]
0x140037349  mov     edx, 0FBh
0x14003734e  mov     rcx, [rcx+18h]
0x140037352  mov     r8, rdi
0x140037355  call    WPP_SF_d
0x14003735a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037361  cmp     rcx, rbx
0x140037364  jz      short loc_140037382
0x140037366  cmp     [rcx+29h], bpl
0x14003736a  jb      short loc_140037382
0x14003736c  movzx   r9d, byte ptr [rsi+8]
0x140037371  mov     edx, 0FCh
0x140037376  mov     rcx, [rcx+18h]
0x14003737a  mov     r8, rdi
0x14003737d  call    WPP_SF_d
0x140037382  cmp     byte ptr [rsi+5], 0Eh
0x140037386  jz      short loc_1400373A4
0x140037388  mov     rcx, cs:WPP_GLOBAL_Control
0x14003738f  cmp     rcx, rbx
0x140037392  jz      short loc_1400373F8
0x140037394  cmp     byte ptr [rcx+29h], 2
0x140037398  jb      short loc_1400373F8
0x14003739a  mov     edx, 0FDh
0x14003739f  mov     r8, rdi
0x1400373a2  jmp     short loc_1400373EF
0x1400373a4  mov     al, [rsi+6]
0x1400373a7  dec     al
0x1400373a9  cmp     al, 1
0x1400373ab  jbe     short loc_1400373C6
0x1400373ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400373b4  cmp     rcx, rbx
0x1400373b7  jz      short loc_1400373F8
0x1400373b9  cmp     byte ptr [rcx+29h], 2
0x1400373bd  jb      short loc_1400373F8
0x1400373bf  mov     edx, 0FEh
0x1400373c4  jmp     short loc_14003739F
0x1400373c6  xor     eax, eax
0x1400373c8  jmp     short loc_1400373FD
0x1400373ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400373d1  lea     rbx, WPP_GLOBAL_Control
0x1400373d8  cmp     rcx, rbx
0x1400373db  jz      short loc_1400373F8
0x1400373dd  cmp     byte ptr [rcx+29h], 2
0x1400373e1  jb      short loc_1400373F8
0x1400373e3  mov     edx, 0EBh
0x1400373e8  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400373ef  mov     rcx, [rcx+18h]
0x1400373f3  call    WPP_SF_
0x1400373f8  mov     eax, 0C0000001h
0x1400373fd  add     rsp, 28h
0x140037401  pop     rdi
0x140037402  pop     rsi
0x140037403  pop     rbp
0x140037404  pop     rbx
0x140037405  retn
```

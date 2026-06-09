# DumpAndValidateClassSpecificInterruptEndpointDescriptor

- ea: `0x14002fdb8`
- end: `0x14002ffaa`
- name: `DumpAndValidateClassSpecificInterruptEndpointDescriptor`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14002fd58`

## callees

- `0x140004bac`
- `0x14001b118`
- `0x14001b15c`
- `0x14002fdb8`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateClassSpecificInterruptEndpointDescriptor(unsigned __int8 *a1, unsigned __int64 a2)
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
      v6 = 709;
LABEL_35:
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
      v6 = 710;
      goto LABEL_35;
    }
  }
  if ( (_BYTE)v4 != 5 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225473LL;
    v6 = 711;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 712, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 713, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 714, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, *a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 715, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[1]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 716, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[2]);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                717,
                WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids,
                *(unsigned __int16 *)(a1 + 3));
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
0x14002fdb8  mov     [rsp+arg_0], rbx
0x14002fdbd  push    rdi
0x14002fdbe  sub     rsp, 20h
0x14002fdc2  mov     rbx, rdx
0x14002fdc5  mov     rdi, rcx
0x14002fdc8  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x14002fdcd  test    eax, eax
0x14002fdcf  jz      short loc_14002FE0C
0x14002fdd1  cmp     rdi, rbx
0x14002fdd4  ja      short loc_14002FDE1
0x14002fdd6  movzx   eax, byte ptr [rdi]
0x14002fdd9  sub     rbx, rdi
0x14002fddc  cmp     rbx, rax
0x14002fddf  jnb     short loc_14002FE25
0x14002fde1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fde8  lea     rbx, WPP_GLOBAL_Control
0x14002fdef  cmp     rcx, rbx
0x14002fdf2  jz      loc_14002FF99
0x14002fdf8  cmp     byte ptr [rcx+29h], 2
0x14002fdfc  jb      loc_14002FF99
0x14002fe02  mov     edx, 2C5h
0x14002fe07  jmp     loc_14002FF89
0x14002fe0c  movzx   eax, byte ptr [rdi]
0x14002fe0f  lea     rcx, [rax+rdi]
0x14002fe13  cmp     rcx, rdi
0x14002fe16  jbe     loc_14002FF6B
0x14002fe1c  cmp     rcx, rbx
0x14002fe1f  ja      loc_14002FF6B
0x14002fe25  cmp     al, 5
0x14002fe27  jz      short loc_14002FE54
0x14002fe29  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe30  lea     rbx, WPP_GLOBAL_Control
0x14002fe37  cmp     rcx, rbx
0x14002fe3a  jz      loc_14002FF99
0x14002fe40  cmp     byte ptr [rcx+29h], 2
0x14002fe44  jb      loc_14002FF99
0x14002fe4a  mov     edx, 2C7h
0x14002fe4f  jmp     loc_14002FF89
0x14002fe54  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe5b  lea     rbx, WPP_GLOBAL_Control
0x14002fe62  cmp     rcx, rbx
0x14002fe65  jz      loc_14002FF67
0x14002fe6b  cmp     byte ptr [rcx+29h], 5
0x14002fe6f  jb      short loc_14002FE86
0x14002fe71  mov     rcx, [rcx+18h]
0x14002fe75  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002fe7c  mov     edx, 2C8h
0x14002fe81  call    WPP_SF_
0x14002fe86  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe8d  cmp     rcx, rbx
0x14002fe90  jz      loc_14002FF67
0x14002fe96  cmp     byte ptr [rcx+29h], 5
0x14002fe9a  jb      short loc_14002FEB4
0x14002fe9c  mov     rcx, [rcx+18h]
0x14002fea0  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002fea7  mov     edx, 2C9h
0x14002feac  mov     r9, rdi
0x14002feaf  call    WPP_SF_q
0x14002feb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002febb  cmp     rcx, rbx
0x14002febe  jz      loc_14002FF67
0x14002fec4  cmp     byte ptr [rcx+29h], 5
0x14002fec8  jb      short loc_14002FEE3
0x14002feca  movzx   r9d, byte ptr [rdi]
0x14002fece  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002fed5  mov     rcx, [rcx+18h]
0x14002fed9  mov     edx, 2CAh
0x14002fede  call    WPP_SF_d
0x14002fee3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002feea  cmp     rcx, rbx
0x14002feed  jz      short loc_14002FF67
0x14002feef  cmp     byte ptr [rcx+29h], 5
0x14002fef3  jb      short loc_14002FF0F
0x14002fef5  movzx   r9d, byte ptr [rdi+1]
0x14002fefa  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002ff01  mov     rcx, [rcx+18h]
0x14002ff05  mov     edx, 2CBh
0x14002ff0a  call    WPP_SF_d
0x14002ff0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff16  cmp     rcx, rbx
0x14002ff19  jz      short loc_14002FF67
0x14002ff1b  cmp     byte ptr [rcx+29h], 5
0x14002ff1f  jb      short loc_14002FF3B
0x14002ff21  movzx   r9d, byte ptr [rdi+2]
0x14002ff26  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002ff2d  mov     rcx, [rcx+18h]
0x14002ff31  mov     edx, 2CCh
0x14002ff36  call    WPP_SF_d
0x14002ff3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff42  cmp     rcx, rbx
0x14002ff45  jz      short loc_14002FF67
0x14002ff47  cmp     byte ptr [rcx+29h], 5
0x14002ff4b  jb      short loc_14002FF67
0x14002ff4d  movzx   r9d, word ptr [rdi+3]
0x14002ff52  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002ff59  mov     rcx, [rcx+18h]
0x14002ff5d  mov     edx, 2CDh
0x14002ff62  call    WPP_SF_d
0x14002ff67  xor     eax, eax
0x14002ff69  jmp     short loc_14002FF9E
0x14002ff6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff72  lea     rbx, WPP_GLOBAL_Control
0x14002ff79  cmp     rcx, rbx
0x14002ff7c  jz      short loc_14002FF99
0x14002ff7e  cmp     byte ptr [rcx+29h], 2
0x14002ff82  jb      short loc_14002FF99
0x14002ff84  mov     edx, 2C6h
0x14002ff89  mov     rcx, [rcx+18h]
0x14002ff8d  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002ff94  call    WPP_SF_
0x14002ff99  mov     eax, 0C0000001h
0x14002ff9e  mov     rbx, [rsp+28h+arg_0]
0x14002ffa3  add     rsp, 20h
0x14002ffa7  pop     rdi
0x14002ffa8  retn
```

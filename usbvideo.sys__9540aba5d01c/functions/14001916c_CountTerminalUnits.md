# CountTerminalUnits

- ea: `0x14001916c`
- end: `0x14001945a`
- name: `CountTerminalUnits`
- size: `750`
- prototype: `__int64 __fastcall(PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140023dfc`

## callees

- `0x140004bac`
- `0x14000d790`
- `0x14001916c`
- `0x14001b118`
- `0x14001b15c`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400191b7`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400193a4`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400191b7`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400193a4`

## pseudocode

```c
__int64 __fastcall CountTerminalUnits(
        PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
        unsigned int *a2,
        _DWORD *a3,
        _DWORD *a4)
{
  _DWORD *v4; // r13
  unsigned int v6; // ebp
  int v7; // r15d
  unsigned int v8; // esi
  int v9; // r12d
  PUSB_INTERFACE_DESCRIPTOR v10; // rdi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int8 *v14; // rax
  unsigned __int8 *v15; // rbx
  unsigned __int8 *v16; // rax
  unsigned int v17; // edx
  PUSB_INTERFACE_DESCRIPTOR v18; // rax

  v4 = a4;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = USBD_ParseConfigurationDescriptorEx(ConfigurationDescriptor, ConfigurationDescriptor, -1, -1, 14, -1, -1);
  if ( v10 )
  {
    while ( 1 )
    {
      if ( v10->bInterfaceSubClass == 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids, v10);
        v14 = (unsigned __int8 *)USBParseDescriptorWrapper(
                                   (_DWORD)ConfigurationDescriptor,
                                   ConfigurationDescriptor->wTotalLength,
                                   (_DWORD)v10,
                                   36,
                                   12);
        v15 = v14;
        if ( !v14 )
          goto LABEL_33;
        v16 = (unsigned __int8 *)USBParseDescriptorWrapper(
                                   (_DWORD)v14,
                                   *(unsigned __int16 *)(v14 + 5),
                                   (unsigned int)v14 + *v14,
                                   36,
                                   4);
        if ( !v16 )
          goto LABEL_33;
        while ( 2 )
        {
          if ( v16[2] == 2 )
          {
            if ( *((_WORD *)v16 + 2) == 257 )
              ++v9;
LABEL_29:
            v17 = v6 + 1;
            ++v8;
            if ( *((_WORD *)v16 + 2) == 257 )
              v17 = v6;
            v6 = v17;
          }
          else if ( v16[2] == 3 )
          {
            goto LABEL_29;
          }
          v16 = (unsigned __int8 *)((unsigned __int64)&v16[*v16]
                                  & -(__int64)(&v16[*v16] < &v15[*(unsigned __int16 *)(v15 + 5)]));
          if ( !v16 )
            goto LABEL_33;
          continue;
        }
      }
      if ( v10->bInterfaceSubClass != 2 )
        break;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids, v10);
      v13 = USBParseDescriptorWrapper(
              (_DWORD)ConfigurationDescriptor,
              ConfigurationDescriptor->wTotalLength,
              (_DWORD)v10,
              36,
              3);
      if ( !v13 )
        goto LABEL_33;
      if ( *(_BYTE *)(v13 + 2) == 1 )
      {
        if ( (unsigned __int8)(*(_BYTE *)(v13 + 9) - 2) <= 1u )
        {
          ++v7;
          ++v8;
        }
        goto LABEL_33;
      }
      if ( *(_BYTE *)(v13 + 2) != 2 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v12 = 21;
LABEL_7:
          WPP_SF_(v11->AttachedDevice, v12, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
        }
      }
LABEL_33:
      v18 = USBD_ParseConfigurationDescriptorEx(
              ConfigurationDescriptor,
              &v10->bLength + v10->bLength,
              -1,
              -1,
              14,
              -1,
              -1);
      v10 = v18;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids, v18);
      if ( !v10 )
      {
        v4 = a4;
        goto LABEL_38;
      }
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      goto LABEL_33;
    v12 = 22;
    goto LABEL_7;
  }
LABEL_38:
  *v4 = v9;
  *a2 = v6;
  *a3 = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids, v6);
  return v8;
}

```

## disassembly

```asm
0x14001916c  mov     rax, rsp
0x14001916f  mov     [rax+8], rbx
0x140019173  mov     [rax+20h], r9
0x140019177  mov     [rax+18h], r8
0x14001917b  mov     [rax+10h], rdx
0x14001917f  push    rbp
0x140019180  push    rsi
0x140019181  push    rdi
0x140019182  push    r12
0x140019184  push    r13
0x140019186  push    r14
0x140019188  push    r15
0x14001918a  sub     rsp, 40h
0x14001918e  or      ebx, 0FFFFFFFFh
0x140019191  mov     r13, r9
0x140019194  mov     [rax-48h], ebx
0x140019197  mov     r9d, ebx; AlternateSetting
0x14001919a  mov     [rax-50h], ebx
0x14001919d  mov     r8d, ebx; InterfaceNumber
0x1400191a0  mov     rdx, rcx; StartPosition
0x1400191a3  mov     dword ptr [rax-58h], 0Eh
0x1400191aa  mov     r14, rcx
0x1400191ad  xor     ebp, ebp
0x1400191af  xor     r15d, r15d
0x1400191b2  xor     esi, esi
0x1400191b4  xor     r12d, r12d
0x1400191b7  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x1400191be  nop     dword ptr [rax+rax+00h]
0x1400191c3  lea     rdx, WPP_GLOBAL_Control
0x1400191ca  mov     rdi, rax
0x1400191cd  test    rax, rax
0x1400191d0  jz      loc_1400193FC
0x1400191d6  mov     r13d, 101h
0x1400191dc  movzx   ecx, byte ptr [rdi+6]
0x1400191e0  sub     ecx, 1
0x1400191e3  jz      loc_1400192C8
0x1400191e9  cmp     ecx, 1
0x1400191ec  jz      short loc_140019222
0x1400191ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400191f5  cmp     rcx, rdx
0x1400191f8  jz      loc_140019385
0x1400191fe  cmp     byte ptr [rcx+29h], 3
0x140019202  jb      loc_140019385
0x140019208  mov     edx, 16h
0x14001920d  mov     rcx, [rcx+18h]
0x140019211  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x140019218  call    WPP_SF_
0x14001921d  jmp     loc_140019385
0x140019222  mov     rcx, cs:WPP_GLOBAL_Control
0x140019229  cmp     rcx, rdx
0x14001922c  jz      short loc_14001924C
0x14001922e  cmp     byte ptr [rcx+29h], 5
0x140019232  jb      short loc_14001924C
0x140019234  mov     rcx, [rcx+18h]
0x140019238  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14001923f  mov     edx, 14h
0x140019244  mov     r9, rdi
0x140019247  call    WPP_SF_q
0x14001924c  movzx   edx, word ptr [r14+2]
0x140019251  mov     r9d, 24h ; '$'
0x140019257  mov     r8, rdi
0x14001925a  mov     qword ptr [rsp+78h+InterfaceClass], 3
0x140019263  mov     rcx, r14
0x140019266  call    USBParseDescriptorWrapper
0x14001926b  test    rax, rax
0x14001926e  jz      loc_140019385
0x140019274  movzx   ecx, byte ptr [rax+2]
0x140019278  sub     ecx, 1
0x14001927b  jz      short loc_1400192B1
0x14001927d  cmp     ecx, 1
0x140019280  jz      loc_140019385
0x140019286  mov     rcx, cs:WPP_GLOBAL_Control
0x14001928d  lea     rax, WPP_GLOBAL_Control
0x140019294  cmp     rcx, rax
0x140019297  jz      loc_140019385
0x14001929d  cmp     byte ptr [rcx+29h], 2
0x1400192a1  jb      loc_140019385
0x1400192a7  mov     edx, 15h
0x1400192ac  jmp     loc_14001920D
0x1400192b1  mov     al, [rax+9]
0x1400192b4  sub     al, 2
0x1400192b6  cmp     al, 1
0x1400192b8  ja      loc_140019385
0x1400192be  inc     r15d
0x1400192c1  inc     esi
0x1400192c3  jmp     loc_140019385
0x1400192c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400192cf  cmp     rcx, rdx
0x1400192d2  jz      short loc_1400192F2
0x1400192d4  cmp     byte ptr [rcx+29h], 5
0x1400192d8  jb      short loc_1400192F2
0x1400192da  mov     rcx, [rcx+18h]
0x1400192de  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x1400192e5  mov     edx, 13h
0x1400192ea  mov     r9, rdi
0x1400192ed  call    WPP_SF_q
0x1400192f2  movzx   edx, word ptr [r14+2]
0x1400192f7  mov     r9d, 24h ; '$'
0x1400192fd  mov     r8, rdi
0x140019300  mov     qword ptr [rsp+78h+InterfaceClass], 0Ch
0x140019309  mov     rcx, r14
0x14001930c  call    USBParseDescriptorWrapper
0x140019311  mov     rbx, rax
0x140019314  test    rax, rax
0x140019317  jz      short loc_140019382
0x140019319  movzx   r8d, byte ptr [rax]
0x14001931d  mov     r9d, 24h ; '$'
0x140019323  movzx   edx, word ptr [rax+5]
0x140019327  add     r8, rax
0x14001932a  mov     rcx, rax
0x14001932d  mov     qword ptr [rsp+78h+InterfaceClass], 4
0x140019336  call    USBParseDescriptorWrapper
0x14001933b  test    rax, rax
0x14001933e  jz      short loc_140019382
0x140019340  movzx   r8d, word ptr [rbx+5]
0x140019345  add     r8, rbx
0x140019348  movzx   edx, byte ptr [rax+2]
0x14001934c  sub     edx, 2
0x14001934f  jz      short loc_140019358
0x140019351  cmp     edx, 1
0x140019354  jnz     short loc_140019371
0x140019356  jmp     short loc_140019362
0x140019358  cmp     [rax+4], r13w
0x14001935d  jnz     short loc_140019362
0x14001935f  inc     r12d
0x140019362  lea     edx, [rbp+1]
0x140019365  inc     esi
0x140019367  cmp     [rax+4], r13w
0x14001936c  cmovz   edx, ebp
0x14001936f  mov     ebp, edx
0x140019371  movzx   edx, byte ptr [rax]
0x140019374  add     rdx, rax
0x140019377  cmp     rdx, r8
0x14001937a  sbb     rax, rax
0x14001937d  and     rax, rdx
0x140019380  jnz     short loc_140019348
0x140019382  or      ebx, 0FFFFFFFFh
0x140019385  movzx   edx, byte ptr [rdi]
0x140019388  mov     r9d, ebx; AlternateSetting
0x14001938b  mov     [rsp+78h+InterfaceProtocol], ebx; InterfaceProtocol
0x14001938f  add     rdx, rdi; StartPosition
0x140019392  mov     [rsp+78h+InterfaceSubClass], ebx; InterfaceSubClass
0x140019396  mov     r8d, ebx; InterfaceNumber
0x140019399  mov     rcx, r14; ConfigurationDescriptor
0x14001939c  mov     [rsp+78h+InterfaceClass], 0Eh; InterfaceClass
0x1400193a4  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x1400193ab  nop     dword ptr [rax+rax+00h]
0x1400193b0  mov     rdi, rax
0x1400193b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400193ba  lea     rdx, WPP_GLOBAL_Control
0x1400193c1  cmp     rcx, rdx
0x1400193c4  jz      short loc_1400193EB
0x1400193c6  cmp     byte ptr [rcx+29h], 5
0x1400193ca  jb      short loc_1400193EB
0x1400193cc  mov     rcx, [rcx+18h]
0x1400193d0  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x1400193d7  mov     edx, 17h
0x1400193dc  mov     r9, rax
0x1400193df  call    WPP_SF_q
0x1400193e4  lea     rdx, WPP_GLOBAL_Control
0x1400193eb  test    rdi, rdi
0x1400193ee  jnz     loc_1400191DC
0x1400193f4  mov     r13, [rsp+78h+arg_18]
0x1400193fc  mov     rax, [rsp+78h+arg_8]
0x140019404  mov     [r13+0], r12d
0x140019408  mov     [rax], ebp
0x14001940a  mov     rax, [rsp+78h+arg_10]
0x140019412  mov     [rax], r15d
0x140019415  mov     rcx, cs:WPP_GLOBAL_Control
0x14001941c  cmp     rcx, rdx
0x14001941f  jz      short loc_14001943F
0x140019421  cmp     byte ptr [rcx+29h], 5
0x140019425  jb      short loc_14001943F
0x140019427  mov     rcx, [rcx+18h]
0x14001942b  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x140019432  mov     edx, 18h
0x140019437  mov     r9d, ebp
0x14001943a  call    WPP_SF_d
0x14001943f  mov     rbx, [rsp+78h+arg_0]
0x140019447  mov     eax, esi
0x140019449  add     rsp, 40h
0x14001944d  pop     r15
0x14001944f  pop     r14
0x140019451  pop     r13
0x140019453  pop     r12
0x140019455  pop     rdi
0x140019456  pop     rsi
0x140019457  pop     rbp
0x140019458  retn
```

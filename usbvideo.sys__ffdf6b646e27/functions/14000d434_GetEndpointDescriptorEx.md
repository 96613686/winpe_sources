# GetEndpointDescriptorEx

- ea: `0x14000d434`
- end: `0x14000d6cd`
- name: `GetEndpointDescriptorEx`
- size: `665`
- prototype: `__int64 __usercall@<rax>(PVOID DescriptorBuffer@<rcx>, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000c95c`
- `0x14000cbf0`
- `0x140016bf0`
- `0x140016cd4`

## callees

- `0x140004bac`
- `0x14000d3e8`
- `0x14000d434`
- `0x140014254`
- `0x140019cd4`
- `0x140021814`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x14000d4b6`
- `USBD!USBD_ParseDescriptors` at `0x14000d4b6`

## pseudocode

```c
PUSB_COMMON_DESCRIPTOR __fastcall GetEndpointDescriptorEx(
        char *DescriptorBuffer,
        UCHAR *a2,
        char a3,
        UCHAR **a4,
        unsigned __int8 **a5,
        UCHAR **a6)
{
  struct _USB_COMMON_DESCRIPTOR *NextVideoAltSetting; // rsi
  UCHAR *i; // r8
  PUSB_COMMON_DESCRIPTOR v12; // rax
  PUSB_COMMON_DESCRIPTOR v13; // rbx
  UCHAR *v14; // rdi
  unsigned __int8 v15; // al
  unsigned __int8 *v16; // rcx

  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  NextVideoAltSetting = (struct _USB_COMMON_DESCRIPTOR *)GetNextVideoAltSetting(DescriptorBuffer, a2);
  if ( !NextVideoAltSetting )
    NextVideoAltSetting = (struct _USB_COMMON_DESCRIPTOR *)&DescriptorBuffer[*((unsigned __int16 *)DescriptorBuffer + 1)];
  for ( i = a2; ; i = &v12->bLength + v12->bLength )
  {
    v12 = USBD_ParseDescriptors(DescriptorBuffer, *((unsigned __int16 *)DescriptorBuffer + 1), i, 5);
    v13 = v12;
    if ( !v12 )
      break;
    if ( v12[1].bLength == a3 )
    {
      if ( v12 > NextVideoAltSetting )
        return 0;
      v14 = &v12->bLength + v12->bLength;
      if ( v14 < (UCHAR *)NextVideoAltSetting )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_qddd(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids,
            v12,
            v14[1],
            *(_WORD *)&v12[2],
            v12[3].bLength);
        v15 = v14[1];
        if ( v15 == 18 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
          if ( a6 )
          {
            *a6 = v14;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_ddddd(
                WPP_GLOBAL_Control->AttachedDevice,
                35,
                WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids,
                *v14,
                *((unsigned __int16 *)v14 + 1),
                *((_DWORD *)v14 + 1),
                *(_WORD *)&v13[2],
                v13[3].bLength);
          }
        }
        else if ( v15 == 48 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
          if ( a4 )
          {
            *a4 = v14;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
          }
          if ( a5 )
          {
            if ( (v14[3] & 0x80u) != 0 )
            {
              _mm_lfence();
              v16 = &v14[*v14];
              if ( v16 < (unsigned __int8 *)NextVideoAltSetting && v16[1] == 49 )
              {
                *a5 = v16;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
              }
            }
          }
        }
      }
      return v13;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x14000d434  push    rbx
0x14000d436  push    rbp
0x14000d437  push    rsi
0x14000d438  push    rdi
0x14000d439  push    r12
0x14000d43b  push    r14
0x14000d43d  push    r15
0x14000d43f  sub     rsp, 40h
0x14000d443  mov     rbp, r9
0x14000d446  mov     r12b, r8b
0x14000d449  mov     rbx, rdx
0x14000d44c  mov     rdi, rcx
0x14000d44f  test    r9, r9
0x14000d452  jz      short loc_14000D45B
0x14000d454  mov     qword ptr [r9], 0
0x14000d45b  mov     r15, [rsp+78h+arg_20]
0x14000d463  test    r15, r15
0x14000d466  jz      short loc_14000D46F
0x14000d468  mov     qword ptr [r15], 0
0x14000d46f  mov     r14, [rsp+78h+arg_28]
0x14000d477  test    r14, r14
0x14000d47a  jz      short loc_14000D483
0x14000d47c  mov     qword ptr [r14], 0
0x14000d483  call    GetNextVideoAltSetting
0x14000d488  mov     rsi, rax
0x14000d48b  test    rax, rax
0x14000d48e  jnz     short loc_14000D497
0x14000d490  movzx   esi, word ptr [rdi+2]
0x14000d494  add     rsi, rdi
0x14000d497  mov     r8, rbx
0x14000d49a  jmp     short loc_14000D4A9
0x14000d49c  cmp     [rbx+2], r12b
0x14000d4a0  jz      short loc_14000D4CF
0x14000d4a2  movzx   r8d, byte ptr [rbx]
0x14000d4a6  add     r8, rbx; StartPosition
0x14000d4a9  movzx   edx, word ptr [rdi+2]; TotalLength
0x14000d4ad  mov     r9d, 5; DescriptorType
0x14000d4b3  mov     rcx, rdi; DescriptorBuffer
0x14000d4b6  call    cs:__imp_USBD_ParseDescriptors
0x14000d4bd  nop     dword ptr [rax+rax+00h]
0x14000d4c2  mov     rbx, rax
0x14000d4c5  test    rax, rax
0x14000d4c8  jnz     short loc_14000D49C
0x14000d4ca  jmp     loc_14000D6BA
0x14000d4cf  cmp     rbx, rsi
0x14000d4d2  jbe     short loc_14000D4DB
0x14000d4d4  xor     ebx, ebx
0x14000d4d6  jmp     loc_14000D6BA
0x14000d4db  movzx   edi, byte ptr [rbx]
0x14000d4de  add     rdi, rbx
0x14000d4e1  cmp     rdi, rsi
0x14000d4e4  jnb     loc_14000D6BA
0x14000d4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d4f1  lea     rdx, WPP_GLOBAL_Control
0x14000d4f8  mov     r12b, 4
0x14000d4fb  cmp     rcx, rdx
0x14000d4fe  jz      short loc_14000D541
0x14000d500  cmp     [rcx+29h], r12b
0x14000d504  jb      short loc_14000D541
0x14000d506  movzx   r8d, word ptr [rbx+4]
0x14000d50b  mov     edx, 1Eh
0x14000d510  movzx   r9d, byte ptr [rdi+1]
0x14000d515  movzx   eax, byte ptr [rbx+6]
0x14000d519  mov     rcx, [rcx+18h]
0x14000d51d  mov     [rsp+78h+var_48], eax
0x14000d521  mov     [rsp+78h+var_50], r8d
0x14000d526  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d52d  mov     [rsp+78h+var_58], r9d
0x14000d532  mov     r9, rbx
0x14000d535  call    WPP_SF_qddd
0x14000d53a  lea     rdx, WPP_GLOBAL_Control
0x14000d541  mov     al, [rdi+1]
0x14000d544  cmp     al, 12h
0x14000d546  jz      loc_14000D636
0x14000d54c  mov     r9d, 30h ; '0'
0x14000d552  cmp     al, r9b
0x14000d555  jnz     loc_14000D6BA
0x14000d55b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d562  cmp     rcx, rdx
0x14000d565  jz      short loc_14000D599
0x14000d567  cmp     [rcx+29h], r12b
0x14000d56b  jb      short loc_14000D599
0x14000d56d  movzx   r8d, byte ptr [rdi]
0x14000d571  lea     edx, [r9-11h]
0x14000d575  movzx   eax, byte ptr [rdi+2]
0x14000d579  mov     rcx, [rcx+18h]
0x14000d57d  mov     [rsp+78h+var_50], eax
0x14000d581  mov     [rsp+78h+var_58], r8d
0x14000d586  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d58d  call    WPP_SF_ddD
0x14000d592  lea     rdx, WPP_GLOBAL_Control
0x14000d599  test    rbp, rbp
0x14000d59c  jz      short loc_14000D5C9
0x14000d59e  mov     [rbp+0], rdi
0x14000d5a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d5a9  cmp     rcx, rdx
0x14000d5ac  jz      short loc_14000D5C9
0x14000d5ae  cmp     [rcx+29h], r12b
0x14000d5b2  jb      short loc_14000D5C9
0x14000d5b4  mov     rcx, [rcx+18h]
0x14000d5b8  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d5bf  mov     edx, 20h ; ' '
0x14000d5c4  call    WPP_SF_
0x14000d5c9  test    r15, r15
0x14000d5cc  jz      loc_14000D6BA
0x14000d5d2  cmp     byte ptr [rdi+3], 0
0x14000d5d6  jge     loc_14000D6BA
0x14000d5dc  lfence
0x14000d5df  movzx   ecx, byte ptr [rdi]
0x14000d5e2  add     rcx, rdi
0x14000d5e5  cmp     rcx, rsi
0x14000d5e8  jnb     loc_14000D6BA
0x14000d5ee  cmp     byte ptr [rcx+1], 31h ; '1'
0x14000d5f2  jnz     loc_14000D6BA
0x14000d5f8  mov     [r15], rcx
0x14000d5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d602  lea     rax, WPP_GLOBAL_Control
0x14000d609  cmp     rcx, rax
0x14000d60c  jz      loc_14000D6BA
0x14000d612  cmp     [rcx+29h], r12b
0x14000d616  jb      loc_14000D6BA
0x14000d61c  mov     rcx, [rcx+18h]
0x14000d620  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d627  mov     edx, 21h ; '!'
0x14000d62c  call    WPP_SF_
0x14000d631  jmp     loc_14000D6BA
0x14000d636  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d63d  cmp     rcx, rdx
0x14000d640  jz      short loc_14000D664
0x14000d642  cmp     [rcx+29h], r12b
0x14000d646  jb      short loc_14000D664
0x14000d648  mov     rcx, [rcx+18h]
0x14000d64c  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d653  mov     edx, 22h ; '"'
0x14000d658  call    WPP_SF_
0x14000d65d  lea     rdx, WPP_GLOBAL_Control
0x14000d664  test    r14, r14
0x14000d667  jz      short loc_14000D6BA
0x14000d669  mov     [r14], rdi
0x14000d66c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d673  cmp     rcx, rdx
0x14000d676  jz      short loc_14000D6BA
0x14000d678  cmp     [rcx+29h], r12b
0x14000d67c  jb      short loc_14000D6BA
0x14000d67e  movzx   eax, byte ptr [rbx+6]
0x14000d682  mov     edx, 23h ; '#'
0x14000d687  movzx   r8d, word ptr [rbx+4]
0x14000d68c  movzx   r10d, word ptr [rdi+2]
0x14000d691  movzx   r9d, byte ptr [rdi]
0x14000d695  mov     rcx, [rcx+18h]
0x14000d699  mov     [rsp+78h+var_40], eax
0x14000d69d  mov     eax, [rdi+4]
0x14000d6a0  mov     [rsp+78h+var_48], r8d
0x14000d6a5  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d6ac  mov     [rsp+78h+var_50], eax
0x14000d6b0  mov     [rsp+78h+var_58], r10d
0x14000d6b5  call    WPP_SF_ddddd
0x14000d6ba  mov     rax, rbx
0x14000d6bd  add     rsp, 40h
0x14000d6c1  pop     r15
0x14000d6c3  pop     r14
0x14000d6c5  pop     r12
0x14000d6c7  pop     rdi
0x14000d6c8  pop     rsi
0x14000d6c9  pop     rbp
0x14000d6ca  pop     rbx
0x14000d6cb  retn
```

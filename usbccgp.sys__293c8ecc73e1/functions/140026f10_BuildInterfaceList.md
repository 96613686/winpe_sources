# BuildInterfaceList

- ea: `0x140026f10`
- end: `0x140027142`
- name: `BuildInterfaceList`
- size: `562`
- prototype: `__int64 __fastcall(PVOID DescriptorBuffer)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400275b0`

## callees

- `0x14000c2bc`
- `0x140026f10`
- `0x1400279e8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140026f8d`
- `ntoskrnl!ExAllocatePool2` at `0x140026f8d`
- `USBD!USBD_ParseDescriptors` at `0x140026f43`
- `USBD!USBD_ParseDescriptors` at `0x140026ff5`
- `USBD!USBD_ParseDescriptors` at `0x140026f43`
- `USBD!USBD_ParseDescriptors` at `0x140026ff5`

## pseudocode

```c
__int64 __fastcall BuildInterfaceList(unsigned __int16 *DescriptorBuffer, __int64 a2)
{
  ULONG v2; // r13d
  int v5; // ebx
  PUSB_COMMON_DESCRIPTOR v6; // rsi
  __int64 *v7; // rdx
  __int64 Pool2; // rax
  __int64 v9; // rdi
  _QWORD *v10; // rax
  __int64 *v11; // rax
  char bLength; // r12
  unsigned __int8 v13; // r14
  PUSB_COMMON_DESCRIPTOR v14; // rax
  char v15; // al
  int v16; // edx
  int bDescriptorType; // ecx
  __int16 v18; // cx
  __int16 v19; // ax
  int v20; // r9d
  char v22; // [rsp+28h] [rbp-60h]
  char v23; // [rsp+30h] [rbp-58h]

  v2 = DescriptorBuffer[1];
  v5 = 0;
  DestroyInterfaceList(a2);
  v6 = USBD_ParseDescriptors(DescriptorBuffer, v2, DescriptorBuffer, 4);
  if ( v6 )
  {
    while ( 1 )
    {
      v7 = WPP_250a8722b9c73d5bc894b816de363468_Traceguids;
      if ( v5 < 0 )
      {
LABEL_30:
        DestroyInterfaceList(a2);
        return (unsigned int)v5;
      }
      if ( v6[1].bDescriptorType )
        break;
      Pool2 = ExAllocatePool2(256, 48, 1130525525);
      v9 = Pool2;
      if ( Pool2 )
      {
        v10 = (_QWORD *)(Pool2 + 16);
        *(_QWORD *)(v9 + 24) = v10;
        *v10 = v10;
        *(_WORD *)(v9 + 40) = 0;
        *(_DWORD *)(v9 + 44) = 0;
        *(_QWORD *)(v9 + 32) = v6;
        v11 = *(__int64 **)(a2 + 8);
        if ( *v11 != a2 )
          __fastfail(3u);
        bLength = v6[1].bLength;
        v13 = 0;
        *(_QWORD *)v9 = a2;
        v5 = 0;
        *(_QWORD *)(v9 + 8) = v11;
        *v11 = v9;
        *(_QWORD *)(a2 + 8) = v9;
        while ( 1 )
        {
          v14 = USBD_ParseDescriptors(DescriptorBuffer, v2, &v6->bLength + v6->bLength, 4);
          v6 = v14;
          if ( !v14 )
            goto LABEL_17;
          v15 = v14->bLength;
          if ( (unsigned __int8)v15 < 9u )
            break;
          v16 = v6[1].bLength;
          if ( (_BYTE)v16 == bLength )
          {
            bDescriptorType = v6[1].bDescriptorType;
            if ( bDescriptorType == v13 + 1 )
            {
              ++v13;
            }
            else
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v16) = 2;
                WPP_RECORDER_SF_dd(
                  g_RecorderLog,
                  v16,
                  8,
                  11,
                  (__int64)WPP_250a8722b9c73d5bc894b816de363468_Traceguids,
                  v6[1].bLength,
                  bDescriptorType);
              }
              v5 = -1073741811;
            }
            if ( v5 >= 0 )
              continue;
          }
          if ( v5 < 0 )
            goto LABEL_28;
LABEL_17:
          v18 = *(_WORD *)(v9 + 32);
          if ( v6 )
            v19 = (_WORD)v6 - v18;
          else
            v19 = v2 + (_WORD)DescriptorBuffer - v18;
          *(_WORD *)(v9 + 40) = v19;
          goto LABEL_28;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_27;
        v23 = v15;
        v20 = 12;
        v22 = bLength;
LABEL_26:
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_dd(
          g_RecorderLog,
          (_DWORD)v7,
          8,
          v20,
          (__int64)WPP_250a8722b9c73d5bc894b816de363468_Traceguids,
          v22,
          v23);
        goto LABEL_27;
      }
      v5 = -1073741670;
LABEL_28:
      if ( !v6 )
      {
        if ( v5 >= 0 )
          return (unsigned int)v5;
        goto LABEL_30;
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = 13;
      v23 = v6[1].bDescriptorType;
      v22 = v6[1].bLength;
      goto LABEL_26;
    }
LABEL_27:
    v5 = -1073741811;
    goto LABEL_28;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140026f10  push    rbx
0x140026f12  push    rbp
0x140026f13  push    rsi
0x140026f14  push    rdi
0x140026f15  push    r12
0x140026f17  push    r13
0x140026f19  push    r14
0x140026f1b  push    r15
0x140026f1d  sub     rsp, 48h
0x140026f21  movzx   r13d, word ptr [rcx+2]
0x140026f26  mov     r15, rcx
0x140026f29  mov     rcx, rdx
0x140026f2c  mov     rbp, rdx
0x140026f2f  xor     ebx, ebx
0x140026f31  call    DestroyInterfaceList
0x140026f36  mov     edx, r13d; TotalLength
0x140026f39  lea     r9d, [rbx+4]; DescriptorType
0x140026f3d  mov     r8, r15; StartPosition
0x140026f40  mov     rcx, r15; DescriptorBuffer
0x140026f43  call    cs:__imp_USBD_ParseDescriptors
0x140026f4a  nop     dword ptr [rax+rax+00h]
0x140026f4f  mov     rsi, rax
0x140026f52  test    rax, rax
0x140026f55  jz      loc_140027127
0x140026f5b  lea     rdx, WPP_250a8722b9c73d5bc894b816de363468_Traceguids
0x140026f62  lea     rcx, WPP_RECORDER_INITIALIZED
0x140026f69  test    ebx, ebx
0x140026f6b  js      loc_14002711F
0x140026f71  movzx   eax, byte ptr [rsi+3]
0x140026f75  test    al, al
0x140026f77  jnz     loc_1400270D7
0x140026f7d  mov     edx, 30h ; '0'
0x140026f82  mov     ecx, 100h
0x140026f87  mov     r8d, 43627355h
0x140026f8d  call    cs:__imp_ExAllocatePool2
0x140026f94  nop     dword ptr [rax+rax+00h]
0x140026f99  mov     rdi, rax
0x140026f9c  test    rax, rax
0x140026f9f  jz      loc_1400270D0
0x140026fa5  add     rax, 10h
0x140026fa9  mov     [rdi+18h], rax
0x140026fad  mov     [rax], rax
0x140026fb0  xor     eax, eax
0x140026fb2  mov     [rdi+28h], ax
0x140026fb6  mov     [rdi+2Ch], eax
0x140026fb9  mov     [rdi+20h], rsi
0x140026fbd  mov     rax, [rbp+8]
0x140026fc1  cmp     [rax], rbp
0x140026fc4  jnz     loc_14002713B
0x140026fca  movzx   r12d, byte ptr [rsi+2]
0x140026fcf  xor     r14b, r14b
0x140026fd2  mov     [rdi], rbp
0x140026fd5  xor     ebx, ebx
0x140026fd7  mov     [rdi+8], rax
0x140026fdb  mov     [rax], rdi
0x140026fde  mov     [rbp+8], rdi
0x140026fe2  movzx   r8d, byte ptr [rsi]
0x140026fe6  mov     r9d, 4; DescriptorType
0x140026fec  add     r8, rsi; StartPosition
0x140026fef  mov     edx, r13d; TotalLength
0x140026ff2  mov     rcx, r15; DescriptorBuffer
0x140026ff5  call    cs:__imp_USBD_ParseDescriptors
0x140026ffc  nop     dword ptr [rax+rax+00h]
0x140027001  mov     rsi, rax
0x140027004  test    rax, rax
0x140027007  jz      short loc_140027081
0x140027009  movzx   eax, byte ptr [rax]
0x14002700c  cmp     al, 9
0x14002700e  jb      loc_140027096
0x140027014  movzx   edx, byte ptr [rsi+2]
0x140027018  cmp     dl, r12b
0x14002701b  jnz     short loc_140027079
0x14002701d  movzx   ecx, byte ptr [rsi+3]
0x140027021  movzx   eax, r14b
0x140027025  inc     eax
0x140027027  cmp     ecx, eax
0x140027029  jnz     short loc_140027030
0x14002702b  inc     r14b
0x14002702e  jmp     short loc_140027071
0x140027030  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027037  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002703e  jz      short loc_14002706C
0x140027040  mov     dword ptr [rsp+88h+var_58], ecx
0x140027044  lea     rax, WPP_250a8722b9c73d5bc894b816de363468_Traceguids
0x14002704b  mov     rcx, cs:g_RecorderLog
0x140027052  mov     r9d, 0Bh
0x140027058  mov     dword ptr [rsp+88h+var_60], edx
0x14002705c  mov     dl, 2
0x14002705e  mov     [rsp+88h+var_68], rax
0x140027063  lea     r8d, [r9-3]
0x140027067  call    WPP_RECORDER_SF_dd
0x14002706c  mov     ebx, 0C000000Dh
0x140027071  test    ebx, ebx
0x140027073  jns     loc_140026FE2
0x140027079  test    ebx, ebx
0x14002707b  js      loc_140027112
0x140027081  movzx   ecx, word ptr [rdi+20h]
0x140027085  test    rsi, rsi
0x140027088  jz      short loc_1400270C3
0x14002708a  movzx   eax, si
0x14002708d  sub     ax, cx
0x140027090  mov     [rdi+28h], ax
0x140027094  jmp     short loc_140027112
0x140027096  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002709d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400270a4  jz      short loc_14002710D
0x1400270a6  mov     dword ptr [rsp+88h+var_58], eax
0x1400270aa  mov     r9d, 0Ch
0x1400270b0  lea     rax, WPP_250a8722b9c73d5bc894b816de363468_Traceguids
0x1400270b7  mov     dword ptr [rsp+88h+var_60], r12d
0x1400270bc  mov     [rsp+88h+var_68], rax
0x1400270c1  jmp     short loc_1400270F9
0x1400270c3  movzx   eax, r15w
0x1400270c7  sub     ax, cx
0x1400270ca  add     ax, r13w
0x1400270ce  jmp     short loc_140027090
0x1400270d0  mov     ebx, 0C000009Ah
0x1400270d5  jmp     short loc_140027112
0x1400270d7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x1400270de  jz      short loc_14002710D
0x1400270e0  mov     ecx, eax
0x1400270e2  mov     r9d, 0Dh
0x1400270e8  movzx   eax, byte ptr [rsi+2]
0x1400270ec  mov     dword ptr [rsp+88h+var_58], ecx
0x1400270f0  mov     dword ptr [rsp+88h+var_60], eax
0x1400270f4  mov     [rsp+88h+var_68], rdx
0x1400270f9  mov     rcx, cs:g_RecorderLog
0x140027100  mov     r8d, 8
0x140027106  mov     dl, 2
0x140027108  call    WPP_RECORDER_SF_dd
0x14002710d  mov     ebx, 0C000000Dh
0x140027112  test    rsi, rsi
0x140027115  jnz     loc_140026F5B
0x14002711b  test    ebx, ebx
0x14002711d  jns     short loc_140027127
0x14002711f  mov     rcx, rbp
0x140027122  call    DestroyInterfaceList
0x140027127  mov     eax, ebx
0x140027129  add     rsp, 48h
0x14002712d  pop     r15
0x14002712f  pop     r14
0x140027131  pop     r13
0x140027133  pop     r12
0x140027135  pop     rdi
0x140027136  pop     rsi
0x140027137  pop     rbp
0x140027138  pop     rbx
0x140027139  retn
0x14002713b  mov     ecx, 3
0x140027140  int     29h; Win8: RtlFailFast(ecx)
```

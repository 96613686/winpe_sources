# SlbNatCreateExternalAddressWithLock

- ea: `0x140014dcc`
- end: `0x1400151e5`
- name: `SlbNatCreateExternalAddressWithLock`
- size: `1049`
- prototype: `__int64 __fastcall(__int64, __int16 *, __int64, char, int)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000975c`
- `0x14003118c`
- `0x140032118`

## callees

- `0x1400085d0`
- `0x14000caa0`
- `0x14000d648`
- `0x14000d7c8`
- `0x140014830`
- `0x140014dcc`
- `0x140019320`
- `0x14001f320`
- `0x14001f680`
- `0x14002e008`
- `0x14002e040`
- `0x14002e108`
- `0x140034078`
- `0x140034318`
- `0x140035808`
- `0x140035948`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140014f46`
- `ntoskrnl!ExAllocatePool2` at `0x140014f46`

## string_xrefs

- `0x140015194`: `Create external address`

## pseudocode

```c
__int64 __fastcall SlbNatCreateExternalAddressWithLock(__int64 a1, __int16 *a2, __int64 a3, char a4, int a5)
{
  __int64 v5; // rbp
  __int64 Instance; // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  int Address; // ebx
  char v14; // r15
  char v15; // r12
  int v16; // eax
  __int64 v17; // rcx
  __int16 v18; // bx
  size_t v19; // r8
  char v20; // al
  __int64 v21; // r8
  __int64 Pool2; // rax
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // xmm1_8
  __int64 *v26; // rax
  PVOID *v27; // rcx
  _QWORD *v28; // rbx
  _DWORD *v29; // r9
  int v30; // ecx
  int v31; // ecx
  int v32; // eax
  _QWORD v34[4]; // [rsp+50h] [rbp-68h] BYREF

  v5 = 0;
  v34[0] = 0;
  if ( a3 )
  {
    Instance = a3;
    if ( a4 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  }
  else
  {
    Instance = SlbNatFindInstance((wchar_t *)a1);
    if ( !Instance )
    {
      Address = -1073741275;
      goto LABEL_56;
    }
  }
  if ( SlbNatFindExternalAddress(Instance, *(unsigned int *)(a1 + 80)) )
  {
    Address = -1073741635;
LABEL_56:
    if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
      McTemplateK0qzqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        v11,
        v12,
        3005,
        (__int64)L"Create external address",
        0,
        Address);
    return (unsigned int)Address;
  }
  if ( *a2 != 2 && *a2 != 23 || (unsigned __int16)a2[10] > (unsigned __int16)a2[11] )
  {
    Address = -1073741811;
    goto LABEL_56;
  }
  v14 = 0;
  v15 = 4;
  if ( a3 )
  {
LABEL_23:
    Pool2 = ExAllocatePool2(256, 96, 1634029139);
    v24 = Pool2;
    if ( !Pool2 )
    {
      Address = -1073741670;
      if ( v14 )
      {
        if ( *a2 != 2 )
          v15 = 16;
        LOBYTE(v12) = v15;
        WinNatLibDeleteAddress((_DWORD)qword_1400273D8, (_DWORD)a2 + 4, v12, (unsigned __int16)a2[10], a2[11]);
      }
      goto LABEL_53;
    }
    *(_DWORD *)(Pool2 + 48) = *(_DWORD *)(a1 + 80);
    *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
    *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
    if ( *(_DWORD *)(Pool2 + 32) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v23, v11, v12);
    *(_OWORD *)(v24 + 52) = *(_OWORD *)a2;
    v25 = *((_QWORD *)a2 + 2);
    *(_QWORD *)(v24 + 40) = v5;
    v5 = 0;
    *(_QWORD *)(v24 + 68) = v25;
    *(_DWORD *)(v24 + 88) = a5;
    if ( (xmmword_1400272E0 & 2) != 0 )
      WPP_SF_d(1025, 10, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, *(unsigned int *)(v24 + 56));
    if ( *(_DWORD *)(v24 + 56) )
    {
      v27 = *(PVOID **)(Instance + 32);
      if ( *v27 == (PVOID)(Instance + 24) )
      {
        *(_QWORD *)v24 = Instance + 24;
        *(_QWORD *)(v24 + 8) = v27;
        *v27 = (PVOID)v24;
        *(_QWORD *)(Instance + 32) = v24;
        ++*(_DWORD *)(Instance + 40);
        goto LABEL_38;
      }
    }
    else
    {
      v26 = (__int64 *)qword_140027360;
      v27 = &qword_140027358;
      if ( *(PVOID **)qword_140027360 == &qword_140027358 )
      {
        *(_QWORD *)v24 = &qword_140027358;
        *(_QWORD *)(v24 + 8) = v26;
        *v26 = v24;
        ++dword_140027368;
        qword_140027360 = v24;
LABEL_38:
        if ( (xmmword_1400272E0 & 2) != 0 )
          WPP_SF_(1025, 11, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids);
        v28 = *(_QWORD **)(Instance + 24);
        while ( v28 != (_QWORD *)(Instance + 24) )
        {
          v29 = v28;
          v28 = (_QWORD *)*v28;
          if ( (xmmword_1400272E0 & 2) != 0 )
            WPP_SF_ddD(v27, 12, v12, (unsigned int)v29[22], v29[12], v29[14]);
        }
        Address = 0;
        if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
        {
          v30 = *(unsigned __int16 *)(v24 + 52);
          memset(v34, 0, 28);
          INETADDR_SETSOCKADDR(v30, (unsigned int)v34, v24 + 56, 0, 0);
          if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
          {
            v31 = 28;
            if ( LOWORD(v34[0]) == 2 )
              v31 = 16;
            McTemplateK0zqbr1hh_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              (unsigned int)WINNATM_EXTERNAL_ADDRESS_ADDITION,
              v12,
              Instance + 80,
              v31,
              (__int64)v34,
              *(_WORD *)(v24 + 72),
              *(_WORD *)(v24 + 74));
          }
        }
        v32 = *(_DWORD *)(a1 + 80);
        if ( *(_DWORD *)(Instance + 256) >= (unsigned int)(v32 + 1) && v32 != -1 )
          return (unsigned int)Address;
        *(_DWORD *)(Instance + 256) = v32 + 1;
        goto LABEL_53;
      }
    }
    __fastfail(3u);
  }
  if ( a4 )
  {
    v16 = SlbNatWfpBlockExternalAddressPortRange(a2, v34);
    v5 = v34[0];
    Address = v16;
    if ( v16 < 0 )
      goto LABEL_53;
    if ( !v34[0] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v11, v12);
  }
  v18 = *a2;
  v19 = 4;
  if ( *a2 != 2 )
    v19 = 16;
  memmove(v34, a2 + 2, v19);
  v20 = 4;
  LOBYTE(v21) = 1;
  if ( v18 != 2 )
    v20 = 16;
  Address = WinNatLibCreateAddress(
              qword_1400273D8,
              *(_QWORD *)(Instance + 16),
              v21,
              (unsigned __int16)a2[10],
              a2[11],
              v34,
              v20,
              0,
              0,
              0);
  if ( Address >= 0 )
  {
    v14 = 1;
    goto LABEL_23;
  }
LABEL_53:
  if ( v5 )
    SlbNatWfpUnblockExternalAddressPortRange(v5);
  if ( Address < 0 )
    goto LABEL_56;
  return (unsigned int)Address;
}

```

## disassembly

```asm
0x140014dcc  mov     [rsp+arg_18], rbx
0x140014dd1  push    rbp
0x140014dd2  push    rsi
0x140014dd3  push    rdi
0x140014dd4  push    r12
0x140014dd6  push    r13
0x140014dd8  push    r14
0x140014dda  push    r15
0x140014ddc  sub     rsp, 80h
0x140014de3  mov     rax, cs:__security_cookie
0x140014dea  xor     rax, rsp
0x140014ded  mov     [rsp+0B8h+var_48], rax
0x140014df2  xor     ebp, ebp
0x140014df4  mov     dil, r9b
0x140014df7  mov     [rsp+0B8h+var_68], rbp
0x140014dfc  mov     rbx, r8
0x140014dff  mov     r14, rdx
0x140014e02  mov     r13, rcx
0x140014e05  lea     r15d, [rbp+10h]
0x140014e09  test    r8, r8
0x140014e0c  jz      short loc_140014E36
0x140014e0e  mov     rsi, rbx
0x140014e11  test    r9b, r9b
0x140014e14  jz      short loc_140014E1B
0x140014e16  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140014e1b  mov     edx, [r13+50h]
0x140014e1f  mov     rcx, rsi
0x140014e22  call    SlbNatFindExternalAddress
0x140014e27  test    rax, rax
0x140014e2a  jz      short loc_140014E4D
0x140014e2c  mov     ebx, 0C00000BDh
0x140014e31  jmp     loc_14001517E
0x140014e36  call    SlbNatFindInstance
0x140014e3b  mov     rsi, rax
0x140014e3e  test    rax, rax
0x140014e41  jnz     short loc_140014E1B
0x140014e43  mov     ebx, 0C0000225h
0x140014e48  jmp     loc_14001517E
0x140014e4d  movzx   eax, word ptr [r14]
0x140014e51  cmp     ax, 2
0x140014e55  jz      short loc_140014E67
0x140014e57  cmp     ax, 17h
0x140014e5b  jz      short loc_140014E67
0x140014e5d  mov     ebx, 0C000000Dh
0x140014e62  jmp     loc_14001517E
0x140014e67  movzx   eax, word ptr [r14+16h]
0x140014e6c  cmp     [r14+14h], ax
0x140014e71  ja      short loc_140014E5D
0x140014e73  xor     r15b, r15b
0x140014e76  mov     r12d, 4
0x140014e7c  test    rbx, rbx
0x140014e7f  jnz     loc_140014F36
0x140014e85  test    dil, dil
0x140014e88  jz      short loc_140014EB0
0x140014e8a  lea     rdx, [rsp+0B8h+var_68]
0x140014e8f  mov     rcx, r14
0x140014e92  call    SlbNatWfpBlockExternalAddressPortRange
0x140014e97  mov     rbp, [rsp+0B8h+var_68]
0x140014e9c  mov     ebx, eax
0x140014e9e  test    eax, eax
0x140014ea0  js      loc_140015167
0x140014ea6  test    rbp, rbp
0x140014ea9  jnz     short loc_140014EB0
0x140014eab  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140014eb0  movzx   ebx, word ptr [r14]
0x140014eb4  lea     rdx, [r14+4]; Src
0x140014eb8  cmp     bx, 2
0x140014ebc  lea     rcx, [rsp+0B8h+var_68]; void *
0x140014ec1  mov     r8, r12
0x140014ec4  mov     r15d, 10h
0x140014eca  cmovnz  r8, r15; Size
0x140014ece  call    memmove
0x140014ed3  movzx   r9d, word ptr [r14+14h]
0x140014ed8  mov     eax, r12d
0x140014edb  mov     rdx, [rsi+10h]
0x140014edf  cmp     bx, 2
0x140014ee3  mov     rcx, cs:qword_1400273D8
0x140014eea  mov     r8b, 1
0x140014eed  mov     [rsp+0B8h+var_70], 0
0x140014ef6  cmovnz  eax, r15d
0x140014efa  mov     [rsp+0B8h+var_78], 0
0x140014f03  mov     [rsp+0B8h+var_80], 0
0x140014f0c  mov     byte ptr [rsp+0B8h+var_88], al
0x140014f10  lea     rax, [rsp+0B8h+var_68]
0x140014f15  mov     [rsp+0B8h+var_90], rax
0x140014f1a  movzx   eax, word ptr [r14+16h]
0x140014f1f  mov     word ptr [rsp+0B8h+var_98], ax
0x140014f24  call    WinNatLibCreateAddress
0x140014f29  mov     ebx, eax
0x140014f2b  test    eax, eax
0x140014f2d  js      loc_14001516D
0x140014f33  mov     r15b, 1
0x140014f36  mov     edx, 60h ; '`'
0x140014f3b  mov     ecx, 100h
0x140014f40  mov     r8d, 61654E53h
0x140014f46  call    cs:__imp_ExAllocatePool2
0x140014f4d  nop     dword ptr [rax+rax+00h]
0x140014f52  mov     rdi, rax
0x140014f55  test    rax, rax
0x140014f58  jnz     short loc_140014F9C
0x140014f5a  mov     ebx, 0C000009Ah
0x140014f5f  test    r15b, r15b
0x140014f62  jz      loc_140015167
0x140014f68  cmp     word ptr [r14], 2
0x140014f6d  lea     r15d, [rax+10h]
0x140014f71  movzx   eax, word ptr [r14+16h]
0x140014f76  lea     rdx, [r14+4]
0x140014f7a  movzx   r9d, word ptr [r14+14h]
0x140014f7f  cmovnz  r12d, r15d
0x140014f83  mov     rcx, cs:qword_1400273D8
0x140014f8a  mov     r8b, r12b
0x140014f8d  mov     word ptr [rsp+0B8h+var_98], ax
0x140014f92  call    WinNatLibDeleteAddress
0x140014f97  jmp     loc_14001516D
0x140014f9c  mov     eax, [r13+50h]
0x140014fa0  mov     [rdi+30h], eax
0x140014fa3  lea     rax, [rdi+10h]
0x140014fa7  mov     [rax+8], rax
0x140014fab  mov     [rax], rax
0x140014fae  cmp     dword ptr [rdi+20h], 0
0x140014fb2  jz      short loc_140014FB9
0x140014fb4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140014fb9  movups  xmm0, xmmword ptr [r14]
0x140014fbd  mov     eax, [rsp+0B8h+arg_20]
0x140014fc4  movups  xmmword ptr [rdi+34h], xmm0
0x140014fc8  movsd   xmm1, qword ptr [r14+10h]
0x140014fce  mov     [rdi+28h], rbp
0x140014fd2  xor     ebp, ebp
0x140014fd4  movsd   qword ptr [rdi+44h], xmm1
0x140014fd9  mov     [rdi+58h], eax
0x140014fdc  mov     r12w, 2
0x140014fe1  mov     ebx, 401h
0x140014fe6  test    byte ptr cs:xmmword_1400272E0, r12b
0x140014fed  jz      short loc_140015004
0x140014fef  mov     r9d, [rdi+38h]
0x140014ff3  lea     edx, [rbp+0Ah]
0x140014ff6  mov     ecx, ebx
0x140014ff8  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140014fff  call    WPP_SF_d
0x140015004  cmp     [rdi+38h], ebp
0x140015007  jnz     short loc_140015035
0x140015009  mov     rax, cs:qword_140027360
0x140015010  lea     rcx, qword_140027358
0x140015017  cmp     [rax], rcx
0x14001501a  jnz     short loc_140015042
0x14001501c  mov     [rdi], rcx
0x14001501f  mov     [rdi+8], rax
0x140015023  mov     [rax], rdi
0x140015026  inc     cs:dword_140027368
0x14001502c  mov     cs:qword_140027360, rdi
0x140015033  jmp     short loc_14001505A
0x140015035  lea     rax, [rsi+18h]
0x140015039  mov     rcx, [rax+8]
0x14001503d  cmp     [rcx], rax
0x140015040  jz      short loc_140015049
0x140015042  mov     ecx, 3
0x140015047  int     29h; Win8: RtlFailFast(ecx)
0x140015049  mov     [rdi], rax
0x14001504c  mov     [rdi+8], rcx
0x140015050  mov     [rcx], rdi
0x140015053  mov     [rax+8], rdi
0x140015057  inc     dword ptr [rsi+28h]
0x14001505a  test    byte ptr cs:xmmword_1400272E0, r12b
0x140015061  jz      short loc_140015076
0x140015063  mov     edx, 0Bh
0x140015068  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x14001506f  mov     ecx, ebx
0x140015071  call    WPP_SF_
0x140015076  lea     r14, [rsi+18h]
0x14001507a  mov     rbx, [r14]
0x14001507d  jmp     short loc_1400150AC
0x14001507f  lea     r9, [rbx]
0x140015082  mov     rbx, [rbx]
0x140015085  test    byte ptr cs:xmmword_1400272E0, r12b
0x14001508c  jz      short loc_1400150AC
0x14001508e  mov     eax, [r9+38h]
0x140015092  mov     edx, 0Ch
0x140015097  mov     dword ptr [rsp+0B8h+var_90], eax
0x14001509b  mov     eax, [r9+30h]
0x14001509f  mov     r9d, [r9+58h]
0x1400150a3  mov     dword ptr [rsp+0B8h+var_98], eax
0x1400150a7  call    WPP_SF_ddD
0x1400150ac  cmp     rbx, r14
0x1400150af  jnz     short loc_14001507F
0x1400150b1  xor     ebx, ebx
0x1400150b3  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x1400150ba  jz      loc_140015145
0x1400150c0  movzx   ecx, word ptr [rdi+34h]
0x1400150c4  lea     r8, [rdi+38h]
0x1400150c8  xorps   xmm0, xmm0
0x1400150cb  lea     rdx, [rsp+0B8h+var_68]
0x1400150d0  xor     eax, eax
0x1400150d2  xor     r9d, r9d
0x1400150d5  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x1400150da  mov     word ptr [rsp+0B8h+var_98], ax
0x1400150df  movups  xmmword ptr [rsp+0B8h+var_68+0Ch], xmm0
0x1400150e4  call    INETADDR_SETSOCKADDR
0x1400150e9  cmp     cs:dword_140027104, 1
0x1400150f0  lea     r15d, [rbx+10h]
0x1400150f4  jnz     short loc_14001514B
0x1400150f6  test    cs:Microsoft_Windows_WinNatEnableBits, r15b
0x1400150fd  jz      short loc_14001514B
0x1400150ff  movzx   eax, word ptr [rdi+4Ah]
0x140015103  lea     ecx, [rbx+1Ch]
0x140015106  cmp     word ptr [rsp+0B8h+var_68], r12w
0x14001510c  lea     r9, [rsi+50h]
0x140015110  mov     word ptr [rsp+0B8h+var_80], ax
0x140015115  lea     rdx, WINNATM_EXTERNAL_ADDRESS_ADDITION
0x14001511c  movzx   eax, word ptr [rdi+48h]
0x140015120  cmovz   ecx, r15d
0x140015124  mov     word ptr [rsp+0B8h+var_88], ax
0x140015129  lea     rax, [rsp+0B8h+var_68]
0x14001512e  mov     [rsp+0B8h+var_90], rax
0x140015133  mov     dword ptr [rsp+0B8h+var_98], ecx
0x140015137  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001513e  call    McTemplateK0zqbr1hh_EtwWriteTransfer
0x140015143  jmp     short loc_14001514B
0x140015145  mov     r15d, 10h
0x14001514b  mov     eax, [r13+50h]
0x14001514f  lea     ecx, [rax+1]
0x140015152  cmp     [rsi+100h], ecx
0x140015158  jb      short loc_14001515F
0x14001515a  cmp     eax, 0FFFFFFFFh
0x14001515d  jnz     short loc_1400151BA
0x14001515f  mov     [rsi+100h], ecx
0x140015165  jmp     short loc_14001516D
0x140015167  mov     r15d, 10h
0x14001516d  test    rbp, rbp
0x140015170  jz      short loc_14001517A
0x140015172  mov     rcx, rbp
0x140015175  call    SlbNatWfpUnblockExternalAddressPortRange
0x14001517a  test    ebx, ebx
0x14001517c  jns     short loc_1400151BA
0x14001517e  cmp     cs:dword_140027104, 1
0x140015185  jnz     short loc_1400151BA
0x140015187  test    cs:byte_140027BED, r15b
0x14001518e  jz      short loc_1400151BA
0x140015190  mov     [rsp+0B8h+var_88], ebx
0x140015194  lea     rax, aCreateExternal; "Create external address"
0x14001519b  mov     dword ptr [rsp+0B8h+var_90], 0
0x1400151a3  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400151aa  mov     r9d, 0BBDh
0x1400151b0  mov     [rsp+0B8h+var_98], rax
0x1400151b5  call    McTemplateK0qzqq_EtwWriteTransfer
0x1400151ba  mov     eax, ebx
0x1400151bc  mov     rcx, [rsp+0B8h+var_48]
0x1400151c1  xor     rcx, rsp; StackCookie
0x1400151c4  call    __security_check_cookie
0x1400151c9  mov     rbx, [rsp+0B8h+arg_18]
0x1400151d1  add     rsp, 80h
0x1400151d8  pop     r15
0x1400151da  pop     r14
0x1400151dc  pop     r13
0x1400151de  pop     r12
0x1400151e0  pop     rdi
0x1400151e1  pop     rsi
0x1400151e2  pop     rbp
0x1400151e3  retn
```

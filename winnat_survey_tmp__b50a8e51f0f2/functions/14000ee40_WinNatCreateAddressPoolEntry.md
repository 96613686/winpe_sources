# WinNatCreateAddressPoolEntry

- ea: `0x14000ee40`
- end: `0x14000f128`
- name: `WinNatCreateAddressPoolEntry`
- size: `744`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bdf0`
- `0x14000fc88`
- `0x140010e64`

## callees

- `0x140004da0`
- `0x1400085d0`
- `0x14000caa0`
- `0x14000e488`
- `0x14000e680`
- `0x14000ee40`
- `0x1400195fc`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000effb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000effb`
- `ntoskrnl!ExAllocatePool2` at `0x14000ee88`
- `ntoskrnl!ExAllocatePool2` at `0x14000ee88`
- `NETIO!NsiGetAllParameters` at `0x14000ef5c`
- `NETIO!NsiGetAllParameters` at `0x14000ef5c`

## pseudocode

```c
__int64 __fastcall WinNatCreateAddressPoolEntry(__int64 a1, __int64 a2, __int64 *a3, char a4)
{
  __int64 v8; // rdx
  __int64 Pool2; // rdi
  __int64 v10; // r8
  _DWORD *v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int AllParameters; // r15d
  char v17; // al
  char v18; // dl
  char v19; // al
  int v20; // r8d
  _QWORD *v21; // rdx
  __int128 v22; // [rsp+60h] [rbp-58h] BYREF

  v22 = 0;
  Pool2 = ExAllocatePool2(64, 80, 1885425239);
  if ( Pool2 )
  {
    v12 = (_DWORD *)(a1 + 536);
    if ( Ipv4AddressType((const UCHAR *)(a1 + 536)) == NlatUnspecified )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, v13);
    v15 = *(_QWORD *)(a1 + 528);
    *(_QWORD *)(Pool2 + 48) = v15;
    *(_QWORD *)(Pool2 + 16) = 1;
    *(_WORD *)(Pool2 + 58) = *(_WORD *)(a1 + 542);
    *(_WORD *)(Pool2 + 56) = *(_WORD *)(a1 + 540);
    *(_DWORD *)(Pool2 + 40) = *v12;
    *(_QWORD *)&v22 = v15;
    DWORD2(v22) = *(_DWORD *)(Pool2 + 40);
    AllParameters = NsiGetAllParameters(1, &NPI_MS_IPV4_MODULEID, 10, &v22, 16, 0, 0, 0, 0, 0, 0);
    if ( (int)(AllParameters + 0x80000000) >= 0 && AllParameters != -1073741275 )
      goto LABEL_13;
    v17 = *(_BYTE *)(Pool2 + 72);
    v18 = v17 | 1;
    v19 = v17 & 0xFE;
    if ( AllParameters != -1073741275 )
      v18 = v19;
    *(_BYTE *)(Pool2 + 72) = v18 ^ (v18 ^ (2 * a4)) & 2;
    AllParameters = WinNatLibCreateAddress(
                      (__int64)qword_140026AE0,
                      *(_QWORD *)(a2 + 888),
                      0,
                      *(_WORD *)(a1 + 540),
                      *(_WORD *)(a1 + 542),
                      (_DWORD *)(a1 + 536),
                      4u,
                      0,
                      0,
                      0);
    if ( AllParameters >= 0 )
    {
      if ( (*(_BYTE *)(Pool2 + 72) & 1) != 0 )
        WinNatLibSetAddress(
          (__int64)qword_140026AE0,
          a1 + 536,
          v20,
          *(unsigned __int16 *)(a1 + 540),
          *(_WORD *)(a1 + 542),
          0);
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 320)) <= 1 )
        __fastfail(0xEu);
      *(_QWORD *)(Pool2 + 64) = a2;
      v21 = *(_QWORD **)(a2 + 904);
      if ( *v21 != a2 + 896 )
        __fastfail(3u);
      *(_QWORD *)(Pool2 + 24) = a2 + 896;
      *(_QWORD *)(Pool2 + 32) = v21;
      *v21 = Pool2 + 24;
      *(_QWORD *)(a2 + 904) = Pool2 + 24;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(Pool2 + 16)) <= 1 )
        __fastfail(0xEu);
      if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
        McTemplateK0zqhhxqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          (unsigned int)WINNAT_ADDRESS_POOL_CONFIG,
          14,
          a1,
          *v12,
          *(_WORD *)(a1 + 540),
          *(_WORD *)(a1 + 542),
          *(_QWORD *)(a1 + 528),
          1,
          AllParameters);
      *a3 = Pool2;
      return 0;
    }
    else
    {
LABEL_13:
      ExFreePoolWithTag((PVOID)Pool2, 0);
      return (unsigned int)AllParameters;
    }
  }
  else
  {
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        v8,
        v10,
        L"Address pool entry allocation failed");
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14000ee40  mov     [rsp+arg_18], rbx
0x14000ee45  push    rbp
0x14000ee46  push    rsi
0x14000ee47  push    rdi
0x14000ee48  push    r12
0x14000ee4a  push    r13
0x14000ee4c  push    r14
0x14000ee4e  push    r15
0x14000ee50  sub     rsp, 80h
0x14000ee57  mov     rax, cs:__security_cookie
0x14000ee5e  xor     rax, rsp
0x14000ee61  mov     [rsp+0B8h+var_48], rax
0x14000ee66  mov     rbp, rdx
0x14000ee69  mov     r13, r8
0x14000ee6c  mov     edx, 50h ; 'P'
0x14000ee71  mov     rsi, rcx
0x14000ee74  xorps   xmm0, xmm0
0x14000ee77  mov     r8d, 70614E57h
0x14000ee7d  mov     r12b, r9b
0x14000ee80  movups  [rsp+0B8h+var_58], xmm0
0x14000ee85  lea     ecx, [rdx-10h]
0x14000ee88  call    cs:__imp_ExAllocatePool2
0x14000ee8f  nop     dword ptr [rax+rax+00h]
0x14000ee94  xor     r15d, r15d
0x14000ee97  mov     rdi, rax
0x14000ee9a  test    rax, rax
0x14000ee9d  jnz     short loc_14000EED0
0x14000ee9f  lea     ebx, [rax+1]
0x14000eea2  cmp     cs:dword_140026104, ebx
0x14000eea8  jnz     short loc_14000EEC6
0x14000eeaa  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14000eeb1  jz      short loc_14000EEC6
0x14000eeb3  lea     r9, aAddressPoolEnt; "Address pool entry allocation failed"
0x14000eeba  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000eec1  call    McTemplateK0z_EtwWriteTransfer
0x14000eec6  mov     eax, 0C000009Ah
0x14000eecb  jmp     loc_14000F0FF
0x14000eed0  lea     r14, [rsi+218h]
0x14000eed7  mov     rcx, r14; Address
0x14000eeda  call    Ipv4AddressType
0x14000eedf  test    eax, eax
0x14000eee1  jnz     short loc_14000EEE8
0x14000eee3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000eee8  mov     rcx, [rsi+210h]
0x14000eeef  lea     r9, [rsp+0B8h+var_58]
0x14000eef4  mov     [rdi+30h], rcx
0x14000eef8  lea     rdx, NPI_MS_IPV4_MODULEID
0x14000eeff  mov     [rsp+0B8h+var_68], r15d
0x14000ef04  mov     ebx, 1
0x14000ef09  mov     [rdi+10h], rbx
0x14000ef0d  movzx   eax, word ptr [rsi+21Eh]
0x14000ef14  mov     [rdi+3Ah], ax
0x14000ef18  movzx   eax, word ptr [rsi+21Ch]
0x14000ef1f  lea     r8d, [rbx+9]
0x14000ef23  mov     [rdi+38h], ax
0x14000ef27  mov     eax, [r14]
0x14000ef2a  mov     [rsp+0B8h+var_70], r15
0x14000ef2f  mov     dword ptr [rsp+0B8h+var_78], r15d
0x14000ef34  mov     [rdi+28h], eax
0x14000ef37  mov     [rsp+0B8h+var_80], r15
0x14000ef3c  mov     qword ptr [rsp+0B8h+var_58], rcx
0x14000ef41  mov     ecx, ebx
0x14000ef43  mov     eax, [rdi+28h]
0x14000ef46  mov     [rsp+0B8h+var_88], r15d
0x14000ef4b  mov     [rsp+0B8h+var_90], r15
0x14000ef50  mov     dword ptr [rsp+0B8h+var_58+8], eax
0x14000ef54  mov     [rsp+0B8h+var_98], 10h
0x14000ef5c  call    cs:__imp_NsiGetAllParameters
0x14000ef63  nop     dword ptr [rax+rax+00h]
0x14000ef68  mov     r15d, eax
0x14000ef6b  mov     r8d, 0C0000225h
0x14000ef71  mov     eax, 80000000h
0x14000ef76  lea     ecx, [r15+rax]
0x14000ef7a  test    eax, ecx
0x14000ef7c  jnz     short loc_14000EF83
0x14000ef7e  cmp     r15d, r8d
0x14000ef81  jnz     short loc_14000EFF6
0x14000ef83  mov     cl, [rdi+48h]
0x14000ef86  mov     al, cl
0x14000ef88  or      cl, bl
0x14000ef8a  and     al, 0FEh
0x14000ef8c  movzx   edx, cl
0x14000ef8f  cmp     r15d, r8d
0x14000ef92  movzx   eax, al
0x14000ef95  cmovnz  edx, eax
0x14000ef98  add     r12b, r12b
0x14000ef9b  xor     r12b, dl
0x14000ef9e  xor     r8d, r8d
0x14000efa1  and     r12b, 2
0x14000efa5  xor     r12b, dl
0x14000efa8  mov     [rdi+48h], r12b
0x14000efac  xor     r12d, r12d
0x14000efaf  movzx   eax, word ptr [rsi+21Eh]
0x14000efb6  movzx   r9d, word ptr [rsi+21Ch]
0x14000efbe  mov     rdx, [rbp+378h]
0x14000efc5  mov     rcx, cs:qword_140026AE0
0x14000efcc  mov     [rsp+0B8h+var_70], r12
0x14000efd1  mov     [rsp+0B8h+var_78], r12
0x14000efd6  mov     [rsp+0B8h+var_80], r12
0x14000efdb  mov     byte ptr [rsp+0B8h+var_88], 4
0x14000efe0  mov     [rsp+0B8h+var_90], r14
0x14000efe5  mov     word ptr [rsp+0B8h+var_98], ax
0x14000efea  call    WinNatLibCreateAddress
0x14000efef  mov     r15d, eax
0x14000eff2  test    eax, eax
0x14000eff4  jns     short loc_14000F00F
0x14000eff6  xor     edx, edx; Tag
0x14000eff8  mov     rcx, rdi; P
0x14000effb  call    cs:__imp_ExFreePoolWithTag
0x14000f002  nop     dword ptr [rax+rax+00h]
0x14000f007  mov     eax, r15d
0x14000f00a  jmp     loc_14000F0FF
0x14000f00f  test    [rdi+48h], bl
0x14000f012  jz      short loc_14000F03C
0x14000f014  movzx   eax, word ptr [rsi+21Eh]
0x14000f01b  mov     rdx, r14
0x14000f01e  movzx   r9d, word ptr [rsi+21Ch]
0x14000f026  mov     rcx, cs:qword_140026AE0
0x14000f02d  mov     byte ptr [rsp+0B8h+var_90], r12b
0x14000f032  mov     word ptr [rsp+0B8h+var_98], ax
0x14000f037  call    WinNatLibSetAddress
0x14000f03c  mov     rax, rbx
0x14000f03f  lock xadd [rbp+140h], rax
0x14000f048  add     rax, rbx
0x14000f04b  mov     r8d, 0Eh
0x14000f051  cmp     rax, rbx
0x14000f054  jg      short loc_14000F05B
0x14000f056  mov     ecx, r8d
0x14000f059  int     29h; Win8: RtlFailFast(ecx)
0x14000f05b  lea     rcx, [rbp+380h]
0x14000f062  mov     [rdi+40h], rbp
0x14000f066  mov     rdx, [rcx+8]
0x14000f06a  cmp     [rdx], rcx
0x14000f06d  jz      short loc_14000F076
0x14000f06f  mov     ecx, 3
0x14000f074  int     29h; Win8: RtlFailFast(ecx)
0x14000f076  lea     rax, [rdi+18h]
0x14000f07a  mov     [rax], rcx
0x14000f07d  mov     [rax+8], rdx
0x14000f081  mov     [rdx], rax
0x14000f084  mov     [rcx+8], rax
0x14000f088  mov     rax, rbx
0x14000f08b  lock xadd [rdi+10h], rax
0x14000f091  add     rax, rbx
0x14000f094  cmp     rax, rbx
0x14000f097  jg      short loc_14000F09E
0x14000f099  mov     rcx, r8
0x14000f09c  int     29h; Win8: RtlFailFast(ecx)
0x14000f09e  cmp     cs:dword_140026104, ebx
0x14000f0a4  jnz     short loc_14000F0F9
0x14000f0a6  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14000f0ad  jz      short loc_14000F0F9
0x14000f0af  mov     rax, [rsi+210h]
0x14000f0b6  lea     rdx, WINNAT_ADDRESS_POOL_CONFIG
0x14000f0bd  mov     dword ptr [rsp+0B8h+var_70], r15d
0x14000f0c2  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f0c9  mov     dword ptr [rsp+0B8h+var_78], ebx
0x14000f0cd  mov     r9, rsi
0x14000f0d0  mov     [rsp+0B8h+var_80], rax
0x14000f0d5  movzx   eax, word ptr [rsi+21Eh]
0x14000f0dc  mov     word ptr [rsp+0B8h+var_88], ax
0x14000f0e1  movzx   eax, word ptr [rsi+21Ch]
0x14000f0e8  mov     word ptr [rsp+0B8h+var_90], ax
0x14000f0ed  mov     eax, [r14]
0x14000f0f0  mov     [rsp+0B8h+var_98], eax
0x14000f0f4  call    McTemplateK0zqhhxqq_EtwWriteTransfer
0x14000f0f9  mov     [r13+0], rdi
0x14000f0fd  xor     eax, eax
0x14000f0ff  mov     rcx, [rsp+0B8h+var_48]
0x14000f104  xor     rcx, rsp; StackCookie
0x14000f107  call    __security_check_cookie
0x14000f10c  mov     rbx, [rsp+0B8h+arg_18]
0x14000f114  add     rsp, 80h
0x14000f11b  pop     r15
0x14000f11d  pop     r14
0x14000f11f  pop     r13
0x14000f121  pop     r12
0x14000f123  pop     rdi
0x14000f124  pop     rsi
0x14000f125  pop     rbp
0x14000f126  retn
```

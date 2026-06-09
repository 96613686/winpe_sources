# WinNatCreateAddressPoolEntry

- ea: `0x14000ee98`
- end: `0x14000f180`
- name: `WinNatCreateAddressPoolEntry`
- size: `744`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, char)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bdf0`
- `0x14000fce8`
- `0x140010ec4`

## callees

- `0x140004da0`
- `0x1400085d0`
- `0x14000caa0`
- `0x14000e4b0`
- `0x14000e6a8`
- `0x14000ee98`
- `0x140019adc`
- `0x14001f320`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f053`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f053`
- `ntoskrnl!ExAllocatePool2` at `0x14000eee0`
- `ntoskrnl!ExAllocatePool2` at `0x14000eee0`
- `NETIO!NsiGetAllParameters` at `0x14000efb4`
- `NETIO!NsiGetAllParameters` at `0x14000efb4`

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
  __int64 v15; // r8
  __int64 v16; // rcx
  int AllParameters; // r15d
  char v18; // al
  char v19; // dl
  char v20; // al
  int v21; // r8d
  _QWORD *v22; // rdx
  int v23; // [rsp+20h] [rbp-98h]
  int v24; // [rsp+30h] [rbp-88h]
  __int128 v25; // [rsp+60h] [rbp-58h] BYREF

  v25 = 0;
  Pool2 = ExAllocatePool2(64, 80, 1885425239);
  if ( Pool2 )
  {
    v12 = (_DWORD *)(a1 + 536);
    if ( Ipv4AddressType((const UCHAR *)(a1 + 536)) == NlatUnspecified )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, v13, v15);
    v16 = *(_QWORD *)(a1 + 528);
    *(_QWORD *)(Pool2 + 48) = v16;
    *(_QWORD *)(Pool2 + 16) = 1;
    *(_WORD *)(Pool2 + 58) = *(_WORD *)(a1 + 542);
    *(_WORD *)(Pool2 + 56) = *(_WORD *)(a1 + 540);
    *(_DWORD *)(Pool2 + 40) = *v12;
    *(_QWORD *)&v25 = v16;
    DWORD2(v25) = *(_DWORD *)(Pool2 + 40);
    AllParameters = NsiGetAllParameters(1, &NPI_MS_IPV4_MODULEID, 10, &v25, 16, 0, 0, 0, 0, 0, 0);
    if ( (int)(AllParameters + 0x80000000) >= 0 && AllParameters != -1073741275 )
      goto LABEL_13;
    v18 = *(_BYTE *)(Pool2 + 72);
    v19 = v18 | 1;
    v20 = v18 & 0xFE;
    if ( AllParameters != -1073741275 )
      v19 = v20;
    *(_BYTE *)(Pool2 + 72) = v19 ^ (v19 ^ (2 * a4)) & 2;
    LOBYTE(v24) = 4;
    LOWORD(v23) = *(_WORD *)(a1 + 542);
    AllParameters = WinNatLibCreateAddress(
                      qword_140027AE0,
                      *(_QWORD *)(a2 + 888),
                      0,
                      *(unsigned __int16 *)(a1 + 540),
                      v23,
                      a1 + 536,
                      v24,
                      0,
                      0,
                      0);
    if ( AllParameters >= 0 )
    {
      if ( (*(_BYTE *)(Pool2 + 72) & 1) != 0 )
        WinNatLibSetAddress(
          (_DWORD)qword_140027AE0,
          a1 + 536,
          v21,
          *(unsigned __int16 *)(a1 + 540),
          *(_WORD *)(a1 + 542),
          0);
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 320)) <= 1 )
        __fastfail(0xEu);
      *(_QWORD *)(Pool2 + 64) = a2;
      v22 = *(_QWORD **)(a2 + 904);
      if ( *v22 != a2 + 896 )
        __fastfail(3u);
      *(_QWORD *)(Pool2 + 24) = a2 + 896;
      *(_QWORD *)(Pool2 + 32) = v22;
      *v22 = Pool2 + 24;
      *(_QWORD *)(a2 + 904) = Pool2 + 24;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(Pool2 + 16)) <= 1 )
        __fastfail(0xEu);
      if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
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
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
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
0x14000ee98  mov     [rsp+arg_18], rbx
0x14000ee9d  push    rbp
0x14000ee9e  push    rsi
0x14000ee9f  push    rdi
0x14000eea0  push    r12
0x14000eea2  push    r13
0x14000eea4  push    r14
0x14000eea6  push    r15
0x14000eea8  sub     rsp, 80h
0x14000eeaf  mov     rax, cs:__security_cookie
0x14000eeb6  xor     rax, rsp
0x14000eeb9  mov     [rsp+0B8h+var_48], rax
0x14000eebe  mov     rbp, rdx
0x14000eec1  mov     r13, r8
0x14000eec4  mov     edx, 50h ; 'P'
0x14000eec9  mov     rsi, rcx
0x14000eecc  xorps   xmm0, xmm0
0x14000eecf  mov     r8d, 70614E57h
0x14000eed5  mov     r12b, r9b
0x14000eed8  movups  [rsp+0B8h+var_58], xmm0
0x14000eedd  lea     ecx, [rdx-10h]
0x14000eee0  call    cs:__imp_ExAllocatePool2
0x14000eee7  nop     dword ptr [rax+rax+00h]
0x14000eeec  xor     r15d, r15d
0x14000eeef  mov     rdi, rax
0x14000eef2  test    rax, rax
0x14000eef5  jnz     short loc_14000EF28
0x14000eef7  lea     ebx, [rax+1]
0x14000eefa  cmp     cs:dword_140027104, ebx
0x14000ef00  jnz     short loc_14000EF1E
0x14000ef02  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14000ef09  jz      short loc_14000EF1E
0x14000ef0b  lea     r9, aAddressPoolEnt; "Address pool entry allocation failed"
0x14000ef12  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000ef19  call    McTemplateK0z_EtwWriteTransfer
0x14000ef1e  mov     eax, 0C000009Ah
0x14000ef23  jmp     loc_14000F157
0x14000ef28  lea     r14, [rsi+218h]
0x14000ef2f  mov     rcx, r14; Address
0x14000ef32  call    Ipv4AddressType
0x14000ef37  test    eax, eax
0x14000ef39  jnz     short loc_14000EF40
0x14000ef3b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000ef40  mov     rcx, [rsi+210h]
0x14000ef47  lea     r9, [rsp+0B8h+var_58]
0x14000ef4c  mov     [rdi+30h], rcx
0x14000ef50  lea     rdx, NPI_MS_IPV4_MODULEID
0x14000ef57  mov     [rsp+0B8h+var_68], r15d
0x14000ef5c  mov     ebx, 1
0x14000ef61  mov     [rdi+10h], rbx
0x14000ef65  movzx   eax, word ptr [rsi+21Eh]
0x14000ef6c  mov     [rdi+3Ah], ax
0x14000ef70  movzx   eax, word ptr [rsi+21Ch]
0x14000ef77  lea     r8d, [rbx+9]
0x14000ef7b  mov     [rdi+38h], ax
0x14000ef7f  mov     eax, [r14]
0x14000ef82  mov     [rsp+0B8h+var_70], r15
0x14000ef87  mov     dword ptr [rsp+0B8h+var_78], r15d
0x14000ef8c  mov     [rdi+28h], eax
0x14000ef8f  mov     [rsp+0B8h+var_80], r15
0x14000ef94  mov     qword ptr [rsp+0B8h+var_58], rcx
0x14000ef99  mov     ecx, ebx
0x14000ef9b  mov     eax, [rdi+28h]
0x14000ef9e  mov     [rsp+0B8h+var_88], r15d
0x14000efa3  mov     [rsp+0B8h+var_90], r15
0x14000efa8  mov     dword ptr [rsp+0B8h+var_58+8], eax
0x14000efac  mov     [rsp+0B8h+var_98], 10h
0x14000efb4  call    cs:__imp_NsiGetAllParameters
0x14000efbb  nop     dword ptr [rax+rax+00h]
0x14000efc0  mov     r15d, eax
0x14000efc3  mov     r8d, 0C0000225h
0x14000efc9  mov     eax, 80000000h
0x14000efce  lea     ecx, [r15+rax]
0x14000efd2  test    eax, ecx
0x14000efd4  jnz     short loc_14000EFDB
0x14000efd6  cmp     r15d, r8d
0x14000efd9  jnz     short loc_14000F04E
0x14000efdb  mov     cl, [rdi+48h]
0x14000efde  mov     al, cl
0x14000efe0  or      cl, bl
0x14000efe2  and     al, 0FEh
0x14000efe4  movzx   edx, cl
0x14000efe7  cmp     r15d, r8d
0x14000efea  movzx   eax, al
0x14000efed  cmovnz  edx, eax
0x14000eff0  add     r12b, r12b
0x14000eff3  xor     r12b, dl
0x14000eff6  xor     r8d, r8d
0x14000eff9  and     r12b, 2
0x14000effd  xor     r12b, dl
0x14000f000  mov     [rdi+48h], r12b
0x14000f004  xor     r12d, r12d
0x14000f007  movzx   eax, word ptr [rsi+21Eh]
0x14000f00e  movzx   r9d, word ptr [rsi+21Ch]
0x14000f016  mov     rdx, [rbp+378h]
0x14000f01d  mov     rcx, cs:qword_140027AE0
0x14000f024  mov     [rsp+0B8h+var_70], r12
0x14000f029  mov     [rsp+0B8h+var_78], r12
0x14000f02e  mov     [rsp+0B8h+var_80], r12
0x14000f033  mov     byte ptr [rsp+0B8h+var_88], 4
0x14000f038  mov     [rsp+0B8h+var_90], r14
0x14000f03d  mov     word ptr [rsp+0B8h+var_98], ax
0x14000f042  call    WinNatLibCreateAddress
0x14000f047  mov     r15d, eax
0x14000f04a  test    eax, eax
0x14000f04c  jns     short loc_14000F067
0x14000f04e  xor     edx, edx; Tag
0x14000f050  mov     rcx, rdi; P
0x14000f053  call    cs:__imp_ExFreePoolWithTag
0x14000f05a  nop     dword ptr [rax+rax+00h]
0x14000f05f  mov     eax, r15d
0x14000f062  jmp     loc_14000F157
0x14000f067  test    [rdi+48h], bl
0x14000f06a  jz      short loc_14000F094
0x14000f06c  movzx   eax, word ptr [rsi+21Eh]
0x14000f073  mov     rdx, r14
0x14000f076  movzx   r9d, word ptr [rsi+21Ch]
0x14000f07e  mov     rcx, cs:qword_140027AE0
0x14000f085  mov     byte ptr [rsp+0B8h+var_90], r12b
0x14000f08a  mov     word ptr [rsp+0B8h+var_98], ax
0x14000f08f  call    WinNatLibSetAddress
0x14000f094  mov     rax, rbx
0x14000f097  lock xadd [rbp+140h], rax
0x14000f0a0  add     rax, rbx
0x14000f0a3  mov     r8d, 0Eh
0x14000f0a9  cmp     rax, rbx
0x14000f0ac  jg      short loc_14000F0B3
0x14000f0ae  mov     ecx, r8d
0x14000f0b1  int     29h; Win8: RtlFailFast(ecx)
0x14000f0b3  lea     rcx, [rbp+380h]
0x14000f0ba  mov     [rdi+40h], rbp
0x14000f0be  mov     rdx, [rcx+8]
0x14000f0c2  cmp     [rdx], rcx
0x14000f0c5  jz      short loc_14000F0CE
0x14000f0c7  mov     ecx, 3
0x14000f0cc  int     29h; Win8: RtlFailFast(ecx)
0x14000f0ce  lea     rax, [rdi+18h]
0x14000f0d2  mov     [rax], rcx
0x14000f0d5  mov     [rax+8], rdx
0x14000f0d9  mov     [rdx], rax
0x14000f0dc  mov     [rcx+8], rax
0x14000f0e0  mov     rax, rbx
0x14000f0e3  lock xadd [rdi+10h], rax
0x14000f0e9  add     rax, rbx
0x14000f0ec  cmp     rax, rbx
0x14000f0ef  jg      short loc_14000F0F6
0x14000f0f1  mov     rcx, r8
0x14000f0f4  int     29h; Win8: RtlFailFast(ecx)
0x14000f0f6  cmp     cs:dword_140027104, ebx
0x14000f0fc  jnz     short loc_14000F151
0x14000f0fe  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14000f105  jz      short loc_14000F151
0x14000f107  mov     rax, [rsi+210h]
0x14000f10e  lea     rdx, WINNAT_ADDRESS_POOL_CONFIG
0x14000f115  mov     dword ptr [rsp+0B8h+var_70], r15d
0x14000f11a  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f121  mov     dword ptr [rsp+0B8h+var_78], ebx
0x14000f125  mov     r9, rsi
0x14000f128  mov     [rsp+0B8h+var_80], rax
0x14000f12d  movzx   eax, word ptr [rsi+21Eh]
0x14000f134  mov     word ptr [rsp+0B8h+var_88], ax
0x14000f139  movzx   eax, word ptr [rsi+21Ch]
0x14000f140  mov     word ptr [rsp+0B8h+var_90], ax
0x14000f145  mov     eax, [r14]
0x14000f148  mov     [rsp+0B8h+var_98], eax
0x14000f14c  call    McTemplateK0zqhhxqq_EtwWriteTransfer
0x14000f151  mov     [r13+0], rdi
0x14000f155  xor     eax, eax
0x14000f157  mov     rcx, [rsp+0B8h+var_48]
0x14000f15c  xor     rcx, rsp; StackCookie
0x14000f15f  call    __security_check_cookie
0x14000f164  mov     rbx, [rsp+0B8h+arg_18]
0x14000f16c  add     rsp, 80h
0x14000f173  pop     r15
0x14000f175  pop     r14
0x14000f177  pop     r13
0x14000f179  pop     r12
0x14000f17b  pop     rdi
0x14000f17c  pop     rsi
0x14000f17d  pop     rbp
0x14000f17e  retn
```

# SlbNatIpsClientReceivePackets

- ea: `0x140001c30`
- end: `0x1400020cf`
- name: `SlbNatIpsClientReceivePackets`
- size: `1183`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140001c30`
- `0x1400020e0`
- `0x140004e60`
- `0x140006340`
- `0x1400077fc`
- `0x14000caa0`
- `0x14000d334`
- `0x14001b4b4`
- `0x14001ef70`
- `0x14001f440`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140001f59`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140001f59`

## pseudocode

```c
__int64 __fastcall SlbNatIpsClientReceivePackets(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r8
  _QWORD *v15; // rax
  _QWORD *v16; // r12
  _QWORD *v17; // r15
  __int64 v18; // rdx
  __int64 v19; // rbx
  unsigned int v20; // edi
  __int64 v21; // rcx
  unsigned int v22; // edi
  char *v23; // r14
  __int64 v24; // rbx
  int v25; // eax
  int v26; // eax
  int v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // r8
  _QWORD *v30; // rcx
  __int64 result; // rax
  __int64 v32; // rcx
  signed __int64 v33; // rax
  bool v34; // cc
  _QWORD *i; // rax
  char v36; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[23]; // [rsp+41h] [rbp-BFh]
  _OWORD v38[11]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v39[24]; // [rsp+110h] [rbp+10h] BYREF

  v11 = *(_QWORD **)(a7 + 8);
  memset(v38, 0, 0xA8u);
  v14 = 0;
  LOWORD(v38[0]) = *(_WORD *)a1;
  *((_QWORD *)&v38[0] + 1) = *(_QWORD *)(a1 + 16);
  *(_QWORD *)&v38[1] = *(_QWORD *)(a1 + 24);
  LODWORD(v38[2]) = a5;
  *((_QWORD *)&v38[2] + 1) = a6;
  *((_QWORD *)&v38[8] + 1) = &v38[8];
  *((_QWORD *)&v38[9] + 1) = &v38[9];
  *(_OWORD *)v37 = 0;
  *((_QWORD *)&v38[1] + 1) = __PAIR64__(a4, a3);
  *(_QWORD *)&v38[3] = a2;
  *(_QWORD *)&v38[4] = 0;
  *((_QWORD *)&v38[4] + 1) = a1;
  *(_QWORD *)&v38[5] = 0;
  *(_QWORD *)&v38[7] = 0;
  *(_QWORD *)&v38[8] = 0;
  *(_QWORD *)&v38[9] = 0;
  BYTE2(v38[0]) = 0;
  WORD4(v38[5]) = 0;
  BYTE8(v38[6]) = 0;
  LODWORD(v38[10]) = 0;
  v36 = 0;
  if ( gAccount )
  {
    for ( i = v11; i; i = (_QWORD *)*i )
      _InterlockedIncrement64(&gNBLIndicate);
  }
  while ( 1 )
  {
    v15 = v11;
    v16 = v11;
    v17 = v11;
    v18 = 1;
    v11 = (_QWORD *)*v11;
    v19 = v16[1];
    *v15 = 0;
    v20 = *(_DWORD *)(*(_QWORD *)(v19 + 8) + 40LL);
    if ( v20 <= *(_DWORD *)(v19 + 16) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, 1, 0, v13);
      v18 = 1;
      v14 = 0;
    }
    v21 = *(_QWORD *)(v19 + 8);
    v22 = v20 - *(_DWORD *)(v19 + 16);
    if ( (*(_BYTE *)(v21 + 10) & 5) != 0 )
      v23 = *(char **)(v21 + 24);
    else
      v23 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v21, 0, MmCached, 0, 0, 0x40000000u);
    if ( !v23 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v18, v14, v13);
    v24 = *(unsigned int *)(v19 + 16);
    if ( LOWORD(v38[0]) != 2 )
    {
      if ( v22 < 0x28 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v18, v14, v13);
      v26 = Ipv6AddressType(&v23[v24 + 24], v18);
      goto LABEL_16;
    }
    if ( v22 < 0x14 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v18, v14, v13);
    v25 = *(_DWORD *)&v23[v24 + 16];
    if ( (v25 & 0xF0) == 0xE0 )
    {
      v26 = 3;
      goto LABEL_16;
    }
    if ( v25 == -1 )
    {
      v26 = 4;
      goto LABEL_16;
    }
    if ( !v25 )
    {
      v26 = 0;
      goto LABEL_16;
    }
    if ( !(_BYTE)v25 || (v25 & 0xF0) == 0xF0 )
    {
      v26 = 5;
LABEL_16:
      v27 = 1;
      goto LABEL_17;
    }
    v27 = 1;
    v26 = 1;
LABEL_17:
    if ( v26 == 1 )
    {
      *((_QWORD *)&v38[3] + 1) = v17;
      SlbNatIpsHandleIncomingUnicastDatagram((__int64)v38);
    }
    else
    {
      *(_QWORD *)&v37[7] = v17;
      *(_QWORD *)&v37[15] = v17;
      if ( gAccount && v16 )
      {
        do
        {
          _InterlockedIncrement64(&gNBLReturn);
          v16 = (_QWORD *)*v16;
        }
        while ( v16 );
      }
      (*(void (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)(a1 + 24) + 40LL))(*(_QWORD *)(a1 + 16), a2, &v36);
    }
    if ( !v11 )
      break;
    v14 = 0;
  }
  v30 = *(_QWORD **)&v38[8];
  if ( *(_QWORD *)&v38[8] )
  {
    if ( !*(_QWORD *)&v38[7] )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(*(_QWORD *)&v38[8], v28, v29, v13);
      v30 = *(_QWORD **)&v38[8];
    }
    if ( (BYTE2(v38[0]) & 2) != 0 )
    {
      SlbNatIpsClientPendPackets(v38);
    }
    else
    {
      if ( (byte_140026BED & 8) != 0 && LOWORD(v38[0]) == 2 )
      {
        memset(v39, 0, 28);
        (*(void (__fastcall **)(_QWORD, _QWORD, _DWORD *))(*(_QWORD *)&v38[1] + 112LL))(
          *((_QWORD *)&v38[0] + 1),
          *(_QWORD *)&v38[7],
          v39);
        if ( (BYTE2(v38[0]) & 1) == 0 )
        {
          if ( *(_QWORD *)&v38[5] )
            v27 = **(_DWORD **)&v38[5];
          else
            v27 = 0;
        }
        SlbNatIpsLogIPv4Datagram(DWORD2(v38[1]), v38[2], DWORD2(v38[2]), v27, v39[0], *(__int64 *)&v38[8], 0, 0);
        v30 = *(_QWORD **)&v38[8];
      }
      *(_QWORD *)&v37[15] = *((_QWORD *)&v38[8] + 1);
      *(_QWORD *)&v37[7] = v30;
      if ( gAccount && v30 )
      {
        do
        {
          _InterlockedIncrement64(&gNBLForward);
          v30 = (_QWORD *)*v30;
        }
        while ( v30 );
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, _QWORD))(*(_QWORD *)&v38[1] + 48LL))(
        *((_QWORD *)&v38[0] + 1),
        *(_QWORD *)&v38[3],
        &v36,
        0,
        *(_QWORD *)&v38[7]);
    }
  }
  if ( *(_QWORD *)&v38[9] )
  {
    *(_OWORD *)&v37[7] = v38[9];
    SlbNatAccountChain(&v36, 4);
    (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)&v38[1] + 64LL))(*((_QWORD *)&v38[0] + 1), &v36);
  }
  if ( *(_QWORD *)&v38[7] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)&v38[1] + 104LL))(*((_QWORD *)&v38[0] + 1));
  result = *(_QWORD *)&v38[5];
  if ( *(_QWORD *)&v38[5] )
  {
    v32 = *(_QWORD *)&v38[5] - 8LL;
    v33 = _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)&v38[5] - 8LL), 0xFFFFFFFFFFFFFFFFuLL);
    v34 = v33 <= 1;
    result = v33 - 1;
    if ( v34 )
    {
      if ( result )
        __fastfail(0xEu);
      return WinNatLibCleanupSession(v32);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001c30  mov     [rsp-8+arg_8], rdx
0x140001c35  push    rbp
0x140001c36  push    rbx
0x140001c37  push    rsi
0x140001c38  push    rdi
0x140001c39  push    r12
0x140001c3b  push    r13
0x140001c3d  push    r14
0x140001c3f  push    r15
0x140001c41  lea     rbp, [rsp-38h]
0x140001c46  sub     rsp, 138h
0x140001c4d  mov     rax, [rbp+70h+arg_30]
0x140001c54  mov     ebx, r8d
0x140001c57  mov     r14, rdx
0x140001c5a  mov     r13, rcx
0x140001c5d  xor     edx, edx; Val
0x140001c5f  lea     rcx, [rsp+170h+var_110]; void *
0x140001c64  mov     r8d, 0A8h; Size
0x140001c6a  mov     edi, r9d
0x140001c6d  mov     rsi, [rax+8]
0x140001c71  call    memset
0x140001c76  movzx   eax, word ptr [r13+0]
0x140001c7b  xor     r8d, r8d
0x140001c7e  cmp     cs:gAccount, r8d
0x140001c85  xorps   xmm0, xmm0
0x140001c88  mov     [rsp+170h+var_110], ax
0x140001c8d  mov     rax, [r13+10h]
0x140001c91  mov     [rsp+170h+var_108], rax
0x140001c96  mov     rax, [r13+18h]
0x140001c9a  mov     [rsp+170h+var_100], rax
0x140001c9f  mov     eax, [rbp+70h+arg_20]
0x140001ca5  mov     [rbp+70h+var_F0], eax
0x140001ca8  mov     rax, [rbp+70h+arg_28]
0x140001caf  mov     [rbp+70h+var_E8], rax
0x140001cb3  lea     rax, [rbp+70h+var_90]
0x140001cb7  mov     [rbp+70h+var_88], rax
0x140001cbb  lea     rax, [rbp+70h+var_80]
0x140001cbf  mov     qword ptr [rbp+70h+var_80+8], rax
0x140001cc3  movdqu  xmmword ptr [rsp+170h+var_12F], xmm0
0x140001cc9  mov     [rsp+170h+var_F8], ebx
0x140001ccd  mov     [rsp+170h+var_F4], edi
0x140001cd1  mov     [rbp+70h+var_E0], r14
0x140001cd5  mov     [rbp+70h+var_D0], r8
0x140001cd9  mov     [rbp+70h+var_C8], r13
0x140001cdd  mov     [rbp+70h+var_C0], r8
0x140001ce1  mov     [rbp+70h+var_A0], r8
0x140001ce5  mov     [rbp+70h+var_90], r8
0x140001ce9  mov     qword ptr [rbp+70h+var_80], r8
0x140001ced  mov     [rsp+170h+var_10E], r8b
0x140001cf2  mov     [rbp+70h+var_B8], r8w
0x140001cf7  mov     [rbp+70h+var_A8], r8b
0x140001cfb  mov     [rbp+70h+var_70], r8d
0x140001cff  mov     [rsp+170h+var_130], r8b
0x140001d04  jnz     loc_140001F88
0x140001d0a  mov     rax, rsi
0x140001d0d  mov     r12, rsi
0x140001d10  mov     r15, rsi
0x140001d13  mov     edx, 1
0x140001d18  mov     rsi, [rsi]
0x140001d1b  mov     rbx, [r12+8]
0x140001d20  mov     [rax], r8
0x140001d23  mov     rax, [rbx+8]
0x140001d27  mov     edi, [rax+28h]
0x140001d2a  cmp     edi, [rbx+10h]
0x140001d2d  jbe     loc_140001E02
0x140001d33  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140001d37  sub     edi, [rbx+10h]
0x140001d3a  test    byte ptr [rcx+0Ah], 5
0x140001d3e  jz      loc_140001F44
0x140001d44  mov     r14, [rcx+18h]
0x140001d48  test    r14, r14
0x140001d4b  jz      loc_140001E14
0x140001d51  cmp     [rsp+170h+var_110], 2
0x140001d57  mov     ebx, [rbx+10h]
0x140001d5a  jnz     loc_140001F6D
0x140001d60  cmp     edi, 14h
0x140001d63  jb      loc_140001EA6
0x140001d69  mov     eax, [rbx+r14+10h]
0x140001d6e  mov     ecx, eax
0x140001d70  and     ecx, 0F0h
0x140001d76  cmp     ecx, 0E0h
0x140001d7c  jz      loc_140001E9C
0x140001d82  cmp     eax, 0FFFFFFFFh
0x140001d85  jz      loc_140001F3A
0x140001d8b  test    eax, eax
0x140001d8d  jz      loc_140001F33
0x140001d93  test    al, al
0x140001d95  jnz     loc_140001F1B
0x140001d9b  mov     eax, 5
0x140001da0  mov     ebx, 1
0x140001da5  cmp     eax, 1
0x140001da8  jnz     loc_140001E63
0x140001dae  lea     rcx, [rsp+170h+var_110]
0x140001db3  mov     [rbp+70h+var_D8], r15
0x140001db7  call    SlbNatIpsHandleIncomingUnicastDatagram
0x140001dbc  test    rsi, rsi
0x140001dbf  jnz     short loc_140001E20
0x140001dc1  mov     rcx, [rbp+70h+var_90]
0x140001dc5  test    rcx, rcx
0x140001dc8  jnz     loc_140001EB0
0x140001dce  mov     rax, qword ptr [rbp+70h+var_80]
0x140001dd2  test    rax, rax
0x140001dd5  jnz     loc_140002089
0x140001ddb  mov     rdx, [rbp+70h+var_A0]
0x140001ddf  test    rdx, rdx
0x140001de2  jnz     short loc_140001E4E
0x140001de4  mov     rax, [rbp+70h+var_C0]
0x140001de8  test    rax, rax
0x140001deb  jnz     short loc_140001E28
0x140001ded  add     rsp, 138h
0x140001df4  pop     r15
0x140001df6  pop     r14
0x140001df8  pop     r13
0x140001dfa  pop     r12
0x140001dfc  pop     rdi
0x140001dfd  pop     rsi
0x140001dfe  pop     rbx
0x140001dff  pop     rbp
0x140001e00  retn
0x140001e02  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140001e07  mov     edx, 1
0x140001e0c  xor     r8d, r8d
0x140001e0f  jmp     loc_140001D33
0x140001e14  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140001e19  jmp     loc_140001D51
0x140001e20  xor     r8d, r8d
0x140001e23  jmp     loc_140001D0A
0x140001e28  lea     rcx, [rax-8]
0x140001e2c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001e33  lock xadd [rcx], rax
0x140001e38  sub     rax, 1
0x140001e3c  jg      short loc_140001DED
0x140001e3e  test    rax, rax
0x140001e41  jnz     loc_1400020C3
0x140001e47  call    WinNatLibCleanupSession
0x140001e4c  jmp     short loc_140001DED
0x140001e4e  mov     rax, [rsp+170h+var_100]
0x140001e53  mov     rcx, [rsp+170h+var_108]
0x140001e58  mov     rax, [rax+68h]
0x140001e5c  call    _guard_dispatch_icall
0x140001e61  jmp     short loc_140001DE4
0x140001e63  cmp     cs:gAccount, 0
0x140001e6a  mov     qword ptr [rsp+170h+var_12F+7], r15
0x140001e6f  mov     qword ptr [rsp+170h+var_12F+0Fh], r15
0x140001e74  jnz     loc_140001FA9
0x140001e7a  mov     rax, [r13+18h]
0x140001e7e  lea     r8, [rsp+170h+var_130]
0x140001e83  mov     rdx, [rbp+70h+arg_8]
0x140001e8a  mov     rcx, [r13+10h]
0x140001e8e  mov     rax, [rax+28h]
0x140001e92  call    _guard_dispatch_icall
0x140001e97  jmp     loc_140001DBC
0x140001e9c  mov     eax, 3
0x140001ea1  jmp     loc_140001DA0
0x140001ea6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140001eab  jmp     loc_140001D69
0x140001eb0  cmp     [rbp+70h+var_A0], 0
0x140001eb5  jz      loc_140001FE6
0x140001ebb  test    [rsp+170h+var_10E], 2
0x140001ec0  jnz     loc_140001FF4
0x140001ec6  test    cs:byte_140026BED, 8
0x140001ecd  jnz     loc_140002003
0x140001ed3  cmp     cs:gAccount, 0
0x140001eda  mov     rax, [rbp+70h+var_88]
0x140001ede  mov     qword ptr [rsp+170h+var_12F+0Fh], rax
0x140001ee3  mov     qword ptr [rsp+170h+var_12F+7], rcx
0x140001ee8  jnz     loc_140001FC8
0x140001eee  mov     rcx, [rbp+70h+var_A0]
0x140001ef2  lea     r8, [rsp+170h+var_130]
0x140001ef7  mov     rax, [rsp+170h+var_100]
0x140001efc  xor     r9d, r9d
0x140001eff  mov     rdx, [rbp+70h+var_E0]
0x140001f03  mov     qword ptr [rsp+170h+BugCheckOnFailure], rcx
0x140001f08  mov     rcx, [rsp+170h+var_108]
0x140001f0d  mov     rax, [rax+30h]
0x140001f11  call    _guard_dispatch_icall
0x140001f16  jmp     loc_140001DCE
0x140001f1b  cmp     ecx, 0F0h
0x140001f21  jz      loc_140001D9B
0x140001f27  mov     ebx, 1
0x140001f2c  mov     eax, ebx
0x140001f2e  jmp     loc_140001DA5
0x140001f33  xor     eax, eax
0x140001f35  jmp     loc_140001DA0
0x140001f3a  mov     eax, 4
0x140001f3f  jmp     loc_140001DA0
0x140001f44  mov     [rsp+170h+Priority], 40000000h; Priority
0x140001f4c  xor     r9d, r9d; RequestedAddress
0x140001f4f  mov     [rsp+170h+BugCheckOnFailure], r8d; BugCheckOnFailure
0x140001f54  mov     r8d, edx; CacheType
0x140001f57  xor     edx, edx; AccessMode
0x140001f59  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140001f60  nop     dword ptr [rax+rax+00h]
0x140001f65  mov     r14, rax
0x140001f68  jmp     loc_140001D48
0x140001f6d  cmp     edi, 28h ; '('
0x140001f70  jnb     short loc_140001F77
0x140001f72  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140001f77  lea     rcx, [r14+18h]
0x140001f7b  add     rcx, rbx
0x140001f7e  call    Ipv6AddressType
0x140001f83  jmp     loc_140001DA0
0x140001f88  mov     rax, rsi
0x140001f8b  test    rsi, rsi
0x140001f8e  jz      loc_140001D0A
0x140001f94  lock inc cs:gNBLIndicate
0x140001f9c  mov     rax, [rax]
0x140001f9f  test    rax, rax
0x140001fa2  jnz     short loc_140001F94
0x140001fa4  jmp     loc_140001D0A
0x140001fa9  test    r12, r12
0x140001fac  jz      loc_140001E7A
0x140001fb2  lock inc cs:gNBLReturn
0x140001fba  mov     r12, [r12]
0x140001fbe  test    r12, r12
0x140001fc1  jnz     short loc_140001FB2
0x140001fc3  jmp     loc_140001E7A
0x140001fc8  test    rcx, rcx
0x140001fcb  jz      loc_140001EEE
0x140001fd1  lock inc cs:gNBLForward
0x140001fd9  mov     rcx, [rcx]
0x140001fdc  test    rcx, rcx
0x140001fdf  jnz     short loc_140001FD1
0x140001fe1  jmp     loc_140001EEE
0x140001fe6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140001feb  mov     rcx, [rbp+70h+var_90]
0x140001fef  jmp     loc_140001EBB
0x140001ff4  lea     rcx, [rsp+170h+var_110]
0x140001ff9  call    SlbNatIpsClientPendPackets
0x140001ffe  jmp     loc_140001DCE
0x140002003  cmp     [rsp+170h+var_110], 2
0x140002009  jnz     loc_140001ED3
0x14000200f  mov     rdx, [rbp+70h+var_A0]
0x140002013  lea     r8, [rbp+70h+var_60]
0x140002017  mov     rcx, [rsp+170h+var_108]
0x14000201c  xor     eax, eax
0x14000201e  mov     rax, [rsp+170h+var_100]
0x140002023  xorps   xmm0, xmm0
0x140002026  movups  xmmword ptr [rbp+70h+var_60], xmm0
0x14000202a  movups  xmmword ptr [rbp+70h+var_60+0Ch], xmm0
0x14000202e  mov     rax, [rax+70h]
0x140002032  call    _guard_dispatch_icall
0x140002037  test    [rsp+170h+var_10E], 1
0x14000203c  jnz     short loc_14000204D
0x14000203e  mov     rax, [rbp+70h+var_C0]
0x140002042  test    rax, rax
0x140002045  jz      short loc_14000204B
0x140002047  mov     ebx, [rax]
0x140002049  jmp     short loc_14000204D
0x14000204b  xor     ebx, ebx
0x14000204d  mov     rax, [rbp+70h+var_90]
0x140002051  mov     r9d, ebx
0x140002054  mov     r8, [rbp+70h+var_E8]
0x140002058  mov     edx, [rbp+70h+var_F0]
0x14000205b  mov     ecx, [rsp+170h+var_F8]
0x14000205f  mov     [rsp+170h+var_138], 0
0x140002067  mov     [rsp+170h+var_140], 0
0x14000206f  mov     qword ptr [rsp+170h+Priority], rax
0x140002074  mov     eax, [rbp+70h+var_60]
0x140002077  mov     [rsp+170h+BugCheckOnFailure], eax
0x14000207b  call    SlbNatIpsLogIPv4Datagram
0x140002080  mov     rcx, [rbp+70h+var_90]
0x140002084  jmp     loc_140001ED3
0x140002089  mov     qword ptr [rsp+170h+var_12F+7], rax
0x14000208e  lea     rcx, [rsp+170h+var_130]
0x140002093  mov     rax, qword ptr [rbp+70h+var_80+8]
0x140002097  mov     edx, 4
0x14000209c  mov     qword ptr [rsp+170h+var_12F+0Fh], rax
0x1400020a1  call    SlbNatAccountChain
0x1400020a6  mov     rax, [rsp+170h+var_100]
0x1400020ab  lea     rdx, [rsp+170h+var_130]
0x1400020b0  mov     rcx, [rsp+170h+var_108]
0x1400020b5  mov     rax, [rax+40h]
0x1400020b9  call    _guard_dispatch_icall
0x1400020be  jmp     loc_140001DDB
0x1400020c3  mov     ecx, 0Eh
0x1400020c8  int     29h; Win8: RtlFailFast(ecx)
0x1400020ca  jmp     loc_140001DED
```

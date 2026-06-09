# WinNatEnumerateAndCreateAddressPoolEntries

- ea: `0x14000fce8`
- end: `0x140010059`
- name: `WinNatEnumerateAndCreateAddressPoolEntries`
- size: `881`
- prototype: `NTSTATUS __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140010ec4`

## callees

- `0x14000caa0`
- `0x14000e4b0`
- `0x14000ee98`
- `0x14000f954`
- `0x14000fce8`
- `0x14001f320`
- `0x14001f980`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000fe42`
- `ntoskrnl!ExAllocatePool2` at `0x14000fe42`
- `NETIO!GetUnicastIpAddressTable` at `0x14000fdb5`
- `NETIO!GetUnicastIpAddressTable` at `0x14000fdb5`
- `NETIO!FreeMibTable` at `0x14001000a`
- `NETIO!FreeMibTable` at `0x140010048`
- `NETIO!FreeMibTable` at `0x14001000a`
- `NETIO!FreeMibTable` at `0x140010048`

## pseudocode

```c
NTSTATUS __fastcall WinNatEnumerateAndCreateAddressPoolEntries(__int64 a1, __int64 a2)
{
  PVOID *v4; // rcx
  _QWORD *v5; // r15
  unsigned __int16 *v6; // rsi
  unsigned __int16 v7; // r9
  unsigned __int16 v8; // r8
  NTSTATUS result; // eax
  int AddressPoolEntry; // edi
  __int64 v11; // rdx
  _OWORD *v12; // rcx
  _OWORD *v13; // rax
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm1
  __int64 Pool2; // rdx
  __int64 v23; // r8
  __int64 *v24; // rax
  __int64 v25; // r14
  PMIB_UNICASTIPADDRESS_TABLE v26; // rdx
  ULONG S_addr; // eax
  int v28; // ecx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  _WORD *v32; // rbx
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+20h] [rbp-E0h] BYREF
  PVOID P; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v35[540]; // [rsp+40h] [rbp-C0h] BYREF

  Table = 0;
  memset(v35, 0, 0x21Au);
  v4 = (PVOID *)qword_140027B08;
  v5 = (_QWORD *)(a1 + 528);
  v6 = (unsigned __int16 *)(a1 + 542);
  if ( qword_140027B08 == &qword_140027B08 )
  {
LABEL_8:
    result = GetUnicastIpAddressTable(2u, &Table);
    AddressPoolEntry = result;
    if ( result < 0 )
      return result;
    v11 = 4;
    v12 = v35;
    v13 = (_OWORD *)a1;
    do
    {
      v14 = v13[1];
      *v12 = *v13;
      v15 = v13[2];
      v12[1] = v14;
      v16 = v13[3];
      v12[2] = v15;
      v17 = v13[4];
      v12[3] = v16;
      v18 = v13[5];
      v12[4] = v17;
      v19 = v13[6];
      v12[5] = v18;
      v20 = v13[7];
      v13 += 8;
      v12[6] = v19;
      v12[7] = v20;
      v12 += 8;
      --v11;
    }
    while ( v11 );
    v21 = v13[1];
    *v12 = *v13;
    v12[1] = v21;
    Pool2 = ExAllocatePool2(64, 40, 1885425239);
    if ( !Pool2 )
    {
      if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          0,
          v23,
          L"Unspecified address tracker allocation failed");
      return -1073741670;
    }
    if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 320)) <= 1 )
      __fastfail(0xEu);
    *(_QWORD *)(Pool2 + 32) = a2;
    *(_QWORD *)(Pool2 + 16) = *v5;
    *(_WORD *)(Pool2 + 24) = *(_WORD *)(a1 + 540);
    *(_WORD *)(Pool2 + 26) = *v6;
    v24 = (__int64 *)qword_140027B10;
    if ( *(PVOID **)qword_140027B10 != &qword_140027B08 )
      __fastfail(3u);
    *(_QWORD *)Pool2 = &qword_140027B08;
    v25 = 0;
    *(_QWORD *)(Pool2 + 8) = v24;
    *v24 = Pool2;
    qword_140027B10 = Pool2;
    v26 = Table;
    if ( !Table->NumEntries )
    {
LABEL_42:
      FreeMibTable(v26);
      return AddressPoolEntry;
    }
    while ( 1 )
    {
      S_addr = v26->Table[v25].Address.Ipv4.sin_addr.S_un.S_addr;
      if ( S_addr == -1 )
        goto LABEL_41;
      if ( (S_addr & 0xF0) == 0xE0 )
      {
        if ( (S_addr & 0xFFFFFF) == 0xE0 )
          goto LABEL_33;
        if ( (_WORD)S_addr == 0xFFEF )
        {
          v28 = 4;
        }
        else
        {
          v28 = 14;
          if ( (_BYTE)S_addr == 0xEF )
            v28 = 5;
        }
      }
      else
      {
        LODWORD(P) = 0;
        if ( (_WORD)S_addr == 0xFEA9 || (v28 = 14, (_BYTE)S_addr == 127) )
LABEL_33:
          v28 = 2;
      }
      if ( v28 == 14 && v26->Table[v25].InterfaceLuid.Value == *v5 && v26->Table[v25].DadState >= NldsDeprecated )
      {
        P = 0;
        *(_DWORD *)&v35[536] = S_addr;
        AddressPoolEntry = WinNatCreateAddressPoolEntry((__int64)v35, a2, (__int64 *)&P, 1);
        if ( AddressPoolEntry < 0 )
        {
          FreeMibTable(Table);
          return -1073741670;
        }
        v32 = P;
        if ( !P )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v30, v29, v31);
        v32[29] = *v6;
        v32[28] = *(_WORD *)(a1 + 540);
        WinNatDereferenceAddressPoolEntry(v32);
        v26 = Table;
      }
LABEL_41:
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= v26->NumEntries )
        goto LABEL_42;
    }
  }
  while ( 1 )
  {
    if ( v4[2] == (PVOID)*v5 )
    {
      v7 = *(_WORD *)(a1 + 540);
      v8 = *((_WORD *)v4 + 12);
      if ( v8 == v7 && *((_WORD *)v4 + 13) == *v6 )
        return a2 != (_QWORD)v4[4] ? 0xC000022A : 0;
      if ( *((_WORD *)v4 + 13) >= v7 && v8 <= *v6 )
        return -1073741811;
    }
    v4 = (PVOID *)*v4;
    if ( v4 == &qword_140027B08 )
      goto LABEL_8;
  }
}

```

## disassembly

```asm
0x14000fce8  mov     [rsp-8+arg_10], rbx
0x14000fced  push    rbp
0x14000fcee  push    rsi
0x14000fcef  push    rdi
0x14000fcf0  push    r12
0x14000fcf2  push    r13
0x14000fcf4  push    r14
0x14000fcf6  push    r15
0x14000fcf8  lea     rbp, [rsp-170h]
0x14000fd00  sub     rsp, 270h
0x14000fd07  mov     rax, cs:__security_cookie
0x14000fd0e  xor     rax, rsp
0x14000fd11  mov     [rbp+1A0h+var_40], rax
0x14000fd18  xor     eax, eax
0x14000fd1a  mov     [rsp+2A0h+Table], 0
0x14000fd23  mov     r12, rdx
0x14000fd26  mov     [rbp+1A0h+var_56], eax
0x14000fd2c  mov     r13, rcx
0x14000fd2f  mov     [rbp+1A0h+var_52], ax
0x14000fd36  xor     edx, edx; Val
0x14000fd38  lea     rcx, [rsp+2A0h+var_260]; void *
0x14000fd3d  mov     r8d, 21Ah; Size
0x14000fd43  call    memset
0x14000fd48  mov     rcx, cs:qword_140027B08
0x14000fd4f  lea     rbx, qword_140027B08
0x14000fd56  lea     r15, [r13+210h]
0x14000fd5d  lea     rsi, [r13+21Eh]
0x14000fd64  cmp     rcx, rbx
0x14000fd67  jz      short loc_14000FDAB
0x14000fd69  mov     r10, [r15]
0x14000fd6c  cmp     [rcx+10h], r10
0x14000fd70  jnz     short loc_14000FDA3
0x14000fd72  movzx   r9d, word ptr [r13+21Ch]
0x14000fd7a  movzx   r8d, word ptr [rcx+18h]
0x14000fd7f  cmp     r8w, r9w
0x14000fd83  jnz     short loc_14000FD92
0x14000fd85  movzx   eax, word ptr [rsi]
0x14000fd88  cmp     [rcx+1Ah], ax
0x14000fd8c  jz      loc_14000FE85
0x14000fd92  cmp     [rcx+1Ah], r9w
0x14000fd97  jb      short loc_14000FDA3
0x14000fd99  cmp     r8w, [rsi]
0x14000fd9d  jbe     loc_14000FE9B
0x14000fda3  mov     rcx, [rcx]
0x14000fda6  cmp     rcx, rbx
0x14000fda9  jnz     short loc_14000FD6C
0x14000fdab  mov     ecx, 2; Family
0x14000fdb0  lea     rdx, [rsp+2A0h+Table]; Table
0x14000fdb5  call    cs:__imp_GetUnicastIpAddressTable
0x14000fdbc  nop     dword ptr [rax+rax+00h]
0x14000fdc1  mov     edi, eax
0x14000fdc3  test    eax, eax
0x14000fdc5  js      loc_140010018
0x14000fdcb  mov     edx, 4
0x14000fdd0  lea     rcx, [rsp+2A0h+var_260]
0x14000fdd5  mov     rax, r13
0x14000fdd8  lea     r8d, [rdx+7Ch]
0x14000fddc  movups  xmm0, xmmword ptr [rax]
0x14000fddf  movups  xmm1, xmmword ptr [rax+10h]
0x14000fde3  movups  xmmword ptr [rcx], xmm0
0x14000fde6  movups  xmm0, xmmword ptr [rax+20h]
0x14000fdea  movups  xmmword ptr [rcx+10h], xmm1
0x14000fdee  movups  xmm1, xmmword ptr [rax+30h]
0x14000fdf2  movups  xmmword ptr [rcx+20h], xmm0
0x14000fdf6  movups  xmm0, xmmword ptr [rax+40h]
0x14000fdfa  movups  xmmword ptr [rcx+30h], xmm1
0x14000fdfe  movups  xmm1, xmmword ptr [rax+50h]
0x14000fe02  movups  xmmword ptr [rcx+40h], xmm0
0x14000fe06  movups  xmm0, xmmword ptr [rax+60h]
0x14000fe0a  movups  xmmword ptr [rcx+50h], xmm1
0x14000fe0e  movups  xmm1, xmmword ptr [rax+70h]
0x14000fe12  add     rax, r8
0x14000fe15  movups  xmmword ptr [rcx+60h], xmm0
0x14000fe19  movups  xmmword ptr [rcx+70h], xmm1
0x14000fe1d  add     rcx, r8
0x14000fe20  sub     rdx, 1
0x14000fe24  jnz     short loc_14000FDDC
0x14000fe26  movups  xmm0, xmmword ptr [rax]
0x14000fe29  mov     edx, 28h ; '('
0x14000fe2e  mov     r8d, 70614E57h
0x14000fe34  movups  xmm1, xmmword ptr [rax+10h]
0x14000fe38  movups  xmmword ptr [rcx], xmm0
0x14000fe3b  movups  xmmword ptr [rcx+10h], xmm1
0x14000fe3f  lea     ecx, [rdx+18h]
0x14000fe42  call    cs:__imp_ExAllocatePool2
0x14000fe49  nop     dword ptr [rax+rax+00h]
0x14000fe4e  mov     rdx, rax
0x14000fe51  test    rax, rax
0x14000fe54  jnz     short loc_14000FEA5
0x14000fe56  cmp     cs:dword_140027104, 1
0x14000fe5d  jnz     short loc_14000FE7B
0x14000fe5f  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14000fe66  jz      short loc_14000FE7B
0x14000fe68  lea     r9, aUnspecifiedAdd; "Unspecified address tracker allocation "...
0x14000fe6f  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000fe76  call    McTemplateK0z_EtwWriteTransfer
0x14000fe7b  mov     eax, 0C000009Ah
0x14000fe80  jmp     loc_140010018
0x14000fe85  mov     rax, [rcx+20h]
0x14000fe89  sub     rax, r12
0x14000fe8c  neg     rax
0x14000fe8f  sbb     eax, eax
0x14000fe91  and     eax, 0C000022Ah
0x14000fe96  jmp     loc_140010018
0x14000fe9b  mov     eax, 0C000000Dh
0x14000fea0  jmp     loc_140010018
0x14000fea5  mov     eax, 1
0x14000feaa  lock xadd [r12+140h], rax
0x14000feb4  inc     rax
0x14000feb7  cmp     rax, 1
0x14000febb  jg      short loc_14000FEC4
0x14000febd  mov     ecx, 0Eh
0x14000fec2  int     29h; Win8: RtlFailFast(ecx)
0x14000fec4  mov     [rdx+20h], r12
0x14000fec8  mov     rax, [r15]
0x14000fecb  mov     [rdx+10h], rax
0x14000fecf  movzx   eax, word ptr [r13+21Ch]
0x14000fed7  mov     [rdx+18h], ax
0x14000fedb  movzx   eax, word ptr [rsi]
0x14000fede  mov     [rdx+1Ah], ax
0x14000fee2  mov     rax, cs:qword_140027B10
0x14000fee9  cmp     [rax], rbx
0x14000feec  jz      short loc_14000FEF5
0x14000feee  mov     ecx, 3
0x14000fef3  int     29h; Win8: RtlFailFast(ecx)
0x14000fef5  mov     [rdx], rbx
0x14000fef8  xor     r14d, r14d
0x14000fefb  mov     [rdx+8], rax
0x14000feff  mov     [rax], rdx
0x14000ff02  mov     cs:qword_140027B10, rdx
0x14000ff09  mov     rdx, [rsp+2A0h+Table]
0x14000ff0e  cmp     [rdx], r14d
0x14000ff11  jbe     loc_140010007
0x14000ff17  lea     r9, [r14+r14*4]
0x14000ff1b  add     r9, r9
0x14000ff1e  mov     eax, [rdx+r9*8+0Ch]
0x14000ff23  cmp     eax, 0FFFFFFFFh
0x14000ff26  jz      loc_14000FFFB
0x14000ff2c  mov     ecx, eax
0x14000ff2e  and     ecx, 0F0h
0x14000ff34  cmp     cl, 0E0h
0x14000ff37  jnz     short loc_14000FF67
0x14000ff39  mov     ecx, eax
0x14000ff3b  and     ecx, 0FFFFFFh
0x14000ff41  cmp     ecx, 0E0h
0x14000ff47  jz      short loc_14000FF86
0x14000ff49  cmp     ax, 0FFEFh
0x14000ff4d  jnz     short loc_14000FF56
0x14000ff4f  mov     ecx, 4
0x14000ff54  jmp     short loc_14000FF8B
0x14000ff56  mov     ecx, 0Eh
0x14000ff5b  cmp     al, 0EFh
0x14000ff5d  lea     r8d, [rcx-9]
0x14000ff61  cmovz   ecx, r8d
0x14000ff65  jmp     short loc_14000FF8B
0x14000ff67  mov     dword ptr [rsp+2A0h+P], 0
0x14000ff6f  lea     rcx, [rsp+2A0h+var_270]
0x14000ff74  mov     r8b, al
0x14000ff77  cmp     ax, 0FEA9h
0x14000ff7b  jz      short loc_14000FF86
0x14000ff7d  mov     ecx, 0Eh
0x14000ff82  cmp     al, 7Fh
0x14000ff84  jnz     short loc_14000FF8B
0x14000ff86  mov     ecx, 2
0x14000ff8b  cmp     ecx, 0Eh
0x14000ff8e  jnz     short loc_14000FFFB
0x14000ff90  mov     rcx, [r15]
0x14000ff93  cmp     [rdx+r9*8+28h], rcx
0x14000ff98  jnz     short loc_14000FFFB
0x14000ff9a  cmp     dword ptr [rdx+r9*8+48h], 3
0x14000ffa0  jl      short loc_14000FFFB
0x14000ffa2  mov     r9b, 1
0x14000ffa5  mov     [rsp+2A0h+P], 0
0x14000ffae  lea     r8, [rsp+2A0h+P]
0x14000ffb3  mov     [rbp+1A0h+var_48], eax
0x14000ffb9  mov     rdx, r12
0x14000ffbc  lea     rcx, [rsp+2A0h+var_260]
0x14000ffc1  call    WinNatCreateAddressPoolEntry
0x14000ffc6  mov     edi, eax
0x14000ffc8  test    eax, eax
0x14000ffca  js      short loc_140010043
0x14000ffcc  mov     rbx, [rsp+2A0h+P]
0x14000ffd1  test    rbx, rbx
0x14000ffd4  jnz     short loc_14000FFDB
0x14000ffd6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000ffdb  movzx   eax, word ptr [rsi]
0x14000ffde  mov     rcx, rbx; P
0x14000ffe1  mov     [rbx+3Ah], ax
0x14000ffe5  movzx   eax, word ptr [r13+21Ch]
0x14000ffed  mov     [rbx+38h], ax
0x14000fff1  call    WinNatDereferenceAddressPoolEntry
0x14000fff6  mov     rdx, [rsp+2A0h+Table]
0x14000fffb  inc     r14d
0x14000fffe  cmp     r14d, [rdx]
0x140010001  jb      loc_14000FF17
0x140010007  mov     rcx, rdx; Memory
0x14001000a  call    cs:__imp_FreeMibTable
0x140010011  nop     dword ptr [rax+rax+00h]
0x140010016  mov     eax, edi
0x140010018  mov     rcx, [rbp+1A0h+var_40]
0x14001001f  xor     rcx, rsp; StackCookie
0x140010022  call    __security_check_cookie
0x140010027  mov     rbx, [rsp+2A0h+arg_10]
0x14001002f  add     rsp, 270h
0x140010036  pop     r15
0x140010038  pop     r14
0x14001003a  pop     r13
0x14001003c  pop     r12
0x14001003e  pop     rdi
0x14001003f  pop     rsi
0x140010040  pop     rbp
0x140010041  retn
0x140010043  mov     rcx, [rsp+2A0h+Table]; Memory
0x140010048  call    cs:__imp_FreeMibTable
0x14001004f  nop     dword ptr [rax+rax+00h]
0x140010054  jmp     loc_14000FE7B
```

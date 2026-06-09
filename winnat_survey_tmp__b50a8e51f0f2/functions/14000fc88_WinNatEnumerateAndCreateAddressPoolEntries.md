# WinNatEnumerateAndCreateAddressPoolEntries

- ea: `0x14000fc88`
- end: `0x14000fff9`
- name: `WinNatEnumerateAndCreateAddressPoolEntries`
- size: `881`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140010e64`

## callees

- `0x14000caa0`
- `0x14000e488`
- `0x14000ee40`
- `0x14000f8fc`
- `0x14000fc88`
- `0x14001ede0`
- `0x14001f440`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000fde2`
- `ntoskrnl!ExAllocatePool2` at `0x14000fde2`
- `NETIO!GetUnicastIpAddressTable` at `0x14000fd55`
- `NETIO!GetUnicastIpAddressTable` at `0x14000fd55`
- `NETIO!FreeMibTable` at `0x14000ffaa`
- `NETIO!FreeMibTable` at `0x14000ffe8`
- `NETIO!FreeMibTable` at `0x14000ffaa`
- `NETIO!FreeMibTable` at `0x14000ffe8`

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
  _WORD *v31; // rbx
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+20h] [rbp-E0h] BYREF
  PVOID P; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v34[540]; // [rsp+40h] [rbp-C0h] BYREF

  Table = 0;
  memset(v34, 0, 0x21Au);
  v4 = (PVOID *)qword_140026B08;
  v5 = (_QWORD *)(a1 + 528);
  v6 = (unsigned __int16 *)(a1 + 542);
  if ( qword_140026B08 == &qword_140026B08 )
  {
LABEL_8:
    result = GetUnicastIpAddressTable(2u, &Table);
    AddressPoolEntry = result;
    if ( result < 0 )
      return result;
    v11 = 4;
    v12 = v34;
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
      if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
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
    v24 = (__int64 *)qword_140026B10;
    if ( *(PVOID **)qword_140026B10 != &qword_140026B08 )
      __fastfail(3u);
    *(_QWORD *)Pool2 = &qword_140026B08;
    v25 = 0;
    *(_QWORD *)(Pool2 + 8) = v24;
    *v24 = Pool2;
    qword_140026B10 = Pool2;
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
        *(_DWORD *)&v34[536] = S_addr;
        AddressPoolEntry = WinNatCreateAddressPoolEntry((__int64)v34, a2, (__int64 *)&P, 1);
        if ( AddressPoolEntry < 0 )
        {
          FreeMibTable(Table);
          return -1073741670;
        }
        v31 = P;
        if ( !P )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v30, v29);
        v31[29] = *v6;
        v31[28] = *(_WORD *)(a1 + 540);
        WinNatDereferenceAddressPoolEntry(v31);
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
    if ( v4 == &qword_140026B08 )
      goto LABEL_8;
  }
}

```

## disassembly

```asm
0x14000fc88  mov     [rsp-8+arg_10], rbx
0x14000fc8d  push    rbp
0x14000fc8e  push    rsi
0x14000fc8f  push    rdi
0x14000fc90  push    r12
0x14000fc92  push    r13
0x14000fc94  push    r14
0x14000fc96  push    r15
0x14000fc98  lea     rbp, [rsp-170h]
0x14000fca0  sub     rsp, 270h
0x14000fca7  mov     rax, cs:__security_cookie
0x14000fcae  xor     rax, rsp
0x14000fcb1  mov     [rbp+1A0h+var_40], rax
0x14000fcb8  xor     eax, eax
0x14000fcba  mov     [rsp+2A0h+Table], 0
0x14000fcc3  mov     r12, rdx
0x14000fcc6  mov     [rbp+1A0h+var_56], eax
0x14000fccc  mov     r13, rcx
0x14000fccf  mov     [rbp+1A0h+var_52], ax
0x14000fcd6  xor     edx, edx; Val
0x14000fcd8  lea     rcx, [rsp+2A0h+var_260]; void *
0x14000fcdd  mov     r8d, 21Ah; Size
0x14000fce3  call    memset
0x14000fce8  mov     rcx, cs:qword_140026B08
0x14000fcef  lea     rbx, qword_140026B08
0x14000fcf6  lea     r15, [r13+210h]
0x14000fcfd  lea     rsi, [r13+21Eh]
0x14000fd04  cmp     rcx, rbx
0x14000fd07  jz      short loc_14000FD4B
0x14000fd09  mov     r10, [r15]
0x14000fd0c  cmp     [rcx+10h], r10
0x14000fd10  jnz     short loc_14000FD43
0x14000fd12  movzx   r9d, word ptr [r13+21Ch]
0x14000fd1a  movzx   r8d, word ptr [rcx+18h]
0x14000fd1f  cmp     r8w, r9w
0x14000fd23  jnz     short loc_14000FD32
0x14000fd25  movzx   eax, word ptr [rsi]
0x14000fd28  cmp     [rcx+1Ah], ax
0x14000fd2c  jz      loc_14000FE25
0x14000fd32  cmp     [rcx+1Ah], r9w
0x14000fd37  jb      short loc_14000FD43
0x14000fd39  cmp     r8w, [rsi]
0x14000fd3d  jbe     loc_14000FE3B
0x14000fd43  mov     rcx, [rcx]
0x14000fd46  cmp     rcx, rbx
0x14000fd49  jnz     short loc_14000FD0C
0x14000fd4b  mov     ecx, 2; Family
0x14000fd50  lea     rdx, [rsp+2A0h+Table]; Table
0x14000fd55  call    cs:__imp_GetUnicastIpAddressTable
0x14000fd5c  nop     dword ptr [rax+rax+00h]
0x14000fd61  mov     edi, eax
0x14000fd63  test    eax, eax
0x14000fd65  js      loc_14000FFB8
0x14000fd6b  mov     edx, 4
0x14000fd70  lea     rcx, [rsp+2A0h+var_260]
0x14000fd75  mov     rax, r13
0x14000fd78  lea     r8d, [rdx+7Ch]
0x14000fd7c  movups  xmm0, xmmword ptr [rax]
0x14000fd7f  movups  xmm1, xmmword ptr [rax+10h]
0x14000fd83  movups  xmmword ptr [rcx], xmm0
0x14000fd86  movups  xmm0, xmmword ptr [rax+20h]
0x14000fd8a  movups  xmmword ptr [rcx+10h], xmm1
0x14000fd8e  movups  xmm1, xmmword ptr [rax+30h]
0x14000fd92  movups  xmmword ptr [rcx+20h], xmm0
0x14000fd96  movups  xmm0, xmmword ptr [rax+40h]
0x14000fd9a  movups  xmmword ptr [rcx+30h], xmm1
0x14000fd9e  movups  xmm1, xmmword ptr [rax+50h]
0x14000fda2  movups  xmmword ptr [rcx+40h], xmm0
0x14000fda6  movups  xmm0, xmmword ptr [rax+60h]
0x14000fdaa  movups  xmmword ptr [rcx+50h], xmm1
0x14000fdae  movups  xmm1, xmmword ptr [rax+70h]
0x14000fdb2  add     rax, r8
0x14000fdb5  movups  xmmword ptr [rcx+60h], xmm0
0x14000fdb9  movups  xmmword ptr [rcx+70h], xmm1
0x14000fdbd  add     rcx, r8
0x14000fdc0  sub     rdx, 1
0x14000fdc4  jnz     short loc_14000FD7C
0x14000fdc6  movups  xmm0, xmmword ptr [rax]
0x14000fdc9  mov     edx, 28h ; '('
0x14000fdce  mov     r8d, 70614E57h
0x14000fdd4  movups  xmm1, xmmword ptr [rax+10h]
0x14000fdd8  movups  xmmword ptr [rcx], xmm0
0x14000fddb  movups  xmmword ptr [rcx+10h], xmm1
0x14000fddf  lea     ecx, [rdx+18h]
0x14000fde2  call    cs:__imp_ExAllocatePool2
0x14000fde9  nop     dword ptr [rax+rax+00h]
0x14000fdee  mov     rdx, rax
0x14000fdf1  test    rax, rax
0x14000fdf4  jnz     short loc_14000FE45
0x14000fdf6  cmp     cs:dword_140026104, 1
0x14000fdfd  jnz     short loc_14000FE1B
0x14000fdff  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14000fe06  jz      short loc_14000FE1B
0x14000fe08  lea     r9, aUnspecifiedAdd; "Unspecified address tracker allocation "...
0x14000fe0f  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000fe16  call    McTemplateK0z_EtwWriteTransfer
0x14000fe1b  mov     eax, 0C000009Ah
0x14000fe20  jmp     loc_14000FFB8
0x14000fe25  mov     rax, [rcx+20h]
0x14000fe29  sub     rax, r12
0x14000fe2c  neg     rax
0x14000fe2f  sbb     eax, eax
0x14000fe31  and     eax, 0C000022Ah
0x14000fe36  jmp     loc_14000FFB8
0x14000fe3b  mov     eax, 0C000000Dh
0x14000fe40  jmp     loc_14000FFB8
0x14000fe45  mov     eax, 1
0x14000fe4a  lock xadd [r12+140h], rax
0x14000fe54  inc     rax
0x14000fe57  cmp     rax, 1
0x14000fe5b  jg      short loc_14000FE64
0x14000fe5d  mov     ecx, 0Eh
0x14000fe62  int     29h; Win8: RtlFailFast(ecx)
0x14000fe64  mov     [rdx+20h], r12
0x14000fe68  mov     rax, [r15]
0x14000fe6b  mov     [rdx+10h], rax
0x14000fe6f  movzx   eax, word ptr [r13+21Ch]
0x14000fe77  mov     [rdx+18h], ax
0x14000fe7b  movzx   eax, word ptr [rsi]
0x14000fe7e  mov     [rdx+1Ah], ax
0x14000fe82  mov     rax, cs:qword_140026B10
0x14000fe89  cmp     [rax], rbx
0x14000fe8c  jz      short loc_14000FE95
0x14000fe8e  mov     ecx, 3
0x14000fe93  int     29h; Win8: RtlFailFast(ecx)
0x14000fe95  mov     [rdx], rbx
0x14000fe98  xor     r14d, r14d
0x14000fe9b  mov     [rdx+8], rax
0x14000fe9f  mov     [rax], rdx
0x14000fea2  mov     cs:qword_140026B10, rdx
0x14000fea9  mov     rdx, [rsp+2A0h+Table]
0x14000feae  cmp     [rdx], r14d
0x14000feb1  jbe     loc_14000FFA7
0x14000feb7  lea     r9, [r14+r14*4]
0x14000febb  add     r9, r9
0x14000febe  mov     eax, [rdx+r9*8+0Ch]
0x14000fec3  cmp     eax, 0FFFFFFFFh
0x14000fec6  jz      loc_14000FF9B
0x14000fecc  mov     ecx, eax
0x14000fece  and     ecx, 0F0h
0x14000fed4  cmp     cl, 0E0h
0x14000fed7  jnz     short loc_14000FF07
0x14000fed9  mov     ecx, eax
0x14000fedb  and     ecx, 0FFFFFFh
0x14000fee1  cmp     ecx, 0E0h
0x14000fee7  jz      short loc_14000FF26
0x14000fee9  cmp     ax, 0FFEFh
0x14000feed  jnz     short loc_14000FEF6
0x14000feef  mov     ecx, 4
0x14000fef4  jmp     short loc_14000FF2B
0x14000fef6  mov     ecx, 0Eh
0x14000fefb  cmp     al, 0EFh
0x14000fefd  lea     r8d, [rcx-9]
0x14000ff01  cmovz   ecx, r8d
0x14000ff05  jmp     short loc_14000FF2B
0x14000ff07  mov     dword ptr [rsp+2A0h+P], 0
0x14000ff0f  lea     rcx, [rsp+2A0h+var_270]
0x14000ff14  mov     r8b, al
0x14000ff17  cmp     ax, 0FEA9h
0x14000ff1b  jz      short loc_14000FF26
0x14000ff1d  mov     ecx, 0Eh
0x14000ff22  cmp     al, 7Fh
0x14000ff24  jnz     short loc_14000FF2B
0x14000ff26  mov     ecx, 2
0x14000ff2b  cmp     ecx, 0Eh
0x14000ff2e  jnz     short loc_14000FF9B
0x14000ff30  mov     rcx, [r15]
0x14000ff33  cmp     [rdx+r9*8+28h], rcx
0x14000ff38  jnz     short loc_14000FF9B
0x14000ff3a  cmp     dword ptr [rdx+r9*8+48h], 3
0x14000ff40  jl      short loc_14000FF9B
0x14000ff42  mov     r9b, 1
0x14000ff45  mov     [rsp+2A0h+P], 0
0x14000ff4e  lea     r8, [rsp+2A0h+P]
0x14000ff53  mov     [rbp+1A0h+var_48], eax
0x14000ff59  mov     rdx, r12
0x14000ff5c  lea     rcx, [rsp+2A0h+var_260]
0x14000ff61  call    WinNatCreateAddressPoolEntry
0x14000ff66  mov     edi, eax
0x14000ff68  test    eax, eax
0x14000ff6a  js      short loc_14000FFE3
0x14000ff6c  mov     rbx, [rsp+2A0h+P]
0x14000ff71  test    rbx, rbx
0x14000ff74  jnz     short loc_14000FF7B
0x14000ff76  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000ff7b  movzx   eax, word ptr [rsi]
0x14000ff7e  mov     rcx, rbx; P
0x14000ff81  mov     [rbx+3Ah], ax
0x14000ff85  movzx   eax, word ptr [r13+21Ch]
0x14000ff8d  mov     [rbx+38h], ax
0x14000ff91  call    WinNatDereferenceAddressPoolEntry
0x14000ff96  mov     rdx, [rsp+2A0h+Table]
0x14000ff9b  inc     r14d
0x14000ff9e  cmp     r14d, [rdx]
0x14000ffa1  jb      loc_14000FEB7
0x14000ffa7  mov     rcx, rdx; Memory
0x14000ffaa  call    cs:__imp_FreeMibTable
0x14000ffb1  nop     dword ptr [rax+rax+00h]
0x14000ffb6  mov     eax, edi
0x14000ffb8  mov     rcx, [rbp+1A0h+var_40]
0x14000ffbf  xor     rcx, rsp; StackCookie
0x14000ffc2  call    __security_check_cookie
0x14000ffc7  mov     rbx, [rsp+2A0h+arg_10]
0x14000ffcf  add     rsp, 270h
0x14000ffd6  pop     r15
0x14000ffd8  pop     r14
0x14000ffda  pop     r13
0x14000ffdc  pop     r12
0x14000ffde  pop     rdi
0x14000ffdf  pop     rsi
0x14000ffe0  pop     rbp
0x14000ffe1  retn
0x14000ffe3  mov     rcx, [rsp+2A0h+Table]; Memory
0x14000ffe8  call    cs:__imp_FreeMibTable
0x14000ffef  nop     dword ptr [rax+rax+00h]
0x14000fff4  jmp     loc_14000FE1B
```

# SrvNetUpdateQuicEndpointsOnInterface

- ea: `0x14001b0d0`
- end: `0x14001b36a`
- name: `SrvNetUpdateQuicEndpointsOnInterface`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14001aff0`

## callees

- `0x140007360`
- `0x140007c60`
- `0x140007f34`
- `0x140008bb0`
- `0x14001389c`
- `0x14001b0d0`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001b1c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b1c5`
- `NETIO!FreeMibTable` at `0x14001b348`
- `NETIO!FreeMibTable` at `0x14001b348`
- `NETIO!GetUnicastIpAddressTable` at `0x14001b25b`
- `NETIO!GetUnicastIpAddressTable` at `0x14001b25b`

## pseudocode

```c
void __fastcall SrvNetUpdateQuicEndpointsOnInterface(unsigned int a1)
{
  char *v2; // r10
  char *v3; // r8
  char *v4; // rcx
  unsigned int i; // r9d
  char *v6; // rdx
  char *PoolWithTag; // rax
  int v8; // ecx
  char *v9; // rsi
  char *v10; // rbx
  __int64 v11; // r8
  unsigned int *v12; // rbx
  _BYTE *v13; // r8
  NTSTATUS UnicastIpAddressTable; // esi
  __int64 v15; // r8
  int v16; // ecx
  PMIB_UNICASTIPADDRESS_TABLE v17; // rcx
  ULONG j; // esi
  char *v19; // r9
  __int16 v20; // ax
  bool v21; // al
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+78h] [rbp+10h] BYREF

  v2 = 0;
  Table = 0;
  v3 = 0;
  if ( a1 >= SrvNetInterfaces
    || (v4 = (char *)Src + 32 * a1, !v4[29])
    || *(_DWORD *)v4 != a1
    || (v2 = (char *)Src + 32 * a1, !v4) )
  {
    for ( i = 0; i < SrvNetInterfaces; ++i )
    {
      v6 = (char *)Src + 32 * i;
      if ( v6[29] )
      {
        if ( *(_DWORD *)v6 == a1 )
        {
          v2 = (char *)Src + 32 * i;
          break;
        }
      }
      else
      {
        if ( v3 )
          v6 = v3;
        v3 = v6;
      }
    }
  }
  if ( v2 )
    v3 = v2;
  if ( !v3 )
  {
    PoolWithTag = (char *)SrvNetAllocatePoolWithTag(
                            66,
                            (unsigned __int64)(unsigned int)SrvNetInterfaces << 6,
                            1717719884);
    v9 = PoolWithTag;
    if ( !PoolWithTag )
      goto LABEL_22;
    memmove(PoolWithTag, Src, 32LL * (unsigned int)SrvNetInterfaces);
    v10 = (char *)Src;
    if ( Src != qword_1400370B0 && Src )
    {
      SrvNetUpdateMemStatistics(*((_DWORD *)Src - 3), *((_DWORD *)Src - 4), 0);
      ExFreePoolWithTag(v10 - 16, 0);
    }
    v8 = SrvNetInterfaces;
    Src = v9;
    v11 = 32LL * (unsigned int)SrvNetInterfaces;
    SrvNetInterfaces *= 2;
    v3 = &v9[v11];
    if ( !v3 )
    {
LABEL_22:
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
        McTemplateK0qqdhzr3q_EtwWriteTransfer(
          v8,
          (unsigned int)SRVNET_EVENT_QUIC_SEND_ENDPOINT_NOTIFICATION_FAILURE,
          (_DWORD)v3,
          2,
          a1,
          0,
          0,
          0,
          0);
      return;
    }
  }
  v12 = (unsigned int *)v3;
  if ( *(_DWORD *)v3 == a1 )
  {
    v13 = v3 + 29;
    if ( *((_BYTE *)v12 + 29) )
      goto LABEL_29;
  }
  else
  {
    v13 = v3 + 29;
  }
  *v12 = a1;
  *((_BYTE *)v12 + 28) = 0;
  *(_QWORD *)(v12 + 5) = 0;
  *v13 = 1;
LABEL_29:
  UnicastIpAddressTable = GetUnicastIpAddressTable(0, &Table);
  if ( UnicastIpAddressTable >= 0 )
  {
    v17 = Table;
    for ( j = 0; j < v17->NumEntries; ++j )
    {
      if ( v17->Table[j].InterfaceIndex == a1 )
      {
        v19 = (char *)v17 + 80 * j;
        v20 = *((_WORD *)v19 + 4);
        v21 = v20 == 2 && v12[5] || v20 == 23 && v12[6];
        if ( !v21 || v17->Table[j].DadState != NldsPreferred || (LOBYTE(v15) = 1, !SrvNetEnableSmbQuic) )
          LOBYTE(v15) = 0;
        SrvNetSendQUICEndpointNotification(v19 + 8, a1, v15);
        v17 = Table;
      }
    }
    FreeMibTable(v17);
  }
  else
  {
    v16 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids,
        (unsigned int)UnicastIpAddressTable);
    }
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
      McTemplateK0qqdhzr3q_EtwWriteTransfer(
        v16,
        (unsigned int)SRVNET_EVENT_QUIC_SEND_ENDPOINT_NOTIFICATION_FAILURE,
        v15,
        0,
        a1,
        UnicastIpAddressTable,
        0,
        0,
        0);
  }
}

```

## disassembly

```asm
0x14001b0d0  mov     [rsp+arg_0], rbx
0x14001b0d5  mov     [rsp+arg_10], rbp
0x14001b0da  push    rsi
0x14001b0db  push    rdi
0x14001b0dc  push    r14
0x14001b0de  sub     rsp, 50h
0x14001b0e2  mov     r11d, cs:SrvNetInterfaces
0x14001b0e9  xor     r14d, r14d
0x14001b0ec  mov     edi, ecx
0x14001b0ee  mov     r10d, r14d
0x14001b0f1  mov     [rsp+68h+Table], r14
0x14001b0f6  mov     r8d, r14d
0x14001b0f9  cmp     ecx, r11d
0x14001b0fc  jnb     short loc_14001B11D
0x14001b0fe  mov     ecx, edi
0x14001b100  shl     rcx, 5
0x14001b104  add     rcx, cs:Src
0x14001b10b  cmp     [rcx+1Dh], r14b
0x14001b10f  jz      short loc_14001B11D
0x14001b111  cmp     [rcx], edi
0x14001b113  jnz     short loc_14001B11D
0x14001b115  mov     r10, rcx
0x14001b118  test    rcx, rcx
0x14001b11b  jnz     short loc_14001B151
0x14001b11d  mov     r9d, r14d
0x14001b120  cmp     r9d, r11d
0x14001b123  jnb     short loc_14001B151
0x14001b125  mov     edx, r9d
0x14001b128  shl     rdx, 5
0x14001b12c  add     rdx, cs:Src
0x14001b133  cmp     [rdx+1Dh], r14b
0x14001b137  jnz     short loc_14001B145
0x14001b139  test    r8, r8
0x14001b13c  cmovnz  rdx, r8
0x14001b140  mov     r8, rdx
0x14001b143  jmp     short loc_14001B149
0x14001b145  cmp     [rdx], edi
0x14001b147  jz      short loc_14001B14E
0x14001b149  inc     r9d
0x14001b14c  jmp     short loc_14001B120
0x14001b14e  mov     r10, rdx
0x14001b151  test    r10, r10
0x14001b154  cmovnz  r8, r10
0x14001b158  test    r8, r8
0x14001b15b  jnz     loc_14001B230
0x14001b161  mov     rdx, r11
0x14001b164  lea     ecx, [r8+42h]
0x14001b168  shl     rdx, 6
0x14001b16c  mov     r8d, 6662534Ch
0x14001b172  call    SrvNetAllocatePoolWithTag
0x14001b177  mov     rsi, rax
0x14001b17a  test    rax, rax
0x14001b17d  jz      short loc_14001B1F3
0x14001b17f  mov     r8d, cs:SrvNetInterfaces
0x14001b186  mov     rcx, rax; void *
0x14001b189  mov     rdx, cs:Src; Src
0x14001b190  shl     r8, 5; Size
0x14001b194  call    memmove
0x14001b199  mov     rbx, cs:Src
0x14001b1a0  lea     rax, qword_1400370B0
0x14001b1a7  cmp     rbx, rax
0x14001b1aa  jz      short loc_14001B1D1
0x14001b1ac  test    rbx, rbx
0x14001b1af  jz      short loc_14001B1D1
0x14001b1b1  mov     ecx, [rbx-0Ch]
0x14001b1b4  xor     r8d, r8d
0x14001b1b7  mov     edx, [rbx-10h]
0x14001b1ba  call    SrvNetUpdateMemStatistics
0x14001b1bf  xor     edx, edx; Tag
0x14001b1c1  lea     rcx, [rbx-10h]; P
0x14001b1c5  call    cs:__imp_ExFreePoolWithTag
0x14001b1cc  nop     dword ptr [rax+rax+00h]
0x14001b1d1  mov     ecx, cs:SrvNetInterfaces
0x14001b1d7  mov     r8d, ecx
0x14001b1da  mov     cs:Src, rsi
0x14001b1e1  shl     r8, 5
0x14001b1e5  lea     eax, [rcx+rcx]
0x14001b1e8  mov     cs:SrvNetInterfaces, eax
0x14001b1ee  add     r8, rsi
0x14001b1f1  jnz     short loc_14001B230
0x14001b1f3  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x14001b1fa  jz      loc_14001B354
0x14001b200  mov     [rsp+68h+var_28], r14d
0x14001b205  mov     r9d, 2
0x14001b20b  mov     [rsp+68h+var_30], r14
0x14001b210  mov     [rsp+68h+var_38], r14w
0x14001b216  mov     [rsp+68h+var_40], r14d
0x14001b21b  lea     rdx, SRVNET_EVENT_QUIC_SEND_ENDPOINT_NOTIFICATION_FAILURE
0x14001b222  mov     [rsp+68h+var_48], edi
0x14001b226  call    McTemplateK0qqdhzr3q_EtwWriteTransfer
0x14001b22b  jmp     loc_14001B354
0x14001b230  mov     rbx, r8
0x14001b233  cmp     [rbx], edi
0x14001b235  jnz     short loc_14001B242
0x14001b237  lea     r8, [rbx+1Dh]
0x14001b23b  cmp     [r8], r14b
0x14001b23e  jnz     short loc_14001B254
0x14001b240  jmp     short loc_14001B246
0x14001b242  add     r8, 1Dh
0x14001b246  mov     [rbx], edi
0x14001b248  mov     [rbx+1Ch], r14b
0x14001b24c  mov     [rbx+14h], r14
0x14001b250  mov     byte ptr [r8], 1
0x14001b254  xor     ecx, ecx; Family
0x14001b256  lea     rdx, [rsp+68h+Table]; Table
0x14001b25b  call    cs:__imp_GetUnicastIpAddressTable
0x14001b262  nop     dword ptr [rax+rax+00h]
0x14001b267  mov     esi, eax
0x14001b269  test    eax, eax
0x14001b26b  jns     short loc_14001B2D0
0x14001b26d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b274  lea     rax, WPP_GLOBAL_Control
0x14001b27b  cmp     rcx, rax
0x14001b27e  jz      short loc_14001B2A7
0x14001b280  test    dword ptr [rcx+2Ch], 200000h
0x14001b287  jz      short loc_14001B2A7
0x14001b289  cmp     byte ptr [rcx+29h], 1
0x14001b28d  jb      short loc_14001B2A7
0x14001b28f  mov     rcx, [rcx+18h]
0x14001b293  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x14001b29a  mov     edx, 1Ah
0x14001b29f  mov     r9d, esi
0x14001b2a2  call    WPP_SF_d
0x14001b2a7  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x14001b2ae  jz      loc_14001B354
0x14001b2b4  mov     [rsp+68h+var_28], r14d
0x14001b2b9  xor     r9d, r9d
0x14001b2bc  mov     [rsp+68h+var_30], r14
0x14001b2c1  mov     [rsp+68h+var_38], r14w
0x14001b2c7  mov     [rsp+68h+var_40], esi
0x14001b2cb  jmp     loc_14001B21B
0x14001b2d0  mov     rcx, [rsp+68h+Table]
0x14001b2d5  mov     esi, r14d
0x14001b2d8  cmp     [rcx], r14d
0x14001b2db  jbe     short loc_14001B348
0x14001b2dd  mov     ebp, 2
0x14001b2e2  mov     eax, esi
0x14001b2e4  lea     rdx, [rax+rax*4]
0x14001b2e8  add     rdx, rdx
0x14001b2eb  cmp     [rcx+rdx*8+30h], edi
0x14001b2ef  jnz     short loc_14001B342
0x14001b2f1  lea     r9, [rcx+rdx*8]
0x14001b2f5  movzx   eax, word ptr [r9+8]
0x14001b2fa  cmp     ax, bp
0x14001b2fd  jnz     short loc_14001B305
0x14001b2ff  cmp     [rbx+14h], r14d
0x14001b303  jnz     short loc_14001B311
0x14001b305  cmp     ax, 17h
0x14001b309  jnz     short loc_14001B315
0x14001b30b  cmp     [rbx+18h], r14d
0x14001b30f  jz      short loc_14001B315
0x14001b311  mov     al, 1
0x14001b313  jmp     short loc_14001B318
0x14001b315  mov     al, r14b
0x14001b318  test    al, al
0x14001b31a  jz      short loc_14001B32F
0x14001b31c  cmp     dword ptr [rcx+rdx*8+48h], 4
0x14001b321  jnz     short loc_14001B32F
0x14001b323  cmp     cs:SrvNetEnableSmbQuic, r14b
0x14001b32a  mov     r8b, 1
0x14001b32d  jnz     short loc_14001B332
0x14001b32f  mov     r8b, r14b
0x14001b332  mov     edx, edi
0x14001b334  lea     rcx, [r9+8]
0x14001b338  call    SrvNetSendQUICEndpointNotification
0x14001b33d  mov     rcx, [rsp+68h+Table]; Memory
0x14001b342  inc     esi
0x14001b344  cmp     esi, [rcx]
0x14001b346  jb      short loc_14001B2E2
0x14001b348  call    cs:__imp_FreeMibTable
0x14001b34f  nop     dword ptr [rax+rax+00h]
0x14001b354  lea     r11, [rsp+68h+var_18]
0x14001b359  mov     rbx, [r11+20h]
0x14001b35d  mov     rbp, [r11+30h]
0x14001b361  mov     rsp, r11
0x14001b364  pop     r14
0x14001b366  pop     rdi
0x14001b367  pop     rsi
0x14001b368  retn
```

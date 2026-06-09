# WinNatDeleteSessionEntryUnderLock

- ea: `0x14000ae68`
- end: `0x14000b218`
- name: `WinNatDeleteSessionEntryUnderLock`
- size: `944`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000a9d0`
- `0x14000c47c`
- `0x14001b0ac`
- `0x14001b50c`

## callees

- `0x14000ae68`
- `0x14000b220`
- `0x14000c990`
- `0x140018bf0`
- `0x140019be8`
- `0x14001aaa8`
- `0x14001ab70`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ae9a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ae9a`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14000aeba`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14000aed7`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14000aef4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14000aeba`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14000aed7`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14000aef4`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x14000af1b`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x14000af1b`

## pseudocode

```c
char __fastcall WinNatDeleteSessionEntryUnderLock(__int64 a1, __int64 a2)
{
  __int64 CurrentProcessorNumber; // r14
  int v5; // edx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // esi
  __int64 v10; // rcx
  int v11; // r8d
  char v12; // dl
  int v13; // ecx
  int v14; // r9d
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // edx
  _BYTE v19[8]; // [rsp+70h] [rbp-59h] BYREF
  _WORD v20[16]; // [rsp+78h] [rbp-51h] BYREF
  _WORD v21[16]; // [rsp+98h] [rbp-31h] BYREF
  _OWORD v22[2]; // [rsp+B8h] [rbp-11h] BYREF
  _OWORD v23[2]; // [rsp+D8h] [rbp+Fh] BYREF

  v19[0] = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  RtlRemoveEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a2 + 168), 0);
  RtlRemoveEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 392), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a2 + 192), 0);
  RtlRemoveEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 400), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a2 + 216), 0);
  if ( (*(_BYTE *)(a1 + 628) & 1) == 0 )
    RtlCleanupTimerWheelEntry(*(_QWORD *)(a1 + 472), a2 + 144, v19);
  if ( !(unsigned __int8)WinNatReleaseBinding(*(_QWORD *)(a2 + 80)) )
    *(_QWORD *)(a2 + 80) = 0;
  if ( (unsigned __int8)WinNatHashTableRestructureRequired(*(_QWORD *)(a1 + 384))
    || (unsigned __int8)WinNatHashTableRestructureRequired(*(_QWORD *)(a1 + 392)) )
  {
    WinNatScheduleRestructureDpc(a1 - 128);
  }
  v5 = *(_DWORD *)(a2 + 120);
  v6 = *(_QWORD *)(a1 + 1216);
  v7 = 136 * CurrentProcessorNumber;
  if ( v5 == 6 )
  {
    --*(_DWORD *)(v7 + v6);
  }
  else if ( v5 == 17 )
  {
    --*(_DWORD *)(v7 + v6 + 24);
  }
  else
  {
    --*(_DWORD *)(v7 + v6 + 48);
  }
  v8 = *(_QWORD *)(a1 + 1216);
  --*(_QWORD *)(v7 + v8 + 80);
  if ( (*(_BYTE *)(a1 + 628) & 2) != 0 )
  {
    LOBYTE(v8) = -*(_BYTE *)(a2 + 256);
    SessionSize -= *(_BYTE *)(a2 + 256) != 0 ? 360LL : 336LL;
  }
  v9 = 28;
  if ( (Microsoft_Windows_WinNatEnableBits & 1) != 0 )
  {
    if ( dword_140026104 )
    {
      v10 = *(_QWORD *)(a2 + 88);
      memset(v21, 0, 28);
      memset(v23, 0, 28);
      memset(v20, 0, 28);
      memset(v22, 0, 28);
      WinNatCopyTransportAddrToSockAddr(v10, v21);
      WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 96), v23);
      WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 104), v20);
      LOBYTE(v8) = WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 112), v22);
      if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 1) != 0 )
      {
        if ( (*(_BYTE *)(a2 + 132) & 1) != 0 )
          v12 = 0;
        else
          v12 = *(_DWORD *)(a2 + 136) - MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
        v13 = 28;
        v14 = 28;
        if ( v20[0] == 2 )
          v13 = 16;
        if ( v21[0] == 2 )
          v14 = 16;
        LOBYTE(v8) = McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer(
                       (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                       (unsigned int)WINNAT_SESSION_DELETE,
                       v11,
                       v14,
                       (__int64)v21,
                       (__int64)v23,
                       v13,
                       (__int64)v20,
                       (__int64)v22,
                       *(_DWORD *)(a2 + 120),
                       v12,
                       *(_DWORD *)(a2 + 248),
                       *(_DWORD *)(a2 + 8));
      }
    }
  }
  if ( (*(_BYTE *)(a1 + 628) & 2) != 0 && (Microsoft_Windows_WinNatEnableBits & 0x40) != 0 )
  {
    v15 = *(_QWORD *)(a2 + 88);
    memset(v20, 0, 28);
    memset(v22, 0, 28);
    memset(v21, 0, 28);
    memset(v23, 0, 28);
    WinNatCopyTransportAddrToSockAddr(v15, v20);
    WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 96), v22);
    WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 104), v21);
    LOBYTE(v8) = WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 112), v23);
    if ( (Microsoft_Windows_WinNatEnableBits & 0x40) != 0 )
    {
      v17 = 28;
      if ( v21[0] == 2 )
        v17 = 16;
      if ( v20[0] == 2 )
        v9 = 16;
      LOBYTE(v8) = McTemplateK0qbr0br0qbr3br3q_EtwWriteTransfer(
                     (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                     (unsigned int)WINNAT_SESSION_DELETE_OPERATIONAL,
                     v16,
                     v9,
                     (__int64)v20,
                     (__int64)v22,
                     v17,
                     (__int64)v21,
                     (__int64)v23,
                     *(_DWORD *)(a2 + 120));
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14000ae68  mov     [rsp-8+arg_10], rbx
0x14000ae6d  push    rbp
0x14000ae6e  push    rsi
0x14000ae6f  push    rdi
0x14000ae70  push    r12
0x14000ae72  push    r14
0x14000ae74  lea     rbp, [rsp-37h]
0x14000ae79  sub     rsp, 100h
0x14000ae80  mov     rax, cs:__security_cookie
0x14000ae87  xor     rax, rsp
0x14000ae8a  mov     [rbp+57h+var_28], rax
0x14000ae8e  mov     rdi, rcx
0x14000ae91  mov     [rbp+57h+var_B0], 0
0x14000ae95  xor     ecx, ecx; ProcNumber
0x14000ae97  mov     rbx, rdx
0x14000ae9a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000aea1  nop     dword ptr [rax+rax+00h]
0x14000aea6  mov     rcx, [rdi+180h]; HashTable
0x14000aead  lea     rdx, [rbx+0A8h]; Entry
0x14000aeb4  xor     r8d, r8d; Context
0x14000aeb7  mov     r14d, eax
0x14000aeba  call    cs:__imp_RtlRemoveEntryHashTable
0x14000aec1  nop     dword ptr [rax+rax+00h]
0x14000aec6  mov     rcx, [rdi+188h]; HashTable
0x14000aecd  lea     rdx, [rbx+0C0h]; Entry
0x14000aed4  xor     r8d, r8d; Context
0x14000aed7  call    cs:__imp_RtlRemoveEntryHashTable
0x14000aede  nop     dword ptr [rax+rax+00h]
0x14000aee3  mov     rcx, [rdi+190h]; HashTable
0x14000aeea  lea     rdx, [rbx+0D8h]; Entry
0x14000aef1  xor     r8d, r8d; Context
0x14000aef4  call    cs:__imp_RtlRemoveEntryHashTable
0x14000aefb  nop     dword ptr [rax+rax+00h]
0x14000af00  test    byte ptr [rdi+274h], 1
0x14000af07  jnz     short loc_14000AF27
0x14000af09  mov     rcx, [rdi+1D8h]
0x14000af10  lea     rdx, [rbx+90h]
0x14000af17  lea     r8, [rbp+57h+var_B0]
0x14000af1b  call    cs:__imp_RtlCleanupTimerWheelEntry
0x14000af22  nop     dword ptr [rax+rax+00h]
0x14000af27  mov     rcx, [rbx+50h]
0x14000af2b  call    WinNatReleaseBinding
0x14000af30  test    al, al
0x14000af32  jnz     short loc_14000AF3C
0x14000af34  mov     qword ptr [rbx+50h], 0
0x14000af3c  mov     rcx, [rdi+180h]
0x14000af43  call    WinNatHashTableRestructureRequired
0x14000af48  test    al, al
0x14000af4a  jnz     short loc_14000AF5C
0x14000af4c  mov     rcx, [rdi+188h]
0x14000af53  call    WinNatHashTableRestructureRequired
0x14000af58  test    al, al
0x14000af5a  jz      short loc_14000AF65
0x14000af5c  lea     rcx, [rdi-80h]
0x14000af60  call    WinNatScheduleRestructureDpc
0x14000af65  mov     edx, [rbx+78h]
0x14000af68  mov     rax, [rdi+4C0h]
0x14000af6f  imul    rcx, r14, 88h
0x14000af76  cmp     edx, 6
0x14000af79  jnz     short loc_14000AF80
0x14000af7b  dec     dword ptr [rcx+rax]
0x14000af7e  jmp     short loc_14000AF8F
0x14000af80  cmp     edx, 11h
0x14000af83  jnz     short loc_14000AF8B
0x14000af85  dec     dword ptr [rcx+rax+18h]
0x14000af89  jmp     short loc_14000AF8F
0x14000af8b  dec     dword ptr [rcx+rax+30h]
0x14000af8f  mov     rax, [rdi+4C0h]
0x14000af96  mov     r14w, 2
0x14000af9b  dec     qword ptr [rcx+rax+50h]
0x14000afa0  test    [rdi+274h], r14b
0x14000afa7  jz      short loc_14000AFC5
0x14000afa9  mov     al, [rbx+100h]
0x14000afaf  neg     al
0x14000afb1  sbb     rcx, rcx
0x14000afb4  and     ecx, 18h
0x14000afb7  add     rcx, 150h
0x14000afbe  sub     cs:SessionSize, rcx
0x14000afc5  test    cs:Microsoft_Windows_WinNatEnableBits, 1
0x14000afcc  mov     esi, 1Ch
0x14000afd1  lea     r12d, [rsi-0Ch]
0x14000afd5  jz      loc_14000B11C
0x14000afdb  cmp     cs:dword_140026104, 0
0x14000afe2  jz      loc_14000B11C
0x14000afe8  mov     rcx, [rbx+58h]
0x14000afec  lea     rdx, [rbp+57h+var_88]
0x14000aff0  xorps   xmm0, xmm0
0x14000aff3  xorps   xmm1, xmm1
0x14000aff6  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x14000affa  xor     eax, eax
0x14000affc  movups  [rbp+57h+var_48], xmm1
0x14000b000  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x14000b004  movups  [rbp+57h+var_68], xmm1
0x14000b008  movups  xmmword ptr [rbp+57h+var_88+0Ch], xmm0
0x14000b00c  movups  [rbp+57h+var_48+0Ch], xmm1
0x14000b010  movups  xmmword ptr [rbp+57h+var_A8+0Ch], xmm0
0x14000b014  movups  [rbp+57h+var_68+0Ch], xmm1
0x14000b018  call    WinNatCopyTransportAddrToSockAddr
0x14000b01d  mov     rcx, [rbx+60h]
0x14000b021  lea     rdx, [rbp+57h+var_48]
0x14000b025  call    WinNatCopyTransportAddrToSockAddr
0x14000b02a  mov     rcx, [rbx+68h]
0x14000b02e  lea     rdx, [rbp+57h+var_A8]
0x14000b032  call    WinNatCopyTransportAddrToSockAddr
0x14000b037  mov     rcx, [rbx+70h]
0x14000b03b  lea     rdx, [rbp+57h+var_68]
0x14000b03f  call    WinNatCopyTransportAddrToSockAddr
0x14000b044  cmp     cs:dword_140026104, 1
0x14000b04b  jnz     loc_14000B11C
0x14000b051  test    cs:Microsoft_Windows_WinNatEnableBits, 1
0x14000b058  jz      loc_14000B11C
0x14000b05e  test    byte ptr [rbx+84h], 1
0x14000b065  jz      short loc_14000B06B
0x14000b067  xor     edx, edx
0x14000b069  jmp     short loc_14000B0AE
0x14000b06b  mov     rcx, 0FFFFF78000000008h
0x14000b075  mov     rax, 346DC5D63886594Bh
0x14000b07f  mov     rcx, [rcx]
0x14000b082  mul     rcx
0x14000b085  mov     rax, 624DD2F1A9FBE77h
0x14000b08f  mov     rcx, rdx
0x14000b092  shr     rcx, 0Bh
0x14000b096  mul     rcx
0x14000b099  sub     rcx, rdx
0x14000b09c  shr     rcx, 1
0x14000b09f  add     rcx, rdx
0x14000b0a2  mov     edx, [rbx+88h]
0x14000b0a8  shr     rcx, 9
0x14000b0ac  sub     edx, ecx
0x14000b0ae  mov     eax, [rbx+8]
0x14000b0b1  mov     ecx, esi
0x14000b0b3  cmp     [rbp+57h+var_A8], r14w
0x14000b0b8  mov     r9d, esi
0x14000b0bb  mov     [rsp+120h+var_C0], eax
0x14000b0bf  mov     eax, [rbx+0F8h]
0x14000b0c5  cmovz   ecx, r12d
0x14000b0c9  cmp     [rbp+57h+var_88], r14w
0x14000b0ce  mov     [rsp+120h+var_C8], eax
0x14000b0d2  mov     eax, [rbx+78h]
0x14000b0d5  cmovz   r9d, r12d
0x14000b0d9  mov     [rsp+120h+var_D0], edx
0x14000b0dd  lea     rdx, WINNAT_SESSION_DELETE
0x14000b0e4  mov     [rsp+120h+var_D8], eax
0x14000b0e8  lea     rax, [rbp+57h+var_68]
0x14000b0ec  mov     [rsp+120h+var_E0], rax
0x14000b0f1  lea     rax, [rbp+57h+var_A8]
0x14000b0f5  mov     [rsp+120h+var_E8], rax
0x14000b0fa  lea     rax, [rbp+57h+var_48]
0x14000b0fe  mov     [rsp+120h+var_F0], ecx
0x14000b102  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000b109  mov     [rsp+120h+var_F8], rax
0x14000b10e  lea     rax, [rbp+57h+var_88]
0x14000b112  mov     [rsp+120h+var_100], rax
0x14000b117  call    McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer
0x14000b11c  test    [rdi+274h], r14b
0x14000b123  jz      loc_14000B1F4
0x14000b129  test    cs:Microsoft_Windows_WinNatEnableBits, 40h
0x14000b130  jz      loc_14000B1F4
0x14000b136  mov     rcx, [rbx+58h]
0x14000b13a  lea     rdx, [rbp+57h+var_A8]
0x14000b13e  xorps   xmm0, xmm0
0x14000b141  xorps   xmm1, xmm1
0x14000b144  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x14000b148  xor     eax, eax
0x14000b14a  movups  [rbp+57h+var_68], xmm1
0x14000b14e  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x14000b152  movups  [rbp+57h+var_48], xmm1
0x14000b156  movups  xmmword ptr [rbp+57h+var_A8+0Ch], xmm0
0x14000b15a  movups  [rbp+57h+var_68+0Ch], xmm1
0x14000b15e  movups  xmmword ptr [rbp+57h+var_88+0Ch], xmm0
0x14000b162  movups  [rbp+57h+var_48+0Ch], xmm1
0x14000b166  call    WinNatCopyTransportAddrToSockAddr
0x14000b16b  mov     rcx, [rbx+60h]
0x14000b16f  lea     rdx, [rbp+57h+var_68]
0x14000b173  call    WinNatCopyTransportAddrToSockAddr
0x14000b178  mov     rcx, [rbx+68h]
0x14000b17c  lea     rdx, [rbp+57h+var_88]
0x14000b180  call    WinNatCopyTransportAddrToSockAddr
0x14000b185  mov     rcx, [rbx+70h]
0x14000b189  lea     rdx, [rbp+57h+var_48]
0x14000b18d  call    WinNatCopyTransportAddrToSockAddr
0x14000b192  test    cs:Microsoft_Windows_WinNatEnableBits, 40h
0x14000b199  jz      short loc_14000B1F4
0x14000b19b  mov     eax, [rbx+78h]
0x14000b19e  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000b1a5  cmp     [rbp+57h+var_88], r14w
0x14000b1aa  mov     edx, esi
0x14000b1ac  mov     [rsp+120h+var_D8], eax
0x14000b1b0  lea     rax, [rbp+57h+var_48]
0x14000b1b4  mov     [rsp+120h+var_E0], rax
0x14000b1b9  cmovz   edx, r12d
0x14000b1bd  cmp     [rbp+57h+var_A8], r14w
0x14000b1c2  lea     rax, [rbp+57h+var_88]
0x14000b1c6  mov     [rsp+120h+var_E8], rax
0x14000b1cb  lea     rax, [rbp+57h+var_68]
0x14000b1cf  mov     [rsp+120h+var_F0], edx
0x14000b1d3  cmovz   esi, r12d
0x14000b1d7  mov     [rsp+120h+var_F8], rax
0x14000b1dc  lea     rdx, WINNAT_SESSION_DELETE_OPERATIONAL
0x14000b1e3  lea     rax, [rbp+57h+var_A8]
0x14000b1e7  mov     r9d, esi
0x14000b1ea  mov     [rsp+120h+var_100], rax
0x14000b1ef  call    McTemplateK0qbr0br0qbr3br3q_EtwWriteTransfer
0x14000b1f4  mov     rcx, [rbp+57h+var_28]
0x14000b1f8  xor     rcx, rsp; StackCookie
0x14000b1fb  call    __security_check_cookie
0x14000b200  mov     rbx, [rsp+120h+arg_10]
0x14000b208  add     rsp, 100h
0x14000b20f  pop     r14
0x14000b211  pop     r12
0x14000b213  pop     rdi
0x14000b214  pop     rsi
0x14000b215  pop     rbp
0x14000b216  retn
```

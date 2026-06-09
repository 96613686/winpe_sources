# WinNatLibReserveBinding

- ea: `0x14001a398`
- end: `0x14001a94b`
- name: `WinNatLibReserveBinding`
- size: `1459`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int16 *, __int16 *, int, char, char, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b50c`

## callees

- `0x140004a80`
- `0x140008df0`
- `0x140009034`
- `0x14000b404`
- `0x14000baf8`
- `0x14000c948`
- `0x14000c9d8`
- `0x14000caa0`
- `0x140011b90`
- `0x140019c68`
- `0x14001a040`
- `0x14001a398`
- `0x14001f140`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a8d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001a8d3`
- `ntoskrnl!RtlSetBits` at `0x14001a67b`
- `ntoskrnl!RtlSetBits` at `0x14001a67b`
- `ntoskrnl!RtlAreBitsClear` at `0x14001a64a`
- `ntoskrnl!RtlAreBitsClear` at `0x14001a64a`
- `ntoskrnl!RtlClearBits` at `0x14001a86e`
- `ntoskrnl!RtlClearBits` at `0x14001a86e`
- `NETIO!PtDestroyTable` at `0x14001a907`
- `NETIO!PtDestroyTable` at `0x14001a907`
- `NETIO!PtDeleteEntry` at `0x14001a49e`
- `NETIO!PtDeleteEntry` at `0x14001a49e`
- `NETIO!PtInsertEntry` at `0x14001a4d3`
- `NETIO!PtInsertEntry` at `0x14001a7fe`
- `NETIO!PtInsertEntry` at `0x14001a4d3`
- `NETIO!PtInsertEntry` at `0x14001a7fe`
- `NETIO!PtCreateTable` at `0x14001a73c`
- `NETIO!PtCreateTable` at `0x14001a73c`

## pseudocode

```c
__int64 __fastcall WinNatLibReserveBinding(
        _QWORD *a1,
        __int64 a2,
        __int16 *a3,
        __int16 *a4,
        int a5,
        char a6,
        char a7,
        unsigned __int8 *a8,
        int a9)
{
  __int64 *v10; // r12
  char v11; // r13
  __int64 v13; // r14
  __int64 v14; // rdi
  int Table; // ebx
  __int64 v16; // rdx
  __int64 v17; // rcx
  char v18; // al
  __int64 v19; // rdx
  __int64 v20; // rcx
  char v21; // al
  char v22; // al
  __int64 v23; // r12
  __int64 BindingUnderLock; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 AddressEntry; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  struct _RTL_BITMAP *BitMapForProtocol; // r9
  __int64 v32; // rcx
  __int64 v33; // rcx
  char v34; // cl
  __int16 *Binding; // rax
  __int64 v36; // rcx
  __int16 *v37; // r9
  size_t v38; // r8
  __int64 v39; // rdx
  bool v40; // zf
  __int16 *v41; // rax
  __int16 *v42; // rsi
  __int16 *v43; // r9
  size_t v44; // r8
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  char v50; // [rsp+50h] [rbp-68h]
  __int64 *v51; // [rsp+58h] [rbp-60h]
  struct _RTL_BITMAP *BitMapHeader; // [rsp+60h] [rbp-58h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-50h] BYREF
  char v55; // [rsp+C8h] [rbp+10h]

  v10 = a1 + 96;
  v50 = 0;
  v11 = 0;
  v51 = a1 + 96;
  v55 = 0;
  v13 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v14 = 0;
  Table = 0;
  RtlAcquireScalableWriteLockAtDpcLevel(a1 + 104, &LockHandle);
  if ( !a2 )
  {
    v23 = 2;
    if ( a7 )
    {
      BindingUnderLock = WinNatFindBindingUnderLock((_DWORD)v51, 1, (_DWORD)a3, 0, a6, 0, a9);
      v14 = BindingUnderLock;
      if ( BindingUnderLock )
      {
        if ( (*(_BYTE *)(BindingUnderLock + 88) & 4) == 0 )
        {
          Table = -1073741788;
          v10 = v51;
          v11 = 0;
          goto LABEL_72;
        }
        BitMapHeader = 0;
        if ( *(int *)(BindingUnderLock + 64) <= 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v26, v25);
        v13 = *(_QWORD *)(v14 + 72);
        if ( v13 )
          goto LABEL_52;
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v26, v25);
      }
    }
    AddressEntry = WinNatLibFindAddressEntry(a1 + 160, 0, __ROR2__(a3[1], 8), 0, 0, 0);
    v13 = AddressEntry;
    if ( !AddressEntry )
    {
      Table = -1073741811;
LABEL_70:
      v11 = v55;
      goto LABEL_71;
    }
    LOBYTE(v28) = a6;
    v55 = 1;
    BitMapForProtocol = (struct _RTL_BITMAP *)WinNatGetBitMapForProtocol(AddressEntry, v28);
    BitMapHeader = BitMapForProtocol;
    if ( *a3 != 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v30, v29);
      BitMapForProtocol = BitMapHeader;
    }
    v32 = 2;
    if ( *a3 != 2 )
      v32 = 4;
    if ( *(_DWORD *)&a3[v32] && !RtlAreBitsClear(BitMapForProtocol, (unsigned __int16)__ROR2__(a3[1], 8), 1u) )
    {
      Table = -1073741302;
      v11 = 1;
LABEL_71:
      v10 = v51;
      goto LABEL_72;
    }
    RtlSetBits(BitMapHeader, (unsigned __int16)__ROR2__(a3[1], 8), 1u);
    LOBYTE(v33) = a6;
    WinNatIncrementPortUsage(v33, v13);
    if ( a7 && !v14 )
    {
      Binding = WinNatLibCreateBinding(v51, 1, a3, v34, *(_QWORD *)(v13 + 112), a9);
      v14 = (__int64)Binding;
      if ( !Binding )
        goto LABEL_46;
      v37 = (__int16 *)*((_QWORD *)Binding + 13);
      v38 = 4;
      *((_DWORD *)Binding + 16) = 0;
      v39 = 2;
      v40 = *a3 == 2;
      v50 = 1;
      *v37 = *a3;
      v37[1] = a3[1];
      if ( !v40 )
        v38 = 16;
      if ( *a3 != 2 )
        v39 = 4;
      memmove(v37 + 2, &a3[v39], v38);
      *(_BYTE *)(v14 + 88) |= 5u;
      *(_QWORD *)(v14 + 72) = v13;
      Table = PtCreateTable(8 * (unsigned int)*(unsigned __int8 *)(v13 + 32), v14 + 16);
      if ( Table < 0 )
        goto LABEL_63;
    }
LABEL_52:
    v41 = WinNatLibCreateBinding(v51, a5, a4, a6, *(_QWORD *)(v13 + 112), a9);
    v42 = v41;
    if ( v41 )
    {
      v43 = (__int16 *)*((_QWORD *)v41 + 13);
      v44 = 4;
      v40 = *a3 == 2;
      *v43 = *a3;
      v43[1] = a3[1];
      if ( !v40 )
        v44 = 16;
      if ( *a3 != 2 )
        v23 = 4;
      memmove(v43 + 2, &a3[v23], v44);
      *((_BYTE *)v42 + 88) |= 1u;
      *((_QWORD *)v42 + 9) = v13;
      if ( v14 )
      {
        Table = PtInsertEntry(*(_QWORD *)(v14 + 16), *((_QWORD *)a8 + 1), *a8, 0, v42 + 20);
        if ( Table < 0 )
        {
          if ( *a4 == 2 )
            v47 = a1[97];
          else
            v47 = a1[96];
          PplFreeToLookasideList(v47, v42);
LABEL_63:
          v11 = v55;
          if ( v55 )
          {
            LOBYTE(v36) = a6;
            WinNatDecrementPortUsage(v36, v13);
            RtlClearBits(BitMapHeader, (unsigned __int16)__ROR2__(a3[1], 8), 1u);
          }
          goto LABEL_71;
        }
        *((_BYTE *)v42 + 88) |= 8u;
        *((_QWORD *)v42 + 6) = v14;
        ++*(_DWORD *)(v14 + 64);
        if ( v50 )
        {
          if ( *(_DWORD *)(v14 + 64) != 1 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v46, v45);
          WinNatInsertBindingToTable(a1, v14);
          v14 = 0;
        }
      }
      WinNatInsertBindingToTable(a1, v42);
      v13 = 0;
      Table = 0;
      goto LABEL_70;
    }
LABEL_46:
    Table = -1073741670;
    goto LABEL_63;
  }
  if ( (*(_BYTE *)(a2 + 88) & 2) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
  if ( *(_DWORD *)(a2 + 92) != a5 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
  v18 = *(_BYTE *)(a2 + 88);
  if ( (v18 & 1) != 0 )
  {
    Table = -1073741270;
    goto LABEL_72;
  }
  if ( (v18 & 8) != 0 )
  {
    if ( !a7 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
    v14 = *(_QWORD *)(a2 + 48);
    if ( !v14 || (*(_BYTE *)(v14 + 88) & 4) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
    if ( *(int *)(v14 + 64) <= 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
    if ( (*(_BYTE *)(a2 + 88) & 0x10) == 0 && (int)PtDeleteEntry(*(_QWORD *)(v14 + 16), a2 + 40) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v19);
    Table = PtInsertEntry(*(_QWORD *)(v14 + 16), *((_QWORD *)a8 + 1), *a8, 0, a2 + 40);
    v11 = 0;
    v21 = *(_BYTE *)(a2 + 88);
    if ( Table >= 0 )
      v22 = v21 | 1;
    else
      v22 = v21 | 0x10;
    *(_BYTE *)(a2 + 88) = v22;
    goto LABEL_71;
  }
  if ( a7 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
  *(_BYTE *)(a2 + 88) |= 1u;
  v11 = 0;
LABEL_72:
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  if ( v13 && v11 )
    WinNatLibDereferenceAddressEntry(v13);
  if ( v14 && v50 )
  {
    if ( *(_QWORD *)(v14 + 16) )
      PtDestroyTable();
    if ( *a3 == 2 )
      v48 = v10[1];
    else
      v48 = *v10;
    PplFreeToLookasideList(v48, v14);
  }
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x14001a398  mov     rax, rsp
0x14001a39b  mov     [rax+18h], rbx
0x14001a39f  mov     [rax+20h], r9
0x14001a3a3  mov     [rax+8], rcx
0x14001a3a7  push    rbp
0x14001a3a8  push    rsi
0x14001a3a9  push    rdi
0x14001a3aa  push    r12
0x14001a3ac  push    r13
0x14001a3ae  push    r14
0x14001a3b0  push    r15
0x14001a3b2  sub     rsp, 80h
0x14001a3b9  mov     r12, rcx
0x14001a3bc  mov     rsi, rdx
0x14001a3bf  xor     ecx, ecx
0x14001a3c1  lea     rdx, [rax-50h]
0x14001a3c5  add     r12, 300h
0x14001a3cc  mov     [rax-40h], rcx
0x14001a3d0  xorps   xmm0, xmm0
0x14001a3d3  mov     [rsp+0B8h+var_68], cl
0x14001a3d7  xor     r13b, r13b
0x14001a3da  mov     [rsp+0B8h+var_60], r12
0x14001a3df  mov     r15, r8
0x14001a3e2  mov     [rsp+0B8h+arg_8], r13b
0x14001a3ea  lea     rcx, [r12+40h]
0x14001a3ef  xor     r14d, r14d
0x14001a3f2  movups  xmmword ptr [rax-50h], xmm0
0x14001a3f6  xor     edi, edi
0x14001a3f8  xor     ebx, ebx
0x14001a3fa  call    RtlAcquireScalableWriteLockAtDpcLevel
0x14001a3ff  test    rsi, rsi
0x14001a402  jz      loc_14001A505
0x14001a408  test    byte ptr [rsi+58h], 2
0x14001a40c  jz      short loc_14001A413
0x14001a40e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a413  mov     eax, [rsp+0B8h+arg_20]
0x14001a41a  cmp     [rsi+5Ch], eax
0x14001a41d  jz      short loc_14001A424
0x14001a41f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a424  mov     al, [rsi+58h]
0x14001a427  mov     ebp, 1
0x14001a42c  test    bpl, al
0x14001a42f  jnz     loc_14001A4FB
0x14001a435  lea     r13d, [rbp+7]
0x14001a439  test    r13b, al
0x14001a43c  jnz     short loc_14001A458
0x14001a43e  cmp     [rsp+0B8h+arg_30], bl
0x14001a445  jz      short loc_14001A44C
0x14001a447  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a44c  or      [rsi+58h], bpl
0x14001a450  mov     r13b, bl
0x14001a453  jmp     loc_14001A8CE
0x14001a458  cmp     [rsp+0B8h+arg_30], bl
0x14001a45f  jnz     short loc_14001A466
0x14001a461  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a466  mov     rdi, [rsi+30h]
0x14001a46a  test    rdi, rdi
0x14001a46d  jz      short loc_14001A47B
0x14001a46f  mov     r12d, 4
0x14001a475  test    [rdi+58h], r12b
0x14001a479  jnz     short loc_14001A480
0x14001a47b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a480  cmp     [rdi+40h], ebx
0x14001a483  jg      short loc_14001A48A
0x14001a485  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a48a  mov     r12d, 10h
0x14001a490  test    [rsi+58h], r12b
0x14001a494  jnz     short loc_14001A4B3
0x14001a496  mov     rcx, [rdi+10h]
0x14001a49a  lea     rdx, [rsi+28h]
0x14001a49e  call    cs:__imp_PtDeleteEntry
0x14001a4a5  nop     dword ptr [rax+rax+00h]
0x14001a4aa  test    eax, eax
0x14001a4ac  jns     short loc_14001A4B3
0x14001a4ae  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a4b3  mov     rdx, [rsp+0B8h+arg_38]
0x14001a4bb  lea     rax, [rsi+28h]
0x14001a4bf  mov     rcx, [rdi+10h]
0x14001a4c3  xor     r9d, r9d
0x14001a4c6  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001a4cb  movzx   r8d, byte ptr [rdx]
0x14001a4cf  mov     rdx, [rdx+8]
0x14001a4d3  call    cs:__imp_PtInsertEntry
0x14001a4da  nop     dword ptr [rax+rax+00h]
0x14001a4df  mov     ebx, eax
0x14001a4e1  mov     r13b, r14b
0x14001a4e4  mov     al, [rsi+58h]
0x14001a4e7  test    ebx, ebx
0x14001a4e9  jns     short loc_14001A4F6
0x14001a4eb  or      al, r12b
0x14001a4ee  mov     [rsi+58h], al
0x14001a4f1  jmp     loc_14001A8C9
0x14001a4f6  or      al, bpl
0x14001a4f9  jmp     short loc_14001A4EE
0x14001a4fb  mov     ebx, 0C000022Ah
0x14001a500  jmp     loc_14001A8CE
0x14001a505  mov     ebp, 1
0x14001a50a  mov     rsi, [rsp+0B8h+var_60]
0x14001a50f  lea     r13d, [rbp+7]
0x14001a513  lea     r12d, [rbp+3]
0x14001a517  cmp     [rsp+0B8h+arg_30], bl
0x14001a51e  jz      short loc_14001A589
0x14001a520  mov     eax, [rsp+0B8h+arg_40]
0x14001a527  xor     r9d, r9d
0x14001a52a  mov     dword ptr [rsp+0B8h+var_88], eax
0x14001a52e  mov     r8, r15
0x14001a531  mov     al, [rsp+0B8h+arg_28]
0x14001a538  mov     edx, ebp
0x14001a53a  mov     byte ptr [rsp+0B8h+var_90], bl
0x14001a53e  mov     rcx, rsi
0x14001a541  mov     byte ptr [rsp+0B8h+var_98], al
0x14001a545  call    WinNatFindBindingUnderLock
0x14001a54a  mov     rdi, rax
0x14001a54d  test    rax, rax
0x14001a550  jz      short loc_14001A589
0x14001a552  test    [rax+58h], r12b
0x14001a556  jnz     short loc_14001A568
0x14001a558  mov     ebx, 0C0000024h
0x14001a55d  mov     r12, rsi
0x14001a560  mov     r13b, r14b
0x14001a563  jmp     loc_14001A8CE
0x14001a568  mov     [rsp+0B8h+BitMapHeader], rbx
0x14001a56d  cmp     [rax+40h], ebx
0x14001a570  jg      short loc_14001A577
0x14001a572  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a577  mov     r14, [rdi+48h]
0x14001a57b  test    r14, r14
0x14001a57e  jnz     loc_14001A752
0x14001a584  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a589  movzx   r11d, word ptr [r15+2]
0x14001a58e  xor     r14d, r14d
0x14001a591  mov     [rsp+0B8h+var_78], r14; __int64
0x14001a596  xor     r9d, r9d
0x14001a599  ror     r11w, 8
0x14001a59e  mov     r8d, r12d
0x14001a5a1  cmp     word ptr [r15], 2
0x14001a5a6  mov     rdx, r12
0x14001a5a9  mov     [rsp+0B8h+var_80], r14; __int64
0x14001a5ae  lea     ecx, [r14+10h]
0x14001a5b2  cmovnz  r8d, ecx
0x14001a5b6  mov     [rsp+0B8h+var_88], r14b; char
0x14001a5bb  mov     rcx, [rsp+0B8h+arg_0]
0x14001a5c3  cmovnz  rdx, r13
0x14001a5c7  mov     [rsp+0B8h+var_90], r11w; __int16
0x14001a5cd  add     rcx, 500h; SpinLock
0x14001a5d4  add     rdx, r15
0x14001a5d7  mov     [rsp+0B8h+var_98], r14w; __int16
0x14001a5dd  call    WinNatLibFindAddressEntry
0x14001a5e2  mov     r14, rax
0x14001a5e5  test    rax, rax
0x14001a5e8  jnz     short loc_14001A5F4
0x14001a5ea  mov     ebx, 0C000000Dh
0x14001a5ef  jmp     loc_14001A8C1
0x14001a5f4  mov     dl, [rsp+0B8h+arg_28]
0x14001a5fb  mov     rcx, r14
0x14001a5fe  mov     [rsp+0B8h+arg_8], bpl
0x14001a606  call    WinNatGetBitMapForProtocol
0x14001a60b  cmp     word ptr [r15], 2
0x14001a610  mov     r9, rax
0x14001a613  mov     [rsp+0B8h+BitMapHeader], rax
0x14001a618  jz      short loc_14001A624
0x14001a61a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a61f  mov     r9, [rsp+0B8h+BitMapHeader]
0x14001a624  cmp     word ptr [r15], 2
0x14001a629  mov     rcx, r12
0x14001a62c  cmovnz  rcx, r13
0x14001a630  mov     ecx, [rcx+r15]
0x14001a634  test    ecx, ecx
0x14001a636  jz      short loc_14001A667
0x14001a638  movzx   eax, word ptr [r15+2]
0x14001a63d  mov     r8d, ebp; Length
0x14001a640  ror     ax, 8
0x14001a644  mov     rcx, r9; BitMapHeader
0x14001a647  movzx   edx, ax; StartingIndex
0x14001a64a  call    cs:__imp_RtlAreBitsClear
0x14001a651  nop     dword ptr [rax+rax+00h]
0x14001a656  test    al, al
0x14001a658  jnz     short loc_14001A667
0x14001a65a  mov     ebx, 0C000020Ah
0x14001a65f  mov     r13b, bpl
0x14001a662  jmp     loc_14001A8C9
0x14001a667  movzx   eax, word ptr [r15+2]
0x14001a66c  mov     r8d, ebp; NumberToSet
0x14001a66f  mov     rcx, [rsp+0B8h+BitMapHeader]; BitMapHeader
0x14001a674  ror     ax, 8
0x14001a678  movzx   edx, ax; StartingIndex
0x14001a67b  call    cs:__imp_RtlSetBits
0x14001a682  nop     dword ptr [rax+rax+00h]
0x14001a687  mov     cl, [rsp+0B8h+arg_28]
0x14001a68e  mov     rdx, r14
0x14001a691  call    WinNatIncrementPortUsage
0x14001a696  cmp     [rsp+0B8h+arg_30], bl
0x14001a69d  jz      loc_14001A752
0x14001a6a3  test    rdi, rdi
0x14001a6a6  jnz     loc_14001A752
0x14001a6ac  mov     eax, [rsp+0B8h+arg_40]
0x14001a6b3  mov     r9b, cl
0x14001a6b6  mov     dword ptr [rsp+0B8h+var_90], eax
0x14001a6ba  mov     r8, r15
0x14001a6bd  mov     rax, [r14+70h]
0x14001a6c1  mov     edx, ebp
0x14001a6c3  mov     rcx, rsi
0x14001a6c6  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001a6cb  call    WinNatLibCreateBinding
0x14001a6d0  mov     rdi, rax
0x14001a6d3  test    rax, rax
0x14001a6d6  jnz     short loc_14001A6E2
0x14001a6d8  mov     ebx, 0C000009Ah
0x14001a6dd  jmp     loc_14001A83E
0x14001a6e2  mov     r9, [rax+68h]
0x14001a6e6  mov     r8, r12
0x14001a6e9  mov     [rax+40h], ebx
0x14001a6ec  mov     rdx, r12
0x14001a6ef  movzx   ecx, word ptr [r15]
0x14001a6f3  cmp     cx, 2
0x14001a6f7  mov     [rsp+0B8h+var_68], bpl
0x14001a6fc  mov     [r9], cx
0x14001a700  lea     rcx, [r9+4]; void *
0x14001a704  movzx   eax, word ptr [r15+2]
0x14001a709  mov     [r9+2], ax
0x14001a70e  mov     eax, 10h
0x14001a713  cmovnz  r8, rax; Size
0x14001a717  cmp     word ptr [r15], 2
0x14001a71c  cmovnz  rdx, r13
0x14001a720  add     rdx, r15; Src
0x14001a723  call    memmove
0x14001a728  or      byte ptr [rdi+58h], 5
0x14001a72c  lea     rdx, [rdi+10h]
0x14001a730  mov     [rdi+48h], r14
0x14001a734  movzx   ecx, byte ptr [r14+20h]
0x14001a739  shl     ecx, 3
0x14001a73c  call    cs:__imp_PtCreateTable
0x14001a743  nop     dword ptr [rax+rax+00h]
0x14001a748  mov     ebx, eax
0x14001a74a  test    eax, eax
0x14001a74c  js      loc_14001A83E
0x14001a752  mov     eax, [rsp+0B8h+arg_40]
0x14001a759  mov     rcx, rsi
0x14001a75c  mov     r9b, [rsp+0B8h+arg_28]
0x14001a764  mov     r8, [rsp+0B8h+arg_18]
0x14001a76c  mov     edx, [rsp+0B8h+arg_20]
0x14001a773  mov     dword ptr [rsp+0B8h+var_90], eax
0x14001a777  mov     rax, [r14+70h]
0x14001a77b  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001a780  call    WinNatLibCreateBinding
0x14001a785  mov     rsi, rax
0x14001a788  test    rax, rax
0x14001a78b  jz      loc_14001A6D8
0x14001a791  mov     r9, [rax+68h]
0x14001a795  mov     r8, r12
0x14001a798  movzx   ecx, word ptr [r15]
0x14001a79c  cmp     cx, 2
0x14001a7a0  mov     [r9], cx
0x14001a7a4  lea     rcx, [r9+4]; void *
0x14001a7a8  movzx   eax, word ptr [r15+2]
0x14001a7ad  mov     [r9+2], ax
0x14001a7b2  mov     eax, 10h
0x14001a7b7  cmovnz  r8, rax; Size
0x14001a7bb  cmp     word ptr [r15], 2
0x14001a7c0  cmovnz  r12, r13
0x14001a7c4  lea     rdx, [r15+r12]; Src
0x14001a7c8  call    memmove
0x14001a7cd  or      [rsi+58h], bpl
0x14001a7d1  mov     [rsi+48h], r14
0x14001a7d5  test    rdi, rdi
0x14001a7d8  jz      loc_14001A8AC
0x14001a7de  mov     rdx, [rsp+0B8h+arg_38]
0x14001a7e6  lea     rax, [rsi+28h]
0x14001a7ea  mov     rcx, [rdi+10h]
0x14001a7ee  xor     r9d, r9d
0x14001a7f1  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001a7f6  movzx   r8d, byte ptr [rdx]
0x14001a7fa  mov     rdx, [rdx+8]
0x14001a7fe  call    cs:__imp_PtInsertEntry
0x14001a805  nop     dword ptr [rax+rax+00h]
0x14001a80a  mov     ebx, eax
0x14001a80c  test    eax, eax
0x14001a80e  jns     short loc_14001A87C
0x14001a810  mov     rax, [rsp+0B8h+arg_18]
0x14001a818  cmp     word ptr [rax], 2
0x14001a81c  mov     rax, [rsp+0B8h+arg_0]
0x14001a824  jnz     short loc_14001A82F
0x14001a826  mov     rcx, [rax+308h]
0x14001a82d  jmp     short loc_14001A836
0x14001a82f  mov     rcx, [rax+300h]
0x14001a836  mov     rdx, rsi
0x14001a839  call    PplFreeToLookasideList
0x14001a83e  mov     r13b, [rsp+0B8h+arg_8]
0x14001a846  test    r13b, r13b
0x14001a849  jz      short loc_14001A8C9
0x14001a84b  mov     cl, [rsp+0B8h+arg_28]
0x14001a852  mov     rdx, r14
0x14001a855  call    WinNatDecrementPortUsage
0x14001a85a  movzx   eax, word ptr [r15+2]
0x14001a85f  mov     r8d, ebp; NumberToClear
0x14001a862  mov     rcx, [rsp+0B8h+BitMapHeader]; BitMapHeader
0x14001a867  ror     ax, 8
0x14001a86b  movzx   edx, ax; StartingIndex
0x14001a86e  call    cs:__imp_RtlClearBits
0x14001a875  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

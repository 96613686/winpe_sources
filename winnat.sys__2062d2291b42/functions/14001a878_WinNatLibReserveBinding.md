# WinNatLibReserveBinding

- ea: `0x14001a878`
- end: `0x14001ae2b`
- name: `WinNatLibReserveBinding`
- size: `1459`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int16 *, __int16 *, int, char, char, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b9ec`

## callees

- `0x140004a80`
- `0x140008df0`
- `0x140009034`
- `0x14000b404`
- `0x14000baf8`
- `0x14000c948`
- `0x14000c9d8`
- `0x14000caa0`
- `0x1400124d0`
- `0x14001a148`
- `0x14001a520`
- `0x14001a878`
- `0x14001f680`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001adb3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001adb3`
- `ntoskrnl!RtlSetBits` at `0x14001ab5b`
- `ntoskrnl!RtlSetBits` at `0x14001ab5b`
- `ntoskrnl!RtlAreBitsClear` at `0x14001ab2a`
- `ntoskrnl!RtlAreBitsClear` at `0x14001ab2a`
- `ntoskrnl!RtlClearBits` at `0x14001ad4e`
- `ntoskrnl!RtlClearBits` at `0x14001ad4e`
- `NETIO!PtDestroyTable` at `0x14001ade7`
- `NETIO!PtDestroyTable` at `0x14001ade7`
- `NETIO!PtDeleteEntry` at `0x14001a97e`
- `NETIO!PtDeleteEntry` at `0x14001a97e`
- `NETIO!PtInsertEntry` at `0x14001a9b3`
- `NETIO!PtInsertEntry` at `0x14001acde`
- `NETIO!PtInsertEntry` at `0x14001a9b3`
- `NETIO!PtInsertEntry` at `0x14001acde`
- `NETIO!PtCreateTable` at `0x14001ac1c`
- `NETIO!PtCreateTable` at `0x14001ac1c`

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
  __int64 v18; // r8
  char v19; // al
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  char v23; // al
  char v24; // al
  __int64 v25; // r12
  __int64 BindingUnderLock; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 AddressEntry; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  struct _RTL_BITMAP *BitMapForProtocol; // r9
  __int64 v36; // rcx
  __int64 v37; // rcx
  char v38; // cl
  __int16 *Binding; // rax
  __int64 v40; // rcx
  __int16 *v41; // r9
  size_t v42; // r8
  __int64 v43; // rdx
  bool v44; // zf
  __int16 *v45; // rax
  __int16 *v46; // rsi
  __int16 *v47; // r9
  size_t v48; // r8
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // rcx
  __int64 v53; // rcx
  char v55; // [rsp+50h] [rbp-68h]
  __int64 *v56; // [rsp+58h] [rbp-60h]
  struct _RTL_BITMAP *BitMapHeader; // [rsp+60h] [rbp-58h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-50h] BYREF
  char v60; // [rsp+C8h] [rbp+10h]

  v10 = a1 + 96;
  v55 = 0;
  v11 = 0;
  v56 = a1 + 96;
  v60 = 0;
  v13 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v14 = 0;
  Table = 0;
  RtlAcquireScalableWriteLockAtDpcLevel(a1 + 104, &LockHandle);
  if ( !a2 )
  {
    v25 = 2;
    if ( a7 )
    {
      BindingUnderLock = WinNatFindBindingUnderLock((_DWORD)v56, 1, (_DWORD)a3, 0, a6, 0, a9);
      v14 = BindingUnderLock;
      if ( BindingUnderLock )
      {
        if ( (*(_BYTE *)(BindingUnderLock + 88) & 4) == 0 )
        {
          Table = -1073741788;
          v10 = v56;
          v11 = 0;
          goto LABEL_72;
        }
        BitMapHeader = 0;
        if ( *(int *)(BindingUnderLock + 64) <= 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v28, v27, v29);
        v13 = *(_QWORD *)(v14 + 72);
        if ( v13 )
          goto LABEL_52;
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v28, v27, v29);
      }
    }
    AddressEntry = WinNatLibFindAddressEntry(a1 + 160, 0, __ROR2__(a3[1], 8), 0, 0, 0);
    v13 = AddressEntry;
    if ( !AddressEntry )
    {
      Table = -1073741811;
LABEL_70:
      v11 = v60;
      goto LABEL_71;
    }
    LOBYTE(v31) = a6;
    v60 = 1;
    BitMapForProtocol = (struct _RTL_BITMAP *)WinNatGetBitMapForProtocol(AddressEntry, v31);
    BitMapHeader = BitMapForProtocol;
    if ( *a3 != 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v33, v32, v34);
      BitMapForProtocol = BitMapHeader;
    }
    v36 = 2;
    if ( *a3 != 2 )
      v36 = 4;
    if ( *(_DWORD *)&a3[v36] && !RtlAreBitsClear(BitMapForProtocol, (unsigned __int16)__ROR2__(a3[1], 8), 1u) )
    {
      Table = -1073741302;
      v11 = 1;
LABEL_71:
      v10 = v56;
      goto LABEL_72;
    }
    RtlSetBits(BitMapHeader, (unsigned __int16)__ROR2__(a3[1], 8), 1u);
    LOBYTE(v37) = a6;
    WinNatIncrementPortUsage(v37, v13);
    if ( a7 && !v14 )
    {
      Binding = WinNatLibCreateBinding(v56, 1, a3, v38, *(_QWORD *)(v13 + 112), a9);
      v14 = (__int64)Binding;
      if ( !Binding )
        goto LABEL_46;
      v41 = (__int16 *)*((_QWORD *)Binding + 13);
      v42 = 4;
      *((_DWORD *)Binding + 16) = 0;
      v43 = 2;
      v44 = *a3 == 2;
      v55 = 1;
      *v41 = *a3;
      v41[1] = a3[1];
      if ( !v44 )
        v42 = 16;
      if ( *a3 != 2 )
        v43 = 4;
      memmove(v41 + 2, &a3[v43], v42);
      *(_BYTE *)(v14 + 88) |= 5u;
      *(_QWORD *)(v14 + 72) = v13;
      Table = PtCreateTable(8 * (unsigned int)*(unsigned __int8 *)(v13 + 32), v14 + 16);
      if ( Table < 0 )
        goto LABEL_63;
    }
LABEL_52:
    v45 = WinNatLibCreateBinding(v56, a5, a4, a6, *(_QWORD *)(v13 + 112), a9);
    v46 = v45;
    if ( v45 )
    {
      v47 = (__int16 *)*((_QWORD *)v45 + 13);
      v48 = 4;
      v44 = *a3 == 2;
      *v47 = *a3;
      v47[1] = a3[1];
      if ( !v44 )
        v48 = 16;
      if ( *a3 != 2 )
        v25 = 4;
      memmove(v47 + 2, &a3[v25], v48);
      *((_BYTE *)v46 + 88) |= 1u;
      *((_QWORD *)v46 + 9) = v13;
      if ( v14 )
      {
        Table = PtInsertEntry(*(_QWORD *)(v14 + 16), *((_QWORD *)a8 + 1), *a8, 0, v46 + 20);
        if ( Table < 0 )
        {
          if ( *a4 == 2 )
            v52 = a1[97];
          else
            v52 = a1[96];
          PplFreeToLookasideList(v52, v46);
LABEL_63:
          v11 = v60;
          if ( v60 )
          {
            LOBYTE(v40) = a6;
            WinNatDecrementPortUsage(v40, v13);
            RtlClearBits(BitMapHeader, (unsigned __int16)__ROR2__(a3[1], 8), 1u);
          }
          goto LABEL_71;
        }
        *((_BYTE *)v46 + 88) |= 8u;
        *((_QWORD *)v46 + 6) = v14;
        ++*(_DWORD *)(v14 + 64);
        if ( v55 )
        {
          if ( *(_DWORD *)(v14 + 64) != 1 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v50, v49, v51);
          WinNatInsertBindingToTable(a1, v14);
          v14 = 0;
        }
      }
      WinNatInsertBindingToTable(a1, v46);
      v13 = 0;
      Table = 0;
      goto LABEL_70;
    }
LABEL_46:
    Table = -1073741670;
    goto LABEL_63;
  }
  if ( (*(_BYTE *)(a2 + 88) & 2) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
  if ( *(_DWORD *)(a2 + 92) != a5 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
  v19 = *(_BYTE *)(a2 + 88);
  if ( (v19 & 1) != 0 )
  {
    Table = -1073741270;
    goto LABEL_72;
  }
  if ( (v19 & 8) != 0 )
  {
    if ( !a7 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
    v14 = *(_QWORD *)(a2 + 48);
    if ( !v14 || (*(_BYTE *)(v14 + 88) & 4) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
    if ( *(int *)(v14 + 64) <= 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
    if ( (*(_BYTE *)(a2 + 88) & 0x10) == 0 && (int)PtDeleteEntry(*(_QWORD *)(v14 + 16), a2 + 40) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v20, v22);
    Table = PtInsertEntry(*(_QWORD *)(v14 + 16), *((_QWORD *)a8 + 1), *a8, 0, a2 + 40);
    v11 = 0;
    v23 = *(_BYTE *)(a2 + 88);
    if ( Table >= 0 )
      v24 = v23 | 1;
    else
      v24 = v23 | 0x10;
    *(_BYTE *)(a2 + 88) = v24;
    goto LABEL_71;
  }
  if ( a7 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
  *(_BYTE *)(a2 + 88) |= 1u;
  v11 = 0;
LABEL_72:
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  if ( v13 && v11 )
    WinNatLibDereferenceAddressEntry(v13);
  if ( v14 && v55 )
  {
    if ( *(_QWORD *)(v14 + 16) )
      PtDestroyTable();
    if ( *a3 == 2 )
      v53 = v10[1];
    else
      v53 = *v10;
    PplFreeToLookasideList(v53, v14);
  }
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x14001a878  mov     rax, rsp
0x14001a87b  mov     [rax+18h], rbx
0x14001a87f  mov     [rax+20h], r9
0x14001a883  mov     [rax+8], rcx
0x14001a887  push    rbp
0x14001a888  push    rsi
0x14001a889  push    rdi
0x14001a88a  push    r12
0x14001a88c  push    r13
0x14001a88e  push    r14
0x14001a890  push    r15
0x14001a892  sub     rsp, 80h
0x14001a899  mov     r12, rcx
0x14001a89c  mov     rsi, rdx
0x14001a89f  xor     ecx, ecx
0x14001a8a1  lea     rdx, [rax-50h]
0x14001a8a5  add     r12, 300h
0x14001a8ac  mov     [rax-40h], rcx
0x14001a8b0  xorps   xmm0, xmm0
0x14001a8b3  mov     [rsp+0B8h+var_68], cl
0x14001a8b7  xor     r13b, r13b
0x14001a8ba  mov     [rsp+0B8h+var_60], r12
0x14001a8bf  mov     r15, r8
0x14001a8c2  mov     [rsp+0B8h+arg_8], r13b
0x14001a8ca  lea     rcx, [r12+40h]
0x14001a8cf  xor     r14d, r14d
0x14001a8d2  movups  xmmword ptr [rax-50h], xmm0
0x14001a8d6  xor     edi, edi
0x14001a8d8  xor     ebx, ebx
0x14001a8da  call    RtlAcquireScalableWriteLockAtDpcLevel
0x14001a8df  test    rsi, rsi
0x14001a8e2  jz      loc_14001A9E5
0x14001a8e8  test    byte ptr [rsi+58h], 2
0x14001a8ec  jz      short loc_14001A8F3
0x14001a8ee  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a8f3  mov     eax, [rsp+0B8h+arg_20]
0x14001a8fa  cmp     [rsi+5Ch], eax
0x14001a8fd  jz      short loc_14001A904
0x14001a8ff  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a904  mov     al, [rsi+58h]
0x14001a907  mov     ebp, 1
0x14001a90c  test    bpl, al
0x14001a90f  jnz     loc_14001A9DB
0x14001a915  lea     r13d, [rbp+7]
0x14001a919  test    r13b, al
0x14001a91c  jnz     short loc_14001A938
0x14001a91e  cmp     [rsp+0B8h+arg_30], bl
0x14001a925  jz      short loc_14001A92C
0x14001a927  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a92c  or      [rsi+58h], bpl
0x14001a930  mov     r13b, bl
0x14001a933  jmp     loc_14001ADAE
0x14001a938  cmp     [rsp+0B8h+arg_30], bl
0x14001a93f  jnz     short loc_14001A946
0x14001a941  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a946  mov     rdi, [rsi+30h]
0x14001a94a  test    rdi, rdi
0x14001a94d  jz      short loc_14001A95B
0x14001a94f  mov     r12d, 4
0x14001a955  test    [rdi+58h], r12b
0x14001a959  jnz     short loc_14001A960
0x14001a95b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a960  cmp     [rdi+40h], ebx
0x14001a963  jg      short loc_14001A96A
0x14001a965  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a96a  mov     r12d, 10h
0x14001a970  test    [rsi+58h], r12b
0x14001a974  jnz     short loc_14001A993
0x14001a976  mov     rcx, [rdi+10h]
0x14001a97a  lea     rdx, [rsi+28h]
0x14001a97e  call    cs:__imp_PtDeleteEntry
0x14001a985  nop     dword ptr [rax+rax+00h]
0x14001a98a  test    eax, eax
0x14001a98c  jns     short loc_14001A993
0x14001a98e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a993  mov     rdx, [rsp+0B8h+arg_38]
0x14001a99b  lea     rax, [rsi+28h]
0x14001a99f  mov     rcx, [rdi+10h]
0x14001a9a3  xor     r9d, r9d
0x14001a9a6  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001a9ab  movzx   r8d, byte ptr [rdx]
0x14001a9af  mov     rdx, [rdx+8]
0x14001a9b3  call    cs:__imp_PtInsertEntry
0x14001a9ba  nop     dword ptr [rax+rax+00h]
0x14001a9bf  mov     ebx, eax
0x14001a9c1  mov     r13b, r14b
0x14001a9c4  mov     al, [rsi+58h]
0x14001a9c7  test    ebx, ebx
0x14001a9c9  jns     short loc_14001A9D6
0x14001a9cb  or      al, r12b
0x14001a9ce  mov     [rsi+58h], al
0x14001a9d1  jmp     loc_14001ADA9
0x14001a9d6  or      al, bpl
0x14001a9d9  jmp     short loc_14001A9CE
0x14001a9db  mov     ebx, 0C000022Ah
0x14001a9e0  jmp     loc_14001ADAE
0x14001a9e5  mov     ebp, 1
0x14001a9ea  mov     rsi, [rsp+0B8h+var_60]
0x14001a9ef  lea     r13d, [rbp+7]
0x14001a9f3  lea     r12d, [rbp+3]
0x14001a9f7  cmp     [rsp+0B8h+arg_30], bl
0x14001a9fe  jz      short loc_14001AA69
0x14001aa00  mov     eax, [rsp+0B8h+arg_40]
0x14001aa07  xor     r9d, r9d
0x14001aa0a  mov     dword ptr [rsp+0B8h+var_88], eax
0x14001aa0e  mov     r8, r15
0x14001aa11  mov     al, [rsp+0B8h+arg_28]
0x14001aa18  mov     edx, ebp
0x14001aa1a  mov     byte ptr [rsp+0B8h+var_90], bl
0x14001aa1e  mov     rcx, rsi
0x14001aa21  mov     byte ptr [rsp+0B8h+var_98], al
0x14001aa25  call    WinNatFindBindingUnderLock
0x14001aa2a  mov     rdi, rax
0x14001aa2d  test    rax, rax
0x14001aa30  jz      short loc_14001AA69
0x14001aa32  test    [rax+58h], r12b
0x14001aa36  jnz     short loc_14001AA48
0x14001aa38  mov     ebx, 0C0000024h
0x14001aa3d  mov     r12, rsi
0x14001aa40  mov     r13b, r14b
0x14001aa43  jmp     loc_14001ADAE
0x14001aa48  mov     [rsp+0B8h+BitMapHeader], rbx
0x14001aa4d  cmp     [rax+40h], ebx
0x14001aa50  jg      short loc_14001AA57
0x14001aa52  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001aa57  mov     r14, [rdi+48h]
0x14001aa5b  test    r14, r14
0x14001aa5e  jnz     loc_14001AC32
0x14001aa64  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001aa69  movzx   r11d, word ptr [r15+2]
0x14001aa6e  xor     r14d, r14d
0x14001aa71  mov     [rsp+0B8h+var_78], r14; __int64
0x14001aa76  xor     r9d, r9d
0x14001aa79  ror     r11w, 8
0x14001aa7e  mov     r8d, r12d
0x14001aa81  cmp     word ptr [r15], 2
0x14001aa86  mov     rdx, r12
0x14001aa89  mov     [rsp+0B8h+var_80], r14; __int64
0x14001aa8e  lea     ecx, [r14+10h]
0x14001aa92  cmovnz  r8d, ecx
0x14001aa96  mov     [rsp+0B8h+var_88], r14b; char
0x14001aa9b  mov     rcx, [rsp+0B8h+arg_0]
0x14001aaa3  cmovnz  rdx, r13
0x14001aaa7  mov     [rsp+0B8h+var_90], r11w; __int16
0x14001aaad  add     rcx, 500h; SpinLock
0x14001aab4  add     rdx, r15
0x14001aab7  mov     [rsp+0B8h+var_98], r14w; __int16
0x14001aabd  call    WinNatLibFindAddressEntry
0x14001aac2  mov     r14, rax
0x14001aac5  test    rax, rax
0x14001aac8  jnz     short loc_14001AAD4
0x14001aaca  mov     ebx, 0C000000Dh
0x14001aacf  jmp     loc_14001ADA1
0x14001aad4  mov     dl, [rsp+0B8h+arg_28]
0x14001aadb  mov     rcx, r14
0x14001aade  mov     [rsp+0B8h+arg_8], bpl
0x14001aae6  call    WinNatGetBitMapForProtocol
0x14001aaeb  cmp     word ptr [r15], 2
0x14001aaf0  mov     r9, rax
0x14001aaf3  mov     [rsp+0B8h+BitMapHeader], rax
0x14001aaf8  jz      short loc_14001AB04
0x14001aafa  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001aaff  mov     r9, [rsp+0B8h+BitMapHeader]
0x14001ab04  cmp     word ptr [r15], 2
0x14001ab09  mov     rcx, r12
0x14001ab0c  cmovnz  rcx, r13
0x14001ab10  mov     ecx, [rcx+r15]
0x14001ab14  test    ecx, ecx
0x14001ab16  jz      short loc_14001AB47
0x14001ab18  movzx   eax, word ptr [r15+2]
0x14001ab1d  mov     r8d, ebp; Length
0x14001ab20  ror     ax, 8
0x14001ab24  mov     rcx, r9; BitMapHeader
0x14001ab27  movzx   edx, ax; StartingIndex
0x14001ab2a  call    cs:__imp_RtlAreBitsClear
0x14001ab31  nop     dword ptr [rax+rax+00h]
0x14001ab36  test    al, al
0x14001ab38  jnz     short loc_14001AB47
0x14001ab3a  mov     ebx, 0C000020Ah
0x14001ab3f  mov     r13b, bpl
0x14001ab42  jmp     loc_14001ADA9
0x14001ab47  movzx   eax, word ptr [r15+2]
0x14001ab4c  mov     r8d, ebp; NumberToSet
0x14001ab4f  mov     rcx, [rsp+0B8h+BitMapHeader]; BitMapHeader
0x14001ab54  ror     ax, 8
0x14001ab58  movzx   edx, ax; StartingIndex
0x14001ab5b  call    cs:__imp_RtlSetBits
0x14001ab62  nop     dword ptr [rax+rax+00h]
0x14001ab67  mov     cl, [rsp+0B8h+arg_28]
0x14001ab6e  mov     rdx, r14
0x14001ab71  call    WinNatIncrementPortUsage
0x14001ab76  cmp     [rsp+0B8h+arg_30], bl
0x14001ab7d  jz      loc_14001AC32
0x14001ab83  test    rdi, rdi
0x14001ab86  jnz     loc_14001AC32
0x14001ab8c  mov     eax, [rsp+0B8h+arg_40]
0x14001ab93  mov     r9b, cl
0x14001ab96  mov     dword ptr [rsp+0B8h+var_90], eax
0x14001ab9a  mov     r8, r15
0x14001ab9d  mov     rax, [r14+70h]
0x14001aba1  mov     edx, ebp
0x14001aba3  mov     rcx, rsi
0x14001aba6  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001abab  call    WinNatLibCreateBinding
0x14001abb0  mov     rdi, rax
0x14001abb3  test    rax, rax
0x14001abb6  jnz     short loc_14001ABC2
0x14001abb8  mov     ebx, 0C000009Ah
0x14001abbd  jmp     loc_14001AD1E
0x14001abc2  mov     r9, [rax+68h]
0x14001abc6  mov     r8, r12
0x14001abc9  mov     [rax+40h], ebx
0x14001abcc  mov     rdx, r12
0x14001abcf  movzx   ecx, word ptr [r15]
0x14001abd3  cmp     cx, 2
0x14001abd7  mov     [rsp+0B8h+var_68], bpl
0x14001abdc  mov     [r9], cx
0x14001abe0  lea     rcx, [r9+4]; void *
0x14001abe4  movzx   eax, word ptr [r15+2]
0x14001abe9  mov     [r9+2], ax
0x14001abee  mov     eax, 10h
0x14001abf3  cmovnz  r8, rax; Size
0x14001abf7  cmp     word ptr [r15], 2
0x14001abfc  cmovnz  rdx, r13
0x14001ac00  add     rdx, r15; Src
0x14001ac03  call    memmove
0x14001ac08  or      byte ptr [rdi+58h], 5
0x14001ac0c  lea     rdx, [rdi+10h]
0x14001ac10  mov     [rdi+48h], r14
0x14001ac14  movzx   ecx, byte ptr [r14+20h]
0x14001ac19  shl     ecx, 3
0x14001ac1c  call    cs:__imp_PtCreateTable
0x14001ac23  nop     dword ptr [rax+rax+00h]
0x14001ac28  mov     ebx, eax
0x14001ac2a  test    eax, eax
0x14001ac2c  js      loc_14001AD1E
0x14001ac32  mov     eax, [rsp+0B8h+arg_40]
0x14001ac39  mov     rcx, rsi
0x14001ac3c  mov     r9b, [rsp+0B8h+arg_28]
0x14001ac44  mov     r8, [rsp+0B8h+arg_18]
0x14001ac4c  mov     edx, [rsp+0B8h+arg_20]
0x14001ac53  mov     dword ptr [rsp+0B8h+var_90], eax
0x14001ac57  mov     rax, [r14+70h]
0x14001ac5b  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001ac60  call    WinNatLibCreateBinding
0x14001ac65  mov     rsi, rax
0x14001ac68  test    rax, rax
0x14001ac6b  jz      loc_14001ABB8
0x14001ac71  mov     r9, [rax+68h]
0x14001ac75  mov     r8, r12
0x14001ac78  movzx   ecx, word ptr [r15]
0x14001ac7c  cmp     cx, 2
0x14001ac80  mov     [r9], cx
0x14001ac84  lea     rcx, [r9+4]; void *
0x14001ac88  movzx   eax, word ptr [r15+2]
0x14001ac8d  mov     [r9+2], ax
0x14001ac92  mov     eax, 10h
0x14001ac97  cmovnz  r8, rax; Size
0x14001ac9b  cmp     word ptr [r15], 2
0x14001aca0  cmovnz  r12, r13
0x14001aca4  lea     rdx, [r15+r12]; Src
0x14001aca8  call    memmove
0x14001acad  or      [rsi+58h], bpl
0x14001acb1  mov     [rsi+48h], r14
0x14001acb5  test    rdi, rdi
0x14001acb8  jz      loc_14001AD8C
0x14001acbe  mov     rdx, [rsp+0B8h+arg_38]
0x14001acc6  lea     rax, [rsi+28h]
0x14001acca  mov     rcx, [rdi+10h]
0x14001acce  xor     r9d, r9d
0x14001acd1  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001acd6  movzx   r8d, byte ptr [rdx]
0x14001acda  mov     rdx, [rdx+8]
0x14001acde  call    cs:__imp_PtInsertEntry
0x14001ace5  nop     dword ptr [rax+rax+00h]
0x14001acea  mov     ebx, eax
0x14001acec  test    eax, eax
0x14001acee  jns     short loc_14001AD5C
0x14001acf0  mov     rax, [rsp+0B8h+arg_18]
0x14001acf8  cmp     word ptr [rax], 2
0x14001acfc  mov     rax, [rsp+0B8h+arg_0]
0x14001ad04  jnz     short loc_14001AD0F
0x14001ad06  mov     rcx, [rax+308h]
0x14001ad0d  jmp     short loc_14001AD16
0x14001ad0f  mov     rcx, [rax+300h]
0x14001ad16  mov     rdx, rsi
0x14001ad19  call    PplFreeToLookasideList
0x14001ad1e  mov     r13b, [rsp+0B8h+arg_8]
0x14001ad26  test    r13b, r13b
0x14001ad29  jz      short loc_14001ADA9
0x14001ad2b  mov     cl, [rsp+0B8h+arg_28]
0x14001ad32  mov     rdx, r14
0x14001ad35  call    WinNatDecrementPortUsage
0x14001ad3a  movzx   eax, word ptr [r15+2]
0x14001ad3f  mov     r8d, ebp; NumberToClear
0x14001ad42  mov     rcx, [rsp+0B8h+BitMapHeader]; BitMapHeader
0x14001ad47  ror     ax, 8
0x14001ad4b  movzx   edx, ax; StartingIndex
0x14001ad4e  call    cs:__imp_RtlClearBits
0x14001ad55  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

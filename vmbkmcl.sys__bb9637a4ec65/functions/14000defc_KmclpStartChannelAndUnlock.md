# KmclpStartChannelAndUnlock

- ea: `0x14000defc`
- end: `0x14000e142`
- name: `KmclpStartChannelAndUnlock`
- size: `582`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14000d310`
- `0x14000ed00`
- `0x14001d4f0`

## callees

- `0x140006e00`
- `0x14000ab90`
- `0x14000d310`
- `0x14000defc`
- `0x14000e148`
- `0x14000f5c4`

## pseudocode

```c
void __fastcall KmclpStartChannelAndUnlock(PVOID Context, __int64 a2, __int64 a3)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // [rsp+20h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x21u, a3, Context, *((_DWORD *)Context + 550));
  }
  v4 = *((_DWORD *)Context + 550);
  if ( !v4 )
    goto LABEL_17;
  v5 = v4 - 1;
  if ( !v5 )
    goto LABEL_17;
  v6 = v5 - 2;
  if ( !v6 )
  {
    *((_DWORD *)Context + 550) = 5;
    v10 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
    v11 = v10 + 207;
    v10 *= 2;
    *((_QWORD *)Context + v10 + 413) = MEMORY[0xFFFFF78000000008];
    *((_BYTE *)Context + 16 * v11) = *((_BYTE *)Context + 2200);
    *((_BYTE *)Context + 8 * v10 + 3313) = *((_BYTE *)Context + 2204);
    *((_WORD *)Context + 4 * v10 + 1657) = *((_DWORD *)Context + 554);
    *((_WORD *)Context + 4 * v10 + 1658) = 1158;
    KmclpStartWaitForAction(Context);
LABEL_17:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LODWORD(v12) = *((_DWORD *)Context + 550);
      WPP_SF_qd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x23u, a3, Context, v12);
    }
    KmclUnlockChannel((__int64)Context);
    return;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    if ( v7 == 7 && *((_DWORD *)Context + 551) == 3 )
    {
      *((_DWORD *)Context + 551) = 2;
      v8 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
      v9 = v8 + 207;
      v8 *= 2;
      *((_QWORD *)Context + v8 + 413) = MEMORY[0xFFFFF78000000008];
      *((_BYTE *)Context + 16 * v9) = *((_BYTE *)Context + 2200);
      *((_BYTE *)Context + 8 * v8 + 3313) = *((_BYTE *)Context + 2204);
      *((_WORD *)Context + 4 * v8 + 1657) = *((_DWORD *)Context + 554);
      *((_WORD *)Context + 4 * v8 + 1658) = 1127;
    }
    goto LABEL_17;
  }
  KmclpResumePausedChannelAndUnlock((char *)Context, a2, a3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x22u,
      (__int64)WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
      Context);
  }
}

```

## disassembly

```asm
0x14000defc  mov     [rsp+arg_0], rbx
0x14000df01  push    rbp
0x14000df02  sub     rsp, 30h
0x14000df06  mov     rbx, rcx
0x14000df09  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df10  lea     rbp, WPP_GLOBAL_Control
0x14000df17  cmp     rcx, rbp
0x14000df1a  jz      short loc_14000DF44
0x14000df1c  mov     eax, [rcx+2Ch]
0x14000df1f  test    al, 1
0x14000df21  jz      short loc_14000DF44
0x14000df23  cmp     byte ptr [rcx+29h], 4
0x14000df27  jb      short loc_14000DF44
0x14000df29  mov     eax, [rbx+898h]
0x14000df2f  mov     edx, 21h ; '!'
0x14000df34  mov     rcx, [rcx+18h]
0x14000df38  mov     r9, rbx
0x14000df3b  mov     dword ptr [rsp+38h+var_18], eax
0x14000df3f  call    WPP_SF_qd
0x14000df44  mov     ecx, [rbx+898h]
0x14000df4a  test    ecx, ecx
0x14000df4c  jz      loc_14000E0FA
0x14000df52  sub     ecx, 1
0x14000df55  jz      loc_14000E0FA
0x14000df5b  sub     ecx, 2
0x14000df5e  jz      loc_14000E06D
0x14000df64  sub     ecx, 1
0x14000df67  jz      loc_14000E023
0x14000df6d  sub     ecx, 1
0x14000df70  jz      loc_14000E0FA
0x14000df76  sub     ecx, 2
0x14000df79  jz      loc_14000E0FA
0x14000df7f  sub     ecx, 3
0x14000df82  jz      loc_14000E0FA
0x14000df88  cmp     ecx, 1
0x14000df8b  jnz     loc_14000E0FA
0x14000df91  cmp     dword ptr [rbx+89Ch], 3
0x14000df98  jnz     loc_14000E0FA
0x14000df9e  mov     dword ptr [rbx+89Ch], 2
0x14000dfa8  lock xadd [rbx+0CE0h], ecx
0x14000dfb0  inc     ecx
0x14000dfb2  mov     eax, 2AAAAAABh
0x14000dfb7  imul    ecx
0x14000dfb9  sar     edx, 2
0x14000dfbc  mov     eax, edx
0x14000dfbe  shr     eax, 1Fh
0x14000dfc1  add     edx, eax
0x14000dfc3  lea     eax, [rdx+rdx*2]
0x14000dfc6  shl     eax, 3
0x14000dfc9  sub     ecx, eax
0x14000dfcb  mov     rax, ds:0FFFFF78000000008h
0x14000dfd5  movsxd  rcx, ecx
0x14000dfd8  mov     rdx, rcx
0x14000dfdb  add     rcx, 0CFh
0x14000dfe2  add     rdx, rdx
0x14000dfe5  add     rcx, rcx
0x14000dfe8  mov     [rbx+rdx*8+0CE8h], rax
0x14000dff0  mov     al, [rbx+898h]
0x14000dff6  mov     [rbx+rcx*8], al
0x14000dff9  mov     al, [rbx+89Ch]
0x14000dfff  mov     [rbx+rdx*8+0CF1h], al
0x14000e006  mov     eax, [rbx+8A8h]
0x14000e00c  mov     [rbx+rdx*8+0CF2h], ax
0x14000e014  mov     word ptr [rbx+rdx*8+0CF4h], 467h
0x14000e01e  jmp     loc_14000E0FA
0x14000e023  mov     rcx, rbx; Context
0x14000e026  call    KmclpResumePausedChannelAndUnlock
0x14000e02b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e032  cmp     rcx, rbp
0x14000e035  jz      loc_14000E136
0x14000e03b  mov     eax, [rcx+2Ch]
0x14000e03e  test    al, 1
0x14000e040  jz      loc_14000E136
0x14000e046  cmp     byte ptr [rcx+29h], 4
0x14000e04a  jb      loc_14000E136
0x14000e050  mov     rcx, [rcx+18h]
0x14000e054  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000e05b  mov     edx, 22h ; '"'
0x14000e060  mov     r9, rbx
0x14000e063  call    WPP_SF_q
0x14000e068  jmp     loc_14000E136
0x14000e06d  mov     dword ptr [rbx+898h], 5
0x14000e077  mov     ecx, 1
0x14000e07c  lock xadd [rbx+0CE0h], ecx
0x14000e084  inc     ecx
0x14000e086  mov     eax, 2AAAAAABh
0x14000e08b  imul    ecx
0x14000e08d  sar     edx, 2
0x14000e090  mov     eax, edx
0x14000e092  shr     eax, 1Fh
0x14000e095  add     edx, eax
0x14000e097  lea     eax, [rdx+rdx*2]
0x14000e09a  shl     eax, 3
0x14000e09d  sub     ecx, eax
0x14000e09f  mov     rax, ds:0FFFFF78000000008h
0x14000e0a9  movsxd  rcx, ecx
0x14000e0ac  mov     rdx, rcx
0x14000e0af  add     rcx, 0CFh
0x14000e0b6  add     rdx, rdx
0x14000e0b9  add     rcx, rcx
0x14000e0bc  mov     [rbx+rdx*8+0CE8h], rax
0x14000e0c4  mov     al, [rbx+898h]
0x14000e0ca  mov     [rbx+rcx*8], al
0x14000e0cd  mov     rcx, rbx; Context
0x14000e0d0  mov     al, [rbx+89Ch]
0x14000e0d6  mov     [rbx+rdx*8+0CF1h], al
0x14000e0dd  mov     eax, [rbx+8A8h]
0x14000e0e3  mov     [rbx+rdx*8+0CF2h], ax
0x14000e0eb  mov     word ptr [rbx+rdx*8+0CF4h], 486h
0x14000e0f5  call    KmclpStartWaitForAction
0x14000e0fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e101  cmp     rcx, rbp
0x14000e104  jz      short loc_14000E12E
0x14000e106  mov     eax, [rcx+2Ch]
0x14000e109  test    al, 1
0x14000e10b  jz      short loc_14000E12E
0x14000e10d  cmp     byte ptr [rcx+29h], 4
0x14000e111  jb      short loc_14000E12E
0x14000e113  mov     eax, [rbx+898h]
0x14000e119  mov     edx, 23h ; '#'
0x14000e11e  mov     rcx, [rcx+18h]
0x14000e122  mov     r9, rbx
0x14000e125  mov     dword ptr [rsp+38h+var_18], eax
0x14000e129  call    WPP_SF_qd
0x14000e12e  mov     rcx, rbx
0x14000e131  call    KmclUnlockChannel
0x14000e136  mov     rbx, [rsp+38h+arg_0]
0x14000e13b  add     rsp, 30h
0x14000e13f  pop     rbp
0x14000e140  retn
```

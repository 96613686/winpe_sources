# WinNatLibCreateAddress

- ea: `0x1400085d0`
- end: `0x140008921`
- name: `WinNatLibCreateAddress`
- size: `849`
- prototype: `__int64 __fastcall(__int64, __int64, char, unsigned __int16, unsigned __int16, _DWORD *Src, unsigned __int8, _DWORD *, _BYTE *, _OWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140007bb0`
- `0x14000ee40`
- `0x14001448c`

## callees

- `0x1400085d0`
- `0x14000a638`
- `0x14000b404`
- `0x14000c9d8`
- `0x14000caa0`
- `0x14000e8a4`
- `0x14001f140`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400088ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400088ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008901`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008901`
- `ntoskrnl!ExAllocatePool2` at `0x14000868e`
- `ntoskrnl!ExAllocatePool2` at `0x14000868e`
- `ntoskrnl!RtlClearAllBits` at `0x140008773`
- `ntoskrnl!RtlClearAllBits` at `0x1400087d5`
- `ntoskrnl!RtlClearAllBits` at `0x14000882c`
- `ntoskrnl!RtlClearAllBits` at `0x140008773`
- `ntoskrnl!RtlClearAllBits` at `0x1400087d5`
- `ntoskrnl!RtlClearAllBits` at `0x14000882c`
- `ntoskrnl!RtlSetBits` at `0x140008789`
- `ntoskrnl!RtlSetBits` at `0x1400087aa`
- `ntoskrnl!RtlSetBits` at `0x1400087eb`
- `ntoskrnl!RtlSetBits` at `0x14000880b`
- `ntoskrnl!RtlSetBits` at `0x140008843`
- `ntoskrnl!RtlSetBits` at `0x140008789`
- `ntoskrnl!RtlSetBits` at `0x1400087aa`
- `ntoskrnl!RtlSetBits` at `0x1400087eb`
- `ntoskrnl!RtlSetBits` at `0x14000880b`
- `ntoskrnl!RtlSetBits` at `0x140008843`

## pseudocode

```c
__int64 __fastcall WinNatLibCreateAddress(
        __int64 a1,
        __int64 a2,
        char a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        _DWORD *Src,
        unsigned __int8 a7,
        _DWORD *a8,
        _BYTE *a9,
        _OWORD *a10)
{
  __int64 AddressEntry; // rax
  __int64 Pool2; // rax
  __int64 v17; // rdi
  __int128 v18; // xmm0
  int v19; // eax
  int v20; // eax
  _QWORD *v21; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-68h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( a5 < a4 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  AddressEntry = WinNatLibFindAddressEntry((PKSPIN_LOCK)(a1 + 1280), a5, 0, a3, (__int64)a8, (__int64)a9);
  if ( AddressEntry )
  {
    WinNatLibDereferenceAddressEntry(AddressEntry);
    return 3221226026LL;
  }
  else
  {
    Pool2 = ExAllocatePool2(64, a7 + 24792LL, 1885424727);
    v17 = Pool2;
    if ( Pool2 )
    {
      *(_BYTE *)(Pool2 + 212) |= 1u;
      *(_QWORD *)Pool2 = 1;
      *(_QWORD *)(Pool2 + 24) = Pool2 + 24792;
      *(_WORD *)(Pool2 + 108) = a5;
      *(_WORD *)(Pool2 + 106) = a4;
      if ( a9 )
        *(_BYTE *)(Pool2 + 207) = *a9;
      if ( a7 == 4 && !*Src )
        *(_BYTE *)(Pool2 + 212) &= ~1u;
      if ( a10 )
      {
        *(_OWORD *)(Pool2 + 126) = *a10;
        *(_OWORD *)(Pool2 + 142) = a10[1];
        *(_OWORD *)(Pool2 + 158) = a10[2];
        *(_OWORD *)(Pool2 + 174) = a10[3];
        v18 = a10[4];
        *(_BYTE *)(Pool2 + 206) = 1;
        *(_OWORD *)(Pool2 + 190) = v18;
      }
      if ( a8 )
      {
        *(_DWORD *)(Pool2 + 120) = *a8;
        *(_BYTE *)(Pool2 + 124) = 1;
      }
      if ( a9 && !*a9 )
        goto LABEL_22;
      *(_DWORD *)(Pool2 + 40) = 0x10000;
      *(_QWORD *)(Pool2 + 48) = Pool2 + 216;
      RtlClearAllBits((PRTL_BITMAP)(Pool2 + 40));
      RtlSetBits((PRTL_BITMAP)(v17 + 40), 0, *(unsigned __int16 *)(v17 + 106));
      v19 = *(unsigned __int16 *)(v17 + 108);
      if ( (_WORD)v19 != 0xFFFF )
        RtlSetBits((PRTL_BITMAP)(v17 + 40), v19 + 1, 0xFFFF - v19);
      if ( !a9 || !*a9 )
      {
LABEL_22:
        *(_DWORD *)(v17 + 64) = 0x10000;
        *(_QWORD *)(v17 + 72) = v17 + 8408;
        RtlClearAllBits((PRTL_BITMAP)(v17 + 64));
        RtlSetBits((PRTL_BITMAP)(v17 + 64), 0, *(unsigned __int16 *)(v17 + 106));
        v20 = *(unsigned __int16 *)(v17 + 108);
        if ( (_WORD)v20 != 0xFFFF )
          RtlSetBits((PRTL_BITMAP)(v17 + 64), v20 + 1, 0xFFFF - v20);
      }
      *(_DWORD *)(v17 + 88) = 0x10000;
      *(_QWORD *)(v17 + 96) = v17 + 16600;
      RtlClearAllBits((PRTL_BITMAP)(v17 + 88));
      RtlSetBits((PRTL_BITMAP)(v17 + 88), 0, 0x3E8u);
      memmove(*(void **)(v17 + 24), Src, a7);
      *(_BYTE *)(v17 + 32) = a7;
      *(_QWORD *)(v17 + 112) = a2;
      if ( (unsigned __int8)RoReferenceEx(*(_QWORD *)(a2 + 408) + 24LL) )
      {
        RtlAcquireScalableWriteLock(a2, &LockHandle);
        if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 336)) <= 1 )
          __fastfail(0xEu);
        v21 = *(_QWORD **)(a2 + 352);
        if ( *v21 != a2 + 344 )
          __fastfail(3u);
        *(_QWORD *)(v17 + 8) = a2 + 344;
        *(_QWORD *)(v17 + 16) = v21;
        *v21 = v17 + 8;
        *(_QWORD *)(a2 + 352) = v17 + 8;
        _InterlockedAdd(
          (volatile signed __int32 *)(a2 + 368),
          *(unsigned __int16 *)(v17 + 108) - *(unsigned __int16 *)(v17 + 106) + 1);
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      else
      {
        ExFreePoolWithTag((PVOID)v17, 0);
      }
      return 0;
    }
    else
    {
      return 3221225626LL;
    }
  }
}

```

## disassembly

```asm
0x1400085d0  push    rbx
0x1400085d2  push    rbp
0x1400085d3  push    rsi
0x1400085d4  push    rdi
0x1400085d5  push    r12
0x1400085d7  push    r13
0x1400085d9  push    r14
0x1400085db  push    r15
0x1400085dd  sub     rsp, 78h
0x1400085e1  movzx   r14d, [rsp+0B8h+arg_20]
0x1400085ea  xor     eax, eax
0x1400085ec  xor     r13d, r13d
0x1400085ef  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x1400085f4  xorps   xmm0, xmm0
0x1400085f7  movzx   ebp, r9w
0x1400085fb  mov     dil, r8b
0x1400085fe  mov     rsi, rdx
0x140008601  mov     rbx, rcx
0x140008604  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140008609  cmp     r14w, r9w
0x14000860d  jnb     short loc_140008614
0x14000860f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140008614  mov     r15, [rsp+0B8h+arg_38]
0x14000861c  lea     rcx, [rbx+500h]; SpinLock
0x140008623  mov     rbx, [rsp+0B8h+arg_40]
0x14000862b  xor     eax, eax
0x14000862d  movzx   r12d, [rsp+0B8h+arg_30]
0x140008636  movzx   r9d, bp
0x14000863a  mov     rdx, [rsp+0B8h+Src]
0x140008642  mov     r8b, r12b
0x140008645  mov     [rsp+0B8h+var_78], rbx; __int64
0x14000864a  mov     [rsp+0B8h+var_80], r15; __int64
0x14000864f  mov     [rsp+0B8h+var_88], dil; char
0x140008654  mov     [rsp+0B8h+var_90], ax; __int16
0x140008659  mov     [rsp+0B8h+var_98], r14w; __int16
0x14000865f  call    WinNatLibFindAddressEntry
0x140008664  test    rax, rax
0x140008667  jz      short loc_14000867B
0x140008669  mov     rcx, rax
0x14000866c  call    WinNatLibDereferenceAddressEntry
0x140008671  mov     eax, 0C000022Ah
0x140008676  jmp     loc_14000890F
0x14000867b  lea     rdx, [r12+60D8h]
0x140008683  mov     ecx, 40h ; '@'
0x140008688  mov     r8d, 70614C57h
0x14000868e  call    cs:__imp_ExAllocatePool2
0x140008695  nop     dword ptr [rax+rax+00h]
0x14000869a  mov     rdi, rax
0x14000869d  test    rax, rax
0x1400086a0  jnz     short loc_1400086AC
0x1400086a2  mov     eax, 0C000009Ah
0x1400086a7  jmp     loc_14000890F
0x1400086ac  or      byte ptr [rdi+0D4h], 1
0x1400086b3  mov     qword ptr [rax], 1
0x1400086ba  add     rax, 60D8h
0x1400086c0  mov     [rdi+18h], rax
0x1400086c4  mov     [rdi+6Ch], r14w
0x1400086c9  mov     [rdi+6Ah], bp
0x1400086cd  test    rbx, rbx
0x1400086d0  jz      short loc_1400086DA
0x1400086d2  mov     al, [rbx]
0x1400086d4  mov     [rdi+0CFh], al
0x1400086da  cmp     r12b, 4
0x1400086de  jnz     short loc_1400086F5
0x1400086e0  mov     rax, [rsp+0B8h+Src]
0x1400086e8  mov     eax, [rax]
0x1400086ea  test    eax, eax
0x1400086ec  jnz     short loc_1400086F5
0x1400086ee  and     byte ptr [rdi+0D4h], 0FEh
0x1400086f5  mov     rax, [rsp+0B8h+arg_48]
0x1400086fd  test    rax, rax
0x140008700  jz      short loc_14000873C
0x140008702  movups  xmm0, xmmword ptr [rax]
0x140008705  movups  xmmword ptr [rdi+7Eh], xmm0
0x140008709  movups  xmm1, xmmword ptr [rax+10h]
0x14000870d  movups  xmmword ptr [rdi+8Eh], xmm1
0x140008714  movups  xmm0, xmmword ptr [rax+20h]
0x140008718  movups  xmmword ptr [rdi+9Eh], xmm0
0x14000871f  movups  xmm1, xmmword ptr [rax+30h]
0x140008723  movups  xmmword ptr [rdi+0AEh], xmm1
0x14000872a  movups  xmm0, xmmword ptr [rax+40h]
0x14000872e  mov     byte ptr [rdi+0CEh], 1
0x140008735  movups  xmmword ptr [rdi+0BEh], xmm0
0x14000873c  test    r15, r15
0x14000873f  jz      short loc_14000874B
0x140008741  mov     eax, [r15]
0x140008744  mov     [rdi+78h], eax
0x140008747  mov     byte ptr [rdi+7Ch], 1
0x14000874b  mov     ebp, 0FFFFh
0x140008750  lea     r15d, [rbp+1]
0x140008754  test    rbx, rbx
0x140008757  jz      short loc_14000875E
0x140008759  cmp     [rbx], r13b
0x14000875c  jz      short loc_1400087C0
0x14000875e  lea     r14, [rdi+28h]
0x140008762  lea     rax, [rdi+0D8h]
0x140008769  mov     [r14], r15d
0x14000876c  mov     rcx, r14; BitMapHeader
0x14000876f  mov     [rdi+30h], rax
0x140008773  call    cs:__imp_RtlClearAllBits
0x14000877a  nop     dword ptr [rax+rax+00h]
0x14000877f  movzx   r8d, word ptr [rdi+6Ah]; NumberToSet
0x140008784  xor     edx, edx; StartingIndex
0x140008786  mov     rcx, r14; BitMapHeader
0x140008789  call    cs:__imp_RtlSetBits
0x140008790  nop     dword ptr [rax+rax+00h]
0x140008795  movzx   eax, word ptr [rdi+6Ch]
0x140008799  cmp     ax, bp
0x14000879c  jz      short loc_1400087B6
0x14000879e  mov     r8d, ebp
0x1400087a1  lea     edx, [rax+1]; StartingIndex
0x1400087a4  sub     r8d, eax; NumberToSet
0x1400087a7  mov     rcx, r14; BitMapHeader
0x1400087aa  call    cs:__imp_RtlSetBits
0x1400087b1  nop     dword ptr [rax+rax+00h]
0x1400087b6  test    rbx, rbx
0x1400087b9  jz      short loc_1400087C0
0x1400087bb  cmp     [rbx], r13b
0x1400087be  jnz     short loc_140008817
0x1400087c0  lea     rbx, [rdi+40h]
0x1400087c4  lea     rax, [rdi+20D8h]
0x1400087cb  mov     [rbx], r15d
0x1400087ce  mov     rcx, rbx; BitMapHeader
0x1400087d1  mov     [rdi+48h], rax
0x1400087d5  call    cs:__imp_RtlClearAllBits
0x1400087dc  nop     dword ptr [rax+rax+00h]
0x1400087e1  movzx   r8d, word ptr [rdi+6Ah]; NumberToSet
0x1400087e6  xor     edx, edx; StartingIndex
0x1400087e8  mov     rcx, rbx; BitMapHeader
0x1400087eb  call    cs:__imp_RtlSetBits
0x1400087f2  nop     dword ptr [rax+rax+00h]
0x1400087f7  movzx   eax, word ptr [rdi+6Ch]
0x1400087fb  cmp     ax, bp
0x1400087fe  jz      short loc_140008817
0x140008800  sub     ebp, eax
0x140008802  lea     edx, [rax+1]; StartingIndex
0x140008805  mov     r8d, ebp; NumberToSet
0x140008808  mov     rcx, rbx; BitMapHeader
0x14000880b  call    cs:__imp_RtlSetBits
0x140008812  nop     dword ptr [rax+rax+00h]
0x140008817  lea     rbx, [rdi+58h]
0x14000881b  lea     rax, [rdi+40D8h]
0x140008822  mov     [rbx], r15d
0x140008825  mov     rcx, rbx; BitMapHeader
0x140008828  mov     [rdi+60h], rax
0x14000882c  call    cs:__imp_RtlClearAllBits
0x140008833  nop     dword ptr [rax+rax+00h]
0x140008838  xor     edx, edx; StartingIndex
0x14000883a  mov     r8d, 3E8h; NumberToSet
0x140008840  mov     rcx, rbx; BitMapHeader
0x140008843  call    cs:__imp_RtlSetBits
0x14000884a  nop     dword ptr [rax+rax+00h]
0x14000884f  mov     rdx, [rsp+0B8h+Src]; Src
0x140008857  mov     r8, r12; Size
0x14000885a  mov     rcx, [rdi+18h]; void *
0x14000885e  call    memmove
0x140008863  mov     [rdi+20h], r12b
0x140008867  mov     [rdi+70h], rsi
0x14000886b  mov     rcx, [rsi+198h]
0x140008872  add     rcx, 18h
0x140008876  call    RoReferenceEx
0x14000887b  test    al, al
0x14000887d  jz      short loc_1400088FC
0x14000887f  lea     rdx, [rsp+0B8h+LockHandle]
0x140008884  mov     rcx, rsi
0x140008887  call    RtlAcquireScalableWriteLock
0x14000888c  mov     r8d, 1
0x140008892  mov     eax, r8d
0x140008895  lock xadd [rsi+150h], rax
0x14000889e  add     rax, r8
0x1400088a1  cmp     rax, r8
0x1400088a4  jg      short loc_1400088AC
0x1400088a6  lea     ecx, [r8+0Dh]
0x1400088aa  int     29h; Win8: RtlFailFast(ecx)
0x1400088ac  lea     rcx, [rsi+158h]
0x1400088b3  mov     rdx, [rcx+8]
0x1400088b7  cmp     [rdx], rcx
0x1400088ba  jz      short loc_1400088C3
0x1400088bc  mov     ecx, 3
0x1400088c1  int     29h; Win8: RtlFailFast(ecx)
0x1400088c3  lea     rax, [rdi+8]
0x1400088c7  mov     [rax], rcx
0x1400088ca  mov     [rax+8], rdx
0x1400088ce  mov     [rdx], rax
0x1400088d1  mov     [rcx+8], rax
0x1400088d5  movzx   ecx, word ptr [rdi+6Ch]
0x1400088d9  movzx   eax, word ptr [rdi+6Ah]
0x1400088dd  sub     ecx, eax
0x1400088df  add     ecx, r8d
0x1400088e2  lock add [rsi+170h], ecx
0x1400088e9  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x1400088ee  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400088f5  nop     dword ptr [rax+rax+00h]
0x1400088fa  jmp     short loc_14000890D
0x1400088fc  xor     edx, edx; Tag
0x1400088fe  mov     rcx, rdi; P
0x140008901  call    cs:__imp_ExFreePoolWithTag
0x140008908  nop     dword ptr [rax+rax+00h]
0x14000890d  xor     eax, eax
0x14000890f  add     rsp, 78h
0x140008913  pop     r15
0x140008915  pop     r14
0x140008917  pop     r13
0x140008919  pop     r12
0x14000891b  pop     rdi
0x14000891c  pop     rsi
0x14000891d  pop     rbp
0x14000891e  pop     rbx
0x14000891f  retn
```

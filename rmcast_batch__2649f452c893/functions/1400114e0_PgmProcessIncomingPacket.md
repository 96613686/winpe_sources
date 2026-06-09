# PgmProcessIncomingPacket

- ea: `0x1400114e0`
- end: `0x1400118fb`
- name: `PgmProcessIncomingPacket`
- size: `1051`
- prototype: `__int64 __fastcall(__int64, const __m128i *, __int64, __int64, unsigned int, __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140014540`

## callees

- `0x1400050ac`
- `0x1400052e4`
- `0x1400114e0`
- `0x140012efc`
- `0x140013d90`
- `0x140015214`
- `0x14001ab38`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400117fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011859`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011879`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011859`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011879`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400117b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011810`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400117b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011810`

## pseudocode

```c
__int64 __fastcall PgmProcessIncomingPacket(
        __int64 a1,
        const __m128i *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned __int8 a7)
{
  unsigned int v9; // ebp
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // edi
  __int64 v14; // r8
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned __int32 v23; // r15d
  KIRQL v24; // al
  struct _DEVICE_OBJECT *v25; // rdx
  struct _DEVICE_OBJECT **p_NextDevice; // rcx
  KIRQL v27; // dl
  KIRQL v28; // r10
  struct _DEVICE_OBJECT *v29; // r8
  struct _DEVICE_OBJECT **v30; // rdx

  if ( a7 )
  {
    if ( ((a7 - 8) & 0xFD) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 149, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a7, a5);
      return 3221226011LL;
    }
    v9 = a5;
    v14 = 36;
    if ( a5 < 0x24 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        return 3221226011LL;
      v11 = 150;
      goto LABEL_66;
    }
    v19 = *(_QWORD *)(a6 + 20);
    v20 = *(_QWORD *)(a6 + 28);
    if ( (_WORD)v19 != 256 || (v21 = HIDWORD(v19), !(_DWORD)v21) || (_WORD)v20 != 256 || !HIDWORD(v20) )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        return 3221226011LL;
      v11 = 151;
      goto LABEL_66;
    }
    if ( a7 == 10 )
    {
      if ( !a2 || a2[1].m128i_i32[0] != 1381188947 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 152, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a2);
        v13 = -1073741285;
        goto LABEL_60;
      }
      v22 = ReceiverProcessNakNcfPacket(a1, (_DWORD)a2, a5, a6, 10);
    }
    else
    {
      if ( !a2[2].m128i_i64[1] )
      {
        v13 = 0;
        if ( *(_DWORD *)a4 == 1 && *(_WORD *)(a4 + 4) == 14 && *(_WORD *)(a4 + 6) == 2 )
        {
          v23 = _byteswap_ulong(*(_DWORD *)(a4 + 10));
          if ( v23 )
          {
            v24 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
            v25 = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.32;
            while ( 1 )
            {
              v25 = *(struct _DEVICE_OBJECT **)&v25->Type;
              if ( v25 == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
                break;
              p_NextDevice = &v25->NextDevice;
              while ( 1 )
              {
                p_NextDevice = (struct _DEVICE_OBJECT **)*p_NextDevice;
                if ( p_NextDevice == &v25->NextDevice )
                  break;
                if ( *((_DWORD *)p_NextDevice + 4) == v23 )
                {
                  v27 = v24;
                  goto LABEL_59;
                }
              }
            }
            KeReleaseSpinLock(&SpinLock, v24);
            v28 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
            v29 = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.32;
            while ( 1 )
            {
              v29 = *(struct _DEVICE_OBJECT **)&v29->Type;
              if ( v29 == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
                break;
              v30 = &v29->NextDevice;
              while ( 1 )
              {
                v30 = (struct _DEVICE_OBJECT **)*v30;
                if ( v30 == &v29->NextDevice )
                  break;
                if ( (*((_DWORD *)v30 + 5) & (_DWORD)v30[2]) == (v23 & *((_DWORD *)v30 + 5)) )
                {
                  KeReleaseSpinLock(&SpinLock, v28);
                  v22 = ReceiverProcessNakNcfPacket(a1, (_DWORD)a2, a5, a6, a7);
                  goto LABEL_40;
                }
              }
            }
            v27 = v28;
LABEL_59:
            KeReleaseSpinLock(&SpinLock, v27);
          }
        }
        goto LABEL_60;
      }
      v22 = SenderProcessNakPacket(v21, a2, a5, a6);
    }
LABEL_40:
    v13 = v22;
LABEL_60:
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
      return v13;
    v17 = a7;
    v16 = 153;
    goto LABEL_11;
  }
  v9 = a5;
  if ( a5 >= 0x24 )
  {
    if ( !a2 || a2[1].m128i_i32[0] != 1381188947 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 148, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a2);
      return (unsigned int)-1073741285;
    }
    v12 = a2[3].m128i_i64[0];
    a2[12] = _mm_add_epi64(_mm_unpacklo_epi64((__m128i)a5, (__m128i)1uLL), _mm_loadu_si128(a2 + 12));
    *(_QWORD *)(v12 + 736) = WPP_MAIN_CB.Dpc.SystemArgument1;
    v13 = ProcessSpmPacket(a1, a2, a5, a6);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
      return v13;
    v16 = 147;
    v17 = 0;
LABEL_11:
    WPP_SF_DqdD(v15->AttachedDevice, v16, v14, v17, a2, v9, v13);
    return v13;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
    return 3221226011LL;
  v11 = 146;
LABEL_66:
  WPP_SF_Dd(v10->AttachedDevice, v11, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, v9, 36);
  return 3221226011LL;
}

```

## disassembly

```asm
0x1400114e0  push    rbx
0x1400114e2  push    rbp
0x1400114e3  push    rsi
0x1400114e4  push    rdi
0x1400114e5  push    r12
0x1400114e7  push    r13
0x1400114e9  push    r14
0x1400114eb  push    r15
0x1400114ed  sub     rsp, 48h
0x1400114f1  movzx   r14d, [rsp+88h+arg_30]
0x1400114fa  mov     rsi, rdx
0x1400114fd  mov     r12, rcx
0x140011500  test    r14b, r14b
0x140011503  jnz     loc_140011622
0x140011509  mov     ebp, [rsp+88h+arg_20]
0x140011510  mov     r8d, 24h ; '$'
0x140011516  cmp     ebp, r8d
0x140011519  jnb     short loc_140011546
0x14001151b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011522  lea     rbx, WPP_GLOBAL_Control
0x140011529  cmp     rcx, rbx
0x14001152c  jz      loc_1400118E4
0x140011532  mov     eax, [rcx+2Ch]
0x140011535  test    al, 2
0x140011537  jz      loc_1400118E4
0x14001153d  lea     edx, [r8+6Eh]
0x140011541  jmp     loc_1400118CC
0x140011546  test    rsi, rsi
0x140011549  jz      loc_1400115E4
0x14001154f  cmp     dword ptr [rdx+10h], 52534553h
0x140011556  jnz     loc_1400115E4
0x14001155c  mov     r9, [rsp+88h+arg_28]
0x140011564  mov     ecx, 1
0x140011569  movq    xmm1, rbp
0x14001156e  mov     r8d, ebp
0x140011571  movq    xmm0, rcx
0x140011576  mov     rcx, [rdx+30h]
0x14001157a  punpcklqdq xmm1, xmm0
0x14001157e  movdqu  xmm0, xmmword ptr [rdx+0C0h]
0x140011586  paddq   xmm1, xmm0
0x14001158a  movdqu  xmmword ptr [rdx+0C0h], xmm1
0x140011592  mov     rax, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x140011599  mov     [rcx+2E0h], rax
0x1400115a0  mov     rcx, r12
0x1400115a3  call    ProcessSpmPacket
0x1400115a8  mov     edi, eax
0x1400115aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115b1  lea     rbx, WPP_GLOBAL_Control
0x1400115b8  cmp     rcx, rbx
0x1400115bb  jz      short loc_14001161B
0x1400115bd  mov     eax, [rcx+2Ch]
0x1400115c0  test    al, 10h
0x1400115c2  jz      short loc_14001161B
0x1400115c4  mov     edx, 93h
0x1400115c9  xor     r9d, r9d
0x1400115cc  mov     rcx, [rcx+18h]
0x1400115d0  mov     [rsp+88h+var_58], edi
0x1400115d4  mov     [rsp+88h+var_60], ebp
0x1400115d8  mov     [rsp+88h+var_68], rsi
0x1400115dd  call    WPP_SF_DqdD
0x1400115e2  jmp     short loc_14001161B
0x1400115e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115eb  lea     rbx, WPP_GLOBAL_Control
0x1400115f2  cmp     rcx, rbx
0x1400115f5  jz      short loc_140011616
0x1400115f7  mov     eax, [rcx+2Ch]
0x1400115fa  test    al, 2
0x1400115fc  jz      short loc_140011616
0x1400115fe  mov     rcx, [rcx+18h]
0x140011602  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140011609  mov     edx, 94h
0x14001160e  mov     r9, rsi
0x140011611  call    WPP_SF_q
0x140011616  mov     edi, 0C000021Bh
0x14001161b  mov     eax, edi
0x14001161d  jmp     loc_1400118E9
0x140011622  lea     eax, [r14-8]
0x140011626  test    al, 0FDh
0x140011628  jz      short loc_140011674
0x14001162a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011631  lea     rbx, WPP_GLOBAL_Control
0x140011638  cmp     rcx, rbx
0x14001163b  jz      loc_1400118E4
0x140011641  mov     eax, [rcx+2Ch]
0x140011644  test    al, 2
0x140011646  jz      loc_1400118E4
0x14001164c  mov     eax, [rsp+88h+arg_20]
0x140011653  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14001165a  mov     rcx, [rcx+18h]
0x14001165e  mov     r9d, r14d
0x140011661  mov     edx, 95h
0x140011666  mov     dword ptr [rsp+88h+var_68], eax
0x14001166a  call    WPP_SF_Dd
0x14001166f  jmp     loc_1400118E4
0x140011674  mov     ebp, [rsp+88h+arg_20]
0x14001167b  mov     r8d, 24h ; '$'
0x140011681  cmp     ebp, r8d
0x140011684  jnb     short loc_1400116B1
0x140011686  mov     rcx, cs:WPP_GLOBAL_Control
0x14001168d  lea     rbx, WPP_GLOBAL_Control
0x140011694  cmp     rcx, rbx
0x140011697  jz      loc_1400118E4
0x14001169d  mov     eax, [rcx+2Ch]
0x1400116a0  test    al, 2
0x1400116a2  jz      loc_1400118E4
0x1400116a8  lea     edx, [r8+72h]
0x1400116ac  jmp     loc_1400118CC
0x1400116b1  mov     r13, [rsp+88h+arg_28]
0x1400116b9  mov     edx, 100h
0x1400116be  mov     rcx, [r13+14h]
0x1400116c2  mov     rax, [r13+1Ch]
0x1400116c6  cmp     dx, cx
0x1400116c9  jnz     loc_1400118AD
0x1400116cf  shr     rcx, 20h
0x1400116d3  test    ecx, ecx
0x1400116d5  jz      loc_1400118AD
0x1400116db  cmp     dx, ax
0x1400116de  jnz     loc_1400118AD
0x1400116e4  shr     rax, 20h
0x1400116e8  test    eax, eax
0x1400116ea  jz      loc_1400118AD
0x1400116f0  lea     rbx, WPP_GLOBAL_Control
0x1400116f7  cmp     r14b, 0Ah
0x1400116fb  jnz     short loc_140011758
0x1400116fd  test    rsi, rsi
0x140011700  jz      short loc_140011723
0x140011702  cmp     dword ptr [rsi+10h], 52534553h
0x140011709  jnz     short loc_140011723
0x14001170b  mov     byte ptr [rsp+88h+var_68], r14b
0x140011710  mov     r9, r13
0x140011713  mov     r8d, ebp
0x140011716  mov     rdx, rsi
0x140011719  mov     rcx, r12
0x14001171c  call    ReceiverProcessNakNcfPacket
0x140011721  jmp     short loc_14001176D
0x140011723  mov     rcx, cs:WPP_GLOBAL_Control
0x14001172a  cmp     rcx, rbx
0x14001172d  jz      short loc_14001174E
0x14001172f  mov     eax, [rcx+2Ch]
0x140011732  test    al, 2
0x140011734  jz      short loc_14001174E
0x140011736  mov     rcx, [rcx+18h]
0x14001173a  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140011741  mov     edx, 98h
0x140011746  mov     r9, rsi
0x140011749  call    WPP_SF_q
0x14001174e  mov     edi, 0C000021Bh
0x140011753  jmp     loc_140011885
0x140011758  cmp     qword ptr [rsi+28h], 0
0x14001175d  jz      short loc_140011774
0x14001175f  mov     r9, r13
0x140011762  mov     r8d, ebp
0x140011765  mov     rdx, rsi
0x140011768  call    SenderProcessNakPacket
0x14001176d  mov     edi, eax
0x14001176f  jmp     loc_140011885
0x140011774  xor     edi, edi
0x140011776  lea     ecx, [rdi+1]
0x140011779  cmp     [r9], ecx
0x14001177c  jnz     loc_140011885
0x140011782  cmp     word ptr [r9+4], 0Eh
0x140011788  jnz     loc_140011885
0x14001178e  cmp     word ptr [r9+6], 2
0x140011794  jnz     loc_140011885
0x14001179a  mov     r15d, [r9+0Ah]
0x14001179e  bswap   r15d
0x1400117a1  test    r15d, r15d
0x1400117a4  jz      loc_140011885
0x1400117aa  lea     rcx, SpinLock; SpinLock
0x1400117b1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400117b8  nop     dword ptr [rax+rax+00h]
0x1400117bd  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h
0x1400117c4  mov     rdx, rcx
0x1400117c7  mov     rdx, [rdx]
0x1400117ca  cmp     rdx, rcx
0x1400117cd  jz      short loc_1400117F4
0x1400117cf  lea     r8, [rdx+10h]
0x1400117d3  mov     rcx, r8
0x1400117d6  mov     rcx, [rcx]
0x1400117d9  cmp     rcx, r8
0x1400117dc  jz      short loc_1400117EB
0x1400117de  cmp     [rcx+10h], r15d
0x1400117e2  jnz     short loc_1400117D6
0x1400117e4  mov     dl, al
0x1400117e6  jmp     loc_140011872
0x1400117eb  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h
0x1400117f2  jmp     short loc_1400117C7
0x1400117f4  mov     dl, al; NewIrql
0x1400117f6  lea     rcx, SpinLock; SpinLock
0x1400117fd  call    cs:__imp_KeReleaseSpinLock
0x140011804  nop     dword ptr [rax+rax+00h]
0x140011809  lea     rcx, SpinLock; SpinLock
0x140011810  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011817  nop     dword ptr [rax+rax+00h]
0x14001181c  lea     r11, WPP_MAIN_CB.DeviceQueue.20h
0x140011823  mov     r10b, al
0x140011826  mov     r8, r11
0x140011829  mov     r8, [r8]
0x14001182c  cmp     r8, r11
0x14001182f  jz      short loc_14001186F
0x140011831  lea     r9, [r8+10h]
0x140011835  mov     rdx, r9
0x140011838  mov     rdx, [rdx]
0x14001183b  cmp     rdx, r9
0x14001183e  jz      short loc_140011829
0x140011840  mov     ecx, [rdx+14h]
0x140011843  mov     eax, [rdx+10h]
0x140011846  and     eax, ecx
0x140011848  and     ecx, r15d
0x14001184b  cmp     eax, ecx
0x14001184d  jnz     short loc_140011838
0x14001184f  mov     dl, r10b; NewIrql
0x140011852  lea     rcx, SpinLock; SpinLock
0x140011859  call    cs:__imp_KeReleaseSpinLock
0x140011860  nop     dword ptr [rax+rax+00h]
0x140011865  mov     byte ptr [rsp+88h+var_68], r14b
0x14001186a  jmp     loc_140011710
0x14001186f  mov     dl, r10b; NewIrql
0x140011872  lea     rcx, SpinLock; SpinLock
0x140011879  call    cs:__imp_KeReleaseSpinLock
0x140011880  nop     dword ptr [rax+rax+00h]
0x140011885  mov     rcx, cs:WPP_GLOBAL_Control
0x14001188c  cmp     rcx, rbx
0x14001188f  jz      loc_14001161B
0x140011895  mov     eax, [rcx+2Ch]
0x140011898  test    al, 10h
0x14001189a  jz      loc_14001161B
0x1400118a0  mov     r9d, r14d
0x1400118a3  mov     edx, 99h
0x1400118a8  jmp     loc_1400115CC
0x1400118ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118b4  lea     rbx, WPP_GLOBAL_Control
0x1400118bb  cmp     rcx, rbx
0x1400118be  jz      short loc_1400118E4
0x1400118c0  mov     eax, [rcx+2Ch]
0x1400118c3  test    al, 2
0x1400118c5  jz      short loc_1400118E4
0x1400118c7  mov     edx, 97h
0x1400118cc  mov     rcx, [rcx+18h]
0x1400118d0  mov     r9d, ebp
0x1400118d3  mov     dword ptr [rsp+88h+var_68], r8d
0x1400118d8  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x1400118df  call    WPP_SF_Dd
0x1400118e4  mov     eax, 0C000021Bh
0x1400118e9  add     rsp, 48h
0x1400118ed  pop     r15
0x1400118ef  pop     r14
0x1400118f1  pop     r13
0x1400118f3  pop     r12
0x1400118f5  pop     rdi
0x1400118f6  pop     rsi
0x1400118f7  pop     rbp
0x1400118f8  pop     rbx
0x1400118f9  retn
```

# InetInspectReceiveDatagram

- ea: `0x140096360`
- end: `0x14009693e`
- name: `InetInspectReceiveDatagram`
- size: `1502`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401309d0`
- `0x140131150`

## callees

- `0x140094c40`
- `0x140096360`
- `0x140096950`
- `0x1400974c0`
- `0x140099b68`
- `0x1400d2f60`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400963a2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140096595`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140096840`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400963a2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140096595`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140096840`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400963f5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400965d9`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14009687f`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400963f5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400965d9`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14009687f`
- `NETIO!WfpNblInfoGet` at `0x14009654f`
- `NETIO!WfpNblInfoGet` at `0x14009654f`
- `NETIO!NetioDereferenceNetBufferList` at `0x140096643`
- `NETIO!NetioDereferenceNetBufferList` at `0x140096643`
- `NETIO!KfdIsV6InTransportFastEmpty` at `0x140096904`
- `NETIO!KfdIsV6InTransportFastEmpty` at `0x140096904`
- `NETIO!KfdIsV4InTransportFastEmpty` at `0x140096922`
- `NETIO!KfdIsV4InTransportFastEmpty` at `0x140096922`

## pseudocode

```c
__int64 __fastcall InetInspectReceiveDatagram(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        int a4,
        __int16 a5,
        __int16 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10,
        int a11)
{
  unsigned int v14; // esi
  int *v15; // r14
  int v16; // ecx
  __int64 DpcTimeCount; // rcx
  int *v18; // rax
  __int64 v19; // rcx
  char v20; // dl
  int v21; // r10d
  char v22; // di
  __int64 v23; // rax
  __int64 v24; // rdx
  _DWORD *v25; // rbx
  ULONG v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v30; // rcx
  int v31; // ecx
  _DWORD *v32; // rbx
  int v33; // eax
  int v34; // edi
  struct _KDPC_WATCHDOG_INFORMATION WatchdogInformation; // [rsp+A8h] [rbp-70h] BYREF

  v14 = 1;
  v15 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  v16 = *v15;
  if ( *v15 == 1 )
  {
    memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
    KeQueryDpcWatchdogInformation(&WatchdogInformation);
    DpcTimeCount = WatchdogInformation.DpcTimeCount;
    v18 = v15 + 8;
LABEL_3:
    *((_QWORD *)v18 + 2) = DpcTimeCount;
    goto LABEL_4;
  }
  if ( !v16 )
  {
    *v15 = 3;
    v18 = v15 + 14;
    *(_OWORD *)(v15 + 14) = 0;
    *(_OWORD *)(v15 + 18) = 0;
    *(_OWORD *)(v15 + 22) = 0;
    *(_OWORD *)(v15 + 2) = 0;
    *(_OWORD *)(v15 + 6) = 0;
    *(_OWORD *)(v15 + 10) = 0;
    v15[26] = 1;
    DpcTimeCount = MEMORY[0xFFFFF78000000008];
    goto LABEL_3;
  }
  v31 = v16 - 2;
  if ( !v31 )
  {
    DpcTimeCount = MEMORY[0xFFFFF78000000008];
    v18 = v15 + 4;
    goto LABEL_3;
  }
  if ( v31 == 1 )
  {
    ++v15[26];
    v18 = v15 + 14;
    DpcTimeCount = MEMORY[0xFFFFF78000000008];
    goto LABEL_3;
  }
LABEL_4:
  if ( a4 != 6 )
  {
    if ( a4 == 17
      && WfpAleFastUdpInspection(
           (KSPIN_LOCK *)a2,
           a3,
           *(_QWORD *)(a8 + 32),
           *(_QWORD *)(a8 + 24),
           a5,
           a6,
           0,
           0,
           *(_QWORD *)(a8 + 8),
           *(_BYTE *)(a8 + 17)) )
    {
      goto LABEL_12;
    }
    goto LABEL_11;
  }
  if ( a2 && (*(_DWORD *)(a2 + 48) & 0x10) != 0 )
    goto LABEL_11;
  if ( a3 == 2 )
  {
    if ( (unsigned __int8)KfdIsV4InTransportFastEmpty() )
    {
      v34 = 0;
      goto LABEL_47;
    }
LABEL_11:
    v14 = WfpProcessInTransportStackIndication(
            a4,
            a3,
            a5,
            a6,
            *(_QWORD *)(a8 + 32),
            *(_DWORD **)(a8 + 24),
            *(_QWORD *)(a8 + 56),
            *(_DWORD *)(a8 + 64),
            *(_BYTE *)(a8 + 16) & 1,
            *(_DWORD *)(a8 + 48),
            a11,
            a10,
            a8,
            0,
            *(_QWORD *)(a8 + 8),
            0,
            (PKSPIN_LOCK)a2,
            0);
LABEL_12:
    v19 = *(_QWORD *)(a8 + 8);
    v20 = *(_BYTE *)(a8 + 17) | 1;
    v21 = *(_DWORD *)(v19 + 136);
    if ( (v21 & 0x2000000) == 0 )
      v20 = *(_BYTE *)(a8 + 17);
    v22 = v20 | 2;
    if ( (v21 & 0x100000) == 0 )
      v22 = v20;
    v23 = WfpNblInfoGet(v19);
    if ( v23 && (*(_DWORD *)(v23 + 4) & 1) != 0 )
      v22 |= 4u;
    *(_BYTE *)(a8 + 17) = v22;
LABEL_20:
    if ( v14 == 2 )
    {
      v30 = *(_QWORD *)(a8 + 8);
      LOBYTE(v24) = 1;
      *(_QWORD *)(a8 + 80) = 0;
      NetioDereferenceNetBufferList(v30, v24);
      *(_QWORD *)(a8 + 8) = 0;
    }
    else if ( v14 )
    {
      if ( v14 == 3 )
        *(_DWORD *)(*(_QWORD *)(a8 + 8) + 140LL) = -1073741790;
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)(a8 + 8) + 140LL) = -1071513340;
    }
    v25 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    switch ( *v25 )
    {
      case 1:
        memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
        KeQueryDpcWatchdogInformation(&WatchdogInformation);
        v26 = WatchdogInformation.DpcTimeCount;
        v27 = 14;
        v28 = 12;
        break;
      case 2:
        v27 = 10;
        v28 = 8;
        v26 = MEMORY[0xFFFFF78000000008];
        break;
      case 3:
        --v25[26];
        v26 = MEMORY[0xFFFFF78000000008];
        if ( !v25[26] )
          *v25 = 0;
        v27 = 20;
        v28 = 18;
        break;
      default:
        goto LABEL_27;
    }
    v25[v27] += v26 - v25[v28];
LABEL_27:
    if ( dword_1402201D4 && (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
    {
      *(_QWORD *)&WatchdogInformation.DpcWatchdogLimit = 0;
      *(_QWORD *)&WatchdogInformation.DpcTimeLimit = a1;
      McTemplateK0ppqqq_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        INET_INSPECT,
        &WatchdogInformation,
        a1,
        a2,
        5,
        v14,
        0);
    }
    return v14;
  }
  if ( a3 != 23 || !(unsigned __int8)KfdIsV6InTransportFastEmpty() )
    goto LABEL_11;
  v34 = 41;
LABEL_47:
  if ( a8 || !a2 || !(unsigned __int8)WfpAleCanPermitTcpDatagramGroup((PKSPIN_LOCK)a2) )
  {
    v14 = ProcessAleForTcpFastPath(
            a2,
            v34,
            a3,
            *(_QWORD *)(a8 + 32),
            *(_QWORD *)(a8 + 24),
            a5,
            a6,
            0,
            1,
            *(_DWORD *)(a8 + 48) - a10,
            a10,
            *(_QWORD *)(a8 + 56),
            *(_DWORD *)(a8 + 64),
            0,
            *(_QWORD *)(a8 + 8),
            0,
            0,
            *(_BYTE *)(a8 + 16) & 1,
            0);
    goto LABEL_20;
  }
  MEMORY[0] = 1;
  v32 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  switch ( *v32 )
  {
    case 1:
      memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
      KeQueryDpcWatchdogInformation(&WatchdogInformation);
      v32[14] += WatchdogInformation.DpcTimeCount - v32[12];
      break;
    case 2:
      v32[10] += MEMORY[0xFFFFF78000000008] - v32[8];
      break;
    case 3:
      --v32[26];
      v33 = MEMORY[0xFFFFF78000000008];
      if ( !v32[26] )
        *v32 = 0;
      v32[20] += v33 - v32[18];
      break;
  }
  return v14;
}

```

## disassembly

```asm
0x140096360  push    rbx
0x140096362  push    rbp
0x140096363  push    rsi
0x140096364  push    rdi
0x140096365  push    r12
0x140096367  push    r13
0x140096369  push    r14
0x14009636b  push    r15
0x14009636d  sub     rsp, 0D8h
0x140096374  mov     rax, cs:__security_cookie
0x14009637b  xor     rax, rsp
0x14009637e  mov     [rsp+118h+var_58], rax
0x140096386  mov     rbx, [rsp+118h+arg_38]
0x14009638e  mov     edi, r9d
0x140096391  mov     [rsp+118h+var_78], rcx
0x140096399  movzx   r12d, r8w
0x14009639d  xor     ecx, ecx; ProcNumber
0x14009639f  mov     r13, rdx
0x1400963a2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400963a9  nop     dword ptr [rax+rax+00h]
0x1400963ae  mov     esi, 1
0x1400963b3  mov     rdx, 0FFFFF78000000008h
0x1400963bd  lea     ecx, [rax+rax*8]
0x1400963c0  mov     rax, cs:gWfpPerProContext
0x1400963c7  shl     ecx, 3
0x1400963ca  mov     r14, [rcx+rax]
0x1400963ce  mov     ecx, [r14]
0x1400963d1  cmp     ecx, esi
0x1400963d3  jnz     loc_14009668E
0x1400963d9  xorps   xmm0, xmm0
0x1400963dc  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x1400963e4  xor     eax, eax
0x1400963e6  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x1400963ee  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x1400963f5  call    cs:__imp_KeQueryDpcWatchdogInformation
0x1400963fc  nop     dword ptr [rax+rax+00h]
0x140096401  mov     ecx, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x140096408  lea     rax, [r14+20h]
0x14009640c  mov     [rax+10h], rcx
0x140096410  movzx   ebp, [rsp+118h+arg_28]
0x140096418  xor     r15d, r15d
0x14009641b  movzx   r14d, [rsp+118h+arg_20]
0x140096424  cmp     edi, 6
0x140096427  jz      short loc_140096471
0x140096429  cmp     edi, 11h
0x14009642c  jnz     short loc_140096490
0x14009642e  movzx   eax, byte ptr [rbx+11h]
0x140096432  movzx   edx, r12w
0x140096436  mov     r9, [rbx+18h]
0x14009643a  mov     rcx, r13; SpinLock
0x14009643d  mov     r8, [rbx+20h]
0x140096441  mov     [rsp+118h+var_D0], al; char
0x140096445  mov     rax, [rbx+8]
0x140096449  mov     qword ptr [rsp+118h+var_D8], rax; __int64
0x14009644e  mov     [rsp+118h+var_E0], r15b; char
0x140096453  mov     [rsp+118h+var_E8], r15b; char
0x140096458  mov     [rsp+118h+var_F0], bp; __int16
0x14009645d  mov     [rsp+118h+var_F8], r14w; __int16
0x140096463  call    WfpAleFastUdpInspection
0x140096468  test    al, al
0x14009646a  jz      short loc_140096490
0x14009646c  jmp     loc_140096517
0x140096471  test    r13, r13
0x140096474  jnz     loc_14009672B
0x14009647a  cmp     r12w, 2
0x14009647f  jz      loc_140096922
0x140096485  cmp     r12w, 17h
0x14009648a  jz      loc_140096904
0x140096490  mov     rax, [rbx+8]
0x140096494  movzx   r9d, bp; int
0x140096498  movzx   edx, byte ptr [rbx+10h]
0x14009649c  movzx   r8d, r14w; int
0x1400964a0  mov     [rsp+118h+var_90], r15; __int64
0x1400964a8  and     dl, sil
0x1400964ab  mov     [rsp+118h+var_98], r13; PKSPIN_LOCK
0x1400964b3  mov     ecx, edi; int
0x1400964b5  mov     [rsp+118h+var_A0], r15; __int64
0x1400964ba  mov     [rsp+118h+var_A8], rax; __int64
0x1400964bf  mov     eax, [rsp+118h+arg_48]
0x1400964c6  mov     qword ptr [rsp+118h+var_B0], r15; char
0x1400964cb  mov     [rsp+118h+var_B8], rbx; __int64
0x1400964d0  mov     [rsp+118h+var_C0], eax; int
0x1400964d4  mov     eax, [rsp+118h+arg_50]
0x1400964db  mov     [rsp+118h+var_C8], eax; int
0x1400964df  mov     eax, [rbx+30h]
0x1400964e2  mov     dword ptr [rsp+118h+var_D0], eax; int
0x1400964e6  mov     eax, [rbx+40h]
0x1400964e9  mov     [rsp+118h+var_D8], dl; char
0x1400964ed  movzx   edx, r12w; int
0x1400964f1  mov     dword ptr [rsp+118h+var_E0], eax; int
0x1400964f5  mov     rax, [rbx+38h]
0x1400964f9  mov     qword ptr [rsp+118h+var_E8], rax; __int64
0x1400964fe  mov     rax, [rbx+18h]
0x140096502  mov     qword ptr [rsp+118h+var_F0], rax; __int64
0x140096507  mov     rax, [rbx+20h]
0x14009650b  mov     qword ptr [rsp+118h+var_F8], rax; __int64
0x140096510  call    WfpProcessInTransportStackIndication
0x140096515  mov     esi, eax
0x140096517  movzx   r9d, byte ptr [rbx+11h]
0x14009651c  mov     rcx, [rbx+8]
0x140096520  movzx   eax, r9b
0x140096524  or      al, 1
0x140096526  movzx   edx, al
0x140096529  mov     r10d, [rcx+88h]
0x140096530  bt      r10d, 19h
0x140096535  cmovnb  edx, r9d
0x140096539  movzx   r8d, dl
0x14009653d  movzx   eax, r8b
0x140096541  or      al, 2
0x140096543  bt      r10d, 14h
0x140096548  movzx   edi, al
0x14009654b  cmovnb  edi, r8d
0x14009654f  call    cs:__imp_WfpNblInfoGet
0x140096556  nop     dword ptr [rax+rax+00h]
0x14009655b  test    rax, rax
0x14009655e  jz      short loc_14009656B
0x140096560  mov     eax, [rax+4]
0x140096563  test    al, 1
0x140096565  jz      short loc_14009656B
0x140096567  or      dil, 4
0x14009656b  mov     [rbx+11h], dil
0x14009656f  cmp     esi, 2
0x140096572  jz      loc_140096639
0x140096578  test    esi, esi
0x14009657a  jz      loc_140096718
0x140096580  cmp     esi, 3
0x140096583  jnz     short loc_140096593
0x140096585  mov     rax, [rbx+8]
0x140096589  mov     dword ptr [rax+8Ch], 0C0000022h
0x140096593  xor     ecx, ecx; ProcNumber
0x140096595  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009659c  nop     dword ptr [rax+rax+00h]
0x1400965a1  mov     rbx, cs:gWfpPerProContext
0x1400965a8  lea     ecx, [rax+rax*8]
0x1400965ab  shl     ecx, 3
0x1400965ae  mov     rbx, [rcx+rbx]
0x1400965b2  mov     ecx, [rbx]
0x1400965b4  cmp     ecx, 1
0x1400965b7  jnz     loc_140096658
0x1400965bd  xorps   xmm0, xmm0
0x1400965c0  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x1400965c8  xor     eax, eax
0x1400965ca  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x1400965d2  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x1400965d9  call    cs:__imp_KeQueryDpcWatchdogInformation
0x1400965e0  nop     dword ptr [rax+rax+00h]
0x1400965e5  mov     eax, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x1400965ec  mov     ecx, 38h ; '8'
0x1400965f1  mov     edx, 30h ; '0'
0x1400965f6  sub     eax, [rbx+rdx]
0x1400965f9  add     [rbx+rcx], eax
0x1400965fc  cmp     cs:dword_1402201D4, 0
0x140096603  jz      short loc_140096612
0x140096605  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x14009660c  jnz     loc_1400966CA
0x140096612  mov     eax, esi
0x140096614  mov     rcx, [rsp+118h+var_58]
0x14009661c  xor     rcx, rsp; StackCookie
0x14009661f  call    __security_check_cookie
0x140096624  add     rsp, 0D8h
0x14009662b  pop     r15
0x14009662d  pop     r14
0x14009662f  pop     r13
0x140096631  pop     r12
0x140096633  pop     rdi
0x140096634  pop     rsi
0x140096635  pop     rbp
0x140096636  pop     rbx
0x140096637  retn
0x140096639  mov     rcx, [rbx+8]
0x14009663d  mov     dl, 1
0x14009663f  mov     [rbx+50h], r15
0x140096643  call    cs:__imp_NetioDereferenceNetBufferList
0x14009664a  nop     dword ptr [rax+rax+00h]
0x14009664f  mov     [rbx+8], r15
0x140096653  jmp     loc_140096593
0x140096658  sub     ecx, 2
0x14009665b  jz      loc_140096765
0x140096661  cmp     ecx, 1
0x140096664  jnz     short loc_1400965FC
0x140096666  dec     dword ptr [rbx+68h]
0x140096669  mov     rax, 0FFFFF78000000008h
0x140096673  mov     rax, [rax]
0x140096676  cmp     dword ptr [rbx+68h], 0
0x14009667a  jnz     short loc_14009667F
0x14009667c  mov     [rbx], r15d
0x14009667f  mov     ecx, 50h ; 'P'
0x140096684  mov     edx, 48h ; 'H'
0x140096689  jmp     loc_1400965F6
0x14009668e  test    ecx, ecx
0x140096690  jnz     loc_14009673C
0x140096696  mov     dword ptr [r14], 3
0x14009669d  lea     rax, [r14+38h]
0x1400966a1  xorps   xmm0, xmm0
0x1400966a4  movups  xmmword ptr [rax], xmm0
0x1400966a7  movups  xmmword ptr [rax+10h], xmm0
0x1400966ab  movups  xmmword ptr [rax+20h], xmm0
0x1400966af  movups  xmmword ptr [r14+8], xmm0
0x1400966b4  movups  xmmword ptr [r14+18h], xmm0
0x1400966b9  movups  xmmword ptr [r14+28h], xmm0
0x1400966be  mov     [r14+68h], esi
0x1400966c2  mov     rcx, [rdx]
0x1400966c5  jmp     loc_14009640C
0x1400966ca  mov     r9, [rsp+118h+var_78]
0x1400966d2  lea     r8, [rsp+118h+WatchdogInformation]
0x1400966da  mov     dword ptr [rsp+118h+var_E0], r15d
0x1400966df  lea     rdx, INET_INSPECT
0x1400966e6  mov     dword ptr [rsp+118h+var_E8], esi
0x1400966ea  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400966f1  mov     dword ptr [rsp+118h+var_F0], 5
0x1400966f9  mov     qword ptr [rsp+118h+var_F8], r13
0x1400966fe  mov     qword ptr [rsp+118h+WatchdogInformation.DpcWatchdogLimit], r15
0x140096706  mov     qword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], r9
0x14009670e  call    McTemplateK0ppqqq_EtwWriteTransfer
0x140096713  jmp     loc_140096612
0x140096718  mov     rax, [rbx+8]
0x14009671c  mov     dword ptr [rax+8Ch], 0C0220104h
0x140096726  jmp     loc_140096593
0x14009672b  mov     eax, [r13+30h]
0x14009672f  test    al, 10h
0x140096731  jnz     loc_140096490
0x140096737  jmp     loc_14009647A
0x14009673c  sub     ecx, 2
0x14009673f  jnz     short loc_14009674D
0x140096741  mov     rcx, [rdx]
0x140096744  lea     rax, [r14+10h]
0x140096748  jmp     loc_14009640C
0x14009674d  cmp     ecx, esi
0x14009674f  jnz     loc_140096410
0x140096755  inc     dword ptr [r14+68h]
0x140096759  lea     rax, [r14+38h]
0x14009675d  mov     rcx, [rdx]
0x140096760  jmp     loc_14009640C
0x140096765  mov     rax, 0FFFFF78000000008h
0x14009676f  mov     ecx, 28h ; '('
0x140096774  mov     edx, 20h ; ' '
0x140096779  mov     rax, [rax]
0x14009677c  jmp     loc_1400965F6
0x140096781  test    rbx, rbx
0x140096784  jz      loc_14009681F
0x14009678a  movzx   eax, byte ptr [rbx+10h]
0x14009678e  movzx   r8d, r12w
0x140096792  mov     r9d, [rbx+30h]
0x140096796  and     al, sil
0x140096799  mov     ecx, [rsp+118h+arg_48]
0x1400967a0  mov     edx, edi
0x1400967a2  mov     [rsp+118h+var_88], r15
0x1400967aa  sub     r9d, ecx
0x1400967ad  mov     byte ptr [rsp+118h+var_90], al
0x1400967b4  mov     rax, [rbx+8]
0x1400967b8  mov     dword ptr [rsp+118h+var_98], r15d
0x1400967c0  mov     [rsp+118h+var_A0], r15
0x1400967c5  mov     [rsp+118h+var_A8], rax
0x1400967ca  mov     eax, [rbx+40h]
0x1400967cd  mov     qword ptr [rsp+118h+var_B0], r15
0x1400967d2  mov     dword ptr [rsp+118h+var_B8], eax
0x1400967d6  mov     rax, [rbx+38h]
0x1400967da  mov     qword ptr [rsp+118h+var_C0], rax
0x1400967df  movzx   eax, bp
0x1400967e2  mov     [rsp+118h+var_C8], ecx
0x1400967e6  mov     rcx, r13
0x1400967e9  mov     dword ptr [rsp+118h+var_D0], r9d
0x1400967ee  mov     r9, [rbx+20h]
0x1400967f2  mov     [rsp+118h+var_D8], sil
0x1400967f7  mov     [rsp+118h+var_E0], 0
0x1400967fc  mov     word ptr [rsp+118h+var_E8], ax
0x140096801  movzx   eax, r14w
0x140096805  mov     [rsp+118h+var_F0], ax
0x14009680a  mov     rax, [rbx+18h]
0x14009680e  mov     qword ptr [rsp+118h+var_F8], rax
0x140096813  call    ProcessAleForTcpFastPath
0x140096818  mov     esi, eax
0x14009681a  jmp     loc_14009656F
0x14009681f  test    r13, r13
0x140096822  jz      loc_14009678A
0x140096828  xor     r8d, r8d
0x14009682b  mov     rcx, r13; SpinLock
0x14009682e  call    WfpAleCanPermitTcpDatagramGroup
0x140096833  test    al, al
0x140096835  jz      loc_14009678A
0x14009683b  xor     ecx, ecx; ProcNumber
0x14009683d  mov     [r15], sil
0x140096840  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140096847  nop     dword ptr [rax+rax+00h]
0x14009684c  lea     ecx, [rax+rax*8]
0x14009684f  mov     rax, cs:gWfpPerProContext
0x140096856  shl     ecx, 3
0x140096859  mov     rbx, [rcx+rax]
0x14009685d  mov     ecx, [rbx]
0x14009685f  cmp     ecx, esi
0x140096861  jnz     short loc_1400968A7
0x140096863  xorps   xmm0, xmm0
0x140096866  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x14009686e  xor     eax, eax
0x140096870  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x140096878  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x14009687f  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140096886  nop     dword ptr [rax+rax+00h]
0x14009688b  mov     eax, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x140096892  mov     edx, 30h ; '0'
  ... truncated ...
```

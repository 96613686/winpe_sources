# InetInspectReceiveDatagram

- ea: `0x140097210`
- end: `0x1400977ee`
- name: `InetInspectReceiveDatagram`
- size: `1502`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140130b10`
- `0x140131290`

## callees

- `0x140095af0`
- `0x140097210`
- `0x140097800`
- `0x140098370`
- `0x14009aa18`
- `0x1400d2d40`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140097252`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140097445`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400976f0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140097252`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140097445`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400976f0`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400972a5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140097489`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14009772f`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400972a5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140097489`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14009772f`
- `NETIO!WfpNblInfoGet` at `0x1400973ff`
- `NETIO!WfpNblInfoGet` at `0x1400973ff`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400974f3`
- `NETIO!NetioDereferenceNetBufferList` at `0x1400974f3`
- `NETIO!KfdIsV6InTransportFastEmpty` at `0x1400977b4`
- `NETIO!KfdIsV6InTransportFastEmpty` at `0x1400977b4`
- `NETIO!KfdIsV4InTransportFastEmpty` at `0x1400977d2`
- `NETIO!KfdIsV4InTransportFastEmpty` at `0x1400977d2`

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
        &INET_INSPECT,
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
0x140097210  push    rbx
0x140097212  push    rbp
0x140097213  push    rsi
0x140097214  push    rdi
0x140097215  push    r12
0x140097217  push    r13
0x140097219  push    r14
0x14009721b  push    r15
0x14009721d  sub     rsp, 0D8h
0x140097224  mov     rax, cs:__security_cookie
0x14009722b  xor     rax, rsp
0x14009722e  mov     [rsp+118h+var_58], rax
0x140097236  mov     rbx, [rsp+118h+arg_38]
0x14009723e  mov     edi, r9d
0x140097241  mov     [rsp+118h+var_78], rcx
0x140097249  movzx   r12d, r8w
0x14009724d  xor     ecx, ecx; ProcNumber
0x14009724f  mov     r13, rdx
0x140097252  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140097259  nop     dword ptr [rax+rax+00h]
0x14009725e  mov     esi, 1
0x140097263  mov     rdx, 0FFFFF78000000008h
0x14009726d  lea     ecx, [rax+rax*8]
0x140097270  mov     rax, cs:gWfpPerProContext
0x140097277  shl     ecx, 3
0x14009727a  mov     r14, [rcx+rax]
0x14009727e  mov     ecx, [r14]
0x140097281  cmp     ecx, esi
0x140097283  jnz     loc_14009753E
0x140097289  xorps   xmm0, xmm0
0x14009728c  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x140097294  xor     eax, eax
0x140097296  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x14009729e  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x1400972a5  call    cs:__imp_KeQueryDpcWatchdogInformation
0x1400972ac  nop     dword ptr [rax+rax+00h]
0x1400972b1  mov     ecx, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x1400972b8  lea     rax, [r14+20h]
0x1400972bc  mov     [rax+10h], rcx
0x1400972c0  movzx   ebp, [rsp+118h+arg_28]
0x1400972c8  xor     r15d, r15d
0x1400972cb  movzx   r14d, [rsp+118h+arg_20]
0x1400972d4  cmp     edi, 6
0x1400972d7  jz      short loc_140097321
0x1400972d9  cmp     edi, 11h
0x1400972dc  jnz     short loc_140097340
0x1400972de  movzx   eax, byte ptr [rbx+11h]
0x1400972e2  movzx   edx, r12w
0x1400972e6  mov     r9, [rbx+18h]
0x1400972ea  mov     rcx, r13; SpinLock
0x1400972ed  mov     r8, [rbx+20h]
0x1400972f1  mov     [rsp+118h+var_D0], al; char
0x1400972f5  mov     rax, [rbx+8]
0x1400972f9  mov     qword ptr [rsp+118h+var_D8], rax; __int64
0x1400972fe  mov     [rsp+118h+var_E0], r15b; char
0x140097303  mov     [rsp+118h+var_E8], r15b; char
0x140097308  mov     [rsp+118h+var_F0], bp; __int16
0x14009730d  mov     [rsp+118h+var_F8], r14w; __int16
0x140097313  call    WfpAleFastUdpInspection
0x140097318  test    al, al
0x14009731a  jz      short loc_140097340
0x14009731c  jmp     loc_1400973C7
0x140097321  test    r13, r13
0x140097324  jnz     loc_1400975DB
0x14009732a  cmp     r12w, 2
0x14009732f  jz      loc_1400977D2
0x140097335  cmp     r12w, 17h
0x14009733a  jz      loc_1400977B4
0x140097340  mov     rax, [rbx+8]
0x140097344  movzx   r9d, bp; int
0x140097348  movzx   edx, byte ptr [rbx+10h]
0x14009734c  movzx   r8d, r14w; int
0x140097350  mov     [rsp+118h+var_90], r15; __int64
0x140097358  and     dl, sil
0x14009735b  mov     [rsp+118h+var_98], r13; PKSPIN_LOCK
0x140097363  mov     ecx, edi; int
0x140097365  mov     [rsp+118h+var_A0], r15; __int64
0x14009736a  mov     [rsp+118h+var_A8], rax; __int64
0x14009736f  mov     eax, [rsp+118h+arg_48]
0x140097376  mov     qword ptr [rsp+118h+var_B0], r15; char
0x14009737b  mov     [rsp+118h+var_B8], rbx; __int64
0x140097380  mov     [rsp+118h+var_C0], eax; int
0x140097384  mov     eax, [rsp+118h+arg_50]
0x14009738b  mov     [rsp+118h+var_C8], eax; int
0x14009738f  mov     eax, [rbx+30h]
0x140097392  mov     dword ptr [rsp+118h+var_D0], eax; int
0x140097396  mov     eax, [rbx+40h]
0x140097399  mov     [rsp+118h+var_D8], dl; char
0x14009739d  movzx   edx, r12w; int
0x1400973a1  mov     dword ptr [rsp+118h+var_E0], eax; int
0x1400973a5  mov     rax, [rbx+38h]
0x1400973a9  mov     qword ptr [rsp+118h+var_E8], rax; __int64
0x1400973ae  mov     rax, [rbx+18h]
0x1400973b2  mov     qword ptr [rsp+118h+var_F0], rax; __int64
0x1400973b7  mov     rax, [rbx+20h]
0x1400973bb  mov     qword ptr [rsp+118h+var_F8], rax; __int64
0x1400973c0  call    WfpProcessInTransportStackIndication
0x1400973c5  mov     esi, eax
0x1400973c7  movzx   r9d, byte ptr [rbx+11h]
0x1400973cc  mov     rcx, [rbx+8]
0x1400973d0  movzx   eax, r9b
0x1400973d4  or      al, 1
0x1400973d6  movzx   edx, al
0x1400973d9  mov     r10d, [rcx+88h]
0x1400973e0  bt      r10d, 19h
0x1400973e5  cmovnb  edx, r9d
0x1400973e9  movzx   r8d, dl
0x1400973ed  movzx   eax, r8b
0x1400973f1  or      al, 2
0x1400973f3  bt      r10d, 14h
0x1400973f8  movzx   edi, al
0x1400973fb  cmovnb  edi, r8d
0x1400973ff  call    cs:__imp_WfpNblInfoGet
0x140097406  nop     dword ptr [rax+rax+00h]
0x14009740b  test    rax, rax
0x14009740e  jz      short loc_14009741B
0x140097410  mov     eax, [rax+4]
0x140097413  test    al, 1
0x140097415  jz      short loc_14009741B
0x140097417  or      dil, 4
0x14009741b  mov     [rbx+11h], dil
0x14009741f  cmp     esi, 2
0x140097422  jz      loc_1400974E9
0x140097428  test    esi, esi
0x14009742a  jz      loc_1400975C8
0x140097430  cmp     esi, 3
0x140097433  jnz     short loc_140097443
0x140097435  mov     rax, [rbx+8]
0x140097439  mov     dword ptr [rax+8Ch], 0C0000022h
0x140097443  xor     ecx, ecx; ProcNumber
0x140097445  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009744c  nop     dword ptr [rax+rax+00h]
0x140097451  mov     rbx, cs:gWfpPerProContext
0x140097458  lea     ecx, [rax+rax*8]
0x14009745b  shl     ecx, 3
0x14009745e  mov     rbx, [rcx+rbx]
0x140097462  mov     ecx, [rbx]
0x140097464  cmp     ecx, 1
0x140097467  jnz     loc_140097508
0x14009746d  xorps   xmm0, xmm0
0x140097470  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x140097478  xor     eax, eax
0x14009747a  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x140097482  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x140097489  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140097490  nop     dword ptr [rax+rax+00h]
0x140097495  mov     eax, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x14009749c  mov     ecx, 38h ; '8'
0x1400974a1  mov     edx, 30h ; '0'
0x1400974a6  sub     eax, [rbx+rdx]
0x1400974a9  add     [rbx+rcx], eax
0x1400974ac  cmp     cs:dword_1402201D4, 0
0x1400974b3  jz      short loc_1400974C2
0x1400974b5  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x1400974bc  jnz     loc_14009757A
0x1400974c2  mov     eax, esi
0x1400974c4  mov     rcx, [rsp+118h+var_58]
0x1400974cc  xor     rcx, rsp; StackCookie
0x1400974cf  call    __security_check_cookie
0x1400974d4  add     rsp, 0D8h
0x1400974db  pop     r15
0x1400974dd  pop     r14
0x1400974df  pop     r13
0x1400974e1  pop     r12
0x1400974e3  pop     rdi
0x1400974e4  pop     rsi
0x1400974e5  pop     rbp
0x1400974e6  pop     rbx
0x1400974e7  retn
0x1400974e9  mov     rcx, [rbx+8]
0x1400974ed  mov     dl, 1
0x1400974ef  mov     [rbx+50h], r15
0x1400974f3  call    cs:__imp_NetioDereferenceNetBufferList
0x1400974fa  nop     dword ptr [rax+rax+00h]
0x1400974ff  mov     [rbx+8], r15
0x140097503  jmp     loc_140097443
0x140097508  sub     ecx, 2
0x14009750b  jz      loc_140097615
0x140097511  cmp     ecx, 1
0x140097514  jnz     short loc_1400974AC
0x140097516  dec     dword ptr [rbx+68h]
0x140097519  mov     rax, 0FFFFF78000000008h
0x140097523  mov     rax, [rax]
0x140097526  cmp     dword ptr [rbx+68h], 0
0x14009752a  jnz     short loc_14009752F
0x14009752c  mov     [rbx], r15d
0x14009752f  mov     ecx, 50h ; 'P'
0x140097534  mov     edx, 48h ; 'H'
0x140097539  jmp     loc_1400974A6
0x14009753e  test    ecx, ecx
0x140097540  jnz     loc_1400975EC
0x140097546  mov     dword ptr [r14], 3
0x14009754d  lea     rax, [r14+38h]
0x140097551  xorps   xmm0, xmm0
0x140097554  movups  xmmword ptr [rax], xmm0
0x140097557  movups  xmmword ptr [rax+10h], xmm0
0x14009755b  movups  xmmword ptr [rax+20h], xmm0
0x14009755f  movups  xmmword ptr [r14+8], xmm0
0x140097564  movups  xmmword ptr [r14+18h], xmm0
0x140097569  movups  xmmword ptr [r14+28h], xmm0
0x14009756e  mov     [r14+68h], esi
0x140097572  mov     rcx, [rdx]
0x140097575  jmp     loc_1400972BC
0x14009757a  mov     r9, [rsp+118h+var_78]
0x140097582  lea     r8, [rsp+118h+WatchdogInformation]
0x14009758a  mov     dword ptr [rsp+118h+var_E0], r15d
0x14009758f  lea     rdx, INET_INSPECT
0x140097596  mov     dword ptr [rsp+118h+var_E8], esi
0x14009759a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400975a1  mov     dword ptr [rsp+118h+var_F0], 5
0x1400975a9  mov     qword ptr [rsp+118h+var_F8], r13
0x1400975ae  mov     qword ptr [rsp+118h+WatchdogInformation.DpcWatchdogLimit], r15
0x1400975b6  mov     qword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], r9
0x1400975be  call    McTemplateK0ppqqq_EtwWriteTransfer
0x1400975c3  jmp     loc_1400974C2
0x1400975c8  mov     rax, [rbx+8]
0x1400975cc  mov     dword ptr [rax+8Ch], 0C0220104h
0x1400975d6  jmp     loc_140097443
0x1400975db  mov     eax, [r13+30h]
0x1400975df  test    al, 10h
0x1400975e1  jnz     loc_140097340
0x1400975e7  jmp     loc_14009732A
0x1400975ec  sub     ecx, 2
0x1400975ef  jnz     short loc_1400975FD
0x1400975f1  mov     rcx, [rdx]
0x1400975f4  lea     rax, [r14+10h]
0x1400975f8  jmp     loc_1400972BC
0x1400975fd  cmp     ecx, esi
0x1400975ff  jnz     loc_1400972C0
0x140097605  inc     dword ptr [r14+68h]
0x140097609  lea     rax, [r14+38h]
0x14009760d  mov     rcx, [rdx]
0x140097610  jmp     loc_1400972BC
0x140097615  mov     rax, 0FFFFF78000000008h
0x14009761f  mov     ecx, 28h ; '('
0x140097624  mov     edx, 20h ; ' '
0x140097629  mov     rax, [rax]
0x14009762c  jmp     loc_1400974A6
0x140097631  test    rbx, rbx
0x140097634  jz      loc_1400976CF
0x14009763a  movzx   eax, byte ptr [rbx+10h]
0x14009763e  movzx   r8d, r12w
0x140097642  mov     r9d, [rbx+30h]
0x140097646  and     al, sil
0x140097649  mov     ecx, [rsp+118h+arg_48]
0x140097650  mov     edx, edi
0x140097652  mov     [rsp+118h+var_88], r15
0x14009765a  sub     r9d, ecx
0x14009765d  mov     byte ptr [rsp+118h+var_90], al
0x140097664  mov     rax, [rbx+8]
0x140097668  mov     dword ptr [rsp+118h+var_98], r15d
0x140097670  mov     [rsp+118h+var_A0], r15
0x140097675  mov     [rsp+118h+var_A8], rax
0x14009767a  mov     eax, [rbx+40h]
0x14009767d  mov     qword ptr [rsp+118h+var_B0], r15
0x140097682  mov     dword ptr [rsp+118h+var_B8], eax
0x140097686  mov     rax, [rbx+38h]
0x14009768a  mov     qword ptr [rsp+118h+var_C0], rax
0x14009768f  movzx   eax, bp
0x140097692  mov     [rsp+118h+var_C8], ecx
0x140097696  mov     rcx, r13
0x140097699  mov     dword ptr [rsp+118h+var_D0], r9d
0x14009769e  mov     r9, [rbx+20h]
0x1400976a2  mov     [rsp+118h+var_D8], sil
0x1400976a7  mov     [rsp+118h+var_E0], 0
0x1400976ac  mov     word ptr [rsp+118h+var_E8], ax
0x1400976b1  movzx   eax, r14w
0x1400976b5  mov     [rsp+118h+var_F0], ax
0x1400976ba  mov     rax, [rbx+18h]
0x1400976be  mov     qword ptr [rsp+118h+var_F8], rax
0x1400976c3  call    ProcessAleForTcpFastPath
0x1400976c8  mov     esi, eax
0x1400976ca  jmp     loc_14009741F
0x1400976cf  test    r13, r13
0x1400976d2  jz      loc_14009763A
0x1400976d8  xor     r8d, r8d
0x1400976db  mov     rcx, r13; SpinLock
0x1400976de  call    WfpAleCanPermitTcpDatagramGroup
0x1400976e3  test    al, al
0x1400976e5  jz      loc_14009763A
0x1400976eb  xor     ecx, ecx; ProcNumber
0x1400976ed  mov     [r15], sil
0x1400976f0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400976f7  nop     dword ptr [rax+rax+00h]
0x1400976fc  lea     ecx, [rax+rax*8]
0x1400976ff  mov     rax, cs:gWfpPerProContext
0x140097706  shl     ecx, 3
0x140097709  mov     rbx, [rcx+rax]
0x14009770d  mov     ecx, [rbx]
0x14009770f  cmp     ecx, esi
0x140097711  jnz     short loc_140097757
0x140097713  xorps   xmm0, xmm0
0x140097716  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x14009771e  xor     eax, eax
0x140097720  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x140097728  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x14009772f  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140097736  nop     dword ptr [rax+rax+00h]
0x14009773b  mov     eax, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x140097742  mov     edx, 30h ; '0'
  ... truncated ...
```

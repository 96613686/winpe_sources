# InetInspectReceiveDatagram

- ea: `0x14005d150`
- end: `0x14005d72e`
- name: `InetInspectReceiveDatagram`
- size: `1502`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14006ca10`
- `0x1400bbfa8`

## callees

- `0x14005d040`
- `0x14005d150`
- `0x14005d740`
- `0x14005e2b0`
- `0x140060000`
- `0x1400e02e0`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005d192`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005d385`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005d630`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005d192`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005d385`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005d630`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14005d1e5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14005d3c9`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14005d66f`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14005d1e5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14005d3c9`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14005d66f`
- `NETIO!WfpNblInfoGet` at `0x14005d33f`
- `NETIO!WfpNblInfoGet` at `0x14005d33f`
- `NETIO!NetioDereferenceNetBufferList` at `0x14005d433`
- `NETIO!NetioDereferenceNetBufferList` at `0x14005d433`
- `NETIO!KfdIsV6InTransportFastEmpty` at `0x14005d6f4`
- `NETIO!KfdIsV6InTransportFastEmpty` at `0x14005d6f4`
- `NETIO!KfdIsV4InTransportFastEmpty` at `0x14005d712`
- `NETIO!KfdIsV4InTransportFastEmpty` at `0x14005d712`

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
            *(_QWORD *)(a8 + 24),
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
    if ( dword_1402241D4 && (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
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
0x14005d150  push    rbx
0x14005d152  push    rbp
0x14005d153  push    rsi
0x14005d154  push    rdi
0x14005d155  push    r12
0x14005d157  push    r13
0x14005d159  push    r14
0x14005d15b  push    r15
0x14005d15d  sub     rsp, 0D8h
0x14005d164  mov     rax, cs:__security_cookie
0x14005d16b  xor     rax, rsp
0x14005d16e  mov     [rsp+118h+var_58], rax
0x14005d176  mov     rbx, [rsp+118h+arg_38]
0x14005d17e  mov     edi, r9d
0x14005d181  mov     [rsp+118h+var_78], rcx
0x14005d189  movzx   r12d, r8w
0x14005d18d  xor     ecx, ecx; ProcNumber
0x14005d18f  mov     r13, rdx
0x14005d192  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005d199  nop     dword ptr [rax+rax+00h]
0x14005d19e  mov     esi, 1
0x14005d1a3  mov     rdx, 0FFFFF78000000008h
0x14005d1ad  lea     ecx, [rax+rax*8]
0x14005d1b0  mov     rax, cs:gWfpPerProContext
0x14005d1b7  shl     ecx, 3
0x14005d1ba  mov     r14, [rcx+rax]
0x14005d1be  mov     ecx, [r14]
0x14005d1c1  cmp     ecx, esi
0x14005d1c3  jnz     loc_14005D47E
0x14005d1c9  xorps   xmm0, xmm0
0x14005d1cc  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x14005d1d4  xor     eax, eax
0x14005d1d6  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x14005d1de  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x14005d1e5  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14005d1ec  nop     dword ptr [rax+rax+00h]
0x14005d1f1  mov     ecx, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x14005d1f8  lea     rax, [r14+20h]
0x14005d1fc  mov     [rax+10h], rcx
0x14005d200  movzx   ebp, [rsp+118h+arg_28]
0x14005d208  xor     r15d, r15d
0x14005d20b  movzx   r14d, [rsp+118h+arg_20]
0x14005d214  cmp     edi, 6
0x14005d217  jz      short loc_14005D261
0x14005d219  cmp     edi, 11h
0x14005d21c  jnz     short loc_14005D280
0x14005d21e  movzx   eax, byte ptr [rbx+11h]
0x14005d222  movzx   edx, r12w
0x14005d226  mov     r9, [rbx+18h]
0x14005d22a  mov     rcx, r13; SpinLock
0x14005d22d  mov     r8, [rbx+20h]
0x14005d231  mov     [rsp+118h+var_D0], al; char
0x14005d235  mov     rax, [rbx+8]
0x14005d239  mov     [rsp+118h+var_D8], rax; __int64
0x14005d23e  mov     [rsp+118h+var_E0], r15b; char
0x14005d243  mov     [rsp+118h+var_E8], r15b; char
0x14005d248  mov     [rsp+118h+var_F0], bp; __int16
0x14005d24d  mov     [rsp+118h+var_F8], r14w; __int16
0x14005d253  call    WfpAleFastUdpInspection
0x14005d258  test    al, al
0x14005d25a  jz      short loc_14005D280
0x14005d25c  jmp     loc_14005D307
0x14005d261  test    r13, r13
0x14005d264  jnz     loc_14005D51B
0x14005d26a  cmp     r12w, 2
0x14005d26f  jz      loc_14005D712
0x14005d275  cmp     r12w, 17h
0x14005d27a  jz      loc_14005D6F4
0x14005d280  mov     rax, [rbx+8]
0x14005d284  movzx   r9d, bp
0x14005d288  movzx   edx, byte ptr [rbx+10h]
0x14005d28c  movzx   r8d, r14w
0x14005d290  mov     [rsp+118h+var_90], r15
0x14005d298  and     dl, sil
0x14005d29b  mov     [rsp+118h+var_98], r13
0x14005d2a3  mov     ecx, edi
0x14005d2a5  mov     [rsp+118h+var_A0], r15
0x14005d2aa  mov     [rsp+118h+var_A8], rax
0x14005d2af  mov     eax, [rsp+118h+arg_48]
0x14005d2b6  mov     [rsp+118h+var_B0], r15
0x14005d2bb  mov     [rsp+118h+var_B8], rbx
0x14005d2c0  mov     dword ptr [rsp+118h+var_C0], eax
0x14005d2c4  mov     eax, [rsp+118h+arg_50]
0x14005d2cb  mov     [rsp+118h+var_C8], eax
0x14005d2cf  mov     eax, [rbx+30h]
0x14005d2d2  mov     dword ptr [rsp+118h+var_D0], eax
0x14005d2d6  mov     eax, [rbx+40h]
0x14005d2d9  mov     byte ptr [rsp+118h+var_D8], dl
0x14005d2dd  movzx   edx, r12w
0x14005d2e1  mov     dword ptr [rsp+118h+var_E0], eax
0x14005d2e5  mov     rax, [rbx+38h]
0x14005d2e9  mov     qword ptr [rsp+118h+var_E8], rax
0x14005d2ee  mov     rax, [rbx+18h]
0x14005d2f2  mov     qword ptr [rsp+118h+var_F0], rax
0x14005d2f7  mov     rax, [rbx+20h]
0x14005d2fb  mov     qword ptr [rsp+118h+var_F8], rax
0x14005d300  call    WfpProcessInTransportStackIndication
0x14005d305  mov     esi, eax
0x14005d307  movzx   r9d, byte ptr [rbx+11h]
0x14005d30c  mov     rcx, [rbx+8]
0x14005d310  movzx   eax, r9b
0x14005d314  or      al, 1
0x14005d316  movzx   edx, al
0x14005d319  mov     r10d, [rcx+88h]
0x14005d320  bt      r10d, 19h
0x14005d325  cmovnb  edx, r9d
0x14005d329  movzx   r8d, dl
0x14005d32d  movzx   eax, r8b
0x14005d331  or      al, 2
0x14005d333  bt      r10d, 14h
0x14005d338  movzx   edi, al
0x14005d33b  cmovnb  edi, r8d
0x14005d33f  call    cs:__imp_WfpNblInfoGet
0x14005d346  nop     dword ptr [rax+rax+00h]
0x14005d34b  test    rax, rax
0x14005d34e  jz      short loc_14005D35B
0x14005d350  mov     eax, [rax+4]
0x14005d353  test    al, 1
0x14005d355  jz      short loc_14005D35B
0x14005d357  or      dil, 4
0x14005d35b  mov     [rbx+11h], dil
0x14005d35f  cmp     esi, 2
0x14005d362  jz      loc_14005D429
0x14005d368  test    esi, esi
0x14005d36a  jz      loc_14005D508
0x14005d370  cmp     esi, 3
0x14005d373  jnz     short loc_14005D383
0x14005d375  mov     rax, [rbx+8]
0x14005d379  mov     dword ptr [rax+8Ch], 0C0000022h
0x14005d383  xor     ecx, ecx; ProcNumber
0x14005d385  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005d38c  nop     dword ptr [rax+rax+00h]
0x14005d391  mov     rbx, cs:gWfpPerProContext
0x14005d398  lea     ecx, [rax+rax*8]
0x14005d39b  shl     ecx, 3
0x14005d39e  mov     rbx, [rcx+rbx]
0x14005d3a2  mov     ecx, [rbx]
0x14005d3a4  cmp     ecx, 1
0x14005d3a7  jnz     loc_14005D448
0x14005d3ad  xorps   xmm0, xmm0
0x14005d3b0  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x14005d3b8  xor     eax, eax
0x14005d3ba  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x14005d3c2  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x14005d3c9  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14005d3d0  nop     dword ptr [rax+rax+00h]
0x14005d3d5  mov     eax, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x14005d3dc  mov     ecx, 38h ; '8'
0x14005d3e1  mov     edx, 30h ; '0'
0x14005d3e6  sub     eax, [rbx+rdx]
0x14005d3e9  add     [rbx+rcx], eax
0x14005d3ec  cmp     cs:dword_1402241D4, 0
0x14005d3f3  jz      short loc_14005D402
0x14005d3f5  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+4, 8
0x14005d3fc  jnz     loc_14005D4BA
0x14005d402  mov     eax, esi
0x14005d404  mov     rcx, [rsp+118h+var_58]
0x14005d40c  xor     rcx, rsp; StackCookie
0x14005d40f  call    __security_check_cookie
0x14005d414  add     rsp, 0D8h
0x14005d41b  pop     r15
0x14005d41d  pop     r14
0x14005d41f  pop     r13
0x14005d421  pop     r12
0x14005d423  pop     rdi
0x14005d424  pop     rsi
0x14005d425  pop     rbp
0x14005d426  pop     rbx
0x14005d427  retn
0x14005d429  mov     rcx, [rbx+8]
0x14005d42d  mov     dl, 1
0x14005d42f  mov     [rbx+50h], r15
0x14005d433  call    cs:__imp_NetioDereferenceNetBufferList
0x14005d43a  nop     dword ptr [rax+rax+00h]
0x14005d43f  mov     [rbx+8], r15
0x14005d443  jmp     loc_14005D383
0x14005d448  sub     ecx, 2
0x14005d44b  jz      loc_14005D555
0x14005d451  cmp     ecx, 1
0x14005d454  jnz     short loc_14005D3EC
0x14005d456  dec     dword ptr [rbx+68h]
0x14005d459  mov     rax, 0FFFFF78000000008h
0x14005d463  mov     rax, [rax]
0x14005d466  cmp     dword ptr [rbx+68h], 0
0x14005d46a  jnz     short loc_14005D46F
0x14005d46c  mov     [rbx], r15d
0x14005d46f  mov     ecx, 50h ; 'P'
0x14005d474  mov     edx, 48h ; 'H'
0x14005d479  jmp     loc_14005D3E6
0x14005d47e  test    ecx, ecx
0x14005d480  jnz     loc_14005D52C
0x14005d486  mov     dword ptr [r14], 3
0x14005d48d  lea     rax, [r14+38h]
0x14005d491  xorps   xmm0, xmm0
0x14005d494  movups  xmmword ptr [rax], xmm0
0x14005d497  movups  xmmword ptr [rax+10h], xmm0
0x14005d49b  movups  xmmword ptr [rax+20h], xmm0
0x14005d49f  movups  xmmword ptr [r14+8], xmm0
0x14005d4a4  movups  xmmword ptr [r14+18h], xmm0
0x14005d4a9  movups  xmmword ptr [r14+28h], xmm0
0x14005d4ae  mov     [r14+68h], esi
0x14005d4b2  mov     rcx, [rdx]
0x14005d4b5  jmp     loc_14005D1FC
0x14005d4ba  mov     r9, [rsp+118h+var_78]
0x14005d4c2  lea     r8, [rsp+118h+WatchdogInformation]
0x14005d4ca  mov     dword ptr [rsp+118h+var_E0], r15d
0x14005d4cf  lea     rdx, INET_INSPECT
0x14005d4d6  mov     dword ptr [rsp+118h+var_E8], esi
0x14005d4da  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14005d4e1  mov     dword ptr [rsp+118h+var_F0], 5
0x14005d4e9  mov     qword ptr [rsp+118h+var_F8], r13
0x14005d4ee  mov     qword ptr [rsp+118h+WatchdogInformation.DpcWatchdogLimit], r15
0x14005d4f6  mov     qword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], r9
0x14005d4fe  call    McTemplateK0ppqqq_EtwWriteTransfer
0x14005d503  jmp     loc_14005D402
0x14005d508  mov     rax, [rbx+8]
0x14005d50c  mov     dword ptr [rax+8Ch], 0C0220104h
0x14005d516  jmp     loc_14005D383
0x14005d51b  mov     eax, [r13+30h]
0x14005d51f  test    al, 10h
0x14005d521  jnz     loc_14005D280
0x14005d527  jmp     loc_14005D26A
0x14005d52c  sub     ecx, 2
0x14005d52f  jnz     short loc_14005D53D
0x14005d531  mov     rcx, [rdx]
0x14005d534  lea     rax, [r14+10h]
0x14005d538  jmp     loc_14005D1FC
0x14005d53d  cmp     ecx, esi
0x14005d53f  jnz     loc_14005D200
0x14005d545  inc     dword ptr [r14+68h]
0x14005d549  lea     rax, [r14+38h]
0x14005d54d  mov     rcx, [rdx]
0x14005d550  jmp     loc_14005D1FC
0x14005d555  mov     rax, 0FFFFF78000000008h
0x14005d55f  mov     ecx, 28h ; '('
0x14005d564  mov     edx, 20h ; ' '
0x14005d569  mov     rax, [rax]
0x14005d56c  jmp     loc_14005D3E6
0x14005d571  test    rbx, rbx
0x14005d574  jz      loc_14005D60F
0x14005d57a  movzx   eax, byte ptr [rbx+10h]
0x14005d57e  movzx   r8d, r12w
0x14005d582  mov     r9d, [rbx+30h]
0x14005d586  and     al, sil
0x14005d589  mov     ecx, [rsp+118h+arg_48]
0x14005d590  mov     edx, edi
0x14005d592  mov     [rsp+118h+var_88], r15
0x14005d59a  sub     r9d, ecx
0x14005d59d  mov     byte ptr [rsp+118h+var_90], al
0x14005d5a4  mov     rax, [rbx+8]
0x14005d5a8  mov     dword ptr [rsp+118h+var_98], r15d
0x14005d5b0  mov     [rsp+118h+var_A0], r15
0x14005d5b5  mov     [rsp+118h+var_A8], rax
0x14005d5ba  mov     eax, [rbx+40h]
0x14005d5bd  mov     [rsp+118h+var_B0], r15
0x14005d5c2  mov     dword ptr [rsp+118h+var_B8], eax
0x14005d5c6  mov     rax, [rbx+38h]
0x14005d5ca  mov     [rsp+118h+var_C0], rax
0x14005d5cf  movzx   eax, bp
0x14005d5d2  mov     [rsp+118h+var_C8], ecx
0x14005d5d6  mov     rcx, r13
0x14005d5d9  mov     dword ptr [rsp+118h+var_D0], r9d
0x14005d5de  mov     r9, [rbx+20h]
0x14005d5e2  mov     byte ptr [rsp+118h+var_D8], sil
0x14005d5e7  mov     [rsp+118h+var_E0], 0
0x14005d5ec  mov     word ptr [rsp+118h+var_E8], ax
0x14005d5f1  movzx   eax, r14w
0x14005d5f5  mov     [rsp+118h+var_F0], ax
0x14005d5fa  mov     rax, [rbx+18h]
0x14005d5fe  mov     qword ptr [rsp+118h+var_F8], rax
0x14005d603  call    ProcessAleForTcpFastPath
0x14005d608  mov     esi, eax
0x14005d60a  jmp     loc_14005D35F
0x14005d60f  test    r13, r13
0x14005d612  jz      loc_14005D57A
0x14005d618  xor     r8d, r8d
0x14005d61b  mov     rcx, r13; SpinLock
0x14005d61e  call    WfpAleCanPermitTcpDatagramGroup
0x14005d623  test    al, al
0x14005d625  jz      loc_14005D57A
0x14005d62b  xor     ecx, ecx; ProcNumber
0x14005d62d  mov     [r15], sil
0x14005d630  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005d637  nop     dword ptr [rax+rax+00h]
0x14005d63c  lea     ecx, [rax+rax*8]
0x14005d63f  mov     rax, cs:gWfpPerProContext
0x14005d646  shl     ecx, 3
0x14005d649  mov     rbx, [rcx+rax]
0x14005d64d  mov     ecx, [rbx]
0x14005d64f  cmp     ecx, esi
0x14005d651  jnz     short loc_14005D697
0x14005d653  xorps   xmm0, xmm0
0x14005d656  lea     rcx, [rsp+118h+WatchdogInformation]; WatchdogInformation
0x14005d65e  xor     eax, eax
0x14005d660  movups  xmmword ptr [rsp+118h+WatchdogInformation.DpcTimeLimit], xmm0
0x14005d668  mov     [rsp+118h+WatchdogInformation.Reserved], eax
0x14005d66f  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14005d676  nop     dword ptr [rax+rax+00h]
0x14005d67b  mov     eax, [rsp+118h+WatchdogInformation.DpcTimeCount]
0x14005d682  mov     edx, 30h ; '0'
  ... truncated ...
```

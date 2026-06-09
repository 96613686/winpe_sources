# AddToChangedDestLists

- ea: `0x1800027d8`
- end: `0x180002be4`
- name: `AddToChangedDestLists`
- size: `1036`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`
- `0x18000d9d0`

## callees

- `0x1800027d8`
- `0x180002cb0`
- `0x180009d14`
- `0x18000dc60`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringA` at `0x180002982`
- `ntdll!RtlIpv6AddressToStringA` at `0x180002982`
- `KERNEL32!EnterCriticalSection` at `0x180002aae`
- `KERNEL32!EnterCriticalSection` at `0x180002b05`
- `KERNEL32!EnterCriticalSection` at `0x180002aae`
- `KERNEL32!EnterCriticalSection` at `0x180002b05`
- `KERNEL32!LeaveCriticalSection` at `0x180002ad8`
- `KERNEL32!LeaveCriticalSection` at `0x180002bb1`
- `KERNEL32!LeaveCriticalSection` at `0x180002ad8`
- `KERNEL32!LeaveCriticalSection` at `0x180002bb1`
- `KERNEL32!CreateTimerQueueTimer` at `0x180002b39`
- `KERNEL32!CreateTimerQueueTimer` at `0x180002b39`
- `KERNEL32!GetLastError` at `0x180002b43`
- `KERNEL32!GetLastError` at `0x180002b43`
- `WS2_32!__imp_htonl` at `0x1800029d4`
- `WS2_32!__imp_htonl` at `0x1800029d4`

## pseudocode

```c
void __fastcall AddToChangedDestLists(char *Parameter, __int64 a2, int a3)
{
  int v6; // edx
  int v7; // eax
  int v8; // edx
  int v9; // ecx
  unsigned int v10; // r12d
  int v11; // eax
  __int64 v12; // r13
  __int64 v13; // r12
  char v14; // bl
  __int128 *v15; // r9
  __int16 v16; // ax
  DWORD v17; // r8d
  u_long v18; // eax
  u_long v19; // ecx
  __int128 *v20; // r9
  char *v21; // rbx
  _QWORD *v22; // rdx
  DWORD LastError; // eax
  __int128 *v24; // r9
  DWORD DueTime[2]; // [rsp+20h] [rbp-E0h]
  DWORD Period[2]; // [rsp+28h] [rbp-D8h]
  DWORD pLength[4]; // [rsp+50h] [rbp-B0h] BYREF
  ULONG uliInst[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+80h] [rbp-80h] BYREF
  __int128 v31; // [rsp+84h] [rbp-7Ch]
  __int128 v32; // [rsp+94h] [rbp-6Ch]
  int v33; // [rsp+A4h] [rbp-5Ch]
  CHAR S[80]; // [rsp+B0h] [rbp-50h] BYREF
  int v35; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v36[2044]; // [rsp+104h] [rbp+4h] BYREF

  pLength[0] = 0;
  *(_QWORD *)uliInst = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v30 = 0;
  v33 = 0;
  v6 = *(_DWORD *)(a2 + 48);
  v7 = a3 & v6;
  v8 = ~v6;
  v9 = ~v7 & (*(_DWORD *)(a2 + 44) | a3 & v8);
  v31 = 0;
  *(_DWORD *)(a2 + 44) = v9;
  v32 = 0;
  v29 = 0;
  if ( *(_QWORD *)(a2 + 8) )
    return;
  if ( (v9 & v8) == 0 )
    return;
  v10 = *(_DWORD *)(a2 + 84);
  GetInstance((LPSPropValue)*(unsigned __int16 *)(*((_QWORD *)Parameter + 2) + 4LL), 0, (ULONG)uliInst);
  if ( v11 )
    return;
  v12 = *(_QWORD *)uliInst;
  v13 = (v10 >> 8) & 0xF;
  LOBYTE(uliInst[0]) = byte_18002BD1A & 8;
  if ( (byte_18002BD1A & 8) != 0 )
  {
    LOWORD(v35) = 0;
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v35, L"Adding dest %p to change list %d: ", a2, (unsigned int)v13);
    v14 = byte_18002BD1A;
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v15 = &v29;
      if ( v12 != -48 )
        LODWORD(v15) = v12 + 48;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
        (unsigned int)&v35,
        (_DWORD)v15,
        0,
        (__int64)&v30);
      v14 = byte_18002BD1A;
    }
    if ( *(_WORD *)(a2 + 80) == 23 )
    {
      *(_OWORD *)uliInst = 0;
      memset_0(S, 0, 0x41u);
      RtmConvertNetAddressToIpv6AddressAndLength((PRTM_NET_ADDRESS)(a2 + 80), (PIN6_ADDR)uliInst, pLength, 0x10u);
      if ( (v14 & 8) != 0 )
      {
        LOWORD(v35) = 0;
        LOWORD(v30) = 0;
        RtlIpv6AddressToStringA((const struct in6_addr *)uliInst, S);
        FormatRRASErrorString(&v35, L"address is %S  mask %d", S, pLength[0]);
        if ( (byte_18002BD1A & 8) != 0 )
        {
LABEL_18:
          v20 = &v29;
          if ( v12 != -48 )
            LODWORD(v20) = v12 + 48;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
            (unsigned int)&v35,
            (_DWORD)v20,
            0,
            (__int64)&v30);
        }
      }
    }
    else
    {
      v16 = *(_WORD *)(a2 + 82);
      v17 = *(_DWORD *)(a2 + 84);
      pLength[0] = v17;
      if ( v16 )
      {
        v18 = htonl(-1 << (32 - v16));
        v14 = byte_18002BD1A;
        v17 = pLength[0];
        v19 = v18;
      }
      else
      {
        v19 = 0;
      }
      if ( (v14 & 8) != 0 )
      {
        LOWORD(v35) = 0;
        LOWORD(v30) = 0;
        Period[0] = HIBYTE(v17);
        DueTime[0] = BYTE2(v17);
        FormatRRASErrorString(
          &v35,
          L"Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d",
          (unsigned __int8)v17,
          BYTE1(v17),
          *(_QWORD *)DueTime,
          *(_QWORD *)Period,
          (unsigned __int8)v19,
          BYTE1(v19),
          BYTE2(v19),
          HIBYTE(v19));
        if ( (byte_18002BD1A & 8) != 0 )
          goto LABEL_18;
      }
    }
  }
  v21 = &Parameter[72 * v13];
  EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 1088));
  v22 = (_QWORD *)*((_QWORD *)v21 + 143);
  *(_QWORD *)(a2 + 8) = *v22;
  *v22 = a2 + 8;
  *((_QWORD *)v21 + 143) = a2 + 8;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v21 + 1088));
  _InterlockedAdd((volatile signed __int32 *)a2, 1u);
  if ( _InterlockedIncrement((volatile signed __int32 *)Parameter + 268) == 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1016));
    if ( !CreateTimerQueueTimer(
            (PHANDLE)Parameter + 133,
            *((HANDLE *)Parameter + 92),
            (WAITORTIMERCALLBACK)ProcessChangedDestLists,
            Parameter,
            0xFAu,
            0xF4240u,
            0) )
    {
      LastError = GetLastError();
      if ( (byte_18002BD1A & 0x10) != 0 )
      {
        LOWORD(v35) = 0;
        LOWORD(v30) = 0;
        FormatRRASErrorString(&v35, L"Timer queue creation failed with error: 0x%x", LastError);
        if ( (byte_18002BD1A & 0x10) != 0 )
        {
          v24 = &v29;
          if ( v12 != -48 )
            LODWORD(v24) = v12 + 48;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RRAS_RTM_PARAM_TRACE_ERROR,
            (unsigned int)&v35,
            (_DWORD)v24,
            0,
            (__int64)&v30);
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 1016));
  }
}

```

## disassembly

```asm
0x1800027d8  mov     [rsp-8+arg_10], rbx
0x1800027dd  push    rbp
0x1800027de  push    rsi
0x1800027df  push    rdi
0x1800027e0  push    r12
0x1800027e2  push    r13
0x1800027e4  push    r14
0x1800027e6  push    r15
0x1800027e8  lea     rbp, [rsp-810h]
0x1800027f0  sub     rsp, 910h
0x1800027f7  mov     rax, cs:__security_cookie
0x1800027fe  xor     rax, rsp
0x180002801  mov     [rbp+840h+var_40], rax
0x180002808  xor     edi, edi
0x18000280a  mov     ebx, r8d
0x18000280d  mov     r15, rdx
0x180002810  mov     [rsp+940h+pLength], edi
0x180002814  mov     rsi, rcx
0x180002817  mov     qword ptr [rsp+940h+uliInst], rdi
0x18000281c  xor     edx, edx; Val
0x18000281e  mov     [rbp+840h+var_840], edi
0x180002821  mov     r8d, 7FCh; Size
0x180002827  lea     rcx, [rbp+840h+var_83C]; void *
0x18000282b  mov     r14d, edi
0x18000282e  call    memset_0
0x180002833  xor     eax, eax
0x180002835  mov     [rbp+840h+var_8C0], edi
0x180002838  mov     [rbp+840h+var_89C], eax
0x18000283b  xorps   xmm0, xmm0
0x18000283e  mov     eax, [r15+30h]
0x180002842  mov     edx, eax
0x180002844  and     eax, ebx
0x180002846  not     edx
0x180002848  mov     ecx, edx
0x18000284a  not     eax
0x18000284c  and     ecx, ebx
0x18000284e  or      ecx, [r15+2Ch]
0x180002852  and     ecx, eax
0x180002854  movups  [rbp+840h+var_8BC], xmm0
0x180002858  mov     [r15+2Ch], ecx
0x18000285c  movups  [rbp+840h+var_8AC], xmm0
0x180002860  movups  [rsp+940h+var_8D0], xmm0
0x180002865  cmp     [r15+8], rdi
0x180002869  jnz     loc_180002BB7
0x18000286f  test    edx, ecx
0x180002871  jz      loc_180002BB7
0x180002877  mov     rcx, [rsi+10h]
0x18000287b  lea     r8, [rsp+940h+uliInst]; uliInst
0x180002880  mov     r12d, [r15+54h]
0x180002884  xor     edx, edx; lpPropSv
0x180002886  movzx   ecx, word ptr [rcx+4]; lpPropMv
0x18000288a  call    GetInstance
0x18000288f  mov     r14d, eax
0x180002892  test    eax, eax
0x180002894  jnz     loc_180002BBA
0x18000289a  mov     al, cs:byte_18002BD1A
0x1800028a0  mov     r13, qword ptr [rsp+940h+uliInst]
0x1800028a5  shr     r12d, 8
0x1800028a9  and     r12d, 0Fh
0x1800028ad  and     al, 8
0x1800028af  mov     byte ptr [rsp+940h+uliInst], al
0x1800028b3  jz      loc_180002A9F
0x1800028b9  mov     eax, edi
0x1800028bb  mov     word ptr [rbp+840h+var_840], di
0x1800028bf  mov     r9d, r12d
0x1800028c2  mov     word ptr [rbp+840h+var_8C0], ax
0x1800028c6  mov     r8, r15
0x1800028c9  lea     rdx, aAddingDestPToC; "Adding dest %p to change list %d: "
0x1800028d0  lea     rcx, [rbp+840h+var_840]
0x1800028d4  call    FormatRRASErrorString
0x1800028d9  mov     bl, cs:byte_18002BD1A
0x1800028df  test    bl, 8
0x1800028e2  jz      short loc_18000291F
0x1800028e4  lea     rax, [r13+30h]
0x1800028e8  test    rax, rax
0x1800028eb  lea     r9, [rsp+940h+var_8D0]
0x1800028f0  lea     r8, [rbp+840h+var_840]
0x1800028f4  cmovnz  r9, rax
0x1800028f8  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800028ff  lea     rax, [rbp+840h+var_8C0]
0x180002903  mov     qword ptr [rsp+940h+Period], rax
0x180002908  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000290f  mov     qword ptr [rsp+940h+DueTime], rdi
0x180002914  call    McTemplateU0zjzz_EventWriteTransfer
0x180002919  mov     bl, cs:byte_18002BD1A
0x18000291f  cmp     word ptr [r15+50h], 17h
0x180002925  jnz     loc_1800029B3
0x18000292b  xor     edx, edx; Val
0x18000292d  lea     rcx, [rbp+840h+S]; void *
0x180002931  xorps   xmm0, xmm0
0x180002934  movups  xmmword ptr [rsp+940h+uliInst], xmm0
0x180002939  lea     r8d, [rdx+41h]; Size
0x18000293d  call    memset_0
0x180002942  mov     r9d, 10h; dwAddressSize
0x180002948  lea     r8, [rsp+940h+pLength]; pLength
0x18000294d  lea     rdx, [rsp+940h+uliInst]; pAddress
0x180002952  lea     rcx, [r15+50h]; pNetAddress
0x180002956  call    RtmConvertNetAddressToIpv6AddressAndLength
0x18000295b  test    bl, 8
0x18000295e  jz      loc_180002A9F
0x180002964  movaps  xmm0, xmmword ptr [rsp+940h+uliInst]
0x180002969  lea     rdx, [rbp+840h+S]; S
0x18000296d  xor     ebx, ebx
0x18000296f  movdqa  xmmword ptr [rsp+940h+uliInst], xmm0
0x180002975  lea     rcx, [rsp+940h+uliInst]; Addr
0x18000297a  mov     word ptr [rbp+840h+var_840], bx
0x18000297e  mov     word ptr [rbp+840h+var_8C0], bx
0x180002982  call    cs:__imp_RtlIpv6AddressToStringA
0x180002988  mov     r9d, [rsp+940h+pLength]
0x18000298d  lea     r8, [rbp+840h+S]
0x180002991  lea     rdx, aAddressIsSMask; "address is %S  mask %d"
0x180002998  lea     rcx, [rbp+840h+var_840]
0x18000299c  call    FormatRRASErrorString
0x1800029a1  test    cs:byte_18002BD1A, 8
0x1800029a8  jz      loc_180002A9F
0x1800029ae  jmp     loc_180002A6A
0x1800029b3  movzx   eax, word ptr [r15+52h]
0x1800029b8  xor     edx, edx
0x1800029ba  mov     r8d, [r15+54h]
0x1800029be  mov     [rsp+940h+pLength], r8d
0x1800029c3  test    ax, ax
0x1800029c6  jz      short loc_1800029EB
0x1800029c8  lea     ecx, [rdx+20h]
0x1800029cb  sub     ecx, eax
0x1800029cd  or      eax, 0FFFFFFFFh
0x1800029d0  shl     eax, cl
0x1800029d2  mov     ecx, eax; hostlong
0x1800029d4  call    cs:__imp_htonl
0x1800029da  mov     bl, cs:byte_18002BD1A
0x1800029e0  xor     edx, edx
0x1800029e2  mov     r8d, [rsp+940h+pLength]
0x1800029e7  mov     ecx, eax
0x1800029e9  jmp     short loc_1800029ED
0x1800029eb  mov     ecx, edx
0x1800029ed  test    bl, 8
0x1800029f0  jz      loc_180002A9F
0x1800029f6  mov     eax, ecx
0x1800029f8  mov     word ptr [rbp+840h+var_840], dx
0x1800029fc  shr     eax, 10h
0x1800029ff  mov     edi, ecx
0x180002a01  movzx   ebx, al
0x180002a04  mov     r10d, r8d
0x180002a07  mov     eax, ecx
0x180002a09  mov     word ptr [rbp+840h+var_8C0], dx
0x180002a0d  shr     eax, 8
0x180002a10  movzx   r11d, al
0x180002a14  mov     eax, r8d
0x180002a17  movzx   edx, cl
0x180002a1a  shr     eax, 10h
0x180002a1d  movzx   ecx, al
0x180002a20  mov     eax, r8d
0x180002a23  shr     r10d, 18h
0x180002a27  shr     eax, 8
0x180002a2a  shr     edi, 18h
0x180002a2d  mov     [rsp+940h+var_8F8], edi
0x180002a31  mov     [rsp+940h+var_900], ebx
0x180002a35  mov     [rsp+940h+var_908], r11d
0x180002a3a  mov     [rsp+940h+Flags], edx
0x180002a3e  lea     rdx, aDestDDDDMaskDD; "Dest: %d.%d.%d.%d Mask: %d.%d.%d.%d"
0x180002a45  mov     [rsp+940h+Period], r10d
0x180002a4a  mov     [rsp+940h+DueTime], ecx
0x180002a4e  lea     rcx, [rbp+840h+var_840]
0x180002a52  movzx   r9d, al
0x180002a56  movzx   r8d, r8b
0x180002a5a  call    FormatRRASErrorString
0x180002a5f  test    cs:byte_18002BD1A, 8
0x180002a66  jz      short loc_180002A9F
0x180002a68  xor     ebx, ebx
0x180002a6a  lea     rax, [r13+30h]
0x180002a6e  test    rax, rax
0x180002a71  lea     r9, [rsp+940h+var_8D0]
0x180002a76  lea     r8, [rbp+840h+var_840]
0x180002a7a  cmovnz  r9, rax
0x180002a7e  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x180002a85  lea     rax, [rbp+840h+var_8C0]
0x180002a89  mov     qword ptr [rsp+940h+Period], rax
0x180002a8e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002a95  mov     qword ptr [rsp+940h+DueTime], rbx
0x180002a9a  call    McTemplateU0zjzz_EventWriteTransfer
0x180002a9f  lea     rdi, [r12+r12*8]
0x180002aa3  lea     rbx, [rsi+rdi*8]
0x180002aa7  lea     rcx, [rbx+440h]; lpCriticalSection
0x180002aae  call    cs:__imp_EnterCriticalSection
0x180002ab4  mov     rdx, [rsi+rdi*8+478h]
0x180002abc  lea     rcx, [r15+8]
0x180002ac0  mov     rax, [rdx]
0x180002ac3  mov     [rcx], rax
0x180002ac6  mov     [rdx], rcx
0x180002ac9  mov     [rsi+rdi*8+478h], rcx
0x180002ad1  lea     rcx, [rbx+440h]; lpCriticalSection
0x180002ad8  call    cs:__imp_LeaveCriticalSection
0x180002ade  mov     ecx, 1
0x180002ae3  lock add [r15], ecx
0x180002ae7  mov     eax, ecx
0x180002ae9  lock xadd [rsi+430h], eax
0x180002af1  add     eax, ecx
0x180002af3  cmp     eax, ecx
0x180002af5  jnz     loc_180002BB7
0x180002afb  lea     rbx, [rsi+3F8h]
0x180002b02  mov     rcx, rbx; lpCriticalSection
0x180002b05  call    cs:__imp_EnterCriticalSection
0x180002b0b  mov     rdx, [rsi+2E0h]; TimerQueue
0x180002b12  lea     rcx, [rsi+428h]; phNewTimer
0x180002b19  xor     edi, edi
0x180002b1b  lea     r8, ProcessChangedDestLists; Callback
0x180002b22  mov     [rsp+940h+Flags], edi; Flags
0x180002b26  mov     r9, rsi; Parameter
0x180002b29  mov     [rsp+940h+Period], 0F4240h; Period
0x180002b31  mov     [rsp+940h+DueTime], 0FAh; DueTime
0x180002b39  call    cs:__imp_CreateTimerQueueTimer
0x180002b3f  test    eax, eax
0x180002b41  jnz     short loc_180002BAE
0x180002b43  call    cs:__imp_GetLastError
0x180002b49  test    cs:byte_18002BD1A, 10h
0x180002b50  mov     r14d, eax
0x180002b53  jz      short loc_180002BAE
0x180002b55  mov     r8d, eax
0x180002b58  mov     word ptr [rbp+840h+var_840], di
0x180002b5c  lea     rdx, aTimerQueueCrea; "Timer queue creation failed with error:"...
0x180002b63  mov     word ptr [rbp+840h+var_8C0], di
0x180002b67  lea     rcx, [rbp+840h+var_840]
0x180002b6b  call    FormatRRASErrorString
0x180002b70  test    cs:byte_18002BD1A, 10h
0x180002b77  jz      short loc_180002BAE
0x180002b79  lea     rax, [r13+30h]
0x180002b7d  test    rax, rax
0x180002b80  lea     r9, [rsp+940h+var_8D0]
0x180002b85  lea     r8, [rbp+840h+var_840]
0x180002b89  cmovnz  r9, rax
0x180002b8d  lea     rdx, RRAS_RTM_PARAM_TRACE_ERROR
0x180002b94  lea     rax, [rbp+840h+var_8C0]
0x180002b98  mov     qword ptr [rsp+940h+Period], rax
0x180002b9d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002ba4  mov     qword ptr [rsp+940h+DueTime], rdi
0x180002ba9  call    McTemplateU0zjzz_EventWriteTransfer
0x180002bae  mov     rcx, rbx; lpCriticalSection
0x180002bb1  call    cs:__imp_LeaveCriticalSection
0x180002bb7  mov     eax, r14d
0x180002bba  mov     rcx, [rbp+840h+var_40]
0x180002bc1  xor     rcx, rsp; StackCookie
0x180002bc4  call    __security_check_cookie
0x180002bc9  mov     rbx, [rsp+940h+arg_10]
0x180002bd1  add     rsp, 910h
0x180002bd8  pop     r15
0x180002bda  pop     r14
0x180002bdc  pop     r13
0x180002bde  pop     r12
0x180002be0  pop     rdi
0x180002be1  pop     rsi
0x180002be2  pop     rbp
0x180002be3  retn
```

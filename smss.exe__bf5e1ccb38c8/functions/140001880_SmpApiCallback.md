# SmpApiCallback

- ea: `0x140001880`
- end: `0x140001e30`
- name: `SmpApiCallback`
- size: `1456`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001880`
- `0x140001e40`
- `0x140001f60`
- `0x140004ec0`
- `0x140005ac4`
- `0x140017740`
- `0x140017ac0`
- `0x140017e28`
- `0x14001cc29`
- `0x14001cc40`
- `0x14001e010`

## import_xrefs

- `ntdll!NtClose` at `0x140001b19`
- `ntdll!NtClose` at `0x140001dc5`
- `ntdll!NtClose` at `0x140001b19`
- `ntdll!NtClose` at `0x140001dc5`
- `ntdll!RtlFreeHeap` at `0x140001b3b`
- `ntdll!RtlFreeHeap` at `0x140001b3b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140001a69`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140001ab7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140001c4b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140001a69`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140001ab7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140001c4b`
- `ntdll!NtAlpcDisconnectPort` at `0x140001b0f`
- `ntdll!NtAlpcDisconnectPort` at `0x140001b0f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140001aa4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140001b23`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140001b87`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140001c94`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140001aa4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140001b23`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140001b87`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140001c94`
- `ntdll!TpSetPoolMinThreads` at `0x140001a93`
- `ntdll!TpSetPoolMinThreads` at `0x140001c79`
- `ntdll!TpSetPoolMinThreads` at `0x140001a93`
- `ntdll!TpSetPoolMinThreads` at `0x140001c79`
- `ntdll!RtlSetThreadIsCritical` at `0x1400018f1`
- `ntdll!RtlSetThreadIsCritical` at `0x140001ddc`
- `ntdll!RtlSetThreadIsCritical` at `0x1400018f1`
- `ntdll!RtlSetThreadIsCritical` at `0x140001ddc`
- `ntdll!AlpcInitializeMessageAttribute` at `0x14000192d`
- `ntdll!AlpcInitializeMessageAttribute` at `0x14000192d`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14000197e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140001b6a`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14000197e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140001b6a`
- `ntdll!AlpcGetMessageAttribute` at `0x14000199c`
- `ntdll!AlpcGetMessageAttribute` at `0x1400019af`
- `ntdll!AlpcGetMessageAttribute` at `0x140001d26`
- `ntdll!AlpcGetMessageAttribute` at `0x14000199c`
- `ntdll!AlpcGetMessageAttribute` at `0x1400019af`
- `ntdll!AlpcGetMessageAttribute` at `0x140001d26`
- `ntdll!NtAlpcCancelMessage` at `0x140001d34`
- `ntdll!NtAlpcCancelMessage` at `0x140001d34`

## pseudocode

```c
NTSTATUS __fastcall SmpApiCallback(__int64 a1, __int64 a2)
{
  int v3; // r13d
  __int64 v4; // r15
  _BYTE *v5; // rsi
  int v6; // edi
  char *v7; // rbx
  unsigned int v8; // r12d
  unsigned int v9; // edx
  unsigned int v10; // edi
  unsigned int v11; // eax
  int v12; // ecx
  unsigned int v13; // ecx
  int v14; // eax
  void *v15; // rcx
  __int64 MessageAttribute; // rax
  __int64 v18; // [rsp+40h] [rbp-1D8h]
  int v19; // [rsp+48h] [rbp-1D0h]
  int v20; // [rsp+48h] [rbp-1D0h]
  __int64 v21; // [rsp+50h] [rbp-1C8h] BYREF
  _BYTE *v22; // [rsp+58h] [rbp-1C0h]
  _OWORD v23[2]; // [rsp+60h] [rbp-1B8h] BYREF
  __int64 v24; // [rsp+80h] [rbp-198h]
  _BYTE v25[4]; // [rsp+90h] [rbp-188h] BYREF
  __int16 v26; // [rsp+94h] [rbp-184h]
  unsigned int v27; // [rsp+B8h] [rbp-160h]
  int v28; // [rsp+BCh] [rbp-15Ch]

  memset_0(v25, 0, 0x148u);
  v3 = 0;
  v21 = 0;
  HIDWORD(v18) = 0;
  RtlSetThreadIsCritical(1u, 0, 1u);
  v4 = SmpApiConnectionPort;
  v5 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  AlpcInitializeMessageAttribute(0x20000000, v23, 40, &v21);
  v19 = 0;
  do
  {
    v21 = 328;
    DWORD1(v23[0]) |= 0x20000000u;
    v6 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _BYTE *, __int64 *, _OWORD *, _QWORD, __int64, int))NtAlpcSendWaitReceivePort)(
           v4,
           0x10000,
           0,
           0,
           v25,
           &v21,
           v23,
           0,
           v18,
           v19);
    LODWORD(v18) = v6;
  }
  while ( v6 < 0 );
  v7 = *(char **)AlpcGetMessageAttribute(v23, 0x20000000);
  v8 = *(_DWORD *)(AlpcGetMessageAttribute(v23, 0x20000000) + 16);
  v20 = 0;
  switch ( (unsigned __int8)v26 )
  {
    case 1u:
      v5 = v25;
      v22 = v25;
      v9 = v27;
      if ( v27 >= 9 )
      {
        v28 = -1073741822;
        break;
      }
      if ( dword_14001FA48[4 * v27] )
      {
        v6 = 0;
        RtlAcquireSRWLockExclusive(a2);
        if ( (unsigned int)(++*(_DWORD *)(a2 + 20) + 1) > *(_DWORD *)(a2 + 16) )
        {
          HIDWORD(v18) = *(_DWORD *)(a2 + 20) + 1;
          v6 = TpSetPoolMinThreads(*(_QWORD *)(a2 + 8), HIDWORD(v18));
          if ( v6 < 0 )
            --*(_DWORD *)(a2 + 20);
          else
            *(_DWORD *)(a2 + 16) = HIDWORD(v18);
        }
        RtlReleaseSRWLockExclusive(a2);
        LODWORD(v18) = v6;
        if ( v6 < 0 )
        {
          v28 = -1073741670;
          break;
        }
        HIDWORD(v18) = 1;
        v9 = v27;
      }
      v28 = 259;
      if ( v9 == 8 )
      {
LABEL_7:
        if ( (*v7 & 6) == 0 )
        {
          v6 = SmpEstablishClientSecurity((__int64)v25, (__int64)v7);
          LODWORD(v18) = v6;
          v9 = v27;
        }
        if ( v6 >= 0 )
        {
          if ( (*v7 & 4) != 0 )
          {
            v6 = ((__int64 (__fastcall *)(_BYTE *, char *, __int64))*(&SmpApiDispatch + 2 * (int)v9))(v25, v7, v4);
            LODWORD(v18) = v6;
            v9 = v27;
          }
          else
          {
            v6 = -1073741790;
            LODWORD(v18) = -1073741790;
          }
        }
        if ( v9 == 5 && v6 == 259 )
        {
          v5 = 0;
          v22 = 0;
LABEL_12:
          if ( HIDWORD(v18) )
          {
            RtlAcquireSRWLockExclusive(a2);
            if ( (unsigned int)(*(_DWORD *)(a2 + 20))-- < *(_DWORD *)(a2 + 16) )
            {
              v10 = *(_DWORD *)(a2 + 20) + 1;
              if ( (int)TpSetPoolMinThreads(*(_QWORD *)(a2 + 8), v10) >= 0 )
                *(_DWORD *)(a2 + 16) = v10;
            }
            RtlReleaseSRWLockExclusive(a2);
          }
          break;
        }
      }
      else
      {
        if ( v9 != 1 )
        {
          switch ( v9 )
          {
            case 0u:
            case 2u:
              break;
            case 3u:
            case 4u:
              goto LABEL_36;
            case 5u:
            case 6u:
            case 7u:
              goto LABEL_7;
            default:
              goto LABEL_11;
          }
        }
        if ( (*v7 & 0x10) != 0 )
        {
LABEL_36:
          v6 = ((__int64 (__fastcall *)(_BYTE *, char *, __int64))*(&SmpApiDispatch + 2 * (int)v9))(v25, v7, v4);
          LODWORD(v18) = v6;
        }
        else
        {
          v6 = -1073741811;
          LODWORD(v18) = -1073741811;
        }
      }
LABEL_11:
      v28 = v6;
      goto LABEL_12;
    case 0xAu:
      SmpHandleConnectionRequest(v4, v25, v23, (unsigned __int16)(v26 & 0xFF00) >> 15);
      break;
    case 5u:
      v3 = 1;
      v20 = 1;
      break;
    default:
      if ( (v26 & 0x2000) != 0 )
      {
        MessageAttribute = AlpcGetMessageAttribute(v23, 0x20000000);
        NtAlpcCancelMessage(v4, 0, MessageAttribute);
        v5 = v25;
        v22 = v25;
      }
      break;
  }
  if ( v7 )
  {
    RtlAcquireSRWLockExclusive(v7 + 24);
    if ( v3 )
      *(_DWORD *)v7 |= 1u;
    v11 = *((_DWORD *)v7 + 1);
    v12 = *((_DWORD *)v7 + 2);
    if ( v8 <= v11 )
    {
      v13 = v12 - 1;
      *((_DWORD *)v7 + 2) = v13;
    }
    else
    {
      v13 = v8 + v12 - v11 - 1;
      *((_DWORD *)v7 + 2) = v13;
      *((_DWORD *)v7 + 1) = v8;
    }
    v14 = *(_DWORD *)v7;
    if ( (*(_DWORD *)v7 & 1) == 0 || v13 )
    {
      RtlReleaseSRWLockExclusive(v7 + 24);
    }
    else
    {
      v15 = (void *)*((_QWORD *)v7 + 4);
      if ( (v14 & 0x10) != 0 )
      {
        SmpDereferenceKnownSubSys(v15);
      }
      else if ( (v14 & 8) != 0 )
      {
        SmpDestroyControlBlock(v15);
        SmpReleaseControlBlock(*((PVOID *)v7 + 4));
      }
      else if ( v15 )
      {
        NtClose(v15);
      }
      NtAlpcDisconnectPort(*((_QWORD *)v7 + 2), 1);
      NtClose(*((HANDLE *)v7 + 2));
      RtlReleaseSRWLockExclusive(v7 + 24);
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v7);
    }
  }
  if ( v5 )
    NtAlpcSendWaitReceivePort(v4, 0x10000, v5, 0, 0, 0, 0, 0, v18, v20, v21);
  return RtlSetThreadIsCritical(0, 0, 1u);
}

```

## disassembly

```asm
0x140001880  mov     [rsp+arg_0], rbx
0x140001885  mov     [rsp+arg_10], rsi
0x14000188a  push    rdi
0x14000188b  push    r12
0x14000188d  push    r13
0x14000188f  push    r14
0x140001891  push    r15
0x140001893  sub     rsp, 1F0h
0x14000189a  mov     rax, cs:__security_cookie
0x1400018a1  xor     rax, rsp
0x1400018a4  mov     [rsp+218h+var_38], rax
0x1400018ac  mov     r14, rdx
0x1400018af  xor     edx, edx; Val
0x1400018b1  mov     r8d, 148h; Size
0x1400018b7  lea     rcx, [rsp+218h+var_188]; void *
0x1400018bf  call    memset_0
0x1400018c4  xor     r13d, r13d
0x1400018c7  mov     [rsp+218h+var_1C8], r13
0x1400018cc  xorps   xmm0, xmm0
0x1400018cf  xor     eax, eax
0x1400018d1  movups  [rsp+218h+var_1B8], xmm0
0x1400018d6  movups  [rsp+218h+var_1A8], xmm0
0x1400018db  mov     [rsp+218h+var_198], rax
0x1400018e3  mov     [rsp+218h+var_1D4], r13d
0x1400018e8  mov     r8b, 1; NeedBreaks
0x1400018eb  xor     edx, edx; OldValue
0x1400018ed  movzx   ecx, r8b; NewValue
0x1400018f1  call    cs:__imp_RtlSetThreadIsCritical
0x1400018f7  mov     r15, cs:SmpApiConnectionPort
0x1400018fe  mov     esi, r13d
0x140001901  xorps   xmm0, xmm0
0x140001904  xor     eax, eax
0x140001906  movups  [rsp+218h+var_1B8], xmm0
0x14000190b  movups  [rsp+218h+var_1A8], xmm0
0x140001910  mov     [rsp+218h+var_198], rax
0x140001918  lea     r9, [rsp+218h+var_1C8]
0x14000191d  mov     r8d, 28h ; '('
0x140001923  lea     rdx, [rsp+218h+var_1B8]
0x140001928  mov     ecx, 20000000h
0x14000192d  call    cs:__imp_AlpcInitializeMessageAttribute
0x140001933  nop
0x140001934  mov     [rsp+218h+var_1D0], r13d
0x140001939  mov     [rsp+218h+var_1C8], 148h
0x140001942  or      dword ptr [rsp+218h+var_1B8+4], 20000000h
0x14000194a  mov     [rsp+218h+var_1E0], r13
0x14000194f  lea     rax, [rsp+218h+var_1B8]
0x140001954  mov     [rsp+218h+var_1E8], rax
0x140001959  lea     rax, [rsp+218h+var_1C8]
0x14000195e  mov     [rsp+218h+var_1F0], rax
0x140001963  lea     rax, [rsp+218h+var_188]
0x14000196b  mov     [rsp+218h+var_1F8], rax
0x140001970  xor     r9d, r9d
0x140001973  xor     r8d, r8d
0x140001976  mov     edx, 10000h
0x14000197b  mov     rcx, r15
0x14000197e  call    cs:__imp_NtAlpcSendWaitReceivePort
0x140001984  mov     edi, eax
0x140001986  mov     [rsp+218h+var_1D8], eax
0x14000198a  test    eax, eax
0x14000198c  js      loc_140001DD0
0x140001992  mov     edx, 20000000h
0x140001997  lea     rcx, [rsp+218h+var_1B8]
0x14000199c  call    cs:__imp_AlpcGetMessageAttribute
0x1400019a2  mov     rbx, [rax]
0x1400019a5  mov     edx, 20000000h
0x1400019aa  lea     rcx, [rsp+218h+var_1B8]
0x1400019af  call    cs:__imp_AlpcGetMessageAttribute
0x1400019b5  mov     r12d, [rax+10h]
0x1400019b9  movzx   ecx, [rsp+218h+var_184]
0x1400019c1  mov     edx, 0FFFFFF00h
0x1400019c6  movzx   eax, cx
0x1400019c9  and     ax, dx
0x1400019cc  movzx   edx, ax
0x1400019cf  mov     eax, 0FFh
0x1400019d4  and     cx, ax
0x1400019d7  mov     r9d, edx
0x1400019da  shr     r9d, 0Fh
0x1400019de  mov     [rsp+218h+var_1D0], r13d
0x1400019e3  cmp     cx, 1
0x1400019e7  jnz     loc_140001B8F
0x1400019ed  lea     r10, [rsp+218h+var_188]
0x1400019f5  mov     rsi, r10
0x1400019f8  mov     [rsp+218h+var_1C0], r10
0x1400019fd  movsxd  rdx, [rsp+218h+var_160]
0x140001a05  cmp     edx, 9
0x140001a08  jnb     loc_140001D4F
0x140001a0e  mov     rax, rdx
0x140001a11  add     rax, rax
0x140001a14  lea     r9, cs:140000000h
0x140001a1b  cmp     ds:rva dword_14001FA48[r9+rax*8], 0
0x140001a24  jnz     loc_140001C42
0x140001a2a  mov     [rsp+218h+var_15C], 103h
0x140001a35  cmp     edx, 8
0x140001a38  jnz     loc_140001BB3
0x140001a3e  test    byte ptr [rbx], 6; jumptable 0000000140001C40 cases 5-7
0x140001a41  jz      loc_140001D6F
0x140001a47  test    edi, edi
0x140001a49  jns     loc_140001BE4
0x140001a4f  cmp     edx, 5
0x140001a52  jz      loc_140001CC9
0x140001a58  mov     [rsp+218h+var_15C], edi; jumptable 0000000140001C40 default case, case 1
0x140001a5f  cmp     [rsp+218h+var_1D4], 0
0x140001a64  jz      short loc_140001AAA
0x140001a66  mov     rcx, r14
0x140001a69  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140001a6f  mov     eax, [r14+14h]
0x140001a73  dec     eax
0x140001a75  mov     [r14+14h], eax
0x140001a79  mov     ecx, [r14+14h]
0x140001a7d  inc     ecx
0x140001a7f  mov     eax, [r14+10h]
0x140001a83  cmp     ecx, eax
0x140001a85  jnb     short loc_140001AA1
0x140001a87  mov     edi, [r14+14h]
0x140001a8b  inc     edi
0x140001a8d  mov     edx, edi
0x140001a8f  mov     rcx, [r14+8]
0x140001a93  call    cs:__imp_TpSetPoolMinThreads
0x140001a99  test    eax, eax
0x140001a9b  js      short loc_140001AA1
0x140001a9d  mov     [r14+10h], edi
0x140001aa1  mov     rcx, r14
0x140001aa4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140001aaa  test    rbx, rbx
0x140001aad  jz      loc_140001B41
0x140001ab3  lea     rcx, [rbx+18h]
0x140001ab7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140001abd  test    r13d, r13d
0x140001ac0  jnz     loc_140001D9B
0x140001ac6  mov     eax, [rbx+4]
0x140001ac9  mov     ecx, [rbx+8]
0x140001acc  cmp     r12d, eax
0x140001acf  jbe     loc_140001B79
0x140001ad5  sub     ecx, eax
0x140001ad7  dec     ecx
0x140001ad9  add     ecx, r12d
0x140001adc  mov     [rbx+8], ecx
0x140001adf  mov     [rbx+4], r12d
0x140001ae3  mov     eax, [rbx]
0x140001ae5  test    al, 1
0x140001ae7  jz      loc_140001B83
0x140001aed  test    ecx, ecx
0x140001aef  jnz     loc_140001B83
0x140001af5  mov     rcx, [rbx+20h]; BaseAddress
0x140001af9  test    al, 10h
0x140001afb  jz      loc_140001DA3
0x140001b01  call    SmpDereferenceKnownSubSys
0x140001b06  mov     edx, 1
0x140001b0b  mov     rcx, [rbx+10h]
0x140001b0f  call    cs:__imp_NtAlpcDisconnectPort
0x140001b15  mov     rcx, [rbx+10h]; Handle
0x140001b19  call    cs:__imp_NtClose
0x140001b1f  lea     rcx, [rbx+18h]
0x140001b23  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140001b29  mov     rcx, gs:60h
0x140001b32  mov     r8, rbx; BaseAddress
0x140001b35  xor     edx, edx; Flags
0x140001b37  mov     rcx, [rcx+30h]; HeapHandle
0x140001b3b  call    cs:__imp_RtlFreeHeap
0x140001b41  test    rsi, rsi
0x140001b44  jz      short loc_140001B74
0x140001b46  xor     eax, eax
0x140001b48  mov     [rsp+218h+var_1E0], rax
0x140001b4d  mov     [rsp+218h+var_1E8], rax
0x140001b52  mov     [rsp+218h+var_1F0], rax
0x140001b57  mov     [rsp+218h+var_1F8], rax
0x140001b5c  xor     r9d, r9d
0x140001b5f  mov     r8, rsi
0x140001b62  mov     edx, 10000h
0x140001b67  mov     rcx, r15
0x140001b6a  call    cs:__imp_NtAlpcSendWaitReceivePort
0x140001b70  mov     [rsp+218h+var_1D8], eax
0x140001b74  jmp     loc_140001DD5
0x140001b79  dec     ecx
0x140001b7b  mov     [rbx+8], ecx
0x140001b7e  jmp     loc_140001AE3
0x140001b83  lea     rcx, [rbx+18h]
0x140001b87  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140001b8d  jmp     short loc_140001B41
0x140001b8f  cmp     cx, 0Ah
0x140001b93  jnz     loc_140001CE1
0x140001b99  lea     r8, [rsp+218h+var_1B8]
0x140001b9e  lea     rdx, [rsp+218h+var_188]
0x140001ba6  mov     rcx, r15
0x140001ba9  call    SmpHandleConnectionRequest
0x140001bae  jmp     loc_140001AAA
0x140001bb3  cmp     edx, 1
0x140001bb6  jnz     short loc_140001C29
0x140001bb8  test    byte ptr [rbx], 10h; jumptable 0000000140001C40 cases 0,2
0x140001bbb  jz      short loc_140001C1B
0x140001bbd  movsxd  rax, edx; jumptable 0000000140001C40 cases 3,4
0x140001bc0  add     rax, rax
0x140001bc3  mov     r8, r15
0x140001bc6  mov     rdx, rbx
0x140001bc9  mov     rcx, r10
0x140001bcc  mov     rax, ds:(SmpApiDispatch - 140000000h)[r9+rax*8]
0x140001bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001bd9  mov     edi, eax
0x140001bdb  mov     [rsp+218h+var_1D8], eax
0x140001bdf  jmp     def_140001C40; jumptable 0000000140001C40 default case, case 1
0x140001be4  test    byte ptr [rbx], 4
0x140001be7  jz      loc_140001CF7
0x140001bed  movsxd  rax, edx
0x140001bf0  add     rax, rax
0x140001bf3  mov     r8, r15
0x140001bf6  mov     rdx, rbx
0x140001bf9  mov     rcx, r10
0x140001bfc  mov     rax, ds:(SmpApiDispatch - 140000000h)[r9+rax*8]
0x140001c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c09  mov     edi, eax
0x140001c0b  mov     [rsp+218h+var_1D8], eax
0x140001c0f  mov     edx, [rsp+218h+var_160]
0x140001c16  jmp     loc_140001A4F
0x140001c1b  mov     edi, 0C000000Dh
0x140001c20  mov     [rsp+218h+var_1D8], edi
0x140001c24  jmp     def_140001C40; jumptable 0000000140001C40 default case, case 1
0x140001c29  cmp     edx, 7; switch 8 cases
0x140001c2c  ja      def_140001C40; jumptable 0000000140001C40 default case, case 1
0x140001c32  movsxd  rax, edx
0x140001c35  mov     ecx, ds:(jpt_140001C40 - 140000000h)[r9+rax*4]
0x140001c3d  add     rcx, r9
0x140001c40  jmp     rcx; switch jump
0x140001c42  xor     edi, edi
0x140001c44  mov     [rsp+218h+var_1CC], edi
0x140001c48  mov     rcx, r14
0x140001c4b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140001c51  mov     eax, [r14+14h]
0x140001c55  inc     eax
0x140001c57  mov     [r14+14h], eax
0x140001c5b  mov     ecx, [r14+14h]
0x140001c5f  inc     ecx
0x140001c61  mov     eax, [r14+10h]
0x140001c65  cmp     ecx, eax
0x140001c67  jbe     short loc_140001C91
0x140001c69  mov     eax, [r14+14h]
0x140001c6d  inc     eax
0x140001c6f  mov     [rsp+218h+var_1D4], eax
0x140001c73  mov     edx, eax
0x140001c75  mov     rcx, [r14+8]
0x140001c79  call    cs:__imp_TpSetPoolMinThreads
0x140001c7f  mov     edi, eax
0x140001c81  mov     [rsp+218h+var_1CC], eax
0x140001c85  test    eax, eax
0x140001c87  js      short loc_140001D05
0x140001c89  mov     eax, [rsp+218h+var_1D4]
0x140001c8d  mov     [r14+10h], eax
0x140001c91  mov     rcx, r14
0x140001c94  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140001c9a  mov     [rsp+218h+var_1D8], edi
0x140001c9e  test    edi, edi
0x140001ca0  js      loc_140001D5F
0x140001ca6  mov     [rsp+218h+var_1D4], 1
0x140001cae  mov     edx, [rsp+218h+var_160]
0x140001cb5  lea     r9, cs:140000000h
0x140001cbc  lea     r10, [rsp+218h+var_188]
0x140001cc4  jmp     loc_140001A2A
0x140001cc9  cmp     edi, 103h
0x140001ccf  jnz     def_140001C40; jumptable 0000000140001C40 default case, case 1
0x140001cd5  xor     esi, esi
0x140001cd7  mov     [rsp+218h+var_1C0], rsi
0x140001cdc  jmp     loc_140001A5F
0x140001ce1  cmp     cx, 5
0x140001ce5  jnz     short loc_140001D11
0x140001ce7  mov     r13d, 1
0x140001ced  mov     [rsp+218h+var_1D0], r13d
0x140001cf2  jmp     loc_140001AAA
0x140001cf7  mov     edi, 0C0000022h
0x140001cfc  mov     [rsp+218h+var_1D8], edi
0x140001d00  jmp     loc_140001A4F
0x140001d05  mov     eax, [r14+14h]
0x140001d09  dec     eax
0x140001d0b  mov     [r14+14h], eax
0x140001d0f  jmp     short loc_140001C91
0x140001d11  bt      dx, 0Dh
0x140001d16  jnb     loc_140001AAA
0x140001d1c  mov     edx, 20000000h
0x140001d21  lea     rcx, [rsp+218h+var_1B8]
0x140001d26  call    cs:__imp_AlpcGetMessageAttribute
0x140001d2c  mov     r8, rax
0x140001d2f  xor     edx, edx
0x140001d31  mov     rcx, r15
0x140001d34  call    cs:__imp_NtAlpcCancelMessage
0x140001d3a  lea     rdx, [rsp+218h+var_188]
0x140001d42  mov     rsi, rdx
0x140001d45  mov     [rsp+218h+var_1C0], rdx
0x140001d4a  jmp     loc_140001AAA
0x140001d4f  mov     [rsp+218h+var_15C], 0C0000002h
0x140001d5a  jmp     loc_140001AAA
0x140001d5f  mov     [rsp+218h+var_15C], 0C000009Ah
0x140001d6a  jmp     loc_140001AAA
0x140001d6f  mov     rdx, rbx
0x140001d72  mov     rcx, r10
0x140001d75  call    SmpEstablishClientSecurity
0x140001d7a  mov     edi, eax
0x140001d7c  mov     [rsp+218h+var_1D8], eax
0x140001d80  mov     edx, [rsp+218h+var_160]
0x140001d87  lea     r9, cs:140000000h
0x140001d8e  lea     r10, [rsp+218h+var_188]
0x140001d96  jmp     loc_140001A47
0x140001d9b  or      dword ptr [rbx], 1
  ... truncated ...
```

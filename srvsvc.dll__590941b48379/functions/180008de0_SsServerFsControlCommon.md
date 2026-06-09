# SsServerFsControlCommon

- ea: `0x180008de0`
- end: `0x18000945e`
- name: `SsServerFsControlCommon`
- size: `1662`
- prototype: `__int64 __fastcall(HANDLE FileHandle, ULONG FsControlCode, unsigned __int16 *hMem, PVOID OutputBuffer, ULONG OutputBufferLength)`
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007480`
- `0x180007750`
- `0x180007be0`
- `0x180007fa0`
- `0x180008470`
- `0x180008930`
- `0x180008ca0`
- `0x180009470`
- `0x180009a20`
- `0x180021d50`
- `0x180028fc0`
- `0x18002e5f0`
- `0x18002e660`
- `0x18002e6d4`
- `0x18002e7f4`
- `0x18002f0fc`
- `0x18003bab4`

## callees

- `0x180008de0`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000900d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000900d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008fa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008fa1`
- `ntdll!NtCreateEvent` at `0x180008e87`
- `ntdll!NtCreateEvent` at `0x180008e87`
- `ntdll!RtlNtStatusToDosError` at `0x180009158`
- `ntdll!RtlNtStatusToDosError` at `0x180009158`
- `ntdll!NtWaitForSingleObject` at `0x180008fb9`
- `ntdll!NtWaitForSingleObject` at `0x180008fb9`
- `ntdll!NtFsControlFile` at `0x180008ecd`
- `ntdll!NtFsControlFile` at `0x180008ecd`
- `ntdll!NtClose` at `0x180008ee8`
- `ntdll!NtClose` at `0x180008ee8`

## pseudocode

```c
__int64 __fastcall SsServerFsControlCommon(
        HANDLE FileHandle,
        ULONG FsControlCode,
        unsigned __int16 *hMem,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  __int128 v9; // rax
  __int64 v10; // rcx
  unsigned __int16 *InputBuffer; // rdi
  ULONG InputBufferLength; // r15d
  int Status; // ebx
  ULONG v14; // ebp
  unsigned __int16 *v16; // rax
  void *v17; // rcx
  char *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // [rsp+50h] [rbp-58h]
  __int64 v23; // [rsp+58h] [rbp-50h]
  __int64 v24; // [rsp+60h] [rbp-48h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-40h] BYREF
  void *EventHandle; // [rsp+B0h] [rbp+8h] BYREF

  IoStatusBlock = 0;
  if ( !FileHandle )
    return 58;
  if ( hMem )
  {
    *((_QWORD *)&v9 + 1) = *((_QWORD *)hMem + 1);
    *(_QWORD *)&v9 = *((_QWORD *)hMem + 3);
    v10 = *((_QWORD *)hMem + 5);
    v22 = *((_QWORD *)&v9 + 1);
    v23 = v9;
    v24 = v10;
    if ( v9 != 0 || v10 )
    {
      InputBufferLength = 96;
      if ( *((_QWORD *)&v9 + 1) )
        InputBufferLength = hMem[1] + 96;
      if ( (_QWORD)v9 )
        InputBufferLength += hMem[9];
      if ( v10 )
        InputBufferLength += hMem[17];
      v16 = (unsigned __int16 *)LocalAlloc(0, InputBufferLength);
      InputBuffer = v16;
      if ( !v16 )
        return 8;
      v17 = v16 + 48;
      *(_OWORD *)v16 = *(_OWORD *)hMem;
      *((_OWORD *)v16 + 1) = *((_OWORD *)hMem + 1);
      *((_OWORD *)v16 + 2) = *((_OWORD *)hMem + 2);
      *((_OWORD *)v16 + 3) = *((_OWORD *)hMem + 3);
      *((_OWORD *)v16 + 4) = *((_OWORD *)hMem + 4);
      *((_OWORD *)v16 + 5) = *((_OWORD *)hMem + 5);
      if ( *((_QWORD *)hMem + 1) )
      {
        *v16 = *hMem;
        v16[1] = hMem[1];
        *((_QWORD *)v16 + 1) = v17;
        memcpy_0(v17, *((const void **)hMem + 1), hMem[1]);
        v18 = (char *)InputBuffer + hMem[1] + 96;
        v19 = *((_QWORD *)InputBuffer + 1) - (_QWORD)InputBuffer;
        if ( !*((_QWORD *)InputBuffer + 1) )
          v19 = 0;
        *((_QWORD *)InputBuffer + 1) = v19;
      }
      else
      {
        v18 = (char *)(v16 + 48);
      }
      if ( *((_QWORD *)hMem + 3) )
      {
        InputBuffer[8] = hMem[8];
        InputBuffer[9] = hMem[9];
        *((_QWORD *)InputBuffer + 3) = v18;
        memcpy_0(v18, *((const void **)hMem + 3), hMem[9]);
        v18 += hMem[9];
        v21 = *((_QWORD *)InputBuffer + 3) - (_QWORD)InputBuffer;
        if ( !*((_QWORD *)InputBuffer + 3) )
          v21 = 0;
        *((_QWORD *)InputBuffer + 3) = v21;
      }
      if ( *((_QWORD *)hMem + 5) )
      {
        InputBuffer[16] = hMem[16];
        InputBuffer[17] = hMem[17];
        *((_QWORD *)InputBuffer + 5) = v18;
        memcpy_0(v18, *((const void **)hMem + 5), hMem[17]);
        v20 = *((_QWORD *)InputBuffer + 5) - (_QWORD)InputBuffer;
        if ( !*((_QWORD *)InputBuffer + 5) )
          v20 = 0;
        *((_QWORD *)InputBuffer + 5) = v20;
      }
    }
    else
    {
      InputBuffer = hMem;
      InputBufferLength = 96;
    }
  }
  else
  {
    v22 = 0;
    InputBuffer = 0;
    v23 = 0;
    InputBufferLength = 0;
    v24 = 0;
  }
  EventHandle = 0;
  Status = NtCreateEvent(&EventHandle, 0x1F01FFu, 0, NotificationEvent, 0);
  if ( Status >= 0 )
  {
    Status = NtFsControlFile(
               FileHandle,
               EventHandle,
               0,
               0,
               &IoStatusBlock,
               FsControlCode,
               InputBuffer,
               InputBufferLength,
               OutputBuffer,
               OutputBufferLength);
    if ( Status == 259 )
      NtWaitForSingleObject(EventHandle, 0, 0);
    NtClose(EventHandle);
  }
  if ( !InputBuffer || (v14 = *((_DWORD *)InputBuffer + 17)) == 0 )
  {
    if ( Status >= 0 )
      Status = IoStatusBlock.Status;
    if ( Status == -2147483612 )
    {
      v14 = 1811;
      goto LABEL_18;
    }
    if ( !Status || Status == -2147483611 )
    {
      v14 = 0;
      goto LABEL_18;
    }
    if ( Status <= -1073741531 )
    {
      if ( Status != -1073741531 )
      {
        switch ( Status )
        {
          case -1073741789:
            v14 = 2123;
            break;
          case -1073741727:
            v14 = 5;
            break;
          case -1073741726:
            v14 = 2202;
            break;
          case -1073741725:
            v14 = 2224;
            break;
          case -1073741724:
            v14 = 2221;
            break;
          case -1073741723:
            v14 = 2223;
            break;
          case -1073741722:
          case -1073741709:
            v14 = 2220;
            break;
          case -1073741721:
            v14 = 2236;
            break;
          case -1073741720:
            v14 = 2237;
            break;
          case -1073741716:
            v14 = 2245;
            break;
          case -1073741713:
            v14 = 2241;
            break;
          case -1073741712:
            v14 = 2240;
            break;
          case -1073741711:
            v14 = 2242;
            break;
          case -1073741604:
          case -1073741602:
            goto LABEL_83;
          case -1073741603:
            v14 = 2227;
            break;
          case -1073741596:
            v14 = 2247;
            break;
          case -1073741573:
            v14 = 2102;
            break;
          case -1073741561:
            v14 = 2401;
            break;
          case -1073741560:
            v14 = 2404;
            break;
          default:
            goto LABEL_45;
        }
        goto LABEL_18;
      }
LABEL_79:
      v14 = 2234;
      goto LABEL_18;
    }
    if ( Status <= -1073741495 )
    {
      switch ( Status )
      {
        case -1073741495:
          v14 = 2403;
          goto LABEL_18;
        case -1073741529:
          goto LABEL_79;
        case -1073741518:
          v14 = 2210;
          goto LABEL_18;
        case -1073741517:
          v14 = 2457;
          goto LABEL_18;
        case -1073741516:
          v14 = 2249;
          goto LABEL_18;
      }
    }
    else
    {
      switch ( Status )
      {
        case -1073741433:
LABEL_83:
          v14 = 2226;
          goto LABEL_18;
        case -1073741421:
          v14 = 2239;
          goto LABEL_18;
        case -1073741261:
          v14 = 2453;
          goto LABEL_18;
      }
    }
LABEL_45:
    v14 = RtlNtStatusToDosError(Status);
    if ( v14 == Status )
      v14 = 2140;
  }
LABEL_18:
  if ( InputBuffer != hMem )
  {
    *(_OWORD *)hMem = *(_OWORD *)InputBuffer;
    *((_OWORD *)hMem + 1) = *((_OWORD *)InputBuffer + 1);
    *((_OWORD *)hMem + 2) = *((_OWORD *)InputBuffer + 2);
    *((_OWORD *)hMem + 3) = *((_OWORD *)InputBuffer + 3);
    *((_OWORD *)hMem + 4) = *((_OWORD *)InputBuffer + 4);
    *((_OWORD *)hMem + 5) = *((_OWORD *)InputBuffer + 5);
    *((_QWORD *)hMem + 1) = v22;
    *((_QWORD *)hMem + 3) = v23;
    *((_QWORD *)hMem + 5) = v24;
    LocalFree(InputBuffer);
  }
  return v14;
}

```

## disassembly

```asm
0x180008de0  mov     rax, rsp
0x180008de3  push    rbp
0x180008de4  push    rsi
0x180008de5  push    r12
0x180008de7  push    r13
0x180008de9  sub     rsp, 88h
0x180008df0  xorps   xmm0, xmm0
0x180008df3  mov     r12, r9
0x180008df6  mov     rsi, r8
0x180008df9  mov     r13d, edx
0x180008dfc  mov     rbp, rcx
0x180008dff  movups  xmmword ptr [rax-40h], xmm0
0x180008e03  test    rcx, rcx
0x180008e06  jz      loc_18000930E
0x180008e0c  mov     [rax+10h], rbx
0x180008e10  mov     [rax+18h], rdi
0x180008e14  mov     [rax+20h], r14
0x180008e18  xor     r14d, r14d
0x180008e1b  mov     [rax-28h], r15
0x180008e1f  test    r8, r8
0x180008e22  jz      loc_180008FC4
0x180008e28  mov     rdx, [r8+8]
0x180008e2c  mov     rax, [r8+18h]
0x180008e30  mov     rcx, [r8+28h]
0x180008e34  mov     [rsp+0A8h+var_58], rdx
0x180008e39  mov     [rsp+0A8h+var_50], rax
0x180008e3e  mov     [rsp+0A8h+var_48], rcx
0x180008e43  test    rdx, rdx
0x180008e46  jnz     loc_180008FDE
0x180008e4c  test    rax, rax
0x180008e4f  jnz     loc_180008FDE
0x180008e55  test    rcx, rcx
0x180008e58  jnz     loc_180008FDE
0x180008e5e  mov     rdi, r8
0x180008e61  mov     r15d, 60h ; '`'
0x180008e67  xor     r9d, r9d; EventType
0x180008e6a  mov     [rsp+0A8h+EventHandle], r14
0x180008e72  xor     r8d, r8d; ObjectAttributes
0x180008e75  mov     [rsp+0A8h+InitialState], 0; InitialState
0x180008e7a  mov     edx, 1F01FFh; DesiredAccess
0x180008e7f  lea     rcx, [rsp+0A8h+EventHandle]; EventHandle
0x180008e87  call    cs:__imp_NtCreateEvent
0x180008e8d  mov     ebx, eax
0x180008e8f  test    eax, eax
0x180008e91  js      short loc_180008EEE
0x180008e93  mov     eax, [rsp+0A8h+arg_20]
0x180008e9a  xor     r9d, r9d; ApcContext
0x180008e9d  mov     rdx, [rsp+0A8h+EventHandle]; Event
0x180008ea5  xor     r8d, r8d; ApcRoutine
0x180008ea8  mov     [rsp+0A8h+OutputBufferLength], eax; OutputBufferLength
0x180008eac  mov     rcx, rbp; FileHandle
0x180008eaf  mov     [rsp+0A8h+OutputBuffer], r12; OutputBuffer
0x180008eb4  lea     rax, [rsp+0A8h+IoStatusBlock]
0x180008eb9  mov     [rsp+0A8h+InputBufferLength], r15d; InputBufferLength
0x180008ebe  mov     [rsp+0A8h+InputBuffer], rdi; InputBuffer
0x180008ec3  mov     [rsp+0A8h+FsControlCode], r13d; FsControlCode
0x180008ec8  mov     qword ptr [rsp+0A8h+InitialState], rax; IoStatusBlock
0x180008ecd  call    cs:__imp_NtFsControlFile
0x180008ed3  mov     ebx, eax
0x180008ed5  cmp     eax, 103h
0x180008eda  jz      loc_180008FAC
0x180008ee0  mov     rcx, [rsp+0A8h+EventHandle]; Handle
0x180008ee8  call    cs:__imp_NtClose
0x180008eee  test    rdi, rdi
0x180008ef1  jz      short loc_180008EFA
0x180008ef3  mov     ebp, [rdi+44h]
0x180008ef6  test    ebp, ebp
0x180008ef8  jnz     short loc_180008F20
0x180008efa  test    ebx, ebx
0x180008efc  cmovns  ebx, dword ptr [rsp+0A8h+IoStatusBlock]
0x180008f01  cmp     ebx, 80000024h
0x180008f07  jz      loc_1800091D4
0x180008f0d  test    ebx, ebx
0x180008f0f  jz      short loc_180008F1D
0x180008f11  cmp     ebx, 80000025h
0x180008f17  jnz     loc_1800090EE
0x180008f1d  mov     ebp, r14d
0x180008f20  cmp     rdi, rsi
0x180008f23  jnz     short loc_180008F55
0x180008f25  mov     eax, ebp
0x180008f27  mov     r14, [rsp+0A8h+arg_18]
0x180008f2f  mov     rdi, [rsp+0A8h+arg_10]
0x180008f37  mov     rbx, [rsp+0A8h+arg_8]
0x180008f3f  mov     r15, [rsp+0A8h+var_28]
0x180008f47  add     rsp, 88h
0x180008f4e  pop     r13
0x180008f50  pop     r12
0x180008f52  pop     rsi
0x180008f53  pop     rbp
0x180008f54  retn
0x180008f55  movups  xmm0, xmmword ptr [rdi]
0x180008f58  mov     rax, [rsp+0A8h+var_58]
0x180008f5d  mov     rcx, rdi; hMem
0x180008f60  movups  xmmword ptr [rsi], xmm0
0x180008f63  movups  xmm1, xmmword ptr [rdi+10h]
0x180008f67  movups  xmmword ptr [rsi+10h], xmm1
0x180008f6b  movups  xmm0, xmmword ptr [rdi+20h]
0x180008f6f  movups  xmmword ptr [rsi+20h], xmm0
0x180008f73  movups  xmm1, xmmword ptr [rdi+30h]
0x180008f77  movups  xmmword ptr [rsi+30h], xmm1
0x180008f7b  movups  xmm0, xmmword ptr [rdi+40h]
0x180008f7f  movups  xmmword ptr [rsi+40h], xmm0
0x180008f83  movups  xmm1, xmmword ptr [rdi+50h]
0x180008f87  movups  xmmword ptr [rsi+50h], xmm1
0x180008f8b  mov     [rsi+8], rax
0x180008f8f  mov     rax, [rsp+0A8h+var_50]
0x180008f94  mov     [rsi+18h], rax
0x180008f98  mov     rax, [rsp+0A8h+var_48]
0x180008f9d  mov     [rsi+28h], rax
0x180008fa1  call    cs:__imp_LocalFree
0x180008fa7  jmp     loc_180008F25
0x180008fac  mov     rcx, [rsp+0A8h+EventHandle]; Handle
0x180008fb4  xor     r8d, r8d; Timeout
0x180008fb7  xor     edx, edx; Alertable
0x180008fb9  call    cs:__imp_NtWaitForSingleObject
0x180008fbf  jmp     loc_180008EE0
0x180008fc4  mov     [rsp+0A8h+var_58], r14
0x180008fc9  mov     rdi, r14
0x180008fcc  mov     [rsp+0A8h+var_50], r14
0x180008fd1  mov     r15d, r14d
0x180008fd4  mov     [rsp+0A8h+var_48], r14
0x180008fd9  jmp     loc_180008E67
0x180008fde  mov     r15d, 60h ; '`'
0x180008fe4  test    rdx, rdx
0x180008fe7  jz      short loc_180008FF2
0x180008fe9  movzx   r15d, word ptr [r8+2]
0x180008fee  add     r15d, 60h ; '`'
0x180008ff2  test    rax, rax
0x180008ff5  jz      short loc_180008FFF
0x180008ff7  movzx   eax, word ptr [r8+12h]
0x180008ffc  add     r15d, eax
0x180008fff  test    rcx, rcx
0x180009002  jnz     loc_180009318
0x180009008  mov     edx, r15d; uBytes
0x18000900b  xor     ecx, ecx; uFlags
0x18000900d  call    cs:__imp_LocalAlloc
0x180009013  mov     rdi, rax
0x180009016  test    rax, rax
0x180009019  jz      loc_1800091B8
0x18000901f  movups  xmm0, xmmword ptr [rsi]
0x180009022  lea     rcx, [rax+60h]; void *
0x180009026  movups  xmmword ptr [rax], xmm0
0x180009029  movups  xmm1, xmmword ptr [rsi+10h]
0x18000902d  movups  xmmword ptr [rax+10h], xmm1
0x180009031  movups  xmm0, xmmword ptr [rsi+20h]
0x180009035  movups  xmmword ptr [rax+20h], xmm0
0x180009039  movups  xmm1, xmmword ptr [rsi+30h]
0x18000903d  movups  xmmword ptr [rax+30h], xmm1
0x180009041  movups  xmm0, xmmword ptr [rsi+40h]
0x180009045  movups  xmmword ptr [rax+40h], xmm0
0x180009049  movups  xmm1, xmmword ptr [rsi+50h]
0x18000904d  movups  xmmword ptr [rax+50h], xmm1
0x180009051  cmp     [rsi+8], r14
0x180009055  jz      loc_1800091C2
0x18000905b  movzx   eax, word ptr [rsi]
0x18000905e  mov     [rdi], ax
0x180009061  movzx   eax, word ptr [rsi+2]
0x180009065  mov     [rdi+2], ax
0x180009069  mov     [rdi+8], rcx
0x18000906d  movzx   r8d, word ptr [rsi+2]; Size
0x180009072  mov     rdx, [rsi+8]; Src
0x180009076  call    memcpy_0
0x18000907b  movzx   ebx, word ptr [rsi+2]
0x18000907f  lea     rax, [rdi+60h]
0x180009083  add     rbx, rax
0x180009086  mov     rax, [rdi+8]
0x18000908a  mov     rcx, rax
0x18000908d  sub     rcx, rdi
0x180009090  test    rax, rax
0x180009093  cmovz   rcx, r14
0x180009097  mov     [rdi+8], rcx
0x18000909b  cmp     [rsi+18h], r14
0x18000909f  jnz     loc_180009172
0x1800090a5  cmp     [rsi+28h], r14
0x1800090a9  jz      loc_180008E67
0x1800090af  movzx   eax, word ptr [rsi+20h]
0x1800090b3  mov     rcx, rbx; void *
0x1800090b6  mov     [rdi+20h], ax
0x1800090ba  movzx   eax, word ptr [rsi+22h]
0x1800090be  mov     [rdi+22h], ax
0x1800090c2  mov     [rdi+28h], rbx
0x1800090c6  movzx   r8d, word ptr [rsi+22h]; Size
0x1800090cb  mov     rdx, [rsi+28h]; Src
0x1800090cf  call    memcpy_0
0x1800090d4  mov     rax, [rdi+28h]
0x1800090d8  mov     rcx, rax
0x1800090db  sub     rcx, rdi
0x1800090de  test    rax, rax
0x1800090e1  cmovz   rcx, r14
0x1800090e5  mov     [rdi+28h], rcx
0x1800090e9  jmp     loc_180008E67
0x1800090ee  cmp     ebx, 0C0000125h
0x1800090f4  jg      short loc_180009126
0x1800090f6  jz      loc_1800092DC
0x1800090fc  lea     eax, [rbx+3FFFFFDDh]; switch 230 cases
0x180009102  cmp     eax, 0E5h
0x180009107  ja      short def_180009124; jumptable 0000000180009124 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180009109  lea     rdx, __ImageBase
0x180009110  cdqe
0x180009112  movzx   eax, ds:(byte_180009378 - 180000000h)[rdx+rax]
0x18000911a  mov     ecx, ds:(jpt_180009124 - 180000000h)[rdx+rax*4]
0x180009121  add     rcx, rdx
0x180009124  jmp     rcx; switch jump
0x180009126  cmp     ebx, 0C0000149h
0x18000912c  jle     loc_1800091DE
0x180009132  cmp     ebx, 0C0000187h
0x180009138  jz      loc_180009304; jumptable 0000000180009124 cases -1073741604,-1073741602
0x18000913e  cmp     ebx, 0C0000193h
0x180009144  jz      loc_1800092FA
0x18000914a  cmp     ebx, 0C0000233h
0x180009150  jz      loc_1800092F0
0x180009156  mov     ecx, ebx; jumptable 0000000180009124 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180009158  call    cs:__imp_RtlNtStatusToDosError
0x18000915e  mov     ebp, eax
0x180009160  cmp     eax, ebx
0x180009162  jnz     loc_180008F20
0x180009168  mov     ebp, 85Ch
0x18000916d  jmp     loc_180008F20
0x180009172  movzx   eax, word ptr [rsi+10h]
0x180009176  mov     rcx, rbx; void *
0x180009179  mov     [rdi+10h], ax
0x18000917d  movzx   eax, word ptr [rsi+12h]
0x180009181  mov     [rdi+12h], ax
0x180009185  mov     [rdi+18h], rbx
0x180009189  movzx   r8d, word ptr [rsi+12h]; Size
0x18000918e  mov     rdx, [rsi+18h]; Src
0x180009192  call    memcpy_0
0x180009197  movzx   eax, word ptr [rsi+12h]
0x18000919b  add     rbx, rax
0x18000919e  mov     rax, [rdi+18h]
0x1800091a2  mov     rdx, rax
0x1800091a5  sub     rdx, rdi
0x1800091a8  test    rax, rax
0x1800091ab  cmovz   rdx, r14
0x1800091af  mov     [rdi+18h], rdx
0x1800091b3  jmp     loc_1800090A5
0x1800091b8  mov     eax, 8
0x1800091bd  jmp     loc_180008F27
0x1800091c2  mov     rbx, rcx
0x1800091c5  jmp     loc_18000909B
0x1800091ca  mov     ebp, 8C5h; jumptable 0000000180009124 case -1073741716
0x1800091cf  jmp     loc_180008F20
0x1800091d4  mov     ebp, 713h
0x1800091d9  jmp     loc_180008F20
0x1800091de  jz      loc_1800092E6
0x1800091e4  cmp     ebx, 0C0000127h
0x1800091ea  jz      loc_1800092DC
0x1800091f0  cmp     ebx, 0C0000132h
0x1800091f6  jz      loc_1800092D2
0x1800091fc  cmp     ebx, 0C0000133h
0x180009202  jz      loc_1800092C8
0x180009208  cmp     ebx, 0C0000134h
0x18000920e  jnz     def_180009124; jumptable 0000000180009124 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180009214  mov     ebp, 8C9h
0x180009219  jmp     loc_180008F20
0x18000921e  mov     ebp, 84Bh; jumptable 0000000180009124 case -1073741789
0x180009223  jmp     loc_180008F20
0x180009228  mov     ebp, 961h; jumptable 0000000180009124 case -1073741561
0x18000922d  jmp     loc_180008F20
0x180009232  mov     ebp, 964h; jumptable 0000000180009124 case -1073741560
0x180009237  jmp     loc_180008F20
0x18000923c  mov     ebp, 8C1h; jumptable 0000000180009124 case -1073741713
0x180009241  jmp     loc_180008F20
0x180009246  mov     ebp, 8C0h; jumptable 0000000180009124 case -1073741712
0x18000924b  jmp     loc_180008F20
0x180009250  mov     ebp, 8C2h; jumptable 0000000180009124 case -1073741711
0x180009255  jmp     loc_180008F20
0x18000925a  mov     ebp, 836h; jumptable 0000000180009124 case -1073741573
0x18000925f  jmp     loc_180008F20
0x180009264  mov     ebp, 8AFh; jumptable 0000000180009124 case -1073741723
0x180009269  jmp     loc_180008F20
0x18000926e  mov     ebp, 8C7h; jumptable 0000000180009124 case -1073741596
0x180009273  jmp     loc_180008F20
0x180009278  mov     ebp, 89Ah; jumptable 0000000180009124 case -1073741726
0x18000927d  jmp     loc_180008F20
0x180009282  mov     ebp, 8B3h; jumptable 0000000180009124 case -1073741603
0x180009287  jmp     loc_180008F20
0x18000928c  mov     ebp, 8BCh; jumptable 0000000180009124 case -1073741721
0x180009291  jmp     loc_180008F20
0x180009296  mov     ebp, 8BDh; jumptable 0000000180009124 case -1073741720
0x18000929b  jmp     loc_180008F20
0x1800092a0  mov     ebp, 8ACh; jumptable 0000000180009124 cases -1073741722,-1073741709
0x1800092a5  jmp     loc_180008F20
0x1800092aa  mov     ebp, 8B0h; jumptable 0000000180009124 case -1073741725
0x1800092af  jmp     loc_180008F20
0x1800092b4  mov     ebp, 8ADh; jumptable 0000000180009124 case -1073741724
0x1800092b9  jmp     loc_180008F20
0x1800092be  mov     ebp, 5; jumptable 0000000180009124 case -1073741727
0x1800092c3  jmp     loc_180008F20
0x1800092c8  mov     ebp, 999h
0x1800092cd  jmp     loc_180008F20
0x1800092d2  mov     ebp, 8A2h
0x1800092d7  jmp     loc_180008F20
0x1800092dc  mov     ebp, 8BAh
0x1800092e1  jmp     loc_180008F20
0x1800092e6  mov     ebp, 963h
0x1800092eb  jmp     loc_180008F20
0x1800092f0  mov     ebp, 995h
0x1800092f5  jmp     loc_180008F20
0x1800092fa  mov     ebp, 8BFh
  ... truncated ...
```

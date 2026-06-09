# WcPortMessage

- ea: `0x140031e90`
- end: `0x140032547`
- name: `WcPortMessage`
- size: `1719`
- prototype: `__int64 __fastcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, char *OutputBuffer, SIZE_T OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x1400020c4`
- `0x140002520`
- `0x140004058`
- `0x1400057a0`
- `0x14001443c`
- `0x14001452c`
- `0x14001a62c`
- `0x14001f488`
- `0x14001fe40`
- `0x140020b60`
- `0x140020e60`
- `0x14002bf4c`
- `0x140031e90`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x140032158`
- `ntoskrnl!MmIsUserAddress` at `0x140032158`
- `ntoskrnl!ProbeForRead` at `0x140031fea`
- `ntoskrnl!ProbeForRead` at `0x140031fea`
- `ntoskrnl!ProbeForWrite` at `0x14003200a`
- `ntoskrnl!ProbeForWrite` at `0x14003200a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003252a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003252a`
- `ntoskrnl!ExAllocatePool2` at `0x140031f66`
- `ntoskrnl!ExAllocatePool2` at `0x140031f66`

## pseudocode

```c
__int64 __fastcall WcPortMessage(
        PVOID PortCookie,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        char *OutputBuffer,
        SIZE_T OutputBufferLength,
        PULONG ReturnOutputBufferLength)
{
  SIZE_T v7; // r14
  unsigned int v9; // edi
  _UNKNOWN **v10; // rdx
  int v11; // r9d
  unsigned int *Pool2; // rbx
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rdx
  unsigned int Unions; // eax
  ULONG v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  char v25; // [rsp+30h] [rbp-68h]
  unsigned int *P; // [rsp+50h] [rbp-48h]
  ULONG v27; // [rsp+B0h] [rbp+18h] BYREF

  v7 = InputBufferLength;
  P = 0;
  v27 = 0;
  if ( InputBufferLength < 0xC )
  {
    v9 = -1073741811;
    v10 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_55;
    v11 = 70;
    v25 = 25;
    goto LABEL_4;
  }
  if ( (unsigned int)OutputBufferLength >= 0xC )
  {
    Pool2 = (unsigned int *)ExAllocatePool2(256, InputBufferLength, 1953317719);
    P = Pool2;
    if ( !Pool2 )
    {
      v9 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sDDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          (unsigned int)&WPP_RECORDER_INITIALIZED,
          14,
          72,
          (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
          39,
          v7,
          154);
      goto LABEL_55;
    }
    ProbeForRead(InputBuffer, v7, 1u);
    ProbeForWrite(OutputBuffer, (unsigned int)OutputBufferLength, 1u);
    RtlCopyFromUser(Pool2, InputBuffer, v7);
    v13 = Pool2[1];
    if ( (_DWORD)v13 == (_DWORD)v7 )
    {
      v9 = 0;
      v14 = *Pool2;
      if ( *Pool2 )
      {
        if ( v14 == 2 )
        {
          if ( (unsigned int)v13 < 0xAC )
          {
            v9 = -1073741811;
            v10 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v11 = 76;
              v25 = 118;
              goto LABEL_4;
            }
            goto LABEL_55;
          }
          if ( v13 != Pool2[3] + 8LL )
          {
            v9 = -1073741811;
            v10 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v11 = 79;
              v25 = -116;
              goto LABEL_4;
            }
            goto LABEL_55;
          }
          RtlWriteULongToUser(OutputBuffer, 3);
          RtlWriteULongToUser(OutputBuffer + 4, 12);
          v22 = WcCopyAsPlaceHolderHandler(Pool2 + 2, Pool2[1] - 8);
          RtlWriteULongToUser(OutputBuffer + 8, v22);
        }
        else if ( v14 == 4 )
        {
          if ( (unsigned int)v13 < 0x9A )
          {
            v9 = -1073741811;
            v10 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v11 = 80;
              v25 = -81;
              goto LABEL_4;
            }
            goto LABEL_55;
          }
          if ( v13 != Pool2[3] + 8LL )
          {
            v9 = -1073741811;
            v10 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v11 = 83;
              v25 = -59;
              goto LABEL_4;
            }
            goto LABEL_55;
          }
          RtlWriteULongToUser(OutputBuffer, 5);
          RtlWriteULongToUser(OutputBuffer + 4, 12);
          v21 = WcCopyFileHandler(Pool2 + 2, Pool2[1] - 8);
          RtlWriteULongToUser(OutputBuffer + 8, v21);
        }
        else if ( v14 == 6 )
        {
          if ( (unsigned int)v13 < 0x7C )
          {
            v9 = -1073741811;
            v10 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v11 = 84;
              v25 = -24;
              goto LABEL_4;
            }
            goto LABEL_55;
          }
          if ( v13 != Pool2[3] + 8LL )
          {
            v9 = -1073741811;
            v10 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v11 = 87;
              v25 = -2;
              goto LABEL_4;
            }
            goto LABEL_55;
          }
          RtlWriteULongToUser(OutputBuffer, 7);
          RtlWriteULongToUser(OutputBuffer + 4, 12);
          v20 = WcSetupVolumeInformationHandler(Pool2 + 2, Pool2[1] - 8);
          RtlWriteULongToUser(OutputBuffer + 8, v20);
        }
        else if ( v14 == 8 )
        {
          RtlWriteULongToUser(OutputBuffer, 9);
          RtlWriteULongToUser(OutputBuffer + 4, 12);
          v19 = WcRemoveUnionContext(Pool2 + 2, Pool2[1] - 8);
          RtlWriteULongToUser(OutputBuffer + 8, v19);
        }
        else
        {
          if ( v14 != 10 )
          {
            if ( v14 == 12 )
            {
              if ( (unsigned int)v13 >= 0x18 )
              {
                if ( (unsigned int)OutputBufferLength >= 0x1C )
                {
                  RtlSetUserMemory(OutputBuffer);
                  LOBYTE(v15) = (unsigned __int8)MmIsUserAddress(Pool2 + 2) != 0;
                  Unions = WcProcessGetUnions(Pool2 + 2, v15, (unsigned int)OutputBufferLength, OutputBuffer, &v27);
                  RtlWriteULongToUser(OutputBuffer + 4, Unions);
                  v17 = v27;
                  RtlWriteULongToUser(OutputBuffer, v27);
                  *ReturnOutputBufferLength = v17;
                }
                else
                {
                  v9 = -1073741811;
                  v10 = &WPP_RECORDER_INITIALIZED;
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    v11 = 93;
                    v25 = 125;
                    goto LABEL_4;
                  }
                }
              }
              else
              {
                v9 = -1073741811;
                v10 = &WPP_RECORDER_INITIALIZED;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  v11 = 92;
                  v25 = 117;
                  goto LABEL_4;
                }
              }
            }
            else
            {
              v9 = -1073741811;
              v10 = &WPP_RECORDER_INITIALIZED;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v11 = 95;
                v25 = -94;
                goto LABEL_4;
              }
            }
            goto LABEL_55;
          }
          RtlWriteULongToUser(OutputBuffer, 11);
          RtlWriteULongToUser(OutputBuffer + 4, 12);
          v18 = WcSetUnion(Pool2 + 2, Pool2[1] - 8);
          RtlWriteULongToUser(OutputBuffer + 8, v18);
        }
      }
      else
      {
        RtlWriteULongToUser(OutputBuffer, 1);
        RtlWriteULongToUser(OutputBuffer + 4, 12);
        v23 = WcSetUnionContext(Pool2 + 2, Pool2[1] - 8, 268369920);
        RtlWriteULongToUser(OutputBuffer + 8, v23);
      }
      *ReturnOutputBufferLength = 12;
      goto LABEL_55;
    }
    v9 = -1073741811;
    v10 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = 73;
      v25 = 65;
      goto LABEL_4;
    }
  }
  else
  {
    v9 = -1073741811;
    v10 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = 71;
      v25 = 31;
LABEL_4:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        (_DWORD)v10,
        14,
        v11,
        (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
        v25,
        13);
    }
  }
LABEL_55:
  if ( P )
    ExFreePoolWithTag(P, 0x746D4357u);
  return v9;
}

```

## disassembly

```asm
0x140031e90  mov     rax, rsp
0x140031e93  push    rbx
0x140031e94  push    rsi
0x140031e95  push    rdi
0x140031e96  push    r12
0x140031e98  push    r13
0x140031e9a  push    r14
0x140031e9c  sub     rsp, 68h
0x140031ea0  mov     rsi, r9
0x140031ea3  mov     r14d, r8d
0x140031ea6  mov     r12, rdx
0x140031ea9  mov     [rsp+98h+P], 0
0x140031eb2  mov     dword ptr [rax+18h], 0
0x140031eb9  cmp     r8d, 0Ch
0x140031ebd  jnb     short loc_140031F1F
0x140031ebf  mov     ecx, 0C000000Dh
0x140031ec4  mov     edi, ecx
0x140031ec6  lea     rdx, WPP_RECORDER_INITIALIZED
0x140031ecd  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140031ed4  jz      loc_14003251B
0x140031eda  mov     r9d, 46h ; 'F'
0x140031ee0  mov     [rax-60h], ecx
0x140031ee3  mov     dword ptr [rax-68h], 519h
0x140031eea  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x140031ef1  mov     [rsp+98h+var_70], rax
0x140031ef6  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x140031efd  mov     [rsp+98h+var_78], rax
0x140031f02  mov     r8d, 0Eh
0x140031f08  mov     dl, 2
0x140031f0a  mov     rcx, cs:wil_details_featureDescriptors_a
0x140031f11  mov     rcx, [rcx+40h]
0x140031f15  call    WPP_RECORDER_SF_sDd
0x140031f1a  jmp     loc_14003251B
0x140031f1f  cmp     dword ptr [rsp+98h+Length], 0Ch
0x140031f27  jnb     short loc_140031F58
0x140031f29  mov     ecx, 0C000000Dh
0x140031f2e  mov     edi, ecx
0x140031f30  lea     rdx, WPP_RECORDER_INITIALIZED
0x140031f37  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140031f3e  jz      loc_14003251B
0x140031f44  mov     r9d, 47h ; 'G'
0x140031f4a  mov     [rsp+98h+var_60], ecx
0x140031f4e  mov     dword ptr [rsp+98h+var_68], 51Fh
0x140031f56  jmp     short loc_140031EEA
0x140031f58  mov     r8d, 746D4357h
0x140031f5e  mov     rdx, r14
0x140031f61  mov     ecx, 100h
0x140031f66  call    cs:__imp_ExAllocatePool2
0x140031f6d  nop     dword ptr [rax+rax+00h]
0x140031f72  mov     rbx, rax
0x140031f75  mov     [rsp+98h+P], rax
0x140031f7a  test    rax, rax
0x140031f7d  jnz     short loc_140031FDE
0x140031f7f  mov     edi, 0C000009Ah
0x140031f84  lea     rdx, WPP_RECORDER_INITIALIZED
0x140031f8b  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140031f92  jz      loc_14003251B
0x140031f98  lea     r9d, [rax+48h]
0x140031f9c  mov     [rsp+98h+var_58], edi
0x140031fa0  mov     [rsp+98h+var_60], r14d
0x140031fa5  mov     dword ptr [rsp+98h+var_68], 527h
0x140031fad  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x140031fb4  mov     [rsp+98h+var_70], rax
0x140031fb9  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x140031fc0  mov     [rsp+98h+var_78], rax
0x140031fc5  lea     r8d, [rbx+0Eh]
0x140031fc9  mov     rcx, cs:wil_details_featureDescriptors_a
0x140031fd0  mov     rcx, [rcx+40h]
0x140031fd4  call    WPP_RECORDER_SF_sDDd
0x140031fd9  jmp     loc_14003251B
0x140031fde  mov     r8d, 1; Alignment
0x140031fe4  mov     rdx, r14; Length
0x140031fe7  mov     rcx, r12; Address
0x140031fea  call    cs:__imp_ProbeForRead
0x140031ff1  nop     dword ptr [rax+rax+00h]
0x140031ff6  mov     r13d, dword ptr [rsp+98h+Length]
0x140031ffe  mov     r8d, 1; Alignment
0x140032004  mov     edx, r13d; Length
0x140032007  mov     rcx, rsi; Address
0x14003200a  call    cs:__imp_ProbeForWrite
0x140032011  nop     dword ptr [rax+rax+00h]
0x140032016  mov     r8, r14; Size
0x140032019  mov     rdx, r12; Src
0x14003201c  mov     rcx, [rsp+98h+P]; void *
0x140032021  call    RtlCopyFromUser
0x140032026  nop
0x140032027  mov     eax, [rbx+4]
0x14003202a  cmp     eax, r14d
0x14003202d  jz      short loc_140032061
0x14003202f  mov     ecx, 0C000000Dh
0x140032034  mov     edi, ecx
0x140032036  lea     rdx, WPP_RECORDER_INITIALIZED
0x14003203d  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140032044  jz      loc_14003251B
0x14003204a  mov     r9d, 49h ; 'I'
0x140032050  mov     [rsp+98h+var_60], ecx
0x140032054  mov     dword ptr [rsp+98h+var_68], 541h
0x14003205c  jmp     loc_140031EEA
0x140032061  xor     edi, edi
0x140032063  mov     ecx, [rbx]
0x140032065  test    ecx, ecx
0x140032067  jz      loc_1400324BA
0x14003206d  cmp     ecx, 2
0x140032070  jz      loc_1400323F9
0x140032076  cmp     ecx, 4
0x140032079  jz      loc_14003232F
0x14003207f  cmp     ecx, 6
0x140032082  jz      loc_140032267
0x140032088  cmp     ecx, 8
0x14003208b  jz      loc_140032214
0x140032091  cmp     ecx, 0Ah
0x140032094  jz      loc_1400321C1
0x14003209a  lea     r12d, [rdi+0Ch]
0x14003209e  cmp     ecx, r12d
0x1400320a1  jz      short loc_1400320D4
0x1400320a3  mov     ecx, 0C000000Dh
0x1400320a8  mov     edi, ecx
0x1400320aa  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400320b1  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400320b8  jz      loc_14003251B
0x1400320be  lea     r9d, [r12+53h]
0x1400320c3  mov     [rsp+98h+var_60], ecx
0x1400320c7  mov     dword ptr [rsp+98h+var_68], 6A2h
0x1400320cf  jmp     loc_140031EEA
0x1400320d4  cmp     eax, 18h
0x1400320d7  jnb     short loc_14003210B
0x1400320d9  mov     ecx, 0C000000Dh
0x1400320de  mov     edi, ecx
0x1400320e0  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400320e7  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400320ee  jz      loc_14003251B
0x1400320f4  mov     r9d, 5Ch ; '\'
0x1400320fa  mov     [rsp+98h+var_60], ecx
0x1400320fe  mov     dword ptr [rsp+98h+var_68], 675h
0x140032106  jmp     loc_140031EEA
0x14003210b  cmp     dword ptr [rsp+98h+Length], 1Ch
0x140032113  jnb     short loc_140032147
0x140032115  mov     ecx, 0C000000Dh
0x14003211a  mov     edi, ecx
0x14003211c  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032123  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003212a  jz      loc_14003251B
0x140032130  mov     r9d, 5Dh ; ']'
0x140032136  mov     [rsp+98h+var_60], ecx
0x14003213a  mov     dword ptr [rsp+98h+var_68], 67Dh
0x140032142  jmp     loc_140031EEA
0x140032147  mov     r8, r13
0x14003214a  xor     edx, edx
0x14003214c  mov     rcx, rsi; void *
0x14003214f  call    RtlSetUserMemory
0x140032154  lea     rcx, [rbx+8]
0x140032158  call    cs:__imp_MmIsUserAddress
0x14003215f  nop     dword ptr [rax+rax+00h]
0x140032164  test    al, al
0x140032166  setnz   dl
0x140032169  lea     rax, [rsp+98h+arg_10]
0x140032171  mov     [rsp+98h+var_78], rax
0x140032176  mov     r9, rsi
0x140032179  mov     r8d, dword ptr [rsp+98h+Length]
0x140032181  lea     rcx, [rbx+8]
0x140032185  call    WcProcessGetUnions
0x14003218a  nop
0x14003218b  lea     rcx, [rsi+4]
0x14003218f  mov     edx, eax
0x140032191  call    RtlWriteULongToUser
0x140032196  mov     ebx, [rsp+98h+arg_10]
0x14003219d  mov     edx, ebx
0x14003219f  mov     rcx, rsi
0x1400321a2  call    RtlWriteULongToUser
0x1400321a7  nop
0x1400321a8  mov     rax, [rsp+98h+ReturnOutputBufferLength]
0x1400321b0  mov     [rax], ebx
0x1400321b2  jmp     loc_14003251B
0x1400321b7  mov     edi, 0C0000005h
0x1400321bc  jmp     loc_14003251B
0x1400321c1  mov     edx, 0Bh
0x1400321c6  mov     rcx, rsi
0x1400321c9  call    RtlWriteULongToUser
0x1400321ce  lea     rcx, [rsi+4]
0x1400321d2  mov     r12d, 0Ch
0x1400321d8  mov     edx, r12d
0x1400321db  call    RtlWriteULongToUser
0x1400321e0  nop
0x1400321e1  mov     edx, [rbx+4]
0x1400321e4  sub     edx, 8
0x1400321e7  lea     rcx, [rbx+8]
0x1400321eb  call    WcSetUnion
0x1400321f0  lea     rcx, [rsi+8]
0x1400321f4  mov     edx, eax
0x1400321f6  call    RtlWriteULongToUser
0x1400321fb  jmp     loc_1400324FB
0x140032200  mov     edi, 0C0000005h
0x140032205  jmp     loc_14003251B
0x14003220a  mov     edi, 0C0000005h
0x14003220f  jmp     loc_14003251B
0x140032214  mov     edx, 9
0x140032219  mov     rcx, rsi
0x14003221c  call    RtlWriteULongToUser
0x140032221  lea     rcx, [rsi+4]
0x140032225  mov     r12d, 0Ch
0x14003222b  mov     edx, r12d
0x14003222e  call    RtlWriteULongToUser
0x140032233  nop
0x140032234  mov     edx, [rbx+4]
0x140032237  sub     edx, 8
0x14003223a  lea     rcx, [rbx+8]
0x14003223e  call    WcRemoveUnionContext
0x140032243  lea     rcx, [rsi+8]
0x140032247  mov     edx, eax
0x140032249  call    RtlWriteULongToUser
0x14003224e  jmp     loc_1400324FB
0x140032253  mov     edi, 0C0000005h
0x140032258  jmp     loc_14003251B
0x14003225d  mov     edi, 0C0000005h
0x140032262  jmp     loc_14003251B
0x140032267  cmp     eax, 7Ch ; '|'
0x14003226a  jnb     short loc_14003229E
0x14003226c  mov     ecx, 0C000000Dh
0x140032271  mov     edi, ecx
0x140032273  lea     rdx, WPP_RECORDER_INITIALIZED
0x14003227a  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140032281  jz      loc_14003251B
0x140032287  mov     r9d, 54h ; 'T'
0x14003228d  mov     [rsp+98h+var_60], ecx
0x140032291  mov     dword ptr [rsp+98h+var_68], 5E8h
0x140032299  jmp     loc_140031EEA
0x14003229e  mov     ecx, [rbx+0Ch]
0x1400322a1  add     rcx, 8
0x1400322a5  cmp     rax, rcx
0x1400322a8  jz      short loc_1400322DC
0x1400322aa  mov     ecx, 0C000000Dh
0x1400322af  mov     edi, ecx
0x1400322b1  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400322b8  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400322bf  jz      loc_14003251B
0x1400322c5  mov     r9d, 57h ; 'W'
0x1400322cb  mov     [rsp+98h+var_60], ecx
0x1400322cf  mov     dword ptr [rsp+98h+var_68], 5FEh
0x1400322d7  jmp     loc_140031EEA
0x1400322dc  mov     edx, 7
0x1400322e1  mov     rcx, rsi
0x1400322e4  call    RtlWriteULongToUser
0x1400322e9  lea     rcx, [rsi+4]
0x1400322ed  mov     r12d, 0Ch
0x1400322f3  mov     edx, r12d
0x1400322f6  call    RtlWriteULongToUser
0x1400322fb  nop
0x1400322fc  mov     edx, [rbx+4]
0x1400322ff  sub     edx, 8
0x140032302  lea     rcx, [rbx+8]
0x140032306  call    WcSetupVolumeInformationHandler
0x14003230b  lea     rcx, [rsi+8]
0x14003230f  mov     edx, eax
0x140032311  call    RtlWriteULongToUser
0x140032316  jmp     loc_1400324FB
0x14003231b  mov     edi, 0C0000005h
0x140032320  jmp     loc_14003251B
0x140032325  mov     edi, 0C0000005h
0x14003232a  jmp     loc_14003251B
0x14003232f  cmp     eax, 9Ah
0x140032334  jnb     short loc_140032368
0x140032336  mov     ecx, 0C000000Dh
0x14003233b  mov     edi, ecx
0x14003233d  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032344  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003234b  jz      loc_14003251B
0x140032351  mov     r9d, 50h ; 'P'
0x140032357  mov     [rsp+98h+var_60], ecx
0x14003235b  mov     dword ptr [rsp+98h+var_68], 5AFh
0x140032363  jmp     loc_140031EEA
0x140032368  mov     ecx, [rbx+0Ch]
0x14003236b  add     rcx, 8
0x14003236f  cmp     rax, rcx
0x140032372  jz      short loc_1400323A6
0x140032374  mov     ecx, 0C000000Dh
0x140032379  mov     edi, ecx
0x14003237b  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032382  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140032389  jz      loc_14003251B
0x14003238f  mov     r9d, 53h ; 'S'
0x140032395  mov     [rsp+98h+var_60], ecx
0x140032399  mov     dword ptr [rsp+98h+var_68], 5C5h
0x1400323a1  jmp     loc_140031EEA
0x1400323a6  mov     edx, 5
0x1400323ab  mov     rcx, rsi
0x1400323ae  call    RtlWriteULongToUser
0x1400323b3  lea     rcx, [rsi+4]
0x1400323b7  mov     r12d, 0Ch
0x1400323bd  mov     edx, r12d
0x1400323c0  call    RtlWriteULongToUser
0x1400323c5  nop
0x1400323c6  mov     edx, [rbx+4]
0x1400323c9  sub     edx, 8
0x1400323cc  lea     rcx, [rbx+8]
0x1400323d0  call    WcCopyFileHandler
0x1400323d5  lea     rcx, [rsi+8]
0x1400323d9  mov     edx, eax
0x1400323db  call    RtlWriteULongToUser
0x1400323e0  jmp     loc_1400324FB
0x1400323e5  mov     edi, 0C0000005h
  ... truncated ...
```

# WcPortMessage

- ea: `0x140031e40`
- end: `0x1400324f7`
- name: `WcPortMessage`
- size: `1719`
- prototype: `NTSTATUS __stdcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
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
- `0x14002befc`
- `0x140031e40`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x140032108`
- `ntoskrnl!MmIsUserAddress` at `0x140032108`
- `ntoskrnl!ProbeForRead` at `0x140031f9a`
- `ntoskrnl!ProbeForRead` at `0x140031f9a`
- `ntoskrnl!ProbeForWrite` at `0x140031fba`
- `ntoskrnl!ProbeForWrite` at `0x140031fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400324da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400324da`
- `ntoskrnl!ExAllocatePool2` at `0x140031f16`
- `ntoskrnl!ExAllocatePool2` at `0x140031f16`

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
          WPP_GLOBAL_Control->DeviceExtension,
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
          v20 = WcSetupVolumeInformationHandler((__int64)(Pool2 + 2), Pool2[1] - 8);
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
        v23 = WcSetUnionContext((__int64)(Pool2 + 2), Pool2[1] - 8, 0xFFF0000u);
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
        WPP_GLOBAL_Control->DeviceExtension,
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
0x140031e40  mov     rax, rsp
0x140031e43  push    rbx
0x140031e44  push    rsi
0x140031e45  push    rdi
0x140031e46  push    r12
0x140031e48  push    r13
0x140031e4a  push    r14
0x140031e4c  sub     rsp, 68h
0x140031e50  mov     rsi, r9
0x140031e53  mov     r14d, r8d
0x140031e56  mov     r12, rdx
0x140031e59  mov     [rsp+98h+P], 0
0x140031e62  mov     dword ptr [rax+18h], 0
0x140031e69  cmp     r8d, 0Ch
0x140031e6d  jnb     short loc_140031ECF
0x140031e6f  mov     ecx, 0C000000Dh
0x140031e74  mov     edi, ecx
0x140031e76  lea     rdx, WPP_RECORDER_INITIALIZED
0x140031e7d  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140031e84  jz      loc_1400324CB
0x140031e8a  mov     r9d, 46h ; 'F'
0x140031e90  mov     [rax-60h], ecx
0x140031e93  mov     dword ptr [rax-68h], 519h
0x140031e9a  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x140031ea1  mov     [rsp+98h+var_70], rax
0x140031ea6  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x140031ead  mov     [rsp+98h+var_78], rax
0x140031eb2  mov     r8d, 0Eh
0x140031eb8  mov     dl, 2
0x140031eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140031ec1  mov     rcx, [rcx+40h]
0x140031ec5  call    WPP_RECORDER_SF_sDd
0x140031eca  jmp     loc_1400324CB
0x140031ecf  cmp     dword ptr [rsp+98h+Length], 0Ch
0x140031ed7  jnb     short loc_140031F08
0x140031ed9  mov     ecx, 0C000000Dh
0x140031ede  mov     edi, ecx
0x140031ee0  lea     rdx, WPP_RECORDER_INITIALIZED
0x140031ee7  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140031eee  jz      loc_1400324CB
0x140031ef4  mov     r9d, 47h ; 'G'
0x140031efa  mov     [rsp+98h+var_60], ecx
0x140031efe  mov     dword ptr [rsp+98h+var_68], 51Fh
0x140031f06  jmp     short loc_140031E9A
0x140031f08  mov     r8d, 746D4357h
0x140031f0e  mov     rdx, r14
0x140031f11  mov     ecx, 100h
0x140031f16  call    cs:__imp_ExAllocatePool2
0x140031f1d  nop     dword ptr [rax+rax+00h]
0x140031f22  mov     rbx, rax
0x140031f25  mov     [rsp+98h+P], rax
0x140031f2a  test    rax, rax
0x140031f2d  jnz     short loc_140031F8E
0x140031f2f  mov     edi, 0C000009Ah
0x140031f34  lea     rdx, WPP_RECORDER_INITIALIZED
0x140031f3b  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140031f42  jz      loc_1400324CB
0x140031f48  lea     r9d, [rax+48h]
0x140031f4c  mov     [rsp+98h+var_58], edi
0x140031f50  mov     [rsp+98h+var_60], r14d
0x140031f55  mov     dword ptr [rsp+98h+var_68], 527h
0x140031f5d  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x140031f64  mov     [rsp+98h+var_70], rax
0x140031f69  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x140031f70  mov     [rsp+98h+var_78], rax
0x140031f75  lea     r8d, [rbx+0Eh]
0x140031f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140031f80  mov     rcx, [rcx+40h]
0x140031f84  call    WPP_RECORDER_SF_sDDd
0x140031f89  jmp     loc_1400324CB
0x140031f8e  mov     r8d, 1; Alignment
0x140031f94  mov     rdx, r14; Length
0x140031f97  mov     rcx, r12; Address
0x140031f9a  call    cs:__imp_ProbeForRead
0x140031fa1  nop     dword ptr [rax+rax+00h]
0x140031fa6  mov     r13d, dword ptr [rsp+98h+Length]
0x140031fae  mov     r8d, 1; Alignment
0x140031fb4  mov     edx, r13d; Length
0x140031fb7  mov     rcx, rsi; Address
0x140031fba  call    cs:__imp_ProbeForWrite
0x140031fc1  nop     dword ptr [rax+rax+00h]
0x140031fc6  mov     r8, r14; Size
0x140031fc9  mov     rdx, r12; Src
0x140031fcc  mov     rcx, [rsp+98h+P]; void *
0x140031fd1  call    RtlCopyFromUser
0x140031fd6  nop
0x140031fd7  mov     eax, [rbx+4]
0x140031fda  cmp     eax, r14d
0x140031fdd  jz      short loc_140032011
0x140031fdf  mov     ecx, 0C000000Dh
0x140031fe4  mov     edi, ecx
0x140031fe6  lea     rdx, WPP_RECORDER_INITIALIZED
0x140031fed  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140031ff4  jz      loc_1400324CB
0x140031ffa  mov     r9d, 49h ; 'I'
0x140032000  mov     [rsp+98h+var_60], ecx
0x140032004  mov     dword ptr [rsp+98h+var_68], 541h
0x14003200c  jmp     loc_140031E9A
0x140032011  xor     edi, edi
0x140032013  mov     ecx, [rbx]
0x140032015  test    ecx, ecx
0x140032017  jz      loc_14003246A
0x14003201d  cmp     ecx, 2
0x140032020  jz      loc_1400323A9
0x140032026  cmp     ecx, 4
0x140032029  jz      loc_1400322DF
0x14003202f  cmp     ecx, 6
0x140032032  jz      loc_140032217
0x140032038  cmp     ecx, 8
0x14003203b  jz      loc_1400321C4
0x140032041  cmp     ecx, 0Ah
0x140032044  jz      loc_140032171
0x14003204a  lea     r12d, [rdi+0Ch]
0x14003204e  cmp     ecx, r12d
0x140032051  jz      short loc_140032084
0x140032053  mov     ecx, 0C000000Dh
0x140032058  mov     edi, ecx
0x14003205a  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032061  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140032068  jz      loc_1400324CB
0x14003206e  lea     r9d, [r12+53h]
0x140032073  mov     [rsp+98h+var_60], ecx
0x140032077  mov     dword ptr [rsp+98h+var_68], 6A2h
0x14003207f  jmp     loc_140031E9A
0x140032084  cmp     eax, 18h
0x140032087  jnb     short loc_1400320BB
0x140032089  mov     ecx, 0C000000Dh
0x14003208e  mov     edi, ecx
0x140032090  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032097  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003209e  jz      loc_1400324CB
0x1400320a4  mov     r9d, 5Ch ; '\'
0x1400320aa  mov     [rsp+98h+var_60], ecx
0x1400320ae  mov     dword ptr [rsp+98h+var_68], 675h
0x1400320b6  jmp     loc_140031E9A
0x1400320bb  cmp     dword ptr [rsp+98h+Length], 1Ch
0x1400320c3  jnb     short loc_1400320F7
0x1400320c5  mov     ecx, 0C000000Dh
0x1400320ca  mov     edi, ecx
0x1400320cc  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400320d3  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400320da  jz      loc_1400324CB
0x1400320e0  mov     r9d, 5Dh ; ']'
0x1400320e6  mov     [rsp+98h+var_60], ecx
0x1400320ea  mov     dword ptr [rsp+98h+var_68], 67Dh
0x1400320f2  jmp     loc_140031E9A
0x1400320f7  mov     r8, r13
0x1400320fa  xor     edx, edx
0x1400320fc  mov     rcx, rsi; void *
0x1400320ff  call    RtlSetUserMemory
0x140032104  lea     rcx, [rbx+8]
0x140032108  call    cs:__imp_MmIsUserAddress
0x14003210f  nop     dword ptr [rax+rax+00h]
0x140032114  test    al, al
0x140032116  setnz   dl
0x140032119  lea     rax, [rsp+98h+arg_10]
0x140032121  mov     [rsp+98h+var_78], rax
0x140032126  mov     r9, rsi
0x140032129  mov     r8d, dword ptr [rsp+98h+Length]
0x140032131  lea     rcx, [rbx+8]
0x140032135  call    WcProcessGetUnions
0x14003213a  nop
0x14003213b  lea     rcx, [rsi+4]
0x14003213f  mov     edx, eax
0x140032141  call    RtlWriteULongToUser
0x140032146  mov     ebx, [rsp+98h+arg_10]
0x14003214d  mov     edx, ebx
0x14003214f  mov     rcx, rsi
0x140032152  call    RtlWriteULongToUser
0x140032157  nop
0x140032158  mov     rax, [rsp+98h+ReturnOutputBufferLength]
0x140032160  mov     [rax], ebx
0x140032162  jmp     loc_1400324CB
0x140032167  mov     edi, 0C0000005h
0x14003216c  jmp     loc_1400324CB
0x140032171  mov     edx, 0Bh
0x140032176  mov     rcx, rsi
0x140032179  call    RtlWriteULongToUser
0x14003217e  lea     rcx, [rsi+4]
0x140032182  mov     r12d, 0Ch
0x140032188  mov     edx, r12d
0x14003218b  call    RtlWriteULongToUser
0x140032190  nop
0x140032191  mov     edx, [rbx+4]
0x140032194  sub     edx, 8
0x140032197  lea     rcx, [rbx+8]
0x14003219b  call    WcSetUnion
0x1400321a0  lea     rcx, [rsi+8]
0x1400321a4  mov     edx, eax
0x1400321a6  call    RtlWriteULongToUser
0x1400321ab  jmp     loc_1400324AB
0x1400321b0  mov     edi, 0C0000005h
0x1400321b5  jmp     loc_1400324CB
0x1400321ba  mov     edi, 0C0000005h
0x1400321bf  jmp     loc_1400324CB
0x1400321c4  mov     edx, 9
0x1400321c9  mov     rcx, rsi
0x1400321cc  call    RtlWriteULongToUser
0x1400321d1  lea     rcx, [rsi+4]
0x1400321d5  mov     r12d, 0Ch
0x1400321db  mov     edx, r12d
0x1400321de  call    RtlWriteULongToUser
0x1400321e3  nop
0x1400321e4  mov     edx, [rbx+4]
0x1400321e7  sub     edx, 8
0x1400321ea  lea     rcx, [rbx+8]
0x1400321ee  call    WcRemoveUnionContext
0x1400321f3  lea     rcx, [rsi+8]
0x1400321f7  mov     edx, eax
0x1400321f9  call    RtlWriteULongToUser
0x1400321fe  jmp     loc_1400324AB
0x140032203  mov     edi, 0C0000005h
0x140032208  jmp     loc_1400324CB
0x14003220d  mov     edi, 0C0000005h
0x140032212  jmp     loc_1400324CB
0x140032217  cmp     eax, 7Ch ; '|'
0x14003221a  jnb     short loc_14003224E
0x14003221c  mov     ecx, 0C000000Dh
0x140032221  mov     edi, ecx
0x140032223  lea     rdx, WPP_RECORDER_INITIALIZED
0x14003222a  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140032231  jz      loc_1400324CB
0x140032237  mov     r9d, 54h ; 'T'
0x14003223d  mov     [rsp+98h+var_60], ecx
0x140032241  mov     dword ptr [rsp+98h+var_68], 5E8h
0x140032249  jmp     loc_140031E9A
0x14003224e  mov     ecx, [rbx+0Ch]
0x140032251  add     rcx, 8
0x140032255  cmp     rax, rcx
0x140032258  jz      short loc_14003228C
0x14003225a  mov     ecx, 0C000000Dh
0x14003225f  mov     edi, ecx
0x140032261  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032268  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003226f  jz      loc_1400324CB
0x140032275  mov     r9d, 57h ; 'W'
0x14003227b  mov     [rsp+98h+var_60], ecx
0x14003227f  mov     dword ptr [rsp+98h+var_68], 5FEh
0x140032287  jmp     loc_140031E9A
0x14003228c  mov     edx, 7
0x140032291  mov     rcx, rsi
0x140032294  call    RtlWriteULongToUser
0x140032299  lea     rcx, [rsi+4]
0x14003229d  mov     r12d, 0Ch
0x1400322a3  mov     edx, r12d
0x1400322a6  call    RtlWriteULongToUser
0x1400322ab  nop
0x1400322ac  mov     edx, [rbx+4]
0x1400322af  sub     edx, 8
0x1400322b2  lea     rcx, [rbx+8]
0x1400322b6  call    WcSetupVolumeInformationHandler
0x1400322bb  lea     rcx, [rsi+8]
0x1400322bf  mov     edx, eax
0x1400322c1  call    RtlWriteULongToUser
0x1400322c6  jmp     loc_1400324AB
0x1400322cb  mov     edi, 0C0000005h
0x1400322d0  jmp     loc_1400324CB
0x1400322d5  mov     edi, 0C0000005h
0x1400322da  jmp     loc_1400324CB
0x1400322df  cmp     eax, 9Ah
0x1400322e4  jnb     short loc_140032318
0x1400322e6  mov     ecx, 0C000000Dh
0x1400322eb  mov     edi, ecx
0x1400322ed  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400322f4  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400322fb  jz      loc_1400324CB
0x140032301  mov     r9d, 50h ; 'P'
0x140032307  mov     [rsp+98h+var_60], ecx
0x14003230b  mov     dword ptr [rsp+98h+var_68], 5AFh
0x140032313  jmp     loc_140031E9A
0x140032318  mov     ecx, [rbx+0Ch]
0x14003231b  add     rcx, 8
0x14003231f  cmp     rax, rcx
0x140032322  jz      short loc_140032356
0x140032324  mov     ecx, 0C000000Dh
0x140032329  mov     edi, ecx
0x14003232b  lea     rdx, WPP_RECORDER_INITIALIZED
0x140032332  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140032339  jz      loc_1400324CB
0x14003233f  mov     r9d, 53h ; 'S'
0x140032345  mov     [rsp+98h+var_60], ecx
0x140032349  mov     dword ptr [rsp+98h+var_68], 5C5h
0x140032351  jmp     loc_140031E9A
0x140032356  mov     edx, 5
0x14003235b  mov     rcx, rsi
0x14003235e  call    RtlWriteULongToUser
0x140032363  lea     rcx, [rsi+4]
0x140032367  mov     r12d, 0Ch
0x14003236d  mov     edx, r12d
0x140032370  call    RtlWriteULongToUser
0x140032375  nop
0x140032376  mov     edx, [rbx+4]
0x140032379  sub     edx, 8
0x14003237c  lea     rcx, [rbx+8]
0x140032380  call    WcCopyFileHandler
0x140032385  lea     rcx, [rsi+8]
0x140032389  mov     edx, eax
0x14003238b  call    RtlWriteULongToUser
0x140032390  jmp     loc_1400324AB
0x140032395  mov     edi, 0C0000005h
  ... truncated ...
```

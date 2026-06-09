# VidPartitionInitialize

- ea: `0x14000a040`
- end: `0x14000a544`
- name: `VidPartitionInitialize`
- size: `1284`
- prototype: `__int64 __fastcall(PVOID DeferredContext, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x1400094b8`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x14000a040`
- `0x14000a62c`
- `0x140011d70`
- `0x140021c60`
- `0x140021e00`
- `0x1400239b0`
- `0x140030990`
- `0x1400309d0`
- `0x1400386a0`
- `0x14009fc24`
- `0x1400f04a0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a378`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a378`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000a0a5`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000a214`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000a0a5`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000a214`
- `ntoskrnl!KeInitializeDpc` at `0x14000a08b`
- `ntoskrnl!KeInitializeDpc` at `0x14000a1fa`
- `ntoskrnl!KeInitializeDpc` at `0x14000a08b`
- `ntoskrnl!KeInitializeDpc` at `0x14000a1fa`
- `ntoskrnl!ExAllocatePool2` at `0x14000a2b0`
- `ntoskrnl!ExAllocatePool2` at `0x14000a396`
- `ntoskrnl!ExAllocatePool2` at `0x14000a41c`
- `ntoskrnl!ExAllocatePool2` at `0x14000a495`
- `ntoskrnl!ExAllocatePool2` at `0x14000a2b0`
- `ntoskrnl!ExAllocatePool2` at `0x14000a396`
- `ntoskrnl!ExAllocatePool2` at `0x14000a41c`
- `ntoskrnl!ExAllocatePool2` at `0x14000a495`

## string_xrefs

- `0x14000a0b8`: `onecore\vm\vid\sys\driver\vidcreateclose.c`

## pseudocode

```c
__int64 __fastcall VidPartitionInitialize(char *DeferredContext, PCUNICODE_STRING SourceString, _OWORD *a3)
{
  PIO_WORKITEM WorkItem; // rax
  int v7; // esi
  PIO_WORKITEM v9; // rax
  __int64 MaximumLength; // rdx
  __int64 Pool2; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  char v15; // cl
  char *v16; // rax
  char *v17; // rdx
  __int64 i; // rcx
  char *v19; // rax
  char *v20; // rdx
  __int64 j; // rcx
  int v22; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v23[3]; // [rsp+34h] [rbp-55h] BYREF
  _BYTE v24[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v25[16]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v26[16]; // [rsp+70h] [rbp-19h] BYREF
  _DWORD *v27; // [rsp+80h] [rbp-9h]
  __int64 v28; // [rsp+88h] [rbp-1h]
  int *v29; // [rsp+90h] [rbp+7h]
  __int64 v30; // [rsp+98h] [rbp+Fh]
  _OWORD *v31; // [rsp+A0h] [rbp+17h]
  __int64 v32; // [rsp+A8h] [rbp+1Fh]

  VidpInitializePartitionInternal(DeferredContext);
  KeInitializeDpc((PRKDPC)DeferredContext + 189, VidInsufficientMemoryDpcRoutine, DeferredContext);
  WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)VidDeviceExtension + 21));
  *((_QWORD *)DeferredContext + 1520) = WorkItem;
  if ( WorkItem )
  {
    KeInitializeDpc((PRKDPC)(DeferredContext + 12192), VidPartitionInterceptDpcRoutine, DeferredContext);
    v9 = IoAllocateWorkItem(*((PDEVICE_OBJECT *)VidDeviceExtension + 21));
    *((_QWORD *)DeferredContext + 1532) = v9;
    if ( v9 )
    {
      v7 = VidStatisticsDataSetup((PFAST_MUTEX)(DeferredContext + 1472));
      if ( v7 >= 0 )
      {
        *(_QWORD *)(*((_QWORD *)DeferredContext + 191) + 400LL) = 1;
        *((_OWORD *)DeferredContext + 41) = *a3;
        *((_WORD *)DeferredContext + 52) = SourceString->Length;
        MaximumLength = SourceString->MaximumLength;
        *((_WORD *)DeferredContext + 53) = SourceString->MaximumLength;
        Pool2 = ExAllocatePool2(64, MaximumLength, 1917084758);
        *((_QWORD *)DeferredContext + 14) = Pool2;
        if ( Pool2 )
        {
          RtlCopyUnicodeString((PUNICODE_STRING)(DeferredContext + 104), SourceString);
          v12 = ExAllocatePool2(64, 48960, 1917084758);
          *((_QWORD *)DeferredContext + 422) = v12;
          if ( v12 )
          {
            v13 = 0;
            do
            {
              v14 = 192 * v13;
              v15 = v13 + 1;
              v13 = (unsigned int)(v13 + 1);
              *(_DWORD *)(v14 + *((_QWORD *)DeferredContext + 422) + 112) = 8;
              *(_BYTE *)(v14 + *((_QWORD *)DeferredContext + 422) + 152) = v15;
            }
            while ( (unsigned int)v13 < 0xFF );
            DeferredContext[3384] = 0;
            v16 = (char *)ExAllocatePool2(64, 0x10000, 1917084758);
            v17 = DeferredContext + 3408;
            *((_QWORD *)DeferredContext + 426) = v16;
            if ( v16 )
            {
              if ( v16 > v17 || v16 + 0xFFFF < v17 )
              {
                LOBYTE(v17) = -1;
                memset(v16, (int)v17, 0x10000u);
              }
              else
              {
                for ( i = 0; i != 0x10000; ++i )
                  *(_BYTE *)(i + *(_QWORD *)v17) = -1;
              }
              v19 = (char *)ExAllocatePool2(64, 256, 1917084758);
              v20 = DeferredContext + 3392;
              *((_QWORD *)DeferredContext + 424) = v19;
              if ( v19 )
              {
                if ( v19 > v20 || v19 + 255 < v20 )
                {
                  LOBYTE(v20) = -1;
                  memset(v19, (int)v20, 0x100u);
                }
                else
                {
                  for ( j = 0; j != 256; ++j )
                    *(_BYTE *)(j + *(_QWORD *)v20) = -1;
                }
                v7 = VidReaderCounterSetup(DeferredContext + 3928);
                if ( v7 >= 0 )
                {
                  v7 = VsmmPartitionInitialize(DeferredContext);
                  if ( v7 >= 0 )
                    return 0;
                }
                else
                {
                  VidTraceErrorInternal0(
                    "VidPartitionInitialize",
                    "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c",
                    1041);
                }
              }
              else
              {
                v7 = -1073741670;
                VidTraceErrorInternal0(
                  "VidPartitionInitialize",
                  "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c",
                  1027);
              }
            }
            else
            {
              v7 = -1073741670;
              VidTraceErrorInternal0("VidPartitionInitialize", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 1006);
            }
          }
          else
          {
            v7 = -1073741670;
            VidTraceErrorInternal0("VidPartitionInitialize", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 979);
          }
        }
        else
        {
          v7 = -1073741670;
          if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          {
            tlgCreate1Sz_char(v25, "VidPartitionInitialize");
            tlgCreate1Sz_char(v26, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
            v23[0] = 963;
            v27 = v23;
            LOWORD(v22) = *((_WORD *)DeferredContext + 53);
            v28 = 4;
            v29 = &v22;
            v30 = 2;
            tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &word_14004648E, 0, 0, 6, v24);
          }
        }
      }
      else
      {
        VidTraceErrorInternal0("VidPartitionInitialize", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 919);
      }
    }
    else
    {
      v7 = -1073741670;
      VidTraceErrorInternal0("VidPartitionInitialize", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 905);
    }
  }
  else
  {
    v7 = -1073741670;
    VidTraceErrorInternal0("VidPartitionInitialize", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 891);
  }
  VidLockAcquireExclusive(DeferredContext + 8);
  VidLockAcquireExclusive(DeferredContext + 3744);
  VidPartitionUninitialize((__int64)DeferredContext);
  VidLockRelease(DeferredContext + 3744);
  VidLockRelease(DeferredContext + 8);
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v25, "VidPartitionInitialize");
    tlgCreate1Sz_char(v26, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
    v23[0] = 1064;
    v27 = v23;
    v28 = 4;
    v29 = &v22;
    v22 = v7;
    v30 = 4;
    v31 = a3;
    v32 = 16;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &byte_14004643F, 0, 0, 7, v24);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a040  mov     [rsp-8+arg_10], rbx
0x14000a045  mov     [rsp-8+arg_18], rsi
0x14000a04a  push    rbp
0x14000a04b  push    rdi
0x14000a04c  push    r13
0x14000a04e  push    r14
0x14000a050  push    r15
0x14000a052  lea     rbp, [rsp-37h]
0x14000a057  sub     rsp, 0C0h
0x14000a05e  mov     rax, cs:__security_cookie
0x14000a065  xor     rax, rsp
0x14000a068  mov     [rbp+57h+var_30], rax
0x14000a06c  mov     r15, r8
0x14000a06f  mov     rbx, rdx
0x14000a072  mov     r14, rcx
0x14000a075  call    VidpInitializePartitionInternal
0x14000a07a  lea     rcx, [r14+2F40h]; Dpc
0x14000a081  mov     r8, r14; DeferredContext
0x14000a084  lea     rdx, VidInsufficientMemoryDpcRoutine; DeferredRoutine
0x14000a08b  call    cs:__imp_KeInitializeDpc
0x14000a092  nop     dword ptr [rax+rax+00h]
0x14000a097  mov     rcx, cs:VidDeviceExtension
0x14000a09e  mov     rcx, [rcx+0A8h]; DeviceObject
0x14000a0a5  call    cs:__imp_IoAllocateWorkItem
0x14000a0ac  nop     dword ptr [rax+rax+00h]
0x14000a0b1  mov     [r14+2F80h], rax
0x14000a0b8  lea     r13, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x14000a0bf  lea     rdi, aVidpartitionin; "VidPartitionInitialize"
0x14000a0c6  test    rax, rax
0x14000a0c9  jnz     loc_14000A1E9
0x14000a0cf  mov     esi, 0C000009Ah
0x14000a0d4  mov     r8d, 37Bh
0x14000a0da  mov     rdx, r13
0x14000a0dd  mov     rcx, rdi
0x14000a0e0  call    VidTraceErrorInternal0
0x14000a0e5  lea     rcx, [r14+8]
0x14000a0e9  call    VidLockAcquireExclusive
0x14000a0ee  lea     rbx, [r14+0EA0h]
0x14000a0f5  mov     rcx, rbx
0x14000a0f8  call    VidLockAcquireExclusive
0x14000a0fd  mov     rcx, r14
0x14000a100  call    VidPartitionUninitialize
0x14000a105  mov     rcx, rbx
0x14000a108  call    VidLockRelease
0x14000a10d  lea     rcx, [r14+8]
0x14000a111  call    VidLockRelease
0x14000a116  test    esi, esi
0x14000a118  jns     loc_14000A1BE
0x14000a11e  mov     eax, cs:dword_140065110
0x14000a124  cmp     eax, 2
0x14000a127  jbe     loc_14000A1BE
0x14000a12d  mov     edx, 100h
0x14000a132  lea     rcx, dword_140065110
0x14000a139  call    _tlgKeywordOn
0x14000a13e  test    al, al
0x14000a140  jz      short loc_14000A1BE
0x14000a142  lea     rdx, aVidpartitionin; "VidPartitionInitialize"
0x14000a149  lea     rcx, [rbp+57h+var_80]
0x14000a14d  call    _tlgCreate1Sz_char
0x14000a152  mov     rdx, r13
0x14000a155  lea     rcx, [rbp+57h+var_70]
0x14000a159  call    _tlgCreate1Sz_char
0x14000a15e  lea     rax, [rbp+57h+var_AC]
0x14000a162  mov     [rbp+57h+var_AC], 428h
0x14000a169  mov     [rbp+57h+var_60], rax
0x14000a16d  lea     rdx, byte_14004643F
0x14000a174  lea     rax, [rbp+57h+var_B0]
0x14000a178  mov     [rbp+57h+var_58], 4
0x14000a180  mov     [rbp+57h+var_50], rax
0x14000a184  lea     rcx, dword_140065110
0x14000a18b  lea     rax, [rbp+57h+var_A0]
0x14000a18f  mov     [rbp+57h+var_B0], esi
0x14000a192  mov     [rsp+0E0h+var_B8], rax
0x14000a197  xor     r9d, r9d
0x14000a19a  xor     r8d, r8d
0x14000a19d  mov     [rsp+0E0h+var_C0], 7
0x14000a1a5  mov     [rbp+57h+var_48], 4
0x14000a1ad  mov     [rbp+57h+var_40], r15
0x14000a1b1  mov     [rbp+57h+var_38], 10h
0x14000a1b9  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a1be  mov     eax, esi
0x14000a1c0  mov     rcx, [rbp+57h+var_30]
0x14000a1c4  xor     rcx, rsp; StackCookie
0x14000a1c7  call    __security_check_cookie
0x14000a1cc  lea     r11, [rsp+0E0h+var_20]
0x14000a1d4  mov     rbx, [r11+40h]
0x14000a1d8  mov     rsi, [r11+48h]
0x14000a1dc  mov     rsp, r11
0x14000a1df  pop     r15
0x14000a1e1  pop     r14
0x14000a1e3  pop     r13
0x14000a1e5  pop     rdi
0x14000a1e6  pop     rbp
0x14000a1e7  retn
0x14000a1e9  lea     rcx, [r14+2FA0h]; Dpc
0x14000a1f0  mov     r8, r14; DeferredContext
0x14000a1f3  lea     rdx, VidPartitionInterceptDpcRoutine; DeferredRoutine
0x14000a1fa  call    cs:__imp_KeInitializeDpc
0x14000a201  nop     dword ptr [rax+rax+00h]
0x14000a206  mov     rcx, cs:VidDeviceExtension
0x14000a20d  mov     rcx, [rcx+0A8h]; DeviceObject
0x14000a214  call    cs:__imp_IoAllocateWorkItem
0x14000a21b  nop     dword ptr [rax+rax+00h]
0x14000a220  mov     [r14+2FE0h], rax
0x14000a227  test    rax, rax
0x14000a22a  jnz     short loc_14000A247
0x14000a22c  mov     esi, 0C000009Ah
0x14000a231  mov     r8d, 389h
0x14000a237  mov     rdx, r13
0x14000a23a  mov     rcx, rdi
0x14000a23d  call    VidTraceErrorInternal0
0x14000a242  jmp     loc_14000A0E5
0x14000a247  lea     rcx, [r14+5C0h]; FastMutex
0x14000a24e  mov     edx, 2CCh
0x14000a253  call    VidStatisticsDataSetup
0x14000a258  mov     esi, eax
0x14000a25a  test    eax, eax
0x14000a25c  jns     short loc_14000A274
0x14000a25e  mov     r8d, 397h
0x14000a264  mov     rdx, r13
0x14000a267  mov     rcx, rdi
0x14000a26a  call    VidTraceErrorInternal0
0x14000a26f  jmp     loc_14000A0E5
0x14000a274  mov     rax, [r14+5F8h]
0x14000a27b  mov     esi, 1
0x14000a280  mov     r8d, 72446456h
0x14000a286  mov     [rax+190h], rsi
0x14000a28d  lea     ecx, [rsi+3Fh]
0x14000a290  movups  xmm0, xmmword ptr [r15]
0x14000a294  movdqu  xmmword ptr [r14+290h], xmm0
0x14000a29d  movzx   eax, word ptr [rbx]
0x14000a2a0  mov     [r14+68h], ax
0x14000a2a5  movzx   eax, word ptr [rbx+2]
0x14000a2a9  mov     edx, eax
0x14000a2ab  mov     [r14+6Ah], ax
0x14000a2b0  call    cs:__imp_ExAllocatePool2
0x14000a2b7  nop     dword ptr [rax+rax+00h]
0x14000a2bc  mov     [r14+70h], rax
0x14000a2c0  test    rax, rax
0x14000a2c3  jnz     loc_14000A371
0x14000a2c9  mov     eax, cs:dword_140065110
0x14000a2cf  mov     esi, 0C000009Ah
0x14000a2d4  cmp     eax, 2
0x14000a2d7  jbe     loc_14000A0E5
0x14000a2dd  mov     edx, 100h
0x14000a2e2  lea     rcx, dword_140065110
0x14000a2e9  call    _tlgKeywordOn
0x14000a2ee  test    al, al
0x14000a2f0  jz      loc_14000A0E5
0x14000a2f6  lea     rdx, aVidpartitionin; "VidPartitionInitialize"
0x14000a2fd  lea     rcx, [rbp+57h+var_80]
0x14000a301  call    _tlgCreate1Sz_char
0x14000a306  mov     rdx, r13
0x14000a309  lea     rcx, [rbp+57h+var_70]
0x14000a30d  call    _tlgCreate1Sz_char
0x14000a312  lea     rax, [rbp+57h+var_AC]
0x14000a316  mov     [rbp+57h+var_AC], 3C3h
0x14000a31d  mov     [rbp+57h+var_60], rax
0x14000a321  lea     rdx, word_14004648E
0x14000a328  movzx   eax, word ptr [r14+6Ah]
0x14000a32d  lea     rcx, dword_140065110
0x14000a334  mov     word ptr [rbp+57h+var_B0], ax
0x14000a338  xor     r9d, r9d
0x14000a33b  lea     rax, [rbp+57h+var_B0]
0x14000a33f  mov     [rbp+57h+var_58], 4
0x14000a347  mov     [rbp+57h+var_50], rax
0x14000a34b  xor     r8d, r8d
0x14000a34e  lea     rax, [rbp+57h+var_A0]
0x14000a352  mov     [rbp+57h+var_48], 2
0x14000a35a  mov     [rsp+0E0h+var_B8], rax
0x14000a35f  mov     [rsp+0E0h+var_C0], 6
0x14000a367  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a36c  jmp     loc_14000A0E5
0x14000a371  mov     rdx, rbx; SourceString
0x14000a374  lea     rcx, [r14+68h]; DestinationString
0x14000a378  call    cs:__imp_RtlCopyUnicodeString
0x14000a37f  nop     dword ptr [rax+rax+00h]
0x14000a384  mov     edi, 72446456h
0x14000a389  mov     edx, 0BF40h
0x14000a38e  mov     r8d, edi
0x14000a391  mov     ecx, 40h ; '@'
0x14000a396  call    cs:__imp_ExAllocatePool2
0x14000a39d  nop     dword ptr [rax+rax+00h]
0x14000a3a2  mov     [r14+0D30h], rax
0x14000a3a9  test    rax, rax
0x14000a3ac  jnz     short loc_14000A3CD
0x14000a3ae  mov     esi, 0C000009Ah
0x14000a3b3  mov     r8d, 3D3h
0x14000a3b9  lea     rcx, aVidpartitionin; "VidPartitionInitialize"
0x14000a3c0  mov     rdx, r13
0x14000a3c3  call    VidTraceErrorInternal0
0x14000a3c8  jmp     loc_14000A0E5
0x14000a3cd  xor     r8d, r8d
0x14000a3d0  mov     rax, [r14+0D30h]
0x14000a3d7  lea     rdx, [r8+r8*2]
0x14000a3db  shl     rdx, 6
0x14000a3df  lea     ecx, [rsi+r8]
0x14000a3e3  add     r8d, esi
0x14000a3e6  mov     dword ptr [rdx+rax+70h], 8
0x14000a3ee  mov     rax, [r14+0D30h]
0x14000a3f5  mov     [rdx+rax+98h], cl
0x14000a3fc  cmp     r8d, 0FFh
0x14000a403  jb      short loc_14000A3D0
0x14000a405  mov     ebx, 10000h
0x14000a40a  mov     byte ptr [r14+0D38h], 0
0x14000a412  mov     edx, ebx
0x14000a414  mov     r8d, edi
0x14000a417  mov     ecx, 40h ; '@'
0x14000a41c  call    cs:__imp_ExAllocatePool2
0x14000a423  nop     dword ptr [rax+rax+00h]
0x14000a428  lea     rdx, [r14+0D50h]
0x14000a42f  mov     rcx, rax; void *
0x14000a432  mov     [rdx], rax
0x14000a435  test    rax, rax
0x14000a438  jnz     short loc_14000A459
0x14000a43a  mov     esi, 0C000009Ah
0x14000a43f  mov     r8d, 3EEh
0x14000a445  lea     rcx, aVidpartitionin; "VidPartitionInitialize"
0x14000a44c  mov     rdx, r13
0x14000a44f  call    VidTraceErrorInternal0
0x14000a454  jmp     loc_14000A0E5
0x14000a459  cmp     rcx, rdx
0x14000a45c  ja      short loc_14000A47C
0x14000a45e  add     rax, 0FFFFh
0x14000a464  cmp     rax, rdx
0x14000a467  jb      short loc_14000A47C
0x14000a469  xor     ecx, ecx
0x14000a46b  mov     rax, [rdx]
0x14000a46e  mov     byte ptr [rcx+rax], 0FFh
0x14000a472  add     rcx, rsi
0x14000a475  cmp     rcx, rbx
0x14000a478  jnz     short loc_14000A46B
0x14000a47a  jmp     short loc_14000A486
0x14000a47c  mov     r8, rbx; Size
0x14000a47f  mov     dl, 0FFh; Val
0x14000a481  call    memset
0x14000a486  mov     ebx, 100h
0x14000a48b  mov     r8d, edi
0x14000a48e  mov     edx, ebx
0x14000a490  mov     ecx, 40h ; '@'
0x14000a495  call    cs:__imp_ExAllocatePool2
0x14000a49c  nop     dword ptr [rax+rax+00h]
0x14000a4a1  lea     rdx, [r14+0D40h]
0x14000a4a8  mov     rcx, rax; void *
0x14000a4ab  mov     [rdx], rax
0x14000a4ae  test    rax, rax
0x14000a4b1  jnz     short loc_14000A4D2
0x14000a4b3  mov     esi, 0C000009Ah
0x14000a4b8  mov     r8d, 403h
0x14000a4be  lea     rcx, aVidpartitionin; "VidPartitionInitialize"
0x14000a4c5  mov     rdx, r13
0x14000a4c8  call    VidTraceErrorInternal0
0x14000a4cd  jmp     loc_14000A0E5
0x14000a4d2  cmp     rcx, rdx
0x14000a4d5  ja      short loc_14000A4F5
0x14000a4d7  add     rax, 0FFh
0x14000a4dd  cmp     rax, rdx
0x14000a4e0  jb      short loc_14000A4F5
0x14000a4e2  xor     ecx, ecx
0x14000a4e4  mov     rax, [rdx]
0x14000a4e7  mov     byte ptr [rcx+rax], 0FFh
0x14000a4eb  add     rcx, rsi
0x14000a4ee  cmp     rcx, rbx
0x14000a4f1  jnz     short loc_14000A4E4
0x14000a4f3  jmp     short loc_14000A4FF
0x14000a4f5  mov     r8, rbx; Size
0x14000a4f8  mov     dl, 0FFh; Val
0x14000a4fa  call    memset
0x14000a4ff  lea     rcx, [r14+0F58h]
0x14000a506  call    VidReaderCounterSetup
0x14000a50b  mov     esi, eax
0x14000a50d  test    eax, eax
0x14000a50f  jns     short loc_14000A52B
0x14000a511  mov     r8d, 411h
0x14000a517  lea     rcx, aVidpartitionin; "VidPartitionInitialize"
0x14000a51e  mov     rdx, r13
0x14000a521  call    VidTraceErrorInternal0
0x14000a526  jmp     loc_14000A0E5
0x14000a52b  mov     rcx, r14
0x14000a52e  call    VsmmPartitionInitialize
0x14000a533  mov     esi, eax
0x14000a535  test    eax, eax
0x14000a537  js      loc_14000A0E5
0x14000a53d  xor     esi, esi
0x14000a53f  jmp     loc_14000A1BE
```

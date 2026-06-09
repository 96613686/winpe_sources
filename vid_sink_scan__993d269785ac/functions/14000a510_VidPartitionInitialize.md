# VidPartitionInitialize

- ea: `0x14000a510`
- end: `0x14000aa14`
- name: `VidPartitionInitialize`
- size: `1284`
- prototype: `__int64 __fastcall(char *DeferredContext, PCUNICODE_STRING SourceString, _OWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x140009988`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x14000a510`
- `0x14000aafc`
- `0x140011f20`
- `0x140021650`
- `0x140021800`
- `0x1400239b0`
- `0x140030790`
- `0x1400307d0`
- `0x140038630`
- `0x14009e1f4`
- `0x1400ed7c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a848`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000a848`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000a575`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000a6e4`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000a575`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000a6e4`
- `ntoskrnl!KeInitializeDpc` at `0x14000a55b`
- `ntoskrnl!KeInitializeDpc` at `0x14000a6ca`
- `ntoskrnl!KeInitializeDpc` at `0x14000a55b`
- `ntoskrnl!KeInitializeDpc` at `0x14000a6ca`
- `ntoskrnl!ExAllocatePool2` at `0x14000a780`
- `ntoskrnl!ExAllocatePool2` at `0x14000a866`
- `ntoskrnl!ExAllocatePool2` at `0x14000a8ec`
- `ntoskrnl!ExAllocatePool2` at `0x14000a965`
- `ntoskrnl!ExAllocatePool2` at `0x14000a780`
- `ntoskrnl!ExAllocatePool2` at `0x14000a866`
- `ntoskrnl!ExAllocatePool2` at `0x14000a8ec`
- `ntoskrnl!ExAllocatePool2` at `0x14000a965`

## string_xrefs

- `0x14000a588`: `onecore\vm\vid\sys\driver\vidcreateclose.c`

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
      v7 = VidStatisticsDataSetup((PFAST_MUTEX)(DeferredContext + 1472), 716);
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
                v7 = VidReaderCounterSetup((ULONG *)DeferredContext + 982);
                if ( v7 >= 0 )
                {
                  v7 = VsmmPartitionInitialize((__int64)DeferredContext);
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
          if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          {
            tlgCreate1Sz_char(v25, "VidPartitionInitialize");
            tlgCreate1Sz_char(v26, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
            v23[0] = 963;
            v27 = v23;
            LOWORD(v22) = *((_WORD *)DeferredContext + 53);
            v28 = 4;
            v29 = &v22;
            v30 = 2;
            tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_1400462E6, 0, 0, 6, v24);
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
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_140046297, 0, 0, 7, v24);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a510  mov     [rsp-8+arg_10], rbx
0x14000a515  mov     [rsp-8+arg_18], rsi
0x14000a51a  push    rbp
0x14000a51b  push    rdi
0x14000a51c  push    r13
0x14000a51e  push    r14
0x14000a520  push    r15
0x14000a522  lea     rbp, [rsp-37h]
0x14000a527  sub     rsp, 0C0h
0x14000a52e  mov     rax, cs:__security_cookie
0x14000a535  xor     rax, rsp
0x14000a538  mov     [rbp+57h+var_30], rax
0x14000a53c  mov     r15, r8
0x14000a53f  mov     rbx, rdx
0x14000a542  mov     r14, rcx
0x14000a545  call    VidpInitializePartitionInternal
0x14000a54a  lea     rcx, [r14+2F40h]; Dpc
0x14000a551  mov     r8, r14; DeferredContext
0x14000a554  lea     rdx, VidInsufficientMemoryDpcRoutine; DeferredRoutine
0x14000a55b  call    cs:__imp_KeInitializeDpc
0x14000a562  nop     dword ptr [rax+rax+00h]
0x14000a567  mov     rcx, cs:VidDeviceExtension
0x14000a56e  mov     rcx, [rcx+0A8h]; DeviceObject
0x14000a575  call    cs:__imp_IoAllocateWorkItem
0x14000a57c  nop     dword ptr [rax+rax+00h]
0x14000a581  mov     [r14+2F80h], rax
0x14000a588  lea     r13, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x14000a58f  lea     rdi, aVidpartitionin; "VidPartitionInitialize"
0x14000a596  test    rax, rax
0x14000a599  jnz     loc_14000A6B9
0x14000a59f  mov     esi, 0C000009Ah
0x14000a5a4  mov     r8d, 37Bh
0x14000a5aa  mov     rdx, r13
0x14000a5ad  mov     rcx, rdi
0x14000a5b0  call    VidTraceErrorInternal0
0x14000a5b5  lea     rcx, [r14+8]
0x14000a5b9  call    VidLockAcquireExclusive
0x14000a5be  lea     rbx, [r14+0EA0h]
0x14000a5c5  mov     rcx, rbx
0x14000a5c8  call    VidLockAcquireExclusive
0x14000a5cd  mov     rcx, r14
0x14000a5d0  call    VidPartitionUninitialize
0x14000a5d5  mov     rcx, rbx
0x14000a5d8  call    VidLockRelease
0x14000a5dd  lea     rcx, [r14+8]
0x14000a5e1  call    VidLockRelease
0x14000a5e6  test    esi, esi
0x14000a5e8  jns     loc_14000A68E
0x14000a5ee  mov     eax, cs:dword_140064110
0x14000a5f4  cmp     eax, 2
0x14000a5f7  jbe     loc_14000A68E
0x14000a5fd  mov     edx, 100h
0x14000a602  lea     rcx, dword_140064110
0x14000a609  call    _tlgKeywordOn
0x14000a60e  test    al, al
0x14000a610  jz      short loc_14000A68E
0x14000a612  lea     rdx, aVidpartitionin; "VidPartitionInitialize"
0x14000a619  lea     rcx, [rbp+57h+var_80]
0x14000a61d  call    _tlgCreate1Sz_char
0x14000a622  mov     rdx, r13
0x14000a625  lea     rcx, [rbp+57h+var_70]
0x14000a629  call    _tlgCreate1Sz_char
0x14000a62e  lea     rax, [rbp+57h+var_AC]
0x14000a632  mov     [rbp+57h+var_AC], 428h
0x14000a639  mov     [rbp+57h+var_60], rax
0x14000a63d  lea     rdx, byte_140046297
0x14000a644  lea     rax, [rbp+57h+var_B0]
0x14000a648  mov     [rbp+57h+var_58], 4
0x14000a650  mov     [rbp+57h+var_50], rax
0x14000a654  lea     rcx, dword_140064110
0x14000a65b  lea     rax, [rbp+57h+var_A0]
0x14000a65f  mov     [rbp+57h+var_B0], esi
0x14000a662  mov     [rsp+0E0h+var_B8], rax
0x14000a667  xor     r9d, r9d
0x14000a66a  xor     r8d, r8d
0x14000a66d  mov     [rsp+0E0h+var_C0], 7
0x14000a675  mov     [rbp+57h+var_48], 4
0x14000a67d  mov     [rbp+57h+var_40], r15
0x14000a681  mov     [rbp+57h+var_38], 10h
0x14000a689  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a68e  mov     eax, esi
0x14000a690  mov     rcx, [rbp+57h+var_30]
0x14000a694  xor     rcx, rsp; StackCookie
0x14000a697  call    __security_check_cookie
0x14000a69c  lea     r11, [rsp+0E0h+var_20]
0x14000a6a4  mov     rbx, [r11+40h]
0x14000a6a8  mov     rsi, [r11+48h]
0x14000a6ac  mov     rsp, r11
0x14000a6af  pop     r15
0x14000a6b1  pop     r14
0x14000a6b3  pop     r13
0x14000a6b5  pop     rdi
0x14000a6b6  pop     rbp
0x14000a6b7  retn
0x14000a6b9  lea     rcx, [r14+2FA0h]; Dpc
0x14000a6c0  mov     r8, r14; DeferredContext
0x14000a6c3  lea     rdx, VidPartitionInterceptDpcRoutine; DeferredRoutine
0x14000a6ca  call    cs:__imp_KeInitializeDpc
0x14000a6d1  nop     dword ptr [rax+rax+00h]
0x14000a6d6  mov     rcx, cs:VidDeviceExtension
0x14000a6dd  mov     rcx, [rcx+0A8h]; DeviceObject
0x14000a6e4  call    cs:__imp_IoAllocateWorkItem
0x14000a6eb  nop     dword ptr [rax+rax+00h]
0x14000a6f0  mov     [r14+2FE0h], rax
0x14000a6f7  test    rax, rax
0x14000a6fa  jnz     short loc_14000A717
0x14000a6fc  mov     esi, 0C000009Ah
0x14000a701  mov     r8d, 389h
0x14000a707  mov     rdx, r13
0x14000a70a  mov     rcx, rdi
0x14000a70d  call    VidTraceErrorInternal0
0x14000a712  jmp     loc_14000A5B5
0x14000a717  lea     rcx, [r14+5C0h]; FastMutex
0x14000a71e  mov     edx, 2CCh
0x14000a723  call    VidStatisticsDataSetup
0x14000a728  mov     esi, eax
0x14000a72a  test    eax, eax
0x14000a72c  jns     short loc_14000A744
0x14000a72e  mov     r8d, 397h
0x14000a734  mov     rdx, r13
0x14000a737  mov     rcx, rdi
0x14000a73a  call    VidTraceErrorInternal0
0x14000a73f  jmp     loc_14000A5B5
0x14000a744  mov     rax, [r14+5F8h]
0x14000a74b  mov     esi, 1
0x14000a750  mov     r8d, 72446456h
0x14000a756  mov     [rax+190h], rsi
0x14000a75d  lea     ecx, [rsi+3Fh]
0x14000a760  movups  xmm0, xmmword ptr [r15]
0x14000a764  movdqu  xmmword ptr [r14+290h], xmm0
0x14000a76d  movzx   eax, word ptr [rbx]
0x14000a770  mov     [r14+68h], ax
0x14000a775  movzx   eax, word ptr [rbx+2]
0x14000a779  mov     edx, eax
0x14000a77b  mov     [r14+6Ah], ax
0x14000a780  call    cs:__imp_ExAllocatePool2
0x14000a787  nop     dword ptr [rax+rax+00h]
0x14000a78c  mov     [r14+70h], rax
0x14000a790  test    rax, rax
0x14000a793  jnz     loc_14000A841
0x14000a799  mov     eax, cs:dword_140064110
0x14000a79f  mov     esi, 0C000009Ah
0x14000a7a4  cmp     eax, 2
0x14000a7a7  jbe     loc_14000A5B5
0x14000a7ad  mov     edx, 100h
0x14000a7b2  lea     rcx, dword_140064110
0x14000a7b9  call    _tlgKeywordOn
0x14000a7be  test    al, al
0x14000a7c0  jz      loc_14000A5B5
0x14000a7c6  lea     rdx, aVidpartitionin; "VidPartitionInitialize"
0x14000a7cd  lea     rcx, [rbp+57h+var_80]
0x14000a7d1  call    _tlgCreate1Sz_char
0x14000a7d6  mov     rdx, r13
0x14000a7d9  lea     rcx, [rbp+57h+var_70]
0x14000a7dd  call    _tlgCreate1Sz_char
0x14000a7e2  lea     rax, [rbp+57h+var_AC]
0x14000a7e6  mov     [rbp+57h+var_AC], 3C3h
0x14000a7ed  mov     [rbp+57h+var_60], rax
0x14000a7f1  lea     rdx, word_1400462E6
0x14000a7f8  movzx   eax, word ptr [r14+6Ah]
0x14000a7fd  lea     rcx, dword_140064110
0x14000a804  mov     word ptr [rbp+57h+var_B0], ax
0x14000a808  xor     r9d, r9d
0x14000a80b  lea     rax, [rbp+57h+var_B0]
0x14000a80f  mov     [rbp+57h+var_58], 4
0x14000a817  mov     [rbp+57h+var_50], rax
0x14000a81b  xor     r8d, r8d
0x14000a81e  lea     rax, [rbp+57h+var_A0]
0x14000a822  mov     [rbp+57h+var_48], 2
0x14000a82a  mov     [rsp+0E0h+var_B8], rax
0x14000a82f  mov     [rsp+0E0h+var_C0], 6
0x14000a837  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a83c  jmp     loc_14000A5B5
0x14000a841  mov     rdx, rbx; SourceString
0x14000a844  lea     rcx, [r14+68h]; DestinationString
0x14000a848  call    cs:__imp_RtlCopyUnicodeString
0x14000a84f  nop     dword ptr [rax+rax+00h]
0x14000a854  mov     edi, 72446456h
0x14000a859  mov     edx, 0BF40h
0x14000a85e  mov     r8d, edi
0x14000a861  mov     ecx, 40h ; '@'
0x14000a866  call    cs:__imp_ExAllocatePool2
0x14000a86d  nop     dword ptr [rax+rax+00h]
0x14000a872  mov     [r14+0D30h], rax
0x14000a879  test    rax, rax
0x14000a87c  jnz     short loc_14000A89D
0x14000a87e  mov     esi, 0C000009Ah
0x14000a883  mov     r8d, 3D3h
0x14000a889  lea     rcx, aVidpartitionin; "VidPartitionInitialize"
0x14000a890  mov     rdx, r13
0x14000a893  call    VidTraceErrorInternal0
0x14000a898  jmp     loc_14000A5B5
0x14000a89d  xor     r8d, r8d
0x14000a8a0  mov     rax, [r14+0D30h]
0x14000a8a7  lea     rdx, [r8+r8*2]
0x14000a8ab  shl     rdx, 6
0x14000a8af  lea     ecx, [rsi+r8]
0x14000a8b3  add     r8d, esi
0x14000a8b6  mov     dword ptr [rdx+rax+70h], 8
0x14000a8be  mov     rax, [r14+0D30h]
0x14000a8c5  mov     [rdx+rax+98h], cl
0x14000a8cc  cmp     r8d, 0FFh
0x14000a8d3  jb      short loc_14000A8A0
0x14000a8d5  mov     ebx, 10000h
0x14000a8da  mov     byte ptr [r14+0D38h], 0
0x14000a8e2  mov     edx, ebx
0x14000a8e4  mov     r8d, edi
0x14000a8e7  mov     ecx, 40h ; '@'
0x14000a8ec  call    cs:__imp_ExAllocatePool2
0x14000a8f3  nop     dword ptr [rax+rax+00h]
0x14000a8f8  lea     rdx, [r14+0D50h]
0x14000a8ff  mov     rcx, rax; void *
0x14000a902  mov     [rdx], rax
0x14000a905  test    rax, rax
0x14000a908  jnz     short loc_14000A929
0x14000a90a  mov     esi, 0C000009Ah
0x14000a90f  mov     r8d, 3EEh
0x14000a915  lea     rcx, aVidpartitionin; "VidPartitionInitialize"
0x14000a91c  mov     rdx, r13
0x14000a91f  call    VidTraceErrorInternal0
0x14000a924  jmp     loc_14000A5B5
0x14000a929  cmp     rcx, rdx
0x14000a92c  ja      short loc_14000A94C
0x14000a92e  add     rax, 0FFFFh
0x14000a934  cmp     rax, rdx
0x14000a937  jb      short loc_14000A94C
0x14000a939  xor     ecx, ecx
0x14000a93b  mov     rax, [rdx]
0x14000a93e  mov     byte ptr [rcx+rax], 0FFh
0x14000a942  add     rcx, rsi
0x14000a945  cmp     rcx, rbx
0x14000a948  jnz     short loc_14000A93B
0x14000a94a  jmp     short loc_14000A956
0x14000a94c  mov     r8, rbx; Size
0x14000a94f  mov     dl, 0FFh; Val
0x14000a951  call    memset
0x14000a956  mov     ebx, 100h
0x14000a95b  mov     r8d, edi
0x14000a95e  mov     edx, ebx
0x14000a960  mov     ecx, 40h ; '@'
0x14000a965  call    cs:__imp_ExAllocatePool2
0x14000a96c  nop     dword ptr [rax+rax+00h]
0x14000a971  lea     rdx, [r14+0D40h]
0x14000a978  mov     rcx, rax; void *
0x14000a97b  mov     [rdx], rax
0x14000a97e  test    rax, rax
0x14000a981  jnz     short loc_14000A9A2
0x14000a983  mov     esi, 0C000009Ah
0x14000a988  mov     r8d, 403h
0x14000a98e  lea     rcx, aVidpartitionin; "VidPartitionInitialize"
0x14000a995  mov     rdx, r13
0x14000a998  call    VidTraceErrorInternal0
0x14000a99d  jmp     loc_14000A5B5
0x14000a9a2  cmp     rcx, rdx
0x14000a9a5  ja      short loc_14000A9C5
0x14000a9a7  add     rax, 0FFh
0x14000a9ad  cmp     rax, rdx
0x14000a9b0  jb      short loc_14000A9C5
0x14000a9b2  xor     ecx, ecx
0x14000a9b4  mov     rax, [rdx]
0x14000a9b7  mov     byte ptr [rcx+rax], 0FFh
0x14000a9bb  add     rcx, rsi
0x14000a9be  cmp     rcx, rbx
0x14000a9c1  jnz     short loc_14000A9B4
0x14000a9c3  jmp     short loc_14000A9CF
0x14000a9c5  mov     r8, rbx; Size
0x14000a9c8  mov     dl, 0FFh; Val
0x14000a9ca  call    memset
0x14000a9cf  lea     rcx, [r14+0F58h]
0x14000a9d6  call    VidReaderCounterSetup
0x14000a9db  mov     esi, eax
0x14000a9dd  test    eax, eax
0x14000a9df  jns     short loc_14000A9FB
0x14000a9e1  mov     r8d, 411h
0x14000a9e7  lea     rcx, aVidpartitionin; "VidPartitionInitialize"
0x14000a9ee  mov     rdx, r13
0x14000a9f1  call    VidTraceErrorInternal0
0x14000a9f6  jmp     loc_14000A5B5
0x14000a9fb  mov     rcx, r14
0x14000a9fe  call    VsmmPartitionInitialize
0x14000aa03  mov     esi, eax
0x14000aa05  test    eax, eax
0x14000aa07  js      loc_14000A5B5
0x14000aa0d  xor     esi, esi
0x14000aa0f  jmp     loc_14000A68E
```

# VsmmHvMemPartSetup

- ea: `0x1400c4fd4`
- end: `0x1400c542d`
- name: `VsmmHvMemPartSetup`
- size: `1113`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update`

## callers

- `0x140083714`

## callees

- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140021e00`
- `0x140024a90`
- `0x14002f724`
- `0x1400309d0`
- `0x140030b60`
- `0x140033b00`
- `0x1400a39b0`
- `0x1400a86dc`
- `0x1400c4fd4`
- `0x1400c5dcc`
- `0x1400c6170`
- `0x1400c628c`
- `0x1400c6d18`
- `0x1400c73ac`
- `0x1400c74d8`
- `0x1400c7610`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1400c5035`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c504e`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c52f2`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c5035`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c504e`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c52f2`
- `ntoskrnl!EtwEventEnabled` at `0x1400c53df`
- `ntoskrnl!EtwEventEnabled` at `0x1400c53df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5323`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5323`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400c5116`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400c5116`
- `HAL!KeQueryPerformanceCounter` at `0x1400c50b1`
- `HAL!KeQueryPerformanceCounter` at `0x1400c539a`
- `HAL!KeQueryPerformanceCounter` at `0x1400c50b1`
- `HAL!KeQueryPerformanceCounter` at `0x1400c539a`

## pseudocode

```c
__int64 __fastcall VsmmHvMemPartSetup(int *Context)
{
  char v2; // r15
  char v3; // r12
  _DWORD *v4; // r13
  char *v5; // r14
  __int64 v6; // rdx
  int HvBootPages; // esi
  int v8; // eax
  int v9; // eax
  char v10; // cl
  int v11; // eax
  int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  LARGE_INTEGER PerformanceCounter; // rax
  bool v17; // zf
  char v19[8]; // [rsp+30h] [rbp-99h] BYREF
  char *v20; // [rsp+38h] [rbp-91h] BYREF
  int v21; // [rsp+40h] [rbp-89h]
  int v22; // [rsp+44h] [rbp-85h]
  int v23; // [rsp+48h] [rbp-81h]
  int v24; // [rsp+4Ch] [rbp-7Dh]
  GUID v25[5]; // [rsp+50h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26[2]; // [rsp+A0h] [rbp-29h] BYREF
  char **v27; // [rsp+C0h] [rbp-9h]
  __int64 v28; // [rsp+C8h] [rbp-1h]

  memset(v25, 0, sizeof(v25));
  v21 = 1319266201;
  v22 = 1243467996;
  v23 = 1462752922;
  v24 = -1644386514;
  EtwActivityIdControl(5u, &v25[1]);
  v2 = 1;
  EtwActivityIdControl(1u, &v25[2]);
  if ( (unsigned int)dword_140065110 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    tlgWriteTransfer_EtwWriteTransfer(
      (__int64)&dword_140065110,
      (unsigned __int8 *)&byte_140052D1F,
      &v25[2],
      &v25[1],
      2u,
      v26);
  v25[4].Data4[0] = 1;
  v19[0] = 0;
  *((LARGE_INTEGER *)Context + 7) = KeQueryPerformanceCounter(0);
  v3 = 1;
  v4 = VidDeviceExtension;
  v5 = (char *)VidDeviceExtension + 1640;
  v20 = (char *)VidDeviceExtension + 1640;
  VidLockAcquireShared((char *)VidDeviceExtension + 1640);
  *((_QWORD *)Context + 12) = -2;
  HvBootPages = VsmmHvMemPartpQueryHvBootPages(Context);
  if ( HvBootPages >= 0 )
  {
    if ( (int)VsmmHvMemPartpNameGetFromRegKey((PUNICODE_STRING)Context + 14) < 0
      && !RtlCreateUnicodeString((PUNICODE_STRING)Context + 14, L"\\KernelObjects\\MemoryPartitionHypervisorMetadata") )
    {
      HvBootPages = -1073741670;
      VidTraceErrorStatusInternal0(
        "VsmmHvMemPartSetup",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
        432,
        3221225626LL);
      goto LABEL_29;
    }
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 4) != 0 )
    {
      v8 = VsmmMemPartSetupViaRestore(Context);
      HvBootPages = v8;
      if ( v8 >= 0 )
      {
        v3 = 0;
LABEL_28:
        v5 = v20;
        goto LABEL_29;
      }
      if ( v8 != -1073741275 )
      {
        VidTraceErrorStatusInternal0(
          "VsmmHvMemPartSetup",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
          457,
          (unsigned int)v8);
        goto LABEL_28;
      }
      VidTraceInfoInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 465);
    }
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 4) == 0 )
      goto LABEL_19;
    v9 = VsmmPhuPartitionExists(v19);
    v10 = v19[0];
    if ( v9 < 0 )
      v10 = 1;
    if ( v10 )
    {
      HvBootPages = 0;
      VidTraceInfoInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 515);
    }
    else
    {
LABEL_19:
      v11 = VsmmHvMemPartpSetupViaOpen(Context);
      HvBootPages = v11;
      if ( v11 < 0 )
      {
        if ( v11 == -1073741772 || v11 == -1073741766 )
        {
          if ( (v4[408] & 1) != 0 )
          {
            HvBootPages = 0;
            VidTraceInfoInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 527);
          }
          else
          {
            v12 = VsmmHvMemPartpSetupViaCreate(Context);
            HvBootPages = v12;
            if ( v12 >= 0 )
              HvBootPages = 0;
            else
              VidTraceErrorStatusInternal0(
                "VsmmHvMemPartSetup",
                "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
                538,
                (unsigned int)v12);
          }
        }
        else
        {
          VidTraceErrorStatusInternal0(
            "VsmmHvMemPartSetup",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
            501,
            (unsigned int)v11);
        }
      }
    }
    goto LABEL_28;
  }
LABEL_29:
  if ( v25[4].Data4[0] )
  {
    if ( (unsigned int)dword_140065110 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      LODWORD(v20) = HvBootPages;
      v27 = &v20;
      v28 = 4;
      tlgWriteTransfer_EtwWriteTransfer(
        (__int64)&dword_140065110,
        (unsigned __int8 *)&word_140052D3E,
        &v25[2],
        0,
        3u,
        v26);
    }
    EtwActivityIdControl(2u, &v25[1]);
    v25[4].Data4[0] = 0;
  }
  if ( *((_QWORD *)Context + 53) == *((_QWORD *)Context + 54) )
  {
    v13 = (_QWORD *)*((_QWORD *)Context + 52);
    if ( v13 )
    {
      ExFreePoolWithTag(v13, 0x6D4D6456u);
      *((_QWORD *)Context + 52) = 0;
    }
  }
  else
  {
    LOBYTE(v6) = 1;
    if ( (int)VsmmHvMemPartpHotAddHvBootPages(Context, v6) < 0 )
      __int2c();
  }
  if ( HvBootPages < 0 )
  {
    VsmmHvMemPartpTeardownLocked(Context);
    v14 = *((_QWORD *)Context + 27);
    Context[8] = 5;
    v13 = *(_QWORD **)(v14 + 56);
    v13[2] = 5;
  }
  if ( v3 )
  {
    v15 = Context[8];
    if ( (v15 & 0xFFFFFFFA) != 0 || v15 == 1 )
      v2 = 0;
    LOBYTE(v13) = v2;
    VsmmHvMemPartpHvLoaderNotify(v13);
    PerformanceCounter = KeQueryPerformanceCounter((PLARGE_INTEGER)Context + 9);
    *((LARGE_INTEGER *)Context + 8) = PerformanceCounter;
    v17 = *((_QWORD *)Context + 55) == 0;
    *((_QWORD *)Context + 51) = 1000000
                              * (PerformanceCounter.QuadPart - *((_QWORD *)Context + 7))
                              / *((_QWORD *)Context + 9);
    if ( !v17 && VID_TRACE_ETW_GUID_Context && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &VID_HV_MEM_PART_REFERENCED) )
      VidTraceInt2Routine(&VID_HV_MEM_PART_REFERENCED, HvBootPages, Context[8]);
  }
  VidLockRelease(v5);
  return (unsigned int)HvBootPages;
}

```

## disassembly

```asm
0x1400c4fd4  push    rbp
0x1400c4fd6  push    rbx
0x1400c4fd7  push    rsi
0x1400c4fd8  push    rdi
0x1400c4fd9  push    r12
0x1400c4fdb  push    r13
0x1400c4fdd  push    r14
0x1400c4fdf  push    r15
0x1400c4fe1  lea     rbp, [rsp-1Fh]
0x1400c4fe6  sub     rsp, 0E8h
0x1400c4fed  mov     rax, cs:__security_cookie
0x1400c4ff4  xor     rax, rsp
0x1400c4ff7  mov     [rbp+57h+var_50], rax
0x1400c4ffb  xor     edx, edx; Val
0x1400c4ffd  mov     rdi, rcx
0x1400c5000  lea     rcx, [rbp+57h+var_D0]; void *
0x1400c5004  lea     r8d, [rdx+50h]; Size
0x1400c5008  call    memset
0x1400c500d  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400c5011  mov     [rsp+120h+var_E0], 4EA26799h
0x1400c5019  mov     ecx, 5; ControlCode
0x1400c501e  mov     [rsp+120h+var_DC], 4A1DD0DCh
0x1400c5026  mov     [rsp+120h+var_D8], 572FD69Ah
0x1400c502e  mov     [rbp+57h+var_D4], 9DFCA72Eh
0x1400c5035  call    cs:__imp_EtwActivityIdControl
0x1400c503c  nop     dword ptr [rax+rax+00h]
0x1400c5041  mov     r15d, 1
0x1400c5047  lea     rdx, [rbp+57h+var_B0]; ActivityId
0x1400c504b  mov     ecx, r15d; ControlCode
0x1400c504e  call    cs:__imp_EtwActivityIdControl
0x1400c5055  nop     dword ptr [rax+rax+00h]
0x1400c505a  mov     eax, cs:dword_140065110
0x1400c5060  cmp     eax, 5
0x1400c5063  jbe     short loc_1400C50A6
0x1400c5065  mov     edx, 100h
0x1400c506a  lea     rcx, dword_140065110
0x1400c5071  call    _tlgKeywordOn
0x1400c5076  test    al, al
0x1400c5078  jz      short loc_1400C50A6
0x1400c507a  lea     rax, [rbp+57h+var_80]
0x1400c507e  mov     [rsp+120h+var_F8], rax
0x1400c5083  lea     r9, [rbp+57h+ActivityId]
0x1400c5087  lea     r8, [rbp+57h+var_B0]
0x1400c508b  mov     [rsp+120h+var_100], 2
0x1400c5093  lea     rdx, byte_140052D1F
0x1400c509a  lea     rcx, dword_140065110
0x1400c50a1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c50a6  xor     ecx, ecx; PerformanceFrequency
0x1400c50a8  mov     [rbp+57h+var_88], r15b
0x1400c50ac  mov     [rsp+120h+var_F0], 0
0x1400c50b1  call    cs:__imp_KeQueryPerformanceCounter
0x1400c50b8  nop     dword ptr [rax+rax+00h]
0x1400c50bd  mov     [rdi+38h], rax
0x1400c50c1  mov     r12b, r15b
0x1400c50c4  mov     r13, cs:VidDeviceExtension
0x1400c50cb  lea     r14, [r13+668h]
0x1400c50d2  mov     rcx, r14
0x1400c50d5  mov     [rsp+120h+var_E8], r14
0x1400c50da  call    VidLockAcquireShared
0x1400c50df  mov     rcx, rdi
0x1400c50e2  mov     qword ptr [rdi+60h], 0FFFFFFFFFFFFFFFEh
0x1400c50ea  call    VsmmHvMemPartpQueryHvBootPages
0x1400c50ef  mov     esi, eax
0x1400c50f1  test    eax, eax
0x1400c50f3  js      loc_1400C5283
0x1400c50f9  lea     rbx, [rdi+0E0h]
0x1400c5100  mov     rcx, rbx; StringOut
0x1400c5103  call    VsmmHvMemPartpNameGetFromRegKey
0x1400c5108  test    eax, eax
0x1400c510a  jns     short loc_1400C514C
0x1400c510c  lea     rdx, aKernelobjectsM_0; "\\KernelObjects\\MemoryPartitionHypervi"...
0x1400c5113  mov     rcx, rbx; DestinationString
0x1400c5116  call    cs:__imp_RtlCreateUnicodeString
0x1400c511d  nop     dword ptr [rax+rax+00h]
0x1400c5122  test    al, al
0x1400c5124  jnz     short loc_1400C514C
0x1400c5126  mov     esi, 0C000009Ah
0x1400c512b  mov     r9d, esi
0x1400c512e  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c5135  mov     r8d, 1B0h
0x1400c513b  lea     rcx, aVsmmhvmemparts; "VsmmHvMemPartSetup"
0x1400c5142  call    VidTraceErrorStatusInternal0
0x1400c5147  jmp     loc_1400C5283
0x1400c514c  mov     rax, cs:VidDeviceExtension
0x1400c5153  lea     rbx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c515a  lea     r14, aVsmmhvmemparts; "VsmmHvMemPartSetup"
0x1400c5161  mov     eax, [rax+288h]
0x1400c5167  test    al, 4
0x1400c5169  jz      short loc_1400C51C6
0x1400c516b  lea     r8, VsmmHvMemPartpRestoreWorkItemRoutine
0x1400c5172  mov     rcx, rdi; Context
0x1400c5175  lea     rdx, [rsp+120h+var_E0]
0x1400c517a  call    VsmmMemPartSetupViaRestore
0x1400c517f  mov     esi, eax
0x1400c5181  test    eax, eax
0x1400c5183  js      short loc_1400C518D
0x1400c5185  xor     r12b, r12b
0x1400c5188  jmp     loc_1400C527E
0x1400c518d  cmp     eax, 0C0000225h
0x1400c5192  jz      short loc_1400C51B5
0x1400c5194  mov     r9d, eax
0x1400c5197  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c519e  mov     r8d, 1C9h
0x1400c51a4  lea     rcx, aVsmmhvmemparts; "VsmmHvMemPartSetup"
0x1400c51ab  call    VidTraceErrorStatusInternal0
0x1400c51b0  jmp     loc_1400C527E
0x1400c51b5  mov     r8d, 1D1h
0x1400c51bb  mov     rdx, rbx
0x1400c51be  mov     rcx, r14
0x1400c51c1  call    VidTraceInfoInternal0
0x1400c51c6  mov     rax, cs:VidDeviceExtension
0x1400c51cd  mov     eax, [rax+288h]
0x1400c51d3  test    al, 4
0x1400c51d5  jz      short loc_1400C5205
0x1400c51d7  lea     rcx, [rsp+120h+var_F0]
0x1400c51dc  call    VsmmPhuPartitionExists
0x1400c51e1  movzx   ecx, [rsp+120h+var_F0]
0x1400c51e6  test    eax, eax
0x1400c51e8  cmovs   ecx, r15d
0x1400c51ec  test    cl, cl
0x1400c51ee  jz      short loc_1400C5205
0x1400c51f0  xor     esi, esi
0x1400c51f2  mov     r8d, 203h
0x1400c51f8  mov     rdx, rbx
0x1400c51fb  mov     rcx, r14
0x1400c51fe  call    VidTraceInfoInternal0
0x1400c5203  jmp     short loc_1400C527E
0x1400c5205  mov     rcx, rdi
0x1400c5208  call    VsmmHvMemPartpSetupViaOpen
0x1400c520d  mov     esi, eax
0x1400c520f  test    eax, eax
0x1400c5211  jns     short loc_1400C527E
0x1400c5213  cmp     eax, 0C0000034h
0x1400c5218  jz      short loc_1400C5237
0x1400c521a  cmp     eax, 0C000003Ah
0x1400c521f  jz      short loc_1400C5237
0x1400c5221  mov     r9d, eax
0x1400c5224  mov     r8d, 1F5h
0x1400c522a  mov     rdx, rbx
0x1400c522d  mov     rcx, r14
0x1400c5230  call    VidTraceErrorStatusInternal0
0x1400c5235  jmp     short loc_1400C527E
0x1400c5237  mov     eax, [r13+660h]
0x1400c523e  test    r15b, al
0x1400c5241  jz      short loc_1400C5258
0x1400c5243  xor     esi, esi
0x1400c5245  mov     r8d, 20Fh
0x1400c524b  mov     rdx, rbx
0x1400c524e  mov     rcx, r14
0x1400c5251  call    VidTraceInfoInternal0
0x1400c5256  jmp     short loc_1400C527E
0x1400c5258  mov     rcx, rdi
0x1400c525b  call    VsmmHvMemPartpSetupViaCreate
0x1400c5260  mov     esi, eax
0x1400c5262  test    eax, eax
0x1400c5264  jns     short loc_1400C527C
0x1400c5266  mov     r9d, eax
0x1400c5269  mov     r8d, 21Ah
0x1400c526f  mov     rdx, rbx
0x1400c5272  mov     rcx, r14
0x1400c5275  call    VidTraceErrorStatusInternal0
0x1400c527a  jmp     short loc_1400C527E
0x1400c527c  xor     esi, esi
0x1400c527e  mov     r14, [rsp+120h+var_E8]
0x1400c5283  cmp     [rbp+57h+var_88], 0
0x1400c5287  jz      short loc_1400C5302
0x1400c5289  mov     eax, cs:dword_140065110
0x1400c528f  cmp     eax, 5
0x1400c5292  jbe     short loc_1400C52E9
0x1400c5294  mov     edx, 100h
0x1400c5299  lea     rcx, dword_140065110
0x1400c52a0  call    _tlgKeywordOn
0x1400c52a5  test    al, al
0x1400c52a7  jz      short loc_1400C52E9
0x1400c52a9  lea     rax, [rsp+120h+var_E8]
0x1400c52ae  mov     dword ptr [rsp+120h+var_E8], esi
0x1400c52b2  mov     [rbp+57h+var_60], rax
0x1400c52b6  lea     r8, [rbp+57h+var_B0]
0x1400c52ba  lea     rax, [rbp+57h+var_80]
0x1400c52be  mov     [rbp+57h+var_58], 4
0x1400c52c6  mov     [rsp+120h+var_F8], rax
0x1400c52cb  lea     rdx, word_140052D3E
0x1400c52d2  xor     r9d, r9d
0x1400c52d5  mov     [rsp+120h+var_100], 3
0x1400c52dd  lea     rcx, dword_140065110
0x1400c52e4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c52e9  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400c52ed  mov     ecx, 2; ControlCode
0x1400c52f2  call    cs:__imp_EtwActivityIdControl
0x1400c52f9  nop     dword ptr [rax+rax+00h]
0x1400c52fe  mov     [rbp+57h+var_88], 0
0x1400c5302  mov     rax, [rdi+1B0h]
0x1400c5309  cmp     [rdi+1A8h], rax
0x1400c5310  jnz     short loc_1400C533C
0x1400c5312  mov     rcx, [rdi+1A0h]; P
0x1400c5319  test    rcx, rcx
0x1400c531c  jz      short loc_1400C534D
0x1400c531e  mov     edx, 6D4D6456h; Tag
0x1400c5323  call    cs:__imp_ExFreePoolWithTag
0x1400c532a  nop     dword ptr [rax+rax+00h]
0x1400c532f  mov     qword ptr [rdi+1A0h], 0
0x1400c533a  jmp     short loc_1400C534D
0x1400c533c  mov     dl, r15b
0x1400c533f  mov     rcx, rdi
0x1400c5342  call    VsmmHvMemPartpHotAddHvBootPages
0x1400c5347  test    eax, eax
0x1400c5349  jns     short loc_1400C534D
0x1400c534b  int     2Ch; Windows NT - assertion failure
0x1400c534d  test    esi, esi
0x1400c534f  jns     short loc_1400C5373
0x1400c5351  mov     rcx, rdi
0x1400c5354  call    VsmmHvMemPartpTeardownLocked
0x1400c5359  mov     rax, [rdi+0D8h]
0x1400c5360  mov     dword ptr [rdi+20h], 5
0x1400c5367  mov     rcx, [rax+38h]
0x1400c536b  mov     qword ptr [rcx+10h], 5
0x1400c5373  test    r12b, r12b
0x1400c5376  jz      loc_1400C5402
0x1400c537c  mov     eax, [rdi+20h]
0x1400c537f  test    eax, 0FFFFFFFAh
0x1400c5384  jnz     short loc_1400C538B
0x1400c5386  cmp     eax, r15d
0x1400c5389  jnz     short loc_1400C538E
0x1400c538b  xor     r15b, r15b
0x1400c538e  mov     cl, r15b
0x1400c5391  call    VsmmHvMemPartpHvLoaderNotify
0x1400c5396  lea     rcx, [rdi+48h]; PerformanceFrequency
0x1400c539a  call    cs:__imp_KeQueryPerformanceCounter
0x1400c53a1  nop     dword ptr [rax+rax+00h]
0x1400c53a6  mov     [rdi+40h], rax
0x1400c53aa  sub     rax, [rdi+38h]
0x1400c53ae  imul    rax, 0F4240h
0x1400c53b5  cqo
0x1400c53b7  idiv    qword ptr [rdi+48h]
0x1400c53bb  cmp     qword ptr [rdi+1B8h], 0
0x1400c53c3  mov     [rdi+198h], rax
0x1400c53ca  jz      short loc_1400C5402
0x1400c53cc  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x1400c53d3  test    rcx, rcx
0x1400c53d6  jz      short loc_1400C5402
0x1400c53d8  lea     rdx, VID_HV_MEM_PART_REFERENCED; EventDescriptor
0x1400c53df  call    cs:__imp_EtwEventEnabled
0x1400c53e6  nop     dword ptr [rax+rax+00h]
0x1400c53eb  test    al, al
0x1400c53ed  jz      short loc_1400C5402
0x1400c53ef  movsxd  r8, dword ptr [rdi+20h]
0x1400c53f3  lea     rcx, VID_HV_MEM_PART_REFERENCED; EventDescriptor
0x1400c53fa  movsxd  rdx, esi
0x1400c53fd  call    VidTraceInt2Routine
0x1400c5402  mov     rcx, r14
0x1400c5405  call    VidLockRelease
0x1400c540a  mov     eax, esi
0x1400c540c  mov     rcx, [rbp+57h+var_50]
0x1400c5410  xor     rcx, rsp; StackCookie
0x1400c5413  call    __security_check_cookie
0x1400c5418  add     rsp, 0E8h
0x1400c541f  pop     r15
0x1400c5421  pop     r14
0x1400c5423  pop     r13
0x1400c5425  pop     r12
0x1400c5427  pop     rdi
0x1400c5428  pop     rsi
0x1400c5429  pop     rbx
0x1400c542a  pop     rbp
0x1400c542b  retn
```

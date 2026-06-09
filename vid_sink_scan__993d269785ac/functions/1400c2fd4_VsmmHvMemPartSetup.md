# VsmmHvMemPartSetup

- ea: `0x1400c2fd4`
- end: `0x1400c342d`
- name: `VsmmHvMemPartSetup`
- size: `1113`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update`

## callers

- `0x14008279c`

## callees

- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140021800`
- `0x1400248f0`
- `0x14002f524`
- `0x1400307d0`
- `0x140030960`
- `0x140033900`
- `0x1400a1f60`
- `0x1400a6974`
- `0x1400c2fd4`
- `0x1400c3dcc`
- `0x1400c4170`
- `0x1400c428c`
- `0x1400c4d18`
- `0x1400c53ac`
- `0x1400c54d8`
- `0x1400c5610`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1400c33df`
- `ntoskrnl!EtwEventEnabled` at `0x1400c33df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3323`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3323`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400c3116`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400c3116`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c3035`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c304e`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c32f2`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c3035`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c304e`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c32f2`
- `HAL!KeQueryPerformanceCounter` at `0x1400c30b1`
- `HAL!KeQueryPerformanceCounter` at `0x1400c339a`
- `HAL!KeQueryPerformanceCounter` at `0x1400c30b1`
- `HAL!KeQueryPerformanceCounter` at `0x1400c339a`

## pseudocode

```c
__int64 __fastcall VsmmHvMemPartSetup(int *Context)
{
  char v2; // r15
  char v3; // r12
  _DWORD *v4; // r13
  char *v5; // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  int HvBootPages; // esi
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  int v12; // eax
  char v13; // cl
  int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  LARGE_INTEGER PerformanceCounter; // rax
  bool v19; // zf
  char v21[8]; // [rsp+30h] [rbp-99h] BYREF
  char *v22; // [rsp+38h] [rbp-91h] BYREF
  _DWORD v23[24]; // [rsp+40h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24[2]; // [rsp+A0h] [rbp-29h] BYREF
  char **v25; // [rsp+C0h] [rbp-9h]
  __int64 v26; // [rsp+C8h] [rbp-1h]

  memset(&v23[4], 0, 0x50u);
  v23[0] = 1319266201;
  v23[1] = 1243467996;
  v23[2] = 1462752922;
  v23[3] = -1644386514;
  EtwActivityIdControl(5u, (LPGUID)&v23[8]);
  v2 = 1;
  EtwActivityIdControl(1u, (LPGUID)&v23[12]);
  if ( (unsigned int)dword_140064110 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    tlgWriteTransfer_EtwWriteTransfer(
      (__int64)&dword_140064110,
      (unsigned __int8 *)&byte_14005285F,
      (const GUID *)&v23[12],
      (const GUID *)&v23[8],
      2u,
      v24);
  LOBYTE(v23[22]) = 1;
  v21[0] = 0;
  *((LARGE_INTEGER *)Context + 7) = KeQueryPerformanceCounter(0);
  v3 = 1;
  v4 = VidDeviceExtension;
  v5 = (char *)VidDeviceExtension + 1640;
  v22 = (char *)VidDeviceExtension + 1640;
  VidLockAcquireShared((char *)VidDeviceExtension + 1640, v6, v7);
  *((_QWORD *)Context + 12) = -2;
  HvBootPages = VsmmHvMemPartpQueryHvBootPages((__int64)Context);
  if ( HvBootPages >= 0 )
  {
    if ( (int)VsmmHvMemPartpNameGetFromRegKey((PUNICODE_STRING)Context + 14) < 0
      && !RtlCreateUnicodeString((PUNICODE_STRING)Context + 14, L"\\KernelObjects\\MemoryPartitionHypervisorMetadata") )
    {
      HvBootPages = -1073741670;
      VidTraceErrorStatusInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 432);
      goto LABEL_29;
    }
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 4) != 0 )
    {
      v11 = VsmmMemPartSetupViaRestore(
              (char *)Context,
              (__int64)v23,
              (IO_WORKITEM_ROUTINE_EX *)VsmmHvMemPartpRestoreWorkItemRoutine);
      HvBootPages = v11;
      if ( v11 >= 0 )
      {
        v3 = 0;
LABEL_28:
        v5 = v22;
        goto LABEL_29;
      }
      if ( v11 != -1073741275 )
      {
        VidTraceErrorStatusInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 457);
        goto LABEL_28;
      }
      VidTraceInfoInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 465);
    }
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 4) == 0 )
      goto LABEL_19;
    v12 = VsmmPhuPartitionExists(v21, v9, v10);
    v13 = v21[0];
    if ( v12 < 0 )
      v13 = 1;
    if ( v13 )
    {
      HvBootPages = 0;
      VidTraceInfoInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 515);
    }
    else
    {
LABEL_19:
      v14 = VsmmHvMemPartpSetupViaOpen(Context);
      HvBootPages = v14;
      if ( v14 < 0 )
      {
        if ( v14 == -1073741772 || v14 == -1073741766 )
        {
          if ( (v4[408] & 1) != 0 )
          {
            HvBootPages = 0;
            VidTraceInfoInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 527);
          }
          else
          {
            HvBootPages = VsmmHvMemPartpSetupViaCreate(Context);
            if ( HvBootPages >= 0 )
              HvBootPages = 0;
            else
              VidTraceErrorStatusInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 538);
          }
        }
        else
        {
          VidTraceErrorStatusInternal0("VsmmHvMemPartSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 501);
        }
      }
    }
    goto LABEL_28;
  }
LABEL_29:
  if ( LOBYTE(v23[22]) )
  {
    if ( (unsigned int)dword_140064110 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      LODWORD(v22) = HvBootPages;
      v25 = &v22;
      v26 = 4;
      tlgWriteTransfer_EtwWriteTransfer(
        (__int64)&dword_140064110,
        (unsigned __int8 *)&byte_140052837,
        (const GUID *)&v23[12],
        0,
        3u,
        v24);
    }
    EtwActivityIdControl(2u, (LPGUID)&v23[8]);
    LOBYTE(v23[22]) = 0;
  }
  if ( *((_QWORD *)Context + 53) == *((_QWORD *)Context + 54) )
  {
    v15 = (_QWORD *)*((_QWORD *)Context + 52);
    if ( v15 )
    {
      ExFreePoolWithTag(v15, 0x6D4D6456u);
      *((_QWORD *)Context + 52) = 0;
    }
  }
  else if ( (int)VsmmHvMemPartpHotAddHvBootPages((__int64)Context, 1) < 0 )
  {
    __int2c();
  }
  if ( HvBootPages < 0 )
  {
    VsmmHvMemPartpTeardownLocked(Context);
    v16 = *((_QWORD *)Context + 27);
    Context[8] = 5;
    v15 = *(_QWORD **)(v16 + 56);
    v15[2] = 5;
  }
  if ( v3 )
  {
    v17 = Context[8];
    if ( (v17 & 0xFFFFFFFA) != 0 || v17 == 1 )
      v2 = 0;
    LOBYTE(v15) = v2;
    VsmmHvMemPartpHvLoaderNotify(v15);
    PerformanceCounter = KeQueryPerformanceCounter((PLARGE_INTEGER)Context + 9);
    *((LARGE_INTEGER *)Context + 8) = PerformanceCounter;
    v19 = *((_QWORD *)Context + 55) == 0;
    *((_QWORD *)Context + 51) = 1000000
                              * (PerformanceCounter.QuadPart - *((_QWORD *)Context + 7))
                              / *((_QWORD *)Context + 9);
    if ( !v19 && VID_TRACE_ETW_GUID_Context && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &VID_HV_MEM_PART_REFERENCED) )
      VidTraceInt2Routine(&VID_HV_MEM_PART_REFERENCED, HvBootPages, Context[8]);
  }
  VidLockRelease(v5);
  return (unsigned int)HvBootPages;
}

```

## disassembly

```asm
0x1400c2fd4  push    rbp
0x1400c2fd6  push    rbx
0x1400c2fd7  push    rsi
0x1400c2fd8  push    rdi
0x1400c2fd9  push    r12
0x1400c2fdb  push    r13
0x1400c2fdd  push    r14
0x1400c2fdf  push    r15
0x1400c2fe1  lea     rbp, [rsp-1Fh]
0x1400c2fe6  sub     rsp, 0E8h
0x1400c2fed  mov     rax, cs:__security_cookie
0x1400c2ff4  xor     rax, rsp
0x1400c2ff7  mov     [rbp+57h+var_50], rax
0x1400c2ffb  xor     edx, edx; Val
0x1400c2ffd  mov     rdi, rcx
0x1400c3000  lea     rcx, [rbp+57h+var_D0]; void *
0x1400c3004  lea     r8d, [rdx+50h]; Size
0x1400c3008  call    memset
0x1400c300d  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400c3011  mov     [rsp+120h+var_E0], 4EA26799h
0x1400c3019  mov     ecx, 5; ControlCode
0x1400c301e  mov     [rsp+120h+var_DC], 4A1DD0DCh
0x1400c3026  mov     [rsp+120h+var_D8], 572FD69Ah
0x1400c302e  mov     [rbp+57h+var_D4], 9DFCA72Eh
0x1400c3035  call    cs:__imp_EtwActivityIdControl
0x1400c303c  nop     dword ptr [rax+rax+00h]
0x1400c3041  mov     r15d, 1
0x1400c3047  lea     rdx, [rbp+57h+var_B0]; ActivityId
0x1400c304b  mov     ecx, r15d; ControlCode
0x1400c304e  call    cs:__imp_EtwActivityIdControl
0x1400c3055  nop     dword ptr [rax+rax+00h]
0x1400c305a  mov     eax, cs:dword_140064110
0x1400c3060  cmp     eax, 5
0x1400c3063  jbe     short loc_1400C30A6
0x1400c3065  mov     edx, 100h
0x1400c306a  lea     rcx, dword_140064110
0x1400c3071  call    _tlgKeywordOn
0x1400c3076  test    al, al
0x1400c3078  jz      short loc_1400C30A6
0x1400c307a  lea     rax, [rbp+57h+var_80]
0x1400c307e  mov     [rsp+120h+var_F8], rax
0x1400c3083  lea     r9, [rbp+57h+ActivityId]
0x1400c3087  lea     r8, [rbp+57h+var_B0]
0x1400c308b  mov     [rsp+120h+var_100], 2
0x1400c3093  lea     rdx, byte_14005285F
0x1400c309a  lea     rcx, dword_140064110
0x1400c30a1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c30a6  xor     ecx, ecx; PerformanceFrequency
0x1400c30a8  mov     [rbp+57h+var_88], r15b
0x1400c30ac  mov     [rsp+120h+var_F0], 0
0x1400c30b1  call    cs:__imp_KeQueryPerformanceCounter
0x1400c30b8  nop     dword ptr [rax+rax+00h]
0x1400c30bd  mov     [rdi+38h], rax
0x1400c30c1  mov     r12b, r15b
0x1400c30c4  mov     r13, cs:VidDeviceExtension
0x1400c30cb  lea     r14, [r13+668h]
0x1400c30d2  mov     rcx, r14
0x1400c30d5  mov     [rsp+120h+var_E8], r14
0x1400c30da  call    VidLockAcquireShared
0x1400c30df  mov     rcx, rdi
0x1400c30e2  mov     qword ptr [rdi+60h], 0FFFFFFFFFFFFFFFEh
0x1400c30ea  call    VsmmHvMemPartpQueryHvBootPages
0x1400c30ef  mov     esi, eax
0x1400c30f1  test    eax, eax
0x1400c30f3  js      loc_1400C3283
0x1400c30f9  lea     rbx, [rdi+0E0h]
0x1400c3100  mov     rcx, rbx; StringOut
0x1400c3103  call    VsmmHvMemPartpNameGetFromRegKey
0x1400c3108  test    eax, eax
0x1400c310a  jns     short loc_1400C314C
0x1400c310c  lea     rdx, aKernelobjectsM_0; "\\KernelObjects\\MemoryPartitionHypervi"...
0x1400c3113  mov     rcx, rbx; DestinationString
0x1400c3116  call    cs:__imp_RtlCreateUnicodeString
0x1400c311d  nop     dword ptr [rax+rax+00h]
0x1400c3122  test    al, al
0x1400c3124  jnz     short loc_1400C314C
0x1400c3126  mov     esi, 0C000009Ah
0x1400c312b  mov     r9d, esi
0x1400c312e  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c3135  mov     r8d, 1B0h
0x1400c313b  lea     rcx, aVsmmhvmemparts; "VsmmHvMemPartSetup"
0x1400c3142  call    VidTraceErrorStatusInternal0
0x1400c3147  jmp     loc_1400C3283
0x1400c314c  mov     rax, cs:VidDeviceExtension
0x1400c3153  lea     rbx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c315a  lea     r14, aVsmmhvmemparts; "VsmmHvMemPartSetup"
0x1400c3161  mov     eax, [rax+288h]
0x1400c3167  test    al, 4
0x1400c3169  jz      short loc_1400C31C6
0x1400c316b  lea     r8, VsmmHvMemPartpRestoreWorkItemRoutine
0x1400c3172  mov     rcx, rdi; Context
0x1400c3175  lea     rdx, [rsp+120h+var_E0]
0x1400c317a  call    VsmmMemPartSetupViaRestore
0x1400c317f  mov     esi, eax
0x1400c3181  test    eax, eax
0x1400c3183  js      short loc_1400C318D
0x1400c3185  xor     r12b, r12b
0x1400c3188  jmp     loc_1400C327E
0x1400c318d  cmp     eax, 0C0000225h
0x1400c3192  jz      short loc_1400C31B5
0x1400c3194  mov     r9d, eax
0x1400c3197  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c319e  mov     r8d, 1C9h
0x1400c31a4  lea     rcx, aVsmmhvmemparts; "VsmmHvMemPartSetup"
0x1400c31ab  call    VidTraceErrorStatusInternal0
0x1400c31b0  jmp     loc_1400C327E
0x1400c31b5  mov     r8d, 1D1h
0x1400c31bb  mov     rdx, rbx
0x1400c31be  mov     rcx, r14
0x1400c31c1  call    VidTraceInfoInternal0
0x1400c31c6  mov     rax, cs:VidDeviceExtension
0x1400c31cd  mov     eax, [rax+288h]
0x1400c31d3  test    al, 4
0x1400c31d5  jz      short loc_1400C3205
0x1400c31d7  lea     rcx, [rsp+120h+var_F0]
0x1400c31dc  call    VsmmPhuPartitionExists
0x1400c31e1  movzx   ecx, [rsp+120h+var_F0]
0x1400c31e6  test    eax, eax
0x1400c31e8  cmovs   ecx, r15d
0x1400c31ec  test    cl, cl
0x1400c31ee  jz      short loc_1400C3205
0x1400c31f0  xor     esi, esi
0x1400c31f2  mov     r8d, 203h
0x1400c31f8  mov     rdx, rbx
0x1400c31fb  mov     rcx, r14
0x1400c31fe  call    VidTraceInfoInternal0
0x1400c3203  jmp     short loc_1400C327E
0x1400c3205  mov     rcx, rdi
0x1400c3208  call    VsmmHvMemPartpSetupViaOpen
0x1400c320d  mov     esi, eax
0x1400c320f  test    eax, eax
0x1400c3211  jns     short loc_1400C327E
0x1400c3213  cmp     eax, 0C0000034h
0x1400c3218  jz      short loc_1400C3237
0x1400c321a  cmp     eax, 0C000003Ah
0x1400c321f  jz      short loc_1400C3237
0x1400c3221  mov     r9d, eax
0x1400c3224  mov     r8d, 1F5h
0x1400c322a  mov     rdx, rbx
0x1400c322d  mov     rcx, r14
0x1400c3230  call    VidTraceErrorStatusInternal0
0x1400c3235  jmp     short loc_1400C327E
0x1400c3237  mov     eax, [r13+660h]
0x1400c323e  test    r15b, al
0x1400c3241  jz      short loc_1400C3258
0x1400c3243  xor     esi, esi
0x1400c3245  mov     r8d, 20Fh
0x1400c324b  mov     rdx, rbx
0x1400c324e  mov     rcx, r14
0x1400c3251  call    VidTraceInfoInternal0
0x1400c3256  jmp     short loc_1400C327E
0x1400c3258  mov     rcx, rdi
0x1400c325b  call    VsmmHvMemPartpSetupViaCreate
0x1400c3260  mov     esi, eax
0x1400c3262  test    eax, eax
0x1400c3264  jns     short loc_1400C327C
0x1400c3266  mov     r9d, eax
0x1400c3269  mov     r8d, 21Ah
0x1400c326f  mov     rdx, rbx
0x1400c3272  mov     rcx, r14
0x1400c3275  call    VidTraceErrorStatusInternal0
0x1400c327a  jmp     short loc_1400C327E
0x1400c327c  xor     esi, esi
0x1400c327e  mov     r14, [rsp+120h+var_E8]
0x1400c3283  cmp     [rbp+57h+var_88], 0
0x1400c3287  jz      short loc_1400C3302
0x1400c3289  mov     eax, cs:dword_140064110
0x1400c328f  cmp     eax, 5
0x1400c3292  jbe     short loc_1400C32E9
0x1400c3294  mov     edx, 100h
0x1400c3299  lea     rcx, dword_140064110
0x1400c32a0  call    _tlgKeywordOn
0x1400c32a5  test    al, al
0x1400c32a7  jz      short loc_1400C32E9
0x1400c32a9  lea     rax, [rsp+120h+var_E8]
0x1400c32ae  mov     dword ptr [rsp+120h+var_E8], esi
0x1400c32b2  mov     [rbp+57h+var_60], rax
0x1400c32b6  lea     r8, [rbp+57h+var_B0]
0x1400c32ba  lea     rax, [rbp+57h+var_80]
0x1400c32be  mov     [rbp+57h+var_58], 4
0x1400c32c6  mov     [rsp+120h+var_F8], rax
0x1400c32cb  lea     rdx, byte_140052837
0x1400c32d2  xor     r9d, r9d
0x1400c32d5  mov     [rsp+120h+var_100], 3
0x1400c32dd  lea     rcx, dword_140064110
0x1400c32e4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c32e9  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400c32ed  mov     ecx, 2; ControlCode
0x1400c32f2  call    cs:__imp_EtwActivityIdControl
0x1400c32f9  nop     dword ptr [rax+rax+00h]
0x1400c32fe  mov     [rbp+57h+var_88], 0
0x1400c3302  mov     rax, [rdi+1B0h]
0x1400c3309  cmp     [rdi+1A8h], rax
0x1400c3310  jnz     short loc_1400C333C
0x1400c3312  mov     rcx, [rdi+1A0h]; P
0x1400c3319  test    rcx, rcx
0x1400c331c  jz      short loc_1400C334D
0x1400c331e  mov     edx, 6D4D6456h; Tag
0x1400c3323  call    cs:__imp_ExFreePoolWithTag
0x1400c332a  nop     dword ptr [rax+rax+00h]
0x1400c332f  mov     qword ptr [rdi+1A0h], 0
0x1400c333a  jmp     short loc_1400C334D
0x1400c333c  mov     dl, r15b
0x1400c333f  mov     rcx, rdi
0x1400c3342  call    VsmmHvMemPartpHotAddHvBootPages
0x1400c3347  test    eax, eax
0x1400c3349  jns     short loc_1400C334D
0x1400c334b  int     2Ch; Windows NT - assertion failure
0x1400c334d  test    esi, esi
0x1400c334f  jns     short loc_1400C3373
0x1400c3351  mov     rcx, rdi
0x1400c3354  call    VsmmHvMemPartpTeardownLocked
0x1400c3359  mov     rax, [rdi+0D8h]
0x1400c3360  mov     dword ptr [rdi+20h], 5
0x1400c3367  mov     rcx, [rax+38h]
0x1400c336b  mov     qword ptr [rcx+10h], 5
0x1400c3373  test    r12b, r12b
0x1400c3376  jz      loc_1400C3402
0x1400c337c  mov     eax, [rdi+20h]
0x1400c337f  test    eax, 0FFFFFFFAh
0x1400c3384  jnz     short loc_1400C338B
0x1400c3386  cmp     eax, r15d
0x1400c3389  jnz     short loc_1400C338E
0x1400c338b  xor     r15b, r15b
0x1400c338e  mov     cl, r15b
0x1400c3391  call    VsmmHvMemPartpHvLoaderNotify
0x1400c3396  lea     rcx, [rdi+48h]; PerformanceFrequency
0x1400c339a  call    cs:__imp_KeQueryPerformanceCounter
0x1400c33a1  nop     dword ptr [rax+rax+00h]
0x1400c33a6  mov     [rdi+40h], rax
0x1400c33aa  sub     rax, [rdi+38h]
0x1400c33ae  imul    rax, 0F4240h
0x1400c33b5  cqo
0x1400c33b7  idiv    qword ptr [rdi+48h]
0x1400c33bb  cmp     qword ptr [rdi+1B8h], 0
0x1400c33c3  mov     [rdi+198h], rax
0x1400c33ca  jz      short loc_1400C3402
0x1400c33cc  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x1400c33d3  test    rcx, rcx
0x1400c33d6  jz      short loc_1400C3402
0x1400c33d8  lea     rdx, VID_HV_MEM_PART_REFERENCED; EventDescriptor
0x1400c33df  call    cs:__imp_EtwEventEnabled
0x1400c33e6  nop     dword ptr [rax+rax+00h]
0x1400c33eb  test    al, al
0x1400c33ed  jz      short loc_1400C3402
0x1400c33ef  movsxd  r8, dword ptr [rdi+20h]
0x1400c33f3  lea     rcx, VID_HV_MEM_PART_REFERENCED; EventDescriptor
0x1400c33fa  movsxd  rdx, esi
0x1400c33fd  call    VidTraceInt2Routine
0x1400c3402  mov     rcx, r14
0x1400c3405  call    VidLockRelease
0x1400c340a  mov     eax, esi
0x1400c340c  mov     rcx, [rbp+57h+var_50]
0x1400c3410  xor     rcx, rsp; StackCookie
0x1400c3413  call    __security_check_cookie
0x1400c3418  add     rsp, 0E8h
0x1400c341f  pop     r15
0x1400c3421  pop     r14
0x1400c3423  pop     r13
0x1400c3425  pop     r12
0x1400c3427  pop     rdi
0x1400c3428  pop     rsi
0x1400c3429  pop     rbx
0x1400c342a  pop     rbp
0x1400c342b  retn
```

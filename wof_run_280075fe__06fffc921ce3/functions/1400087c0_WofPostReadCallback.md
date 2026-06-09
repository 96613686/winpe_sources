# WofPostReadCallback

- ea: `0x1400087c0`
- end: `0x140008d2a`
- name: `WofPostReadCallback`
- size: `1386`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1400087c0`
- `0x14000ba78`
- `0x14000dc88`
- `0x14000e3dc`
- `0x14000e9d8`
- `0x140011640`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000897a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000897a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140008816`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140008816`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008cd8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008cd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000883c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000883c`
- `FLTMGR!FltLockUserBuffer` at `0x1400089d1`
- `FLTMGR!FltLockUserBuffer` at `0x1400089d1`
- `FLTMGR!FltGetStreamContext` at `0x140008855`
- `FLTMGR!FltGetStreamContext` at `0x140008855`
- `FLTMGR!FltReleaseContext` at `0x140008c84`
- `FLTMGR!FltReleaseContext` at `0x140008c84`

## string_xrefs

- `0x140008a65`: `cached`
- `0x140008a5a`: `noncached`

## pseudocode

```c
__int64 __fastcall WofPostReadCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // rsi
  char v6; // di
  struct _EX_RUNDOWN_REF *v7; // rbp
  __int64 *v9; // rdx
  LARGE_INTEGER ByteOffset; // rbx
  struct _MDL *MdlAddress; // rcx
  PVOID MappedSystemVa; // r12
  int v13; // r12d
  int v14; // edx
  int v15; // edx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  const char *v17; // rax
  unsigned int v18; // edx
  __int64 v19; // r10
  int v20; // edx
  int BugCheckOnFailure; // [rsp+20h] [rbp-98h]
  int Priority; // [rsp+28h] [rbp-90h]
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-50h] BYREF
  __int64 v24; // [rsp+70h] [rbp-48h] BYREF
  ULONG_PTR v25; // [rsp+78h] [rbp-40h] BYREF
  ULONG IrpFlags; // [rsp+C0h] [rbp+8h]
  unsigned int Information; // [rsp+D0h] [rbp+18h]

  v3 = a3 & 0xFFFFFFFFFFFFFFFCuLL;
  Context = 0;
  v24 = 0;
  v25 = 0;
  v6 = a3 & 2;
  if ( (a3 & 2) != 0 )
    v7 = *(struct _EX_RUNDOWN_REF **)v3;
  else
    v7 = (struct _EX_RUNDOWN_REF *)(a3 & 0xFFFFFFFFFFFFFFFCuLL);
  if ( CallbackData->IoStatus.Status < 0 || (a3 & 1) != 0 )
  {
    if ( v6 )
    {
      (*((void (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * *(unsigned int *)(v3 + 8) + 31))(*(_QWORD *)(v3 + 16));
      ExFreePoolWithTag((PVOID)v3, 0);
    }
    if ( v7 )
      goto LABEL_7;
    return 0;
  }
  KeEnterCriticalRegion();
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    IrpFlags = CallbackData->Iopb->IrpFlags;
    v9 = WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        3,
        18,
        (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids,
        *(_QWORD *)(a2 + 32));
      v9 = WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids;
    }
    Information = CallbackData->IoStatus.Information;
    ByteOffset = CallbackData->Iopb->Parameters.Read.ByteOffset;
    if ( Information )
    {
      if ( (*((int (__fastcall **)(char *, __int64 *, _QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
            + 53 * *((unsigned int *)Context + 3)
            + 40))(
             (char *)Context + 64,
             &v24,
             0) < 0
        || ByteOffset.QuadPart >= v24 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v15) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            3,
            20,
            (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids);
        }
        v13 = -1073741807;
      }
      else
      {
        v13 = FltLockUserBuffer(CallbackData);
        if ( v13 >= 0 )
        {
          Iopb = CallbackData->Iopb;
          MappedSystemVa = 0;
          if ( (Iopb->MinorFunction & 2) != 0
            || ((MdlAddress = Iopb->Parameters.Read.MdlAddress, (MdlAddress->MdlFlags & 5) == 0)
              ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u))
              : (MappedSystemVa = MdlAddress->MappedSystemVa),
                MappedSystemVa) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              v17 = "cached";
              if ( (IrpFlags & 1) != 0 )
                v17 = "noncached";
              WPP_RECORDER_SF_dDsZq(
                WPP_GLOBAL_Control->DeviceExtension,
                LODWORD(CallbackData->Iopb->TargetFileObject) + 88,
                CallbackData->Iopb,
                22,
                BugCheckOnFailure,
                CallbackData->Iopb->Parameters.Read.Length,
                ByteOffset.QuadPart,
                (__int64)v17,
                (__int64)&CallbackData->Iopb->TargetFileObject->FileName,
                (char)MappedSystemVa);
            }
            if ( MappedSystemVa )
            {
              v18 = Information;
              if ( Information > v24 || ByteOffset.QuadPart > v24 - Information )
                v18 = v24 - ByteOffset.LowPart;
              if ( v6 )
                v19 = *(_QWORD *)(v3 + 16);
              else
                v19 = 0;
              LOBYTE(Priority) = (IrpFlags & 2) != 0;
              v13 = (*((__int64 (__fastcall **)(PFLT_CALLBACK_DATA, __int64, struct _EX_RUNDOWN_REF *, _QWORD, char *, int, LARGE_INTEGER, unsigned int, PVOID, _QWORD, ULONG_PTR *))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                     + 53 * *((unsigned int *)Context + 3)
                     + 30))(
                      CallbackData,
                      v19,
                      v7,
                      *(_QWORD *)(a2 + 24),
                      (char *)Context + 64,
                      Priority,
                      ByteOffset,
                      v18,
                      MappedSystemVa,
                      0,
                      &v25);
              if ( v13 >= 0 )
              {
                CallbackData->IoStatus.Information = v25;
                CallbackData->IoStatus.Status = v13;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                  && LOWORD(WPP_GLOBAL_Control->DeviceType) )
                {
                  LOBYTE(v20) = 5;
                  WPP_RECORDER_SF_d(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v20,
                    3,
                    25,
                    (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids,
                    CallbackData->IoStatus.Information);
                }
                goto LABEL_56;
              }
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v20) = 2;
                WPP_RECORDER_SF_d(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v20,
                  3,
                  24,
                  (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids,
                  v13);
              }
            }
            else
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LOBYTE(v14) = 5;
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v14,
                  3,
                  23,
                  (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids);
              }
              v13 = -1073741592;
            }
          }
          else
          {
            v13 = -1073741801;
          }
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            3,
            21,
            (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids);
        }
      }
      CallbackData->IoStatus.Status = v13;
      CallbackData->IoStatus.Information = 0;
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
           && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        3,
        19,
        (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids);
    }
LABEL_56:
    FltReleaseContext(Context);
  }
  if ( v6 )
  {
    (*((void (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * *(unsigned int *)(v3 + 8) + 31))(*(_QWORD *)(v3 + 16));
    ExFreePoolWithTag((PVOID)v3, 0);
  }
  KeLeaveCriticalRegion();
  if ( v7 )
LABEL_7:
    ExReleaseRundownProtection(v7);
  return 0;
}

```

## disassembly

```asm
0x1400087c0  push    rbp
0x1400087c2  push    rsi
0x1400087c3  push    rdi
0x1400087c4  push    r13
0x1400087c6  push    r14
0x1400087c8  push    r15
0x1400087ca  sub     rsp, 88h
0x1400087d1  xor     eax, eax
0x1400087d3  mov     rsi, r8
0x1400087d6  and     rsi, 0FFFFFFFFFFFFFFFCh
0x1400087da  mov     [rsp+0B8h+Context], rax
0x1400087df  movzx   edi, r8b
0x1400087e3  mov     [rsp+0B8h+var_48], rax
0x1400087e8  mov     [rsp+0B8h+var_40], rax
0x1400087ed  mov     r13, rdx
0x1400087f0  mov     r15, rcx
0x1400087f3  and     dil, 2
0x1400087f7  jnz     loc_14000898B
0x1400087fd  mov     rbp, rsi
0x140008800  cmp     [rcx+18h], eax
0x140008803  jge     short loc_140008836
0x140008805  test    dil, dil
0x140008808  jnz     loc_140008CF2
0x14000880e  test    rbp, rbp
0x140008811  jz      short loc_140008822
0x140008813  mov     rcx, rbp; RunRef
0x140008816  call    cs:__imp_ExReleaseRundownProtection
0x14000881d  nop     dword ptr [rax+rax+00h]
0x140008822  xor     eax, eax
0x140008824  add     rsp, 88h
0x14000882b  pop     r15
0x14000882d  pop     r14
0x14000882f  pop     r13
0x140008831  pop     rdi
0x140008832  pop     rsi
0x140008833  pop     rbp
0x140008834  retn
0x140008836  test    r8b, 1
0x14000883a  jnz     short loc_140008805
0x14000883c  call    cs:__imp_KeEnterCriticalRegion
0x140008843  nop     dword ptr [rax+rax+00h]
0x140008848  mov     rdx, [r13+20h]; FileObject
0x14000884c  lea     r8, [rsp+0B8h+Context]; Context
0x140008851  mov     rcx, [r13+18h]; Instance
0x140008855  call    cs:__imp_FltGetStreamContext
0x14000885c  nop     dword ptr [rax+rax+00h]
0x140008861  lea     r8, WPP_MAIN_CB.Queue+10h
0x140008868  test    eax, eax
0x14000886a  js      loc_140008CA7
0x140008870  mov     rax, [r15+10h]
0x140008874  mov     [rsp+0B8h+arg_8], rbx
0x14000887c  mov     [rsp+0B8h+var_38], r12
0x140008884  mov     eax, [rax]
0x140008886  mov     [rsp+0B8h+arg_0], eax
0x14000888d  shr     eax, 1
0x14000888f  and     al, 1
0x140008891  mov     [rsp+0B8h+var_58], eax
0x140008895  lea     r12, WPP_RECORDER_INITIALIZED
0x14000889c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400088a3  lea     rdx, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x1400088aa  jz      short loc_1400088E6
0x1400088ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088b3  mov     r9d, 12h
0x1400088b9  mov     rax, [r13+20h]
0x1400088bd  mov     r8d, 3
0x1400088c3  mov     qword ptr [rsp+0B8h+Priority], rax
0x1400088c8  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rdx
0x1400088cd  mov     dl, 4
0x1400088cf  mov     rcx, [rcx+40h]
0x1400088d3  call    WPP_RECORDER_SF_q
0x1400088d8  lea     r8, WPP_MAIN_CB.Queue+10h
0x1400088df  lea     rdx, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x1400088e6  mov     eax, [r15+20h]
0x1400088ea  mov     rbx, [r15+10h]
0x1400088ee  mov     [rsp+0B8h+arg_10], eax
0x1400088f5  mov     rbx, [rbx+28h]
0x1400088f9  test    eax, eax
0x1400088fb  jnz     loc_140008993
0x140008901  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008908  jz      loc_140008C7F
0x14000890e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008915  cmp     [rcx+48h], ax
0x140008919  jz      loc_140008C7F
0x14000891f  mov     rcx, [rcx+40h]
0x140008923  mov     r9d, 13h
0x140008929  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rdx
0x14000892e  mov     r8d, 3
0x140008934  mov     dl, 5
0x140008936  call    WPP_RECORDER_SF_
0x14000893b  jmp     loc_140008C7F
0x140008940  mov     rcx, [rcx+38h]; MemoryDescriptorList
0x140008944  test    byte ptr [rcx+0Ah], 5
0x140008948  jz      short loc_140008962
0x14000894a  mov     r12, [rcx+18h]
0x14000894e  test    r12, r12
0x140008951  jnz     loc_140008A38
0x140008957  mov     r12d, 0C0000017h
0x14000895d  jmp     loc_140008C73
0x140008962  mov     [rsp+0B8h+Priority], 40000010h; Priority
0x14000896a  xor     r9d, r9d; RequestedAddress
0x14000896d  xor     edx, edx; AccessMode
0x14000896f  mov     [rsp+0B8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140008974  mov     r8d, 1; CacheType
0x14000897a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140008981  nop     dword ptr [rax+rax+00h]
0x140008986  mov     r12, rax
0x140008989  jmp     short loc_14000894E
0x14000898b  mov     rbp, [rsi]
0x14000898e  jmp     loc_140008800
0x140008993  mov     rcx, [rsp+0B8h+Context]
0x140008998  mov     eax, [rcx+0Ch]
0x14000899b  add     rcx, 40h ; '@'
0x14000899f  imul    rdx, rax, 1A8h
0x1400089a6  mov     rax, [rdx+r8+140h]
0x1400089ae  xor     r8d, r8d
0x1400089b1  lea     rdx, [rsp+0B8h+var_48]
0x1400089b6  call    _guard_dispatch_icall
0x1400089bb  test    eax, eax
0x1400089bd  js      loc_140008C33
0x1400089c3  cmp     rbx, [rsp+0B8h+var_48]
0x1400089c8  jge     loc_140008C33
0x1400089ce  mov     rcx, r15; CallbackData
0x1400089d1  call    cs:__imp_FltLockUserBuffer
0x1400089d8  nop     dword ptr [rax+rax+00h]
0x1400089dd  mov     r12d, eax
0x1400089e0  test    eax, eax
0x1400089e2  jns     short loc_140008A27
0x1400089e4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400089eb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400089f2  jz      loc_140008C73
0x1400089f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089ff  lea     rax, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x140008a06  mov     r9d, 15h
0x140008a0c  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140008a11  mov     r8d, 3
0x140008a17  mov     dl, 2
0x140008a19  mov     rcx, [rcx+40h]
0x140008a1d  call    WPP_RECORDER_SF_
0x140008a22  jmp     loc_140008C73
0x140008a27  mov     rcx, [r15+10h]
0x140008a2b  xor     r12d, r12d
0x140008a2e  test    byte ptr [rcx+5], 2
0x140008a32  jz      loc_140008940
0x140008a38  lea     rax, WPP_RECORDER_INITIALIZED
0x140008a3f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008a46  jz      short loc_140008AAD
0x140008a48  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a4f  cmp     word ptr [rcx+48h], 0
0x140008a54  jz      short loc_140008AAD
0x140008a56  mov     r8, [r15+10h]
0x140008a5a  lea     r9, aNoncached; "noncached"
0x140008a61  mov     rcx, [rcx+40h]
0x140008a65  lea     rax, aCached; "cached"
0x140008a6c  mov     [rsp+0B8h+var_70], r12
0x140008a71  mov     rdx, [r8+8]
0x140008a75  add     rdx, 58h ; 'X'
0x140008a79  test    byte ptr [rsp+0B8h+arg_0], 1
0x140008a81  mov     [rsp+0B8h+var_78], rdx
0x140008a86  cmovnz  rax, r9
0x140008a8a  mov     r9d, 16h
0x140008a90  mov     [rsp+0B8h+var_80], rax
0x140008a95  mov     eax, [r8+18h]
0x140008a99  mov     dword ptr [rsp+0B8h+var_88], ebx
0x140008a9d  mov     [rsp+0B8h+Priority], eax
0x140008aa1  call    WPP_RECORDER_SF_dDsZq
0x140008aa6  lea     rax, WPP_RECORDER_INITIALIZED
0x140008aad  test    r12, r12
0x140008ab0  jnz     short loc_140008AF7
0x140008ab2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008ab9  jz      short loc_140008AEC
0x140008abb  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ac2  cmp     [rcx+48h], r12w
0x140008ac7  jz      short loc_140008AEC
0x140008ac9  mov     rcx, [rcx+40h]
0x140008acd  lea     rax, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x140008ad4  mov     r9d, 17h
0x140008ada  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140008adf  mov     r8d, 3
0x140008ae5  mov     dl, 5
0x140008ae7  call    WPP_RECORDER_SF_
0x140008aec  mov     r12d, 0C00000E8h
0x140008af2  jmp     loc_140008C73
0x140008af7  mov     edx, [rsp+0B8h+arg_10]
0x140008afe  mov     rcx, [rsp+0B8h+var_48]
0x140008b03  cmp     rdx, rcx
0x140008b06  jg      short loc_140008B13
0x140008b08  mov     rax, rcx
0x140008b0b  sub     rax, rdx
0x140008b0e  cmp     rbx, rax
0x140008b11  jle     short loc_140008B17
0x140008b13  mov     edx, ecx
0x140008b15  sub     edx, ebx
0x140008b17  test    dil, dil
0x140008b1a  jz      short loc_140008B22
0x140008b1c  mov     r10, [rsi+10h]
0x140008b20  jmp     short loc_140008B25
0x140008b22  xor     r10d, r10d
0x140008b25  mov     r8, [rsp+0B8h+Context]
0x140008b2a  lea     r9, WPP_MAIN_CB.Queue+10h
0x140008b31  mov     eax, [r8+0Ch]
0x140008b35  add     r8, 40h ; '@'
0x140008b39  imul    rcx, rax, 1A8h
0x140008b40  mov     rax, [rcx+r9+0F0h]
0x140008b48  lea     rcx, [rsp+0B8h+var_40]
0x140008b4d  mov     r9, [r13+18h]
0x140008b51  mov     [rsp+0B8h+var_68], rcx
0x140008b56  mov     ecx, [rsp+0B8h+var_58]
0x140008b5a  mov     [rsp+0B8h+var_70], 0
0x140008b63  mov     [rsp+0B8h+var_78], r12
0x140008b68  mov     dword ptr [rsp+0B8h+var_80], edx
0x140008b6c  mov     rdx, r10
0x140008b6f  mov     [rsp+0B8h+var_88], rbx
0x140008b74  mov     byte ptr [rsp+0B8h+Priority], cl
0x140008b78  mov     rcx, r15
0x140008b7b  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], r8
0x140008b80  mov     r8, rbp
0x140008b83  call    _guard_dispatch_icall
0x140008b88  mov     r12d, eax
0x140008b8b  test    eax, eax
0x140008b8d  jns     short loc_140008BD7
0x140008b8f  lea     rax, WPP_RECORDER_INITIALIZED
0x140008b96  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008b9d  jz      loc_140008C73
0x140008ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x140008baa  lea     rax, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x140008bb1  mov     r9d, 18h
0x140008bb7  mov     [rsp+0B8h+Priority], r12d
0x140008bbc  mov     r8d, 3
0x140008bc2  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140008bc7  mov     dl, 2
0x140008bc9  mov     rcx, [rcx+40h]
0x140008bcd  call    WPP_RECORDER_SF_d
0x140008bd2  jmp     loc_140008C73
0x140008bd7  mov     rax, [rsp+0B8h+var_40]
0x140008bdc  mov     [r15+20h], rax
0x140008be0  mov     [r15+18h], r12d
0x140008be4  lea     rax, WPP_RECORDER_INITIALIZED
0x140008beb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008bf2  jz      loc_140008C7F
0x140008bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bff  cmp     word ptr [rcx+48h], 0
0x140008c04  jz      short loc_140008C7F
0x140008c06  mov     eax, [r15+20h]
0x140008c0a  mov     r9d, 19h
0x140008c10  mov     rcx, [rcx+40h]
0x140008c14  mov     r8d, 3
0x140008c1a  mov     [rsp+0B8h+Priority], eax
0x140008c1e  mov     dl, 5
0x140008c20  lea     rax, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x140008c27  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140008c2c  call    WPP_RECORDER_SF_d
0x140008c31  jmp     short loc_140008C7F
0x140008c33  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008c3a  jz      short loc_140008C6D
0x140008c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c43  cmp     word ptr [rcx+48h], 0
0x140008c48  jz      short loc_140008C6D
0x140008c4a  mov     rcx, [rcx+40h]
0x140008c4e  lea     rax, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x140008c55  mov     r9d, 14h
0x140008c5b  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140008c60  mov     r8d, 3
0x140008c66  mov     dl, 5
0x140008c68  call    WPP_RECORDER_SF_
0x140008c6d  mov     r12d, 0C0000011h
0x140008c73  mov     [r15+18h], r12d
0x140008c77  mov     qword ptr [r15+20h], 0
0x140008c7f  mov     rcx, [rsp+0B8h+Context]; Context
0x140008c84  call    cs:__imp_FltReleaseContext
0x140008c8b  nop     dword ptr [rax+rax+00h]
0x140008c90  mov     r12, [rsp+0B8h+var_38]
0x140008c98  lea     r8, WPP_MAIN_CB.Queue+10h
0x140008c9f  mov     rbx, [rsp+0B8h+arg_8]
0x140008ca7  test    dil, dil
0x140008caa  jz      short loc_140008CD8
0x140008cac  mov     eax, [rsi+8]
0x140008caf  mov     rcx, [rsi+10h]
0x140008cb3  imul    rdx, rax, 1A8h
0x140008cba  mov     rax, [rdx+r8+0F8h]
0x140008cc2  call    _guard_dispatch_icall
0x140008cc7  xor     edx, edx; Tag
0x140008cc9  mov     rcx, rsi; P
0x140008ccc  call    cs:__imp_ExFreePoolWithTag
0x140008cd3  nop     dword ptr [rax+rax+00h]
0x140008cd8  call    cs:__imp_KeLeaveCriticalRegion
0x140008cdf  nop     dword ptr [rax+rax+00h]
0x140008ce4  test    rbp, rbp
0x140008ce7  jz      loc_140008822
0x140008ced  jmp     loc_140008813
0x140008cf2  mov     eax, [rsi+8]
0x140008cf5  lea     r9, WPP_MAIN_CB.Queue+10h
0x140008cfc  mov     rcx, [rsi+10h]
0x140008d00  imul    rax, 1A8h
0x140008d07  mov     rax, [rax+r9+0F8h]
0x140008d0f  call    _guard_dispatch_icall
0x140008d14  xor     edx, edx; Tag
0x140008d16  mov     rcx, rsi; P
0x140008d19  call    cs:__imp_ExFreePoolWithTag
0x140008d20  nop     dword ptr [rax+rax+00h]
0x140008d25  jmp     loc_14000880E
  ... truncated ...
```

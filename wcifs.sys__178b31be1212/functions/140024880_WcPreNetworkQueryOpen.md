# WcPreNetworkQueryOpen

- ea: `0x140024880`
- end: `0x140024c2d`
- name: `WcPreNetworkQueryOpen`
- size: `941`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x140001580`
- `0x1400020c4`
- `0x140024880`

## import_xrefs

- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x1400249ae`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x1400249ae`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024c1c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024c1c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002492b`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002492b`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002498f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002498f`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140024a3a`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140024a3a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140024c01`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140024c01`
- `FLTMGR!FltGetFileNameInformation` at `0x14002490d`
- `FLTMGR!FltGetFileNameInformation` at `0x14002490d`
- `FLTMGR!FltObjectReference` at `0x140024a70`
- `FLTMGR!FltObjectReference` at `0x140024a70`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140024b0a`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140024b0a`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140024a00`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140024a00`

## string_xrefs

- `0x140024bb6`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcPreNetworkQueryOpen(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rdx
  _QWORD *v7; // rdi
  unsigned int v8; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v9; // rcx
  int v11; // edx
  int ExtraCreateParameter; // r14d
  char *v13; // rax
  IRP *Irp; // rbp
  struct _ECP_LIST *UserBuffer; // rdx
  __int64 *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rcx
  int v19; // r9d
  char EcpContext; // [rsp+30h] [rbp-48h]
  int v21; // [rsp+38h] [rbp-40h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp-38h] BYREF
  PECP_LIST EcpList; // [rsp+48h] [rbp-30h] BYREF
  int v24; // [rsp+88h] [rbp+10h] BYREF
  PVOID v25; // [rsp+98h] [rbp+20h] BYREF

  v24 = 268369920;
  FileNameInformation = 0;
  v4 = *(_QWORD *)(a2 + 32);
  EcpList = 0;
  v25 = 0;
  v7 = 0;
  if ( !(unsigned __int8)WcUnionsExistForInstance(*(_QWORD *)(a2 + 24), v4, &v24, 0) )
  {
    v8 = 1;
LABEL_3:
    v9 = FileNameInformation;
    goto LABEL_4;
  }
  ExtraCreateParameter = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
  if ( ExtraCreateParameter < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = ExtraCreateParameter;
      v19 = 77;
      EcpContext = 47;
      goto LABEL_31;
    }
    goto LABEL_21;
  }
  v13 = (char *)ExAllocateFromPagedLookasideList(&stru_14000E400);
  v7 = v13;
  if ( !v13 )
  {
    ExtraCreateParameter = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = -1073741670;
      v19 = 78;
      EcpContext = 56;
      goto LABEL_31;
    }
    goto LABEL_21;
  }
  *((_QWORD *)v13 + 1) = v13;
  *(_QWORD *)v13 = v13;
  *(_OWORD *)(v13 + 24) = 0;
  *((_DWORD *)v13 + 4) = v24;
  *((_DWORD *)v13 + 5) = -2147483644;
  *((_DWORD *)v13 + 10) = 48;
  Irp = CallbackData->Iopb->Parameters.QueryOpen.Irp;
  UserBuffer = (struct _ECP_LIST *)Irp->UserBuffer;
  EcpList = UserBuffer;
  if ( !UserBuffer )
  {
    ExtraCreateParameter = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
    if ( ExtraCreateParameter >= 0 )
    {
      FsRtlSetEcpListIntoIrp(Irp, EcpList);
      goto LABEL_14;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = ExtraCreateParameter;
      v19 = 79;
      EcpContext = 73;
LABEL_31:
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v11,
        5,
        v19,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        EcpContext,
        v21);
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  ExtraCreateParameter = FltFindExtraCreateParameter(Globals, UserBuffer, &ECP_TYPE_OPEN_REPARSE_GUID, &v25, 0);
  if ( (int)(ExtraCreateParameter + 0x80000000) >= 0 && ExtraCreateParameter != -1073741275 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = ExtraCreateParameter;
      v19 = 80;
      EcpContext = 96;
      goto LABEL_31;
    }
LABEL_21:
    CallbackData->IoStatus.Status = ExtraCreateParameter;
    CallbackData->IoStatus.Information = 0;
    v8 = 4;
    goto LABEL_3;
  }
LABEL_14:
  v16 = (__int64 *)v25;
  if ( v25 )
    goto LABEL_17;
  ExtraCreateParameter = FltAllocateExtraCreateParameterFromLookasideList(
                           Globals,
                           &ECP_TYPE_OPEN_REPARSE_GUID,
                           0x10u,
                           0,
                           0,
                           qword_14000E300,
                           &v25);
  if ( ExtraCreateParameter < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    v21 = ExtraCreateParameter;
    v19 = 81;
    EcpContext = 113;
    goto LABEL_31;
  }
  v17 = v25;
  *((_QWORD *)v25 + 1) = v25;
  *v17 = v17;
  FltInsertExtraCreateParameter(Globals, EcpList, v25);
  v16 = (__int64 *)v25;
LABEL_17:
  v18 = *v16;
  if ( *(__int64 **)(*v16 + 8) != v16 )
    __fastfail(3u);
  *v7 = v18;
  v7[1] = v16;
  *(_QWORD *)(v18 + 8) = v7;
  *v16 = (__int64)v7;
  ExtraCreateParameter = FltObjectReference(Globals);
  if ( ExtraCreateParameter < 0 )
    goto LABEL_21;
  v9 = 0;
  v7[6] = FileNameInformation;
  v8 = 0;
  *a3 = v7;
  v7 = 0;
  FileNameInformation = 0;
LABEL_4:
  if ( v9 )
    FltReleaseFileNameInformation(v9);
  if ( v7 )
    ExFreeToPagedLookasideList(&stru_14000E400, v7);
  return v8;
}

```

## disassembly

```asm
0x140024880  mov     r11, rsp
0x140024883  mov     [r11+8], rbx
0x140024887  push    rbp
0x140024888  push    rsi
0x140024889  push    rdi
0x14002488a  push    r14
0x14002488c  push    r15
0x14002488e  sub     rsp, 50h
0x140024892  xor     r15d, r15d
0x140024895  mov     dword ptr [r11+10h], 0FFF0000h
0x14002489d  mov     rax, rdx
0x1400248a0  mov     [r11-38h], r15
0x1400248a4  mov     rdx, [rdx+20h]
0x1400248a8  mov     rsi, r8
0x1400248ab  mov     rbx, rcx
0x1400248ae  mov     [r11-30h], r15
0x1400248b2  xor     r9d, r9d
0x1400248b5  mov     [r11+20h], r15
0x1400248b9  mov     rcx, [rax+18h]
0x1400248bd  lea     r8, [r11+10h]
0x1400248c1  mov     edi, r15d
0x1400248c4  call    WcUnionsExistForInstance
0x1400248c9  test    al, al
0x1400248cb  jnz     short loc_140024900
0x1400248cd  mov     ebx, 1
0x1400248d2  mov     rcx, [rsp+78h+FileNameInformation]; FileNameInformation
0x1400248d7  test    rcx, rcx
0x1400248da  jnz     loc_140024C01
0x1400248e0  test    rdi, rdi
0x1400248e3  jnz     loc_140024C12
0x1400248e9  mov     eax, ebx
0x1400248eb  mov     rbx, [rsp+78h+arg_0]
0x1400248f3  add     rsp, 50h
0x1400248f7  pop     r15
0x1400248f9  pop     r14
0x1400248fb  pop     rdi
0x1400248fc  pop     rsi
0x1400248fd  pop     rbp
0x1400248fe  retn
0x140024900  lea     r8, [rsp+78h+FileNameInformation]; FileNameInformation
0x140024905  mov     edx, 102h; NameOptions
0x14002490a  mov     rcx, rbx; CallbackData
0x14002490d  call    cs:__imp_FltGetFileNameInformation
0x140024914  nop     dword ptr [rax+rax+00h]
0x140024919  mov     r14d, eax
0x14002491c  test    eax, eax
0x14002491e  js      loc_140024B5E
0x140024924  lea     rcx, stru_14000E400; Lookaside
0x14002492b  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140024932  nop     dword ptr [rax+rax+00h]
0x140024937  mov     rdi, rax
0x14002493a  test    rax, rax
0x14002493d  jz      loc_140024AA2
0x140024943  mov     [rax+8], rax
0x140024947  xorps   xmm0, xmm0
0x14002494a  mov     [rax], rax
0x14002494d  movups  xmmword ptr [rax+18h], xmm0
0x140024951  mov     eax, [rsp+78h+arg_8]
0x140024958  mov     [rdi+10h], eax
0x14002495b  mov     dword ptr [rdi+14h], 80000004h
0x140024962  mov     dword ptr [rdi+28h], 30h ; '0'
0x140024969  mov     rax, [rbx+10h]
0x14002496d  mov     rcx, cs:Globals; Filter
0x140024974  mov     rbp, [rax+18h]
0x140024978  mov     rdx, [rbp+70h]; EcpList
0x14002497c  mov     [rsp+78h+EcpList], rdx
0x140024981  test    rdx, rdx
0x140024984  jnz     loc_140024AF6
0x14002498a  lea     r8, [rsp+78h+EcpList]; EcpList
0x14002498f  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140024996  nop     dword ptr [rax+rax+00h]
0x14002499b  mov     r14d, eax
0x14002499e  test    eax, eax
0x1400249a0  js      loc_140024ACE
0x1400249a6  mov     rdx, [rsp+78h+EcpList]; EcpList
0x1400249ab  mov     rcx, rbp; Irp
0x1400249ae  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x1400249b5  nop     dword ptr [rax+rax+00h]
0x1400249ba  mov     rax, [rsp+78h+arg_18]
0x1400249c2  test    rax, rax
0x1400249c5  jnz     loc_140024A4E
0x1400249cb  mov     rcx, cs:Globals; Filter
0x1400249d2  lea     rax, [rsp+78h+arg_18]
0x1400249da  mov     [rsp+78h+EcpContext], rax; EcpContext
0x1400249df  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x1400249e6  lea     rax, qword_14000E300
0x1400249ed  xor     r9d, r9d; Flags
0x1400249f0  mov     [rsp+78h+LookasideList], rax; LookasideList
0x1400249f5  mov     r8d, 10h; SizeOfContext
0x1400249fb  mov     [rsp+78h+CleanupCallback], r15; CleanupCallback
0x140024a00  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140024a07  nop     dword ptr [rax+rax+00h]
0x140024a0c  mov     r14d, eax
0x140024a0f  test    eax, eax
0x140024a11  js      loc_140024BE4
0x140024a17  mov     rax, [rsp+78h+arg_18]
0x140024a1f  mov     [rax+8], rax
0x140024a23  mov     [rax], rax
0x140024a26  mov     r8, [rsp+78h+arg_18]; EcpContext
0x140024a2e  mov     rdx, [rsp+78h+EcpList]; EcpList
0x140024a33  mov     rcx, cs:Globals; Filter
0x140024a3a  call    cs:__imp_FltInsertExtraCreateParameter
0x140024a41  nop     dword ptr [rax+rax+00h]
0x140024a46  mov     rax, [rsp+78h+arg_18]
0x140024a4e  mov     rcx, [rax]
0x140024a51  cmp     [rcx+8], rax
0x140024a55  jnz     loc_140024BFA
0x140024a5b  mov     [rdi], rcx
0x140024a5e  mov     [rdi+8], rax
0x140024a62  mov     [rcx+8], rdi
0x140024a66  mov     [rax], rdi
0x140024a69  mov     rcx, cs:Globals; FltObject
0x140024a70  call    cs:__imp_FltObjectReference
0x140024a77  nop     dword ptr [rax+rax+00h]
0x140024a7c  mov     r14d, eax
0x140024a7f  test    eax, eax
0x140024a81  js      short loc_140024ABC
0x140024a83  mov     rax, [rsp+78h+FileNameInformation]
0x140024a88  mov     rcx, r15
0x140024a8b  mov     [rdi+30h], rax
0x140024a8f  mov     ebx, r15d
0x140024a92  mov     [rsi], rdi
0x140024a95  mov     rdi, r15
0x140024a98  mov     [rsp+78h+FileNameInformation], rcx
0x140024a9d  jmp     loc_1400248D7
0x140024aa2  mov     r14d, 0C000009Ah
0x140024aa8  lea     rax, WPP_RECORDER_INITIALIZED
0x140024aaf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024ab6  jnz     loc_140024B87
0x140024abc  mov     [rbx+18h], r14d
0x140024ac0  mov     [rbx+20h], r15
0x140024ac4  mov     ebx, 4
0x140024ac9  jmp     loc_1400248D2
0x140024ace  lea     rax, WPP_RECORDER_INITIALIZED
0x140024ad5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024adc  jz      short loc_140024ABC
0x140024ade  mov     [rsp+78h+var_40], r14d
0x140024ae3  mov     r9d, 4Fh ; 'O'
0x140024ae9  mov     dword ptr [rsp+78h+EcpContext], 0D49h
0x140024af1  jmp     loc_140024BAF
0x140024af6  lea     r9, [rsp+78h+arg_18]; EcpContext
0x140024afe  mov     [rsp+78h+CleanupCallback], r15; EcpContextSize
0x140024b03  lea     r8, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x140024b0a  call    cs:__imp_FltFindExtraCreateParameter
0x140024b11  nop     dword ptr [rax+rax+00h]
0x140024b16  mov     ecx, 80000000h
0x140024b1b  mov     r14d, eax
0x140024b1e  add     eax, ecx
0x140024b20  test    ecx, eax
0x140024b22  jnz     loc_1400249BA
0x140024b28  cmp     r14d, 0C0000225h
0x140024b2f  jz      loc_1400249BA
0x140024b35  lea     rax, WPP_RECORDER_INITIALIZED
0x140024b3c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024b43  jz      loc_140024ABC
0x140024b49  mov     [rsp+78h+var_40], r14d
0x140024b4e  mov     r9d, 50h ; 'P'
0x140024b54  mov     dword ptr [rsp+78h+EcpContext], 0D60h
0x140024b5c  jmp     short loc_140024BAF
0x140024b5e  lea     rax, WPP_RECORDER_INITIALIZED
0x140024b65  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024b6c  jz      loc_140024ABC
0x140024b72  mov     [rsp+78h+var_40], r14d
0x140024b77  mov     r9d, 4Dh ; 'M'
0x140024b7d  mov     dword ptr [rsp+78h+EcpContext], 0D2Fh
0x140024b85  jmp     short loc_140024BAF
0x140024b87  mov     [rsp+78h+var_40], r14d
0x140024b8c  mov     r9d, 4Eh ; 'N'
0x140024b92  mov     dword ptr [rsp+78h+EcpContext], 0D38h
0x140024b9a  jmp     short loc_140024BAF
0x140024b9c  mov     [rsp+78h+var_40], r14d
0x140024ba1  mov     r9d, 51h ; 'Q'
0x140024ba7  mov     dword ptr [rsp+78h+EcpContext], 0D71h
0x140024baf  mov     rcx, cs:wil_details_featureDescriptors_a
0x140024bb6  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140024bbd  mov     [rsp+78h+LookasideList], rax
0x140024bc2  mov     r8d, 5
0x140024bc8  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140024bcf  mov     dl, 2
0x140024bd1  mov     [rsp+78h+CleanupCallback], rax
0x140024bd6  mov     rcx, [rcx+40h]
0x140024bda  call    WPP_RECORDER_SF_sDd
0x140024bdf  jmp     loc_140024ABC
0x140024be4  lea     rax, WPP_RECORDER_INITIALIZED
0x140024beb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024bf2  jz      loc_140024ABC
0x140024bf8  jmp     short loc_140024B9C
0x140024bfa  mov     ecx, 3
0x140024bff  int     29h; Win8: RtlFailFast(ecx)
0x140024c01  call    cs:__imp_FltReleaseFileNameInformation
0x140024c08  nop     dword ptr [rax+rax+00h]
0x140024c0d  jmp     loc_1400248E0
0x140024c12  mov     rdx, rdi; Entry
0x140024c15  lea     rcx, stru_14000E400; Lookaside
0x140024c1c  call    cs:__imp_ExFreeToPagedLookasideList
0x140024c23  nop     dword ptr [rax+rax+00h]
0x140024c28  jmp     loc_1400248E9
```

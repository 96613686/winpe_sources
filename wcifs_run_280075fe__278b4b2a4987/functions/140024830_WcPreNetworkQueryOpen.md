# WcPreNetworkQueryOpen

- ea: `0x140024830`
- end: `0x140024bdd`
- name: `WcPreNetworkQueryOpen`
- size: `941`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x140001580`
- `0x1400020c4`
- `0x140024830`

## import_xrefs

- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14002495e`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14002495e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024bcc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024bcc`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400248db`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400248db`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002493f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002493f`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400249ea`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400249ea`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140024bb1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140024bb1`
- `FLTMGR!FltGetFileNameInformation` at `0x1400248bd`
- `FLTMGR!FltGetFileNameInformation` at `0x1400248bd`
- `FLTMGR!FltObjectReference` at `0x140024a20`
- `FLTMGR!FltObjectReference` at `0x140024a20`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140024aba`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140024aba`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x1400249b0`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x1400249b0`

## string_xrefs

- `0x140024b66`: `onecore\base\fs\wci\wcifs\create.c`

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
  char v21; // [rsp+38h] [rbp-40h]
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
      v21 = -102;
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
        WPP_GLOBAL_Control->DeviceExtension,
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
0x140024830  mov     r11, rsp
0x140024833  mov     [r11+8], rbx
0x140024837  push    rbp
0x140024838  push    rsi
0x140024839  push    rdi
0x14002483a  push    r14
0x14002483c  push    r15
0x14002483e  sub     rsp, 50h
0x140024842  xor     r15d, r15d
0x140024845  mov     dword ptr [r11+10h], 0FFF0000h
0x14002484d  mov     rax, rdx
0x140024850  mov     [r11-38h], r15
0x140024854  mov     rdx, [rdx+20h]
0x140024858  mov     rsi, r8
0x14002485b  mov     rbx, rcx
0x14002485e  mov     [r11-30h], r15
0x140024862  xor     r9d, r9d
0x140024865  mov     [r11+20h], r15
0x140024869  mov     rcx, [rax+18h]
0x14002486d  lea     r8, [r11+10h]
0x140024871  mov     edi, r15d
0x140024874  call    WcUnionsExistForInstance
0x140024879  test    al, al
0x14002487b  jnz     short loc_1400248B0
0x14002487d  mov     ebx, 1
0x140024882  mov     rcx, [rsp+78h+FileNameInformation]; FileNameInformation
0x140024887  test    rcx, rcx
0x14002488a  jnz     loc_140024BB1
0x140024890  test    rdi, rdi
0x140024893  jnz     loc_140024BC2
0x140024899  mov     eax, ebx
0x14002489b  mov     rbx, [rsp+78h+arg_0]
0x1400248a3  add     rsp, 50h
0x1400248a7  pop     r15
0x1400248a9  pop     r14
0x1400248ab  pop     rdi
0x1400248ac  pop     rsi
0x1400248ad  pop     rbp
0x1400248ae  retn
0x1400248b0  lea     r8, [rsp+78h+FileNameInformation]; FileNameInformation
0x1400248b5  mov     edx, 102h; NameOptions
0x1400248ba  mov     rcx, rbx; CallbackData
0x1400248bd  call    cs:__imp_FltGetFileNameInformation
0x1400248c4  nop     dword ptr [rax+rax+00h]
0x1400248c9  mov     r14d, eax
0x1400248cc  test    eax, eax
0x1400248ce  js      loc_140024B0E
0x1400248d4  lea     rcx, stru_14000E400; Lookaside
0x1400248db  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400248e2  nop     dword ptr [rax+rax+00h]
0x1400248e7  mov     rdi, rax
0x1400248ea  test    rax, rax
0x1400248ed  jz      loc_140024A52
0x1400248f3  mov     [rax+8], rax
0x1400248f7  xorps   xmm0, xmm0
0x1400248fa  mov     [rax], rax
0x1400248fd  movups  xmmword ptr [rax+18h], xmm0
0x140024901  mov     eax, [rsp+78h+arg_8]
0x140024908  mov     [rdi+10h], eax
0x14002490b  mov     dword ptr [rdi+14h], 80000004h
0x140024912  mov     dword ptr [rdi+28h], 30h ; '0'
0x140024919  mov     rax, [rbx+10h]
0x14002491d  mov     rcx, cs:Globals; Filter
0x140024924  mov     rbp, [rax+18h]
0x140024928  mov     rdx, [rbp+70h]; EcpList
0x14002492c  mov     [rsp+78h+EcpList], rdx
0x140024931  test    rdx, rdx
0x140024934  jnz     loc_140024AA6
0x14002493a  lea     r8, [rsp+78h+EcpList]; EcpList
0x14002493f  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140024946  nop     dword ptr [rax+rax+00h]
0x14002494b  mov     r14d, eax
0x14002494e  test    eax, eax
0x140024950  js      loc_140024A7E
0x140024956  mov     rdx, [rsp+78h+EcpList]; EcpList
0x14002495b  mov     rcx, rbp; Irp
0x14002495e  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x140024965  nop     dword ptr [rax+rax+00h]
0x14002496a  mov     rax, [rsp+78h+arg_18]
0x140024972  test    rax, rax
0x140024975  jnz     loc_1400249FE
0x14002497b  mov     rcx, cs:Globals; Filter
0x140024982  lea     rax, [rsp+78h+arg_18]
0x14002498a  mov     [rsp+78h+EcpContext], rax; EcpContext
0x14002498f  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x140024996  lea     rax, qword_14000E300
0x14002499d  xor     r9d, r9d; Flags
0x1400249a0  mov     [rsp+78h+LookasideList], rax; LookasideList
0x1400249a5  mov     r8d, 10h; SizeOfContext
0x1400249ab  mov     [rsp+78h+CleanupCallback], r15; CleanupCallback
0x1400249b0  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x1400249b7  nop     dword ptr [rax+rax+00h]
0x1400249bc  mov     r14d, eax
0x1400249bf  test    eax, eax
0x1400249c1  js      loc_140024B94
0x1400249c7  mov     rax, [rsp+78h+arg_18]
0x1400249cf  mov     [rax+8], rax
0x1400249d3  mov     [rax], rax
0x1400249d6  mov     r8, [rsp+78h+arg_18]; EcpContext
0x1400249de  mov     rdx, [rsp+78h+EcpList]; EcpList
0x1400249e3  mov     rcx, cs:Globals; Filter
0x1400249ea  call    cs:__imp_FltInsertExtraCreateParameter
0x1400249f1  nop     dword ptr [rax+rax+00h]
0x1400249f6  mov     rax, [rsp+78h+arg_18]
0x1400249fe  mov     rcx, [rax]
0x140024a01  cmp     [rcx+8], rax
0x140024a05  jnz     loc_140024BAA
0x140024a0b  mov     [rdi], rcx
0x140024a0e  mov     [rdi+8], rax
0x140024a12  mov     [rcx+8], rdi
0x140024a16  mov     [rax], rdi
0x140024a19  mov     rcx, cs:Globals; FltObject
0x140024a20  call    cs:__imp_FltObjectReference
0x140024a27  nop     dword ptr [rax+rax+00h]
0x140024a2c  mov     r14d, eax
0x140024a2f  test    eax, eax
0x140024a31  js      short loc_140024A6C
0x140024a33  mov     rax, [rsp+78h+FileNameInformation]
0x140024a38  mov     rcx, r15
0x140024a3b  mov     [rdi+30h], rax
0x140024a3f  mov     ebx, r15d
0x140024a42  mov     [rsi], rdi
0x140024a45  mov     rdi, r15
0x140024a48  mov     [rsp+78h+FileNameInformation], rcx
0x140024a4d  jmp     loc_140024887
0x140024a52  mov     r14d, 0C000009Ah
0x140024a58  lea     rax, WPP_RECORDER_INITIALIZED
0x140024a5f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024a66  jnz     loc_140024B37
0x140024a6c  mov     [rbx+18h], r14d
0x140024a70  mov     [rbx+20h], r15
0x140024a74  mov     ebx, 4
0x140024a79  jmp     loc_140024882
0x140024a7e  lea     rax, WPP_RECORDER_INITIALIZED
0x140024a85  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024a8c  jz      short loc_140024A6C
0x140024a8e  mov     dword ptr [rsp+78h+var_40], r14d
0x140024a93  mov     r9d, 4Fh ; 'O'
0x140024a99  mov     dword ptr [rsp+78h+EcpContext], 0D49h
0x140024aa1  jmp     loc_140024B5F
0x140024aa6  lea     r9, [rsp+78h+arg_18]; EcpContext
0x140024aae  mov     [rsp+78h+CleanupCallback], r15; EcpContextSize
0x140024ab3  lea     r8, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x140024aba  call    cs:__imp_FltFindExtraCreateParameter
0x140024ac1  nop     dword ptr [rax+rax+00h]
0x140024ac6  mov     ecx, 80000000h
0x140024acb  mov     r14d, eax
0x140024ace  add     eax, ecx
0x140024ad0  test    ecx, eax
0x140024ad2  jnz     loc_14002496A
0x140024ad8  cmp     r14d, 0C0000225h
0x140024adf  jz      loc_14002496A
0x140024ae5  lea     rax, WPP_RECORDER_INITIALIZED
0x140024aec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024af3  jz      loc_140024A6C
0x140024af9  mov     dword ptr [rsp+78h+var_40], r14d
0x140024afe  mov     r9d, 50h ; 'P'
0x140024b04  mov     dword ptr [rsp+78h+EcpContext], 0D60h
0x140024b0c  jmp     short loc_140024B5F
0x140024b0e  lea     rax, WPP_RECORDER_INITIALIZED
0x140024b15  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024b1c  jz      loc_140024A6C
0x140024b22  mov     dword ptr [rsp+78h+var_40], r14d
0x140024b27  mov     r9d, 4Dh ; 'M'
0x140024b2d  mov     dword ptr [rsp+78h+EcpContext], 0D2Fh
0x140024b35  jmp     short loc_140024B5F
0x140024b37  mov     dword ptr [rsp+78h+var_40], r14d
0x140024b3c  mov     r9d, 4Eh ; 'N'
0x140024b42  mov     dword ptr [rsp+78h+EcpContext], 0D38h
0x140024b4a  jmp     short loc_140024B5F
0x140024b4c  mov     dword ptr [rsp+78h+var_40], r14d
0x140024b51  mov     r9d, 51h ; 'Q'
0x140024b57  mov     dword ptr [rsp+78h+EcpContext], 0D71h
0x140024b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b66  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140024b6d  mov     [rsp+78h+LookasideList], rax
0x140024b72  mov     r8d, 5
0x140024b78  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140024b7f  mov     dl, 2
0x140024b81  mov     [rsp+78h+CleanupCallback], rax
0x140024b86  mov     rcx, [rcx+40h]
0x140024b8a  call    WPP_RECORDER_SF_sDd
0x140024b8f  jmp     loc_140024A6C
0x140024b94  lea     rax, WPP_RECORDER_INITIALIZED
0x140024b9b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024ba2  jz      loc_140024A6C
0x140024ba8  jmp     short loc_140024B4C
0x140024baa  mov     ecx, 3
0x140024baf  int     29h; Win8: RtlFailFast(ecx)
0x140024bb1  call    cs:__imp_FltReleaseFileNameInformation
0x140024bb8  nop     dword ptr [rax+rax+00h]
0x140024bbd  jmp     loc_140024890
0x140024bc2  mov     rdx, rdi; Entry
0x140024bc5  lea     rcx, stru_14000E400; Lookaside
0x140024bcc  call    cs:__imp_ExFreeToPagedLookasideList
0x140024bd3  nop     dword ptr [rax+rax+00h]
0x140024bd8  jmp     loc_140024899
```

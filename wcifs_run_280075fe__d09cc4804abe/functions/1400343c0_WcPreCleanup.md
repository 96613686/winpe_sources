# WcPreCleanup

- ea: `0x1400343c0`
- end: `0x140034b9c`
- name: `WcPreCleanup`
- size: `2012`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001500`
- `0x1400016f0`
- `0x1400020c4`
- `0x140007c60`
- `0x14001bcec`
- `0x140027854`
- `0x140029608`
- `0x14002d5f8`
- `0x1400343c0`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14003457b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14003457b`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140034563`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14003458d`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140034563`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14003458d`
- `ntoskrnl!EtwWriteTransfer` at `0x140034b47`
- `ntoskrnl!EtwWriteTransfer` at `0x140034b47`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140034535`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140034535`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140034499`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140034894`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140034499`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140034894`
- `ntoskrnl!ObfDereferenceObject` at `0x140034644`
- `ntoskrnl!ObfDereferenceObject` at `0x14003466e`
- `ntoskrnl!ObfDereferenceObject` at `0x140034644`
- `ntoskrnl!ObfDereferenceObject` at `0x14003466e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400345dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400345dd`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400345ac`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400345ac`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400345c9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400345c9`
- `FLTMGR!FltCreateFileEx2` at `0x1400347dc`
- `FLTMGR!FltCreateFileEx2` at `0x1400347dc`
- `FLTMGR!FltClose` at `0x140034630`
- `FLTMGR!FltClose` at `0x140034659`
- `FLTMGR!FltClose` at `0x140034630`
- `FLTMGR!FltClose` at `0x140034659`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003451a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003451a`
- `FLTMGR!FltGetFileNameInformation` at `0x140034738`
- `FLTMGR!FltGetFileNameInformation` at `0x1400348e3`
- `FLTMGR!FltGetFileNameInformation` at `0x140034738`
- `FLTMGR!FltGetFileNameInformation` at `0x1400348e3`
- `FLTMGR!FltParseFileNameInformation` at `0x1400348fb`
- `FLTMGR!FltParseFileNameInformation` at `0x1400348fb`
- `FLTMGR!FltGetStreamHandleContext` at `0x140034458`
- `FLTMGR!FltGetStreamHandleContext` at `0x140034458`
- `FLTMGR!FltReleaseContext` at `0x1400345f2`
- `FLTMGR!FltReleaseContext` at `0x140034606`
- `FLTMGR!FltReleaseContext` at `0x14003461b`
- `FLTMGR!FltReleaseContext` at `0x140034683`
- `FLTMGR!FltReleaseContext` at `0x140034698`
- `FLTMGR!FltReleaseContext` at `0x1400345f2`
- `FLTMGR!FltReleaseContext` at `0x140034606`
- `FLTMGR!FltReleaseContext` at `0x14003461b`
- `FLTMGR!FltReleaseContext` at `0x140034683`
- `FLTMGR!FltReleaseContext` at `0x140034698`

## pseudocode

```c
__int64 __fastcall WcPreCleanup(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rbx
  struct _FILE_OBJECT *v5; // rdx
  struct _FLT_INSTANCE *v7; // rcx
  _QWORD *v8; // rax
  int v9; // edx
  int v10; // r9d
  unsigned int v11; // r13d
  PFLT_CONTEXT v12; // rsi
  struct _FLT_INSTANCE *v14; // rdx
  NTSTATUS v15; // eax
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  char v18; // [rsp+80h] [rbp-80h]
  PFLT_CONTEXT v19; // [rsp+88h] [rbp-78h]
  int v20; // [rsp+90h] [rbp-70h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation[2]; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v22; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_CONTEXT v24; // [rsp+B8h] [rbp-48h]
  HANDLE FileHandle; // [rsp+C0h] [rbp-40h]
  PVOID Object; // [rsp+C8h] [rbp-38h] BYREF
  PFLT_CONTEXT v27; // [rsp+D0h] [rbp-30h]
  PFLT_CONTEXT v28; // [rsp+D8h] [rbp-28h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+E0h] [rbp-20h]
  __int128 v30; // [rsp+F0h] [rbp-10h]
  PFLT_CALLBACK_DATA CallbackDataa; // [rsp+100h] [rbp+0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+108h] [rbp+8h] BYREF
  struct _IO_STATUS_BLOCK v33; // [rsp+138h] [rbp+38h] BYREF

  v3 = 0;
  *(_QWORD *)&EventDescriptor.Id = a3;
  CallbackDataa = CallbackData;
  v19 = 0;
  v5 = *(struct _FILE_OBJECT **)(a2 + 32);
  v24 = 0;
  v7 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  FileNameInformation[0] = 0;
  v30 = 0;
  FileHandle = 0;
  FileNameInformation[1] = 0;
  v18 = 0;
  v22 = 0;
  memset(&ObjectAttributes, 0, 44);
  Object = 0;
  v28 = 0;
  v33 = 0;
  v27 = 0;
  if ( FltGetStreamHandleContext(v7, v5, &Context) >= 0 && (*((_DWORD *)Context + 10) & 1) != 0 )
  {
    v20 = WcPrepareForDelete(CallbackData);
    if ( v20 < 0 )
    {
      v8 = ExAllocateFromPagedLookasideList(&stru_14000E500);
      v3 = v8;
      if ( v8 )
      {
        *((_BYTE *)v8 + 17) = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v9,
            5,
            55,
            (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
            131,
            v20);
        }
        if ( FltGetFileNameInformation(CallbackDataa, 0x101u, FileNameInformation) >= 0 )
        {
          v14 = *(struct _FLT_INSTANCE **)(a2 + 24);
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &FileNameInformation[0]->Name;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v15 = FltCreateFileEx2(
                  Globals,
                  v14,
                  &v22,
                  (PFILE_OBJECT *)&Object,
                  0x10000u,
                  &ObjectAttributes,
                  &v33,
                  0,
                  0x80u,
                  3u,
                  1u,
                  0x200000u,
                  0,
                  0,
                  0x800u,
                  0);
          if ( v15 >= 0 )
          {
            v11 = 5;
            *v3 = 0;
            v3[1] = 0;
            v3[3] = v22;
            v22 = 0;
            **(_QWORD **)&EventDescriptor.Id = v3;
            v3 = 0;
            goto LABEL_9;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            AllocationSize = v15;
            v10 = 56;
            IoStatusBlock = -89;
            goto LABEL_7;
          }
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        AllocationSize = -102;
        v10 = 54;
        IoStatusBlock = 125;
LABEL_7:
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          5,
          v10,
          (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
          IoStatusBlock,
          AllocationSize);
      }
LABEL_8:
      v11 = 1;
LABEL_9:
      v12 = v19;
      goto LABEL_10;
    }
  }
  if ( !(unsigned __int8)WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) )
    goto LABEL_8;
  v12 = v19;
  v11 = 1;
LABEL_10:
  if ( FileNameInformation[0] )
    FltReleaseFileNameInformation(FileNameInformation[0]);
  if ( v3 )
    ExFreeToPagedLookasideList(&stru_14000E500, v3);
  if ( v24 )
    FltReleaseContext(v24);
  if ( v12 )
    FltReleaseContext(v12);
  if ( Context )
    FltReleaseContext(Context);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v22 )
    FltClose(v22);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v27 )
    FltReleaseContext(v27);
  if ( v28 )
    FltReleaseContext(v28);
  return v11;
}

```

## disassembly

```asm
0x1400343c0  mov     [rsp-8+arg_18], rbx
0x1400343c5  push    rbp
0x1400343c6  push    rsi
0x1400343c7  push    rdi
0x1400343c8  push    r12
0x1400343ca  push    r13
0x1400343cc  push    r14
0x1400343ce  push    r15
0x1400343d0  lea     rbp, [rsp-0B0h]
0x1400343d8  sub     rsp, 1B0h
0x1400343df  mov     rax, cs:__security_cookie
0x1400343e6  xor     rax, rsp
0x1400343e9  mov     [rbp+0E0h+var_40], rax
0x1400343f0  xor     ebx, ebx
0x1400343f2  mov     qword ptr [rbp+0E0h+EventDescriptor.Id], r8
0x1400343f6  xorps   xmm0, xmm0
0x1400343f9  mov     [rbp+0E0h+CallbackData], rcx
0x1400343fd  mov     r13, rdx
0x140034400  mov     [rbp+0E0h+var_158], rbx
0x140034404  mov     rdx, [rdx+20h]; FileObject
0x140034408  mov     r15, r8
0x14003440b  mov     r14, rcx
0x14003440e  mov     [rbp+0E0h+var_128], rbx
0x140034412  movups  xmmword ptr [rbp+0E0h+var_D8.ObjectName], xmm0
0x140034416  mov     rcx, [r13+18h]; Instance
0x14003441a  lea     r8, [rbp+0E0h+Context]; Context
0x14003441e  xor     eax, eax
0x140034420  mov     [rbp+0E0h+Context], rbx
0x140034424  mov     [rbp+0E0h+FileNameInformation], rbx
0x140034428  mov     r12d, ebx
0x14003442b  movups  [rbp+0E0h+var_F0], xmm0
0x14003442f  mov     [rbp+0E0h+FileHandle], rbx
0x140034433  mov     edi, ebx
0x140034435  mov     [rbp+0E0h+FileObject], rbx
0x140034439  mov     [rbp+0E0h+var_160], bl
0x14003443c  mov     [rbp+0E0h+var_138], rbx
0x140034440  movups  xmmword ptr [rbp+0E0h+var_D8.Length], xmm0
0x140034444  mov     [rbp+0E0h+Object], rbx
0x140034448  movups  xmmword ptr [rbp+0E0h+var_D8+1Ch], xmm0
0x14003444c  mov     [rbp+0E0h+var_108], rbx
0x140034450  movups  xmmword ptr [rbp+0E0h+var_A8], xmm0
0x140034454  mov     [rbp+0E0h+var_110], rbx
0x140034458  call    cs:__imp_FltGetStreamHandleContext
0x14003445f  nop     dword ptr [rax+rax+00h]
0x140034464  test    eax, eax
0x140034466  js      loc_14003483E
0x14003446c  mov     rax, [rbp+0E0h+Context]
0x140034470  mov     ecx, [rax+28h]
0x140034473  test    cl, 1
0x140034476  jz      loc_14003483E
0x14003447c  mov     rdx, r13
0x14003447f  mov     rcx, r14; CallbackData
0x140034482  call    WcPrepareForDelete
0x140034487  mov     [rbp+0E0h+var_150], eax
0x14003448a  test    eax, eax
0x14003448c  jns     loc_14003483E
0x140034492  lea     rcx, stru_14000E500; Lookaside
0x140034499  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400344a0  nop     dword ptr [rax+rax+00h]
0x1400344a5  mov     rbx, rax
0x1400344a8  test    rax, rax
0x1400344ab  jnz     loc_1400346D2
0x1400344b1  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400344b8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400344bf  jz      short loc_140034507
0x1400344c1  mov     dword ptr [rsp+1E0h+AllocationSize], 0C000009Ah
0x1400344c9  mov     r9d, 36h ; '6'
0x1400344cf  mov     dword ptr [rsp+1E0h+IoStatusBlock], 87Dh
0x1400344d7  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x1400344de  mov     [rsp+1E0h+ObjectAttributes], r14
0x1400344e3  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x1400344ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400344f1  mov     r8d, 5
0x1400344f7  mov     dl, 2
0x1400344f9  mov     qword ptr [rsp+1E0h+DesiredAccess], r15
0x1400344fe  mov     rcx, [rcx+40h]
0x140034502  call    WPP_RECORDER_SF_sDd
0x140034507  mov     r13d, 1
0x14003450d  mov     rsi, [rbp+0E0h+var_158]
0x140034511  mov     rcx, [rbp+0E0h+FileNameInformation]; FileNameInformation
0x140034515  test    rcx, rcx
0x140034518  jz      short loc_140034526
0x14003451a  call    cs:__imp_FltReleaseFileNameInformation
0x140034521  nop     dword ptr [rax+rax+00h]
0x140034526  test    rbx, rbx
0x140034529  jz      short loc_140034541
0x14003452b  mov     rdx, rbx; Entry
0x14003452e  lea     rcx, stru_14000E500; Lookaside
0x140034535  call    cs:__imp_ExFreeToPagedLookasideList
0x14003453c  nop     dword ptr [rax+rax+00h]
0x140034541  test    rdi, rdi
0x140034544  jz      loc_1400345E9
0x14003454a  mov     eax, 0FFFFFFFFh
0x14003454f  lock xadd [rdi], eax
0x140034553  cmp     eax, 1
0x140034556  jnz     loc_1400345E9
0x14003455c  movzx   edx, al; Restart
0x14003455f  lea     rcx, [rdi+40h]; Table
0x140034563  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14003456a  nop     dword ptr [rax+rax+00h]
0x14003456f  test    rax, rax
0x140034572  jz      short loc_14003459E
0x140034574  mov     rdx, rax; Buffer
0x140034577  lea     rcx, [rdi+40h]; Table
0x14003457b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140034582  nop     dword ptr [rax+rax+00h]
0x140034587  xor     edx, edx; Restart
0x140034589  lea     rcx, [rdi+40h]; Table
0x14003458d  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140034594  nop     dword ptr [rax+rax+00h]
0x140034599  test    rax, rax
0x14003459c  jnz     short loc_140034574
0x14003459e  mov     eax, [rdi+20h]
0x1400345a1  test    al, 1
0x1400345a3  jz      short loc_1400345D5
0x1400345a5  lea     rcx, FastMutex; FastMutex
0x1400345ac  call    cs:__imp_ExAcquireFastMutex
0x1400345b3  nop     dword ptr [rax+rax+00h]
0x1400345b8  dec     cs:dword_14000E244
0x1400345be  lea     rcx, FastMutex; FastMutex
0x1400345c5  and     dword ptr [rdi+20h], 0FFFFFFFEh
0x1400345c9  call    cs:__imp_ExReleaseFastMutex
0x1400345d0  nop     dword ptr [rax+rax+00h]
0x1400345d5  mov     edx, 63754357h; Tag
0x1400345da  mov     rcx, rdi; P
0x1400345dd  call    cs:__imp_ExFreePoolWithTag
0x1400345e4  nop     dword ptr [rax+rax+00h]
0x1400345e9  mov     rcx, [rbp+0E0h+var_128]; Context
0x1400345ed  test    rcx, rcx
0x1400345f0  jz      short loc_1400345FE
0x1400345f2  call    cs:__imp_FltReleaseContext
0x1400345f9  nop     dword ptr [rax+rax+00h]
0x1400345fe  test    rsi, rsi
0x140034601  jz      short loc_140034612
0x140034603  mov     rcx, rsi; Context
0x140034606  call    cs:__imp_FltReleaseContext
0x14003460d  nop     dword ptr [rax+rax+00h]
0x140034612  mov     rcx, [rbp+0E0h+Context]; Context
0x140034616  test    rcx, rcx
0x140034619  jz      short loc_140034627
0x14003461b  call    cs:__imp_FltReleaseContext
0x140034622  nop     dword ptr [rax+rax+00h]
0x140034627  mov     rcx, [rbp+0E0h+FileHandle]; FileHandle
0x14003462b  test    rcx, rcx
0x14003462e  jz      short loc_14003463C
0x140034630  call    cs:__imp_FltClose
0x140034637  nop     dword ptr [rax+rax+00h]
0x14003463c  test    r12, r12
0x14003463f  jz      short loc_140034650
0x140034641  mov     rcx, r12; Object
0x140034644  call    cs:__imp_ObfDereferenceObject
0x14003464b  nop     dword ptr [rax+rax+00h]
0x140034650  mov     rcx, [rbp+0E0h+var_138]; FileHandle
0x140034654  test    rcx, rcx
0x140034657  jz      short loc_140034665
0x140034659  call    cs:__imp_FltClose
0x140034660  nop     dword ptr [rax+rax+00h]
0x140034665  mov     rcx, [rbp+0E0h+Object]; Object
0x140034669  test    rcx, rcx
0x14003466c  jz      short loc_14003467A
0x14003466e  call    cs:__imp_ObfDereferenceObject
0x140034675  nop     dword ptr [rax+rax+00h]
0x14003467a  mov     rcx, [rbp+0E0h+var_110]; Context
0x14003467e  test    rcx, rcx
0x140034681  jz      short loc_14003468F
0x140034683  call    cs:__imp_FltReleaseContext
0x14003468a  nop     dword ptr [rax+rax+00h]
0x14003468f  mov     rcx, [rbp+0E0h+var_108]; Context
0x140034693  test    rcx, rcx
0x140034696  jz      short loc_1400346A4
0x140034698  call    cs:__imp_FltReleaseContext
0x14003469f  nop     dword ptr [rax+rax+00h]
0x1400346a4  mov     eax, r13d
0x1400346a7  mov     rcx, [rbp+0E0h+var_40]
0x1400346ae  xor     rcx, rsp; StackCookie
0x1400346b1  call    __security_check_cookie
0x1400346b6  mov     rbx, [rsp+1E0h+arg_18]
0x1400346be  add     rsp, 1B0h
0x1400346c5  pop     r15
0x1400346c7  pop     r14
0x1400346c9  pop     r13
0x1400346cb  pop     r12
0x1400346cd  pop     rdi
0x1400346ce  pop     rsi
0x1400346cf  pop     rbp
0x1400346d0  retn
0x1400346d2  mov     byte ptr [rax+11h], 1
0x1400346d6  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400346dd  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400346e4  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x1400346eb  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x1400346f2  jz      short loc_14003472B
0x1400346f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400346fb  mov     r9d, 37h ; '7'
0x140034701  mov     eax, [rbp+0E0h+var_150]
0x140034704  mov     r8d, 5
0x14003470a  mov     dword ptr [rsp+1E0h+AllocationSize], eax
0x14003470e  mov     dl, 2
0x140034710  mov     dword ptr [rsp+1E0h+IoStatusBlock], 883h
0x140034718  mov     rcx, [rcx+40h]
0x14003471c  mov     [rsp+1E0h+ObjectAttributes], r14
0x140034721  mov     qword ptr [rsp+1E0h+DesiredAccess], r15
0x140034726  call    WPP_RECORDER_SF_sDd
0x14003472b  mov     rcx, [rbp+0E0h+CallbackData]; CallbackData
0x14003472f  lea     r8, [rbp+0E0h+FileNameInformation]; FileNameInformation
0x140034733  mov     edx, 101h; NameOptions
0x140034738  call    cs:__imp_FltGetFileNameInformation
0x14003473f  nop     dword ptr [rax+rax+00h]
0x140034744  test    eax, eax
0x140034746  js      loc_140034507
0x14003474c  mov     rax, [rbp+0E0h+FileNameInformation]
0x140034750  lea     r9, [rbp+0E0h+Object]; FileObject
0x140034754  mov     rdx, [r13+18h]; Instance
0x140034758  lea     r8, [rbp+0E0h+var_138]; FileHandle
0x14003475c  xor     ecx, ecx
0x14003475e  mov     [rbp+0E0h+var_D8.Length], 30h ; '0'
0x140034765  mov     [rsp+1E0h+DriverContext], rcx; DriverContext
0x14003476a  add     rax, 8
0x14003476e  mov     [rsp+1E0h+Flags], 800h; Flags
0x140034776  xorps   xmm0, xmm0
0x140034779  mov     [rsp+1E0h+EaLength], ecx; EaLength
0x14003477d  mov     [rsp+1E0h+EaBuffer], rcx; EaBuffer
0x140034782  mov     [rsp+1E0h+CreateOptions], 200000h; CreateOptions
0x14003478a  mov     [rsp+1E0h+CreateDisposition], 1; CreateDisposition
0x140034792  mov     [rsp+1E0h+ShareAccess], 3; ShareAccess
0x14003479a  mov     [rsp+1E0h+FileAttributes], 80h; FileAttributes
0x1400347a2  mov     [rsp+1E0h+AllocationSize], rcx; AllocationSize
0x1400347a7  mov     [rbp+0E0h+var_D8.ObjectName], rax
0x1400347ab  lea     rax, [rbp+0E0h+var_A8]
0x1400347af  mov     [rsp+1E0h+IoStatusBlock], rax; IoStatusBlock
0x1400347b4  lea     rax, [rbp+0E0h+var_D8]
0x1400347b8  mov     [rbp+0E0h+var_D8.RootDirectory], rcx
0x1400347bc  mov     rcx, cs:Globals; Filter
0x1400347c3  mov     [rsp+1E0h+ObjectAttributes], rax; ObjectAttributes
0x1400347c8  mov     [rsp+1E0h+DesiredAccess], 10000h; DesiredAccess
0x1400347d0  mov     [rbp+0E0h+var_D8.Attributes], 240h
0x1400347d7  movdqu  xmmword ptr [rbp+0E0h+var_D8.SecurityDescriptor], xmm0
0x1400347dc  call    cs:__imp_FltCreateFileEx2
0x1400347e3  nop     dword ptr [rax+rax+00h]
0x1400347e8  test    eax, eax
0x1400347ea  jns     short loc_140034815
0x1400347ec  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400347f3  jz      loc_140034507
0x1400347f9  mov     dword ptr [rsp+1E0h+AllocationSize], eax
0x1400347fd  mov     r9d, 38h ; '8'
0x140034803  mov     dword ptr [rsp+1E0h+IoStatusBlock], 8A7h
0x14003480b  mov     [rsp+1E0h+ObjectAttributes], r14
0x140034810  jmp     loc_1400344EA
0x140034815  xor     ecx, ecx
0x140034817  mov     r13d, 5
0x14003481d  mov     [rbx], rcx
0x140034820  mov     [rbx+8], rcx
0x140034824  mov     rax, [rbp+0E0h+var_138]
0x140034828  mov     [rbx+18h], rax
0x14003482c  mov     rax, qword ptr [rbp+0E0h+EventDescriptor.Id]
0x140034830  mov     [rbp+0E0h+var_138], rcx
0x140034834  mov     [rax], rbx
0x140034837  mov     ebx, ecx
0x140034839  jmp     loc_14003450D
0x14003483e  mov     rdx, [r13+20h]; FileObject
0x140034842  lea     r9, [rbp+0E0h+var_158]
0x140034846  mov     rcx, [r13+18h]; Instance
0x14003484a  lea     r8, [rbp+0E0h+var_128]
0x14003484e  call    WcGetContextFileObject
0x140034853  test    al, al
0x140034855  jz      loc_140034507
0x14003485b  mov     rsi, [rbp+0E0h+var_158]
0x14003485f  test    rsi, rsi
0x140034862  jz      loc_140034B85
0x140034868  mov     r8, [r13+20h]
0x14003486c  mov     rcx, r14
0x14003486f  mov     rdx, [r13+18h]
0x140034873  call    WcGetUnionContext
0x140034878  mov     rdi, rax
0x14003487b  test    rax, rax
0x14003487e  jz      loc_140034B90
0x140034884  cmp     [rsi+1Ch], bl
0x140034887  jz      loc_140034B90
0x14003488d  lea     rcx, stru_14000E500; Lookaside
0x140034894  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003489b  nop     dword ptr [rax+rax+00h]
0x1400348a0  mov     rbx, rax
0x1400348a3  test    rax, rax
0x1400348a6  jnz     short loc_1400348D7
0x1400348a8  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400348af  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400348b6  jz      loc_140034507
0x1400348bc  mov     dword ptr [rsp+1E0h+AllocationSize], 0C000009Ah
0x1400348c4  mov     r9d, 39h ; '9'
0x1400348ca  mov     dword ptr [rsp+1E0h+IoStatusBlock], 8CBh
0x1400348d2  jmp     loc_1400344D7
0x1400348d7  lea     r8, [rbp+0E0h+FileNameInformation]; FileNameInformation
0x1400348db  mov     edx, 301h; NameOptions
0x1400348e0  mov     rcx, r14; CallbackData
0x1400348e3  call    cs:__imp_FltGetFileNameInformation
0x1400348ea  nop     dword ptr [rax+rax+00h]
0x1400348ef  test    eax, eax
0x1400348f1  js      loc_140034B85
0x1400348f7  mov     rcx, [rbp+0E0h+FileNameInformation]; FileNameInformation
0x1400348fb  call    cs:__imp_FltParseFileNameInformation
  ... truncated ...
```

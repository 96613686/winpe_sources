# UdfCommonSetInfo

- ea: `0x140031f84`
- end: `0x1400322eb`
- name: `UdfCommonSetInfo`
- size: `871`
- prototype: `__int64 __fastcall(PVOID Context, IRP *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x14000ca10`
- `0x140012cc8`
- `0x140031f84`
- `0x140032ccc`
- `0x140032d78`
- `0x140033158`
- `0x140033548`
- `0x140034410`
- `0x140034450`
- `0x140045f10`
- `0x14004ce50`
- `0x140054460`
- `0x140059988`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140032257`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032275`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b66d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b692`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032257`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032275`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b66d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b692`
- `ntoskrnl!FsRtlCheckOplock` at `0x14003206b`
- `ntoskrnl!FsRtlCheckOplock` at `0x14003206b`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14003208f`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14003208f`

## pseudocode

```c
__int64 __fastcall UdfCommonSetInfo(PVOID Context, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  unsigned int v4; // ebx
  ULONG Options; // edi
  __int64 MasterIrp; // r12
  IRP *v7; // r11
  int v8; // r15d
  __int64 v9; // rsi
  __int64 v10; // rax
  char v11; // al
  char v12; // r15
  __int64 v13; // rbx
  __int64 v14; // r8
  ULONG v15; // edi
  ULONG v16; // edi
  ULONG v17; // edi
  ULONG v18; // edi
  ULONG v19; // edi
  ULONG v20; // edi
  unsigned int v21; // eax
  char v23; // [rsp+30h] [rbp-58h]
  __int64 v24; // [rsp+38h] [rbp-50h] BYREF
  __int64 v25; // [rsp+40h] [rbp-48h]
  char v27; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+20h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  v28 = 0;
  v24 = 0;
  v27 = 0;
  v23 = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  MasterIrp = (__int64)a2->AssociatedIrp.MasterIrp;
  v25 = MasterIrp;
  v8 = UdfDecodeFileObject(CurrentStackLocation->FileObject, &v28, &v24);
  v9 = v28;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
  {
    WPP_SF_qD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      10,
      WPP_0dbe93714b6730a9f09221a306b03890_Traceguids,
      v28,
      Options);
    v7 = a2;
  }
  if ( v8 == 4 && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 136) + 8LL) + 48LL) & 0x10) == 0 && Options - 19 <= 1 )
  {
    if ( Options == 20 && CurrentStackLocation->Parameters.SetFile.AdvanceOnly )
      goto LABEL_42;
    v4 = FsRtlCheckOplock((POPLOCK)(v9 + 88), v7, Context, 0, 0);
    if ( v4 )
      goto LABEL_42;
    if ( *(_DWORD *)(v9 + 216) || !FsRtlOplockIsFastIoPossible((POPLOCK)(v9 + 88)) )
    {
      v11 = 0;
    }
    else
    {
      v10 = *(_QWORD *)(v9 + 504);
      if ( v10 && *(_BYTE *)(v10 + 16) )
        v11 = 2;
      else
        v11 = 1;
    }
    *(_BYTE *)(v9 + 5) = v11;
    MasterIrp = v25;
  }
  if ( (unsigned int)(v8 - 3) >= 2 )
  {
    v4 = -1073741811;
LABEL_42:
    v12 = v27;
    goto LABEL_43;
  }
  if ( Options - 10 <= 1 )
  {
    UdfAcquireResource(Context, *((_QWORD *)Context + 2) + 1480LL, 0, 0);
    v23 = 1;
  }
  UdfAcquireResource(Context, *(_QWORD *)(*(_QWORD *)(v9 + 136) + 80LL) + 8LL, 0, 0);
  v12 = 1;
  v27 = 1;
  v13 = v24;
  UdfVerifyScbOperation(Context, v9, v24);
  if ( Options != 14 )
    *(_DWORD *)(*((_QWORD *)Context + 2) + 2132LL) = 0;
  v15 = Options - 4;
  if ( !v15 )
  {
    v4 = UdfSetBasicInfo((_DWORD)Context, MasterIrp, (__int64)&v27);
    goto LABEL_42;
  }
  v16 = v15 - 6;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 2;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 5;
          if ( v20 )
          {
            if ( v20 != 1 )
            {
              v4 = -1073741811;
              goto LABEL_43;
            }
            if ( CurrentStackLocation->Parameters.SetFile.AdvanceOnly )
            {
              v4 = 0;
              goto LABEL_43;
            }
            v21 = UdfSetEndOfFileInfo((_DWORD)Context, CurrentStackLocation->FileObject, v9, v13, MasterIrp);
          }
          else
          {
            v21 = UdfSetAllocationInfo((_DWORD)Context, CurrentStackLocation->FileObject, v9, v13, MasterIrp);
          }
        }
        else
        {
          v21 = UdfSetPositionInfo(Context, CurrentStackLocation->FileObject, v14, MasterIrp);
        }
      }
      else
      {
        v21 = UdfSetDispositionInfo(Context, CurrentStackLocation->FileObject, v9, v13, MasterIrp);
      }
    }
    else
    {
      v21 = UdfSetLinkInfo((int)Context);
    }
  }
  else
  {
    v21 = UdfSetRenameInfo((int)Context);
  }
  v4 = v21;
LABEL_43:
  if ( v12 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v9 + 136) + 80LL) + 8LL));
  if ( v23 )
    ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)Context + 2) + 1480LL));
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 11, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
  }
  if ( v4 != 259 )
  {
    a2->IoStatus.Information = 0;
    UdfCompleteRequest(Context, a2, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x140031f84  mov     rax, rsp
0x140031f87  mov     [rax+10h], rdx
0x140031f8b  mov     [rax+8], rcx
0x140031f8f  push    rbx
0x140031f90  push    rsi
0x140031f91  push    rdi
0x140031f92  push    r12
0x140031f94  push    r13
0x140031f96  push    r14
0x140031f98  push    r15
0x140031f9a  sub     rsp, 50h
0x140031f9e  mov     r11, rdx
0x140031fa1  mov     r14, rcx
0x140031fa4  mov     r13, [rdx+0B8h]
0x140031fab  xor     ebx, ebx
0x140031fad  mov     [rax+20h], rbx
0x140031fb1  mov     [rax-50h], rbx
0x140031fb5  mov     [rax+18h], bl
0x140031fb8  mov     [rax-58h], bl
0x140031fbb  mov     edi, [r13+10h]
0x140031fbf  mov     r12, [rdx+18h]
0x140031fc3  mov     [rsp+88h+var_48], r12
0x140031fc8  lea     r8, [rax-50h]
0x140031fcc  lea     rdx, [rax+20h]
0x140031fd0  mov     rcx, [r13+30h]
0x140031fd4  call    UdfDecodeFileObject
0x140031fd9  mov     r15d, eax
0x140031fdc  lea     rax, WPP_GLOBAL_Control
0x140031fe3  mov     rcx, cs:WPP_GLOBAL_Control
0x140031fea  mov     rsi, [rsp+88h+arg_18]
0x140031ff2  cmp     rcx, rax
0x140031ff5  jz      short loc_140032022
0x140031ff7  test    dword ptr [rcx+2Ch], 200h
0x140031ffe  jz      short loc_140032022
0x140032000  lea     edx, [rbx+0Ah]
0x140032003  mov     dword ptr [rsp+88h+PostIrpRoutine], edi
0x140032007  mov     r9, rsi
0x14003200a  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x140032011  mov     rcx, [rcx+18h]
0x140032015  call    WPP_SF_qD
0x14003201a  mov     r11, [rsp+88h+arg_8]
0x140032022  cmp     r15d, 4
0x140032026  jnz     loc_1400320C6
0x14003202c  mov     rax, [rsi+88h]
0x140032033  mov     rcx, [rax+8]
0x140032037  mov     eax, [rcx+30h]
0x14003203a  test    al, 10h
0x14003203c  jnz     loc_1400320C6
0x140032042  lea     eax, [rdi-13h]
0x140032045  cmp     eax, 1
0x140032048  ja      short loc_1400320C6
0x14003204a  cmp     edi, 14h
0x14003204d  jnz     short loc_140032059
0x14003204f  cmp     [r13+21h], bl
0x140032053  jnz     loc_14003223B
0x140032059  mov     [rsp+88h+PostIrpRoutine], rbx; PostIrpRoutine
0x14003205e  xor     r9d, r9d; CompletionRoutine
0x140032061  mov     r8, r14; Context
0x140032064  mov     rdx, r11; Irp
0x140032067  lea     rcx, [rsi+58h]; Oplock
0x14003206b  call    cs:__imp_FsRtlCheckOplock
0x140032072  nop     dword ptr [rax+rax+00h]
0x140032077  mov     ebx, eax
0x140032079  test    eax, eax
0x14003207b  jnz     loc_14003223B
0x140032081  xor     ebx, ebx
0x140032083  cmp     [rsi+0D8h], ebx
0x140032089  jnz     short loc_1400320BC
0x14003208b  lea     rcx, [rsi+58h]; Oplock
0x14003208f  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140032096  nop     dword ptr [rax+rax+00h]
0x14003209b  test    al, al
0x14003209d  jz      short loc_1400320BC
0x14003209f  mov     rax, [rsi+1F8h]
0x1400320a6  test    rax, rax
0x1400320a9  jz      short loc_1400320B5
0x1400320ab  cmp     [rax+10h], bl
0x1400320ae  jz      short loc_1400320B5
0x1400320b0  lea     eax, [rbx+2]
0x1400320b3  jmp     short loc_1400320BE
0x1400320b5  mov     eax, 1
0x1400320ba  jmp     short loc_1400320BE
0x1400320bc  mov     eax, ebx
0x1400320be  mov     [rsi+5], al
0x1400320c1  mov     r12, [rsp+88h+var_48]
0x1400320c6  sub     r15d, 3
0x1400320ca  jz      short loc_1400320DC
0x1400320cc  cmp     r15d, 1
0x1400320d0  jz      short loc_1400320DC
0x1400320d2  mov     ebx, 0C000000Dh
0x1400320d7  jmp     loc_14003223B
0x1400320dc  lea     eax, [rdi-0Ah]
0x1400320df  cmp     eax, 1
0x1400320e2  ja      short loc_140032102
0x1400320e4  mov     rdx, [r14+10h]
0x1400320e8  add     rdx, 5C8h
0x1400320ef  xor     r9d, r9d
0x1400320f2  xor     r8d, r8d
0x1400320f5  mov     rcx, r14
0x1400320f8  call    UdfAcquireResource
0x1400320fd  mov     [rsp+88h+var_58], 1
0x140032102  mov     rax, [rsi+88h]
0x140032109  mov     rdx, [rax+50h]
0x14003210d  add     rdx, 8
0x140032111  xor     r9d, r9d
0x140032114  xor     r8d, r8d
0x140032117  mov     rcx, r14
0x14003211a  call    UdfAcquireResource
0x14003211f  mov     r15b, 1
0x140032122  mov     [rsp+88h+arg_10], r15b
0x14003212a  mov     rbx, [rsp+88h+var_50]
0x14003212f  mov     r8, rbx
0x140032132  mov     rdx, rsi
0x140032135  mov     rcx, r14
0x140032138  call    UdfVerifyScbOperation
0x14003213d  cmp     edi, 0Eh
0x140032140  jz      short loc_140032150
0x140032142  mov     rax, [r14+10h]
0x140032146  mov     dword ptr [rax+854h], 0
0x140032150  sub     edi, 4
0x140032153  jz      loc_140032215
0x140032159  sub     edi, 6
0x14003215c  jz      loc_140032205
0x140032162  sub     edi, 1
0x140032165  jz      loc_1400321F5
0x14003216b  sub     edi, 2
0x14003216e  jz      short loc_1400321DC
0x140032170  sub     edi, 1
0x140032173  jz      short loc_1400321C9
0x140032175  sub     edi, 5
0x140032178  jz      short loc_1400321B0
0x14003217a  cmp     edi, 1
0x14003217d  jz      short loc_140032189
0x14003217f  mov     ebx, 0C000000Dh
0x140032184  jmp     loc_140032243
0x140032189  cmp     byte ptr [r13+21h], 0
0x14003218e  jz      short loc_140032197
0x140032190  xor     ebx, ebx
0x140032192  jmp     loc_140032243
0x140032197  mov     [rsp+88h+PostIrpRoutine], r12
0x14003219c  mov     r9, rbx
0x14003219f  mov     r8, rsi
0x1400321a2  mov     rdx, [r13+30h]
0x1400321a6  mov     rcx, r14
0x1400321a9  call    UdfSetEndOfFileInfo
0x1400321ae  jmp     short loc_1400321D8
0x1400321b0  mov     [rsp+88h+PostIrpRoutine], r12
0x1400321b5  mov     r9, rbx
0x1400321b8  mov     r8, rsi
0x1400321bb  mov     rdx, [r13+30h]
0x1400321bf  mov     rcx, r14
0x1400321c2  call    UdfSetAllocationInfo
0x1400321c7  jmp     short loc_1400321D8
0x1400321c9  mov     r9, r12
0x1400321cc  mov     rdx, [r13+30h]
0x1400321d0  mov     rcx, r14
0x1400321d3  call    UdfSetPositionInfo
0x1400321d8  mov     ebx, eax
0x1400321da  jmp     short loc_140032243
0x1400321dc  mov     [rsp+88h+PostIrpRoutine], r12
0x1400321e1  mov     r9, rbx
0x1400321e4  mov     r8, rsi
0x1400321e7  mov     rdx, [r13+30h]
0x1400321eb  mov     rcx, r14
0x1400321ee  call    UdfSetDispositionInfo
0x1400321f3  jmp     short loc_1400321D8
0x1400321f5  mov     r8, rbx
0x1400321f8  mov     rdx, rsi
0x1400321fb  mov     rcx, r14; int
0x1400321fe  call    UdfSetLinkInfo
0x140032203  jmp     short loc_1400321D8
0x140032205  mov     r8, rbx
0x140032208  mov     rdx, rsi
0x14003220b  mov     rcx, r14; int
0x14003220e  call    UdfSetRenameInfo
0x140032213  jmp     short loc_1400321D8
0x140032215  lea     rax, [rsp+88h+arg_10]
0x14003221d  mov     [rsp+88h+var_60], rax
0x140032222  mov     [rsp+88h+PostIrpRoutine], r12
0x140032227  mov     r9, rbx
0x14003222a  mov     r8, rsi
0x14003222d  mov     rdx, [r13+30h]
0x140032231  mov     rcx, r14
0x140032234  call    UdfSetBasicInfo
0x140032239  mov     ebx, eax
0x14003223b  mov     r15b, [rsp+88h+arg_10]
0x140032243  test    r15b, r15b
0x140032246  jz      short loc_140032263
0x140032248  mov     rax, [rsi+88h]
0x14003224f  mov     rcx, [rax+50h]
0x140032253  add     rcx, 8; Resource
0x140032257  call    cs:__imp_ExReleaseResourceLite
0x14003225e  nop     dword ptr [rax+rax+00h]
0x140032263  cmp     [rsp+88h+var_58], 0
0x140032268  jz      short loc_140032281
0x14003226a  mov     rcx, [r14+10h]
0x14003226e  add     rcx, 5C8h; Resource
0x140032275  call    cs:__imp_ExReleaseResourceLite
0x14003227c  nop     dword ptr [rax+rax+00h]
0x140032281  mov     rcx, cs:WPP_GLOBAL_Control
0x140032288  lea     rax, WPP_GLOBAL_Control
0x14003228f  cmp     rcx, rax
0x140032292  jz      short loc_1400322B5
0x140032294  test    dword ptr [rcx+2Ch], 200h
0x14003229b  jz      short loc_1400322B5
0x14003229d  mov     edx, 0Bh
0x1400322a2  mov     r9d, ebx
0x1400322a5  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x1400322ac  mov     rcx, [rcx+18h]
0x1400322b0  call    WPP_SF_d
0x1400322b5  cmp     ebx, 103h
0x1400322bb  jz      short loc_1400322D8
0x1400322bd  mov     rdx, [rsp+88h+arg_8]
0x1400322c5  mov     qword ptr [rdx+38h], 0
0x1400322cd  mov     r8d, ebx
0x1400322d0  mov     rcx, r14
0x1400322d3  call    UdfCompleteRequest
0x1400322d8  mov     eax, ebx
0x1400322da  add     rsp, 50h
0x1400322de  pop     r15
0x1400322e0  pop     r14
0x1400322e2  pop     r13
0x1400322e4  pop     r12
0x1400322e6  pop     rdi
0x1400322e7  pop     rsi
0x1400322e8  pop     rbx
0x1400322e9  retn
0x14005b645  push    rbp
0x14005b647  sub     rsp, 30h
0x14005b64b  mov     rbp, rdx
0x14005b64e  cmp     byte ptr [rbp+0A0h], 0
0x14005b655  jz      short loc_14005B67A
0x14005b657  mov     rax, [rbp+0A8h]
0x14005b65e  mov     rcx, [rax+88h]
0x14005b665  mov     rcx, [rcx+50h]
0x14005b669  add     rcx, 8; Resource
0x14005b66d  call    cs:__imp_ExReleaseResourceLite
0x14005b674  nop     dword ptr [rax+rax+00h]
0x14005b679  nop
0x14005b67a  cmp     byte ptr [rbp+30h], 0
0x14005b67e  jz      short loc_14005B69F
0x14005b680  mov     rax, [rbp+90h]
0x14005b687  mov     rcx, [rax+10h]
0x14005b68b  add     rcx, 5C8h; Resource
0x14005b692  call    cs:__imp_ExReleaseResourceLite
0x14005b699  nop     dword ptr [rax+rax+00h]
0x14005b69e  nop
0x14005b69f  add     rsp, 30h
0x14005b6a3  pop     rbp
0x14005b6a4  retn
```

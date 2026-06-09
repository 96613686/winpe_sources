# SrvAdminProcessFsctlFsp

- ea: `0x140025760`
- end: `0x14002598a`
- name: `SrvAdminProcessFsctlFsp`
- size: `554`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `40`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004d30`
- `0x14000a1f0`
- `0x14000c550`
- `0x14000d1b0`
- `0x1400138e0`
- `0x140023ae0`
- `0x140023be0`
- `0x140023c20`
- `0x140023f90`
- `0x1400254a0`
- `0x1400254d0`
- `0x140025510`
- `0x1400256e0`
- `0x140025730`
- `0x140025740`
- `0x140025760`
- `0x140026730`
- `0x1400269f0`
- `0x140026a60`
- `0x140026e00`
- `0x140026e90`
- `0x140027040`
- `0x140027150`
- `0x140027220`
- `0x140027390`
- `0x140027450`
- `0x140027470`
- `0x1400276e0`
- `0x140027750`
- `0x1400277b0`
- `0x140027b80`
- `0x140027bf0`
- `0x140027c50`
- `0x140027ce0`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x14004dda0`
- `0x140054510`
- `0x140055180`
- `0x140055720`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x1400258ce`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400258ce`
- `ntoskrnl!IofCompleteRequest` at `0x140025958`
- `ntoskrnl!IofCompleteRequest` at `0x140025958`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002590a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002590a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025922`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002593c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025922`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002593c`
- `ntoskrnl!IoFreeWorkItem` at `0x1400257bb`
- `ntoskrnl!IoFreeWorkItem` at `0x1400257bb`

## pseudocode

```c
void __fastcall SrvAdminProcessFsctlFsp(PVOID IoObject, IRP *Context, PIO_WORKITEM IoWorkItem)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v4; // ebp
  PVOID v5; // r14
  PFILE_OBJECT FileObject; // rax
  PVOID FsContext; // rax
  struct _IO_STACK_LOCATION *v9; // r15
  struct _IRP *MasterIrp; // rdi
  PVOID UserBuffer; // r12
  ULONG Length; // r13d
  PMDL MdlAddress; // rax
  __int64 Options; // r11
  const wchar_t *v15; // rcx
  struct _IRP *v16; // rax
  char *v17; // rdx
  const wchar_t *v18; // rcx
  int v19; // ebx
  PMDL v20; // rcx
  _DWORD *MappedSystemVa; // rax
  PVOID v22; // rcx
  __int64 v23; // [rsp+30h] [rbp-58h] BYREF
  __int128 v24; // [rsp+38h] [rbp-50h] BYREF

  CurrentStackLocation = Context->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  v5 = 0;
  v23 = 0;
  v24 = 0;
  if ( CurrentStackLocation )
  {
    FileObject = CurrentStackLocation->FileObject;
    if ( FileObject )
    {
      FsContext = FileObject->FsContext;
      if ( FsContext )
        v5 = FsContext;
    }
  }
  IoFreeWorkItem(IoWorkItem);
  v9 = Context->Tail.Overlay.CurrentStackLocation;
  MasterIrp = Context->AssociatedIrp.MasterIrp;
  UserBuffer = Context->UserBuffer;
  Length = v9->Parameters.Read.Length;
  MdlAddress = MasterIrp->MdlAddress;
  Options = v9->Parameters.Create.Options;
  if ( MdlAddress )
  {
    v15 = (const wchar_t *)((char *)MasterIrp + (_QWORD)MdlAddress);
    MasterIrp->MdlAddress = (PMDL)((char *)MasterIrp + (_QWORD)MdlAddress);
    if ( (struct _IRP *)((char *)MasterIrp + (_QWORD)MdlAddress)
      && (v15 <= (const wchar_t *)MasterIrp || v15 >= (const wchar_t *)((char *)MasterIrp + Options)) )
    {
      v4 = -1073741819;
    }
  }
  else
  {
    v15 = 0;
  }
  v16 = MasterIrp->AssociatedIrp.MasterIrp;
  if ( v16 )
  {
    v17 = (char *)MasterIrp + (_QWORD)v16;
    MasterIrp->AssociatedIrp.MasterIrp = (struct _IRP *)((char *)MasterIrp + (_QWORD)v16);
    if ( (struct _IRP *)((char *)MasterIrp + (_QWORD)v16) )
    {
      if ( v17 <= (char *)MasterIrp || v17 >= (char *)MasterIrp + Options )
        v4 = -1073741819;
    }
  }
  if ( (MasterIrp->Type & 1) != 0
    || (MasterIrp->Flags & 1) != 0
    || v15 && RtlStringCbLengthW(v15, (size_t)MasterIrp + Options - (_QWORD)v15, 0) < 0
    || (v18 = (const wchar_t *)MasterIrp->AssociatedIrp.MasterIrp) != 0
    && RtlStringCbLengthW(v18, (size_t)MasterIrp + Options - (_QWORD)v18, 0) < 0 )
  {
    v4 = -1073741811;
  }
  else if ( v4 >= 0 )
  {
    v19 = SvcSetActivityIdForCurrentThread(Context, &v24, &v23);
    v4 = ((__int64 (__fastcall *)(PVOID, struct _IRP *, PVOID, _QWORD))SvcApiDispatch[(v9->Parameters.Read.ByteOffset.LowPart >> 2)
                                                                                    & 0x7FF])(
           v5,
           MasterIrp,
           UserBuffer,
           Length);
    if ( v19 >= 0 )
      IoClearActivityIdThread(v23);
  }
  v20 = Context->MdlAddress;
  if ( (v20->MdlFlags & 5) != 0 )
    MappedSystemVa = v20->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v20, 0, MmCached, 0, 0, 0x40000010u);
  MappedSystemVa[17] = *(_DWORD *)&MasterIrp->Cancel;
  ExFreePoolWithTag(Context->AssociatedIrp.MasterIrp, 0);
  v22 = Context->UserBuffer;
  Context->AssociatedIrp.MasterIrp = 0;
  ExFreePoolWithTag(v22, 0);
  Context->UserBuffer = 0;
  Context->IoStatus.Status = v4;
  IofCompleteRequest(Context, 2);
}

```

## disassembly

```asm
0x140025760  mov     [rsp+arg_0], rbx
0x140025765  push    rbp
0x140025766  push    rsi
0x140025767  push    rdi
0x140025768  push    r12
0x14002576a  push    r13
0x14002576c  push    r14
0x14002576e  push    r15
0x140025770  sub     rsp, 50h
0x140025774  mov     rax, cs:__security_cookie
0x14002577b  xor     rax, rsp
0x14002577e  mov     [rsp+88h+var_40], rax
0x140025783  mov     rax, [rdx+0B8h]
0x14002578a  xor     ebp, ebp
0x14002578c  xor     r14d, r14d
0x14002578f  mov     [rsp+88h+var_58], rbp
0x140025794  xorps   xmm0, xmm0
0x140025797  mov     rsi, rdx
0x14002579a  movups  [rsp+88h+var_50], xmm0
0x14002579f  test    rax, rax
0x1400257a2  jz      short loc_1400257B8
0x1400257a4  mov     rax, [rax+30h]
0x1400257a8  test    rax, rax
0x1400257ab  jz      short loc_1400257B8
0x1400257ad  mov     rax, [rax+18h]
0x1400257b1  test    rax, rax
0x1400257b4  cmovnz  r14, rax
0x1400257b8  mov     rcx, r8; IoWorkItem
0x1400257bb  call    cs:__imp_IoFreeWorkItem
0x1400257c2  nop     dword ptr [rax+rax+00h]
0x1400257c7  mov     r15, [rsi+0B8h]
0x1400257ce  mov     r8d, 0C0000005h
0x1400257d4  mov     rdi, [rsi+18h]
0x1400257d8  mov     r12, [rsi+70h]
0x1400257dc  mov     r13d, [r15+8]
0x1400257e0  mov     rax, [rdi+8]
0x1400257e4  mov     r11d, [r15+10h]
0x1400257e8  test    rax, rax
0x1400257eb  jz      short loc_14002580D
0x1400257ed  lea     rcx, [rax+rdi]
0x1400257f1  mov     [rdi+8], rcx
0x1400257f5  test    rcx, rcx
0x1400257f8  jz      short loc_14002580F
0x1400257fa  cmp     rcx, rdi
0x1400257fd  jbe     short loc_140025808
0x1400257ff  lea     rax, [rdi+r11]
0x140025803  cmp     rcx, rax
0x140025806  jb      short loc_14002580F
0x140025808  mov     ebp, r8d
0x14002580b  jmp     short loc_14002580F
0x14002580d  xor     ecx, ecx; psz
0x14002580f  mov     rax, [rdi+18h]
0x140025813  test    rax, rax
0x140025816  jz      short loc_140025836
0x140025818  lea     rdx, [rax+rdi]
0x14002581c  mov     [rdi+18h], rdx
0x140025820  test    rdx, rdx
0x140025823  jz      short loc_140025836
0x140025825  cmp     rdx, rdi
0x140025828  jbe     short loc_140025833
0x14002582a  lea     rax, [rdi+r11]
0x14002582e  cmp     rdx, rax
0x140025831  jb      short loc_140025836
0x140025833  mov     ebp, r8d
0x140025836  test    byte ptr [rdi], 1
0x140025839  jnz     loc_1400258DC
0x14002583f  test    byte ptr [rdi+10h], 1
0x140025843  jnz     loc_1400258DC
0x140025849  test    rcx, rcx
0x14002584c  jz      short loc_140025863
0x14002584e  mov     rdx, r11
0x140025851  xor     r8d, r8d; pcbLength
0x140025854  sub     rdx, rcx
0x140025857  add     rdx, rdi; cbMax
0x14002585a  call    RtlStringCbLengthW
0x14002585f  test    eax, eax
0x140025861  js      short loc_1400258DC
0x140025863  mov     rcx, [rdi+18h]; psz
0x140025867  test    rcx, rcx
0x14002586a  jz      short loc_140025881
0x14002586c  mov     rdx, r11
0x14002586f  xor     r8d, r8d; pcbLength
0x140025872  sub     rdx, rcx
0x140025875  add     rdx, rdi; cbMax
0x140025878  call    RtlStringCbLengthW
0x14002587d  test    eax, eax
0x14002587f  js      short loc_1400258DC
0x140025881  test    ebp, ebp
0x140025883  js      short loc_1400258E1
0x140025885  lea     r8, [rsp+88h+var_58]
0x14002588a  mov     rcx, rsi
0x14002588d  lea     rdx, [rsp+88h+var_50]
0x140025892  call    SvcSetActivityIdForCurrentThread
0x140025897  mov     ecx, [r15+18h]
0x14002589b  mov     ebx, eax
0x14002589d  shr     rcx, 2
0x1400258a1  lea     rax, SvcApiDispatch
0x1400258a8  and     ecx, 7FFh
0x1400258ae  mov     r9d, r13d
0x1400258b1  mov     r8, r12
0x1400258b4  mov     rdx, rdi
0x1400258b7  mov     rax, ds:(SvcApiDispatch - 14002E4B0h)[rax+rcx*8]
0x1400258bb  mov     rcx, r14
0x1400258be  call    _guard_dispatch_icall
0x1400258c3  mov     ebp, eax
0x1400258c5  test    ebx, ebx
0x1400258c7  js      short loc_1400258E1
0x1400258c9  mov     rcx, [rsp+88h+var_58]
0x1400258ce  call    cs:__imp_IoClearActivityIdThread
0x1400258d5  nop     dword ptr [rax+rax+00h]
0x1400258da  jmp     short loc_1400258E1
0x1400258dc  mov     ebp, 0C000000Dh
0x1400258e1  mov     rcx, [rsi+8]; MemoryDescriptorList
0x1400258e5  test    byte ptr [rcx+0Ah], 5
0x1400258e9  jz      short loc_1400258F1
0x1400258eb  mov     rax, [rcx+18h]
0x1400258ef  jmp     short loc_140025916
0x1400258f1  xor     r9d, r9d; RequestedAddress
0x1400258f4  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400258fc  xor     edx, edx; AccessMode
0x1400258fe  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140025906  lea     r8d, [r9+1]; CacheType
0x14002590a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140025911  nop     dword ptr [rax+rax+00h]
0x140025916  mov     edx, [rdi+44h]
0x140025919  mov     [rax+44h], edx
0x14002591c  xor     edx, edx; Tag
0x14002591e  mov     rcx, [rsi+18h]; P
0x140025922  call    cs:__imp_ExFreePoolWithTag
0x140025929  nop     dword ptr [rax+rax+00h]
0x14002592e  mov     rcx, [rsi+70h]; P
0x140025932  xor     edx, edx; Tag
0x140025934  mov     qword ptr [rsi+18h], 0
0x14002593c  call    cs:__imp_ExFreePoolWithTag
0x140025943  nop     dword ptr [rax+rax+00h]
0x140025948  mov     dl, 2; PriorityBoost
0x14002594a  mov     qword ptr [rsi+70h], 0
0x140025952  mov     rcx, rsi; Irp
0x140025955  mov     [rsi+30h], ebp
0x140025958  call    cs:__imp_IofCompleteRequest
0x14002595f  nop     dword ptr [rax+rax+00h]
0x140025964  mov     rcx, [rsp+88h+var_40]
0x140025969  xor     rcx, rsp; StackCookie
0x14002596c  call    __security_check_cookie
0x140025971  mov     rbx, [rsp+88h+arg_0]
0x140025979  add     rsp, 50h
0x14002597d  pop     r15
0x14002597f  pop     r14
0x140025981  pop     r13
0x140025983  pop     r12
0x140025985  pop     rdi
0x140025986  pop     rsi
0x140025987  pop     rbp
0x140025988  retn
```

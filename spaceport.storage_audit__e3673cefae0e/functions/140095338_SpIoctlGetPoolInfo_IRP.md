# SpIoctlGetPoolInfo(_IRP *)

- ea: `0x140095338`
- end: `0x140095a4b`
- name: `?SpIoctlGetPoolInfo@@YAJPEAU_IRP@@@Z`
- size: `1811`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b57b0`

## callees

- `0x14000ba20`
- `0x14000fa40`
- `0x140015fb0`
- `0x1400187f0`
- `0x140019060`
- `0x14001d3f0`
- `0x14001eac0`
- `0x14002ce90`
- `0x14002e104`
- `0x14002e43c`
- `0x14002e46c`
- `0x14005a478`
- `0x140062d4c`
- `0x140067fc0`
- `0x1400680a0`
- `0x1400681c0`
- `0x1400684c0`
- `0x140095338`
- `0x1400b55b0`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140095925`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140095925`

## pseudocode

```c
__int64 __fastcall SpIoctlGetPoolInfo(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  int v3; // ebp
  struct _IRP *MasterIrp; // rdi
  int Flink_high; // r15d
  ULONG Length; // ebx
  char v7; // r13
  _OWORD *DeviceExtension; // rsi
  struct SP_POOL *PoolById; // rax
  struct SP_POOL *v10; // r14
  struct SDB_OBJECT *Object; // rbp
  const wchar_t *v12; // r8
  const wchar_t *v13; // r8
  int v14; // ecx
  int v15; // eax
  _OWORD *v16; // rsi
  __int64 v17; // rdx
  struct _KEVENT *v18; // xmm0_8
  int v19; // r12d
  unsigned int v20; // ebx
  unsigned int v21; // ecx
  bool v22; // cf
  SDB_RECORD *RecordByType; // rcx
  struct SDB_OBJECT *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  void *v27; // r15
  char *v28; // rdx
  struct _LIST_ENTRY *Flink; // r9
  void **v30; // rdx
  __int64 v31; // rcx
  char *v32; // r8
  unsigned int v33; // r14d
  ULONG v34; // eax
  ULONG v35; // r8d
  ULONG v36; // r12d
  unsigned int v37; // esi
  ULONG DeviceType; // ecx
  const char *v39; // r9
  struct _GUID Buf1; // [rsp+60h] [rbp-68h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  Buf1 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids);
  }
  SpAcquireResourceShared((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96), 0);
  if ( CurrentStackLocation->Parameters.Create.Options < 0x28 )
  {
    v3 = -1073741820;
    goto LABEL_68;
  }
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type != 40 )
  {
    v3 = -1073741811;
    goto LABEL_68;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0xB10 )
  {
    v3 = -1073741789;
    goto LABEL_68;
  }
  Flink_high = HIDWORD(MasterIrp->ThreadListEntry.Flink);
  Buf1 = *(struct _GUID *)(&MasterIrp->Size + 1);
  Length = CurrentStackLocation->Parameters.Read.Length;
  v7 = 0;
  memset(MasterIrp, 0, Length);
  *(_DWORD *)&MasterIrp->Type = 2832;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids, &Buf1);
  }
  DeviceExtension = WPP_MAIN_CB.DeviceExtension;
  if ( *(_OWORD *)&Buf1 == *((_OWORD *)WPP_MAIN_CB.DeviceExtension + 23) || !memcmp(&Buf1, &GUID_NULL, 0x10u) )
  {
    *(_OWORD *)&MasterIrp->MdlAddress = DeviceExtension[23];
    RtlStringCbCopyW((NTSTRSAFE_PWSTR)&MasterIrp->AssociatedIrp, 0x200u, L"Primordial");
    LOWORD(MasterIrp[12].Overlay.AsynchronousParameters.UserApcRoutine) = 1;
    *((_QWORD *)&MasterIrp[12].Tail.CompletionKey + 10) = -1;
    MasterIrp[13].Overlay.AsynchronousParameters.UserApcContext = (PVOID)-1LL;
    BYTE2(MasterIrp[12].Overlay.AllocationSize.u.LowPart) = 0;
    *((_DWORD *)&MasterIrp[12].Overlay.AllocationSize + 2) = 3;
    *((_DWORD *)&MasterIrp[12].Overlay.AllocationSize + 3) = 3;
    LODWORD(MasterIrp[12].UserBuffer) = 1;
    MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
    MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = 0;
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 13) = 70;
    *((_BYTE *)&MasterIrp[12].Tail.CompletionKey + 56) = 1;
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 15) = 1;
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 8) = 0x20000000;
    *(PVOID *)((char *)&MasterIrp[12].Tail.Apc.Reserved[1] + 4) = 0;
    MasterIrp[12].Tail.Overlay.CurrentStackLocation = (struct _IO_STACK_LOCATION *)0x10000000;
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 18) = 2;
    *(_DWORD *)&MasterIrp[13].Type = 0;
    *(_QWORD *)(&MasterIrp[13].Size + 1) = 1;
    HIDWORD(MasterIrp[13].MdlAddress) = 1;
    MasterIrp[13].Flags = 2;
    MasterIrp[13].UserBuffer = 0;
    MasterIrp[12].Overlay.AllocationSize.HighPart = 31;
    MasterIrp[13].Tail.Apc.Type = 1;
    if ( !(unsigned int)Feature_SpacesPoolVersion2700__private_IsEnabledDeviceUsageNoInline() )
      MasterIrp[12].Overlay.AllocationSize.HighPart = 29;
    v28 = (char *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 30);
    if ( v28 != (char *)WPP_MAIN_CB.DeviceExtension + 240 )
    {
      Flink = MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
      do
      {
        MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)((char *)Flink
                                                                                                 + *((_QWORD *)v28 - 48));
        if ( SC_DRIVE::HasSpacesPartition((SC_DRIVE *)(v28 - 592)) )
          MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)((char *)MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink + *(_QWORD *)(v31 + 464));
        v28 = (char *)*v30;
      }
      while ( v28 != v32 );
    }
    v20 = Length - 2832;
    v16 = &MasterIrp[13].Tail.CompletionKey + 1;
    *(_DWORD *)(&MasterIrp->Size + 1) += 2832;
    v19 = *(_DWORD *)(&MasterIrp->Size + 1);
  }
  else
  {
    PoolById = SpFindPoolById(&Buf1);
    v10 = PoolById;
    if ( !PoolById )
    {
      v3 = -1073741275;
      goto LABEL_68;
    }
    Object = SDB_RECORD::GetObject(*(SDB_RECORD **)(*((_QWORD *)PoolById + 6) + 272LL));
    *(struct _GUID *)&MasterIrp->MdlAddress = Buf1;
    v12 = (const wchar_t *)*((_QWORD *)Object + 6);
    if ( v12 )
      RtlStringCbCopyW((NTSTRSAFE_PWSTR)&MasterIrp->AssociatedIrp, 0x200u, v12);
    v13 = (const wchar_t *)*((_QWORD *)Object + 7);
    if ( v13 )
      RtlStringCbCopyW((NTSTRSAFE_PWSTR)&MasterIrp[2].Tail, 0x800u, v13);
    LOBYTE(MasterIrp[12].Overlay.AsynchronousParameters.UserApcRoutine) = 0;
    BYTE1(MasterIrp[12].Overlay.AsynchronousParameters.UserApcRoutine) = *((_BYTE *)v10 + 69);
    BYTE2(MasterIrp[12].Overlay.AllocationSize.u.LowPart) = *((_BYTE *)v10 + 70);
    *((_BYTE *)&MasterIrp[12].Tail.CompletionKey + 53) = *((_BYTE *)Object + 64) & 1;
    *((_BYTE *)&MasterIrp[12].Tail.CompletionKey + 54) = (*((_BYTE *)Object + 64) & 2) != 0;
    *((_BYTE *)&MasterIrp[12].Tail.CompletionKey + 55) = (*((_BYTE *)Object + 64) & 4) != 0;
    *((_BYTE *)&MasterIrp[12].Tail.CompletionKey + 56) = *((_BYTE *)Object + 81);
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 15) = *((_DWORD *)Object + 21);
    MasterIrp[12].CancelRoutine = (PDRIVER_CANCEL)*((_QWORD *)v10 + 10);
    LODWORD(MasterIrp[12].UserBuffer) = *((_DWORD *)v10 + 26);
    MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)*((_QWORD *)Object + 30);
    MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)*((_QWORD *)Object + 31);
    *((_BYTE *)&MasterIrp[12].Tail.CompletionKey + 52) = *((_BYTE *)Object + 80);
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 8) = SDB_CONFIG::GetSize(*((SDB_CONFIG **)v10 + 6)) + 0x2000;
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 11) = *((_DWORD *)Object + 18);
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 12) = *((_DWORD *)Object + 19);
    MasterIrp[12].Tail.Overlay.CurrentStackLocation = (struct _IO_STACK_LOCATION *)*((_QWORD *)Object + 11);
    *(_OWORD *)(&MasterIrp[12].Tail.CompletionKey + 9) = *((_OWORD *)Object + 6);
    *(_OWORD *)&MasterIrp[13].Type = *((_OWORD *)Object + 7);
    MasterIrp[13].Flags = *((_DWORD *)Object + 32);
    *(union _IRP::$6B96A96ED958C92F2CB4B83EAB343043 *)((char *)&MasterIrp[13].Overlay + 8) = (union _IRP::$6B96A96ED958C92F2CB4B83EAB343043)*((_OWORD *)Object + 13);
    MasterIrp[13].UserBuffer = (PVOID)*((_QWORD *)Object + 28);
    MasterIrp[12].Overlay.AllocationSize.HighPart = *(_DWORD *)(*((_QWORD *)v10 + 6) + 48LL);
    MasterIrp[13].Tail.Apc.Type = SDB_CONFIG::IsWritable(*((SDB_CONFIG **)v10 + 6));
    if ( *((_BYTE *)v10 + 65) )
    {
      v14 = (SS_STORE::IsHealthy(*(SS_STORE **)(*((_QWORD *)v10 + 6) + 8LL)) != 0) + 2;
      v15 = v14;
    }
    else
    {
      if ( (*((_BYTE *)v10 + 80) & 1) != 0 || (v15 = 1, !*((_BYTE *)v10 + 64)) )
        v15 = 0;
      v14 = 1;
    }
    *((_DWORD *)&MasterIrp[12].Overlay.AllocationSize + 2) = v15;
    v16 = &MasterIrp[13].Tail.CompletionKey + 1;
    *((_DWORD *)&MasterIrp[12].Overlay.AllocationSize + 3) = v14;
    v17 = Length - 2832;
    *(_OWORD *)(&MasterIrp[13].Flags + 1) = *(_OWORD *)((char *)Object + 132);
    *(LIST_ENTRY *)((char *)&MasterIrp[13].ThreadListEntry + 4) = *(LIST_ENTRY *)((char *)Object + 148);
    *(_OWORD *)((char *)&MasterIrp[13].IoStatus.Pointer + 4) = *(_OWORD *)((char *)Object + 164);
    *(_OWORD *)&MasterIrp[13].Cancel = *(_OWORD *)((char *)Object + 180);
    v18 = *(struct _KEVENT **)((char *)Object + 196);
    *(_DWORD *)(&MasterIrp->Size + 1) += 2832;
    v19 = *(_DWORD *)(&MasterIrp->Size + 1);
    *(PKEVENT *)((char *)&MasterIrp[13].UserEvent + 4) = v18;
    if ( (Flink_high & 2) != 0 )
    {
      v20 = Length - 2832;
    }
    else
    {
      v21 = (((_DWORD)MasterIrp + 2835) & 0xFFFFFFFC) - ((_DWORD)MasterIrp + 2832);
      if ( (unsigned int)v17 < v21 )
        v7 = 1;
      else
        v16 = (_OWORD *)((char *)v16 + v21);
      v20 = v17 - v21;
      v22 = (unsigned int)v17 < v21;
      LOBYTE(v17) = 2;
      if ( v22 )
        v20 = 0;
      v19 += v21;
      *(_DWORD *)(&MasterIrp->Size + 1) = v19;
      RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)v10 + 6), v17, 0);
      if ( RecordByType )
      {
        do
        {
          v24 = SDB_RECORD::GetObject(RecordByType);
          if ( (*((_BYTE *)v24 + 64) & 2) != 0 )
          {
            if ( v20 < 0x10 )
            {
              v20 = 0;
              v7 = 1;
            }
            else
            {
              *v16 = *((_OWORD *)v24 + 2);
              if ( !*((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 7) )
                *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 7) = (_DWORD)v16 - (_DWORD)MasterIrp;
              ++v16;
              v20 -= 16;
            }
            ++*((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 6);
            *(_DWORD *)(&MasterIrp->Size + 1) += 16;
          }
          LOBYTE(v25) = 2;
          RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)v10 + 6), v25, v26);
        }
        while ( RecordByType );
        v19 = *(_DWORD *)(&MasterIrp->Size + 1);
      }
    }
    v27 = (void *)*((_QWORD *)Object + 29);
    if ( v27 )
      goto LABEL_57;
  }
  v27 = (void *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 48);
LABEL_57:
  v3 = 0;
  v33 = (((_DWORD)v16 + 3) & 0xFFFFFFFC) - (_DWORD)v16;
  if ( v20 < v33 )
    v7 = 1;
  else
    v16 = (_OWORD *)((char *)v16 + v33);
  *(_DWORD *)(&MasterIrp->Size + 1) = v19 + v33;
  v34 = RtlLengthSecurityDescriptor(v27);
  v35 = v20 - v33;
  v36 = v34;
  if ( v20 < v33 )
    v35 = 0;
  if ( v35 < v34 )
  {
    v7 = 1;
  }
  else
  {
    memmove(v16, v27, v34);
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 9) = v36;
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 10) = (_DWORD)v16 - (_DWORD)MasterIrp;
    LODWORD(v16) = v36 + (_DWORD)v16;
  }
  *(_DWORD *)(&MasterIrp->Size + 1) += v36;
  v37 = (_DWORD)v16 - (_DWORD)MasterIrp;
  if ( v7 )
    v3 = -2147483643;
  a1->IoStatus.Information = v37;
LABEL_68:
  SpReleaseResourceShared((struct _ERESOURCE *)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  if ( v3 >= 0 || v3 == -2147483643 || v3 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v39 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v39 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v39,
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140095338  push    rbx
0x14009533a  push    rbp
0x14009533b  push    rsi
0x14009533c  push    rdi
0x14009533d  push    r12
0x14009533f  push    r13
0x140095341  push    r14
0x140095343  push    r15
0x140095345  sub     rsp, 88h
0x14009534c  mov     rax, cs:__security_cookie
0x140095353  xor     rax, rsp
0x140095356  mov     [rsp+0C8h+var_58], rax
0x14009535b  mov     rbx, [rcx+0B8h]
0x140095362  xorps   xmm0, xmm0
0x140095365  movups  [rsp+0C8h+Buf1], xmm0
0x14009536a  mov     rdi, rcx
0x14009536d  mov     [rsp+0C8h+var_98], rcx
0x140095372  mov     rcx, cs:WPP_GLOBAL_Control
0x140095379  lea     rsi, WPP_GLOBAL_Control
0x140095380  cmp     rcx, rsi
0x140095383  jz      short loc_1400953A7
0x140095385  mov     eax, [rcx+2Ch]
0x140095388  test    al, 1
0x14009538a  jz      short loc_1400953A7
0x14009538c  cmp     byte ptr [rcx+29h], 3
0x140095390  jb      short loc_1400953A7
0x140095392  mov     rcx, [rcx+18h]
0x140095396  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x14009539d  mov     edx, 0Ch
0x1400953a2  call    WPP_SF_
0x1400953a7  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400953ae  xor     edx, edx; unsigned __int8
0x1400953b0  add     rcx, 60h ; '`'; Resource
0x1400953b4  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400953b9  xor     r12d, r12d
0x1400953bc  mov     r14d, 80000005h
0x1400953c2  cmp     dword ptr [rbx+10h], 28h ; '('
0x1400953c6  jnb     short loc_1400953D2
0x1400953c8  mov     ebp, 0C0000004h
0x1400953cd  jmp     loc_140095994
0x1400953d2  mov     rdi, [rdi+18h]
0x1400953d6  cmp     dword ptr [rdi], 28h ; '('
0x1400953d9  movups  xmm1, xmmword ptr [rdi+4]
0x1400953dd  jz      short loc_1400953E9
0x1400953df  mov     ebp, 0C000000Dh
0x1400953e4  jmp     loc_140095994
0x1400953e9  mov     r14d, 0B10h
0x1400953ef  cmp     [rbx+8], r14d
0x1400953f3  jnb     short loc_140095405
0x1400953f5  mov     ebp, 0C0000023h
0x1400953fa  mov     r14d, 80000005h
0x140095400  jmp     loc_140095994
0x140095405  mov     r15d, [rdi+24h]
0x140095409  xor     edx, edx; Val
0x14009540b  movdqu  [rsp+0C8h+Buf1], xmm1
0x140095411  mov     ebx, [rbx+8]
0x140095414  mov     rcx, rdi; void *
0x140095417  mov     r8d, ebx; Size
0x14009541a  mov     r13b, r12b
0x14009541d  call    memset
0x140095422  mov     [rdi], r14d
0x140095425  mov     rcx, cs:WPP_GLOBAL_Control
0x14009542c  mov     ebp, 2
0x140095431  cmp     rcx, rsi
0x140095434  jz      short loc_14009545C
0x140095436  mov     eax, [rcx+2Ch]
0x140095439  test    bpl, al
0x14009543c  jz      short loc_14009545C
0x14009543e  cmp     byte ptr [rcx+29h], 3
0x140095442  jb      short loc_14009545C
0x140095444  mov     rcx, [rcx+18h]
0x140095448  lea     edx, [rbp+0Bh]
0x14009544b  lea     r9, [rsp+0C8h+Buf1]
0x140095450  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x140095457  call    WPP_SF__guid_
0x14009545c  mov     rsi, cs:WPP_MAIN_CB.DeviceExtension
0x140095463  mov     rax, qword ptr [rsp+0C8h+Buf1]
0x140095468  cmp     rax, [rsi+170h]
0x14009546f  jnz     short loc_140095483
0x140095471  mov     rax, qword ptr [rsp+0C8h+Buf1+8]
0x140095476  cmp     rax, [rsi+178h]
0x14009547d  jz      loc_140095791
0x140095483  mov     r8d, 10h; Size
0x140095489  lea     rdx, GUID_NULL; Buf2
0x140095490  lea     rcx, [rsp+0C8h+Buf1]; Buf1
0x140095495  call    memcmp
0x14009549a  test    eax, eax
0x14009549c  jz      loc_140095791
0x1400954a2  lea     rcx, [rsp+0C8h+Buf1]; struct _GUID *
0x1400954a7  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x1400954ac  mov     r14, rax
0x1400954af  test    rax, rax
0x1400954b2  jnz     short loc_1400954C4
0x1400954b4  mov     ebp, 0C0000225h
0x1400954b9  mov     r14d, 80000005h
0x1400954bf  jmp     loc_14009598D
0x1400954c4  mov     rcx, [rax+30h]
0x1400954c8  mov     rcx, [rcx+110h]; this
0x1400954cf  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400954d4  movups  xmm0, [rsp+0C8h+Buf1]
0x1400954d9  mov     rbp, rax
0x1400954dc  movdqu  xmmword ptr [rdi+8], xmm0
0x1400954e1  mov     r8, [rax+30h]; pszSrc
0x1400954e5  test    r8, r8
0x1400954e8  jz      short loc_1400954F8
0x1400954ea  lea     rcx, [rdi+18h]; pszDest
0x1400954ee  mov     edx, 200h; cbDest
0x1400954f3  call    RtlStringCbCopyW
0x1400954f8  mov     r8, [rbp+38h]; pszSrc
0x1400954fc  test    r8, r8
0x1400954ff  jz      short loc_140095512
0x140095501  lea     rcx, [rdi+218h]; pszDest
0x140095508  mov     edx, 800h; cbDest
0x14009550d  call    RtlStringCbCopyW
0x140095512  mov     [rdi+0A18h], r12b
0x140095519  mov     esi, 1
0x14009551e  mov     al, [r14+45h]
0x140095522  mov     [rdi+0A19h], al
0x140095528  mov     al, [r14+46h]
0x14009552c  mov     [rdi+0A1Ah], al
0x140095532  mov     al, [rbp+40h]
0x140095535  and     al, sil
0x140095538  mov     [rdi+0A6Dh], al
0x14009553e  mov     al, [rbp+40h]
0x140095541  shr     al, 1
0x140095543  and     al, sil
0x140095546  mov     [rdi+0A6Eh], al
0x14009554c  mov     al, [rbp+40h]
0x14009554f  shr     al, 2
0x140095552  and     al, sil
0x140095555  mov     [rdi+0A6Fh], al
0x14009555b  mov     al, [rbp+51h]
0x14009555e  mov     [rdi+0A70h], al
0x140095564  mov     eax, [rbp+54h]
0x140095567  mov     [rdi+0A74h], eax
0x14009556d  mov     rax, [r14+50h]
0x140095571  mov     [rdi+0A28h], rax
0x140095578  mov     eax, [r14+68h]
0x14009557c  mov     [rdi+0A30h], eax
0x140095582  mov     rax, [rbp+0F0h]
0x140095589  mov     [rdi+0A38h], rax
0x140095590  mov     rax, [rbp+0F8h]
0x140095597  mov     [rdi+0A40h], rax
0x14009559e  mov     al, [rbp+50h]
0x1400955a1  mov     [rdi+0A6Ch], al
0x1400955a7  mov     rcx, [r14+30h]; this
0x1400955ab  call    ?GetSize@SDB_CONFIG@@QEAAKXZ; SDB_CONFIG::GetSize(void)
0x1400955b0  add     eax, 2000h
0x1400955b5  mov     [rdi+0A58h], eax
0x1400955bb  mov     eax, [rbp+48h]
0x1400955be  mov     [rdi+0A64h], eax
0x1400955c4  mov     eax, [rbp+4Ch]
0x1400955c7  mov     [rdi+0A68h], eax
0x1400955cd  mov     rax, [rbp+58h]
0x1400955d1  mov     [rdi+0A78h], rax
0x1400955d8  movups  xmm0, xmmword ptr [rbp+60h]
0x1400955dc  movups  xmmword ptr [rdi+0A80h], xmm0
0x1400955e3  movups  xmm1, xmmword ptr [rbp+70h]
0x1400955e7  movups  xmmword ptr [rdi+0A90h], xmm1
0x1400955ee  mov     eax, [rbp+80h]
0x1400955f4  mov     [rdi+0AA0h], eax
0x1400955fa  movups  xmm0, xmmword ptr [rbp+0D0h]
0x140095601  movups  xmmword ptr [rdi+0AF0h], xmm0
0x140095608  movsd   xmm1, qword ptr [rbp+0E0h]
0x140095610  movsd   qword ptr [rdi+0B00h], xmm1
0x140095618  mov     rax, [r14+30h]
0x14009561c  mov     ecx, [rax+30h]
0x14009561f  mov     [rdi+0A1Ch], ecx
0x140095625  mov     rcx, [r14+30h]; this
0x140095629  call    ?IsWritable@SDB_CONFIG@@QEAAEXZ; SDB_CONFIG::IsWritable(void)
0x14009562e  mov     [rdi+0B08h], al
0x140095634  cmp     [r14+41h], r12b
0x140095638  jz      short loc_140095654
0x14009563a  mov     rcx, [r14+30h]
0x14009563e  mov     rcx, [rcx+8]; this
0x140095642  call    ?IsHealthy@SS_STORE@@QEAAEXZ; SS_STORE::IsHealthy(void)
0x140095647  neg     al
0x140095649  sbb     ecx, ecx
0x14009564b  neg     ecx
0x14009564d  add     ecx, 2
0x140095650  mov     eax, ecx
0x140095652  jmp     short loc_140095667
0x140095654  test    [r14+50h], sil
0x140095658  jnz     short loc_140095662
0x14009565a  mov     eax, esi
0x14009565c  cmp     [r14+40h], r12b
0x140095660  jnz     short loc_140095665
0x140095662  mov     eax, r12d
0x140095665  mov     ecx, esi
0x140095667  mov     [rdi+0A20h], eax
0x14009566d  lea     rsi, [rdi+0B10h]
0x140095674  mov     [rdi+0A24h], ecx
0x14009567a  lea     edx, [rbx-0B10h]
0x140095680  movups  xmm0, xmmword ptr [rbp+84h]
0x140095687  movups  xmmword ptr [rdi+0AA4h], xmm0
0x14009568e  movups  xmm1, xmmword ptr [rbp+94h]
0x140095695  movups  xmmword ptr [rdi+0AB4h], xmm1
0x14009569c  movups  xmm0, xmmword ptr [rbp+0A4h]
0x1400956a3  movups  xmmword ptr [rdi+0AC4h], xmm0
0x1400956aa  movups  xmm1, xmmword ptr [rbp+0B4h]
0x1400956b1  movups  xmmword ptr [rdi+0AD4h], xmm1
0x1400956b8  movsd   xmm0, qword ptr [rbp+0C4h]
0x1400956c0  add     dword ptr [rdi+4], 0B10h
0x1400956c7  mov     r12d, [rdi+4]
0x1400956cb  movsd   qword ptr [rdi+0AE4h], xmm0
0x1400956d3  test    r15b, 2
0x1400956d7  jz      short loc_1400956E0
0x1400956d9  mov     ebx, edx
0x1400956db  jmp     loc_14009577C
0x1400956e0  lea     rcx, [rsi+3]
0x1400956e4  and     ecx, 0FFFFFFFCh
0x1400956e7  sub     ecx, esi
0x1400956e9  cmp     edx, ecx
0x1400956eb  jb      short loc_1400956F4
0x1400956ed  mov     eax, ecx
0x1400956ef  add     rsi, rax
0x1400956f2  jmp     short loc_1400956F7
0x1400956f4  mov     r13b, 1
0x1400956f7  mov     ebx, edx
0x1400956f9  xor     eax, eax
0x1400956fb  sub     ebx, ecx
0x1400956fd  cmp     edx, ecx
0x1400956ff  mov     dl, 2
0x140095701  cmovb   ebx, eax
0x140095704  add     r12d, ecx
0x140095707  mov     [rdi+4], r12d
0x14009570b  xor     r8d, r8d
0x14009570e  mov     rcx, [r14+30h]
0x140095712  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x140095717  mov     rcx, rax; this
0x14009571a  test    rax, rax
0x14009571d  jz      short loc_14009577C
0x14009571f  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x140095724  test    byte ptr [rax+40h], 2
0x140095728  jz      short loc_140095762
0x14009572a  cmp     ebx, 10h
0x14009572d  jb      short loc_140095753
0x14009572f  movups  xmm0, xmmword ptr [rax+20h]
0x140095733  movdqu  xmmword ptr [rsi], xmm0
0x140095737  cmp     dword ptr [rdi+0A54h], 0
0x14009573e  jnz     short loc_14009574A
0x140095740  mov     eax, esi
0x140095742  sub     eax, edi
0x140095744  mov     [rdi+0A54h], eax
0x14009574a  add     rsi, 10h
0x14009574e  add     ebx, 0FFFFFFF0h
0x140095751  jmp     short loc_140095758
0x140095753  xor     ebx, ebx
0x140095755  mov     r13b, 1
0x140095758  inc     dword ptr [rdi+0A50h]
0x14009575e  add     dword ptr [rdi+4], 10h
0x140095762  mov     r8, rcx
0x140095765  mov     dl, 2
0x140095767  mov     rcx, [r14+30h]
0x14009576b  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x140095770  mov     rcx, rax
0x140095773  test    rax, rax
0x140095776  jnz     short loc_14009571F
0x140095778  mov     r12d, [rdi+4]
0x14009577c  mov     r15, [rbp+0E8h]
0x140095783  test    r15, r15
0x140095786  jnz     loc_1400958FE
0x14009578c  jmp     loc_1400958F0
0x140095791  movups  xmm0, xmmword ptr [rsi+170h]
0x140095798  lea     rcx, [rdi+18h]; pszDest
0x14009579c  mov     edx, 200h; cbDest
0x1400957a1  lea     r8, aPrimordial; "Primordial"
0x1400957a8  movdqu  xmmword ptr [rdi+8], xmm0
0x1400957ad  call    RtlStringCbCopyW
0x1400957b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400957b6  mov     word ptr [rdi+0A18h], 1
0x1400957bf  mov     [rdi+0A88h], rax
0x1400957c6  mov     [rdi+0AF0h], rax
0x1400957cd  mov     [rdi+0A1Ah], r12b
0x1400957d4  mov     dword ptr [rdi+0A20h], 3
0x1400957de  mov     dword ptr [rdi+0A24h], 3
0x1400957e8  mov     dword ptr [rdi+0A30h], 1
0x1400957f2  mov     [rdi+0A38h], r12
0x1400957f9  mov     [rdi+0A40h], r12
0x140095800  mov     dword ptr [rdi+0A6Ch], 46h ; 'F'
0x14009580a  mov     byte ptr [rdi+0A70h], 1
0x140095811  mov     dword ptr [rdi+0A74h], 1
0x14009581b  mov     dword ptr [rdi+0A58h], 20000000h
0x140095825  mov     [rdi+0A64h], r12
0x14009582c  mov     qword ptr [rdi+0A78h], 10000000h
0x140095837  mov     [rdi+0A80h], ebp
0x14009583d  mov     [rdi+0A90h], r12d
0x140095844  mov     qword ptr [rdi+0A94h], 1
0x14009584f  mov     dword ptr [rdi+0A9Ch], 1
0x140095859  mov     [rdi+0AA0h], ebp
0x14009585f  mov     [rdi+0B00h], r12
0x140095866  mov     dword ptr [rdi+0A1Ch], 1Fh
0x140095870  mov     byte ptr [rdi+0B08h], 1
0x140095877  call    Feature_SpacesPoolVersion2700__private_IsEnabledDeviceUsageNoInline
0x14009587c  test    eax, eax
0x14009587e  jnz     short loc_14009588A
0x140095880  mov     dword ptr [rdi+0A1Ch], 1Dh
0x14009588a  mov     r8, cs:WPP_MAIN_CB.DeviceExtension
0x140095891  add     r8, 0F0h
0x140095898  mov     rdx, [r8]
  ... truncated ...
```

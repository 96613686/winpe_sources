# SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140016080`
- end: `0x140016140`
- name: `?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `192`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140011970`
- `0x140015820`
- `0x140016080`
- `0x140022180`
- `0x14002bf40`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400160ba`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400160ba`

## pseudocode

```c
__int64 __fastcall SpIoCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, void *a3)
{
  PEX_RUNDOWN_REF_CACHE_AWARE *DeviceExtension; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  char v5; // di
  unsigned int v6; // ebp
  NTSTATUS Status; // eax
  UCHAR MajorFunction; // cl
  struct _IO_STACK_LOCATION *v13; // rax
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rdx
  struct _IO_STACK_LOCATION *v15; // rax
  void *v16; // rcx
  unsigned int v17; // r8d
  struct _IO_STACK_LOCATION *v18; // rax
  struct _IO_STACK_LOCATION *v19; // rax
  struct _IO_STACK_LOCATION *v20; // rax
  struct _IO_STACK_LOCATION *v21; // rax
  struct _IO_STACK_LOCATION *v22; // rax
  struct _IO_STACK_LOCATION *v23; // rax
  struct _IO_STACK_LOCATION *v24; // rax
  struct _IO_STACK_LOCATION *v25; // rax
  ULONG SortKey; // r9d
  struct _IO_STACK_LOCATION *v27; // rax
  struct _IO_STACK_LOCATION *v28; // rax
  struct _IO_STACK_LOCATION *v29; // rax
  struct _IO_STACK_LOCATION *v30; // rax
  char *v31; // rcx
  struct _IO_STACK_LOCATION *v32; // rax
  struct _IO_STACK_LOCATION *v33; // rax
  PEX_RUNDOWN_REF_CACHE_AWARE v34; // rax

  DeviceExtension = (PEX_RUNDOWN_REF_CACHE_AWARE *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = (unsigned __int8)a3 & 1;
  v6 = 0;
  if ( ((unsigned __int8)a3 & 2) != 0 )
    ExReleaseRundownProtectionCacheAware(DeviceExtension[31]);
  if ( a2->PendingReturned )
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  Status = a2->IoStatus.Status;
  if ( Status < 0 )
  {
    MajorFunction = CurrentStackLocation->MajorFunction;
    if ( CurrentStackLocation->MajorFunction == 3 && CurrentStackLocation->MinorFunction == 83 )
    {
      CurrentStackLocation->MinorFunction = 84;
      SpDispatch(a1, a2);
      return (unsigned int)-1073741802;
    }
    if ( Status > -1058602988 )
    {
      switch ( Status )
      {
        case -1058602983:
          v32 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v32[-1].MajorFunction = *(_OWORD *)&v32->MajorFunction;
          *(_OWORD *)&v32[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v32->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v32[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v32->Parameters.SetQuota + 6);
          v32[-1].FileObject = v32->FileObject;
          v32[-1].Control = 0;
          v33 = a2->Tail.Overlay.CurrentStackLocation;
          v33[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v16 = DeviceExtension + 169;
          v33[-1].Context = (PVOID)1;
          v33[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v34 = DeviceExtension[18];
          if ( !v34 )
            v16 = DeviceExtension + 195;
          v17 = v34 != 0 ? 0x3E8 : 0;
          goto LABEL_38;
        case -1058602981:
          v29 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v29[-1].MajorFunction = *(_OWORD *)&v29->MajorFunction;
          *(_OWORD *)&v29[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v29->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v29[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v29->Parameters.SetQuota + 6);
          v29[-1].FileObject = v29->FileObject;
          v29[-1].Control = 0;
          v30 = a2->Tail.Overlay.CurrentStackLocation;
          v30[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v31 = (char *)WPP_MAIN_CB.DeviceExtension;
          v30[-1].Context = (PVOID)1;
          v16 = v31 + 984;
          v30[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v17 = 0;
          goto LABEL_38;
        case -1058602976:
          v27 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v27[-1].MajorFunction = *(_OWORD *)&v27->MajorFunction;
          *(_OWORD *)&v27[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v27->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v27[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v27->Parameters.SetQuota + 6);
          v27[-1].FileObject = v27->FileObject;
          v27[-1].Control = 0;
          v28 = a2->Tail.Overlay.CurrentStackLocation;
          v28[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v16 = DeviceExtension + 117;
          v28[-1].Context = (PVOID)1;
          v28[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v17 = 0;
          goto LABEL_38;
        case -1058602970:
          v24 = a2->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v24[-1].MajorFunction = *(_OWORD *)&v24->MajorFunction;
          *(_OWORD *)&v24[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v24->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v24[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v24->Parameters.SetQuota + 6);
          v24[-1].FileObject = v24->FileObject;
          v24[-1].Control = 0;
          v25 = a2->Tail.Overlay.CurrentStackLocation;
          v25[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v25[-1].Context = (PVOID)1;
          v25[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          SortKey = a2->Tail.Overlay.DeviceQueueEntry.SortKey;
          _InterlockedIncrement((volatile signed __int32 *)DeviceExtension[18] + 142);
          SP_WORKITEM::Insert(DeviceExtension + 143, &a2->Tail.Overlay.ListEntry, 0x3E8u, SortKey & 1);
          SP_DEVICE::RunCacheDestage((SP_DEVICE *)(DeviceExtension + 1));
          return (unsigned int)-1073741802;
      }
      goto LABEL_32;
    }
    if ( Status == -1058602988 )
    {
      v22 = a2->Tail.Overlay.CurrentStackLocation;
      p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
      *(_OWORD *)&v22[-1].MajorFunction = *(_OWORD *)&v22->MajorFunction;
      *(_OWORD *)&v22[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v22->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v22[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v22->Parameters.SetQuota + 6);
      v22[-1].FileObject = v22->FileObject;
      v22[-1].Control = 0;
      v23 = a2->Tail.Overlay.CurrentStackLocation;
      v23[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
      v16 = DeviceExtension + 91;
      v23[-1].Context = (PVOID)1;
      v23[-1].Control = -32;
      --a2->CurrentLocation;
      --a2->Tail.Overlay.CurrentStackLocation;
      v17 = 0;
      goto LABEL_38;
    }
    if ( Status != -1073740693 )
    {
      if ( Status == -1072037859 )
      {
        if ( MajorFunction == 4 )
        {
          CurrentStackLocation->MinorFunction = 82;
          v18 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v18[-1].MajorFunction = *(_OWORD *)&v18->MajorFunction;
          *(_OWORD *)&v18[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v18->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v18[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v18->Parameters.SetQuota + 6);
          v18[-1].FileObject = v18->FileObject;
          v18[-1].Control = 0;
          v19 = a2->Tail.Overlay.CurrentStackLocation;
          v19[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v16 = DeviceExtension + 221;
          v19[-1].Context = (PVOID)1;
          v19[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v17 = 0;
          goto LABEL_38;
        }
LABEL_32:
        SpLogStatus((struct SP_DEVICE *)(DeviceExtension + 1), a2);
        return v6;
      }
      if ( Status != -1058602997 )
      {
        if ( Status == -1058602989 )
        {
          v13 = a2->Tail.Overlay.CurrentStackLocation;
          p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
          *(_OWORD *)&v13[-1].MajorFunction = *(_OWORD *)&v13->MajorFunction;
          *(_OWORD *)&v13[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v13->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v13[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v13->Parameters.SetQuota + 6);
          v13[-1].FileObject = v13->FileObject;
          v13[-1].Control = 0;
          v15 = a2->Tail.Overlay.CurrentStackLocation;
          v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
          v16 = DeviceExtension + 65;
          v15[-1].Context = (PVOID)1;
          v15[-1].Control = -32;
          --a2->CurrentLocation;
          --a2->Tail.Overlay.CurrentStackLocation;
          v17 = 0;
LABEL_38:
          SP_WORKITEM::Insert(v16, &p_ListEntry->ListEntry, v17, 0);
          return (unsigned int)-1073741802;
        }
        goto LABEL_32;
      }
    }
    if ( !v5 && MajorFunction == 4 && CurrentStackLocation->MinorFunction != 85 && DeviceExtension[18] )
    {
      v20 = a2->Tail.Overlay.CurrentStackLocation;
      p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
      *(_OWORD *)&v20[-1].MajorFunction = *(_OWORD *)&v20->MajorFunction;
      *(_OWORD *)&v20[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v20->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v20[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v20->Parameters.SetQuota + 6);
      v20[-1].FileObject = v20->FileObject;
      v20[-1].Control = 0;
      v21 = a2->Tail.Overlay.CurrentStackLocation;
      v21[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpIoCompletionRoutine;
      v16 = DeviceExtension + 247;
      v21[-1].Context = (PVOID)1;
      v21[-1].Control = -32;
      --a2->CurrentLocation;
      --a2->Tail.Overlay.CurrentStackLocation;
      v17 = 0;
      CurrentStackLocation->MinorFunction = 85;
      goto LABEL_38;
    }
    goto LABEL_32;
  }
  if ( v5 )
  {
    a2->Tail.Overlay.DriverContext[2] = a3;
    SpDispatch(a1, a2);
    return (unsigned int)-1073741802;
  }
  return v6;
}

```

## disassembly

```asm
0x140016080  push    rbx
0x140016082  push    rbp
0x140016083  push    rsi
0x140016084  push    rdi
0x140016085  push    r12
0x140016087  push    r14
0x140016089  push    r15
0x14001608b  sub     rsp, 20h
0x14001608f  mov     r15, [rcx+40h]
0x140016093  movzx   edi, r8b
0x140016097  mov     r12, [rdx+0B8h]
0x14001609e  and     dil, 1
0x1400160a2  xor     ebp, ebp
0x1400160a4  mov     rsi, r8
0x1400160a7  mov     rbx, rdx
0x1400160aa  mov     r14, rcx
0x1400160ad  test    r8b, 2
0x1400160b1  jz      short loc_1400160C6
0x1400160b3  mov     rcx, [r15+0F8h]; RunRefCacheAware
0x1400160ba  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400160c1  nop     dword ptr [rax+rax+00h]
0x1400160c6  cmp     [rbx+41h], bpl
0x1400160ca  jnz     short loc_1400160EA
0x1400160cc  mov     eax, [rbx+30h]
0x1400160cf  test    eax, eax
0x1400160d1  js      short loc_14001610F
0x1400160d3  test    dil, dil
0x1400160d6  jnz     short loc_1400160F7
0x1400160d8  mov     eax, ebp
0x1400160da  add     rsp, 20h
0x1400160de  pop     r15
0x1400160e0  pop     r14
0x1400160e2  pop     r12
0x1400160e4  pop     rdi
0x1400160e5  pop     rsi
0x1400160e6  pop     rbp
0x1400160e7  pop     rbx
0x1400160e8  retn
0x1400160ea  mov     rax, [rbx+0B8h]
0x1400160f1  or      byte ptr [rax+3], 1
0x1400160f5  jmp     short loc_1400160CC
0x1400160f7  mov     rdx, rbx; struct _IRP *
0x1400160fa  mov     [rbx+88h], rsi
0x140016101  mov     rcx, r14; struct _DEVICE_OBJECT *
0x140016104  call    ?SpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; SpDispatch(_DEVICE_OBJECT *,_IRP *)
0x140016109  nop
0x14001610a  jmp     loc_14006A30C
0x14001610f  movzx   ecx, byte ptr [r12]
0x140016114  cmp     cl, 3
0x140016117  jnz     loc_140069EA8
0x14001611d  cmp     byte ptr [r12+1], 53h ; 'S'
0x140016123  jnz     loc_140069EA8
0x140016129  mov     rdx, rbx; struct _IRP *
0x14001612c  mov     byte ptr [r12+1], 54h ; 'T'
0x140016132  mov     rcx, r14; struct _DEVICE_OBJECT *
0x140016135  call    ?SpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; SpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14001613a  nop
0x14001613b  jmp     loc_14006A30C
0x140069ea8  cmp     eax, 0C0E70014h
0x140069ead  jg      loc_14006A0D1
0x140069eb3  jz      loc_14006A066
0x140069eb9  cmp     eax, 0C000046Bh
0x140069ebe  jz      loc_140069FCA
0x140069ec4  cmp     eax, 0C01A001Dh
0x140069ec9  jz      loc_140069F50
0x140069ecf  cmp     eax, 0C0E7000Bh
0x140069ed4  jz      loc_140069FCA
0x140069eda  cmp     eax, 0C0E70013h
0x140069edf  jnz     loc_14006A192
0x140069ee5  mov     rax, [rbx+0B8h]
0x140069eec  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140069ef3  lea     rdx, [rbx+0A8h]
0x140069efa  movups  xmm0, xmmword ptr [rax]
0x140069efd  movups  xmmword ptr [rax-48h], xmm0
0x140069f01  movups  xmm1, xmmword ptr [rax+10h]
0x140069f05  movups  xmmword ptr [rax-38h], xmm1
0x140069f09  movups  xmm0, xmmword ptr [rax+20h]
0x140069f0d  movups  xmmword ptr [rax-28h], xmm0
0x140069f11  movsd   xmm1, qword ptr [rax+30h]
0x140069f16  movsd   qword ptr [rax-18h], xmm1
0x140069f1b  mov     [rax-45h], bpl
0x140069f1f  mov     rax, [rbx+0B8h]
0x140069f26  mov     [rax-10h], rcx
0x140069f2a  lea     rcx, [r15+208h]
0x140069f31  mov     qword ptr [rax-8], 1
0x140069f39  mov     byte ptr [rax-45h], 0E0h
0x140069f3d  dec     byte ptr [rbx+43h]
0x140069f40  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140069f48  xor     r8d, r8d
0x140069f4b  jmp     loc_14006A304
0x140069f50  cmp     cl, 4
0x140069f53  jnz     loc_14006A192
0x140069f59  mov     byte ptr [r12+1], 52h ; 'R'
0x140069f5f  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140069f66  mov     rax, [rbx+0B8h]
0x140069f6d  lea     rdx, [rbx+0A8h]
0x140069f74  movups  xmm0, xmmword ptr [rax]
0x140069f77  movups  xmmword ptr [rax-48h], xmm0
0x140069f7b  movups  xmm1, xmmword ptr [rax+10h]
0x140069f7f  movups  xmmword ptr [rax-38h], xmm1
0x140069f83  movups  xmm0, xmmword ptr [rax+20h]
0x140069f87  movups  xmmword ptr [rax-28h], xmm0
0x140069f8b  movsd   xmm1, qword ptr [rax+30h]
0x140069f90  movsd   qword ptr [rax-18h], xmm1
0x140069f95  mov     [rax-45h], bpl
0x140069f99  mov     rax, [rbx+0B8h]
0x140069fa0  mov     [rax-10h], rcx
0x140069fa4  lea     rcx, [r15+6E8h]
0x140069fab  mov     qword ptr [rax-8], 1
0x140069fb3  mov     byte ptr [rax-45h], 0E0h
0x140069fb7  dec     byte ptr [rbx+43h]
0x140069fba  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140069fc2  xor     r8d, r8d
0x140069fc5  jmp     loc_14006A304
0x140069fca  test    dil, dil
0x140069fcd  jnz     loc_14006A192
0x140069fd3  cmp     cl, 4
0x140069fd6  jnz     loc_14006A192
0x140069fdc  cmp     byte ptr [r12+1], 55h ; 'U'
0x140069fe2  jz      loc_14006A192
0x140069fe8  cmp     [r15+90h], rbp
0x140069fef  jz      loc_14006A192
0x140069ff5  mov     rax, [rbx+0B8h]
0x140069ffc  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a003  lea     rdx, [rbx+0A8h]
0x14006a00a  movups  xmm0, xmmword ptr [rax]
0x14006a00d  movups  xmmword ptr [rax-48h], xmm0
0x14006a011  movups  xmm1, xmmword ptr [rax+10h]
0x14006a015  movups  xmmword ptr [rax-38h], xmm1
0x14006a019  movups  xmm0, xmmword ptr [rax+20h]
0x14006a01d  movups  xmmword ptr [rax-28h], xmm0
0x14006a021  movsd   xmm1, qword ptr [rax+30h]
0x14006a026  movsd   qword ptr [rax-18h], xmm1
0x14006a02b  mov     [rax-45h], bpl
0x14006a02f  mov     rax, [rbx+0B8h]
0x14006a036  mov     [rax-10h], rcx
0x14006a03a  lea     rcx, [r15+7B8h]
0x14006a041  mov     qword ptr [rax-8], 1
0x14006a049  mov     byte ptr [rax-45h], 0E0h
0x14006a04d  dec     byte ptr [rbx+43h]
0x14006a050  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a058  xor     r8d, r8d
0x14006a05b  mov     byte ptr [r12+1], 55h ; 'U'
0x14006a061  jmp     loc_14006A304
0x14006a066  mov     rax, [rbx+0B8h]
0x14006a06d  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a074  lea     rdx, [rbx+0A8h]
0x14006a07b  movups  xmm0, xmmword ptr [rax]
0x14006a07e  movups  xmmword ptr [rax-48h], xmm0
0x14006a082  movups  xmm1, xmmword ptr [rax+10h]
0x14006a086  movups  xmmword ptr [rax-38h], xmm1
0x14006a08a  movups  xmm0, xmmword ptr [rax+20h]
0x14006a08e  movups  xmmword ptr [rax-28h], xmm0
0x14006a092  movsd   xmm1, qword ptr [rax+30h]
0x14006a097  movsd   qword ptr [rax-18h], xmm1
0x14006a09c  mov     [rax-45h], bpl
0x14006a0a0  mov     rax, [rbx+0B8h]
0x14006a0a7  mov     [rax-10h], rcx
0x14006a0ab  lea     rcx, [r15+2D8h]
0x14006a0b2  mov     qword ptr [rax-8], 1
0x14006a0ba  mov     byte ptr [rax-45h], 0E0h
0x14006a0be  dec     byte ptr [rbx+43h]
0x14006a0c1  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a0c9  xor     r8d, r8d
0x14006a0cc  jmp     loc_14006A304
0x14006a0d1  cmp     eax, 0C0E70019h
0x14006a0d6  jz      loc_14006A281
0x14006a0dc  cmp     eax, 0C0E7001Bh
0x14006a0e1  jz      loc_14006A20F
0x14006a0e7  cmp     eax, 0C0E70020h
0x14006a0ec  jz      loc_14006A1A4
0x14006a0f2  cmp     eax, 0C0E70026h
0x14006a0f7  jnz     loc_14006A192
0x14006a0fd  mov     rax, [rbx+0B8h]
0x14006a104  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a10b  movups  xmm0, xmmword ptr [rax]
0x14006a10e  movups  xmmword ptr [rax-48h], xmm0
0x14006a112  movups  xmm1, xmmword ptr [rax+10h]
0x14006a116  movups  xmmword ptr [rax-38h], xmm1
0x14006a11a  movups  xmm0, xmmword ptr [rax+20h]
0x14006a11e  movups  xmmword ptr [rax-28h], xmm0
0x14006a122  movsd   xmm1, qword ptr [rax+30h]
0x14006a127  movsd   qword ptr [rax-18h], xmm1
0x14006a12c  mov     [rax-45h], bpl
0x14006a130  mov     rax, [rbx+0B8h]
0x14006a137  mov     [rax-10h], rcx
0x14006a13b  mov     qword ptr [rax-8], 1
0x14006a143  mov     byte ptr [rax-45h], 0E0h
0x14006a147  dec     byte ptr [rbx+43h]
0x14006a14a  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a152  mov     r9d, [rbx+88h]
0x14006a159  mov     rax, [r15+90h]
0x14006a160  lock inc dword ptr [rax+238h]
0x14006a167  and     r9b, 1; unsigned __int8
0x14006a16b  lea     rdx, [rbx+0A8h]; struct _LIST_ENTRY *
0x14006a172  lea     rcx, [r15+478h]; Context
0x14006a179  mov     r8d, 3E8h; unsigned int
0x14006a17f  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14006a184  lea     rcx, [r15+8]; this
0x14006a188  call    ?RunCacheDestage@SP_DEVICE@@UEAAXXZ; SP_DEVICE::RunCacheDestage(void)
0x14006a18d  jmp     loc_14006A30C
0x14006a192  mov     rdx, rbx; struct _IRP *
0x14006a195  lea     rcx, [r15+8]; struct SP_DEVICE *
0x14006a199  call    ?SpLogStatus@@YAXPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpLogStatus(SP_DEVICE *,_IRP *)
0x14006a19e  nop
0x14006a19f  jmp     loc_1400160D8
0x14006a1a4  mov     rax, [rbx+0B8h]
0x14006a1ab  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a1b2  lea     rdx, [rbx+0A8h]
0x14006a1b9  movups  xmm0, xmmword ptr [rax]
0x14006a1bc  movups  xmmword ptr [rax-48h], xmm0
0x14006a1c0  movups  xmm1, xmmword ptr [rax+10h]
0x14006a1c4  movups  xmmword ptr [rax-38h], xmm1
0x14006a1c8  movups  xmm0, xmmword ptr [rax+20h]
0x14006a1cc  movups  xmmword ptr [rax-28h], xmm0
0x14006a1d0  movsd   xmm1, qword ptr [rax+30h]
0x14006a1d5  movsd   qword ptr [rax-18h], xmm1
0x14006a1da  mov     [rax-45h], bpl
0x14006a1de  mov     rax, [rbx+0B8h]
0x14006a1e5  mov     [rax-10h], rcx
0x14006a1e9  lea     rcx, [r15+3A8h]
0x14006a1f0  mov     qword ptr [rax-8], 1
0x14006a1f8  mov     byte ptr [rax-45h], 0E0h
0x14006a1fc  dec     byte ptr [rbx+43h]
0x14006a1ff  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a207  xor     r8d, r8d
0x14006a20a  jmp     loc_14006A304
0x14006a20f  mov     rax, [rbx+0B8h]
0x14006a216  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a21d  lea     rdx, [rbx+0A8h]
0x14006a224  movups  xmm0, xmmword ptr [rax]
0x14006a227  movups  xmmword ptr [rax-48h], xmm0
0x14006a22b  movups  xmm1, xmmword ptr [rax+10h]
0x14006a22f  movups  xmmword ptr [rax-38h], xmm1
0x14006a233  movups  xmm0, xmmword ptr [rax+20h]
0x14006a237  movups  xmmword ptr [rax-28h], xmm0
0x14006a23b  movsd   xmm1, qword ptr [rax+30h]
0x14006a240  movsd   qword ptr [rax-18h], xmm1
0x14006a245  mov     [rax-45h], bpl
0x14006a249  mov     rax, [rbx+0B8h]
0x14006a250  mov     [rax-10h], rcx
0x14006a254  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14006a25b  mov     qword ptr [rax-8], 1
0x14006a263  add     rcx, 3D8h
0x14006a26a  mov     byte ptr [rax-45h], 0E0h
0x14006a26e  dec     byte ptr [rbx+43h]
0x14006a271  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a279  xor     r8d, r8d
0x14006a27c  jmp     loc_14006A304
0x14006a281  mov     rax, [rbx+0B8h]
0x14006a288  lea     rcx, ?SpIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14006a28f  lea     rdx, [rbx+0A8h]; struct _LIST_ENTRY *
0x14006a296  movups  xmm0, xmmword ptr [rax]
0x14006a299  movups  xmmword ptr [rax-48h], xmm0
0x14006a29d  movups  xmm1, xmmword ptr [rax+10h]
0x14006a2a1  movups  xmmword ptr [rax-38h], xmm1
0x14006a2a5  movups  xmm0, xmmword ptr [rax+20h]
0x14006a2a9  movups  xmmword ptr [rax-28h], xmm0
0x14006a2ad  movsd   xmm1, qword ptr [rax+30h]
0x14006a2b2  movsd   qword ptr [rax-18h], xmm1
0x14006a2b7  mov     [rax-45h], bpl
0x14006a2bb  mov     rax, [rbx+0B8h]
0x14006a2c2  mov     [rax-10h], rcx
0x14006a2c6  lea     rcx, [r15+548h]
0x14006a2cd  mov     qword ptr [rax-8], 1
0x14006a2d5  mov     byte ptr [rax-45h], 0E0h
0x14006a2d9  dec     byte ptr [rbx+43h]
0x14006a2dc  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006a2e4  mov     rax, [r15+90h]
0x14006a2eb  test    rax, rax
0x14006a2ee  jnz     short loc_14006A2F7
0x14006a2f0  lea     rcx, [r15+618h]; Context
0x14006a2f7  neg     rax
0x14006a2fa  sbb     r8d, r8d
0x14006a2fd  and     r8d, 3E8h; unsigned int
0x14006a304  xor     r9d, r9d; unsigned __int8
0x14006a307  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14006a30c  mov     ebp, 0C0000016h
0x14006a311  jmp     loc_1400160D8
```

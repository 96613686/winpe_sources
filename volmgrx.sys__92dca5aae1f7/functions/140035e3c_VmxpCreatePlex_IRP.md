# VmxpCreatePlex(_IRP *)

- ea: `0x140035e3c`
- end: `0x1400362a2`
- name: `?VmxpCreatePlex@@YAJPEAU_IRP@@@Z`
- size: `1126`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x1400099d8`
- `0x14002a3f4`
- `0x1400314e8`
- `0x140035e3c`
- `0x14003acbc`
- `0x14003c244`
- `0x14003f51c`
- `0x14004a70c`
- `0x14004bac0`
- `0x14004f1e4`
- `0x1400578d0`
- `0x140057dc0`
- `0x14005abb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140036160`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036160`

## pseudocode

```c
__int64 __fastcall VmxpCreatePlex(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _IRP *MasterIrp; // r14
  struct VMX_RECORD **v3; // rsi
  unsigned int v4; // r12d
  VMX_NOTIFICATION_QUEUE *v5; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  unsigned int Options; // edx
  int v9; // eax
  __int64 v10; // r9
  struct _GUID *p_Flags; // rax
  struct VMX_PACK *v12; // r13
  struct VMX_RECORD *VolumeById; // rax
  struct VMX_RECORD *v14; // r15
  VMX_PACK *v15; // rcx
  int updated; // eax
  VMX_PACK *v17; // rcx
  VMX_PACK *v18; // rcx
  bool v19; // sf
  int v21; // [rsp+30h] [rbp-28h]
  struct VMX_RECORD **v22; // [rsp+38h] [rbp-20h] BYREF
  struct VMX_PACK *v23; // [rsp+40h] [rbp-18h] BYREF
  struct VMX_RECORD *v24; // [rsp+48h] [rbp-10h] BYREF
  char v26; // [rsp+A8h] [rbp+50h] BYREF
  char v27; // [rsp+B0h] [rbp+58h]
  unsigned int v28; // [rsp+B8h] [rbp+60h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  v23 = 0;
  v24 = 0;
  v3 = 0;
  v22 = 0;
  v4 = 0;
  v28 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v26, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -1070071783;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v7 = 221;
      goto LABEL_71;
    }
    goto LABEL_73;
  }
  if ( !*((_BYTE *)Global + 274) )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -1070071717;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v7 = 222;
      goto LABEL_71;
    }
    goto LABEL_73;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  v6 = -1073741811;
  if ( Options < 0x70 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v7 = 223;
      goto LABEL_71;
    }
    goto LABEL_73;
  }
  if ( LODWORD(MasterIrp->ThreadListEntry.Flink) >= 0xFFFFFFE0 )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -1073741675;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_73;
    }
    v7 = 224;
LABEL_71:
    v10 = (unsigned int)v6;
LABEL_72:
    WPP_SF_d(*((_QWORD *)v5 + 3), v7, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v10);
    goto LABEL_73;
  }
  if ( Options < LODWORD(MasterIrp->ThreadListEntry.Flink) + 32 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v7 = 225;
      goto LABEL_71;
    }
    goto LABEL_73;
  }
  if ( HIDWORD(MasterIrp->ThreadListEntry.Flink) == 2 && !*((_BYTE *)Global + 275) )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = -1070071716;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v7 = 226;
      goto LABEL_71;
    }
    goto LABEL_73;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x20 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v7 = 227;
      goto LABEL_71;
    }
    goto LABEL_73;
  }
  v9 = VmxpValidatePackIdInput((struct _GUID *)MasterIrp, &v23);
  v6 = v9;
  if ( v9 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_73;
    }
    v7 = 228;
    v10 = (unsigned int)v9;
    goto LABEL_72;
  }
  p_Flags = (struct _GUID *)&MasterIrp->Flags;
  while ( 1 )
  {
    v12 = v23;
    VolumeById = VMX_CONFIG::FindVolumeById(*((VMX_CONFIG **)v23 + 2), p_Flags);
    v14 = VolumeById;
    if ( !VolumeById )
      break;
    v21 = *(_DWORD *)(*((_QWORD *)VolumeById + (*((_WORD *)VolumeById + 32) & 1) + 5) + 156LL);
    v6 = VMX_PACK::BeginTransaction(v12);
    if ( v6 < 0 )
      goto LABEL_51;
    v27 = 0;
    v6 = VMX_PACK::CreatePlexTransaction(v12, v14, (struct _VM_PLEX_LAYOUT *)&MasterIrp->ThreadListEntry, &v24);
    if ( v6 < 0 )
    {
LABEL_47:
      VMX_PACK::AbortTransaction(v12);
      goto LABEL_48;
    }
    if ( (v21 & 0x800000) != 0 )
    {
      updated = VMX_PACK::UpdatePartitionsQueryPlexDisks(v15, v24, 0, &v22, &v28);
      v4 = v28;
      v6 = updated;
      v3 = v22;
      if ( updated < 0 )
        goto LABEL_47;
      v6 = VMX_PACK::UpdatePartitions(v17, v22, v28, 0);
      if ( v6 < 0 )
        goto LABEL_47;
      v27 = 1;
    }
    v6 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v12, 0, 1);
LABEL_48:
    if ( v6 < 0 && v27 )
      VMX_PACK::UpdatePartitions(v18, v3, v4, 1);
LABEL_51:
    if ( v3 )
    {
      ExFreePoolWithTag(v3, 0);
      v3 = 0;
      v4 = 0;
      v22 = 0;
      v28 = 0;
    }
    if ( v6 >= 0 )
    {
      *(_OWORD *)&MasterIrp->Type = *(_OWORD *)(*(_QWORD *)(*((_QWORD *)v12 + 2) + 8LL) + 8LL);
      *(_OWORD *)&MasterIrp->Flags = *(_OWORD *)(*((_QWORD *)v14 + (*((_WORD *)v14 + 32) & 1) + 5) + 232LL);
      a1->IoStatus.Information = 32;
      VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v26);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        230,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)v6);
    }
    if ( v6 == -1070071728 || v6 == -1070071804 )
    {
      v19 = VmxpRecoverPackConfigOnline(v12, &v23) < 0;
      p_Flags = (struct _GUID *)&MasterIrp->Flags;
      if ( !v19 )
        continue;
    }
    goto LABEL_73;
  }
  v5 = WPP_GLOBAL_Control;
  v6 = -1070071738;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v7 = 229;
    goto LABEL_71;
  }
LABEL_73:
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v26);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140035e3c  mov     [rsp-40h+arg_0], rcx
0x140035e41  push    rbp
0x140035e42  push    rbx
0x140035e43  push    rsi
0x140035e44  push    rdi
0x140035e45  push    r12
0x140035e47  push    r13
0x140035e49  push    r14
0x140035e4b  push    r15
0x140035e4d  mov     rbp, rsp
0x140035e50  sub     rsp, 58h
0x140035e54  mov     rdi, [rcx+0B8h]
0x140035e5b  xor     r15d, r15d
0x140035e5e  mov     r14, [rcx+18h]
0x140035e62  xor     edx, edx; unsigned __int8
0x140035e64  lea     rcx, [rbp+arg_8]; this
0x140035e68  mov     [rbp+var_18], r15
0x140035e6c  mov     [rbp+var_10], r15
0x140035e70  mov     esi, r15d
0x140035e73  mov     [rbp+var_20], r15
0x140035e77  mov     r12d, r15d
0x140035e7a  mov     [rbp+arg_18], r15d
0x140035e7e  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x140035e83  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140035e8a  cmp     [rcx+111h], r15b
0x140035e91  jnz     short loc_140035ECE
0x140035e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140035e9a  lea     rdi, WPP_GLOBAL_Control
0x140035ea1  mov     ebx, 0C0380019h
0x140035ea6  cmp     rcx, rdi
0x140035ea9  jz      loc_140036285
0x140035eaf  mov     eax, [rcx+2Ch]
0x140035eb2  test    al, 2
0x140035eb4  jz      loc_140036285
0x140035eba  cmp     byte ptr [rcx+29h], 2
0x140035ebe  jb      loc_140036285
0x140035ec4  mov     edx, 0DDh
0x140035ec9  jmp     loc_140036272
0x140035ece  cmp     [rcx+112h], r15b
0x140035ed5  jnz     short loc_140035F12
0x140035ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x140035ede  lea     rdi, WPP_GLOBAL_Control
0x140035ee5  mov     ebx, 0C038005Bh
0x140035eea  cmp     rcx, rdi
0x140035eed  jz      loc_140036285
0x140035ef3  mov     eax, [rcx+2Ch]
0x140035ef6  test    al, 2
0x140035ef8  jz      loc_140036285
0x140035efe  cmp     byte ptr [rcx+29h], 2
0x140035f02  jb      loc_140036285
0x140035f08  mov     edx, 0DEh
0x140035f0d  jmp     loc_140036272
0x140035f12  mov     edx, [rdi+10h]
0x140035f15  mov     ebx, 0C000000Dh
0x140035f1a  cmp     edx, 70h ; 'p'
0x140035f1d  jnb     short loc_140035F55
0x140035f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035f26  lea     rdi, WPP_GLOBAL_Control
0x140035f2d  cmp     rcx, rdi
0x140035f30  jz      loc_140036285
0x140035f36  mov     eax, [rcx+2Ch]
0x140035f39  test    al, 2
0x140035f3b  jz      loc_140036285
0x140035f41  cmp     byte ptr [rcx+29h], 2
0x140035f45  jb      loc_140036285
0x140035f4b  mov     edx, 0DFh
0x140035f50  jmp     loc_140036272
0x140035f55  mov     eax, [r14+20h]
0x140035f59  add     eax, 20h ; ' '
0x140035f5c  cmp     eax, 20h ; ' '
0x140035f5f  jb      loc_140036248
0x140035f65  cmp     edx, eax
0x140035f67  jnb     short loc_140035F9F
0x140035f69  mov     rcx, cs:WPP_GLOBAL_Control
0x140035f70  lea     rdi, WPP_GLOBAL_Control
0x140035f77  cmp     rcx, rdi
0x140035f7a  jz      loc_140036285
0x140035f80  mov     eax, [rcx+2Ch]
0x140035f83  test    al, 2
0x140035f85  jz      loc_140036285
0x140035f8b  cmp     byte ptr [rcx+29h], 2
0x140035f8f  jb      loc_140036285
0x140035f95  mov     edx, 0E1h
0x140035f9a  jmp     loc_140036272
0x140035f9f  cmp     dword ptr [r14+24h], 2
0x140035fa4  jnz     short loc_140035FEA
0x140035fa6  cmp     [rcx+113h], r15b
0x140035fad  jnz     short loc_140035FEA
0x140035faf  mov     rcx, cs:WPP_GLOBAL_Control
0x140035fb6  lea     rdi, WPP_GLOBAL_Control
0x140035fbd  mov     ebx, 0C038005Ch
0x140035fc2  cmp     rcx, rdi
0x140035fc5  jz      loc_140036285
0x140035fcb  mov     eax, [rcx+2Ch]
0x140035fce  test    al, 2
0x140035fd0  jz      loc_140036285
0x140035fd6  cmp     byte ptr [rcx+29h], 2
0x140035fda  jb      loc_140036285
0x140035fe0  mov     edx, 0E2h
0x140035fe5  jmp     loc_140036272
0x140035fea  cmp     dword ptr [rdi+8], 20h ; ' '
0x140035fee  jnb     short loc_140036026
0x140035ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x140035ff7  lea     rdi, WPP_GLOBAL_Control
0x140035ffe  cmp     rcx, rdi
0x140036001  jz      loc_140036285
0x140036007  mov     eax, [rcx+2Ch]
0x14003600a  test    al, 2
0x14003600c  jz      loc_140036285
0x140036012  cmp     byte ptr [rcx+29h], 2
0x140036016  jb      loc_140036285
0x14003601c  mov     edx, 0E3h
0x140036021  jmp     loc_140036272
0x140036026  lea     rdx, [rbp+var_18]; struct VMX_PACK **
0x14003602a  mov     rcx, r14; struct _GUID *
0x14003602d  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x140036032  mov     ebx, eax
0x140036034  test    eax, eax
0x140036036  jns     short loc_140036072
0x140036038  mov     rcx, cs:WPP_GLOBAL_Control
0x14003603f  lea     rdi, WPP_GLOBAL_Control
0x140036046  cmp     rcx, rdi
0x140036049  jz      loc_140036285
0x14003604f  mov     edx, [rcx+2Ch]
0x140036052  test    dl, 2
0x140036055  jz      loc_140036285
0x14003605b  cmp     byte ptr [rcx+29h], 2
0x14003605f  jb      loc_140036285
0x140036065  mov     edx, 0E4h
0x14003606a  mov     r9d, eax
0x14003606d  jmp     loc_140036275
0x140036072  lea     rax, [r14+10h]
0x140036076  lea     rdi, WPP_GLOBAL_Control
0x14003607d  mov     r13, [rbp+var_18]
0x140036081  mov     rdx, rax; struct _GUID *
0x140036084  mov     rcx, [r13+10h]; this
0x140036088  call    ?FindVolumeById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindVolumeById(_GUID *)
0x14003608d  mov     r15, rax
0x140036090  test    rax, rax
0x140036093  jz      loc_140036223
0x140036099  movzx   ecx, word ptr [rax+40h]
0x14003609d  and     ecx, 1
0x1400360a0  mov     rcx, [rax+rcx*8+28h]
0x1400360a5  mov     eax, [rcx+9Ch]
0x1400360ab  mov     rcx, r13; this
0x1400360ae  mov     [rbp+var_28], eax
0x1400360b1  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x1400360b6  mov     ebx, eax
0x1400360b8  test    eax, eax
0x1400360ba  js      loc_140036156
0x1400360c0  lea     r9, [rbp+var_10]; struct VMX_RECORD **
0x1400360c4  mov     [rbp+arg_10], 0
0x1400360c8  lea     r8, [r14+20h]; struct _VM_PLEX_LAYOUT *
0x1400360cc  mov     rdx, r15; struct VMX_RECORD *
0x1400360cf  mov     rcx, r13; this
0x1400360d2  call    ?CreatePlexTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@PEAU_VM_PLEX_LAYOUT@@PEAPEAV2@@Z; VMX_PACK::CreatePlexTransaction(VMX_RECORD *,_VM_PLEX_LAYOUT *,VMX_RECORD * *)
0x1400360d7  mov     ebx, eax
0x1400360d9  test    eax, eax
0x1400360db  js      short loc_140036136
0x1400360dd  test    [rbp+var_28], 800000h
0x1400360e4  jz      short loc_140036125
0x1400360e6  mov     rdx, [rbp+var_10]; struct VMX_RECORD *
0x1400360ea  lea     rax, [rbp+arg_18]
0x1400360ee  lea     r9, [rbp+var_20]; struct VMX_RECORD ***
0x1400360f2  mov     [rsp+58h+var_38], rax; unsigned int *
0x1400360f7  xor     r8d, r8d; unsigned __int8
0x1400360fa  call    ?UpdatePartitionsQueryPlexDisks@VMX_PACK@@QEAAJPEAVVMX_RECORD@@EPEAPEAPEAV2@PEAK@Z; VMX_PACK::UpdatePartitionsQueryPlexDisks(VMX_RECORD *,uchar,VMX_RECORD * * *,ulong *)
0x1400360ff  mov     r12d, [rbp+arg_18]
0x140036103  mov     ebx, eax
0x140036105  mov     rsi, [rbp+var_20]
0x140036109  test    eax, eax
0x14003610b  js      short loc_140036136
0x14003610d  xor     r9d, r9d; unsigned __int8
0x140036110  mov     r8d, r12d; unsigned int
0x140036113  mov     rdx, rsi; struct VMX_RECORD **
0x140036116  call    ?UpdatePartitions@VMX_PACK@@QEAAJPEAPEAVVMX_RECORD@@KE@Z; VMX_PACK::UpdatePartitions(VMX_RECORD * *,ulong,uchar)
0x14003611b  mov     ebx, eax
0x14003611d  test    eax, eax
0x14003611f  js      short loc_140036136
0x140036121  mov     [rbp+arg_10], 1
0x140036125  mov     r8b, 1; unsigned __int8
0x140036128  xor     edx, edx; unsigned __int8
0x14003612a  mov     rcx, r13; this
0x14003612d  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x140036132  mov     ebx, eax
0x140036134  jmp     short loc_14003613E
0x140036136  mov     rcx, r13; this
0x140036139  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14003613e  test    ebx, ebx
0x140036140  jns     short loc_140036156
0x140036142  cmp     [rbp+arg_10], 0
0x140036146  jz      short loc_140036156
0x140036148  mov     r9b, 1; unsigned __int8
0x14003614b  mov     r8d, r12d; unsigned int
0x14003614e  mov     rdx, rsi; struct VMX_RECORD **
0x140036151  call    ?UpdatePartitions@VMX_PACK@@QEAAJPEAPEAVVMX_RECORD@@KE@Z; VMX_PACK::UpdatePartitions(VMX_RECORD * *,ulong,uchar)
0x140036156  test    rsi, rsi
0x140036159  jz      short loc_140036179
0x14003615b  xor     edx, edx; Tag
0x14003615d  mov     rcx, rsi; P
0x140036160  call    cs:__imp_ExFreePoolWithTag
0x140036167  nop     dword ptr [rax+rax+00h]
0x14003616c  xor     esi, esi
0x14003616e  xor     r12d, r12d
0x140036171  mov     [rbp+var_20], rsi
0x140036175  mov     [rbp+arg_18], r12d
0x140036179  test    ebx, ebx
0x14003617b  jns     short loc_1400361DF
0x14003617d  mov     rcx, cs:WPP_GLOBAL_Control
0x140036184  cmp     rcx, rdi
0x140036187  jz      short loc_1400361AE
0x140036189  mov     eax, [rcx+2Ch]
0x14003618c  test    al, 2
0x14003618e  jz      short loc_1400361AE
0x140036190  cmp     byte ptr [rcx+29h], 2
0x140036194  jb      short loc_1400361AE
0x140036196  mov     rcx, [rcx+18h]
0x14003619a  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x1400361a1  mov     edx, 0E6h
0x1400361a6  mov     r9d, ebx
0x1400361a9  call    WPP_SF_d
0x1400361ae  cmp     ebx, 0C0380050h
0x1400361b4  jz      short loc_1400361C2
0x1400361b6  cmp     ebx, 0C0380004h
0x1400361bc  jnz     loc_140036285
0x1400361c2  lea     rdx, [rbp+var_18]; struct VMX_PACK **
0x1400361c6  mov     rcx, r13; struct VMX_PACK *
0x1400361c9  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x1400361ce  test    eax, eax
0x1400361d0  lea     rax, [r14+10h]
0x1400361d4  jns     loc_14003607D
0x1400361da  jmp     loc_140036285
0x1400361df  mov     rax, [r13+10h]
0x1400361e3  mov     rcx, [rax+8]
0x1400361e7  movups  xmm0, xmmword ptr [rcx+8]
0x1400361eb  lea     rcx, [rbp+arg_8]; this
0x1400361ef  movdqu  xmmword ptr [r14], xmm0
0x1400361f4  movzx   eax, word ptr [r15+40h]
0x1400361f9  and     eax, 1
0x1400361fc  mov     rax, [r15+rax*8+28h]
0x140036201  movups  xmm0, xmmword ptr [rax+0E8h]
0x140036208  mov     rax, [rbp+arg_0]
0x14003620c  movdqu  xmmword ptr [r14+10h], xmm0
0x140036212  mov     qword ptr [rax+38h], 20h ; ' '
0x14003621a  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x14003621f  xor     eax, eax
0x140036221  jmp     short loc_140036290
0x140036223  mov     rcx, cs:WPP_GLOBAL_Control
0x14003622a  mov     ebx, 0C0380046h
0x14003622f  cmp     rcx, rdi
0x140036232  jz      short loc_140036285
0x140036234  mov     eax, [rcx+2Ch]
0x140036237  test    al, 2
0x140036239  jz      short loc_140036285
0x14003623b  cmp     byte ptr [rcx+29h], 2
0x14003623f  jb      short loc_140036285
0x140036241  mov     edx, 0E5h
0x140036246  jmp     short loc_140036272
0x140036248  mov     rcx, cs:WPP_GLOBAL_Control
0x14003624f  lea     rdi, WPP_GLOBAL_Control
0x140036256  mov     ebx, 0C0000095h
0x14003625b  cmp     rcx, rdi
0x14003625e  jz      short loc_140036285
0x140036260  mov     eax, [rcx+2Ch]
0x140036263  test    al, 2
0x140036265  jz      short loc_140036285
0x140036267  cmp     byte ptr [rcx+29h], 2
0x14003626b  jb      short loc_140036285
0x14003626d  mov     edx, 0E0h
0x140036272  mov     r9d, ebx
0x140036275  mov     rcx, [rcx+18h]
0x140036279  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140036280  call    WPP_SF_d
0x140036285  lea     rcx, [rbp+arg_8]; this
0x140036289  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x14003628e  mov     eax, ebx
0x140036290  add     rsp, 58h
0x140036294  pop     r15
0x140036296  pop     r14
0x140036298  pop     r13
0x14003629a  pop     r12
0x14003629c  pop     rdi
0x14003629d  pop     rsi
0x14003629e  pop     rbx
0x14003629f  pop     rbp
0x1400362a0  retn
```

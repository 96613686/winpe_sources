# VmxpDeleteVolumePartitions(_IRP *)

- ea: `0x140036e70`
- end: `0x1400372b9`
- name: `?VmxpDeleteVolumePartitions@@YAJPEAU_IRP@@@Z`
- size: `1097`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x1400099d8`
- `0x14001b9a0`
- `0x14002a3f4`
- `0x1400314e8`
- `0x140036e70`
- `0x14003acbc`
- `0x14003c244`
- `0x14003f51c`
- `0x14003ff74`
- `0x14004a70c`
- `0x14004bac0`
- `0x1400509bc`
- `0x1400578d0`
- `0x140057f54`
- `0x14005abb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003710e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003710e`

## pseudocode

```c
__int64 __fastcall VmxpDeleteVolumePartitions(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct _GUID *MasterIrp; // r13
  VMX_NOTIFICATION_QUEUE *v4; // rcx
  int v5; // edi
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // r9
  struct VMX_PACK *v9; // r15
  struct VMX_RECORD *VolumeById; // rax
  __int64 v11; // r8
  struct VMX_RECORD *v12; // r14
  __int64 v13; // rcx
  __int64 v14; // rdx
  VMX_PACK *v15; // rcx
  PVOID v16; // rbx
  VMX_PACK *v17; // rcx
  char v19; // [rsp+80h] [rbp+48h] BYREF
  unsigned int v20; // [rsp+88h] [rbp+50h] BYREF
  struct VMX_PACK *v21; // [rsp+90h] [rbp+58h] BYREF
  PVOID P; // [rsp+98h] [rbp+60h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  MasterIrp = (struct _GUID *)a1->AssociatedIrp.MasterIrp;
  v21 = 0;
  P = 0;
  v20 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v19, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v4 = WPP_GLOBAL_Control;
    v5 = -1070071783;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_70;
    }
    v6 = 210;
    goto LABEL_68;
  }
  v5 = -1073741811;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x20 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_70;
    }
    v6 = 211;
    goto LABEL_68;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x20 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_70;
    }
    v6 = 212;
LABEL_68:
    v8 = (unsigned int)v5;
LABEL_69:
    WPP_SF_d(*((_QWORD *)v4 + 3), v6, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v8);
    goto LABEL_70;
  }
  v7 = VmxpValidatePackIdInput(MasterIrp, &v21);
  v5 = v7;
  if ( v7 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_70;
    }
    v6 = 213;
    v8 = (unsigned int)v7;
    goto LABEL_69;
  }
  while ( 1 )
  {
    v9 = v21;
    VolumeById = VMX_CONFIG::FindVolumeById(*((VMX_CONFIG **)v21 + 2), MasterIrp + 1);
    v11 = 0;
    v12 = VolumeById;
    if ( !VolumeById )
      break;
    v13 = *((_WORD *)VolumeById + 32) & 1;
    v14 = *((_QWORD *)VolumeById + v13 + 5);
    if ( *(_DWORD *)(v14 + 160) > 1u )
    {
      if ( !*((_BYTE *)Global + 274) )
      {
        v4 = WPP_GLOBAL_Control;
        v5 = -1070071717;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v6 = 215;
          goto LABEL_68;
        }
        goto LABEL_70;
      }
    }
    else if ( VMX_VOLUME_INFO::IsRaid5(*((VMX_VOLUME_INFO **)VolumeById + v13 + 5))
           && *((_BYTE *)Global + 275) == (_BYTE)v11 )
    {
      v4 = WPP_GLOBAL_Control;
      v5 = -1070071716;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v6 = 216;
        goto LABEL_68;
      }
      goto LABEL_70;
    }
    if ( (*(_DWORD *)(v14 + 156) & 0x800000) == 0 )
    {
      v4 = WPP_GLOBAL_Control;
      v5 = -1070071734;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v6 = 217;
        goto LABEL_68;
      }
      goto LABEL_70;
    }
    if ( *(_QWORD *)(v14 + 248) == v11 )
    {
      v4 = WPP_GLOBAL_Control;
      v5 = -1070071733;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v6 = 218;
        goto LABEL_68;
      }
      goto LABEL_70;
    }
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 88LL))(v14);
    if ( v5 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v6 = 219;
        goto LABEL_68;
      }
      goto LABEL_70;
    }
    v5 = VMX_PACK::BeginTransaction(v9);
    if ( v5 >= 0 )
    {
      v5 = VMX_PACK::DeleteVolumePartitionsTransaction(v9, v12);
      if ( v5 < 0 )
      {
        VMX_PACK::AbortTransaction(v9);
      }
      else
      {
        v5 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v9, 0, 1);
        if ( v5 >= 0 )
        {
          VMX_PACK::UpdatePartitionsQueryVolumeDisks(v15, v12, 1, (struct VMX_RECORD ***)&P, &v20);
          v16 = P;
          VMX_PACK::UpdatePartitions(v17, (struct VMX_RECORD **)P, v20, 1);
          if ( v16 )
            ExFreePoolWithTag(v16, 0);
          *MasterIrp = *(struct _GUID *)(*(_QWORD *)(*((_QWORD *)v9 + 2) + 8LL) + 8LL);
          MasterIrp[1] = *(struct _GUID *)(*((_QWORD *)v12 + (*((_WORD *)v12 + 32) & 1) + 5) + 232LL);
          a1->IoStatus.Information = 32;
          VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v19);
          return 0;
        }
      }
    }
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        220,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)v5);
    }
    if ( v5 != -1070071728 && v5 != -1070071804 || VmxpRecoverPackConfigOnline(v9, &v21) < 0 )
      goto LABEL_70;
  }
  v4 = WPP_GLOBAL_Control;
  v5 = -1070071738;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v6 = 214;
    goto LABEL_68;
  }
LABEL_70:
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140036e70  push    rbp
0x140036e72  push    rbx
0x140036e73  push    rsi
0x140036e74  push    rdi
0x140036e75  push    r12
0x140036e77  push    r13
0x140036e79  push    r14
0x140036e7b  push    r15
0x140036e7d  mov     rbp, rsp
0x140036e80  sub     rsp, 38h
0x140036e84  mov     rbx, [rcx+0B8h]
0x140036e8b  xor     esi, esi
0x140036e8d  mov     r13, [rcx+18h]
0x140036e91  mov     r12, rcx
0x140036e94  lea     rcx, [rbp+arg_0]; this
0x140036e98  mov     [rbp+arg_10], rsi
0x140036e9c  xor     edx, edx; unsigned __int8
0x140036e9e  mov     [rbp+P], rsi
0x140036ea2  mov     [rbp+arg_8], esi
0x140036ea5  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x140036eaa  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140036eb1  cmp     [rax+111h], sil
0x140036eb8  jnz     short loc_140036EF6
0x140036eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140036ec1  lea     rsi, WPP_GLOBAL_Control
0x140036ec8  mov     edi, 0C0380019h
0x140036ecd  cmp     rcx, rsi
0x140036ed0  jz      loc_14003729C
0x140036ed6  mov     eax, [rcx+2Ch]
0x140036ed9  mov     bl, 2
0x140036edb  test    bl, al
0x140036edd  jz      loc_14003729C
0x140036ee3  cmp     [rcx+29h], bl
0x140036ee6  jb      loc_14003729C
0x140036eec  mov     edx, 0D2h
0x140036ef1  jmp     loc_140037289
0x140036ef6  cmp     dword ptr [rbx+10h], 20h ; ' '
0x140036efa  mov     edi, 0C000000Dh
0x140036eff  jnb     short loc_140036F38
0x140036f01  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f08  lea     rsi, WPP_GLOBAL_Control
0x140036f0f  cmp     rcx, rsi
0x140036f12  jz      loc_14003729C
0x140036f18  mov     eax, [rcx+2Ch]
0x140036f1b  mov     bl, 2
0x140036f1d  test    bl, al
0x140036f1f  jz      loc_14003729C
0x140036f25  cmp     [rcx+29h], bl
0x140036f28  jb      loc_14003729C
0x140036f2e  mov     edx, 0D3h
0x140036f33  jmp     loc_140037289
0x140036f38  cmp     dword ptr [rbx+8], 20h ; ' '
0x140036f3c  jnb     short loc_140036F75
0x140036f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f45  lea     rsi, WPP_GLOBAL_Control
0x140036f4c  cmp     rcx, rsi
0x140036f4f  jz      loc_14003729C
0x140036f55  mov     eax, [rcx+2Ch]
0x140036f58  mov     bl, 2
0x140036f5a  test    bl, al
0x140036f5c  jz      loc_14003729C
0x140036f62  cmp     [rcx+29h], bl
0x140036f65  jb      loc_14003729C
0x140036f6b  mov     edx, 0D4h
0x140036f70  jmp     loc_140037289
0x140036f75  lea     rdx, [rbp+arg_10]; struct VMX_PACK **
0x140036f79  mov     rcx, r13; struct _GUID *
0x140036f7c  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x140036f81  mov     edi, eax
0x140036f83  test    eax, eax
0x140036f85  jns     short loc_140036FC1
0x140036f87  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f8e  lea     rsi, WPP_GLOBAL_Control
0x140036f95  cmp     rcx, rsi
0x140036f98  jz      loc_14003729C
0x140036f9e  mov     edx, [rcx+2Ch]
0x140036fa1  mov     bl, 2
0x140036fa3  test    bl, dl
0x140036fa5  jz      loc_14003729C
0x140036fab  cmp     [rcx+29h], bl
0x140036fae  jb      loc_14003729C
0x140036fb4  mov     edx, 0D5h
0x140036fb9  mov     r9d, eax
0x140036fbc  jmp     loc_14003728C
0x140036fc1  lea     rsi, WPP_GLOBAL_Control
0x140036fc8  mov     bl, 2
0x140036fca  lea     rax, [r13+10h]
0x140036fce  mov     r15, [rbp+arg_10]
0x140036fd2  mov     rdx, rax; struct _GUID *
0x140036fd5  mov     rcx, [r15+10h]; this
0x140036fd9  call    ?FindVolumeById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindVolumeById(_GUID *)
0x140036fde  xor     r8d, r8d
0x140036fe1  mov     r14, rax
0x140036fe4  test    rax, rax
0x140036fe7  jz      loc_140037267
0x140036fed  movzx   ecx, word ptr [rax+40h]
0x140036ff1  and     ecx, 1
0x140036ff4  mov     rdx, [rax+rcx*8+28h]
0x140036ff9  cmp     dword ptr [rdx+0A0h], 1
0x140037000  ja      short loc_140037051
0x140037002  mov     rcx, rdx; this
0x140037005  call    ?IsRaid5@VMX_VOLUME_INFO@@QEAAEXZ; VMX_VOLUME_INFO::IsRaid5(void)
0x14003700a  test    al, al
0x14003700c  jz      short loc_140037065
0x14003700e  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140037015  cmp     [rax+113h], r8b
0x14003701c  jnz     short loc_140037065
0x14003701e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037025  mov     edi, 0C038005Ch
0x14003702a  cmp     rcx, rsi
0x14003702d  jz      loc_14003729C
0x140037033  mov     eax, [rcx+2Ch]
0x140037036  test    bl, al
0x140037038  jz      loc_14003729C
0x14003703e  cmp     [rcx+29h], bl
0x140037041  jb      loc_14003729C
0x140037047  mov     edx, 0D8h
0x14003704c  jmp     loc_140037289
0x140037051  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140037058  cmp     [rax+112h], r8b
0x14003705f  jz      loc_140037243
0x140037065  test    dword ptr [rdx+9Ch], 800000h
0x14003706f  jz      loc_14003721F
0x140037075  cmp     [rdx+0F8h], r8
0x14003707c  jz      loc_1400371EF
0x140037082  mov     rax, [rdx]
0x140037085  mov     rcx, rdx
0x140037088  mov     rax, [rax+58h]
0x14003708c  call    _guard_dispatch_icall
0x140037091  mov     edi, eax
0x140037093  test    eax, eax
0x140037095  js      loc_1400371C1
0x14003709b  mov     rcx, r15; this
0x14003709e  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x1400370a3  mov     edi, eax
0x1400370a5  test    eax, eax
0x1400370a7  js      loc_140037164
0x1400370ad  mov     rdx, r14; struct VMX_RECORD *
0x1400370b0  mov     rcx, r15; this
0x1400370b3  call    ?DeleteVolumePartitionsTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::DeleteVolumePartitionsTransaction(VMX_RECORD *)
0x1400370b8  mov     edi, eax
0x1400370ba  mov     rcx, r15; this
0x1400370bd  test    eax, eax
0x1400370bf  js      loc_14003715F
0x1400370c5  mov     r8b, 1; unsigned __int8
0x1400370c8  xor     edx, edx; unsigned __int8
0x1400370ca  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x1400370cf  mov     edi, eax
0x1400370d1  test    eax, eax
0x1400370d3  js      loc_140037164
0x1400370d9  lea     rax, [rbp+arg_8]
0x1400370dd  mov     r8b, 1; unsigned __int8
0x1400370e0  lea     r9, [rbp+P]; struct VMX_RECORD ***
0x1400370e4  mov     [rsp+38h+var_18], rax; unsigned int *
0x1400370e9  mov     rdx, r14; struct VMX_RECORD *
0x1400370ec  call    ?UpdatePartitionsQueryVolumeDisks@VMX_PACK@@QEAAJPEAVVMX_RECORD@@EPEAPEAPEAV2@PEAK@Z; VMX_PACK::UpdatePartitionsQueryVolumeDisks(VMX_RECORD *,uchar,VMX_RECORD * * *,ulong *)
0x1400370f1  mov     rbx, [rbp+P]
0x1400370f5  mov     r9b, 1; unsigned __int8
0x1400370f8  mov     r8d, [rbp+arg_8]; unsigned int
0x1400370fc  mov     rdx, rbx; struct VMX_RECORD **
0x1400370ff  call    ?UpdatePartitions@VMX_PACK@@QEAAJPEAPEAVVMX_RECORD@@KE@Z; VMX_PACK::UpdatePartitions(VMX_RECORD * *,ulong,uchar)
0x140037104  test    rbx, rbx
0x140037107  jz      short loc_14003711A
0x140037109  xor     edx, edx; Tag
0x14003710b  mov     rcx, rbx; P
0x14003710e  call    cs:__imp_ExFreePoolWithTag
0x140037115  nop     dword ptr [rax+rax+00h]
0x14003711a  mov     rax, [r15+10h]
0x14003711e  mov     rcx, [rax+8]
0x140037122  movups  xmm0, xmmword ptr [rcx+8]
0x140037126  lea     rcx, [rbp+arg_0]; this
0x14003712a  movdqu  xmmword ptr [r13+0], xmm0
0x140037130  movzx   eax, word ptr [r14+40h]
0x140037135  and     eax, 1
0x140037138  mov     rax, [r14+rax*8+28h]
0x14003713d  movups  xmm0, xmmword ptr [rax+0E8h]
0x140037144  movdqu  xmmword ptr [r13+10h], xmm0
0x14003714a  mov     qword ptr [r12+38h], 20h ; ' '
0x140037153  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x140037158  xor     eax, eax
0x14003715a  jmp     loc_1400372A7
0x14003715f  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140037164  mov     rcx, cs:WPP_GLOBAL_Control
0x14003716b  cmp     rcx, rsi
0x14003716e  jz      short loc_140037194
0x140037170  mov     eax, [rcx+2Ch]
0x140037173  test    bl, al
0x140037175  jz      short loc_140037194
0x140037177  cmp     [rcx+29h], bl
0x14003717a  jb      short loc_140037194
0x14003717c  mov     rcx, [rcx+18h]
0x140037180  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140037187  mov     edx, 0DCh
0x14003718c  mov     r9d, edi
0x14003718f  call    WPP_SF_d
0x140037194  cmp     edi, 0C0380050h
0x14003719a  jz      short loc_1400371A8
0x14003719c  cmp     edi, 0C0380004h
0x1400371a2  jnz     loc_14003729C
0x1400371a8  lea     rdx, [rbp+arg_10]; struct VMX_PACK **
0x1400371ac  mov     rcx, r15; struct VMX_PACK *
0x1400371af  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x1400371b4  test    eax, eax
0x1400371b6  js      loc_14003729C
0x1400371bc  jmp     loc_140036FCA
0x1400371c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371c8  cmp     rcx, rsi
0x1400371cb  jz      loc_14003729C
0x1400371d1  mov     eax, [rcx+2Ch]
0x1400371d4  test    al, 8
0x1400371d6  jz      loc_14003729C
0x1400371dc  cmp     [rcx+29h], bl
0x1400371df  jb      loc_14003729C
0x1400371e5  mov     edx, 0DBh
0x1400371ea  jmp     loc_140037289
0x1400371ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371f6  mov     edi, 0C038004Bh
0x1400371fb  cmp     rcx, rsi
0x1400371fe  jz      loc_14003729C
0x140037204  mov     eax, [rcx+2Ch]
0x140037207  test    bl, al
0x140037209  jz      loc_14003729C
0x14003720f  cmp     [rcx+29h], bl
0x140037212  jb      loc_14003729C
0x140037218  mov     edx, 0DAh
0x14003721d  jmp     short loc_140037289
0x14003721f  mov     rcx, cs:WPP_GLOBAL_Control
0x140037226  mov     edi, 0C038004Ah
0x14003722b  cmp     rcx, rsi
0x14003722e  jz      short loc_14003729C
0x140037230  mov     eax, [rcx+2Ch]
0x140037233  test    bl, al
0x140037235  jz      short loc_14003729C
0x140037237  cmp     [rcx+29h], bl
0x14003723a  jb      short loc_14003729C
0x14003723c  mov     edx, 0D9h
0x140037241  jmp     short loc_140037289
0x140037243  mov     rcx, cs:WPP_GLOBAL_Control
0x14003724a  mov     edi, 0C038005Bh
0x14003724f  cmp     rcx, rsi
0x140037252  jz      short loc_14003729C
0x140037254  mov     eax, [rcx+2Ch]
0x140037257  test    bl, al
0x140037259  jz      short loc_14003729C
0x14003725b  cmp     [rcx+29h], bl
0x14003725e  jb      short loc_14003729C
0x140037260  mov     edx, 0D7h
0x140037265  jmp     short loc_140037289
0x140037267  mov     rcx, cs:WPP_GLOBAL_Control
0x14003726e  mov     edi, 0C0380046h
0x140037273  cmp     rcx, rsi
0x140037276  jz      short loc_14003729C
0x140037278  mov     eax, [rcx+2Ch]
0x14003727b  test    bl, al
0x14003727d  jz      short loc_14003729C
0x14003727f  cmp     [rcx+29h], bl
0x140037282  jb      short loc_14003729C
0x140037284  mov     edx, 0D6h
0x140037289  mov     r9d, edi
0x14003728c  mov     rcx, [rcx+18h]
0x140037290  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140037297  call    WPP_SF_d
0x14003729c  lea     rcx, [rbp+arg_0]; this
0x1400372a0  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x1400372a5  mov     eax, edi
0x1400372a7  add     rsp, 38h
0x1400372ab  pop     r15
0x1400372ad  pop     r14
0x1400372af  pop     r13
0x1400372b1  pop     r12
0x1400372b3  pop     rdi
0x1400372b4  pop     rsi
0x1400372b5  pop     rbx
0x1400372b6  pop     rbp
0x1400372b7  retn
```

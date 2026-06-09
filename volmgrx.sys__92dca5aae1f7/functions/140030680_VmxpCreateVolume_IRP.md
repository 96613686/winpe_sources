# VmxpCreateVolume(_IRP *)

- ea: `0x140030680`
- end: `0x1400309fe`
- name: `?VmxpCreateVolume@@YAJPEAU_IRP@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x1400099d8`
- `0x14002a3f4`
- `0x140030680`
- `0x1400314e8`
- `0x14003acbc`
- `0x14003c244`
- `0x14004a70c`
- `0x14004bac0`
- `0x14005013c`
- `0x14005abb4`

## pseudocode

```c
__int64 __fastcall VmxpCreateVolume(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct _IRP *MasterIrp; // rsi
  VMX_NOTIFICATION_QUEUE *v4; // rcx
  int v5; // edi
  __int64 v6; // rdx
  unsigned int Options; // ecx
  int v8; // eax
  __int64 v9; // r11
  __int64 v10; // r9
  struct VMX_PACK *v11; // rbp
  struct VMX_RECORD *v12; // rcx
  __int64 v13; // rax
  char v15; // [rsp+60h] [rbp+8h] BYREF
  struct VMX_PACK *v16; // [rsp+68h] [rbp+10h] BYREF
  struct VMX_RECORD *v17; // [rsp+70h] [rbp+18h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  v16 = 0;
  v17 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v15, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v4 = WPP_GLOBAL_Control;
    v5 = -1070071783;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_61;
    }
    v6 = 167;
    goto LABEL_59;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  v5 = -1073741811;
  if ( Options < 0x80 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_61;
    }
    v6 = 168;
    goto LABEL_59;
  }
  if ( LODWORD(MasterIrp->ThreadListEntry.Flink) >= 0xFFFFFFE0 )
  {
    v4 = WPP_GLOBAL_Control;
    v5 = -1073741675;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_61;
    }
    v6 = 169;
    goto LABEL_59;
  }
  if ( Options < LODWORD(MasterIrp->ThreadListEntry.Flink) + 32 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_61;
    }
    v6 = 170;
    goto LABEL_59;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x20 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_61;
    }
    v6 = 171;
    goto LABEL_59;
  }
  v8 = VmxpValidatePackIdInput((struct _GUID *)MasterIrp, &v16);
  v5 = v8;
  if ( v8 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_61;
    }
    v6 = 172;
    v10 = (unsigned int)v8;
    goto LABEL_60;
  }
  if ( HIDWORD(MasterIrp->ThreadListEntry.Flink) > 1 )
  {
    if ( *(_BYTE *)(v9 + 274) )
      goto LABEL_39;
    v4 = WPP_GLOBAL_Control;
    v5 = -1070071717;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_61;
    }
    v6 = 173;
LABEL_59:
    v10 = (unsigned int)v5;
LABEL_60:
    WPP_SF_d(*((_QWORD *)v4 + 3), v6, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v10);
LABEL_61:
    VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v15);
    return (unsigned int)v5;
  }
  if ( HIDWORD(MasterIrp->IoStatus.Pointer) == 2 && !*(_BYTE *)(v9 + 275) )
  {
    v4 = WPP_GLOBAL_Control;
    v5 = -1070071716;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_61;
    }
    v6 = 174;
    goto LABEL_59;
  }
  while ( 1 )
  {
LABEL_39:
    v11 = v16;
    v5 = VMX_PACK::BeginTransaction(v16);
    if ( v5 < 0 )
      goto LABEL_45;
    v5 = VMX_PACK::CreateVolumeTransaction(
           (VMX_CONFIG **)v11,
           (struct _GUID *)&MasterIrp->Flags,
           (struct _VM_VOLUME_LAYOUT *)&MasterIrp->ThreadListEntry,
           &v17);
    if ( v5 >= 0 )
      break;
    VMX_PACK::AbortTransaction(v11);
LABEL_45:
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        175,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)v5);
    }
    if ( v5 != -1070071728 && v5 != -1070071804 || VmxpRecoverPackConfigOnline(v11, &v16) < 0 )
      goto LABEL_61;
  }
  v5 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v11, 0, 1);
  if ( v5 < 0 )
    goto LABEL_45;
  v12 = v17;
  *(_OWORD *)&MasterIrp->Type = *(_OWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 2) + 8LL) + 8LL);
  if ( (*((_BYTE *)v12 + 64) & 1) != 0 )
    v13 = *((_QWORD *)v12 + 6);
  else
    v13 = *((_QWORD *)v12 + 5);
  *(_OWORD *)&MasterIrp->Flags = *(_OWORD *)(v13 + 232);
  a1->IoStatus.Information = 32;
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v15);
  return 0;
}

```

## disassembly

```asm
0x140030680  push    rbx
0x140030682  push    rbp
0x140030683  push    rsi
0x140030684  push    rdi
0x140030685  push    r12
0x140030687  push    r14
0x140030689  push    r15
0x14003068b  sub     rsp, 20h
0x14003068f  mov     rbx, [rcx+0B8h]
0x140030696  mov     r14, rcx
0x140030699  mov     rsi, [rcx+18h]
0x14003069d  xor     edx, edx; unsigned __int8
0x14003069f  lea     rcx, [rsp+58h+arg_0]; this
0x1400306a4  mov     [rsp+58h+arg_8], 0
0x1400306ad  mov     [rsp+58h+arg_10], 0
0x1400306b6  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x1400306bb  mov     r11, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400306c2  cmp     byte ptr [r11+111h], 0
0x1400306ca  jnz     short loc_140030707
0x1400306cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400306d3  lea     rbx, WPP_GLOBAL_Control
0x1400306da  mov     edi, 0C0380019h
0x1400306df  cmp     rcx, rbx
0x1400306e2  jz      loc_1400309E2
0x1400306e8  mov     eax, [rcx+2Ch]
0x1400306eb  test    al, 2
0x1400306ed  jz      loc_1400309E2
0x1400306f3  cmp     byte ptr [rcx+29h], 2
0x1400306f7  jb      loc_1400309E2
0x1400306fd  mov     edx, 0A7h
0x140030702  jmp     loc_1400309CF
0x140030707  mov     ecx, [rbx+10h]
0x14003070a  mov     edi, 0C000000Dh
0x14003070f  cmp     ecx, 80h
0x140030715  jnb     short loc_14003074D
0x140030717  mov     rcx, cs:WPP_GLOBAL_Control
0x14003071e  lea     rbx, WPP_GLOBAL_Control
0x140030725  cmp     rcx, rbx
0x140030728  jz      loc_1400309E2
0x14003072e  mov     eax, [rcx+2Ch]
0x140030731  test    al, 2
0x140030733  jz      loc_1400309E2
0x140030739  cmp     byte ptr [rcx+29h], 2
0x14003073d  jb      loc_1400309E2
0x140030743  mov     edx, 0A8h
0x140030748  jmp     loc_1400309CF
0x14003074d  mov     eax, [rsi+20h]
0x140030750  add     eax, 20h ; ' '
0x140030753  cmp     eax, 20h ; ' '
0x140030756  jb      loc_1400309A5
0x14003075c  cmp     ecx, eax
0x14003075e  jnb     short loc_140030796
0x140030760  mov     rcx, cs:WPP_GLOBAL_Control
0x140030767  lea     rbx, WPP_GLOBAL_Control
0x14003076e  cmp     rcx, rbx
0x140030771  jz      loc_1400309E2
0x140030777  mov     eax, [rcx+2Ch]
0x14003077a  test    al, 2
0x14003077c  jz      loc_1400309E2
0x140030782  cmp     byte ptr [rcx+29h], 2
0x140030786  jb      loc_1400309E2
0x14003078c  mov     edx, 0AAh
0x140030791  jmp     loc_1400309CF
0x140030796  cmp     dword ptr [rbx+8], 20h ; ' '
0x14003079a  jnb     short loc_1400307D2
0x14003079c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307a3  lea     rbx, WPP_GLOBAL_Control
0x1400307aa  cmp     rcx, rbx
0x1400307ad  jz      loc_1400309E2
0x1400307b3  mov     eax, [rcx+2Ch]
0x1400307b6  test    al, 2
0x1400307b8  jz      loc_1400309E2
0x1400307be  cmp     byte ptr [rcx+29h], 2
0x1400307c2  jb      loc_1400309E2
0x1400307c8  mov     edx, 0ABh
0x1400307cd  jmp     loc_1400309CF
0x1400307d2  lea     rdx, [rsp+58h+arg_8]; struct VMX_PACK **
0x1400307d7  mov     rcx, rsi; struct _GUID *
0x1400307da  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x1400307df  mov     edi, eax
0x1400307e1  test    eax, eax
0x1400307e3  jns     short loc_14003081F
0x1400307e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307ec  lea     rbx, WPP_GLOBAL_Control
0x1400307f3  cmp     rcx, rbx
0x1400307f6  jz      loc_1400309E2
0x1400307fc  mov     edx, [rcx+2Ch]
0x1400307ff  test    dl, 2
0x140030802  jz      loc_1400309E2
0x140030808  cmp     byte ptr [rcx+29h], 2
0x14003080c  jb      loc_1400309E2
0x140030812  mov     edx, 0ACh
0x140030817  mov     r9d, eax
0x14003081a  jmp     loc_1400309D2
0x14003081f  cmp     dword ptr [rsi+24h], 1
0x140030823  jbe     short loc_14003086E
0x140030825  cmp     byte ptr [r11+112h], 0
0x14003082d  jnz     loc_1400308B9
0x140030833  mov     rcx, cs:WPP_GLOBAL_Control
0x14003083a  lea     rbx, WPP_GLOBAL_Control
0x140030841  mov     edi, 0C038005Bh
0x140030846  cmp     rcx, rbx
0x140030849  jz      loc_1400309E2
0x14003084f  mov     eax, [rcx+2Ch]
0x140030852  test    al, 2
0x140030854  jz      loc_1400309E2
0x14003085a  cmp     byte ptr [rcx+29h], 2
0x14003085e  jb      loc_1400309E2
0x140030864  mov     edx, 0ADh
0x140030869  jmp     loc_1400309CF
0x14003086e  cmp     dword ptr [rsi+34h], 2
0x140030872  jnz     short loc_1400308B9
0x140030874  cmp     byte ptr [r11+113h], 0
0x14003087c  jnz     short loc_1400308B9
0x14003087e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030885  lea     rbx, WPP_GLOBAL_Control
0x14003088c  mov     edi, 0C038005Ch
0x140030891  cmp     rcx, rbx
0x140030894  jz      loc_1400309E2
0x14003089a  mov     eax, [rcx+2Ch]
0x14003089d  test    al, 2
0x14003089f  jz      loc_1400309E2
0x1400308a5  cmp     byte ptr [rcx+29h], 2
0x1400308a9  jb      loc_1400309E2
0x1400308af  mov     edx, 0AEh
0x1400308b4  jmp     loc_1400309CF
0x1400308b9  lea     rbx, WPP_GLOBAL_Control
0x1400308c0  mov     rbp, [rsp+58h+arg_8]
0x1400308c5  mov     rcx, rbp; this
0x1400308c8  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x1400308cd  mov     edi, eax
0x1400308cf  test    eax, eax
0x1400308d1  js      short loc_140030927
0x1400308d3  lea     r9, [rsp+58h+arg_10]; struct VMX_RECORD **
0x1400308d8  mov     rcx, rbp; this
0x1400308db  lea     r8, [rsi+20h]; struct _VM_VOLUME_LAYOUT *
0x1400308df  lea     rdx, [rsi+10h]; struct _GUID *
0x1400308e3  call    ?CreateVolumeTransaction@VMX_PACK@@QEAAJPEAU_GUID@@PEAU_VM_VOLUME_LAYOUT@@PEAPEAVVMX_RECORD@@@Z; VMX_PACK::CreateVolumeTransaction(_GUID *,_VM_VOLUME_LAYOUT *,VMX_RECORD * *)
0x1400308e8  mov     edi, eax
0x1400308ea  mov     rcx, rbp; this
0x1400308ed  test    eax, eax
0x1400308ef  js      short loc_140030922
0x1400308f1  mov     r8b, 1; unsigned __int8
0x1400308f4  xor     edx, edx; unsigned __int8
0x1400308f6  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x1400308fb  mov     edi, eax
0x1400308fd  test    eax, eax
0x1400308ff  js      short loc_140030927
0x140030901  mov     rax, [rbp+10h]
0x140030905  mov     rcx, [rax+8]
0x140030909  movups  xmm0, xmmword ptr [rcx+8]
0x14003090d  mov     rcx, [rsp+58h+arg_10]
0x140030912  movdqu  xmmword ptr [rsi], xmm0
0x140030916  test    byte ptr [rcx+40h], 1
0x14003091a  jz      short loc_14003097F
0x14003091c  mov     rax, [rcx+30h]
0x140030920  jmp     short loc_140030983
0x140030922  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x140030927  mov     rcx, cs:WPP_GLOBAL_Control
0x14003092e  cmp     rcx, rbx
0x140030931  jz      short loc_140030958
0x140030933  mov     eax, [rcx+2Ch]
0x140030936  test    al, 2
0x140030938  jz      short loc_140030958
0x14003093a  cmp     byte ptr [rcx+29h], 2
0x14003093e  jb      short loc_140030958
0x140030940  mov     rcx, [rcx+18h]
0x140030944  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003094b  mov     edx, 0AFh
0x140030950  mov     r9d, edi
0x140030953  call    WPP_SF_d
0x140030958  cmp     edi, 0C0380050h
0x14003095e  jz      short loc_140030968
0x140030960  cmp     edi, 0C0380004h
0x140030966  jnz     short loc_1400309E2
0x140030968  lea     rdx, [rsp+58h+arg_8]; struct VMX_PACK **
0x14003096d  mov     rcx, rbp; struct VMX_PACK *
0x140030970  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x140030975  test    eax, eax
0x140030977  jns     loc_1400308C0
0x14003097d  jmp     short loc_1400309E2
0x14003097f  mov     rax, [rcx+28h]
0x140030983  movups  xmm0, xmmword ptr [rax+0E8h]
0x14003098a  lea     rcx, [rsp+58h+arg_0]; this
0x14003098f  movdqu  xmmword ptr [rsi+10h], xmm0
0x140030994  mov     qword ptr [r14+38h], 20h ; ' '
0x14003099c  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x1400309a1  xor     eax, eax
0x1400309a3  jmp     short loc_1400309EE
0x1400309a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400309ac  lea     rbx, WPP_GLOBAL_Control
0x1400309b3  mov     edi, 0C0000095h
0x1400309b8  cmp     rcx, rbx
0x1400309bb  jz      short loc_1400309E2
0x1400309bd  mov     eax, [rcx+2Ch]
0x1400309c0  test    al, 2
0x1400309c2  jz      short loc_1400309E2
0x1400309c4  cmp     byte ptr [rcx+29h], 2
0x1400309c8  jb      short loc_1400309E2
0x1400309ca  mov     edx, 0A9h
0x1400309cf  mov     r9d, edi
0x1400309d2  mov     rcx, [rcx+18h]
0x1400309d6  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x1400309dd  call    WPP_SF_d
0x1400309e2  lea     rcx, [rsp+58h+arg_0]; this
0x1400309e7  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x1400309ec  mov     eax, edi
0x1400309ee  add     rsp, 20h
0x1400309f2  pop     r15
0x1400309f4  pop     r14
0x1400309f6  pop     r12
0x1400309f8  pop     rdi
0x1400309f9  pop     rsi
0x1400309fa  pop     rbp
0x1400309fb  pop     rbx
0x1400309fc  retn
```

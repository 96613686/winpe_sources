# CUsbBusFilter::EvtQueryBusRelationsCompletionWorkItemCallback(_IRP *)

- ea: `0x140003258`
- end: `0x1400039e2`
- name: `?EvtQueryBusRelationsCompletionWorkItemCallback@CUsbBusFilter@@QEAAXPEAU_IRP@@@Z`
- size: `1930`
- prototype: `void __fastcall(CUsbBusFilter *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400126b0`

## callees

- `0x140001e80`
- `0x140003258`
- `0x140004a18`
- `0x140004c74`
- `0x140004f18`
- `0x140004f48`
- `0x1400051b4`
- `0x140006278`
- `0x14000aa30`

## import_xrefs

- `ntoskrnl!IoGetLowerDeviceObject` at `0x140003754`
- `ntoskrnl!IoGetLowerDeviceObject` at `0x140003754`
- `ntoskrnl!IofCompleteRequest` at `0x14000387e`
- `ntoskrnl!IofCompleteRequest` at `0x14000387e`
- `ntoskrnl!ObfDereferenceObject` at `0x140003766`
- `ntoskrnl!ObfDereferenceObject` at `0x140003785`
- `ntoskrnl!ObfDereferenceObject` at `0x1400038b4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400038fe`
- `ntoskrnl!ObfDereferenceObject` at `0x140003766`
- `ntoskrnl!ObfDereferenceObject` at `0x140003785`
- `ntoskrnl!ObfDereferenceObject` at `0x1400038b4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400038fe`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400036e4`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400036e4`

## pseudocode

```c
void __fastcall CUsbBusFilter::EvtQueryBusRelationsCompletionWorkItemCallback(
        CUsbFilterControl **this,
        struct _IRP *a2)
{
  _DWORD *Information; // r13
  CUsbFilterControl *v4; // rdx
  struct _LIST_ENTRY *Blink; // rax
  __int64 v6; // rax
  CUsbFilterControl *v7; // rdx
  PVOID v8; // r15
  int v9; // eax
  char v10; // si
  unsigned int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // r15d
  __int64 v14; // r12
  unsigned int v15; // ebx
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // r14
  bool v21; // zf
  __int64 v22; // r12
  unsigned int v23; // eax
  unsigned int v24; // ebx
  unsigned int v25; // r15d
  __int64 v26; // rax
  struct _DEVICE_OBJECT *v27; // rcx
  __int64 v28; // r14
  char v29; // bl
  PDEVICE_OBJECT AttachedDeviceReference; // r12
  __int64 v31; // rax
  PDEVICE_OBJECT LowerDeviceObject; // rbx
  __int64 v33; // r12
  unsigned int v34; // ebx
  unsigned int v35; // r14d
  int v36; // eax
  PVOID Object; // [rsp+30h] [rbp-48h] BYREF
  struct WDFCOLLECTION__ *v38; // [rsp+38h] [rbp-40h] BYREF
  struct _DRIVER_OBJECT *v39; // [rsp+40h] [rbp-38h]
  __int64 v40; // [rsp+48h] [rbp-30h]
  struct CUsbPdoFilter *v41; // [rsp+50h] [rbp-28h] BYREF
  struct _GUID v42; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v43; // [rsp+C0h] [rbp+48h] BYREF
  PIRP Irp; // [rsp+C8h] [rbp+50h]
  int v45; // [rsp+D0h] [rbp+58h]
  void *v46; // [rsp+D8h] [rbp+60h] BYREF

  Irp = a2;
  Information = (_DWORD *)a2->IoStatus.Information;
  v4 = *this;
  v46 = 0;
  Blink = WPP_MAIN_CB.Queue.ListEntry.Flink[15].Blink;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *))Blink)(WPP_MAIN_CB.Queue.ListEntry.Blink, v4);
  v7 = *this;
  v39 = *(struct _DRIVER_OBJECT **)(v6 + 8);
  ((void (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *))WPP_MAIN_CB.Queue.ListEntry.Flink[66].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    v7);
  v8 = 0;
  Object = 0;
  v38 = 0;
  if ( *Information )
  {
    v9 = CUsbFilterControl::AllocateClaimCheckCollectionSnapshot(this[4], &v43, &v38);
    if ( v9 < 0 )
    {
      v10 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
          (unsigned int)v9);
      goto LABEL_57;
    }
  }
  ((void (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    *this);
  v10 = 1;
  v11 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          this[3]);
  v12 = 0;
  v43 = v11;
  if ( v11 )
  {
    v13 = v11;
    do
    {
      v46 = (void *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                      this[3],
                      v12++);
      *(_BYTE *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, void *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  v46,
                  off_14000F150) = 0;
    }
    while ( v12 < v13 );
    v8 = Object;
    v11 = v43;
  }
  v14 = 0;
  if ( *Information )
  {
    do
    {
      v15 = 0;
      if ( v11 )
      {
        while ( 1 )
        {
          v46 = (void *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                          WPP_MAIN_CB.Queue.ListEntry.Blink,
                          this[3],
                          v15);
          v16 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, void *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  v46,
                  off_14000F150);
          if ( *(_QWORD *)(v16 + 8) == *(_QWORD *)&Information[2 * v14 + 2] )
            break;
          if ( ++v15 >= v43 )
            goto LABEL_14;
        }
        *(_BYTE *)v16 = 1;
      }
      else
      {
LABEL_14:
        v17 = CUsbBusFilter::AllocatePdoProprietaryIdObject(
                (CUsbBusFilter *)this,
                *(struct _DEVICE_OBJECT **)&Information[2 * v14 + 2],
                &v46);
        if ( v17 >= 0 )
        {
          *(_BYTE *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, void *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                      v46,
                      off_14000F150) = 1;
          v18 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Blink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  this[3],
                  v46);
          if ( v18 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                36,
                WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
                (unsigned int)v18);
            ((void (__fastcall *)(struct _LIST_ENTRY *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(
              WPP_MAIN_CB.Queue.ListEntry.Blink,
              v46);
            v46 = 0;
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            35,
            WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
            (unsigned int)v17);
        }
      }
      v11 = v43;
      v14 = (unsigned int)(v14 + 1);
    }
    while ( (unsigned int)v14 < *Information );
    v8 = Object;
  }
  v19 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          this[3]);
  while ( (--v19 & 0x80000000) == 0 )
  {
    v46 = (void *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                    WPP_MAIN_CB.Queue.ListEntry.Blink,
                    this[3],
                    v19);
    if ( !*(_BYTE *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, void *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                      v46,
                      off_14000F150) )
      ((void (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[8].Flink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        this[3],
        v46);
  }
  v20 = 0;
  v45 = 0;
  while ( (unsigned int)v20 < *Information )
  {
    v21 = *(_QWORD *)&Information[2 * v20 + 2] == 0;
    v22 = (unsigned int)v20;
    v40 = (unsigned int)v20;
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
          (unsigned int)v20);
      goto LABEL_54;
    }
    v23 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            this[3]);
    v24 = 0;
    if ( !v23 )
      goto LABEL_73;
    v25 = v23;
    do
    {
      v46 = (void *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                      this[3],
                      v24);
      v26 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, void *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
              WPP_MAIN_CB.Queue.ListEntry.Blink,
              v46,
              off_14000F150);
      v27 = *(struct _DEVICE_OBJECT **)&Information[2 * v22 + 2];
      v28 = v26;
      if ( *(struct _DEVICE_OBJECT **)(v26 + 8) == v27 )
        break;
      v28 = 0;
      ++v24;
    }
    while ( v24 < v25 );
    v8 = Object;
    if ( !v28 )
    {
      LODWORD(v20) = v45;
LABEL_73:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
      goto LABEL_54;
    }
    v29 = 0;
    LOBYTE(v43) = 0;
    AttachedDeviceReference = IoGetAttachedDeviceReference(v27);
    if ( AttachedDeviceReference )
    {
      while ( 1 )
      {
        if ( AttachedDeviceReference->DriverObject == v39 )
        {
          v31 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, PDEVICE_OBJECT))WPP_MAIN_CB.Queue.ListEntry.Flink[15].Flink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  AttachedDeviceReference);
          if ( ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                 v31,
                 off_14000F090) )
          {
            break;
          }
        }
        LowerDeviceObject = IoGetLowerDeviceObject(AttachedDeviceReference);
        ObfDereferenceObject(AttachedDeviceReference);
        AttachedDeviceReference = LowerDeviceObject;
        if ( !LowerDeviceObject )
        {
          v29 = v43;
          goto LABEL_45;
        }
      }
      v29 = 1;
      ObfDereferenceObject(AttachedDeviceReference);
    }
LABEL_45:
    if ( v8 )
    {
      ObfDereferenceObject(v8);
      v8 = 0;
      Object = 0;
    }
    if ( *(_BYTE *)(v28 + 2) )
      goto LABEL_70;
    v33 = v40;
    if ( !CUsbBusFilter::ValidateWithClaimChecks(
            (CUsbBusFilter *)this,
            v38,
            *(struct _DEVICE_OBJECT **)&Information[2 * v40 + 2],
            &v42,
            (struct _EPROCESS **)&Object) )
    {
      v8 = Object;
LABEL_70:
      if ( v29 )
        CUsbBusFilter::UsbCyclePort((CUsbBusFilter *)this, *(_DWORD *)(v28 + 24));
      goto LABEL_53;
    }
    if ( !v29 )
    {
      if ( !*(_BYTE *)(v28 + 1) )
      {
        v8 = Object;
        v36 = CUsbPdoFilter::CreateInstance(
                (struct WDFDEVICE__ *)*this,
                *(struct _DEVICE_OBJECT **)&Information[2 * v33 + 2],
                &v42,
                (struct _EPROCESS *)Object,
                (const unsigned __int16 *)(v28 + *(unsigned int *)(v28 + 88) + 104LL),
                &v41);
        if ( v36 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            39,
            WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
            (unsigned int)v36);
        }
        goto LABEL_53;
      }
      CUsbBusFilter::UsbCyclePort((CUsbBusFilter *)this, *(_DWORD *)(v28 + 24));
    }
    v8 = Object;
LABEL_53:
    LODWORD(v20) = v45;
LABEL_54:
    v20 = (unsigned int)(v20 + 1);
    v45 = v20;
  }
  v34 = 0;
  v35 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          this[3]);
  if ( v35 )
  {
    do
    {
      v46 = (void *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                      this[3],
                      v34++);
      *(_BYTE *)(((__int64 (__fastcall *)(struct _LIST_ENTRY *, void *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                   WPP_MAIN_CB.Queue.ListEntry.Blink,
                   v46,
                   off_14000F150)
               + 1) = 1;
    }
    while ( v34 < v35 );
  }
LABEL_57:
  IofCompleteRequest(Irp, 0);
  if ( v10 )
    ((void (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControl *))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Blink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      *this);
  if ( v8 )
    ObfDereferenceObject(v8);
  if ( v38 )
    ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFCOLLECTION__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      v38);
}

```

## disassembly

```asm
0x140003258  mov     [rsp-40h+Irp], rdx
0x14000325d  push    rbp
0x14000325e  push    rbx
0x14000325f  push    rsi
0x140003260  push    rdi
0x140003261  push    r12
0x140003263  push    r13
0x140003265  push    r14
0x140003267  push    r15
0x140003269  mov     rbp, rsp
0x14000326c  sub     rsp, 78h
0x140003270  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003277  mov     rdi, rcx
0x14000327a  mov     r13, [rdx+38h]
0x14000327e  xorps   xmm0, xmm0
0x140003281  mov     rdx, [rcx]
0x140003284  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000328b  mov     [rbp+arg_18], 0
0x140003293  mov     rax, [rax+0F8h]
0x14000329a  mov     [rbp+var_28], 0
0x1400032a2  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x1400032a6  mov     [rbp+arg_0], 0
0x1400032ad  call    _guard_dispatch_icall
0x1400032b2  mov     rdx, [rdi]
0x1400032b5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400032bc  mov     rax, [rax+8]
0x1400032c0  mov     [rbp+var_38], rax
0x1400032c4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400032cb  mov     rax, [rax+420h]
0x1400032d2  call    _guard_dispatch_icall
0x1400032d7  xor     r15d, r15d
0x1400032da  mov     [rbp+Object], r15
0x1400032de  mov     [rbp+var_40], r15
0x1400032e2  cmp     [r13+0], r15d
0x1400032e6  jz      short loc_14000333D
0x1400032e8  mov     rcx, [rdi+20h]; this
0x1400032ec  lea     r8, [rbp+var_40]; struct WDFCOLLECTION__ **
0x1400032f0  lea     rdx, [rbp+arg_0]; unsigned int *
0x1400032f4  call    ?AllocateClaimCheckCollectionSnapshot@CUsbFilterControl@@QEAAJPEAKPEAPEAUWDFCOLLECTION__@@@Z; CUsbFilterControl::AllocateClaimCheckCollectionSnapshot(ulong *,WDFCOLLECTION__ * *)
0x1400032f9  test    eax, eax
0x1400032fb  jns     short loc_14000333D
0x1400032fd  xor     sil, sil
0x140003300  mov     rcx, cs:WPP_GLOBAL_Control
0x140003307  lea     rdx, WPP_GLOBAL_Control
0x14000330e  cmp     rcx, rdx
0x140003311  jz      loc_140003878
0x140003317  cmp     byte ptr [rcx+29h], 2
0x14000331b  jb      loc_140003878
0x140003321  mov     rcx, [rcx+18h]
0x140003325  lea     edx, [r15+22h]
0x140003329  mov     r9d, eax
0x14000332c  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140003333  call    WPP_SF_d
0x140003338  jmp     loc_140003878
0x14000333d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003344  mov     rdx, [rdi]
0x140003347  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000334e  mov     rax, [rax+9B0h]
0x140003355  call    _guard_dispatch_icall
0x14000335a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003361  mov     esi, 1
0x140003366  mov     rdx, [rdi+18h]
0x14000336a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003371  mov     rax, [rax+70h]
0x140003375  call    _guard_dispatch_icall
0x14000337a  xor     ebx, ebx
0x14000337c  mov     [rbp+arg_0], eax
0x14000337f  test    eax, eax
0x140003381  jz      short loc_1400033E0
0x140003383  mov     r15d, eax
0x140003386  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000338d  mov     r8d, ebx
0x140003390  mov     rdx, [rdi+18h]
0x140003394  mov     rax, [rcx+90h]
0x14000339b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400033a2  call    _guard_dispatch_icall
0x1400033a7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x1400033ae  mov     rdx, rax
0x1400033b1  mov     r8, cs:off_14000F150
0x1400033b8  mov     [rbp+arg_18], rax
0x1400033bc  mov     rax, [rcx+650h]
0x1400033c3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400033ca  call    _guard_dispatch_icall
0x1400033cf  add     ebx, esi
0x1400033d1  mov     byte ptr [rax], 0
0x1400033d4  cmp     ebx, r15d
0x1400033d7  jb      short loc_140003386
0x1400033d9  mov     r15, [rbp+Object]
0x1400033dd  mov     eax, [rbp+arg_0]
0x1400033e0  xor     r12d, r12d
0x1400033e3  cmp     [r13+0], r12d
0x1400033e7  jbe     loc_140003558
0x1400033ed  lea     r15, WPP_GLOBAL_Control
0x1400033f4  xor     ebx, ebx
0x1400033f6  test    eax, eax
0x1400033f8  jz      short loc_140003455
0x1400033fa  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003401  mov     r8d, ebx
0x140003404  mov     rdx, [rdi+18h]
0x140003408  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000340f  mov     rax, [rax+90h]
0x140003416  call    _guard_dispatch_icall
0x14000341b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140003422  mov     rdx, rax
0x140003425  mov     r8, cs:off_14000F150
0x14000342c  mov     [rbp+arg_18], rax
0x140003430  mov     rax, [rcx+650h]
0x140003437  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000343e  call    _guard_dispatch_icall
0x140003443  mov     rcx, [r13+r12*8+8]
0x140003448  cmp     [rax+8], rcx
0x14000344c  jz      short loc_1400034A1
0x14000344e  add     ebx, esi
0x140003450  cmp     ebx, [rbp+arg_0]
0x140003453  jb      short loc_1400033FA
0x140003455  mov     rdx, [r13+r12*8+8]; struct _DEVICE_OBJECT *
0x14000345a  lea     r8, [rbp+arg_18]; void **
0x14000345e  mov     rcx, rdi; this
0x140003461  call    ?AllocatePdoProprietaryIdObject@CUsbBusFilter@@AEAAJPEAU_DEVICE_OBJECT@@PEAPEAX@Z; CUsbBusFilter::AllocatePdoProprietaryIdObject(_DEVICE_OBJECT *,void * *)
0x140003466  test    eax, eax
0x140003468  jns     short loc_1400034A9
0x14000346a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003471  cmp     rcx, r15
0x140003474  jz      loc_140003544
0x14000347a  cmp     byte ptr [rcx+29h], 2
0x14000347e  jb      loc_140003544
0x140003484  mov     rcx, [rcx+18h]
0x140003488  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x14000348f  mov     edx, 23h ; '#'
0x140003494  mov     r9d, eax
0x140003497  call    WPP_SF_d
0x14000349c  jmp     loc_140003544
0x1400034a1  mov     [rax], sil
0x1400034a4  jmp     loc_140003544
0x1400034a9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400034b0  mov     r8, cs:off_14000F150
0x1400034b7  mov     rdx, [rbp+arg_18]
0x1400034bb  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400034c2  mov     rax, [rax+650h]
0x1400034c9  call    _guard_dispatch_icall
0x1400034ce  mov     [rax], sil
0x1400034d1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400034d8  mov     r8, [rbp+arg_18]
0x1400034dc  mov     rdx, [rdi+18h]
0x1400034e0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400034e7  mov     rax, [rax+78h]
0x1400034eb  call    _guard_dispatch_icall
0x1400034f0  test    eax, eax
0x1400034f2  jns     short loc_140003544
0x1400034f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034fb  cmp     rcx, r15
0x1400034fe  jz      short loc_14000351E
0x140003500  cmp     byte ptr [rcx+29h], 2
0x140003504  jb      short loc_14000351E
0x140003506  mov     rcx, [rcx+18h]
0x14000350a  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140003511  mov     edx, 24h ; '$'
0x140003516  mov     r9d, eax
0x140003519  call    WPP_SF_d
0x14000351e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003525  mov     rdx, [rbp+arg_18]
0x140003529  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003530  mov     rax, [rax+680h]
0x140003537  call    _guard_dispatch_icall
0x14000353c  mov     [rbp+arg_18], 0
0x140003544  mov     eax, [rbp+arg_0]
0x140003547  add     r12d, esi
0x14000354a  cmp     r12d, [r13+0]
0x14000354e  jb      loc_1400033F4
0x140003554  mov     r15, [rbp+Object]
0x140003558  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000355f  mov     rdx, [rdi+18h]
0x140003563  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000356a  mov     rax, [rax+70h]
0x14000356e  call    _guard_dispatch_icall
0x140003573  mov     ebx, eax
0x140003575  jmp     short loc_1400035E7
0x140003577  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000357e  mov     r8d, ebx
0x140003581  mov     rdx, [rdi+18h]
0x140003585  mov     rax, [rcx+90h]
0x14000358c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003593  call    _guard_dispatch_icall
0x140003598  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000359f  mov     rdx, rax
0x1400035a2  mov     r8, cs:off_14000F150
0x1400035a9  mov     [rbp+arg_18], rax
0x1400035ad  mov     rax, [rcx+650h]
0x1400035b4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400035bb  call    _guard_dispatch_icall
0x1400035c0  cmp     byte ptr [rax], 0
0x1400035c3  jnz     short loc_1400035E7
0x1400035c5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400035cc  mov     r8, [rbp+arg_18]
0x1400035d0  mov     rdx, [rdi+18h]
0x1400035d4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400035db  mov     rax, [rax+80h]
0x1400035e2  call    _guard_dispatch_icall
0x1400035e7  sub     ebx, esi
0x1400035e9  jns     short loc_140003577
0x1400035eb  xor     r14d, r14d
0x1400035ee  mov     [rbp+arg_10], r14d
0x1400035f2  cmp     [r13+0], r14d
0x1400035f6  jbe     loc_140003800
0x1400035fc  cmp     qword ptr [r13+r14*8+8], 0
0x140003602  mov     r12d, r14d
0x140003605  mov     [rbp+var_30], r12
0x140003609  jnz     short loc_140003649
0x14000360b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003612  lea     rax, WPP_GLOBAL_Control
0x140003619  cmp     rcx, rax
0x14000361c  jz      loc_1400037EF
0x140003622  cmp     byte ptr [rcx+29h], 2
0x140003626  jb      loc_1400037EF
0x14000362c  mov     rcx, [rcx+18h]
0x140003630  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140003637  mov     edx, 25h ; '%'
0x14000363c  mov     r9d, r14d
0x14000363f  call    WPP_SF_d
0x140003644  jmp     loc_1400037EF
0x140003649  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003650  mov     rdx, [rdi+18h]
0x140003654  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000365b  mov     rax, [rax+70h]
0x14000365f  call    _guard_dispatch_icall
0x140003664  xor     ebx, ebx
0x140003666  test    eax, eax
0x140003668  jz      loc_1400039A7
0x14000366e  mov     r15d, eax
0x140003671  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140003678  mov     r8d, ebx
0x14000367b  mov     rdx, [rdi+18h]
0x14000367f  mov     rax, [rcx+90h]
0x140003686  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000368d  call    _guard_dispatch_icall
0x140003692  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140003699  mov     rdx, rax
0x14000369c  mov     r8, cs:off_14000F150
0x1400036a3  mov     [rbp+arg_18], rax
0x1400036a7  mov     rax, [rcx+650h]
0x1400036ae  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400036b5  call    _guard_dispatch_icall
0x1400036ba  mov     rcx, [r13+r12*8+8]; DeviceObject
0x1400036bf  mov     r14, rax
0x1400036c2  cmp     [rax+8], rcx
0x1400036c6  jz      short loc_1400036D2
0x1400036c8  xor     r14d, r14d
0x1400036cb  add     ebx, esi
0x1400036cd  cmp     ebx, r15d
0x1400036d0  jb      short loc_140003671
0x1400036d2  mov     r15, [rbp+Object]
0x1400036d6  test    r14, r14
0x1400036d9  jz      loc_1400039A3
0x1400036df  xor     bl, bl
0x1400036e1  mov     byte ptr [rbp+arg_0], bl
0x1400036e4  call    cs:__imp_IoGetAttachedDeviceReference
0x1400036eb  nop     dword ptr [rax+rax+00h]
0x1400036f0  mov     r12, rax
0x1400036f3  test    rax, rax
0x1400036f6  jz      loc_14000377D
0x1400036fc  mov     rax, [rbp+var_38]
0x140003700  cmp     [r12+8], rax
0x140003705  jnz     short loc_140003751
0x140003707  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000370e  mov     rdx, r12
0x140003711  mov     rax, [rcx+0F0h]
0x140003718  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000371f  call    _guard_dispatch_icall
0x140003724  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000372b  mov     rdx, rax
0x14000372e  mov     r8, cs:off_14000F090
0x140003735  mov     rax, [rcx+650h]
0x14000373c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003743  call    _guard_dispatch_icall
0x140003748  test    rax, rax
0x14000374b  jnz     loc_1400038F8
0x140003751  mov     rcx, r12; DeviceObject
0x140003754  call    cs:__imp_IoGetLowerDeviceObject
0x14000375b  nop     dword ptr [rax+rax+00h]
0x140003760  mov     rcx, r12; Object
0x140003763  mov     rbx, rax
0x140003766  call    cs:__imp_ObfDereferenceObject
0x14000376d  nop     dword ptr [rax+rax+00h]
0x140003772  mov     r12, rbx
0x140003775  test    rbx, rbx
0x140003778  jnz     short loc_1400036FC
0x14000377a  mov     bl, byte ptr [rbp+arg_0]
0x14000377d  test    r15, r15
0x140003780  jz      short loc_140003798
0x140003782  mov     rcx, r15; Object
0x140003785  call    cs:__imp_ObfDereferenceObject
0x14000378c  nop     dword ptr [rax+rax+00h]
0x140003791  xor     r15d, r15d
0x140003794  mov     [rbp+Object], r15
0x140003798  cmp     byte ptr [r14+2], 0
0x14000379d  jnz     loc_14000398A
0x1400037a3  mov     r12, [rbp+var_30]
0x1400037a7  lea     rax, [rbp+Object]
0x1400037ab  mov     rdx, [rbp+var_40]; struct WDFCOLLECTION__ *
0x1400037af  lea     r9, [rbp+var_20]; struct _GUID *
  ... truncated ...
```

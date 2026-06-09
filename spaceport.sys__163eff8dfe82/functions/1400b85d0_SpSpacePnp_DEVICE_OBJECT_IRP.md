# SpSpacePnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400b85d0`
- end: `0x1400b8874`
- name: `?SpSpacePnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `676`
- prototype: `__int64 __fastcall(PVOID Object, struct _IRP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1400268c0`
- `0x14002b094`
- `0x14002bc90`
- `0x14002ce90`
- `0x1400a4fd4`
- `0x1400a5438`
- `0x1400a6144`
- `0x1400a6a14`
- `0x1400a6d30`
- `0x1400a71e4`
- `0x1400ae6c4`
- `0x1400b85d0`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400b875a`
- `ntoskrnl!ObfReferenceObject` at `0x1400b875a`
- `ntoskrnl!IofCompleteRequest` at `0x1400b8665`
- `ntoskrnl!IofCompleteRequest` at `0x1400b8665`

## pseudocode

```c
__int64 __fastcall SpSpacePnp(_QWORD *Object, struct _IRP *a2)
{
  __int64 v2; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  struct _IRP *MinorFunction; // rdx
  __int64 v7; // rsi
  int started; // eax
  int Status; // ebx
  IO_STATUS_BLOCK *p_IoStatus; // rsi
  ULONG DeviceType; // ecx
  const char *v12; // r9
  ULONG Length; // eax
  _QWORD *v14; // r14
  PIO_SECURITY_CONTEXT SecurityContext; // rdx
  struct _DEVICE_RELATIONS *v17; // [rsp+40h] [rbp+8h] BYREF
  __int64 v18; // [rsp+48h] [rbp+10h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v18 = v2;
  MinorFunction = (struct _IRP *)CurrentStackLocation->MinorFunction;
  v17 = 0;
  if ( (_DWORD)MinorFunction != 1 )
  {
    v7 = Object[8] + 8LL;
    switch ( (int)MinorFunction )
    {
      case 0:
        started = SpStartDevice((struct SP_DEVICE *)v7, MinorFunction);
        goto LABEL_31;
      case 2:
        SP_DEVICE::AcquireRundownExclusive((SP_DEVICE *)v7);
        *(_BYTE *)(v7 + 169) = 0;
        SP_DEVICE::ReleaseRundownExclusive((SP_DEVICE *)v7);
        if ( *(_BYTE *)(v7 + 168) == 5 )
        {
          if ( *(_BYTE *)(v7 + 170) )
            SpMarkDeleted(*(struct _DEVICE_OBJECT **)(v7 + 160), 1);
          SpDeleteDevice((struct SP_DEVICE *)v7);
        }
        break;
      case 5:
        Status = -1073741823;
        goto LABEL_7;
      case 6:
      case 10:
      case 20:
        break;
      case 7:
        Length = CurrentStackLocation->Parameters.Read.Length;
        if ( Length == 2 )
        {
          a2->IoStatus.Information = 0;
          Status = SpQueryPowerRelations((struct SP_DEVICE *)v7, &v17);
          if ( Status >= 0 )
            a2->IoStatus.Information = (ULONG_PTR)v17;
LABEL_32:
          if ( Status == 259 )
            goto LABEL_10;
          p_IoStatus = &a2->IoStatus;
          if ( Status != -1073741637 )
            goto LABEL_8;
        }
        else
        {
          p_IoStatus = &a2->IoStatus;
          if ( Length == 4 )
          {
            v14 = SC_ENV::Allocate(0x10u, 0x58587053u, 0, 0);
            if ( v14 )
            {
              ObfReferenceObject(Object);
              *(_DWORD *)v14 = 1;
              v14[1] = Object;
              Status = 0;
              a2->IoStatus.Information = (ULONG_PTR)v14;
            }
            else
            {
              Status = -1073741670;
            }
            goto LABEL_8;
          }
        }
LABEL_36:
        Status = p_IoStatus->Status;
        goto LABEL_9;
      case 9:
        SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
        HIDWORD(SecurityContext->SecurityQos) = HIDWORD(SecurityContext->SecurityQos)
                                              ^ ((unsigned __int8)HIDWORD(SecurityContext->SecurityQos)
                                               ^ (unsigned __int8)(16 * *(_BYTE *)(Object[8] + 3119LL)))
                                              & 0x10
                                              | 0x2C0;
        LODWORD(SecurityContext->AccessState) = *(_DWORD *)(v7 + 3104);
        break;
      case 12:
        started = SpQueryDeviceText((struct SP_DEVICE *)0x140000000LL, a2);
        goto LABEL_31;
      case 19:
        started = SpQueryId((struct SP_DEVICE *)v7, a2);
        goto LABEL_31;
      case 22:
        started = SpDeviceUsageNotification((struct SP_DEVICE *)v7, a2);
LABEL_31:
        Status = started;
        goto LABEL_32;
      case 23:
        SP_DEVICE::AcquireRundownExclusive((SP_DEVICE *)v7);
        *(_BYTE *)(v7 + 169) = 0;
        SP_DEVICE::ReleaseRundownExclusive((SP_DEVICE *)v7);
        break;
      default:
        p_IoStatus = &a2->IoStatus;
        goto LABEL_36;
    }
  }
  Status = 0;
LABEL_7:
  p_IoStatus = &a2->IoStatus;
LABEL_8:
  p_IoStatus->Status = Status;
LABEL_9:
  IofCompleteRequest(a2, 0);
LABEL_10:
  if ( Status >= 0 || Status == -2147483643 || Status == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v12 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v12 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      29,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v12,
      Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400b85d0  push    rbx
0x1400b85d2  sub     rsp, 30h
0x1400b85d6  mov     r8, [rdx+0B8h]
0x1400b85dd  mov     rbx, rcx
0x1400b85e0  mov     [rsp+38h+arg_8], rsi
0x1400b85e5  mov     [rsp+38h+arg_10], rdi
0x1400b85ea  mov     rdi, rdx
0x1400b85ed  mov     [rsp+38h+arg_18], r14
0x1400b85f2  movzx   edx, byte ptr [r8+1]
0x1400b85f7  mov     [rsp+38h+arg_0], 0
0x1400b8600  cmp     edx, 1
0x1400b8603  jz      short loc_1400B8658; jumptable 00000001400B8627 cases 6,10,20
0x1400b8605  cmp     edx, 17h; switch 24 cases
0x1400b8608  ja      def_1400B8627; jumptable 00000001400B8627 default case, cases 1,3,4,8,11,13-18,21
0x1400b860e  mov     rsi, [rcx+40h]
0x1400b8612  lea     rcx, cs:140000000h; struct SP_DEVICE *
0x1400b8619  mov     edx, ds:(jpt_1400B8627 - 140000000h)[rcx+rdx*4]
0x1400b8620  add     rsi, 8
0x1400b8624  add     rdx, rcx; struct _IRP *
0x1400b8627  jmp     rdx; switch jump
0x1400b862d  mov     rcx, rsi; jumptable 00000001400B8627 case 0
0x1400b8630  call    ?SpStartDevice@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpStartDevice(SP_DEVICE *,_IRP *)
0x1400b8635  jmp     loc_1400B87E6
0x1400b863a  mov     ebx, 0C0000001h; jumptable 00000001400B8627 case 5
0x1400b863f  jmp     short loc_1400B865A
0x1400b8641  mov     rcx, rsi; jumptable 00000001400B8627 case 23
0x1400b8644  call    ?AcquireRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireRundownExclusive(void)
0x1400b8649  mov     rcx, rsi; this
0x1400b864c  mov     byte ptr [rsi+0A9h], 0
0x1400b8653  call    ?ReleaseRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownExclusive(void)
0x1400b8658  xor     ebx, ebx; jumptable 00000001400B8627 cases 6,10,20
0x1400b865a  lea     rsi, [rdi+30h]
0x1400b865e  mov     [rsi], ebx
0x1400b8660  xor     edx, edx; PriorityBoost
0x1400b8662  mov     rcx, rdi; Irp
0x1400b8665  call    cs:__imp_IofCompleteRequest
0x1400b866c  nop     dword ptr [rax+rax+00h]
0x1400b8671  mov     r14, [rsp+38h+arg_18]
0x1400b8676  mov     rdi, [rsp+38h+arg_10]
0x1400b867b  mov     rsi, [rsp+38h+arg_8]
0x1400b8680  test    ebx, ebx
0x1400b8682  jns     loc_1400B8811
0x1400b8688  cmp     ebx, 80000005h
0x1400b868e  jz      loc_1400B8811
0x1400b8694  cmp     ebx, 0C0000023h
0x1400b869a  jz      loc_1400B8811
0x1400b86a0  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400b86a6  cmp     ecx, 1
0x1400b86a9  jz      short loc_1400B86B6
0x1400b86ab  mov     ecx, 1
0x1400b86b0  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400b86b6  lea     r9, aError; "Error"
0x1400b86bd  jmp     loc_1400B882E
0x1400b86c2  mov     rcx, rsi; jumptable 00000001400B8627 case 2
0x1400b86c5  call    ?AcquireRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireRundownExclusive(void)
0x1400b86ca  mov     rcx, rsi; this
0x1400b86cd  mov     byte ptr [rsi+0A9h], 0
0x1400b86d4  call    ?ReleaseRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownExclusive(void)
0x1400b86d9  cmp     byte ptr [rsi+0A8h], 5
0x1400b86e0  jnz     loc_1400B8658; jumptable 00000001400B8627 cases 6,10,20
0x1400b86e6  cmp     byte ptr [rsi+0AAh], 0
0x1400b86ed  jz      short loc_1400B86FD
0x1400b86ef  mov     rcx, [rsi+0A0h]; struct _DEVICE_OBJECT *
0x1400b86f6  mov     dl, 1; unsigned __int8
0x1400b86f8  call    ?SpMarkDeleted@@YAJPEAU_DEVICE_OBJECT@@E@Z; SpMarkDeleted(_DEVICE_OBJECT *,uchar)
0x1400b86fd  mov     rcx, rsi; struct SP_DEVICE *
0x1400b8700  call    ?SpDeleteDevice@@YAXPEAVSP_DEVICE@@@Z; SpDeleteDevice(SP_DEVICE *)
0x1400b8705  jmp     loc_1400B8658; jumptable 00000001400B8627 cases 6,10,20
0x1400b870a  mov     rdx, rdi; jumptable 00000001400B8627 case 22
0x1400b870d  mov     rcx, rsi; this
0x1400b8710  call    ?SpDeviceUsageNotification@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpDeviceUsageNotification(SP_DEVICE *,_IRP *)
0x1400b8715  jmp     loc_1400B87E6
0x1400b871a  mov     eax, [r8+8]; jumptable 00000001400B8627 case 7
0x1400b871e  cmp     eax, 2
0x1400b8721  jz      short loc_1400B877C
0x1400b8723  lea     rsi, [rdi+30h]
0x1400b8727  cmp     eax, 4
0x1400b872a  jnz     loc_1400B880A
0x1400b8730  xor     r9d, r9d; unsigned int
0x1400b8733  xor     r8d, r8d; unsigned __int8
0x1400b8736  mov     edx, 58587053h; unsigned int
0x1400b873b  mov     ecx, 10h; unsigned __int64
0x1400b8740  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400b8745  mov     r14, rax
0x1400b8748  test    rax, rax
0x1400b874b  jnz     short loc_1400B8757
0x1400b874d  mov     ebx, 0C000009Ah
0x1400b8752  jmp     loc_1400B865E
0x1400b8757  mov     rcx, rbx; Object
0x1400b875a  call    cs:__imp_ObfReferenceObject
0x1400b8761  nop     dword ptr [rax+rax+00h]
0x1400b8766  mov     dword ptr [r14], 1
0x1400b876d  mov     [r14+8], rbx
0x1400b8771  xor     ebx, ebx
0x1400b8773  mov     [rdi+38h], r14
0x1400b8777  jmp     loc_1400B865E
0x1400b877c  lea     rdx, [rsp+38h+arg_0]; struct _DEVICE_RELATIONS **
0x1400b8781  mov     qword ptr [rdi+38h], 0
0x1400b8789  mov     rcx, rsi; struct SP_DEVICE *
0x1400b878c  call    ?SpQueryPowerRelations@@YAJPEAVSP_DEVICE@@PEAPEAU_DEVICE_RELATIONS@@@Z; SpQueryPowerRelations(SP_DEVICE *,_DEVICE_RELATIONS * *)
0x1400b8791  mov     ebx, eax
0x1400b8793  test    eax, eax
0x1400b8795  js      short loc_1400B87E8
0x1400b8797  mov     rax, [rsp+38h+arg_0]
0x1400b879c  mov     [rdi+38h], rax
0x1400b87a0  jmp     short loc_1400B87E8
0x1400b87a2  mov     rdx, [r8+8]; jumptable 00000001400B8627 case 9
0x1400b87a6  movzx   ecx, byte ptr [rsi+0C27h]
0x1400b87ad  shl     ecx, 4
0x1400b87b0  mov     eax, [rdx+4]
0x1400b87b3  xor     ecx, eax
0x1400b87b5  and     ecx, 10h
0x1400b87b8  xor     ecx, eax
0x1400b87ba  or      ecx, 2C0h
0x1400b87c0  mov     [rdx+4], ecx
0x1400b87c3  mov     eax, [rsi+0C20h]
0x1400b87c9  mov     [rdx+8], eax
0x1400b87cc  jmp     loc_1400B8658; jumptable 00000001400B8627 cases 6,10,20
0x1400b87d1  mov     rdx, rdi; jumptable 00000001400B8627 case 19
0x1400b87d4  mov     rcx, rsi; struct SP_DEVICE *
0x1400b87d7  call    ?SpQueryId@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryId(SP_DEVICE *,_IRP *)
0x1400b87dc  jmp     short loc_1400B87E6
0x1400b87de  mov     rdx, rdi; jumptable 00000001400B8627 case 12
0x1400b87e1  call    ?SpQueryDeviceText@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryDeviceText(SP_DEVICE *,_IRP *)
0x1400b87e6  mov     ebx, eax
0x1400b87e8  cmp     ebx, 103h
0x1400b87ee  jz      loc_1400B8671
0x1400b87f4  lea     rsi, [rdi+30h]
0x1400b87f8  cmp     ebx, 0C00000BBh
0x1400b87fe  jnz     loc_1400B865E
0x1400b8804  jmp     short loc_1400B880A
0x1400b8806  lea     rsi, [rdi+30h]; jumptable 00000001400B8627 default case, cases 1,3,4,8,11,13-18,21
0x1400b880a  mov     ebx, [rsi]
0x1400b880c  jmp     loc_1400B8660
0x1400b8811  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400b8817  cmp     ecx, 3
0x1400b881a  jz      short loc_1400B8827
0x1400b881c  mov     ecx, 3
0x1400b8821  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400b8827  lea     r9, aExit; "Exit "
0x1400b882e  mov     r10, cs:WPP_GLOBAL_Control
0x1400b8835  lea     rax, WPP_GLOBAL_Control
0x1400b883c  cmp     r10, rax
0x1400b883f  jz      short loc_1400B886B
0x1400b8841  mov     eax, [r10+2Ch]
0x1400b8845  test    al, 1
0x1400b8847  jz      short loc_1400B886B
0x1400b8849  movzx   eax, byte ptr [r10+29h]
0x1400b884e  cmp     eax, ecx
0x1400b8850  jb      short loc_1400B886B
0x1400b8852  mov     rcx, [r10+18h]
0x1400b8856  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400b885d  mov     edx, 1Dh
0x1400b8862  mov     [rsp+38h+var_18], ebx
0x1400b8866  call    WPP_SF_sd
0x1400b886b  mov     eax, ebx
0x1400b886d  add     rsp, 30h
0x1400b8871  pop     rbx
0x1400b8872  retn
```

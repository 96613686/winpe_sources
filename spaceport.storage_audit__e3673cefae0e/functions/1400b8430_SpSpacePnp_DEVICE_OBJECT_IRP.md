# SpSpacePnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400b8430`
- end: `0x1400b86d4`
- name: `?SpSpacePnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `676`
- prototype: `__int64 __fastcall(_QWORD *Object, struct _IRP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1400268c0`
- `0x14002b094`
- `0x14002bc90`
- `0x14002ce90`
- `0x1400a4ea4`
- `0x1400a5308`
- `0x1400a6014`
- `0x1400a68e4`
- `0x1400a6c00`
- `0x1400a70b4`
- `0x1400ae524`
- `0x1400b8430`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400b85ba`
- `ntoskrnl!ObfReferenceObject` at `0x1400b85ba`
- `ntoskrnl!IofCompleteRequest` at `0x1400b84c5`
- `ntoskrnl!IofCompleteRequest` at `0x1400b84c5`

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
            SpMarkDeleted(*(struct _DEVICE_OBJECT **)(v7 + 160), 1u);
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
0x1400b8430  push    rbx
0x1400b8432  sub     rsp, 30h
0x1400b8436  mov     r8, [rdx+0B8h]
0x1400b843d  mov     rbx, rcx
0x1400b8440  mov     [rsp+38h+arg_8], rsi
0x1400b8445  mov     [rsp+38h+arg_10], rdi
0x1400b844a  mov     rdi, rdx
0x1400b844d  mov     [rsp+38h+arg_18], r14
0x1400b8452  movzx   edx, byte ptr [r8+1]
0x1400b8457  mov     [rsp+38h+arg_0], 0
0x1400b8460  cmp     edx, 1
0x1400b8463  jz      short loc_1400B84B8; jumptable 00000001400B8487 cases 6,10,20
0x1400b8465  cmp     edx, 17h; switch 24 cases
0x1400b8468  ja      def_1400B8487; jumptable 00000001400B8487 default case, cases 1,3,4,8,11,13-18,21
0x1400b846e  mov     rsi, [rcx+40h]
0x1400b8472  lea     rcx, cs:140000000h; struct SP_DEVICE *
0x1400b8479  mov     edx, ds:(jpt_1400B8487 - 140000000h)[rcx+rdx*4]
0x1400b8480  add     rsi, 8
0x1400b8484  add     rdx, rcx; struct _IRP *
0x1400b8487  jmp     rdx; switch jump
0x1400b848d  mov     rcx, rsi; jumptable 00000001400B8487 case 0
0x1400b8490  call    ?SpStartDevice@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpStartDevice(SP_DEVICE *,_IRP *)
0x1400b8495  jmp     loc_1400B8646
0x1400b849a  mov     ebx, 0C0000001h; jumptable 00000001400B8487 case 5
0x1400b849f  jmp     short loc_1400B84BA
0x1400b84a1  mov     rcx, rsi; jumptable 00000001400B8487 case 23
0x1400b84a4  call    ?AcquireRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireRundownExclusive(void)
0x1400b84a9  mov     rcx, rsi; this
0x1400b84ac  mov     byte ptr [rsi+0A9h], 0
0x1400b84b3  call    ?ReleaseRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownExclusive(void)
0x1400b84b8  xor     ebx, ebx; jumptable 00000001400B8487 cases 6,10,20
0x1400b84ba  lea     rsi, [rdi+30h]
0x1400b84be  mov     [rsi], ebx
0x1400b84c0  xor     edx, edx; PriorityBoost
0x1400b84c2  mov     rcx, rdi; Irp
0x1400b84c5  call    cs:__imp_IofCompleteRequest
0x1400b84cc  nop     dword ptr [rax+rax+00h]
0x1400b84d1  mov     r14, [rsp+38h+arg_18]
0x1400b84d6  mov     rdi, [rsp+38h+arg_10]
0x1400b84db  mov     rsi, [rsp+38h+arg_8]
0x1400b84e0  test    ebx, ebx
0x1400b84e2  jns     loc_1400B8671
0x1400b84e8  cmp     ebx, 80000005h
0x1400b84ee  jz      loc_1400B8671
0x1400b84f4  cmp     ebx, 0C0000023h
0x1400b84fa  jz      loc_1400B8671
0x1400b8500  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400b8506  cmp     ecx, 1
0x1400b8509  jz      short loc_1400B8516
0x1400b850b  mov     ecx, 1
0x1400b8510  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400b8516  lea     r9, aError; "Error"
0x1400b851d  jmp     loc_1400B868E
0x1400b8522  mov     rcx, rsi; jumptable 00000001400B8487 case 2
0x1400b8525  call    ?AcquireRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireRundownExclusive(void)
0x1400b852a  mov     rcx, rsi; this
0x1400b852d  mov     byte ptr [rsi+0A9h], 0
0x1400b8534  call    ?ReleaseRundownExclusive@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseRundownExclusive(void)
0x1400b8539  cmp     byte ptr [rsi+0A8h], 5
0x1400b8540  jnz     loc_1400B84B8; jumptable 00000001400B8487 cases 6,10,20
0x1400b8546  cmp     byte ptr [rsi+0AAh], 0
0x1400b854d  jz      short loc_1400B855D
0x1400b854f  mov     rcx, [rsi+0A0h]; struct _DEVICE_OBJECT *
0x1400b8556  mov     dl, 1; unsigned __int8
0x1400b8558  call    ?SpMarkDeleted@@YAJPEAU_DEVICE_OBJECT@@E@Z; SpMarkDeleted(_DEVICE_OBJECT *,uchar)
0x1400b855d  mov     rcx, rsi; struct SP_DEVICE *
0x1400b8560  call    ?SpDeleteDevice@@YAXPEAVSP_DEVICE@@@Z; SpDeleteDevice(SP_DEVICE *)
0x1400b8565  jmp     loc_1400B84B8; jumptable 00000001400B8487 cases 6,10,20
0x1400b856a  mov     rdx, rdi; jumptable 00000001400B8487 case 22
0x1400b856d  mov     rcx, rsi; this
0x1400b8570  call    ?SpDeviceUsageNotification@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpDeviceUsageNotification(SP_DEVICE *,_IRP *)
0x1400b8575  jmp     loc_1400B8646
0x1400b857a  mov     eax, [r8+8]; jumptable 00000001400B8487 case 7
0x1400b857e  cmp     eax, 2
0x1400b8581  jz      short loc_1400B85DC
0x1400b8583  lea     rsi, [rdi+30h]
0x1400b8587  cmp     eax, 4
0x1400b858a  jnz     loc_1400B866A
0x1400b8590  xor     r9d, r9d; unsigned int
0x1400b8593  xor     r8d, r8d; unsigned __int8
0x1400b8596  mov     edx, 58587053h; unsigned int
0x1400b859b  mov     ecx, 10h; unsigned __int64
0x1400b85a0  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400b85a5  mov     r14, rax
0x1400b85a8  test    rax, rax
0x1400b85ab  jnz     short loc_1400B85B7
0x1400b85ad  mov     ebx, 0C000009Ah
0x1400b85b2  jmp     loc_1400B84BE
0x1400b85b7  mov     rcx, rbx; Object
0x1400b85ba  call    cs:__imp_ObfReferenceObject
0x1400b85c1  nop     dword ptr [rax+rax+00h]
0x1400b85c6  mov     dword ptr [r14], 1
0x1400b85cd  mov     [r14+8], rbx
0x1400b85d1  xor     ebx, ebx
0x1400b85d3  mov     [rdi+38h], r14
0x1400b85d7  jmp     loc_1400B84BE
0x1400b85dc  lea     rdx, [rsp+38h+arg_0]; struct _DEVICE_RELATIONS **
0x1400b85e1  mov     qword ptr [rdi+38h], 0
0x1400b85e9  mov     rcx, rsi; struct SP_DEVICE *
0x1400b85ec  call    ?SpQueryPowerRelations@@YAJPEAVSP_DEVICE@@PEAPEAU_DEVICE_RELATIONS@@@Z; SpQueryPowerRelations(SP_DEVICE *,_DEVICE_RELATIONS * *)
0x1400b85f1  mov     ebx, eax
0x1400b85f3  test    eax, eax
0x1400b85f5  js      short loc_1400B8648
0x1400b85f7  mov     rax, [rsp+38h+arg_0]
0x1400b85fc  mov     [rdi+38h], rax
0x1400b8600  jmp     short loc_1400B8648
0x1400b8602  mov     rdx, [r8+8]; jumptable 00000001400B8487 case 9
0x1400b8606  movzx   ecx, byte ptr [rsi+0C27h]
0x1400b860d  shl     ecx, 4
0x1400b8610  mov     eax, [rdx+4]
0x1400b8613  xor     ecx, eax
0x1400b8615  and     ecx, 10h
0x1400b8618  xor     ecx, eax
0x1400b861a  or      ecx, 2C0h
0x1400b8620  mov     [rdx+4], ecx
0x1400b8623  mov     eax, [rsi+0C20h]
0x1400b8629  mov     [rdx+8], eax
0x1400b862c  jmp     loc_1400B84B8; jumptable 00000001400B8487 cases 6,10,20
0x1400b8631  mov     rdx, rdi; jumptable 00000001400B8487 case 19
0x1400b8634  mov     rcx, rsi; struct SP_DEVICE *
0x1400b8637  call    ?SpQueryId@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryId(SP_DEVICE *,_IRP *)
0x1400b863c  jmp     short loc_1400B8646
0x1400b863e  mov     rdx, rdi; jumptable 00000001400B8487 case 12
0x1400b8641  call    ?SpQueryDeviceText@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryDeviceText(SP_DEVICE *,_IRP *)
0x1400b8646  mov     ebx, eax
0x1400b8648  cmp     ebx, 103h
0x1400b864e  jz      loc_1400B84D1
0x1400b8654  lea     rsi, [rdi+30h]
0x1400b8658  cmp     ebx, 0C00000BBh
0x1400b865e  jnz     loc_1400B84BE
0x1400b8664  jmp     short loc_1400B866A
0x1400b8666  lea     rsi, [rdi+30h]; jumptable 00000001400B8487 default case, cases 1,3,4,8,11,13-18,21
0x1400b866a  mov     ebx, [rsi]
0x1400b866c  jmp     loc_1400B84C0
0x1400b8671  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400b8677  cmp     ecx, 3
0x1400b867a  jz      short loc_1400B8687
0x1400b867c  mov     ecx, 3
0x1400b8681  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400b8687  lea     r9, aExit; "Exit "
0x1400b868e  mov     r10, cs:WPP_GLOBAL_Control
0x1400b8695  lea     rax, WPP_GLOBAL_Control
0x1400b869c  cmp     r10, rax
0x1400b869f  jz      short loc_1400B86CB
0x1400b86a1  mov     eax, [r10+2Ch]
0x1400b86a5  test    al, 1
0x1400b86a7  jz      short loc_1400B86CB
0x1400b86a9  movzx   eax, byte ptr [r10+29h]
0x1400b86ae  cmp     eax, ecx
0x1400b86b0  jb      short loc_1400B86CB
0x1400b86b2  mov     rcx, [r10+18h]
0x1400b86b6  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400b86bd  mov     edx, 1Dh
0x1400b86c2  mov     [rsp+38h+var_18], ebx
0x1400b86c6  call    WPP_SF_sd
0x1400b86cb  mov     eax, ebx
0x1400b86cd  add     rsp, 30h
0x1400b86d1  pop     rbx
0x1400b86d2  retn
```

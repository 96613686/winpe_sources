# SpSpaceScsi(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001e230`
- end: `0x14001e2c9`
- name: `?SpSpaceScsi@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `153`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140010a80`
- `0x14001e230`
- `0x14001e2d0`
- `0x140034a6c`
- `0x140034cac`
- `0x140034d80`
- `0x140034f5c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001e26f`
- `ntoskrnl!IofCompleteRequest` at `0x14001e26f`

## pseudocode

```c
__int64 __fastcall SpSpaceScsi(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  PIO_SECURITY_CONTEXT SecurityContext; // rdx
  int v6; // ecx
  unsigned int Capacity; // ebx
  char v9; // cl
  PEX_RUNDOWN_REF_CACHE_AWARE *v10; // r9
  int v11; // ecx
  char v12; // si

  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  a2->IoStatus.Information = 0;
  v6 = BYTE2(SecurityContext->SecurityQos);
  if ( v6 == 6 )
    goto LABEL_2;
  v10 = (PEX_RUNDOWN_REF_CACHE_AWARE *)(DeviceExtension + 8);
  if ( BYTE2(SecurityContext->SecurityQos) )
  {
    v11 = v6 - 1;
    if ( v11 )
    {
      if ( (unsigned int)(v11 - 6) >= 2 )
      {
        Capacity = -1073741808;
        goto LABEL_3;
      }
    }
    else
    {
      *(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 24) = *((_QWORD *)DeviceExtension + 21);
    }
LABEL_2:
    Capacity = 0;
LABEL_3:
    a2->IoStatus.Status = Capacity;
    SpNtStatusToSrbStatus(a2);
    IofCompleteRequest(a2, 0);
    return Capacity;
  }
  v12 = 1;
  switch ( LOBYTE(SecurityContext[3].SecurityQos) )
  {
    case 0:
    case 0x1B:
    case 0x1E:
      Capacity = 0;
      break;
    case 0x12:
      Capacity = SpScsiInquiry(v10, a2);
      break;
    case 0x1A:
      Capacity = SpScsiModeSense((struct SP_DEVICE *)v10, a2);
      break;
    case 0x25:
    case 0x9E:
      Capacity = SpScsiReadCapacity((struct SP_DEVICE *)v10, a2);
      break;
    case 0x28:
    case 0x2A:
    case 0x88:
    case 0x8A:
      Capacity = SpScsiReadWrite((struct SP_DEVICE *)v10, a2);
      v12 = 0;
      break;
    case 0x35:
    case 0x91:
      Capacity = SpScsiSynchronizeCache((struct SP_DEVICE *)v10, a2);
      v12 = 0;
      break;
    default:
      Capacity = -1073741822;
      break;
  }
  v9 = 0;
  if ( Capacity != 259 )
    v9 = v12;
  if ( v9 )
    goto LABEL_3;
  return Capacity;
}

```

## disassembly

```asm
0x14001e230  mov     [rsp+arg_8], rbx
0x14001e235  push    rdi
0x14001e236  sub     rsp, 20h
0x14001e23a  mov     rax, [rcx+40h]
0x14001e23e  mov     rdi, rdx
0x14001e241  mov     r8, [rdx+0B8h]
0x14001e248  mov     rdx, [r8+8]
0x14001e24c  mov     qword ptr [rdi+38h], 0
0x14001e254  movzx   ecx, byte ptr [rdx+2]
0x14001e258  cmp     ecx, 6
0x14001e25b  jnz     short loc_14001E2A3
0x14001e25d  xor     ebx, ebx
0x14001e25f  mov     rcx, rdi; struct _IRP *
0x14001e262  mov     [rdi+30h], ebx
0x14001e265  call    ?SpNtStatusToSrbStatus@@YAXPEAU_IRP@@@Z; SpNtStatusToSrbStatus(_IRP *)
0x14001e26a  xor     edx, edx; PriorityBoost
0x14001e26c  mov     rcx, rdi; Irp
0x14001e26f  call    cs:__imp_IofCompleteRequest
0x14001e276  nop     dword ptr [rax+rax+00h]
0x14001e27b  mov     eax, ebx
0x14001e27d  mov     rbx, [rsp+28h+arg_8]
0x14001e282  add     rsp, 20h
0x14001e286  pop     rdi
0x14001e287  retn
0x14001e289  xor     ecx, ecx
0x14001e28b  movzx   eax, sil
0x14001e28f  mov     rsi, [rsp+28h+arg_0]
0x14001e294  cmp     ebx, 103h
0x14001e29a  cmovnz  ecx, eax
0x14001e29d  test    cl, cl
0x14001e29f  jz      short loc_14001E27B
0x14001e2a1  jmp     short loc_14001E25F
0x14001e2a3  lea     r9, [rax+8]
0x14001e2a7  test    ecx, ecx
0x14001e2a9  jz      loc_14006B508
0x14001e2af  sub     ecx, 1
0x14001e2b2  jz      loc_14006B4F4
0x14001e2b8  sub     ecx, 6
0x14001e2bb  jz      short loc_14001E25D
0x14001e2bd  cmp     ecx, 1
0x14001e2c0  jz      short loc_14001E25D
0x14001e2c2  mov     ebx, 0C0000010h
0x14001e2c7  jmp     short loc_14001E25F
0x14006b4f4  mov     rcx, [r8+8]
0x14006b4f8  mov     rax, [r9+0A0h]
0x14006b4ff  mov     [rcx+18h], rax
0x14006b503  jmp     loc_14001E25D
0x14006b508  movzx   eax, byte ptr [rdx+48h]
0x14006b50c  mov     [rsp+28h+arg_0], rsi
0x14006b511  mov     sil, 1
0x14006b514  cmp     eax, 9Eh; switch 159 cases
0x14006b519  ja      def_14006B538; jumptable 000000014006B538 default case, cases 1-17,19-25,28,29,31-36,38,39,41,43-52,54-135,137,139-144,146-157
0x14006b51f  lea     rcx, cs:140000000h
0x14006b526  movzx   eax, ds:(byte_140073643 - 140000000h)[rcx+rax]
0x14006b52e  mov     edx, ds:(jpt_14006B538 - 140000000h)[rcx+rax*4]
0x14006b535  add     rdx, rcx
0x14006b538  jmp     rdx; switch jump
0x14006b53e  mov     rdx, rdi; jumptable 000000014006B538 case 18
0x14006b541  mov     rcx, r9; struct SP_DEVICE *
0x14006b544  call    ?SpScsiInquiry@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiInquiry(SP_DEVICE *,_IRP *)
0x14006b549  mov     ebx, eax
0x14006b54b  jmp     loc_14001E289
0x14006b550  mov     rdx, rdi; jumptable 000000014006B538 cases 37,158
0x14006b553  mov     rcx, r9; this
0x14006b556  call    ?SpScsiReadCapacity@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiReadCapacity(SP_DEVICE *,_IRP *)
0x14006b55b  mov     ebx, eax
0x14006b55d  jmp     loc_14001E289
0x14006b562  mov     rdx, rdi; jumptable 000000014006B538 cases 40,42,136,138
0x14006b565  mov     rcx, r9; struct SP_DEVICE *
0x14006b568  call    ?SpScsiReadWrite@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiReadWrite(SP_DEVICE *,_IRP *)
0x14006b56d  mov     ebx, eax
0x14006b56f  xor     sil, sil
0x14006b572  jmp     loc_14001E289
0x14006b577  mov     rdx, rdi; jumptable 000000014006B538 cases 53,145
0x14006b57a  mov     rcx, r9; struct SP_DEVICE *
0x14006b57d  call    ?SpScsiSynchronizeCache@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiSynchronizeCache(SP_DEVICE *,_IRP *)
0x14006b582  mov     ebx, eax
0x14006b584  xor     sil, sil
0x14006b587  jmp     loc_14001E289
0x14006b58c  mov     rdx, rdi; jumptable 000000014006B538 case 26
0x14006b58f  mov     rcx, r9; struct SP_DEVICE *
0x14006b592  call    ?SpScsiModeSense@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiModeSense(SP_DEVICE *,_IRP *)
0x14006b597  mov     ebx, eax
0x14006b599  jmp     loc_14001E289
0x14006b59e  xor     ebx, ebx; jumptable 000000014006B538 cases 0,27,30
0x14006b5a0  jmp     loc_14001E289
0x14006b5a5  mov     ebx, 0C0000002h; jumptable 000000014006B538 default case, cases 1-17,19-25,28,29,31-36,38,39,41,43-52,54-135,137,139-144,146-157
0x14006b5aa  jmp     loc_14001E289
```

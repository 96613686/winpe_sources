# VmpLogicalToPhysical(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x14001256c`
- end: `0x14001265b`
- name: `?VmpLogicalToPhysical@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `239`
- prototype: `NTSTATUS __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140002db0`
- `0x140005090`
- `0x140005540`
- `0x14001256c`

## pseudocode

```c
NTSTATUS __fastcall VmpLogicalToPhysical(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  NTSTATUS result; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v6; // rsi
  struct _IRP *MasterIrp; // rdx
  _QWORD v8[18]; // [rsp+30h] [rbp-98h] BYREF

  memset(v8, 0, sizeof(v8));
  if ( *((_BYTE *)a1 + 426) )
    return (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(
             *((_QWORD *)a1 + 54),
             a2);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options < 8 || CurrentStackLocation->Parameters.Read.Length < 0x18 )
    return -1073741811;
  v6 = *(_QWORD *)a2->AssociatedIrp.MasterIrp;
  result = VmpSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 43), 0x70048u, 0, 0, v8, 0x90u);
  if ( result < 0 )
    return result;
  if ( v6 < 0 || v6 >= v8[2] )
    return -1073741811;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  *(_DWORD *)&MasterIrp->Type = 1;
  LODWORD(MasterIrp->MdlAddress) = *((_DWORD *)a1 + 96);
  *(_QWORD *)&MasterIrp->Flags = v6 + v8[1];
  result = 0;
  a2->IoStatus.Information = 24;
  return result;
}

```

## disassembly

```asm
0x14001256c  mov     [rsp+arg_0], rbx
0x140012571  mov     [rsp+arg_8], rsi
0x140012576  push    rdi
0x140012577  sub     rsp, 0C0h
0x14001257e  mov     rbx, rdx
0x140012581  mov     rdi, rcx
0x140012584  xor     edx, edx; Val
0x140012586  lea     rcx, [rsp+0C8h+var_98]; void *
0x14001258b  mov     r8d, 90h; Size
0x140012591  call    memset
0x140012596  cmp     byte ptr [rdi+1AAh], 0
0x14001259d  jz      short loc_1400125C2
0x14001259f  mov     rax, [rdi+8]
0x1400125a3  mov     rdx, rbx
0x1400125a6  mov     rcx, [rdi+1B0h]
0x1400125ad  mov     r8, [rax+188h]
0x1400125b4  mov     rax, [r8+68h]
0x1400125b8  call    _guard_dispatch_icall
0x1400125bd  jmp     loc_140012645
0x1400125c2  mov     rax, [rbx+0B8h]
0x1400125c9  cmp     dword ptr [rax+10h], 8
0x1400125cd  jb      short loc_140012640
0x1400125cf  cmp     dword ptr [rax+8], 18h
0x1400125d3  jb      short loc_140012640
0x1400125d5  mov     rax, [rbx+18h]
0x1400125d9  xor     r9d, r9d; InputBufferLength
0x1400125dc  mov     rcx, [rdi+158h]; DeviceObject
0x1400125e3  xor     r8d, r8d; InputBuffer
0x1400125e6  mov     [rsp+0C8h+var_A0], 90h; ULONG
0x1400125ee  mov     edx, 70048h; IoControlCode
0x1400125f3  mov     rsi, [rax]
0x1400125f6  lea     rax, [rsp+0C8h+var_98]
0x1400125fb  mov     [rsp+0C8h+var_A8], rax; PVOID
0x140012600  call    VmpSendDeviceControl
0x140012605  test    eax, eax
0x140012607  js      short loc_140012645
0x140012609  test    rsi, rsi
0x14001260c  js      short loc_140012640
0x14001260e  cmp     rsi, [rsp+0C8h+var_88]
0x140012613  jge     short loc_140012640
0x140012615  mov     rdx, [rbx+18h]
0x140012619  mov     dword ptr [rdx], 1
0x14001261f  mov     eax, [rdi+180h]
0x140012625  mov     [rdx+8], eax
0x140012628  mov     rcx, [rsp+0C8h+var_90]
0x14001262d  add     rcx, rsi
0x140012630  mov     [rdx+10h], rcx
0x140012634  xor     eax, eax
0x140012636  mov     qword ptr [rbx+38h], 18h
0x14001263e  jmp     short loc_140012645
0x140012640  mov     eax, 0C000000Dh
0x140012645  lea     r11, [rsp+0C8h+var_8]
0x14001264d  mov     rbx, [r11+10h]
0x140012651  mov     rsi, [r11+18h]
0x140012655  mov     rsp, r11
0x140012658  pop     rdi
0x140012659  retn
```

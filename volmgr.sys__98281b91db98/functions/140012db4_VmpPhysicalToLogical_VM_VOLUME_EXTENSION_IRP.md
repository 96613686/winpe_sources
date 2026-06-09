# VmpPhysicalToLogical(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140012db4`
- end: `0x140012ea4`
- name: `?VmpPhysicalToLogical@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `240`
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
- `0x140012db4`

## pseudocode

```c
NTSTATUS __fastcall VmpPhysicalToLogical(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  NTSTATUS result; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *MasterIrp; // rbx
  PMDL MdlAddress; // rbx
  _QWORD v8[18]; // [rsp+30h] [rbp-98h] BYREF

  memset(v8, 0, sizeof(v8));
  if ( *((_BYTE *)a1 + 426) )
    return (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(
             *((_QWORD *)a1 + 54),
             a2);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
    return -1073741811;
  if ( CurrentStackLocation->Parameters.Read.Length < 8 )
    return -1073741811;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( *((_DWORD *)a1 + 96) != *(_DWORD *)&MasterIrp->Type )
    return -1073741811;
  MdlAddress = MasterIrp->MdlAddress;
  result = VmpSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 43), 0x70048u, 0, 0, v8, 0x90u);
  if ( result < 0 )
    return result;
  if ( (__int64)MdlAddress < v8[1] || v8[1] + v8[2] <= (__int64)MdlAddress )
    return -1073741811;
  *(_QWORD *)a2->AssociatedIrp.MasterIrp = (char *)MdlAddress - v8[1];
  result = 0;
  a2->IoStatus.Information = 8;
  return result;
}

```

## disassembly

```asm
0x140012db4  mov     [rsp+arg_0], rbx
0x140012db9  mov     [rsp+arg_8], rsi
0x140012dbe  push    rdi
0x140012dbf  sub     rsp, 0C0h
0x140012dc6  mov     rdi, rdx
0x140012dc9  mov     rsi, rcx
0x140012dcc  xor     edx, edx; Val
0x140012dce  lea     rcx, [rsp+0C8h+var_98]; void *
0x140012dd3  mov     r8d, 90h; Size
0x140012dd9  call    memset
0x140012dde  cmp     byte ptr [rsi+1AAh], 0
0x140012de5  jz      short loc_140012E0A
0x140012de7  mov     rax, [rsi+8]
0x140012deb  mov     rdx, rdi
0x140012dee  mov     rcx, [rsi+1B0h]
0x140012df5  mov     r8, [rax+188h]
0x140012dfc  mov     rax, [r8+68h]
0x140012e00  call    _guard_dispatch_icall
0x140012e05  jmp     loc_140012E8E
0x140012e0a  mov     rax, [rdi+0B8h]
0x140012e11  cmp     dword ptr [rax+10h], 10h
0x140012e15  jb      short loc_140012E89
0x140012e17  cmp     dword ptr [rax+8], 8
0x140012e1b  jb      short loc_140012E89
0x140012e1d  mov     rbx, [rdi+18h]
0x140012e21  mov     eax, [rbx]
0x140012e23  cmp     [rsi+180h], eax
0x140012e29  jnz     short loc_140012E89
0x140012e2b  mov     rcx, [rsi+158h]; DeviceObject
0x140012e32  lea     rax, [rsp+0C8h+var_98]
0x140012e37  mov     rbx, [rbx+8]
0x140012e3b  xor     r9d, r9d; InputBufferLength
0x140012e3e  mov     [rsp+0C8h+var_A0], 90h; ULONG
0x140012e46  xor     r8d, r8d; InputBuffer
0x140012e49  mov     edx, 70048h; IoControlCode
0x140012e4e  mov     [rsp+0C8h+var_A8], rax; PVOID
0x140012e53  call    VmpSendDeviceControl
0x140012e58  test    eax, eax
0x140012e5a  js      short loc_140012E8E
0x140012e5c  mov     rdx, [rsp+0C8h+var_90]
0x140012e61  cmp     rbx, rdx
0x140012e64  jl      short loc_140012E89
0x140012e66  mov     rcx, [rsp+0C8h+var_88]
0x140012e6b  add     rcx, rdx
0x140012e6e  cmp     rcx, rbx
0x140012e71  jle     short loc_140012E89
0x140012e73  mov     rax, [rdi+18h]
0x140012e77  sub     rbx, rdx
0x140012e7a  mov     [rax], rbx
0x140012e7d  xor     eax, eax
0x140012e7f  mov     qword ptr [rdi+38h], 8
0x140012e87  jmp     short loc_140012E8E
0x140012e89  mov     eax, 0C000000Dh
0x140012e8e  lea     r11, [rsp+0C8h+var_8]
0x140012e96  mov     rbx, [r11+10h]
0x140012e9a  mov     rsi, [r11+18h]
0x140012e9e  mov     rsp, r11
0x140012ea1  pop     rdi
0x140012ea2  retn
```

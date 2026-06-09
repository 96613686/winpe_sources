# VmpGetVolumeDiskExtents(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140015800`
- end: `0x1400158f2`
- name: `?VmpGetVolumeDiskExtents@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `242`
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
- `0x140015800`

## pseudocode

```c
NTSTATUS __fastcall VmpGetVolumeDiskExtents(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  NTSTATUS result; // eax
  struct _IRP *MasterIrp; // rcx
  _QWORD v6[19]; // [rsp+30h] [rbp-98h] BYREF

  memset(v6, 0, 0x90u);
  if ( *((_BYTE *)a1 + 426) )
    return (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(
             *((_QWORD *)a1 + 54),
             a2);
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 0x20 )
    return -1073741811;
  result = VmpSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 43), 0x70048u, 0, 0, v6, 0x90u);
  if ( result >= 0 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    *(_OWORD *)&MasterIrp->Type = 0;
    *(_OWORD *)&MasterIrp->Flags = 0;
    *(_DWORD *)&MasterIrp->Type = 1;
    LODWORD(MasterIrp->MdlAddress) = *((_DWORD *)a1 + 96);
    *(_QWORD *)&MasterIrp->Flags = v6[1];
    MasterIrp->AssociatedIrp.MasterIrp = (struct _IRP *)v6[2];
    result = 0;
    a2->IoStatus.Information = 32;
  }
  return result;
}

```

## disassembly

```asm
0x140015800  mov     [rsp+arg_0], rbx
0x140015805  push    rdi
0x140015806  sub     rsp, 0C0h
0x14001580d  mov     rdi, rdx
0x140015810  mov     rbx, rcx
0x140015813  xor     edx, edx; Val
0x140015815  lea     rcx, [rsp+0C8h+var_98]; void *
0x14001581a  mov     r8d, 90h; Size
0x140015820  call    memset
0x140015825  cmp     byte ptr [rbx+1AAh], 0
0x14001582c  jnz     loc_1400158BB
0x140015832  mov     rax, [rdi+0B8h]
0x140015839  cmp     dword ptr [rax+8], 20h ; ' '
0x14001583d  jb      loc_1400158EB
0x140015843  mov     rcx, [rbx+158h]; DeviceObject
0x14001584a  lea     rax, [rsp+0C8h+var_98]
0x14001584f  mov     [rsp+0C8h+var_A0], 90h; ULONG
0x140015857  xor     r9d, r9d; InputBufferLength
0x14001585a  xor     r8d, r8d; InputBuffer
0x14001585d  mov     [rsp+0C8h+var_A8], rax; PVOID
0x140015862  mov     edx, 70048h; IoControlCode
0x140015867  call    VmpSendDeviceControl
0x14001586c  test    eax, eax
0x14001586e  js      short loc_1400158A9
0x140015870  mov     rcx, [rdi+18h]
0x140015874  xorps   xmm0, xmm0
0x140015877  movups  xmmword ptr [rcx], xmm0
0x14001587a  movups  xmmword ptr [rcx+10h], xmm0
0x14001587e  mov     dword ptr [rcx], 1
0x140015884  mov     eax, [rbx+180h]
0x14001588a  mov     [rcx+8], eax
0x14001588d  mov     rax, [rsp+0C8h+var_90]
0x140015892  mov     [rcx+10h], rax
0x140015896  mov     rax, [rsp+0C8h+var_88]
0x14001589b  mov     [rcx+18h], rax
0x14001589f  xor     eax, eax
0x1400158a1  mov     qword ptr [rdi+38h], 20h ; ' '
0x1400158a9  mov     rbx, [rsp+0C8h+arg_0]
0x1400158b1  add     rsp, 0C0h
0x1400158b8  pop     rdi
0x1400158b9  retn
0x1400158bb  mov     rax, [rbx+8]
0x1400158bf  mov     rdx, rdi
0x1400158c2  mov     rcx, [rax+188h]
0x1400158c9  mov     rax, [rcx+68h]
0x1400158cd  mov     rcx, [rbx+1B0h]
0x1400158d4  call    _guard_dispatch_icall
0x1400158d9  mov     rbx, [rsp+0C8h+arg_0]
0x1400158e1  add     rsp, 0C0h
0x1400158e8  pop     rdi
0x1400158e9  retn
0x1400158eb  mov     eax, 0C000000Dh
0x1400158f0  jmp     short loc_1400158A9
```

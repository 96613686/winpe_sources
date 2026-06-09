# VhdmpiPrepareIrp(_IRP *,_VHD_SRB_EXTENSION *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *)

- ea: `0x140012d60`
- end: `0x140012fd9`
- name: `?VhdmpiPrepareIrp@@YAXPEAU_IRP@@PEAU_VHD_SRB_EXTENSION@@P6AJPEAU_DEVICE_OBJECT@@0PEAX@Z3@Z`
- size: `633`
- prototype: `void __fastcall(struct _IRP *, struct _VHD_SRB_EXTENSION *, int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *), void *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009a30`
- `0x140012c00`
- `0x140014c30`
- `0x140015540`
- `0x140018480`

## callees

- `0x140012d60`
- `0x140036284`

## import_xrefs

- `ntoskrnl!IoSetIoAttributionIrp` at `0x140012dd5`
- `ntoskrnl!IoSetIoAttributionIrp` at `0x140012dd5`
- `ntoskrnl!IoPropagateIrpExtension` at `0x140012e6e`
- `ntoskrnl!IoPropagateIrpExtension` at `0x140012e6e`
- `ntoskrnl!IoSetActivityIdIrp` at `0x140012f85`
- `ntoskrnl!IoSetActivityIdIrp` at `0x140012f85`
- `storport!StorPortExtendedFunction` at `0x140012efa`
- `storport!StorPortExtendedFunction` at `0x140012efa`

## string_xrefs

- `0x140012f49`: `StorPortPropagateIrpExtension failed: StorStatus = %u, Srb = %p, Irp = %p`
- `0x140012ecd`: `IoPropagateIrpExtension failed: Status = 0x%08x, SourceIrp = %p, Irp = %p`

## pseudocode

```c
void __fastcall VhdmpiPrepareIrp(struct _IRP *a1, struct _VHD_SRB_EXTENSION *a2, unsigned __int64 a3, void *a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // edx
  __int64 v11; // rcx
  int v12; // eax
  unsigned __int16 v13; // dx
  char *v14; // rax
  unsigned int v15; // eax
  struct _IO_STACK_LOCATION *v16; // rcx
  __int64 v17; // [rsp+30h] [rbp-18h]
  struct _IRP *v18; // [rsp+38h] [rbp-10h]

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)a3;
  CurrentStackLocation[-1].Context = a4;
  CurrentStackLocation[-1].Control = -32;
  a1->Tail.Overlay.Thread = (PETHREAD)VhdmpLockBackingFileThread;
  a1->RequestorMode = 0;
  if ( !a2 )
    return;
  v7 = *((_DWORD *)a2 + 17);
  if ( !v7 )
  {
    a3 = *((_QWORD *)a2 + 3);
    if ( !a3 )
      goto LABEL_25;
    v15 = StorPortExtendedFunction(71, VhdmpAdapterExtension, a3, a1, 8);
    a3 = v15;
    if ( !v15
      || (unsigned int)dword_1400876D0 <= 3
      || (qword_1400876E0 & 2) == 0
      || (qword_1400876E8 & 2) != qword_1400876E8 )
    {
      goto LABEL_25;
    }
    v13 = 6307;
    v18 = a1;
    v17 = *((_QWORD *)a2 + 3);
    v14 = "StorPortPropagateIrpExtension failed: StorStatus = %u, Srb = %p, Irp = %p";
    goto LABEL_24;
  }
  if ( v7 == 1 )
  {
    v8 = *((_QWORD *)a2 + 2);
    if ( v8 )
    {
      v9 = *(_QWORD *)(v8 + 96);
      if ( v9 )
      {
        v10 = IoSetIoAttributionIrp(a1, v9, 2);
        if ( (int)(v10 + 0x80000000) >= 0
          && v10 != -1073741275
          && (unsigned int)dword_1400876D0 > 3
          && (qword_1400876E0 & 2) != 0
          && (qword_1400876E8 & 2) == qword_1400876E8 )
        {
          TraceEvents(
            "VhdmpiPrepareIrp",
            0x18BEu,
            3u,
            2u,
            "IoSetIoAttributionIrp failed: Status = 0x%08x, Srb = %p, Irp = %p",
            v10,
            *((_QWORD *)a2 + 3),
            a1);
        }
        goto LABEL_25;
      }
    }
    v11 = *((_QWORD *)a2 + 12);
    if ( v11 )
    {
      v12 = IoPropagateIrpExtension(v11, a1, 8);
      a3 = (unsigned int)v12;
      if ( v12 < 0
        && (unsigned int)dword_1400876D0 > 3
        && (qword_1400876E0 & 2) != 0
        && (qword_1400876E8 & 2) == qword_1400876E8 )
      {
        v13 = 6418;
        v18 = a1;
        v17 = *((_QWORD *)a2 + 12);
        v14 = "IoPropagateIrpExtension failed: Status = 0x%08x, SourceIrp = %p, Irp = %p";
LABEL_24:
        TraceEvents("VhdmpiPrepareIrp", v13, 3u, 2u, v14, a3, v17, v18);
      }
    }
  }
LABEL_25:
  if ( *((_BYTE *)a2 + 272) )
    IoSetActivityIdIrp(a1, (char *)a2 + 256, a3);
  if ( *((_BYTE *)a2 + 274) )
    a1->Tail.Overlay.CurrentStackLocation[-1].FileObject = (PFILE_OBJECT)((unsigned __int64)a1->Tail.Overlay.CurrentStackLocation[-1].FileObject
                                                                        | 8);
  if ( byte_14008E395 && (*((_DWORD *)a2 + 16) & 0x20000) != 0 )
  {
    v16 = a1->Tail.Overlay.CurrentStackLocation;
    if ( (unsigned __int8)(v16[-1].MajorFunction - 3) <= 1u )
      v16[-1].Flags |= 0x20u;
  }
}

```

## disassembly

```asm
0x140012d60  mov     [rsp+arg_0], rbx
0x140012d65  push    rdi
0x140012d66  sub     rsp, 40h
0x140012d6a  mov     rax, [rcx+0B8h]
0x140012d71  mov     rbx, rdx
0x140012d74  mov     rdi, rcx
0x140012d77  mov     [rax-10h], r8
0x140012d7b  mov     [rax-8], r9
0x140012d7f  mov     byte ptr [rax-45h], 0E0h
0x140012d83  mov     rax, cs:VhdmpLockBackingFileThread
0x140012d8a  mov     [rcx+98h], rax
0x140012d91  mov     byte ptr [rcx+40h], 0
0x140012d95  test    rdx, rdx
0x140012d98  jz      loc_140012FCD
0x140012d9e  mov     ecx, [rdx+44h]
0x140012da1  test    ecx, ecx
0x140012da3  jz      loc_140012ED6
0x140012da9  cmp     ecx, 1
0x140012dac  jnz     loc_140012F72
0x140012db2  mov     rax, [rdx+10h]
0x140012db6  test    rax, rax
0x140012db9  jz      loc_140012E58
0x140012dbf  mov     rdx, [rax+60h]
0x140012dc3  test    rdx, rdx
0x140012dc6  jz      loc_140012E58
0x140012dcc  mov     r8d, 2
0x140012dd2  mov     rcx, rdi
0x140012dd5  call    cs:__imp_IoSetIoAttributionIrp
0x140012ddc  nop     dword ptr [rax+rax+00h]
0x140012de1  mov     edx, eax
0x140012de3  mov     eax, 80000000h
0x140012de8  lea     ecx, [rdx+rax]
0x140012deb  test    eax, ecx
0x140012ded  jnz     loc_140012F72
0x140012df3  cmp     edx, 0C0000225h
0x140012df9  jz      loc_140012F72
0x140012dff  mov     ecx, cs:dword_1400876D0
0x140012e05  cmp     ecx, 3
0x140012e08  jbe     loc_140012F72
0x140012e0e  mov     rcx, cs:qword_1400876E8
0x140012e15  mov     rax, cs:qword_1400876E0
0x140012e1c  test    al, 2
0x140012e1e  jz      loc_140012F72
0x140012e24  mov     rax, rcx
0x140012e27  and     eax, 2
0x140012e2a  cmp     rax, rcx
0x140012e2d  jnz     loc_140012F72
0x140012e33  mov     rax, [rbx+18h]
0x140012e37  mov     ecx, 18BEh
0x140012e3c  mov     [rsp+48h+var_10], rdi
0x140012e41  mov     [rsp+48h+var_18], rax
0x140012e46  lea     rax, aIosetioattribu; "IoSetIoAttributionIrp failed: Status = "...
0x140012e4d  mov     dword ptr [rsp+48h+var_20], edx
0x140012e51  mov     edx, ecx
0x140012e53  jmp     loc_140012F55
0x140012e58  mov     rcx, [rbx+60h]
0x140012e5c  test    rcx, rcx
0x140012e5f  jz      loc_140012F72
0x140012e65  mov     r8d, 8
0x140012e6b  mov     rdx, rdi
0x140012e6e  call    cs:__imp_IoPropagateIrpExtension
0x140012e75  nop     dword ptr [rax+rax+00h]
0x140012e7a  mov     r8d, eax
0x140012e7d  test    eax, eax
0x140012e7f  jns     loc_140012F72
0x140012e85  mov     ecx, cs:dword_1400876D0
0x140012e8b  cmp     ecx, 3
0x140012e8e  jbe     loc_140012F72
0x140012e94  mov     rdx, cs:qword_1400876E8
0x140012e9b  mov     rcx, cs:qword_1400876E0
0x140012ea2  test    cl, 2
0x140012ea5  jz      loc_140012F72
0x140012eab  mov     rcx, rdx
0x140012eae  and     ecx, 2
0x140012eb1  cmp     rcx, rdx
0x140012eb4  jnz     loc_140012F72
0x140012eba  mov     rax, [rbx+60h]
0x140012ebe  mov     edx, 1912h
0x140012ec3  mov     [rsp+48h+var_10], rdi
0x140012ec8  mov     [rsp+48h+var_18], rax
0x140012ecd  lea     rax, aIopropagateirp; "IoPropagateIrpExtension failed: Status "...
0x140012ed4  jmp     short loc_140012F50
0x140012ed6  mov     r8, [rdx+18h]
0x140012eda  test    r8, r8
0x140012edd  jz      loc_140012F72
0x140012ee3  mov     rdx, cs:VhdmpAdapterExtension
0x140012eea  mov     r9, rdi
0x140012eed  mov     ecx, 47h ; 'G'
0x140012ef2  mov     dword ptr [rsp+48h+var_28], 8
0x140012efa  call    cs:__imp_StorPortExtendedFunction
0x140012f01  nop     dword ptr [rax+rax+00h]
0x140012f06  mov     r8d, eax
0x140012f09  test    eax, eax
0x140012f0b  jz      short loc_140012F72
0x140012f0d  mov     ecx, cs:dword_1400876D0
0x140012f13  cmp     ecx, 3
0x140012f16  jbe     short loc_140012F72
0x140012f18  mov     rdx, cs:qword_1400876E8
0x140012f1f  mov     rcx, cs:qword_1400876E0
0x140012f26  test    cl, 2
0x140012f29  jz      short loc_140012F72
0x140012f2b  mov     rcx, rdx
0x140012f2e  and     ecx, 2
0x140012f31  cmp     rcx, rdx
0x140012f34  jnz     short loc_140012F72
0x140012f36  mov     rax, [rbx+18h]
0x140012f3a  mov     edx, 18A3h; int
0x140012f3f  mov     [rsp+48h+var_10], rdi
0x140012f44  mov     [rsp+48h+var_18], rax
0x140012f49  lea     rax, aStorportpropag; "StorPortPropagateIrpExtension failed: S"...
0x140012f50  mov     dword ptr [rsp+48h+var_20], r8d; char
0x140012f55  mov     r9d, 2; int
0x140012f5b  mov     [rsp+48h+var_28], rax; char *
0x140012f60  mov     r8d, 3; int
0x140012f66  lea     rcx, aVhdmpipreparei; "VhdmpiPrepareIrp"
0x140012f6d  call    TraceEvents
0x140012f72  cmp     byte ptr [rbx+110h], 0
0x140012f79  jz      short loc_140012F91
0x140012f7b  lea     rdx, [rbx+100h]
0x140012f82  mov     rcx, rdi
0x140012f85  call    cs:__imp_IoSetActivityIdIrp
0x140012f8c  nop     dword ptr [rax+rax+00h]
0x140012f91  cmp     byte ptr [rbx+112h], 0
0x140012f98  jz      short loc_140012FA6
0x140012f9a  mov     rax, [rdi+0B8h]
0x140012fa1  or      qword ptr [rax-18h], 8
0x140012fa6  cmp     cs:byte_14008E395, 0
0x140012fad  jz      short loc_140012FCD
0x140012faf  test    dword ptr [rbx+40h], 20000h
0x140012fb6  jz      short loc_140012FCD
0x140012fb8  mov     rcx, [rdi+0B8h]
0x140012fbf  movzx   eax, byte ptr [rcx-48h]
0x140012fc3  sub     al, 3
0x140012fc5  cmp     al, 1
0x140012fc7  ja      short loc_140012FCD
0x140012fc9  or      byte ptr [rcx-46h], 20h
0x140012fcd  mov     rbx, [rsp+48h+arg_0]
0x140012fd2  add     rsp, 40h
0x140012fd6  pop     rdi
0x140012fd7  retn
```

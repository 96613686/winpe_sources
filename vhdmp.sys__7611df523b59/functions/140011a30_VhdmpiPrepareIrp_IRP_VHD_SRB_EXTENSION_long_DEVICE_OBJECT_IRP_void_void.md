# VhdmpiPrepareIrp(_IRP *,_VHD_SRB_EXTENSION *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *)

- ea: `0x140011a30`
- end: `0x140011ca9`
- name: `?VhdmpiPrepareIrp@@YAXPEAU_IRP@@PEAU_VHD_SRB_EXTENSION@@P6AJPEAU_DEVICE_OBJECT@@0PEAX@Z3@Z`
- size: `633`
- prototype: `void __fastcall(struct _IRP *, struct _VHD_SRB_EXTENSION *, int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *), void *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009a30`
- `0x1400118d0`
- `0x140014790`
- `0x1400150a0`
- `0x140017fe0`

## callees

- `0x140011a30`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!IoSetIoAttributionIrp` at `0x140011aa5`
- `ntoskrnl!IoSetIoAttributionIrp` at `0x140011aa5`
- `ntoskrnl!IoPropagateIrpExtension` at `0x140011b3e`
- `ntoskrnl!IoPropagateIrpExtension` at `0x140011b3e`
- `ntoskrnl!IoSetActivityIdIrp` at `0x140011c55`
- `ntoskrnl!IoSetActivityIdIrp` at `0x140011c55`
- `storport!StorPortExtendedFunction` at `0x140011bca`
- `storport!StorPortExtendedFunction` at `0x140011bca`

## string_xrefs

- `0x140011b9d`: `IoPropagateIrpExtension failed: Status = 0x%08x, SourceIrp = %p, Irp = %p`
- `0x140011c19`: `StorPortPropagateIrpExtension failed: StorStatus = %u, Srb = %p, Irp = %p`

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
      || (unsigned int)dword_140087708 <= 3
      || (qword_140087718 & 2) == 0
      || (qword_140087720 & 2) != qword_140087720 )
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
          && (unsigned int)dword_140087708 > 3
          && (qword_140087718 & 2) != 0
          && (qword_140087720 & 2) == qword_140087720 )
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
        && (unsigned int)dword_140087708 > 3
        && (qword_140087718 & 2) != 0
        && (qword_140087720 & 2) == qword_140087720 )
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
0x140011a30  mov     [rsp+arg_0], rbx
0x140011a35  push    rdi
0x140011a36  sub     rsp, 40h
0x140011a3a  mov     rax, [rcx+0B8h]
0x140011a41  mov     rbx, rdx
0x140011a44  mov     rdi, rcx
0x140011a47  mov     [rax-10h], r8
0x140011a4b  mov     [rax-8], r9
0x140011a4f  mov     byte ptr [rax-45h], 0E0h
0x140011a53  mov     rax, cs:VhdmpLockBackingFileThread
0x140011a5a  mov     [rcx+98h], rax
0x140011a61  mov     byte ptr [rcx+40h], 0
0x140011a65  test    rdx, rdx
0x140011a68  jz      loc_140011C9D
0x140011a6e  mov     ecx, [rdx+44h]
0x140011a71  test    ecx, ecx
0x140011a73  jz      loc_140011BA6
0x140011a79  cmp     ecx, 1
0x140011a7c  jnz     loc_140011C42
0x140011a82  mov     rax, [rdx+10h]
0x140011a86  test    rax, rax
0x140011a89  jz      loc_140011B28
0x140011a8f  mov     rdx, [rax+60h]
0x140011a93  test    rdx, rdx
0x140011a96  jz      loc_140011B28
0x140011a9c  mov     r8d, 2
0x140011aa2  mov     rcx, rdi
0x140011aa5  call    cs:__imp_IoSetIoAttributionIrp
0x140011aac  nop     dword ptr [rax+rax+00h]
0x140011ab1  mov     edx, eax
0x140011ab3  mov     eax, 80000000h
0x140011ab8  lea     ecx, [rdx+rax]
0x140011abb  test    eax, ecx
0x140011abd  jnz     loc_140011C42
0x140011ac3  cmp     edx, 0C0000225h
0x140011ac9  jz      loc_140011C42
0x140011acf  mov     ecx, cs:dword_140087708
0x140011ad5  cmp     ecx, 3
0x140011ad8  jbe     loc_140011C42
0x140011ade  mov     rcx, cs:qword_140087720
0x140011ae5  mov     rax, cs:qword_140087718
0x140011aec  test    al, 2
0x140011aee  jz      loc_140011C42
0x140011af4  mov     rax, rcx
0x140011af7  and     eax, 2
0x140011afa  cmp     rax, rcx
0x140011afd  jnz     loc_140011C42
0x140011b03  mov     rax, [rbx+18h]
0x140011b07  mov     ecx, 18BEh
0x140011b0c  mov     [rsp+48h+var_10], rdi
0x140011b11  mov     [rsp+48h+var_18], rax
0x140011b16  lea     rax, aIosetioattribu; "IoSetIoAttributionIrp failed: Status = "...
0x140011b1d  mov     dword ptr [rsp+48h+var_20], edx
0x140011b21  mov     edx, ecx
0x140011b23  jmp     loc_140011C25
0x140011b28  mov     rcx, [rbx+60h]
0x140011b2c  test    rcx, rcx
0x140011b2f  jz      loc_140011C42
0x140011b35  mov     r8d, 8
0x140011b3b  mov     rdx, rdi
0x140011b3e  call    cs:__imp_IoPropagateIrpExtension
0x140011b45  nop     dword ptr [rax+rax+00h]
0x140011b4a  mov     r8d, eax
0x140011b4d  test    eax, eax
0x140011b4f  jns     loc_140011C42
0x140011b55  mov     ecx, cs:dword_140087708
0x140011b5b  cmp     ecx, 3
0x140011b5e  jbe     loc_140011C42
0x140011b64  mov     rdx, cs:qword_140087720
0x140011b6b  mov     rcx, cs:qword_140087718
0x140011b72  test    cl, 2
0x140011b75  jz      loc_140011C42
0x140011b7b  mov     rcx, rdx
0x140011b7e  and     ecx, 2
0x140011b81  cmp     rcx, rdx
0x140011b84  jnz     loc_140011C42
0x140011b8a  mov     rax, [rbx+60h]
0x140011b8e  mov     edx, 1912h
0x140011b93  mov     [rsp+48h+var_10], rdi
0x140011b98  mov     [rsp+48h+var_18], rax
0x140011b9d  lea     rax, aIopropagateirp; "IoPropagateIrpExtension failed: Status "...
0x140011ba4  jmp     short loc_140011C20
0x140011ba6  mov     r8, [rdx+18h]
0x140011baa  test    r8, r8
0x140011bad  jz      loc_140011C42
0x140011bb3  mov     rdx, cs:VhdmpAdapterExtension
0x140011bba  mov     r9, rdi
0x140011bbd  mov     ecx, 47h ; 'G'
0x140011bc2  mov     dword ptr [rsp+48h+var_28], 8
0x140011bca  call    cs:__imp_StorPortExtendedFunction
0x140011bd1  nop     dword ptr [rax+rax+00h]
0x140011bd6  mov     r8d, eax
0x140011bd9  test    eax, eax
0x140011bdb  jz      short loc_140011C42
0x140011bdd  mov     ecx, cs:dword_140087708
0x140011be3  cmp     ecx, 3
0x140011be6  jbe     short loc_140011C42
0x140011be8  mov     rdx, cs:qword_140087720
0x140011bef  mov     rcx, cs:qword_140087718
0x140011bf6  test    cl, 2
0x140011bf9  jz      short loc_140011C42
0x140011bfb  mov     rcx, rdx
0x140011bfe  and     ecx, 2
0x140011c01  cmp     rcx, rdx
0x140011c04  jnz     short loc_140011C42
0x140011c06  mov     rax, [rbx+18h]
0x140011c0a  mov     edx, 18A3h; int
0x140011c0f  mov     [rsp+48h+var_10], rdi
0x140011c14  mov     [rsp+48h+var_18], rax
0x140011c19  lea     rax, aStorportpropag; "StorPortPropagateIrpExtension failed: S"...
0x140011c20  mov     dword ptr [rsp+48h+var_20], r8d; char
0x140011c25  mov     r9d, 2; int
0x140011c2b  mov     [rsp+48h+var_28], rax; char *
0x140011c30  mov     r8d, 3; int
0x140011c36  lea     rcx, aVhdmpipreparei; "VhdmpiPrepareIrp"
0x140011c3d  call    TraceEvents
0x140011c42  cmp     byte ptr [rbx+110h], 0
0x140011c49  jz      short loc_140011C61
0x140011c4b  lea     rdx, [rbx+100h]
0x140011c52  mov     rcx, rdi
0x140011c55  call    cs:__imp_IoSetActivityIdIrp
0x140011c5c  nop     dword ptr [rax+rax+00h]
0x140011c61  cmp     byte ptr [rbx+112h], 0
0x140011c68  jz      short loc_140011C76
0x140011c6a  mov     rax, [rdi+0B8h]
0x140011c71  or      qword ptr [rax-18h], 8
0x140011c76  cmp     cs:byte_14008E395, 0
0x140011c7d  jz      short loc_140011C9D
0x140011c7f  test    dword ptr [rbx+40h], 20000h
0x140011c86  jz      short loc_140011C9D
0x140011c88  mov     rcx, [rdi+0B8h]
0x140011c8f  movzx   eax, byte ptr [rcx-48h]
0x140011c93  sub     al, 3
0x140011c95  cmp     al, 1
0x140011c97  ja      short loc_140011C9D
0x140011c99  or      byte ptr [rcx-46h], 20h
0x140011c9d  mov     rbx, [rsp+48h+arg_0]
0x140011ca2  add     rsp, 40h
0x140011ca6  pop     rdi
0x140011ca7  retn
```

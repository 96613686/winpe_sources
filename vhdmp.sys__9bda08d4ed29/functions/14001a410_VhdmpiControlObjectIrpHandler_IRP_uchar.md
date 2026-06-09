# VhdmpiControlObjectIrpHandler(_IRP *,uchar)

- ea: `0x14001a410`
- end: `0x14001a600`
- name: `?VhdmpiControlObjectIrpHandler@@YAJPEAU_IRP@@E@Z`
- size: `496`
- prototype: `__int64 __fastcall(struct _IRP *, unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018860`

## callees

- `0x14001a410`
- `0x14001a608`
- `0x1400465d4`
- `0x140047638`
- `0x140048bb8`
- `0x140048c20`
- `0x14009d7a4`
- `0x1400e8fc4`
- `0x1400e9d84`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001a4aa`
- `ntoskrnl!IofCompleteRequest` at `0x14001a590`
- `ntoskrnl!IofCompleteRequest` at `0x14001a5cb`
- `ntoskrnl!IofCompleteRequest` at `0x14001a4aa`
- `ntoskrnl!IofCompleteRequest` at `0x14001a590`
- `ntoskrnl!IofCompleteRequest` at `0x14001a5cb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001a51c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001a570`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001a51c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001a570`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001a487`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001a487`

## pseudocode

```c
__int64 __fastcall VhdmpiControlObjectIrpHandler(struct _IRP *a1, unsigned __int8 a2)
{
  int v2; // edi
  struct _IRP *v3; // rbx
  unsigned int v5; // edi
  struct _EX_RUNDOWN_REF *FsContext2; // rsi
  int v8; // edi
  int v9; // edi
  int v10; // edi
  int v11; // eax
  bool v12; // zf

  v2 = a2;
  v3 = a1;
  switch ( a2 )
  {
    case 0u:
      return (unsigned int)VhdmpiCreateHandler(a1);
    case 2u:
      return (unsigned int)VhdmpiCloseHandler(a1);
    case 3u:
    case 4u:
    case 9u:
    case 0xEu:
      FsContext2 = (struct _EX_RUNDOWN_REF *)a1->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2;
      if ( !FsContext2 )
      {
        if ( a2 == 14 )
        {
          if ( a1->RequestorMode )
            return (unsigned int)VhdmpiRootControlObjectDeviceControlHandlerUserMode(a1);
          else
            return (unsigned int)VhdmpiRootControlObjectDeviceControlHandlerKernelMode(a1);
        }
        goto LABEL_14;
      }
      if ( !ExAcquireRundownProtection(FsContext2 + 33) )
      {
        a1 = v3;
LABEL_14:
        v3->IoStatus.Status = -1073741528;
        v5 = -1073741528;
LABEL_15:
        v3->IoStatus.Information = 0;
        IofCompleteRequest(a1, 0);
        return v5;
      }
      v8 = v2 - 3;
      if ( !v8 || (v9 = v8 - 1) == 0 || (v10 = v9 - 5) == 0 )
      {
        if ( (HIDWORD(FsContext2->Ptr) & 0x800) != 0 )
        {
          v5 = -1073741637;
          v3->IoStatus.Information = 0;
          v3->IoStatus.Status = -1073741637;
          IofCompleteRequest(v3, 0);
          goto LABEL_25;
        }
        v5 = VhdmpiRawIoHandler((struct _VHD_HANDLE_CONTEXT *)FsContext2, v3);
        v12 = v5 == 259;
LABEL_24:
        if ( v12 )
          return v5;
LABEL_25:
        ExReleaseRundownProtection(FsContext2 + 33);
        return v5;
      }
      if ( v10 == 5 )
      {
        if ( FsContext2[38].Count || **(char ****)(FsContext2[7].Count + 144) != &IsoParser )
        {
          v11 = VhdmpiVhdControlObjectDeviceControlHandler((struct _VHD_HANDLE_CONTEXT *)FsContext2, v3);
LABEL_23:
          v5 = v11;
          v12 = v11 == 259;
          goto LABEL_24;
        }
      }
      else
      {
        ExReleaseRundownProtection(FsContext2 + 33);
        v3->IoStatus.Information = 0;
        v3->IoStatus.Status = -1073741808;
        IofCompleteRequest(v3, 0);
        __debugbreak();
      }
      v11 = VhdmpiIsoControlObjectDeviceControlHandler((struct _VHD_HANDLE_CONTEXT *)FsContext2, v3);
      goto LABEL_23;
  }
  if ( a2 != 18 )
  {
    v5 = -1073741637;
    a1->IoStatus.Status = -1073741637;
    goto LABEL_15;
  }
  return (unsigned int)VhdmpiCleanupHandler(a1);
}

```

## disassembly

```asm
0x14001a410  push    rbx
0x14001a412  push    rbp
0x14001a413  push    rsi
0x14001a414  push    rdi
0x14001a415  sub     rsp, 28h
0x14001a419  movzx   edi, dl
0x14001a41c  mov     rbx, rcx
0x14001a41f  mov     ecx, edi
0x14001a421  test    dl, dl
0x14001a423  jz      loc_14001A52D
0x14001a429  sub     ecx, 2
0x14001a42c  jz      loc_14001A5F3
0x14001a432  sub     ecx, 1
0x14001a435  jz      short loc_14001A465
0x14001a437  sub     ecx, 1
0x14001a43a  jz      short loc_14001A465
0x14001a43c  sub     ecx, 5
0x14001a43f  jz      short loc_14001A465
0x14001a441  sub     ecx, 5
0x14001a444  jz      short loc_14001A465
0x14001a446  cmp     ecx, 4
0x14001a449  mov     rcx, rbx; Irp
0x14001a44c  jnz     loc_14001A53A
0x14001a452  call    ?VhdmpiCleanupHandler@@YAJPEAU_IRP@@@Z; VhdmpiCleanupHandler(_IRP *)
0x14001a457  mov     edi, eax
0x14001a459  mov     eax, edi
0x14001a45b  add     rsp, 28h
0x14001a45f  pop     rdi
0x14001a460  pop     rsi
0x14001a461  pop     rbp
0x14001a462  pop     rbx
0x14001a463  retn
0x14001a465  mov     rax, [rbx+0B8h]
0x14001a46c  mov     rcx, [rax+30h]
0x14001a470  mov     rsi, [rcx+20h]
0x14001a474  test    rsi, rsi
0x14001a477  jz      loc_14001A547
0x14001a47d  lea     rbp, [rsi+108h]
0x14001a484  mov     rcx, rbp; RunRef
0x14001a487  call    cs:__imp_ExAcquireRundownProtection
0x14001a48e  nop     dword ptr [rax+rax+00h]
0x14001a493  test    al, al
0x14001a495  jnz     short loc_14001A4B8
0x14001a497  mov     rcx, rbx; Irp
0x14001a49a  mov     eax, 0C0000128h
0x14001a49f  mov     [rbx+30h], eax
0x14001a4a2  mov     edi, eax
0x14001a4a4  xor     edx, edx; PriorityBoost
0x14001a4a6  mov     [rbx+38h], rdx
0x14001a4aa  call    cs:__imp_IofCompleteRequest
0x14001a4b1  nop     dword ptr [rax+rax+00h]
0x14001a4b6  jmp     short loc_14001A459
0x14001a4b8  sub     edi, 3
0x14001a4bb  jz      loc_14001A5AD
0x14001a4c1  sub     edi, 1
0x14001a4c4  jz      loc_14001A5AD
0x14001a4ca  sub     edi, 5
0x14001a4cd  jz      loc_14001A5AD
0x14001a4d3  cmp     edi, 5
0x14001a4d6  jnz     loc_14001A56D
0x14001a4dc  cmp     qword ptr [rsi+130h], 0
0x14001a4e4  jnz     short loc_14001A501
0x14001a4e6  mov     rax, [rsi+38h]
0x14001a4ea  mov     rcx, [rax+90h]
0x14001a4f1  lea     rax, IsoParser
0x14001a4f8  cmp     [rcx], rax
0x14001a4fb  jz      loc_14001A59D
0x14001a501  mov     rdx, rbx; struct _IRP *
0x14001a504  mov     rcx, rsi; struct _VHD_HANDLE_CONTEXT *
0x14001a507  call    ?VhdmpiVhdControlObjectDeviceControlHandler@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z; VhdmpiVhdControlObjectDeviceControlHandler(_VHD_HANDLE_CONTEXT *,_IRP *)
0x14001a50c  mov     edi, eax
0x14001a50e  cmp     eax, 103h
0x14001a513  jz      loc_14001A459
0x14001a519  mov     rcx, rbp; RunRef
0x14001a51c  call    cs:__imp_ExReleaseRundownProtection
0x14001a523  nop     dword ptr [rax+rax+00h]
0x14001a528  jmp     loc_14001A459
0x14001a52d  mov     rcx, rbx; struct _IRP *
0x14001a530  call    VhdmpiCreateHandler
0x14001a535  jmp     loc_14001A457
0x14001a53a  mov     edi, 0C00000BBh
0x14001a53f  mov     [rbx+30h], edi
0x14001a542  jmp     loc_14001A4A4
0x14001a547  mov     rcx, rbx; Irp
0x14001a54a  cmp     dl, 0Eh
0x14001a54d  jnz     loc_14001A49A
0x14001a553  cmp     byte ptr [rbx+40h], 0
0x14001a557  jnz     short loc_14001A563
0x14001a559  call    ?VhdmpiRootControlObjectDeviceControlHandlerKernelMode@@YAJPEAU_IRP@@@Z; VhdmpiRootControlObjectDeviceControlHandlerKernelMode(_IRP *)
0x14001a55e  jmp     loc_14001A457
0x14001a563  call    ?VhdmpiRootControlObjectDeviceControlHandlerUserMode@@YAJPEAU_IRP@@@Z; VhdmpiRootControlObjectDeviceControlHandlerUserMode(_IRP *)
0x14001a568  jmp     loc_14001A457
0x14001a56d  mov     rcx, rbp; RunRef
0x14001a570  call    cs:__imp_ExReleaseRundownProtection
0x14001a577  nop     dword ptr [rax+rax+00h]
0x14001a57c  xor     edx, edx; PriorityBoost
0x14001a57e  mov     qword ptr [rbx+38h], 0
0x14001a586  mov     rcx, rbx; Irp
0x14001a589  mov     dword ptr [rbx+30h], 0C0000010h
0x14001a590  call    cs:__imp_IofCompleteRequest
0x14001a597  nop     dword ptr [rax+rax+00h]
0x14001a59c  int     3; Trap to Debugger
0x14001a59d  mov     rdx, rbx; struct _IRP *
0x14001a5a0  mov     rcx, rsi; struct _VHD_HANDLE_CONTEXT *
0x14001a5a3  call    ?VhdmpiIsoControlObjectDeviceControlHandler@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z; VhdmpiIsoControlObjectDeviceControlHandler(_VHD_HANDLE_CONTEXT *,_IRP *)
0x14001a5a8  jmp     loc_14001A50C
0x14001a5ad  test    dword ptr [rsi+4], 800h
0x14001a5b4  jz      short loc_14001A5DC
0x14001a5b6  mov     edi, 0C00000BBh
0x14001a5bb  mov     qword ptr [rbx+38h], 0
0x14001a5c3  xor     edx, edx; PriorityBoost
0x14001a5c5  mov     [rbx+30h], edi
0x14001a5c8  mov     rcx, rbx; Irp
0x14001a5cb  call    cs:__imp_IofCompleteRequest
0x14001a5d2  nop     dword ptr [rax+rax+00h]
0x14001a5d7  jmp     loc_14001A519
0x14001a5dc  mov     rdx, rbx; struct _IRP *
0x14001a5df  mov     rcx, rsi; struct _VHD_HANDLE_CONTEXT *
0x14001a5e2  call    ?VhdmpiRawIoHandler@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z; VhdmpiRawIoHandler(_VHD_HANDLE_CONTEXT *,_IRP *)
0x14001a5e7  mov     edi, eax
0x14001a5e9  cmp     eax, 103h
0x14001a5ee  jmp     loc_14001A513
0x14001a5f3  mov     rcx, rbx; Irp
0x14001a5f6  call    ?VhdmpiCloseHandler@@YAJPEAU_IRP@@@Z; VhdmpiCloseHandler(_IRP *)
0x14001a5fb  jmp     loc_14001A457
```

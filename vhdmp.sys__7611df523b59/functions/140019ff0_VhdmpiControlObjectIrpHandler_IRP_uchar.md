# VhdmpiControlObjectIrpHandler(_IRP *,uchar)

- ea: `0x140019ff0`
- end: `0x14001a1e0`
- name: `?VhdmpiControlObjectIrpHandler@@YAJPEAU_IRP@@E@Z`
- size: `496`
- prototype: `__int64 __fastcall(struct _IRP *, unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400183c0`

## callees

- `0x140019ff0`
- `0x14001a1e8`
- `0x1400461e4`
- `0x140047248`
- `0x1400487c8`
- `0x140048830`
- `0x14009d7a4`
- `0x1400e9034`
- `0x1400e9df4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001a08a`
- `ntoskrnl!IofCompleteRequest` at `0x14001a170`
- `ntoskrnl!IofCompleteRequest` at `0x14001a1ab`
- `ntoskrnl!IofCompleteRequest` at `0x14001a08a`
- `ntoskrnl!IofCompleteRequest` at `0x14001a170`
- `ntoskrnl!IofCompleteRequest` at `0x14001a1ab`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001a0fc`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001a150`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001a0fc`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001a150`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001a067`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001a067`

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
0x140019ff0  push    rbx
0x140019ff2  push    rbp
0x140019ff3  push    rsi
0x140019ff4  push    rdi
0x140019ff5  sub     rsp, 28h
0x140019ff9  movzx   edi, dl
0x140019ffc  mov     rbx, rcx
0x140019fff  mov     ecx, edi
0x14001a001  test    dl, dl
0x14001a003  jz      loc_14001A10D
0x14001a009  sub     ecx, 2
0x14001a00c  jz      loc_14001A1D3
0x14001a012  sub     ecx, 1
0x14001a015  jz      short loc_14001A045
0x14001a017  sub     ecx, 1
0x14001a01a  jz      short loc_14001A045
0x14001a01c  sub     ecx, 5
0x14001a01f  jz      short loc_14001A045
0x14001a021  sub     ecx, 5
0x14001a024  jz      short loc_14001A045
0x14001a026  cmp     ecx, 4
0x14001a029  mov     rcx, rbx; Irp
0x14001a02c  jnz     loc_14001A11A
0x14001a032  call    ?VhdmpiCleanupHandler@@YAJPEAU_IRP@@@Z; VhdmpiCleanupHandler(_IRP *)
0x14001a037  mov     edi, eax
0x14001a039  mov     eax, edi
0x14001a03b  add     rsp, 28h
0x14001a03f  pop     rdi
0x14001a040  pop     rsi
0x14001a041  pop     rbp
0x14001a042  pop     rbx
0x14001a043  retn
0x14001a045  mov     rax, [rbx+0B8h]
0x14001a04c  mov     rcx, [rax+30h]
0x14001a050  mov     rsi, [rcx+20h]
0x14001a054  test    rsi, rsi
0x14001a057  jz      loc_14001A127
0x14001a05d  lea     rbp, [rsi+108h]
0x14001a064  mov     rcx, rbp; RunRef
0x14001a067  call    cs:__imp_ExAcquireRundownProtection
0x14001a06e  nop     dword ptr [rax+rax+00h]
0x14001a073  test    al, al
0x14001a075  jnz     short loc_14001A098
0x14001a077  mov     rcx, rbx; Irp
0x14001a07a  mov     eax, 0C0000128h
0x14001a07f  mov     [rbx+30h], eax
0x14001a082  mov     edi, eax
0x14001a084  xor     edx, edx; PriorityBoost
0x14001a086  mov     [rbx+38h], rdx
0x14001a08a  call    cs:__imp_IofCompleteRequest
0x14001a091  nop     dword ptr [rax+rax+00h]
0x14001a096  jmp     short loc_14001A039
0x14001a098  sub     edi, 3
0x14001a09b  jz      loc_14001A18D
0x14001a0a1  sub     edi, 1
0x14001a0a4  jz      loc_14001A18D
0x14001a0aa  sub     edi, 5
0x14001a0ad  jz      loc_14001A18D
0x14001a0b3  cmp     edi, 5
0x14001a0b6  jnz     loc_14001A14D
0x14001a0bc  cmp     qword ptr [rsi+130h], 0
0x14001a0c4  jnz     short loc_14001A0E1
0x14001a0c6  mov     rax, [rsi+38h]
0x14001a0ca  mov     rcx, [rax+90h]
0x14001a0d1  lea     rax, IsoParser
0x14001a0d8  cmp     [rcx], rax
0x14001a0db  jz      loc_14001A17D
0x14001a0e1  mov     rdx, rbx; struct _IRP *
0x14001a0e4  mov     rcx, rsi; struct _VHD_HANDLE_CONTEXT *
0x14001a0e7  call    ?VhdmpiVhdControlObjectDeviceControlHandler@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z; VhdmpiVhdControlObjectDeviceControlHandler(_VHD_HANDLE_CONTEXT *,_IRP *)
0x14001a0ec  mov     edi, eax
0x14001a0ee  cmp     eax, 103h
0x14001a0f3  jz      loc_14001A039
0x14001a0f9  mov     rcx, rbp; RunRef
0x14001a0fc  call    cs:__imp_ExReleaseRundownProtection
0x14001a103  nop     dword ptr [rax+rax+00h]
0x14001a108  jmp     loc_14001A039
0x14001a10d  mov     rcx, rbx; struct _IRP *
0x14001a110  call    VhdmpiCreateHandler
0x14001a115  jmp     loc_14001A037
0x14001a11a  mov     edi, 0C00000BBh
0x14001a11f  mov     [rbx+30h], edi
0x14001a122  jmp     loc_14001A084
0x14001a127  mov     rcx, rbx; Irp
0x14001a12a  cmp     dl, 0Eh
0x14001a12d  jnz     loc_14001A07A
0x14001a133  cmp     byte ptr [rbx+40h], 0
0x14001a137  jnz     short loc_14001A143
0x14001a139  call    ?VhdmpiRootControlObjectDeviceControlHandlerKernelMode@@YAJPEAU_IRP@@@Z; VhdmpiRootControlObjectDeviceControlHandlerKernelMode(_IRP *)
0x14001a13e  jmp     loc_14001A037
0x14001a143  call    ?VhdmpiRootControlObjectDeviceControlHandlerUserMode@@YAJPEAU_IRP@@@Z; VhdmpiRootControlObjectDeviceControlHandlerUserMode(_IRP *)
0x14001a148  jmp     loc_14001A037
0x14001a14d  mov     rcx, rbp; RunRef
0x14001a150  call    cs:__imp_ExReleaseRundownProtection
0x14001a157  nop     dword ptr [rax+rax+00h]
0x14001a15c  xor     edx, edx; PriorityBoost
0x14001a15e  mov     qword ptr [rbx+38h], 0
0x14001a166  mov     rcx, rbx; Irp
0x14001a169  mov     dword ptr [rbx+30h], 0C0000010h
0x14001a170  call    cs:__imp_IofCompleteRequest
0x14001a177  nop     dword ptr [rax+rax+00h]
0x14001a17c  int     3; Trap to Debugger
0x14001a17d  mov     rdx, rbx; struct _IRP *
0x14001a180  mov     rcx, rsi; struct _VHD_HANDLE_CONTEXT *
0x14001a183  call    ?VhdmpiIsoControlObjectDeviceControlHandler@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z; VhdmpiIsoControlObjectDeviceControlHandler(_VHD_HANDLE_CONTEXT *,_IRP *)
0x14001a188  jmp     loc_14001A0EC
0x14001a18d  test    dword ptr [rsi+4], 800h
0x14001a194  jz      short loc_14001A1BC
0x14001a196  mov     edi, 0C00000BBh
0x14001a19b  mov     qword ptr [rbx+38h], 0
0x14001a1a3  xor     edx, edx; PriorityBoost
0x14001a1a5  mov     [rbx+30h], edi
0x14001a1a8  mov     rcx, rbx; Irp
0x14001a1ab  call    cs:__imp_IofCompleteRequest
0x14001a1b2  nop     dword ptr [rax+rax+00h]
0x14001a1b7  jmp     loc_14001A0F9
0x14001a1bc  mov     rdx, rbx; struct _IRP *
0x14001a1bf  mov     rcx, rsi; struct _VHD_HANDLE_CONTEXT *
0x14001a1c2  call    ?VhdmpiRawIoHandler@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z; VhdmpiRawIoHandler(_VHD_HANDLE_CONTEXT *,_IRP *)
0x14001a1c7  mov     edi, eax
0x14001a1c9  cmp     eax, 103h
0x14001a1ce  jmp     loc_14001A0F3
0x14001a1d3  mov     rcx, rbx; Irp
0x14001a1d6  call    ?VhdmpiCloseHandler@@YAJPEAU_IRP@@@Z; VhdmpiCloseHandler(_IRP *)
0x14001a1db  jmp     loc_14001A037
```

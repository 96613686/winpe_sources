# VhdmpiIsoInsertMediaThread(_VHD_HANDLE_CONTEXT *,_VHD_ASYNC_OP_CONTEXT *,void *,ulong)

- ea: `0x1400aa6a0`
- end: `0x1400aaa3e`
- name: `?VhdmpiIsoInsertMediaThread@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_ASYNC_OP_CONTEXT@@PEAXK@Z`
- size: `926`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _VHD_ASYNC_OP_CONTEXT *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x140019704`
- `0x14001df30`
- `0x140023560`
- `0x14002d7a0`
- `0x14002da18`
- `0x140031b20`
- `0x140035e94`
- `0x14004a384`
- `0x14004a46c`
- `0x14004a524`
- `0x14004a7e0`
- `0x14005d840`
- `0x1400aa6a0`
- `0x1400cff8c`
- `0x1400e98ec`

## string_xrefs

- `0x1400aa7c8`: `VhdmpiIsoInsertMediaThread: invalid request... Flags: 0x%x PendingOperationCount: 0x%x`
- `0x1400aa745`: `VhdmpiIsoInsertMediaThread: invalid request... Input buffer too small: 0x%x.`
- `0x1400aa70e`: `VhdmpiIsoInsertMediaThread`
- `0x1400aa75d`: `VhdmpiIsoInsertMediaThread`
- `0x1400aa7c1`: `VhdmpiIsoInsertMediaThread`
- `0x1400aa87a`: `VhdmpiIsoInsertMediaThread`
- `0x1400aa900`: `VhdmpiIsoInsertMediaThread`
- `0x1400aa96d`: `VhdmpiIsoInsertMediaThread`
- `0x1400aa9e1`: `VhdmpiIsoInsertMediaThread`
- `0x1400aa700`: `VhdmpiIsoInsertMediaThread: entered... VirtualDisk (0x%p)`
- `0x1400aa8e8`: `VhdmpiIsoInsertMediaThread: failed to open new media (0x%08x)`
- `0x1400aa863`: `VhdmpiIsoInsertMediaThread: invalid request packet`
- `0x1400aa811`: `VhdmpiIsoInsertMediaThread:`
- `0x1400aa9ca`: `VhdmpiIsoInsertMediaThread: invalid request... Inserting media on Disk that is not surfaced`
- `0x1400aa955`: `VhdmpiIsoInsertMediaThread: failed to exchange new backing store (0x%08x)`

## pseudocode

```c
__int64 __fastcall VhdmpiIsoInsertMediaThread(
        struct _VHD_HANDLE_CONTEXT *a1,
        struct _VHD_ASYNC_OP_CONTEXT *a2,
        unsigned int *a3,
        unsigned int a4)
{
  __int64 v4; // r14
  struct _VHD_BACKING_STORE_HEADER *v5; // rsi
  unsigned __int8 v9; // r8
  int v10; // edi
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rbp
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-38h] BYREF
  struct _VHD_BACKING_STORE_HEADER *v16; // [rsp+90h] [rbp+8h] BYREF

  v4 = *((_QWORD *)a1 + 7);
  v5 = 0;
  v16 = 0;
  DestinationString = 0;
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    TraceEvents(
      "VhdmpiIsoInsertMediaThread",
      0x11Du,
      v9,
      (unsigned int)a2,
      "VhdmpiIsoInsertMediaThread: entered... VirtualDisk (0x%p)",
      a1);
  if ( a4 < 8 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
      TraceEvents(
        "VhdmpiIsoInsertMediaThread",
        0x129u,
        2u,
        2u,
        "VhdmpiIsoInsertMediaThread: invalid request... Input buffer too small: 0x%x.",
        a4);
    return (unsigned int)-1073741811;
  }
  if ( *(_DWORD *)(v4 + 260) )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
    {
      v11 = VhdmpiVirtualDiskFlagsAsULONG(v4);
      TraceEvents(
        "VhdmpiIsoInsertMediaThread",
        0x135u,
        2u,
        2u,
        "VhdmpiIsoInsertMediaThread: invalid request... Flags: 0x%x PendingOperationCount: 0x%x",
        v11,
        *(_DWORD *)(v4 + 256));
    }
    return (unsigned int)-1073741436;
  }
  v12 = VhdmpiAddRundownRefSurfaceByHandleContext(a1, a2);
  v13 = v12;
  if ( v12 && (*(_DWORD *)(v12 + 56) & 0x200) != 0 )
  {
    VhdmpiHoldAllIoAndWait(v4);
    if ( VhdmpiValidateFileName(
           (__int64)a3,
           8u,
           a4,
           a3[1],
           *a3,
           &DestinationString,
           (char)"VhdmpiIsoInsertMediaThread:") )
    {
      v10 = VhdmpiCreateBackingStoreChain(a1, &IsoParser, &DestinationString, v4, 0, 0, 2, 0, &v16);
      if ( v10 >= 0 )
      {
        v5 = v16;
        v10 = VhdmpiIsoModifyBackingStore(a1, (struct _VHD_VIRTUAL_DISK *)v4, v16);
        if ( v10 >= 0 )
        {
          v5 = 0;
          VhdmpiInsertScsiStateMedia(v13 + 656);
          (*(void (__fastcall **)(_QWORD))(v13 + 1512))(*(_QWORD *)(v13 + 1504));
        }
        else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        {
          TraceEvents(
            "VhdmpiIsoInsertMediaThread",
            0x18Cu,
            2u,
            8u,
            "VhdmpiIsoInsertMediaThread: failed to exchange new backing store (0x%08x)",
            v10);
        }
      }
      else
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
          TraceEvents(
            "VhdmpiIsoInsertMediaThread",
            0x17Du,
            2u,
            8u,
            "VhdmpiIsoInsertMediaThread: failed to open new media (0x%08x)",
            v10);
        v5 = v16;
      }
    }
    else
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        TraceEvents("VhdmpiIsoInsertMediaThread", 0x163u, 2u, 8u, "VhdmpiIsoInsertMediaThread: invalid request packet");
      v10 = -1073741811;
    }
    VhdmpiReleaseAllIo(v4);
  }
  else
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
      TraceEvents(
        "VhdmpiIsoInsertMediaThread",
        0x14Au,
        2u,
        2u,
        "VhdmpiIsoInsertMediaThread: invalid request... Inserting media on Disk that is not surfaced");
    v10 = -1073741436;
    if ( !v13 )
      goto LABEL_37;
  }
  VhdmpiReleaseRundownRefVirtualDiskSurface(v13, 0);
LABEL_37:
  if ( v5 )
  {
    VhdmpiReleaseBackingStoreAccess(a1, v5, 1);
    VhdmpiReleaseBackingStore((char)v5);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400aa6a0  mov     rax, rsp
0x1400aa6a3  mov     [rax+10h], rbx
0x1400aa6a7  mov     [rax+18h], rbp
0x1400aa6ab  push    rsi
0x1400aa6ac  push    rdi
0x1400aa6ad  push    r13
0x1400aa6af  push    r14
0x1400aa6b1  push    r15
0x1400aa6b3  sub     rsp, 60h
0x1400aa6b7  mov     r14, [rcx+38h]
0x1400aa6bb  xor     esi, esi
0x1400aa6bd  xorps   xmm0, xmm0
0x1400aa6c0  mov     [rax+8], rsi
0x1400aa6c4  mov     rbx, r8
0x1400aa6c7  mov     edi, r9d
0x1400aa6ca  movups  xmmword ptr [rax-38h], xmm0
0x1400aa6ce  mov     eax, cs:dword_140087708
0x1400aa6d4  lea     r8d, [rsi+5]
0x1400aa6d8  mov     r15, rcx
0x1400aa6db  cmp     eax, r8d
0x1400aa6de  jbe     short loc_1400AA71A
0x1400aa6e0  lea     edx, [rsi+4]
0x1400aa6e3  lea     rcx, dword_140087708
0x1400aa6ea  call    _tlgKeywordOn
0x1400aa6ef  test    al, al
0x1400aa6f1  jz      short loc_1400AA71A
0x1400aa6f3  mov     ecx, 11Dh
0x1400aa6f8  mov     [rsp+88h+DestinationString], r15; char
0x1400aa6fd  mov     r9d, edx; int
0x1400aa700  lea     rax, aVhdmpiisoinser; "VhdmpiIsoInsertMediaThread: entered... "...
0x1400aa707  mov     edx, ecx; int
0x1400aa709  mov     [rsp+88h+var_68], rax; char *
0x1400aa70e  lea     rcx, aVhdmpiisoinser_0; "VhdmpiIsoInsertMediaThread"
0x1400aa715  call    TraceEvents
0x1400aa71a  mov     r13d, 8
0x1400aa720  cmp     edi, r13d
0x1400aa723  jnb     short loc_1400AA776
0x1400aa725  mov     eax, cs:dword_140087708
0x1400aa72b  lea     ebx, [r13-6]
0x1400aa72f  cmp     eax, ebx
0x1400aa731  jbe     short loc_1400AA76C
0x1400aa733  mov     edx, ebx
0x1400aa735  lea     rcx, dword_140087708
0x1400aa73c  call    _tlgKeywordOn
0x1400aa741  test    al, al
0x1400aa743  jz      short loc_1400AA76C
0x1400aa745  lea     rax, aVhdmpiisoinser_4; "VhdmpiIsoInsertMediaThread: invalid req"...
0x1400aa74c  mov     dword ptr [rsp+88h+DestinationString], edi; char
0x1400aa750  mov     edx, 129h; int
0x1400aa755  mov     [rsp+88h+var_68], rax; char *
0x1400aa75a  mov     r9d, ebx; int
0x1400aa75d  lea     rcx, aVhdmpiisoinser_0; "VhdmpiIsoInsertMediaThread"
0x1400aa764  mov     r8d, ebx; int
0x1400aa767  call    TraceEvents
0x1400aa76c  mov     edi, 0C000000Dh
0x1400aa771  jmp     loc_1400AAA22
0x1400aa776  mov     eax, [r14+104h]
0x1400aa77d  test    eax, eax
0x1400aa77f  jz      short loc_1400AA7E6
0x1400aa781  mov     eax, cs:dword_140087708
0x1400aa787  mov     ebx, 2
0x1400aa78c  cmp     eax, ebx
0x1400aa78e  jbe     short loc_1400AA7DC
0x1400aa790  mov     edx, ebx
0x1400aa792  lea     rcx, dword_140087708
0x1400aa799  call    _tlgKeywordOn
0x1400aa79e  test    al, al
0x1400aa7a0  jz      short loc_1400AA7DC
0x1400aa7a2  mov     rcx, r14
0x1400aa7a5  call    VhdmpiVirtualDiskFlagsAsULONG
0x1400aa7aa  mov     ecx, [r14+100h]
0x1400aa7b1  mov     edx, 135h; int
0x1400aa7b6  mov     dword ptr [rsp+88h+var_58], ecx
0x1400aa7ba  mov     r9d, ebx; int
0x1400aa7bd  mov     dword ptr [rsp+88h+DestinationString], eax; char
0x1400aa7c1  lea     rcx, aVhdmpiisoinser_0; "VhdmpiIsoInsertMediaThread"
0x1400aa7c8  lea     rax, aVhdmpiisoinser_1; "VhdmpiIsoInsertMediaThread: invalid req"...
0x1400aa7cf  mov     r8d, ebx; int
0x1400aa7d2  mov     [rsp+88h+var_68], rax; char *
0x1400aa7d7  call    TraceEvents
0x1400aa7dc  mov     edi, 0C0000184h
0x1400aa7e1  jmp     loc_1400AAA22
0x1400aa7e6  mov     rcx, r15
0x1400aa7e9  call    VhdmpiAddRundownRefSurfaceByHandleContext
0x1400aa7ee  mov     rbp, rax
0x1400aa7f1  test    rax, rax
0x1400aa7f4  jz      loc_1400AA9A9
0x1400aa7fa  test    dword ptr [rax+38h], 200h
0x1400aa801  jz      loc_1400AA9A9
0x1400aa807  mov     rcx, r14
0x1400aa80a  call    VhdmpiHoldAllIoAndWait
0x1400aa80f  mov     ecx, [rbx]
0x1400aa811  lea     rax, aVhdmpiisoinser_5; "VhdmpiIsoInsertMediaThread:"
0x1400aa818  mov     r9d, [rbx+4]; int
0x1400aa81c  mov     r8d, edi; int
0x1400aa81f  mov     qword ptr [rsp+88h+var_58], rax; char
0x1400aa824  mov     edx, r13d; int
0x1400aa827  lea     rax, [rsp+88h+var_38]
0x1400aa82c  mov     [rsp+88h+DestinationString], rax; char
0x1400aa831  mov     dword ptr [rsp+88h+var_68], ecx; int
0x1400aa835  mov     rcx, rbx; int
0x1400aa838  call    VhdmpiValidateFileName
0x1400aa83d  mov     ebx, 2
0x1400aa842  test    al, al
0x1400aa844  jnz     short loc_1400AA890
0x1400aa846  mov     eax, cs:dword_140087708
0x1400aa84c  cmp     eax, ebx
0x1400aa84e  jbe     short loc_1400AA886
0x1400aa850  mov     rdx, r13
0x1400aa853  lea     rcx, dword_140087708
0x1400aa85a  call    _tlgKeywordOn
0x1400aa85f  test    al, al
0x1400aa861  jz      short loc_1400AA886
0x1400aa863  lea     rax, aVhdmpiisoinser_2; "VhdmpiIsoInsertMediaThread: invalid req"...
0x1400aa86a  mov     edx, 163h; int
0x1400aa86f  mov     r9d, r13d; int
0x1400aa872  mov     [rsp+88h+var_68], rax; char *
0x1400aa877  mov     r8d, ebx; int
0x1400aa87a  lea     rcx, aVhdmpiisoinser_0; "VhdmpiIsoInsertMediaThread"
0x1400aa881  call    TraceEvents
0x1400aa886  mov     edi, 0C000000Dh
0x1400aa88b  jmp     loc_1400AA99F
0x1400aa890  lea     rax, [rsp+88h+arg_0]
0x1400aa898  mov     r9, r14
0x1400aa89b  mov     [rsp+88h+var_48], rax
0x1400aa8a0  lea     r8, [rsp+88h+var_38]
0x1400aa8a5  mov     [rsp+88h+var_50], esi
0x1400aa8a9  lea     rdx, IsoParser
0x1400aa8b0  mov     dword ptr [rsp+88h+var_58], ebx
0x1400aa8b4  mov     rcx, r15
0x1400aa8b7  mov     [rsp+88h+DestinationString], rsi
0x1400aa8bc  mov     dword ptr [rsp+88h+var_68], esi
0x1400aa8c0  call    VhdmpiCreateBackingStoreChain
0x1400aa8c5  mov     edi, eax
0x1400aa8c7  test    eax, eax
0x1400aa8c9  jns     short loc_1400AA91C
0x1400aa8cb  mov     ecx, cs:dword_140087708
0x1400aa8d1  cmp     ecx, ebx
0x1400aa8d3  jbe     short loc_1400AA90F
0x1400aa8d5  mov     rdx, r13
0x1400aa8d8  lea     rcx, dword_140087708
0x1400aa8df  call    _tlgKeywordOn
0x1400aa8e4  test    al, al
0x1400aa8e6  jz      short loc_1400AA90F
0x1400aa8e8  lea     rax, aVhdmpiisoinser_3; "VhdmpiIsoInsertMediaThread: failed to o"...
0x1400aa8ef  mov     dword ptr [rsp+88h+DestinationString], edi; char
0x1400aa8f3  mov     edx, 17Dh; int
0x1400aa8f8  mov     [rsp+88h+var_68], rax; char *
0x1400aa8fd  mov     r9d, r13d; int
0x1400aa900  lea     rcx, aVhdmpiisoinser_0; "VhdmpiIsoInsertMediaThread"
0x1400aa907  mov     r8d, ebx; int
0x1400aa90a  call    TraceEvents
0x1400aa90f  mov     rsi, [rsp+88h+arg_0]
0x1400aa917  jmp     loc_1400AA99F
0x1400aa91c  mov     rsi, [rsp+88h+arg_0]
0x1400aa924  mov     rdx, r14; struct _VHD_VIRTUAL_DISK *
0x1400aa927  mov     r8, rsi; struct _VHD_BACKING_STORE_HEADER *
0x1400aa92a  mov     rcx, r15; struct _VHD_HANDLE_CONTEXT *
0x1400aa92d  call    ?VhdmpiIsoModifyBackingStore@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_VIRTUAL_DISK@@PEAU_VHD_BACKING_STORE_HEADER@@@Z; VhdmpiIsoModifyBackingStore(_VHD_HANDLE_CONTEXT *,_VHD_VIRTUAL_DISK *,_VHD_BACKING_STORE_HEADER *)
0x1400aa932  mov     edi, eax
0x1400aa934  test    eax, eax
0x1400aa936  jns     short loc_1400AA97E
0x1400aa938  mov     eax, cs:dword_140087708
0x1400aa93e  cmp     eax, ebx
0x1400aa940  jbe     short loc_1400AA99F
0x1400aa942  mov     rdx, r13
0x1400aa945  lea     rcx, dword_140087708
0x1400aa94c  call    _tlgKeywordOn
0x1400aa951  test    al, al
0x1400aa953  jz      short loc_1400AA99F
0x1400aa955  lea     rax, aVhdmpiisoinser_7; "VhdmpiIsoInsertMediaThread: failed to e"...
0x1400aa95c  mov     dword ptr [rsp+88h+DestinationString], edi; char
0x1400aa960  mov     edx, 18Ch; int
0x1400aa965  mov     [rsp+88h+var_68], rax; char *
0x1400aa96a  mov     r9d, r13d; int
0x1400aa96d  lea     rcx, aVhdmpiisoinser_0; "VhdmpiIsoInsertMediaThread"
0x1400aa974  mov     r8d, ebx; int
0x1400aa977  call    TraceEvents
0x1400aa97c  jmp     short loc_1400AA99F
0x1400aa97e  lea     rcx, [rbp+290h]
0x1400aa985  xor     esi, esi
0x1400aa987  call    VhdmpiInsertScsiStateMedia
0x1400aa98c  mov     rax, [rbp+5E8h]
0x1400aa993  mov     rcx, [rbp+5E0h]
0x1400aa99a  call    _guard_dispatch_icall
0x1400aa99f  mov     rcx, r14
0x1400aa9a2  call    VhdmpiReleaseAllIo
0x1400aa9a7  jmp     short loc_1400AA9F7
0x1400aa9a9  mov     eax, cs:dword_140087708
0x1400aa9af  mov     ebx, 2
0x1400aa9b4  cmp     eax, ebx
0x1400aa9b6  jbe     short loc_1400AA9ED
0x1400aa9b8  mov     edx, ebx
0x1400aa9ba  lea     rcx, dword_140087708
0x1400aa9c1  call    _tlgKeywordOn
0x1400aa9c6  test    al, al
0x1400aa9c8  jz      short loc_1400AA9ED
0x1400aa9ca  lea     rax, aVhdmpiisoinser_6; "VhdmpiIsoInsertMediaThread: invalid req"...
0x1400aa9d1  mov     edx, 14Ah; int
0x1400aa9d6  mov     r9d, ebx; int
0x1400aa9d9  mov     [rsp+88h+var_68], rax; char *
0x1400aa9de  mov     r8d, ebx; int
0x1400aa9e1  lea     rcx, aVhdmpiisoinser_0; "VhdmpiIsoInsertMediaThread"
0x1400aa9e8  call    TraceEvents
0x1400aa9ed  mov     edi, 0C0000184h
0x1400aa9f2  test    rbp, rbp
0x1400aa9f5  jz      short loc_1400AAA01
0x1400aa9f7  xor     edx, edx
0x1400aa9f9  mov     rcx, rbp
0x1400aa9fc  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400aaa01  test    rsi, rsi
0x1400aaa04  jz      short loc_1400AAA22
0x1400aaa06  mov     r8d, 1
0x1400aaa0c  mov     rdx, rsi
0x1400aaa0f  mov     rcx, r15
0x1400aaa12  call    VhdmpiReleaseBackingStoreAccess
0x1400aaa17  mov     rdx, r14
0x1400aaa1a  mov     rcx, rsi; char
0x1400aaa1d  call    VhdmpiReleaseBackingStore
0x1400aaa22  lea     r11, [rsp+88h+var_28]
0x1400aaa27  mov     eax, edi
0x1400aaa29  mov     rbx, [r11+38h]
0x1400aaa2d  mov     rbp, [r11+40h]
0x1400aaa31  mov     rsp, r11
0x1400aaa34  pop     r15
0x1400aaa36  pop     r14
0x1400aaa38  pop     r13
0x1400aaa3a  pop     rdi
0x1400aaa3b  pop     rsi
0x1400aaa3c  retn
```

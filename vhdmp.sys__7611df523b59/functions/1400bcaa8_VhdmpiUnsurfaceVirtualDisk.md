# VhdmpiUnsurfaceVirtualDisk

- ea: `0x1400bcaa8`
- end: `0x1400bcda4`
- name: `VhdmpiUnsurfaceVirtualDisk`
- size: `764`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a1e8`
- `0x140047248`

## callees

- `0x140023560`
- `0x140023ae4`
- `0x1400269cc`
- `0x140034ec0`
- `0x1400358bc`
- `0x140035e94`
- `0x14005d7c0`
- `0x1400bbfc8`
- `0x1400bc15c`
- `0x1400bcaa8`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x1400bcc37`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400bcc37`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400bcc66`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400bcc66`
- `FSDEPENDS!DependentFSCheckStoragePrivilege` at `0x1400bcc53`
- `FSDEPENDS!DependentFSCheckStoragePrivilege` at `0x1400bcc53`

## string_xrefs

- `0x1400bcb62`: `VhdmpiUnsurfaceVirtualDisk: access is denied`
- `0x1400bccb1`: `VhdmpiUnsurfaceVirtualDisk: CheckStoragePrivilege failed for handle %p, returned status 0x%x`

## pseudocode

```c
__int64 __fastcall VhdmpiUnsurfaceVirtualDisk(__int64 a1, __int64 a2, __int64 a3)
{
  struct _VHD_VIRTUAL_DISK *v3; // rbp
  __int64 v5; // rcx
  int v6; // ebx
  struct _VHD_SURFACE *v7; // rdi
  unsigned int v8; // edx
  unsigned int v9; // r9d
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+40h] [rbp-78h] BYREF
  _VIRTUAL_STORAGE_TYPE v12; // [rsp+60h] [rbp-58h] BYREF

  v3 = *(struct _VHD_VIRTUAL_DISK **)(a1 + 56);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  memset(&v12, 0, sizeof(v12));
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents("VhdmpiUnsurfaceVirtualDisk", 0x29Cu, 5u, 0x10u, "VhdmpiUnsurfaceVirtualDisk: enter");
  v5 = *(unsigned int *)(a1 + 4);
  if ( (v5 & 1) != 0 && (*(_DWORD *)(a1 + 8) & 0x40000) == 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents("VhdmpiUnsurfaceVirtualDisk", 0x2A7u, 2u, 0x10u, "VhdmpiUnsurfaceVirtualDisk: access is denied");
    goto LABEL_9;
  }
  if ( (v5 & 0x10) == 0 )
  {
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
      McTemplateK0p_EtwWriteTransfer(v5, VhdUnsurfaceBegin, 0);
    v7 = VhdmpiAddRefCompletedSurfaceByHandleContext((struct _VHD_HANDLE_CONTEXT *)a1, a2, a3);
    if ( v7 )
    {
      if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
        TraceEvents(
          "VhdmpiUnsurfaceVirtualDisk",
          0x2B9u,
          5u,
          0x10u,
          "VhdmpiUnsurfaceVirtualDisk: Unsurfacing surface for virtual disk %p.",
          v3);
      VhdmpiRemoveSurfaceOwnershipFromHandle(a1, v7);
    }
    else
    {
      v7 = VhdmpiFindAndAddRefPermanentSurface(v3, &v12);
      if ( !v7 )
        return (unsigned int)-1073741202;
      SeCaptureSubjectContext(&SubjectContext);
      v6 = DependentFSCheckStoragePrivilege(&SubjectContext, &v12, 0x40000);
      SeReleaseSubjectContext(&SubjectContext);
      if ( v6 < 0 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 64) )
          TraceEvents(
            "VhdmpiUnsurfaceVirtualDisk",
            0x2DDu,
            v8 - 62,
            v8,
            "VhdmpiUnsurfaceVirtualDisk: CheckStoragePrivilege failed for handle %p, returned status 0x%x",
            (const void *)a1,
            v6);
LABEL_29:
        VhdmpiReleaseSurface(v7);
        if ( (int)(v6 + 0x80000000) < 0 || v6 == -1073741202 )
          return (unsigned int)v6;
        goto LABEL_31;
      }
      if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
        TraceEvents(
          "VhdmpiUnsurfaceVirtualDisk",
          0x2E4u,
          5u,
          0x10u,
          "VhdmpiUnsurfaceVirtualDisk: Unsurfacing permanent surface for virtual disk %p.",
          v3);
      VhdmpiHaltSurfaceOrWait(v7);
    }
    v6 = 0;
    goto LABEL_29;
  }
LABEL_9:
  v6 = -1073741790;
LABEL_31:
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
    TraceEvents(
      "VhdmpiUnsurfaceVirtualDisk",
      0x2F2u,
      2u,
      v9,
      "Log status 0x%08X: VhdmpiUnsurfaceVirtualDisk, VirtualDisk = %p",
      v6,
      v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400bcaa8  push    rbx
0x1400bcaaa  push    rbp
0x1400bcaab  push    rsi
0x1400bcaac  push    rdi
0x1400bcaad  push    r13
0x1400bcaaf  push    r14
0x1400bcab1  sub     rsp, 88h
0x1400bcab8  mov     rax, cs:__security_cookie
0x1400bcabf  xor     rax, rsp
0x1400bcac2  mov     [rsp+0B8h+var_40], rax
0x1400bcac7  mov     rbp, [rcx+38h]
0x1400bcacb  lea     r13, dword_140087708
0x1400bcad2  xor     eax, eax
0x1400bcad4  lea     rbx, aVhdmpiunsurfac_1; "VhdmpiUnsurfaceVirtualDisk"
0x1400bcadb  xorps   xmm0, xmm0
0x1400bcade  mov     dword ptr [rsp+0B8h+var_58.VendorId.Data4+4], eax
0x1400bcae2  mov     eax, cs:dword_140087708
0x1400bcae8  xorps   xmm1, xmm1
0x1400bcaeb  mov     rsi, rcx
0x1400bcaee  mov     r14d, 10h
0x1400bcaf4  movups  xmmword ptr [rsp+0B8h+SubjectContext.ClientToken], xmm0
0x1400bcaf9  movups  xmmword ptr [rsp+0B8h+SubjectContext.PrimaryToken], xmm0
0x1400bcafe  movups  xmmword ptr [rsp+0B8h+var_58.DeviceId], xmm1
0x1400bcb03  cmp     eax, 5
0x1400bcb06  jbe     short loc_1400BCB37
0x1400bcb08  mov     edx, r14d
0x1400bcb0b  mov     rcx, r13
0x1400bcb0e  call    _tlgKeywordOn
0x1400bcb13  test    al, al
0x1400bcb15  jz      short loc_1400BCB37
0x1400bcb17  lea     rax, aVhdmpiunsurfac; "VhdmpiUnsurfaceVirtualDisk: enter"
0x1400bcb1e  mov     edx, 29Ch; int
0x1400bcb23  mov     r9d, r14d; int
0x1400bcb26  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcb2b  lea     r8d, [r14-0Bh]; int
0x1400bcb2f  mov     rcx, rbx; int
0x1400bcb32  call    TraceEvents
0x1400bcb37  mov     ecx, [rsi+4]
0x1400bcb3a  test    cl, 1
0x1400bcb3d  jz      short loc_1400BCB8E
0x1400bcb3f  test    dword ptr [rsi+8], 40000h
0x1400bcb46  jnz     short loc_1400BCB8E
0x1400bcb48  mov     eax, cs:dword_140087708
0x1400bcb4e  cmp     eax, 2
0x1400bcb51  jbe     short loc_1400BCB84
0x1400bcb53  mov     rdx, r14
0x1400bcb56  mov     rcx, r13
0x1400bcb59  call    _tlgKeywordOn
0x1400bcb5e  test    al, al
0x1400bcb60  jz      short loc_1400BCB84
0x1400bcb62  lea     rax, aVhdmpiunsurfac_4; "VhdmpiUnsurfaceVirtualDisk: access is d"...
0x1400bcb69  mov     edx, 2A7h; int
0x1400bcb6e  mov     r9d, r14d; int
0x1400bcb71  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcb76  mov     r8d, 2; int
0x1400bcb7c  mov     rcx, rbx; int
0x1400bcb7f  call    TraceEvents
0x1400bcb84  mov     ebx, 0C0000022h
0x1400bcb89  jmp     loc_1400BCD38
0x1400bcb8e  test    r14b, cl
0x1400bcb91  jnz     short loc_1400BCB84
0x1400bcb93  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400bcb9a  jz      short loc_1400BCBB2
0x1400bcb9c  mov     r9, [rbp+0B00h]
0x1400bcba3  lea     rdx, VhdUnsurfaceBegin
0x1400bcbaa  xor     r8d, r8d
0x1400bcbad  call    McTemplateK0p_EtwWriteTransfer
0x1400bcbb2  mov     rcx, rsi; struct _VHD_HANDLE_CONTEXT *
0x1400bcbb5  call    ?VhdmpiAddRefCompletedSurfaceByHandleContext@@YAPEAU_VHD_SURFACE@@PEAU_VHD_HANDLE_CONTEXT@@@Z; VhdmpiAddRefCompletedSurfaceByHandleContext(_VHD_HANDLE_CONTEXT *)
0x1400bcbba  mov     rdi, rax
0x1400bcbbd  test    rax, rax
0x1400bcbc0  jz      short loc_1400BCC13
0x1400bcbc2  mov     ecx, cs:dword_140087708
0x1400bcbc8  cmp     ecx, 5
0x1400bcbcb  jbe     short loc_1400BCC03
0x1400bcbcd  mov     rdx, r14
0x1400bcbd0  mov     rcx, r13
0x1400bcbd3  call    _tlgKeywordOn
0x1400bcbd8  test    al, al
0x1400bcbda  jz      short loc_1400BCC03
0x1400bcbdc  lea     rax, aVhdmpiunsurfac_0; "VhdmpiUnsurfaceVirtualDisk: Unsurfacing"...
0x1400bcbe3  mov     qword ptr [rsp+0B8h+var_90], rbp; char
0x1400bcbe8  mov     edx, 2B9h; int
0x1400bcbed  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcbf2  mov     r9d, r14d; int
0x1400bcbf5  mov     r8d, 5; int
0x1400bcbfb  mov     rcx, rbx; int
0x1400bcbfe  call    TraceEvents
0x1400bcc03  mov     rdx, rdi
0x1400bcc06  mov     rcx, rsi
0x1400bcc09  call    VhdmpiRemoveSurfaceOwnershipFromHandle
0x1400bcc0e  jmp     loc_1400BCD1A
0x1400bcc13  lea     rdx, [rsp+0B8h+var_58]; struct _VIRTUAL_STORAGE_TYPE *
0x1400bcc18  mov     rcx, rbp; struct _VHD_VIRTUAL_DISK *
0x1400bcc1b  call    ?VhdmpiFindAndAddRefPermanentSurface@@YAPEAU_VHD_SURFACE@@PEAU_VHD_VIRTUAL_DISK@@PEAU_VIRTUAL_STORAGE_TYPE@@@Z; VhdmpiFindAndAddRefPermanentSurface(_VHD_VIRTUAL_DISK *,_VIRTUAL_STORAGE_TYPE *)
0x1400bcc20  mov     rdi, rax
0x1400bcc23  test    rax, rax
0x1400bcc26  jnz     short loc_1400BCC32
0x1400bcc28  mov     ebx, 0C000026Eh
0x1400bcc2d  jmp     loc_1400BCD84
0x1400bcc32  lea     rcx, [rsp+0B8h+SubjectContext]; SubjectContext
0x1400bcc37  call    cs:__imp_SeCaptureSubjectContext
0x1400bcc3e  nop     dword ptr [rax+rax+00h]
0x1400bcc43  mov     r8d, 40000h
0x1400bcc49  lea     rdx, [rsp+0B8h+var_58]
0x1400bcc4e  lea     rcx, [rsp+0B8h+SubjectContext]
0x1400bcc53  call    cs:__imp_DependentFSCheckStoragePrivilege
0x1400bcc5a  nop     dword ptr [rax+rax+00h]
0x1400bcc5f  lea     rcx, [rsp+0B8h+SubjectContext]; SubjectContext
0x1400bcc64  mov     ebx, eax
0x1400bcc66  call    cs:__imp_SeReleaseSubjectContext
0x1400bcc6d  nop     dword ptr [rax+rax+00h]
0x1400bcc72  test    ebx, ebx
0x1400bcc74  jns     short loc_1400BCCCB
0x1400bcc76  mov     ecx, cs:dword_140087708
0x1400bcc7c  cmp     ecx, 2
0x1400bcc7f  jbe     loc_1400BCD1C
0x1400bcc85  mov     edx, 40h ; '@'
0x1400bcc8a  mov     rcx, r13
0x1400bcc8d  call    _tlgKeywordOn
0x1400bcc92  test    al, al
0x1400bcc94  jz      loc_1400BCD1C
0x1400bcc9a  mov     ecx, 2DDh
0x1400bcc9f  mov     dword ptr [rsp+0B8h+var_88], ebx
0x1400bcca3  mov     r9d, edx; int
0x1400bcca6  mov     qword ptr [rsp+0B8h+var_90], rsi; char
0x1400bccab  lea     r8d, [rdx-3Eh]; int
0x1400bccaf  mov     edx, ecx; int
0x1400bccb1  lea     rax, aVhdmpiunsurfac_3; "VhdmpiUnsurfaceVirtualDisk: CheckStorag"...
0x1400bccb8  lea     rcx, aVhdmpiunsurfac_1; "VhdmpiUnsurfaceVirtualDisk"
0x1400bccbf  mov     [rsp+0B8h+var_98], rax; char *
0x1400bccc4  call    TraceEvents
0x1400bccc9  jmp     short loc_1400BCD1C
0x1400bcccb  mov     eax, cs:dword_140087708
0x1400bccd1  cmp     eax, 5
0x1400bccd4  jbe     short loc_1400BCD10
0x1400bccd6  mov     rdx, r14
0x1400bccd9  mov     rcx, r13
0x1400bccdc  call    _tlgKeywordOn
0x1400bcce1  test    al, al
0x1400bcce3  jz      short loc_1400BCD10
0x1400bcce5  lea     rax, aVhdmpiunsurfac_2; "VhdmpiUnsurfaceVirtualDisk: Unsurfacing"...
0x1400bccec  mov     qword ptr [rsp+0B8h+var_90], rbp; char
0x1400bccf1  mov     edx, 2E4h; int
0x1400bccf6  mov     [rsp+0B8h+var_98], rax; char *
0x1400bccfb  mov     r9d, r14d; int
0x1400bccfe  lea     rcx, aVhdmpiunsurfac_1; "VhdmpiUnsurfaceVirtualDisk"
0x1400bcd05  mov     r8d, 5; int
0x1400bcd0b  call    TraceEvents
0x1400bcd10  mov     dl, 1
0x1400bcd12  mov     rcx, rdi; struct _VHD_SURFACE *
0x1400bcd15  call    VhdmpiHaltSurfaceOrWait
0x1400bcd1a  xor     ebx, ebx
0x1400bcd1c  mov     rcx, rdi
0x1400bcd1f  call    VhdmpiReleaseSurface
0x1400bcd24  mov     edx, 80000000h
0x1400bcd29  lea     eax, [rbx+rdx]
0x1400bcd2c  test    edx, eax
0x1400bcd2e  jnz     short loc_1400BCD84
0x1400bcd30  cmp     ebx, 0C000026Eh
0x1400bcd36  jz      short loc_1400BCD84
0x1400bcd38  mov     eax, cs:dword_140087708
0x1400bcd3e  cmp     eax, 2
0x1400bcd41  jbe     short loc_1400BCD84
0x1400bcd43  mov     r9d, 80000h
0x1400bcd49  mov     rcx, r13
0x1400bcd4c  mov     edx, r9d
0x1400bcd4f  call    _tlgKeywordOn
0x1400bcd54  test    al, al
0x1400bcd56  jz      short loc_1400BCD84
0x1400bcd58  mov     [rsp+0B8h+var_88], rbp
0x1400bcd5d  lea     rax, aLogStatus0x08x_2; "Log status 0x%08X: VhdmpiUnsurfaceVirtu"...
0x1400bcd64  mov     dword ptr [rsp+0B8h+var_90], ebx; char
0x1400bcd68  lea     rcx, aVhdmpiunsurfac_1; "VhdmpiUnsurfaceVirtualDisk"
0x1400bcd6f  mov     edx, 2F2h; int
0x1400bcd74  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcd79  mov     r8d, 2; int
0x1400bcd7f  call    TraceEvents
0x1400bcd84  mov     eax, ebx
0x1400bcd86  mov     rcx, [rsp+0B8h+var_40]
0x1400bcd8b  xor     rcx, rsp; StackCookie
0x1400bcd8e  call    __security_check_cookie
0x1400bcd93  add     rsp, 88h
0x1400bcd9a  pop     r14
0x1400bcd9c  pop     r13
0x1400bcd9e  pop     rdi
0x1400bcd9f  pop     rsi
0x1400bcda0  pop     rbp
0x1400bcda1  pop     rbx
0x1400bcda2  retn
```

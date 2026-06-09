# VhdmpiUnsurfaceVirtualDisk

- ea: `0x1400bca98`
- end: `0x1400bcd94`
- name: `VhdmpiUnsurfaceVirtualDisk`
- size: `764`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a608`
- `0x140047638`

## callees

- `0x140023980`
- `0x140023f04`
- `0x140026dec`
- `0x1400352b0`
- `0x140035cac`
- `0x140036284`
- `0x14005dbb0`
- `0x1400bbfb8`
- `0x1400bc14c`
- `0x1400bca98`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x1400bcc27`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400bcc27`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400bcc56`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400bcc56`
- `FSDEPENDS!DependentFSCheckStoragePrivilege` at `0x1400bcc43`
- `FSDEPENDS!DependentFSCheckStoragePrivilege` at `0x1400bcc43`

## string_xrefs

- `0x1400bcb52`: `VhdmpiUnsurfaceVirtualDisk: access is denied`
- `0x1400bcca1`: `VhdmpiUnsurfaceVirtualDisk: CheckStoragePrivilege failed for handle %p, returned status 0x%x`

## pseudocode

```c
__int64 __fastcall VhdmpiUnsurfaceVirtualDisk(__int64 a1)
{
  struct _VHD_VIRTUAL_DISK *v1; // rbp
  __int64 v3; // rcx
  int v4; // ebx
  struct _VHD_SURFACE *v5; // rdi
  unsigned int v6; // edx
  unsigned int v7; // r9d
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+40h] [rbp-78h] BYREF
  _VIRTUAL_STORAGE_TYPE v10; // [rsp+60h] [rbp-58h] BYREF

  v1 = *(struct _VHD_VIRTUAL_DISK **)(a1 + 56);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  memset(&v10, 0, sizeof(v10));
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents("VhdmpiUnsurfaceVirtualDisk", 0x29Cu, 5u, 0x10u, "VhdmpiUnsurfaceVirtualDisk: enter");
  v3 = *(unsigned int *)(a1 + 4);
  if ( (v3 & 1) != 0 && (*(_DWORD *)(a1 + 8) & 0x40000) == 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents("VhdmpiUnsurfaceVirtualDisk", 0x2A7u, 2u, 0x10u, "VhdmpiUnsurfaceVirtualDisk: access is denied");
    goto LABEL_9;
  }
  if ( (v3 & 0x10) == 0 )
  {
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
      McTemplateK0p_EtwWriteTransfer(v3, VhdUnsurfaceBegin, 0, *((_QWORD *)v1 + 352));
    v5 = VhdmpiAddRefCompletedSurfaceByHandleContext((struct _VHD_HANDLE_CONTEXT *)a1);
    if ( v5 )
    {
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
        TraceEvents(
          "VhdmpiUnsurfaceVirtualDisk",
          0x2B9u,
          5u,
          0x10u,
          "VhdmpiUnsurfaceVirtualDisk: Unsurfacing surface for virtual disk %p.",
          v1);
      VhdmpiRemoveSurfaceOwnershipFromHandle(a1, v5);
    }
    else
    {
      v5 = VhdmpiFindAndAddRefPermanentSurface(v1, &v10);
      if ( !v5 )
        return (unsigned int)-1073741202;
      SeCaptureSubjectContext(&SubjectContext);
      v4 = DependentFSCheckStoragePrivilege(&SubjectContext, &v10, 0x40000);
      SeReleaseSubjectContext(&SubjectContext);
      if ( v4 < 0 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 64) )
          TraceEvents(
            "VhdmpiUnsurfaceVirtualDisk",
            0x2DDu,
            v6 - 62,
            v6,
            "VhdmpiUnsurfaceVirtualDisk: CheckStoragePrivilege failed for handle %p, returned status 0x%x",
            (const void *)a1,
            v4);
LABEL_29:
        VhdmpiReleaseSurface(v5);
        if ( (int)(v4 + 0x80000000) < 0 || v4 == -1073741202 )
          return (unsigned int)v4;
        goto LABEL_31;
      }
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
        TraceEvents(
          "VhdmpiUnsurfaceVirtualDisk",
          0x2E4u,
          5u,
          0x10u,
          "VhdmpiUnsurfaceVirtualDisk: Unsurfacing permanent surface for virtual disk %p.",
          v1);
      VhdmpiHaltSurfaceOrWait(v5);
    }
    v4 = 0;
    goto LABEL_29;
  }
LABEL_9:
  v4 = -1073741790;
LABEL_31:
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
    TraceEvents(
      "VhdmpiUnsurfaceVirtualDisk",
      0x2F2u,
      2u,
      v7,
      "Log status 0x%08X: VhdmpiUnsurfaceVirtualDisk, VirtualDisk = %p",
      v4,
      v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400bca98  push    rbx
0x1400bca9a  push    rbp
0x1400bca9b  push    rsi
0x1400bca9c  push    rdi
0x1400bca9d  push    r13
0x1400bca9f  push    r14
0x1400bcaa1  sub     rsp, 88h
0x1400bcaa8  mov     rax, cs:__security_cookie
0x1400bcaaf  xor     rax, rsp
0x1400bcab2  mov     [rsp+0B8h+var_40], rax
0x1400bcab7  mov     rbp, [rcx+38h]
0x1400bcabb  lea     r13, dword_1400876D0
0x1400bcac2  xor     eax, eax
0x1400bcac4  lea     rbx, aVhdmpiunsurfac_1; "VhdmpiUnsurfaceVirtualDisk"
0x1400bcacb  xorps   xmm0, xmm0
0x1400bcace  mov     dword ptr [rsp+0B8h+var_58.VendorId.Data4+4], eax
0x1400bcad2  mov     eax, cs:dword_1400876D0
0x1400bcad8  xorps   xmm1, xmm1
0x1400bcadb  mov     rsi, rcx
0x1400bcade  mov     r14d, 10h
0x1400bcae4  movups  xmmword ptr [rsp+0B8h+SubjectContext.ClientToken], xmm0
0x1400bcae9  movups  xmmword ptr [rsp+0B8h+SubjectContext.PrimaryToken], xmm0
0x1400bcaee  movups  xmmword ptr [rsp+0B8h+var_58.DeviceId], xmm1
0x1400bcaf3  cmp     eax, 5
0x1400bcaf6  jbe     short loc_1400BCB27
0x1400bcaf8  mov     edx, r14d
0x1400bcafb  mov     rcx, r13
0x1400bcafe  call    _tlgKeywordOn
0x1400bcb03  test    al, al
0x1400bcb05  jz      short loc_1400BCB27
0x1400bcb07  lea     rax, aVhdmpiunsurfac; "VhdmpiUnsurfaceVirtualDisk: enter"
0x1400bcb0e  mov     edx, 29Ch; int
0x1400bcb13  mov     r9d, r14d; int
0x1400bcb16  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcb1b  lea     r8d, [r14-0Bh]; int
0x1400bcb1f  mov     rcx, rbx; int
0x1400bcb22  call    TraceEvents
0x1400bcb27  mov     ecx, [rsi+4]
0x1400bcb2a  test    cl, 1
0x1400bcb2d  jz      short loc_1400BCB7E
0x1400bcb2f  test    dword ptr [rsi+8], 40000h
0x1400bcb36  jnz     short loc_1400BCB7E
0x1400bcb38  mov     eax, cs:dword_1400876D0
0x1400bcb3e  cmp     eax, 2
0x1400bcb41  jbe     short loc_1400BCB74
0x1400bcb43  mov     rdx, r14
0x1400bcb46  mov     rcx, r13
0x1400bcb49  call    _tlgKeywordOn
0x1400bcb4e  test    al, al
0x1400bcb50  jz      short loc_1400BCB74
0x1400bcb52  lea     rax, aVhdmpiunsurfac_4; "VhdmpiUnsurfaceVirtualDisk: access is d"...
0x1400bcb59  mov     edx, 2A7h; int
0x1400bcb5e  mov     r9d, r14d; int
0x1400bcb61  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcb66  mov     r8d, 2; int
0x1400bcb6c  mov     rcx, rbx; int
0x1400bcb6f  call    TraceEvents
0x1400bcb74  mov     ebx, 0C0000022h
0x1400bcb79  jmp     loc_1400BCD28
0x1400bcb7e  test    r14b, cl
0x1400bcb81  jnz     short loc_1400BCB74
0x1400bcb83  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400bcb8a  jz      short loc_1400BCBA2
0x1400bcb8c  mov     r9, [rbp+0B00h]
0x1400bcb93  lea     rdx, VhdUnsurfaceBegin
0x1400bcb9a  xor     r8d, r8d
0x1400bcb9d  call    McTemplateK0p_EtwWriteTransfer
0x1400bcba2  mov     rcx, rsi; struct _VHD_HANDLE_CONTEXT *
0x1400bcba5  call    ?VhdmpiAddRefCompletedSurfaceByHandleContext@@YAPEAU_VHD_SURFACE@@PEAU_VHD_HANDLE_CONTEXT@@@Z; VhdmpiAddRefCompletedSurfaceByHandleContext(_VHD_HANDLE_CONTEXT *)
0x1400bcbaa  mov     rdi, rax
0x1400bcbad  test    rax, rax
0x1400bcbb0  jz      short loc_1400BCC03
0x1400bcbb2  mov     ecx, cs:dword_1400876D0
0x1400bcbb8  cmp     ecx, 5
0x1400bcbbb  jbe     short loc_1400BCBF3
0x1400bcbbd  mov     rdx, r14
0x1400bcbc0  mov     rcx, r13
0x1400bcbc3  call    _tlgKeywordOn
0x1400bcbc8  test    al, al
0x1400bcbca  jz      short loc_1400BCBF3
0x1400bcbcc  lea     rax, aVhdmpiunsurfac_0; "VhdmpiUnsurfaceVirtualDisk: Unsurfacing"...
0x1400bcbd3  mov     qword ptr [rsp+0B8h+var_90], rbp; char
0x1400bcbd8  mov     edx, 2B9h; int
0x1400bcbdd  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcbe2  mov     r9d, r14d; int
0x1400bcbe5  mov     r8d, 5; int
0x1400bcbeb  mov     rcx, rbx; int
0x1400bcbee  call    TraceEvents
0x1400bcbf3  mov     rdx, rdi
0x1400bcbf6  mov     rcx, rsi
0x1400bcbf9  call    VhdmpiRemoveSurfaceOwnershipFromHandle
0x1400bcbfe  jmp     loc_1400BCD0A
0x1400bcc03  lea     rdx, [rsp+0B8h+var_58]; struct _VIRTUAL_STORAGE_TYPE *
0x1400bcc08  mov     rcx, rbp; struct _VHD_VIRTUAL_DISK *
0x1400bcc0b  call    ?VhdmpiFindAndAddRefPermanentSurface@@YAPEAU_VHD_SURFACE@@PEAU_VHD_VIRTUAL_DISK@@PEAU_VIRTUAL_STORAGE_TYPE@@@Z; VhdmpiFindAndAddRefPermanentSurface(_VHD_VIRTUAL_DISK *,_VIRTUAL_STORAGE_TYPE *)
0x1400bcc10  mov     rdi, rax
0x1400bcc13  test    rax, rax
0x1400bcc16  jnz     short loc_1400BCC22
0x1400bcc18  mov     ebx, 0C000026Eh
0x1400bcc1d  jmp     loc_1400BCD74
0x1400bcc22  lea     rcx, [rsp+0B8h+SubjectContext]; SubjectContext
0x1400bcc27  call    cs:__imp_SeCaptureSubjectContext
0x1400bcc2e  nop     dword ptr [rax+rax+00h]
0x1400bcc33  mov     r8d, 40000h
0x1400bcc39  lea     rdx, [rsp+0B8h+var_58]
0x1400bcc3e  lea     rcx, [rsp+0B8h+SubjectContext]
0x1400bcc43  call    cs:__imp_DependentFSCheckStoragePrivilege
0x1400bcc4a  nop     dword ptr [rax+rax+00h]
0x1400bcc4f  lea     rcx, [rsp+0B8h+SubjectContext]; SubjectContext
0x1400bcc54  mov     ebx, eax
0x1400bcc56  call    cs:__imp_SeReleaseSubjectContext
0x1400bcc5d  nop     dword ptr [rax+rax+00h]
0x1400bcc62  test    ebx, ebx
0x1400bcc64  jns     short loc_1400BCCBB
0x1400bcc66  mov     ecx, cs:dword_1400876D0
0x1400bcc6c  cmp     ecx, 2
0x1400bcc6f  jbe     loc_1400BCD0C
0x1400bcc75  mov     edx, 40h ; '@'
0x1400bcc7a  mov     rcx, r13
0x1400bcc7d  call    _tlgKeywordOn
0x1400bcc82  test    al, al
0x1400bcc84  jz      loc_1400BCD0C
0x1400bcc8a  mov     ecx, 2DDh
0x1400bcc8f  mov     dword ptr [rsp+0B8h+var_88], ebx
0x1400bcc93  mov     r9d, edx; int
0x1400bcc96  mov     qword ptr [rsp+0B8h+var_90], rsi; char
0x1400bcc9b  lea     r8d, [rdx-3Eh]; int
0x1400bcc9f  mov     edx, ecx; int
0x1400bcca1  lea     rax, aVhdmpiunsurfac_3; "VhdmpiUnsurfaceVirtualDisk: CheckStorag"...
0x1400bcca8  lea     rcx, aVhdmpiunsurfac_1; "VhdmpiUnsurfaceVirtualDisk"
0x1400bccaf  mov     [rsp+0B8h+var_98], rax; char *
0x1400bccb4  call    TraceEvents
0x1400bccb9  jmp     short loc_1400BCD0C
0x1400bccbb  mov     eax, cs:dword_1400876D0
0x1400bccc1  cmp     eax, 5
0x1400bccc4  jbe     short loc_1400BCD00
0x1400bccc6  mov     rdx, r14
0x1400bccc9  mov     rcx, r13
0x1400bcccc  call    _tlgKeywordOn
0x1400bccd1  test    al, al
0x1400bccd3  jz      short loc_1400BCD00
0x1400bccd5  lea     rax, aVhdmpiunsurfac_2; "VhdmpiUnsurfaceVirtualDisk: Unsurfacing"...
0x1400bccdc  mov     qword ptr [rsp+0B8h+var_90], rbp; char
0x1400bcce1  mov     edx, 2E4h; int
0x1400bcce6  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcceb  mov     r9d, r14d; int
0x1400bccee  lea     rcx, aVhdmpiunsurfac_1; "VhdmpiUnsurfaceVirtualDisk"
0x1400bccf5  mov     r8d, 5; int
0x1400bccfb  call    TraceEvents
0x1400bcd00  mov     dl, 1
0x1400bcd02  mov     rcx, rdi; struct _VHD_SURFACE *
0x1400bcd05  call    VhdmpiHaltSurfaceOrWait
0x1400bcd0a  xor     ebx, ebx
0x1400bcd0c  mov     rcx, rdi
0x1400bcd0f  call    VhdmpiReleaseSurface
0x1400bcd14  mov     edx, 80000000h
0x1400bcd19  lea     eax, [rbx+rdx]
0x1400bcd1c  test    edx, eax
0x1400bcd1e  jnz     short loc_1400BCD74
0x1400bcd20  cmp     ebx, 0C000026Eh
0x1400bcd26  jz      short loc_1400BCD74
0x1400bcd28  mov     eax, cs:dword_1400876D0
0x1400bcd2e  cmp     eax, 2
0x1400bcd31  jbe     short loc_1400BCD74
0x1400bcd33  mov     r9d, 80000h
0x1400bcd39  mov     rcx, r13
0x1400bcd3c  mov     edx, r9d
0x1400bcd3f  call    _tlgKeywordOn
0x1400bcd44  test    al, al
0x1400bcd46  jz      short loc_1400BCD74
0x1400bcd48  mov     [rsp+0B8h+var_88], rbp
0x1400bcd4d  lea     rax, aLogStatus0x08x_2; "Log status 0x%08X: VhdmpiUnsurfaceVirtu"...
0x1400bcd54  mov     dword ptr [rsp+0B8h+var_90], ebx; char
0x1400bcd58  lea     rcx, aVhdmpiunsurfac_1; "VhdmpiUnsurfaceVirtualDisk"
0x1400bcd5f  mov     edx, 2F2h; int
0x1400bcd64  mov     [rsp+0B8h+var_98], rax; char *
0x1400bcd69  mov     r8d, 2; int
0x1400bcd6f  call    TraceEvents
0x1400bcd74  mov     eax, ebx
0x1400bcd76  mov     rcx, [rsp+0B8h+var_40]
0x1400bcd7b  xor     rcx, rsp; StackCookie
0x1400bcd7e  call    __security_check_cookie
0x1400bcd83  add     rsp, 88h
0x1400bcd8a  pop     r14
0x1400bcd8c  pop     r13
0x1400bcd8e  pop     rdi
0x1400bcd8f  pop     rsi
0x1400bcd90  pop     rbp
0x1400bcd91  pop     rbx
0x1400bcd92  retn
```

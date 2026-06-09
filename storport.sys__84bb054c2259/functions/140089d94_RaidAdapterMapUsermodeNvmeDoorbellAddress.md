# RaidAdapterMapUsermodeNvmeDoorbellAddress

- ea: `0x140089d94`
- end: `0x14008a0e9`
- name: `RaidAdapterMapUsermodeNvmeDoorbellAddress`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140006f50`

## callees

- `0x140070710`
- `0x1400864ec`
- `0x140089d94`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140089f05`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140089f05`
- `ntoskrnl!ZwMapViewOfSection` at `0x140089ff1`
- `ntoskrnl!ZwMapViewOfSection` at `0x140089ff1`
- `ntoskrnl!ZwClose` at `0x14008a0ae`
- `ntoskrnl!ZwClose` at `0x14008a0c3`
- `ntoskrnl!ZwClose` at `0x14008a0ae`
- `ntoskrnl!ZwClose` at `0x14008a0c3`
- `ntoskrnl!ZwOpenProcess` at `0x140089f5d`
- `ntoskrnl!ZwOpenProcess` at `0x140089f5d`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140089eef`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140089eef`
- `ntoskrnl!ZwOpenSection` at `0x140089e90`
- `ntoskrnl!ZwOpenSection` at `0x140089e90`

## pseudocode

```c
__int64 __fastcall RaidAdapterMapUsermodeNvmeDoorbellAddress(__int64 a1, IRP *a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r8
  unsigned __int16 v8; // r9
  unsigned int v9; // eax
  unsigned __int64 v10; // r8
  unsigned __int16 v11; // dx
  unsigned __int64 v13; // rax
  NTSTATUS v14; // ebx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  ULONG RequestorProcessId; // eax
  void *v18; // rbx
  __int64 v19; // rdx
  int v20; // edx
  int v21; // r8d
  PVOID v22; // rdx
  unsigned __int16 i; // cx
  __int64 v24; // rax
  int CommitSize; // [rsp+20h] [rbp-89h]
  int SectionOffset; // [rsp+28h] [rbp-81h]
  int ViewSize; // [rsp+30h] [rbp-79h]
  SECTION_INHERIT InheritDisposition; // [rsp+38h] [rbp-71h]
  union _LARGE_INTEGER v30; // [rsp+80h] [rbp-29h] BYREF
  ULONG_PTR v31; // [rsp+88h] [rbp-21h] BYREF
  _QWORD v32[2]; // [rsp+90h] [rbp-19h] BYREF
  _CLIENT_ID ClientId; // [rsp+A0h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp+7h] BYREF
  void *ProcessHandle; // [rsp+110h] [rbp+67h] BYREF
  PVOID BaseAddress; // [rsp+120h] [rbp+77h] BYREF
  void *SectionHandle; // [rsp+128h] [rbp+7Fh] BYREF

  SectionHandle = 0;
  v5 = *(_QWORD *)(a4 + 24);
  v32[1] = L"\\Device\\PhysicalMemory";
  v8 = *(_WORD *)(a3 + 44);
  v9 = (*(_DWORD *)(a1 + 4816) & 0xFFFFC000) + 4096;
  ProcessHandle = 0;
  v30.LowPart = v9;
  v10 = v5 + 4;
  v11 = 0;
  v30.HighPart = *(_DWORD *)(a1 + 4820);
  BaseAddress = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v32[0] = 3014700;
  for ( ClientId = 0; v11 < v8; ++v11 )
  {
    v13 = (unsigned __int64)v11 << 6;
    if ( v10 < *(_QWORD *)(v13 + a4 + 72) + 4LL )
      v10 = *(_QWORD *)(v13 + a4 + 72) + 4LL;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  v31 = (v10 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v32;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v14 = ZwOpenSection(&SectionHandle, 6u, &ObjectAttributes);
  if ( v14 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v16 = 32;
LABEL_10:
      WPP_SF_d(v15->AttachedDevice, v16, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids, (unsigned int)v14);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  RequestorProcessId = IoGetRequestorProcessId(a2);
  v18 = (void *)RequestorProcessId;
  if ( !RequestorProcessId || (HANDLE)RequestorProcessId == PsGetCurrentProcessId() )
  {
    v19 = -1;
    ProcessHandle = (void *)-1LL;
LABEL_20:
    v14 = ZwMapViewOfSection(SectionHandle, (HANDLE)v19, &BaseAddress, 0, 0, &v30, &v31, ViewUnmap, 0, 4u);
    if ( v14 >= 0 )
    {
      if ( (byte_140177433 & 0x40) != 0 )
        McTemplateK0quuujjzssszpq_EtwWriteTransfer(
          a1 + 5128,
          v20,
          v21,
          *(_DWORD *)(a1 + 56),
          CommitSize,
          SectionOffset,
          ViewSize,
          InheritDisposition,
          a1 + 5128,
          *(_QWORD *)(a1 + 4784));
      v22 = BaseAddress;
      for ( i = 0; i < *(_WORD *)(a3 + 44); *(_QWORD *)((v24 << 6) + a4 + 72) += v22 )
        v24 = i++;
      *(_QWORD *)(a4 + 24) += v22;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v16 = 34;
        goto LABEL_10;
      }
    }
    goto LABEL_30;
  }
  ClientId.UniqueThread = 0;
  ClientId.UniqueProcess = v18;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.ObjectName = 0;
  v14 = ZwOpenProcess(&ProcessHandle, 0x1FFFFFu, &ObjectAttributes, &ClientId);
  if ( v14 >= 0 )
  {
    v19 = (__int64)ProcessHandle;
    goto LABEL_20;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v16 = 33;
    goto LABEL_10;
  }
LABEL_30:
  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    ZwClose(ProcessHandle);
  if ( SectionHandle )
    ZwClose(SectionHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140089d94  mov     [rsp-8+arg_8], rbx
0x140089d99  push    rbp
0x140089d9a  push    rsi
0x140089d9b  push    rdi
0x140089d9c  push    r14
0x140089d9e  push    r15
0x140089da0  lea     rbp, [rsp-37h]
0x140089da5  sub     rsp, 0E0h
0x140089dac  mov     r14, r8
0x140089daf  mov     [rbp+57h+SectionHandle], 0
0x140089db7  mov     r8, [r9+18h]
0x140089dbb  lea     rax, aDevicePhysical; "\\Device\\PhysicalMemory"
0x140089dc2  mov     [rbp+57h+var_68], rax
0x140089dc6  mov     rdi, r9
0x140089dc9  mov     eax, [rcx+12D0h]
0x140089dcf  mov     r15, rdx
0x140089dd2  movzx   r9d, word ptr [r14+2Ch]
0x140089dd7  and     eax, 0FFFFC000h
0x140089ddc  add     eax, 1000h
0x140089de1  mov     [rbp+57h+ProcessHandle], 0
0x140089de9  mov     dword ptr [rbp+57h+var_80], eax
0x140089dec  add     r8, 4
0x140089df0  mov     eax, [rcx+12D4h]
0x140089df6  xor     edx, edx
0x140089df8  mov     dword ptr [rbp+57h+var_80+4], eax
0x140089dfb  xorps   xmm0, xmm0
0x140089dfe  xor     eax, eax
0x140089e00  mov     [rbp+57h+BaseAddress], 0
0x140089e08  mov     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x140089e0f  mov     rsi, rcx
0x140089e12  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x140089e19  mov     [rbp+57h+var_70], 2E002Ch
0x140089e21  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x140089e25  cmp     ax, r9w
0x140089e29  jnb     short loc_140089E4C
0x140089e2b  movzx   eax, dx
0x140089e2e  shl     rax, 6
0x140089e32  mov     rcx, [rax+rdi+48h]
0x140089e37  add     rcx, 4
0x140089e3b  cmp     r8, rcx
0x140089e3e  jnb     short loc_140089E43
0x140089e40  mov     r8, rcx
0x140089e43  inc     dx
0x140089e46  cmp     dx, r9w
0x140089e4a  jb      short loc_140089E2B
0x140089e4c  lea     rax, [r8+0FFFh]
0x140089e53  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140089e5a  and     rax, 0FFFFFFFFFFFFF000h
0x140089e60  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140089e68  mov     [rbp+57h+var_78], rax
0x140089e6c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140089e70  lea     rax, [rbp+57h+var_70]
0x140089e74  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140089e7b  xorps   xmm0, xmm0
0x140089e7e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140089e82  mov     edx, 6; DesiredAccess
0x140089e87  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x140089e8b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140089e90  call    cs:__imp_ZwOpenSection
0x140089e97  nop     dword ptr [rax+rax+00h]
0x140089e9c  mov     ebx, eax
0x140089e9e  test    eax, eax
0x140089ea0  jns     short loc_140089EEC
0x140089ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x140089ea9  lea     rax, WPP_GLOBAL_Control
0x140089eb0  cmp     rcx, rax
0x140089eb3  jz      loc_14008A0A0
0x140089eb9  mov     edx, [rcx+2Ch]
0x140089ebc  test    dl, 1
0x140089ebf  jz      loc_14008A0A0
0x140089ec5  cmp     byte ptr [rcx+29h], 2
0x140089ec9  jb      loc_14008A0A0
0x140089ecf  mov     edx, 20h ; ' '
0x140089ed4  mov     rcx, [rcx+18h]
0x140089ed8  lea     r8, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids
0x140089edf  mov     r9d, ebx
0x140089ee2  call    WPP_SF_d
0x140089ee7  jmp     loc_14008A0A0
0x140089eec  mov     rcx, r15; Irp
0x140089eef  call    cs:__imp_IoGetRequestorProcessId
0x140089ef6  nop     dword ptr [rax+rax+00h]
0x140089efb  mov     ebx, eax
0x140089efd  test    eax, eax
0x140089eff  jz      loc_140089FAB
0x140089f05  call    cs:__imp_PsGetCurrentProcessId
0x140089f0c  nop     dword ptr [rax+rax+00h]
0x140089f11  cmp     rbx, rax
0x140089f14  jz      loc_140089FAB
0x140089f1a  xorps   xmm0, xmm0
0x140089f1d  mov     [rbp+57h+ClientId.UniqueThread], 0
0x140089f25  lea     r9, [rbp+57h+ClientId]; ClientId
0x140089f29  mov     [rbp+57h+ClientId.UniqueProcess], rbx
0x140089f2d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140089f31  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140089f38  mov     edx, 1FFFFFh; DesiredAccess
0x140089f3d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140089f45  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140089f49  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140089f50  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140089f55  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140089f5d  call    cs:__imp_ZwOpenProcess
0x140089f64  nop     dword ptr [rax+rax+00h]
0x140089f69  mov     ebx, eax
0x140089f6b  test    eax, eax
0x140089f6d  jns     short loc_140089FA5
0x140089f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140089f76  lea     rax, WPP_GLOBAL_Control
0x140089f7d  cmp     rcx, rax
0x140089f80  jz      loc_14008A0A0
0x140089f86  mov     eax, [rcx+2Ch]
0x140089f89  test    al, 1
0x140089f8b  jz      loc_14008A0A0
0x140089f91  cmp     byte ptr [rcx+29h], 2
0x140089f95  jb      loc_14008A0A0
0x140089f9b  mov     edx, 21h ; '!'
0x140089fa0  jmp     loc_140089ED4
0x140089fa5  mov     rdx, [rbp+57h+ProcessHandle]
0x140089fa9  jmp     short loc_140089FB3
0x140089fab  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140089faf  mov     [rbp+57h+ProcessHandle], rdx
0x140089fb3  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x140089fb7  lea     rax, [rbp+57h+var_78]
0x140089fbb  mov     [rsp+100h+Win32Protect], 4; Win32Protect
0x140089fc3  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x140089fc7  mov     [rsp+100h+AllocationType], 0; AllocationType
0x140089fcf  xor     r9d, r9d; ZeroBits
0x140089fd2  mov     [rsp+100h+InheritDisposition], 2; InheritDisposition
0x140089fda  mov     [rsp+100h+ViewSize], rax; ViewSize
0x140089fdf  lea     rax, [rbp+57h+var_80]
0x140089fe3  mov     [rsp+100h+SectionOffset], rax; SectionOffset
0x140089fe8  mov     [rsp+100h+CommitSize], 0; CommitSize
0x140089ff1  call    cs:__imp_ZwMapViewOfSection
0x140089ff8  nop     dword ptr [rax+rax+00h]
0x140089ffd  mov     ebx, eax
0x140089fff  test    eax, eax
0x14008a001  jns     short loc_14008A031
0x14008a003  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a00a  lea     rax, WPP_GLOBAL_Control
0x14008a011  cmp     rcx, rax
0x14008a014  jz      loc_14008A0A0
0x14008a01a  mov     eax, [rcx+2Ch]
0x14008a01d  test    al, 1
0x14008a01f  jz      short loc_14008A0A0
0x14008a021  cmp     byte ptr [rcx+29h], 2
0x14008a025  jb      short loc_14008A0A0
0x14008a027  mov     edx, 22h ; '"'
0x14008a02c  jmp     loc_140089ED4
0x14008a031  test    cs:byte_140177433, 40h
0x14008a038  jz      short loc_14008A077
0x14008a03a  mov     eax, dword ptr [rbp+57h+var_78]
0x14008a03d  lea     rcx, [rsi+1408h]
0x14008a044  mov     r9d, [rsi+38h]
0x14008a048  mov     [rsp+100h+var_88], eax
0x14008a04c  mov     rax, [rbp+57h+BaseAddress]
0x14008a050  mov     [rsp+100h+var_90], rax
0x14008a055  mov     rax, [rsi+1418h]
0x14008a05c  mov     [rsp+100h+var_98], rax
0x14008a061  mov     rax, [rsi+12B0h]
0x14008a068  mov     qword ptr [rsp+100h+Win32Protect], rax
0x14008a06d  mov     qword ptr [rsp+100h+AllocationType], rcx
0x14008a072  call    McTemplateK0quuujjzssszpq_EtwWriteTransfer
0x14008a077  mov     rdx, [rbp+57h+BaseAddress]
0x14008a07b  xor     ecx, ecx
0x14008a07d  xor     eax, eax
0x14008a07f  cmp     ax, [r14+2Ch]
0x14008a084  jnb     short loc_14008A09C
0x14008a086  movzx   eax, cx
0x14008a089  inc     cx
0x14008a08c  shl     rax, 6
0x14008a090  add     [rax+rdi+48h], rdx
0x14008a095  cmp     cx, [r14+2Ch]
0x14008a09a  jb      short loc_14008A086
0x14008a09c  add     [rdi+18h], rdx
0x14008a0a0  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14008a0a4  lea     rax, [rcx-1]
0x14008a0a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14008a0ac  ja      short loc_14008A0BA
0x14008a0ae  call    cs:__imp_ZwClose
0x14008a0b5  nop     dword ptr [rax+rax+00h]
0x14008a0ba  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x14008a0be  test    rcx, rcx
0x14008a0c1  jz      short loc_14008A0CF
0x14008a0c3  call    cs:__imp_ZwClose
0x14008a0ca  nop     dword ptr [rax+rax+00h]
0x14008a0cf  mov     eax, ebx
0x14008a0d1  mov     rbx, [rsp+100h+arg_8]
0x14008a0d9  add     rsp, 0E0h
0x14008a0e0  pop     r15
0x14008a0e2  pop     r14
0x14008a0e4  pop     rdi
0x14008a0e5  pop     rsi
0x14008a0e6  pop     rbp
0x14008a0e7  retn
```

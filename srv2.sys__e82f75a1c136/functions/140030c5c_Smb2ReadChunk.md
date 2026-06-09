# Smb2ReadChunk

- ea: `0x140030c5c`
- end: `0x140031025`
- name: `Smb2ReadChunk`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14005a50c`

## callees

- `0x140005070`
- `0x1400125d0`
- `0x1400222ec`
- `0x140022690`
- `0x140022958`
- `0x140030bdc`
- `0x140030c5c`
- `0x1400384d0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140030d2a`
- `ntoskrnl!IoBuildPartialMdl` at `0x140030d2a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140030e53`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140030e53`
- `ntoskrnl!IofCallDriver` at `0x140030fa0`
- `ntoskrnl!IofCallDriver` at `0x140030fa0`
- `ntoskrnl!MmUnmapLockedPages` at `0x140030d05`
- `ntoskrnl!MmUnmapLockedPages` at `0x140030d05`

## string_xrefs

- `0x140030f80`: `Smb2ReadChunk`

## pseudocode

```c
__int64 __fastcall Smb2ReadChunk(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rax
  __int64 v4; // r12
  __int64 v5; // r14
  unsigned __int8 (__fastcall *v6)(struct _FILE_OBJECT *, __int64, _QWORD, _QWORD); // r13
  _QWORD *v7; // rax
  ULONG v8; // esi
  __int64 v9; // rdi
  void *v10; // rcx
  struct _FILE_OBJECT *v11; // r10
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // ebx
  __int64 result; // rax
  int v16; // edi
  int v17; // esi
  unsigned int RelatedDeviceObject; // eax
  int v19; // r9d
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-88h]
  int v22; // [rsp+20h] [rbp-88h]
  void *v23; // [rsp+B0h] [rbp+8h]
  struct _FILE_OBJECT *v24; // [rsp+B0h] [rbp+8h]
  struct _DEVICE_OBJECT *DeviceObject; // [rsp+B8h] [rbp+10h]
  struct _MDL *SourceMdl; // [rsp+C0h] [rbp+18h]
  PMDL SourceMdla; // [rsp+C0h] [rbp+18h]
  __int64 v28; // [rsp+C8h] [rbp+20h]

  v1 = *(_QWORD *)(a1 + 560);
  v3 = *(_QWORD *)(v1 + 352);
  *(_DWORD *)(v1 + 408) = 1;
  if ( v3 && *(_QWORD *)(v3 + 96) )
  {
    v4 = *(unsigned int *)(v1 + 348);
    v5 = *(_QWORD *)(v1 + 216);
    v6 = *(unsigned __int8 (__fastcall **)(struct _FILE_OBJECT *, __int64, _QWORD, _QWORD))(v1 + 376);
    DeviceObject = *(struct _DEVICE_OBJECT **)(v1 + 392);
    v7 = *(_QWORD **)(v1 + 368);
    v8 = (*(_DWORD *)(v5 + 24 * v4 + 48) + 4095) & 0xFFFFF000;
    v9 = v7[10];
    v10 = (void *)v7[3];
    v23 = v10;
    SourceMdl = (struct _MDL *)v7[7];
    if ( (*(_BYTE *)(v9 + 10) & 0x20) != 0 )
    {
      MmUnmapLockedPages(*(PVOID *)(v9 + 24), (PMDL)v9);
      v10 = v23;
    }
    IoBuildPartialMdl(SourceMdl, (PMDL)v9, v10, v8);
    v11 = *(struct _FILE_OBJECT **)(*(_QWORD *)(v1 + 352) + 96LL);
    v12 = *(_QWORD *)(v1 + 368);
    v24 = v11;
    SourceMdla = *(PMDL *)(v12 + 80);
    v28 = *(_QWORD *)(v12 + 24);
    if ( !*(_BYTE *)(v1 + 412) && v6 )
    {
      v21 = *(_DWORD *)(v1 + 360);
      if ( v6(v11, v5 + 8 * (v4 + 2 * (v4 + 2)), *(unsigned int *)(v5 + 24 * v4 + 48), 0) )
      {
        v13 = *(_QWORD *)(a1 + 120);
        if ( *(_QWORD *)(v13 + 56) < (unsigned __int64)*(unsigned int *)(v5 + 24 * v4 + 48) )
        {
          *(_QWORD *)(v13 + 56) = 0;
          *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = -1073741793;
        }
        v14 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
            a1,
            *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL));
        }
        return (unsigned int)v14;
      }
      v11 = v24;
    }
    v16 = *(_DWORD *)(v1 + 360);
    v17 = *(_DWORD *)(v5 + 24 * v4 + 48);
    RelatedDeviceObject = (unsigned int)IoGetRelatedDeviceObject(v11);
    LOBYTE(v19) = 3;
    v14 = Smb2BuildChunkRequest(
            a1,
            (_DWORD)v24,
            RelatedDeviceObject,
            v19,
            v21,
            v28,
            v17,
            (__int64)SourceMdla,
            *(_QWORD *)(v5 + 24 * v4 + 32),
            v16);
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
          a1,
          *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL));
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = v14;
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
      return (unsigned int)v14;
    }
    *(_QWORD *)(a1 + 48) = Smb2PerformCopyChunkIrpWorker;
    if ( (int)Srv2MarkWorkItemCancellable(a1, 0) >= 0 )
    {
      LOBYTE(v22) = 1;
      LOBYTE(v20) = 3;
      SRV2_PERF_ENTER_EX(a1 + 584, v20, 260, "Smb2ReadChunk", v22);
      IofCallDriver(DeviceObject, *(PIRP *)(a1 + 120));
      return 259;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids, a1);
      }
      result = 3221225760LL;
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = -1073741536;
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
    }
  }
  else
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = -1073741595;
    *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids);
    }
    return 3221225701LL;
  }
  return result;
}

```

## disassembly

```asm
0x140030c5c  push    rbx
0x140030c5e  push    rbp
0x140030c5f  push    rsi
0x140030c60  push    rdi
0x140030c61  push    r12
0x140030c63  push    r13
0x140030c65  push    r14
0x140030c67  push    r15
0x140030c69  sub     rsp, 68h
0x140030c6d  mov     rbx, [rcx+230h]
0x140030c74  mov     rbp, rcx
0x140030c77  mov     rax, [rbx+160h]
0x140030c7e  mov     dword ptr [rbx+198h], 1
0x140030c88  test    rax, rax
0x140030c8b  jz      loc_140030FB3
0x140030c91  cmp     qword ptr [rax+60h], 0
0x140030c96  jz      loc_140030FB3
0x140030c9c  mov     rax, [rbx+188h]
0x140030ca3  mov     r12d, [rbx+15Ch]
0x140030caa  mov     r14, [rbx+0D8h]
0x140030cb1  mov     r13, [rbx+178h]
0x140030cb8  mov     [rsp+0A8h+DeviceObject], rax
0x140030cc0  mov     rax, [rbx+170h]
0x140030cc7  lea     r15, [r12+r12*2]
0x140030ccb  mov     esi, [r14+r15*8+30h]
0x140030cd0  add     esi, 0FFFh
0x140030cd6  and     esi, 0FFFFF000h
0x140030cdc  mov     rdi, [rax+50h]
0x140030ce0  mov     rcx, [rax+18h]
0x140030ce4  mov     rax, [rax+38h]
0x140030ce8  mov     [rsp+0A8h+arg_0], rcx
0x140030cf0  test    byte ptr [rdi+0Ah], 20h
0x140030cf4  mov     [rsp+0A8h+SourceMdl], rax
0x140030cfc  jz      short loc_140030D19
0x140030cfe  mov     rcx, [rdi+18h]; BaseAddress
0x140030d02  mov     rdx, rdi; MemoryDescriptorList
0x140030d05  call    cs:__imp_MmUnmapLockedPages
0x140030d0c  nop     dword ptr [rax+rax+00h]
0x140030d11  mov     rcx, [rsp+0A8h+arg_0]
0x140030d19  mov     r8, rcx; VirtualAddress
0x140030d1c  mov     r9d, esi; Length
0x140030d1f  mov     rcx, [rsp+0A8h+SourceMdl]; SourceMdl
0x140030d27  mov     rdx, rdi; TargetMdl
0x140030d2a  call    cs:__imp_IoBuildPartialMdl
0x140030d31  nop     dword ptr [rax+rax+00h]
0x140030d36  cmp     byte ptr [rbx+19Ch], 0
0x140030d3d  mov     rax, [rbx+160h]
0x140030d44  mov     r10, [rax+60h]
0x140030d48  mov     rax, [rbx+170h]
0x140030d4f  mov     [rsp+0A8h+arg_0], r10
0x140030d57  mov     rcx, [rax+50h]
0x140030d5b  mov     r9, [rax+18h]
0x140030d5f  mov     [rsp+0A8h+SourceMdl], rcx
0x140030d67  mov     [rsp+0A8h+arg_18], r9
0x140030d6f  jnz     loc_140030E41
0x140030d75  test    r13, r13
0x140030d78  jz      loc_140030E41
0x140030d7e  mov     ecx, [rbx+168h]
0x140030d84  lea     rdx, [r12+2]
0x140030d89  mov     r8, [rbp+78h]
0x140030d8d  lea     rdx, [r12+rdx*2]
0x140030d91  mov     rax, [rsp+0A8h+DeviceObject]
0x140030d99  lea     rdx, [r14+rdx*8]
0x140030d9d  mov     [rsp+0A8h+var_70], rax
0x140030da2  add     r8, 30h ; '0'
0x140030da6  mov     [rsp+0A8h+var_78], r8
0x140030dab  mov     rax, r13
0x140030dae  mov     r8d, [r14+r15*8+30h]
0x140030db3  mov     [rsp+0A8h+var_80], r9
0x140030db8  xor     r9d, r9d
0x140030dbb  mov     dword ptr [rsp+0A8h+var_88], ecx
0x140030dbf  mov     rcx, r10
0x140030dc2  call    _guard_dispatch_icall
0x140030dc7  test    al, al
0x140030dc9  jz      short loc_140030E39
0x140030dcb  mov     rcx, [rbp+78h]
0x140030dcf  mov     eax, [r14+r15*8+30h]
0x140030dd4  cmp     [rcx+38h], rax
0x140030dd8  jnb     short loc_140030DED
0x140030dda  mov     qword ptr [rcx+38h], 0
0x140030de2  mov     rax, [rbp+78h]
0x140030de6  mov     dword ptr [rax+30h], 0C000001Fh
0x140030ded  mov     rax, [rbp+78h]
0x140030df1  mov     ebx, [rax+30h]
0x140030df4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030dfb  lea     rax, WPP_GLOBAL_Control
0x140030e02  cmp     rcx, rax
0x140030e05  jz      short loc_140030E32
0x140030e07  test    dword ptr [rcx+2Ch], 20000000h
0x140030e0e  jz      short loc_140030E32
0x140030e10  cmp     byte ptr [rcx+29h], 2
0x140030e14  jb      short loc_140030E32
0x140030e16  mov     rcx, [rcx+18h]
0x140030e1a  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140030e21  mov     edx, 0Bh
0x140030e26  mov     dword ptr [rsp+0A8h+var_88], ebx
0x140030e2a  mov     r9, rbp
0x140030e2d  call    WPP_SF_qD
0x140030e32  mov     eax, ebx
0x140030e34  jmp     loc_140031013
0x140030e39  mov     r10, [rsp+0A8h+arg_0]
0x140030e41  mov     edi, [rbx+168h]
0x140030e47  mov     rcx, r10; FileObject
0x140030e4a  mov     esi, [r14+r15*8+30h]
0x140030e4f  lea     rbx, [r12+r12*2]
0x140030e53  call    cs:__imp_IoGetRelatedDeviceObject
0x140030e5a  nop     dword ptr [rax+rax+00h]
0x140030e5f  mov     rdx, [rsp+0A8h+arg_0]
0x140030e67  mov     r9b, 3
0x140030e6a  mov     r8, rax
0x140030e6d  mov     [rsp+0A8h+var_60], edi
0x140030e71  mov     rax, [r14+rbx*8+20h]
0x140030e76  mov     rcx, rbp
0x140030e79  mov     [rsp+0A8h+var_68], rax
0x140030e7e  mov     rax, [rsp+0A8h+SourceMdl]
0x140030e86  mov     [rsp+0A8h+var_70], rax
0x140030e8b  mov     rax, [rsp+0A8h+arg_18]
0x140030e93  mov     dword ptr [rsp+0A8h+var_78], esi
0x140030e97  mov     [rsp+0A8h+var_80], rax
0x140030e9c  call    Smb2BuildChunkRequest
0x140030ea1  mov     ebx, eax
0x140030ea3  test    eax, eax
0x140030ea5  jns     short loc_140030F04
0x140030ea7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030eae  lea     rax, WPP_GLOBAL_Control
0x140030eb5  cmp     rcx, rax
0x140030eb8  jz      short loc_140030EEC
0x140030eba  test    dword ptr [rcx+2Ch], 20000000h
0x140030ec1  jz      short loc_140030EEC
0x140030ec3  cmp     byte ptr [rcx+29h], 1
0x140030ec7  jb      short loc_140030EEC
0x140030ec9  mov     rax, [rbp+78h]
0x140030ecd  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140030ed4  mov     rcx, [rcx+18h]
0x140030ed8  mov     edx, 0Ch
0x140030edd  mov     r9, rbp
0x140030ee0  mov     eax, [rax+30h]
0x140030ee3  mov     dword ptr [rsp+0A8h+var_88], eax
0x140030ee7  call    WPP_SF_qD
0x140030eec  mov     rax, [rbp+78h]
0x140030ef0  mov     [rax+30h], ebx
0x140030ef3  mov     rax, [rbp+78h]
0x140030ef7  mov     qword ptr [rax+38h], 0
0x140030eff  jmp     loc_140030E32
0x140030f04  lea     rax, Smb2PerformCopyChunkIrpWorker
0x140030f0b  xor     edx, edx
0x140030f0d  mov     rcx, rbp
0x140030f10  mov     [rbp+30h], rax
0x140030f14  call    Srv2MarkWorkItemCancellable
0x140030f19  test    eax, eax
0x140030f1b  jns     short loc_140030F74
0x140030f1d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030f24  lea     rax, WPP_GLOBAL_Control
0x140030f2b  cmp     rcx, rax
0x140030f2e  jz      short loc_140030F57
0x140030f30  test    dword ptr [rcx+2Ch], 20000000h
0x140030f37  jz      short loc_140030F57
0x140030f39  cmp     byte ptr [rcx+29h], 1
0x140030f3d  jb      short loc_140030F57
0x140030f3f  mov     rcx, [rcx+18h]
0x140030f43  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x140030f4a  mov     edx, 0Dh
0x140030f4f  mov     r9, rbp
0x140030f52  call    WPP_SF_q
0x140030f57  mov     rcx, [rbp+78h]
0x140030f5b  mov     eax, 0C0000120h
0x140030f60  mov     [rcx+30h], eax
0x140030f63  mov     rcx, [rbp+78h]
0x140030f67  mov     qword ptr [rcx+38h], 0
0x140030f6f  jmp     loc_140031013
0x140030f74  lea     rcx, [rbp+248h]
0x140030f7b  mov     byte ptr [rsp+0A8h+var_88], 1
0x140030f80  lea     r9, aSmb2readchunk; "Smb2ReadChunk"
0x140030f87  mov     r8d, 104h
0x140030f8d  mov     dl, 3
0x140030f8f  call    SRV2_PERF_ENTER_EX
0x140030f94  mov     rdx, [rbp+78h]; Irp
0x140030f98  mov     rcx, [rsp+0A8h+DeviceObject]; DeviceObject
0x140030fa0  call    cs:__imp_IofCallDriver
0x140030fa7  nop     dword ptr [rax+rax+00h]
0x140030fac  mov     eax, 103h
0x140030fb1  jmp     short loc_140031013
0x140030fb3  mov     rax, [rcx+78h]
0x140030fb7  mov     edi, 0C00000E5h
0x140030fbc  mov     [rax+30h], edi
0x140030fbf  mov     rax, [rcx+78h]
0x140030fc3  mov     qword ptr [rax+38h], 0
0x140030fcb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030fd2  lea     rax, WPP_GLOBAL_Control
0x140030fd9  cmp     rcx, rax
0x140030fdc  jz      short loc_140031011
0x140030fde  test    dword ptr [rcx+2Ch], 20000000h
0x140030fe5  jz      short loc_140031011
0x140030fe7  cmp     byte ptr [rcx+29h], 1
0x140030feb  jb      short loc_140031011
0x140030fed  mov     r8, [rbx+160h]
0x140030ff4  mov     edx, 0Ah
0x140030ff9  mov     rcx, [rcx+18h]
0x140030ffd  mov     r9, rbp
0x140031000  mov     [rsp+0A8h+var_88], r8
0x140031005  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x14003100c  call    WPP_SF_qq
0x140031011  mov     eax, edi
0x140031013  add     rsp, 68h
0x140031017  pop     r15
0x140031019  pop     r14
0x14003101b  pop     r13
0x14003101d  pop     r12
0x14003101f  pop     rdi
0x140031020  pop     rsi
0x140031021  pop     rbp
0x140031022  pop     rbx
0x140031023  retn
```

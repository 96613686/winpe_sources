# Smb2CreateRkfBypassEcp

- ea: `0x140094e44`
- end: `0x140095035`
- name: `Smb2CreateRkfBypassEcp`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001bd4c`

## callees

- `0x1400222ec`
- `0x1400224b8`
- `0x140038980`
- `0x140094e44`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140094fd3`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140094fd3`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140094f82`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140094f82`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140094f6c`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140094f6c`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140094e74`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140094e74`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140094eff`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140094eff`

## pseudocode

```c
__int64 __fastcall Smb2CreateRkfBypassEcp(struct _ECP_LIST **a1)
{
  struct _ECP_LIST *v1; // rax
  unsigned int Parameter; // ebx
  char v4; // si
  NTSTATUS v5; // eax
  PDEVICE_OBJECT v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r9
  PVOID EcpContext; // [rsp+50h] [rbp+20h] BYREF
  PECP_LIST EcpList; // [rsp+58h] [rbp+28h] BYREF

  v1 = *a1;
  EcpList = 0;
  EcpContext = 0;
  if ( v1 )
  {
    v4 = 0;
    EcpList = v1;
  }
  else
  {
    Parameter = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
    if ( (Parameter & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, Parameter);
      }
      return Parameter;
    }
    v4 = 1;
  }
  v5 = FsRtlAllocateExtraCreateParameter(&Smb2RkfGuidEcpIn, 0x68u, 0, 0, 0x5324534Cu, &EcpContext);
  Parameter = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 49;
      v8 = (unsigned int)v5;
LABEL_19:
      WPP_SF_d(v6->AttachedDevice, v7, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, v8);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  memset(EcpContext, 0, 0x68u);
  *(_DWORD *)EcpContext = 0;
  Parameter = FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
  if ( (Parameter & 0x80000000) != 0 )
  {
    FsRtlFreeExtraCreateParameter(EcpContext);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 50;
      v8 = Parameter;
      goto LABEL_19;
    }
LABEL_20:
    if ( v4 )
      FsRtlFreeExtraCreateParameterList(EcpList);
    return Parameter;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 51, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, EcpContext);
  }
  *a1 = EcpList;
  return Parameter;
}

```

## disassembly

```asm
0x140094e44  mov     [rsp-18h+arg_10], rbx
0x140094e49  push    rbp
0x140094e4a  push    rsi
0x140094e4b  push    rdi
0x140094e4c  mov     rbp, rsp
0x140094e4f  sub     rsp, 30h
0x140094e53  mov     rax, [rcx]
0x140094e56  mov     rdi, rcx
0x140094e59  mov     [rbp+EcpList], 0
0x140094e61  mov     [rbp+arg_0], 0
0x140094e69  test    rax, rax
0x140094e6c  jnz     short loc_140094ED6
0x140094e6e  lea     rdx, [rbp+EcpList]; EcpList
0x140094e72  xor     ecx, ecx; Flags
0x140094e74  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x140094e7b  nop     dword ptr [rax+rax+00h]
0x140094e80  mov     ebx, eax
0x140094e82  test    eax, eax
0x140094e84  jns     short loc_140094ED1
0x140094e86  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140094e8d  lea     rcx, WPP_GLOBAL_Control
0x140094e94  cmp     rax, rcx
0x140094e97  jz      loc_140095025
0x140094e9d  test    dword ptr [rax+2Ch], 100000h
0x140094ea4  jz      loc_140095025
0x140094eaa  cmp     byte ptr [rax+29h], 1
0x140094eae  jb      loc_140095025
0x140094eb4  mov     rcx, [rax+18h]
0x140094eb8  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140094ebf  mov     edx, 30h ; '0'
0x140094ec4  mov     r9d, ebx
0x140094ec7  call    WPP_SF_d
0x140094ecc  jmp     loc_140095025
0x140094ed1  mov     sil, 1
0x140094ed4  jmp     short loc_140094EDD
0x140094ed6  xor     sil, sil
0x140094ed9  mov     [rbp+EcpList], rax
0x140094edd  xor     r9d, r9d; CleanupCallback
0x140094ee0  lea     rax, [rbp+arg_0]
0x140094ee4  mov     [rsp+30h+EcpContext], rax; EcpContext
0x140094ee9  lea     rcx, Smb2RkfGuidEcpIn; EcpType
0x140094ef0  xor     r8d, r8d; Flags
0x140094ef3  mov     [rsp+30h+PoolTag], 5324534Ch; PoolTag
0x140094efb  lea     edx, [r9+68h]; SizeOfContext
0x140094eff  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140094f06  nop     dword ptr [rax+rax+00h]
0x140094f0b  mov     ebx, eax
0x140094f0d  test    eax, eax
0x140094f0f  jns     short loc_140094F4B
0x140094f11  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140094f18  lea     rcx, WPP_GLOBAL_Control
0x140094f1f  cmp     r10, rcx
0x140094f22  jz      loc_140094FCA
0x140094f28  test    dword ptr [r10+2Ch], 100000h
0x140094f30  jz      loc_140094FCA
0x140094f36  cmp     byte ptr [r10+29h], 1
0x140094f3b  jb      loc_140094FCA
0x140094f41  mov     edx, 31h ; '1'
0x140094f46  mov     r9d, eax
0x140094f49  jmp     short loc_140094FBA
0x140094f4b  mov     rcx, [rbp+arg_0]; void *
0x140094f4f  xor     edx, edx; Val
0x140094f51  lea     r8d, [rdx+68h]; Size
0x140094f55  call    memset
0x140094f5a  mov     rax, [rbp+arg_0]
0x140094f5e  mov     dword ptr [rax], 0
0x140094f64  mov     rdx, [rbp+arg_0]; EcpContext
0x140094f68  mov     rcx, [rbp+EcpList]; EcpList
0x140094f6c  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140094f73  nop     dword ptr [rax+rax+00h]
0x140094f78  mov     ebx, eax
0x140094f7a  test    eax, eax
0x140094f7c  jns     short loc_140094FE1
0x140094f7e  mov     rcx, [rbp+arg_0]; EcpContext
0x140094f82  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140094f89  nop     dword ptr [rax+rax+00h]
0x140094f8e  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140094f95  lea     rcx, WPP_GLOBAL_Control
0x140094f9c  cmp     r10, rcx
0x140094f9f  jz      short loc_140094FCA
0x140094fa1  test    dword ptr [r10+2Ch], 100000h
0x140094fa9  jz      short loc_140094FCA
0x140094fab  cmp     byte ptr [r10+29h], 1
0x140094fb0  jb      short loc_140094FCA
0x140094fb2  mov     edx, 32h ; '2'
0x140094fb7  mov     r9d, ebx
0x140094fba  mov     rcx, [r10+18h]
0x140094fbe  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140094fc5  call    WPP_SF_d
0x140094fca  test    sil, sil
0x140094fcd  jz      short loc_140095025
0x140094fcf  mov     rcx, [rbp+EcpList]; EcpList
0x140094fd3  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140094fda  nop     dword ptr [rax+rax+00h]
0x140094fdf  jmp     short loc_140095025
0x140094fe1  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140094fe8  lea     rcx, WPP_GLOBAL_Control
0x140094fef  cmp     r10, rcx
0x140094ff2  jz      short loc_14009501E
0x140094ff4  test    dword ptr [r10+2Ch], 100000h
0x140094ffc  jz      short loc_14009501E
0x140094ffe  cmp     byte ptr [r10+29h], 2
0x140095003  jb      short loc_14009501E
0x140095005  mov     r9, [rbp+arg_0]
0x140095009  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140095010  mov     rcx, [r10+18h]
0x140095014  mov     edx, 33h ; '3'
0x140095019  call    WPP_SF_q
0x14009501e  mov     rax, [rbp+EcpList]
0x140095022  mov     [rdi], rax
0x140095025  mov     eax, ebx
0x140095027  mov     rbx, [rsp+30h+arg_10]
0x14009502c  add     rsp, 30h
0x140095030  pop     rdi
0x140095031  pop     rsi
0x140095032  pop     rbp
0x140095033  retn
```

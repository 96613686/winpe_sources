# Smb2CreateRkfBypassEcp

- ea: `0x140094df4`
- end: `0x140094fe5`
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
- `0x140094df4`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140094f83`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140094f83`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140094f32`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140094f32`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140094f1c`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140094f1c`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140094e24`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140094e24`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140094eaf`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140094eaf`

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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, Parameter);
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
      WPP_SF_d(v6->AttachedDevice, v7, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, v8);
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
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, EcpContext);
  }
  *a1 = EcpList;
  return Parameter;
}

```

## disassembly

```asm
0x140094df4  mov     [rsp-18h+arg_10], rbx
0x140094df9  push    rbp
0x140094dfa  push    rsi
0x140094dfb  push    rdi
0x140094dfc  mov     rbp, rsp
0x140094dff  sub     rsp, 30h
0x140094e03  mov     rax, [rcx]
0x140094e06  mov     rdi, rcx
0x140094e09  mov     [rbp+EcpList], 0
0x140094e11  mov     [rbp+arg_0], 0
0x140094e19  test    rax, rax
0x140094e1c  jnz     short loc_140094E86
0x140094e1e  lea     rdx, [rbp+EcpList]; EcpList
0x140094e22  xor     ecx, ecx; Flags
0x140094e24  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x140094e2b  nop     dword ptr [rax+rax+00h]
0x140094e30  mov     ebx, eax
0x140094e32  test    eax, eax
0x140094e34  jns     short loc_140094E81
0x140094e36  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140094e3d  lea     rcx, WPP_GLOBAL_Control
0x140094e44  cmp     rax, rcx
0x140094e47  jz      loc_140094FD5
0x140094e4d  test    dword ptr [rax+2Ch], 100000h
0x140094e54  jz      loc_140094FD5
0x140094e5a  cmp     byte ptr [rax+29h], 1
0x140094e5e  jb      loc_140094FD5
0x140094e64  mov     rcx, [rax+18h]
0x140094e68  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140094e6f  mov     edx, 30h ; '0'
0x140094e74  mov     r9d, ebx
0x140094e77  call    WPP_SF_d
0x140094e7c  jmp     loc_140094FD5
0x140094e81  mov     sil, 1
0x140094e84  jmp     short loc_140094E8D
0x140094e86  xor     sil, sil
0x140094e89  mov     [rbp+EcpList], rax
0x140094e8d  xor     r9d, r9d; CleanupCallback
0x140094e90  lea     rax, [rbp+arg_0]
0x140094e94  mov     [rsp+30h+EcpContext], rax; EcpContext
0x140094e99  lea     rcx, Smb2RkfGuidEcpIn; EcpType
0x140094ea0  xor     r8d, r8d; Flags
0x140094ea3  mov     [rsp+30h+PoolTag], 5324534Ch; PoolTag
0x140094eab  lea     edx, [r9+68h]; SizeOfContext
0x140094eaf  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140094eb6  nop     dword ptr [rax+rax+00h]
0x140094ebb  mov     ebx, eax
0x140094ebd  test    eax, eax
0x140094ebf  jns     short loc_140094EFB
0x140094ec1  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140094ec8  lea     rcx, WPP_GLOBAL_Control
0x140094ecf  cmp     r10, rcx
0x140094ed2  jz      loc_140094F7A
0x140094ed8  test    dword ptr [r10+2Ch], 100000h
0x140094ee0  jz      loc_140094F7A
0x140094ee6  cmp     byte ptr [r10+29h], 1
0x140094eeb  jb      loc_140094F7A
0x140094ef1  mov     edx, 31h ; '1'
0x140094ef6  mov     r9d, eax
0x140094ef9  jmp     short loc_140094F6A
0x140094efb  mov     rcx, [rbp+arg_0]; void *
0x140094eff  xor     edx, edx; Val
0x140094f01  lea     r8d, [rdx+68h]; Size
0x140094f05  call    memset
0x140094f0a  mov     rax, [rbp+arg_0]
0x140094f0e  mov     dword ptr [rax], 0
0x140094f14  mov     rdx, [rbp+arg_0]; EcpContext
0x140094f18  mov     rcx, [rbp+EcpList]; EcpList
0x140094f1c  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140094f23  nop     dword ptr [rax+rax+00h]
0x140094f28  mov     ebx, eax
0x140094f2a  test    eax, eax
0x140094f2c  jns     short loc_140094F91
0x140094f2e  mov     rcx, [rbp+arg_0]; EcpContext
0x140094f32  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140094f39  nop     dword ptr [rax+rax+00h]
0x140094f3e  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140094f45  lea     rcx, WPP_GLOBAL_Control
0x140094f4c  cmp     r10, rcx
0x140094f4f  jz      short loc_140094F7A
0x140094f51  test    dword ptr [r10+2Ch], 100000h
0x140094f59  jz      short loc_140094F7A
0x140094f5b  cmp     byte ptr [r10+29h], 1
0x140094f60  jb      short loc_140094F7A
0x140094f62  mov     edx, 32h ; '2'
0x140094f67  mov     r9d, ebx
0x140094f6a  mov     rcx, [r10+18h]
0x140094f6e  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140094f75  call    WPP_SF_d
0x140094f7a  test    sil, sil
0x140094f7d  jz      short loc_140094FD5
0x140094f7f  mov     rcx, [rbp+EcpList]; EcpList
0x140094f83  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140094f8a  nop     dword ptr [rax+rax+00h]
0x140094f8f  jmp     short loc_140094FD5
0x140094f91  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140094f98  lea     rcx, WPP_GLOBAL_Control
0x140094f9f  cmp     r10, rcx
0x140094fa2  jz      short loc_140094FCE
0x140094fa4  test    dword ptr [r10+2Ch], 100000h
0x140094fac  jz      short loc_140094FCE
0x140094fae  cmp     byte ptr [r10+29h], 2
0x140094fb3  jb      short loc_140094FCE
0x140094fb5  mov     r9, [rbp+arg_0]
0x140094fb9  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140094fc0  mov     rcx, [r10+18h]
0x140094fc4  mov     edx, 33h ; '3'
0x140094fc9  call    WPP_SF_q
0x140094fce  mov     rax, [rbp+EcpList]
0x140094fd2  mov     [rdi], rax
0x140094fd5  mov     eax, ebx
0x140094fd7  mov     rbx, [rsp+30h+arg_10]
0x140094fdc  add     rsp, 30h
0x140094fe0  pop     rdi
0x140094fe1  pop     rsi
0x140094fe2  pop     rbp
0x140094fe3  retn
```

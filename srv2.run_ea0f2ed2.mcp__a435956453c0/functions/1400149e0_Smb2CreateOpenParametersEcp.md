# Smb2CreateOpenParametersEcp

- ea: `0x1400149e0`
- end: `0x140014b6a`
- name: `Smb2CreateOpenParametersEcp`
- size: `394`
- prototype: `__int64 __fastcall(PECP_LIST EcpList)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14007a290`

## callees

- `0x1400149e0`
- `0x1400222ec`
- `0x1400224b8`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140014a10`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140014a10`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140014b33`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140014b33`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140014a76`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140014a76`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140014a4a`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140014a4a`

## pseudocode

```c
__int64 __fastcall Smb2CreateOpenParametersEcp(PECP_LIST EcpList)
{
  NTSTATUS Parameter; // ebx
  char v3; // di
  PDEVICE_OBJECT v4; // rcx
  __int64 v6; // rdx
  ULONG EcpContextSize; // [rsp+48h] [rbp+10h] BYREF
  PVOID EcpContext; // [rsp+50h] [rbp+18h] BYREF

  EcpContext = 0;
  EcpContextSize = 0;
  Parameter = 0;
  if ( FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_OPEN_PARAMETERS, &EcpContext, &EcpContextSize) >= 0 )
  {
LABEL_6:
    *((_DWORD *)EcpContext + 1) |= 0x18u;
    return (unsigned int)Parameter;
  }
  Parameter = FsRtlAllocateExtraCreateParameter(&GUID_ECP_OPEN_PARAMETERS, 8u, 0, 0, 0x5324534Cu, &EcpContext);
  if ( Parameter < 0 )
  {
    v3 = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v6 = 56;
      goto LABEL_21;
    }
  }
  else
  {
    *(_QWORD *)EcpContext = 0;
    *(_WORD *)EcpContext = 8;
    Parameter = FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
    if ( Parameter >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 58, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, EcpContext);
      }
      goto LABEL_6;
    }
    v3 = 1;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v6 = 57;
LABEL_21:
      WPP_SF_d(v4->AttachedDevice, v6, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, (unsigned int)Parameter);
    }
  }
  if ( EcpContext && v3 )
    FsRtlFreeExtraCreateParameter(EcpContext);
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x1400149e0  mov     [rsp+arg_0], rbx
0x1400149e5  mov     [rsp+arg_18], rsi
0x1400149ea  push    rdi
0x1400149eb  sub     rsp, 30h
0x1400149ef  xor     eax, eax
0x1400149f1  lea     r9, [rsp+38h+EcpContextSize]; EcpContextSize
0x1400149f6  lea     r8, [rsp+38h+EcpContext]; EcpContext
0x1400149fb  mov     [rsp+38h+EcpContext], rax
0x140014a00  lea     rdx, GUID_ECP_OPEN_PARAMETERS; EcpType
0x140014a07  mov     [rsp+38h+EcpContextSize], eax
0x140014a0b  mov     ebx, eax
0x140014a0d  mov     rdi, rcx
0x140014a10  call    cs:__imp_FsRtlFindExtraCreateParameter
0x140014a17  nop     dword ptr [rax+rax+00h]
0x140014a1c  test    eax, eax
0x140014a1e  jns     loc_140014AA8
0x140014a24  lea     rax, [rsp+38h+EcpContext]
0x140014a29  mov     esi, 8
0x140014a2e  mov     [rsp+38h+var_10], rax; EcpContext
0x140014a33  lea     rcx, GUID_ECP_OPEN_PARAMETERS; EcpType
0x140014a3a  mov     edx, esi; SizeOfContext
0x140014a3c  mov     [rsp+38h+PoolTag], 5324534Ch; PoolTag
0x140014a44  xor     r9d, r9d; CleanupCallback
0x140014a47  xor     r8d, r8d; Flags
0x140014a4a  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140014a51  nop     dword ptr [rax+rax+00h]
0x140014a56  mov     ebx, eax
0x140014a58  test    eax, eax
0x140014a5a  js      short loc_140014AB3
0x140014a5c  mov     rax, [rsp+38h+EcpContext]
0x140014a61  xor     ecx, ecx
0x140014a63  mov     [rax], rcx
0x140014a66  mov     rcx, rdi; EcpList
0x140014a69  mov     rax, [rsp+38h+EcpContext]
0x140014a6e  mov     [rax], si
0x140014a71  mov     rdx, [rsp+38h+EcpContext]; EcpContext
0x140014a76  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140014a7d  nop     dword ptr [rax+rax+00h]
0x140014a82  mov     ebx, eax
0x140014a84  test    eax, eax
0x140014a86  js      short loc_140014AE6
0x140014a88  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a8f  lea     rax, WPP_GLOBAL_Control
0x140014a96  cmp     rcx, rax
0x140014a99  jz      short loc_140014AA8
0x140014a9b  test    dword ptr [rcx+2Ch], 100000h
0x140014aa2  jnz     loc_140014B41
0x140014aa8  mov     rax, [rsp+38h+EcpContext]
0x140014aad  or      dword ptr [rax+4], 18h
0x140014ab1  jmp     short loc_140014AD3
0x140014ab3  xor     dil, dil
0x140014ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140014abd  lea     rax, WPP_GLOBAL_Control
0x140014ac4  cmp     rcx, rax
0x140014ac7  jnz     short loc_140014B15
0x140014ac9  mov     rcx, [rsp+38h+EcpContext]; EcpContext
0x140014ace  test    rcx, rcx
0x140014ad1  jnz     short loc_140014B2E
0x140014ad3  mov     rsi, [rsp+38h+arg_18]
0x140014ad8  mov     eax, ebx
0x140014ada  mov     rbx, [rsp+38h+arg_0]
0x140014adf  add     rsp, 30h
0x140014ae3  pop     rdi
0x140014ae4  retn
0x140014ae6  mov     dil, 1
0x140014ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x140014af0  lea     rax, WPP_GLOBAL_Control
0x140014af7  cmp     rcx, rax
0x140014afa  jz      short loc_140014AC9
0x140014afc  test    dword ptr [rcx+2Ch], 100000h
0x140014b03  jz      short loc_140014AC9
0x140014b05  cmp     [rcx+29h], dil
0x140014b09  jb      short loc_140014AC9
0x140014b0b  mov     edx, 39h ; '9'
0x140014b10  jmp     loc_14003C744
0x140014b15  test    dword ptr [rcx+2Ch], 100000h
0x140014b1c  jz      short loc_140014AC9
0x140014b1e  cmp     byte ptr [rcx+29h], 1
0x140014b22  jb      short loc_140014AC9
0x140014b24  mov     edx, 38h ; '8'
0x140014b29  jmp     loc_14003C744
0x140014b2e  test    dil, dil
0x140014b31  jz      short loc_140014AD3
0x140014b33  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140014b3a  nop     dword ptr [rax+rax+00h]
0x140014b3f  jmp     short loc_140014AD3
0x140014b41  cmp     byte ptr [rcx+29h], 2
0x140014b45  jb      loc_140014AA8
0x140014b4b  mov     r9, [rsp+38h+EcpContext]
0x140014b50  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140014b57  mov     rcx, [rcx+18h]
0x140014b5b  mov     edx, 3Ah ; ':'
0x140014b60  call    WPP_SF_q
0x140014b65  jmp     loc_140014AA8
0x14003c744  mov     rcx, [rcx+18h]
0x14003c748  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14003c74f  mov     r9d, ebx
0x14003c752  call    WPP_SF_d
0x14003c757  nop
0x14003c758  jmp     loc_140014AC9
```

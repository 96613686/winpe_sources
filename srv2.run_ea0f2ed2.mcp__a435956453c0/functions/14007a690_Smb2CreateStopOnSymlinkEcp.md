# Smb2CreateStopOnSymlinkEcp

- ea: `0x14007a690`
- end: `0x14007a893`
- name: `Smb2CreateStopOnSymlinkEcp`
- size: `515`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1400792e0`
- `0x14007a290`

## callees

- `0x1400222ec`
- `0x1400224b8`
- `0x14007a690`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x1400981ab`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x1400981ab`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a6c9`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a6c9`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a819`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a819`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a730`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a730`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007a786`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007a786`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a706`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a706`

## pseudocode

```c
__int64 __fastcall Smb2CreateStopOnSymlinkEcp(struct _ECP_LIST **a1)
{
  struct _ECP_LIST *v2; // rcx
  char v3; // si
  NTSTATUS Parameter; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  PVOID EcpContext; // [rsp+50h] [rbp+8h] BYREF
  PECP_LIST EcpList; // [rsp+58h] [rbp+10h] BYREF

  v2 = *a1;
  EcpList = 0;
  if ( v2 )
  {
    EcpList = v2;
    v3 = 0;
    Parameter = 0;
    if ( FsRtlFindExtraCreateParameter(v2, &ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID, 0, 0) >= 0 )
      return (unsigned int)Parameter;
LABEL_3:
    EcpContext = 0;
    Parameter = FsRtlAllocateExtraCreateParameter(
                  &ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID,
                  8u,
                  0,
                  0,
                  0x5324534Cu,
                  &EcpContext);
    if ( Parameter < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
LABEL_27:
        if ( v3 )
          FsRtlFreeExtraCreateParameterList(EcpList);
        return (unsigned int)Parameter;
      }
      v7 = 53;
    }
    else
    {
      *(_QWORD *)EcpContext = 0;
      Parameter = FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
      if ( Parameter >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 55, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, EcpContext);
        }
        if ( v3 )
          *a1 = EcpList;
        return (unsigned int)Parameter;
      }
      FsRtlFreeExtraCreateParameter(EcpContext);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_27;
      }
      v7 = 54;
    }
    WPP_SF_d(v6->AttachedDevice, v7, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, (unsigned int)Parameter);
    goto LABEL_27;
  }
  Parameter = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
  if ( Parameter >= 0 )
  {
    v3 = 1;
    goto LABEL_3;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      52,
      &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
      (unsigned int)Parameter);
  }
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x14007a690  mov     [rsp+arg_10], rbx
0x14007a695  push    rbp
0x14007a696  push    rsi
0x14007a697  push    rdi
0x14007a698  sub     rsp, 30h
0x14007a69c  xor     ebp, ebp
0x14007a69e  mov     rdi, rcx
0x14007a6a1  mov     rcx, [rcx]; EcpList
0x14007a6a4  mov     [rsp+48h+EcpList], rbp
0x14007a6a9  test    rcx, rcx
0x14007a6ac  jz      loc_14007A77F
0x14007a6b2  xor     r9d, r9d; EcpContextSize
0x14007a6b5  mov     [rsp+48h+EcpList], rcx
0x14007a6ba  xor     r8d, r8d; EcpContext
0x14007a6bd  lea     rdx, ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID; EcpType
0x14007a6c4  xor     sil, sil
0x14007a6c7  mov     ebx, ebp
0x14007a6c9  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14007a6d0  nop     dword ptr [rax+rax+00h]
0x14007a6d5  test    eax, eax
0x14007a6d7  jns     loc_14007A76F
0x14007a6dd  lea     rax, [rsp+48h+arg_0]
0x14007a6e2  mov     [rsp+48h+arg_0], rbp
0x14007a6e7  mov     [rsp+48h+EcpContext], rax; EcpContext
0x14007a6ec  lea     rcx, ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID; EcpType
0x14007a6f3  xor     r9d, r9d; CleanupCallback
0x14007a6f6  mov     [rsp+48h+PoolTag], 5324534Ch; PoolTag
0x14007a6fe  xor     r8d, r8d; Flags
0x14007a701  mov     edx, 8; SizeOfContext
0x14007a706  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14007a70d  nop     dword ptr [rax+rax+00h]
0x14007a712  mov     ebx, eax
0x14007a714  test    eax, eax
0x14007a716  js      loc_14007A7DC
0x14007a71c  mov     rax, [rsp+48h+arg_0]
0x14007a721  xor     ecx, ecx
0x14007a723  mov     [rax], rcx
0x14007a726  mov     rdx, [rsp+48h+arg_0]; EcpContext
0x14007a72b  mov     rcx, [rsp+48h+EcpList]; EcpList
0x14007a730  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14007a737  nop     dword ptr [rax+rax+00h]
0x14007a73c  mov     ebx, eax
0x14007a73e  test    eax, eax
0x14007a740  js      loc_14007A814
0x14007a746  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a74d  lea     rax, WPP_GLOBAL_Control
0x14007a754  cmp     rcx, rax
0x14007a757  jz      short loc_14007A766
0x14007a759  test    dword ptr [rcx+2Ch], 100000h
0x14007a760  jnz     loc_14007A85D
0x14007a766  test    sil, sil
0x14007a769  jnz     loc_14007A886
0x14007a76f  mov     eax, ebx
0x14007a771  mov     rbx, [rsp+48h+arg_10]
0x14007a776  add     rsp, 30h
0x14007a77a  pop     rdi
0x14007a77b  pop     rsi
0x14007a77c  pop     rbp
0x14007a77d  retn
0x14007a77f  lea     rdx, [rsp+48h+EcpList]; EcpList
0x14007a784  xor     ecx, ecx; Flags
0x14007a786  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14007a78d  nop     dword ptr [rax+rax+00h]
0x14007a792  mov     ebx, eax
0x14007a794  test    eax, eax
0x14007a796  js      short loc_14007A7A0
0x14007a798  mov     sil, 1
0x14007a79b  jmp     loc_14007A6DD
0x14007a7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a7a7  lea     rax, WPP_GLOBAL_Control
0x14007a7ae  cmp     rcx, rax
0x14007a7b1  jz      short loc_14007A76F
0x14007a7b3  test    dword ptr [rcx+2Ch], 100000h
0x14007a7ba  jz      short loc_14007A76F
0x14007a7bc  cmp     byte ptr [rcx+29h], 1
0x14007a7c0  jb      short loc_14007A76F
0x14007a7c2  mov     rcx, [rcx+18h]
0x14007a7c6  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007a7cd  mov     edx, 34h ; '4'
0x14007a7d2  mov     r9d, ebx
0x14007a7d5  call    WPP_SF_d
0x14007a7da  jmp     short loc_14007A76F
0x14007a7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a7e3  lea     rax, WPP_GLOBAL_Control
0x14007a7ea  cmp     rcx, rax
0x14007a7ed  jz      loc_14009819D
0x14007a7f3  test    dword ptr [rcx+2Ch], 100000h
0x14007a7fa  jz      loc_14009819D
0x14007a800  cmp     byte ptr [rcx+29h], 1
0x14007a804  jb      loc_14009819D
0x14007a80a  mov     edx, 35h ; '5'
0x14007a80f  jmp     loc_14009818A
0x14007a814  mov     rcx, [rsp+48h+arg_0]; EcpContext
0x14007a819  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14007a820  nop     dword ptr [rax+rax+00h]
0x14007a825  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a82c  lea     rax, WPP_GLOBAL_Control
0x14007a833  cmp     rcx, rax
0x14007a836  jz      loc_14009819D
0x14007a83c  test    dword ptr [rcx+2Ch], 100000h
0x14007a843  jz      loc_14009819D
0x14007a849  cmp     byte ptr [rcx+29h], 1
0x14007a84d  jb      loc_14009819D
0x14007a853  mov     edx, 36h ; '6'
0x14007a858  jmp     loc_14009818A
0x14007a85d  cmp     byte ptr [rcx+29h], 2
0x14007a861  jb      loc_14007A766
0x14007a867  mov     r9, [rsp+48h+arg_0]
0x14007a86c  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007a873  mov     rcx, [rcx+18h]
0x14007a877  mov     edx, 37h ; '7'
0x14007a87c  call    WPP_SF_q
0x14007a881  jmp     loc_14007A766
0x14007a886  mov     rax, [rsp+48h+EcpList]
0x14007a88b  mov     [rdi], rax
0x14007a88e  jmp     loc_14007A76F
0x14009818a  mov     rcx, [rcx+18h]
0x14009818e  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140098195  mov     r9d, ebx
0x140098198  call    WPP_SF_d
0x14009819d  test    sil, sil
0x1400981a0  jz      loc_14007A76F
0x1400981a6  mov     rcx, [rsp+48h+EcpList]; EcpList
0x1400981ab  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x1400981b2  nop     dword ptr [rax+rax+00h]
0x1400981b7  nop
0x1400981b8  jmp     loc_14007A76F
```

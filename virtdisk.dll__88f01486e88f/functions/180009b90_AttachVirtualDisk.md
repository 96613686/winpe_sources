# AttachVirtualDisk

- ea: `0x180009b90`
- end: `0x180009f60`
- name: `AttachVirtualDisk`
- size: `976`
- prototype: `DWORD __stdcall(HANDLE VirtualDiskHandle, PSECURITY_DESCRIPTOR SecurityDescriptor, ATTACH_VIRTUAL_DISK_FLAG Flags, ULONG ProviderSpecificFlags, PATTACH_VIRTUAL_DISK_PARAMETERS Parameters, LPOVERLAPPED Overlapped)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004060`
- `0x1800063a8`
- `0x180006fac`
- `0x180007f2c`
- `0x180009b90`
- `0x180009f68`
- `0x180009fc0`
- `0x18000ac64`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f3c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009f2c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009f2c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180009c82`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180009c82`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180009d01`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180009d01`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180009c5e`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180009c5e`
- `ntdll!RtlFreeHeap` at `0x180009cc0`
- `ntdll!RtlFreeHeap` at `0x180009d50`
- `ntdll!RtlFreeHeap` at `0x180009d78`
- `ntdll!RtlFreeHeap` at `0x180009cc0`
- `ntdll!RtlFreeHeap` at `0x180009d50`
- `ntdll!RtlFreeHeap` at `0x180009d78`
- `ntdll!RtlAllocateHeap` at `0x180009ce2`
- `ntdll!RtlAllocateHeap` at `0x180009e02`
- `ntdll!RtlAllocateHeap` at `0x180009ce2`
- `ntdll!RtlAllocateHeap` at `0x180009e02`

## pseudocode

```c
DWORD __stdcall AttachVirtualDisk(
        HANDLE VirtualDiskHandle,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        ATTACH_VIRTUAL_DISK_FLAG Flags,
        ULONG ProviderSpecificFlags,
        PATTACH_VIRTUAL_DISK_PARAMETERS Parameters,
        LPOVERLAPPED Overlapped)
{
  struct _ATTACH_VIRTUAL_DISK_PARAMETERS *v6; // rdi
  PVOID v7; // r14
  PSECURITY_DESCRIPTOR v9; // r13
  char *v10; // rbx
  DWORD LastError; // ebx
  DWORD SecurityDescriptorLength; // esi
  DWORD v13; // r13d
  __int64 v14; // rcx
  struct _ATTACH_VIRTUAL_DISK_PARAMETERS *Heap; // rax
  DWORD dwBufferLength; // [rsp+40h] [rbp-30h] BYREF
  int v18; // [rsp+44h] [rbp-2Ch]
  DWORD BytesReturned; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h]
  __int64 v21; // [rsp+58h] [rbp-18h]
  HANDLE TokenHandle[2]; // [rsp+60h] [rbp-10h] BYREF

  v6 = 0;
  v7 = 0;
  BytesReturned = 0;
  v9 = SecurityDescriptor;
  v10 = (char *)VirtualDiskHandle;
  *(_OWORD *)TokenHandle = 0;
  if ( (Microsoft_Windows_VIRTDISKEnableBits & 1) != 0 )
    McTemplateU0p_EventWriteTransfer(VirtualDiskHandle, VirtdiskAttachStart, VirtualDiskHandle);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1ea7e73471d83c272d67ddaccec018cc_Traceguids);
  }
  if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = 6;
    goto LABEL_24;
  }
  if ( (Flags & 0xFFFFF800) != 0 || Parameters && (unsigned int)(Parameters->Version - 1) > 1 )
  {
    LastError = 87;
    goto LABEL_24;
  }
  SecurityDescriptorLength = 0;
  if ( !v9 )
  {
    v13 = 56;
LABEL_37:
    Heap = (struct _ATTACH_VIRTUAL_DISK_PARAMETERS *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v13);
    v6 = Heap;
    if ( !Heap )
    {
      LastError = 14;
LABEL_39:
      v9 = SecurityDescriptor;
      goto LABEL_24;
    }
    Heap->Version = ATTACH_VIRTUAL_DISK_VERSION_1;
    Heap->Version1.Reserved = Flags;
    Heap[1].Version = ProviderSpecificFlags;
    if ( v7 )
    {
      Heap[1].Version1.Reserved = 56;
      Heap[2].Version = SecurityDescriptorLength;
      memcpy_0(&Heap[7], v7, SecurityDescriptorLength);
    }
    if ( (Flags & 0x100) != 0 )
    {
      if ( (Flags & 0xC0) == 0x40 )
      {
        v21 = 0;
        v20 = 0;
        v18 = 0;
        LastError = ParseVirtualDiskPartitionTable(v10, (__int64)&v6[5], (__int64)&v6[6]);
        if ( LastError )
          goto LABEL_39;
        if ( !v18 )
        {
          LastError = 1785;
          goto LABEL_39;
        }
        v6->Version1.Reserved |= 0x80u;
LABEL_54:
        TryEnableManageVolumePrivilege(TokenHandle);
        if ( DeviceIoControl(VirtualDiskHandle, 0x2D191Cu, v6, v13, 0, 0, &BytesReturned, Overlapped) )
          LastError = 0;
        else
          LastError = GetLastError();
        goto LABEL_39;
      }
    }
    else
    {
      if ( (Flags & 0x80u) == 0 )
        goto LABEL_54;
      if ( (Flags & 0x40) != 0 && Parameters && Parameters->Version == 2 )
      {
        v6[5] = Parameters[1];
        v6[6] = Parameters[2];
        goto LABEL_54;
      }
    }
    LastError = 87;
    goto LABEL_39;
  }
  LastError = 0;
  if ( IsValidSecurityDescriptor(v9) )
  {
    while ( 1 )
    {
      dwBufferLength = SecurityDescriptorLength;
      if ( MakeSelfRelativeSD(v9, v7, &dwBufferLength) )
        break;
      if ( GetLastError() == 1361 )
      {
        SecurityDescriptorLength = GetSecurityDescriptorLength(v9);
        v7 = v9;
LABEL_21:
        v10 = (char *)VirtualDiskHandle;
        v13 = SecurityDescriptorLength + 56;
        goto LABEL_37;
      }
      if ( v7 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      v7 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, dwBufferLength);
      if ( !v7 )
        goto LABEL_23;
      SecurityDescriptorLength = dwBufferLength;
    }
    if ( v7 )
      goto LABEL_21;
LABEL_23:
    LastError = 14;
  }
LABEL_24:
  RevertManageVolumePrivilege(TokenHandle);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v7 && v7 != v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( (Microsoft_Windows_VIRTDISKEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v14, VirtdiskAttachStop, LastError);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1ea7e73471d83c272d67ddaccec018cc_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180009b90  mov     rax, rsp
0x180009b93  mov     [rax+18h], rbx
0x180009b97  mov     [rax+20h], r9d
0x180009b9b  mov     [rax+10h], rdx
0x180009b9f  mov     [rax+8], rcx
0x180009ba3  push    rbp
0x180009ba4  push    rsi
0x180009ba5  push    rdi
0x180009ba6  push    r12
0x180009ba8  push    r13
0x180009baa  push    r14
0x180009bac  push    r15
0x180009bae  mov     rbp, rsp
0x180009bb1  sub     rsp, 70h
0x180009bb5  xor     edi, edi
0x180009bb7  xor     r14d, r14d
0x180009bba  test    cs:Microsoft_Windows_VIRTDISKEnableBits, 1
0x180009bc1  xorps   xmm0, xmm0
0x180009bc4  mov     r15d, r8d
0x180009bc7  mov     [rbp+BytesReturned], edi
0x180009bca  mov     r13, rdx
0x180009bcd  mov     rbx, rcx
0x180009bd0  movups  xmmword ptr [rbp+TokenHandle], xmm0
0x180009bd4  jz      short loc_180009BE5
0x180009bd6  mov     r8, rcx
0x180009bd9  lea     rdx, VirtdiskAttachStart
0x180009be0  call    McTemplateU0p_EventWriteTransfer
0x180009be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bec  lea     rsi, WPP_GLOBAL_Control
0x180009bf3  cmp     rcx, rsi
0x180009bf6  jz      short loc_180009C19
0x180009bf8  test    byte ptr [rcx+1Ch], 20h
0x180009bfc  jz      short loc_180009C19
0x180009bfe  cmp     byte ptr [rcx+19h], 4
0x180009c02  jb      short loc_180009C19
0x180009c04  mov     rcx, [rcx+10h]
0x180009c08  lea     r8, WPP_1ea7e73471d83c272d67ddaccec018cc_Traceguids
0x180009c0f  mov     edx, 0Ah
0x180009c14  call    WPP_SF_
0x180009c19  lea     rax, [rbx-1]
0x180009c1d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009c21  ja      loc_180009F56
0x180009c27  test    r15d, 0FFFFF800h
0x180009c2e  jz      short loc_180009C3A
0x180009c30  mov     ebx, 57h ; 'W'
0x180009c35  jmp     loc_180009D30
0x180009c3a  mov     r12, [rbp+Parameters]
0x180009c3e  test    r12, r12
0x180009c41  jz      short loc_180009C4E
0x180009c43  mov     eax, [r12]
0x180009c47  dec     eax
0x180009c49  cmp     eax, 1
0x180009c4c  ja      short loc_180009C30
0x180009c4e  xor     esi, esi
0x180009c50  test    r13, r13
0x180009c53  jz      loc_180009DE7
0x180009c59  mov     rcx, r13; pSecurityDescriptor
0x180009c5c  xor     ebx, ebx
0x180009c5e  call    cs:__imp_IsValidSecurityDescriptor
0x180009c65  nop     dword ptr [rax+rax+00h]
0x180009c6a  test    eax, eax
0x180009c6c  jz      loc_180009D29
0x180009c72  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180009c76  mov     [rbp+dwBufferLength], esi
0x180009c79  mov     rdx, r14; pSelfRelativeSecurityDescriptor
0x180009c7c  mov     rcx, r13; pAbsoluteSecurityDescriptor
0x180009c7f  mov     rbx, r14
0x180009c82  call    cs:__imp_MakeSelfRelativeSD
0x180009c89  nop     dword ptr [rax+rax+00h]
0x180009c8e  test    eax, eax
0x180009c90  jnz     loc_180009D1F
0x180009c96  call    cs:__imp_GetLastError
0x180009c9d  nop     dword ptr [rax+rax+00h]
0x180009ca2  cmp     eax, 551h
0x180009ca7  jz      short loc_180009CFE
0x180009ca9  test    r14, r14
0x180009cac  jz      short loc_180009CCC
0x180009cae  mov     rcx, gs:60h
0x180009cb7  mov     r8, r14; P
0x180009cba  xor     edx, edx; Flags
0x180009cbc  mov     rcx, [rcx+30h]; HeapHandle
0x180009cc0  call    cs:__imp_RtlFreeHeap
0x180009cc7  nop     dword ptr [rax+rax+00h]
0x180009ccc  mov     rcx, gs:60h
0x180009cd5  mov     edx, 8; Flags
0x180009cda  mov     r8d, [rbp+dwBufferLength]; Size
0x180009cde  mov     rcx, [rcx+30h]; HeapHandle
0x180009ce2  call    cs:__imp_RtlAllocateHeap
0x180009ce9  nop     dword ptr [rax+rax+00h]
0x180009cee  mov     r14, rax
0x180009cf1  test    rax, rax
0x180009cf4  jz      short loc_180009D24
0x180009cf6  mov     esi, [rbp+dwBufferLength]
0x180009cf9  jmp     loc_180009C72
0x180009cfe  mov     rcx, r13; pSecurityDescriptor
0x180009d01  call    cs:__imp_GetSecurityDescriptorLength
0x180009d08  nop     dword ptr [rax+rax+00h]
0x180009d0d  mov     esi, eax
0x180009d0f  mov     r14, r13
0x180009d12  mov     rbx, [rbp+hDevice]
0x180009d16  lea     r13d, [rsi+38h]
0x180009d1a  jmp     loc_180009DED
0x180009d1f  test    rbx, rbx
0x180009d22  jnz     short loc_180009D12
0x180009d24  mov     ebx, 0Eh
0x180009d29  lea     rsi, WPP_GLOBAL_Control
0x180009d30  lea     rcx, [rbp+TokenHandle]
0x180009d34  call    RevertManageVolumePrivilege
0x180009d39  test    rdi, rdi
0x180009d3c  jz      short loc_180009D5C
0x180009d3e  mov     rcx, gs:60h
0x180009d47  mov     r8, rdi; P
0x180009d4a  xor     edx, edx; Flags
0x180009d4c  mov     rcx, [rcx+30h]; HeapHandle
0x180009d50  call    cs:__imp_RtlFreeHeap
0x180009d57  nop     dword ptr [rax+rax+00h]
0x180009d5c  test    r14, r14
0x180009d5f  jz      short loc_180009D84
0x180009d61  cmp     r14, r13
0x180009d64  jz      short loc_180009D84
0x180009d66  mov     rcx, gs:60h
0x180009d6f  mov     r8, r14; P
0x180009d72  xor     edx, edx; Flags
0x180009d74  mov     rcx, [rcx+30h]; HeapHandle
0x180009d78  call    cs:__imp_RtlFreeHeap
0x180009d7f  nop     dword ptr [rax+rax+00h]
0x180009d84  test    cs:Microsoft_Windows_VIRTDISKEnableBits, 1
0x180009d8b  jz      short loc_180009D9C
0x180009d8d  mov     r8d, ebx
0x180009d90  lea     rdx, VirtdiskAttachStop
0x180009d97  call    McTemplateU0q_EventWriteTransfer
0x180009d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009da3  cmp     rcx, rsi
0x180009da6  jz      short loc_180009DCC
0x180009da8  test    byte ptr [rcx+1Ch], 20h
0x180009dac  jz      short loc_180009DCC
0x180009dae  cmp     byte ptr [rcx+19h], 4
0x180009db2  jb      short loc_180009DCC
0x180009db4  mov     rcx, [rcx+10h]
0x180009db8  lea     r8, WPP_1ea7e73471d83c272d67ddaccec018cc_Traceguids
0x180009dbf  mov     edx, 0Bh
0x180009dc4  mov     r9d, ebx
0x180009dc7  call    WPP_SF_d
0x180009dcc  mov     eax, ebx
0x180009dce  mov     rbx, [rsp+70h+arg_10]
0x180009dd6  add     rsp, 70h
0x180009dda  pop     r15
0x180009ddc  pop     r14
0x180009dde  pop     r13
0x180009de0  pop     r12
0x180009de2  pop     rdi
0x180009de3  pop     rsi
0x180009de4  pop     rbp
0x180009de5  retn
0x180009de7  mov     r13d, 38h ; '8'
0x180009ded  mov     rcx, gs:60h
0x180009df6  mov     edx, 8; Flags
0x180009dfb  mov     r8d, r13d; Size
0x180009dfe  mov     rcx, [rcx+30h]; HeapHandle
0x180009e02  call    cs:__imp_RtlAllocateHeap
0x180009e09  nop     dword ptr [rax+rax+00h]
0x180009e0e  mov     rdi, rax
0x180009e11  test    rax, rax
0x180009e14  jnz     short loc_180009E22
0x180009e16  lea     ebx, [rax+0Eh]
0x180009e19  mov     r13, [rbp+arg_8]
0x180009e1d  jmp     loc_180009D29
0x180009e22  mov     dword ptr [rax], 1
0x180009e28  mov     [rax+4], r15d
0x180009e2c  mov     eax, [rbp+arg_18]
0x180009e2f  mov     [rdi+8], eax
0x180009e32  test    r14, r14
0x180009e35  jz      short loc_180009E50
0x180009e37  mov     r8d, esi; Size
0x180009e3a  lea     rcx, [rdi+38h]; void *
0x180009e3e  mov     rdx, r14; Src
0x180009e41  mov     dword ptr [rdi+0Ch], 38h ; '8'
0x180009e48  mov     [rdi+10h], esi
0x180009e4b  call    memcpy_0
0x180009e50  bt      r15d, 8
0x180009e55  jnb     short loc_180009EC8
0x180009e57  and     r15b, 0C0h
0x180009e5b  cmp     r15b, 40h ; '@'
0x180009e5f  jnz     short loc_180009EBE
0x180009e61  lea     rax, [rdi+30h]
0x180009e65  mov     [rbp+var_18], 0
0x180009e6d  lea     rcx, [rdi+28h]
0x180009e71  mov     qword ptr [rsp+70h+nOutBufferSize], rax; __int64
0x180009e76  mov     [rsp+70h+lpOutBuffer], rcx; __int64
0x180009e7b  lea     r9, [rbp+var_20]
0x180009e7f  mov     rcx, rbx; hFile
0x180009e82  mov     [rbp+var_20], 0
0x180009e8a  lea     r8, [rbp+var_18]
0x180009e8e  mov     [rbp+var_2C], 0
0x180009e95  lea     rdx, [rbp+var_2C]
0x180009e99  call    ParseVirtualDiskPartitionTable
0x180009e9e  mov     ebx, eax
0x180009ea0  test    eax, eax
0x180009ea2  jnz     loc_180009E19
0x180009ea8  cmp     [rbp+var_2C], eax
0x180009eab  jnz     short loc_180009EB7
0x180009ead  mov     ebx, 6F9h
0x180009eb2  jmp     loc_180009E19
0x180009eb7  bts     dword ptr [rdi+4], 7
0x180009ebc  jmp     short loc_180009EF1
0x180009ebe  mov     ebx, 57h ; 'W'
0x180009ec3  jmp     loc_180009E19
0x180009ec8  test    r15b, r15b
0x180009ecb  jns     short loc_180009EF1
0x180009ecd  test    r15b, 40h
0x180009ed1  jz      short loc_180009EBE
0x180009ed3  test    r12, r12
0x180009ed6  jz      short loc_180009EBE
0x180009ed8  cmp     dword ptr [r12], 2
0x180009edd  jnz     short loc_180009EBE
0x180009edf  mov     rax, [r12+8]
0x180009ee4  mov     [rdi+28h], rax
0x180009ee8  mov     rax, [r12+10h]
0x180009eed  mov     [rdi+30h], rax
0x180009ef1  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x180009ef5  call    TryEnableManageVolumePrivilege
0x180009efa  mov     rax, [rbp+Overlapped]
0x180009efe  mov     r9d, r13d; nInBufferSize
0x180009f01  mov     rcx, [rbp+hDevice]; hDevice
0x180009f05  mov     r8, rdi; lpInBuffer
0x180009f08  mov     [rsp+70h+lpOverlapped], rax; lpOverlapped
0x180009f0d  mov     edx, 2D191Ch; dwIoControlCode
0x180009f12  lea     rax, [rbp+BytesReturned]
0x180009f16  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x180009f1b  mov     [rsp+70h+nOutBufferSize], 0; nOutBufferSize
0x180009f23  mov     [rsp+70h+lpOutBuffer], 0; lpOutBuffer
0x180009f2c  call    cs:__imp_DeviceIoControl
0x180009f33  nop     dword ptr [rax+rax+00h]
0x180009f38  test    eax, eax
0x180009f3a  jnz     short loc_180009F4F
0x180009f3c  call    cs:__imp_GetLastError
0x180009f43  nop     dword ptr [rax+rax+00h]
0x180009f48  mov     ebx, eax
0x180009f4a  jmp     loc_180009E19
0x180009f4f  xor     ebx, ebx
0x180009f51  jmp     loc_180009E19
0x180009f56  mov     ebx, 6
0x180009f5b  jmp     loc_180009D30
```

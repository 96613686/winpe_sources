# WsGetUserInfo

- ea: `0x180005b50`
- end: `0x180005ddb`
- name: `WsGetUserInfo`
- size: `651`
- prototype: `__int64 __usercall@<rax>(PLUID SourceLuid@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d584`

## callees

- `0x180005504`
- `0x180005b50`
- `0x180005df0`
- `0x18001fbd0`
- `0x1800204f6`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180005bc6`
- `ntdll!RtlCopyLuid` at `0x180005ccb`
- `ntdll!RtlCopyLuid` at `0x180005bc6`
- `ntdll!RtlCopyLuid` at `0x180005ccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005c23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005c23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005db5`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180005c03`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180005c03`

## pseudocode

```c
__int64 __fastcall WsGetUserInfo(PLUID SourceLuid, int a2, PVOID *a3, HLOCAL *a4, unsigned int *a5, unsigned int *a6)
{
  unsigned int v10; // eax
  unsigned int v11; // ebp
  __int64 result; // rax
  unsigned __int16 *v13; // rdx
  int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // eax
  unsigned int i; // edx
  unsigned int v18; // ecx
  int ProtocolStatus; // [rsp+50h] [rbp-C8h] BYREF
  ULONG ReturnBufferLength; // [rsp+54h] [rbp-C4h] BYREF
  int ProtocolSubmitBuffer; // [rsp+58h] [rbp-C0h] BYREF
  struct _LUID DestinationLuid; // [rsp+5Ch] [rbp-BCh] BYREF
  _DWORD v23[2]; // [rsp+70h] [rbp-A8h] BYREF
  _BYTE v24[4]; // [rsp+78h] [rbp-A0h] BYREF
  struct _LUID v25; // [rsp+7Ch] [rbp-9Ch] BYREF
  unsigned int v26; // [rsp+A8h] [rbp-70h]
  __int64 v27; // [rsp+B0h] [rbp-68h]

  ReturnBufferLength = 0;
  if ( a2 != 1 && a2 != 1101 )
    goto LABEL_3;
  memset_0(v24, 0, 0x58u);
  if ( !WsDgReceiverDeviceHandle )
  {
    if ( a6 )
      *a6 += 2;
    *a5 = 0;
    *a4 = 0;
LABEL_23:
    if ( a2 == 1101 )
    {
      v18 = *a6 + 8;
      if ( v18 < *a6 )
      {
LABEL_11:
        *a6 = -1;
        return 2140;
      }
      *a6 = v18;
      return 0;
    }
LABEL_3:
    ProtocolStatus = 0;
    DestinationLuid = 0;
    ProtocolSubmitBuffer = 3;
    RtlCopyLuid(&DestinationLuid, SourceLuid);
    v10 = LsaCallAuthenticationPackage(
            LsaHandle,
            AuthenticationPackage,
            &ProtocolSubmitBuffer,
            0xCu,
            a3,
            &ReturnBufferLength,
            &ProtocolStatus);
    if ( v10 || (v10 = ProtocolStatus) != 0 )
    {
      v11 = WsMapStatus(v10);
      if ( v11 )
      {
        LocalFree(*a4);
        *a4 = 0;
        result = v11;
        *a5 = 0;
        return result;
      }
    }
    if ( a6 )
    {
      v13 = (unsigned __int16 *)*a3;
      if ( a2 )
        v14 = v13[16] + v13[24] + v13[8] + 38;
      else
        v14 = v13[8] + 10;
      v15 = *a6 + v14;
      if ( v15 < *a6 )
        goto LABEL_11;
      *a6 = v15;
    }
    return 0;
  }
  v23[1] = 6;
  v23[0] = 0;
  RtlCopyLuid(&v25, SourceLuid);
  v27 = 0;
  result = WsDeviceControlGetInfo(1, WsDgReceiverDeviceHandle, 1245207, v23, 96, a4, -1, 0);
  if ( !(_DWORD)result )
  {
    if ( a6 )
      *a6 += 2;
    v16 = v26;
    *a5 = v26;
    if ( !v16 && *a4 )
    {
      LocalFree(*a4);
      *a4 = 0;
    }
    if ( a6 )
    {
      for ( i = 0; i < *a5; ++i )
      {
        if ( *((_DWORD *)*a4 + 6 * i + 4) == 4 )
          *a6 += *((unsigned __int16 *)*a4 + 12 * i) + 2;
      }
    }
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x180005b50  push    rbx
0x180005b52  push    rbp
0x180005b53  push    rsi
0x180005b54  push    rdi
0x180005b55  push    r12
0x180005b57  push    r14
0x180005b59  push    r15
0x180005b5b  sub     rsp, 0E0h
0x180005b62  mov     rax, cs:__security_cookie
0x180005b69  xor     rax, rsp
0x180005b6c  mov     [rsp+118h+var_48], rax
0x180005b74  mov     r15, [rsp+118h+arg_20]
0x180005b7c  xor     r12d, r12d
0x180005b7f  mov     rbx, [rsp+118h+arg_28]
0x180005b87  mov     r14, r9
0x180005b8a  mov     [rsp+118h+var_C4], r12d
0x180005b8f  mov     rsi, r8
0x180005b92  mov     edi, edx
0x180005b94  mov     rbp, rcx
0x180005b97  cmp     edx, 1
0x180005b9a  jz      loc_180005C97
0x180005ba0  cmp     edx, 44Dh
0x180005ba6  jz      loc_180005C97
0x180005bac  mov     rdx, rbp; SourceLuid
0x180005baf  mov     [rsp+118h+var_C8], r12d
0x180005bb4  lea     rcx, [rsp+118h+DestinationLuid]; DestinationLuid
0x180005bb9  mov     qword ptr [rsp+118h+DestinationLuid.LowPart], r12
0x180005bbe  mov     [rsp+118h+ProtocolSubmitBuffer], 3
0x180005bc6  call    cs:__imp_RtlCopyLuid
0x180005bcd  nop     dword ptr [rax+rax+00h]
0x180005bd2  mov     edx, cs:AuthenticationPackage; AuthenticationPackage
0x180005bd8  lea     rax, [rsp+118h+var_C8]
0x180005bdd  mov     rcx, cs:LsaHandle; LsaHandle
0x180005be4  lea     r8, [rsp+118h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x180005be9  mov     [rsp+118h+ProtocolStatus], rax; ProtocolStatus
0x180005bee  mov     r9d, 0Ch; SubmitBufferLength
0x180005bf4  lea     rax, [rsp+118h+var_C4]
0x180005bf9  mov     [rsp+118h+ReturnBufferLength], rax; ReturnBufferLength
0x180005bfe  mov     [rsp+118h+ProtocolReturnBuffer], rsi; ProtocolReturnBuffer
0x180005c03  call    cs:__imp_LsaCallAuthenticationPackage
0x180005c0a  nop     dword ptr [rax+rax+00h]
0x180005c0f  test    eax, eax
0x180005c11  jz      short loc_180005C39
0x180005c13  mov     ecx, eax
0x180005c15  call    WsMapStatus
0x180005c1a  mov     ebp, eax
0x180005c1c  test    eax, eax
0x180005c1e  jz      short loc_180005C41
0x180005c20  mov     rcx, [r14]; hMem
0x180005c23  call    cs:__imp_LocalFree
0x180005c2a  nop     dword ptr [rax+rax+00h]
0x180005c2f  mov     [r14], r12
0x180005c32  mov     eax, ebp
0x180005c34  mov     [r15], r12d
0x180005c37  jmp     short loc_180005C74
0x180005c39  mov     eax, [rsp+118h+var_C8]
0x180005c3d  test    eax, eax
0x180005c3f  jnz     short loc_180005C13
0x180005c41  test    rbx, rbx
0x180005c44  jz      loc_180005D72
0x180005c4a  mov     rdx, [rsi]
0x180005c4d  test    edi, edi
0x180005c4f  jnz     loc_180005D79
0x180005c55  movzx   eax, word ptr [rdx+10h]
0x180005c59  add     eax, 0Ah
0x180005c5c  mov     ecx, [rbx]
0x180005c5e  lea     edx, [rcx+rax]
0x180005c61  cmp     edx, ecx
0x180005c63  jnb     loc_180005DD7
0x180005c69  mov     dword ptr [rbx], 0FFFFFFFFh
0x180005c6f  mov     eax, 85Ch
0x180005c74  mov     rcx, [rsp+118h+var_48]
0x180005c7c  xor     rcx, rsp; StackCookie
0x180005c7f  call    __security_check_cookie
0x180005c84  add     rsp, 0E0h
0x180005c8b  pop     r15
0x180005c8d  pop     r14
0x180005c8f  pop     r12
0x180005c91  pop     rdi
0x180005c92  pop     rsi
0x180005c93  pop     rbp
0x180005c94  pop     rbx
0x180005c95  retn
0x180005c97  xor     edx, edx; Val
0x180005c99  lea     rcx, [rsp+118h+var_A0]; void *
0x180005c9e  mov     r8d, 58h ; 'X'; Size
0x180005ca4  call    memset_0
0x180005ca9  cmp     cs:WsDgReceiverDeviceHandle, r12
0x180005cb0  jz      loc_180005D91
0x180005cb6  mov     rdx, rbp; SourceLuid
0x180005cb9  mov     [rsp+118h+var_A4], 6
0x180005cc1  lea     rcx, [rsp+118h+var_9C]; DestinationLuid
0x180005cc6  mov     [rsp+118h+var_A8], r12d
0x180005ccb  call    cs:__imp_RtlCopyLuid
0x180005cd2  nop     dword ptr [rax+rax+00h]
0x180005cd7  mov     rdx, cs:WsDgReceiverDeviceHandle
0x180005cde  lea     r9, [rsp+118h+var_A8]
0x180005ce3  mov     [rsp+118h+var_E0], r12d
0x180005ce8  mov     r8d, 130017h
0x180005cee  mov     dword ptr [rsp+118h+ProtocolStatus], 0FFFFFFFFh
0x180005cf6  mov     ecx, 1
0x180005cfb  mov     [rsp+118h+ReturnBufferLength], r14
0x180005d00  mov     dword ptr [rsp+118h+ProtocolReturnBuffer], 60h ; '`'
0x180005d08  mov     [rsp+118h+var_68], r12
0x180005d10  call    WsDeviceControlGetInfo
0x180005d15  test    eax, eax
0x180005d17  jnz     loc_180005C74
0x180005d1d  test    rbx, rbx
0x180005d20  jnz     short loc_180005DA1
0x180005d22  mov     eax, [rsp+118h+var_70]
0x180005d29  mov     [r15], eax
0x180005d2c  test    eax, eax
0x180005d2e  jz      short loc_180005DA9
0x180005d30  test    rbx, rbx
0x180005d33  jz      short loc_180005D57
0x180005d35  mov     edx, r12d
0x180005d38  cmp     [r15], r12d
0x180005d3b  jbe     short loc_180005D57
0x180005d3d  nop     dword ptr [rax]
0x180005d40  mov     eax, edx
0x180005d42  lea     rcx, [rax+rax*2]
0x180005d46  mov     rax, [r14]
0x180005d49  cmp     dword ptr [rax+rcx*8+10h], 4
0x180005d4e  jz      short loc_180005DC9
0x180005d50  inc     edx
0x180005d52  cmp     edx, [r15]
0x180005d55  jb      short loc_180005D40
0x180005d57  cmp     edi, 44Dh
0x180005d5d  jnz     loc_180005BAC
0x180005d63  mov     eax, [rbx]
0x180005d65  lea     ecx, [rax+8]
0x180005d68  cmp     ecx, eax
0x180005d6a  jb      loc_180005C69
0x180005d70  mov     [rbx], ecx
0x180005d72  xor     eax, eax
0x180005d74  jmp     loc_180005C74
0x180005d79  movzx   eax, word ptr [rdx+20h]
0x180005d7d  movzx   ecx, word ptr [rdx+30h]
0x180005d81  add     ecx, eax
0x180005d83  movzx   eax, word ptr [rdx+10h]
0x180005d87  add     eax, 26h ; '&'
0x180005d8a  add     eax, ecx
0x180005d8c  jmp     loc_180005C5C
0x180005d91  test    rbx, rbx
0x180005d94  jz      short loc_180005D99
0x180005d96  add     dword ptr [rbx], 2
0x180005d99  mov     [r15], r12d
0x180005d9c  mov     [r14], r12
0x180005d9f  jmp     short loc_180005D57
0x180005da1  add     dword ptr [rbx], 2
0x180005da4  jmp     loc_180005D22
0x180005da9  mov     rcx, [r14]; hMem
0x180005dac  test    rcx, rcx
0x180005daf  jz      loc_180005D30
0x180005db5  call    cs:__imp_LocalFree
0x180005dbc  nop     dword ptr [rax+rax+00h]
0x180005dc1  mov     [r14], r12
0x180005dc4  jmp     loc_180005D30
0x180005dc9  movzx   eax, word ptr [rax+rcx*8]
0x180005dcd  add     eax, 2
0x180005dd0  add     [rbx], eax
0x180005dd2  jmp     loc_180005D50
0x180005dd7  mov     [rbx], edx
0x180005dd9  jmp     short loc_180005D72
```

# ConfigCiSecurityPolicyCheck

- ea: `0x140002b90`
- end: `0x140002df8`
- name: `ConfigCiSecurityPolicyCheck`
- size: `616`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140002e00`

## callees

- `0x140002b90`
- `0x140004bd0`
- `0x140009010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002de5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002de5`
- `ntdll!RtlRunOnceExecuteOnce` at `0x140002c15`
- `ntdll!RtlRunOnceExecuteOnce` at `0x140002c15`
- `ntdll!NtQuerySystemInformation` at `0x140002bdd`
- `ntdll!NtQuerySystemInformation` at `0x140002bdd`
- `ntdll!RtlNtStatusToDosError` at `0x140002c21`
- `ntdll!RtlNtStatusToDosError` at `0x140002c21`

## pseudocode

```c
__int64 __fastcall ConfigCiSecurityPolicyCheck(__int64 a1, char *a2)
{
  NTSTATUS v4; // eax
  ULONG v5; // ebx
  __int64 v6; // r8
  int v7; // eax
  char *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  bool v12; // zf
  int v13; // ecx
  int v14; // eax
  _DWORD v15[2]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v16; // [rsp+38h] [rbp-71h] BYREF
  __int64 v17; // [rsp+40h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR SystemInformation[2]; // [rsp+58h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-29h] BYREF
  void *v21; // [rsp+90h] [rbp-19h]
  int v22; // [rsp+98h] [rbp-11h]
  int v23; // [rsp+9Ch] [rbp-Dh]
  char *v24; // [rsp+A0h] [rbp-9h]
  int v25; // [rsp+A8h] [rbp-1h]
  int v26; // [rsp+ACh] [rbp+3h]
  char *v27; // [rsp+B0h] [rbp+7h]
  int v28; // [rsp+B8h] [rbp+Fh]
  int v29; // [rsp+BCh] [rbp+13h]
  __int64 *v30; // [rsp+C0h] [rbp+17h]
  __int64 v31; // [rsp+C8h] [rbp+1Fh]
  __int64 *v32; // [rsp+D0h] [rbp+27h]
  __int64 v33; // [rsp+D8h] [rbp+2Fh]

  v15[0] = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  if ( NtQuerySystemInformation(SystemContextSwitchInformation|0x80, SystemInformation, 0x20u, 0) < 0
    || (SystemInformation[0].Ptr & 0x50) != 0x50 )
  {
    return 0;
  }
  v4 = RtlRunOnceExecuteOnce(&unk_14000F170, LoadWldpLibrary, 0, 0);
  if ( v4 < 0 )
  {
    v5 = RtlNtStatusToDosError(v4);
    v6 = 1;
    goto LABEL_11;
  }
  if ( !WldpModuleHandle || !IsAllowedEntryPoint )
  {
    v6 = 2;
LABEL_18:
    v5 = 5;
LABEL_19:
    if ( (unsigned int)dword_14000F000 > 5 )
    {
      v9 = *(char **)(a1 + 24);
      v10 = -1;
      if ( v9 )
      {
        v11 = -1;
        do
          v12 = *(_WORD *)&v9[2 * v11++ + 2] == 0;
        while ( !v12 );
        v13 = 2 * v11 + 2;
      }
      else
      {
        v9 = "";
        v13 = 2;
      }
      v24 = v9;
      v25 = v13;
      v26 = 0;
      if ( a2 )
      {
        do
          v12 = *(_WORD *)&a2[2 * v10++ + 2] == 0;
        while ( !v12 );
        v14 = 2 * v10 + 2;
      }
      else
      {
        a2 = "";
        v14 = 2;
      }
      v28 = v14;
      v16 = v6;
      v30 = &v16;
      v27 = a2;
      v29 = 0;
      v31 = 8;
      v33 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      v17 = v5;
      v32 = &v17;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000F008;
      UserData.Size = *(unsigned __int16 *)off_14000F008;
      v21 = &unk_14000BB02;
      UserData.Reserved = 2;
      v22 = 83;
      v23 = 1;
      v15[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
    }
    return v5;
  }
  v7 = IsAllowedEntryPoint(1, *(_QWORD *)(a1 + 16), a2, v15);
  v5 = v7;
  if ( v7 >= 0 )
  {
    if ( v15[0] )
      return 0;
    v6 = 4;
    goto LABEL_18;
  }
  if ( (v7 & 0x1FFF0000) == 0x70000 )
    v5 = (unsigned __int16)v7;
  v6 = 3;
LABEL_11:
  if ( v5 )
    goto LABEL_19;
  return v5;
}

```

## disassembly

```asm
0x140002b90  mov     [rsp-8+arg_18], rsi
0x140002b95  push    rbp
0x140002b96  push    rdi
0x140002b97  push    r14
0x140002b99  lea     rbp, [rsp-47h]
0x140002b9e  sub     rsp, 0F0h
0x140002ba5  mov     rax, cs:__security_cookie
0x140002bac  xor     rax, rsp
0x140002baf  mov     [rbp+57h+var_20], rax
0x140002bb3  xorps   xmm0, xmm0
0x140002bb6  mov     rdi, rdx
0x140002bb9  mov     rsi, rcx
0x140002bbc  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x140002bc0  xor     r14d, r14d
0x140002bc3  mov     ecx, 0A4h; SystemInformationClass
0x140002bc8  xor     r9d, r9d; ReturnLength
0x140002bcb  mov     [rbp+57h+var_D0], r14d
0x140002bcf  mov     r8d, 20h ; ' '; SystemInformationLength
0x140002bd5  movups  [rbp+57h+SystemInformation], xmm0
0x140002bd9  movups  [rbp+57h+var_98], xmm0
0x140002bdd  call    cs:__imp_NtQuerySystemInformation
0x140002be3  test    eax, eax
0x140002be5  js      loc_140002DF0
0x140002beb  mov     eax, dword ptr [rbp+57h+SystemInformation]
0x140002bee  and     eax, 50h
0x140002bf1  cmp     al, 50h ; 'P'
0x140002bf3  jnz     loc_140002DF0
0x140002bf9  xor     r9d, r9d
0x140002bfc  mov     [rsp+100h+arg_10], rbx
0x140002c04  xor     r8d, r8d
0x140002c07  lea     rdx, LoadWldpLibrary
0x140002c0e  lea     rcx, unk_14000F170
0x140002c15  call    cs:__imp_RtlRunOnceExecuteOnce
0x140002c1b  test    eax, eax
0x140002c1d  jns     short loc_140002C31
0x140002c1f  mov     ecx, eax; Status
0x140002c21  call    cs:__imp_RtlNtStatusToDosError
0x140002c27  mov     ebx, eax
0x140002c29  mov     r8d, 1
0x140002c2f  jmp     short loc_140002C76
0x140002c31  cmp     cs:WldpModuleHandle, r14
0x140002c38  jz      short loc_140002CB7
0x140002c3a  mov     rax, cs:IsAllowedEntryPoint
0x140002c41  test    rax, rax
0x140002c44  jz      short loc_140002CB7
0x140002c46  mov     rdx, [rsi+10h]
0x140002c4a  lea     r9, [rbp+57h+var_D0]
0x140002c4e  mov     r8, rdi
0x140002c51  mov     ecx, 1
0x140002c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c5b  mov     ebx, eax
0x140002c5d  test    eax, eax
0x140002c5f  jns     short loc_140002CA4
0x140002c61  and     eax, 1FFF0000h
0x140002c66  cmp     eax, 70000h
0x140002c6b  jnz     short loc_140002C70
0x140002c6d  movzx   ebx, bx
0x140002c70  mov     r8d, 3
0x140002c76  test    ebx, ebx
0x140002c78  jnz     short loc_140002CC2
0x140002c7a  mov     eax, ebx
0x140002c7c  mov     rbx, [rsp+100h+arg_10]
0x140002c84  mov     rcx, [rbp+57h+var_20]
0x140002c88  xor     rcx, rsp; StackCookie
0x140002c8b  call    __security_check_cookie
0x140002c90  mov     rsi, [rsp+100h+arg_18]
0x140002c98  add     rsp, 0F0h
0x140002c9f  pop     r14
0x140002ca1  pop     rdi
0x140002ca2  pop     rbp
0x140002ca3  retn
0x140002ca4  cmp     [rbp+57h+var_D0], r14d
0x140002ca8  jnz     short loc_140002CB2
0x140002caa  mov     r8d, 4
0x140002cb0  jmp     short loc_140002CBD
0x140002cb2  mov     eax, r14d
0x140002cb5  jmp     short loc_140002C7C
0x140002cb7  mov     r8d, 2
0x140002cbd  mov     ebx, 5
0x140002cc2  mov     eax, cs:dword_14000F000
0x140002cc8  cmp     eax, 5
0x140002ccb  jbe     short loc_140002C7A
0x140002ccd  mov     rdx, [rsi+18h]
0x140002cd1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002cd8  test    rdx, rdx
0x140002cdb  jz      short loc_140002CF5
0x140002cdd  mov     rcx, rax
0x140002ce0  cmp     [rdx+rcx*2+2], r14w
0x140002ce6  lea     rcx, [rcx+1]
0x140002cea  jnz     short loc_140002CE0
0x140002cec  lea     ecx, ds:2[rcx*2]
0x140002cf3  jmp     short loc_140002D01
0x140002cf5  lea     rdx, aNourlmimefilte+10h; ""
0x140002cfc  mov     ecx, 2
0x140002d01  mov     [rbp+57h+var_60], rdx
0x140002d05  mov     [rbp+57h+var_58], ecx
0x140002d08  mov     [rbp+57h+var_54], r14d
0x140002d0c  test    rdi, rdi
0x140002d0f  jz      short loc_140002D26
0x140002d11  cmp     [rdi+rax*2+2], r14w
0x140002d17  lea     rax, [rax+1]
0x140002d1b  jnz     short loc_140002D11
0x140002d1d  lea     eax, ds:2[rax*2]
0x140002d24  jmp     short loc_140002D32
0x140002d26  lea     rdi, aNourlmimefilte+10h; ""
0x140002d2d  mov     eax, 2
0x140002d32  mov     [rbp+57h+var_48], eax
0x140002d35  lea     rcx, _TraceLoggingMetadata
0x140002d3c  mov     [rbp+57h+var_C8], r8
0x140002d40  lea     rax, [rbp+57h+var_C8]
0x140002d44  mov     [rbp+57h+var_40], rax
0x140002d48  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002d4c  mov     [rbp+57h+var_50], rdi
0x140002d50  xor     r9d, r9d; RelatedActivityId
0x140002d53  mov     [rbp+57h+var_44], r14d
0x140002d57  xor     r8d, r8d; ActivityId
0x140002d5a  mov     [rbp+57h+var_38], 8
0x140002d62  mov     [rbp+57h+var_28], 8
0x140002d6a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002d71  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x140002d75  mov     eax, ebx
0x140002d77  mov     [rbp+57h+var_C0], rax
0x140002d7b  lea     rax, [rbp+57h+var_C0]
0x140002d7f  mov     [rbp+57h+var_30], rax
0x140002d83  movzx   eax, cs:word_14000BAF8
0x140002d8a  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140002d8d  mov     rax, cs:off_14000F008
0x140002d94  mov     [rbp+57h+var_80.Ptr], rax
0x140002d98  movzx   eax, word ptr [rax]
0x140002d9b  mov     [rbp+57h+var_80.Size], eax
0x140002d9e  lea     rax, unk_14000BB02
0x140002da5  mov     [rbp+57h+var_70], rax
0x140002da9  lea     rax, _TraceLoggingMetadataEnd
0x140002db0  sub     eax, ecx
0x140002db2  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x140002db9  mov     [rbp+57h+var_68], 53h ; 'S'
0x140002dc0  mov     [rbp+57h+var_64], 1
0x140002dc7  mov     [rbp+57h+var_CC], eax
0x140002dca  mov     eax, [rbp+57h+var_CC]
0x140002dcd  mov     rcx, cs:RegHandle; RegHandle
0x140002dd4  lea     rax, [rbp+57h+var_80]
0x140002dd8  mov     [rsp+100h+UserData], rax; UserData
0x140002ddd  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x140002de5  call    cs:__imp_EventWriteTransfer
0x140002deb  jmp     loc_140002C7A
0x140002df0  mov     eax, r14d
0x140002df3  jmp     loc_140002C84
```

# ConfigCiSecurityPolicyCheck

- ea: `0x140002e20`
- end: `0x1400030a1`
- name: `ConfigCiSecurityPolicyCheck`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400030b0`

## callees

- `0x140002e20`
- `0x140004f90`
- `0x140009010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140003088`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140003088`
- `ntdll!RtlRunOnceExecuteOnce` at `0x140002eab`
- `ntdll!RtlRunOnceExecuteOnce` at `0x140002eab`
- `ntdll!NtQuerySystemInformation` at `0x140002e6d`
- `ntdll!NtQuerySystemInformation` at `0x140002e6d`
- `ntdll!RtlNtStatusToDosError` at `0x140002ebd`
- `ntdll!RtlNtStatusToDosError` at `0x140002ebd`

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
0x140002e20  mov     [rsp-8+arg_18], rsi
0x140002e25  push    rbp
0x140002e26  push    rdi
0x140002e27  push    r14
0x140002e29  lea     rbp, [rsp-47h]
0x140002e2e  sub     rsp, 0F0h
0x140002e35  mov     rax, cs:__security_cookie
0x140002e3c  xor     rax, rsp
0x140002e3f  mov     [rbp+57h+var_20], rax
0x140002e43  xorps   xmm0, xmm0
0x140002e46  mov     rdi, rdx
0x140002e49  mov     rsi, rcx
0x140002e4c  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x140002e50  xor     r14d, r14d
0x140002e53  mov     ecx, 0A4h; SystemInformationClass
0x140002e58  xor     r9d, r9d; ReturnLength
0x140002e5b  mov     [rbp+57h+var_D0], r14d
0x140002e5f  mov     r8d, 20h ; ' '; SystemInformationLength
0x140002e65  movups  [rbp+57h+SystemInformation], xmm0
0x140002e69  movups  [rbp+57h+var_98], xmm0
0x140002e6d  call    cs:__imp_NtQuerySystemInformation
0x140002e74  nop     dword ptr [rax+rax+00h]
0x140002e79  test    eax, eax
0x140002e7b  js      loc_140003099
0x140002e81  mov     eax, dword ptr [rbp+57h+SystemInformation]
0x140002e84  and     eax, 50h
0x140002e87  cmp     al, 50h ; 'P'
0x140002e89  jnz     loc_140003099
0x140002e8f  xor     r9d, r9d
0x140002e92  mov     [rsp+100h+arg_10], rbx
0x140002e9a  xor     r8d, r8d
0x140002e9d  lea     rdx, LoadWldpLibrary
0x140002ea4  lea     rcx, unk_14000F170
0x140002eab  call    cs:__imp_RtlRunOnceExecuteOnce
0x140002eb2  nop     dword ptr [rax+rax+00h]
0x140002eb7  test    eax, eax
0x140002eb9  jns     short loc_140002ED3
0x140002ebb  mov     ecx, eax; Status
0x140002ebd  call    cs:__imp_RtlNtStatusToDosError
0x140002ec4  nop     dword ptr [rax+rax+00h]
0x140002ec9  mov     ebx, eax
0x140002ecb  mov     r8d, 1
0x140002ed1  jmp     short loc_140002F18
0x140002ed3  cmp     cs:WldpModuleHandle, r14
0x140002eda  jz      short loc_140002F5A
0x140002edc  mov     rax, cs:IsAllowedEntryPoint
0x140002ee3  test    rax, rax
0x140002ee6  jz      short loc_140002F5A
0x140002ee8  mov     rdx, [rsi+10h]
0x140002eec  lea     r9, [rbp+57h+var_D0]
0x140002ef0  mov     r8, rdi
0x140002ef3  mov     ecx, 1
0x140002ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002efd  mov     ebx, eax
0x140002eff  test    eax, eax
0x140002f01  jns     short loc_140002F47
0x140002f03  and     eax, 1FFF0000h
0x140002f08  cmp     eax, 70000h
0x140002f0d  jnz     short loc_140002F12
0x140002f0f  movzx   ebx, bx
0x140002f12  mov     r8d, 3
0x140002f18  test    ebx, ebx
0x140002f1a  jnz     short loc_140002F65
0x140002f1c  mov     eax, ebx
0x140002f1e  mov     rbx, [rsp+100h+arg_10]
0x140002f26  mov     rcx, [rbp+57h+var_20]
0x140002f2a  xor     rcx, rsp; StackCookie
0x140002f2d  call    __security_check_cookie
0x140002f32  mov     rsi, [rsp+100h+arg_18]
0x140002f3a  add     rsp, 0F0h
0x140002f41  pop     r14
0x140002f43  pop     rdi
0x140002f44  pop     rbp
0x140002f45  retn
0x140002f47  cmp     [rbp+57h+var_D0], r14d
0x140002f4b  jnz     short loc_140002F55
0x140002f4d  mov     r8d, 4
0x140002f53  jmp     short loc_140002F60
0x140002f55  mov     eax, r14d
0x140002f58  jmp     short loc_140002F1E
0x140002f5a  mov     r8d, 2
0x140002f60  mov     ebx, 5
0x140002f65  mov     eax, cs:dword_14000F000
0x140002f6b  cmp     eax, 5
0x140002f6e  jbe     short loc_140002F1C
0x140002f70  mov     rdx, [rsi+18h]
0x140002f74  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002f7b  test    rdx, rdx
0x140002f7e  jz      short loc_140002F98
0x140002f80  mov     rcx, rax
0x140002f83  cmp     [rdx+rcx*2+2], r14w
0x140002f89  lea     rcx, [rcx+1]
0x140002f8d  jnz     short loc_140002F83
0x140002f8f  lea     ecx, ds:2[rcx*2]
0x140002f96  jmp     short loc_140002FA4
0x140002f98  lea     rdx, aNourlmimefilte+10h; ""
0x140002f9f  mov     ecx, 2
0x140002fa4  mov     [rbp+57h+var_60], rdx
0x140002fa8  mov     [rbp+57h+var_58], ecx
0x140002fab  mov     [rbp+57h+var_54], r14d
0x140002faf  test    rdi, rdi
0x140002fb2  jz      short loc_140002FC9
0x140002fb4  cmp     [rdi+rax*2+2], r14w
0x140002fba  lea     rax, [rax+1]
0x140002fbe  jnz     short loc_140002FB4
0x140002fc0  lea     eax, ds:2[rax*2]
0x140002fc7  jmp     short loc_140002FD5
0x140002fc9  lea     rdi, aNourlmimefilte+10h; ""
0x140002fd0  mov     eax, 2
0x140002fd5  mov     [rbp+57h+var_48], eax
0x140002fd8  lea     rcx, _TraceLoggingMetadata
0x140002fdf  mov     [rbp+57h+var_C8], r8
0x140002fe3  lea     rax, [rbp+57h+var_C8]
0x140002fe7  mov     [rbp+57h+var_40], rax
0x140002feb  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002fef  mov     [rbp+57h+var_50], rdi
0x140002ff3  xor     r9d, r9d; RelatedActivityId
0x140002ff6  mov     [rbp+57h+var_44], r14d
0x140002ffa  xor     r8d, r8d; ActivityId
0x140002ffd  mov     [rbp+57h+var_38], 8
0x140003005  mov     [rbp+57h+var_28], 8
0x14000300d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140003014  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x140003018  mov     eax, ebx
0x14000301a  mov     [rbp+57h+var_C0], rax
0x14000301e  lea     rax, [rbp+57h+var_C0]
0x140003022  mov     [rbp+57h+var_30], rax
0x140003026  movzx   eax, cs:word_14000BAF8
0x14000302d  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140003030  mov     rax, cs:off_14000F008
0x140003037  mov     [rbp+57h+var_80.Ptr], rax
0x14000303b  movzx   eax, word ptr [rax]
0x14000303e  mov     [rbp+57h+var_80.Size], eax
0x140003041  lea     rax, unk_14000BB02
0x140003048  mov     [rbp+57h+var_70], rax
0x14000304c  lea     rax, _TraceLoggingMetadataEnd
0x140003053  sub     eax, ecx
0x140003055  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x14000305c  mov     [rbp+57h+var_68], 53h ; 'S'
0x140003063  mov     [rbp+57h+var_64], 1
0x14000306a  mov     [rbp+57h+var_CC], eax
0x14000306d  mov     eax, [rbp+57h+var_CC]
0x140003070  mov     rcx, cs:RegHandle; RegHandle
0x140003077  lea     rax, [rbp+57h+var_80]
0x14000307b  mov     [rsp+100h+UserData], rax; UserData
0x140003080  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x140003088  call    cs:__imp_EventWriteTransfer
0x14000308f  nop     dword ptr [rax+rax+00h]
0x140003094  jmp     loc_140002F1C
0x140003099  mov     eax, r14d
0x14000309c  jmp     loc_140002F26
```

# WsCreateConfigInfoObject

- ea: `0x180007ecc`
- end: `0x180008040`
- name: `WsCreateConfigInfoObject`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007224`

## callees

- `0x180007cb0`
- `0x180007ecc`
- `0x1800084a0`

## import_xrefs

- `ntdll!NtClose` at `0x180008013`
- `ntdll!NtClose` at `0x180008013`
- `ntdll!NtOpenProcessToken` at `0x180007fca`
- `ntdll!NtOpenProcessToken` at `0x180007fca`
- `ntdll!RtlNewSecurityObject` at `0x180008001`
- `ntdll!RtlNewSecurityObject` at `0x180008001`

## pseudocode

```c
__int64 WsCreateConfigInfoObject()
{
  void *v0; // r8
  int SecurityDescriptor; // ebx
  __int16 v3; // [rsp+30h] [rbp-29h] BYREF
  char v4; // [rsp+32h] [rbp-27h]
  int v5; // [rsp+34h] [rbp-25h]
  __int64 v6; // [rsp+38h] [rbp-21h]
  __int16 v7; // [rsp+40h] [rbp-19h]
  char v8; // [rsp+42h] [rbp-17h]
  int v9; // [rsp+44h] [rbp-15h]
  __int64 v10; // [rsp+48h] [rbp-11h]
  __int16 v11; // [rsp+50h] [rbp-9h]
  char v12; // [rsp+52h] [rbp-7h]
  int v13; // [rsp+54h] [rbp-5h]
  __int64 v14; // [rsp+58h] [rbp-1h]
  __int16 v15; // [rsp+60h] [rbp+7h]
  char v16; // [rsp+62h] [rbp+9h]
  int v17; // [rsp+64h] [rbp+Bh]
  __int64 v18; // [rsp+68h] [rbp+Fh]
  __int16 v19; // [rsp+70h] [rbp+17h]
  char v20; // [rsp+72h] [rbp+19h]
  int v21; // [rsp+74h] [rbp+1Bh]
  __int64 v22; // [rsp+78h] [rbp+1Fh]
  __int16 v23; // [rsp+80h] [rbp+27h]
  char v24; // [rsp+82h] [rbp+29h]
  int v25; // [rsp+84h] [rbp+2Bh]
  __int64 v26; // [rsp+88h] [rbp+2Fh]
  __int16 v27; // [rsp+90h] [rbp+37h]
  char v28; // [rsp+92h] [rbp+39h]
  int v29; // [rsp+94h] [rbp+3Bh]
  __int64 v30; // [rsp+98h] [rbp+3Fh]
  __int16 v31; // [rsp+A0h] [rbp+47h]
  char v32; // [rsp+A2h] [rbp+49h]
  int v33; // [rsp+A4h] [rbp+4Bh]
  __int64 v34; // [rsp+A8h] [rbp+4Fh]
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+C0h] [rbp+67h] BYREF
  void *TokenHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  v3 = 0;
  v4 = 0;
  v7 = 0;
  v8 = 0;
  v5 = 7;
  v6 = WsLmsvcsGlobalData + 16;
  v13 = 7;
  v10 = WsLmsvcsGlobalData + 80;
  v14 = WsLmsvcsGlobalData + 112;
  v18 = WsLmsvcsGlobalData + 120;
  v22 = WsLmsvcsGlobalData + 128;
  v26 = WsLmsvcsGlobalData + 88;
  v30 = WsLmsvcsGlobalData + 8;
  v0 = *(void **)(WsLmsvcsGlobalData + 48);
  v17 = 7;
  v21 = 7;
  v34 = WsLmsvcsGlobalData + 72;
  v29 = 1;
  v33 = 1;
  v9 = 0x10000000;
  v11 = 0;
  v12 = 0;
  v15 = 0;
  v16 = 0;
  v19 = 0;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 3;
  v27 = 0;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  CreatorDescriptor = 0;
  TokenHandle = 0;
  SecurityDescriptor = NetpCreateSecurityDescriptor((__int64)&v3, 8u, v0, v0, (struct _ACL **)&CreatorDescriptor);
  if ( SecurityDescriptor >= 0 )
  {
    SecurityDescriptor = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlNewSecurityObject(
                             0,
                             CreatorDescriptor,
                             &ConfigurationInfoSd,
                             0,
                             TokenHandle,
                             &WsConfigInfoMapping);
      NtClose(TokenHandle);
    }
    NetpMemoryFree(CreatorDescriptor);
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x180007ecc  mov     [rsp-8+arg_10], rbx
0x180007ed1  mov     [rsp-8+arg_18], rdi
0x180007ed6  push    rbp
0x180007ed7  lea     rbp, [rsp-57h]
0x180007edc  sub     rsp, 0B0h
0x180007ee3  mov     r8, cs:WsLmsvcsGlobalData
0x180007eea  xor     edi, edi
0x180007eec  mov     [rbp+57h+var_80], di
0x180007ef0  mov     [rbp+57h+var_7E], dil
0x180007ef4  mov     [rbp+57h+var_70], di
0x180007ef8  lea     ecx, [rdi+7]
0x180007efb  mov     [rbp+57h+var_6E], dil
0x180007eff  lea     rax, [r8+10h]
0x180007f03  mov     [rbp+57h+var_7C], ecx
0x180007f06  mov     [rbp+57h+var_78], rax
0x180007f0a  lea     edx, [rdi+8]
0x180007f0d  lea     rax, [r8+50h]
0x180007f11  mov     [rbp+57h+var_5C], ecx
0x180007f14  mov     [rbp+57h+var_68], rax
0x180007f18  lea     rax, [r8+70h]
0x180007f1c  mov     [rbp+57h+var_58], rax
0x180007f20  lea     rax, [r8+78h]
0x180007f24  mov     [rbp+57h+var_48], rax
0x180007f28  lea     rax, [r8+80h]
0x180007f2f  mov     [rbp+57h+var_38], rax
0x180007f33  lea     rax, [r8+58h]
0x180007f37  mov     [rbp+57h+var_28], rax
0x180007f3b  lea     rax, [r8+8]
0x180007f3f  mov     [rbp+57h+var_18], rax
0x180007f43  lea     rax, [r8+48h]
0x180007f47  mov     r8, [r8+30h]
0x180007f4b  mov     [rbp+57h+var_4C], ecx
0x180007f4e  mov     r9, r8
0x180007f51  mov     [rbp+57h+var_3C], ecx
0x180007f54  lea     ecx, [rdi+1]
0x180007f57  mov     [rbp+57h+var_8], rax
0x180007f5b  lea     rax, [rbp+57h+CreatorDescriptor]
0x180007f5f  mov     [rbp+57h+var_1C], ecx
0x180007f62  mov     [rbp+57h+var_C], ecx
0x180007f65  lea     rcx, [rbp+57h+var_80]
0x180007f69  mov     [rsp+0B0h+Token], rax
0x180007f6e  mov     [rbp+57h+var_6C], 10000000h
0x180007f75  mov     [rbp+57h+var_60], di
0x180007f79  mov     [rbp+57h+var_5E], dil
0x180007f7d  mov     [rbp+57h+var_50], di
0x180007f81  mov     [rbp+57h+var_4E], dil
0x180007f85  mov     [rbp+57h+var_40], di
0x180007f89  mov     [rbp+57h+var_3E], dil
0x180007f8d  mov     [rbp+57h+var_30], di
0x180007f91  mov     [rbp+57h+var_2E], dil
0x180007f95  mov     [rbp+57h+var_2C], 3
0x180007f9c  mov     [rbp+57h+var_20], di
0x180007fa0  mov     [rbp+57h+var_1E], dil
0x180007fa4  mov     [rbp+57h+var_10], di
0x180007fa8  mov     [rbp+57h+var_E], dil
0x180007fac  mov     [rbp+57h+CreatorDescriptor], rdi
0x180007fb0  mov     [rbp+57h+TokenHandle], rdi
0x180007fb4  call    NetpCreateSecurityDescriptor
0x180007fb9  mov     ebx, eax
0x180007fbb  test    eax, eax
0x180007fbd  js      short loc_180008028
0x180007fbf  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180007fc3  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180007fc7  lea     edx, [rdi+8]; DesiredAccess
0x180007fca  call    cs:__imp_NtOpenProcessToken
0x180007fd1  nop     dword ptr [rax+rax+00h]
0x180007fd6  mov     ebx, eax
0x180007fd8  test    eax, eax
0x180007fda  js      short loc_18000801F
0x180007fdc  mov     rdx, [rbp+57h+CreatorDescriptor]; CreatorDescriptor
0x180007fe0  lea     rax, WsConfigInfoMapping
0x180007fe7  mov     [rsp+0B0h+GenericMapping], rax; GenericMapping
0x180007fec  lea     r8, ConfigurationInfoSd; NewDescriptor
0x180007ff3  mov     rax, [rbp+57h+TokenHandle]
0x180007ff7  xor     r9d, r9d; IsDirectoryObject
0x180007ffa  xor     ecx, ecx; ParentDescriptor
0x180007ffc  mov     [rsp+0B0h+Token], rax; Token
0x180008001  call    cs:__imp_RtlNewSecurityObject
0x180008008  nop     dword ptr [rax+rax+00h]
0x18000800d  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180008011  mov     ebx, eax
0x180008013  call    cs:__imp_NtClose
0x18000801a  nop     dword ptr [rax+rax+00h]
0x18000801f  mov     rcx, [rbp+57h+CreatorDescriptor]
0x180008023  call    NetpMemoryFree
0x180008028  lea     r11, [rsp+0B0h+var_s0]
0x180008030  mov     eax, ebx
0x180008032  mov     rbx, [r11+20h]
0x180008036  mov     rdi, [r11+28h]
0x18000803a  mov     rsp, r11
0x18000803d  pop     rbp
0x18000803e  retn
```

# WldpGetLockdownPolicy

- ea: `0x180014ad0`
- end: `0x180014ea5`
- name: `WldpGetLockdownPolicy`
- size: `981`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180014ad0`
- `0x180014eb0`
- `0x180015118`
- `0x18001c210`
- `0x18001cd18`
- `0x180020778`
- `0x18002790c`
- `0x1800282b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d3c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014c96`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014c96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WldpGetLockdownPolicy(__int64 a1, unsigned int *a2, int a3)
{
  unsigned int *v4; // rdx
  __int64 v5; // r8
  int v6; // ecx
  unsigned int v7; // r14d
  __int64 v8; // r10
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // ebx
  unsigned int v14; // eax
  const WCHAR *v15; // rcx
  int v16; // edi
  HANDLE FileW; // rbx
  char v18; // si
  char v19; // al
  unsigned int v20; // eax
  unsigned int v21; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v22[4]; // [rsp+48h] [rbp-41h] BYREF
  __int128 v23; // [rsp+58h] [rbp-31h]
  __int64 v24; // [rsp+68h] [rbp-21h]
  _QWORD v25[3]; // [rsp+78h] [rbp-11h] BYREF
  char v26; // [rsp+90h] [rbp+7h]
  _QWORD v27[9]; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v28; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int *v29; // [rsp+F8h] [rbp+6Fh] BYREF
  int PolicySettingEnabledInternal; // [rsp+108h] [rbp+7Fh] BYREF

  v29 = a2;
  v28 = a1;
  PolicySettingEnabledInternal = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v24 = 0;
  GetStateInfo(v22);
  v27[0] = &v28;
  v27[1] = &v29;
  v27[2] = &PolicySettingEnabledInternal;
  wil::ScopeExit__lambda_8ff4e2081fbfca1eb3cf09e498ea5798___(v25, v27);
  v4 = v29;
  if ( !v29 )
    goto LABEL_20;
  v5 = v28;
  if ( !v28 )
    goto LABEL_3;
  if ( *(_DWORD *)(v28 + 4) == 5 )
  {
    v21 = 0;
    PolicySettingEnabledInternal = WldpQueryPolicySettingEnabledInternal(1, (int *)&v21);
    if ( PolicySettingEnabledInternal >= 0 && v21 )
    {
      v5 = v28;
      if ( (v22[*(int *)(v28 + 4)] & 0x80000005) == -2147483643 && (v22[*(int *)(v28 + 4)] & 4) != 0 )
        goto LABEL_43;
    }
    else
    {
      v5 = v28;
    }
    v4 = v29;
  }
  if ( !v5 )
  {
LABEL_3:
    if ( !a3 )
    {
      *v4 = v22[0];
      goto LABEL_18;
    }
LABEL_20:
    PolicySettingEnabledInternal = -2147024809;
    goto LABEL_18;
  }
  if ( *(_DWORD *)v5 != 1 )
    goto LABEL_20;
  v6 = *(_DWORD *)(v5 + 4);
  if ( (unsigned int)(v6 - 1) > 6 || v6 == 1 && (*(_QWORD *)(v5 + 8) || *(_QWORD *)(v5 + 16)) )
    goto LABEL_20;
  *v4 = 0;
  v7 = -2147483644;
  v8 = v28;
  if ( (v22[1] & 0x80000004) == 0x80000000 )
    goto LABEL_17;
  v9 = *(int *)(v28 + 4);
  if ( (_DWORD)v9 == 1 )
    goto LABEL_17;
  if ( !*(_QWORD *)(v28 + 16) )
  {
    v10 = *(_QWORD *)(v28 + 8);
    if ( !v10 )
      goto LABEL_17;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v10 + 2 * v11) );
    if ( !v11 )
    {
LABEL_17:
      *v29 = v22[*(int *)(v28 + 4)];
      goto LABEL_18;
    }
  }
  v14 = v22[v9] & 0x8000001C;
  if ( v14 == -2147483628 || v14 == -2147483620 && (v22[v9] & 0x80000007) != 0x80000007 )
  {
    v21 = 0;
    PolicySettingEnabledInternal = IsPathInExclusionList(*(_QWORD *)(v28 + 8), &v21);
    if ( PolicySettingEnabledInternal < 0 )
      goto LABEL_18;
    if ( v21 )
      goto LABEL_65;
    v8 = v28;
  }
  if ( (a3 & 0x100) != 0 )
    goto LABEL_37;
  v15 = *(const WCHAR **)(v8 + 8);
  if ( !v15 && !*(_QWORD *)(v8 + 16) )
    goto LABEL_37;
  v16 = v22[*(int *)(v8 + 4)];
  if ( (v16 & 0x80000004) == 0x80000000 )
    goto LABEL_37;
  FileW = *(HANDLE *)(v8 + 16);
  v18 = 0;
  if ( !FileW || FileW == (HANDLE)-1LL )
  {
    FileW = CreateFileW(v15, 0x80000000, 5u, 0, 3u, 0, 0);
    v8 = v28;
    if ( FileW == (HANDLE)-1LL )
      FileW = 0;
    else
      v18 = 1;
  }
  v21 = 0;
  v19 = (v16 & 0x8000001C) != 0x80000004 || *(_WORD *)((char *)&v24 + 5);
  PolicySettingEnabledInternal = WldpIsFileTrusted(
                                   FileW,
                                   *(const unsigned __int16 **)(v8 + 8),
                                   *(_DWORD *)(v8 + 4),
                                   v16,
                                   v19,
                                   &v21);
  if ( v18 )
    CloseHandle(FileW);
  if ( PolicySettingEnabledInternal >= 0 )
  {
    if ( v21 != 1 )
    {
      if ( v21 != 3 )
      {
        v8 = v28;
LABEL_37:
        v20 = v22[*(int *)(v8 + 4)] & 0x8000001C;
        if ( v20 != -2147483644 && v20 != -2147483628 )
        {
          if ( v20 == -2147483620 )
          {
            v7 = -2147483620;
          }
          else
          {
            v7 = 0;
            if ( (v22[*(int *)(v8 + 4)] & 0x80000004) == 0x80000000 )
              v7 = 0x80000000;
          }
        }
        *v29 = v7;
        goto LABEL_18;
      }
LABEL_43:
      *v29 = -2147483620;
      goto LABEL_18;
    }
LABEL_65:
    *v29 = 0x80000000;
  }
LABEL_18:
  v12 = PolicySettingEnabledInternal;
  if ( v26 )
  {
    v26 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl'::`2'::impl) )
      EmitLockdownPolicyTelemetry(*(_QWORD *)v25[0], *(_QWORD *)v25[1], *(unsigned int *)v25[2]);
  }
  return v12;
}

```

## disassembly

```asm
0x180014ad0  mov     [rsp-8+arg_8], rdx
0x180014ad5  mov     [rsp-8+arg_0], rcx
0x180014ada  push    rbp
0x180014adb  push    rbx
0x180014adc  push    rsi
0x180014add  push    rdi
0x180014ade  push    r12
0x180014ae0  push    r14
0x180014ae2  push    r15
0x180014ae4  lea     rbp, [rsp-27h]
0x180014ae9  sub     rsp, 0B0h
0x180014af0  mov     ebx, r8d
0x180014af3  xor     r15d, r15d
0x180014af6  mov     [rbp+57h+arg_18], r15d
0x180014afa  xorps   xmm0, xmm0
0x180014afd  xor     eax, eax
0x180014aff  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180014b03  movups  [rbp+57h+var_88], xmm0
0x180014b07  mov     [rbp+57h+var_78], rax
0x180014b0b  lea     rcx, [rbp+57h+var_98]
0x180014b0f  call    GetStateInfo
0x180014b14  lea     rax, [rbp+57h+arg_0]
0x180014b18  mov     [rbp+57h+var_48], rax
0x180014b1c  lea     rax, [rbp+57h+arg_8]
0x180014b20  mov     [rbp+57h+var_40], rax
0x180014b24  lea     rax, [rbp+57h+arg_18]
0x180014b28  mov     [rbp+57h+var_38], rax
0x180014b2c  lea     rdx, [rbp+57h+var_48]
0x180014b30  lea     rcx, [rbp+57h+var_68]
0x180014b34  call    wil__ScopeExit__lambda_8ff4e2081fbfca1eb3cf09e498ea5798___
0x180014b39  nop
0x180014b3a  mov     rdx, [rbp+57h+arg_8]
0x180014b3e  test    rdx, rdx
0x180014b41  jz      loc_180014C11
0x180014b47  mov     r8, [rbp+57h+arg_0]
0x180014b4b  test    r8, r8
0x180014b4e  jnz     short loc_180014B62
0x180014b50  test    ebx, ebx
0x180014b52  jnz     loc_180014C11
0x180014b58  mov     eax, [rbp+57h+var_98]
0x180014b5b  mov     [rdx], eax
0x180014b5d  jmp     loc_180014BF0
0x180014b62  cmp     dword ptr [r8+4], 5
0x180014b67  jz      loc_180014D44
0x180014b6d  test    r8, r8
0x180014b70  jz      short loc_180014B50
0x180014b72  cmp     dword ptr [r8], 1
0x180014b76  jnz     loc_180014C11
0x180014b7c  mov     ecx, [r8+4]
0x180014b80  lea     eax, [rcx-1]
0x180014b83  cmp     eax, 6
0x180014b86  ja      loc_180014C11
0x180014b8c  cmp     ecx, 1
0x180014b8f  jz      loc_180014DA4
0x180014b95  mov     [rdx], r15d
0x180014b98  mov     eax, [rbp+57h+var_98+4]
0x180014b9b  mov     r14d, 80000004h
0x180014ba1  and     eax, r14d
0x180014ba4  mov     r10, [rbp+57h+arg_0]
0x180014ba8  mov     r12d, 80000000h
0x180014bae  cmp     eax, r12d
0x180014bb1  jz      short loc_180014BE2
0x180014bb3  movsxd  rdx, dword ptr [r10+4]
0x180014bb7  cmp     edx, 1
0x180014bba  jz      short loc_180014BE2
0x180014bbc  cmp     qword ptr [r10+10h], 0
0x180014bc1  jnz     short loc_180014C1A
0x180014bc3  mov     rcx, [r10+8]
0x180014bc7  test    rcx, rcx
0x180014bca  jz      short loc_180014BE2
0x180014bcc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014bd3  inc     rax
0x180014bd6  cmp     word ptr [rcx+rax*2], 0
0x180014bdb  jnz     short loc_180014BD3
0x180014bdd  test    rax, rax
0x180014be0  jnz     short loc_180014C1A
0x180014be2  movsxd  rax, dword ptr [r10+4]
0x180014be6  mov     ecx, [rbp+rax*4+57h+var_98]
0x180014bea  mov     rax, [rbp+57h+arg_8]
0x180014bee  mov     [rax], ecx
0x180014bf0  mov     ebx, [rbp+57h+arg_18]
0x180014bf3  cmp     [rbp+57h+var_50], 0
0x180014bf7  jnz     loc_180014E6E
0x180014bfd  mov     eax, ebx
0x180014bff  add     rsp, 0B0h
0x180014c06  pop     r15
0x180014c08  pop     r14
0x180014c0a  pop     r12
0x180014c0c  pop     rdi
0x180014c0d  pop     rsi
0x180014c0e  pop     rbx
0x180014c0f  pop     rbp
0x180014c10  retn
0x180014c11  mov     [rbp+57h+arg_18], 80070057h
0x180014c18  jmp     short loc_180014BF0
0x180014c1a  mov     ecx, [rbp+rdx*4+57h+var_98]
0x180014c1e  mov     eax, ecx
0x180014c20  and     eax, 8000001Ch
0x180014c25  cmp     eax, 80000014h
0x180014c2a  jz      loc_180014DD1
0x180014c30  cmp     eax, 8000001Ch
0x180014c35  jz      loc_180014DBF
0x180014c3b  bt      ebx, 8
0x180014c3f  jb      loc_180014D0D
0x180014c45  mov     rcx, [r10+8]; lpFileName
0x180014c49  test    rcx, rcx
0x180014c4c  jz      loc_180014DFC
0x180014c52  movsxd  rax, dword ptr [r10+4]
0x180014c56  mov     edi, [rbp+rax*4+57h+var_98]
0x180014c5a  mov     eax, edi
0x180014c5c  and     eax, r14d
0x180014c5f  cmp     eax, r12d
0x180014c62  jz      loc_180014D0D
0x180014c68  mov     rbx, [r10+10h]
0x180014c6c  xor     sil, sil
0x180014c6f  test    rbx, rbx
0x180014c72  jnz     loc_180014E0C
0x180014c78  mov     [rsp+0E0h+hTemplateFile], r15; hTemplateFile
0x180014c7d  mov     [rsp+0E0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180014c82  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180014c8a  xor     r9d, r9d; lpSecurityAttributes
0x180014c8d  mov     r8d, 5; dwShareMode
0x180014c93  mov     edx, r12d; dwDesiredAccess
0x180014c96  call    cs:__imp_CreateFileW
0x180014c9c  mov     rbx, rax
0x180014c9f  mov     r10, [rbp+57h+arg_0]
0x180014ca3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014ca7  jnz     loc_180014D31
0x180014cad  mov     rbx, r15
0x180014cb0  mov     [rbp+57h+var_A0], r15d
0x180014cb4  mov     eax, edi
0x180014cb6  and     eax, 8000001Ch
0x180014cbb  cmp     eax, r14d
0x180014cbe  jz      loc_180014E1B
0x180014cc4  mov     al, 1
0x180014cc6  lea     rcx, [rbp+57h+var_A0]
0x180014cca  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx; unsigned int *
0x180014ccf  mov     byte ptr [rsp+0E0h+dwCreationDisposition], al; char
0x180014cd3  mov     r9d, edi; unsigned int
0x180014cd6  mov     r8d, [r10+4]; unsigned int
0x180014cda  mov     rdx, [r10+8]; unsigned __int16 *
0x180014cde  mov     rcx, rbx; void *
0x180014ce1  call    ?WldpIsFileTrusted@@YAJQEAXPEBGKKEPEAK@Z; WldpIsFileTrusted(void * const,ushort const *,ulong,ulong,uchar,ulong *)
0x180014ce6  mov     [rbp+57h+arg_18], eax
0x180014ce9  test    sil, sil
0x180014cec  jnz     short loc_180014D39
0x180014cee  cmp     [rbp+57h+arg_18], 0
0x180014cf2  jl      loc_180014BF0
0x180014cf8  mov     eax, [rbp+57h+var_A0]
0x180014cfb  cmp     eax, 1
0x180014cfe  jz      loc_180014E62
0x180014d04  cmp     eax, 3
0x180014d07  jz      short loc_180014D88
0x180014d09  mov     r10, [rbp+57h+arg_0]
0x180014d0d  movsxd  rax, dword ptr [r10+4]
0x180014d11  mov     ecx, [rbp+rax*4+57h+var_98]
0x180014d15  mov     eax, ecx
0x180014d17  and     eax, 8000001Ch
0x180014d1c  cmp     eax, r14d
0x180014d1f  jnz     loc_180014E36
0x180014d25  mov     rax, [rbp+57h+arg_8]
0x180014d29  mov     [rax], r14d
0x180014d2c  jmp     loc_180014BF0
0x180014d31  mov     sil, 1
0x180014d34  jmp     loc_180014CB0
0x180014d39  mov     rcx, rbx; hObject
0x180014d3c  call    cs:__imp_CloseHandle
0x180014d42  jmp     short loc_180014CEE
0x180014d44  mov     [rbp+57h+var_A0], r15d
0x180014d48  lea     rdx, [rbp+57h+var_A0]
0x180014d4c  mov     ecx, 1
0x180014d51  call    ?WldpQueryPolicySettingEnabledInternal@@YAJW4WLDP_POLICY_SETTING_INTERNAL@@PEAH@Z; WldpQueryPolicySettingEnabledInternal(WLDP_POLICY_SETTING_INTERNAL,int *)
0x180014d56  mov     [rbp+57h+arg_18], eax
0x180014d59  test    eax, eax
0x180014d5b  js      short loc_180014D97
0x180014d5d  cmp     [rbp+57h+var_A0], 0
0x180014d61  jz      short loc_180014D97
0x180014d63  mov     r8, [rbp+57h+arg_0]
0x180014d67  movsxd  rax, dword ptr [r8+4]
0x180014d6b  mov     edx, [rbp+rax*4+57h+var_98]
0x180014d6f  mov     eax, edx
0x180014d71  and     eax, 80000005h
0x180014d76  cmp     eax, 80000005h
0x180014d7b  setz    cl
0x180014d7e  test    dl, 4
0x180014d81  setnz   al
0x180014d84  test    al, cl
0x180014d86  jz      short loc_180014D9B
0x180014d88  mov     rax, [rbp+57h+arg_8]
0x180014d8c  mov     dword ptr [rax], 8000001Ch
0x180014d92  jmp     loc_180014BF0
0x180014d97  mov     r8, [rbp+57h+arg_0]
0x180014d9b  mov     rdx, [rbp+57h+arg_8]
0x180014d9f  jmp     loc_180014B6D
0x180014da4  cmp     qword ptr [r8+8], 0
0x180014da9  jnz     loc_180014C11
0x180014daf  cmp     qword ptr [r8+10h], 0
0x180014db4  jnz     loc_180014C11
0x180014dba  jmp     loc_180014B95
0x180014dbf  and     ecx, 80000007h
0x180014dc5  cmp     ecx, 80000007h
0x180014dcb  jz      loc_180014C3B
0x180014dd1  mov     [rbp+57h+var_A0], r15d
0x180014dd5  lea     rdx, [rbp+57h+var_A0]
0x180014dd9  mov     rcx, [r10+8]
0x180014ddd  call    IsPathInExclusionList
0x180014de2  mov     [rbp+57h+arg_18], eax
0x180014de5  test    eax, eax
0x180014de7  js      loc_180014BF0
0x180014ded  cmp     [rbp+57h+var_A0], 0
0x180014df1  jnz     short loc_180014E62
0x180014df3  mov     r10, [rbp+57h+arg_0]
0x180014df7  jmp     loc_180014C3B
0x180014dfc  cmp     qword ptr [r10+10h], 0
0x180014e01  jz      loc_180014D0D
0x180014e07  jmp     loc_180014C52
0x180014e0c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180014e10  jnz     loc_180014CB0
0x180014e16  jmp     loc_180014C78
0x180014e1b  cmp     byte ptr [rbp+57h+var_78+5], 0
0x180014e1f  jnz     loc_180014CC4
0x180014e25  cmp     byte ptr [rbp+57h+var_78+6], 0
0x180014e29  jnz     loc_180014CC4
0x180014e2f  xor     eax, eax
0x180014e31  jmp     loc_180014CC6
0x180014e36  cmp     eax, 80000014h
0x180014e3b  jz      loc_180014D25
0x180014e41  cmp     eax, 8000001Ch
0x180014e46  jnz     short loc_180014E50
0x180014e48  mov     r14d, eax
0x180014e4b  jmp     loc_180014D25
0x180014e50  and     ecx, r14d
0x180014e53  mov     r14d, r15d
0x180014e56  cmp     ecx, r12d
0x180014e59  cmovz   r14d, r12d
0x180014e5d  jmp     loc_180014D25
0x180014e62  mov     rax, [rbp+57h+arg_8]
0x180014e66  mov     [rax], r12d
0x180014e69  jmp     loc_180014BF0
0x180014e6e  mov     [rbp+57h+var_50], 0
0x180014e72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl(void)'::`2'::impl
0x180014e79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(void)
0x180014e7e  test    al, al
0x180014e80  jnz     loc_180014BFD
0x180014e86  mov     r8, [rbp+57h+var_58]
0x180014e8a  mov     r8d, [r8]
0x180014e8d  mov     rdx, [rbp+57h+var_60]
0x180014e91  mov     rdx, [rdx]
0x180014e94  mov     rcx, [rbp+57h+var_68]
0x180014e98  mov     rcx, [rcx]
0x180014e9b  call    EmitLockdownPolicyTelemetry
0x180014ea0  jmp     loc_180014BFD
```

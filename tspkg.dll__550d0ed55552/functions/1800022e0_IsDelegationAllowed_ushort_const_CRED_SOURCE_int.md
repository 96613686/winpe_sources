# IsDelegationAllowed(ushort const *,CRED_SOURCE,int *)

- ea: `0x1800022e0`
- end: `0x180002569`
- name: `?IsDelegationAllowed@@YAJPEBGW4CRED_SOURCE@@PEAH@Z`
- size: `649`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006650`

## callees

- `0x1800021b4`
- `0x1800022e0`
- `0x180002e50`
- `0x18000a208`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002437`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000255e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002437`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000255e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000233d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000237d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000233d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000237d`

## pseudocode

```c
__int64 __fastcall IsDelegationAllowed(wchar_t *a1, int a2, _DWORD *a3)
{
  int v6; // esi
  LSTATUS v7; // eax
  int v8; // ebx
  unsigned __int64 v9; // rdx
  HKEY v10; // r12
  unsigned __int64 v11; // r15
  HKEY v12; // r13
  int v13; // eax
  int v15; // r15d
  HKEY phkResult; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v17; // [rsp+58h] [rbp-8h] BYREF
  int v18; // [rsp+A0h] [rbp+40h] BYREF
  int v19; // [rsp+B0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+58h] BYREF

  hKey = 0;
  v18 = 0;
  v19 = 0;
  v6 = 0;
  *a3 = 0;
  if ( !a1 && a2 )
    return 2147942487LL;
  phkResult = 0;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\CredentialsDelegation",
         0,
         0x20019u,
         &phkResult);
  v8 = v7;
  if ( v7 == 2 )
  {
    v8 = 0;
  }
  else if ( v7 > 0 )
  {
    v8 = (unsigned __int16)v7 | 0x80070000;
  }
  if ( v8 >= 0 )
  {
    hKey = 0;
    RegOpenKeyExW(
      HKEY_LOCAL_MACHINE,
      L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults",
      0,
      0x20019u,
      &hKey);
    if ( !a2 )
    {
      v10 = hKey;
      v11 = 0;
      v12 = phkResult;
      v17 = 0;
      if ( !a1
        || (v8 = StringCchLengthW(a1, v9, &v17), v8 >= 0)
        && (v11 = v17,
            v8 = CheckValue(
                   v12,
                   v10,
                   L"DenyDefaultCredentials",
                   0,
                   0,
                   L"ConcatenateDefaults_DenyDefault",
                   a1,
                   v17,
                   &v19),
            v8 >= 0)
        && !v19 )
      {
        v13 = CheckValue(v12, v10, L"AllowDefaultCredentials", 0, 0, L"ConcatenateDefaults_AllowDefault", a1, v11, &v18);
        v6 = v18;
        v8 = v13;
      }
      if ( v8 < 0 || !v6 )
        goto LABEL_9;
LABEL_32:
      *a3 = 1;
      goto LABEL_9;
    }
    v15 = a2 - 1;
    if ( !v15 )
    {
      v8 = CheckPolicyValue(phkResult, hKey, a1, 1, &v18, &v19);
      if ( v8 < 0 || !v18 )
        goto LABEL_9;
      goto LABEL_32;
    }
    if ( v15 == 1 )
    {
      v8 = CheckPolicyValue(phkResult, hKey, a1, 2, &v18, &v19);
      if ( v8 < 0 || !v18 )
        goto LABEL_9;
      goto LABEL_32;
    }
    v8 = -2147024809;
  }
LABEL_9:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800022e0  push    rbp
0x1800022e2  push    rbx
0x1800022e3  push    rsi
0x1800022e4  push    rdi
0x1800022e5  push    r12
0x1800022e7  push    r14
0x1800022e9  push    r15
0x1800022eb  mov     rbp, rsp
0x1800022ee  sub     rsp, 60h
0x1800022f2  xor     r12d, r12d
0x1800022f5  mov     r14, r8
0x1800022f8  mov     [rbp+hKey], r12
0x1800022fc  mov     r15d, edx
0x1800022ff  mov     [rbp+arg_0], r12d
0x180002303  mov     rdi, rcx
0x180002306  mov     [rbp+arg_10], r12d
0x18000230a  mov     esi, r12d
0x18000230d  mov     [r8], r12d
0x180002310  test    rcx, rcx
0x180002313  jz      loc_18000243F
0x180002319  lea     rax, [rbp+var_10]
0x18000231d  mov     [rbp+var_10], r12
0x180002321  mov     r9d, 20019h; samDesired
0x180002327  mov     [rsp+60h+phkResult], rax; phkResult
0x18000232c  xor     r8d, r8d; ulOptions
0x18000232f  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180002336  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000233d  call    cs:__imp_RegOpenKeyExW
0x180002343  mov     ebx, eax
0x180002345  cmp     eax, 2
0x180002348  jnz     loc_180002421
0x18000234e  mov     ebx, r12d
0x180002351  test    ebx, ebx
0x180002353  js      loc_1800023FA
0x180002359  lea     rax, [rbp+hKey]
0x18000235d  mov     [rbp+hKey], r12
0x180002361  mov     r9d, 20019h; samDesired
0x180002367  mov     [rsp+60h+phkResult], rax; phkResult
0x18000236c  xor     r8d, r8d; ulOptions
0x18000236f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180002376  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000237d  call    cs:__imp_RegOpenKeyExW
0x180002383  test    r15d, r15d
0x180002386  jnz     loc_18000244F
0x18000238c  mov     r12, [rbp+hKey]
0x180002390  xor     r15d, r15d
0x180002393  mov     [rsp+60h+arg_8], r13
0x18000239b  mov     r13, [rbp+var_10]
0x18000239f  mov     [rbp+var_8], r15
0x1800023a3  test    rdi, rdi
0x1800023a6  jnz     loc_1800024DF
0x1800023ac  mov     r8, cs:off_18001E000; unsigned __int16 *
0x1800023b3  lea     rax, [rbp+arg_0]
0x1800023b7  mov     [rsp+60h+var_20], rax; int *
0x1800023bc  xor     r9d, r9d; unsigned __int16 *
0x1800023bf  mov     rax, cs:off_18001E030; "ConcatenateDefaults_AllowDefault"
0x1800023c6  mov     rdx, r12; hKey
0x1800023c9  mov     [rsp+60h+var_28], r15; unsigned __int64
0x1800023ce  mov     rcx, r13; HKEY
0x1800023d1  mov     [rsp+60h+var_30], rdi; unsigned __int16 *
0x1800023d6  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800023db  mov     [rsp+60h+phkResult], rsi; unsigned __int16 *
0x1800023e0  call    ?CheckValue@@YAJPEAUHKEY__@@0PEBG1111_KPEAH@Z; CheckValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,int *)
0x1800023e5  mov     esi, [rbp+arg_0]
0x1800023e8  mov     ebx, eax
0x1800023ea  mov     r13, [rsp+60h+arg_8]
0x1800023f2  test    ebx, ebx
0x1800023f4  jns     loc_18000254A
0x1800023fa  mov     rcx, [rbp+var_10]; hKey
0x1800023fe  test    rcx, rcx
0x180002401  jnz     loc_18000255E
0x180002407  mov     rcx, [rbp+hKey]; hKey
0x18000240b  test    rcx, rcx
0x18000240e  jnz     short loc_180002437
0x180002410  mov     eax, ebx
0x180002412  add     rsp, 60h
0x180002416  pop     r15
0x180002418  pop     r14
0x18000241a  pop     r12
0x18000241c  pop     rdi
0x18000241d  pop     rsi
0x18000241e  pop     rbx
0x18000241f  pop     rbp
0x180002420  retn
0x180002421  test    eax, eax
0x180002423  jle     loc_180002351
0x180002429  movzx   ebx, ax
0x18000242c  or      ebx, 80070000h
0x180002432  jmp     loc_180002351
0x180002437  call    cs:__imp_RegCloseKey
0x18000243d  jmp     short loc_180002410
0x18000243f  test    r15d, r15d
0x180002442  jz      loc_180002319
0x180002448  mov     eax, 80070057h
0x18000244d  jmp     short loc_180002412
0x18000244f  sub     r15d, 1
0x180002453  jz      short loc_1800024A2
0x180002455  cmp     r15d, 1
0x180002459  jz      short loc_180002462
0x18000245b  mov     ebx, 80070057h
0x180002460  jmp     short loc_1800023FA
0x180002462  mov     rdx, [rbp+hKey]
0x180002466  lea     rax, [rbp+arg_10]
0x18000246a  mov     rcx, [rbp+var_10]
0x18000246e  mov     r9d, 2
0x180002474  mov     [rsp+60h+var_38], rax
0x180002479  mov     r8, rdi
0x18000247c  lea     rax, [rbp+arg_0]
0x180002480  mov     [rsp+60h+phkResult], rax
0x180002485  call    ?CheckPolicyValue@@YAJPEAUHKEY__@@0PEBGW4PolicyID@@PEAH3@Z; CheckPolicyValue(HKEY__ *,HKEY__ *,ushort const *,PolicyID,int *,int *)
0x18000248a  mov     ebx, eax
0x18000248c  test    eax, eax
0x18000248e  js      loc_1800023FA
0x180002494  cmp     [rbp+arg_0], esi
0x180002497  jz      loc_1800023FA
0x18000249d  jmp     loc_180002552
0x1800024a2  mov     rdx, [rbp+hKey]
0x1800024a6  lea     rax, [rbp+arg_10]
0x1800024aa  mov     rcx, [rbp+var_10]
0x1800024ae  mov     r9d, 1
0x1800024b4  mov     [rsp+60h+var_38], rax
0x1800024b9  mov     r8, rdi
0x1800024bc  lea     rax, [rbp+arg_0]
0x1800024c0  mov     [rsp+60h+phkResult], rax
0x1800024c5  call    ?CheckPolicyValue@@YAJPEAUHKEY__@@0PEBGW4PolicyID@@PEAH3@Z; CheckPolicyValue(HKEY__ *,HKEY__ *,ushort const *,PolicyID,int *,int *)
0x1800024ca  mov     ebx, eax
0x1800024cc  test    eax, eax
0x1800024ce  js      loc_1800023FA
0x1800024d4  cmp     [rbp+arg_0], esi
0x1800024d7  jz      loc_1800023FA
0x1800024dd  jmp     short loc_180002552
0x1800024df  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800024e3  mov     rcx, rdi; unsigned __int16 *
0x1800024e6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800024eb  mov     ebx, eax
0x1800024ed  test    eax, eax
0x1800024ef  js      loc_1800023EA
0x1800024f5  mov     r15, [rbp+var_8]
0x1800024f9  lea     rax, [rbp+arg_10]
0x1800024fd  mov     r8, cs:off_18001E018; unsigned __int16 *
0x180002504  xor     r9d, r9d; unsigned __int16 *
0x180002507  mov     [rsp+60h+var_20], rax; int *
0x18000250c  mov     rdx, r12; hKey
0x18000250f  mov     rax, cs:off_18001E038; "ConcatenateDefaults_DenyDefault"
0x180002516  mov     rcx, r13; HKEY
0x180002519  mov     [rsp+60h+var_28], r15; unsigned __int64
0x18000251e  mov     [rsp+60h+var_30], rdi; unsigned __int16 *
0x180002523  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180002528  mov     [rsp+60h+phkResult], rsi; unsigned __int16 *
0x18000252d  call    ?CheckValue@@YAJPEAUHKEY__@@0PEBG1111_KPEAH@Z; CheckValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,int *)
0x180002532  mov     ebx, eax
0x180002534  test    eax, eax
0x180002536  js      loc_1800023EA
0x18000253c  cmp     [rbp+arg_10], esi
0x18000253f  jnz     loc_1800023EA
0x180002545  jmp     loc_1800023AC
0x18000254a  test    esi, esi
0x18000254c  jz      loc_1800023FA
0x180002552  mov     dword ptr [r14], 1
0x180002559  jmp     loc_1800023FA
0x18000255e  call    cs:__imp_RegCloseKey
0x180002564  jmp     loc_180002407
```

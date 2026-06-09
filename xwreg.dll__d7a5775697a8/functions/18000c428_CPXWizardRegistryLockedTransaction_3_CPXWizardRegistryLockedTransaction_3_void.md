# CPXWizardRegistryLockedTransaction<3>::CPXWizardRegistryLockedTransaction<3>(void)

- ea: `0x18000c428`
- end: `0x18000c5bf`
- name: `??0?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ`
- size: `407`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c5c8`
- `0x18000ca6c`

## callees

- `0x1800011dc`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000c428`
- `0x18000cf6c`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c547`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c547`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c57e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c57e`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistryLockedTransaction<3>::CPXWizardRegistryLockedTransaction<3>(__int64 a1)
{
  int *v3; // r15
  HKEY *phkResult; // r14
  CRegistryLockedTransaction *v5; // rax
  CRegistryLockedTransaction *v6; // rax
  int Key; // eax
  unsigned int v8; // r11d
  struct _GUID v10; // [rsp+78h] [rbp-C0h] BYREF
  WCHAR SubKey[64]; // [rsp+90h] [rbp-A8h] BYREF

  *(_DWORD *)&v10.Data2 = 1215636632;
  *(_DWORD *)v10.Data4 = 1731213971;
  *(_DWORD *)&v10.Data4[4] = 1882228958;
  v3 = (int *)(a1 + 16);
  *(_DWORD *)(a1 + 16) = 0;
  phkResult = (HKEY *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  v10.Data1 = 2004592771;
  *(_QWORD *)a1 = 0;
  v5 = (CRegistryLockedTransaction *)operator new(0x240u);
  if ( v5 )
    v6 = CRegistryLockedTransaction::CRegistryLockedTransaction(v5, &v10);
  else
    v6 = 0;
  *(_QWORD *)a1 = v6;
  if ( *(_QWORD *)a1 )
  {
    SubKey[0] = 0;
    StringCchCopyW(SubKey, 0x40u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
    StringCchCatW(SubKey, v8, off_18001D308);
    Key = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, phkResult);
    if ( Key == 2 )
      Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, phkResult, 0);
    if ( Key > 0 )
      Key = (unsigned __int16)Key | 0x80070000;
  }
  else
  {
    Key = -2147024882;
  }
  *v3 = Key;
  return a1;
}

```

## disassembly

```asm
0x18000c428  mov     [rsp+arg_8], rbx
0x18000c42d  mov     [rsp+arg_10], rsi
0x18000c432  push    rdi
0x18000c433  push    r14
0x18000c435  push    r15
0x18000c437  sub     rsp, 120h
0x18000c43e  mov     rax, cs:__security_cookie
0x18000c445  xor     rax, rsp
0x18000c448  mov     [rsp+138h+var_28], rax
0x18000c450  mov     rdi, rcx
0x18000c453  mov     rsi, rcx
0x18000c456  mov     [rsp+138h+var_E8], rcx
0x18000c45b  mov     dword ptr [rsp+138h+var_C0.Data2], 48752498h
0x18000c463  mov     dword ptr [rsp+138h+var_C0.Data4], 67303A93h
0x18000c46e  mov     dword ptr [rsp+138h+var_C0.Data4+4], 703088DEh
0x18000c479  lea     r15, [rcx+10h]
0x18000c47d  mov     [rsp+138h+var_D8], r15
0x18000c482  xor     ebx, ebx
0x18000c484  mov     [r15], ebx
0x18000c487  lea     r14, [rcx+8]
0x18000c48b  mov     [rsp+138h+var_D0], r14
0x18000c490  mov     [r14], rbx
0x18000c493  mov     [rsp+138h+var_C0.Data1], 777BA883h
0x18000c49b  mov     [rcx], rbx
0x18000c49e  mov     ecx, 240h; Size
0x18000c4a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4a8  mov     [rsp+138h+var_C8], rax
0x18000c4ad  test    rax, rax
0x18000c4b0  jz      short loc_18000C4C1
0x18000c4b2  lea     rdx, [rsp+138h+var_C0]; struct _GUID *
0x18000c4b7  mov     rcx, rax; this
0x18000c4ba  call    ??0CRegistryLockedTransaction@@QEAA@PEBU_GUID@@@Z; CRegistryLockedTransaction::CRegistryLockedTransaction(_GUID const *)
0x18000c4bf  jmp     short loc_18000C4C4
0x18000c4c1  mov     rax, rbx
0x18000c4c4  mov     [rdi], rax
0x18000c4c7  jmp     short loc_18000C4DD
0x18000c4c9  xor     ebx, ebx
0x18000c4cb  mov     rsi, [rsp+138h+var_E8]
0x18000c4d0  mov     rdi, rsi
0x18000c4d3  mov     r15, [rsp+138h+var_D8]
0x18000c4d8  mov     r14, [rsp+138h+var_D0]
0x18000c4dd  cmp     [rdi], rbx
0x18000c4e0  jnz     short loc_18000C4EC
0x18000c4e2  mov     eax, 8007000Eh
0x18000c4e7  jmp     loc_18000C590
0x18000c4ec  mov     [rsp+138h+SubKey], bx
0x18000c4f4  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c4fb  mov     r11d, 40h ; '@'
0x18000c501  mov     edx, r11d; unsigned __int64
0x18000c504  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18000c50c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c511  mov     r8, cs:off_18001D308; unsigned __int16 *
0x18000c518  mov     edx, r11d; unsigned __int64
0x18000c51b  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18000c523  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c528  mov     [rsp+138h+phkResult], r14; phkResult
0x18000c52d  mov     edi, 20006h
0x18000c532  mov     r9d, edi; samDesired
0x18000c535  xor     r8d, r8d; ulOptions
0x18000c538  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x18000c540  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c547  call    cs:__imp_RegOpenKeyExW
0x18000c54d  cmp     eax, 2
0x18000c550  jnz     short loc_18000C584
0x18000c552  mov     [rsp+138h+lpdwDisposition], rbx; lpdwDisposition
0x18000c557  mov     [rsp+138h+var_100], r14; phkResult
0x18000c55c  mov     [rsp+138h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000c561  mov     [rsp+138h+samDesired], edi; samDesired
0x18000c565  mov     dword ptr [rsp+138h+phkResult], ebx; dwOptions
0x18000c569  xor     r9d, r9d; lpClass
0x18000c56c  xor     r8d, r8d; Reserved
0x18000c56f  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x18000c577  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c57e  call    cs:__imp_RegCreateKeyExW
0x18000c584  test    eax, eax
0x18000c586  jle     short loc_18000C590
0x18000c588  movzx   eax, ax
0x18000c58b  or      eax, 80070000h
0x18000c590  mov     [r15], eax
0x18000c593  mov     rax, rsi
0x18000c596  mov     rcx, [rsp+138h+var_28]
0x18000c59e  xor     rcx, rsp; StackCookie
0x18000c5a1  call    __security_check_cookie
0x18000c5a6  lea     r11, [rsp+138h+var_18]
0x18000c5ae  mov     rbx, [r11+28h]
0x18000c5b2  mov     rsi, [r11+30h]
0x18000c5b6  mov     rsp, r11
0x18000c5b9  pop     r15
0x18000c5bb  pop     r14
0x18000c5bd  pop     rdi
0x18000c5be  retn
```

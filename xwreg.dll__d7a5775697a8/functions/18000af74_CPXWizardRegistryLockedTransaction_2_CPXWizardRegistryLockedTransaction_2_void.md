# CPXWizardRegistryLockedTransaction<2>::CPXWizardRegistryLockedTransaction<2>(void)

- ea: `0x18000af74`
- end: `0x18000b10b`
- name: `??0?$CPXWizardRegistryLockedTransaction@$01@@QEAA@XZ`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b114`
- `0x18000bac8`
- `0x18000c240`

## callees

- `0x1800011dc`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000af74`
- `0x18000cf6c`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b093`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b093`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b0ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b0ca`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistryLockedTransaction<2>::CPXWizardRegistryLockedTransaction<2>(__int64 a1)
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
  v10.Data1 = 2004592770;
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
    StringCchCatW(SubKey, v8, off_18001D208);
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
0x18000af74  mov     [rsp+arg_8], rbx
0x18000af79  mov     [rsp+arg_10], rsi
0x18000af7e  push    rdi
0x18000af7f  push    r14
0x18000af81  push    r15
0x18000af83  sub     rsp, 120h
0x18000af8a  mov     rax, cs:__security_cookie
0x18000af91  xor     rax, rsp
0x18000af94  mov     [rsp+138h+var_28], rax
0x18000af9c  mov     rdi, rcx
0x18000af9f  mov     rsi, rcx
0x18000afa2  mov     [rsp+138h+var_E8], rcx
0x18000afa7  mov     dword ptr [rsp+138h+var_C0.Data2], 48752498h
0x18000afaf  mov     dword ptr [rsp+138h+var_C0.Data4], 67303A93h
0x18000afba  mov     dword ptr [rsp+138h+var_C0.Data4+4], 703088DEh
0x18000afc5  lea     r15, [rcx+10h]
0x18000afc9  mov     [rsp+138h+var_D8], r15
0x18000afce  xor     ebx, ebx
0x18000afd0  mov     [r15], ebx
0x18000afd3  lea     r14, [rcx+8]
0x18000afd7  mov     [rsp+138h+var_D0], r14
0x18000afdc  mov     [r14], rbx
0x18000afdf  mov     [rsp+138h+var_C0.Data1], 777BA882h
0x18000afe7  mov     [rcx], rbx
0x18000afea  mov     ecx, 240h; Size
0x18000afef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aff4  mov     [rsp+138h+var_C8], rax
0x18000aff9  test    rax, rax
0x18000affc  jz      short loc_18000B00D
0x18000affe  lea     rdx, [rsp+138h+var_C0]; struct _GUID *
0x18000b003  mov     rcx, rax; this
0x18000b006  call    ??0CRegistryLockedTransaction@@QEAA@PEBU_GUID@@@Z; CRegistryLockedTransaction::CRegistryLockedTransaction(_GUID const *)
0x18000b00b  jmp     short loc_18000B010
0x18000b00d  mov     rax, rbx
0x18000b010  mov     [rdi], rax
0x18000b013  jmp     short loc_18000B029
0x18000b015  xor     ebx, ebx
0x18000b017  mov     rsi, [rsp+138h+var_E8]
0x18000b01c  mov     rdi, rsi
0x18000b01f  mov     r15, [rsp+138h+var_D8]
0x18000b024  mov     r14, [rsp+138h+var_D0]
0x18000b029  cmp     [rdi], rbx
0x18000b02c  jnz     short loc_18000B038
0x18000b02e  mov     eax, 8007000Eh
0x18000b033  jmp     loc_18000B0DC
0x18000b038  mov     [rsp+138h+SubKey], bx
0x18000b040  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000b047  mov     r11d, 40h ; '@'
0x18000b04d  mov     edx, r11d; unsigned __int64
0x18000b050  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18000b058  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b05d  mov     r8, cs:off_18001D208; unsigned __int16 *
0x18000b064  mov     edx, r11d; unsigned __int64
0x18000b067  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18000b06f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b074  mov     [rsp+138h+phkResult], r14; phkResult
0x18000b079  mov     edi, 20006h
0x18000b07e  mov     r9d, edi; samDesired
0x18000b081  xor     r8d, r8d; ulOptions
0x18000b084  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x18000b08c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b093  call    cs:__imp_RegOpenKeyExW
0x18000b099  cmp     eax, 2
0x18000b09c  jnz     short loc_18000B0D0
0x18000b09e  mov     [rsp+138h+lpdwDisposition], rbx; lpdwDisposition
0x18000b0a3  mov     [rsp+138h+var_100], r14; phkResult
0x18000b0a8  mov     [rsp+138h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000b0ad  mov     [rsp+138h+samDesired], edi; samDesired
0x18000b0b1  mov     dword ptr [rsp+138h+phkResult], ebx; dwOptions
0x18000b0b5  xor     r9d, r9d; lpClass
0x18000b0b8  xor     r8d, r8d; Reserved
0x18000b0bb  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x18000b0c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b0ca  call    cs:__imp_RegCreateKeyExW
0x18000b0d0  test    eax, eax
0x18000b0d2  jle     short loc_18000B0DC
0x18000b0d4  movzx   eax, ax
0x18000b0d7  or      eax, 80070000h
0x18000b0dc  mov     [r15], eax
0x18000b0df  mov     rax, rsi
0x18000b0e2  mov     rcx, [rsp+138h+var_28]
0x18000b0ea  xor     rcx, rsp; StackCookie
0x18000b0ed  call    __security_check_cookie
0x18000b0f2  lea     r11, [rsp+138h+var_18]
0x18000b0fa  mov     rbx, [r11+28h]
0x18000b0fe  mov     rsi, [r11+30h]
0x18000b102  mov     rsp, r11
0x18000b105  pop     r15
0x18000b107  pop     r14
0x18000b109  pop     rdi
0x18000b10a  retn
```

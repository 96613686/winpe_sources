# CPXWizardRegistryLockedTransaction<1>::CPXWizardRegistryLockedTransaction<1>(void)

- ea: `0x180007860`
- end: `0x1800079f7`
- name: `??0?$CPXWizardRegistryLockedTransaction@$00@@QEAA@XZ`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800085ac`
- `0x180009ca0`

## callees

- `0x1800011dc`
- `0x180007860`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000cf6c`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000797f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000797f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800079b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800079b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPXWizardRegistryLockedTransaction<1>::CPXWizardRegistryLockedTransaction<1>(__int64 a1)
{
  CRegistryLockedTransaction **v1; // rdi
  __int64 v2; // rsi
  int *v3; // r15
  HKEY *phkResult; // r14
  CRegistryLockedTransaction *v5; // rax
  CRegistryLockedTransaction *v6; // rax
  int Key; // eax
  unsigned int v8; // r11d
  int *v11; // [rsp+60h] [rbp-D8h]
  HKEY *v12; // [rsp+68h] [rbp-D0h]
  struct _GUID v13; // [rsp+78h] [rbp-C0h] BYREF
  WCHAR SubKey[64]; // [rsp+90h] [rbp-A8h] BYREF

  try
  {
    v1 = (CRegistryLockedTransaction **)a1;
    v2 = a1;
    *(_DWORD *)&v13.Data2 = 1215636632;
    *(_DWORD *)v13.Data4 = 1731213971;
    *(_DWORD *)&v13.Data4[4] = 1882228958;
    v3 = (int *)(a1 + 16);
    v11 = (int *)(a1 + 16);
    *(_DWORD *)(a1 + 16) = 0;
    phkResult = (HKEY *)(a1 + 8);
    v12 = (HKEY *)(a1 + 8);
    *(_QWORD *)(a1 + 8) = 0;
    v13.Data1 = 2004592769;
    *(_QWORD *)a1 = 0;
    v5 = (CRegistryLockedTransaction *)operator new(0x240u);
    if ( v5 )
      v6 = CRegistryLockedTransaction::CRegistryLockedTransaction(v5, &v13);
    else
      v6 = 0;
    *v1 = v6;
  }
  catch ( ... )
  {
    v2 = a1;
    v1 = (CRegistryLockedTransaction **)a1;
    v3 = v11;
    phkResult = v12;
  }
  if ( *v1 )
  {
    SubKey[0] = 0;
    StringCchCopyW(SubKey, 0x40u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
    StringCchCatW(SubKey, v8, off_18001D168);
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
  return v2;
}

```

## disassembly

```asm
0x180007860  mov     [rsp+arg_8], rbx
0x180007865  mov     [rsp+arg_10], rsi
0x18000786a  push    rdi
0x18000786b  push    r14
0x18000786d  push    r15
0x18000786f  sub     rsp, 120h
0x180007876  mov     rax, cs:__security_cookie
0x18000787d  xor     rax, rsp
0x180007880  mov     [rsp+138h+var_28], rax
0x180007888  mov     rdi, rcx
0x18000788b  mov     rsi, rcx
0x18000788e  mov     [rsp+138h+var_E8], rcx
0x180007893  mov     dword ptr [rsp+138h+var_C0.Data2], 48752498h
0x18000789b  mov     dword ptr [rsp+138h+var_C0.Data4], 67303A93h
0x1800078a6  mov     dword ptr [rsp+138h+var_C0.Data4+4], 703088DEh
0x1800078b1  lea     r15, [rcx+10h]
0x1800078b5  mov     [rsp+138h+var_D8], r15
0x1800078ba  xor     ebx, ebx
0x1800078bc  mov     [r15], ebx
0x1800078bf  lea     r14, [rcx+8]
0x1800078c3  mov     [rsp+138h+var_D0], r14
0x1800078c8  mov     [r14], rbx
0x1800078cb  mov     [rsp+138h+var_C0.Data1], 777BA881h
0x1800078d3  mov     [rcx], rbx
0x1800078d6  mov     ecx, 240h; Size
0x1800078db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800078e0  mov     [rsp+138h+var_C8], rax
0x1800078e5  test    rax, rax
0x1800078e8  jz      short loc_1800078F9
0x1800078ea  lea     rdx, [rsp+138h+var_C0]; struct _GUID *
0x1800078ef  mov     rcx, rax; this
0x1800078f2  call    ??0CRegistryLockedTransaction@@QEAA@PEBU_GUID@@@Z; CRegistryLockedTransaction::CRegistryLockedTransaction(_GUID const *)
0x1800078f7  jmp     short loc_1800078FC
0x1800078f9  mov     rax, rbx
0x1800078fc  mov     [rdi], rax
0x1800078ff  jmp     short loc_180007915
0x180007901  xor     ebx, ebx
0x180007903  mov     rsi, [rsp+138h+var_E8]
0x180007908  mov     rdi, rsi
0x18000790b  mov     r15, [rsp+138h+var_D8]
0x180007910  mov     r14, [rsp+138h+var_D0]
0x180007915  cmp     [rdi], rbx
0x180007918  jnz     short loc_180007924
0x18000791a  mov     eax, 8007000Eh
0x18000791f  jmp     loc_1800079C8
0x180007924  mov     [rsp+138h+SubKey], bx
0x18000792c  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007933  mov     r11d, 40h ; '@'
0x180007939  mov     edx, r11d; unsigned __int64
0x18000793c  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x180007944  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007949  mov     r8, cs:off_18001D168; unsigned __int16 *
0x180007950  mov     edx, r11d; unsigned __int64
0x180007953  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18000795b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007960  mov     [rsp+138h+phkResult], r14; phkResult
0x180007965  mov     edi, 20006h
0x18000796a  mov     r9d, edi; samDesired
0x18000796d  xor     r8d, r8d; ulOptions
0x180007970  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x180007978  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000797f  call    cs:__imp_RegOpenKeyExW
0x180007985  cmp     eax, 2
0x180007988  jnz     short loc_1800079BC
0x18000798a  mov     [rsp+138h+lpdwDisposition], rbx; lpdwDisposition
0x18000798f  mov     [rsp+138h+var_100], r14; phkResult
0x180007994  mov     [rsp+138h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180007999  mov     [rsp+138h+samDesired], edi; samDesired
0x18000799d  mov     dword ptr [rsp+138h+phkResult], ebx; dwOptions
0x1800079a1  xor     r9d, r9d; lpClass
0x1800079a4  xor     r8d, r8d; Reserved
0x1800079a7  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x1800079af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800079b6  call    cs:__imp_RegCreateKeyExW
0x1800079bc  test    eax, eax
0x1800079be  jle     short loc_1800079C8
0x1800079c0  movzx   eax, ax
0x1800079c3  or      eax, 80070000h
0x1800079c8  mov     [r15], eax
0x1800079cb  mov     rax, rsi
0x1800079ce  mov     rcx, [rsp+138h+var_28]
0x1800079d6  xor     rcx, rsp; StackCookie
0x1800079d9  call    __security_check_cookie
0x1800079de  lea     r11, [rsp+138h+var_18]
0x1800079e6  mov     rbx, [r11+28h]
0x1800079ea  mov     rsi, [r11+30h]
0x1800079ee  mov     rsp, r11
0x1800079f1  pop     r15
0x1800079f3  pop     r14
0x1800079f5  pop     rdi
0x1800079f6  retn
```

# EvaluateCurrentStateFromRegistry(uint,reg_FeatureStage,long volatile *)

- ea: `0x1800020bc`
- end: `0x1800021ec`
- name: `?EvaluateCurrentStateFromRegistry@@YAHIW4reg_FeatureStage@@PECJ@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800021f4`

## callees

- `0x1800020bc`
- `0x180003d98`
- `0x180026670`
- `0x180026d46`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180002197`
- `ADVAPI32!RegCloseKey` at `0x180002197`
- `ADVAPI32!RegQueryValueExW` at `0x180002180`
- `ADVAPI32!RegQueryValueExW` at `0x180002180`
- `ADVAPI32!RegOpenKeyExW` at `0x18000211f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000211f`

## pseudocode

```c
__int64 __fastcall EvaluateCurrentStateFromRegistry(int a1, int a2, volatile signed __int32 *a3)
{
  unsigned int v3; // ebx
  BOOL v6; // edi
  LSTATUS v7; // r14d
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  DWORD Type; // [rsp+34h] [rbp-3Ch] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  WCHAR ValueName[16]; // [rsp+48h] [rbp-28h] BYREF

  v3 = 0;
  cbData = 4;
  v6 = a2 != 1;
  memset_0(ValueName, 0, sizeof(ValueName));
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Policies\\Microsoft\\FeatureManagement\\Overrides",
          0,
          0x20019u,
          &hKey) )
  {
    StringCchPrintfW(
      ValueName,
      0x10u,
      L"%lu",
      __ROR4__(_byteswap_ulong(a1 ^ 0x74161A4E) ^ 0x8FB23D4F, 255) ^ 0x833EA8FF);
    v7 = RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    if ( !v7 && Type == 4 && cbData == 4 )
      v6 = *(_DWORD *)Data != 0;
  }
  _InterlockedCompareExchange(a3, v6 + 1, 0);
  LOBYTE(v3) = *a3 != 1;
  return v3;
}

```

## disassembly

```asm
0x1800020bc  push    rbp
0x1800020be  push    rbx
0x1800020bf  push    rsi
0x1800020c0  push    rdi
0x1800020c1  push    r14
0x1800020c3  mov     rbp, rsp
0x1800020c6  sub     rsp, 70h
0x1800020ca  mov     rax, cs:__security_cookie
0x1800020d1  xor     rax, rsp
0x1800020d4  mov     [rbp+var_8], rax
0x1800020d8  xor     ebx, ebx
0x1800020da  mov     [rbp+cbData], 4
0x1800020e1  cmp     edx, 1
0x1800020e4  mov     rsi, r8
0x1800020e7  mov     r14d, ecx
0x1800020ea  mov     edi, ebx
0x1800020ec  setnz   dil
0x1800020f0  lea     rcx, [rbp+ValueName]; void *
0x1800020f4  xor     edx, edx; Val
0x1800020f6  lea     r8d, [rbx+20h]; Size
0x1800020fa  call    memset_0
0x1800020ff  lea     rax, [rbp+hKey]
0x180002103  mov     r9d, 20019h; samDesired
0x180002109  xor     r8d, r8d; ulOptions
0x18000210c  mov     [rsp+70h+phkResult], rax; phkResult
0x180002111  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Policies\\Mi"...
0x180002118  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000211f  call    cs:__imp_RegOpenKeyExW
0x180002125  test    eax, eax
0x180002127  jnz     loc_1800021C2
0x18000212d  xor     r14d, 74161A4Eh
0x180002134  lea     r8, aLu; "%lu"
0x18000213b  bswap   r14d
0x18000213e  xor     r14d, 8FB23D4Fh
0x180002145  lea     edx, [rbx+10h]; unsigned __int64
0x180002148  ror     r14d, 0FFh
0x18000214c  lea     rcx, [rbp+ValueName]; Buffer
0x180002150  xor     r14d, 833EA8FFh
0x180002157  mov     r9d, r14d
0x18000215a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000215f  mov     rcx, [rbp+hKey]; hKey
0x180002163  lea     rax, [rbp+cbData]
0x180002167  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000216c  lea     r9, [rbp+Type]; lpType
0x180002170  lea     rax, [rbp+Data]
0x180002174  xor     r8d, r8d; lpReserved
0x180002177  lea     rdx, [rbp+ValueName]; lpValueName
0x18000217b  mov     [rsp+70h+phkResult], rax; lpData
0x180002180  call    cs:__imp_RegQueryValueExW
0x180002186  mov     rcx, [rbp+hKey]; hKey
0x18000218a  mov     r14d, eax
0x18000218d  lea     rdx, [rcx-1]
0x180002191  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180002195  ja      short loc_18000219D
0x180002197  call    cs:__imp_RegCloseKey
0x18000219d  test    r14d, r14d
0x1800021a0  jnz     short loc_1800021C2
0x1800021a2  cmp     [rbp+Type], 4
0x1800021a6  jnz     short loc_1800021C2
0x1800021a8  cmp     [rbp+cbData], 4
0x1800021ac  jnz     short loc_1800021C2
0x1800021ae  mov     eax, dword ptr [rbp+Data]
0x1800021b1  mov     edi, ebx
0x1800021b3  neg     eax
0x1800021b5  sbb     ecx, ecx
0x1800021b7  neg     ecx
0x1800021b9  inc     ecx
0x1800021bb  cmp     ecx, 1
0x1800021be  setnz   dil
0x1800021c2  lea     ecx, [rdi+1]
0x1800021c5  xor     eax, eax
0x1800021c7  lock cmpxchg [rsi], ecx
0x1800021cb  mov     ecx, [rsi]
0x1800021cd  cmp     ecx, 1
0x1800021d0  setnz   bl
0x1800021d3  mov     eax, ebx
0x1800021d5  mov     rcx, [rbp+var_8]
0x1800021d9  xor     rcx, rsp; StackCookie
0x1800021dc  call    __security_check_cookie
0x1800021e1  add     rsp, 70h
0x1800021e5  pop     r14
0x1800021e7  pop     rdi
0x1800021e8  pop     rsi
0x1800021e9  pop     rbx
0x1800021ea  pop     rbp
0x1800021eb  retn
```

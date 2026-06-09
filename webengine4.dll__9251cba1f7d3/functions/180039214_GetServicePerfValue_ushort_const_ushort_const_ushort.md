# GetServicePerfValue(ushort const *,ushort const *,ushort * *)

- ea: `0x180039214`
- end: `0x1800393c3`
- name: `?GetServicePerfValue@@YAJPEBG0PEAPEAG@Z`
- size: `431`
- prototype: `__int64 __fastcall(LPCWSTR lpString, LPCWSTR lpValueName, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180038eec`
- `0x180039d9c`

## callees

- `0x18000dd78`
- `0x180039214`
- `0x18004d690`
- `0x18004d754`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18003923c`
- `KERNEL32!lstrlenW` at `0x18003924e`
- `KERNEL32!lstrlenW` at `0x18003925d`
- `KERNEL32!lstrlenW` at `0x18003929b`
- `KERNEL32!lstrlenW` at `0x1800392a6`
- `KERNEL32!lstrlenW` at `0x1800392b5`
- `KERNEL32!lstrlenW` at `0x18003923c`
- `KERNEL32!lstrlenW` at `0x18003924e`
- `KERNEL32!lstrlenW` at `0x18003925d`
- `KERNEL32!lstrlenW` at `0x18003929b`
- `KERNEL32!lstrlenW` at `0x1800392a6`
- `KERNEL32!lstrlenW` at `0x1800392b5`
- `ADVAPI32!RegCloseKey` at `0x18003939d`
- `ADVAPI32!RegCloseKey` at `0x18003939d`
- `ADVAPI32!RegOpenKeyExW` at `0x18003930a`
- `ADVAPI32!RegOpenKeyExW` at `0x18003930a`
- `ADVAPI32!RegQueryValueExW` at `0x18003936a`
- `ADVAPI32!RegQueryValueExW` at `0x18003936a`

## string_xrefs

- `0x180039254`: `SYSTEM\CurrentControlSet\Services\`
- `0x1800392ac`: `SYSTEM\CurrentControlSet\Services\`
- `0x1800392cd`: `SYSTEM\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall GetServicePerfValue(LPCWSTR lpString, LPCWSTR lpValueName, unsigned __int16 **a3)
{
  int v6; // ebx
  int v7; // ebx
  unsigned __int64 v8; // rax
  wchar_t *v9; // rdi
  unsigned int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // eax
  LSTATUS v14; // eax
  unsigned __int16 *v15; // rax
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  Type = 0;
  hKey = 0;
  *a3 = 0;
  v6 = lstrlenW(lpString);
  v7 = lstrlenW(L"Performance") + v6;
  v8 = saturated_mul(v7 + lstrlenW(L"SYSTEM\\CurrentControlSet\\Services\\") + 3, 2u);
  v9 = (wchar_t *)MemAlloc(v8);
  if ( !v9 )
    goto LABEL_2;
  v11 = lstrlenW(lpString);
  v12 = lstrlenW(L"Performance") + v11;
  v13 = lstrlenW(L"SYSTEM\\CurrentControlSet\\Services\\");
  v10 = StringCchPrintfW(
          v9,
          v13 + v12 + 3,
          L"%s\\%s\\%s",
          L"SYSTEM\\CurrentControlSet\\Services\\",
          lpString,
          L"Performance");
  if ( !v10 )
  {
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey);
    if ( v14 )
      goto LABEL_5;
    cbData = 522;
    v15 = (unsigned __int16 *)MemAlloc(0x414u);
    *a3 = v15;
    if ( !v15 )
    {
LABEL_2:
      v10 = -2147024882;
      goto LABEL_13;
    }
    v14 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)v15, &cbData);
    if ( v14 )
    {
LABEL_5:
      v10 = (unsigned __int16)v14 | 0x80070000;
      if ( v14 <= 0 )
        v10 = v14;
    }
    else if ( Type == 1 )
    {
      v10 = 0;
    }
    else
    {
      MemFree(*a3);
      *a3 = 0;
      v10 = -2147023267;
    }
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    MemFree(v9);
  return v10;
}

```

## disassembly

```asm
0x180039214  mov     rax, rsp
0x180039217  mov     [rax+8], rbx
0x18003921b  push    rbp
0x18003921c  push    rsi
0x18003921d  push    rdi
0x18003921e  push    r13
0x180039220  push    r14
0x180039222  sub     rsp, 40h
0x180039226  and     dword ptr [rax+18h], 0
0x18003922a  mov     rsi, r8
0x18003922d  and     qword ptr [rax-38h], 0
0x180039232  mov     r14, rdx
0x180039235  and     qword ptr [r8], 0
0x180039239  mov     rbp, rcx
0x18003923c  call    cs:__imp_lstrlenW
0x180039242  lea     r13, aPerformance; "Performance"
0x180039249  mov     ebx, eax
0x18003924b  mov     rcx, r13; lpString
0x18003924e  call    cs:__imp_lstrlenW
0x180039254  lea     rcx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\"
0x18003925b  add     ebx, eax
0x18003925d  call    cs:__imp_lstrlenW
0x180039263  lea     ecx, [rax+3]
0x180039266  mov     eax, 2
0x18003926b  add     ecx, ebx
0x18003926d  movsxd  rdx, ecx
0x180039270  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180039277  mul     rdx
0x18003927a  cmovo   rax, rcx
0x18003927e  mov     rcx, rax; unsigned __int64
0x180039281  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180039286  mov     rdi, rax
0x180039289  test    rax, rax
0x18003928c  jnz     short loc_180039298
0x18003928e  mov     ebx, 8007000Eh
0x180039293  jmp     loc_180039393
0x180039298  mov     rcx, rbp; lpString
0x18003929b  call    cs:__imp_lstrlenW
0x1800392a1  mov     rcx, r13; lpString
0x1800392a4  mov     ebx, eax
0x1800392a6  call    cs:__imp_lstrlenW
0x1800392ac  lea     rcx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\"
0x1800392b3  add     ebx, eax
0x1800392b5  call    cs:__imp_lstrlenW
0x1800392bb  lea     ecx, [rbx+3]
0x1800392be  mov     [rsp+68h+lpcbData], r13
0x1800392c3  add     ecx, eax
0x1800392c5  mov     [rsp+68h+phkResult], rbp
0x1800392ca  movsxd  rdx, ecx; unsigned __int64
0x1800392cd  lea     r9, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\"
0x1800392d4  mov     rcx, rdi; Buffer
0x1800392d7  lea     r8, aSSS; "%s\\%s\\%s"
0x1800392de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800392e3  mov     ebx, eax
0x1800392e5  test    eax, eax
0x1800392e7  jnz     loc_180039393
0x1800392ed  lea     rax, [rsp+68h+hKey]
0x1800392f2  mov     r9d, 20019h; samDesired
0x1800392f8  xor     r8d, r8d; ulOptions
0x1800392fb  mov     [rsp+68h+phkResult], rax; phkResult
0x180039300  mov     rdx, rdi; lpSubKey
0x180039303  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003930a  call    cs:__imp_RegOpenKeyExW
0x180039310  test    eax, eax
0x180039312  jz      short loc_180039324
0x180039314  movzx   ebx, ax
0x180039317  or      ebx, 80070000h
0x18003931d  test    eax, eax
0x18003931f  cmovle  ebx, eax
0x180039322  jmp     short loc_180039393
0x180039324  mov     ecx, 414h; unsigned __int64
0x180039329  mov     [rsp+68h+cbData], 20Ah
0x180039334  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180039339  mov     [rsi], rax
0x18003933c  test    rax, rax
0x18003933f  jz      loc_18003928E
0x180039345  lea     rcx, [rsp+68h+cbData]
0x18003934d  xor     r8d, r8d; lpReserved
0x180039350  mov     [rsp+68h+lpcbData], rcx; lpcbData
0x180039355  lea     r9, [rsp+68h+Type]; lpType
0x18003935d  mov     rcx, [rsp+68h+hKey]; hKey
0x180039362  mov     rdx, r14; lpValueName
0x180039365  mov     [rsp+68h+phkResult], rax; lpData
0x18003936a  call    cs:__imp_RegQueryValueExW
0x180039370  test    eax, eax
0x180039372  jnz     short loc_180039314
0x180039374  cmp     [rsp+68h+Type], 1
0x18003937c  jz      short loc_180039391
0x18003937e  mov     rcx, [rsi]; lpMem
0x180039381  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180039386  and     qword ptr [rsi], 0
0x18003938a  mov     ebx, 8007065Dh
0x18003938f  jmp     short loc_180039393
0x180039391  xor     ebx, ebx
0x180039393  mov     rcx, [rsp+68h+hKey]; hKey
0x180039398  test    rcx, rcx
0x18003939b  jz      short loc_1800393A3
0x18003939d  call    cs:__imp_RegCloseKey
0x1800393a3  test    rdi, rdi
0x1800393a6  jz      short loc_1800393B0
0x1800393a8  mov     rcx, rdi; lpMem
0x1800393ab  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800393b0  mov     eax, ebx
0x1800393b2  mov     rbx, [rsp+68h+arg_0]
0x1800393b7  add     rsp, 40h
0x1800393bb  pop     r14
0x1800393bd  pop     r13
0x1800393bf  pop     rdi
0x1800393c0  pop     rsi
0x1800393c1  pop     rbp
0x1800393c2  retn
```

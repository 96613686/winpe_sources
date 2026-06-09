# CMSSAdmin::SetDiacritics(int)

- ea: `0x180004844`
- end: `0x180004934`
- name: `?SetDiacritics@CMSSAdmin@@QEAAJH@Z`
- size: `240`
- prototype: `__int64 __fastcall(CMSSAdmin *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004360`
- `0x180012b70`

## callees

- `0x180004844`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000490b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000490b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004921`

## pseudocode

```c
__int64 __fastcall CMSSAdmin::SetDiacritics(CMSSAdmin *this, int a2)
{
  __int64 v2; // rcx
  signed int v4; // ebx
  unsigned int v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  int v9; // [rsp+40h] [rbp+8h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v2 = *((_QWORD *)this + 3);
  v4 = -2147418113;
  if ( v2 )
  {
    v9 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v2 + 88LL))(v2, &v9);
    if ( v4 >= 0 )
    {
      v5 = a2 ? v9 | 2 : v9 & 0xFFFFFFFD;
      Data = v5;
      if ( v5 != v9 )
      {
        hKey = 0;
        v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", 0, 0x40000000u, &hKey);
        v4 = v6;
        if ( v6 > 0 )
          v4 = (unsigned __int16)v6 | 0x80070000;
        if ( v4 >= 0 )
        {
          v7 = RegSetValueExW(hKey, L"SystemIndexNormalization", 0, 4u, (const BYTE *)&Data, 4u);
          v4 = v7;
          if ( v7 > 0 )
            v4 = (unsigned __int16)v7 | 0x80070000;
          RegCloseKey(hKey);
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004844  mov     [rsp+arg_8], rbx
0x180004849  push    rdi
0x18000484a  sub     rsp, 30h
0x18000484e  mov     rcx, [rcx+18h]
0x180004852  mov     edi, edx
0x180004854  mov     ebx, 8000FFFFh
0x180004859  test    rcx, rcx
0x18000485c  jz      loc_180004927
0x180004862  mov     [rsp+38h+arg_0], 0
0x18000486a  lea     rdx, [rsp+38h+arg_0]
0x18000486f  mov     rax, [rcx]
0x180004872  mov     rax, [rax+58h]
0x180004876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487b  mov     ebx, eax
0x18000487d  test    eax, eax
0x18000487f  js      loc_180004927
0x180004885  mov     ecx, [rsp+38h+arg_0]
0x180004889  mov     eax, ecx
0x18000488b  test    edi, edi
0x18000488d  jz      short loc_180004894
0x18000488f  or      eax, 2
0x180004892  jmp     short loc_180004897
0x180004894  and     eax, 0FFFFFFFDh
0x180004897  mov     [rsp+38h+Data], eax
0x18000489b  cmp     eax, ecx
0x18000489d  jz      loc_180004927
0x1800048a3  lea     rax, [rsp+38h+hKey]
0x1800048a8  mov     [rsp+38h+hKey], 0
0x1800048b1  mov     r9d, 40000000h; samDesired
0x1800048b7  mov     [rsp+38h+phkResult], rax; phkResult
0x1800048bc  xor     r8d, r8d; ulOptions
0x1800048bf  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Search"
0x1800048c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800048cd  call    cs:__imp_RegOpenKeyExW
0x1800048d3  mov     ebx, eax
0x1800048d5  mov     edi, 80070000h
0x1800048da  test    eax, eax
0x1800048dc  jle     short loc_1800048E3
0x1800048de  movzx   ebx, ax
0x1800048e1  or      ebx, edi
0x1800048e3  test    ebx, ebx
0x1800048e5  js      short loc_180004927
0x1800048e7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800048ec  lea     rax, [rsp+38h+Data]
0x1800048f1  mov     r9d, 4; dwType
0x1800048f7  lea     rdx, aSystemindexnor; "SystemIndexNormalization"
0x1800048fe  mov     [rsp+38h+cbData], r9d; cbData
0x180004903  xor     r8d, r8d; Reserved
0x180004906  mov     [rsp+38h+phkResult], rax; lpData
0x18000490b  call    cs:__imp_RegSetValueExW
0x180004911  mov     ebx, eax
0x180004913  test    eax, eax
0x180004915  jle     short loc_18000491C
0x180004917  movzx   ebx, ax
0x18000491a  or      ebx, edi
0x18000491c  mov     rcx, [rsp+38h+hKey]; hKey
0x180004921  call    cs:__imp_RegCloseKey
0x180004927  mov     eax, ebx
0x180004929  mov     rbx, [rsp+38h+arg_8]
0x18000492e  add     rsp, 30h
0x180004932  pop     rdi
0x180004933  retn
```

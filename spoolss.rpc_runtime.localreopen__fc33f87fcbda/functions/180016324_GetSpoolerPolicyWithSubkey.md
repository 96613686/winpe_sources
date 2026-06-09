# GetSpoolerPolicyWithSubkey

- ea: `0x180016324`
- end: `0x180016434`
- name: `GetSpoolerPolicyWithSubkey`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800162c8`

## callees

- `0x180016240`
- `0x180016258`
- `0x180016324`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800163d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800163d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016404`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016415`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016404`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016415`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800163a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800163a0`

## pseudocode

```c
__int64 __fastcall GetSpoolerPolicyWithSubkey(HKEY a1, const WCHAR *a2, BYTE *a3, DWORD *a4, DWORD *a5)
{
  int v8; // ebx
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // eax
  int v12; // edx
  HKEY phkResult; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  DWORD Type; // [rsp+70h] [rbp+8h] BYREF
  int v17; // [rsp+74h] [rbp+Ch]

  v17 = HIDWORD(a1);
  hKey = 0;
  phkResult = 0;
  Type = 0;
  if ( a2 && a3 && a4 )
  {
    v8 = OpenPrintPolicyKey(a1, &hKey);
    if ( v8 >= 0 )
    {
      v9 = RegOpenKeyExW(hKey, L"WPP", 0, 0x20019u, &phkResult);
      v8 = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v9, v10);
      if ( v8 >= 0 )
      {
        v11 = RegQueryValueExW(phkResult, a2, 0, &Type, a3, a4);
        v8 = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v11, v12);
        if ( v8 >= 0 && a5 )
          *a5 = Type;
        RegCloseKey(phkResult);
      }
      RegCloseKey(hKey);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016324  mov     rax, rsp
0x180016327  mov     [rax+8], rcx
0x18001632b  push    rbx
0x18001632c  push    rbp
0x18001632d  push    rsi
0x18001632e  push    rdi
0x18001632f  sub     rsp, 48h
0x180016333  mov     qword ptr [rax-30h], 0
0x18001633b  mov     rdi, r9
0x18001633e  mov     qword ptr [rax-38h], 0
0x180016346  mov     rsi, r8
0x180016349  mov     dword ptr [rax+8], 0
0x180016350  mov     rbp, rdx
0x180016353  test    rdx, rdx
0x180016356  jz      loc_180016423
0x18001635c  test    r8, r8
0x18001635f  jz      loc_180016423
0x180016365  test    r9, r9
0x180016368  jz      loc_180016423
0x18001636e  lea     rdx, [rax-30h]; HKEY *
0x180016372  call    ?OpenPrintPolicyKey@@YAJPEAUHKEY__@@PEAPEAU1@@Z; OpenPrintPolicyKey(HKEY__ *,HKEY__ * *)
0x180016377  mov     ebx, eax
0x180016379  test    eax, eax
0x18001637b  js      loc_180016428
0x180016381  mov     rcx, [rsp+68h+hKey]; hKey
0x180016386  lea     rax, [rsp+68h+var_38]
0x18001638b  mov     r9d, 20019h; samDesired
0x180016391  mov     [rsp+68h+phkResult], rax; phkResult
0x180016396  xor     r8d, r8d; ulOptions
0x180016399  lea     rdx, aWpp; "WPP"
0x1800163a0  call    cs:__imp_RegOpenKeyExW
0x1800163a7  nop     dword ptr [rax+rax+00h]
0x1800163ac  mov     ecx, eax; this
0x1800163ae  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x1800163b3  mov     ebx, eax
0x1800163b5  test    eax, eax
0x1800163b7  js      short loc_180016410
0x1800163b9  mov     rcx, [rsp+68h+var_38]; hKey
0x1800163be  lea     r9, [rsp+68h+Type]; lpType
0x1800163c3  mov     [rsp+68h+lpcbData], rdi; lpcbData
0x1800163c8  xor     r8d, r8d; lpReserved
0x1800163cb  mov     rdx, rbp; lpValueName
0x1800163ce  mov     [rsp+68h+phkResult], rsi; lpData
0x1800163d3  call    cs:__imp_RegQueryValueExW
0x1800163da  nop     dword ptr [rax+rax+00h]
0x1800163df  mov     ecx, eax; this
0x1800163e1  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x1800163e6  mov     ebx, eax
0x1800163e8  test    eax, eax
0x1800163ea  js      short loc_1800163FF
0x1800163ec  mov     rcx, [rsp+68h+arg_20]
0x1800163f4  test    rcx, rcx
0x1800163f7  jz      short loc_1800163FF
0x1800163f9  mov     eax, [rsp+68h+Type]
0x1800163fd  mov     [rcx], eax
0x1800163ff  mov     rcx, [rsp+68h+var_38]; hKey
0x180016404  call    cs:__imp_RegCloseKey
0x18001640b  nop     dword ptr [rax+rax+00h]
0x180016410  mov     rcx, [rsp+68h+hKey]; hKey
0x180016415  call    cs:__imp_RegCloseKey
0x18001641c  nop     dword ptr [rax+rax+00h]
0x180016421  jmp     short loc_180016428
0x180016423  mov     ebx, 80004003h
0x180016428  mov     eax, ebx
0x18001642a  add     rsp, 48h
0x18001642e  pop     rdi
0x18001642f  pop     rsi
0x180016430  pop     rbp
0x180016431  pop     rbx
0x180016432  retn
```

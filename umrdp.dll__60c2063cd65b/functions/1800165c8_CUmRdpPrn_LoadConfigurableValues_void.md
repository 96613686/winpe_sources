# CUmRdpPrn::LoadConfigurableValues(void)

- ea: `0x1800165c8`
- end: `0x1800166dc`
- name: `?LoadConfigurableValues@CUmRdpPrn@@AEAAXXZ`
- size: `276`
- prototype: `void __fastcall(CUmRdpPrn *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015428`

## callees

- `0x180009108`
- `0x1800165c8`
- `0x18001948c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800166a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800166a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016606`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016606`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016644`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016644`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800166b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800166b8`

## string_xrefs

- `0x18001663d`: `PrintRdrConfigThreshold`

## pseudocode

```c
void __fastcall CUmRdpPrn::LoadConfigurableValues(CUmRdpPrn *this)
{
  LPVOID *v2; // rdi
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  cbData = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\Wds\\rdpwd",
         0,
         0x20019u,
         &hKey) )
  {
    hKey = 0;
  }
  else
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"PrintRdrConfigThreshold", 0, 0, (LPBYTE)this + 136, &cbData) )
      *((_DWORD *)this + 34) = 20;
    v2 = (LPVOID *)((char *)this + 232);
    if ( (unsigned int)TSNUTL_FetchRegistryValue(hKey, L"PrinterMappingINFName", (unsigned __int16 **)this + 29)
      && !(unsigned int)TSNUTL_FetchRegistryValue(hKey, L"PrinterMappingINFSection", (unsigned __int16 **)this + 30) )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, *v2);
      *v2 = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  CUmRdpPrn::ReadPrinterDriverPolicy(this);
}

```

## disassembly

```asm
0x1800165c8  mov     rax, rsp
0x1800165cb  mov     [rax+8], rbx
0x1800165cf  push    rdi
0x1800165d0  sub     rsp, 30h
0x1800165d4  mov     qword ptr [rax+18h], 0
0x1800165dc  mov     rbx, rcx
0x1800165df  mov     dword ptr [rax+10h], 0
0x1800165e6  lea     rax, [rax+18h]
0x1800165ea  mov     r9d, 20019h; samDesired
0x1800165f0  mov     [rsp+38h+phkResult], rax; phkResult
0x1800165f5  xor     r8d, r8d; ulOptions
0x1800165f8  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x1800165ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016606  call    cs:__imp_RegOpenKeyExW
0x18001660c  test    eax, eax
0x18001660e  jnz     loc_1800166C0
0x180016614  mov     rcx, [rsp+38h+hKey]; hKey
0x180016619  lea     rax, [rsp+38h+cbData]
0x18001661e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180016623  lea     rdi, [rbx+88h]
0x18001662a  xor     r9d, r9d; lpType
0x18001662d  mov     [rsp+38h+phkResult], rdi; lpData
0x180016632  xor     r8d, r8d; lpReserved
0x180016635  mov     [rsp+38h+cbData], 4
0x18001663d  lea     rdx, aPrintrdrconfig; "PrintRdrConfigThreshold"
0x180016644  call    cs:__imp_RegQueryValueExW
0x18001664a  test    eax, eax
0x18001664c  jz      short loc_180016654
0x18001664e  mov     dword ptr [rdi], 14h
0x180016654  mov     rcx, [rsp+38h+hKey]; hkey
0x180016659  lea     rdi, [rbx+0E8h]
0x180016660  mov     r8, rdi; unsigned __int16 **
0x180016663  lea     rdx, aPrintermapping; "PrinterMappingINFName"
0x18001666a  call    ?TSNUTL_FetchRegistryValue@@YAHPEAUHKEY__@@PEAGPEAPEAG@Z; TSNUTL_FetchRegistryValue(HKEY__ *,ushort *,ushort * *)
0x18001666f  test    eax, eax
0x180016671  jz      short loc_1800166AE
0x180016673  mov     rcx, [rsp+38h+hKey]; hkey
0x180016678  lea     r8, [rbx+0F0h]; unsigned __int16 **
0x18001667f  lea     rdx, aPrintermapping_0; "PrinterMappingINFSection"
0x180016686  call    ?TSNUTL_FetchRegistryValue@@YAHPEAUHKEY__@@PEAGPEAPEAG@Z; TSNUTL_FetchRegistryValue(HKEY__ *,ushort *,ushort * *)
0x18001668b  test    eax, eax
0x18001668d  jnz     short loc_1800166AE
0x18001668f  mov     rcx, gs:60h
0x180016698  xor     edx, edx; dwFlags
0x18001669a  mov     r8, [rdi]; lpMem
0x18001669d  mov     rcx, [rcx+30h]; hHeap
0x1800166a1  call    cs:__imp_HeapFree
0x1800166a7  mov     qword ptr [rdi], 0
0x1800166ae  mov     rcx, [rsp+38h+hKey]; hKey
0x1800166b3  test    rcx, rcx
0x1800166b6  jz      short loc_1800166C9
0x1800166b8  call    cs:__imp_RegCloseKey
0x1800166be  jmp     short loc_1800166C9
0x1800166c0  mov     [rsp+38h+hKey], 0
0x1800166c9  mov     rcx, rbx; this
0x1800166cc  call    ?ReadPrinterDriverPolicy@CUmRdpPrn@@QEAAXXZ; CUmRdpPrn::ReadPrinterDriverPolicy(void)
0x1800166d1  mov     rbx, [rsp+38h+arg_0]
0x1800166d6  add     rsp, 30h
0x1800166da  pop     rdi
0x1800166db  retn
```

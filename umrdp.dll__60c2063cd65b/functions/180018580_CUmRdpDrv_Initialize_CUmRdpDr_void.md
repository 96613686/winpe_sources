# CUmRdpDrv::Initialize(CUmRdpDr *,void *)

- ea: `0x180018580`
- end: `0x18001861c`
- name: `?Initialize@CUmRdpDrv@@QEAAHPEAVCUmRdpDr@@PEAX@Z`
- size: `156`
- prototype: `__int64 __fastcall(CUmRdpDrv *__hidden this, struct CUmRdpDr *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180011850`

## callees

- `0x180018580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800185c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800185c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800185f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800185f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018604`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018604`

## string_xrefs

- `0x1800185a1`: `SYSTEM\CurrentControlSet\Services\RDPNP\NetworkProvider`

## pseudocode

```c
__int64 __fastcall CUmRdpDrv::Initialize(CUmRdpDrv *this, struct CUmRdpDr *a2, void *a3)
{
  BYTE *v3; // rbx
  __int64 result; // rax
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = a2;
  v3 = (BYTE *)this + 12;
  *((_QWORD *)this + 67) = a3;
  hKey = 0;
  cbData = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RDPNP\\NetworkProvider",
         0,
         0x20019u,
         &hKey) )
  {
    result = 0;
    *(_WORD *)v3 = 0;
  }
  else
  {
    cbData = 520;
    RegQueryValueExW(hKey, L"Name", 0, 0, v3, &cbData);
    RegCloseKey(hKey);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180018580  push    rbx
0x180018582  sub     rsp, 30h
0x180018586  mov     [rcx], rdx
0x180018589  lea     rbx, [rcx+0Ch]
0x18001858d  mov     [rcx+218h], r8
0x180018594  lea     rax, [rsp+38h+hKey]
0x180018599  xor     r8d, r8d; ulOptions
0x18001859c  mov     [rsp+38h+phkResult], rax; phkResult
0x1800185a1  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\RD"...
0x1800185a8  mov     [rsp+38h+hKey], 0
0x1800185b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800185b8  mov     [rsp+38h+cbData], 0
0x1800185c0  mov     r9d, 20019h; samDesired
0x1800185c6  call    cs:__imp_RegOpenKeyExW
0x1800185cc  test    eax, eax
0x1800185ce  jnz     short loc_180018611
0x1800185d0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800185d5  lea     rax, [rsp+38h+cbData]
0x1800185da  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800185df  lea     rdx, aName; "Name"
0x1800185e6  xor     r9d, r9d; lpType
0x1800185e9  mov     [rsp+38h+phkResult], rbx; lpData
0x1800185ee  xor     r8d, r8d; lpReserved
0x1800185f1  mov     [rsp+38h+cbData], 208h
0x1800185f9  call    cs:__imp_RegQueryValueExW
0x1800185ff  mov     rcx, [rsp+38h+hKey]; hKey
0x180018604  call    cs:__imp_RegCloseKey
0x18001860a  mov     eax, 1
0x18001860f  jmp     short loc_180018616
0x180018611  xor     eax, eax
0x180018613  mov     [rbx], ax
0x180018616  add     rsp, 30h
0x18001861a  pop     rbx
0x18001861b  retn
```

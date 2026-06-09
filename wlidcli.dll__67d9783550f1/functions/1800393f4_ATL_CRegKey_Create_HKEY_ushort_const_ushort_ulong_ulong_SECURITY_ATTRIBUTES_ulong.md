# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1800393f4`
- end: `0x18003948d`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `153`
- prototype: `__int64 __usercall@<rax>(ATL::CRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, DWORD, REGSAM, LPSECURITY_ATTRIBUTES, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a3fc`
- `0x18005b540`
- `0x18005b690`

## callees

- `0x18000d554`
- `0x1800393f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039454`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039454`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        DWORD dwOptions,
        REGSAM samDesired,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        unsigned int *a8)
{
  unsigned int v9; // edx
  DWORD dwDisposition; // [rsp+50h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-10h] BYREF

  dwDisposition = 0;
  phkResult = 0;
  v9 = RegCreateKeyExW(hKey, lpSubKey, 0, a4, dwOptions, samDesired, lpSecurityAttributes, &phkResult, &dwDisposition);
  if ( a8 )
    *a8 = dwDisposition;
  if ( !v9 )
  {
    v9 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v9;
}

```

## disassembly

```asm
0x1800393f4  push    rbx
0x1800393f6  sub     rsp, 60h
0x1800393fa  mov     r10, r8
0x1800393fd  mov     [rsp+68h+dwDisposition], 0
0x180039405  mov     r11, rdx
0x180039408  mov     [rsp+68h+var_10], 0
0x180039411  lea     rax, [rsp+68h+dwDisposition]
0x180039416  mov     rbx, rcx
0x180039419  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18003941e  xor     r8d, r8d; Reserved
0x180039421  lea     rax, [rsp+68h+var_10]
0x180039426  mov     rdx, r10; lpSubKey
0x180039429  mov     [rsp+68h+phkResult], rax; phkResult
0x18003942e  mov     rcx, r11; hKey
0x180039431  mov     rax, [rsp+68h+arg_30]
0x180039439  mov     [rsp+68h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18003943e  mov     eax, [rsp+68h+arg_28]
0x180039445  mov     [rsp+68h+samDesired], eax; samDesired
0x180039449  mov     eax, [rsp+68h+arg_20]
0x180039450  mov     [rsp+68h+dwOptions], eax; dwOptions
0x180039454  call    cs:__imp_RegCreateKeyExW
0x18003945a  mov     edx, eax
0x18003945c  mov     rax, [rsp+68h+arg_38]
0x180039464  test    rax, rax
0x180039467  jz      short loc_18003946F
0x180039469  mov     ecx, [rsp+68h+dwDisposition]
0x18003946d  mov     [rax], ecx
0x18003946f  test    edx, edx
0x180039471  jnz     short loc_180039485
0x180039473  mov     rcx, rbx; this
0x180039476  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003947b  mov     edx, eax
0x18003947d  mov     rax, [rsp+68h+var_10]
0x180039482  mov     [rbx], rax
0x180039485  mov     eax, edx
0x180039487  add     rsp, 60h
0x18003948b  pop     rbx
0x18003948c  retn
```

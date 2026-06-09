# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18001db54`
- end: `0x18001dbed`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `153`
- prototype: `__int64 __usercall@<rax>(ATL::CRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, DWORD, REGSAM, LPSECURITY_ATTRIBUTES, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ef4c`
- `0x180039a00`
- `0x180039b10`
- `0x18003f44c`

## callees

- `0x180011530`
- `0x18001db54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dbb4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dbb4`

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
0x18001db54  push    rbx
0x18001db56  sub     rsp, 60h
0x18001db5a  mov     r10, r8
0x18001db5d  mov     [rsp+68h+dwDisposition], 0
0x18001db65  mov     r11, rdx
0x18001db68  mov     [rsp+68h+var_10], 0
0x18001db71  lea     rax, [rsp+68h+dwDisposition]
0x18001db76  mov     rbx, rcx
0x18001db79  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18001db7e  xor     r8d, r8d; Reserved
0x18001db81  lea     rax, [rsp+68h+var_10]
0x18001db86  mov     rdx, r10; lpSubKey
0x18001db89  mov     [rsp+68h+phkResult], rax; phkResult
0x18001db8e  mov     rcx, r11; hKey
0x18001db91  mov     rax, [rsp+68h+arg_30]
0x18001db99  mov     [rsp+68h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18001db9e  mov     eax, [rsp+68h+arg_28]
0x18001dba5  mov     [rsp+68h+samDesired], eax; samDesired
0x18001dba9  mov     eax, [rsp+68h+arg_20]
0x18001dbb0  mov     [rsp+68h+dwOptions], eax; dwOptions
0x18001dbb4  call    cs:__imp_RegCreateKeyExW
0x18001dbba  mov     edx, eax
0x18001dbbc  mov     rax, [rsp+68h+arg_38]
0x18001dbc4  test    rax, rax
0x18001dbc7  jz      short loc_18001DBCF
0x18001dbc9  mov     ecx, [rsp+68h+dwDisposition]
0x18001dbcd  mov     [rax], ecx
0x18001dbcf  test    edx, edx
0x18001dbd1  jnz     short loc_18001DBE5
0x18001dbd3  mov     rcx, rbx; this
0x18001dbd6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001dbdb  mov     edx, eax
0x18001dbdd  mov     rax, [rsp+68h+var_10]
0x18001dbe2  mov     [rbx], rax
0x18001dbe5  mov     eax, edx
0x18001dbe7  add     rsp, 60h
0x18001dbeb  pop     rbx
0x18001dbec  retn
```

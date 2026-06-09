# CDevNode::GetSoftwareKey(std::unique_ptr<CRegistryKey,std::default_delete<CRegistryKey>> &)

- ea: `0x18000af00`
- end: `0x18000af8c`
- name: `?GetSoftwareKey@CDevNode@@QEAAXAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z`
- size: `140`
- prototype: `CRegistryKey *__fastcall(_QWORD *, CRegistryKey **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008a60`

## callees

- `0x18000246c`
- `0x180007264`
- `0x180008020`
- `0x18000af00`
- `0x18000bc58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af44`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18000af2b`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18000af2b`

## pseudocode

```c
CRegistryKey *__fastcall CDevNode::GetSoftwareKey(_QWORD *a1, CRegistryKey **a2)
{
  HKEY v3; // rdi
  DWORD LastError; // eax
  CRegistryKey *result; // rax
  CRegistryKey *v6; // rdx
  CRegistryKey *v7; // [rsp+40h] [rbp+8h]

  v3 = (HKEY)DevObjOpenDevRegKey(*a1, a1 + 2, 1, 0, 2, 3);
  if ( v3 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL && GetLastError() )
  {
    LastError = GetLastError();
    CException::ThrowException(LastError, 0, 0);
  }
  v7 = (CRegistryKey *)operator new(0x20u);
  result = CRegistryKey::CRegistryKey(v7, v3);
  v6 = *a2;
  *a2 = result;
  if ( v6 )
    return (CRegistryKey *)std::default_delete<CRegistryKey>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000af00  mov     [rsp+arg_8], rbx
0x18000af05  push    rdi
0x18000af06  sub     rsp, 30h
0x18000af0a  xor     r9d, r9d
0x18000af0d  mov     [rsp+38h+var_10], 3
0x18000af15  mov     rbx, rdx
0x18000af18  mov     [rsp+38h+var_18], 2
0x18000af20  lea     rdx, [rcx+10h]
0x18000af24  mov     rcx, [rcx]
0x18000af27  lea     r8d, [r9+1]
0x18000af2b  call    cs:__imp_DevObjOpenDevRegKey
0x18000af31  mov     rdi, rax
0x18000af34  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000af38  jnz     short loc_18000AF57
0x18000af3a  call    cs:__imp_GetLastError
0x18000af40  test    eax, eax
0x18000af42  jz      short loc_18000AF57
0x18000af44  call    cs:__imp_GetLastError
0x18000af4a  xor     r8d, r8d
0x18000af4d  xor     edx, edx
0x18000af4f  mov     ecx, eax
0x18000af51  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000af57  mov     ecx, 20h ; ' '; Size
0x18000af5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000af61  mov     rdx, rdi; HKEY
0x18000af64  mov     [rsp+38h+arg_0], rax
0x18000af69  mov     rcx, rax; this
0x18000af6c  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@@Z; CRegistryKey::CRegistryKey(HKEY__ *)
0x18000af71  mov     rdx, [rbx]
0x18000af74  mov     [rbx], rax
0x18000af77  test    rdx, rdx
0x18000af7a  jz      short loc_18000AF81
0x18000af7c  call    ??R?$default_delete@VCRegistryKey@@@std@@QEBAXPEAVCRegistryKey@@@Z; std::default_delete<CRegistryKey>::operator()(CRegistryKey *)
0x18000af81  mov     rbx, [rsp+38h+arg_8]
0x18000af86  add     rsp, 30h
0x18000af8a  pop     rdi
0x18000af8b  retn
```

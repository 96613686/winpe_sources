# CDevNode::GetHardwareKey(std::unique_ptr<CRegistryKey,std::default_delete<CRegistryKey>> &)

- ea: `0x18000aa38`
- end: `0x18000aac3`
- name: `?GetHardwareKey@CDevNode@@QEAAXAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z`
- size: `139`
- prototype: `CRegistryKey *__fastcall(_QWORD *, CRegistryKey **)`
- caller_count: `15`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180003dc4`
- `0x1800045d0`
- `0x1800053e4`
- `0x180006f18`
- `0x1800073b4`
- `0x180008904`
- `0x180008960`
- `0x180008b6c`
- `0x180008bf0`
- `0x180008f48`
- `0x1800090d4`
- `0x180009204`
- `0x180009424`
- `0x180009748`
- `0x18000ba28`

## callees

- `0x18000246c`
- `0x180007264`
- `0x180008020`
- `0x18000aa38`
- `0x18000bc58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa7b`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18000aa62`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18000aa62`

## pseudocode

```c
CRegistryKey *__fastcall CDevNode::GetHardwareKey(_QWORD *a1, CRegistryKey **a2)
{
  HKEY v3; // rdi
  DWORD LastError; // eax
  CRegistryKey *result; // rax
  CRegistryKey *v6; // rdx
  CRegistryKey *v7; // [rsp+40h] [rbp+8h]

  v3 = (HKEY)DevObjOpenDevRegKey(*a1, a1 + 2, 1, 0, 1, 3);
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
0x18000aa38  mov     [rsp+arg_8], rbx
0x18000aa3d  push    rdi
0x18000aa3e  sub     rsp, 30h
0x18000aa42  mov     rbx, rdx
0x18000aa45  mov     [rsp+38h+var_10], 3
0x18000aa4d  lea     rdx, [rcx+10h]
0x18000aa51  mov     r8d, 1
0x18000aa57  mov     rcx, [rcx]
0x18000aa5a  xor     r9d, r9d
0x18000aa5d  mov     [rsp+38h+var_18], r8d
0x18000aa62  call    cs:__imp_DevObjOpenDevRegKey
0x18000aa68  mov     rdi, rax
0x18000aa6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aa6f  jnz     short loc_18000AA8E
0x18000aa71  call    cs:__imp_GetLastError
0x18000aa77  test    eax, eax
0x18000aa79  jz      short loc_18000AA8E
0x18000aa7b  call    cs:__imp_GetLastError
0x18000aa81  xor     r8d, r8d
0x18000aa84  xor     edx, edx
0x18000aa86  mov     ecx, eax
0x18000aa88  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000aa8e  mov     ecx, 20h ; ' '; Size
0x18000aa93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aa98  mov     rdx, rdi; HKEY
0x18000aa9b  mov     [rsp+38h+arg_0], rax
0x18000aaa0  mov     rcx, rax; this
0x18000aaa3  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@@Z; CRegistryKey::CRegistryKey(HKEY__ *)
0x18000aaa8  mov     rdx, [rbx]
0x18000aaab  mov     [rbx], rax
0x18000aaae  test    rdx, rdx
0x18000aab1  jz      short loc_18000AAB8
0x18000aab3  call    ??R?$default_delete@VCRegistryKey@@@std@@QEBAXPEAVCRegistryKey@@@Z; std::default_delete<CRegistryKey>::operator()(CRegistryKey *)
0x18000aab8  mov     rbx, [rsp+38h+arg_8]
0x18000aabd  add     rsp, 30h
0x18000aac1  pop     rdi
0x18000aac2  retn
```

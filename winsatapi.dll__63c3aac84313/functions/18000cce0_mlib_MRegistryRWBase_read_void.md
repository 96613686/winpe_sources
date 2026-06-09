# mlib::MRegistryRWBase::read(void)

- ea: `0x18000cce0`
- end: `0x18000cd8e`
- name: `?read@MRegistryRWBase@mlib@@UEAAHXZ`
- size: `174`
- prototype: `__int64 __fastcall(mlib::MRegistryRWBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e818`

## callees

- `0x18000cce0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cd11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cd11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd70`

## pseudocode

```c
__int64 __fastcall mlib::MRegistryRWBase::read(HKEY *this)
{
  HKEY *v1; // r14
  LSTATUS v3; // edi
  unsigned int v5; // edi
  DWORD LastError; // esi

  v1 = this + 1;
  v3 = RegOpenKeyExW(this[4], *((LPCWSTR *)this[3] + 3), 0, 0x20019u, this + 1);
  SetLastError(v3);
  if ( v3 )
  {
    *v1 = 0;
    return 1;
  }
  else
  {
    v5 = (*((__int64 (__fastcall **)(HKEY *))*this + 3))(this);
    LastError = GetLastError();
    *((_BYTE *)this + 64) = v5 == 0;
    if ( *v1 )
    {
      RegCloseKey(*v1);
      *v1 = 0;
    }
    SetLastError(LastError);
    return v5;
  }
}

```

## disassembly

```asm
0x18000cce0  mov     [rsp+arg_8], rbx
0x18000cce5  mov     [rsp+arg_10], rdi
0x18000ccea  push    r14
0x18000ccec  sub     rsp, 30h
0x18000ccf0  mov     rdx, [rcx+18h]
0x18000ccf4  lea     r14, [rcx+8]
0x18000ccf8  mov     rbx, rcx
0x18000ccfb  mov     [rsp+38h+phkResult], r14; phkResult
0x18000cd00  mov     rcx, [rcx+20h]; hKey
0x18000cd04  mov     r9d, 20019h; samDesired
0x18000cd0a  xor     r8d, r8d; ulOptions
0x18000cd0d  mov     rdx, [rdx+18h]; lpSubKey
0x18000cd11  call    cs:__imp_RegOpenKeyExW
0x18000cd17  mov     ecx, eax; dwErrCode
0x18000cd19  mov     edi, eax
0x18000cd1b  call    cs:__imp_SetLastError
0x18000cd21  test    edi, edi
0x18000cd23  jz      short loc_18000CD33
0x18000cd25  mov     qword ptr [r14], 0
0x18000cd2c  mov     eax, 1
0x18000cd31  jmp     short loc_18000CD7D
0x18000cd33  mov     rax, [rbx]
0x18000cd36  mov     rcx, rbx
0x18000cd39  mov     [rsp+38h+arg_0], rsi
0x18000cd3e  mov     rax, [rax+18h]
0x18000cd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd47  mov     edi, eax
0x18000cd49  call    cs:__imp_GetLastError
0x18000cd4f  test    edi, edi
0x18000cd51  mov     esi, eax
0x18000cd53  setz    cl
0x18000cd56  mov     [rbx+40h], cl
0x18000cd59  mov     rcx, [r14]; hKey
0x18000cd5c  test    rcx, rcx
0x18000cd5f  jz      short loc_18000CD6E
0x18000cd61  call    cs:__imp_RegCloseKey
0x18000cd67  mov     qword ptr [r14], 0
0x18000cd6e  mov     ecx, esi; dwErrCode
0x18000cd70  call    cs:__imp_SetLastError
0x18000cd76  mov     rsi, [rsp+38h+arg_0]
0x18000cd7b  mov     eax, edi
0x18000cd7d  mov     rbx, [rsp+38h+arg_8]
0x18000cd82  mov     rdi, [rsp+38h+arg_10]
0x18000cd87  add     rsp, 30h
0x18000cd8b  pop     r14
0x18000cd8d  retn
```

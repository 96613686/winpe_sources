# mlib::MRegistryRWBase::write(void)

- ea: `0x18002c9a0`
- end: `0x18002ca03`
- name: `?write@MRegistryRWBase@mlib@@UEAAHXZ`
- size: `99`
- prototype: `__int64 __fastcall(mlib::MRegistryRWBase *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006148`
- `0x180011174`
- `0x18002c7c8`

## callees

- `0x180011670`
- `0x18002c824`
- `0x18002c9a0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c9eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c9eb`

## pseudocode

```c
__int64 __fastcall mlib::MRegistryRWBase::write(mlib::MRegistryRWBase *this)
{
  unsigned int v2; // esi
  DWORD LastError; // ebx

  v2 = 1;
  if ( !(unsigned int)mlib::RegistryKey::OpenKeyWR(this) )
  {
    v2 = (*(__int64 (__fastcall **)(mlib::MRegistryRWBase *))(*(_QWORD *)this + 32LL))(this);
    LastError = GetLastError();
    *((_BYTE *)this + 65) = v2 == 0;
    mlib::RegistryKey::CloseKey(this);
    SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x18002c9a0  mov     [rsp+arg_0], rbx
0x18002c9a5  mov     [rsp+arg_8], rsi
0x18002c9aa  push    rdi
0x18002c9ab  sub     rsp, 20h
0x18002c9af  mov     rdi, rcx
0x18002c9b2  mov     esi, 1
0x18002c9b7  call    ?OpenKeyWR@RegistryKey@mlib@@QEAAHXZ; mlib::RegistryKey::OpenKeyWR(void)
0x18002c9bc  test    eax, eax
0x18002c9be  jnz     short loc_18002C9F1
0x18002c9c0  mov     rax, [rdi]
0x18002c9c3  mov     rcx, rdi
0x18002c9c6  mov     rax, [rax+20h]
0x18002c9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9cf  mov     esi, eax
0x18002c9d1  call    cs:__imp_GetLastError
0x18002c9d7  test    esi, esi
0x18002c9d9  mov     ebx, eax
0x18002c9db  setz    cl
0x18002c9de  mov     [rdi+41h], cl
0x18002c9e1  mov     rcx, rdi; this
0x18002c9e4  call    ?CloseKey@RegistryKey@mlib@@QEAAXXZ; mlib::RegistryKey::CloseKey(void)
0x18002c9e9  mov     ecx, ebx; dwErrCode
0x18002c9eb  call    cs:__imp_SetLastError
0x18002c9f1  mov     rbx, [rsp+28h+arg_0]
0x18002c9f6  mov     eax, esi
0x18002c9f8  mov     rsi, [rsp+28h+arg_8]
0x18002c9fd  add     rsp, 20h
0x18002ca01  pop     rdi
0x18002ca02  retn
```

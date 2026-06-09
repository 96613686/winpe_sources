# _anonymous_namespace_::lua_vm_entry_t::_lua_vm_entry_t

- ea: `0x18008f3ec`
- end: `0x18008f458`
- name: `_anonymous_namespace_::lua_vm_entry_t::_lua_vm_entry_t`
- size: `108`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180090780`
- `0x180090bf0`
- `0x18009a883`
- `0x18009acef`

## callees

- `0x18003b0bc`
- `0x18008f3ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configthreadlocale` at `0x18008f431`
- `api-ms-win-crt-private-l1-1-0!_o__configthreadlocale` at `0x18008f431`
- `api-ms-win-crt-private-l1-1-0!_o_setlocale` at `0x18008f428`
- `api-ms-win-crt-private-l1-1-0!_o_setlocale` at `0x18008f428`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f401`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f401`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f447`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18008f40d`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18008f40d`

## pseudocode

```c
HLOCAL __fastcall anonymous_namespace_::lua_vm_entry_t::_lua_vm_entry_t(__int64 a1)
{
  const WCHAR *v1; // rbx
  HANDLE CurrentThread; // rax
  __int64 v4; // rdx
  HLOCAL result; // rax

  v1 = *(const WCHAR **)a1;
  if ( *(_QWORD *)a1 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadDescription(CurrentThread, v1);
  }
  if ( *(_QWORD *)(a1 + 40) <= 0xFu )
    v4 = a1 + 16;
  else
    v4 = *(_QWORD *)(a1 + 16);
  _o_setlocale(0, v4);
  _o__configthreadlocale(*(unsigned int *)(a1 + 8));
  result = (HLOCAL)std::string::~string(a1 + 16);
  if ( *(_QWORD *)a1 )
    return LocalFree(*(HLOCAL *)a1);
  return result;
}

```

## disassembly

```asm
0x18008f3ec  mov     [rsp+arg_0], rbx
0x18008f3f1  push    rdi
0x18008f3f2  sub     rsp, 20h
0x18008f3f6  mov     rbx, [rcx]
0x18008f3f9  mov     rdi, rcx
0x18008f3fc  test    rbx, rbx
0x18008f3ff  jz      short loc_18008F413
0x18008f401  call    cs:__imp_GetCurrentThread
0x18008f407  mov     rcx, rax; hThread
0x18008f40a  mov     rdx, rbx; lpThreadDescription
0x18008f40d  call    cs:__imp_SetThreadDescription
0x18008f413  lea     rbx, [rdi+10h]
0x18008f417  cmp     qword ptr [rbx+18h], 0Fh
0x18008f41c  jbe     short loc_18008F423
0x18008f41e  mov     rdx, [rbx]
0x18008f421  jmp     short loc_18008F426
0x18008f423  mov     rdx, rbx
0x18008f426  xor     ecx, ecx
0x18008f428  call    cs:__imp__o_setlocale
0x18008f42e  mov     ecx, [rdi+8]
0x18008f431  call    cs:__imp__o__configthreadlocale
0x18008f437  mov     rcx, rbx
0x18008f43a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18008f43f  mov     rcx, [rdi]; hMem
0x18008f442  test    rcx, rcx
0x18008f445  jz      short loc_18008F44D
0x18008f447  call    cs:__imp_LocalFree
0x18008f44d  mov     rbx, [rsp+28h+arg_0]
0x18008f452  add     rsp, 20h
0x18008f456  pop     rdi
0x18008f457  retn
```

# CSpDynamicString::_allocate(ulong)

- ea: `0x180004b24`
- end: `0x180004b8e`
- name: `?_allocate@CSpDynamicString@@AEAAJK@Z`
- size: `106`
- prototype: `__int64 __fastcall(CSpDynamicString *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x180004b24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004b46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004b46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b78`

## pseudocode

```c
__int64 __fastcall CSpDynamicString::_allocate(CSpDynamicString *this, unsigned int a2)
{
  __int64 v3; // rbx
  SIZE_T v4; // rcx
  _WORD *v5; // rax
  _WORD *v6; // rdx
  __int64 result; // rax

  if ( a2 >= 0x4FFFFFFF || (v3 = a2, v4 = 2LL * (a2 + 1), v4 <= a2) )
  {
    SetLastError(0x216u);
    return 2147942934LL;
  }
  else
  {
    v5 = CoTaskMemAlloc(v4);
    *(_QWORD *)this = v5;
    v6 = v5;
    if ( v5 )
    {
      result = 0;
      v6[v3] = 0;
    }
    else
    {
      SetLastError(0xEu);
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004b24  mov     [rsp+arg_0], rbx
0x180004b29  push    rdi
0x180004b2a  sub     rsp, 20h
0x180004b2e  mov     rdi, rcx
0x180004b31  cmp     edx, 4FFFFFFFh
0x180004b37  jnb     short loc_180004B73
0x180004b39  lea     ecx, [rdx+1]
0x180004b3c  mov     ebx, edx
0x180004b3e  add     rcx, rcx; cb
0x180004b41  cmp     rcx, rbx
0x180004b44  jbe     short loc_180004B73
0x180004b46  call    cs:__imp_CoTaskMemAlloc
0x180004b4c  mov     [rdi], rax
0x180004b4f  mov     rdx, rax
0x180004b52  test    rax, rax
0x180004b55  jz      short loc_180004B61
0x180004b57  xor     eax, eax
0x180004b59  xor     ecx, ecx
0x180004b5b  mov     [rdx+rbx*2], cx
0x180004b5f  jmp     short loc_180004B83
0x180004b61  mov     ecx, 0Eh; dwErrCode
0x180004b66  call    cs:__imp_SetLastError
0x180004b6c  mov     eax, 8007000Eh
0x180004b71  jmp     short loc_180004B83
0x180004b73  mov     ecx, 216h; dwErrCode
0x180004b78  call    cs:__imp_SetLastError
0x180004b7e  mov     eax, 80070216h
0x180004b83  mov     rbx, [rsp+28h+arg_0]
0x180004b88  add     rsp, 20h
0x180004b8c  pop     rdi
0x180004b8d  retn
```

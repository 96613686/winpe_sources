# CSpDynamicString::_allocate(ulong)

- ea: `0x180006160`
- end: `0x1800061ca`
- name: `?_allocate@CSpDynamicString@@AEAAJK@Z`
- size: `106`
- prototype: `__int64 __fastcall(CSpDynamicString *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004a18`
- `0x180004a80`
- `0x180004b60`
- `0x18000725c`

## callees

- `0x180006160`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061b4`

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
0x180006160  mov     [rsp+arg_0], rbx
0x180006165  push    rdi
0x180006166  sub     rsp, 20h
0x18000616a  mov     rdi, rcx
0x18000616d  cmp     edx, 4FFFFFFFh
0x180006173  jnb     short loc_1800061AF
0x180006175  lea     ecx, [rdx+1]
0x180006178  mov     ebx, edx
0x18000617a  add     rcx, rcx; cb
0x18000617d  cmp     rcx, rbx
0x180006180  jbe     short loc_1800061AF
0x180006182  call    cs:__imp_CoTaskMemAlloc
0x180006188  mov     [rdi], rax
0x18000618b  mov     rdx, rax
0x18000618e  test    rax, rax
0x180006191  jz      short loc_18000619D
0x180006193  xor     eax, eax
0x180006195  xor     ecx, ecx
0x180006197  mov     [rdx+rbx*2], cx
0x18000619b  jmp     short loc_1800061BF
0x18000619d  mov     ecx, 0Eh; dwErrCode
0x1800061a2  call    cs:__imp_SetLastError
0x1800061a8  mov     eax, 8007000Eh
0x1800061ad  jmp     short loc_1800061BF
0x1800061af  mov     ecx, 216h; dwErrCode
0x1800061b4  call    cs:__imp_SetLastError
0x1800061ba  mov     eax, 80070216h
0x1800061bf  mov     rbx, [rsp+28h+arg_0]
0x1800061c4  add     rsp, 20h
0x1800061c8  pop     rdi
0x1800061c9  retn
```

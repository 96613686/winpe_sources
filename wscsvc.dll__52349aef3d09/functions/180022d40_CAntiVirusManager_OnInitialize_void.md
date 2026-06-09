# CAntiVirusManager::OnInitialize(void)

- ea: `0x180022d40`
- end: `0x180022d93`
- name: `?OnInitialize@CAntiVirusManager@@MEAAJXZ`
- size: `83`
- prototype: `__int64 __fastcall(CAntiVirusManager *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180022d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180022d70`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180022d70`
- `OLEAUT32!__imp_SysAllocString` at `0x180022d5b`
- `OLEAUT32!__imp_SysAllocString` at `0x180022d5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180022d7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180022d7b`

## pseudocode

```c
__int64 __fastcall CAntiVirusManager::OnInitialize(CAntiVirusManager *this)
{
  unsigned int v2; // ebx
  const OLECHAR *v3; // rax
  OLECHAR *v4; // rdi

  v2 = 0;
  v3 = SysAllocString(L"{D68DDC3A-831F-4fae-9E44-DA132C1ACF46}");
  v4 = (OLECHAR *)v3;
  if ( v3 )
  {
    v2 = CLSIDFromString(v3, (LPCLSID)((char *)this + 88));
    SysFreeString(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x180022d40  mov     [rsp+arg_0], rbx
0x180022d45  mov     [rsp+arg_8], rsi
0x180022d4a  push    rdi
0x180022d4b  sub     rsp, 20h
0x180022d4f  mov     rsi, rcx
0x180022d52  xor     ebx, ebx
0x180022d54  lea     rcx, aD68ddc3a831f4f; "{D68DDC3A-831F-4fae-9E44-DA132C1ACF46}"
0x180022d5b  call    cs:__imp_SysAllocString
0x180022d61  mov     rdi, rax
0x180022d64  test    rax, rax
0x180022d67  jz      short loc_180022D81
0x180022d69  lea     rdx, [rsi+58h]; pclsid
0x180022d6d  mov     rcx, rax; lpsz
0x180022d70  call    cs:__imp_CLSIDFromString
0x180022d76  mov     rcx, rdi; bstrString
0x180022d79  mov     ebx, eax
0x180022d7b  call    cs:__imp_SysFreeString
0x180022d81  mov     rsi, [rsp+28h+arg_8]
0x180022d86  mov     eax, ebx
0x180022d88  mov     rbx, [rsp+28h+arg_0]
0x180022d8d  add     rsp, 20h
0x180022d91  pop     rdi
0x180022d92  retn
```

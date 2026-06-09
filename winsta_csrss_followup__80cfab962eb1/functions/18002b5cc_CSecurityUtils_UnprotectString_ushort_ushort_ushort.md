# CSecurityUtils::UnprotectString(ushort *,ushort *,ushort)

- ea: `0x18002b5cc`
- end: `0x18002b672`
- name: `?UnprotectString@CSecurityUtils@@CAJPEAG0G@Z`
- size: `166`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800223c0`

## callees

- `0x180005b40`
- `0x18002b55c`
- `0x18002b5cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b607`
- `CRYPT32!CryptUnprotectMemory` at `0x18002b5f7`
- `CRYPT32!CryptUnprotectMemory` at `0x18002b5f7`

## string_xrefs

- `0x18002b63a`: `CSecurityUtils::UnprotectString`

## pseudocode

```c
__int64 __fastcall CSecurityUtils::UnprotectString(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 a3)
{
  unsigned __int64 v3; // rsi
  DWORD v5; // edx
  signed int LastError; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  v3 = a3;
  v5 = *a2;
  v11 = 0;
  if ( CryptUnprotectMemory(a1, v5, 2u) )
  {
    v9 = StringCbLengthW(a1, v3, &v11);
    v8 = v9;
    if ( v9 >= 0 )
      *a2 = v11;
    else
      _DbgPrintMessage(8, "StringCbLength failed: 0x%x in %s", v9, "CSecurityUtils::UnprotectString");
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x18002b5cc  mov     [rsp+arg_0], rbx
0x18002b5d1  mov     [rsp+arg_10], rsi
0x18002b5d6  push    rdi
0x18002b5d7  sub     rsp, 20h
0x18002b5db  movzx   esi, r8w
0x18002b5df  mov     rdi, rdx
0x18002b5e2  movzx   edx, word ptr [rdx]; cbDataIn
0x18002b5e5  mov     r8d, 2; dwFlags
0x18002b5eb  mov     rbx, rcx
0x18002b5ee  mov     [rsp+28h+arg_8], 0
0x18002b5f7  call    cs:__imp_CryptUnprotectMemory
0x18002b5fe  nop     dword ptr [rax+rax+00h]
0x18002b603  test    eax, eax
0x18002b605  jnz     short loc_18002B624
0x18002b607  call    cs:__imp_GetLastError
0x18002b60e  nop     dword ptr [rax+rax+00h]
0x18002b613  mov     ebx, eax
0x18002b615  test    eax, eax
0x18002b617  jle     short loc_18002B65F
0x18002b619  movzx   ebx, ax
0x18002b61c  or      ebx, 80070000h
0x18002b622  jmp     short loc_18002B65F
0x18002b624  mov     rdx, rsi; unsigned __int64
0x18002b627  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x18002b62c  mov     rcx, rbx; unsigned __int16 *
0x18002b62f  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002b634  mov     ebx, eax
0x18002b636  test    eax, eax
0x18002b638  jns     short loc_18002B657
0x18002b63a  lea     r9, aCsecurityutils_2; "CSecurityUtils::UnprotectString"
0x18002b641  mov     r8d, eax
0x18002b644  lea     rdx, aStringcblength; "StringCbLength failed: 0x%x in %s"
0x18002b64b  mov     ecx, 8; int
0x18002b650  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b655  jmp     short loc_18002B65F
0x18002b657  movzx   eax, word ptr [rsp+28h+arg_8]
0x18002b65c  mov     [rdi], ax
0x18002b65f  mov     rsi, [rsp+28h+arg_10]
0x18002b664  mov     eax, ebx
0x18002b666  mov     rbx, [rsp+28h+arg_0]
0x18002b66b  add     rsp, 20h
0x18002b66f  pop     rdi
0x18002b670  retn
```

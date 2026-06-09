# CSecurityUtils::UnprotectString(ushort *,ushort *,ushort)

- ea: `0x180029988`
- end: `0x180029a21`
- name: `?UnprotectString@CSecurityUtils@@CAJPEAG0G@Z`
- size: `153`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020c00`

## callees

- `0x180007890`
- `0x180029918`
- `0x180029988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299bd`
- `CRYPT32!CryptUnprotectMemory` at `0x1800299b3`
- `CRYPT32!CryptUnprotectMemory` at `0x1800299b3`

## string_xrefs

- `0x1800299ea`: `CSecurityUtils::UnprotectString`

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
0x180029988  mov     [rsp+arg_0], rbx
0x18002998d  mov     [rsp+arg_10], rsi
0x180029992  push    rdi
0x180029993  sub     rsp, 20h
0x180029997  movzx   esi, r8w
0x18002999b  mov     rdi, rdx
0x18002999e  movzx   edx, word ptr [rdx]; cbDataIn
0x1800299a1  mov     r8d, 2; dwFlags
0x1800299a7  mov     rbx, rcx
0x1800299aa  mov     [rsp+28h+arg_8], 0
0x1800299b3  call    cs:__imp_CryptUnprotectMemory
0x1800299b9  test    eax, eax
0x1800299bb  jnz     short loc_1800299D4
0x1800299bd  call    cs:__imp_GetLastError
0x1800299c3  mov     ebx, eax
0x1800299c5  test    eax, eax
0x1800299c7  jle     short loc_180029A0F
0x1800299c9  movzx   ebx, ax
0x1800299cc  or      ebx, 80070000h
0x1800299d2  jmp     short loc_180029A0F
0x1800299d4  mov     rdx, rsi; unsigned __int64
0x1800299d7  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x1800299dc  mov     rcx, rbx; unsigned __int16 *
0x1800299df  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800299e4  mov     ebx, eax
0x1800299e6  test    eax, eax
0x1800299e8  jns     short loc_180029A07
0x1800299ea  lea     r9, aCsecurityutils_2; "CSecurityUtils::UnprotectString"
0x1800299f1  mov     r8d, eax
0x1800299f4  lea     rdx, aStringcblength; "StringCbLength failed: 0x%x in %s"
0x1800299fb  mov     ecx, 8; int
0x180029a00  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029a05  jmp     short loc_180029A0F
0x180029a07  movzx   eax, word ptr [rsp+28h+arg_8]
0x180029a0c  mov     [rdi], ax
0x180029a0f  mov     rsi, [rsp+28h+arg_10]
0x180029a14  mov     eax, ebx
0x180029a16  mov     rbx, [rsp+28h+arg_0]
0x180029a1b  add     rsp, 20h
0x180029a1f  pop     rdi
0x180029a20  retn
```

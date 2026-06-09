# CACSecurityPage::GetCurrentIHVSecurityProfile(void)

- ea: `0x1800082f8`
- end: `0x180008333`
- name: `?GetCurrentIHVSecurityProfile@CACSecurityPage@@AEAAPEAGXZ`
- size: `59`
- prototype: `unsigned __int16 *__fastcall(CACSecurityPage *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009380`
- `0x18000a29c`
- `0x18000a4b4`
- `0x18000a690`
- `0x18000b6f8`
- `0x18000bb54`
- `0x18000d714`

## callees

- `0x1800082f8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008319`
- `OLEAUT32!__imp_SysAllocString` at `0x180008322`
- `OLEAUT32!__imp_SysAllocString` at `0x180008319`
- `OLEAUT32!__imp_SysAllocString` at `0x180008322`

## pseudocode

```c
BSTR __fastcall CACSecurityPage::GetCurrentIHVSecurityProfile(CACSecurityPage *this)
{
  __int64 v1; // rdx
  const OLECHAR *v2; // rcx
  const OLECHAR *v3; // rax

  v1 = 0;
  v2 = *(const OLECHAR **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 552LL) + 32LL) + 440LL);
  if ( v2 )
  {
    v3 = SysAllocString(v2);
    return SysAllocString(v3);
  }
  return (BSTR)v1;
}

```

## disassembly

```asm
0x1800082f8  sub     rsp, 28h
0x1800082fc  mov     rax, [rcx+28h]
0x180008300  xor     edx, edx
0x180008302  mov     rcx, [rax+228h]
0x180008309  mov     rax, [rcx+20h]
0x18000830d  mov     rcx, [rax+1B8h]; psz
0x180008314  test    rcx, rcx
0x180008317  jz      short loc_18000832B
0x180008319  call    cs:__imp_SysAllocString
0x18000831f  mov     rcx, rax; psz
0x180008322  call    cs:__imp_SysAllocString
0x180008328  mov     rdx, rax
0x18000832b  mov     rax, rdx
0x18000832e  add     rsp, 28h
0x180008332  retn
```

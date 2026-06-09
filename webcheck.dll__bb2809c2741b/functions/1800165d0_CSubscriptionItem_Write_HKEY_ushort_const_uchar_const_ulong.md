# CSubscriptionItem::Write(HKEY__ *,ushort const *,uchar const *,ulong)

- ea: `0x1800165d0`
- end: `0x180016657`
- name: `?Write@CSubscriptionItem@@QEAAJPEAUHKEY__@@PEBGPEBEK@Z`
- size: `135`
- prototype: `int(CSubscriptionItem *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016530`
- `0x180016660`

## callees

- `0x1800165d0`
- `0x180019948`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180016646`
- `ADVAPI32!RegCloseKey` at `0x180016646`
- `ADVAPI32!RegSetValueExW` at `0x180016630`
- `ADVAPI32!RegSetValueExW` at `0x180016630`

## pseudocode

```c
__int64 __fastcall CSubscriptionItem::Write(
        CSubscriptionItem *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        DWORD cbData)
{
  HKEY v6; // rcx
  unsigned int v10; // ebx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = a2;
  v6 = a2;
  v10 = -2147467259;
  if ( !a2 )
  {
    if ( !OpenItemKey((const struct _GUID *)((char *)this + 12), 0, 0x20006u, &hKey) )
      return v10;
    v6 = hKey;
  }
  v10 = RegSetValueExW(v6, a3, 0, 3u, a4, cbData) != 0 ? 0x80004005 : 0;
  if ( !a2 )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x1800165d0  push    rbx
0x1800165d2  push    rbp
0x1800165d3  push    rsi
0x1800165d4  push    rdi
0x1800165d5  sub     rsp, 38h
0x1800165d9  mov     [rsp+58h+hKey], rdx
0x1800165de  mov     rax, rcx
0x1800165e1  mov     rcx, rdx
0x1800165e4  mov     rsi, r9
0x1800165e7  mov     rbp, r8
0x1800165ea  mov     rdi, rdx
0x1800165ed  mov     ebx, 80004005h
0x1800165f2  test    rdx, rdx
0x1800165f5  jnz     short loc_180016614
0x1800165f7  lea     rcx, [rax+0Ch]; struct _GUID *
0x1800165fb  mov     r8d, 20006h; unsigned int
0x180016601  lea     r9, [rsp+58h+hKey]; HKEY *
0x180016606  call    ?OpenItemKey@@YAHPEBU_GUID@@HKPEAPEAUHKEY__@@@Z; OpenItemKey(_GUID const *,int,ulong,HKEY__ * *)
0x18001660b  test    eax, eax
0x18001660d  jz      short loc_18001664C
0x18001660f  mov     rcx, [rsp+58h+hKey]; hKey
0x180016614  mov     eax, [rsp+58h+arg_20]
0x18001661b  mov     r9d, 3; dwType
0x180016621  mov     [rsp+58h+cbData], eax; cbData
0x180016625  xor     r8d, r8d; Reserved
0x180016628  mov     rdx, rbp; lpValueName
0x18001662b  mov     [rsp+58h+lpData], rsi; lpData
0x180016630  call    cs:__imp_RegSetValueExW
0x180016636  neg     eax
0x180016638  sbb     ecx, ecx
0x18001663a  and     ebx, ecx
0x18001663c  test    rdi, rdi
0x18001663f  jnz     short loc_18001664C
0x180016641  mov     rcx, [rsp+58h+hKey]; hKey
0x180016646  call    cs:__imp_RegCloseKey
0x18001664c  mov     eax, ebx
0x18001664e  add     rsp, 38h
0x180016652  pop     rdi
0x180016653  pop     rsi
0x180016654  pop     rbp
0x180016655  pop     rbx
0x180016656  retn
```

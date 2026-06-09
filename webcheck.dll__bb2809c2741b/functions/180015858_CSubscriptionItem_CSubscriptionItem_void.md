# CSubscriptionItem::~CSubscriptionItem(void)

- ea: `0x180015858`
- end: `0x1800158c4`
- name: `??1CSubscriptionItem@@AEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CSubscriptionItem *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800164f0`

## callees

- `0x180015858`
- `0x180019858`
- `0x180029280`

## import_xrefs

- `SHLWAPI!SHDeleteKeyW` at `0x18001589f`
- `SHLWAPI!SHDeleteKeyW` at `0x18001589f`

## pseudocode

```c
void __fastcall CSubscriptionItem::~CSubscriptionItem(CSubscriptionItem *this, __int64 a2, unsigned int a3)
{
  bool v3; // sf
  WCHAR pszSubKey[264]; // [rsp+20h] [rbp-228h] BYREF

  v3 = *((int *)this + 7) < 0;
  *(_QWORD *)this = &CSubscriptionItem::`vftable';
  if ( v3 && ItemKeyNameFromCookie((const struct _GUID *)((char *)this + 12), pszSubKey, a3) )
    SHDeleteKeyW(HKEY_CURRENT_USER, pszSubKey);
  _InterlockedDecrement((volatile signed __int32 *)&g_cObj);
}

```

## disassembly

```asm
0x180015858  sub     rsp, 248h
0x18001585f  mov     rax, cs:__security_cookie
0x180015866  xor     rax, rsp
0x180015869  mov     [rsp+248h+var_18], rax
0x180015871  cmp     dword ptr [rcx+1Ch], 0
0x180015875  lea     rax, ??_7CSubscriptionItem@@6B@; const CSubscriptionItem::`vftable'
0x18001587c  mov     [rcx], rax
0x18001587f  jge     short loc_1800158A5
0x180015881  add     rcx, 0Ch; struct _GUID *
0x180015885  lea     rdx, [rsp+248h+pszSubKey]; unsigned __int16 *
0x18001588a  call    ?ItemKeyNameFromCookie@@YAHPEBU_GUID@@PEAGK@Z; ItemKeyNameFromCookie(_GUID const *,ushort *,ulong)
0x18001588f  test    eax, eax
0x180015891  jz      short loc_1800158A5
0x180015893  lea     rdx, [rsp+248h+pszSubKey]; pszSubKey
0x180015898  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001589f  call    cs:__imp_SHDeleteKeyW
0x1800158a5  lock dec cs:?g_cObj@@3KA; ulong g_cObj
0x1800158ac  mov     rcx, [rsp+248h+var_18]
0x1800158b4  xor     rcx, rsp; StackCookie
0x1800158b7  call    __security_check_cookie
0x1800158bc  add     rsp, 248h
0x1800158c3  retn
```

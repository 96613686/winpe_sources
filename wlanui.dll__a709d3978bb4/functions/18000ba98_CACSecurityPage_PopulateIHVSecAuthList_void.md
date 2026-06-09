# CACSecurityPage::PopulateIHVSecAuthList(void)

- ea: `0x18000ba98`
- end: `0x18000bb4d`
- name: `?PopulateIHVSecAuthList@CACSecurityPage@@AEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x180008498`
- `0x18000ba98`
- `0x180010f64`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000badd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bae6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000badd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bae6`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::PopulateIHVSecAuthList(CACSecurityPage *this)
{
  __int64 v1; // rax
  int PropertyDisplayInfo; // edi
  unsigned __int16 *v4; // rbp
  const OLECHAR *v5; // rcx
  const OLECHAR *v6; // rax
  IHVExtHelper *v7; // rsi
  struct _DOT11EXT_IHV_PARAMS *UpdatedIHVParams; // rax
  struct _DOT11EXT_IHV_PARAMS *v9; // rax

  v1 = *((_QWORD *)this + 154);
  if ( !v1 || !*(_DWORD *)(v1 + 52) )
    return 0;
  PropertyDisplayInfo = 0;
  v4 = 0;
  v5 = *(const OLECHAR **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 552LL) + 32LL) + 440LL);
  if ( v5 )
  {
    v6 = SysAllocString(v5);
    v4 = SysAllocString(v6);
  }
  v7 = *(IHVExtHelper **)(*((_QWORD *)this + 154) + 32LL);
  if ( v7 )
  {
    UpdatedIHVParams = CACSecurityPage::GetUpdatedIHVParams(this);
    PropertyDisplayInfo = IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(v7, v4, UpdatedIHVParams, 0x80010000);
    if ( PropertyDisplayInfo < 0 )
    {
      v9 = CACSecurityPage::GetUpdatedIHVParams(this);
      return (unsigned int)IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(v7, 0, v9, 0x80010000);
    }
  }
  return (unsigned int)PropertyDisplayInfo;
}

```

## disassembly

```asm
0x18000ba98  push    rbx
0x18000ba9a  push    rbp
0x18000ba9b  push    rsi
0x18000ba9c  push    rdi
0x18000ba9d  sub     rsp, 28h
0x18000baa1  mov     rax, [rcx+4D0h]
0x18000baa8  mov     rbx, rcx
0x18000baab  test    rax, rax
0x18000baae  jz      loc_18000BB42
0x18000bab4  cmp     dword ptr [rax+34h], 0
0x18000bab8  jz      loc_18000BB42
0x18000babe  mov     rax, [rcx+28h]
0x18000bac2  xor     edi, edi
0x18000bac4  xor     ebp, ebp
0x18000bac6  mov     rdx, [rax+228h]
0x18000bacd  mov     rax, [rdx+20h]
0x18000bad1  mov     rcx, [rax+1B8h]; psz
0x18000bad8  test    rcx, rcx
0x18000badb  jz      short loc_18000BAEF
0x18000badd  call    cs:__imp_SysAllocString
0x18000bae3  mov     rcx, rax; psz
0x18000bae6  call    cs:__imp_SysAllocString
0x18000baec  mov     rbp, rax
0x18000baef  mov     rax, [rbx+4D0h]
0x18000baf6  mov     rsi, [rax+20h]
0x18000bafa  test    rsi, rsi
0x18000bafd  jz      short loc_18000BB3E
0x18000baff  mov     rcx, rbx; this
0x18000bb02  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000bb07  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x18000bb0a  mov     r9d, 80010000h; unsigned int
0x18000bb10  mov     rdx, rbp; unsigned __int16 *
0x18000bb13  mov     rcx, rsi; this
0x18000bb16  call    ?IHVExtHlpLoadPropertyDisplayInfo@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@K@Z; IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(ushort *,_DOT11EXT_IHV_PARAMS *,ulong)
0x18000bb1b  mov     edi, eax
0x18000bb1d  test    eax, eax
0x18000bb1f  jns     short loc_18000BB3E
0x18000bb21  mov     rcx, rbx; this
0x18000bb24  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000bb29  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x18000bb2c  xor     edx, edx; unsigned __int16 *
0x18000bb2e  mov     r9d, 80010000h; unsigned int
0x18000bb34  mov     rcx, rsi; this
0x18000bb37  call    ?IHVExtHlpLoadPropertyDisplayInfo@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@K@Z; IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(ushort *,_DOT11EXT_IHV_PARAMS *,ulong)
0x18000bb3c  mov     edi, eax
0x18000bb3e  mov     eax, edi
0x18000bb40  jmp     short loc_18000BB44
0x18000bb42  xor     eax, eax
0x18000bb44  add     rsp, 28h
0x18000bb48  pop     rdi
0x18000bb49  pop     rsi
0x18000bb4a  pop     rbp
0x18000bb4b  pop     rbx
0x18000bb4c  retn
```

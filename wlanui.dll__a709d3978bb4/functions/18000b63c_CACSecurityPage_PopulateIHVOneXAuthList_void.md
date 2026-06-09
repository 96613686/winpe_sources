# CACSecurityPage::PopulateIHVOneXAuthList(void)

- ea: `0x18000b63c`
- end: `0x18000b6f1`
- name: `?PopulateIHVOneXAuthList@CACSecurityPage@@AEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x180008498`
- `0x18000b63c`
- `0x180010f64`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b681`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b68a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b681`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b68a`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::PopulateIHVOneXAuthList(CACSecurityPage *this)
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
  v7 = *(IHVExtHelper **)(*((_QWORD *)this + 154) + 40LL);
  if ( v7 )
  {
    UpdatedIHVParams = CACSecurityPage::GetUpdatedIHVParams(this);
    PropertyDisplayInfo = IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(v7, v4, UpdatedIHVParams, 0x80000000);
    if ( PropertyDisplayInfo < 0 )
    {
      v9 = CACSecurityPage::GetUpdatedIHVParams(this);
      return (unsigned int)IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(v7, 0, v9, 0x80000000);
    }
  }
  return (unsigned int)PropertyDisplayInfo;
}

```

## disassembly

```asm
0x18000b63c  push    rbx
0x18000b63e  push    rbp
0x18000b63f  push    rsi
0x18000b640  push    rdi
0x18000b641  sub     rsp, 28h
0x18000b645  mov     rax, [rcx+4D0h]
0x18000b64c  mov     rbx, rcx
0x18000b64f  test    rax, rax
0x18000b652  jz      loc_18000B6E6
0x18000b658  cmp     dword ptr [rax+34h], 0
0x18000b65c  jz      loc_18000B6E6
0x18000b662  mov     rax, [rcx+28h]
0x18000b666  xor     edi, edi
0x18000b668  xor     ebp, ebp
0x18000b66a  mov     rdx, [rax+228h]
0x18000b671  mov     rax, [rdx+20h]
0x18000b675  mov     rcx, [rax+1B8h]; psz
0x18000b67c  test    rcx, rcx
0x18000b67f  jz      short loc_18000B693
0x18000b681  call    cs:__imp_SysAllocString
0x18000b687  mov     rcx, rax; psz
0x18000b68a  call    cs:__imp_SysAllocString
0x18000b690  mov     rbp, rax
0x18000b693  mov     rax, [rbx+4D0h]
0x18000b69a  mov     rsi, [rax+28h]
0x18000b69e  test    rsi, rsi
0x18000b6a1  jz      short loc_18000B6E2
0x18000b6a3  mov     rcx, rbx; this
0x18000b6a6  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000b6ab  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x18000b6ae  mov     r9d, 80000000h; unsigned int
0x18000b6b4  mov     rdx, rbp; unsigned __int16 *
0x18000b6b7  mov     rcx, rsi; this
0x18000b6ba  call    ?IHVExtHlpLoadPropertyDisplayInfo@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@K@Z; IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(ushort *,_DOT11EXT_IHV_PARAMS *,ulong)
0x18000b6bf  mov     edi, eax
0x18000b6c1  test    eax, eax
0x18000b6c3  jns     short loc_18000B6E2
0x18000b6c5  mov     rcx, rbx; this
0x18000b6c8  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000b6cd  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x18000b6d0  xor     edx, edx; unsigned __int16 *
0x18000b6d2  mov     r9d, 80000000h; unsigned int
0x18000b6d8  mov     rcx, rsi; this
0x18000b6db  call    ?IHVExtHlpLoadPropertyDisplayInfo@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@K@Z; IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(ushort *,_DOT11EXT_IHV_PARAMS *,ulong)
0x18000b6e0  mov     edi, eax
0x18000b6e2  mov     eax, edi
0x18000b6e4  jmp     short loc_18000B6E8
0x18000b6e6  xor     eax, eax
0x18000b6e8  add     rsp, 28h
0x18000b6ec  pop     rdi
0x18000b6ed  pop     rsi
0x18000b6ee  pop     rbp
0x18000b6ef  pop     rbx
0x18000b6f0  retn
```

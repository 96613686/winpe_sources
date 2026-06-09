# ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(void)

- ea: `0x18000cfa4`
- end: `0x18000cfcd`
- name: `??1?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d130`
- `0x18000d180`
- `0x1800105cc`
- `0x18002e34f`
- `0x18002e373`
- `0x18002e651`

## callees

- `0x18000cfa4`
- `0x18000d60c`

## import_xrefs

- `msvcrt!free` at `0x18000cfc1`
- `msvcrt!free` at `0x18000cfc1`

## pseudocode

```c
void __fastcall ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::~CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallDestructors(
      v2,
      *(_QWORD *)(a1 + 8));
    free(*(void **)a1);
  }
}

```

## disassembly

```asm
0x18000cfa4  push    rbx
0x18000cfa6  sub     rsp, 20h
0x18000cfaa  mov     rbx, rcx
0x18000cfad  mov     rcx, [rcx]
0x18000cfb0  test    rcx, rcx
0x18000cfb3  jz      short loc_18000CFC7
0x18000cfb5  mov     rdx, [rbx+8]
0x18000cfb9  call    ?CallDestructors@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@CAXPEAV?$CComPtr@VCUICommand@@@2@_K@Z; ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::CallDestructors(ATL::CComPtr<CUICommand> *,unsigned __int64)
0x18000cfbe  mov     rcx, [rbx]; Block
0x18000cfc1  call    cs:__imp_free
0x18000cfc7  add     rsp, 20h
0x18000cfcb  pop     rbx
0x18000cfcc  retn
```

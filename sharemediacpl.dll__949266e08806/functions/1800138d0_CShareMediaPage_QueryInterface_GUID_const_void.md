# CShareMediaPage::QueryInterface(_GUID const &,void * *)

- ea: `0x1800138d0`
- end: `0x18001397d`
- name: `?QueryInterface@CShareMediaPage@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(CShareMediaPage *__hidden this, IID *riid, void **ppv)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180013990`
- `0x1800139b0`
- `0x1800139d0`
- `0x1800139f0`

## callees

- `0x180003860`
- `0x180003888`
- `0x1800138d0`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x180013922`
- `SHLWAPI!__imp_QISearch` at `0x18001393e`
- `SHLWAPI!__imp_QISearch` at `0x180013922`
- `SHLWAPI!__imp_QISearch` at `0x18001393e`

## pseudocode

```c
__int64 __fastcall CShareMediaPage::QueryInterface(CShareMediaPage *this, IID *riid, void **ppv)
{
  HRESULT v6; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, (const GUID *)WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids);
  v6 = QISearch(this, &stru_180020860, riid, ppv);
  if ( v6 < 0 )
    v6 = QISearch(this, &`CElementWithSite::QueryInterface'::`2'::qit, riid, ppv);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0xFu,
      (const GUID *)WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids,
      v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800138d0  push    rbx
0x1800138d2  push    rbp
0x1800138d3  push    rsi
0x1800138d4  push    rdi
0x1800138d5  push    r14
0x1800138d7  sub     rsp, 20h
0x1800138db  mov     rdi, r8
0x1800138de  mov     rsi, rdx
0x1800138e1  mov     rbp, rcx
0x1800138e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138eb  lea     r14, WPP_GLOBAL_Control
0x1800138f2  cmp     rcx, r14
0x1800138f5  jz      short loc_180013912
0x1800138f7  test    byte ptr [rcx+1Ch], 20h
0x1800138fb  jz      short loc_180013912
0x1800138fd  mov     rcx, [rcx+10h]
0x180013901  lea     r8, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids
0x180013908  mov     edx, 0Eh
0x18001390d  call    WPP_SF_
0x180013912  mov     r9, rdi; ppv
0x180013915  lea     rdx, stru_180020860; pqit
0x18001391c  mov     r8, rsi; riid
0x18001391f  mov     rcx, rbp; that
0x180013922  call    cs:__imp_QISearch
0x180013928  mov     ebx, eax
0x18001392a  test    eax, eax
0x18001392c  jns     short loc_180013946
0x18001392e  mov     r9, rdi; ppv
0x180013931  lea     rdx, ?qit@?1??QueryInterface@CElementWithSite@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x180013938  mov     r8, rsi; riid
0x18001393b  mov     rcx, rbp; that
0x18001393e  call    cs:__imp_QISearch
0x180013944  mov     ebx, eax
0x180013946  mov     rcx, cs:WPP_GLOBAL_Control
0x18001394d  cmp     rcx, r14
0x180013950  jz      short loc_180013970
0x180013952  test    byte ptr [rcx+1Ch], 20h
0x180013956  jz      short loc_180013970
0x180013958  mov     rcx, [rcx+10h]
0x18001395c  lea     r8, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids
0x180013963  mov     edx, 0Fh
0x180013968  mov     r9d, ebx
0x18001396b  call    WPP_SF_d
0x180013970  mov     eax, ebx
0x180013972  add     rsp, 20h
0x180013976  pop     r14
0x180013978  pop     rdi
0x180013979  pop     rsi
0x18001397a  pop     rbp
0x18001397b  pop     rbx
0x18001397c  retn
```

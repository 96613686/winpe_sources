# FrameProvider::QueryInterface(_GUID const &,void * *)

- ea: `0x180017f80`
- end: `0x180017fce`
- name: `?QueryInterface@FrameProvider@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `78`
- prototype: `int(FrameProvider *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180017fe0`
- `0x180017ff0`
- `0x180018000`
- `0x180018010`
- `0x180018020`

## callees

- `0x180017f80`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x180017fa5`
- `SHLWAPI!__imp_QISearch` at `0x180017fa5`
- `DUI70!?QueryInterface@XProvider@DirectUI@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x180017fb8`
- `DUI70!?QueryInterface@XProvider@DirectUI@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x180017fb8`

## pseudocode

```c
HRESULT __fastcall FrameProvider::QueryInterface(FrameProvider *this, const struct _GUID *a2, void **a3)
{
  HRESULT result; // eax

  result = QISearch(this, &stru_1800208B0, a2, a3);
  if ( result < 0 )
    return DirectUI::XProvider::QueryInterface(this, a2, a3);
  return result;
}

```

## disassembly

```asm
0x180017f80  mov     [rsp+arg_0], rbx
0x180017f85  mov     [rsp+arg_8], rsi
0x180017f8a  push    rdi
0x180017f8b  sub     rsp, 20h
0x180017f8f  mov     rbx, r8
0x180017f92  mov     r9, r8; ppv
0x180017f95  mov     r8, rdx; riid
0x180017f98  mov     rdi, rdx
0x180017f9b  lea     rdx, stru_1800208B0; pqit
0x180017fa2  mov     rsi, rcx
0x180017fa5  call    cs:__imp_QISearch
0x180017fab  test    eax, eax
0x180017fad  jns     short loc_180017FBE
0x180017faf  mov     r8, rbx
0x180017fb2  mov     rdx, rdi
0x180017fb5  mov     rcx, rsi
0x180017fb8  call    cs:__imp_?QueryInterface@XProvider@DirectUI@@UEAAJAEBU_GUID@@PEAPEAX@Z; DirectUI::XProvider::QueryInterface(_GUID const &,void * *)
0x180017fbe  mov     rbx, [rsp+28h+arg_0]
0x180017fc3  mov     rsi, [rsp+28h+arg_8]
0x180017fc8  add     rsp, 20h
0x180017fcc  pop     rdi
0x180017fcd  retn
```

# CUICommand::GetString(WTL::CString const &,ushort * *)

- ea: `0x1800146e4`
- end: `0x18001472e`
- name: `?GetString@CUICommand@@IEBAJAEBVCString@WTL@@PEAPEAG@Z`
- size: `74`
- prototype: `__int64 __fastcall(CUICommand *__hidden this, const struct WTL::CString *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014920`
- `0x180014940`
- `0x180014990`

## callees

- `0x180011630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014708`

## pseudocode

```c
__int64 __fastcall CUICommand::GetString(CUICommand *this, const unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rax

  v5 = *((_DWORD *)*a2 - 2) + 1;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5);
  *a3 = v6;
  return StringCchCopyW(v6, v5, *a2);
}

```

## disassembly

```asm
0x1800146e4  mov     [rsp+arg_0], rbx
0x1800146e9  mov     [rsp+arg_8], rsi
0x1800146ee  push    rdi
0x1800146ef  sub     rsp, 20h
0x1800146f3  mov     rax, [rdx]
0x1800146f6  mov     rdi, r8
0x1800146f9  mov     rsi, rdx
0x1800146fc  mov     ecx, [rax-8]
0x1800146ff  inc     ecx
0x180014701  movsxd  rbx, ecx
0x180014704  lea     rcx, [rbx+rbx]; cb
0x180014708  call    cs:__imp_CoTaskMemAlloc
0x18001470e  mov     [rdi], rax
0x180014711  mov     rdx, rbx; unsigned __int64
0x180014714  mov     r8, [rsi]; unsigned __int16 *
0x180014717  mov     rcx, rax; unsigned __int16 *
0x18001471a  mov     rbx, [rsp+28h+arg_0]
0x18001471f  mov     rsi, [rsp+28h+arg_8]
0x180014724  add     rsp, 20h
0x180014728  pop     rdi
0x180014729  jmp     ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
```

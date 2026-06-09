# CWMPRichPreviewRemoteService::GetCustomUIMode(ushort * *)

- ea: `0x140004a40`
- end: `0x140004a6d`
- name: `?GetCustomUIMode@CWMPRichPreviewRemoteService@@UEAAJPEAPEAG@Z`
- size: `45`
- prototype: `__int64 __fastcall(CWMPRichPreviewRemoteService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140004a40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140004a5c`
- `OLEAUT32!__imp_SysAllocString` at `0x140004a5c`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::GetCustomUIMode(
        CWMPRichPreviewRemoteService *this,
        unsigned __int16 **a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = SysAllocString(L"res://wmploc/RT_TEXT/RichPreview.wsz");
  return 0;
}

```

## disassembly

```asm
0x140004a40  push    rbx
0x140004a42  sub     rsp, 20h
0x140004a46  mov     rbx, rdx
0x140004a49  test    rdx, rdx
0x140004a4c  jnz     short loc_140004A55
0x140004a4e  mov     eax, 80004003h
0x140004a53  jmp     short loc_140004A67
0x140004a55  lea     rcx, aResWmplocRtTex; "res://wmploc/RT_TEXT/RichPreview.wsz"
0x140004a5c  call    cs:__imp_SysAllocString
0x140004a62  mov     [rbx], rax
0x140004a65  xor     eax, eax
0x140004a67  add     rsp, 20h
0x140004a6b  pop     rbx
0x140004a6c  retn
```

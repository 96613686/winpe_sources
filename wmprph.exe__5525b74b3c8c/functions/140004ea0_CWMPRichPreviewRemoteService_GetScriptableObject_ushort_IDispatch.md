# CWMPRichPreviewRemoteService::GetScriptableObject(ushort * *,IDispatch * *)

- ea: `0x140004ea0`
- end: `0x140004ef6`
- name: `?GetScriptableObject@CWMPRichPreviewRemoteService@@UEAAJPEAPEAGPEAPEAUIDispatch@@@Z`
- size: `86`
- prototype: `__int64 __fastcall(CWMPRichPreviewRemoteService *__hidden this, unsigned __int16 **, struct IDispatch **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update`

## callees

- `0x140004ea0`
- `0x14000f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140004ed4`
- `OLEAUT32!__imp_SysAllocString` at `0x140004ed4`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::GetScriptableObject(
        __int64 (__fastcall ***this)(char *, GUID *),
        unsigned __int16 **a2,
        struct IDispatch **a3)
{
  __int64 result; // rax
  unsigned __int16 *v5; // rax

  if ( !a3 )
    return 2147942487LL;
  result = (**(this - 2))((char *)this - 16, &GUID_00020400_0000_0000_c000_000000000046);
  if ( (int)result < 0 )
    return result;
  if ( !a2 )
    return 2147942487LL;
  v5 = SysAllocString(L"Launcher");
  *a2 = v5;
  return v5 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140004ea0  push    rbx
0x140004ea2  sub     rsp, 20h
0x140004ea6  mov     rbx, rdx
0x140004ea9  test    r8, r8
0x140004eac  jz      short loc_140004EEB
0x140004eae  add     rcx, 0FFFFFFFFFFFFFFF0h
0x140004eb2  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x140004eb9  mov     rax, [rcx]
0x140004ebc  mov     rax, [rax]
0x140004ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ec4  test    eax, eax
0x140004ec6  js      short loc_140004EF0
0x140004ec8  test    rbx, rbx
0x140004ecb  jz      short loc_140004EEB
0x140004ecd  lea     rcx, aLauncher; "Launcher"
0x140004ed4  call    cs:__imp_SysAllocString
0x140004eda  mov     [rbx], rax
0x140004edd  neg     rax
0x140004ee0  sbb     eax, eax
0x140004ee2  not     eax
0x140004ee4  and     eax, 8007000Eh
0x140004ee9  jmp     short loc_140004EF0
0x140004eeb  mov     eax, 80070057h
0x140004ef0  add     rsp, 20h
0x140004ef4  pop     rbx
0x140004ef5  retn
```

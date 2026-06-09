# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18002e028`
- end: `0x18002e047`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `13`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18004ab8c`
- `0x18004abc2`
- `0x18004abd4`
- `0x18004abe6`
- `0x18004abf8`
- `0x18004ac0a`
- `0x18004ac1c`
- `0x18004ac2e`
- `0x18004ac40`
- `0x18004ac52`
- `0x18004b199`
- `0x18004b1bd`
- `0x18004b2b9`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e034`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HString::~HString(HSTRING *this)
{
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18002e028  push    rbx
0x18002e02a  sub     rsp, 20h
0x18002e02e  mov     rbx, rcx
0x18002e031  mov     rcx, [rcx]; string
0x18002e034  call    cs:__imp_WindowsDeleteString
0x18002e03a  mov     qword ptr [rbx], 0
0x18002e041  add     rsp, 20h
0x18002e045  pop     rbx
0x18002e046  retn
```

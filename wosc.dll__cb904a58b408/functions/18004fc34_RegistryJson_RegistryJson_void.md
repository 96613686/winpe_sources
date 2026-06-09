# RegistryJson::~RegistryJson(void)

- ea: `0x18004fc34`
- end: `0x18004fc94`
- name: `??1RegistryJson@@MEAA@XZ`
- size: `96`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18004fe50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fc4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fc5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fc6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fc4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fc5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fc6f`

## pseudocode

```c
void __fastcall RegistryJson::~RegistryJson(HSTRING *this)
{
  *this = (HSTRING)&RegistryJson::`vftable';
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  *this = (HSTRING)&RegValet::IRegistryJson::`vftable';
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18004fc34  push    rbx
0x18004fc36  sub     rsp, 20h
0x18004fc3a  lea     rax, ??_7RegistryJson@@6B@; const RegistryJson::`vftable'
0x18004fc41  mov     rbx, rcx
0x18004fc44  mov     [rcx], rax
0x18004fc47  mov     rcx, [rcx+28h]; string
0x18004fc4b  call    cs:__imp_WindowsDeleteString
0x18004fc51  mov     qword ptr [rbx+28h], 0
0x18004fc59  mov     rcx, [rbx+20h]; string
0x18004fc5d  call    cs:__imp_WindowsDeleteString
0x18004fc63  mov     qword ptr [rbx+20h], 0
0x18004fc6b  mov     rcx, [rbx+18h]; string
0x18004fc6f  call    cs:__imp_WindowsDeleteString
0x18004fc75  mov     qword ptr [rbx+18h], 0
0x18004fc7d  lea     rax, ??_7IRegistryJson@RegValet@@6B@; const RegValet::IRegistryJson::`vftable'
0x18004fc84  mov     [rbx], rax
0x18004fc87  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18004fc8e  add     rsp, 20h
0x18004fc92  pop     rbx
0x18004fc93  retn
```

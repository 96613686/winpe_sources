# CPickerParameters::Clear(void)

- ea: `0x18000fb2c`
- end: `0x18000fc63`
- name: `?Clear@CPickerParameters@@QEAAXXZ`
- size: `311`
- prototype: `void __fastcall(CPickerParameters *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f6d8`
- `0x180021a04`
- `0x18002705c`
- `0x18004be58`

## callees

- `0x18000fb2c`
- `0x18000fc6c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fbaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fbc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fbda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fbf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fc0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fc1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fc34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fc4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fbaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fbc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fbda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fbf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fc0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fc1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fc34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fc4c`

## pseudocode

```c
void __fastcall CPickerParameters::Clear(CPickerParameters *this)
{
  __int64 v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx
  HSTRING v5; // rcx
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx

  SafeRelease<IQueryContinue>((char *)this + 32);
  SafeRelease<IQueryContinue>((char *)this + 40);
  SafeRelease<IQueryContinue>((char *)this + 48);
  SafeRelease<IQueryContinue>((char *)this + 56);
  SafeRelease<IQueryContinue>((char *)this + 64);
  SafeRelease<IQueryContinue>((char *)this + 72);
  SafeRelease<IQueryContinue>((char *)this + 80);
  SafeRelease<IQueryContinue>((char *)this + 88);
  v2 = *((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  SafeRelease<IQueryContinue>((char *)this + 96);
  WindowsDeleteString(*((HSTRING *)this + 18));
  v3 = (HSTRING)*((_QWORD *)this + 19);
  *((_QWORD *)this + 18) = 0;
  WindowsDeleteString(v3);
  v4 = (HSTRING)*((_QWORD *)this + 20);
  *((_QWORD *)this + 19) = 0;
  WindowsDeleteString(v4);
  v5 = (HSTRING)*((_QWORD *)this + 21);
  *((_QWORD *)this + 20) = 0;
  WindowsDeleteString(v5);
  v6 = (HSTRING)*((_QWORD *)this + 22);
  *((_QWORD *)this + 21) = 0;
  WindowsDeleteString(v6);
  v7 = (HSTRING)*((_QWORD *)this + 15);
  *((_QWORD *)this + 22) = 0;
  WindowsDeleteString(v7);
  v8 = (HSTRING)*((_QWORD *)this + 16);
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(v8);
  v9 = (HSTRING)*((_QWORD *)this + 17);
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(v9);
  *((_QWORD *)this + 17) = 0;
}

```

## disassembly

```asm
0x18000fb2c  push    rbx
0x18000fb2e  sub     rsp, 20h
0x18000fb32  mov     rbx, rcx
0x18000fb35  add     rcx, 20h ; ' '
0x18000fb39  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fb3e  lea     rcx, [rbx+28h]
0x18000fb42  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fb47  lea     rcx, [rbx+30h]
0x18000fb4b  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fb50  lea     rcx, [rbx+38h]
0x18000fb54  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fb59  lea     rcx, [rbx+40h]
0x18000fb5d  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fb62  lea     rcx, [rbx+48h]
0x18000fb66  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fb6b  lea     rcx, [rbx+50h]
0x18000fb6f  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fb74  lea     rcx, [rbx+58h]
0x18000fb78  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fb7d  mov     rcx, [rbx+68h]
0x18000fb81  mov     qword ptr [rbx+68h], 0
0x18000fb89  test    rcx, rcx
0x18000fb8c  jz      short loc_18000FB9A
0x18000fb8e  mov     rax, [rcx]
0x18000fb91  mov     rax, [rax+10h]
0x18000fb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb9a  lea     rcx, [rbx+60h]
0x18000fb9e  call    ??$SafeRelease@UIQueryContinue@@@@YAXPEAPEAUIQueryContinue@@@Z; SafeRelease<IQueryContinue>(IQueryContinue * *)
0x18000fba3  mov     rcx, [rbx+90h]; string
0x18000fbaa  call    cs:__imp_WindowsDeleteString
0x18000fbb0  mov     rcx, [rbx+98h]; string
0x18000fbb7  mov     qword ptr [rbx+90h], 0
0x18000fbc2  call    cs:__imp_WindowsDeleteString
0x18000fbc8  mov     rcx, [rbx+0A0h]; string
0x18000fbcf  mov     qword ptr [rbx+98h], 0
0x18000fbda  call    cs:__imp_WindowsDeleteString
0x18000fbe0  mov     rcx, [rbx+0A8h]; string
0x18000fbe7  mov     qword ptr [rbx+0A0h], 0
0x18000fbf2  call    cs:__imp_WindowsDeleteString
0x18000fbf8  mov     rcx, [rbx+0B0h]; string
0x18000fbff  mov     qword ptr [rbx+0A8h], 0
0x18000fc0a  call    cs:__imp_WindowsDeleteString
0x18000fc10  mov     rcx, [rbx+78h]; string
0x18000fc14  mov     qword ptr [rbx+0B0h], 0
0x18000fc1f  call    cs:__imp_WindowsDeleteString
0x18000fc25  mov     rcx, [rbx+80h]; string
0x18000fc2c  mov     qword ptr [rbx+78h], 0
0x18000fc34  call    cs:__imp_WindowsDeleteString
0x18000fc3a  mov     rcx, [rbx+88h]; string
0x18000fc41  mov     qword ptr [rbx+80h], 0
0x18000fc4c  call    cs:__imp_WindowsDeleteString
0x18000fc52  mov     qword ptr [rbx+88h], 0
0x18000fc5d  add     rsp, 20h
0x18000fc61  pop     rbx
0x18000fc62  retn
```

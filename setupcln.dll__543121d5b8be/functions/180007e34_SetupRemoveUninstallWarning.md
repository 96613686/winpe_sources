# SetupRemoveUninstallWarning

- ea: `0x180007e34`
- end: `0x180007ede`
- name: `SetupRemoveUninstallWarning`
- size: `170`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180005c30`

## callees

- `0x180003a40`
- `0x180005a88`
- `0x1800064e8`
- `0x180007e34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e60`
- `USER32!MessageBoxW` at `0x180007ea7`
- `USER32!MessageBoxW` at `0x180007ea7`

## string_xrefs

- `0x180007e59`: `setupcln.dll`

## pseudocode

```c
_BOOL8 SetupRemoveUninstallWarning()
{
  HMODULE ModuleHandleW; // rbx
  LPCWSTR v1; // rbx
  LPCWSTR v2; // rdi
  BOOL v3; // esi
  LPCWSTR lpCaption; // [rsp+30h] [rbp+8h] BYREF
  LPCWSTR lpText; // [rsp+38h] [rbp+10h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpCaption);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpText);
  ModuleHandleW = GetModuleHandleW(L"setupcln.dll");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
    &lpCaption,
    ModuleHandleW,
    1011);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
    &lpText,
    ModuleHandleW,
    1010);
  v1 = lpCaption;
  v2 = lpText;
  v3 = MessageBoxW(0, lpText, lpCaption, 0x134u) == 6;
  ATL::CStringData::Release((ATL::CStringData *)(v2 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v1 - 12));
  return v3;
}

```

## disassembly

```asm
0x180007e34  mov     [rsp+arg_10], rbx
0x180007e39  mov     [rsp+arg_18], rsi
0x180007e3e  push    rdi
0x180007e3f  sub     rsp, 20h
0x180007e43  lea     rcx, [rsp+28h+lpCaption]
0x180007e48  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180007e4d  nop
0x180007e4e  lea     rcx, [rsp+28h+lpText]
0x180007e53  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180007e58  nop
0x180007e59  lea     rcx, ModuleName; "setupcln.dll"
0x180007e60  call    cs:__imp_GetModuleHandleW
0x180007e66  mov     rbx, rax
0x180007e69  mov     r8d, 3F3h
0x180007e6f  mov     rdx, rax
0x180007e72  lea     rcx, [rsp+28h+lpCaption]
0x180007e77  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x180007e7c  mov     r8d, 3F2h
0x180007e82  mov     rdx, rbx
0x180007e85  lea     rcx, [rsp+28h+lpText]
0x180007e8a  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x180007e8f  mov     r9d, 134h; uType
0x180007e95  mov     rbx, [rsp+28h+lpCaption]
0x180007e9a  mov     r8, rbx; lpCaption
0x180007e9d  mov     rdi, [rsp+28h+lpText]
0x180007ea2  mov     rdx, rdi; lpText
0x180007ea5  xor     ecx, ecx; hWnd
0x180007ea7  call    cs:__imp_MessageBoxW
0x180007ead  cmp     eax, 6
0x180007eb0  jnz     short loc_180007EB7
0x180007eb2  lea     esi, [rax-5]
0x180007eb5  jmp     short loc_180007EB9
0x180007eb7  xor     esi, esi
0x180007eb9  lea     rcx, [rdi-18h]; this
0x180007ebd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007ec2  nop
0x180007ec3  lea     rcx, [rbx-18h]; this
0x180007ec7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007ecc  mov     eax, esi
0x180007ece  mov     rbx, [rsp+28h+arg_10]
0x180007ed3  mov     rsi, [rsp+28h+arg_18]
0x180007ed8  add     rsp, 20h
0x180007edc  pop     rdi
0x180007edd  retn
```

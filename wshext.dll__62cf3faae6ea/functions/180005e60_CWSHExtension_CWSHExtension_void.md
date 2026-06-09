# CWSHExtension::~CWSHExtension(void)

- ea: `0x180005e60`
- end: `0x180005ee3`
- name: `??1CWSHExtension@@UEAA@XZ`
- size: `131`
- prototype: `void __fastcall(CWSHExtension *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005f00`

## callees

- `0x180005e60`
- `0x18000e010`

## pseudocode

```c
void __fastcall CWSHExtension::~CWSHExtension(CWSHExtension *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CWSHExtension::`vftable'{for `IWSHExtension'};
  *((_QWORD *)this + 1) = &CWSHExtension::`vftable'{for `IShellExtInit'};
  *((_QWORD *)this + 2) = &CWSHExtension::`vftable'{for `IShellPropSheetExt'};
  *((_QWORD *)this + 3) = &CWSHExtension::`vftable'{for `IDropTarget'};
  *((_QWORD *)this + 4) = &CWSHExtension::`vftable'{for `IPersistFile'};
  *((_QWORD *)this + 5) = &CWSHExtension::`vftable'{for `CUnkObj'};
  _InterlockedCompareExchange((volatile signed __int32 *)&g_cRefPropSheet, 0, 0);
  v2 = *((_QWORD *)this + 10);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 5) = &CUnknown::`vftable';
  _InterlockedDecrement(&Global::g_cObjects);
}

```

## disassembly

```asm
0x180005e60  push    rbx
0x180005e62  sub     rsp, 20h
0x180005e66  lea     rax, ??_7CWSHExtension@@6BIWSHExtension@@@; const CWSHExtension::`vftable'{for `IWSHExtension'}
0x180005e6d  mov     rbx, rcx
0x180005e70  mov     [rcx], rax
0x180005e73  lea     rax, ??_7CWSHExtension@@6BIShellExtInit@@@; const CWSHExtension::`vftable'{for `IShellExtInit'}
0x180005e7a  mov     [rcx+8], rax
0x180005e7e  lea     rax, ??_7CWSHExtension@@6BIShellPropSheetExt@@@; const CWSHExtension::`vftable'{for `IShellPropSheetExt'}
0x180005e85  mov     [rcx+10h], rax
0x180005e89  lea     rax, ??_7CWSHExtension@@6BIDropTarget@@@; const CWSHExtension::`vftable'{for `IDropTarget'}
0x180005e90  mov     [rcx+18h], rax
0x180005e94  lea     rax, ??_7CWSHExtension@@6BIPersistFile@@@; const CWSHExtension::`vftable'{for `IPersistFile'}
0x180005e9b  mov     [rcx+20h], rax
0x180005e9f  lea     rax, ??_7CWSHExtension@@6BCUnkObj@@@; const CWSHExtension::`vftable'{for `CUnkObj'}
0x180005ea6  mov     [rcx+28h], rax
0x180005eaa  xor     ecx, ecx
0x180005eac  xor     eax, eax
0x180005eae  lock cmpxchg cs:?g_cRefPropSheet@@3IA, ecx; uint g_cRefPropSheet
0x180005eb6  mov     rcx, [rbx+50h]
0x180005eba  test    rcx, rcx
0x180005ebd  jz      short loc_180005ECB
0x180005ebf  mov     rax, [rcx]
0x180005ec2  mov     rax, [rax+10h]
0x180005ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ecb  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x180005ed2  mov     [rbx+28h], rax
0x180005ed6  lock dec cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x180005edd  add     rsp, 20h
0x180005ee1  pop     rbx
0x180005ee2  retn
```

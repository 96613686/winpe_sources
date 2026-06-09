# CSecurityExtension::~CSecurityExtension(void)

- ea: `0x180008cd8`
- end: `0x180008d46`
- name: `??1CSecurityExtension@@AEAA@XZ`
- size: `110`
- prototype: `void __fastcall(CSecurityExtension *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009f00`

## callees

- `0x180008cd8`
- `0x1800165e4`
- `0x18001e010`

## pseudocode

```c
void __fastcall CSecurityExtension::~CSecurityExtension(CSecurityExtension *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CSecurityExtension::`vftable'{for `IShellExtInit'};
  *((_QWORD *)this + 1) = &CSecurityExtension::`vftable'{for `IShellPropSheetExt'};
  *((_QWORD *)this + 2) = &CSecurityExtension::`vftable'{for `IElevatedNtfsSecurity'};
  v2 = *((_QWORD *)this + 4);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 4) = 0;
  }
  LocalFreeString((unsigned __int16 **)this + 6);
  LocalFreeString((unsigned __int16 **)this + 7);
  LocalFreeString((unsigned __int16 **)this + 8);
  _InterlockedDecrement(&g_cRefThisDll);
}

```

## disassembly

```asm
0x180008cd8  push    rbx
0x180008cda  sub     rsp, 20h
0x180008cde  lea     rax, ??_7CSecurityExtension@@6BIShellExtInit@@@; const CSecurityExtension::`vftable'{for `IShellExtInit'}
0x180008ce5  mov     rbx, rcx
0x180008ce8  mov     [rcx], rax
0x180008ceb  lea     rax, ??_7CSecurityExtension@@6BIShellPropSheetExt@@@; const CSecurityExtension::`vftable'{for `IShellPropSheetExt'}
0x180008cf2  mov     [rcx+8], rax
0x180008cf6  lea     rax, ??_7CSecurityExtension@@6BIElevatedNtfsSecurity@@@; const CSecurityExtension::`vftable'{for `IElevatedNtfsSecurity'}
0x180008cfd  mov     [rcx+10h], rax
0x180008d01  mov     rcx, [rcx+20h]
0x180008d05  test    rcx, rcx
0x180008d08  jz      short loc_180008D1E
0x180008d0a  mov     rax, [rcx]
0x180008d0d  mov     rax, [rax+10h]
0x180008d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d16  mov     qword ptr [rbx+20h], 0
0x180008d1e  lea     rcx, [rbx+30h]; unsigned __int16 **
0x180008d22  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x180008d27  lea     rcx, [rbx+38h]; unsigned __int16 **
0x180008d2b  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x180008d30  lea     rcx, [rbx+40h]; unsigned __int16 **
0x180008d34  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x180008d39  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180008d40  add     rsp, 20h
0x180008d44  pop     rbx
0x180008d45  retn
```

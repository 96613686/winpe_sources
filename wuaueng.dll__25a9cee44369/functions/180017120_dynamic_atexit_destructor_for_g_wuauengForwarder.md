# _dynamic_atexit_destructor_for__g_wuauengForwarder__

- ea: `0x180017120`
- end: `0x18001716f`
- name: `_dynamic_atexit_destructor_for__g_wuauengForwarder__`
- size: `79`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800159b0`
- `0x180017120`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017130`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017130`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001713d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001713d`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_wuauengForwarder__()
{
  void (__fastcall ***v0)(_QWORD, __int64); // rcx

  if ( hLibModule )
    FreeLibrary(hLibModule);
  DeleteCriticalSection(&CriticalSection);
  v0 = (void (__fastcall ***)(_QWORD, __int64))qword_1800224A0;
  qword_1800224A0 = 0;
  if ( v0 )
    (**v0)(v0, 1);
}

```

## disassembly

```asm
0x180017120  sub     rsp, 28h
0x180017124  mov     rcx, cs:hLibModule; hLibModule
0x18001712b  test    rcx, rcx
0x18001712e  jz      short loc_180017136
0x180017130  call    cs:__imp_FreeLibrary
0x180017136  lea     rcx, CriticalSection; lpCriticalSection
0x18001713d  call    cs:__imp_DeleteCriticalSection
0x180017143  mov     rcx, cs:qword_1800224A0
0x18001714a  mov     cs:qword_1800224A0, 0
0x180017155  test    rcx, rcx
0x180017158  jz      short loc_18001716A
0x18001715a  mov     rax, [rcx]
0x18001715d  mov     edx, 1
0x180017162  mov     rax, [rax]
0x180017165  call    _guard_dispatch_icall
0x18001716a  add     rsp, 28h
0x18001716e  retn
```

# _dynamic_atexit_destructor_for__g_wuapicoreForwarder__

- ea: `0x180017170`
- end: `0x1800171bf`
- name: `_dynamic_atexit_destructor_for__g_wuapicoreForwarder__`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015a00`
- `0x180017170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017180`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017180`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001718d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001718d`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_wuapicoreForwarder__()
{
  void (__fastcall ***v0)(_QWORD, __int64); // rcx

  if ( hLibModule )
    FreeLibrary(hLibModule);
  DeleteCriticalSection(&CriticalSection);
  v0 = (void (__fastcall ***)(_QWORD, __int64))qword_180022480;
  qword_180022480 = 0;
  if ( v0 )
    (**v0)(v0, 1);
}

```

## disassembly

```asm
0x180017170  sub     rsp, 28h
0x180017174  mov     rcx, cs:hLibModule; hLibModule
0x18001717b  test    rcx, rcx
0x18001717e  jz      short loc_180017186
0x180017180  call    cs:__imp_FreeLibrary
0x180017186  lea     rcx, CriticalSection; lpCriticalSection
0x18001718d  call    cs:__imp_DeleteCriticalSection
0x180017193  mov     rcx, cs:qword_180022480
0x18001719a  mov     cs:qword_180022480, 0
0x1800171a5  test    rcx, rcx
0x1800171a8  jz      short loc_1800171BA
0x1800171aa  mov     rax, [rcx]
0x1800171ad  mov     edx, 1
0x1800171b2  mov     rax, [rax]
0x1800171b5  call    _guard_dispatch_icall
0x1800171ba  add     rsp, 28h
0x1800171be  retn
```

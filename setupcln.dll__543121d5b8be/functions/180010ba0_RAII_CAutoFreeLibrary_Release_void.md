# RAII::CAutoFreeLibrary::Release(void)

- ea: `0x180010ba0`
- end: `0x180010bc6`
- name: `?Release@CAutoFreeLibrary@RAII@@UEAAXXZ`
- size: `38`
- prototype: `void __fastcall(RAII::CAutoFreeLibrary *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d9d0`
- `0x18000de00`
- `0x18001200c`
- `0x1800123a0`

## callees

- `0x180010ba0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010bb2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010bb2`

## pseudocode

```c
void __fastcall RAII::CAutoFreeLibrary::Release(RAII::CAutoFreeLibrary *this)
{
  HMODULE v2; // rcx

  v2 = (HMODULE)*((_QWORD *)this + 1);
  if ( v2 )
  {
    FreeLibrary(v2);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180010ba0  push    rbx
0x180010ba2  sub     rsp, 20h
0x180010ba6  mov     rbx, rcx
0x180010ba9  mov     rcx, [rcx+8]; hLibModule
0x180010bad  test    rcx, rcx
0x180010bb0  jz      short loc_180010BC0
0x180010bb2  call    cs:__imp_FreeLibrary
0x180010bb8  mov     qword ptr [rbx+8], 0
0x180010bc0  add     rsp, 20h
0x180010bc4  pop     rbx
0x180010bc5  retn
```

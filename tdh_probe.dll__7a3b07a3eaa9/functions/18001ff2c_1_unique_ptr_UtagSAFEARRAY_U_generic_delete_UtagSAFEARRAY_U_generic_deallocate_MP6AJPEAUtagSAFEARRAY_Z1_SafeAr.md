# ??1?$unique_ptr@UtagSAFEARRAY@@U?$generic_delete@UtagSAFEARRAY@@U?$generic_deallocate@$MP6AJPEAUtagSAFEARRAY@@@Z1?SafeArrayDestroy@@YAJ0@ZPEAU1@@tlx@@@tlx@@@utl@@QEAA@XZ

- ea: `0x18001ff2c`
- end: `0x18001ff43`
- name: `??1?$unique_ptr@UtagSAFEARRAY@@U?$generic_delete@UtagSAFEARRAY@@U?$generic_deallocate@$MP6AJPEAUtagSAFEARRAY@@@Z1?SafeArrayDestroy@@YAJ0@ZPEAU1@@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18001443c`
- `0x18001f990`
- `0x180029f04`
- `0x18002aa4c`
- `0x18002acc0`
- `0x18004a366`
- `0x18004a38a`
- `0x18004a7cb`
- `0x18004a7dd`
- `0x18004a7ef`
- `0x18004ac05`
- `0x18004ac17`
- `0x18004ac29`

## callees

- `0x18001ff2c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001ff38`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001ff38`

## pseudocode

```c
HRESULT __fastcall __1__unique_ptr_UtagSAFEARRAY__U__generic_delete_UtagSAFEARRAY__U__generic_deallocate__MP6AJPEAUtagSAFEARRAY___Z1_SafeArrayDestroy__YAJ0_ZPEAU1__tlx___tlx___utl__QEAA_XZ(
        SAFEARRAY **a1)
{
  SAFEARRAY *v1; // rcx
  HRESULT result; // eax

  v1 = *a1;
  if ( v1 )
    return SafeArrayDestroy(v1);
  return result;
}

```

## disassembly

```asm
0x18001ff2c  sub     rsp, 28h
0x18001ff30  mov     rcx, [rcx]; psa
0x18001ff33  test    rcx, rcx
0x18001ff36  jz      short loc_18001FF3E
0x18001ff38  call    cs:__imp_SafeArrayDestroy
0x18001ff3e  add     rsp, 28h
0x18001ff42  retn
```

# ??1?$unique_ptr@UtagSAFEARRAY@@U?$generic_delete@UtagSAFEARRAY@@U?$generic_deallocate@$MP6AJPEAUtagSAFEARRAY@@@Z1?SafeArrayUnaccessData@@YAJ0@ZPEAU1@@tlx@@@tlx@@@utl@@QEAA@XZ

- ea: `0x18001ff0c`
- end: `0x18001ff23`
- name: `??1?$unique_ptr@UtagSAFEARRAY@@U?$generic_delete@UtagSAFEARRAY@@U?$generic_deallocate@$MP6AJPEAUtagSAFEARRAY@@@Z1?SafeArrayUnaccessData@@YAJ0@ZPEAU1@@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18001443c`
- `0x18001f990`
- `0x18002acc0`
- `0x18004a39c`
- `0x18004a3ae`
- `0x18004a801`
- `0x18004a813`
- `0x18004ac3b`
- `0x18004ac4d`

## callees

- `0x18001ff0c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001ff18`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001ff18`

## pseudocode

```c
HRESULT __fastcall __1__unique_ptr_UtagSAFEARRAY__U__generic_delete_UtagSAFEARRAY__U__generic_deallocate__MP6AJPEAUtagSAFEARRAY___Z1_SafeArrayUnaccessData__YAJ0_ZPEAU1__tlx___tlx___utl__QEAA_XZ(
        SAFEARRAY **a1)
{
  SAFEARRAY *v1; // rcx
  HRESULT result; // eax

  v1 = *a1;
  if ( v1 )
    return SafeArrayUnaccessData(v1);
  return result;
}

```

## disassembly

```asm
0x18001ff0c  sub     rsp, 28h
0x18001ff10  mov     rcx, [rcx]; psa
0x18001ff13  test    rcx, rcx
0x18001ff16  jz      short loc_18001FF1E
0x18001ff18  call    cs:__imp_SafeArrayUnaccessData
0x18001ff1e  add     rsp, 28h
0x18001ff22  retn
```

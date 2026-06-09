# std::filesystem::_Throw_fs_error(char const *,__std_win_error)

- ea: `0x180025f88`
- end: `0x180025fe1`
- name: `?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@@Z`
- size: `89`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b024`
- `0x18000cf18`
- `0x18000ecdc`

## callees

- `0x180025eec`
- `0x180027a18`
- `0x180028338`
- `0x180044848`

## string_xrefs

- `0x180025fa3`: `directory_iterator::operator++`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn std::filesystem::_Throw_fs_error()
{
  __int128 v0; // xmm6
  __int64 v1; // r8
  __int64 v2; // r9
  __int128 v3; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v4[16]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v5[32]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[168]; // [rsp+60h] [rbp-A8h] BYREF

  v0 = *(_OWORD *)std::_Make_ec(v4);
  std::string::string(v5, "directory_iterator::operator++", v1, v2);
  v3 = v0;
  std::filesystem::filesystem_error::filesystem_error(pExceptionObject, v5, &v3);
  throw (std::filesystem::filesystem_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180025f88  mov     rax, rsp
0x180025f8b  sub     rsp, 108h
0x180025f92  movaps  xmmword ptr [rax-18h], xmm6
0x180025f96  lea     rcx, [rsp+108h+var_D8]
0x180025f9b  call    ?_Make_ec@std@@YA?AVerror_code@1@W4__std_win_error@@@Z; std::_Make_ec(__std_win_error)
0x180025fa0  movups  xmm6, xmmword ptr [rax]
0x180025fa3  lea     rdx, aDirectoryItera; "directory_iterator::operator++"
0x180025faa  lea     rcx, [rsp+108h+var_C8]
0x180025faf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180025fb4  nop
0x180025fb5  movdqu  [rsp+108h+var_E8], xmm6
0x180025fbb  lea     r8, [rsp+108h+var_E8]
0x180025fc0  lea     rdx, [rsp+108h+var_C8]
0x180025fc5  lea     rcx, [rsp+108h+pExceptionObject]
0x180025fca  call    ??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@Verror_code@2@@Z; std::filesystem::filesystem_error::filesystem_error(std::string const &,std::error_code)
0x180025fcf  lea     rdx, _TI5?AVfilesystem_error@filesystem@std@@; pThrowInfo
0x180025fd6  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180025fdb  call    _CxxThrowException
```

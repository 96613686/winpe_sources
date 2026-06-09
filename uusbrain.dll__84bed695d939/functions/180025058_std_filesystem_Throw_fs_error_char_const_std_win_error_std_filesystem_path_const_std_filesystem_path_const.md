# std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180025058`
- end: `0x1800250c7`
- name: `?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@2@Z`
- size: `111`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c510`

## callees

- `0x180024fa4`
- `0x180027a18`
- `0x180028338`
- `0x180044848`

## string_xrefs

- `0x18002507e`: `rename`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall __noreturn std::filesystem::_Throw_fs_error(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int128 v6; // xmm6
  __int64 v7; // r8
  __int64 v8; // r9
  __int128 v9; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v10[16]; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v11[32]; // [rsp+50h] [rbp-C8h] BYREF
  _QWORD pExceptionObject[21]; // [rsp+70h] [rbp-A8h] BYREF

  v6 = *(_OWORD *)std::_Make_ec(v10);
  std::string::string(v11, "rename", v7, v8);
  v9 = v6;
  std::filesystem::filesystem_error::filesystem_error(pExceptionObject, (__int64)v11, a3, a4, &v9);
  throw (std::filesystem::filesystem_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180025058  mov     rax, rsp
0x18002505b  mov     [rax+8], rbx
0x18002505f  push    rdi
0x180025060  sub     rsp, 110h
0x180025067  movaps  xmmword ptr [rax-18h], xmm6
0x18002506b  mov     rbx, r9
0x18002506e  mov     rdi, r8
0x180025071  lea     rcx, [rsp+118h+var_D8]
0x180025076  call    ?_Make_ec@std@@YA?AVerror_code@1@W4__std_win_error@@@Z; std::_Make_ec(__std_win_error)
0x18002507b  movups  xmm6, xmmword ptr [rax]
0x18002507e  lea     rdx, aRename; "rename"
0x180025085  lea     rcx, [rsp+118h+var_C8]
0x18002508a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002508f  nop
0x180025090  movdqu  [rsp+118h+var_E8], xmm6
0x180025096  lea     rax, [rsp+118h+var_E8]
0x18002509b  mov     [rsp+118h+var_F8], rax
0x1800250a0  mov     r9, rbx
0x1800250a3  mov     r8, rdi
0x1800250a6  lea     rdx, [rsp+118h+var_C8]
0x1800250ab  lea     rcx, [rsp+118h+pExceptionObject]
0x1800250b0  call    ??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@1Verror_code@2@@Z; std::filesystem::filesystem_error::filesystem_error(std::string const &,std::filesystem::path const &,std::filesystem::path const &,std::error_code)
0x1800250b5  lea     rdx, _TI5?AVfilesystem_error@filesystem@std@@; pThrowInfo
0x1800250bc  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800250c1  call    _CxxThrowException
```

# COSInstaller::DeleteMergedSandboxDir(wchar_t * const)

- ea: `0x18002b4fc`
- end: `0x18002b59f`
- name: `?DeleteMergedSandboxDir@COSInstaller@@AEAAJQEA_W@Z`
- size: `163`
- prototype: `__int64 __fastcall(COSInstaller *this, wchar_t *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18002a83c`
- `0x18002daa8`

## callees

- `0x180003950`
- `0x18000c684`
- `0x18000ca2c`
- `0x18002b4fc`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18002b533`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b533`

## string_xrefs

- `0x18002b51d`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002b565`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COSInstaller::DeleteMergedSandboxDir(COSInstaller *this, wchar_t *const a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  __int64 result; // rax
  int v6; // edx
  int v7; // edi
  int v8; // r8d
  int v9; // r9d
  int v10; // [rsp+20h] [rbp-38h]
  int v11; // [rsp+28h] [rbp-30h]
  unsigned int v12; // [rsp+30h] [rbp-28h]
  void *v13; // [rsp+38h] [rbp-20h]
  int v14; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
  {
    v3 = -2147467261;
    v4 = 1987;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)v3,
      v10);
    return (unsigned int)v3;
  }
  if ( !SysStringLen(a2) )
  {
    v3 = -2147024809;
    v4 = 1988;
    goto LABEL_3;
  }
  v7 = CheckIfDirExists(a2);
  if ( v7 >= 0 )
  {
    v3 = SusDeleteDirectoryW(a2, v6, v8, v9, v10, v11, v12, v13, v14);
    if ( v3 < 0 )
    {
      v4 = 1995;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    result = 2147942402LL;
    if ( v7 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7C5,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)v7,
        v10);
      return (unsigned int)v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b4fc  mov     [rsp+arg_0], rbx
0x18002b501  push    rdi
0x18002b502  sub     rsp, 50h
0x18002b506  mov     rbx, rdx
0x18002b509  test    rdx, rdx
0x18002b50c  jnz     short loc_18002B530
0x18002b50e  mov     ebx, 80004003h
0x18002b513  mov     edx, 7C3h; void *
0x18002b518  mov     rcx, [rsp+58h]; this
0x18002b51d  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002b524  mov     r9d, ebx; char *
0x18002b527  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b52c  mov     eax, ebx
0x18002b52e  jmp     short loc_18002B594
0x18002b530  mov     rcx, rbx; pbstr
0x18002b533  call    cs:__imp_SysStringLen
0x18002b539  test    eax, eax
0x18002b53b  jnz     short loc_18002B549
0x18002b53d  mov     ebx, 80070057h
0x18002b542  mov     edx, 7C4h
0x18002b547  jmp     short loc_18002B518
0x18002b549  mov     rcx, rbx; wchar_t *
0x18002b54c  call    ?CheckIfDirExists@@YAJPEB_W@Z; CheckIfDirExists(wchar_t const *)
0x18002b551  mov     edi, eax
0x18002b553  test    eax, eax
0x18002b555  jns     short loc_18002B57D
0x18002b557  mov     eax, 80070002h
0x18002b55c  cmp     edi, eax
0x18002b55e  jz      short loc_18002B594
0x18002b560  mov     rcx, [rsp+58h]; this
0x18002b565  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002b56c  mov     r9d, edi; char *
0x18002b56f  mov     edx, 7C5h; void *
0x18002b574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b579  mov     eax, edi
0x18002b57b  jmp     short loc_18002B594
0x18002b57d  mov     rcx, rbx; wchar_t *
0x18002b580  call    ?SusDeleteDirectoryW@@YAJPEB_WHHHHHKPEAXH@Z; SusDeleteDirectoryW(wchar_t const *,int,int,int,int,int,ulong,void *,int)
0x18002b585  mov     ebx, eax
0x18002b587  test    eax, eax
0x18002b589  jns     short loc_18002B592
0x18002b58b  mov     edx, 7CBh
0x18002b590  jmp     short loc_18002B518
0x18002b592  xor     eax, eax
0x18002b594  mov     rbx, [rsp+58h+arg_0]
0x18002b599  add     rsp, 50h
0x18002b59d  pop     rdi
0x18002b59e  retn
```

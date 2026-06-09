# UnBCL::Directory::GetWindowsDir(void)

- ea: `0x18002d710`
- end: `0x18002d7bf`
- name: `?GetWindowsDir@Directory@UnBCL@@SAPEAVString@2@XZ`
- size: `175`
- prototype: `struct UnBCL::String *(void)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callees

- `0x1800015ac`
- `0x180008160`
- `0x18002d710`
- `0x1800477d0`
- `0x18005b790`
- `0x180064680`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002d78b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002d78b`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002d728`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002d75c`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002d728`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002d75c`

## string_xrefs

- `0x18002d7a5`: `base\ntsetup\unbcl\src\directory.cpp`
- `0x18002d7ac`: `GetWindowsDirectoryW failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct UnBCL::String *UnBCL::Directory::GetWindowsDir(void)
{
  UINT WindowsDirectoryW; // eax
  UINT v1; // edi
  WCHAR *v2; // rax
  unsigned __int16 *v3; // rbx
  UnBCL::String *v4; // rax
  __int64 v5; // rdi

  WindowsDirectoryW = GetWindowsDirectoryW(0, 0);
  v1 = WindowsDirectoryW;
  if ( !WindowsDirectoryW )
    UnBCL::Win32Exception::ThrowLastError(
      L"GetWindowsDirectoryW failed",
      "base\\ntsetup\\unbcl\\src\\directory.cpp",
      1802);
  v2 = (WCHAR *)operator new[](saturated_mul(WindowsDirectoryW, 2u));
  v3 = v2;
  if ( !v2 )
    UnBCL::Allocator::MemAllocFailed();
  GetWindowsDirectoryW(v2, v1);
  v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  if ( v4 )
    v5 = UnBCL::String::String(v4, v3);
  else
    v5 = 0;
  operator delete[](v3);
  return (struct UnBCL::String *)v5;
}

```

## disassembly

```asm
0x18002d710  push    rdi
0x18002d712  sub     rsp, 30h
0x18002d716  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002d71f  mov     [rsp+38h+arg_8], rbx
0x18002d724  xor     edx, edx; uSize
0x18002d726  xor     ecx, ecx; lpBuffer
0x18002d728  call    cs:__imp_GetWindowsDirectoryW
0x18002d72e  mov     edi, eax
0x18002d730  test    eax, eax
0x18002d732  jz      short loc_18002D79F
0x18002d734  mov     eax, 2
0x18002d739  mul     rdi
0x18002d73c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d743  cmovb   rax, rcx
0x18002d747  mov     rcx, rax; unsigned __int64
0x18002d74a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d74f  mov     rbx, rax
0x18002d752  test    rax, rax
0x18002d755  jz      short loc_18002D7B9
0x18002d757  mov     edx, edi; uSize
0x18002d759  mov     rcx, rax; lpBuffer
0x18002d75c  call    cs:__imp_GetWindowsDirectoryW
0x18002d762  mov     ecx, 18h; unsigned __int64
0x18002d767  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002d76c  mov     [rsp+38h+arg_0], rax
0x18002d771  test    rax, rax
0x18002d774  jz      short loc_18002D786
0x18002d776  mov     rdx, rbx; unsigned __int16 *
0x18002d779  mov     rcx, rax; this
0x18002d77c  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002d781  mov     rdi, rax
0x18002d784  jmp     short loc_18002D788
0x18002d786  xor     edi, edi
0x18002d788  mov     rcx, rbx
0x18002d78b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002d791  mov     rax, rdi
0x18002d794  mov     rbx, [rsp+38h+arg_8]
0x18002d799  add     rsp, 30h
0x18002d79d  pop     rdi
0x18002d79e  retn
0x18002d79f  mov     r8d, 70Ah; int
0x18002d7a5  lea     rdx, aBaseNtsetupUnb_3; "base\\ntsetup\\unbcl\\src\\directory.cp"...
0x18002d7ac  lea     rcx, aGetwindowsdire; "GetWindowsDirectoryW failed"
0x18002d7b3  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBGPEBDH@Z; UnBCL::Win32Exception::ThrowLastError(ushort const *,char const *,int)
0x18002d7b9  call    ?MemAllocFailed@Allocator@UnBCL@@SAHXZ; UnBCL::Allocator::MemAllocFailed(void)
```

# UnBCL::Directory::GetSystemDir(void)

- ea: `0x18002d020`
- end: `0x18002d0cf`
- name: `?GetSystemDir@Directory@UnBCL@@SAPEAVString@2@XZ`
- size: `175`
- prototype: `struct UnBCL::String *(void)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callees

- `0x1800015ac`
- `0x180008160`
- `0x18002d020`
- `0x1800477d0`
- `0x18005b790`
- `0x180064680`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002d09b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002d09b`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d038`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d06c`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d038`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d06c`

## string_xrefs

- `0x18002d0b5`: `base\ntsetup\unbcl\src\directory.cpp`
- `0x18002d0bc`: `GetSystemDirectoryW failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct UnBCL::String *UnBCL::Directory::GetSystemDir(void)
{
  UINT SystemDirectoryW; // eax
  UINT v1; // edi
  WCHAR *v2; // rax
  unsigned __int16 *v3; // rbx
  UnBCL::String *v4; // rax
  __int64 v5; // rdi

  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v1 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    UnBCL::Win32Exception::ThrowLastError(
      L"GetSystemDirectoryW failed",
      "base\\ntsetup\\unbcl\\src\\directory.cpp",
      1825);
  v2 = (WCHAR *)operator new[](saturated_mul(SystemDirectoryW, 2u));
  v3 = v2;
  if ( !v2 )
    UnBCL::Allocator::MemAllocFailed();
  GetSystemDirectoryW(v2, v1);
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
0x18002d020  push    rdi
0x18002d022  sub     rsp, 30h
0x18002d026  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002d02f  mov     [rsp+38h+arg_8], rbx
0x18002d034  xor     edx, edx; uSize
0x18002d036  xor     ecx, ecx; lpBuffer
0x18002d038  call    cs:__imp_GetSystemDirectoryW
0x18002d03e  mov     edi, eax
0x18002d040  test    eax, eax
0x18002d042  jz      short loc_18002D0AF
0x18002d044  mov     eax, 2
0x18002d049  mul     rdi
0x18002d04c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d053  cmovb   rax, rcx
0x18002d057  mov     rcx, rax; unsigned __int64
0x18002d05a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d05f  mov     rbx, rax
0x18002d062  test    rax, rax
0x18002d065  jz      short loc_18002D0C9
0x18002d067  mov     edx, edi; uSize
0x18002d069  mov     rcx, rax; lpBuffer
0x18002d06c  call    cs:__imp_GetSystemDirectoryW
0x18002d072  mov     ecx, 18h; unsigned __int64
0x18002d077  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002d07c  mov     [rsp+38h+arg_0], rax
0x18002d081  test    rax, rax
0x18002d084  jz      short loc_18002D096
0x18002d086  mov     rdx, rbx; unsigned __int16 *
0x18002d089  mov     rcx, rax; this
0x18002d08c  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002d091  mov     rdi, rax
0x18002d094  jmp     short loc_18002D098
0x18002d096  xor     edi, edi
0x18002d098  mov     rcx, rbx
0x18002d09b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002d0a1  mov     rax, rdi
0x18002d0a4  mov     rbx, [rsp+38h+arg_8]
0x18002d0a9  add     rsp, 30h
0x18002d0ad  pop     rdi
0x18002d0ae  retn
0x18002d0af  mov     r8d, 721h; int
0x18002d0b5  lea     rdx, aBaseNtsetupUnb_3; "base\\ntsetup\\unbcl\\src\\directory.cp"...
0x18002d0bc  lea     rcx, aGetsystemdirec; "GetSystemDirectoryW failed"
0x18002d0c3  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBGPEBDH@Z; UnBCL::Win32Exception::ThrowLastError(ushort const *,char const *,int)
0x18002d0c9  call    ?MemAllocFailed@Allocator@UnBCL@@SAHXZ; UnBCL::Allocator::MemAllocFailed(void)
```

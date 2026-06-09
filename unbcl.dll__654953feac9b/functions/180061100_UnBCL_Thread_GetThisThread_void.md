# UnBCL::Thread::GetThisThread(void)

- ea: `0x180061100`
- end: `0x1800611b3`
- name: `?GetThisThread@Thread@UnBCL@@SAPEAV12@XZ`
- size: `179`
- prototype: `struct UnBCL::Thread *(void)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800477d0`
- `0x180060b50`
- `0x180060ce0`
- `0x180061100`
- `0x1800646f0`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x18006115b`
- `KERNEL32!DuplicateHandle` at `0x18006115b`
- `KERNEL32!GetCurrentThread` at `0x180061126`
- `KERNEL32!GetCurrentThread` at `0x180061126`
- `KERNEL32!GetCurrentProcess` at `0x18006111d`
- `KERNEL32!GetCurrentProcess` at `0x18006112f`
- `KERNEL32!GetCurrentProcess` at `0x18006111d`
- `KERNEL32!GetCurrentProcess` at `0x18006112f`

## string_xrefs

- `0x1800611a6`: `base\ntsetup\unbcl\src\thread.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct UnBCL::Thread *UnBCL::Thread::GetThisThread(void)
{
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v2; // rax
  struct UnBCL::Thread *result; // rax
  const struct UnBCL::String *v4; // rax
  HANDLE TargetHandle; // [rsp+60h] [rbp+8h] BYREF
  struct UnBCL::Thread *v6; // [rsp+68h] [rbp+10h]

  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v2 = GetCurrentProcess();
  if ( !DuplicateHandle(v2, CurrentThread, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    v4 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_4__2();
    UnBCL::Win32Exception::ThrowLastError(v4, "base\\ntsetup\\unbcl\\src\\thread.cpp", 118);
  }
  result = (struct UnBCL::Thread *)UnBCL::Object::operator new(0x38u);
  v6 = result;
  if ( result )
    return (struct UnBCL::Thread *)UnBCL::Thread::Thread(result, TargetHandle);
  return result;
}

```

## disassembly

```asm
0x180061100  push    rdi
0x180061102  sub     rsp, 50h
0x180061106  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x18006110f  mov     [rsp+58h+arg_10], rbx
0x180061114  mov     [rsp+58h+TargetHandle], 0
0x18006111d  call    cs:__imp_GetCurrentProcess
0x180061123  mov     rdi, rax
0x180061126  call    cs:__imp_GetCurrentThread
0x18006112c  mov     rbx, rax
0x18006112f  call    cs:__imp_GetCurrentProcess
0x180061135  mov     [rsp+58h+dwOptions], 2; dwOptions
0x18006113d  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x180061145  mov     [rsp+58h+dwDesiredAccess], 0; dwDesiredAccess
0x18006114d  lea     r9, [rsp+58h+TargetHandle]; lpTargetHandle
0x180061152  mov     r8, rdi; hTargetProcessHandle
0x180061155  mov     rdx, rbx; hSourceHandle
0x180061158  mov     rcx, rax; hSourceProcessHandle
0x18006115b  call    cs:__imp_DuplicateHandle
0x180061161  test    eax, eax
0x180061163  jz      short loc_180061198
0x180061165  mov     ecx, 38h ; '8'; unsigned __int64
0x18006116a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18006116f  mov     [rsp+58h+arg_8], rax
0x180061174  test    rax, rax
0x180061177  jz      short loc_18006118D
0x180061179  mov     r8d, 1
0x18006117f  mov     rdx, [rsp+58h+TargetHandle]; void *
0x180061184  mov     rcx, rax; this
0x180061187  call    ??0Thread@UnBCL@@AEAA@PEAX@Z; UnBCL::Thread::Thread(void *)
0x18006118c  nop
0x18006118d  mov     rbx, [rsp+58h+arg_10]
0x180061192  add     rsp, 50h
0x180061196  pop     rdi
0x180061197  retn
0x180061198  call    UnBCL_____StringLiteral_4__2
0x18006119d  mov     rcx, rax; struct UnBCL::String *
0x1800611a0  mov     r8d, 76h ; 'v'; int
0x1800611a6  lea     rdx, aBaseNtsetupUnb; "base\\ntsetup\\unbcl\\src\\thread.cpp"
0x1800611ad  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBVString@2@PEBDH@Z; UnBCL::Win32Exception::ThrowLastError(UnBCL::String const *,char const *,int)
```

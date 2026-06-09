# UnBCL::Monitor::InitTarget(UnBCL::SyncObject *)

- ea: `0x180040dd0`
- end: `0x180040e86`
- name: `?InitTarget@Monitor@UnBCL@@CAKPEAVSyncObject@2@@Z`
- size: `182`
- prototype: `unsigned int __fastcall(struct UnBCL::SyncObject *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180040e90`
- `0x180040fd0`
- `0x180041150`

## callees

- `0x180040dd0`
- `0x180047680`
- `0x1800477d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180040e2b`
- `KERNEL32!CreateEventW` at `0x180040e2b`
- `KERNEL32!CloseHandle` at `0x180040e46`
- `KERNEL32!CloseHandle` at `0x180040e46`
- `KERNEL32!GetLastError` at `0x180040e19`
- `KERNEL32!GetLastError` at `0x180040e3a`
- `KERNEL32!GetLastError` at `0x180040e19`
- `KERNEL32!GetLastError` at `0x180040e3a`
- `KERNEL32!CreateSemaphoreExW` at `0x180040e0a`
- `KERNEL32!CreateSemaphoreExW` at `0x180040e0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall UnBCL::Monitor::InitTarget(struct UnBCL::SyncObject *a1)
{
  HANDLE Semaphore; // rax
  HANDLE EventW; // rax
  DWORD LastError; // ebx
  UnBCL::SyncObject *v6; // rax
  const struct UnBCL::SyncObject *v7; // rdx
  __int64 v8; // rax

  if ( !*((_QWORD *)a1 + 2) )
  {
    Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
    *((_QWORD *)a1 + 2) = Semaphore;
    if ( !Semaphore )
      return GetLastError();
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)a1 + 3) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      CloseHandle(*((HANDLE *)a1 + 2));
      return LastError;
    }
    v6 = (UnBCL::SyncObject *)UnBCL::Object::operator new(0x60u);
    if ( v6 )
      v8 = UnBCL::SyncObject::SyncObject(v6, v7);
    else
      v8 = 0;
    *((_QWORD *)a1 + 4) = v8;
    *((_QWORD *)a1 + 5) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180040dd0  mov     rax, rsp
0x180040dd3  push    rdi
0x180040dd4  sub     rsp, 40h
0x180040dd8  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180040de0  mov     [rax+10h], rbx
0x180040de4  mov     rdi, rcx
0x180040de7  xor     ebx, ebx
0x180040de9  cmp     [rcx+10h], rbx
0x180040ded  jnz     loc_180040E79
0x180040df3  mov     dword ptr [rax-20h], 1F0003h
0x180040dfa  mov     [rax-28h], ebx
0x180040dfd  xor     r9d, r9d; lpName
0x180040e00  xor     edx, edx; lInitialCount
0x180040e02  xor     ecx, ecx; lpSemaphoreAttributes
0x180040e04  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180040e0a  call    cs:__imp_CreateSemaphoreExW
0x180040e10  mov     [rdi+10h], rax
0x180040e14  test    rax, rax
0x180040e17  jnz     short loc_180040E21
0x180040e19  call    cs:__imp_GetLastError
0x180040e1f  jmp     short loc_180040E7B
0x180040e21  xor     r9d, r9d; lpName
0x180040e24  xor     r8d, r8d; bInitialState
0x180040e27  xor     edx, edx; bManualReset
0x180040e29  xor     ecx, ecx; lpEventAttributes
0x180040e2b  call    cs:__imp_CreateEventW
0x180040e31  mov     [rdi+18h], rax
0x180040e35  test    rax, rax
0x180040e38  jnz     short loc_180040E50
0x180040e3a  call    cs:__imp_GetLastError
0x180040e40  mov     ebx, eax
0x180040e42  mov     rcx, [rdi+10h]; hObject
0x180040e46  call    cs:__imp_CloseHandle
0x180040e4c  mov     eax, ebx
0x180040e4e  jmp     short loc_180040E7B
0x180040e50  mov     ecx, 60h ; '`'; unsigned __int64
0x180040e55  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180040e5a  mov     [rsp+48h+arg_0], rax
0x180040e5f  test    rax, rax
0x180040e62  jz      short loc_180040E6E
0x180040e64  mov     rcx, rax; this
0x180040e67  call    ??0SyncObject@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SyncObject::SyncObject(UnBCL::SyncObject const &)
0x180040e6c  jmp     short loc_180040E71
0x180040e6e  mov     rax, rbx
0x180040e71  mov     [rdi+20h], rax
0x180040e75  mov     [rdi+28h], rbx
0x180040e79  xor     eax, eax
0x180040e7b  mov     rbx, [rsp+48h+arg_8]
0x180040e80  add     rsp, 40h
0x180040e84  pop     rdi
0x180040e85  retn
```

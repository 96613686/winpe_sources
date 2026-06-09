# UnBCL::Thread::Thread(UnBCL::ThreadStartDelegate *)

- ea: `0x180060e00`
- end: `0x180060ecf`
- name: `??0Thread@UnBCL@@QEAA@PEAVThreadStartDelegate@1@@Z`
- size: `207`
- prototype: `_QWORD(UnBCL::Thread *__hidden this, struct UnBCL::ThreadStartDelegate *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180060b98`
- `0x180060e00`
- `0x1800646f0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180060e9b`
- `KERNEL32!CreateThread` at `0x180060e9b`

## string_xrefs

- `0x180060ec2`: `base\ntsetup\unbcl\src\thread.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
UnBCL::Thread *__fastcall UnBCL::Thread::Thread(UnBCL::Thread *this, struct UnBCL::ThreadStartDelegate *a2, int a3)
{
  HANDLE Thread; // rax
  const struct UnBCL::String *v6; // rax

  if ( a3 )
  {
    *(_QWORD *)this = &UnBCL::Thread::`vbtable';
    *((_QWORD *)this + 5) = &UnBCL::Object::`vftable';
    *((_DWORD *)this + 12) = 0;
    *((_DWORD *)this + 13) = _InterlockedIncrement(&dword_1800FFC68);
  }
  *(_QWORD *)((char *)this + *(int *)(*(_QWORD *)this + 4LL)) = &UnBCL::Thread::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 3) = 0;
  Thread = CreateThread(0, 0, UnBCL::Thread::StartAddress, a2, 4u, (LPDWORD)this + 8);
  if ( !Thread )
  {
    v6 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_0__5();
    UnBCL::Win32Exception::ThrowLastError(v6, "base\\ntsetup\\unbcl\\src\\thread.cpp", 27);
  }
  *((_QWORD *)this + 3) = Thread;
  return this;
}

```

## disassembly

```asm
0x180060e00  mov     [rsp+arg_0], rcx
0x180060e05  push    rbx
0x180060e06  sub     rsp, 40h
0x180060e0a  mov     [rsp+48h+var_10], 0FFFFFFFFFFFFFFFEh
0x180060e13  mov     rbx, rcx
0x180060e16  mov     [rsp+48h+var_18], 0
0x180060e1e  test    r8d, r8d
0x180060e21  jz      short loc_180060E57
0x180060e23  lea     rax, ??_8Thread@UnBCL@@7B@; const UnBCL::Thread::`vbtable'
0x180060e2a  mov     [rcx], rax
0x180060e2d  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x180060e34  mov     [rcx+28h], rax
0x180060e38  mov     dword ptr [rcx+30h], 0
0x180060e3f  mov     ecx, 1
0x180060e44  mov     eax, ecx
0x180060e46  lock xadd cs:dword_1800FFC68, eax
0x180060e4e  add     eax, ecx
0x180060e50  mov     [rbx+34h], eax
0x180060e53  mov     [rsp+48h+var_18], ecx
0x180060e57  mov     rax, [rbx]
0x180060e5a  movsxd  rcx, dword ptr [rax+4]
0x180060e5e  lea     rax, ??_7Thread@UnBCL@@6B@; const UnBCL::Thread::`vftable'
0x180060e65  mov     [rcx+rbx], rax
0x180060e69  mov     dword ptr [rbx+8], 0
0x180060e70  mov     [rbx+10h], rdx
0x180060e74  mov     qword ptr [rbx+18h], 0
0x180060e7c  lea     rax, [rbx+20h]
0x180060e80  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180060e85  mov     [rsp+48h+dwCreationFlags], 4; dwCreationFlags
0x180060e8d  mov     r9, rdx; lpParameter
0x180060e90  lea     r8, ?StartAddress@Thread@UnBCL@@CAKPEAX@Z; lpStartAddress
0x180060e97  xor     edx, edx; dwStackSize
0x180060e99  xor     ecx, ecx; lpThreadAttributes
0x180060e9b  call    cs:__imp_CreateThread
0x180060ea1  test    rax, rax
0x180060ea4  jz      short loc_180060EB3
0x180060ea6  mov     [rbx+18h], rax
0x180060eaa  mov     rax, rbx
0x180060ead  add     rsp, 40h
0x180060eb1  pop     rbx
0x180060eb2  retn
0x180060eb3  call    UnBCL_____StringLiteral_0__5
0x180060eb8  nop
0x180060eb9  mov     rcx, rax; struct UnBCL::String *
0x180060ebc  mov     r8d, 1Bh; int
0x180060ec2  lea     rdx, aBaseNtsetupUnb; "base\\ntsetup\\unbcl\\src\\thread.cpp"
0x180060ec9  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBVString@2@PEBDH@Z; UnBCL::Win32Exception::ThrowLastError(UnBCL::String const *,char const *,int)
```

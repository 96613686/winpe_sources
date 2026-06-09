# UnBCL::Thread::Start(void)

- ea: `0x180061280`
- end: `0x1800612c7`
- name: `?Start@Thread@UnBCL@@QEAAXXZ`
- size: `71`
- prototype: `void __fastcall(UnBCL::Thread *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180060b08`
- `0x180061280`
- `0x1800646f0`

## import_xrefs

- `KERNEL32!ResumeThread` at `0x180061294`
- `KERNEL32!ResumeThread` at `0x180061294`

## string_xrefs

- `0x1800612b4`: `base\ntsetup\unbcl\src\thread.cpp`

## pseudocode

```c
void __fastcall UnBCL::Thread::Start(UnBCL::Thread *this)
{
  const struct UnBCL::String *v2; // rax

  *((_DWORD *)this + 2) = 1;
  if ( ResumeThread(*((HANDLE *)this + 3)) == -1 )
  {
    *((_DWORD *)this + 2) = 0;
    v2 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_3__3();
    UnBCL::Win32Exception::ThrowLastError(v2, "base\\ntsetup\\unbcl\\src\\thread.cpp", 78);
  }
}

```

## disassembly

```asm
0x180061280  push    rbx
0x180061282  sub     rsp, 20h
0x180061286  mov     rbx, rcx
0x180061289  mov     dword ptr [rcx+8], 1
0x180061290  mov     rcx, [rcx+18h]; hThread
0x180061294  call    cs:__imp_ResumeThread
0x18006129a  cmp     eax, 0FFFFFFFFh
0x18006129d  jz      short loc_1800612A5
0x18006129f  add     rsp, 20h
0x1800612a3  pop     rbx
0x1800612a4  retn
0x1800612a5  mov     dword ptr [rbx+8], 0
0x1800612ac  call    UnBCL_____StringLiteral_3__3
0x1800612b1  mov     rcx, rax; struct UnBCL::String *
0x1800612b4  lea     rdx, aBaseNtsetupUnb; "base\\ntsetup\\unbcl\\src\\thread.cpp"
0x1800612bb  mov     r8d, 4Eh ; 'N'; int
0x1800612c1  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBVString@2@PEBDH@Z; UnBCL::Win32Exception::ThrowLastError(UnBCL::String const *,char const *,int)
```

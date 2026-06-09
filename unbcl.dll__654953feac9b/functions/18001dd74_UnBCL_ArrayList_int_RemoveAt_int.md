# UnBCL::ArrayList<int>::RemoveAt(int)

- ea: `0x18001dd74`
- end: `0x18001deb5`
- name: `?RemoveAt@?$ArrayList@H@UnBCL@@UEAAXH@Z`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001dd60`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x180009b40`
- `0x180009e7c`
- `0x18001dd74`
- `0x1800477d0`
- `0x18006f010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001de14`
- `msvcrt!memmove_s` at `0x18001de14`

## string_xrefs

- `0x18001de69`: `index out of range to ArrayList#RemoveAt`
- `0x18001de79`: `void __cdecl UnBCL::ArrayList<int>::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<int>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rdi
  int (__fastcall ***v4)(_QWORD); // rcx
  __int64 v5; // rax
  __int64 *v6; // rbx
  unsigned __int64 v7; // rcx
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  UnBCL::ArgumentOutOfRangeException *v11; // rax
  __int64 pExceptionObject; // [rsp+50h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v14; // [rsp+58h] [rbp+20h]

  v2 = a2;
  if ( a2 < 0
    || (v4 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 104) + 12LL) - 104LL), a2 >= (**v4)(v4)) )
  {
    v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v14 = v11;
    if ( v11 )
      v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                                                    v11,
                                                    L"index out of range to ArrayList#RemoveAt");
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::ArrayList<int>::RemoveAt(int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  ++*(_DWORD *)(a1 - 88);
  LODWORD(v5) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 - 112) + 32LL))(a1 - 112);
  v6 = (__int64 *)(a1 - 96);
  if ( (_DWORD)v5 )
  {
    v5 = *v6;
    if ( v2 >= *(_QWORD *)(*v6 + 8) )
      goto LABEL_15;
  }
  v7 = v2 + 1;
  if ( v2 + 1 < v2 )
    goto LABEL_15;
  if ( v2 == -1 )
    goto LABEL_15;
  v8 = (_QWORD *)*v6;
  v9 = v8[1];
  if ( v7 > v9 )
    goto LABEL_15;
  v10 = v9 - v7;
  if ( !v10 )
    goto LABEL_14;
  LODWORD(v5) = memmove_s((void *const)(*v8 + 4 * v2), 4 * v10, (const void *const)(*v8 + 4 * v7), 4 * v10);
  switch ( (_DWORD)v5 )
  {
    case 0:
      goto LABEL_14;
    case 0xC:
      ATL::AtlThrowImpl(-2147024882);
    case 0x16:
    case 0x22:
LABEL_15:
      ATL::AtlThrowImpl(-2147024809);
  }
  if ( (_DWORD)v5 != 80 )
    ATL::AtlThrowImpl(-2147467259);
LABEL_14:
  --v8[1];
  return v5;
}

```

## disassembly

```asm
0x18001dd74  push    rdi
0x18001dd76  sub     rsp, 30h
0x18001dd7a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001dd83  mov     [rsp+38h+arg_0], rbx
0x18001dd88  mov     [rsp+38h+arg_8], rsi
0x18001dd8d  movsxd  rdi, edx
0x18001dd90  mov     rbx, rcx
0x18001dd93  test    edx, edx
0x18001dd95  js      loc_18001DE55
0x18001dd9b  mov     rax, [rcx-68h]
0x18001dd9f  movsxd  rcx, dword ptr [rax+0Ch]
0x18001dda3  add     rcx, 0FFFFFFFFFFFFFF98h
0x18001dda7  add     rcx, rbx
0x18001ddaa  mov     rax, [rcx]
0x18001ddad  mov     rax, [rax]
0x18001ddb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddb5  cmp     edi, eax
0x18001ddb7  jge     loc_18001DE55
0x18001ddbd  inc     dword ptr [rbx-58h]
0x18001ddc0  mov     rax, [rbx-70h]
0x18001ddc4  lea     rcx, [rbx-70h]
0x18001ddc8  mov     rax, [rax+20h]
0x18001ddcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddd1  add     rbx, 0FFFFFFFFFFFFFFA0h
0x18001ddd5  test    eax, eax
0x18001ddd7  jz      short loc_18001DDE2
0x18001ddd9  mov     rax, [rbx]
0x18001dddc  cmp     rdi, [rax+8]
0x18001dde0  jnb     short loc_18001DE4A
0x18001dde2  lea     rcx, [rdi+1]
0x18001dde6  cmp     rcx, rdi
0x18001dde9  jb      short loc_18001DE4A
0x18001ddeb  cmp     rcx, 1
0x18001ddef  jb      short loc_18001DE4A
0x18001ddf1  mov     rbx, [rbx]
0x18001ddf4  mov     rdx, [rbx+8]
0x18001ddf8  cmp     rcx, rdx
0x18001ddfb  ja      short loc_18001DE4A
0x18001ddfd  sub     rdx, rcx
0x18001de00  jz      short loc_18001DE36
0x18001de02  mov     rax, [rbx]
0x18001de05  shl     rdx, 2; DestinationSize
0x18001de09  lea     r8, [rax+rcx*4]; Source
0x18001de0d  lea     rcx, [rax+rdi*4]; Destination
0x18001de11  mov     r9, rdx; SourceSize
0x18001de14  call    cs:__imp_memmove_s
0x18001de1a  test    eax, eax
0x18001de1c  jz      short loc_18001DE36
0x18001de1e  cmp     eax, 0Ch
0x18001de21  jz      loc_18001DEAA
0x18001de27  cmp     eax, 16h
0x18001de2a  jz      short loc_18001DE4A
0x18001de2c  cmp     eax, 22h ; '"'
0x18001de2f  jz      short loc_18001DE4A
0x18001de31  cmp     eax, 50h ; 'P'
0x18001de34  jnz     short loc_18001DE9F
0x18001de36  dec     qword ptr [rbx+8]
0x18001de3a  mov     rbx, [rsp+38h+arg_0]
0x18001de3f  mov     rsi, [rsp+38h+arg_8]
0x18001de44  add     rsp, 30h
0x18001de48  pop     rdi
0x18001de49  retn
0x18001de4a  mov     ecx, 80070057h; int
0x18001de4f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001de55  mov     ecx, 38h ; '8'; unsigned __int64
0x18001de5a  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001de5f  mov     [rsp+38h+arg_18], rax
0x18001de64  test    rax, rax
0x18001de67  jz      short loc_18001DE79
0x18001de69  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18001de70  mov     rcx, rax; this
0x18001de73  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18001de78  nop
0x18001de79  lea     rdx, aVoidCdeclUnbcl_71; "void __cdecl UnBCL::ArrayList<int>::Rem"...
0x18001de80  mov     rcx, rax
0x18001de83  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001de88  mov     [rsp+38h+pExceptionObject], rax
0x18001de8d  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18001de94  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18001de99  call    _CxxThrowException_0
0x18001de9f  mov     ecx, 80004005h; int
0x18001dea4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001deaa  mov     ecx, 8007000Eh; int
0x18001deaf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

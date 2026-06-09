# UnBCL::ArrayList<ushort>::RemoveAt(int)

- ea: `0x18001dc10`
- end: `0x18001dd50`
- name: `?RemoveAt@?$ArrayList@G@UnBCL@@UEAAXH@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001dbf0`

## callees

- `0x18000225c`
- `0x1800066cc`
- `0x180009b40`
- `0x180009e7c`
- `0x18001dc10`
- `0x1800477d0`
- `0x18006f010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001dcaf`
- `msvcrt!memmove_s` at `0x18001dcaf`

## string_xrefs

- `0x18001dd04`: `index out of range to ArrayList#RemoveAt`
- `0x18001dd14`: `void __cdecl UnBCL::ArrayList<unsigned short>::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<unsigned short>::RemoveAt(__int64 a1, int a2)
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
                         "void __cdecl UnBCL::ArrayList<unsigned short>::RemoveAt(int)");
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
  LODWORD(v5) = memmove_s((void *const)(*v8 + 2 * v2), 2 * v10, (const void *const)(*v8 + 2 * v7), 2 * v10);
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
0x18001dc10  push    rdi
0x18001dc12  sub     rsp, 30h
0x18001dc16  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001dc1f  mov     [rsp+38h+arg_0], rbx
0x18001dc24  mov     [rsp+38h+arg_8], rsi
0x18001dc29  movsxd  rdi, edx
0x18001dc2c  mov     rbx, rcx
0x18001dc2f  test    edx, edx
0x18001dc31  js      loc_18001DCF0
0x18001dc37  mov     rax, [rcx-68h]
0x18001dc3b  movsxd  rcx, dword ptr [rax+0Ch]
0x18001dc3f  add     rcx, 0FFFFFFFFFFFFFF98h
0x18001dc43  add     rcx, rbx
0x18001dc46  mov     rax, [rcx]
0x18001dc49  mov     rax, [rax]
0x18001dc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc51  cmp     edi, eax
0x18001dc53  jge     loc_18001DCF0
0x18001dc59  inc     dword ptr [rbx-58h]
0x18001dc5c  mov     rax, [rbx-70h]
0x18001dc60  lea     rcx, [rbx-70h]
0x18001dc64  mov     rax, [rax+20h]
0x18001dc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc6d  add     rbx, 0FFFFFFFFFFFFFFA0h
0x18001dc71  test    eax, eax
0x18001dc73  jz      short loc_18001DC7E
0x18001dc75  mov     rax, [rbx]
0x18001dc78  cmp     rdi, [rax+8]
0x18001dc7c  jnb     short loc_18001DCE5
0x18001dc7e  lea     rcx, [rdi+1]
0x18001dc82  cmp     rcx, rdi
0x18001dc85  jb      short loc_18001DCE5
0x18001dc87  cmp     rcx, 1
0x18001dc8b  jb      short loc_18001DCE5
0x18001dc8d  mov     rbx, [rbx]
0x18001dc90  mov     rdx, [rbx+8]
0x18001dc94  cmp     rcx, rdx
0x18001dc97  ja      short loc_18001DCE5
0x18001dc99  sub     rdx, rcx
0x18001dc9c  jz      short loc_18001DCD1
0x18001dc9e  mov     rax, [rbx]
0x18001dca1  add     rdx, rdx; DestinationSize
0x18001dca4  lea     r8, [rax+rcx*2]; Source
0x18001dca8  lea     rcx, [rax+rdi*2]; Destination
0x18001dcac  mov     r9, rdx; SourceSize
0x18001dcaf  call    cs:__imp_memmove_s
0x18001dcb5  test    eax, eax
0x18001dcb7  jz      short loc_18001DCD1
0x18001dcb9  cmp     eax, 0Ch
0x18001dcbc  jz      loc_18001DD45
0x18001dcc2  cmp     eax, 16h
0x18001dcc5  jz      short loc_18001DCE5
0x18001dcc7  cmp     eax, 22h ; '"'
0x18001dcca  jz      short loc_18001DCE5
0x18001dccc  cmp     eax, 50h ; 'P'
0x18001dccf  jnz     short loc_18001DD3A
0x18001dcd1  dec     qword ptr [rbx+8]
0x18001dcd5  mov     rbx, [rsp+38h+arg_0]
0x18001dcda  mov     rsi, [rsp+38h+arg_8]
0x18001dcdf  add     rsp, 30h
0x18001dce3  pop     rdi
0x18001dce4  retn
0x18001dce5  mov     ecx, 80070057h; int
0x18001dcea  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001dcf0  mov     ecx, 38h ; '8'; unsigned __int64
0x18001dcf5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18001dcfa  mov     [rsp+38h+arg_18], rax
0x18001dcff  test    rax, rax
0x18001dd02  jz      short loc_18001DD14
0x18001dd04  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18001dd0b  mov     rcx, rax; this
0x18001dd0e  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18001dd13  nop
0x18001dd14  lea     rdx, aVoidCdeclUnbcl_122; "void __cdecl UnBCL::ArrayList<unsigned "...
0x18001dd1b  mov     rcx, rax
0x18001dd1e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001dd23  mov     [rsp+38h+pExceptionObject], rax
0x18001dd28  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18001dd2f  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18001dd34  call    _CxxThrowException_0
0x18001dd3a  mov     ecx, 80004005h; int
0x18001dd3f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001dd45  mov     ecx, 8007000Eh; int
0x18001dd4a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

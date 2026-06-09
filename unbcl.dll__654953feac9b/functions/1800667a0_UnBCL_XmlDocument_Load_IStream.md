# UnBCL::XmlDocument::Load(IStream *)

- ea: `0x1800667a0`
- end: `0x18006691f`
- name: `?Load@XmlDocument@UnBCL@@QEAAXPEAUIStream@@@Z`
- size: `383`
- prototype: `void __fastcall(UnBCL::XmlDocument *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x18005b790`
- `0x1800667a0`
- `0x180068410`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800668f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800668f1`

## string_xrefs

- `0x1800668fb`: `void __cdecl UnBCL::XmlDocument::Load(struct IStream *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UnBCL::XmlDocument::Load(UnBCL::XmlDocument *this, struct IStream *a2)
{
  __int64 v3; // rcx
  UnBCL::String *v4; // rax
  struct UnBCL::String *v5; // rbx
  UnBCL::XmlException *v6; // rax
  __int64 v7; // rdi
  BSTR bstrString; // [rsp+30h] [rbp-48h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v10[5]; // [rsp+50h] [rbp-28h] BYREF
  __int16 v11; // [rsp+A0h] [rbp+28h] BYREF
  int v12; // [rsp+A8h] [rbp+30h] BYREF
  int v13; // [rsp+B0h] [rbp+38h] BYREF
  __int64 v14; // [rsp+B8h] [rbp+40h] BYREF

  pExceptionObject[1] = -2;
  v10[0] = 13;
  v11 = 0;
  v10[1] = a2;
  v3 = *((_QWORD *)this + 3);
  v10[2] = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD *, __int16 *))(*(_QWORD *)v3 + 464LL))(v3, v10, &v11) || !v11 )
  {
    v14 = 0;
    bstrString = 0;
    v13 = 0;
    v12 = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 480LL))(*((_QWORD *)this + 3), &v14) >= 0 )
    {
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 72LL))(v14, &bstrString);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 88LL))(v14, &v13);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 96LL))(v14, &v12);
    }
    v4 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    pExceptionObject[0] = v4;
    if ( v4 )
      v5 = (struct UnBCL::String *)UnBCL::String::String(v4, bstrString);
    else
      v5 = 0;
    v6 = (UnBCL::XmlException *)UnBCL::Object::operator new(0x40u);
    pExceptionObject[0] = v6;
    if ( v6 )
      v7 = UnBCL::XmlException::XmlException(v6, v5, 0, v13, v12, 0);
    else
      v7 = 0;
    if ( v5 )
      (**(void (__fastcall ***)(struct UnBCL::String *, __int64))v5)(v5, 1);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    pExceptionObject[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                            v7,
                            "void __cdecl UnBCL::XmlDocument::Load(struct IStream *)");
    throw (UnBCL::XmlException **)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800667a0  push    rbp
0x1800667a2  push    rbx
0x1800667a3  push    rsi
0x1800667a4  push    rdi
0x1800667a5  mov     rbp, rsp
0x1800667a8  sub     rsp, 78h
0x1800667ac  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x1800667b4  mov     rbx, rcx
0x1800667b7  xorps   xmm0, xmm0
0x1800667ba  xor     r8d, r8d
0x1800667bd  movups  [rbp+var_28], xmm0
0x1800667c1  xor     esi, esi
0x1800667c3  mov     [rbp+arg_0], si
0x1800667c7  lea     eax, [rsi+0Dh]
0x1800667ca  mov     word ptr [rbp+var_28], ax
0x1800667ce  mov     qword ptr [rbp+var_28+8], rdx
0x1800667d2  mov     rcx, [rcx+18h]
0x1800667d6  movups  xmm0, [rbp+var_28]
0x1800667da  movaps  [rbp+var_28], xmm0
0x1800667de  mov     [rbp+var_18], r8
0x1800667e2  mov     rax, [rcx]
0x1800667e5  lea     r8, [rbp+arg_0]
0x1800667e9  lea     rdx, [rbp+var_28]
0x1800667ed  mov     rax, [rax+1D0h]
0x1800667f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667f9  test    eax, eax
0x1800667fb  jnz     short loc_18006680C
0x1800667fd  cmp     [rbp+arg_0], si
0x180066801  jz      short loc_18006680C
0x180066803  add     rsp, 78h
0x180066807  pop     rdi
0x180066808  pop     rsi
0x180066809  pop     rbx
0x18006680a  pop     rbp
0x18006680b  retn
0x18006680c  mov     [rbp+arg_18], rsi
0x180066810  mov     [rbp+bstrString], rsi
0x180066814  mov     [rbp+arg_10], esi
0x180066817  mov     [rbp+arg_8], esi
0x18006681a  mov     rcx, [rbx+18h]
0x18006681e  mov     rax, [rcx]
0x180066821  lea     rdx, [rbp+arg_18]
0x180066825  mov     rax, [rax+1E0h]
0x18006682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066831  test    eax, eax
0x180066833  js      short loc_180066871
0x180066835  mov     rcx, [rbp+arg_18]
0x180066839  mov     rax, [rcx]
0x18006683c  lea     rdx, [rbp+bstrString]
0x180066840  mov     rax, [rax+48h]
0x180066844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066849  mov     rcx, [rbp+arg_18]
0x18006684d  mov     rax, [rcx]
0x180066850  lea     rdx, [rbp+arg_10]
0x180066854  mov     rax, [rax+58h]
0x180066858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006685d  mov     rcx, [rbp+arg_18]
0x180066861  mov     rax, [rcx]
0x180066864  lea     rdx, [rbp+arg_8]
0x180066868  mov     rax, [rax+60h]
0x18006686c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066871  mov     ecx, 18h; unsigned __int64
0x180066876  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18006687b  mov     [rbp+pExceptionObject], rax
0x18006687f  test    rax, rax
0x180066882  jz      short loc_180066895
0x180066884  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180066888  mov     rcx, rax; this
0x18006688b  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180066890  mov     rbx, rax
0x180066893  jmp     short loc_180066898
0x180066895  mov     rbx, rsi
0x180066898  mov     ecx, 40h ; '@'; unsigned __int64
0x18006689d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800668a2  mov     [rbp+pExceptionObject], rax
0x1800668a6  test    rax, rax
0x1800668a9  jz      short loc_1800668CD
0x1800668ab  mov     [rsp+78h+var_50], esi; int
0x1800668af  mov     ecx, [rbp+arg_8]
0x1800668b2  mov     [rsp+78h+var_58], ecx; int
0x1800668b6  mov     r9d, [rbp+arg_10]; int
0x1800668ba  xor     r8d, r8d; struct UnBCL::Exception *
0x1800668bd  mov     rdx, rbx; struct UnBCL::String *
0x1800668c0  mov     rcx, rax; this
0x1800668c3  call    ??0XmlException@UnBCL@@QEAA@PEAVString@1@PEAVException@1@HHJ@Z; UnBCL::XmlException::XmlException(UnBCL::String *,UnBCL::Exception *,int,int,long)
0x1800668c8  mov     rdi, rax
0x1800668cb  jmp     short loc_1800668D0
0x1800668cd  mov     rdi, rsi
0x1800668d0  test    rbx, rbx
0x1800668d3  jz      short loc_1800668E8
0x1800668d5  mov     rax, [rbx]
0x1800668d8  mov     edx, 1
0x1800668dd  mov     rcx, rbx
0x1800668e0  mov     rax, [rax]
0x1800668e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668e8  mov     rcx, [rbp+bstrString]; bstrString
0x1800668ec  test    rcx, rcx
0x1800668ef  jz      short loc_1800668FB
0x1800668f1  call    cs:__imp_SysFreeString
0x1800668f7  mov     [rbp+bstrString], rsi
0x1800668fb  lea     rdx, aVoidCdeclUnbcl_5; "void __cdecl UnBCL::XmlDocument::Load(s"...
0x180066902  mov     rcx, rdi
0x180066905  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18006690a  mov     [rbp+pExceptionObject], rax
0x18006690e  lea     rdx, _TI5PEAVXmlException@UnBCL@@; pThrowInfo
0x180066915  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180066919  call    _CxxThrowException_0
```

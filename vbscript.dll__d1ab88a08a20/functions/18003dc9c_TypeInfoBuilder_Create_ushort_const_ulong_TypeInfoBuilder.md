# TypeInfoBuilder::Create(ushort const *,ulong,TypeInfoBuilder * *)

- ea: `0x18003dc9c`
- end: `0x18003dedd`
- name: `?Create@TypeInfoBuilder@@SAJPEBGKPEAPEAV1@@Z`
- size: `577`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct TypeInfoBuilder **)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18004d0a0`
- `0x18005df20`

## callees

- `0x18003dc9c`
- `0x180043230`
- `0x180046884`
- `0x180066b3c`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x18003dd16`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x18003dd16`

## pseudocode

```c
__int64 __fastcall TypeInfoBuilder::Create(const unsigned __int16 *a1, unsigned int a2, ICreateTypeLib2 ***a3)
{
  ICreateTypeLib2 **v6; // rax
  ICreateTypeLib2 **v7; // rbx
  HRESULT DispatchTypeInfo; // edi
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  struct ITypeInfo *v13; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+20h] BYREF

  v14 = 0;
  v13 = 0;
  v6 = (ICreateTypeLib2 **)operator new(0x18u);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 0;
    v6[1] = 0;
    v6[2] = 0;
    DispatchTypeInfo = GetDispatchTypeInfo(&v13);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    v9 = v7 + 2;
    DispatchTypeInfo = CreateTypeLib2(SYS_WIN32, L"VBSDeb.tlb", v7 + 2);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 80LL))(*v9, a2);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v9 + 32LL))(
                         *v9,
                         L"VBScriptTypeLib");
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v9 + 56LL))(
                         *v9,
                         L"Visual Basic Scripting Type Library");
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v9 + 40LL))(*v9, 10, 8);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v9 + 48LL))(*v9, &IID_IScriptTypeLib);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 88LL))(*v9, 0);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    v10 = *v9;
    v11 = v7 + 1;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, ICreateTypeLib2 **))(*(_QWORD *)v10 + 24LL))(
                         v10,
                         a1,
                         4,
                         v7 + 1);
    if ( DispatchTypeInfo < 0
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v11 + 40LL))(
                               *v11,
                               L"Visual Basic Scripting Type Info"),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v11 + 24LL))(
                               *v11,
                               &IID_IScriptTypeInfo),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v11 + 56LL))(*v11, 10, 8),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, struct ITypeInfo *, unsigned int *))(*(_QWORD *)*v11 + 64LL))(
                               *v11,
                               v13,
                               &v14),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v11 + 80LL))(*v11, 0, v14),
          DispatchTypeInfo < 0) )
    {
LABEL_17:
      TypeInfoBuilder::Release((TypeInfoBuilder *)v7);
    }
    else
    {
      DispatchTypeInfo = 0;
      *a3 = v7;
    }
  }
  else
  {
    DispatchTypeInfo = -2147024882;
  }
  if ( v13 )
    ((void (__fastcall *)(struct ITypeInfo *))v13->lpVtbl->Release)(v13);
  return (unsigned int)DispatchTypeInfo;
}

```

## disassembly

```asm
0x18003dc9c  mov     rax, rsp
0x18003dc9f  push    rbx
0x18003dca0  push    rbp
0x18003dca1  push    rsi
0x18003dca2  push    rdi
0x18003dca3  push    r14
0x18003dca5  push    r15
0x18003dca7  sub     rsp, 48h
0x18003dcab  mov     r15, rcx
0x18003dcae  mov     dword ptr [rax+20h], 0
0x18003dcb5  mov     ecx, 18h; Size
0x18003dcba  mov     qword ptr [rax-48h], 0
0x18003dcc2  mov     r14, r8
0x18003dcc5  mov     ebp, edx
0x18003dcc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dccc  mov     rbx, rax
0x18003dccf  test    rax, rax
0x18003dcd2  jz      loc_18003DEB2
0x18003dcd8  lea     rcx, [rsp+78h+var_48]; struct ITypeInfo **
0x18003dcdd  mov     qword ptr [rax], 0
0x18003dce4  mov     qword ptr [rax+8], 0
0x18003dcec  mov     qword ptr [rax+10h], 0
0x18003dcf4  call    ?GetDispatchTypeInfo@@YAJPEAPEAUITypeInfo@@@Z; GetDispatchTypeInfo(ITypeInfo * *)
0x18003dcf9  mov     edi, eax
0x18003dcfb  test    eax, eax
0x18003dcfd  js      loc_18003DEA8
0x18003dd03  lea     rsi, [rbx+10h]
0x18003dd07  mov     ecx, 1; syskind
0x18003dd0c  mov     r8, rsi; ppctlib
0x18003dd0f  lea     rdx, szFile; "VBSDeb.tlb"
0x18003dd16  call    cs:__imp_CreateTypeLib2
0x18003dd1d  nop     dword ptr [rax+rax+00h]
0x18003dd22  mov     edi, eax
0x18003dd24  test    eax, eax
0x18003dd26  js      loc_18003DEA8
0x18003dd2c  mov     rcx, [rsi]
0x18003dd2f  mov     edx, ebp
0x18003dd31  mov     rax, [rcx]
0x18003dd34  mov     rax, [rax+50h]
0x18003dd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd3d  mov     edi, eax
0x18003dd3f  test    eax, eax
0x18003dd41  js      loc_18003DEA8
0x18003dd47  mov     rcx, [rsi]
0x18003dd4a  lea     rdx, aVbscripttypeli; "VBScriptTypeLib"
0x18003dd51  mov     rax, [rcx]
0x18003dd54  mov     rax, [rax+20h]
0x18003dd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd5d  mov     edi, eax
0x18003dd5f  test    eax, eax
0x18003dd61  js      loc_18003DEA8
0x18003dd67  mov     rcx, [rsi]
0x18003dd6a  lea     rdx, aVisualBasicScr; "Visual Basic Scripting Type Library"
0x18003dd71  mov     rax, [rcx]
0x18003dd74  mov     rax, [rax+38h]
0x18003dd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd7d  mov     edi, eax
0x18003dd7f  test    eax, eax
0x18003dd81  js      loc_18003DEA8
0x18003dd87  mov     rcx, [rsi]
0x18003dd8a  mov     ebp, 8
0x18003dd8f  mov     r8d, ebp
0x18003dd92  mov     rax, [rcx]
0x18003dd95  lea     edx, [rbp+2]
0x18003dd98  mov     rax, [rax+28h]
0x18003dd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dda1  mov     edi, eax
0x18003dda3  test    eax, eax
0x18003dda5  js      loc_18003DEA8
0x18003ddab  mov     rcx, [rsi]
0x18003ddae  lea     rdx, IID_IScriptTypeLib
0x18003ddb5  mov     rax, [rcx]
0x18003ddb8  mov     rax, [rax+30h]
0x18003ddbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddc1  mov     edi, eax
0x18003ddc3  test    eax, eax
0x18003ddc5  js      loc_18003DEA8
0x18003ddcb  mov     rcx, [rsi]
0x18003ddce  xor     edx, edx
0x18003ddd0  mov     rax, [rcx]
0x18003ddd3  mov     rax, [rax+58h]
0x18003ddd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dddc  mov     edi, eax
0x18003ddde  test    eax, eax
0x18003dde0  js      loc_18003DEA8
0x18003dde6  mov     rcx, [rsi]
0x18003dde9  lea     r8d, [rbp-4]
0x18003dded  lea     rsi, [rbx+8]
0x18003ddf1  mov     rdx, r15
0x18003ddf4  mov     r9, rsi
0x18003ddf7  mov     rax, [rcx]
0x18003ddfa  mov     rax, [rax+18h]
0x18003ddfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de03  mov     edi, eax
0x18003de05  test    eax, eax
0x18003de07  js      loc_18003DEA8
0x18003de0d  mov     rcx, [rsi]
0x18003de10  lea     rdx, aVisualBasicScr_0; "Visual Basic Scripting Type Info"
0x18003de17  mov     rax, [rcx]
0x18003de1a  mov     rax, [rax+28h]
0x18003de1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de23  mov     edi, eax
0x18003de25  test    eax, eax
0x18003de27  js      short loc_18003DEA8
0x18003de29  mov     rcx, [rsi]
0x18003de2c  lea     rdx, IID_IScriptTypeInfo
0x18003de33  mov     rax, [rcx]
0x18003de36  mov     rax, [rax+18h]
0x18003de3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de3f  mov     edi, eax
0x18003de41  test    eax, eax
0x18003de43  js      short loc_18003DEA8
0x18003de45  mov     rcx, [rsi]
0x18003de48  lea     edx, [rbp+2]
0x18003de4b  mov     r8d, ebp
0x18003de4e  mov     rax, [rcx]
0x18003de51  mov     rax, [rax+38h]
0x18003de55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de5a  mov     edi, eax
0x18003de5c  test    eax, eax
0x18003de5e  js      short loc_18003DEA8
0x18003de60  mov     rcx, [rsi]
0x18003de63  lea     r8, [rsp+78h+arg_18]
0x18003de6b  mov     rdx, [rsp+78h+var_48]
0x18003de70  mov     rax, [rcx]
0x18003de73  mov     rax, [rax+40h]
0x18003de77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de7c  mov     edi, eax
0x18003de7e  test    eax, eax
0x18003de80  js      short loc_18003DEA8
0x18003de82  mov     rcx, [rsi]
0x18003de85  xor     edx, edx
0x18003de87  mov     r8d, [rsp+78h+arg_18]
0x18003de8f  mov     rax, [rcx]
0x18003de92  mov     rax, [rax+50h]
0x18003de96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de9b  mov     edi, eax
0x18003de9d  test    eax, eax
0x18003de9f  js      short loc_18003DEA8
0x18003dea1  xor     edi, edi
0x18003dea3  mov     [r14], rbx
0x18003dea6  jmp     short loc_18003DEB7
0x18003dea8  mov     rcx, rbx; this
0x18003deab  call    ?Release@TypeInfoBuilder@@QEAAXXZ; TypeInfoBuilder::Release(void)
0x18003deb0  jmp     short loc_18003DEB7
0x18003deb2  mov     edi, 8007000Eh
0x18003deb7  mov     rcx, [rsp+78h+var_48]
0x18003debc  test    rcx, rcx
0x18003debf  jz      short loc_18003DECD
0x18003dec1  mov     rax, [rcx]
0x18003dec4  mov     rax, [rax+10h]
0x18003dec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003decd  mov     eax, edi
0x18003decf  add     rsp, 48h
0x18003ded3  pop     r15
0x18003ded5  pop     r14
0x18003ded7  pop     rdi
0x18003ded8  pop     rsi
0x18003ded9  pop     rbp
0x18003deda  pop     rbx
0x18003dedb  retn
```

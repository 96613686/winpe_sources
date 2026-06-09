# SavedStateRepository::GetNode(ushort const *,tagVARIANT &)

- ea: `0x140266d90`
- end: `0x14026702e`
- name: `?GetNode@SavedStateRepository@@UEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `670`
- prototype: `__int64 __fastcall(SavedStateRepository *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140267034`

## callees

- `0x140017040`
- `0x1400421f0`
- `0x1401332f0`
- `0x140266d90`
- `0x140267320`
- `0x1402c4010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140266f9d`
- `OLEAUT32!__imp_SysAllocString` at `0x140266f9d`
- `OLEAUT32!__imp_SysStringLen` at `0x140266fb0`
- `OLEAUT32!__imp_SysStringLen` at `0x140266fb0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140266e79`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140266e79`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140266ee0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140266ee0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140266ea0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140266ea0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140266ec4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140266ec4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SavedStateRepository::GetNode(
        SavedStateRepository *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  int v6; // eax
  int Array; // ebx
  SAFEARRAY *v8; // rax
  SAFEARRAY *v9; // rsi
  SHORT v10; // ax
  const OLECHAR *v11; // rcx
  OLECHAR *v12; // rax
  VARTYPE v14[2]; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v15; // [rsp+24h] [rbp-3Ch] BYREF
  void *ppvData; // [rsp+28h] [rbp-38h] BYREF
  OLECHAR *psz[4]; // [rsp+30h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-10h] BYREF

  v6 = *((_DWORD *)this + 32);
  if ( (v6 & 1) == 0 && (v6 & 0xFFFFFFFC) == 0 )
    return (unsigned int)-2147418113;
  v14[0] = 0;
  Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, VARTYPE *))(**((_QWORD **)this + 13) + 176LL))(
            *((_QWORD *)this + 13),
            a2,
            v14);
  if ( Array < 0 )
    return (unsigned int)Array;
  if ( v14[0] == 5 )
  {
    ppvData = 0;
    Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void **))(**((_QWORD **)this + 13) + 120LL))(
              *((_QWORD *)this + 13),
              a2,
              &ppvData);
    if ( Array < 0 )
      return (unsigned int)Array;
    a3->llVal = (LONGLONG)ppvData;
    goto LABEL_32;
  }
  if ( v14[0] != 8 )
  {
    switch ( v14[0] )
    {
      case 0xBu:
        v15 = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 13)
                                                                                            + 104LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &v15);
        if ( Array < 0 )
          return (unsigned int)Array;
        if ( v15 )
          v10 = -1;
        else
          v10 = 0;
        a3->iVal = v10;
        break;
      case 0x14u:
        ppvData = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void **))(**((_QWORD **)this + 13) + 80LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &ppvData);
        if ( Array < 0 )
          return (unsigned int)Array;
        a3->llVal = (LONGLONG)ppvData;
        break;
      case 0x2011u:
        v15 = 0;
        Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 13)
                                                                                            + 160LL))(
                  *((_QWORD *)this + 13),
                  a2,
                  &v15);
        if ( Array < 0 )
          return (unsigned int)Array;
        rgsabound.cElements = v15;
        rgsabound.lLbound = 0;
        v8 = SafeArrayCreate(0x11u, 1u, &rgsabound);
        v9 = v8;
        if ( v8 )
        {
          ppvData = 0;
          SafeArrayAccessData(v8, &ppvData);
          Array = SavedStateRepository::ReadArray(this, a2, ppvData, v15);
          SafeArrayUnaccessData(v9);
          if ( Array < 0 )
          {
            SafeArrayDestroy(v9);
            return (unsigned int)Array;
          }
          a3->llVal = (LONGLONG)v9;
        }
        break;
      default:
        return (unsigned int)-2147024809;
    }
LABEL_32:
    a3->vt = v14[0];
    return (unsigned int)Array;
  }
  std::wstring::wstring(psz);
  Array = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, OLECHAR **))(**((_QWORD **)this + 13) + 136LL))(
            *((_QWORD *)this + 13),
            a2,
            psz);
  if ( Array >= 0 )
  {
    v11 = (const OLECHAR *)psz;
    if ( psz[3] > (OLECHAR *)7 )
      v11 = psz[0];
    v12 = SysAllocString(v11);
    a3->llVal = (LONGLONG)v12;
    if ( !SysStringLen(v12) )
      Array = -2147024882;
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)psz);
  if ( Array >= 0 )
    goto LABEL_32;
  return (unsigned int)Array;
}

```

## disassembly

```asm
0x140266d90  mov     [rsp-28h+arg_18], rbx
0x140266d95  push    rbp
0x140266d96  push    rsi
0x140266d97  push    rdi
0x140266d98  push    r14
0x140266d9a  push    r15
0x140266d9c  mov     rbp, rsp
0x140266d9f  sub     rsp, 60h
0x140266da3  mov     rax, cs:__security_cookie
0x140266daa  xor     rax, rsp
0x140266dad  mov     [rbp+var_8], rax
0x140266db1  mov     rdi, r8
0x140266db4  mov     r15, rdx
0x140266db7  mov     r14, rcx
0x140266dba  mov     eax, [rcx+80h]
0x140266dc0  test    al, 1
0x140266dc2  jnz     short loc_140266DD5
0x140266dc4  test    eax, 0FFFFFFFCh
0x140266dc9  ja      short loc_140266DD5
0x140266dcb  mov     ebx, 8000FFFFh
0x140266dd0  jmp     loc_14026700B
0x140266dd5  xor     eax, eax
0x140266dd7  mov     [rbp+var_40], ax
0x140266ddb  mov     rcx, [rcx+68h]
0x140266ddf  mov     rax, [rcx]
0x140266de2  lea     r8, [rbp+var_40]
0x140266de6  mov     rax, [rax+0B0h]
0x140266ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140266df2  mov     ebx, eax
0x140266df4  test    eax, eax
0x140266df6  js      loc_14026700B
0x140266dfc  movzx   eax, [rbp+var_40]
0x140266e00  cmp     eax, 5
0x140266e03  jz      loc_140266FD5
0x140266e09  cmp     eax, 8
0x140266e0c  jz      loc_140266F65
0x140266e12  cmp     eax, 0Bh
0x140266e15  jz      loc_140266F27
0x140266e1b  cmp     eax, 14h
0x140266e1e  jz      loc_140266EF1
0x140266e24  cmp     eax, 2011h
0x140266e29  jz      short loc_140266E35
0x140266e2b  mov     ebx, 80070057h
0x140266e30  jmp     loc_14026700B
0x140266e35  mov     [rbp+var_3C], 0
0x140266e3c  mov     rcx, [r14+68h]
0x140266e40  mov     rax, [rcx]
0x140266e43  lea     r8, [rbp+var_3C]
0x140266e47  mov     rdx, r15
0x140266e4a  mov     rax, [rax+0A0h]
0x140266e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140266e56  mov     ebx, eax
0x140266e58  test    eax, eax
0x140266e5a  js      loc_14026700B
0x140266e60  mov     eax, [rbp+var_3C]
0x140266e63  mov     [rbp+rgsabound.cElements], eax
0x140266e66  mov     [rbp+rgsabound.lLbound], 0
0x140266e6d  mov     ecx, 11h; vt
0x140266e72  lea     r8, [rbp+rgsabound]; rgsabound
0x140266e76  lea     edx, [rcx-10h]; cDims
0x140266e79  call    cs:__imp_SafeArrayCreate
0x140266e80  nop     dword ptr [rax+rax+00h]
0x140266e85  mov     rsi, rax
0x140266e88  test    rax, rax
0x140266e8b  jz      loc_140267004
0x140266e91  mov     [rbp+ppvData], 0
0x140266e99  lea     rdx, [rbp+ppvData]; ppvData
0x140266e9d  mov     rcx, rax; psa
0x140266ea0  call    cs:__imp_SafeArrayAccessData
0x140266ea7  nop     dword ptr [rax+rax+00h]
0x140266eac  mov     r9d, [rbp+var_3C]; unsigned int
0x140266eb0  mov     r8, [rbp+ppvData]; void *
0x140266eb4  mov     rdx, r15; unsigned __int16 *
0x140266eb7  mov     rcx, r14; this
0x140266eba  call    ?ReadArray@SavedStateRepository@@UEBAJPEBGPEAXI@Z; SavedStateRepository::ReadArray(ushort const *,void *,uint)
0x140266ebf  mov     ebx, eax
0x140266ec1  mov     rcx, rsi; psa
0x140266ec4  call    cs:__imp_SafeArrayUnaccessData
0x140266ecb  nop     dword ptr [rax+rax+00h]
0x140266ed0  test    ebx, ebx
0x140266ed2  js      short loc_140266EDD
0x140266ed4  mov     [rdi+8], rsi
0x140266ed8  jmp     loc_140267004
0x140266edd  mov     rcx, rsi; psa
0x140266ee0  call    cs:__imp_SafeArrayDestroy
0x140266ee7  nop     dword ptr [rax+rax+00h]
0x140266eec  jmp     loc_14026700B
0x140266ef1  mov     [rbp+ppvData], 0
0x140266ef9  mov     rcx, [r14+68h]
0x140266efd  mov     rax, [rcx]
0x140266f00  lea     r8, [rbp+ppvData]
0x140266f04  mov     rdx, r15
0x140266f07  mov     rax, [rax+50h]
0x140266f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140266f10  mov     ebx, eax
0x140266f12  test    eax, eax
0x140266f14  js      loc_14026700B
0x140266f1a  mov     rax, [rbp+ppvData]
0x140266f1e  mov     [rdi+8], rax
0x140266f22  jmp     loc_140267004
0x140266f27  mov     [rbp+var_3C], 0
0x140266f2e  mov     rcx, [r14+68h]
0x140266f32  mov     rax, [rcx]
0x140266f35  lea     r8, [rbp+var_3C]
0x140266f39  mov     rdx, r15
0x140266f3c  mov     rax, [rax+68h]
0x140266f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140266f45  mov     ebx, eax
0x140266f47  test    eax, eax
0x140266f49  js      loc_14026700B
0x140266f4f  cmp     [rbp+var_3C], 0
0x140266f53  jz      short loc_140266F5A
0x140266f55  or      eax, 0FFFFFFFFh
0x140266f58  jmp     short loc_140266F5C
0x140266f5a  xor     eax, eax
0x140266f5c  mov     [rdi+8], ax
0x140266f60  jmp     loc_140267004
0x140266f65  lea     rcx, [rbp+psz]; void *
0x140266f69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140266f6e  nop
0x140266f6f  mov     rcx, [r14+68h]
0x140266f73  mov     rax, [rcx]
0x140266f76  lea     r8, [rbp+psz]
0x140266f7a  mov     rdx, r15
0x140266f7d  mov     rax, [rax+88h]
0x140266f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140266f89  mov     ebx, eax
0x140266f8b  test    eax, eax
0x140266f8d  js      short loc_140266FC6
0x140266f8f  lea     rcx, [rbp+psz]
0x140266f93  cmp     [rbp+var_18], 7
0x140266f98  cmova   rcx, [rbp+psz]; psz
0x140266f9d  call    cs:__imp_SysAllocString
0x140266fa4  nop     dword ptr [rax+rax+00h]
0x140266fa9  mov     [rdi+8], rax
0x140266fad  mov     rcx, rax; pbstr
0x140266fb0  call    cs:__imp_SysStringLen
0x140266fb7  nop     dword ptr [rax+rax+00h]
0x140266fbc  mov     ecx, 8007000Eh
0x140266fc1  test    eax, eax
0x140266fc3  cmovz   ebx, ecx
0x140266fc6  lea     rcx, [rbp+psz]; this
0x140266fca  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140266fcf  test    ebx, ebx
0x140266fd1  js      short loc_14026700B
0x140266fd3  jmp     short loc_140267004
0x140266fd5  xorps   xmm0, xmm0
0x140266fd8  movsd   [rbp+ppvData], xmm0
0x140266fdd  mov     rcx, [r14+68h]
0x140266fe1  mov     rax, [rcx]
0x140266fe4  lea     r8, [rbp+ppvData]
0x140266fe8  mov     rdx, r15
0x140266feb  mov     rax, [rax+78h]
0x140266fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140266ff4  mov     ebx, eax
0x140266ff6  test    eax, eax
0x140266ff8  js      short loc_14026700B
0x140266ffa  movsd   xmm0, [rbp+ppvData]
0x140266fff  movsd   qword ptr [rdi+8], xmm0
0x140267004  movzx   eax, [rbp+var_40]
0x140267008  mov     [rdi], ax
0x14026700b  mov     eax, ebx
0x14026700d  mov     rcx, [rbp+var_8]
0x140267011  xor     rcx, rsp; StackCookie
0x140267014  call    __security_check_cookie
0x140267019  mov     rbx, [rsp+60h+arg_18]
0x140267021  add     rsp, 60h
0x140267025  pop     r15
0x140267027  pop     r14
0x140267029  pop     rdi
0x14026702a  pop     rsi
0x14026702b  pop     rbp
0x14026702c  retn
```

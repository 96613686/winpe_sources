# CSWbemObjectObjectPath::get_Keys(ISWbemNamedValueSet * *)

- ea: `0x180020020`
- end: `0x180020163`
- name: `?get_Keys@CSWbemObjectObjectPath@@UEAAJPEAPEAUISWbemNamedValueSet@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(CSWbemObjectObjectPath *__hidden this, struct ISWbemNamedValueSet **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x18001148c`
- `0x18001fc1c`
- `0x180020020`
- `0x180022d70`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180020094`
- `OLEAUT32!__imp_SysAllocString` at `0x180020094`
- `OLEAUT32!__imp_SysFreeString` at `0x1800200cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002013b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800200cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002013b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002007c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800200dd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002007c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800200dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSWbemObjectObjectPath::get_Keys(CSWbemObjectObjectPath *this, struct ISWbemNamedValueSet **a2)
{
  char v4; // si
  int v5; // edi
  CWbemPathCracker *v6; // rbp
  OLECHAR *v7; // rbx
  struct CWbemPathCracker *v8; // rbp
  CSWbemNamedValueSet *v9; // rax
  CSWbemNamedValueSet *v10; // rbx
  unsigned int v11; // edx
  OLECHAR *psz; // [rsp+70h] [rbp+18h] BYREF
  OLECHAR *v14; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  ResetLastErrors();
  if ( !a2 )
  {
    v5 = -2147217400;
LABEL_19:
    CDispatchHelp::RaiseException((CSWbemObjectObjectPath *)((char *)this + 40), v5);
    return (unsigned int)v5;
  }
  v5 = -2147217407;
  *a2 = 0;
  psz = 0;
  if ( (*(unsigned int (__fastcall **)(CSWbemObjectObjectPath *, OLECHAR **))(*(_QWORD *)this + 56LL))(this, &psz) )
    goto LABEL_19;
  v6 = (CWbemPathCracker *)CWin32DefaultArena::WbemMemAlloc(0x20u);
  if ( v6 )
  {
    v7 = SysAllocString(psz);
    v14 = v7;
    v4 = 1;
    v8 = CWbemPathCracker::CWbemPathCracker(v6, (const struct ATL::CComBSTR *)&v14);
  }
  else
  {
    v8 = 0;
    v7 = v14;
  }
  if ( (v4 & 1) != 0 )
    SysFreeString(v7);
  if ( v8
    && ((v9 = (CSWbemNamedValueSet *)CWin32DefaultArena::WbemMemAlloc(0x98u)) == 0
      ? (v10 = 0)
      : (v10 = CSWbemNamedValueSet::CSWbemNamedValueSet(v9, v8, 0)),
        v10) )
  {
    if ( (**(int (__fastcall ***)(CSWbemNamedValueSet *, GUID *, struct ISWbemNamedValueSet **))v10)(
           v10,
           &IID_ISWbemNamedValueSet,
           a2) < 0 )
      CSWbemNamedValueSet::`scalar deleting destructor'(v10, v11);
    else
      v5 = 0;
  }
  else
  {
    v5 = -2147217402;
  }
  SysFreeString(psz);
  if ( v5 < 0 )
    goto LABEL_19;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020020  mov     [rsp+arg_0], rbx
0x180020025  push    rbp
0x180020026  push    rsi
0x180020027  push    rdi
0x180020028  push    r14
0x18002002a  push    r15
0x18002002c  sub     rsp, 30h
0x180020030  mov     r14, rdx
0x180020033  mov     r15, rcx
0x180020036  xor     esi, esi
0x180020038  mov     dword ptr [rsp+58h+arg_8], esi
0x18002003c  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180020041  test    r14, r14
0x180020044  jnz     short loc_180020050
0x180020046  mov     edi, 80041008h
0x18002004b  jmp     loc_180020145
0x180020050  mov     edi, 80041001h
0x180020055  mov     [r14], rsi
0x180020058  mov     [rsp+58h+psz], rsi
0x18002005d  mov     rax, [r15]
0x180020060  lea     rdx, [rsp+58h+psz]
0x180020065  mov     rcx, r15
0x180020068  mov     rax, [rax+38h]
0x18002006c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020071  test    eax, eax
0x180020073  jnz     loc_180020145
0x180020079  lea     ecx, [rax+20h]
0x18002007c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180020082  mov     rbp, rax
0x180020085  mov     [rsp+58h+var_38], rax
0x18002008a  test    rax, rax
0x18002008d  jz      short loc_1800200BD
0x18002008f  mov     rcx, [rsp+58h+psz]; psz
0x180020094  call    cs:__imp_SysAllocString
0x18002009a  mov     rbx, rax
0x18002009d  mov     [rsp+58h+arg_18], rax
0x1800200a2  mov     esi, 1
0x1800200a7  mov     dword ptr [rsp+58h+arg_8], esi
0x1800200ab  lea     rdx, [rsp+58h+arg_18]; struct ATL::CComBSTR *
0x1800200b0  mov     rcx, rbp; this
0x1800200b3  call    ??0CWbemPathCracker@@QEAA@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::CWbemPathCracker(ATL::CComBSTR const &)
0x1800200b8  mov     rbp, rax
0x1800200bb  jmp     short loc_1800200C4
0x1800200bd  xor     ebp, ebp
0x1800200bf  mov     rbx, [rsp+58h+arg_18]
0x1800200c4  test    sil, 1
0x1800200c8  jz      short loc_1800200D3
0x1800200ca  mov     rcx, rbx; bstrString
0x1800200cd  call    cs:__imp_SysFreeString
0x1800200d3  test    rbp, rbp
0x1800200d6  jz      short loc_180020107
0x1800200d8  mov     ecx, 98h
0x1800200dd  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800200e3  mov     [rsp+58h+arg_8], rax
0x1800200e8  test    rax, rax
0x1800200eb  jz      short loc_180020100
0x1800200ed  xor     r8d, r8d; bool
0x1800200f0  mov     rdx, rbp; struct CWbemPathCracker *
0x1800200f3  mov     rcx, rax; this
0x1800200f6  call    ??0CSWbemNamedValueSet@@QEAA@PEAVCWbemPathCracker@@_N@Z; CSWbemNamedValueSet::CSWbemNamedValueSet(CWbemPathCracker *,bool)
0x1800200fb  mov     rbx, rax
0x1800200fe  jmp     short loc_180020102
0x180020100  xor     ebx, ebx
0x180020102  test    rbx, rbx
0x180020105  jnz     short loc_18002010E
0x180020107  mov     edi, 80041006h
0x18002010c  jmp     short loc_180020136
0x18002010e  mov     rax, [rbx]
0x180020111  mov     r8, r14
0x180020114  lea     rdx, IID_ISWbemNamedValueSet
0x18002011b  mov     rcx, rbx
0x18002011e  mov     rax, [rax]
0x180020121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020126  test    eax, eax
0x180020128  js      short loc_18002012E
0x18002012a  xor     edi, edi
0x18002012c  jmp     short loc_180020136
0x18002012e  mov     rcx, rbx; this
0x180020131  call    ??_GCSWbemNamedValueSet@@QEAAPEAXI@Z; CSWbemNamedValueSet::`scalar deleting destructor'(uint)
0x180020136  mov     rcx, [rsp+58h+psz]; bstrString
0x18002013b  call    cs:__imp_SysFreeString
0x180020141  test    edi, edi
0x180020143  jns     short loc_180020150
0x180020145  lea     rcx, [r15+28h]; this
0x180020149  mov     edx, edi; int
0x18002014b  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180020150  mov     eax, edi
0x180020152  mov     rbx, [rsp+58h+arg_0]
0x180020157  add     rsp, 30h
0x18002015b  pop     r15
0x18002015d  pop     r14
0x18002015f  pop     rdi
0x180020160  pop     rsi
0x180020161  pop     rbp
0x180020162  retn
```

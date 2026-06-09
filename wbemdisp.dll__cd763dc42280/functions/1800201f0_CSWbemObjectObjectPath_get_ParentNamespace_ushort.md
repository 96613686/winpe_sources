# CSWbemObjectObjectPath::get_ParentNamespace(ushort * *)

- ea: `0x1800201f0`
- end: `0x1800202e1`
- name: `?get_ParentNamespace@CSWbemObjectObjectPath@@UEAAJPEAPEAG@Z`
- size: `241`
- prototype: `__int64 __fastcall(CSWbemObjectObjectPath *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x180010794`
- `0x18001148c`
- `0x18001643c`
- `0x1800201f0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002024e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800202c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002024e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800202c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002026c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800202a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800202ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18002026c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800202a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800202ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSWbemObjectObjectPath::get_ParentNamespace(CSWbemObjectObjectPath *this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  OLECHAR *v5; // rbx
  OLECHAR *v6; // rbx
  BSTR v8[4]; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v9; // [rsp+68h] [rbp+28h] BYREF
  OLECHAR *psz; // [rsp+70h] [rbp+30h] BYREF

  ResetLastErrors();
  if ( a2 )
  {
    psz = 0;
    *a2 = 0;
    if ( !(*(unsigned int (__fastcall **)(CSWbemObjectObjectPath *, OLECHAR **))(*(_QWORD *)this + 56LL))(this, &psz) )
    {
      v5 = SysAllocString(psz);
      v9 = v5;
      CWbemPathCracker::CWbemPathCracker((CWbemPathCracker *)v8, (const struct ATL::CComBSTR *)&v9);
      SysFreeString(v5);
      v9 = 0;
      if ( CWbemPathCracker::GetNamespacePath((CWbemPathCracker *)v8, (struct ATL::CComBSTR *)&v9, 1) )
      {
        v6 = 0;
        *a2 = v9;
      }
      else
      {
        v6 = v9;
      }
      SysFreeString(psz);
      SysFreeString(v6);
      CWbemPathCracker::~CWbemPathCracker(v8);
    }
    v4 = 0;
    if ( !*a2 )
      *a2 = SysAllocString(&SystemName);
  }
  else
  {
    v4 = -2147217400;
    CDispatchHelp::RaiseException((CSWbemObjectObjectPath *)((char *)this + 40), -2147217400);
  }
  return v4;
}

```

## disassembly

```asm
0x1800201f0  mov     [rsp-18h+arg_0], rbx
0x1800201f5  push    rbp
0x1800201f6  push    rsi
0x1800201f7  push    rdi
0x1800201f8  mov     rbp, rsp
0x1800201fb  sub     rsp, 40h
0x1800201ff  mov     rdi, rdx
0x180020202  mov     rsi, rcx
0x180020205  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002020a  test    rdi, rdi
0x18002020d  jnz     short loc_180020224
0x18002020f  mov     ebx, 80041008h
0x180020214  lea     rcx, [rsi+28h]; this
0x180020218  mov     edx, ebx; int
0x18002021a  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18002021f  jmp     loc_1800202D2
0x180020224  mov     [rbp+psz], 0
0x18002022c  mov     qword ptr [rdi], 0
0x180020233  mov     rax, [rsi]
0x180020236  lea     rdx, [rbp+psz]
0x18002023a  mov     rcx, rsi
0x18002023d  mov     rax, [rax+38h]
0x180020241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020246  test    eax, eax
0x180020248  jnz     short loc_1800202BB
0x18002024a  mov     rcx, [rbp+psz]; psz
0x18002024e  call    cs:__imp_SysAllocString
0x180020254  mov     rbx, rax
0x180020257  mov     [rbp+arg_8], rax
0x18002025b  lea     rdx, [rbp+arg_8]; struct ATL::CComBSTR *
0x18002025f  lea     rcx, [rbp+var_20]; this
0x180020263  call    ??0CWbemPathCracker@@QEAA@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::CWbemPathCracker(ATL::CComBSTR const &)
0x180020268  nop
0x180020269  mov     rcx, rbx; bstrString
0x18002026c  call    cs:__imp_SysFreeString
0x180020272  mov     [rbp+arg_8], 0
0x18002027a  mov     r8b, 1; bool
0x18002027d  lea     rdx, [rbp+arg_8]; struct ATL::CComBSTR *
0x180020281  lea     rcx, [rbp+var_20]; this
0x180020285  call    ?GetNamespacePath@CWbemPathCracker@@QEAA_NAEAVCComBSTR@ATL@@_N@Z; CWbemPathCracker::GetNamespacePath(ATL::CComBSTR &,bool)
0x18002028a  test    al, al
0x18002028c  jz      short loc_180020299
0x18002028e  mov     rax, [rbp+arg_8]
0x180020292  xor     ebx, ebx
0x180020294  mov     [rdi], rax
0x180020297  jmp     short loc_18002029D
0x180020299  mov     rbx, [rbp+arg_8]
0x18002029d  mov     rcx, [rbp+psz]; bstrString
0x1800202a1  call    cs:__imp_SysFreeString
0x1800202a7  nop
0x1800202a8  mov     rcx, rbx; bstrString
0x1800202ab  call    cs:__imp_SysFreeString
0x1800202b1  nop
0x1800202b2  lea     rcx, [rbp+var_20]; this
0x1800202b6  call    ??1CWbemPathCracker@@UEAA@XZ; CWbemPathCracker::~CWbemPathCracker(void)
0x1800202bb  xor     ebx, ebx
0x1800202bd  cmp     [rdi], rbx
0x1800202c0  jnz     short loc_1800202D2
0x1800202c2  lea     rcx, SystemName; psz
0x1800202c9  call    cs:__imp_SysAllocString
0x1800202cf  mov     [rdi], rax
0x1800202d2  mov     eax, ebx
0x1800202d4  mov     rbx, [rsp+40h+arg_0]
0x1800202d9  add     rsp, 40h
0x1800202dd  pop     rdi
0x1800202de  pop     rsi
0x1800202df  pop     rbp
0x1800202e0  retn
```

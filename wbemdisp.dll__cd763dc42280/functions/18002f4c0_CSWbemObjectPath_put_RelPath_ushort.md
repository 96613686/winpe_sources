# CSWbemObjectPath::put_RelPath(ushort *)

- ea: `0x18002f4c0`
- end: `0x18002f565`
- name: `?put_RelPath@CSWbemObjectPath@@UEAAJPEAG@Z`
- size: `165`
- prototype: `int(CSWbemObjectPath *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x18001148c`
- `0x18001643c`
- `0x18002f4c0`
- `0x180032bac`
- `0x180033304`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002f4de`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f4de`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f53b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f53b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSWbemObjectPath::put_RelPath(CSWbemObjectPath *this, unsigned __int16 *a2)
{
  CWbemPathCracker *v4; // rsi
  OLECHAR *v5; // rbx
  bool v6; // di
  unsigned int v7; // ebx
  BSTR v9[9]; // [rsp+20h] [rbp-48h] BYREF
  OLECHAR *v10; // [rsp+70h] [rbp+8h] BYREF

  ResetLastErrors();
  v4 = (CWbemPathCracker *)*((_QWORD *)this + 18);
  v5 = SysAllocString(a2);
  v10 = v5;
  v6 = 0;
  CWbemPathCracker::CWbemPathCracker((CWbemPathCracker *)v9, (const struct ATL::CComBSTR *)&v10);
  if ( CWbemPathCracker::CopyServerAndNamespace(v4, (struct CWbemPathCracker *)v9) )
  {
    CWbemPathCracker::operator=(v4, (CWbemPathCracker *)v9);
    v6 = *((_DWORD *)v4 + 7) != 0;
  }
  CWbemPathCracker::~CWbemPathCracker(v9);
  SysFreeString(v5);
  if ( v6 )
  {
    return 0;
  }
  else
  {
    v7 = -2147217407;
    CDispatchHelp::RaiseException((CSWbemObjectPath *)((char *)this + 32), -2147217407);
  }
  return v7;
}

```

## disassembly

```asm
0x18002f4c0  push    rbx
0x18002f4c2  push    rbp
0x18002f4c3  push    rsi
0x18002f4c4  push    rdi
0x18002f4c5  sub     rsp, 48h
0x18002f4c9  mov     rbx, rdx
0x18002f4cc  mov     rbp, rcx
0x18002f4cf  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002f4d4  mov     rsi, [rbp+90h]
0x18002f4db  mov     rcx, rbx; psz
0x18002f4de  call    cs:__imp_SysAllocString
0x18002f4e4  mov     rbx, rax
0x18002f4e7  mov     [rsp+68h+arg_0], rax
0x18002f4ec  xor     dil, dil
0x18002f4ef  lea     rdx, [rsp+68h+arg_0]; struct ATL::CComBSTR *
0x18002f4f4  lea     rcx, [rsp+68h+var_48]; this
0x18002f4f9  call    ??0CWbemPathCracker@@QEAA@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::CWbemPathCracker(ATL::CComBSTR const &)
0x18002f4fe  nop
0x18002f4ff  lea     rdx, [rsp+68h+var_48]; struct CWbemPathCracker *
0x18002f504  mov     rcx, rsi; this
0x18002f507  call    ?CopyServerAndNamespace@CWbemPathCracker@@AEAA_NAEAV1@@Z; CWbemPathCracker::CopyServerAndNamespace(CWbemPathCracker &)
0x18002f50c  test    al, al
0x18002f50e  jz      short loc_18002F52D
0x18002f510  lea     rdx, [rsp+68h+var_48]; CWbemPathCracker *
0x18002f515  mov     rcx, rsi; this
0x18002f518  call    ??4CWbemPathCracker@@QEAAAEBV0@AEAV0@@Z; CWbemPathCracker::operator=(CWbemPathCracker &)
0x18002f51d  movzx   edi, dil
0x18002f521  mov     eax, 1
0x18002f526  cmp     dword ptr [rsi+1Ch], 0
0x18002f52a  cmovnz  edi, eax
0x18002f52d  lea     rcx, [rsp+68h+var_48]; this
0x18002f532  call    ??1CWbemPathCracker@@UEAA@XZ; CWbemPathCracker::~CWbemPathCracker(void)
0x18002f537  nop
0x18002f538  mov     rcx, rbx; bstrString
0x18002f53b  call    cs:__imp_SysFreeString
0x18002f541  test    dil, dil
0x18002f544  jz      short loc_18002F54A
0x18002f546  xor     ebx, ebx
0x18002f548  jmp     short loc_18002F55A
0x18002f54a  mov     ebx, 80041001h
0x18002f54f  lea     rcx, [rbp+20h]; this
0x18002f553  mov     edx, ebx; int
0x18002f555  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18002f55a  mov     eax, ebx
0x18002f55c  add     rsp, 48h
0x18002f560  pop     rdi
0x18002f561  pop     rsi
0x18002f562  pop     rbp
0x18002f563  pop     rbx
0x18002f564  retn
```

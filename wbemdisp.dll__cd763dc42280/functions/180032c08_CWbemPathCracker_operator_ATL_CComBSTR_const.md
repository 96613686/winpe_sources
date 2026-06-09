# CWbemPathCracker::operator=(ATL::CComBSTR const &)

- ea: `0x180032c08`
- end: `0x180032c7e`
- name: `??4CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(CWbemPathCracker *this, struct ATL::CComBSTR *)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002c860`
- `0x18002f0c0`
- `0x18002f430`
- `0x1800317c0`
- `0x180032bac`

## callees

- `0x1800044a4`
- `0x18001148c`
- `0x180011538`
- `0x18001643c`
- `0x180032c08`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180032c25`
- `OLEAUT32!__imp_SysStringLen` at `0x180032c25`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CWbemPathCracker::operator=(CWbemPathCracker *this, struct ATL::CComBSTR *a2)
{
  char v4; // bl
  BSTR v6[3]; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+3Ch] [rbp-Ch]

  if ( *(_QWORD *)a2 && SysStringLen(*(BSTR *)a2) )
  {
    v4 = 0;
    CWbemPathCracker::CWbemPathCracker((CWbemPathCracker *)v6, a2);
    if ( v7 )
    {
      CWbemPathCracker::SetText(this, a2, 0);
      v4 = 1;
    }
    CWbemPathCracker::~CWbemPathCracker(v6);
  }
  else
  {
    CWbemPathCracker::CreateParsers(this);
    return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x180032c08  mov     [rsp+arg_0], rbx
0x180032c0d  mov     [rsp+arg_8], rsi
0x180032c12  push    rdi
0x180032c13  sub     rsp, 40h
0x180032c17  mov     rdi, rdx
0x180032c1a  mov     rsi, rcx
0x180032c1d  mov     rcx, [rdx]; pbstr
0x180032c20  test    rcx, rcx
0x180032c23  jz      short loc_180032C62
0x180032c25  call    cs:__imp_SysStringLen
0x180032c2b  test    eax, eax
0x180032c2d  jz      short loc_180032C62
0x180032c2f  xor     bl, bl
0x180032c31  mov     rdx, rdi; struct ATL::CComBSTR *
0x180032c34  lea     rcx, [rsp+48h+var_28]; this
0x180032c39  call    ??0CWbemPathCracker@@QEAA@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::CWbemPathCracker(ATL::CComBSTR const &)
0x180032c3e  nop
0x180032c3f  cmp     [rsp+48h+var_C], 0
0x180032c44  jz      short loc_180032C56
0x180032c46  xor     r8d, r8d; bool
0x180032c49  mov     rdx, rdi; struct ATL::CComBSTR *
0x180032c4c  mov     rcx, rsi; this
0x180032c4f  call    ?SetText@CWbemPathCracker@@AEAAXAEBVCComBSTR@ATL@@_N@Z; CWbemPathCracker::SetText(ATL::CComBSTR const &,bool)
0x180032c54  mov     bl, 1
0x180032c56  lea     rcx, [rsp+48h+var_28]; this
0x180032c5b  call    ??1CWbemPathCracker@@UEAA@XZ; CWbemPathCracker::~CWbemPathCracker(void)
0x180032c60  jmp     short loc_180032C6C
0x180032c62  mov     rcx, rsi; this
0x180032c65  call    ?CreateParsers@CWbemPathCracker@@AEAAXXZ; CWbemPathCracker::CreateParsers(void)
0x180032c6a  mov     bl, 1
0x180032c6c  mov     al, bl
0x180032c6e  mov     rbx, [rsp+48h+arg_0]
0x180032c73  mov     rsi, [rsp+48h+arg_8]
0x180032c78  add     rsp, 40h
0x180032c7c  pop     rdi
0x180032c7d  retn
```

# CSWbemObjectObjectPath::get_IsSingleton(short *)

- ea: `0x18001ff50`
- end: `0x180020015`
- name: `?get_IsSingleton@CSWbemObjectObjectPath@@UEAAJPEAF@Z`
- size: `197`
- prototype: `__int64 __fastcall(CSWbemObjectObjectPath *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x18001148c`
- `0x18001643c`
- `0x18001ff50`
- `0x180033748`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001ffc1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ffc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ffe2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ffff`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ffe2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ffff`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSWbemObjectObjectPath::get_IsSingleton(CSWbemObjectObjectPath *this, __int16 *a2)
{
  unsigned int v4; // ebx
  OLECHAR *v6; // rbx
  BSTR v7[5]; // [rsp+20h] [rbp-28h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp+10h] BYREF
  OLECHAR *v9; // [rsp+60h] [rbp+18h] BYREF

  ResetLastErrors();
  if ( a2 )
  {
    v4 = -2147217407;
    psz = 0;
    *a2 = 0;
    if ( !(*(unsigned int (__fastcall **)(CSWbemObjectObjectPath *, OLECHAR **))(*(_QWORD *)this + 56LL))(this, &psz) )
    {
      v6 = SysAllocString(psz);
      v9 = v6;
      CWbemPathCracker::CWbemPathCracker((CWbemPathCracker *)v7, (const struct ATL::CComBSTR *)&v9);
      SysFreeString(v6);
      *a2 = CWbemPathCracker::IsSingleton((CWbemPathCracker *)v7);
      v4 = 0;
      SysFreeString(psz);
      CWbemPathCracker::~CWbemPathCracker(v7);
      return v4;
    }
  }
  else
  {
    v4 = -2147217400;
  }
  CDispatchHelp::RaiseException((CSWbemObjectObjectPath *)((char *)this + 40), v4);
  return v4;
}

```

## disassembly

```asm
0x18001ff50  mov     [rsp+arg_0], rbx
0x18001ff55  mov     [rsp+arg_18], rsi
0x18001ff5a  push    rdi
0x18001ff5b  sub     rsp, 40h
0x18001ff5f  mov     rsi, rdx
0x18001ff62  mov     rdi, rcx
0x18001ff65  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001ff6a  test    rsi, rsi
0x18001ff6d  jnz     short loc_18001FF91
0x18001ff6f  mov     ebx, 80041008h
0x18001ff74  lea     rcx, [rdi+28h]; this
0x18001ff78  mov     edx, ebx; int
0x18001ff7a  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001ff7f  mov     eax, ebx
0x18001ff81  mov     rbx, [rsp+48h+arg_0]
0x18001ff86  mov     rsi, [rsp+48h+arg_18]
0x18001ff8b  add     rsp, 40h
0x18001ff8f  pop     rdi
0x18001ff90  retn
0x18001ff91  mov     ebx, 80041001h
0x18001ff96  mov     [rsp+48h+psz], 0
0x18001ff9f  xor     eax, eax
0x18001ffa1  mov     [rsi], ax
0x18001ffa4  mov     rax, [rdi]
0x18001ffa7  lea     rdx, [rsp+48h+psz]
0x18001ffac  mov     rcx, rdi
0x18001ffaf  mov     rax, [rax+38h]
0x18001ffb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffb8  test    eax, eax
0x18001ffba  jnz     short loc_18001FF74
0x18001ffbc  mov     rcx, [rsp+48h+psz]; psz
0x18001ffc1  call    cs:__imp_SysAllocString
0x18001ffc7  mov     rbx, rax
0x18001ffca  mov     [rsp+48h+arg_10], rax
0x18001ffcf  lea     rdx, [rsp+48h+arg_10]; struct ATL::CComBSTR *
0x18001ffd4  lea     rcx, [rsp+48h+var_28]; this
0x18001ffd9  call    ??0CWbemPathCracker@@QEAA@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::CWbemPathCracker(ATL::CComBSTR const &)
0x18001ffde  nop
0x18001ffdf  mov     rcx, rbx; bstrString
0x18001ffe2  call    cs:__imp_SysFreeString
0x18001ffe8  lea     rcx, [rsp+48h+var_28]; this
0x18001ffed  call    ?IsSingleton@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsSingleton(void)
0x18001fff2  movzx   eax, al
0x18001fff5  mov     [rsi], ax
0x18001fff8  xor     ebx, ebx
0x18001fffa  mov     rcx, [rsp+48h+psz]; bstrString
0x18001ffff  call    cs:__imp_SysFreeString
0x180020005  nop
0x180020006  lea     rcx, [rsp+48h+var_28]; this
0x18002000b  call    ??1CWbemPathCracker@@UEAA@XZ; CWbemPathCracker::~CWbemPathCracker(void)
0x180020010  jmp     loc_18001FF7F
```

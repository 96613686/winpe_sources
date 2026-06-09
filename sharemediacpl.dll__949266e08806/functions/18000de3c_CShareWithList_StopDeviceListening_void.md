# CShareWithList::StopDeviceListening(void)

- ea: `0x18000de3c`
- end: `0x18000df25`
- name: `?StopDeviceListening@CShareWithList@@QEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(CShareWithList *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bd4c`
- `0x18000dba8`
- `0x180010bec`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000de3c`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000deb4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000deb4`
- `OLEAUT32!__imp_SysStringLen` at `0x18000de90`
- `OLEAUT32!__imp_SysStringLen` at `0x18000de90`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000dedb`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000dedb`

## pseudocode

```c
__int64 __fastcall CShareWithList::StopDeviceListening(CShareWithList *this)
{
  _QWORD *v2; // rcx
  unsigned int v3; // edi

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 5) )
  {
    v3 = 0;
    if ( SysStringLen(*((BSTR *)this + 6)) )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 120LL))(
             *((_QWORD *)this + 5),
             *((_QWORD *)this + 6));
      SysFreeString(*((BSTR *)this + 6));
      *((_QWORD *)this + 6) = 0;
    }
    v2 = WPP_GLOBAL_Control;
  }
  else
  {
    v3 = -2147024809;
  }
  if ( *((_QWORD *)this + 4) )
  {
    DirectUI::DUIXmlParser::Destroy(*((DirectUI::DUIXmlParser **)this + 4));
    *((_QWORD *)this + 4) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 107, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18000de3c  mov     [rsp+arg_0], rbx
0x18000de41  mov     [rsp+arg_8], rbp
0x18000de46  push    rdi
0x18000de47  sub     rsp, 20h
0x18000de4b  mov     rbx, rcx
0x18000de4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de55  lea     rbp, WPP_GLOBAL_Control
0x18000de5c  cmp     rcx, rbp
0x18000de5f  jz      short loc_18000DE83
0x18000de61  test    byte ptr [rcx+1Ch], 20h
0x18000de65  jz      short loc_18000DE83
0x18000de67  mov     rcx, [rcx+10h]
0x18000de6b  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000de72  mov     edx, 6Ah ; 'j'
0x18000de77  call    WPP_SF_
0x18000de7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de83  cmp     qword ptr [rbx+28h], 0
0x18000de88  jz      short loc_18000DECB
0x18000de8a  mov     rcx, [rbx+30h]; pbstr
0x18000de8e  xor     edi, edi
0x18000de90  call    cs:__imp_SysStringLen
0x18000de96  test    eax, eax
0x18000de98  jz      short loc_18000DEC2
0x18000de9a  mov     rcx, [rbx+28h]
0x18000de9e  mov     rdx, [rbx+30h]
0x18000dea2  mov     rax, [rcx]
0x18000dea5  mov     rax, [rax+78h]
0x18000dea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deae  mov     rcx, [rbx+30h]; bstrString
0x18000deb2  mov     edi, eax
0x18000deb4  call    cs:__imp_SysFreeString
0x18000deba  mov     qword ptr [rbx+30h], 0
0x18000dec2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dec9  jmp     short loc_18000DED0
0x18000decb  mov     edi, 80070057h
0x18000ded0  cmp     qword ptr [rbx+20h], 0
0x18000ded5  jz      short loc_18000DEF0
0x18000ded7  mov     rcx, [rbx+20h]
0x18000dedb  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18000dee1  mov     qword ptr [rbx+20h], 0
0x18000dee9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000def0  cmp     rcx, rbp
0x18000def3  jz      short loc_18000DF13
0x18000def5  test    byte ptr [rcx+1Ch], 20h
0x18000def9  jz      short loc_18000DF13
0x18000defb  mov     rcx, [rcx+10h]
0x18000deff  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000df06  mov     edx, 6Bh ; 'k'
0x18000df0b  mov     r9d, edi
0x18000df0e  call    WPP_SF_d
0x18000df13  mov     rbx, [rsp+28h+arg_0]
0x18000df18  mov     eax, edi
0x18000df1a  mov     rbp, [rsp+28h+arg_8]
0x18000df1f  add     rsp, 20h
0x18000df23  pop     rdi
0x18000df24  retn
```

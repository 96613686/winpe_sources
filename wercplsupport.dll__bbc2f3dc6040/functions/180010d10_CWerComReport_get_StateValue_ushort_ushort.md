# CWerComReport::_get_StateValue(ushort *,ushort * *)

- ea: `0x180010d10`
- end: `0x180010e4a`
- name: `?_get_StateValue@CWerComReport@@QEAAJPEAGPEAPEAG@Z`
- size: `314`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011a40`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e35c`
- `0x180010d10`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010de0`
- `OLEAUT32!__imp_SysAllocString` at `0x180010de0`
- `OLEAUT32!__imp_SysFreeString` at `0x180010dd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180010dd5`
- `wer!WerpGetTextFromReport` at `0x180010d9a`
- `wer!WerpGetTextFromReport` at `0x180010d9a`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_StateValue(CWerComReport *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  int WerApiLock; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int TextFromReport; // eax
  unsigned __int16 *v11; // rax
  OLECHAR *psz; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  psz = 0;
  v13 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v13, this);
  if ( WerApiLock < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 58;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  TextFromReport = WerpGetTextFromReport(*((_QWORD *)this + 4), a2, &psz);
  WerApiLock = TextFromReport;
  if ( TextFromReport < 0 )
  {
    if ( TextFromReport != -2147023728 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 59;
        goto LABEL_5;
      }
    }
LABEL_6:
    if ( v13 )
      _InterlockedExchange((volatile __int32 *)(v13 + 48), 0);
    return (unsigned int)WerApiLock;
  }
  if ( !a3 || (SysFreeString(*a3), v11 = SysAllocString(psz), (*a3 = v11) != 0) )
  {
    if ( v13 )
      _InterlockedExchange((volatile __int32 *)(v13 + 48), 0);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    if ( v13 )
      _InterlockedExchange((volatile __int32 *)(v13 + 48), 0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180010d10  push    rbx
0x180010d12  push    rbp
0x180010d13  push    rsi
0x180010d14  push    rdi
0x180010d15  sub     rsp, 38h
0x180010d19  mov     rbp, rdx
0x180010d1c  mov     [rsp+58h+psz], 0
0x180010d25  mov     rdx, rcx; struct CWerComReport *
0x180010d28  mov     [rsp+58h+arg_18], 0
0x180010d31  mov     rsi, rcx
0x180010d34  mov     rdi, r8
0x180010d37  lea     rcx, [rsp+58h+arg_18]; this
0x180010d3c  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x180010d41  mov     ebx, eax
0x180010d43  test    eax, eax
0x180010d45  jns     short loc_180010D8E
0x180010d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d4e  lea     rdx, WPP_GLOBAL_Control
0x180010d55  cmp     rcx, rdx
0x180010d58  jz      short loc_180010D78
0x180010d5a  test    byte ptr [rcx+1Ch], 1
0x180010d5e  jz      short loc_180010D78
0x180010d60  mov     edx, 3Ah ; ':'
0x180010d65  mov     rcx, [rcx+10h]
0x180010d69  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010d70  mov     r9d, ebx
0x180010d73  call    WPP_SF_d
0x180010d78  mov     rax, [rsp+58h+arg_18]
0x180010d7d  test    rax, rax
0x180010d80  jz      short loc_180010D87
0x180010d82  xor     ecx, ecx
0x180010d84  xchg    ecx, [rax+30h]
0x180010d87  mov     eax, ebx
0x180010d89  jmp     loc_180010E41
0x180010d8e  mov     rcx, [rsi+20h]
0x180010d92  lea     r8, [rsp+58h+psz]
0x180010d97  mov     rdx, rbp
0x180010d9a  call    cs:__imp_WerpGetTextFromReport
0x180010da0  mov     ebx, eax
0x180010da2  test    eax, eax
0x180010da4  jns     short loc_180010DCD
0x180010da6  cmp     eax, 80070490h
0x180010dab  jz      short loc_180010D78
0x180010dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180010db4  lea     rdx, WPP_GLOBAL_Control
0x180010dbb  cmp     rcx, rdx
0x180010dbe  jz      short loc_180010D78
0x180010dc0  test    byte ptr [rcx+1Ch], 1
0x180010dc4  jz      short loc_180010D78
0x180010dc6  mov     edx, 3Bh ; ';'
0x180010dcb  jmp     short loc_180010D65
0x180010dcd  test    rdi, rdi
0x180010dd0  jz      short loc_180010E30
0x180010dd2  mov     rcx, [rdi]; bstrString
0x180010dd5  call    cs:__imp_SysFreeString
0x180010ddb  mov     rcx, [rsp+58h+psz]; psz
0x180010de0  call    cs:__imp_SysAllocString
0x180010de6  mov     [rdi], rax
0x180010de9  test    rax, rax
0x180010dec  jnz     short loc_180010E30
0x180010dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180010df5  lea     rdx, WPP_GLOBAL_Control
0x180010dfc  cmp     rcx, rdx
0x180010dff  jz      short loc_180010E1A
0x180010e01  test    byte ptr [rcx+1Ch], 1
0x180010e05  jz      short loc_180010E1A
0x180010e07  mov     rcx, [rcx+10h]
0x180010e0b  lea     edx, [rax+3Ch]
0x180010e0e  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010e15  call    WPP_SF_
0x180010e1a  mov     rax, [rsp+58h+arg_18]
0x180010e1f  test    rax, rax
0x180010e22  jz      short loc_180010E29
0x180010e24  xor     ecx, ecx
0x180010e26  xchg    ecx, [rax+30h]
0x180010e29  mov     eax, 8007000Eh
0x180010e2e  jmp     short loc_180010E41
0x180010e30  mov     rax, [rsp+58h+arg_18]
0x180010e35  test    rax, rax
0x180010e38  jz      short loc_180010E3F
0x180010e3a  xor     ecx, ecx
0x180010e3c  xchg    ecx, [rax+30h]
0x180010e3f  xor     eax, eax
0x180010e41  add     rsp, 38h
0x180010e45  pop     rdi
0x180010e46  pop     rsi
0x180010e47  pop     rbp
0x180010e48  pop     rbx
0x180010e49  retn
```

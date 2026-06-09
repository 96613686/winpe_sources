# CWerComReport::_get_IntegratorId(ushort * *)

- ea: `0x180010508`
- end: `0x180010647`
- name: `?_get_IntegratorId@CWerComReport@@QEAAJPEAPEAG@Z`
- size: `319`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800115c0`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e35c`
- `0x180010508`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800105d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800105d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800105cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800105cb`
- `wer!WerpGetIntegratorReportId` at `0x180010590`
- `wer!WerpGetIntegratorReportId` at `0x180010590`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_IntegratorId(CWerComReport *this, unsigned __int16 **a2)
{
  int WerApiLock; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int IntegratorReportId; // eax
  unsigned __int16 *v9; // rax
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp+20h] BYREF

  psz = 0;
  v10 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v10, this);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 61;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  IntegratorReportId = WerpGetIntegratorReportId(*((_QWORD *)this + 4), &psz);
  WerApiLock = IntegratorReportId;
  if ( IntegratorReportId < 0 )
  {
    if ( IntegratorReportId != -2147023728 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 62;
        goto LABEL_5;
      }
    }
LABEL_6:
    if ( v10 )
      _InterlockedExchange((volatile __int32 *)(v10 + 48), 0);
    return (unsigned int)WerApiLock;
  }
  if ( !a2 || (SysFreeString(*a2), v9 = SysAllocString(psz), (*a2 = v9) != 0) )
  {
    if ( v10 )
      _InterlockedExchange((volatile __int32 *)(v10 + 48), 0);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    if ( v10 )
      _InterlockedExchange((volatile __int32 *)(v10 + 48), 0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180010508  mov     rax, rsp
0x18001050b  mov     [rax+8], rbx
0x18001050f  mov     [rax+10h], rsi
0x180010513  push    rdi
0x180010514  sub     rsp, 20h
0x180010518  mov     rdi, rdx
0x18001051b  mov     qword ptr [rax+20h], 0
0x180010523  mov     rdx, rcx; struct CWerComReport *
0x180010526  mov     qword ptr [rax+18h], 0
0x18001052e  mov     rsi, rcx
0x180010531  lea     rcx, [rax+18h]; this
0x180010535  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18001053a  mov     ebx, eax
0x18001053c  test    eax, eax
0x18001053e  jns     short loc_180010587
0x180010540  mov     rcx, cs:WPP_GLOBAL_Control
0x180010547  lea     rdx, WPP_GLOBAL_Control
0x18001054e  cmp     rcx, rdx
0x180010551  jz      short loc_180010571
0x180010553  test    byte ptr [rcx+1Ch], 1
0x180010557  jz      short loc_180010571
0x180010559  mov     edx, 3Dh ; '='
0x18001055e  mov     rcx, [rcx+10h]
0x180010562  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010569  mov     r9d, ebx
0x18001056c  call    WPP_SF_d
0x180010571  mov     rax, [rsp+28h+arg_10]
0x180010576  test    rax, rax
0x180010579  jz      short loc_180010580
0x18001057b  xor     ecx, ecx
0x18001057d  xchg    ecx, [rax+30h]
0x180010580  mov     eax, ebx
0x180010582  jmp     loc_180010637
0x180010587  mov     rcx, [rsi+20h]
0x18001058b  lea     rdx, [rsp+28h+psz]
0x180010590  call    cs:__imp_WerpGetIntegratorReportId
0x180010596  mov     ebx, eax
0x180010598  test    eax, eax
0x18001059a  jns     short loc_1800105C3
0x18001059c  cmp     eax, 80070490h
0x1800105a1  jz      short loc_180010571
0x1800105a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105aa  lea     rdx, WPP_GLOBAL_Control
0x1800105b1  cmp     rcx, rdx
0x1800105b4  jz      short loc_180010571
0x1800105b6  test    byte ptr [rcx+1Ch], 1
0x1800105ba  jz      short loc_180010571
0x1800105bc  mov     edx, 3Eh ; '>'
0x1800105c1  jmp     short loc_18001055E
0x1800105c3  test    rdi, rdi
0x1800105c6  jz      short loc_180010626
0x1800105c8  mov     rcx, [rdi]; bstrString
0x1800105cb  call    cs:__imp_SysFreeString
0x1800105d1  mov     rcx, [rsp+28h+psz]; psz
0x1800105d6  call    cs:__imp_SysAllocString
0x1800105dc  mov     [rdi], rax
0x1800105df  test    rax, rax
0x1800105e2  jnz     short loc_180010626
0x1800105e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105eb  lea     rdx, WPP_GLOBAL_Control
0x1800105f2  cmp     rcx, rdx
0x1800105f5  jz      short loc_180010610
0x1800105f7  test    byte ptr [rcx+1Ch], 1
0x1800105fb  jz      short loc_180010610
0x1800105fd  mov     rcx, [rcx+10h]
0x180010601  lea     edx, [rax+3Fh]
0x180010604  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18001060b  call    WPP_SF_
0x180010610  mov     rax, [rsp+28h+arg_10]
0x180010615  test    rax, rax
0x180010618  jz      short loc_18001061F
0x18001061a  xor     ecx, ecx
0x18001061c  xchg    ecx, [rax+30h]
0x18001061f  mov     eax, 8007000Eh
0x180010624  jmp     short loc_180010637
0x180010626  mov     rax, [rsp+28h+arg_10]
0x18001062b  test    rax, rax
0x18001062e  jz      short loc_180010635
0x180010630  xor     ecx, ecx
0x180010632  xchg    ecx, [rax+30h]
0x180010635  xor     eax, eax
0x180010637  mov     rbx, [rsp+28h+arg_0]
0x18001063c  mov     rsi, [rsp+28h+arg_8]
0x180010641  add     rsp, 20h
0x180010645  pop     rdi
0x180010646  retn
```

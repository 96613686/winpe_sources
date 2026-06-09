# ApplySettings::ProcessIAS(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x1800450d8`
- end: `0x180045203`
- name: `?ProcessIAS@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043eec`

## callees

- `0x180038ad0`
- `0x180042a80`
- `0x1800450d8`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `msvcrt!wcstol` at `0x180045134`
- `msvcrt!wcstol` at `0x180045134`
- `KERNEL32!GetLastError` at `0x18004517b`
- `KERNEL32!GetLastError` at `0x18004517b`
- `OLEAUT32!__imp_SysAllocString` at `0x180045150`
- `OLEAUT32!__imp_SysAllocString` at `0x180045150`
- `OLEAUT32!__imp_SysFreeString` at `0x180045171`
- `OLEAUT32!__imp_SysFreeString` at `0x180045171`

## string_xrefs

- `0x1800451cc`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800451b8`: `g_pService->put_Description`

## pseudocode

```c
__int64 __fastcall ApplySettings::ProcessIAS(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebp
  const wchar_t *v5; // rsi
  const OLECHAR *v6; // rdi
  OLECHAR *v7; // rbx
  signed int LastError; // eax
  char v9; // bl
  int v10; // r8d
  int v11; // r9d

  v4 = 0;
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 16);
  v5 = (const wchar_t *)(a1 + 48);
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 48);
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 80);
  v6 = (const OLECHAR *)(a1 + 112);
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 112);
  if ( *(_QWORD *)(a1 + 72) >= 8u )
    v5 = *(const wchar_t **)v5;
  if ( wcstol(v5, 0, 10) == 3 )
  {
    if ( *(_QWORD *)(a1 + 136) >= 8u )
      v6 = *(const OLECHAR **)v6;
    v7 = SysAllocString(v6);
    v4 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)(a1 + 8) + 120LL))(*(_QWORD *)(a1 + 8), v7);
    SysFreeString(v7);
    if ( v4 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v9 = LastError;
      }
      else
      {
        v9 = 5;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
        WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, v10, v11, (__int64)"g_pService->put_Description", v9);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800450d8  push    rbx
0x1800450da  push    rbp
0x1800450db  push    rsi
0x1800450dc  push    rdi
0x1800450dd  push    r14
0x1800450df  sub     rsp, 30h
0x1800450e3  mov     rbx, rdx
0x1800450e6  mov     r14, rcx
0x1800450e9  lea     rdx, [rcx+10h]
0x1800450ed  xor     ebp, ebp
0x1800450ef  mov     rcx, rbx
0x1800450f2  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x1800450f7  lea     rsi, [r14+30h]
0x1800450fb  mov     rcx, rbx
0x1800450fe  mov     rdx, rsi
0x180045101  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180045106  lea     rdx, [r14+50h]
0x18004510a  mov     rcx, rbx
0x18004510d  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180045112  lea     rdi, [r14+70h]
0x180045116  mov     rcx, rbx
0x180045119  mov     rdx, rdi
0x18004511c  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180045121  cmp     qword ptr [rsi+18h], 8
0x180045126  jb      short loc_18004512B
0x180045128  mov     rsi, [rsi]
0x18004512b  xor     edx, edx; EndPtr
0x18004512d  mov     rcx, rsi; String
0x180045130  lea     r8d, [rdx+0Ah]; Radix
0x180045134  call    cs:__imp_wcstol
0x18004513a  cmp     eax, 3
0x18004513d  jnz     loc_1800451F6
0x180045143  cmp     qword ptr [rdi+18h], 8
0x180045148  jb      short loc_18004514D
0x18004514a  mov     rdi, [rdi]
0x18004514d  mov     rcx, rdi; psz
0x180045150  call    cs:__imp_SysAllocString
0x180045156  mov     rcx, [r14+8]
0x18004515a  mov     rbx, rax
0x18004515d  mov     rdx, [rcx]
0x180045160  mov     rax, [rdx+78h]
0x180045164  mov     rdx, rbx
0x180045167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004516c  mov     rcx, rbx; bstrString
0x18004516f  mov     ebp, eax
0x180045171  call    cs:__imp_SysFreeString
0x180045177  test    ebp, ebp
0x180045179  jz      short loc_1800451F6
0x18004517b  call    cs:__imp_GetLastError
0x180045181  mov     ebx, eax
0x180045183  test    eax, eax
0x180045185  jz      short loc_180045194
0x180045187  jle     short loc_180045199
0x180045189  movzx   ebx, ax
0x18004518c  or      ebx, 80070000h
0x180045192  jmp     short loc_180045199
0x180045194  mov     ebx, 80004005h
0x180045199  mov     rax, cs:WPP_GLOBAL_Control
0x1800451a0  lea     rcx, WPP_GLOBAL_Control
0x1800451a7  cmp     rax, rcx
0x1800451aa  jz      short loc_1800451F6
0x1800451ac  cmp     byte ptr [rax+19h], 2
0x1800451b0  jb      short loc_1800451F6
0x1800451b2  test    byte ptr [rax+1Ch], 10h
0x1800451b6  jz      short loc_1800451F6
0x1800451b8  lea     rdi, aGPservicePutDe; "g_pService->put_Description"
0x1800451bf  mov     r9d, ebx
0x1800451c2  mov     r8, rdi
0x1800451c5  lea     rdx, aNpsds; "NPSDS"
0x1800451cc  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800451d3  call    WppDbgPrint
0x1800451d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800451df  mov     edx, 24h ; '$'
0x1800451e4  mov     [rsp+58h+var_30], ebx
0x1800451e8  mov     [rsp+58h+var_38], rdi
0x1800451ed  mov     rcx, [rcx+10h]
0x1800451f1  call    WPP_SF_ssd
0x1800451f6  mov     eax, ebp
0x1800451f8  add     rsp, 30h
0x1800451fc  pop     r14
0x1800451fe  pop     rdi
0x1800451ff  pop     rsi
0x180045200  pop     rbp
0x180045201  pop     rbx
0x180045202  retn
```

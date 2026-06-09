# DllGetClassObject

- ea: `0x180005990`
- end: `0x180005b76`
- name: `DllGetClassObject`
- size: `486`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001918`
- `0x18000593c`
- `0x180005990`
- `0x180005f3c`
- `0x180007010`

## string_xrefs

- `0x1800059af`: `onecoreuap\base\diagnosis\platform\notifications\inproc\dll\dllmain.cpp`
- `0x180005a75`: `onecoreuap\base\diagnosis\platform\notifications\inproc\dll\dllmain.cpp`
- `0x180005ad3`: `onecoreuap\base\diagnosis\platform\notifications\inproc\dll\dllmain.cpp`
- `0x180005b17`: `onecoreuap\base\diagnosis\platform\notifications\inproc\dll\dllmain.cpp`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  int v11; // eax
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( ppv )
  {
    *ppv = 0;
    if ( *(_OWORD *)&GUID_201600d8_6eff_48ce_b842_e14d37a0682d == *(_OWORD *)rclsid )
    {
      v9 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v10 = v9;
      if ( v9 )
      {
        v9[2] = 1;
        *(_QWORD *)v9 = &CWpnIdleTaskHandlerFactory::`vftable';
        _InterlockedIncrement(&g_Count);
        v11 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v9)(v9, riid, ppv);
        v5 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB2,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\dll\\dllmain.cpp",
            (const char *)(unsigned int)v11,
            v13);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_3a96b840b9793ae967b06867319dff15_Traceguids, v5);
        }
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 16LL))(v10);
      }
      else
      {
        v5 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\dll\\dllmain.cpp",
          (const char *)0x8007000ELL,
          v13);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v7 = 12;
          v8 = 2147942414LL;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v5 = -2147221231;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\dll\\dllmain.cpp",
        (const char *)0x80040111LL,
        v13);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v7 = 14;
        v8 = 2147746065LL;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v5 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\dll\\dllmain.cpp",
      (const char *)0x80070057LL,
      v13);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v7 = 11;
      v8 = 2147942487LL;
LABEL_18:
      WPP_SF_D(v6[2], v7, WPP_3a96b840b9793ae967b06867319dff15_Traceguids, v8);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180005990  mov     [rsp+arg_0], rbx
0x180005995  mov     [rsp+arg_8], rsi
0x18000599a  push    rdi; int
0x18000599b  sub     rsp, 20h
0x18000599f  mov     rbx, r8
0x1800059a2  mov     rsi, rdx
0x1800059a5  test    r8, r8
0x1800059a8  jnz     short loc_1800059F9
0x1800059aa  mov     rcx, [rsp+28h]; this
0x1800059af  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800059b6  mov     ebx, 80070057h
0x1800059bb  mov     edx, 0A6h; void *
0x1800059c0  mov     r9d, ebx; char *
0x1800059c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800059c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059cf  lea     rax, WPP_GLOBAL_Control
0x1800059d6  cmp     rcx, rax
0x1800059d9  jz      loc_180005B64
0x1800059df  test    byte ptr [rcx+1Ch], 80h
0x1800059e3  jz      loc_180005B64
0x1800059e9  mov     edx, 0Bh
0x1800059ee  mov     r9d, 80070057h
0x1800059f4  jmp     loc_180005B54
0x1800059f9  mov     qword ptr [r8], 0
0x180005a00  mov     rax, qword ptr cs:_GUID_201600d8_6eff_48ce_b842_e14d37a0682d.Data1
0x180005a07  cmp     rax, [rcx]
0x180005a0a  jnz     loc_180005B12
0x180005a10  mov     rax, qword ptr cs:_GUID_201600d8_6eff_48ce_b842_e14d37a0682d.Data4
0x180005a17  cmp     rax, [rcx+8]
0x180005a1b  jnz     loc_180005B12
0x180005a21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005a28  mov     ecx, 10h; unsigned __int64
0x180005a2d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005a32  mov     rdi, rax
0x180005a35  test    rax, rax
0x180005a38  jz      loc_180005ACE
0x180005a3e  lea     rax, ??_7CWpnIdleTaskHandlerFactory@@6B@; const CWpnIdleTaskHandlerFactory::`vftable'
0x180005a45  mov     dword ptr [rdi+8], 1
0x180005a4c  mov     [rdi], rax
0x180005a4f  lock inc cs:?g_Count@@3JA; long g_Count
0x180005a56  mov     rax, [rdi]
0x180005a59  mov     r8, rbx
0x180005a5c  mov     rdx, rsi
0x180005a5f  mov     rcx, rdi
0x180005a62  mov     rax, [rax]
0x180005a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a6a  mov     ebx, eax
0x180005a6c  test    eax, eax
0x180005a6e  jns     short loc_180005ABA
0x180005a70  mov     rcx, [rsp+28h]; this
0x180005a75  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005a7c  mov     r9d, eax; char *
0x180005a7f  mov     edx, 0B2h; void *
0x180005a84  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a90  lea     rax, WPP_GLOBAL_Control
0x180005a97  cmp     rcx, rax
0x180005a9a  jz      short loc_180005ABA
0x180005a9c  test    byte ptr [rcx+1Ch], 80h
0x180005aa0  jz      short loc_180005ABA
0x180005aa2  mov     rcx, [rcx+10h]
0x180005aa6  lea     r8, WPP_3a96b840b9793ae967b06867319dff15_Traceguids
0x180005aad  mov     edx, 0Dh
0x180005ab2  mov     r9d, ebx
0x180005ab5  call    WPP_SF_D
0x180005aba  mov     rax, [rdi]
0x180005abd  mov     rcx, rdi
0x180005ac0  mov     rax, [rax+10h]
0x180005ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac9  jmp     loc_180005B64
0x180005ace  mov     rcx, [rsp+28h]; this
0x180005ad3  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005ada  mov     ebx, 8007000Eh
0x180005adf  mov     edx, 0AFh; void *
0x180005ae4  mov     r9d, ebx; char *
0x180005ae7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180005af3  lea     rax, WPP_GLOBAL_Control
0x180005afa  cmp     rcx, rax
0x180005afd  jz      short loc_180005B64
0x180005aff  test    byte ptr [rcx+1Ch], 80h
0x180005b03  jz      short loc_180005B64
0x180005b05  mov     edx, 0Ch
0x180005b0a  mov     r9d, 8007000Eh
0x180005b10  jmp     short loc_180005B54
0x180005b12  mov     rcx, [rsp+28h]; this
0x180005b17  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005b1e  mov     ebx, 80040111h
0x180005b23  mov     edx, 0B5h; void *
0x180005b28  mov     r9d, ebx; char *
0x180005b2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b37  lea     rax, WPP_GLOBAL_Control
0x180005b3e  cmp     rcx, rax
0x180005b41  jz      short loc_180005B64
0x180005b43  test    byte ptr [rcx+1Ch], 80h
0x180005b47  jz      short loc_180005B64
0x180005b49  mov     edx, 0Eh
0x180005b4e  mov     r9d, 80040111h
0x180005b54  mov     rcx, [rcx+10h]
0x180005b58  lea     r8, WPP_3a96b840b9793ae967b06867319dff15_Traceguids
0x180005b5f  call    WPP_SF_D
0x180005b64  mov     rsi, [rsp+28h+arg_8]
0x180005b69  mov     eax, ebx
0x180005b6b  mov     rbx, [rsp+28h+arg_0]
0x180005b70  add     rsp, 20h
0x180005b74  pop     rdi
0x180005b75  retn
```

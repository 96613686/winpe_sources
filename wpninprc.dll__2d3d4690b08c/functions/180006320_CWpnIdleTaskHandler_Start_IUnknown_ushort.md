# CWpnIdleTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x180006320`
- end: `0x180006552`
- name: `?Start@CWpnIdleTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `562`
- prototype: `__int64 __fastcall(CWpnIdleTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000593c`
- `0x180005f3c`
- `0x180006320`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800063c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800063c9`

## string_xrefs

- `0x180006356`: `onecoreuap\base\diagnosis\platform\notifications\inproc\idletask\wpnidletaskhandler.cpp`
- `0x1800063d9`: `onecoreuap\base\diagnosis\platform\notifications\inproc\idletask\wpnidletaskhandler.cpp`
- `0x180006439`: `onecoreuap\base\diagnosis\platform\notifications\inproc\idletask\wpnidletaskhandler.cpp`
- `0x1800064a8`: `onecoreuap\base\diagnosis\platform\notifications\inproc\idletask\wpnidletaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandler::Start(CWpnIdleTaskHandler *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  HRESULT v8; // eax
  int v9; // eax
  int v10; // eax
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 v16; // [rsp+58h] [rbp+18h] BYREF
  LPVOID v17; // [rsp+68h] [rbp+28h] BYREF

  v17 = 0;
  v16 = 0;
  v14 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\idletask\\wpnidletaskhandler.cpp",
      (const char *)0x80070057LL,
      ppv);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v6 = 10;
      v7 = 2147942487LL;
LABEL_5:
      WPP_SF_D(v5[2], v6, WPP_aab964af9582394b9cffffcc869db8a6_Traceguids, v7);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  v8 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         0x15u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &v17);
  v4 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\idletask\\wpnidletaskhandler.cpp",
      (const char *)(unsigned int)v8,
      ppva);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_20;
    v6 = 11;
    goto LABEL_10;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v17 + 56LL))(v17, &v16);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\idletask\\wpnidletaskhandler.cpp",
      (const char *)(unsigned int)v9,
      ppva);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_20;
    v6 = 12;
LABEL_10:
    v7 = v4;
    goto LABEL_5;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
          a2,
          &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
          &v14);
  v4 = v10;
  if ( v10 >= 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 32LL))(v14, (unsigned int)v10);
    goto LABEL_20;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x75,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\idletask\\wpnidletaskhandler.cpp",
    (const char *)(unsigned int)v10,
    ppva);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v6 = 14;
    goto LABEL_10;
  }
LABEL_20:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return v4;
}

```

## disassembly

```asm
0x180006320  mov     [rsp-8+arg_0], rbx
0x180006325  mov     [rsp-8+arg_10], rdi
0x18000632a  push    rbp
0x18000632b  mov     rbp, rsp
0x18000632e  sub     rsp, 40h
0x180006332  mov     [rbp+arg_18], 0
0x18000633a  mov     rdi, rdx
0x18000633d  mov     [rbp+arg_8], 0
0x180006345  mov     [rbp+var_10], 0
0x18000634d  test    rdx, rdx
0x180006350  jnz     short loc_1800063AC
0x180006352  mov     rcx, [rbp+8]; this
0x180006356  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000635d  mov     ebx, 80070057h
0x180006362  lea     edx, [rdi+64h]; void *
0x180006365  mov     r9d, ebx; char *
0x180006368  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000636d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006374  lea     rax, WPP_GLOBAL_Control
0x18000637b  cmp     rcx, rax
0x18000637e  jz      loc_1800064F1
0x180006384  test    byte ptr [rcx+1Ch], 80h
0x180006388  jz      loc_1800064F1
0x18000638e  lea     edx, [rdi+0Ah]
0x180006391  mov     r9d, 80070057h
0x180006397  mov     rcx, [rcx+10h]
0x18000639b  lea     r8, WPP_aab964af9582394b9cffffcc869db8a6_Traceguids
0x1800063a2  call    WPP_SF_D
0x1800063a7  jmp     loc_1800064F1
0x1800063ac  xor     edx, edx; pUnkOuter
0x1800063ae  lea     rax, [rbp+arg_18]
0x1800063b2  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800063b9  mov     qword ptr [rsp+40h+ppv], rax; int
0x1800063be  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x1800063c5  lea     r8d, [rdx+15h]; dwClsContext
0x1800063c9  call    cs:__imp_CoCreateInstance
0x1800063cf  mov     ebx, eax
0x1800063d1  test    eax, eax
0x1800063d3  jns     short loc_18000641B
0x1800063d5  mov     rcx, [rbp+8]; this
0x1800063d9  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800063e0  mov     r9d, eax; char *
0x1800063e3  mov     edx, 6Ch ; 'l'; void *
0x1800063e8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800063ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063f4  lea     rax, WPP_GLOBAL_Control
0x1800063fb  cmp     rcx, rax
0x1800063fe  jz      loc_1800064F1
0x180006404  test    byte ptr [rcx+1Ch], 80h
0x180006408  jz      loc_1800064F1
0x18000640e  mov     edx, 0Bh
0x180006413  mov     r9d, ebx
0x180006416  jmp     loc_180006397
0x18000641b  mov     rcx, [rbp+arg_18]
0x18000641f  lea     rdx, [rbp+arg_8]
0x180006423  mov     rax, [rcx]
0x180006426  mov     rax, [rax+38h]
0x18000642a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642f  mov     ebx, eax
0x180006431  test    eax, eax
0x180006433  jns     short loc_180006475
0x180006435  mov     rcx, [rbp+8]; this
0x180006439  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006440  mov     r9d, eax; char *
0x180006443  mov     edx, 6Fh ; 'o'; void *
0x180006448  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000644d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006454  lea     rax, WPP_GLOBAL_Control
0x18000645b  cmp     rcx, rax
0x18000645e  jz      loc_1800064F1
0x180006464  test    byte ptr [rcx+1Ch], 80h
0x180006468  jz      loc_1800064F1
0x18000646e  mov     edx, 0Ch
0x180006473  jmp     short loc_180006413
0x180006475  mov     rcx, [rbp+arg_8]
0x180006479  mov     rax, [rcx]
0x18000647c  mov     rax, [rax+18h]
0x180006480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006485  mov     rax, [rdi]
0x180006488  lea     r8, [rbp+var_10]
0x18000648c  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180006493  mov     rcx, rdi
0x180006496  mov     rax, [rax]
0x180006499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000649e  mov     ebx, eax
0x1800064a0  test    eax, eax
0x1800064a2  jns     short loc_1800064DF
0x1800064a4  mov     rcx, [rbp+8]; this
0x1800064a8  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800064af  mov     r9d, eax; char *
0x1800064b2  mov     edx, 75h ; 'u'; void *
0x1800064b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800064bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064c3  lea     rax, WPP_GLOBAL_Control
0x1800064ca  cmp     rcx, rax
0x1800064cd  jz      short loc_1800064F1
0x1800064cf  test    byte ptr [rcx+1Ch], 80h
0x1800064d3  jz      short loc_1800064F1
0x1800064d5  mov     edx, 0Eh
0x1800064da  jmp     loc_180006413
0x1800064df  mov     rcx, [rbp+var_10]
0x1800064e3  mov     edx, ebx
0x1800064e5  mov     rax, [rcx]
0x1800064e8  mov     rax, [rax+20h]
0x1800064ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064f1  mov     rcx, [rbp+arg_8]
0x1800064f5  test    rcx, rcx
0x1800064f8  jz      short loc_18000650E
0x1800064fa  mov     rax, [rcx]
0x1800064fd  mov     rax, [rax+10h]
0x180006501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006506  mov     [rbp+arg_8], 0
0x18000650e  mov     rcx, [rbp+arg_18]
0x180006512  test    rcx, rcx
0x180006515  jz      short loc_18000652B
0x180006517  mov     rax, [rcx]
0x18000651a  mov     rax, [rax+10h]
0x18000651e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006523  mov     [rbp+arg_18], 0
0x18000652b  mov     rcx, [rbp+var_10]
0x18000652f  test    rcx, rcx
0x180006532  jz      short loc_180006540
0x180006534  mov     rax, [rcx]
0x180006537  mov     rax, [rax+10h]
0x18000653b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006540  mov     rdi, [rsp+40h+arg_10]
0x180006545  mov     eax, ebx
0x180006547  mov     rbx, [rsp+40h+arg_0]
0x18000654c  add     rsp, 40h
0x180006550  pop     rbp
0x180006551  retn
```

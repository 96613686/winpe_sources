# wil::details::functor_wrapper_void__lambda_1e07142daacc5b73b84cb89898de8e97___::Run

- ea: `0x180025930`
- end: `0x180025acb`
- name: `wil::details::functor_wrapper_void__lambda_1e07142daacc5b73b84cb89898de8e97___::Run`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002414c`

## callees

- `0x18000bf4c`
- `0x180024490`
- `0x180024878`
- `0x180025930`
- `0x180026538`
- `0x180033010`

## string_xrefs

- `0x180025aa4`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180025ab9`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::details::functor_wrapper_void__lambda_1e07142daacc5b73b84cb89898de8e97___::Run(__int64 a1)
{
  __int64 *v1; // rdi
  __int64 v2; // rax
  int v3; // eax
  DWORD v4; // edx
  int v5; // r8d
  __int64 v6; // rbx
  int v7; // eax
  __int64 v8; // rcx
  TetheringServiceTelemetry *v9; // rcx
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v14; // [rsp+30h] [rbp+8h] BYREF
  __int64 v15; // [rsp+38h] [rbp+10h] BYREF

  v1 = *(__int64 **)(a1 + 8);
  v2 = *v1;
  v15 = 0;
  v3 =  Windows::Devices::Radios::IRadioStatics::`vcall'{48,{flat}}(*(_QWORD *)(v2 + 48), 1, &v15);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x735,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v3,
      v12);
  v6 = v15;
  v14 = 0;
  v7 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus> *>(
         v15,
         v4,
         v5);
  if ( v7 >= 0 )
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 64LL))(v6, &v14);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v7,
      v12);
  v8 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( v14 )
  {
    switch ( v14 )
    {
      case 1:
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids);
        }
        *(_DWORD *)(*v1 + 8) = 4;
        break;
      case 2:
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v10 = 17;
          goto LABEL_24;
        }
        break;
      case 3:
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v10 = 18;
LABEL_24:
          WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids);
        }
        break;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v10 = 15;
      goto LABEL_24;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180025930  mov     [rsp+arg_10], rbx
0x180025935  push    rdi; int
0x180025936  sub     rsp, 20h
0x18002593a  mov     rdi, [rcx+8]
0x18002593e  mov     rax, [rdi]
0x180025941  mov     [rsp+28h+arg_8], 0
0x18002594a  lea     r8, [rsp+28h+arg_8]
0x18002594f  mov     edx, 1
0x180025954  mov     rcx, [rax+30h]
0x180025958  call    ??_9IRadioStatics@Radios@Devices@Windows@@$BDA@AA; [thunk]: Windows::Devices::Radios::IRadioStatics::`vcall'{48,{flat}}
0x18002595d  mov     rcx, [rsp+28h]; this
0x180025962  test    eax, eax
0x180025964  js      loc_180025AB6
0x18002596a  mov     rbx, [rsp+28h+arg_8]
0x18002596f  mov     [rsp+28h+arg_0], 0
0x180025977  mov     rcx, rbx
0x18002597a  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18002597f  test    eax, eax
0x180025981  js      short loc_180025998
0x180025983  mov     rax, [rbx]
0x180025986  lea     rdx, [rsp+28h+arg_0]
0x18002598b  mov     rcx, rbx
0x18002598e  mov     rax, [rax+40h]
0x180025992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025997  nop
0x180025998  mov     rcx, [rsp+28h]; this
0x18002599d  test    eax, eax
0x18002599f  js      loc_180025AA1
0x1800259a5  mov     rcx, [rsp+28h+arg_8]
0x1800259aa  test    rcx, rcx
0x1800259ad  jz      short loc_1800259C5
0x1800259af  mov     [rsp+28h+arg_8], 0
0x1800259b8  mov     rax, [rcx]
0x1800259bb  mov     rax, [rax+10h]
0x1800259bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259c4  nop
0x1800259c5  mov     eax, [rsp+28h+arg_0]
0x1800259c9  test    eax, eax
0x1800259cb  jz      loc_180025A66
0x1800259d1  sub     eax, 1
0x1800259d4  jz      short loc_180025A2C
0x1800259d6  sub     eax, 1
0x1800259d9  jz      short loc_180025A0C
0x1800259db  cmp     eax, 1
0x1800259de  jnz     loc_180025A94
0x1800259e4  lea     rax, WPP_GLOBAL_Control
0x1800259eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259f2  cmp     rcx, rax
0x1800259f5  jz      loc_180025A94
0x1800259fb  test    byte ptr [rcx+1Ch], 4
0x1800259ff  jz      loc_180025A94
0x180025a05  mov     edx, 12h
0x180025a0a  jmp     short loc_180025A84
0x180025a0c  lea     rax, WPP_GLOBAL_Control
0x180025a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a1a  cmp     rcx, rax
0x180025a1d  jz      short loc_180025A94
0x180025a1f  test    byte ptr [rcx+1Ch], 4
0x180025a23  jz      short loc_180025A94
0x180025a25  mov     edx, 11h
0x180025a2a  jmp     short loc_180025A84
0x180025a2c  lea     rax, WPP_GLOBAL_Control
0x180025a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a3a  cmp     rcx, rax
0x180025a3d  jz      short loc_180025A5A
0x180025a3f  test    byte ptr [rcx+1Ch], 4
0x180025a43  jz      short loc_180025A5A
0x180025a45  mov     edx, 10h
0x180025a4a  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x180025a51  mov     rcx, [rcx+10h]
0x180025a55  call    WPP_SF_
0x180025a5a  mov     rax, [rdi]
0x180025a5d  mov     dword ptr [rax+8], 4
0x180025a64  jmp     short loc_180025A94
0x180025a66  lea     rax, WPP_GLOBAL_Control
0x180025a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a74  cmp     rcx, rax
0x180025a77  jz      short loc_180025A94
0x180025a79  test    byte ptr [rcx+1Ch], 4
0x180025a7d  jz      short loc_180025A94
0x180025a7f  mov     edx, 0Fh
0x180025a84  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x180025a8b  mov     rcx, [rcx+10h]
0x180025a8f  call    WPP_SF_
0x180025a94  xor     eax, eax
0x180025a96  mov     rbx, [rsp+28h+arg_10]
0x180025a9b  add     rsp, 20h
0x180025a9f  pop     rdi
0x180025aa0  retn
0x180025aa1  mov     r9d, eax; char *
0x180025aa4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025aab  mov     edx, 71Bh; void *
0x180025ab0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025ab6  mov     r9d, eax; char *
0x180025ab9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025ac0  mov     edx, 735h; void *
0x180025ac5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

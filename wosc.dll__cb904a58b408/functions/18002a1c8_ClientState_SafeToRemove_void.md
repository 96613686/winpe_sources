# ClientState::SafeToRemove(void)

- ea: `0x18002a1c8`
- end: `0x18002a306`
- name: `?SafeToRemove@ClientState@@QEAA_NXZ`
- size: `318`
- prototype: `bool __fastcall(ClientState *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180026b20`

## callees

- `0x18000fe24`
- `0x1800101fc`
- `0x180021f1c`
- `0x180024cd0`
- `0x18002a1c8`
- `0x18002bd0c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a208`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a208`

## string_xrefs

- `0x18002a26a`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ClientState::SafeToRemove(ClientState *this)
{
  void (__fastcall ***v2)(_QWORD, _QWORD); // rcx
  _WORD *v3; // rax
  _WORD *v4; // rax
  int v5; // eax
  _WORD *v6; // rax
  __int64 TypeFromJson; // rax
  const char *v8; // r9
  const char *v9; // r9
  int v11; // [rsp+20h] [rbp-38h]
  std::_Ref_count_base *v12[2]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v13[8]; // [rsp+40h] [rbp-18h] BYREF
  std::_Ref_count_base *v14; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !*((_QWORD *)this + 9) )
    return 1;
  v2 = (void (__fastcall ***)(_QWORD, _QWORD))*((_QWORD *)this + 36);
  if ( v2 )
  {
    (**v2)(v2, 0);
    RegDeleteValueW(*((HKEY *)this + 52), L"LastPayload");
  }
  v3 = (_WORD *)*((_QWORD *)this + 46);
  if ( !v3 || !*v3 )
    return 1;
  v4 = (_WORD *)*((_QWORD *)this + 9);
  if ( v4 )
  {
    if ( *v4 )
    {
      v5 = RegValet::SetValue::_Set(*((HKEY *)this + 52), L"ETag", 1u, &String1, 2u);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
          (const char *)(unsigned int)v5,
          v11);
    }
  }
  v6 = (_WORD *)*((_QWORD *)this + 20);
  if ( v6 )
  {
    if ( !*v6 )
      return 1;
  }
  *(_OWORD *)v12 = 0;
  try
  {
    TypeFromJson = ClientState::MakeTypeFromJsonString<INotificationType>((__int64)v13, *((const WCHAR **)this + 46));
    std::shared_ptr<CnsFlightState>::operator=(v12, TypeFromJson);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      v8);
    if ( v12[1] )
      std::_Ref_count_base::_Decref(v12[1]);
    return 1;
  }
  try
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v12[0])(v12[0]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      v9);
  }
  if ( v12[1] )
    std::_Ref_count_base::_Decref(v12[1]);
  return 0;
}

```

## disassembly

```asm
0x18002a1c8  mov     [rsp+arg_0], rbx
0x18002a1cd  push    rdi
0x18002a1ce  sub     rsp, 50h
0x18002a1d2  mov     rdi, rcx
0x18002a1d5  xor     ebx, ebx
0x18002a1d7  cmp     [rcx+48h], rbx
0x18002a1db  jz      loc_18002A2F9
0x18002a1e1  mov     rcx, [rcx+120h]
0x18002a1e8  test    rcx, rcx
0x18002a1eb  jz      short loc_18002A20E
0x18002a1ed  mov     rax, [rcx]
0x18002a1f0  xor     edx, edx
0x18002a1f2  mov     rax, [rax]
0x18002a1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1fa  lea     rdx, ?c_regvalLastPayload@ClientState@@0QBGB; "LastPayload"
0x18002a201  mov     rcx, [rdi+1A0h]; hKey
0x18002a208  call    cs:__imp_RegDeleteValueW
0x18002a20e  mov     rax, [rdi+170h]
0x18002a215  test    rax, rax
0x18002a218  jz      loc_18002A2F9
0x18002a21e  cmp     [rax], bx
0x18002a221  jz      loc_18002A2F9
0x18002a227  mov     rax, [rdi+48h]
0x18002a22b  test    rax, rax
0x18002a22e  jz      short loc_18002A27C
0x18002a230  cmp     [rax], bx
0x18002a233  jz      short loc_18002A27C
0x18002a235  mov     qword ptr [rsp+58h+var_38], 2; int
0x18002a23e  lea     r9, String1; void *
0x18002a245  mov     r8d, 1; unsigned int
0x18002a24b  lea     rdx, ?c_regvalETag@ClientState@@0QBGB; "ETag"
0x18002a252  mov     rcx, [rdi+1A0h]; HKEY
0x18002a259  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002a25e  mov     rcx, [rsp+58h]; this
0x18002a263  test    eax, eax
0x18002a265  jns     short loc_18002A27C
0x18002a267  mov     r9d, eax; char *
0x18002a26a  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a271  mov     edx, 10Ch; void *
0x18002a276  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a27c  mov     rax, [rdi+0A0h]
0x18002a283  test    rax, rax
0x18002a286  jz      short loc_18002A28D
0x18002a288  cmp     [rax], bx
0x18002a28b  jz      short loc_18002A2F9
0x18002a28d  xorps   xmm0, xmm0
0x18002a290  movdqu  xmmword ptr [rsp+58h+var_28], xmm0
0x18002a296  mov     rdx, [rdi+170h]
0x18002a29d  lea     rcx, [rsp+58h+var_18]
0x18002a2a2  call    ??$MakeTypeFromJsonString@VINotificationType@@@ClientState@@CA?AV?$shared_ptr@VINotificationType@@@std@@PEBGP6A?AV12@PEAUIJsonObject@Json@Data@Windows@@@Z@Z; ClientState::MakeTypeFromJsonString<INotificationType>(ushort const *,std::shared_ptr<INotificationType> (*)(Windows::Data::Json::IJsonObject *))
0x18002a2a7  mov     rdx, rax
0x18002a2aa  lea     rcx, [rsp+58h+var_28]
0x18002a2af  call    ??4?$shared_ptr@UCnsFlightState@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CnsFlightState>::operator=(std::shared_ptr<CnsFlightState> &&)
0x18002a2b4  mov     rcx, [rsp+58h+var_10]; this
0x18002a2b9  test    rcx, rcx
0x18002a2bc  jz      short loc_18002A2C4
0x18002a2be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a2c3  nop
0x18002a2c4  mov     rcx, [rsp+58h+var_28]
0x18002a2c9  mov     rax, [rcx]
0x18002a2cc  mov     rax, [rax]
0x18002a2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2d4  nop
0x18002a2d5  jmp     short $+2
0x18002a2d7  mov     rcx, [rsp+58h+var_28+8]; this
0x18002a2dc  test    rcx, rcx
0x18002a2df  jz      short loc_18002A2E6
0x18002a2e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a2e6  xor     al, al
0x18002a2e8  jmp     short loc_18002A2FB
0x18002a2ea  mov     rcx, [rsp+58h+var_28+8]; this
0x18002a2ef  test    rcx, rcx
0x18002a2f2  jz      short loc_18002A2F9
0x18002a2f4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a2f9  mov     al, 1
0x18002a2fb  mov     rbx, [rsp+58h+arg_0]
0x18002a300  add     rsp, 50h
0x18002a304  pop     rdi
0x18002a305  retn
```

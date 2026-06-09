# CJsonParser::Initialize(ushort const *)

- ea: `0x180019238`
- end: `0x1800193f4`
- name: `?Initialize@CJsonParser@@QEAAJPEBG@Z`
- size: `444`
- prototype: `__int64 __fastcall(CJsonParser *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d620`

## callees

- `0x18000c1d4`
- `0x180019238`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800192c1`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800192c1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001932a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001932a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800192f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001938a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800192f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001938a`

## string_xrefs

- `0x1800192ea`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall CJsonParser::Initialize(CJsonParser *this, const unsigned __int16 *a2)
{
  int ActivationFactory; // ebx
  _QWORD *v5; // rcx
  int v7; // edi
  int v8; // eax
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  _QWORD *v12; // rcx
  HSTRING v13; // rbx
  unsigned int v14; // r8d
  _QWORD *v15; // rbx
  _QWORD *v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // r15
  unsigned __int64 v19; // rdx
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  _BYTE v23[8]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF

  v24 = 0;
  v23[0] = 0;
  if ( !a2 )
  {
    ActivationFactory = -2147024809;
    goto LABEL_3;
  }
  v7 = 1;
  v8 = RoInitialize(1);
  ActivationFactory = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147417850 )
      goto LABEL_3;
    v7 = 0;
  }
  *(_DWORD *)this = v7;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    __debugbreak();
  }
  v12 = v24;
  v13 = string;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
  }
  ActivationFactory = RoGetActivationFactory(v13, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v24);
  if ( ActivationFactory >= 0 )
  {
    v15 = v24;
    v16 = (_QWORD *)((char *)this + 8);
    v17 = *((_QWORD *)this + 1);
    v18 = *v24;
    if ( v17 )
    {
      *v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    string = 0;
    v19 = -1;
    do
      ++v19;
    while ( a2[v19] );
    if ( v19 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v19, v14);
      __debugbreak();
    }
    if ( (int)v19 + 1 < (unsigned int)v19 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v19, v14);
      JUMPOUT(0x1800193F3LL);
    }
    v20 = WindowsCreateStringReference(a2, v19, &hstringHeader, &string);
    if ( v20 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
      __debugbreak();
    }
    ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, char *, _BYTE *))(v18 + 56))(
                          v15,
                          string,
                          (char *)this + 8,
                          v23);
    if ( ActivationFactory >= 0 && (!v23[0] || !*v16) )
      ActivationFactory = -2147467259;
  }
LABEL_3:
  v5 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180019238  mov     [rsp-28h+arg_10], rbx
0x18001923d  mov     [rsp-28h+arg_18], rsi
0x180019242  push    rbp
0x180019243  push    rdi
0x180019244  push    r12
0x180019246  push    r14
0x180019248  push    r15
0x18001924a  mov     rbp, rsp
0x18001924d  sub     rsp, 70h
0x180019251  mov     rax, cs:__security_cookie
0x180019258  xor     rax, rsp
0x18001925b  mov     [rbp+var_10], rax
0x18001925f  xor     r12d, r12d
0x180019262  mov     r14, rdx
0x180019265  mov     [rbp+var_38], r12
0x180019269  mov     rsi, rcx
0x18001926c  mov     [rbp+var_40], r12b
0x180019270  test    rdx, rdx
0x180019273  jnz     short loc_1800192BA
0x180019275  mov     ebx, 80070057h
0x18001927a  mov     rcx, [rbp+var_38]
0x18001927e  test    rcx, rcx
0x180019281  jz      short loc_180019293
0x180019283  mov     [rbp+var_38], r12
0x180019287  mov     rax, [rcx]
0x18001928a  mov     rax, [rax+10h]
0x18001928e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019293  mov     eax, ebx
0x180019295  mov     rcx, [rbp+var_10]
0x180019299  xor     rcx, rsp; StackCookie
0x18001929c  call    __security_check_cookie
0x1800192a1  lea     r11, [rsp+70h+var_s0]
0x1800192a6  mov     rbx, [r11+40h]
0x1800192aa  mov     rsi, [r11+48h]
0x1800192ae  mov     rsp, r11
0x1800192b1  pop     r15
0x1800192b3  pop     r14
0x1800192b5  pop     r12
0x1800192b7  pop     rdi
0x1800192b8  pop     rbp
0x1800192b9  retn
0x1800192ba  mov     edi, 1
0x1800192bf  mov     ecx, edi
0x1800192c1  call    cs:__imp_RoInitialize
0x1800192c7  mov     ebx, eax
0x1800192c9  test    eax, eax
0x1800192cb  jns     short loc_1800192D7
0x1800192cd  cmp     eax, 80010106h
0x1800192d2  jnz     short loc_18001927A
0x1800192d4  mov     edi, r12d
0x1800192d7  mov     [rsi], edi
0x1800192d9  lea     r9, [rbp+string]; string
0x1800192dd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800192e1  mov     [rbp+string], r12
0x1800192e5  mov     edx, 1Ch; length
0x1800192ea  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800192f1  call    cs:__imp_WindowsCreateStringReference
0x1800192f7  test    eax, eax
0x1800192f9  js      loc_1800193E1
0x1800192ff  mov     rcx, [rbp+var_38]
0x180019303  mov     rbx, [rbp+string]
0x180019307  test    rcx, rcx
0x18001930a  jz      short loc_18001931C
0x18001930c  mov     [rbp+var_38], r12
0x180019310  mov     rax, [rcx]
0x180019313  mov     rax, [rax+10h]
0x180019317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001931c  lea     r8, [rbp+var_38]
0x180019320  mov     rcx, rbx
0x180019323  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18001932a  call    cs:__imp_RoGetActivationFactory
0x180019330  mov     ebx, eax
0x180019332  test    eax, eax
0x180019334  js      loc_18001927A
0x18001933a  mov     rbx, [rbp+var_38]
0x18001933e  lea     rdi, [rsi+8]
0x180019342  mov     rcx, [rdi]
0x180019345  mov     r15, [rbx]
0x180019348  test    rcx, rcx
0x18001934b  jz      short loc_18001935C
0x18001934d  mov     [rdi], r12
0x180019350  mov     rax, [rcx]
0x180019353  mov     rax, [rax+10h]
0x180019357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001935c  mov     [rbp+string], r12
0x180019360  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019364  inc     rdx; int
0x180019367  cmp     [r14+rdx*2], r12w
0x18001936c  jnz     short loc_180019364
0x18001936e  mov     eax, 0FFFFFFFFh
0x180019373  cmp     rdx, rax
0x180019376  ja      short loc_1800193D6
0x180019378  lea     eax, [rdx+1]
0x18001937b  cmp     eax, edx
0x18001937d  jb      short loc_1800193E9
0x18001937f  lea     r9, [rbp+string]; string
0x180019383  mov     rcx, r14; sourceString
0x180019386  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001938a  call    cs:__imp_WindowsCreateStringReference
0x180019390  test    eax, eax
0x180019392  js      short loc_1800193CE
0x180019394  mov     rdx, [rbp+string]
0x180019398  lea     r9, [rbp+var_40]
0x18001939c  mov     rax, [r15+38h]
0x1800193a0  mov     r8, rdi
0x1800193a3  mov     rcx, rbx
0x1800193a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193ab  mov     ebx, eax
0x1800193ad  test    eax, eax
0x1800193af  js      loc_18001927A
0x1800193b5  cmp     [rbp+var_40], r12b
0x1800193b9  jz      short loc_1800193C4
0x1800193bb  cmp     [rdi], r12
0x1800193be  jnz     loc_18001927A
0x1800193c4  mov     ebx, 80004005h
0x1800193c9  jmp     loc_18001927A
0x1800193ce  mov     ecx, eax; this
0x1800193d0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800193d5  int     3; Trap to Debugger
0x1800193d6  mov     ecx, 80070216h; this
0x1800193db  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800193e0  int     3; Trap to Debugger
0x1800193e1  mov     ecx, eax; this
0x1800193e3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800193e8  int     3; Trap to Debugger
0x1800193e9  mov     ecx, 80070216h; this
0x1800193ee  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

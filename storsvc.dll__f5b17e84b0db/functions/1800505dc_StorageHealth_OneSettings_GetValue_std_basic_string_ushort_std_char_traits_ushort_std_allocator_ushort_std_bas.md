# StorageHealth::OneSettings::GetValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800505dc`
- end: `0x180050773`
- name: `?GetValue@OneSettings@StorageHealth@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z`
- size: `407`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004f390`
- `0x18004fdf8`

## callees

- `0x18000d030`
- `0x18000d400`
- `0x18000d5a4`
- `0x180012734`
- `0x180012c9c`
- `0x18001c130`
- `0x18001c208`
- `0x18002ce80`
- `0x1800503b8`
- `0x1800505dc`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr_s` at `0x1800506bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr_s` at `0x1800506bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800506e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800506e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050722`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StorageHealth::OneSettings::GetValue(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rax
  wchar_t *v9; // r14
  const wchar_t *v10; // rax
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v14; // rax
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v18[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v18[1] = a2;
  LODWORD(v18[0]) = 0;
  if ( *(_QWORD *)(a1 + 288) )
  {
    string = 0;
    v7 = *(_QWORD *)(a2 + 16) + 1LL;
    v8 = 2 * v7;
    if ( !is_mul_ok(v7, 2u) )
      v8 = -1;
    v9 = (wchar_t *)operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
    v18[0] = v9;
    if ( v9 )
    {
      v10 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v6 = StringCchCopyW(v9, v7, v10);
      if ( v6 >= 0 )
      {
        if ( (unsigned int)_o__wcsupr_s(v9, v7) )
        {
          v6 = -2147418113;
        }
        else
        {
          v12 = *(_QWORD *)(a1 + 288);
          v13 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v12 + 80LL);
          WindowsDeleteString(string);
          string = 0;
          v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v19, v18);
          LODWORD(v18[0]) = 1;
          v6 = v13(v12, *(_QWORD *)(v14 + 24), &string);
        }
        if ( v6 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          std::wstring::assign(a3, StringRawBuffer);
        }
      }
      operator delete(v9, v11);
    }
    else
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagehealth\\onesettings.cpp",
        (const char *)0x8007000ELL,
        (int)string);
    }
    WindowsDeleteString(string);
    string = 0;
  }
  else
  {
    v6 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagehealth\\onesettings.cpp",
      (const char *)0x8000FFFFLL,
      (int)string);
  }
  std::wstring::_Tidy_deallocate(a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800505dc  push    rbp
0x1800505de  push    rbx
0x1800505df  push    rsi
0x1800505e0  push    rdi
0x1800505e1  push    r12
0x1800505e3  push    r14
0x1800505e5  push    r15
0x1800505e7  mov     rbp, rsp
0x1800505ea  sub     rsp, 60h
0x1800505ee  mov     rax, cs:__security_cookie
0x1800505f5  xor     rax, rsp
0x1800505f8  mov     [rbp+var_8], rax
0x1800505fc  mov     r12, r8
0x1800505ff  mov     rsi, rdx
0x180050602  mov     r15, rcx
0x180050605  mov     [rbp+var_30], rdx
0x180050609  mov     dword ptr [rbp+var_38], 0
0x180050610  cmp     qword ptr [rcx+120h], 0
0x180050618  jnz     short loc_18005063C
0x18005061a  mov     rcx, [rbp+38h]; this
0x18005061e  mov     ebx, 8000FFFFh
0x180050623  mov     r9d, ebx; char *
0x180050626  lea     r8, aOnecoreDrivers_29; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18005062d  mov     edx, 0FDh; void *
0x180050632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050637  jmp     loc_18005074E
0x18005063c  mov     [rbp+string], 0
0x180050644  mov     rdi, [rdx+10h]
0x180050648  inc     rdi
0x18005064b  mov     eax, 2
0x180050650  mul     rdi
0x180050653  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005065a  cmovb   rax, rcx
0x18005065e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180050665  mov     rcx, rax; unsigned __int64
0x180050668  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005066d  mov     r14, rax
0x180050670  mov     [rbp+var_38], rax
0x180050674  test    rax, rax
0x180050677  jnz     short loc_18005069B
0x180050679  mov     rcx, [rbp+38h]; this
0x18005067d  mov     ebx, 8007000Eh
0x180050682  mov     r9d, ebx; char *
0x180050685  lea     r8, aOnecoreDrivers_29; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18005068c  mov     edx, 105h; void *
0x180050691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050696  jmp     loc_18005073C
0x18005069b  mov     rcx, rsi
0x18005069e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800506a3  mov     r8, rax; wchar_t *
0x1800506a6  mov     rdx, rdi; unsigned __int64
0x1800506a9  mov     rcx, r14; wchar_t *
0x1800506ac  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800506b1  mov     ebx, eax
0x1800506b3  test    eax, eax
0x1800506b5  js      short loc_180050733
0x1800506b7  mov     rdx, rdi
0x1800506ba  mov     rcx, r14
0x1800506bd  call    cs:__imp__o__wcsupr_s
0x1800506c3  test    eax, eax
0x1800506c5  jz      short loc_1800506CE
0x1800506c7  mov     ebx, 8000FFFFh
0x1800506cc  jmp     short loc_180050718
0x1800506ce  mov     rdi, [r15+120h]
0x1800506d5  mov     rax, [rdi]
0x1800506d8  mov     rbx, [rax+50h]
0x1800506dc  mov     rcx, [rbp+string]; string
0x1800506e0  call    cs:__imp_WindowsDeleteString
0x1800506e6  mov     [rbp+string], 0
0x1800506ee  lea     rdx, [rbp+var_38]
0x1800506f2  lea     rcx, [rbp+var_28]
0x1800506f6  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800506fb  nop
0x1800506fc  mov     dword ptr [rbp+var_38], 1
0x180050703  lea     r8, [rbp+string]
0x180050707  mov     rdx, [rax+18h]
0x18005070b  mov     rcx, rdi
0x18005070e  mov     rax, rbx
0x180050711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050716  mov     ebx, eax
0x180050718  test    ebx, ebx
0x18005071a  js      short loc_180050733
0x18005071c  xor     edx, edx; length
0x18005071e  mov     rcx, [rbp+string]; string
0x180050722  call    cs:__imp_WindowsGetStringRawBuffer
0x180050728  mov     rdx, rax
0x18005072b  mov     rcx, r12
0x18005072e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180050733  mov     rcx, r14; void *
0x180050736  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005073b  nop
0x18005073c  mov     rcx, [rbp+string]; string
0x180050740  call    cs:__imp_WindowsDeleteString
0x180050746  mov     [rbp+string], 0
0x18005074e  mov     rcx, rsi
0x180050751  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050756  mov     eax, ebx
0x180050758  mov     rcx, [rbp+var_8]
0x18005075c  xor     rcx, rsp; StackCookie
0x18005075f  call    __security_check_cookie
0x180050764  add     rsp, 60h
0x180050768  pop     r15
0x18005076a  pop     r14
0x18005076c  pop     r12
0x18005076e  pop     rdi
0x18005076f  pop     rsi
0x180050770  pop     rbx
0x180050771  pop     rbp
0x180050772  retn
```

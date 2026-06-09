# GetCurrentUserSidString

- ea: `0x1801195e0`
- end: `0x1801197b4`
- name: `GetCurrentUserSidString`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180118d80`

## callees

- `0x180035c40`
- `0x180042d18`
- `0x1801195e0`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801196c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801196eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801196c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801196eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801196f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801196f9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180119638`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180119638`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSidString(__int64 a1)
{
  int ActivationFactory; // ebx
  __int64 v3; // rdx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-40h] BYREF
  __int64 v15; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]

  v14 = 0;
  v18 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.User",
    0x26u,
    0x25u);
  ActivationFactory = RoGetActivationFactory(v18, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v14);
  if ( ActivationFactory < 0 )
  {
    v3 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
    return (unsigned int)ActivationFactory;
  }
  v15 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 104LL))(v14, &v15);
  if ( ActivationFactory < 0 )
  {
LABEL_6:
    v5 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v6 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return (unsigned int)ActivationFactory;
  }
  v7 = v15;
  string = 0;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  ActivationFactory = v8(v7, &string);
  if ( ActivationFactory < 0 )
  {
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_6;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          a1,
                          StringRawBuffer) )
  {
    WindowsDeleteString(string);
    v12 = v15;
    string = 0;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return 0;
  }
  else
  {
    WindowsDeleteString(string);
    v10 = v15;
    string = 0;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1801195e0  mov     [rsp-18h+arg_8], rbx
0x1801195e5  mov     [rsp-18h+arg_10], rsi
0x1801195ea  push    rbp
0x1801195eb  push    rdi
0x1801195ec  push    r14
0x1801195ee  mov     rbp, rsp
0x1801195f1  sub     rsp, 60h
0x1801195f5  mov     rax, cs:__security_cookie
0x1801195fc  xor     rax, rsp
0x1801195ff  mov     [rbp+var_8], rax
0x180119603  xor     r14d, r14d
0x180119606  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x18011960d  mov     rsi, rcx
0x180119610  mov     [rbp+var_40], r14
0x180119614  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180119618  mov     [rbp+var_10], r14
0x18011961c  lea     r9d, [r14+25h]; unsigned int
0x180119620  lea     r8d, [r14+26h]; unsigned int
0x180119624  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180119629  mov     rcx, [rbp+var_10]
0x18011962d  lea     r8, [rbp+var_40]
0x180119631  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x180119638  call    cs:__imp_RoGetActivationFactory
0x18011963e  mov     ebx, eax
0x180119640  test    eax, eax
0x180119642  jns     short loc_180119667
0x180119644  mov     rdx, [rbp+var_40]
0x180119648  test    rdx, rdx
0x18011964b  jz      short loc_180119660
0x18011964d  mov     [rbp+var_40], r14
0x180119651  mov     rcx, [rdx]
0x180119654  mov     rax, [rcx+10h]
0x180119658  mov     rcx, rdx
0x18011965b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119660  mov     eax, ebx
0x180119662  jmp     loc_180119793
0x180119667  mov     rcx, [rbp+var_40]
0x18011966b  lea     rdx, [rbp+var_38]
0x18011966f  mov     [rbp+var_38], r14
0x180119673  mov     rax, [rcx]
0x180119676  mov     rax, [rax+68h]
0x18011967a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011967f  mov     ebx, eax
0x180119681  test    eax, eax
0x180119683  jns     short loc_1801196B7
0x180119685  mov     rdx, [rbp+var_38]
0x180119689  test    rdx, rdx
0x18011968c  jz      short loc_1801196A1
0x18011968e  mov     [rbp+var_38], r14
0x180119692  mov     rcx, [rdx]
0x180119695  mov     rax, [rcx+10h]
0x180119699  mov     rcx, rdx
0x18011969c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801196a1  mov     rcx, [rbp+var_40]
0x1801196a5  test    rcx, rcx
0x1801196a8  jz      short loc_180119660
0x1801196aa  mov     [rbp+var_40], r14
0x1801196ae  mov     rax, [rcx]
0x1801196b1  mov     rax, [rax+10h]
0x1801196b5  jmp     short loc_18011965B
0x1801196b7  mov     rdi, [rbp+var_38]
0x1801196bb  xor     ecx, ecx; string
0x1801196bd  mov     [rbp+string], r14
0x1801196c1  mov     rax, [rdi]
0x1801196c4  mov     rbx, [rax+40h]
0x1801196c8  call    cs:__imp_WindowsDeleteString
0x1801196ce  lea     rdx, [rbp+string]
0x1801196d2  mov     [rbp+string], r14
0x1801196d6  mov     rcx, rdi
0x1801196d9  mov     rax, rbx
0x1801196dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801196e1  mov     rcx, [rbp+string]; string
0x1801196e5  mov     ebx, eax
0x1801196e7  test    eax, eax
0x1801196e9  jns     short loc_1801196F7
0x1801196eb  call    cs:__imp_WindowsDeleteString
0x1801196f1  mov     [rbp+string], r14
0x1801196f5  jmp     short loc_180119685
0x1801196f7  xor     edx, edx; length
0x1801196f9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801196ff  mov     rdx, rax
0x180119702  mov     rcx, rsi
0x180119705  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18011970a  mov     rcx, [rbp+string]; string
0x18011970e  test    al, al
0x180119710  jnz     short loc_180119755
0x180119712  call    cs:__imp_WindowsDeleteString
0x180119718  mov     rcx, [rbp+var_38]
0x18011971c  mov     [rbp+string], r14
0x180119720  test    rcx, rcx
0x180119723  jz      short loc_180119735
0x180119725  mov     [rbp+var_38], r14
0x180119729  mov     rax, [rcx]
0x18011972c  mov     rax, [rax+10h]
0x180119730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119735  mov     rcx, [rbp+var_40]
0x180119739  test    rcx, rcx
0x18011973c  jz      short loc_18011974E
0x18011973e  mov     [rbp+var_40], r14
0x180119742  mov     rax, [rcx]
0x180119745  mov     rax, [rax+10h]
0x180119749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011974e  mov     eax, 8007000Eh
0x180119753  jmp     short loc_180119793
0x180119755  call    cs:__imp_WindowsDeleteString
0x18011975b  mov     rcx, [rbp+var_38]
0x18011975f  mov     [rbp+string], r14
0x180119763  test    rcx, rcx
0x180119766  jz      short loc_180119778
0x180119768  mov     [rbp+var_38], r14
0x18011976c  mov     rax, [rcx]
0x18011976f  mov     rax, [rax+10h]
0x180119773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119778  mov     rcx, [rbp+var_40]
0x18011977c  test    rcx, rcx
0x18011977f  jz      short loc_180119791
0x180119781  mov     [rbp+var_40], r14
0x180119785  mov     rax, [rcx]
0x180119788  mov     rax, [rax+10h]
0x18011978c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119791  xor     eax, eax
0x180119793  mov     rcx, [rbp+var_8]
0x180119797  xor     rcx, rsp; StackCookie
0x18011979a  call    __security_check_cookie
0x18011979f  lea     r11, [rsp+60h+var_s0]
0x1801197a4  mov     rbx, [r11+28h]
0x1801197a8  mov     rsi, [r11+30h]
0x1801197ac  mov     rsp, r11
0x1801197af  pop     r14
0x1801197b1  pop     rdi
0x1801197b2  pop     rbp
0x1801197b3  retn
```

# NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)

- ea: `0x180008390`
- end: `0x180008551`
- name: `?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z`
- size: `449`
- prototype: ``
- caller_count: `18`
- callee_count: `5`
- tags: ``

## callers

- `0x1800020d0`
- `0x180009380`
- `0x18000cb68`
- `0x180016334`
- `0x18001780c`
- `0x180018d90`
- `0x1800199dc`
- `0x180019b4c`
- `0x180019d04`
- `0x18001a1a8`
- `0x18001a40c`
- `0x18001acfc`
- `0x18001afb0`
- `0x18001d9d4`
- `0x18001dc28`
- `0x18002d280`
- `0x18002d370`
- `0x18002d73c`

## callees

- `0x180008390`
- `0x18001b848`
- `0x18001ff00`
- `0x1800307c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000851c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000851c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800083d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800083d9`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000841a`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000841a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NotificationParser::CreateValueSet(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  int v5; // edi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v8; // rcx
  int v9; // eax
  __int64 result; // rax
  int v11[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 (__fastcall ***v12)(_QWORD, GUID *, int *); // [rsp+28h] [rbp-50h] BYREF
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)v11 = 0;
  v13 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  *(_QWORD *)v11 = 0;
  v12 = 0;
  v5 = RoActivateInstance(string, &v12);
  if ( v5 < 0 )
    goto LABEL_6;
  if ( memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
  {
    v5 = (**v12)(v12, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, v11);
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, int *)))(*v12)[2])(v12);
LABEL_6:
    v6 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v11;
    goto LABEL_7;
  }
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v12;
  *(_QWORD *)v11 = v12;
LABEL_7:
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v5,
      v11[0]);
  v7 = **v6;
  v8 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = v7(v6, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v13);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6EB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v9,
      v11[0]);
  *a2 = *(_QWORD *)v11;
  result = v13;
  *a3 = v13;
  return result;
}

```

## disassembly

```asm
0x180008390  mov     [rsp+arg_0], rbx
0x180008395  mov     [rsp+arg_18], rbp
0x18000839a  push    rsi
0x18000839b  push    rdi
0x18000839c  push    r14
0x18000839e  sub     rsp, 60h
0x1800083a2  mov     rax, cs:__security_cookie
0x1800083a9  xor     rax, rsp
0x1800083ac  mov     [rsp+78h+var_20], rax
0x1800083b1  mov     r14, r8
0x1800083b4  mov     rsi, rdx
0x1800083b7  xor     ebp, ebp
0x1800083b9  mov     qword ptr [rsp+78h+var_58], rbp
0x1800083be  mov     [rsp+78h+var_48], rbp
0x1800083c3  lea     r9, [rsp+78h+string]; string
0x1800083c8  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x1800083cd  mov     edx, 27h ; '''; length
0x1800083d2  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x1800083d9  call    cs:__imp_WindowsCreateStringReference
0x1800083df  test    eax, eax
0x1800083e1  js      loc_18000850C
0x1800083e7  mov     rbx, [rsp+78h+string]
0x1800083ec  mov     rcx, qword ptr [rsp+78h+var_58]
0x1800083f1  test    rcx, rcx
0x1800083f4  jz      short loc_180008408
0x1800083f6  mov     qword ptr [rsp+78h+var_58], rbp
0x1800083fb  mov     rax, [rcx]
0x1800083fe  mov     rax, [rax+10h]
0x180008402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008407  nop
0x180008408  mov     qword ptr [rsp+78h+var_58], rbp; int
0x18000840d  mov     [rsp+78h+var_50], rbp
0x180008412  lea     rdx, [rsp+78h+var_50]
0x180008417  mov     rcx, rbx
0x18000841a  call    cs:__imp_RoActivateInstance
0x180008420  mov     edi, eax
0x180008422  test    eax, eax
0x180008424  js      short loc_180008476
0x180008426  mov     r8d, 10h; Size
0x18000842c  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180008433  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x18000843a  call    memcmp_0
0x18000843f  test    eax, eax
0x180008441  jz      loc_1800084FD
0x180008447  mov     rcx, [rsp+78h+var_50]
0x18000844c  mov     rax, [rcx]
0x18000844f  lea     r8, [rsp+78h+var_58]
0x180008454  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18000845b  mov     rax, [rax]
0x18000845e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008463  mov     edi, eax
0x180008465  mov     rcx, [rsp+78h+var_50]
0x18000846a  mov     rax, [rcx]
0x18000846d  mov     rax, [rax+10h]
0x180008471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008476  mov     rbx, qword ptr [rsp+78h+var_58]
0x18000847b  mov     rcx, [rsp+78h]; this
0x180008480  test    edi, edi
0x180008482  js      loc_180008527
0x180008488  mov     rax, [rbx]
0x18000848b  mov     rdi, [rax]
0x18000848e  mov     rcx, [rsp+78h+var_48]
0x180008493  test    rcx, rcx
0x180008496  jz      short loc_1800084AA
0x180008498  mov     [rsp+78h+var_48], rbp
0x18000849d  mov     rdx, [rcx]
0x1800084a0  mov     rax, [rdx+10h]
0x1800084a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a9  nop
0x1800084aa  lea     r8, [rsp+78h+var_48]
0x1800084af  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800084b6  mov     rcx, rbx
0x1800084b9  mov     rax, rdi
0x1800084bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084c1  nop
0x1800084c2  mov     rcx, [rsp+78h]; this
0x1800084c7  test    eax, eax
0x1800084c9  js      short loc_18000853C
0x1800084cb  mov     rax, qword ptr [rsp+78h+var_58]
0x1800084d0  mov     [rsi], rax
0x1800084d3  mov     rax, [rsp+78h+var_48]
0x1800084d8  mov     [r14], rax
0x1800084db  mov     rcx, [rsp+78h+var_20]
0x1800084e0  xor     rcx, rsp; StackCookie
0x1800084e3  call    __security_check_cookie
0x1800084e8  lea     r11, [rsp+78h+var_18]
0x1800084ed  mov     rbx, [r11+20h]
0x1800084f1  mov     rbp, [r11+38h]
0x1800084f5  mov     rsp, r11
0x1800084f8  pop     r14
0x1800084fa  pop     rdi
0x1800084fb  pop     rsi
0x1800084fc  retn
0x1800084fd  mov     rbx, [rsp+78h+var_50]
0x180008502  mov     qword ptr [rsp+78h+var_58], rbx
0x180008507  jmp     loc_18000847B
0x18000850c  xor     r9d, r9d; lpArguments
0x18000850f  xor     r8d, r8d; nNumberOfArguments
0x180008512  mov     edx, 1; dwExceptionFlags
0x180008517  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000851c  call    cs:__imp_RaiseException
0x180008522  jmp     loc_1800083E7
0x180008527  mov     r9d, edi; char *
0x18000852a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180008531  mov     edx, 6E8h; void *
0x180008536  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000853c  mov     r9d, eax; char *
0x18000853f  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180008546  mov     edx, 6EBh; void *
0x18000854b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

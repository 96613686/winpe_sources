# CProfile::GetFriendlySecurity(WTL::CString const &,WTL::CString const &,bool)

- ea: `0x18002780c`
- end: `0x180027a35`
- name: `?GetFriendlySecurity@CProfile@@SA?AVCString@WTL@@AEBV23@0_N@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002c8a8`

## callees

- `0x1800036ac`
- `0x180008484`
- `0x18000cee0`
- `0x18000d1d0`
- `0x18000d290`
- `0x18000d2e4`
- `0x180012d4c`
- `0x18002780c`
- `0x18002d81a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
WTL::CString *__fastcall CProfile::GetFriendlySecurity(
        WTL::CString *a1,
        const struct WTL::CString *a2,
        const struct WTL::CString *a3,
        char a4)
{
  wchar_t *v7; // rbx
  UINT v8; // edx
  __int64 v9; // rax
  wchar_t *v11; // [rsp+28h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-18h] BYREF

  WTL::CString::CString((WTL::CString *)&String1, a2);
  WTL::CString::CString((WTL::CString *)&v11, a3);
  WTL::CString::MakeLower((WTL::CString *)&String1);
  WTL::CString::MakeLower((WTL::CString *)&v11);
  *(_QWORD *)a1 = WTL::_atltmpPchNil;
  v7 = String1;
  if ( !wcscmp_0(String1, L"open") )
  {
    if ( a4 )
    {
      v8 = 19011;
LABEL_26:
      WTL::CString::LoadStringW(a1, v8);
      goto LABEL_27;
    }
    if ( !wcscmp_0(v11, L"none") )
    {
      v8 = 19001;
      goto LABEL_26;
    }
  }
  if ( !wcscmp_0(v11, L"wep") )
  {
    v8 = 19006;
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"wpa") )
  {
    v8 = 19008;
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"wpapsk") )
  {
    v8 = 19007;
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"wpa2") )
  {
    v8 = 19010;
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"wpa2psk") )
  {
    v8 = 19009;
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"wpa3ent") )
  {
    v8 = 19015;
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"wpa3") || !wcscmp_0(v7, L"wpa3ent192") )
  {
    v8 = 19014;
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"wpa3sae") )
  {
    v8 = 19013;
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"ihv") )
  {
    v8 = 19012;
    goto LABEL_26;
  }
  v9 = WTL::operator+((WTL::CString *)v14);
  WTL::operator+(v13, v9, a3);
  WTL::CString::operator=(a1);
  WTL::CString::~CString((WTL::CString *)v13);
  WTL::CString::~CString((WTL::CString *)v14);
LABEL_27:
  WTL::CString::~CString((WTL::CString *)&v11);
  WTL::CString::~CString((WTL::CString *)&String1);
  return a1;
}

```

## disassembly

```asm
0x18002780c  mov     [rsp-30h+arg_0], rcx
0x180027811  push    rbp
0x180027812  push    rbx
0x180027813  push    rsi
0x180027814  push    rdi
0x180027815  push    r14
0x180027817  push    r15
0x180027819  mov     rbp, rsp
0x18002781c  sub     rsp, 58h
0x180027820  mov     sil, r9b
0x180027823  mov     r14, r8
0x180027826  mov     r15, rdx
0x180027829  mov     rdi, rcx
0x18002782c  mov     [rbp+var_38], 0
0x180027833  lea     rcx, [rbp+String1]; this
0x180027837  call    ??0CString@WTL@@QEAA@AEBV01@@Z; WTL::CString::CString(WTL::CString const &)
0x18002783c  nop
0x18002783d  mov     rdx, r14; struct WTL::CString *
0x180027840  lea     rcx, [rbp+var_30]; this
0x180027844  call    ??0CString@WTL@@QEAA@AEBV01@@Z; WTL::CString::CString(WTL::CString const &)
0x180027849  nop
0x18002784a  lea     rcx, [rbp+String1]; this
0x18002784e  call    ?MakeLower@CString@WTL@@QEAAXXZ; WTL::CString::MakeLower(void)
0x180027853  lea     rcx, [rbp+var_30]; this
0x180027857  call    ?MakeLower@CString@WTL@@QEAAXXZ; WTL::CString::MakeLower(void)
0x18002785c  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180027863  mov     [rdi], rax
0x180027866  mov     [rbp+var_38], 1
0x18002786d  lea     rdx, aOpen; "open"
0x180027874  mov     rbx, [rbp+String1]
0x180027878  mov     rcx, rbx; String1
0x18002787b  call    wcscmp_0
0x180027880  test    eax, eax
0x180027882  jnz     short loc_1800278B1
0x180027884  test    sil, sil
0x180027887  jz      short loc_180027893
0x180027889  mov     edx, 4A43h
0x18002788e  jmp     loc_180027A08
0x180027893  lea     rdx, aNone; "none"
0x18002789a  mov     rcx, [rbp+var_30]; String1
0x18002789e  call    wcscmp_0
0x1800278a3  test    eax, eax
0x1800278a5  jnz     short loc_1800278B1
0x1800278a7  mov     edx, 4A39h
0x1800278ac  jmp     loc_180027A08
0x1800278b1  lea     rdx, aWep; "wep"
0x1800278b8  mov     rcx, [rbp+var_30]; String1
0x1800278bc  call    wcscmp_0
0x1800278c1  test    eax, eax
0x1800278c3  jnz     short loc_1800278CF
0x1800278c5  mov     edx, 4A3Eh
0x1800278ca  jmp     loc_180027A08
0x1800278cf  lea     rdx, aWpa; "wpa"
0x1800278d6  mov     rcx, rbx; String1
0x1800278d9  call    wcscmp_0
0x1800278de  test    eax, eax
0x1800278e0  jnz     short loc_1800278EC
0x1800278e2  mov     edx, 4A40h
0x1800278e7  jmp     loc_180027A08
0x1800278ec  lea     rdx, aWpapsk; "wpapsk"
0x1800278f3  mov     rcx, rbx; String1
0x1800278f6  call    wcscmp_0
0x1800278fb  test    eax, eax
0x1800278fd  jnz     short loc_180027909
0x1800278ff  mov     edx, 4A3Fh
0x180027904  jmp     loc_180027A08
0x180027909  lea     rdx, aWpa2; "wpa2"
0x180027910  mov     rcx, rbx; String1
0x180027913  call    wcscmp_0
0x180027918  test    eax, eax
0x18002791a  jnz     short loc_180027926
0x18002791c  mov     edx, 4A42h
0x180027921  jmp     loc_180027A08
0x180027926  lea     rdx, aWpa2psk; "wpa2psk"
0x18002792d  mov     rcx, rbx; String1
0x180027930  call    wcscmp_0
0x180027935  test    eax, eax
0x180027937  jnz     short loc_180027943
0x180027939  mov     edx, 4A41h
0x18002793e  jmp     loc_180027A08
0x180027943  lea     rdx, aWpa3ent; "wpa3ent"
0x18002794a  mov     rcx, rbx; String1
0x18002794d  call    wcscmp_0
0x180027952  test    eax, eax
0x180027954  jnz     short loc_180027960
0x180027956  mov     edx, 4A47h
0x18002795b  jmp     loc_180027A08
0x180027960  lea     rdx, aWpa3; "wpa3"
0x180027967  mov     rcx, rbx; String1
0x18002796a  call    wcscmp_0
0x18002796f  test    eax, eax
0x180027971  jz      loc_180027A03
0x180027977  lea     rdx, aWpa3ent192; "wpa3ent192"
0x18002797e  mov     rcx, rbx; String1
0x180027981  call    wcscmp_0
0x180027986  test    eax, eax
0x180027988  jz      short loc_180027A03
0x18002798a  lea     rdx, aWpa3sae; "wpa3sae"
0x180027991  mov     rcx, rbx; String1
0x180027994  call    wcscmp_0
0x180027999  test    eax, eax
0x18002799b  jnz     short loc_1800279A4
0x18002799d  mov     edx, 4A45h
0x1800279a2  jmp     short loc_180027A08
0x1800279a4  lea     rdx, aIhv_0; "ihv"
0x1800279ab  mov     rcx, rbx; String1
0x1800279ae  call    wcscmp_0
0x1800279b3  test    eax, eax
0x1800279b5  jnz     short loc_1800279BE
0x1800279b7  mov     edx, 4A44h
0x1800279bc  jmp     short loc_180027A08
0x1800279be  lea     r8, asc_180038128; " / "
0x1800279c5  mov     rdx, r15
0x1800279c8  lea     rcx, [rbp+var_18]; this
0x1800279cc  call    ??HWTL@@YA?AVCString@0@AEBV10@PEBG@Z; WTL::operator+(WTL::CString const &,ushort const *)
0x1800279d1  nop
0x1800279d2  mov     r8, r14
0x1800279d5  mov     rdx, rax
0x1800279d8  lea     rcx, [rbp+var_20]
0x1800279dc  call    ??HWTL@@YA?AVCString@0@AEBV10@0@Z; WTL::operator+(WTL::CString const &,WTL::CString const &)
0x1800279e1  nop
0x1800279e2  mov     rdx, rax
0x1800279e5  mov     rcx, rdi; this
0x1800279e8  call    ??4CString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator=(WTL::CString const &)
0x1800279ed  nop
0x1800279ee  lea     rcx, [rbp+var_20]; this
0x1800279f2  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800279f7  nop
0x1800279f8  lea     rcx, [rbp+var_18]; this
0x1800279fc  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180027a01  jmp     short loc_180027A11
0x180027a03  mov     edx, 4A46h; uID
0x180027a08  mov     rcx, rdi; this
0x180027a0b  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180027a10  nop
0x180027a11  lea     rcx, [rbp+var_30]; this
0x180027a15  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180027a1a  nop
0x180027a1b  lea     rcx, [rbp+String1]; this
0x180027a1f  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180027a24  mov     rax, rdi
0x180027a27  add     rsp, 58h
0x180027a2b  pop     r15
0x180027a2d  pop     r14
0x180027a2f  pop     rdi
0x180027a30  pop     rsi
0x180027a31  pop     rbx
0x180027a32  pop     rbp
0x180027a33  retn
```

# SerializeTrace(SOS_TraceStream &,wchar_t *,char *)

- ea: `0x100430960`
- end: `0x100430ac5`
- name: `?SerializeTrace@@YAXAEAVSOS_TraceStream@@PEA_WPEAD@Z`
- size: `357`
- prototype: `void(struct SOS_TraceStream *, wchar_t *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100401170`
- `0x10041db30`
- `0x10042dd80`
- `0x100430750`
- `0x100430960`

## import_xrefs

- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004309a9`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004309a9`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1004309a2`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1004309a2`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x100430a9b`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x100430a9b`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x100430a0a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x100430a3d`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x100430a78`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x100430a0a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x100430a3d`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x100430a78`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x100430a57`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x100430a6a`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x100430a8f`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x100430a57`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x100430a6a`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x100430a8f`
- `MSVCP140!?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ` at `0x100430a83`
- `MSVCP140!?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ` at `0x100430a83`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x1004309d8`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x1004309d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SerializeTrace(struct SOS_TraceStream *a1, wchar_t *a2, va_list a3)
{
  __crt_locale_pointers *Locale; // rbx
  unsigned __int64 *v7; // rax
  int v8; // eax
  __int64 v9; // rdi
  unsigned __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // r14
  unsigned __int8 v13; // di
  _BYTE v14[8]; // [rsp+40h] [rbp-258h] BYREF
  _BYTE v15[8]; // [rsp+48h] [rbp-250h] BYREF
  _BYTE v16[8]; // [rsp+50h] [rbp-248h] BYREF
  __int64 v17; // [rsp+58h] [rbp-240h]
  wchar_t Buffer[256]; // [rsp+60h] [rbp-238h] BYREF

  if ( a1 )
  {
    v17 = -2;
    TraceStreamHolder::TraceStreamHolder((TraceStreamHolder *)v16, a1);
    Locale = GetDefaultLocale();
    v7 = _local_stdio_printf_options();
    v8 = __stdio_common_vsnwprintf_s(*v7, Buffer, 0x100u, 0xFFu, a2, Locale, a3);
    v9 = -1;
    if ( v8 < 0 )
      v8 = -1;
    v10 = v8;
    if ( v10 >= 256 )
      _report_rangecheckfailure();
    v11 = 0;
    Buffer[v10] = 0;
    TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v14, a1);
    do
      ++v9;
    while ( Buffer[v9] );
    v12 = (unsigned int)v9;
    if ( (_DWORD)v9 )
    {
      do
      {
        v13 = Buffer[v11];
        TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v15, a1);
        std::operator<<<std::char_traits<char>>((char *)a1 + 16, v13);
        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v15);
        ++v11;
      }
      while ( v11 < v12 );
    }
    TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v14);
    TraceStreamProtector::TraceStreamProtector((TraceStreamProtector *)v14, a1);
    std::ostream::flush((char *)a1 + 16);
    TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v14);
    TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v16);
  }
}

```

## disassembly

```asm
0x100430960  test    rcx, rcx
0x100430963  jz      locret_100430ABE
0x100430969  push    rbx
0x10043096a  push    rbp
0x10043096b  push    rsi
0x10043096c  push    rdi
0x10043096d  push    r14
0x10043096f  sub     rsp, 270h
0x100430976  mov     [rsp+298h+var_240], 0FFFFFFFFFFFFFFFEh
0x10043097f  mov     rax, cs:__security_cookie
0x100430986  xor     rax, rsp
0x100430989  mov     [rsp+298h+var_38], rax
0x100430991  mov     rbp, r8
0x100430994  mov     rdi, rdx
0x100430997  mov     rsi, rcx
0x10043099a  mov     rdx, rcx
0x10043099d  lea     rcx, [rsp+298h+var_248]
0x1004309a2  call    cs:__imp_??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z; TraceStreamHolder::TraceStreamHolder(SOS_TraceStream &)
0x1004309a8  nop
0x1004309a9  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004309af  mov     rbx, rax
0x1004309b2  call    __local_stdio_printf_options
0x1004309b7  mov     [rsp+298h+ArgList], rbp; ArgList
0x1004309bc  mov     [rsp+298h+Locale], rbx; Locale
0x1004309c1  mov     [rsp+298h+Format], rdi; Format
0x1004309c6  mov     r9d, 0FFh; MaxCount
0x1004309cc  lea     r8d, [r9+1]; BufferCount
0x1004309d0  lea     rdx, [rsp+298h+Buffer]; Buffer
0x1004309d5  mov     rcx, [rax]; Options
0x1004309d8  call    cs:__imp___stdio_common_vsnwprintf_s
0x1004309de  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1004309e5  test    eax, eax
0x1004309e7  cmovs   eax, edi
0x1004309ea  cdqe
0x1004309ec  add     rax, rax
0x1004309ef  cmp     rax, 200h
0x1004309f5  jnb     loc_100430ABF
0x1004309fb  xor     ebx, ebx
0x1004309fd  mov     [rsp+rax+298h+Buffer], bx
0x100430a02  mov     rdx, rsi
0x100430a05  lea     rcx, [rsp+298h+var_258]
0x100430a0a  call    cs:__imp_??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z; TraceStreamProtector::TraceStreamProtector(SOS_TraceStream &)
0x100430a10  nop
0x100430a11  lea     rax, [rsp+298h+Buffer]
0x100430a16  inc     rdi
0x100430a19  cmp     word ptr [rax+rdi*2], 0
0x100430a1e  jnz     short loc_100430A16
0x100430a20  mov     r14d, edi
0x100430a23  test    edi, edi
0x100430a25  jz      short loc_100430A65
0x100430a27  nop     word ptr [rax+rax]
0x100430a2c  nop     dword ptr [rax+00h]
0x100430a30  movzx   edi, byte ptr [rsp+rbx*2+298h+Buffer]
0x100430a35  mov     rdx, rsi
0x100430a38  lea     rcx, [rsp+298h+var_250]
0x100430a3d  call    cs:__imp_??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z; TraceStreamProtector::TraceStreamProtector(SOS_TraceStream &)
0x100430a43  nop
0x100430a44  movzx   edx, dil
0x100430a48  lea     rcx, [rsi+10h]
0x100430a4c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@D@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char)
0x100430a51  nop
0x100430a52  lea     rcx, [rsp+298h+var_250]
0x100430a57  call    cs:__imp_??1TraceStreamProtector@@QEAA@XZ; TraceStreamProtector::~TraceStreamProtector(void)
0x100430a5d  inc     rbx
0x100430a60  cmp     rbx, r14
0x100430a63  jl      short loc_100430A30
0x100430a65  lea     rcx, [rsp+298h+var_258]
0x100430a6a  call    cs:__imp_??1TraceStreamProtector@@QEAA@XZ; TraceStreamProtector::~TraceStreamProtector(void)
0x100430a70  mov     rdx, rsi
0x100430a73  lea     rcx, [rsp+298h+var_258]
0x100430a78  call    cs:__imp_??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z; TraceStreamProtector::TraceStreamProtector(SOS_TraceStream &)
0x100430a7e  nop
0x100430a7f  lea     rcx, [rsi+10h]
0x100430a83  call    cs:__imp_?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x100430a89  nop
0x100430a8a  lea     rcx, [rsp+298h+var_258]
0x100430a8f  call    cs:__imp_??1TraceStreamProtector@@QEAA@XZ; TraceStreamProtector::~TraceStreamProtector(void)
0x100430a95  nop
0x100430a96  lea     rcx, [rsp+298h+var_248]
0x100430a9b  call    cs:__imp_??1TraceStreamHolder@@QEAA@XZ; TraceStreamHolder::~TraceStreamHolder(void)
0x100430aa1  mov     rcx, [rsp+298h+var_38]
0x100430aa9  xor     rcx, rsp; StackCookie
0x100430aac  call    __security_check_cookie
0x100430ab1  add     rsp, 270h
0x100430ab8  pop     r14
0x100430aba  pop     rdi
0x100430abb  pop     rsi
0x100430abc  pop     rbp
0x100430abd  pop     rbx
0x100430abe  retn
0x100430abf  call    __report_rangecheckfailure
```

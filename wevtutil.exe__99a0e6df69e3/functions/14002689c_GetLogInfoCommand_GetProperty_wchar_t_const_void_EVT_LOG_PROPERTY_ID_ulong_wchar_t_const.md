# GetLogInfoCommand::GetProperty(wchar_t const *,void *,_EVT_LOG_PROPERTY_ID,ulong,wchar_t const *)

- ea: `0x14002689c`
- end: `0x140026a7f`
- name: `?GetProperty@GetLogInfoCommand@@AEAAXPEB_WPEAXW4_EVT_LOG_PROPERTY_ID@@K0@Z`
- size: `483`
- prototype: `void(GetLogInfoCommand *__hidden this, const wchar_t *, void *, enum _EVT_LOG_PROPERTY_ID, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140026680`

## callees

- `0x14000a574`
- `0x14000cabc`
- `0x140010450`
- `0x14001a0e0`
- `0x1400217b8`
- `0x140021b00`
- `0x140022cec`
- `0x14002689c`
- `0x1400290f0`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetLogInfoCommand::GetProperty(
        GetLogInfoCommand *this,
        const wchar_t *a2,
        void *a3,
        EVT_LOG_PROPERTY_ID a4,
        unsigned int a5)
{
  unsigned int LogInfo; // eax
  unsigned int v8; // edi
  const wchar_t *p_pExceptionObject; // r8
  const char *v10; // [rsp+20h] [rbp-49h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-9h] BYREF
  __m128i si128; // [rsp+70h] [rbp+7h]

  LogInfo = GetLogInfo(a3, a4);
  v8 = LogInfo;
  if ( LogInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ddea4538a2063d21a9f201416765e880_Traceguids, LogInfo);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v8, 0, 0, v10, 40, 4u, a2);
    throw (EvtException *)&pExceptionObject;
  }
  if ( MEMORY[0xC] )
  {
    if ( MEMORY[0xC] != a5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ddea4538a2063d21a9f201416765e880_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, 0, 0, v10, 50, 4u, a2);
      throw (EvtException *)&pExceptionObject;
    }
    if ( MEMORY[0xC] == 1 )
    {
      XmlPrinter::PrintNameValue((GetLogInfoCommand *)((char *)this + 72), a2, MEMORY[0]);
    }
    else
    {
      pExceptionObject = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(pExceptionObject) = 0;
      FormatEvtVariant(&pExceptionObject, 0);
      p_pExceptionObject = (const wchar_t *)&pExceptionObject;
      if ( si128.m128i_i64[1] > 7uLL )
        p_pExceptionObject = (const wchar_t *)pExceptionObject;
      XmlPrinter::PrintNameValue((GetLogInfoCommand *)((char *)this + 72), a2, p_pExceptionObject);
      std::wstring::_Tidy_deallocate(&pExceptionObject);
    }
  }
}

```

## disassembly

```asm
0x14002689c  push    rbp
0x14002689e  push    rbx
0x14002689f  push    rsi
0x1400268a0  push    rdi
0x1400268a1  lea     rbp, [rsp-2Fh]
0x1400268a6  sub     rsp, 98h
0x1400268ad  mov     rax, cs:__security_cookie
0x1400268b4  xor     rax, rsp
0x1400268b7  mov     [rbp+47h+var_28], rax
0x1400268bb  mov     r10d, r9d
0x1400268be  mov     rax, r8
0x1400268c1  mov     rbx, rdx
0x1400268c4  mov     rsi, rcx
0x1400268c7  xorps   xmm0, xmm0
0x1400268ca  movdqu  [rbp+47h+var_68], xmm0
0x1400268cf  mov     [rbp+47h+var_58], 0
0x1400268d7  mov     [rbp+47h+var_70], 0
0x1400268df  lea     r9, [rbp+47h+var_70]
0x1400268e3  lea     r8, [rbp+47h+var_68]
0x1400268e7  mov     edx, r10d; PropertyId
0x1400268ea  mov     rcx, rax; Log
0x1400268ed  call    ?GetLogInfo@@YAKPEAXW4_EVT_LOG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetLogInfo(void *,_EVT_LOG_PROPERTY_ID,std::vector<uchar> &,_EVT_VARIANT * &)
0x1400268f2  mov     edi, eax
0x1400268f4  test    eax, eax
0x1400268f6  jz      short loc_140026969
0x1400268f8  lea     rdx, WPP_GLOBAL_Control
0x1400268ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140026906  cmp     rcx, rdx
0x140026909  jz      short loc_140026932
0x14002690b  test    dword ptr [rcx+1Ch], 400000h
0x140026912  jz      short loc_140026932
0x140026914  cmp     byte ptr [rcx+19h], 2
0x140026918  jb      short loc_140026932
0x14002691a  mov     edx, 0Ah
0x14002691f  mov     r9d, eax
0x140026922  lea     r8, WPP_ddea4538a2063d21a9f201416765e880_Traceguids
0x140026929  mov     rcx, [rcx+10h]
0x14002692d  call    WPP_SF_d
0x140026932  mov     [rsp+0B0h+Src], rbx; Src
0x140026937  mov     [rsp+0B0h+var_80], 4; unsigned int
0x14002693f  mov     [rsp+0B0h+var_88], 28h ; '('; int
0x140026947  xor     r9d, r9d; unsigned int
0x14002694a  xor     r8d, r8d; unsigned int
0x14002694d  mov     edx, edi; unsigned int
0x14002694f  lea     rcx, [rbp+47h+pExceptionObject]; this
0x140026953  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140026958  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002695f  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x140026963  call    _CxxThrowException_0
0x140026969  mov     r8, [rbp+47h+var_70]
0x14002696d  mov     eax, [r8+0Ch]
0x140026971  test    eax, eax
0x140026973  jz      loc_140026A52
0x140026979  cmp     eax, [rbp+47h+arg_20]
0x14002697c  jz      short loc_1400269F2
0x14002697e  lea     rdx, WPP_GLOBAL_Control
0x140026985  mov     edi, 0Dh
0x14002698a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026991  cmp     rcx, rdx
0x140026994  jz      short loc_1400269BB
0x140026996  test    dword ptr [rcx+1Ch], 400000h
0x14002699d  jz      short loc_1400269BB
0x14002699f  cmp     byte ptr [rcx+19h], 2
0x1400269a3  jb      short loc_1400269BB
0x1400269a5  lea     edx, [rdi-2]
0x1400269a8  mov     r9d, edi
0x1400269ab  lea     r8, WPP_ddea4538a2063d21a9f201416765e880_Traceguids
0x1400269b2  mov     rcx, [rcx+10h]
0x1400269b6  call    WPP_SF_d
0x1400269bb  mov     [rsp+0B0h+Src], rbx; Src
0x1400269c0  mov     [rsp+0B0h+var_80], 4; unsigned int
0x1400269c8  mov     [rsp+0B0h+var_88], 32h ; '2'; int
0x1400269d0  xor     r9d, r9d; unsigned int
0x1400269d3  xor     r8d, r8d; unsigned int
0x1400269d6  mov     edx, edi; unsigned int
0x1400269d8  lea     rcx, [rbp+47h+pExceptionObject]; this
0x1400269dc  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400269e1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400269e8  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x1400269ec  call    _CxxThrowException_0
0x1400269f2  cmp     eax, 1
0x1400269f5  jnz     short loc_140026A08
0x1400269f7  mov     r8, [r8]; wchar_t *
0x1400269fa  mov     rdx, rbx; wchar_t *
0x1400269fd  lea     rcx, [rsi+48h]; this
0x140026a01  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x140026a06  jmp     short loc_140026A52
0x140026a08  xorps   xmm0, xmm0
0x140026a0b  movups  [rbp+47h+pExceptionObject], xmm0
0x140026a0f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140026a17  movdqu  [rbp+47h+var_40], xmm1
0x140026a1c  xor     eax, eax
0x140026a1e  mov     word ptr [rbp+47h+pExceptionObject], ax
0x140026a22  xor     edx, edx
0x140026a24  lea     rcx, [rbp+47h+pExceptionObject]
0x140026a28  call    ?FormatEvtVariant@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WPEAU_EVT_VARIANT@@@Z; FormatEvtVariant(std::wstring &,wchar_t const *,_EVT_VARIANT *)
0x140026a2d  lea     r8, [rbp+47h+pExceptionObject]
0x140026a31  cmp     qword ptr [rbp+47h+var_40+8], 7
0x140026a36  cmova   r8, qword ptr [rbp+47h+pExceptionObject]; wchar_t *
0x140026a3b  mov     rdx, rbx; wchar_t *
0x140026a3e  lea     rcx, [rsi+48h]; this
0x140026a42  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x140026a47  nop
0x140026a48  lea     rcx, [rbp+47h+pExceptionObject]
0x140026a4c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140026a51  nop
0x140026a52  mov     rcx, qword ptr [rbp+47h+var_68]
0x140026a56  test    rcx, rcx
0x140026a59  jz      short loc_140026A67
0x140026a5b  mov     rdx, [rbp+47h+var_58]
0x140026a5f  sub     rdx, rcx
0x140026a62  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140026a67  mov     rcx, [rbp+47h+var_28]
0x140026a6b  xor     rcx, rsp; StackCookie
0x140026a6e  call    __security_check_cookie
0x140026a73  add     rsp, 98h
0x140026a7a  pop     rdi
0x140026a7b  pop     rsi
0x140026a7c  pop     rbx
0x140026a7d  pop     rbp
0x140026a7e  retn
```

# GetPublisherCommand::GetProperty(wchar_t const *,void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,ulong,wchar_t const *)

- ea: `0x140026bb8`
- end: `0x140026dbc`
- name: `?GetProperty@GetPublisherCommand@@AEAAXPEB_WPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@K0@Z`
- size: `516`
- prototype: `void __fastcall(GetPublisherCommand *this, const wchar_t *, void *, EVT_PUBLISHER_METADATA_PROPERTY_ID PropertyId, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000db10`

## callees

- `0x14000a574`
- `0x14000cabc`
- `0x140010450`
- `0x14001a0e0`
- `0x14002164c`
- `0x1400217b8`
- `0x140021b00`
- `0x140022cec`
- `0x140026bb8`
- `0x14002924c`
- `0x140031810`

## pseudocode

```c
void __fastcall GetPublisherCommand::GetProperty(
        GetPublisherCommand *this,
        const wchar_t *a2,
        void *a3,
        EVT_PUBLISHER_METADATA_PROPERTY_ID PropertyId,
        unsigned int a5)
{
  unsigned int PublisherProperty; // eax
  unsigned int v10; // esi
  DWORD Type; // eax
  const wchar_t *p_pExceptionObject; // r8
  const char *v13; // [rsp+20h] [rbp-59h]
  struct _EVT_VARIANT *v14; // [rsp+40h] [rbp-39h] BYREF
  __int128 v15; // [rsp+48h] [rbp-31h] BYREF
  __int64 v16; // [rsp+58h] [rbp-21h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-19h] BYREF
  __m128i si128; // [rsp+70h] [rbp-9h]

  v15 = 0;
  v16 = 0;
  v14 = 0;
  PublisherProperty = GetPublisherProperty(a3, PropertyId, (__int64)&v15, &v14);
  v10 = PublisherProperty;
  if ( PublisherProperty )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids,
        PublisherProperty);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v10, 0, 0, v13, 99, 4u, a2);
    throw (EvtException *)&pExceptionObject;
  }
  Type = v14->Type;
  if ( Type )
  {
    if ( Type != a5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, 0, 0, v13, 109, 4u, a2);
      throw (EvtException *)&pExceptionObject;
    }
    if ( Type == 1 )
    {
      XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, v14->StringVal);
    }
    else if ( PropertyId == EvtPublisherMetadataPublisherMessageID )
    {
      GetPublisherCommand::PrintMessage(this, a2, a3, v14->BooleanVal);
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
      XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, p_pExceptionObject);
      std::wstring::_Tidy_deallocate(&pExceptionObject);
    }
  }
  if ( (_QWORD)v15 )
    std::_Deallocate<16>(v15, v16 - v15);
}

```

## disassembly

```asm
0x140026bb8  push    rbp
0x140026bba  push    rbx
0x140026bbb  push    rsi
0x140026bbc  push    rdi
0x140026bbd  push    r14
0x140026bbf  push    r15
0x140026bc1  lea     rbp, [rsp-1Fh]
0x140026bc6  sub     rsp, 98h
0x140026bcd  mov     rax, cs:__security_cookie
0x140026bd4  xor     rax, rsp
0x140026bd7  mov     [rbp+47h+var_38], rax
0x140026bdb  mov     r14d, r9d
0x140026bde  mov     r15, r8
0x140026be1  mov     rbx, rdx
0x140026be4  mov     rdi, rcx
0x140026be7  xorps   xmm0, xmm0
0x140026bea  movdqu  [rbp+47h+var_78], xmm0
0x140026bef  mov     [rbp+47h+var_68], 0
0x140026bf7  mov     [rbp+47h+var_80], 0
0x140026bff  lea     r9, [rbp+47h+var_80]
0x140026c03  lea     r8, [rbp+47h+var_78]
0x140026c07  mov     edx, r14d; PropertyId
0x140026c0a  mov     rcx, r15; PublisherMetadata
0x140026c0d  call    ?GetPublisherProperty@@YAKPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetPublisherProperty(void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,std::vector<uchar> &,_EVT_VARIANT * &)
0x140026c12  mov     esi, eax
0x140026c14  test    eax, eax
0x140026c16  jz      short loc_140026C89
0x140026c18  lea     rdx, WPP_GLOBAL_Control
0x140026c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c26  cmp     rcx, rdx
0x140026c29  jz      short loc_140026C52
0x140026c2b  test    dword ptr [rcx+1Ch], 400000h
0x140026c32  jz      short loc_140026C52
0x140026c34  cmp     byte ptr [rcx+19h], 2
0x140026c38  jb      short loc_140026C52
0x140026c3a  mov     edx, 0Bh
0x140026c3f  mov     r9d, eax
0x140026c42  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x140026c49  mov     rcx, [rcx+10h]
0x140026c4d  call    WPP_SF_d
0x140026c52  mov     [rsp+0C0h+Src], rbx; Src
0x140026c57  mov     [rsp+0C0h+var_90], 4; unsigned int
0x140026c5f  mov     [rsp+0C0h+var_98], 63h ; 'c'; int
0x140026c67  xor     r9d, r9d; unsigned int
0x140026c6a  xor     r8d, r8d; unsigned int
0x140026c6d  mov     edx, esi; unsigned int
0x140026c6f  lea     rcx, [rbp+47h+pExceptionObject]; this
0x140026c73  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140026c78  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026c7f  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x140026c83  call    _CxxThrowException_0
0x140026c89  mov     r8, [rbp+47h+var_80]
0x140026c8d  mov     eax, [r8+0Ch]
0x140026c91  test    eax, eax
0x140026c93  jz      loc_140026D8B
0x140026c99  cmp     eax, [rbp+47h+arg_20]
0x140026c9c  jz      short loc_140026D12
0x140026c9e  lea     rdx, WPP_GLOBAL_Control
0x140026ca5  mov     edi, 0Dh
0x140026caa  mov     rcx, cs:WPP_GLOBAL_Control
0x140026cb1  cmp     rcx, rdx
0x140026cb4  jz      short loc_140026CDB
0x140026cb6  test    dword ptr [rcx+1Ch], 400000h
0x140026cbd  jz      short loc_140026CDB
0x140026cbf  cmp     byte ptr [rcx+19h], 2
0x140026cc3  jb      short loc_140026CDB
0x140026cc5  lea     edx, [rdi-1]
0x140026cc8  mov     r9d, edi
0x140026ccb  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x140026cd2  mov     rcx, [rcx+10h]
0x140026cd6  call    WPP_SF_d
0x140026cdb  mov     [rsp+0C0h+Src], rbx; Src
0x140026ce0  mov     [rsp+0C0h+var_90], 4; unsigned int
0x140026ce8  mov     [rsp+0C0h+var_98], 6Dh ; 'm'; int
0x140026cf0  xor     r9d, r9d; unsigned int
0x140026cf3  xor     r8d, r8d; unsigned int
0x140026cf6  mov     edx, edi; unsigned int
0x140026cf8  lea     rcx, [rbp+47h+pExceptionObject]; this
0x140026cfc  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140026d01  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026d08  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x140026d0c  call    _CxxThrowException_0
0x140026d12  cmp     eax, 1
0x140026d15  jnz     short loc_140026D28
0x140026d17  lea     rcx, [rdi+48h]; this
0x140026d1b  mov     r8, [r8]; wchar_t *
0x140026d1e  mov     rdx, rbx; wchar_t *
0x140026d21  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x140026d26  jmp     short loc_140026D8B
0x140026d28  cmp     r14d, 5
0x140026d2c  jnz     short loc_140026D41
0x140026d2e  mov     r9d, [r8]; unsigned int
0x140026d31  mov     r8, r15; void *
0x140026d34  mov     rdx, rbx; wchar_t *
0x140026d37  mov     rcx, rdi; this
0x140026d3a  call    ?PrintMessage@GetPublisherCommand@@AEAAXPEB_WPEAXK@Z; GetPublisherCommand::PrintMessage(wchar_t const *,void *,ulong)
0x140026d3f  jmp     short loc_140026D8B
0x140026d41  xorps   xmm0, xmm0
0x140026d44  movups  [rbp+47h+pExceptionObject], xmm0
0x140026d48  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140026d50  movdqu  [rbp+47h+var_50], xmm1
0x140026d55  xor     eax, eax
0x140026d57  mov     word ptr [rbp+47h+pExceptionObject], ax
0x140026d5b  xor     edx, edx
0x140026d5d  lea     rcx, [rbp+47h+pExceptionObject]
0x140026d61  call    ?FormatEvtVariant@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WPEAU_EVT_VARIANT@@@Z; FormatEvtVariant(std::wstring &,wchar_t const *,_EVT_VARIANT *)
0x140026d66  lea     r8, [rbp+47h+pExceptionObject]
0x140026d6a  cmp     qword ptr [rbp+47h+var_50+8], 7
0x140026d6f  cmova   r8, qword ptr [rbp+47h+pExceptionObject]; wchar_t *
0x140026d74  lea     rcx, [rdi+48h]; this
0x140026d78  mov     rdx, rbx; wchar_t *
0x140026d7b  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x140026d80  nop
0x140026d81  lea     rcx, [rbp+47h+pExceptionObject]
0x140026d85  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140026d8a  nop
0x140026d8b  mov     rcx, qword ptr [rbp+47h+var_78]
0x140026d8f  test    rcx, rcx
0x140026d92  jz      short loc_140026DA0
0x140026d94  mov     rdx, [rbp+47h+var_68]
0x140026d98  sub     rdx, rcx
0x140026d9b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140026da0  mov     rcx, [rbp+47h+var_38]
0x140026da4  xor     rcx, rsp; StackCookie
0x140026da7  call    __security_check_cookie
0x140026dac  add     rsp, 98h
0x140026db3  pop     r15
0x140026db5  pop     r14
0x140026db7  pop     rdi
0x140026db8  pop     rsi
0x140026db9  pop     rbx
0x140026dba  pop     rbp
0x140026dbb  retn
```

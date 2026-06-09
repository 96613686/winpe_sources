# GetPublisherCommand::GetPropertyEventMetadata(wchar_t const *,void *,void *,_EVT_EVENT_METADATA_PROPERTY_ID,ulong,wchar_t const *)

- ea: `0x140026fe8`
- end: `0x1400271ea`
- name: `?GetPropertyEventMetadata@GetPublisherCommand@@AEAAXPEB_WPEAX1W4_EVT_EVENT_METADATA_PROPERTY_ID@@K0@Z`
- size: `514`
- prototype: `void __fastcall(GetPublisherCommand *__hidden this, const wchar_t *, void *, EVT_HANDLE EventMetadata, EVT_EVENT_METADATA_PROPERTY_ID PropertyId, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400100dc`

## callees

- `0x14000a574`
- `0x14000cabc`
- `0x140010450`
- `0x14001a0e0`
- `0x14002164c`
- `0x1400217b8`
- `0x140021b00`
- `0x140022cec`
- `0x140026fe8`
- `0x140028e54`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetPublisherCommand::GetPropertyEventMetadata(
        GetPublisherCommand *this,
        const wchar_t *a2,
        void *a3,
        EVT_HANDLE EventMetadata,
        EVT_EVENT_METADATA_PROPERTY_ID PropertyId,
        unsigned int a6,
        const wchar_t *a7)
{
  unsigned int EventProperty; // eax
  unsigned int v11; // esi
  const wchar_t *p_pExceptionObject; // r8
  const char *v13; // [rsp+20h] [rbp-51h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-11h] BYREF
  __m128i si128; // [rsp+70h] [rbp-1h]

  EventProperty = GetEventProperty(EventMetadata, PropertyId);
  v11 = EventProperty;
  if ( EventProperty )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, EventProperty);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v11, 0, 0, v13, 144, 4u, a2);
    throw (EvtException *)&pExceptionObject;
  }
  if ( MEMORY[0xC] )
  {
    if ( MEMORY[0xC] != a6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, 0, 0, v13, 154, 4u, a2);
      throw (EvtException *)&pExceptionObject;
    }
    if ( MEMORY[0xC] == 1 )
    {
      XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, MEMORY[0]);
    }
    else if ( PropertyId == EventMetadataEventMessageID )
    {
      GetPublisherCommand::PrintMessage(this, a2, a3, MEMORY[0]);
    }
    else
    {
      pExceptionObject = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(pExceptionObject) = 0;
      FormatEvtVariant(&pExceptionObject, a7);
      p_pExceptionObject = (const wchar_t *)&pExceptionObject;
      if ( si128.m128i_i64[1] > 7uLL )
        p_pExceptionObject = (const wchar_t *)pExceptionObject;
      XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, p_pExceptionObject);
      std::wstring::_Tidy_deallocate(&pExceptionObject);
    }
  }
}

```

## disassembly

```asm
0x140026fe8  push    rbp
0x140026fea  push    rbx
0x140026feb  push    rsi
0x140026fec  push    rdi
0x140026fed  push    r14
0x140026fef  lea     rbp, [rsp-1Fh]
0x140026ff4  sub     rsp, 90h
0x140026ffb  mov     rax, cs:__security_cookie
0x140027002  xor     rax, rsp
0x140027005  mov     [rbp+3Fh+var_28], rax
0x140027009  mov     rax, r9
0x14002700c  mov     r14, r8
0x14002700f  mov     rbx, rdx
0x140027012  mov     rdi, rcx
0x140027015  xorps   xmm0, xmm0
0x140027018  movdqu  [rbp+3Fh+var_68], xmm0
0x14002701d  mov     [rbp+3Fh+var_58], 0
0x140027025  mov     [rbp+3Fh+var_70], 0
0x14002702d  lea     r9, [rbp+3Fh+var_70]
0x140027031  lea     r8, [rbp+3Fh+var_68]
0x140027035  mov     edx, [rbp+3Fh+PropertyId]; PropertyId
0x140027038  mov     rcx, rax; EventMetadata
0x14002703b  call    ?GetEventProperty@@YAKPEAXW4_EVT_EVENT_METADATA_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetEventProperty(void *,_EVT_EVENT_METADATA_PROPERTY_ID,std::vector<uchar> &,_EVT_VARIANT * &)
0x140027040  mov     esi, eax
0x140027042  test    eax, eax
0x140027044  jz      short loc_1400270B7
0x140027046  lea     rdx, WPP_GLOBAL_Control
0x14002704d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027054  cmp     rcx, rdx
0x140027057  jz      short loc_140027080
0x140027059  test    dword ptr [rcx+1Ch], 400000h
0x140027060  jz      short loc_140027080
0x140027062  cmp     byte ptr [rcx+19h], 2
0x140027066  jb      short loc_140027080
0x140027068  mov     edx, 0Dh
0x14002706d  mov     r9d, eax
0x140027070  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x140027077  mov     rcx, [rcx+10h]
0x14002707b  call    WPP_SF_d
0x140027080  mov     [rsp+0B0h+Src], rbx; Src
0x140027085  mov     [rsp+0B0h+var_80], 4; unsigned int
0x14002708d  mov     [rsp+0B0h+var_88], 90h; int
0x140027095  xor     r9d, r9d; unsigned int
0x140027098  xor     r8d, r8d; unsigned int
0x14002709b  mov     edx, esi; unsigned int
0x14002709d  lea     rcx, [rbp+3Fh+pExceptionObject]; this
0x1400270a1  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400270a6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400270ad  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x1400270b1  call    _CxxThrowException_0
0x1400270b7  mov     r8, [rbp+3Fh+var_70]
0x1400270bb  mov     eax, [r8+0Ch]
0x1400270bf  test    eax, eax
0x1400270c1  jz      loc_1400271BB
0x1400270c7  cmp     eax, [rbp+3Fh+arg_28]
0x1400270ca  jz      short loc_140027140
0x1400270cc  lea     rdx, WPP_GLOBAL_Control
0x1400270d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400270da  cmp     rcx, rdx
0x1400270dd  jz      short loc_140027107
0x1400270df  test    dword ptr [rcx+1Ch], 400000h
0x1400270e6  jz      short loc_140027107
0x1400270e8  cmp     byte ptr [rcx+19h], 2
0x1400270ec  jb      short loc_140027107
0x1400270ee  mov     edx, 0Eh
0x1400270f3  lea     r9d, [rdx-1]
0x1400270f7  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x1400270fe  mov     rcx, [rcx+10h]
0x140027102  call    WPP_SF_d
0x140027107  mov     [rsp+0B0h+Src], rbx; Src
0x14002710c  mov     [rsp+0B0h+var_80], 4; unsigned int
0x140027114  mov     [rsp+0B0h+var_88], 9Ah; int
0x14002711c  xor     r9d, r9d; unsigned int
0x14002711f  xor     r8d, r8d; unsigned int
0x140027122  lea     edx, [r9+0Dh]; unsigned int
0x140027126  lea     rcx, [rbp+3Fh+pExceptionObject]; this
0x14002712a  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14002712f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140027136  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x14002713a  call    _CxxThrowException_0
0x140027140  cmp     eax, 1
0x140027143  jnz     short loc_140027156
0x140027145  lea     rcx, [rdi+48h]; this
0x140027149  mov     r8, [r8]; wchar_t *
0x14002714c  mov     rdx, rbx; wchar_t *
0x14002714f  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x140027154  jmp     short loc_1400271BB
0x140027156  cmp     [rbp+3Fh+PropertyId], 7
0x14002715a  jnz     short loc_14002716F
0x14002715c  mov     r9d, [r8]; unsigned int
0x14002715f  mov     r8, r14; void *
0x140027162  mov     rdx, rbx; wchar_t *
0x140027165  mov     rcx, rdi; this
0x140027168  call    ?PrintMessage@GetPublisherCommand@@AEAAXPEB_WPEAXK@Z; GetPublisherCommand::PrintMessage(wchar_t const *,void *,ulong)
0x14002716d  jmp     short loc_1400271BB
0x14002716f  xorps   xmm0, xmm0
0x140027172  movups  [rbp+3Fh+pExceptionObject], xmm0
0x140027176  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14002717e  movdqu  [rbp+3Fh+var_40], xmm1
0x140027183  xor     eax, eax
0x140027185  mov     word ptr [rbp+3Fh+pExceptionObject], ax
0x140027189  mov     rdx, [rbp+3Fh+arg_30]
0x14002718d  lea     rcx, [rbp+3Fh+pExceptionObject]
0x140027191  call    ?FormatEvtVariant@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WPEAU_EVT_VARIANT@@@Z; FormatEvtVariant(std::wstring &,wchar_t const *,_EVT_VARIANT *)
0x140027196  lea     r8, [rbp+3Fh+pExceptionObject]
0x14002719a  cmp     qword ptr [rbp+3Fh+var_40+8], 7
0x14002719f  cmova   r8, qword ptr [rbp+3Fh+pExceptionObject]; wchar_t *
0x1400271a4  lea     rcx, [rdi+48h]; this
0x1400271a8  mov     rdx, rbx; wchar_t *
0x1400271ab  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x1400271b0  nop
0x1400271b1  lea     rcx, [rbp+3Fh+pExceptionObject]
0x1400271b5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400271ba  nop
0x1400271bb  mov     rcx, qword ptr [rbp+3Fh+var_68]
0x1400271bf  test    rcx, rcx
0x1400271c2  jz      short loc_1400271D0
0x1400271c4  mov     rdx, [rbp+3Fh+var_58]
0x1400271c8  sub     rdx, rcx
0x1400271cb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400271d0  mov     rcx, [rbp+3Fh+var_28]
0x1400271d4  xor     rcx, rsp; StackCookie
0x1400271d7  call    __security_check_cookie
0x1400271dc  add     rsp, 90h
0x1400271e3  pop     r14
0x1400271e5  pop     rdi
0x1400271e6  pop     rsi
0x1400271e7  pop     rbx
0x1400271e8  pop     rbp
0x1400271e9  retn
```

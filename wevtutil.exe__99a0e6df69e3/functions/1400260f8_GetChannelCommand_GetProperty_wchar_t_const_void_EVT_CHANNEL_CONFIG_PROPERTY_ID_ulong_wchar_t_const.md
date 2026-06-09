# GetChannelCommand::GetProperty(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,ulong,wchar_t const *)

- ea: `0x1400260f8`
- end: `0x1400262dd`
- name: `?GetProperty@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@K0@Z`
- size: `485`
- prototype: `void(GetChannelCommand *__hidden this, const wchar_t *, void *, enum _EVT_CHANNEL_CONFIG_PROPERTY_ID, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e550`

## callees

- `0x14000a574`
- `0x14000cabc`
- `0x140010450`
- `0x14001a0e0`
- `0x1400217b8`
- `0x140021b00`
- `0x140022cec`
- `0x1400260f8`
- `0x140028ce8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetChannelCommand::GetProperty(
        GetChannelCommand *this,
        const wchar_t *a2,
        void *a3,
        EVT_CHANNEL_CONFIG_PROPERTY_ID a4,
        unsigned int a5,
        const wchar_t *a6)
{
  unsigned int ChannelProperty; // eax
  unsigned int v9; // edi
  DWORD Type; // eax
  const wchar_t *p_pExceptionObject; // r8
  const char *v12; // [rsp+20h] [rbp-49h]
  struct _EVT_VARIANT *v13; // [rsp+40h] [rbp-29h] BYREF
  __int128 v14; // [rsp+48h] [rbp-21h] BYREF
  __int64 v15; // [rsp+58h] [rbp-11h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-9h] BYREF
  __m128i si128; // [rsp+70h] [rbp+7h]

  v14 = 0;
  v15 = 0;
  v13 = 0;
  ChannelProperty = GetChannelProperty(a3, a4, (__int64)&v14, &v13);
  v9 = ChannelProperty;
  if ( ChannelProperty )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids,
        ChannelProperty);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v9, 0, 0, v12, 47, 4u, a2);
    throw (EvtException *)&pExceptionObject;
  }
  Type = v13->Type;
  if ( Type )
  {
    if ( Type != a5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, 0, 0, v12, 57, 4u, a2);
      throw (EvtException *)&pExceptionObject;
    }
    if ( Type == 1 )
    {
      XmlPrinter::PrintNameValue((GetChannelCommand *)((char *)this + 72), a2, v13->StringVal);
    }
    else
    {
      pExceptionObject = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(pExceptionObject) = 0;
      FormatEvtVariant(&pExceptionObject, a6);
      p_pExceptionObject = (const wchar_t *)&pExceptionObject;
      if ( si128.m128i_i64[1] > 7uLL )
        p_pExceptionObject = (const wchar_t *)pExceptionObject;
      XmlPrinter::PrintNameValue((GetChannelCommand *)((char *)this + 72), a2, p_pExceptionObject);
      std::wstring::_Tidy_deallocate(&pExceptionObject);
    }
  }
  if ( (_QWORD)v14 )
    std::_Deallocate<16>(v14, v15 - v14);
}

```

## disassembly

```asm
0x1400260f8  push    rbp
0x1400260fa  push    rbx
0x1400260fb  push    rsi
0x1400260fc  push    rdi
0x1400260fd  lea     rbp, [rsp-2Fh]
0x140026102  sub     rsp, 98h
0x140026109  mov     rax, cs:__security_cookie
0x140026110  xor     rax, rsp
0x140026113  mov     [rbp+47h+var_28], rax
0x140026117  mov     r10d, r9d
0x14002611a  mov     rax, r8
0x14002611d  mov     rbx, rdx
0x140026120  mov     rsi, rcx
0x140026123  xorps   xmm0, xmm0
0x140026126  movdqu  [rbp+47h+var_68], xmm0
0x14002612b  mov     [rbp+47h+var_58], 0
0x140026133  mov     [rbp+47h+var_70], 0
0x14002613b  lea     r9, [rbp+47h+var_70]
0x14002613f  lea     r8, [rbp+47h+var_68]
0x140026143  mov     edx, r10d; PropertyId
0x140026146  mov     rcx, rax; ChannelConfig
0x140026149  call    ?GetChannelProperty@@YAKPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetChannelProperty(void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,std::vector<uchar> &,_EVT_VARIANT * &)
0x14002614e  mov     edi, eax
0x140026150  test    eax, eax
0x140026152  jz      short loc_1400261C5
0x140026154  lea     rdx, WPP_GLOBAL_Control
0x14002615b  mov     rcx, cs:WPP_GLOBAL_Control
0x140026162  cmp     rcx, rdx
0x140026165  jz      short loc_14002618E
0x140026167  test    dword ptr [rcx+1Ch], 400000h
0x14002616e  jz      short loc_14002618E
0x140026170  cmp     byte ptr [rcx+19h], 2
0x140026174  jb      short loc_14002618E
0x140026176  mov     edx, 0Ah
0x14002617b  mov     r9d, eax
0x14002617e  lea     r8, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids
0x140026185  mov     rcx, [rcx+10h]
0x140026189  call    WPP_SF_d
0x14002618e  mov     [rsp+0B0h+Src], rbx; Src
0x140026193  mov     [rsp+0B0h+var_80], 4; unsigned int
0x14002619b  mov     [rsp+0B0h+var_88], 2Fh ; '/'; int
0x1400261a3  xor     r9d, r9d; unsigned int
0x1400261a6  xor     r8d, r8d; unsigned int
0x1400261a9  mov     edx, edi; unsigned int
0x1400261ab  lea     rcx, [rbp+47h+pExceptionObject]; this
0x1400261af  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400261b4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400261bb  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x1400261bf  call    _CxxThrowException_0
0x1400261c5  mov     r8, [rbp+47h+var_70]
0x1400261c9  mov     eax, [r8+0Ch]
0x1400261cd  test    eax, eax
0x1400261cf  jz      loc_1400262B0
0x1400261d5  cmp     eax, [rbp+47h+arg_20]
0x1400261d8  jz      short loc_14002624E
0x1400261da  lea     rdx, WPP_GLOBAL_Control
0x1400261e1  mov     edi, 0Dh
0x1400261e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400261ed  cmp     rcx, rdx
0x1400261f0  jz      short loc_140026217
0x1400261f2  test    dword ptr [rcx+1Ch], 400000h
0x1400261f9  jz      short loc_140026217
0x1400261fb  cmp     byte ptr [rcx+19h], 2
0x1400261ff  jb      short loc_140026217
0x140026201  lea     edx, [rdi-2]
0x140026204  mov     r9d, edi
0x140026207  lea     r8, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids
0x14002620e  mov     rcx, [rcx+10h]
0x140026212  call    WPP_SF_d
0x140026217  mov     [rsp+0B0h+Src], rbx; Src
0x14002621c  mov     [rsp+0B0h+var_80], 4; unsigned int
0x140026224  mov     [rsp+0B0h+var_88], 39h ; '9'; int
0x14002622c  xor     r9d, r9d; unsigned int
0x14002622f  xor     r8d, r8d; unsigned int
0x140026232  mov     edx, edi; unsigned int
0x140026234  lea     rcx, [rbp+47h+pExceptionObject]; this
0x140026238  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14002623d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026244  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x140026248  call    _CxxThrowException_0
0x14002624e  cmp     eax, 1
0x140026251  jnz     short loc_140026264
0x140026253  mov     r8, [r8]; wchar_t *
0x140026256  mov     rdx, rbx; wchar_t *
0x140026259  lea     rcx, [rsi+48h]; this
0x14002625d  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x140026262  jmp     short loc_1400262B0
0x140026264  xorps   xmm0, xmm0
0x140026267  movups  [rbp+47h+pExceptionObject], xmm0
0x14002626b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140026273  movdqu  [rbp+47h+var_40], xmm1
0x140026278  xor     eax, eax
0x14002627a  mov     word ptr [rbp+47h+pExceptionObject], ax
0x14002627e  mov     rdx, [rbp+47h+arg_28]
0x140026282  lea     rcx, [rbp+47h+pExceptionObject]
0x140026286  call    ?FormatEvtVariant@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WPEAU_EVT_VARIANT@@@Z; FormatEvtVariant(std::wstring &,wchar_t const *,_EVT_VARIANT *)
0x14002628b  lea     r8, [rbp+47h+pExceptionObject]
0x14002628f  cmp     qword ptr [rbp+47h+var_40+8], 7
0x140026294  cmova   r8, qword ptr [rbp+47h+pExceptionObject]; wchar_t *
0x140026299  mov     rdx, rbx; wchar_t *
0x14002629c  lea     rcx, [rsi+48h]; this
0x1400262a0  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x1400262a5  nop
0x1400262a6  lea     rcx, [rbp+47h+pExceptionObject]
0x1400262aa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400262af  nop
0x1400262b0  mov     rcx, qword ptr [rbp+47h+var_68]
0x1400262b4  test    rcx, rcx
0x1400262b7  jz      short loc_1400262C5
0x1400262b9  mov     rdx, [rbp+47h+var_58]
0x1400262bd  sub     rdx, rcx
0x1400262c0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400262c5  mov     rcx, [rbp+47h+var_28]
0x1400262c9  xor     rcx, rsp; StackCookie
0x1400262cc  call    __security_check_cookie
0x1400262d1  add     rsp, 98h
0x1400262d8  pop     rdi
0x1400262d9  pop     rsi
0x1400262da  pop     rbx
0x1400262db  pop     rbp
0x1400262dc  retn
```

# GetPublisherCommand::PrintMessage(wchar_t const *,void *,ulong)

- ea: `0x14002164c`
- end: `0x1400217af`
- name: `?PrintMessage@GetPublisherCommand@@AEAAXPEB_WPEAXK@Z`
- size: `355`
- prototype: `void(GetPublisherCommand *__hidden this, const wchar_t *, void *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140026bb8`
- `0x140026dc4`
- `0x140026fe8`

## callees

- `0x14000a574`
- `0x14000cabc`
- `0x14000d7e4`
- `0x140010450`
- `0x14002164c`
- `0x1400217b8`
- `0x140021b00`
- `0x140022cec`
- `0x1400293bc`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetPublisherCommand::PrintMessage(GetPublisherCommand *this, const wchar_t *a2, void *a3, DWORD a4)
{
  unsigned int v6; // esi
  const wchar_t *v7; // r8
  int v8; // [rsp+20h] [rbp-39h]
  const char *v9; // [rsp+20h] [rbp-39h]
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-19h] BYREF
  wchar_t *v11[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v12; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v13; // [rsp+80h] [rbp+27h]

  if ( a4 == -1 )
  {
    XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, &ValueName);
  }
  else if ( *((_BYTE *)this + 114) )
  {
    *(_OWORD *)v11 = 0;
    v12 = 0;
    v6 = RenderMessage(a3, 0, a4, v8, 8u, (__int64)v11);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, v6);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v6, 0, 0, v9, 72, 4u, a2);
      throw (EvtException *)pExceptionObject;
    }
    XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, v11[0]);
    if ( v11[0] )
      std::_Deallocate<16>(v11[0], v12 - (unsigned __int64)v11[0]);
  }
  else
  {
    std::to_wstring(v11, a4);
    v7 = (const wchar_t *)v11;
    if ( v13 > 7 )
      v7 = v11[0];
    XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, v7);
    std::wstring::_Tidy_deallocate(v11);
  }
}

```

## disassembly

```asm
0x14002164c  push    rbp
0x14002164e  push    rbx
0x14002164f  push    rsi
0x140021650  push    rdi
0x140021651  lea     rbp, [rsp-3Fh]
0x140021656  sub     rsp, 98h
0x14002165d  mov     rax, cs:__security_cookie
0x140021664  xor     rax, rsp
0x140021667  mov     [rbp+57h+var_28], rax
0x14002166b  mov     rax, r8
0x14002166e  mov     rdi, rdx
0x140021671  mov     rbx, rcx
0x140021674  cmp     r9d, 0FFFFFFFFh
0x140021678  jnz     short loc_14002168F
0x14002167a  add     rcx, 48h ; 'H'; this
0x14002167e  lea     r8, ValueName; wchar_t *
0x140021685  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14002168a  jmp     loc_140021797
0x14002168f  cmp     byte ptr [rcx+72h], 0
0x140021693  jz      loc_140021766
0x140021699  xorps   xmm0, xmm0
0x14002169c  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x1400216a1  mov     [rbp+57h+var_38], 0
0x1400216a9  lea     rcx, [rbp+57h+var_48]
0x1400216ad  mov     qword ptr [rsp+0B0h+var_80], rcx; __int64
0x1400216b2  mov     [rsp+0B0h+var_88], 8; DWORD
0x1400216ba  mov     r8d, r9d; MessageId
0x1400216bd  xor     edx, edx; Event
0x1400216bf  mov     rcx, rax; PublisherMetadata
0x1400216c2  call    ?RenderMessage@@YAKPEAX0KKPEAU_EVT_VARIANT@@KAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; RenderMessage(void *,void *,ulong,ulong,_EVT_VARIANT *,ulong,std::vector<uchar> &)
0x1400216c7  mov     esi, eax
0x1400216c9  test    eax, eax
0x1400216cb  jz      short loc_14002173E
0x1400216cd  lea     rax, WPP_GLOBAL_Control
0x1400216d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400216db  cmp     rcx, rax
0x1400216de  jz      short loc_140021707
0x1400216e0  test    dword ptr [rcx+1Ch], 400000h
0x1400216e7  jz      short loc_140021707
0x1400216e9  cmp     byte ptr [rcx+19h], 2
0x1400216ed  jb      short loc_140021707
0x1400216ef  mov     edx, 0Ah
0x1400216f4  mov     r9d, esi
0x1400216f7  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x1400216fe  mov     rcx, [rcx+10h]
0x140021702  call    WPP_SF_d
0x140021707  mov     [rsp+0B0h+Src], rdi; Src
0x14002170c  mov     [rsp+0B0h+var_80], 4; unsigned int
0x140021714  mov     [rsp+0B0h+var_88], 48h ; 'H'; int
0x14002171c  xor     r9d, r9d; unsigned int
0x14002171f  xor     r8d, r8d; unsigned int
0x140021722  mov     edx, esi; unsigned int
0x140021724  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140021728  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14002172d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140021734  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140021738  call    _CxxThrowException_0
0x14002173e  lea     rcx, [rbx+48h]; this
0x140021742  mov     r8, [rbp+57h+var_48]; wchar_t *
0x140021746  mov     rdx, rdi; wchar_t *
0x140021749  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14002174e  nop
0x14002174f  mov     rcx, [rbp+57h+var_48]
0x140021753  test    rcx, rcx
0x140021756  jz      short loc_140021797
0x140021758  mov     rdx, [rbp+57h+var_38]
0x14002175c  sub     rdx, rcx
0x14002175f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140021764  jmp     short loc_140021797
0x140021766  mov     edx, r9d
0x140021769  lea     rcx, [rbp+57h+var_48]
0x14002176d  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x140021772  nop
0x140021773  lea     r8, [rbp+57h+var_48]
0x140021777  cmp     [rbp+57h+var_30], 7
0x14002177c  cmova   r8, [rbp+57h+var_48]; wchar_t *
0x140021781  lea     rcx, [rbx+48h]; this
0x140021785  mov     rdx, rdi; wchar_t *
0x140021788  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14002178d  nop
0x14002178e  lea     rcx, [rbp+57h+var_48]
0x140021792  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140021797  mov     rcx, [rbp+57h+var_28]
0x14002179b  xor     rcx, rsp; StackCookie
0x14002179e  call    __security_check_cookie
0x1400217a3  add     rsp, 98h
0x1400217aa  pop     rdi
0x1400217ab  pop     rsi
0x1400217ac  pop     rbx
0x1400217ad  pop     rbp
0x1400217ae  retn
```

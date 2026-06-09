# GetPublisherCommand::GetPropertyOpcodeValue(wchar_t const *,void *,ulong,ulong)

- ea: `0x14000b470`
- end: `0x14000b6ca`
- name: `?GetPropertyOpcodeValue@GetPublisherCommand@@AEAAXPEB_WPEAXKK@Z`
- size: `602`
- prototype: `void(GetPublisherCommand *__hidden this, const wchar_t *, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000db10`

## callees

- `0x14000a574`
- `0x14000b470`
- `0x14000cabc`
- `0x14000d7e4`
- `0x140010450`
- `0x1400217b8`
- `0x140021b00`
- `0x140022cec`
- `0x1400257ec`
- `0x140028b68`
- `0x140031810`

## string_xrefs

- `0x14000b63d`: `  task`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetPublisherCommand::GetPropertyOpcodeValue(
        GetPublisherCommand *this,
        const wchar_t *a2,
        void *a3,
        __int64 a4,
        DWORD ArrayIndex)
{
  unsigned int ArrayProperty; // eax
  unsigned int v7; // ebx
  unsigned __int16 *v8; // rbx
  const wchar_t *v9; // r8
  __int64 v10; // rax
  const wchar_t *v11; // r8
  __int64 v12; // rax
  const wchar_t *v13; // r8
  char *v14; // [rsp+20h] [rbp-51h]
  char v15[8]; // [rsp+40h] [rbp-31h] BYREF
  __int128 v16; // [rsp+48h] [rbp-29h] BYREF
  __int64 v17; // [rsp+58h] [rbp-19h]
  wchar_t *v18[3]; // [rsp+60h] [rbp-11h] BYREF
  unsigned __int64 v19; // [rsp+78h] [rbp+7h]
  _BYTE pExceptionObject[40]; // [rsp+80h] [rbp+Fh] BYREF

  v16 = 0;
  v17 = 0;
  *(_QWORD *)v15 = 0;
  ArrayProperty = GetArrayProperty(a3, 0x17u, ArrayIndex, (__int64)&v16, (struct _EVT_VARIANT **)v15);
  v7 = ArrayProperty;
  if ( ArrayProperty )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, ArrayProperty);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v7, 0, 0, v14, 272, 4u, L"value");
    throw (EvtException *)pExceptionObject;
  }
  v8 = *(unsigned __int16 **)v15;
  if ( *(_DWORD *)(*(_QWORD *)v15 + 12LL) )
  {
    if ( *(_DWORD *)(*(_QWORD *)v15 + 12LL) != 8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, v14, 282, 4u, L"value");
      throw (EvtException *)pExceptionObject;
    }
    std::to_wstring(v18, (unsigned int)**(_DWORD **)v15);
    v9 = (const wchar_t *)v18;
    if ( v19 > 7 )
      v9 = v18[0];
    XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), L"value", v9);
    if ( !*((_BYTE *)this + 104) )
    {
      v10 = std::to_wstring(pExceptionObject, *v8);
      std::wstring::operator=(v18, v10);
      std::wstring::_Tidy_deallocate(pExceptionObject);
      v11 = (const wchar_t *)v18;
      if ( v19 > 7 )
        v11 = v18[0];
      XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), L"  task", v11);
      v12 = std::to_wstring(pExceptionObject, v8[1]);
      std::wstring::operator=(v18, v12);
      std::wstring::_Tidy_deallocate(pExceptionObject);
      v13 = (const wchar_t *)v18;
      if ( v19 > 7 )
        v13 = v18[0];
      XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), L"  opcode", v13);
    }
    std::wstring::_Tidy_deallocate(v18);
  }
  if ( (_QWORD)v16 )
    std::_Deallocate<16>(v16, v17 - v16);
}

```

## disassembly

```asm
0x14000b470  mov     [rsp-8+arg_8], rbx
0x14000b475  push    rbp
0x14000b476  push    rsi
0x14000b477  push    rdi
0x14000b478  lea     rbp, [rsp-3Fh]
0x14000b47d  sub     rsp, 0B0h
0x14000b484  mov     rax, cs:__security_cookie
0x14000b48b  xor     rax, rsp
0x14000b48e  mov     [rbp+4Fh+var_18], rax
0x14000b492  mov     rax, r8
0x14000b495  mov     rdi, rcx
0x14000b498  xorps   xmm0, xmm0
0x14000b49b  movdqu  [rbp+4Fh+var_78], xmm0
0x14000b4a0  mov     [rbp+4Fh+var_68], 0
0x14000b4a8  mov     qword ptr [rbp+4Fh+var_80], 0
0x14000b4b0  lea     rcx, [rbp+4Fh+var_80]
0x14000b4b4  mov     [rsp+0C0h+var_A0], rcx; char *
0x14000b4b9  lea     r9, [rbp+4Fh+var_78]
0x14000b4bd  mov     r8d, [rbp+4Fh+ArrayIndex]; ArrayIndex
0x14000b4c1  mov     edx, 17h; PropertyId
0x14000b4c6  mov     rcx, rax; ObjectArray
0x14000b4c9  call    ?GetArrayProperty@@YAKPEAXKKAEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetArrayProperty(void *,ulong,ulong,std::vector<uchar> &,_EVT_VARIANT * &)
0x14000b4ce  mov     ebx, eax
0x14000b4d0  test    eax, eax
0x14000b4d2  jz      short loc_14000B54C
0x14000b4d4  lea     rdx, WPP_GLOBAL_Control
0x14000b4db  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4e2  cmp     rcx, rdx
0x14000b4e5  jz      short loc_14000B50E
0x14000b4e7  test    dword ptr [rcx+1Ch], 400000h
0x14000b4ee  jz      short loc_14000B50E
0x14000b4f0  cmp     byte ptr [rcx+19h], 2
0x14000b4f4  jb      short loc_14000B50E
0x14000b4f6  mov     edx, 14h
0x14000b4fb  mov     r9d, eax
0x14000b4fe  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x14000b505  mov     rcx, [rcx+10h]
0x14000b509  call    WPP_SF_d
0x14000b50e  lea     rdx, aValue; "value"
0x14000b515  mov     [rsp+0C0h+Src], rdx; Src
0x14000b51a  mov     [rsp+0C0h+var_90], 4; unsigned int
0x14000b522  mov     [rsp+0C0h+var_98], 110h; int
0x14000b52a  xor     r9d, r9d; unsigned int
0x14000b52d  xor     r8d, r8d; unsigned int
0x14000b530  mov     edx, ebx; unsigned int
0x14000b532  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000b536  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000b53b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000b542  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000b546  call    _CxxThrowException_0
0x14000b54c  mov     rbx, qword ptr [rbp+4Fh+var_80]
0x14000b550  cmp     dword ptr [rbx+0Ch], 0
0x14000b554  jz      loc_14000B696
0x14000b55a  cmp     dword ptr [rbx+0Ch], 8
0x14000b55e  jz      short loc_14000B5DB
0x14000b560  lea     rdx, WPP_GLOBAL_Control
0x14000b567  mov     ebx, 0Dh
0x14000b56c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b573  cmp     rcx, rdx
0x14000b576  jz      short loc_14000B59D
0x14000b578  test    dword ptr [rcx+1Ch], 400000h
0x14000b57f  jz      short loc_14000B59D
0x14000b581  cmp     byte ptr [rcx+19h], 2
0x14000b585  jb      short loc_14000B59D
0x14000b587  lea     edx, [rbx+8]
0x14000b58a  mov     r9d, ebx
0x14000b58d  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x14000b594  mov     rcx, [rcx+10h]
0x14000b598  call    WPP_SF_d
0x14000b59d  lea     rdx, aValue; "value"
0x14000b5a4  mov     [rsp+0C0h+Src], rdx; Src
0x14000b5a9  mov     [rsp+0C0h+var_90], 4; unsigned int
0x14000b5b1  mov     [rsp+0C0h+var_98], 11Ah; int
0x14000b5b9  xor     r9d, r9d; unsigned int
0x14000b5bc  xor     r8d, r8d; unsigned int
0x14000b5bf  mov     edx, ebx; unsigned int
0x14000b5c1  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000b5c5  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000b5ca  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000b5d1  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000b5d5  call    _CxxThrowException_0
0x14000b5db  mov     edx, [rbx]
0x14000b5dd  lea     rcx, [rbp+4Fh+var_60]
0x14000b5e1  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x14000b5e6  nop
0x14000b5e7  lea     rsi, [rdi+48h]
0x14000b5eb  lea     r8, [rbp+4Fh+var_60]
0x14000b5ef  cmp     [rbp+4Fh+var_48], 7
0x14000b5f4  cmova   r8, [rbp+4Fh+var_60]; wchar_t *
0x14000b5f9  lea     rdx, aValue; "value"
0x14000b600  mov     rcx, rsi; this
0x14000b603  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14000b608  cmp     byte ptr [rdi+68h], 0
0x14000b60c  jnz     short loc_14000B68C
0x14000b60e  movzx   edx, word ptr [rbx]
0x14000b611  lea     rcx, [rbp+4Fh+pExceptionObject]
0x14000b615  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x14000b61a  mov     rdx, rax
0x14000b61d  lea     rcx, [rbp+4Fh+var_60]
0x14000b621  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000b626  lea     rcx, [rbp+4Fh+pExceptionObject]
0x14000b62a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b62f  lea     r8, [rbp+4Fh+var_60]
0x14000b633  cmp     [rbp+4Fh+var_48], 7
0x14000b638  cmova   r8, [rbp+4Fh+var_60]; wchar_t *
0x14000b63d  lea     rdx, aTask; "  task"
0x14000b644  mov     rcx, rsi; this
0x14000b647  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14000b64c  movzx   edx, word ptr [rbx+2]
0x14000b650  lea     rcx, [rbp+4Fh+pExceptionObject]
0x14000b654  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x14000b659  mov     rdx, rax
0x14000b65c  lea     rcx, [rbp+4Fh+var_60]
0x14000b660  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000b665  lea     rcx, [rbp+4Fh+pExceptionObject]
0x14000b669  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b66e  lea     r8, [rbp+4Fh+var_60]
0x14000b672  cmp     [rbp+4Fh+var_48], 7
0x14000b677  cmova   r8, [rbp+4Fh+var_60]; wchar_t *
0x14000b67c  lea     rdx, aOpcode_1; "  opcode"
0x14000b683  mov     rcx, rsi; this
0x14000b686  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x14000b68b  nop
0x14000b68c  lea     rcx, [rbp+4Fh+var_60]
0x14000b690  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000b695  nop
0x14000b696  mov     rcx, qword ptr [rbp+4Fh+var_78]
0x14000b69a  test    rcx, rcx
0x14000b69d  jz      short loc_14000B6AB
0x14000b69f  mov     rdx, [rbp+4Fh+var_68]
0x14000b6a3  sub     rdx, rcx
0x14000b6a6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000b6ab  mov     rcx, [rbp+4Fh+var_18]
0x14000b6af  xor     rcx, rsp; StackCookie
0x14000b6b2  call    __security_check_cookie
0x14000b6b7  mov     rbx, [rsp+0C0h+arg_8]
0x14000b6bf  add     rsp, 0B0h
0x14000b6c6  pop     rdi
0x14000b6c7  pop     rsi
0x14000b6c8  pop     rbp
0x14000b6c9  retn
```

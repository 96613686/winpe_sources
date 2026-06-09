# GetPublisherCommand::GetPropertyArrayElement(wchar_t const *,void *,void *,ulong,ulong,ulong,wchar_t const *)

- ea: `0x140026dc4`
- end: `0x140026fe0`
- name: `?GetPropertyArrayElement@GetPublisherCommand@@AEAAXPEB_WPEAX1KKK0@Z`
- size: `540`
- prototype: `void __fastcall(GetPublisherCommand *__hidden this, const wchar_t *, void *, EVT_OBJECT_ARRAY_PROPERTY_HANDLE ObjectArray, DWORD PropertyId, DWORD ArrayIndex, unsigned int, const wchar_t *)`
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
- `0x140026dc4`
- `0x140028b68`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetPublisherCommand::GetPropertyArrayElement(
        GetPublisherCommand *this,
        const wchar_t *a2,
        void *a3,
        EVT_OBJECT_ARRAY_PROPERTY_HANDLE ObjectArray,
        DWORD PropertyId,
        DWORD ArrayIndex,
        unsigned int a7,
        const wchar_t *a8)
{
  unsigned int ArrayProperty; // eax
  unsigned int v12; // r14d
  int v13; // eax
  int v14; // eax
  const wchar_t *p_pExceptionObject; // r8
  char *v16; // [rsp+20h] [rbp-69h]
  char v17[8]; // [rsp+40h] [rbp-49h] BYREF
  __int128 v18; // [rsp+48h] [rbp-41h] BYREF
  __int64 v19; // [rsp+58h] [rbp-31h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-29h] BYREF
  __m128i si128; // [rsp+70h] [rbp-19h]

  v18 = 0;
  v19 = 0;
  *(_QWORD *)v17 = 0;
  ArrayProperty = GetArrayProperty(ObjectArray, PropertyId, ArrayIndex, (__int64)&v18, (struct _EVT_VARIANT **)v17);
  v12 = ArrayProperty;
  if ( ArrayProperty )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, ArrayProperty);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v12, 0, 0, v16, 228, 4u, a2);
    throw (EvtException *)&pExceptionObject;
  }
  v13 = *(_DWORD *)(*(_QWORD *)v17 + 12LL);
  if ( v13 )
  {
    if ( v13 != a7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, 0, 0, v16, 238, 4u, a2);
      throw (EvtException *)&pExceptionObject;
    }
    if ( v13 == 1 )
    {
      XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, **(const wchar_t ***)v17);
    }
    else if ( PropertyId <= 0x1C && (v14 = 286296096, _bittest(&v14, PropertyId)) )
    {
      GetPublisherCommand::PrintMessage(this, a2, a3, **(_DWORD **)v17);
    }
    else
    {
      pExceptionObject = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(pExceptionObject) = 0;
      FormatEvtVariant(&pExceptionObject, a8);
      p_pExceptionObject = (const wchar_t *)&pExceptionObject;
      if ( si128.m128i_i64[1] > 7uLL )
        p_pExceptionObject = (const wchar_t *)pExceptionObject;
      XmlPrinter::PrintNameValue((GetPublisherCommand *)((char *)this + 72), a2, p_pExceptionObject);
      std::wstring::_Tidy_deallocate(&pExceptionObject);
    }
  }
  if ( (_QWORD)v18 )
    std::_Deallocate<16>(v18, v19 - v18);
}

```

## disassembly

```asm
0x140026dc4  push    rbp
0x140026dc6  push    rbx
0x140026dc7  push    rsi
0x140026dc8  push    rdi
0x140026dc9  push    r14
0x140026dcb  push    r15
0x140026dcd  lea     rbp, [rsp-0Fh]
0x140026dd2  sub     rsp, 98h
0x140026dd9  mov     rax, cs:__security_cookie
0x140026de0  xor     rax, rsp
0x140026de3  mov     [rbp+37h+var_38], rax
0x140026de7  mov     rax, r9
0x140026dea  mov     r15, r8
0x140026ded  mov     rbx, rdx
0x140026df0  mov     rsi, rcx
0x140026df3  xorps   xmm0, xmm0
0x140026df6  movdqu  [rbp+37h+var_78], xmm0
0x140026dfb  mov     [rbp+37h+var_68], 0
0x140026e03  mov     qword ptr [rbp+37h+var_80], 0
0x140026e0b  lea     rcx, [rbp+37h+var_80]
0x140026e0f  mov     [rsp+0C0h+var_A0], rcx; char *
0x140026e14  lea     r9, [rbp+37h+var_78]
0x140026e18  mov     r8d, [rbp+37h+ArrayIndex]; ArrayIndex
0x140026e1c  mov     edi, [rbp+37h+PropertyId]
0x140026e1f  mov     edx, edi; PropertyId
0x140026e21  mov     rcx, rax; ObjectArray
0x140026e24  call    ?GetArrayProperty@@YAKPEAXKKAEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetArrayProperty(void *,ulong,ulong,std::vector<uchar> &,_EVT_VARIANT * &)
0x140026e29  mov     r14d, eax
0x140026e2c  test    eax, eax
0x140026e2e  jz      short loc_140026EA2
0x140026e30  lea     rdx, WPP_GLOBAL_Control
0x140026e37  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e3e  cmp     rcx, rdx
0x140026e41  jz      short loc_140026E6A
0x140026e43  test    dword ptr [rcx+1Ch], 400000h
0x140026e4a  jz      short loc_140026E6A
0x140026e4c  cmp     byte ptr [rcx+19h], 2
0x140026e50  jb      short loc_140026E6A
0x140026e52  mov     edx, 12h
0x140026e57  mov     r9d, eax
0x140026e5a  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x140026e61  mov     rcx, [rcx+10h]
0x140026e65  call    WPP_SF_d
0x140026e6a  mov     [rsp+0C0h+Src], rbx; Src
0x140026e6f  mov     [rsp+0C0h+var_90], 4; unsigned int
0x140026e77  mov     [rsp+0C0h+var_98], 0E4h; int
0x140026e7f  xor     r9d, r9d; unsigned int
0x140026e82  xor     r8d, r8d; unsigned int
0x140026e85  mov     edx, r14d; unsigned int
0x140026e88  lea     rcx, [rbp+37h+pExceptionObject]; this
0x140026e8c  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140026e91  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026e98  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x140026e9c  call    _CxxThrowException_0
0x140026ea2  mov     r8, qword ptr [rbp+37h+var_80]
0x140026ea6  mov     eax, [r8+0Ch]
0x140026eaa  test    eax, eax
0x140026eac  jz      loc_140026FAF
0x140026eb2  cmp     eax, [rbp+37h+arg_30]
0x140026eb5  jz      short loc_140026F2B
0x140026eb7  lea     rdx, WPP_GLOBAL_Control
0x140026ebe  mov     edi, 0Dh
0x140026ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x140026eca  cmp     rcx, rdx
0x140026ecd  jz      short loc_140026EF4
0x140026ecf  test    dword ptr [rcx+1Ch], 400000h
0x140026ed6  jz      short loc_140026EF4
0x140026ed8  cmp     byte ptr [rcx+19h], 2
0x140026edc  jb      short loc_140026EF4
0x140026ede  lea     edx, [rdi+6]
0x140026ee1  mov     r9d, edi
0x140026ee4  lea     r8, WPP_9a4c2ad3d89635fc01093627ef0df9b7_Traceguids
0x140026eeb  mov     rcx, [rcx+10h]
0x140026eef  call    WPP_SF_d
0x140026ef4  mov     [rsp+0C0h+Src], rbx; Src
0x140026ef9  mov     [rsp+0C0h+var_90], 4; unsigned int
0x140026f01  mov     [rsp+0C0h+var_98], 0EEh; int
0x140026f09  xor     r9d, r9d; unsigned int
0x140026f0c  xor     r8d, r8d; unsigned int
0x140026f0f  mov     edx, edi; unsigned int
0x140026f11  lea     rcx, [rbp+37h+pExceptionObject]; this
0x140026f15  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140026f1a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026f21  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x140026f25  call    _CxxThrowException_0
0x140026f2b  cmp     eax, 1
0x140026f2e  jnz     short loc_140026F41
0x140026f30  lea     rcx, [rsi+48h]; this
0x140026f34  mov     r8, [r8]; wchar_t *
0x140026f37  mov     rdx, rbx; wchar_t *
0x140026f3a  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x140026f3f  jmp     short loc_140026FAF
0x140026f41  cmp     edi, 1Ch
0x140026f44  ja      short loc_140026F63
0x140026f46  mov     eax, 11108820h
0x140026f4b  bt      eax, edi
0x140026f4e  jnb     short loc_140026F63
0x140026f50  mov     r9d, [r8]; unsigned int
0x140026f53  mov     r8, r15; void *
0x140026f56  mov     rdx, rbx; wchar_t *
0x140026f59  mov     rcx, rsi; this
0x140026f5c  call    ?PrintMessage@GetPublisherCommand@@AEAAXPEB_WPEAXK@Z; GetPublisherCommand::PrintMessage(wchar_t const *,void *,ulong)
0x140026f61  jmp     short loc_140026FAF
0x140026f63  xorps   xmm0, xmm0
0x140026f66  movups  [rbp+37h+pExceptionObject], xmm0
0x140026f6a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140026f72  movdqu  [rbp+37h+var_50], xmm1
0x140026f77  xor     eax, eax
0x140026f79  mov     word ptr [rbp+37h+pExceptionObject], ax
0x140026f7d  mov     rdx, [rbp+37h+arg_38]
0x140026f81  lea     rcx, [rbp+37h+pExceptionObject]
0x140026f85  call    ?FormatEvtVariant@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WPEAU_EVT_VARIANT@@@Z; FormatEvtVariant(std::wstring &,wchar_t const *,_EVT_VARIANT *)
0x140026f8a  lea     r8, [rbp+37h+pExceptionObject]
0x140026f8e  cmp     qword ptr [rbp+37h+var_50+8], 7
0x140026f93  cmova   r8, qword ptr [rbp+37h+pExceptionObject]; wchar_t *
0x140026f98  lea     rcx, [rsi+48h]; this
0x140026f9c  mov     rdx, rbx; wchar_t *
0x140026f9f  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x140026fa4  nop
0x140026fa5  lea     rcx, [rbp+37h+pExceptionObject]
0x140026fa9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140026fae  nop
0x140026faf  mov     rcx, qword ptr [rbp+37h+var_78]
0x140026fb3  test    rcx, rcx
0x140026fb6  jz      short loc_140026FC4
0x140026fb8  mov     rdx, [rbp+37h+var_68]
0x140026fbc  sub     rdx, rcx
0x140026fbf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140026fc4  mov     rcx, [rbp+37h+var_38]
0x140026fc8  xor     rcx, rsp; StackCookie
0x140026fcb  call    __security_check_cookie
0x140026fd0  add     rsp, 98h
0x140026fd7  pop     r15
0x140026fd9  pop     r14
0x140026fdb  pop     rdi
0x140026fdc  pop     rsi
0x140026fdd  pop     rbx
0x140026fde  pop     rbp
0x140026fdf  retn
```

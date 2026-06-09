# CProfileProps::Initialize(void)

- ea: `0x180028d6c`
- end: `0x1800290da`
- name: `?Initialize@CProfileProps@@IEAAXXZ`
- size: `878`
- prototype: `void __fastcall(CProfileProps *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800289a8`

## callees

- `0x180001e2c`
- `0x180001e9c`
- `0x1800036ac`
- `0x18000cf1c`
- `0x180012a70`
- `0x180028d6c`
- `0x180029648`
- `0x180029708`
- `0x1800297ac`
- `0x180029844`
- `0x18002d840`

## string_xrefs

- `0x180028e52`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CProfileProps::Initialize(CProfileProps *this, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 i; // rdi
  _BYTE v8[8]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v9; // [rsp+28h] [rbp-50h] BYREF
  int v10; // [rsp+38h] [rbp-40h]

  if ( dword_1800407E0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800407E0);
    if ( dword_1800407E0 == -1 )
    {
      xmmword_180040560 = xmmword_1800383A0;
      dword_180040570 = 2;
      qword_180040578 = (__int64)L"Name";
      dword_180040580 = 0;
      xmmword_180040588 = xmmword_180038388;
      dword_180040598 = 3;
      qword_1800405A0 = (__int64)L"Priority";
      dword_1800405A8 = 1;
      xmmword_1800405B0 = xmmword_180038370;
      dword_1800405C0 = 4;
      qword_1800405C8 = (__int64)L"Security";
      dword_1800405D0 = 2;
      xmmword_1800405D8 = xmmword_180038358;
      dword_1800405E8 = 5;
      qword_1800405F0 = (__int64)L"Type";
      dword_1800405F8 = 3;
      xmmword_180040600 = xmmword_180038340;
      dword_180040610 = 6;
      qword_180040618 = (__int64)L"WPS";
      dword_180040620 = 4;
      xmmword_180040628 = xmmword_180038328;
      dword_180040638 = 8;
      qword_180040640 = (__int64)L"Managed";
      dword_180040648 = 5;
      xmmword_180040650 = xmmword_180038310;
      dword_180040660 = 9;
      qword_180040668 = (__int64)L"Connect Mode";
      dword_180040670 = 6;
      xmmword_180040678 = xmmword_1800382F8;
      dword_180040688 = 10;
      qword_180040690 = (__int64)L"Guid";
      dword_180040698 = 7;
      xmmword_1800406A0 = xmmword_1800382E0;
      dword_1800406B0 = 11;
      qword_1800406B8 = (__int64)L"Interface";
      dword_1800406C0 = 8;
      xmmword_1800406C8 = xmmword_1800382C8;
      dword_1800406D8 = 12;
      qword_1800406E0 = (__int64)L"Adhoc";
      dword_1800406E8 = 9;
      Init_thread_footer(&dword_1800407E0);
    }
  }
  *((_DWORD *)this + 2) = 10;
  LOBYTE(a3) = 1;
  ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(
    (char *)this + 16,
    257,
    a3);
  LOBYTE(v4) = 1;
  ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(
    (char *)this + 88,
    257,
    v4);
  LOBYTE(v5) = 1;
  ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(
    (char *)this + 160,
    257,
    v5);
  LOBYTE(v6) = 1;
  ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(
    (char *)this + 232,
    257,
    v6);
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
  {
    v9 = *(__int128 *)((char *)&xmmword_180040560 + 40 * i);
    v10 = *((_DWORD *)&xmmword_180040560 + 10 * i + 4);
    WTL::CString::CString((WTL::CString *)v8, *((const unsigned __int16 **)&xmmword_180040560 + 5 * i + 3));
    ATL::CAtlMap<unsigned int,_tagpropertykey,ATL::CElementTraits<unsigned int>,CStructTraits<_tagpropertykey>>::SetAt(
      (char *)this + 16,
      (unsigned int)i,
      &v9);
    ATL::CAtlMap<_tagpropertykey,unsigned int,CStructTraits<_tagpropertykey>,ATL::CElementTraits<unsigned int>>::SetAt(
      (char *)this + 88,
      &v9,
      (unsigned int)i);
    ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::SetAt(
      (char *)this + 160,
      v8,
      &v9);
    ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::SetAt(
      (char *)this + 232,
      &v9,
      v8);
    WTL::CString::~CString((WTL::CString *)v8);
  }
}

```

## disassembly

```asm
0x180028d6c  mov     [rsp+arg_8], rbx
0x180028d71  mov     [rsp+arg_10], rbp
0x180028d76  push    rsi
0x180028d77  push    rdi
0x180028d78  push    r12
0x180028d7a  push    r14
0x180028d7c  push    r15
0x180028d7e  sub     rsp, 50h
0x180028d82  mov     rax, cs:__security_cookie
0x180028d89  xor     rax, rsp
0x180028d8c  mov     [rsp+78h+var_38], rax
0x180028d91  mov     rbx, rcx
0x180028d94  mov     edx, cs:_tls_index
0x180028d9a  mov     rax, gs:58h
0x180028da3  mov     ecx, 4
0x180028da8  mov     rax, [rax+rdx*8]
0x180028dac  mov     eax, [rcx+rax]
0x180028daf  cmp     cs:dword_1800407E0, eax
0x180028db5  jle     loc_180028FD4
0x180028dbb  lea     rcx, dword_1800407E0
0x180028dc2  call    _Init_thread_header
0x180028dc7  cmp     cs:dword_1800407E0, 0FFFFFFFFh
0x180028dce  jnz     loc_180028FD4
0x180028dd4  movups  xmm0, cs:xmmword_1800383A0
0x180028ddb  movaps  cs:xmmword_180040560, xmm0
0x180028de2  mov     eax, cs:dword_1800383B0
0x180028de8  mov     cs:dword_180040570, eax
0x180028dee  lea     rax, aName; "Name"
0x180028df5  mov     cs:qword_180040578, rax
0x180028dfc  mov     cs:dword_180040580, 0
0x180028e06  movups  xmm0, cs:xmmword_180038388
0x180028e0d  movups  cs:xmmword_180040588, xmm0
0x180028e14  mov     eax, cs:dword_180038398
0x180028e1a  mov     cs:dword_180040598, eax
0x180028e20  lea     rax, aPriority; "Priority"
0x180028e27  mov     cs:qword_1800405A0, rax
0x180028e2e  mov     cs:dword_1800405A8, 1
0x180028e38  movups  xmm0, cs:xmmword_180038370
0x180028e3f  movaps  cs:xmmword_1800405B0, xmm0
0x180028e46  mov     eax, cs:dword_180038380
0x180028e4c  mov     cs:dword_1800405C0, eax
0x180028e52  lea     rax, aSecurity; "Security"
0x180028e59  mov     cs:qword_1800405C8, rax
0x180028e60  mov     cs:dword_1800405D0, 2
0x180028e6a  movups  xmm0, cs:xmmword_180038358
0x180028e71  movups  cs:xmmword_1800405D8, xmm0
0x180028e78  mov     eax, cs:dword_180038368
0x180028e7e  mov     cs:dword_1800405E8, eax
0x180028e84  lea     rax, aType; "Type"
0x180028e8b  mov     cs:qword_1800405F0, rax
0x180028e92  mov     cs:dword_1800405F8, 3
0x180028e9c  movups  xmm0, cs:xmmword_180038340
0x180028ea3  movaps  cs:xmmword_180040600, xmm0
0x180028eaa  mov     eax, cs:dword_180038350
0x180028eb0  mov     cs:dword_180040610, eax
0x180028eb6  lea     rax, aWps; "WPS"
0x180028ebd  mov     cs:qword_180040618, rax
0x180028ec4  mov     cs:dword_180040620, 4
0x180028ece  movups  xmm0, cs:xmmword_180038328
0x180028ed5  movups  cs:xmmword_180040628, xmm0
0x180028edc  mov     eax, cs:dword_180038338
0x180028ee2  mov     cs:dword_180040638, eax
0x180028ee8  lea     rax, aManaged; "Managed"
0x180028eef  mov     cs:qword_180040640, rax
0x180028ef6  mov     cs:dword_180040648, 5
0x180028f00  movups  xmm0, cs:xmmword_180038310
0x180028f07  movaps  cs:xmmword_180040650, xmm0
0x180028f0e  mov     eax, cs:dword_180038320
0x180028f14  mov     cs:dword_180040660, eax
0x180028f1a  lea     rax, aConnectMode; "Connect Mode"
0x180028f21  mov     cs:qword_180040668, rax
0x180028f28  mov     cs:dword_180040670, 6
0x180028f32  movups  xmm0, cs:xmmword_1800382F8
0x180028f39  movups  cs:xmmword_180040678, xmm0
0x180028f40  mov     eax, cs:dword_180038308
0x180028f46  mov     cs:dword_180040688, eax
0x180028f4c  lea     rax, aGuid; "Guid"
0x180028f53  mov     cs:qword_180040690, rax
0x180028f5a  mov     cs:dword_180040698, 7
0x180028f64  movups  xmm0, cs:xmmword_1800382E0
0x180028f6b  movaps  cs:xmmword_1800406A0, xmm0
0x180028f72  mov     eax, cs:dword_1800382F0
0x180028f78  mov     cs:dword_1800406B0, eax
0x180028f7e  lea     rax, aInterface; "Interface"
0x180028f85  mov     cs:qword_1800406B8, rax
0x180028f8c  mov     cs:dword_1800406C0, 8
0x180028f96  movups  xmm0, cs:xmmword_1800382C8
0x180028f9d  movups  cs:xmmword_1800406C8, xmm0
0x180028fa4  mov     eax, cs:dword_1800382D8
0x180028faa  mov     cs:dword_1800406D8, eax
0x180028fb0  lea     rax, aAdhoc; "Adhoc"
0x180028fb7  mov     cs:qword_1800406E0, rax
0x180028fbe  mov     cs:dword_1800406E8, 9
0x180028fc8  lea     rcx, dword_1800407E0
0x180028fcf  call    _Init_thread_footer
0x180028fd4  mov     dword ptr [rbx+8], 0Ah
0x180028fdb  mov     r8b, 1
0x180028fde  mov     edi, 101h
0x180028fe3  mov     edx, edi
0x180028fe5  lea     rcx, [rbx+10h]
0x180028fe9  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x180028fee  mov     r8b, 1
0x180028ff1  mov     edx, edi
0x180028ff3  lea     rcx, [rbx+58h]
0x180028ff7  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x180028ffc  lea     r14, [rbx+0A0h]
0x180029003  mov     r8b, 1
0x180029006  mov     edx, edi
0x180029008  mov     rcx, r14
0x18002900b  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x180029010  lea     r15, [rbx+0E8h]
0x180029017  mov     r8b, 1
0x18002901a  mov     edx, edi
0x18002901c  mov     rcx, r15
0x18002901f  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x180029024  xor     edi, edi
0x180029026  cmp     [rbx+8], edi
0x180029029  jbe     loc_1800290B4
0x18002902f  lea     r12, xmmword_180040560
0x180029036  lea     rdx, [rdi+rdi*4]
0x18002903a  movups  xmm0, xmmword ptr [r12+rdx*8]
0x18002903f  movups  [rsp+78h+var_50], xmm0
0x180029044  mov     eax, [r12+rdx*8+10h]
0x180029049  mov     [rsp+78h+var_40], eax
0x18002904d  mov     rdx, [r12+rdx*8+18h]; Source
0x180029052  lea     rcx, [rsp+78h+var_58]; this
0x180029057  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18002905c  nop
0x18002905d  lea     r8, [rsp+78h+var_50]
0x180029062  mov     edx, edi
0x180029064  lea     rcx, [rbx+10h]
0x180029068  call    ?SetAt@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAAPEAU__POSITION@@IAEBU_tagpropertykey@@@Z; ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::SetAt(uint,_tagpropertykey const &)
0x18002906d  mov     r8d, edi
0x180029070  lea     rdx, [rsp+78h+var_50]
0x180029075  lea     rcx, [rbx+58h]
0x180029079  call    ?SetAt@?$CAtlMap@U_tagpropertykey@@IV?$CStructTraits@U_tagpropertykey@@@@V?$CElementTraits@I@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBU_tagpropertykey@@I@Z; ATL::CAtlMap<_tagpropertykey,uint,CStructTraits<_tagpropertykey>,ATL::CElementTraits<uint>>::SetAt(_tagpropertykey const &,uint)
0x18002907e  lea     r8, [rsp+78h+var_50]
0x180029083  lea     rdx, [rsp+78h+var_58]
0x180029088  mov     rcx, r14
0x18002908b  call    ?SetAt@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAAPEAU__POSITION@@AEBVCString@WTL@@AEBU_tagpropertykey@@@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::SetAt(WTL::CString const &,_tagpropertykey const &)
0x180029090  lea     r8, [rsp+78h+var_58]
0x180029095  lea     rdx, [rsp+78h+var_50]
0x18002909a  mov     rcx, r15
0x18002909d  call    ?SetAt@?$CAtlMap@U_tagpropertykey@@VCString@WTL@@V?$CStructTraits@U_tagpropertykey@@@@VCStringTraits@@@ATL@@QEAAPEAU__POSITION@@AEBU_tagpropertykey@@AEBVCString@WTL@@@Z; ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::SetAt(_tagpropertykey const &,WTL::CString const &)
0x1800290a2  nop
0x1800290a3  lea     rcx, [rsp+78h+var_58]; this
0x1800290a8  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800290ad  inc     edi
0x1800290af  cmp     edi, [rbx+8]
0x1800290b2  jb      short loc_180029036
0x1800290b4  mov     rcx, [rsp+78h+var_38]
0x1800290b9  xor     rcx, rsp; StackCookie
0x1800290bc  call    __security_check_cookie
0x1800290c1  lea     r11, [rsp+78h+var_28]
0x1800290c6  mov     rbx, [r11+38h]
0x1800290ca  mov     rbp, [r11+40h]
0x1800290ce  mov     rsp, r11
0x1800290d1  pop     r15
0x1800290d3  pop     r14
0x1800290d5  pop     r12
0x1800290d7  pop     rdi
0x1800290d8  pop     rsi
0x1800290d9  retn
```

# GetPostData(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,tagVARIANT *)

- ea: `0x180021e18`
- end: `0x180022044`
- name: `?GetPostData@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagVARIANT@@@Z`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800224dc`

## callees

- `0x180002da0`
- `0x18000a1a8`
- `0x18000ba8c`
- `0x18000cc9c`
- `0x18000e870`
- `0x180012654`
- `0x18001b3b4`
- `0x180021a64`
- `0x180021a90`
- `0x180021e18`
- `0x180053890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021faf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021faf`
- `OLEAUT32!__imp_VariantInit` at `0x180021ecc`
- `OLEAUT32!__imp_VariantInit` at `0x180021ecc`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180021f22`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180021f22`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180021fd7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180021fd7`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180021edc`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180021edc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021ef9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021ef9`

## string_xrefs

- `0x180021f30`: `hr = SafeArrayAccessData(psa, reinterpret_cast<LPVOID*>(&pPostData))`
- `0x180021fba`: `hr = SafeCopyMemory(pPostData, cElems, CW2A(wstrPostData.GetBuffer(), CP_UTF8), cElems)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetPostData(_QWORD *a1, VARIANTARG *a2)
{
  SIZE_T v4; // rbx
  SAFEARRAY *Vector; // rdi
  rsize_t v6; // r15
  HLOCAL v7; // rbx
  HRESULT v8; // eax
  __int64 Buffer; // rax
  errno_t v10; // r15d
  unsigned int v11; // ebx
  char *v13; // [rsp+20h] [rbp-E0h]
  HRESULT v14; // [rsp+30h] [rbp-D0h] BYREF
  void *ppvData[3]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v16[6]; // [rsp+50h] [rbp-B0h] BYREF
  void *Source; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v18[136]; // [rsp+88h] [rbp-78h] BYREF

  v16[4] = a1;
  v14 = 0;
  v4 = *(unsigned int *)(*a1 - 16LL);
  memset(ppvData, 0, sizeof(ppvData));
  v16[0] = "GetPostData";
  v16[1] = &v14;
  v16[2] = 0;
  v16[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
    "GetPostData",
    (const char *)0x2A,
    0,
    (const unsigned __int16 *)v13);
  if ( a2 )
  {
    VariantInit(a2);
    Vector = SafeArrayCreateVector(0x11u, 0, v4);
    if ( Vector
      && (v6 = v4,
          v7 = LocalAlloc(0x40u, v4),
          Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(ppvData),
          (ppvData[0] = v7) != 0) )
    {
      v8 = SafeArrayAccessData(Vector, ppvData);
      v14 = v8;
      if ( v8 >= 0 )
      {
        Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(a1);
        Source = v18;
        ATL::CW2AEX<128>::Init(&Source, Buffer, 65001);
        v10 = memcpy_s_0(ppvData[0], v6, Source, v6);
        v14 = v10 != 0 ? 0x8000FFFF : 0;
        if ( Source != v18 )
          free(Source);
        if ( v10 )
        {
          Telemetry::IfFailExit(
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
            "GetPostData",
            0x3Du,
            v10 != 0 ? 0x8000FFFF : 0,
            "hr = SafeCopyMemory(pPostData, cElems, CW2A(wstrPostData.GetBuffer(), CP_UTF8), cElems)");
        }
        else
        {
          v14 = SafeArrayUnaccessData(Vector);
          a2->vt = 8209;
          a2->llVal = (LONGLONG)Vector;
        }
      }
      else
      {
        Telemetry::IfFailExit(
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
          "GetPostData",
          0x3Au,
          v8,
          "hr = SafeArrayAccessData(psa, reinterpret_cast<LPVOID*>(&pPostData))");
      }
    }
    else
    {
      v14 = -2147024882;
    }
  }
  else
  {
    v14 = -2147467261;
  }
  v11 = v14;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v16);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  ATL::CStringData::Release((ATL::CStringData *)(*a1 - 24LL));
  return v11;
}

```

## disassembly

```asm
0x180021e18  mov     [rsp-8+arg_10], rbx
0x180021e1d  mov     [rsp-8+arg_18], rsi
0x180021e22  push    rbp
0x180021e23  push    rdi
0x180021e24  push    r13
0x180021e26  push    r14
0x180021e28  push    r15
0x180021e2a  lea     rbp, [rsp-20h]
0x180021e2f  sub     rsp, 120h
0x180021e36  mov     rax, cs:__security_cookie
0x180021e3d  xor     rax, rsp
0x180021e40  mov     [rbp+40h+var_30], rax
0x180021e44  mov     rsi, rdx
0x180021e47  mov     r14, rcx
0x180021e4a  mov     [rsp+140h+var_D0], rcx
0x180021e4f  mov     [rsp+140h+var_110], 0
0x180021e57  mov     rax, [rcx]
0x180021e5a  mov     ebx, [rax-10h]
0x180021e5d  mov     [rsp+140h+ppvData], 0
0x180021e66  mov     [rsp+140h+var_F8], 0
0x180021e6f  mov     [rsp+140h+var_100], 0
0x180021e78  lea     r13, aGetpostdata; "GetPostData"
0x180021e7f  mov     [rsp+140h+var_F0], r13
0x180021e84  lea     rax, [rsp+140h+var_110]
0x180021e89  mov     [rsp+140h+var_E8], rax
0x180021e8e  mov     [rsp+140h+var_E0], 0
0x180021e97  mov     [rsp+140h+var_D8], 0
0x180021ea0  xor     r9d, r9d; unsigned int
0x180021ea3  lea     r8d, [r9+2Ah]; char *
0x180021ea7  mov     rdx, r13; char *
0x180021eaa  lea     rcx, aClientcoreDsEx_4; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180021eb1  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180021eb6  nop
0x180021eb7  test    rsi, rsi
0x180021eba  jnz     short loc_180021EC9
0x180021ebc  mov     [rsp+140h+var_110], 80004003h
0x180021ec4  jmp     loc_180021FF4
0x180021ec9  mov     rcx, rsi; pvarg
0x180021ecc  call    cs:__imp_VariantInit
0x180021ed2  mov     ecx, 11h; vt
0x180021ed7  mov     r8d, ebx; cElements
0x180021eda  xor     edx, edx; lLbound
0x180021edc  call    cs:__imp_SafeArrayCreateVector
0x180021ee2  mov     rdi, rax
0x180021ee5  test    rax, rax
0x180021ee8  jz      loc_180021FEC
0x180021eee  mov     r15, rbx
0x180021ef1  mov     rdx, rbx; uBytes
0x180021ef4  mov     ecx, 40h ; '@'; uFlags
0x180021ef9  call    cs:__imp_LocalAlloc
0x180021eff  mov     rbx, rax
0x180021f02  lea     rcx, [rsp+140h+ppvData]
0x180021f07  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180021f0c  mov     [rsp+140h+ppvData], rbx
0x180021f11  test    rbx, rbx
0x180021f14  jz      loc_180021FEC
0x180021f1a  lea     rdx, [rsp+140h+ppvData]; ppvData
0x180021f1f  mov     rcx, rdi; psa
0x180021f22  call    cs:__imp_SafeArrayAccessData
0x180021f28  mov     [rsp+140h+var_110], eax
0x180021f2c  test    eax, eax
0x180021f2e  jns     short loc_180021F59
0x180021f30  lea     r8, aHrSafearrayacc; "hr = SafeArrayAccessData(psa, reinterpr"...
0x180021f37  mov     [rsp+140h+var_120], r8; char *
0x180021f3c  mov     r9d, eax; int
0x180021f3f  mov     r8d, 3Ah ; ':'; unsigned int
0x180021f45  mov     rdx, r13; char *
0x180021f48  lea     rcx, aClientcoreDsEx_4; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180021f4f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180021f54  jmp     loc_180021FF4
0x180021f59  mov     rcx, r14
0x180021f5c  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180021f61  lea     rcx, [rbp+40h+var_B8]
0x180021f65  mov     [rbp+40h+Source], rcx
0x180021f69  mov     r8d, 0FDE9h
0x180021f6f  mov     rdx, rax
0x180021f72  lea     rcx, [rbp+40h+Source]
0x180021f76  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x180021f7b  mov     r9, r15; SourceSize
0x180021f7e  mov     r8, [rbp+40h+Source]; Source
0x180021f82  mov     rdx, r15; DestinationSize
0x180021f85  mov     rcx, [rsp+140h+ppvData]; Destination
0x180021f8a  call    memcpy_s_0
0x180021f8f  mov     r15d, eax
0x180021f92  mov     ecx, eax
0x180021f94  neg     ecx
0x180021f96  sbb     ebx, ebx
0x180021f98  and     ebx, 8000FFFFh
0x180021f9e  mov     [rsp+140h+var_110], ebx
0x180021fa2  mov     rcx, [rbp+40h+Source]; Block
0x180021fa6  lea     rax, [rbp+40h+var_B8]
0x180021faa  cmp     rcx, rax
0x180021fad  jz      short loc_180021FB5
0x180021faf  call    cs:__imp_free
0x180021fb5  test    r15d, r15d
0x180021fb8  jz      short loc_180021FD4
0x180021fba  lea     rax, aHrSafecopymemo_1; "hr = SafeCopyMemory(pPostData, cElems, "...
0x180021fc1  mov     [rsp+140h+var_120], rax
0x180021fc6  mov     r9d, ebx
0x180021fc9  mov     r8d, 3Dh ; '='
0x180021fcf  jmp     loc_180021F45
0x180021fd4  mov     rcx, rdi; psa
0x180021fd7  call    cs:__imp_SafeArrayUnaccessData
0x180021fdd  mov     [rsp+140h+var_110], eax
0x180021fe1  mov     word ptr [rsi], 2011h
0x180021fe6  mov     [rsi+8], rdi
0x180021fea  jmp     short loc_180021FF4
0x180021fec  mov     [rsp+140h+var_110], 8007000Eh
0x180021ff4  mov     ebx, [rsp+140h+var_110]
0x180021ff8  lea     rcx, [rsp+140h+var_F0]
0x180021ffd  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180022002  nop
0x180022003  lea     rcx, [rsp+140h+ppvData]
0x180022008  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18002200d  nop
0x18002200e  mov     rcx, [r14]
0x180022011  sub     rcx, 18h; this
0x180022015  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002201a  mov     eax, ebx
0x18002201c  mov     rcx, [rbp+40h+var_30]
0x180022020  xor     rcx, rsp; StackCookie
0x180022023  call    __security_check_cookie
0x180022028  lea     r11, [rsp+140h+var_20]
0x180022030  mov     rbx, [r11+40h]
0x180022034  mov     rsi, [r11+48h]
0x180022038  mov     rsp, r11
0x18002203b  pop     r15
0x18002203d  pop     r14
0x18002203f  pop     r13
0x180022041  pop     rdi
0x180022042  pop     rbp
0x180022043  retn
```

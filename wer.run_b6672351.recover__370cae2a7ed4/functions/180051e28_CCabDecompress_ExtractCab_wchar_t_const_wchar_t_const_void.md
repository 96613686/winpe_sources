# CCabDecompress::ExtractCab(wchar_t const *,wchar_t const *,void *)

- ea: `0x180051e28`
- end: `0x180052212`
- name: `?ExtractCab@CCabDecompress@@QEAAJPEB_W0PEAX@Z`
- size: `1002`
- prototype: `__int64 __fastcall(CCabDecompress *__hidden this, LPCWCH lpWideCharStr, const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800748bc`

## callees

- `0x180004c64`
- `0x18000da00`
- `0x1800170b0`
- `0x180020680`
- `0x18002cf3c`
- `0x180051e28`
- `0x180052218`
- `0x180053300`
- `0x18006852c`
- `0x18009767c`
- `0x1800a06f0`
- `0x1800a0e7c`

## import_xrefs

- `ntdll!strrchr` at `0x180051f2e`
- `ntdll!strrchr` at `0x180051f2e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180052125`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180052125`
- `Cabinet!__imp_FDICreate` at `0x180052062`
- `Cabinet!__imp_FDICreate` at `0x180052062`
- `Cabinet!__imp_FDICopy` at `0x180052110`
- `Cabinet!__imp_FDICopy` at `0x180052110`
- `Cabinet!__imp_FDIDestroy` at `0x180052179`
- `Cabinet!__imp_FDIDestroy` at `0x180052179`

## pseudocode

```c
__int64 __fastcall CCabDecompress::ExtractCab(HANDLE *this, LPCWCH lpWideCharStr, wchar_t *a3, void *a4)
{
  unsigned int v8; // r8d
  unsigned int v9; // edi
  int v10; // eax
  wchar_t *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  char *v14; // rax
  _BYTE *v15; // r10
  HFDI v16; // rsi
  ERF perf; // [rsp+50h] [rbp-B0h] BYREF
  char Str[272]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR pszCabinet[272]; // [rsp+170h] [rbp+70h] BYREF

  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  if ( lpWideCharStr && a3 )
  {
    Str[0] = 0;
    pszCabinet[0] = 0;
    if ( !UtilPathIsDirectory(a3) )
    {
      v9 = -2147024809;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, a3);
      return v9;
    }
    v10 = WideToAnsi(lpWideCharStr, Str, v8);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return v9;
      v12 = 76;
      goto LABEL_11;
    }
    v14 = strrchr(Str, 92);
    if ( v14 )
    {
      v10 = StringCchCopyA(pszCabinet, 0x104u, v14 + 1);
      v9 = v10;
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v12 = 78;
        goto LABEL_11;
      }
      *v15 = 0;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               this + 1,
                               a3) )
      {
        v9 = -2147024882;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v12 = 79;
        v13 = 2147942414LL;
LABEL_12:
        WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v13);
        return v9;
      }
      *this = a4;
      v16 = FDICreate(
              CCabDecompress::static_FDIAlloc,
              CCabDecompress::static_FDIFree,
              CCabDecompress::static_FDIOpen,
              CCabDecompress::static_FDIRead,
              CCabDecompress::static_FDIWrite,
              CCabDecompress::static_FDIClose,
              CCabDecompress::static_FDISeek,
              1,
              &perf);
      if ( !v16 )
      {
        v10 = FDIGetHRESULTFromERF(&perf);
        v9 = v10;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v9;
        v12 = 80;
        goto LABEL_11;
      }
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          (unsigned int)Str,
          (__int64)pszCabinet);
      if ( FDICopy(v16, pszCabinet, Str, 0, CCabDecompress::static_FDINotify, 0, this) )
      {
        v9 = 0;
      }
      else
      {
        if ( WaitForSingleObject(*this, 0) )
          v9 = FDIGetHRESULTFromERF(&perf);
        else
          v9 = -2147467260;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v9);
      }
      if ( !FDIDestroy(v16) && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = FDIGetHRESULTFromERF(&perf);
        v11 = WPP_GLOBAL_Control;
        v12 = 83;
LABEL_11:
        v13 = (unsigned int)v10;
        goto LABEL_12;
      }
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, Str);
    }
  }
  else
  {
    v9 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x180051e28  mov     [rsp-8+arg_18], rbx
0x180051e2d  push    rbp
0x180051e2e  push    rsi
0x180051e2f  push    rdi
0x180051e30  push    r14
0x180051e32  push    r15
0x180051e34  lea     rbp, [rsp-190h]
0x180051e3c  sub     rsp, 290h
0x180051e43  mov     rax, cs:__security_cookie
0x180051e4a  xor     rax, rsp
0x180051e4d  mov     [rbp+1B0h+var_30], rax
0x180051e54  xor     eax, eax
0x180051e56  mov     r15, r9
0x180051e59  mov     qword ptr [rsp+2B0h+var_260.erfOper], rax
0x180051e5e  mov     rsi, r8
0x180051e61  mov     [rsp+2B0h+var_260.fError], eax
0x180051e65  mov     rbx, rdx
0x180051e68  mov     r14, rcx
0x180051e6b  test    rdx, rdx
0x180051e6e  jz      loc_1800521B6
0x180051e74  test    r8, r8
0x180051e77  jz      loc_1800521B6
0x180051e7d  mov     rcx, r8; wchar_t *
0x180051e80  mov     [rsp+2B0h+Str], al
0x180051e84  mov     [rbp+1B0h+pszCabinet], al
0x180051e87  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x180051e8c  test    al, al
0x180051e8e  jnz     short loc_180051ED3
0x180051e90  mov     edi, 80070057h
0x180051e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e9c  lea     rbx, WPP_GLOBAL_Control
0x180051ea3  cmp     rcx, rbx
0x180051ea6  jz      loc_1800521E9
0x180051eac  test    byte ptr [rcx+1Ch], 1
0x180051eb0  jz      loc_1800521E9
0x180051eb6  mov     rcx, [rcx+10h]
0x180051eba  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x180051ec1  mov     edx, 4Bh ; 'K'
0x180051ec6  mov     r9, rsi
0x180051ec9  call    WPP_SF_S
0x180051ece  jmp     loc_1800521E9
0x180051ed3  lea     rdx, [rsp+2B0h+Str]; lpMultiByteStr
0x180051ed8  mov     rcx, rbx; lpWideCharStr
0x180051edb  call    ?WideToAnsi@@YAJPEB_WPEADK@Z; WideToAnsi(wchar_t const *,char *,ulong)
0x180051ee0  mov     edi, eax
0x180051ee2  test    eax, eax
0x180051ee4  jns     short loc_180051F24
0x180051ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180051eed  lea     rbx, WPP_GLOBAL_Control
0x180051ef4  cmp     rcx, rbx
0x180051ef7  jz      loc_1800521E9
0x180051efd  test    byte ptr [rcx+1Ch], 1
0x180051f01  jz      loc_1800521E9
0x180051f07  mov     edx, 4Ch ; 'L'
0x180051f0c  mov     r9d, eax
0x180051f0f  mov     rcx, [rcx+10h]
0x180051f13  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x180051f1a  call    WPP_SF_d
0x180051f1f  jmp     loc_1800521E9
0x180051f24  mov     edx, 5Ch ; '\'; Ch
0x180051f29  lea     rcx, [rsp+2B0h+Str]; Str
0x180051f2e  call    cs:__imp_strrchr
0x180051f35  nop     dword ptr [rax+rax+00h]
0x180051f3a  test    rax, rax
0x180051f3d  jnz     short loc_180051F7D
0x180051f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180051f46  lea     rbx, WPP_GLOBAL_Control
0x180051f4d  cmp     rcx, rbx
0x180051f50  jz      loc_1800521E9
0x180051f56  test    byte ptr [rcx+1Ch], 1
0x180051f5a  jz      loc_1800521E9
0x180051f60  mov     rcx, [rcx+10h]
0x180051f64  lea     edx, [rax+4Dh]
0x180051f67  lea     r9, [rsp+2B0h+Str]
0x180051f6c  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x180051f73  call    WPP_SF_s
0x180051f78  jmp     loc_1800521E9
0x180051f7d  lea     r10, [rax+1]
0x180051f81  mov     edx, 104h; unsigned __int64
0x180051f86  mov     r8, r10; char *
0x180051f89  lea     rcx, [rbp+1B0h+pszCabinet]; char *
0x180051f8d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180051f92  mov     edi, eax
0x180051f94  test    eax, eax
0x180051f96  jns     short loc_180051FC3
0x180051f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180051f9f  lea     rbx, WPP_GLOBAL_Control
0x180051fa6  cmp     rcx, rbx
0x180051fa9  jz      loc_1800521E9
0x180051faf  test    byte ptr [rcx+1Ch], 1
0x180051fb3  jz      loc_1800521E9
0x180051fb9  mov     edx, 4Eh ; 'N'
0x180051fbe  jmp     loc_180051F0C
0x180051fc3  lea     rcx, [r14+8]
0x180051fc7  mov     byte ptr [r10], 0
0x180051fcb  mov     rdx, rsi
0x180051fce  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180051fd3  test    al, al
0x180051fd5  jnz     short loc_18005200D
0x180051fd7  mov     edi, 8007000Eh
0x180051fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180051fe3  lea     rbx, WPP_GLOBAL_Control
0x180051fea  cmp     rcx, rbx
0x180051fed  jz      loc_1800521E9
0x180051ff3  test    byte ptr [rcx+1Ch], 1
0x180051ff7  jz      loc_1800521E9
0x180051ffd  mov     edx, 4Fh ; 'O'
0x180052002  mov     r9d, 8007000Eh
0x180052008  jmp     loc_180051F0F
0x18005200d  lea     rax, [rsp+2B0h+var_260]
0x180052012  mov     [r14], r15
0x180052015  mov     [rsp+2B0h+perf], rax; perf
0x18005201a  lea     r9, ?static_FDIRead@CCabDecompress@@KAI_JPEAXI@Z; pfnread
0x180052021  mov     [rsp+2B0h+cpuType], 1; cpuType
0x180052029  lea     rax, ?static_FDISeek@CCabDecompress@@KAJ_JJH@Z; CCabDecompress::static_FDISeek(__int64,long,int)
0x180052030  mov     [rsp+2B0h+pfnseek], rax; pfnseek
0x180052035  lea     r8, ?static_FDIOpen@CCabDecompress@@KA_JPEADHH@Z; pfnopen
0x18005203c  lea     rax, ?static_FDIClose@CCabDecompress@@KAH_J@Z; CCabDecompress::static_FDIClose(__int64)
0x180052043  mov     [rsp+2B0h+pfnclose], rax; pfnclose
0x180052048  lea     rdx, ?static_FDIFree@CCabDecompress@@KAXPEAX@Z; pfnfree
0x18005204f  lea     rax, ?static_FDIWrite@CCabDecompress@@KAI_JPEAXI@Z; CCabDecompress::static_FDIWrite(__int64,void *,uint)
0x180052056  lea     rcx, ?static_FDIAlloc@CCabDecompress@@KAPEAXK@Z; pfnalloc
0x18005205d  mov     [rsp+2B0h+pfnwrite], rax; pfnwrite
0x180052062  call    cs:__imp_FDICreate
0x180052069  nop     dword ptr [rax+rax+00h]
0x18005206e  mov     rsi, rax
0x180052071  test    rax, rax
0x180052074  jnz     short loc_1800520AB
0x180052076  lea     rcx, [rsp+2B0h+var_260]; struct ERF *
0x18005207b  call    ?FDIGetHRESULTFromERF@@YAJAEAUERF@@@Z; FDIGetHRESULTFromERF(ERF &)
0x180052080  mov     edi, eax
0x180052082  mov     rcx, cs:WPP_GLOBAL_Control
0x180052089  lea     rbx, WPP_GLOBAL_Control
0x180052090  cmp     rcx, rbx
0x180052093  jz      loc_1800521E9
0x180052099  test    byte ptr [rcx+1Ch], 1
0x18005209d  jz      loc_1800521E9
0x1800520a3  lea     edx, [rsi+50h]
0x1800520a6  jmp     loc_180051F0C
0x1800520ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800520b2  lea     rbx, WPP_GLOBAL_Control
0x1800520b9  cmp     rcx, rbx
0x1800520bc  jz      short loc_1800520E7
0x1800520be  test    byte ptr [rcx+1Ch], 4
0x1800520c2  jz      short loc_1800520E7
0x1800520c4  mov     rcx, [rcx+10h]
0x1800520c8  lea     rax, [rbp+1B0h+pszCabinet]
0x1800520cc  mov     edx, 51h ; 'Q'
0x1800520d1  mov     [rsp+2B0h+pfnwrite], rax
0x1800520d6  lea     r9, [rsp+2B0h+Str]
0x1800520db  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800520e2  call    WPP_SF_ss
0x1800520e7  mov     [rsp+2B0h+pfnseek], r14; pvUser
0x1800520ec  lea     rax, ?static_FDINotify@CCabDecompress@@KA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; CCabDecompress::static_FDINotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x1800520f3  mov     [rsp+2B0h+pfnclose], 0; pfnfdid
0x1800520fc  lea     r8, [rsp+2B0h+Str]; pszCabPath
0x180052101  xor     r9d, r9d; flags
0x180052104  mov     [rsp+2B0h+pfnwrite], rax; pfnfdin
0x180052109  lea     rdx, [rbp+1B0h+pszCabinet]; pszCabinet
0x18005210d  mov     rcx, rsi; hfdi
0x180052110  call    cs:__imp_FDICopy
0x180052117  nop     dword ptr [rax+rax+00h]
0x18005211c  test    eax, eax
0x18005211e  jnz     short loc_180052174
0x180052120  mov     rcx, [r14]; hHandle
0x180052123  xor     edx, edx; dwMilliseconds
0x180052125  call    cs:__imp_WaitForSingleObject
0x18005212c  nop     dword ptr [rax+rax+00h]
0x180052131  test    eax, eax
0x180052133  jnz     short loc_18005213C
0x180052135  mov     edi, 80004004h
0x18005213a  jmp     short loc_180052148
0x18005213c  lea     rcx, [rsp+2B0h+var_260]; struct ERF *
0x180052141  call    ?FDIGetHRESULTFromERF@@YAJAEAUERF@@@Z; FDIGetHRESULTFromERF(ERF &)
0x180052146  mov     edi, eax
0x180052148  mov     rcx, cs:WPP_GLOBAL_Control
0x18005214f  cmp     rcx, rbx
0x180052152  jz      short loc_180052176
0x180052154  test    byte ptr [rcx+1Ch], 1
0x180052158  jz      short loc_180052176
0x18005215a  mov     rcx, [rcx+10h]
0x18005215e  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x180052165  mov     edx, 52h ; 'R'
0x18005216a  mov     r9d, edi
0x18005216d  call    WPP_SF_d
0x180052172  jmp     short loc_180052176
0x180052174  xor     edi, edi
0x180052176  mov     rcx, rsi; hfdi
0x180052179  call    cs:__imp_FDIDestroy
0x180052180  nop     dword ptr [rax+rax+00h]
0x180052185  test    eax, eax
0x180052187  jnz     short loc_1800521E9
0x180052189  mov     rax, cs:WPP_GLOBAL_Control
0x180052190  cmp     rax, rbx
0x180052193  jz      short loc_1800521E9
0x180052195  test    byte ptr [rax+1Ch], 1
0x180052199  jz      short loc_1800521E9
0x18005219b  lea     rcx, [rsp+2B0h+var_260]; struct ERF *
0x1800521a0  call    ?FDIGetHRESULTFromERF@@YAJAEAUERF@@@Z; FDIGetHRESULTFromERF(ERF &)
0x1800521a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800521ac  mov     edx, 53h ; 'S'
0x1800521b1  jmp     loc_180051F0C
0x1800521b6  mov     edi, 80070057h
0x1800521bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800521c2  lea     rbx, WPP_GLOBAL_Control
0x1800521c9  cmp     rcx, rbx
0x1800521cc  jz      short loc_1800521E9
0x1800521ce  test    byte ptr [rcx+1Ch], 1
0x1800521d2  jz      short loc_1800521E9
0x1800521d4  mov     rcx, [rcx+10h]
0x1800521d8  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800521df  mov     edx, 4Ah ; 'J'
0x1800521e4  call    WPP_SF_
0x1800521e9  mov     eax, edi
0x1800521eb  mov     rcx, [rbp+1B0h+var_30]
0x1800521f2  xor     rcx, rsp; StackCookie
0x1800521f5  call    __security_check_cookie
0x1800521fa  mov     rbx, [rsp+2B0h+arg_18]
0x180052202  add     rsp, 290h
0x180052209  pop     r15
0x18005220b  pop     r14
0x18005220d  pop     rdi
0x18005220e  pop     rsi
0x18005220f  pop     rbp
0x180052210  retn
```

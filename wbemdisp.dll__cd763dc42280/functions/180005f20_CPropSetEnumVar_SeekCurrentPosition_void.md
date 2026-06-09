# CPropSetEnumVar::SeekCurrentPosition(void)

- ea: `0x180005f20`
- end: `0x1800062ec`
- name: `?SeekCurrentPosition@CPropSetEnumVar@@AEAA_NXZ`
- size: `972`
- prototype: `bool __fastcall(CPropSetEnumVar *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800052d0`

## callees

- `0x1800050dc`
- `0x180005f20`
- `0x180006300`
- `0x180006550`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800060f1`
- `OLEAUT32!__imp_SysAllocString` at `0x180006199`
- `OLEAUT32!__imp_SysAllocString` at `0x1800060f1`
- `OLEAUT32!__imp_SysAllocString` at `0x180006199`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180006295`
- `OLEAUT32!__imp_SysFreeString` at `0x1800062a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800062b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180006295`
- `OLEAUT32!__imp_SysFreeString` at `0x1800062a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800062b1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180005fa8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180005fa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ff9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006006`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ff9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006006`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005fb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005fb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fc7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000605b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006131`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000605b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006131`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800062d0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800062d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall CPropSetEnumVar::SeekCurrentPosition(CPropSetEnumVar *this)
{
  __int64 v2; // rbx
  int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // ebp
  bool v7; // zf
  _QWORD *v8; // r15
  CWbemErrorCache *v9; // rbx
  DWORD CurrentThreadId; // esi
  void *v11; // rcx
  void *v12; // rdi
  int v13; // ebx
  __int64 v14; // rcx
  _QWORD *v15; // rsi
  _QWORD *v16; // rax
  OLECHAR *v17; // r13
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // r12
  _DWORD *v21; // rax
  _DWORD *v22; // rdi
  __int64 v23; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  struct _COAUTHIDENTITY *v28; // rcx
  OLECHAR *psz; // [rsp+90h] [rbp+8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+98h] [rbp+10h] BYREF
  _QWORD *v31; // [rsp+A0h] [rbp+18h]
  _DWORD *v32; // [rsp+A8h] [rbp+20h]

  v2 = *((_QWORD *)this + 2);
  v3 = -2147217407;
  ResetLastErrors();
  v4 = *(_QWORD *)(v2 + 40);
  if ( !v4 )
    goto LABEL_30;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 80LL))(v4);
  v5 = 48;
  if ( !*(_BYTE *)(v2 + 136) )
    v5 = 64;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v2 + 40) + 64LL))(*(_QWORD *)(v2 + 40), v5);
  if ( v3 < 0 )
LABEL_30:
    CDispatchHelp::RaiseException((CDispatchHelp *)(v2 + 48), v3);
  v6 = 0;
  v7 = *((_DWORD *)this + 6) == 0;
  if ( *((_DWORD *)this + 6) )
  {
    while ( 1 )
    {
      v8 = (_QWORD *)*((_QWORD *)this + 2);
      SetErrorInfo(0, 0);
      EnterCriticalSection(&g_csErrorCache);
      v9 = g_pErrorCache;
      if ( g_pErrorCache )
      {
        CurrentThreadId = GetCurrentThreadId();
        CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v9 + 8));
        v11 = (void *)*((_QWORD *)v9 + 6);
        v12 = v11;
        if ( v11 )
        {
          while ( CurrentThreadId != *((_DWORD *)v12 + 4) )
          {
            v12 = *(void **)v12;
            if ( !v12 )
              goto LABEL_8;
          }
          if ( v12 == v11 )
            *((_QWORD *)v9 + 6) = *(_QWORD *)v12;
          if ( *(_QWORD *)v12 )
            *(_QWORD *)(*(_QWORD *)v12 + 8LL) = *((_QWORD *)v12 + 1);
          v25 = (_QWORD *)*((_QWORD *)v12 + 1);
          if ( v25 )
            *v25 = *(_QWORD *)v12;
          v26 = *((_QWORD *)v12 + 8);
          if ( v26 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            *((_QWORD *)v12 + 8) = 0;
          }
          v27 = *((_QWORD *)v12 + 7);
          if ( v27 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            *((_QWORD *)v12 + 7) = 0;
          }
          SysFreeString(*((BSTR *)v12 + 6));
          *((_QWORD *)v12 + 6) = 0;
          SysFreeString(*((BSTR *)v12 + 4));
          *((_QWORD *)v12 + 4) = 0;
          SysFreeString(*((BSTR *)v12 + 5));
          *((_QWORD *)v12 + 5) = 0;
          v28 = (struct _COAUTHIDENTITY *)*((_QWORD *)v12 + 3);
          if ( v28 )
          {
            WbemFreeAuthIdentity(v28);
            *((_QWORD *)v12 + 3) = 0;
          }
          CWin32DefaultArena::WbemMemFree(v12);
        }
LABEL_8:
        LeaveCriticalSection(lpCriticalSection);
      }
      LeaveCriticalSection(&g_csErrorCache);
      v13 = -2147217407;
      v14 = v8[5];
      if ( !v14 )
        break;
      v15 = 0;
      psz = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR **, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
              v14,
              0,
              &psz,
              0,
              0,
              0);
      if ( !v13 )
      {
        v16 = CWin32DefaultArena::WbemMemAlloc(0x98u);
        v15 = v16;
        v31 = v16;
        if ( v16 )
        {
          v17 = psz;
          v18 = v8[4];
          v19 = v18 + 16;
          if ( !v18 )
            v19 = 0;
          v20 = v8[3];
          *v16 = &CSWbemProperty::`vftable'{for `ISWbemProperty'};
          v16[1] = &CSWbemProperty::`vftable'{for `ISupportErrorInfo'};
          v16[2] = &CSWbemProperty::`vftable'{for `IProvideClassInfo'};
          v16[9] = 0;
          v16[10] = 0;
          v16[11] = 0;
          v16[7] = 0;
          *((_DWORD *)v16 + 16) = 0;
          v16[6] = &CSWbemProperty::CPropertyDispatchHelp::`vftable';
          v16[11] = v16;
          *((GUID *)v16 + 6) = IID_ISWbemProperty;
          *((GUID *)v16 + 7) = CLSID_SWbemProperty;
          v16[7] = SysAllocString(L"SWbemProperty");
          *((_DWORD *)v15 + 36) = 1;
          v15[4] = v19;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
          (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v15[4] + 24LL))(v15[4], v15 + 5);
          v21 = CWin32DefaultArena::WbemMemAlloc(0x18u);
          v22 = v21;
          v32 = v21;
          if ( v21 )
          {
            v23 = v15[4];
            v21[2] = 1;
            *(_QWORD *)v21 = &CWbemObjectSite::`vftable';
            *((_QWORD *)v21 + 2) = v23;
            if ( v23 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
          }
          else
          {
            v22 = 0;
          }
          v15[17] = v22;
          v15[3] = v20;
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
          v15[16] = SysAllocString(v17);
          _InterlockedIncrement(&g_cObj);
        }
        else
        {
          v15 = 0;
        }
        if ( !v15 )
          v13 = -2147217402;
        SysFreeString(psz);
      }
      if ( v13 < 0 )
        break;
      if ( !v13 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        if ( (unsigned int)++v6 < *((_DWORD *)this + 6) )
          continue;
      }
      return v6 == *((_DWORD *)this + 6);
    }
    CDispatchHelp::RaiseException((CDispatchHelp *)(v8 + 6), v13);
    return v6 == *((_DWORD *)this + 6);
  }
  return v7;
}

```

## disassembly

```asm
0x180005f20  push    rbx
0x180005f22  push    rbp
0x180005f23  push    rsi
0x180005f24  push    rdi
0x180005f25  push    r12
0x180005f27  push    r13
0x180005f29  push    r14
0x180005f2b  push    r15
0x180005f2d  sub     rsp, 48h
0x180005f31  mov     r14, rcx
0x180005f34  mov     rbx, [rcx+10h]
0x180005f38  mov     edi, 80041001h
0x180005f3d  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180005f42  mov     rcx, [rbx+28h]
0x180005f46  test    rcx, rcx
0x180005f49  jz      loc_180006212
0x180005f4f  mov     rax, [rcx]
0x180005f52  mov     rax, [rax+50h]
0x180005f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f5b  mov     rcx, [rbx+28h]
0x180005f5f  mov     rax, [rcx]
0x180005f62  mov     edx, 30h ; '0'
0x180005f67  mov     r8d, 40h ; '@'
0x180005f6d  cmp     byte ptr [rbx+88h], 0
0x180005f74  cmovz   edx, r8d
0x180005f78  mov     rax, [rax+40h]
0x180005f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f81  mov     edi, eax
0x180005f83  test    eax, eax
0x180005f85  js      loc_180006212
0x180005f8b  xor     r12d, r12d
0x180005f8e  mov     ebp, r12d
0x180005f91  cmp     r12d, [r14+18h]
0x180005f95  jnb     loc_1800061F2
0x180005f9b  nop     dword ptr [rax+rax+00h]
0x180005fa0  mov     r15, [r14+10h]
0x180005fa4  xor     edx, edx; perrinfo
0x180005fa6  xor     ecx, ecx; dwReserved
0x180005fa8  call    cs:__imp_SetErrorInfo
0x180005fae  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005fb5  call    cs:__imp_EnterCriticalSection
0x180005fbb  mov     rbx, cs:?g_pErrorCache@@3PEAVCWbemErrorCache@@EA; CWbemErrorCache * g_pErrorCache
0x180005fc2  test    rbx, rbx
0x180005fc5  jz      short loc_180005FFF
0x180005fc7  call    cs:__imp_GetCurrentThreadId
0x180005fcd  mov     esi, eax
0x180005fcf  lea     rdx, [rbx+8]; struct _RTL_CRITICAL_SECTION *
0x180005fd3  lea     rcx, [rsp+88h+lpCriticalSection]; this
0x180005fdb  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180005fe0  nop
0x180005fe1  mov     rcx, [rbx+30h]
0x180005fe5  mov     rdi, rcx
0x180005fe8  test    rcx, rcx
0x180005feb  jnz     loc_180006222
0x180005ff1  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180005ff9  call    cs:__imp_LeaveCriticalSection
0x180005fff  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006006  call    cs:__imp_LeaveCriticalSection
0x18000600c  mov     ebx, 80041001h
0x180006011  mov     rcx, [r15+28h]
0x180006015  test    rcx, rcx
0x180006018  jz      loc_1800062DC
0x18000601e  mov     rsi, r12
0x180006021  mov     [rsp+88h+psz], r12
0x180006029  mov     rax, [rcx]
0x18000602c  mov     [rsp+88h+var_60], r12
0x180006031  mov     [rsp+88h+var_68], r12
0x180006036  xor     r9d, r9d
0x180006039  lea     r8, [rsp+88h+psz]
0x180006041  xor     edx, edx
0x180006043  mov     rax, [rax+48h]
0x180006047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000604c  mov     ebx, eax
0x18000604e  test    eax, eax
0x180006050  jnz     loc_1800061C9
0x180006056  mov     ecx, 98h
0x18000605b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180006061  mov     rsi, rax
0x180006064  mov     [rsp+88h+arg_10], rax
0x18000606c  test    rax, rax
0x18000606f  jz      loc_180006206
0x180006075  mov     r13, [rsp+88h+psz]
0x18000607d  mov     rcx, [r15+20h]
0x180006081  lea     rdi, [rcx+10h]
0x180006085  test    rcx, rcx
0x180006088  cmovz   rdi, r12
0x18000608c  mov     r12, [r15+18h]
0x180006090  lea     rax, ??_7CSWbemProperty@@6BISWbemProperty@@@; const CSWbemProperty::`vftable'{for `ISWbemProperty'}
0x180006097  mov     [rsi], rax
0x18000609a  lea     rax, ??_7CSWbemProperty@@6BISupportErrorInfo@@@; const CSWbemProperty::`vftable'{for `ISupportErrorInfo'}
0x1800060a1  mov     [rsi+8], rax
0x1800060a5  lea     rax, ??_7CSWbemProperty@@6BIProvideClassInfo@@@; const CSWbemProperty::`vftable'{for `IProvideClassInfo'}
0x1800060ac  mov     [rsi+10h], rax
0x1800060b0  xor     eax, eax
0x1800060b2  mov     [rsi+48h], rax
0x1800060b6  mov     [rsi+50h], rax
0x1800060ba  mov     [rsi+58h], rax
0x1800060be  mov     [rsi+38h], rax
0x1800060c2  mov     [rsi+40h], eax
0x1800060c5  lea     rax, ??_7CPropertyDispatchHelp@CSWbemProperty@@6B@; const CSWbemProperty::CPropertyDispatchHelp::`vftable'
0x1800060cc  mov     [rsi+30h], rax
0x1800060d0  movups  xmm1, xmmword ptr cs:CLSID_SWbemProperty.Data1
0x1800060d7  movups  xmm0, xmmword ptr cs:IID_ISWbemProperty.Data1
0x1800060de  mov     [rsi+58h], rsi
0x1800060e2  movups  xmmword ptr [rsi+60h], xmm0
0x1800060e6  movups  xmmword ptr [rsi+70h], xmm1
0x1800060ea  lea     rcx, aSwbemproperty; "SWbemProperty"
0x1800060f1  call    cs:__imp_SysAllocString
0x1800060f7  mov     [rsi+38h], rax
0x1800060fb  mov     dword ptr [rsi+90h], 1
0x180006105  mov     [rsi+20h], rdi
0x180006109  mov     rax, [rdi]
0x18000610c  mov     rcx, rdi
0x18000610f  mov     rax, [rax+8]
0x180006113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006118  mov     rcx, [rsi+20h]
0x18000611c  mov     rax, [rcx]
0x18000611f  lea     rdx, [rsi+28h]
0x180006123  mov     rax, [rax+18h]
0x180006127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612c  mov     ecx, 18h
0x180006131  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180006137  mov     rdi, rax
0x18000613a  mov     [rsp+88h+arg_18], rax
0x180006142  test    rax, rax
0x180006145  jz      loc_18000620B
0x18000614b  mov     rcx, [rsi+20h]
0x18000614f  mov     dword ptr [rax+8], 1
0x180006156  lea     rax, ??_7CWbemObjectSite@@6B@; const CWbemObjectSite::`vftable'
0x18000615d  mov     [rdi], rax
0x180006160  mov     [rdi+10h], rcx
0x180006164  test    rcx, rcx
0x180006167  jz      short loc_180006176
0x180006169  mov     rax, [rcx]
0x18000616c  mov     rax, [rax+8]
0x180006170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006175  nop
0x180006176  mov     [rsi+88h], rdi
0x18000617d  mov     [rsi+18h], r12
0x180006181  test    r12, r12
0x180006184  jz      short loc_180006196
0x180006186  mov     rax, [r12]
0x18000618a  mov     rcx, r12
0x18000618d  mov     rax, [rax+8]
0x180006191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006196  mov     rcx, r13; psz
0x180006199  call    cs:__imp_SysAllocString
0x18000619f  mov     [rsi+80h], rax
0x1800061a6  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800061ad  xor     r12d, r12d
0x1800061b0  test    rsi, rsi
0x1800061b3  mov     eax, 80041006h
0x1800061b8  cmovz   ebx, eax
0x1800061bb  mov     rcx, [rsp+88h+psz]; bstrString
0x1800061c3  call    cs:__imp_SysFreeString
0x1800061c9  test    ebx, ebx
0x1800061cb  js      loc_1800062DC
0x1800061d1  jnz     short loc_1800061EE
0x1800061d3  mov     rax, [rsi]
0x1800061d6  mov     rcx, rsi
0x1800061d9  mov     rax, [rax+10h]
0x1800061dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061e2  inc     ebp
0x1800061e4  cmp     ebp, [r14+18h]
0x1800061e8  jb      loc_180005FA0
0x1800061ee  cmp     ebp, [r14+18h]
0x1800061f2  setz    al
0x1800061f5  add     rsp, 48h
0x1800061f9  pop     r15
0x1800061fb  pop     r14
0x1800061fd  pop     r13
0x1800061ff  pop     r12
0x180006201  pop     rdi
0x180006202  pop     rsi
0x180006203  pop     rbp
0x180006204  pop     rbx
0x180006205  retn
0x180006206  mov     rsi, r12
0x180006209  jmp     short loc_1800061B0
0x18000620b  xor     edi, edi
0x18000620d  jmp     loc_180006176
0x180006212  lea     rcx, [rbx+30h]; this
0x180006216  mov     edx, edi; int
0x180006218  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18000621d  jmp     loc_180005F8B
0x180006222  cmp     esi, [rdi+10h]
0x180006225  jz      short loc_180006234
0x180006227  mov     rdi, [rdi]
0x18000622a  test    rdi, rdi
0x18000622d  jnz     short loc_180006222
0x18000622f  jmp     loc_180005FF1
0x180006234  cmp     rdi, rcx
0x180006237  jnz     short loc_180006240
0x180006239  mov     rax, [rdi]
0x18000623c  mov     [rbx+30h], rax
0x180006240  mov     rcx, [rdi]
0x180006243  test    rcx, rcx
0x180006246  jz      short loc_180006250
0x180006248  mov     rax, [rdi+8]
0x18000624c  mov     [rcx+8], rax
0x180006250  mov     rcx, [rdi+8]
0x180006254  test    rcx, rcx
0x180006257  jz      short loc_18000625F
0x180006259  mov     rax, [rdi]
0x18000625c  mov     [rcx], rax
0x18000625f  mov     rcx, [rdi+40h]
0x180006263  test    rcx, rcx
0x180006266  jz      short loc_180006278
0x180006268  mov     rax, [rcx]
0x18000626b  mov     rax, [rax+10h]
0x18000626f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006274  mov     [rdi+40h], r12
0x180006278  mov     rcx, [rdi+38h]
0x18000627c  test    rcx, rcx
0x18000627f  jz      short loc_180006291
0x180006281  mov     rax, [rcx]
0x180006284  mov     rax, [rax+10h]
0x180006288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628d  mov     [rdi+38h], r12
0x180006291  mov     rcx, [rdi+30h]; bstrString
0x180006295  call    cs:__imp_SysFreeString
0x18000629b  mov     [rdi+30h], r12
0x18000629f  mov     rcx, [rdi+20h]; bstrString
0x1800062a3  call    cs:__imp_SysFreeString
0x1800062a9  mov     [rdi+20h], r12
0x1800062ad  mov     rcx, [rdi+28h]; bstrString
0x1800062b1  call    cs:__imp_SysFreeString
0x1800062b7  mov     [rdi+28h], r12
0x1800062bb  mov     rcx, [rdi+18h]; pv
0x1800062bf  test    rcx, rcx
0x1800062c2  jz      short loc_1800062CD
0x1800062c4  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x1800062c9  mov     [rdi+18h], r12
0x1800062cd  mov     rcx, rdi
0x1800062d0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800062d6  nop
0x1800062d7  jmp     loc_180005FF1
0x1800062dc  lea     rcx, [r15+30h]; this
0x1800062e0  mov     edx, ebx; int
0x1800062e2  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x1800062e7  jmp     loc_1800061EE
```

# TraceLog::LimitFrequency(RegistryT<256> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,TimeSpan const &,std::function<void (void)> const &)

- ea: `0x140088634`
- end: `0x140088910`
- name: `?LimitFrequency@TraceLog@@YAXAEAV?$RegistryT@$0BAA@@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVTimeSpan@@AEBV?$function@$$A6AXXZ@4@@Z`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140031d90`

## callees

- `0x140005530`
- `0x140006338`
- `0x140009858`
- `0x14000ccac`
- `0x140060f58`
- `0x14006803c`
- `0x140068dbc`
- `0x140069748`
- `0x140088014`
- `0x140088130`
- `0x140088634`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x1400887cd`
- `KERNEL32!CompareFileTime` at `0x1400887f9`
- `KERNEL32!CompareFileTime` at `0x1400887cd`
- `KERNEL32!CompareFileTime` at `0x1400887f9`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14008867f`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140088824`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14008867f`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140088824`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
int __fastcall TraceLog::LimitFrequency(
        __int64 (__fastcall ***a1)(_QWORD, __int64 *, _OWORD *),
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v8; // rcx
  int result; // eax
  __int64 (__fastcall *v10)(_QWORD, __int64 *, _OWORD *); // rbx
  _QWORD *v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  char v13; // bl
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 (__fastcall ***v16)(_QWORD, __int64); // rcx
  char **v17; // rcx
  const FILETIME *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdi
  void (__fastcall *v22)(__int64, char **); // rbx
  __int64 (__fastcall ***v23)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v24)(_QWORD, __int64); // rcx
  __int64 v25; // [rsp+20h] [rbp-99h] BYREF
  _QWORD v26[2]; // [rsp+28h] [rbp-91h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-81h] BYREF
  __int64 v28; // [rsp+48h] [rbp-71h] BYREF
  __int64 v29; // [rsp+50h] [rbp-69h] BYREF
  char *v30[2]; // [rsp+58h] [rbp-61h] BYREF
  FILETIME *lpFileTime1; // [rsp+68h] [rbp-51h]
  _OWORD pExceptionObject[2]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v33[40]; // [rsp+A0h] [rbp-19h] BYREF
  char **v34; // [rsp+C8h] [rbp+Fh]

  v25 = a2;
  if ( (unsigned __int8)lambda_970c1268d4d3e21c45305266ae53b436_::operator()(&v25) )
  {
    v8 = *(_QWORD *)(a4 + 56);
    if ( !v8 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    v10 = **a1;
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    std::wstring::_Construct<1,unsigned short const *>((char **)pExceptionObject, L"Squelch", 7u);
    v11 = (_QWORD *)v10(a1, &v28, pExceptionObject);
    (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v11 + 48LL))(*v11, &v25);
    if ( v28 )
    {
      v12 = (void (__fastcall ***)(_QWORD, __int64))(v28 + *(int *)(*(_QWORD *)(v28 + 8) + 4LL) + 8LL);
      (**v12)(v12, 1);
    }
    std::wstring::~wstring((char **)pExceptionObject);
    v13 = 1;
    DateTime::GetCurrent(&FileTime2);
    v14 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64))v25)(v25, &v29, a2);
    v15 = *(_QWORD *)v14 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v14 + 8LL) + 4LL);
    result = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 40LL))(v15, v33);
    if ( v29 )
    {
      v16 = (__int64 (__fastcall ***)(_QWORD, __int64))(v29 + *(int *)(*(_QWORD *)(v29 + 8) + 4LL) + 8LL);
      result = (**v16)(v16, 1);
    }
    v17 = v34;
    if ( v34 )
    {
      v26[0] = v33;
      result = stdext::try_execute__lambda_6d459bc6bb4e76a2d403c7867349fa72___(v30, v26);
      if ( lpFileTime1 )
      {
        result = TimeSpan::Zero;
        if ( *a3 >= TimeSpan::Zero && *a3 <= TimeSpan::Zero )
          goto LABEL_16;
        result = CompareFileTime(lpFileTime1, &FileTime2);
        if ( result < 0 )
        {
          if ( !lpFileTime1 )
          {
            ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
            throw (ErrorCodeException *)pExceptionObject;
          }
          v18 = (const FILETIME *)DateTime::operator+(lpFileTime1, v26, a3);
          result = CompareFileTime(v18, &FileTime2);
          if ( result > 0 )
LABEL_16:
            v13 = 0;
        }
      }
      v17 = v34;
    }
    if ( v17 )
      result = std::wstring::~wstring(v17);
    if ( v13 )
    {
      v19 = *(_QWORD *)(a4 + 56);
      if ( !v19 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v20 = (**(__int64 (__fastcall ***)(__int64, _QWORD *, __int64))v25)(v25, v26, a2);
      v21 = *(_QWORD *)v20;
      v22 = *(void (__fastcall **)(__int64, char **))(**(_QWORD **)v20 + 32LL);
      DateTime::ToDebugString(&FileTime2, v30, 0);
      v22(v21, v30);
      result = std::wstring::~wstring(v30);
      if ( v26[0] )
      {
        v23 = (__int64 (__fastcall ***)(_QWORD, __int64))(v26[0] + *(int *)(*(_QWORD *)(v26[0] + 8LL) + 4LL) + 8LL);
        result = (**v23)(v23, 1);
      }
    }
    if ( v25 )
    {
      v24 = (__int64 (__fastcall ***)(_QWORD, __int64))(v25 + 8 + *(int *)(*(_QWORD *)(v25 + 8) + 4LL));
      return (**v24)(v24, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140088634  push    rbp
0x140088636  push    rbx
0x140088637  push    rsi
0x140088638  push    rdi
0x140088639  push    r14
0x14008863b  push    r15
0x14008863d  lea     rbp, [rsp-2Fh]
0x140088642  sub     rsp, 0E8h
0x140088649  mov     rax, cs:__security_cookie
0x140088650  xor     rax, rsp
0x140088653  mov     [rbp+57h+var_40], rax
0x140088657  mov     rdi, r9
0x14008865a  mov     rsi, r8
0x14008865d  mov     r15, rdx
0x140088660  mov     r14, rcx
0x140088663  mov     [rsp+110h+var_F0], rdx
0x140088668  lea     rcx, [rsp+110h+var_F0]
0x14008866d  call    _lambda_970c1268d4d3e21c45305266ae53b436___operator__
0x140088672  test    al, al
0x140088674  jz      short loc_140088697
0x140088676  mov     rcx, [rdi+38h]
0x14008867a  test    rcx, rcx
0x14008867d  jnz     short loc_140088686
0x14008867f  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x140088685  int     3; Trap to Debugger
0x140088686  mov     rax, [rcx]
0x140088689  mov     rax, [rax+10h]
0x14008868d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088692  jmp     loc_1400888D5
0x140088697  mov     rax, [r14]
0x14008869a  mov     rbx, [rax]
0x14008869d  xorps   xmm0, xmm0
0x1400886a0  movups  [rbp+57h+pExceptionObject], xmm0
0x1400886a4  xorps   xmm1, xmm1
0x1400886a7  movdqu  [rbp+57h+var_88], xmm1
0x1400886ac  mov     r8d, 7
0x1400886b2  lea     rdx, aSquelch; "Squelch"
0x1400886b9  lea     rcx, [rbp+57h+pExceptionObject]
0x1400886bd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400886c2  nop
0x1400886c3  lea     r8, [rbp+57h+pExceptionObject]
0x1400886c7  lea     rdx, [rbp+57h+var_C8]
0x1400886cb  mov     rcx, r14
0x1400886ce  mov     rax, rbx
0x1400886d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400886d6  nop
0x1400886d7  mov     rcx, [rax]
0x1400886da  mov     rax, [rcx]
0x1400886dd  lea     rdx, [rsp+110h+var_F0]
0x1400886e2  mov     rax, [rax+30h]
0x1400886e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400886eb  nop
0x1400886ec  mov     r14d, 1
0x1400886f2  mov     rdx, [rbp+57h+var_C8]
0x1400886f6  test    rdx, rdx
0x1400886f9  jz      short loc_140088719
0x1400886fb  mov     rax, [rdx+8]
0x1400886ff  movsxd  rcx, dword ptr [rax+4]
0x140088703  add     rcx, 8
0x140088707  add     rcx, rdx
0x14008870a  mov     rax, [rcx]
0x14008870d  mov     edx, r14d
0x140088710  mov     rax, [rax]
0x140088713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088718  nop
0x140088719  lea     rcx, [rbp+57h+pExceptionObject]
0x14008871d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140088722  mov     bl, r14b
0x140088725  lea     rcx, [rsp+110h+FileTime2]
0x14008872a  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x14008872f  mov     rcx, [rsp+110h+var_F0]
0x140088734  mov     rax, [rcx]
0x140088737  mov     r8, r15
0x14008873a  lea     rdx, [rbp+57h+var_C0]
0x14008873e  mov     rax, [rax]
0x140088741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088746  nop
0x140088747  mov     rdx, [rax]
0x14008874a  mov     rax, [rdx+8]
0x14008874e  movsxd  rcx, dword ptr [rax+4]
0x140088752  add     rdx, 8
0x140088756  add     rcx, rdx
0x140088759  mov     rax, [rcx]
0x14008875c  lea     rdx, [rbp+57h+var_70]
0x140088760  mov     rax, [rax+28h]
0x140088764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088769  nop
0x14008876a  mov     rdx, [rbp+57h+var_C0]
0x14008876e  test    rdx, rdx
0x140088771  jz      short loc_140088790
0x140088773  mov     rax, [rdx+8]
0x140088777  movsxd  rcx, dword ptr [rax+4]
0x14008877b  add     rcx, 8
0x14008877f  add     rcx, rdx
0x140088782  mov     rax, [rcx]
0x140088785  mov     edx, r14d
0x140088788  mov     rax, [rax]
0x14008878b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088790  mov     rcx, [rbp+57h+var_48]
0x140088794  test    rcx, rcx
0x140088797  jz      short loc_140088809
0x140088799  lea     rax, [rbp+57h+var_70]
0x14008879d  mov     [rsp+110h+var_E8], rax
0x1400887a2  lea     rdx, [rsp+110h+var_E8]
0x1400887a7  lea     rcx, [rbp+57h+var_B8]
0x1400887ab  call    stdext__try_execute__lambda_6d459bc6bb4e76a2d403c7867349fa72___
0x1400887b0  nop
0x1400887b1  mov     rcx, [rbp+57h+lpFileTime1]; lpFileTime1
0x1400887b5  test    rcx, rcx
0x1400887b8  jz      short loc_140088805
0x1400887ba  mov     rax, cs:?Zero@TimeSpan@@2V1@B; TimeSpan const TimeSpan::Zero
0x1400887c1  cmp     [rsi], rax
0x1400887c4  jb      short loc_1400887C8
0x1400887c6  jbe     short loc_140088803
0x1400887c8  lea     rdx, [rsp+110h+FileTime2]; lpFileTime2
0x1400887cd  call    cs:__imp_CompareFileTime
0x1400887d3  test    eax, eax
0x1400887d5  jns     short loc_140088805
0x1400887d7  mov     rcx, [rbp+57h+lpFileTime1]
0x1400887db  test    rcx, rcx
0x1400887de  jz      loc_1400888F1
0x1400887e4  mov     r8, rsi
0x1400887e7  lea     rdx, [rsp+110h+var_E8]
0x1400887ec  call    ??HDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator+(TimeSpan const &)
0x1400887f1  lea     rdx, [rsp+110h+FileTime2]; lpFileTime2
0x1400887f6  mov     rcx, rax; lpFileTime1
0x1400887f9  call    cs:__imp_CompareFileTime
0x1400887ff  test    eax, eax
0x140088801  jle     short loc_140088805
0x140088803  xor     bl, bl
0x140088805  mov     rcx, [rbp+57h+var_48]
0x140088809  test    rcx, rcx
0x14008880c  jz      short loc_140088813
0x14008880e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140088813  test    bl, bl
0x140088815  jz      loc_1400888AE
0x14008881b  mov     rcx, [rdi+38h]
0x14008881f  test    rcx, rcx
0x140088822  jnz     short loc_14008882B
0x140088824  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14008882a  int     3; Trap to Debugger
0x14008882b  mov     rax, [rcx]
0x14008882e  mov     rax, [rax+10h]
0x140088832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140088837  mov     rcx, [rsp+110h+var_F0]
0x14008883c  mov     rax, [rcx]
0x14008883f  mov     r8, r15
0x140088842  lea     rdx, [rsp+110h+var_E8]
0x140088847  mov     rax, [rax]
0x14008884a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008884f  nop
0x140088850  mov     rdi, [rax]
0x140088853  mov     rax, [rdi]
0x140088856  mov     rbx, [rax+20h]
0x14008885a  xor     r8d, r8d
0x14008885d  lea     rdx, [rbp+57h+var_B8]
0x140088861  lea     rcx, [rsp+110h+FileTime2]
0x140088866  call    ?ToDebugString@DateTime@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TimeType@@@Z; DateTime::ToDebugString(TimeType)
0x14008886b  nop
0x14008886c  lea     rdx, [rbp+57h+var_B8]
0x140088870  mov     rcx, rdi
0x140088873  mov     rax, rbx
0x140088876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008887b  nop
0x14008887c  lea     rcx, [rbp+57h+var_B8]
0x140088880  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140088885  nop
0x140088886  mov     rdx, [rsp+110h+var_E8]
0x14008888b  test    rdx, rdx
0x14008888e  jz      short loc_1400888AE
0x140088890  mov     rax, [rdx+8]
0x140088894  movsxd  rcx, dword ptr [rax+4]
0x140088898  add     rcx, 8
0x14008889c  add     rcx, rdx
0x14008889f  mov     rax, [rcx]
0x1400888a2  mov     edx, r14d
0x1400888a5  mov     rax, [rax]
0x1400888a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400888ad  nop
0x1400888ae  mov     r8, [rsp+110h+var_F0]
0x1400888b3  test    r8, r8
0x1400888b6  jz      short loc_1400888D5
0x1400888b8  mov     rax, [r8+8]
0x1400888bc  movsxd  rcx, dword ptr [rax+4]
0x1400888c0  add     r8, 8
0x1400888c4  add     rcx, r8
0x1400888c7  mov     rax, [rcx]
0x1400888ca  mov     edx, r14d
0x1400888cd  mov     rax, [rax]
0x1400888d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400888d5  mov     rcx, [rbp+57h+var_40]
0x1400888d9  xor     rcx, rsp; StackCookie
0x1400888dc  call    __security_check_cookie
0x1400888e1  add     rsp, 0E8h
0x1400888e8  pop     r15
0x1400888ea  pop     r14
0x1400888ec  pop     rdi
0x1400888ed  pop     rsi
0x1400888ee  pop     rbx
0x1400888ef  pop     rbp
0x1400888f0  retn
0x1400888f1  mov     edx, 80004003h; int
0x1400888f6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400888fa  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400888ff  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140088906  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14008890a  call    _CxxThrowException_0
```

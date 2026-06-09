# CTextTemplate::Apply(IWbemClassObject *)

- ea: `0x1800016f0`
- end: `0x180001cff`
- name: `?Apply@CTextTemplate@@QEAAPEAGPEAUIWbemClassObject@@@Z`
- size: `1551`
- prototype: `unsigned __int16 *__fastcall(CTextTemplate *__hidden this, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x1800016f0`
- `0x1800029a0`
- `0x180002cb0`
- `0x180005ec0`
- `0x1800094f0`
- `0x18000a290`
- `0x18000ab30`
- `0x18000dee0`
- `0x180010770`
- `0x180013564`
- `0x180014120`
- `0x18001d970`
- `0x180022e40`
- `0x1800254d0`
- `0x180028484`
- `0x1800298f0`
- `0x18002c98c`
- `0x180038810`
- `0x180038830`
- `0x180038c20`
- `0x180038ff0`
- `0x180039040`
- `0x180039100`
- `0x180047010`

## import_xrefs

- `msvcrt!wcschr` at `0x180001769`
- `msvcrt!wcschr` at `0x180001783`
- `msvcrt!wcschr` at `0x18000179c`
- `msvcrt!wcschr` at `0x1800017ad`
- `msvcrt!wcschr` at `0x18000186e`
- `msvcrt!wcschr` at `0x18000188c`
- `msvcrt!wcschr` at `0x180001769`
- `msvcrt!wcschr` at `0x180001783`
- `msvcrt!wcschr` at `0x18000179c`
- `msvcrt!wcschr` at `0x1800017ad`
- `msvcrt!wcschr` at `0x18000186e`
- `msvcrt!wcschr` at `0x18000188c`
- `OLEAUT32!__imp_SysAllocString` at `0x180001cb7`
- `OLEAUT32!__imp_SysAllocString` at `0x180001cb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180001970`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c50`
- `OLEAUT32!__imp_SysFreeString` at `0x180001970`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c50`
- `OLEAUT32!__imp_VariantInit` at `0x18000197f`
- `OLEAUT32!__imp_VariantInit` at `0x18000197f`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180001a92`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180001a92`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180001ab2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180001ab2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180001aa2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180001aa2`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180001ae1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180001ae1`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
BSTR __fastcall CTextTemplate::Apply(const wchar_t **this, struct IWbemClassObject *a2)
{
  const wchar_t *i; // rdi
  __int64 v5; // rdx
  wchar_t *v6; // r12
  wchar_t *v7; // rax
  wchar_t *v8; // rax
  __int64 v9; // rsi
  void *v10; // rax
  wchar_t *v11; // rbx
  signed int v12; // eax
  unsigned int v13; // edi
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // rdi
  wchar_t *v16; // rax
  int v17; // eax
  const wchar_t *v18; // rdx
  const OLECHAR *v19; // rdx
  int j; // eax
  const OLECHAR *v21; // rdx
  OLECHAR *Text; // rax
  OLECHAR *v24; // rbx
  BSTR v25; // rdi
  BSTR v26; // [rsp+40h] [rbp-99h] BYREF
  int v27; // [rsp+48h] [rbp-91h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-89h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-81h] BYREF
  __int64 v30; // [rsp+60h] [rbp-79h]
  __int64 v31; // [rsp+68h] [rbp-71h]
  __int64 v32; // [rsp+70h] [rbp-69h]
  __int64 v33; // [rsp+78h] [rbp-61h]
  wchar_t *Str; // [rsp+80h] [rbp-59h] BYREF
  __int64 v35; // [rsp+88h] [rbp-51h] BYREF
  const OLECHAR *v36; // [rsp+90h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-41h] BYREF
  int (__fastcall ***pv)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-29h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-21h] BYREF
  const OLECHAR *v40; // [rsp+C0h] [rbp-19h] BYREF
  const OLECHAR *v41; // [rsp+C8h] [rbp-11h] BYREF
  int v42; // [rsp+D0h] [rbp-9h] BYREF
  __int128 v43; // [rsp+D8h] [rbp-1h]
  int v44; // [rsp+E8h] [rbp+Fh]
  int v45; // [rsp+ECh] [rbp+13h]
  BSTR *p_bstrString; // [rsp+F0h] [rbp+17h]
  BSTR *v47; // [rsp+F8h] [rbp+1Fh]
  __int64 plUbound; // [rsp+140h] [rbp+67h] BYREF
  const OLECHAR *plLbound; // [rsp+150h] [rbp+77h] BYREF
  __int64 rgIndices; // [rsp+158h] [rbp+7Fh] BYREF

  psz = (OLECHAR *)&unk_180070020;
  v30 = 0;
  v31 = 0;
  v32 = 50;
  v33 = 50;
  for ( i = *this; ; ++i )
  {
    v5 = *i;
    if ( !(_WORD)v5 )
      break;
    if ( (_WORD)v5 != 37 || (++i, v5 = 37, *i == 37) )
    {
      WString2::operator+=(&psz, v5);
      continue;
    }
    v6 = wcschr(i, 0x25u);
    if ( !v6 )
    {
      WString2::operator+=(&psz, L"<error>");
      break;
    }
    v7 = wcschr(i, 0x28u);
    if ( v7 )
    {
      if ( v7 < v6 )
      {
        v8 = wcschr(v7 + 1, 0x29u);
        if ( v8 )
          v6 = wcschr(v8 + 1, 0x25u);
      }
    }
    v9 = v6 - i;
    v10 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v9 + 1, 2u));
    std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&Str, v10);
    v11 = Str;
    if ( !Str )
    {
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&Str);
      WString2::DeleteString((WString2 *)&psz, 1);
      return 0;
    }
    v12 = StringCchCopyNW(Str, v9 + 1, i, v6 - i);
    v13 = v12;
    if ( v12 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v12);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_caa7cf28e9283147a4c859e60103ff52_Traceguids, v13);
      }
    }
    *(_WORD *)std::unique_ptr<unsigned short [0]>::operator[](&Str, v9) = 0;
    v14 = wcschr(v11, 0x28u);
    v15 = v14;
    if ( v14 )
    {
      *v14 = 0;
      v15 = v14 + 1;
      v16 = wcschr(v14 + 1, 0x29u);
      if ( v16 )
        *v16 = 0;
      else
        v15 = 0;
    }
    if ( !(unsigned int)wbem_wcsicmp(v11, L"__TEXT") )
    {
      plUbound = 0;
      ((void (__fastcall *)(struct IWbemClassObject *, _QWORD, __int64 *))a2->lpVtbl->GetObjectText)(a2, 0, &plUbound);
      if ( plUbound )
      {
        v39 = plUbound;
        WString2::operator+=(&psz, plUbound);
        CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v39);
      }
      else
      {
        WString2::operator+=(&psz, L"<error>");
      }
      goto LABEL_63;
    }
    if ( CTextTemplate::IsEmbeddedObjectProperty((CTextTemplate *)this, v11) )
    {
      bstrString = CTextTemplate::HandleEmbeddedObjectProperties((CTextTemplate *)this, v11, a2);
      if ( bstrString )
      {
        p_bstrString = &bstrString;
        bstrString = CTextTemplate::ReturnEscapedReturns((CTextTemplate *)this, bstrString);
        if ( bstrString )
          CTextTemplate::ConcatWithoutQuotes((CTextTemplate *)this, (struct WString2 *)&psz, &bstrString);
        SysFreeString(bstrString);
      }
      goto LABEL_63;
    }
    VariantInit(&pvarg);
    v27 = 0;
    v17 = ((__int64 (__fastcall *)(struct IWbemClassObject *, wchar_t *, _QWORD, VARIANTARG *, int *, _QWORD))a2->lpVtbl->Get)(
            a2,
            v11,
            0,
            &pvarg,
            &v27,
            0);
    if ( v17 == -2147217406 )
    {
      v18 = L"<unknown>";
    }
    else if ( v17 >= 0 )
    {
      switch ( pvarg.vt )
      {
        case 1u:
          v18 = L"<null>";
          break;
        case 0xDu:
          plLbound = 0;
          plUbound = 0;
          if ( (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
                 pvarg.llVal,
                 &IID_IWbemClassObject,
                 &plUbound) >= 0 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, const OLECHAR **))(*(_QWORD *)plUbound + 104LL))(
              plUbound,
              0,
              &plLbound);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)plUbound + 16LL))(plUbound);
          }
          v40 = plLbound;
          v19 = plLbound;
          if ( !plLbound )
            v19 = L"<error>";
          WString2::operator+=(&psz, v19);
          CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v40);
          goto LABEL_62;
        case 0x200Du:
          rgIndices = 0;
          LODWORD(plLbound) = 0;
          LODWORD(plUbound) = 0;
          SafeArrayGetDim(pvarg.parray);
          SafeArrayGetLBound(pvarg.parray, 1u, (LONG *)&plLbound);
          SafeArrayGetUBound(pvarg.parray, 1u, (LONG *)&plUbound);
          WString2::operator+=(&psz, L"{");
          for ( j = (int)plLbound; ; j = rgIndices + 1 )
          {
            LODWORD(rgIndices) = j;
            if ( j > (int)plUbound )
              break;
            pv = 0;
            SafeArrayGetElement(pvarg.parray, (LONG *)&rgIndices, &pv);
            v36 = 0;
            v35 = 0;
            if ( (**pv)(pv, &IID_IWbemClassObject, &v35) >= 0 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, const OLECHAR **))(*(_QWORD *)v35 + 104LL))(v35, 0, &v36);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            }
            v41 = v36;
            v21 = v36;
            if ( !v36 )
              v21 = L"<error>";
            WString2::operator+=(&psz, v21);
            if ( (int)rgIndices < (int)plUbound )
              WString2::operator+=(&psz, L", ");
            CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v41);
          }
          v18 = L"}";
          break;
        default:
          v44 = 0;
          v42 = 0;
          v45 = 1;
          v43 = 0;
          CVar::SetVariant((CVar *)&v42, &pvarg, 0);
          Text = CVar::GetText((CVar *)&v42, 0, v27, v15);
          v26 = Text;
          v47 = &v26;
          if ( Text )
          {
            if ( (pvarg.vt & 0x2000) != 0 )
            {
              Text = CTextTemplate::ProcessArray((CTextTemplate *)this, &pvarg, Text);
              v26 = Text;
            }
            if ( Text )
            {
              v26 = CTextTemplate::ReturnEscapedReturns((CTextTemplate *)this, Text);
              if ( v26 )
                CTextTemplate::ConcatWithoutQuotes((CTextTemplate *)this, (struct WString2 *)&psz, &v26);
            }
          }
          else
          {
            WString2::operator+=(&psz, L"<error>");
          }
          SysFreeString(v26);
          CVar::~CVar((CVar *)&v42);
          goto LABEL_62;
      }
    }
    else
    {
      v18 = L"<failed>";
    }
    WString2::operator+=(&psz, v18);
LABEL_62:
    _variant_t::~_variant_t((_variant_t *)&pvarg);
LABEL_63:
    i = v6;
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&Str);
  }
  v24 = psz;
  v25 = SysAllocString(psz);
  if ( v24 != (OLECHAR *)&unk_180070020 )
  {
    CMUILocale::_Free(v24);
    v30 = 0;
    psz = (OLECHAR *)&unk_180070020;
    v31 = 0;
  }
  return v25;
}

```

## disassembly

```asm
0x1800016f0  mov     [rsp-8+arg_8], rbx
0x1800016f5  push    rbp
0x1800016f6  push    rsi
0x1800016f7  push    rdi
0x1800016f8  push    r12
0x1800016fa  push    r13
0x1800016fc  push    r14
0x1800016fe  push    r15
0x180001700  lea     rbp, [rsp-27h]
0x180001705  sub     rsp, 100h
0x18000170c  mov     r13, rdx
0x18000170f  mov     r15, rcx
0x180001712  lea     rsi, unk_180070020
0x180001719  mov     [rsp+130h+psz], rsi
0x18000171e  xor     r14d, r14d
0x180001721  mov     [rbp+57h+var_D0], r14
0x180001725  mov     [rbp+57h+var_C8], r14
0x180001729  lea     eax, [r14+32h]
0x18000172d  mov     [rbp+57h+var_C0], rax
0x180001731  mov     [rbp+57h+var_B8], rax
0x180001735  mov     rdi, [rcx]
0x180001738  lea     ebx, [rax-0Dh]
0x18000173b  movzx   edx, word ptr [rdi]
0x18000173e  test    dx, dx
0x180001741  jz      loc_180001CAF
0x180001747  cmp     dx, bx
0x18000174a  jnz     short loc_180001757
0x18000174c  add     rdi, 2
0x180001750  mov     edx, ebx; Ch
0x180001752  cmp     [rdi], bx
0x180001755  jnz     short loc_180001766
0x180001757  lea     rcx, [rsp+130h+psz]
0x18000175c  call    ??YWString2@@QEAAAEAV0@G@Z; WString2::operator+=(ushort)
0x180001761  jmp     loc_180001C7B
0x180001766  mov     rcx, rdi; Str
0x180001769  call    cs:__imp_wcschr
0x18000176f  mov     r12, rax
0x180001772  test    rax, rax
0x180001775  jz      loc_180001C9E
0x18000177b  mov     edx, 28h ; '('; Ch
0x180001780  mov     rcx, rdi; Str
0x180001783  call    cs:__imp_wcschr
0x180001789  test    rax, rax
0x18000178c  jz      short loc_1800017B6
0x18000178e  cmp     rax, r12
0x180001791  jnb     short loc_1800017B6
0x180001793  mov     edx, 29h ; ')'; Ch
0x180001798  lea     rcx, [rax+2]; Str
0x18000179c  call    cs:__imp_wcschr
0x1800017a2  test    rax, rax
0x1800017a5  jz      short loc_1800017B6
0x1800017a7  mov     edx, ebx; Ch
0x1800017a9  lea     rcx, [rax+2]; Str
0x1800017ad  call    cs:__imp_wcschr
0x1800017b3  mov     r12, rax
0x1800017b6  mov     rsi, r12
0x1800017b9  sub     rsi, rdi
0x1800017bc  sar     rsi, 1
0x1800017bf  lea     r14, [rsi+1]
0x1800017c3  mov     eax, 2
0x1800017c8  mul     r14
0x1800017cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800017d2  cmovb   rax, rcx
0x1800017d6  mov     rcx, rax; unsigned __int64
0x1800017d9  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800017de  mov     rdx, rax
0x1800017e1  lea     rcx, [rbp+57h+Str]
0x1800017e5  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x1800017ea  nop
0x1800017eb  mov     rbx, [rbp+57h+Str]
0x1800017ef  test    rbx, rbx
0x1800017f2  jz      loc_180001C84
0x1800017f8  mov     r9, rsi; unsigned __int64
0x1800017fb  mov     r8, rdi; unsigned __int16 *
0x1800017fe  mov     rdx, r14; unsigned __int64
0x180001801  mov     rcx, rbx; unsigned __int16 *
0x180001804  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180001809  mov     edi, eax
0x18000180b  xor     r14d, r14d
0x18000180e  test    eax, eax
0x180001810  jns     short loc_180001856
0x180001812  mov     edx, eax; int
0x180001814  lea     rcx, unk_18006A9C0; this
0x18000181b  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001820  lea     rax, WPP_GLOBAL_Control
0x180001827  mov     rcx, cs:WPP_GLOBAL_Control
0x18000182e  cmp     rcx, rax
0x180001831  jz      short loc_180001856
0x180001833  test    byte ptr [rcx+1Ch], 1
0x180001837  jz      short loc_180001856
0x180001839  cmp     byte ptr [rcx+19h], 2
0x18000183d  jb      short loc_180001856
0x18000183f  lea     edx, [r14+0Ah]
0x180001843  mov     r9d, edi
0x180001846  lea     r8, WPP_caa7cf28e9283147a4c859e60103ff52_Traceguids
0x18000184d  mov     rcx, [rcx+10h]
0x180001851  call    WPP_SF_D
0x180001856  mov     rdx, rsi
0x180001859  lea     rcx, [rbp+57h+Str]
0x18000185d  call    ??A?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEBAAEAG_K@Z; std::unique_ptr<ushort [0]>::operator[](unsigned __int64)
0x180001862  mov     [rax], r14w
0x180001866  mov     edx, 28h ; '('; Ch
0x18000186b  mov     rcx, rbx; Str
0x18000186e  call    cs:__imp_wcschr
0x180001874  mov     rdi, rax
0x180001877  test    rax, rax
0x18000187a  jz      short loc_1800018A0
0x18000187c  mov     [rax], r14w
0x180001880  add     rdi, 2
0x180001884  mov     edx, 29h ; ')'; Ch
0x180001889  mov     rcx, rdi; Str
0x18000188c  call    cs:__imp_wcschr
0x180001892  test    rax, rax
0x180001895  jz      short loc_18000189D
0x180001897  mov     [rax], r14w
0x18000189b  jmp     short loc_1800018A0
0x18000189d  mov     rdi, r14
0x1800018a0  lea     rdx, aText; "__TEXT"
0x1800018a7  mov     rcx, rbx; unsigned __int16 *
0x1800018aa  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800018af  test    eax, eax
0x1800018b1  jnz     short loc_18000190D
0x1800018b3  mov     [rbp+57h+plUbound], r14
0x1800018b7  mov     rax, [r13+0]
0x1800018bb  lea     r8, [rbp+57h+plUbound]
0x1800018bf  xor     edx, edx
0x1800018c1  mov     rcx, r13
0x1800018c4  mov     rax, [rax+68h]
0x1800018c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018cd  mov     rax, [rbp+57h+plUbound]
0x1800018d1  test    rax, rax
0x1800018d4  jz      short loc_1800018F7
0x1800018d6  mov     [rbp+57h+var_78], rax
0x1800018da  mov     rdx, [rbp+57h+plUbound]
0x1800018de  lea     rcx, [rsp+130h+psz]
0x1800018e3  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x1800018e8  nop
0x1800018e9  lea     rcx, [rbp+57h+var_78]; this
0x1800018ed  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x1800018f2  jmp     loc_180001C6A
0x1800018f7  lea     rdx, aError; "<error>"
0x1800018fe  lea     rcx, [rsp+130h+psz]
0x180001903  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180001908  jmp     loc_180001C6A
0x18000190d  mov     rdx, rbx; unsigned __int16 *
0x180001910  mov     rcx, r15; this
0x180001913  call    ?IsEmbeddedObjectProperty@CTextTemplate@@AEAAHPEAG@Z; CTextTemplate::IsEmbeddedObjectProperty(ushort *)
0x180001918  test    eax, eax
0x18000191a  jz      short loc_18000197B
0x18000191c  mov     r8, r13; struct IWbemClassObject *
0x18000191f  mov     rdx, rbx; unsigned __int16 *
0x180001922  mov     rcx, r15; this
0x180001925  call    ?HandleEmbeddedObjectProperties@CTextTemplate@@AEAAPEAGPEAGPEAUIWbemClassObject@@@Z; CTextTemplate::HandleEmbeddedObjectProperties(ushort *,IWbemClassObject *)
0x18000192a  mov     [rsp+130h+bstrString], rax
0x18000192f  test    rax, rax
0x180001932  jz      loc_180001C6A
0x180001938  lea     rax, [rsp+130h+bstrString]
0x18000193d  mov     [rbp+57h+var_40], rax
0x180001941  mov     rdx, [rsp+130h+bstrString]; unsigned __int16 *
0x180001946  mov     rcx, r15; this
0x180001949  call    ?ReturnEscapedReturns@CTextTemplate@@AEAAPEAGPEAG@Z; CTextTemplate::ReturnEscapedReturns(ushort *)
0x18000194e  mov     [rsp+130h+bstrString], rax
0x180001953  test    rax, rax
0x180001956  jz      short loc_18000196B
0x180001958  lea     r8, [rsp+130h+bstrString]; unsigned __int16 **
0x18000195d  lea     rdx, [rsp+130h+psz]; struct WString2 *
0x180001962  mov     rcx, r15; this
0x180001965  call    ?ConcatWithoutQuotes@CTextTemplate@@AEAAXAEAVWString2@@AEAPEAG@Z; CTextTemplate::ConcatWithoutQuotes(WString2 &,ushort * &)
0x18000196a  nop
0x18000196b  mov     rcx, [rsp+130h+bstrString]; bstrString
0x180001970  call    cs:__imp_SysFreeString
0x180001976  jmp     loc_180001C6A
0x18000197b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000197f  call    cs:__imp_VariantInit
0x180001985  nop
0x180001986  mov     [rsp+130h+var_E8], r14d
0x18000198b  mov     rax, [r13+0]
0x18000198f  mov     [rsp+130h+var_108], r14
0x180001994  lea     rcx, [rsp+130h+var_E8]
0x180001999  mov     [rsp+130h+var_110], rcx
0x18000199e  lea     r9, [rbp+57h+pvarg]
0x1800019a2  xor     r8d, r8d
0x1800019a5  mov     rdx, rbx
0x1800019a8  mov     rcx, r13
0x1800019ab  mov     rax, [rax+20h]
0x1800019af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019b4  cmp     eax, 80041002h
0x1800019b9  jnz     short loc_1800019C7
0x1800019bb  lea     rdx, psz; "<unknown>"
0x1800019c2  jmp     loc_180001B90
0x1800019c7  test    eax, eax
0x1800019c9  jns     short loc_1800019D7
0x1800019cb  lea     rdx, aFailed; "<failed>"
0x1800019d2  jmp     loc_180001B90
0x1800019d7  movzx   eax, word ptr [rbp+57h+pvarg]
0x1800019db  mov     ebx, 1
0x1800019e0  cmp     ax, bx
0x1800019e3  jnz     short loc_1800019F1
0x1800019e5  lea     rdx, aNull; "<null>"
0x1800019ec  jmp     loc_180001B90
0x1800019f1  cmp     ax, 0Dh
0x1800019f5  jnz     short loc_180001A74
0x1800019f7  mov     [rbp+57h+plLbound], r14
0x1800019fb  mov     [rbp+57h+plUbound], r14
0x1800019ff  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x180001a03  mov     rax, [rcx]
0x180001a06  lea     r8, [rbp+57h+plUbound]
0x180001a0a  lea     rdx, IID_IWbemClassObject
0x180001a11  mov     rax, [rax]
0x180001a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a19  test    eax, eax
0x180001a1b  js      short loc_180001A43
0x180001a1d  mov     rcx, [rbp+57h+plUbound]
0x180001a21  mov     rax, [rcx]
0x180001a24  lea     r8, [rbp+57h+plLbound]
0x180001a28  xor     edx, edx
0x180001a2a  mov     rax, [rax+68h]
0x180001a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a33  mov     rcx, [rbp+57h+plUbound]
0x180001a37  mov     rax, [rcx]
0x180001a3a  mov     rax, [rax+10h]
0x180001a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a43  mov     rax, [rbp+57h+plLbound]
0x180001a47  mov     [rbp+57h+var_70], rax
0x180001a4b  mov     rdx, [rbp+57h+plLbound]
0x180001a4f  lea     rcx, [rsp+130h+psz]
0x180001a54  test    rdx, rdx
0x180001a57  jnz     short loc_180001A60
0x180001a59  lea     rdx, aError; "<error>"
0x180001a60  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180001a65  nop
0x180001a66  lea     rcx, [rbp+57h+var_70]; this
0x180001a6a  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180001a6f  jmp     loc_180001C61
0x180001a74  mov     ecx, 200Dh
0x180001a79  cmp     ax, cx
0x180001a7c  jnz     loc_180001B9F
0x180001a82  mov     [rbp+57h+rgIndices], r14
0x180001a86  mov     dword ptr [rbp+57h+plLbound], r14d
0x180001a8a  mov     dword ptr [rbp+57h+plUbound], r14d
0x180001a8e  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180001a92  call    cs:__imp_SafeArrayGetDim
0x180001a98  lea     r8, [rbp+57h+plLbound]; plLbound
0x180001a9c  mov     edx, ebx; nDim
0x180001a9e  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180001aa2  call    cs:__imp_SafeArrayGetLBound
0x180001aa8  lea     r8, [rbp+57h+plUbound]; plUbound
0x180001aac  mov     edx, ebx; nDim
0x180001aae  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180001ab2  call    cs:__imp_SafeArrayGetUBound
0x180001ab8  lea     rdx, asc_18004B7F0; "{"
0x180001abf  lea     rcx, [rsp+130h+psz]
0x180001ac4  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180001ac9  mov     eax, dword ptr [rbp+57h+plLbound]
0x180001acc  jmp     loc_180001B7D
0x180001ad1  mov     [rbp+57h+pv], r14
0x180001ad5  lea     r8, [rbp+57h+pv]; pv
0x180001ad9  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180001add  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180001ae1  call    cs:__imp_SafeArrayGetElement
0x180001ae7  mov     [rbp+57h+var_A0], r14
0x180001aeb  mov     [rbp+57h+var_A8], r14
0x180001aef  mov     rcx, [rbp+57h+pv]
0x180001af3  mov     rax, [rcx]
0x180001af6  lea     r8, [rbp+57h+var_A8]
0x180001afa  lea     rdx, IID_IWbemClassObject
0x180001b01  mov     rax, [rax]
0x180001b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b09  test    eax, eax
0x180001b0b  js      short loc_180001B33
0x180001b0d  mov     rcx, [rbp+57h+var_A8]
0x180001b11  mov     rax, [rcx]
0x180001b14  lea     r8, [rbp+57h+var_A0]
0x180001b18  xor     edx, edx
0x180001b1a  mov     rax, [rax+68h]
0x180001b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b23  mov     rcx, [rbp+57h+var_A8]
0x180001b27  mov     rax, [rcx]
0x180001b2a  mov     rax, [rax+10h]
0x180001b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b33  mov     rax, [rbp+57h+var_A0]
0x180001b37  mov     [rbp+57h+var_68], rax
0x180001b3b  mov     rdx, [rbp+57h+var_A0]
0x180001b3f  lea     rcx, [rsp+130h+psz]
0x180001b44  test    rdx, rdx
0x180001b47  jnz     short loc_180001B50
0x180001b49  lea     rdx, aError; "<error>"
0x180001b50  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180001b55  mov     eax, dword ptr [rbp+57h+plUbound]
0x180001b58  cmp     dword ptr [rbp+57h+rgIndices], eax
0x180001b5b  jge     short loc_180001B6F
0x180001b5d  lea     rdx, asc_18004B1DC; ", "
0x180001b64  lea     rcx, [rsp+130h+psz]
0x180001b69  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180001b6e  nop
0x180001b6f  lea     rcx, [rbp+57h+var_68]; this
0x180001b73  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180001b78  mov     eax, dword ptr [rbp+57h+rgIndices]
0x180001b7b  add     eax, ebx
0x180001b7d  cmp     eax, dword ptr [rbp+57h+plUbound]
  ... truncated ...
```

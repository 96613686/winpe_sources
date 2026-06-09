# User::LookupUserSid(_bstr_t &,_bstr_t &,_SID_NAME_USE &,void *)

- ea: `0x18002ab10`
- end: `0x18002ae13`
- name: `?LookupUserSid@User@@CAHAEAV_bstr_t@@0AEAW4_SID_NAME_USE@@PEAX@Z`
- size: `771`
- prototype: `__int64 __fastcall(struct _bstr_t *this, struct _bstr_t *, enum _SID_NAME_USE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009280`

## callees

- `0x180007e90`
- `0x180009150`
- `0x18002ab10`
- `0x18003b74c`
- `0x18003c664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab77`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ac42`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ac6b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ac42`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ac6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002abf1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac01`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac10`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac99`
- `OLEAUT32!__imp_SysFreeString` at `0x18002acdc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ad1b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ad2b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002abf1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac01`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac10`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac99`
- `OLEAUT32!__imp_SysFreeString` at `0x18002acdc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ad1b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ad2b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002aca8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002aceb`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002aca8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002aceb`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002acb9`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002acfc`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002acb9`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002acfc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002ab6b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002abd7`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002ab6b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002abd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall User::LookupUserSid(struct _bstr_t *this, struct _bstr_t *a2, enum _SID_NAME_USE *a3, void *a4)
{
  WCHAR *v7; // rbx
  BSTR v8; // r14
  BSTR v9; // rsi
  UINT v10; // edx
  WCHAR *v11; // rdi
  UINT v12; // edx
  unsigned int v13; // r15d
  UINT v15; // eax
  UINT v16; // eax
  BSTR *v17; // rax
  struct IErrorInfo *v18; // rdx
  BSTR *v19; // rbx
  BSTR *v20; // rax
  struct IErrorInfo *v21; // rdx
  BSTR *v22; // rbx
  DWORD ui; // [rsp+30h] [rbp-38h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-34h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-30h] BYREF
  BSTR v26; // [rsp+40h] [rbp-28h]
  WCHAR *v27; // [rsp+48h] [rbp-20h]
  WCHAR *v28; // [rsp+50h] [rbp-18h] BYREF
  BSTR v29; // [rsp+58h] [rbp-10h]

  v7 = 0;
  cchName = 0;
  ui = 0;
  peUse = SidTypeUnknown;
  v8 = 0;
  v29 = 0;
  v9 = 0;
  v26 = 0;
  LookupAccountSidLocalW(a4, 0, &cchName, 0, &ui, &peUse);
  if ( GetLastError() == 122 )
  {
    v10 = cchName++;
    if ( v10 )
    {
      v11 = SysAllocStringLen(0, v10);
      v27 = v11;
      if ( !v11 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    else
    {
      v11 = 0;
      v27 = 0;
    }
    v12 = ui++;
    if ( v12 )
    {
      v7 = SysAllocStringLen(0, v12);
      v28 = v7;
      if ( !v7 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    else
    {
      v28 = 0;
    }
    v13 = LookupAccountSidLocalW(a4, v11, &cchName, v7, &ui, &peUse);
    if ( v13 )
    {
      if ( v11 )
      {
        SysFreeString(0);
        v15 = SysStringByteLen(v11);
        v8 = SysAllocStringByteLen((LPCSTR)v11, v15);
        v29 = v8;
        if ( !v8 )
          goto LABEL_28;
      }
      if ( v7 )
      {
        SysFreeString(0);
        v16 = SysStringByteLen(v7);
        v9 = SysAllocStringByteLen((LPCSTR)v7, v16);
        v26 = v9;
        if ( !v9 )
LABEL_28:
          ATL::PrivateAtlThrow(-2147024882);
      }
      SysFreeString(v7);
      SysFreeString(v11);
      v17 = (BSTR *)operator new(0x18u);
      v19 = v17;
      v28 = (WCHAR *)v17;
      v13 = 1;
      if ( v17 )
      {
        v17[1] = 0;
        *((_DWORD *)v17 + 4) = 1;
        *v17 = v9;
      }
      else
      {
        v19 = 0;
      }
      v28 = (WCHAR *)v19;
      if ( !v19 )
        _com_raise_error(-2147024882, v18);
      _InterlockedIncrement((volatile signed __int32 *)v19 + 4);
      _bstr_t::_Free(this);
      *(_QWORD *)this = v19;
      _bstr_t::_Free((_bstr_t *)&v28);
      v26 = 0;
      v20 = (BSTR *)operator new(0x18u);
      v22 = v20;
      v28 = (WCHAR *)v20;
      if ( v20 )
      {
        v20[1] = 0;
        *((_DWORD *)v20 + 4) = 1;
        *v20 = v8;
      }
      else
      {
        v22 = 0;
      }
      v28 = (WCHAR *)v22;
      if ( !v22 )
        _com_raise_error(-2147024882, v21);
      _InterlockedIncrement((volatile signed __int32 *)v22 + 4);
      _bstr_t::_Free(a2);
      *(_QWORD *)a2 = v22;
      _bstr_t::_Free((_bstr_t *)&v28);
      *a3 = peUse;
    }
    else
    {
      SysFreeString(v7);
      SysFreeString(v11);
    }
  }
  else
  {
    v13 = 0;
  }
  SysFreeString(0);
  SysFreeString(0);
  return v13;
}

```

## disassembly

```asm
0x18002ab10  mov     [rsp-40h+arg_10], r8
0x18002ab15  push    rbp
0x18002ab16  push    rbx
0x18002ab17  push    rsi
0x18002ab18  push    rdi
0x18002ab19  push    r12
0x18002ab1b  push    r13
0x18002ab1d  push    r14
0x18002ab1f  push    r15
0x18002ab21  mov     rbp, rsp
0x18002ab24  sub     rsp, 68h
0x18002ab28  mov     r15, r9
0x18002ab2b  mov     r13, rdx
0x18002ab2e  mov     r12, rcx
0x18002ab31  xor     ebx, ebx
0x18002ab33  mov     [rbp+cchName], ebx
0x18002ab36  mov     [rbp+ui], ebx
0x18002ab39  mov     [rbp+var_30], 8
0x18002ab40  mov     r14d, ebx
0x18002ab43  mov     [rbp+var_10], rbx
0x18002ab47  mov     esi, ebx
0x18002ab49  mov     [rbp+var_28], rbx
0x18002ab4d  lea     rax, [rbp+var_30]
0x18002ab51  mov     [rsp+68h+peUse], rax; peUse
0x18002ab56  lea     rax, [rbp+ui]
0x18002ab5a  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002ab5f  xor     r9d, r9d; ReferencedDomainName
0x18002ab62  lea     r8, [rbp+cchName]; cchName
0x18002ab66  xor     edx, edx; Name
0x18002ab68  mov     rcx, r15; Sid
0x18002ab6b  call    cs:__imp_LookupAccountSidLocalW
0x18002ab72  nop     dword ptr [rax+rax+00h]
0x18002ab77  call    cs:__imp_GetLastError
0x18002ab7e  nop     dword ptr [rax+rax+00h]
0x18002ab83  cmp     eax, 7Ah ; 'z'
0x18002ab86  jnz     loc_18002ADD8
0x18002ab8c  mov     edx, [rbp+cchName]; ui
0x18002ab8f  lea     eax, [rdx+1]
0x18002ab92  mov     [rbp+cchName], eax
0x18002ab95  test    edx, edx
0x18002ab97  jnz     loc_18002AC40
0x18002ab9d  mov     edi, ebx
0x18002ab9f  mov     [rbp+var_20], rbx
0x18002aba3  mov     edx, [rbp+ui]; ui
0x18002aba6  lea     eax, [rdx+1]
0x18002aba9  mov     [rbp+ui], eax
0x18002abac  test    edx, edx
0x18002abae  jnz     loc_18002AC69
0x18002abb4  mov     [rbp+var_18], rbx
0x18002abb8  lea     rax, [rbp+var_30]
0x18002abbc  mov     [rsp+68h+peUse], rax; peUse
0x18002abc1  lea     rax, [rbp+ui]
0x18002abc5  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002abca  mov     r9, rbx; ReferencedDomainName
0x18002abcd  lea     r8, [rbp+cchName]; cchName
0x18002abd1  mov     rdx, rdi; Name
0x18002abd4  mov     rcx, r15; Sid
0x18002abd7  call    cs:__imp_LookupAccountSidLocalW
0x18002abde  nop     dword ptr [rax+rax+00h]
0x18002abe3  mov     r15d, eax
0x18002abe6  test    eax, eax
0x18002abe8  jnz     loc_18002AC92
0x18002abee  mov     rcx, rbx; bstrString
0x18002abf1  call    cs:__imp_SysFreeString
0x18002abf8  nop     dword ptr [rax+rax+00h]
0x18002abfd  nop
0x18002abfe  mov     rcx, rdi; bstrString
0x18002ac01  call    cs:__imp_SysFreeString
0x18002ac08  nop     dword ptr [rax+rax+00h]
0x18002ac0d  nop
0x18002ac0e  xor     ecx, ecx; bstrString
0x18002ac10  call    cs:__imp_SysFreeString
0x18002ac17  nop     dword ptr [rax+rax+00h]
0x18002ac1c  nop
0x18002ac1d  xor     ecx, ecx; bstrString
0x18002ac1f  call    cs:__imp_SysFreeString
0x18002ac26  nop     dword ptr [rax+rax+00h]
0x18002ac2b  mov     eax, r15d
0x18002ac2e  add     rsp, 68h
0x18002ac32  pop     r15
0x18002ac34  pop     r14
0x18002ac36  pop     r13
0x18002ac38  pop     r12
0x18002ac3a  pop     rdi
0x18002ac3b  pop     rsi
0x18002ac3c  pop     rbx
0x18002ac3d  pop     rbp
0x18002ac3e  retn
0x18002ac40  xor     ecx, ecx; strIn
0x18002ac42  call    cs:__imp_SysAllocStringLen
0x18002ac49  nop     dword ptr [rax+rax+00h]
0x18002ac4e  mov     rdi, rax
0x18002ac51  mov     [rbp+var_20], rax
0x18002ac55  test    rax, rax
0x18002ac58  jnz     loc_18002ABA3
0x18002ac5e  mov     ecx, 8007000Eh; int
0x18002ac63  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002ac69  xor     ecx, ecx; strIn
0x18002ac6b  call    cs:__imp_SysAllocStringLen
0x18002ac72  nop     dword ptr [rax+rax+00h]
0x18002ac77  mov     rbx, rax
0x18002ac7a  mov     [rbp+var_18], rax
0x18002ac7e  test    rax, rax
0x18002ac81  jnz     loc_18002ABB8
0x18002ac87  mov     ecx, 8007000Eh; int
0x18002ac8c  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002ac92  test    rdi, rdi
0x18002ac95  jz      short loc_18002ACD5
0x18002ac97  xor     ecx, ecx; bstrString
0x18002ac99  call    cs:__imp_SysFreeString
0x18002aca0  nop     dword ptr [rax+rax+00h]
0x18002aca5  mov     rcx, rdi; bstr
0x18002aca8  call    cs:__imp_SysStringByteLen
0x18002acaf  nop     dword ptr [rax+rax+00h]
0x18002acb4  mov     edx, eax; len
0x18002acb6  mov     rcx, rdi; psz
0x18002acb9  call    cs:__imp_SysAllocStringByteLen
0x18002acc0  nop     dword ptr [rax+rax+00h]
0x18002acc5  mov     r14, rax
0x18002acc8  mov     [rbp+var_10], rax
0x18002accc  test    rax, rax
0x18002accf  jz      loc_18002ADE0
0x18002acd5  test    rbx, rbx
0x18002acd8  jz      short loc_18002AD18
0x18002acda  xor     ecx, ecx; bstrString
0x18002acdc  call    cs:__imp_SysFreeString
0x18002ace3  nop     dword ptr [rax+rax+00h]
0x18002ace8  mov     rcx, rbx; bstr
0x18002aceb  call    cs:__imp_SysStringByteLen
0x18002acf2  nop     dword ptr [rax+rax+00h]
0x18002acf7  mov     edx, eax; len
0x18002acf9  mov     rcx, rbx; psz
0x18002acfc  call    cs:__imp_SysAllocStringByteLen
0x18002ad03  nop     dword ptr [rax+rax+00h]
0x18002ad08  mov     rsi, rax
0x18002ad0b  mov     [rbp+var_28], rax
0x18002ad0f  test    rax, rax
0x18002ad12  jz      loc_18002ADE0
0x18002ad18  mov     rcx, rbx; bstrString
0x18002ad1b  call    cs:__imp_SysFreeString
0x18002ad22  nop     dword ptr [rax+rax+00h]
0x18002ad27  nop
0x18002ad28  mov     rcx, rdi; bstrString
0x18002ad2b  call    cs:__imp_SysFreeString
0x18002ad32  nop     dword ptr [rax+rax+00h]
0x18002ad37  mov     ecx, 18h; unsigned __int64
0x18002ad3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ad41  mov     rbx, rax
0x18002ad44  mov     [rbp+var_18], rax
0x18002ad48  mov     r15d, 1
0x18002ad4e  test    rax, rax
0x18002ad51  jz      short loc_18002AD76
0x18002ad53  mov     qword ptr [rax+8], 0
0x18002ad5b  mov     [rax+10h], r15d
0x18002ad5f  mov     [rax], rsi
0x18002ad62  mov     [rbp+var_18], rbx
0x18002ad66  test    rbx, rbx
0x18002ad69  jnz     short loc_18002AD7A
0x18002ad6b  mov     ecx, 8007000Eh; int
0x18002ad70  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18002ad76  xor     ebx, ebx
0x18002ad78  jmp     short loc_18002AD62
0x18002ad7a  lock inc dword ptr [rbx+10h]
0x18002ad7e  mov     rcx, r12; this
0x18002ad81  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002ad86  mov     [r12], rbx
0x18002ad8a  lea     rcx, [rbp+var_18]; this
0x18002ad8e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002ad93  mov     [rbp+var_28], 0
0x18002ad9b  mov     ecx, 18h; unsigned __int64
0x18002ada0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ada5  mov     rbx, rax
0x18002ada8  mov     [rbp+var_18], rax
0x18002adac  test    rax, rax
0x18002adaf  jz      short loc_18002ADD4
0x18002adb1  mov     qword ptr [rax+8], 0
0x18002adb9  mov     [rax+10h], r15d
0x18002adbd  mov     [rax], r14
0x18002adc0  mov     [rbp+var_18], rbx
0x18002adc4  test    rbx, rbx
0x18002adc7  jnz     short loc_18002ADEB
0x18002adc9  mov     ecx, 8007000Eh; int
0x18002adce  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18002add4  xor     ebx, ebx
0x18002add6  jmp     short loc_18002ADC0
0x18002add8  mov     r15d, ebx
0x18002addb  jmp     loc_18002AC0E
0x18002ade0  mov     ecx, 8007000Eh; int
0x18002ade5  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002adeb  lock inc dword ptr [rbx+10h]
0x18002adef  mov     rcx, r13; this
0x18002adf2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002adf7  mov     [r13+0], rbx
0x18002adfb  lea     rcx, [rbp+var_18]; this
0x18002adff  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002ae04  mov     eax, [rbp+var_30]
0x18002ae07  mov     rcx, [rbp+arg_10]
0x18002ae0b  mov     [rcx], eax
0x18002ae0d  jmp     loc_18002AC0E
```

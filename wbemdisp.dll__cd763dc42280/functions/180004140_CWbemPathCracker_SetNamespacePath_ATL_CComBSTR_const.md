# CWbemPathCracker::SetNamespacePath(ATL::CComBSTR const &)

- ea: `0x180004140`
- end: `0x18000449e`
- name: `?SetNamespacePath@CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@@Z`
- size: `862`
- prototype: `bool __fastcall(CWbemPathCracker *__hidden this, const struct ATL::CComBSTR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800045c0`
- `0x18002f3b0`

## callees

- `0x180004140`
- `0x180004d28`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000436c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800043f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000436c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800043f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180004273`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000444c`
- `OLEAUT32!__imp_SysFreeString` at `0x180004273`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000444c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800041f4`
- `OLEAUT32!__imp_SysStringLen` at `0x18000440b`
- `OLEAUT32!__imp_SysStringLen` at `0x180004418`
- `OLEAUT32!__imp_SysStringLen` at `0x18000446f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800041f4`
- `OLEAUT32!__imp_SysStringLen` at `0x18000440b`
- `OLEAUT32!__imp_SysStringLen` at `0x180004418`
- `OLEAUT32!__imp_SysStringLen` at `0x18000446f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000432e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000432e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000438c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000438c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800041c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800041c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_BOOL8 __fastcall CWbemPathCracker::SetNamespacePath(CWbemPathCracker *this, BSTR *a2)
{
  bool v4; // r14
  int TypeFromText; // eax
  BSTR v6; // rsi
  __int64 v8; // rcx
  char v9; // r13
  unsigned int v10; // esi
  OLECHAR *v11; // rbx
  OLECHAR *v12; // rax
  OLECHAR *v13; // r15
  bool v14; // r12
  OLECHAR *v15; // rax
  OLECHAR *v16; // rbx
  int v17; // eax
  int v18; // ecx
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-10h]
  int v21; // [rsp+48h] [rbp-8h]
  int v22; // [rsp+4Ch] [rbp-4h]
  OLECHAR *v23; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+50h] BYREF
  OLECHAR *v25; // [rsp+A8h] [rbp+58h]

  v4 = 0;
  if ( *((_DWORD *)this + 7) == 1 && *((_QWORD *)this + 1) )
  {
    ppv = 0;
    bstrString = 0;
    v21 = 0;
    v22 = 1;
    _InterlockedIncrement(&g_cObj);
    CoCreateInstance(&CLSID_WbemDefPath, 0, 1u, &IID_IWbemPath, &ppv);
    TypeFromText = CWbemPathCracker::GetTypeFromText(a2);
    if ( TypeFromText )
    {
      if ( TypeFromText == 1 && ppv )
      {
        if ( *a2 && SysStringLen(*a2) > 1 && **a2 == 123 && (v6 = *a2, v6[SysStringLen(*a2) - 1] == 125) )
        {
          v15 = SysAllocString(*a2 + 1);
          v16 = v15;
          v23 = v15;
          if ( v15 && SysStringLen(v15) )
            v16[SysStringLen(v16) - 1] = 0;
          v17 = (*(__int64 (__fastcall **)(LPVOID, __int64, OLECHAR *))(*(_QWORD *)ppv + 24LL))(ppv, 12, v16);
          v18 = v22;
          if ( v17 >= 0 )
            v18 = 1;
          v22 = v18;
          SysFreeString(v16);
        }
        else if ( (*(int (__fastcall **)(LPVOID, __int64, BSTR))(*(_QWORD *)ppv + 24LL))(ppv, 12, *a2) >= 0 )
        {
          v22 = 1;
        }
      }
    }
    else
    {
      v22 = 0;
    }
    if ( v22 )
    {
      v24 = 0;
      if ( v22 == 1 && ppv && (*(int (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 64LL))(ppv, &v24) >= 0 )
      {
        if ( *((_DWORD *)this + 7) == 1 )
        {
          v8 = *((_QWORD *)this + 1);
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 96LL))(v8);
        }
        if ( v24 )
        {
          v9 = 1;
          v10 = 0;
          while ( v9 )
          {
            v11 = 0;
            v25 = 0;
            if ( v22 != 1 )
              goto LABEL_42;
            if ( !ppv )
              goto LABEL_42;
            LODWORD(v23) = 0;
            (*(void (__fastcall **)(LPVOID, _QWORD, OLECHAR **, _QWORD))(*(_QWORD *)ppv + 80LL))(ppv, v10, &v23, 0);
            v12 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)((_DWORD)v23 + 1), 2u));
            v13 = v12;
            if ( !v12 )
              goto LABEL_42;
            v14 = 0;
            v12[(unsigned int)v23] = 0;
            if ( (*(int (__fastcall **)(LPVOID, _QWORD, OLECHAR **, OLECHAR *))(*(_QWORD *)ppv + 80LL))(
                   ppv,
                   v10,
                   &v23,
                   v12) >= 0 )
            {
              v11 = SysAllocString(v13);
              v25 = v11;
              v14 = v11 != 0;
            }
            CWin32DefaultArena::WbemMemFree(v13);
            if ( !v14
              || (*(int (__fastcall **)(_QWORD, _QWORD, OLECHAR *))(**((_QWORD **)this + 1) + 72LL))(
                   *((_QWORD *)this + 1),
                   v10,
                   v11) < 0 )
            {
LABEL_42:
              v9 = 0;
            }
            SysFreeString(v11);
            if ( ++v10 >= v24 )
            {
              v4 = v9 != 0;
              break;
            }
          }
        }
      }
    }
    _InterlockedDecrement(&g_cObj);
    SysFreeString(bstrString);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return v4;
}

```

## disassembly

```asm
0x180004140  mov     [rsp-38h+arg_8], rbx
0x180004145  push    rbp
0x180004146  push    rsi
0x180004147  push    rdi
0x180004148  push    r12
0x18000414a  push    r13
0x18000414c  push    r14
0x18000414e  push    r15
0x180004150  mov     rbp, rsp
0x180004153  sub     rsp, 50h
0x180004157  mov     rbx, rdx
0x18000415a  mov     rdi, rcx
0x18000415d  xor     r14b, r14b
0x180004160  cmp     dword ptr [rcx+1Ch], 1
0x180004164  jnz     loc_180004290
0x18000416a  cmp     qword ptr [rcx+8], 0
0x18000416f  jz      loc_180004290
0x180004175  lea     rax, ??_7CWbemPathCracker@@6B@; const CWbemPathCracker::`vftable'
0x18000417c  mov     [rbp+var_20], rax
0x180004180  xor     r15d, r15d
0x180004183  mov     [rbp+var_18], r15
0x180004187  mov     [rbp+bstrString], r15
0x18000418b  mov     [rbp+var_8], r15d
0x18000418f  mov     r12d, 1
0x180004195  mov     [rbp+var_4], r12d
0x180004199  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800041a0  mov     rcx, [rbp+var_18]
0x1800041a4  test    rcx, rcx
0x1800041a7  jnz     loc_180004457
0x1800041ad  lea     rax, [rbp+var_18]
0x1800041b1  mov     [rsp+50h+ppv], rax; ppv
0x1800041b6  lea     r9, IID_IWbemPath; riid
0x1800041bd  mov     r8d, r12d; dwClsContext
0x1800041c0  xor     edx, edx; pUnkOuter
0x1800041c2  lea     rcx, CLSID_WbemDefPath; rclsid
0x1800041c9  call    cs:__imp_CoCreateInstance
0x1800041cf  nop
0x1800041d0  mov     rcx, rbx
0x1800041d3  call    ?GetTypeFromText@CWbemPathCracker@@CA?AW4WbemPathType@1@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::GetTypeFromText(ATL::CComBSTR const &)
0x1800041d8  test    eax, eax
0x1800041da  jz      loc_18000448C
0x1800041e0  cmp     eax, 1
0x1800041e3  jnz     short loc_180004230
0x1800041e5  cmp     [rbp+var_18], 0
0x1800041ea  jz      short loc_180004230
0x1800041ec  mov     rcx, [rbx]; pbstr
0x1800041ef  test    rcx, rcx
0x1800041f2  jz      short loc_180004210
0x1800041f4  call    cs:__imp_SysStringLen
0x1800041fa  cmp     eax, 1
0x1800041fd  jbe     short loc_180004210
0x1800041ff  mov     rsi, [rbx]
0x180004202  mov     eax, 7Bh ; '{'
0x180004207  cmp     ax, [rsi]
0x18000420a  jz      loc_18000446C
0x180004210  mov     rcx, [rbp+var_18]
0x180004214  mov     rax, [rcx]
0x180004217  mov     r8, [rbx]
0x18000421a  mov     edx, 0Ch
0x18000421f  mov     rax, [rax+18h]
0x180004223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004228  test    eax, eax
0x18000422a  js      short loc_180004230
0x18000422c  mov     [rbp+var_4], r12d
0x180004230  mov     ecx, [rbp+var_4]
0x180004233  test    ecx, ecx
0x180004235  jz      short loc_18000425D
0x180004237  mov     [rbp+arg_10], r15d
0x18000423b  cmp     ecx, 1
0x18000423e  jnz     short loc_18000425D
0x180004240  mov     rcx, [rbp+var_18]
0x180004244  test    rcx, rcx
0x180004247  jz      short loc_18000425D
0x180004249  mov     rax, [rcx]
0x18000424c  lea     rdx, [rbp+arg_10]
0x180004250  mov     rax, [rax+40h]
0x180004254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004259  test    eax, eax
0x18000425b  jns     short loc_1800042AC
0x18000425d  lea     rax, ??_7CWbemPathCracker@@6B@; const CWbemPathCracker::`vftable'
0x180004264  mov     [rbp+var_20], rax
0x180004268  lock dec cs:?g_cObj@@3JA; long g_cObj
0x18000426f  mov     rcx, [rbp+bstrString]; bstrString
0x180004273  call    cs:__imp_SysFreeString
0x180004279  nop
0x18000427a  mov     rcx, [rbp+var_18]
0x18000427e  test    rcx, rcx
0x180004281  jz      short loc_180004290
0x180004283  mov     rdx, [rcx]
0x180004286  mov     rax, [rdx+10h]
0x18000428a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000428f  nop
0x180004290  movzx   eax, r14b
0x180004294  mov     rbx, [rsp+50h+arg_8]
0x18000429c  add     rsp, 50h
0x1800042a0  pop     r15
0x1800042a2  pop     r14
0x1800042a4  pop     r13
0x1800042a6  pop     r12
0x1800042a8  pop     rdi
0x1800042a9  pop     rsi
0x1800042aa  pop     rbp
0x1800042ab  retn
0x1800042ac  cmp     dword ptr [rdi+1Ch], 1
0x1800042b0  jnz     short loc_1800042C7
0x1800042b2  mov     rcx, [rdi+8]
0x1800042b6  test    rcx, rcx
0x1800042b9  jz      short loc_1800042C7
0x1800042bb  mov     rax, [rcx]
0x1800042be  mov     rax, [rax+60h]
0x1800042c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c7  cmp     [rbp+arg_10], 0
0x1800042cb  jbe     short loc_18000425D
0x1800042cd  mov     r13b, 1
0x1800042d0  mov     esi, r15d
0x1800042d3  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800042da  test    r13b, r13b
0x1800042dd  jz      loc_18000425D
0x1800042e3  mov     rbx, r15
0x1800042e6  mov     [rbp+arg_18], rbx
0x1800042ea  cmp     [rbp+var_4], 1
0x1800042ee  jnz     loc_180004495
0x1800042f4  mov     rcx, [rbp+var_18]
0x1800042f8  test    rcx, rcx
0x1800042fb  jz      loc_180004495
0x180004301  mov     dword ptr [rbp+arg_0], r15d
0x180004305  mov     rax, [rcx]
0x180004308  xor     r9d, r9d
0x18000430b  lea     r8, [rbp+arg_0]
0x18000430f  mov     edx, esi
0x180004311  mov     rax, [rax+50h]
0x180004315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000431a  mov     ecx, dword ptr [rbp+arg_0]
0x18000431d  inc     ecx
0x18000431f  mov     eax, 2
0x180004324  mul     rcx
0x180004327  cmovb   rax, r12
0x18000432b  mov     rcx, rax
0x18000432e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180004334  mov     r15, rax
0x180004337  test    rax, rax
0x18000433a  jz      loc_180004495
0x180004340  xor     r12b, r12b
0x180004343  mov     edx, dword ptr [rbp+arg_0]
0x180004346  xor     ecx, ecx
0x180004348  mov     [rax+rdx*2], cx
0x18000434c  mov     rcx, [rbp+var_18]
0x180004350  mov     rdx, [rcx]
0x180004353  mov     rax, [rdx+50h]
0x180004357  mov     r9, r15
0x18000435a  lea     r8, [rbp+arg_0]
0x18000435e  mov     edx, esi
0x180004360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004365  test    eax, eax
0x180004367  js      short loc_180004389
0x180004369  mov     rcx, r15; psz
0x18000436c  call    cs:__imp_SysAllocString
0x180004372  mov     rbx, rax
0x180004375  mov     [rbp+arg_18], rax
0x180004379  movzx   r12d, r12b
0x18000437d  test    rax, rax
0x180004380  mov     eax, 1
0x180004385  cmovnz  r12d, eax
0x180004389  mov     rcx, r15
0x18000438c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180004392  nop
0x180004393  test    r12b, r12b
0x180004396  jz      loc_180004495
0x18000439c  mov     rcx, [rdi+8]
0x1800043a0  mov     rax, [rcx]
0x1800043a3  mov     r8, rbx
0x1800043a6  mov     edx, esi
0x1800043a8  mov     rax, [rax+48h]
0x1800043ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043b1  test    eax, eax
0x1800043b3  js      loc_180004495
0x1800043b9  mov     rcx, rbx; bstrString
0x1800043bc  call    cs:__imp_SysFreeString
0x1800043c2  inc     esi
0x1800043c4  cmp     esi, [rbp+arg_10]
0x1800043c7  mov     r15d, 0
0x1800043cd  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800043d4  jb      loc_1800042DA
0x1800043da  movzx   r14d, r14b
0x1800043de  test    r13b, r13b
0x1800043e1  mov     eax, 1
0x1800043e6  cmovnz  r14d, eax
0x1800043ea  jmp     loc_18000425D
0x1800043ef  mov     rcx, [rbx]
0x1800043f2  add     rcx, 2; psz
0x1800043f6  call    cs:__imp_SysAllocString
0x1800043fc  mov     rbx, rax
0x1800043ff  mov     [rbp+arg_0], rax
0x180004403  test    rax, rax
0x180004406  jz      short loc_180004425
0x180004408  mov     rcx, rax; pbstr
0x18000440b  call    cs:__imp_SysStringLen
0x180004411  test    eax, eax
0x180004413  jz      short loc_180004425
0x180004415  mov     rcx, rbx; pbstr
0x180004418  call    cs:__imp_SysStringLen
0x18000441e  dec     eax
0x180004420  mov     [rbx+rax*2], r15w
0x180004425  mov     rcx, [rbp+var_18]
0x180004429  mov     rax, [rcx]
0x18000442c  mov     r8, rbx
0x18000442f  mov     edx, 0Ch
0x180004434  mov     rax, [rax+18h]
0x180004438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443d  mov     ecx, [rbp+var_4]
0x180004440  test    eax, eax
0x180004442  cmovns  ecx, r12d
0x180004446  mov     [rbp+var_4], ecx
0x180004449  mov     rcx, rbx; bstrString
0x18000444c  call    cs:__imp_SysFreeString
0x180004452  jmp     loc_180004230
0x180004457  mov     [rbp+var_18], r15
0x18000445b  mov     rax, [rcx]
0x18000445e  mov     rax, [rax+10h]
0x180004462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004467  jmp     loc_1800041AD
0x18000446c  mov     rcx, rsi; pbstr
0x18000446f  call    cs:__imp_SysStringLen
0x180004475  lea     ecx, [rax-1]
0x180004478  mov     eax, 7Dh ; '}'
0x18000447d  cmp     ax, [rsi+rcx*2]
0x180004481  jnz     loc_180004210
0x180004487  jmp     loc_1800043EF
0x18000448c  mov     [rbp+var_4], r15d
0x180004490  jmp     loc_180004230
0x180004495  xor     r13b, r13b
0x180004498  jmp     loc_1800043B9
```

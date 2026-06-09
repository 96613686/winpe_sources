# Signal_Exception(_GUID const &,ushort const *,uint,...)

- ea: `0x14000a098`
- end: `0x14000a22f`
- name: `?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ`
- size: `407`
- prototype: `__int64(const struct _GUID *, const unsigned __int16 *, unsigned int, ...)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140002570`
- `0x14000ee80`
- `0x14000f1b0`
- `0x14000f2f0`
- `0x14000f700`

## callees

- `0x140009cf0`
- `0x14000a098`
- `0x1400146ac`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000a211`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a21a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a211`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a21a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000a1dc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000a1dc`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x14000a0df`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x14000a0df`

## pseudocode

```c
__int64 Signal_Exception(const struct _GUID *a1, const unsigned __int16 *a2, unsigned int a3, ...)
{
  OLECHAR *v4; // rdi
  unsigned __int16 *v5; // rsi
  HRESULT v7; // ebx
  int Str; // eax
  int v9; // eax
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-38h] BYREF
  LPCWCH lpWideCharStr; // [rsp+28h] [rbp-30h] BYREF
  char *v13; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v14; // [rsp+38h] [rbp-20h] BYREF
  IErrorInfo *perrinfo; // [rsp+40h] [rbp-18h] BYREF
  va_list va; // [rsp+A8h] [rbp+50h] BYREF

  va_start(va, a3);
  v13 = 0;
  v4 = 0;
  perrinfo = 0;
  v5 = 0;
  lpWideCharStr = 0;
  v14 = 0;
  pperrinfo = 0;
  v7 = CreateErrorInfo(&pperrinfo);
  if ( v7 >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a1);
    if ( v7 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo->lpVtbl->SetSource)(
             pperrinfo,
             a2);
      if ( v7 >= 0 )
      {
        Str = LoadStr((unsigned __int16 **)&lpWideCharStr, a3);
        v4 = (OLECHAR *)lpWideCharStr;
        if ( Str )
        {
          va_copy(v13, va);
          v9 = FormatLine(lpWideCharStr, &v14, &v13);
          v13 = 0;
          v7 = v9;
          v5 = v14;
          if ( v9 >= 0 )
          {
            v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
                   pperrinfo,
                   v14);
            if ( v7 >= 0 )
            {
              v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpFile)(pperrinfo, 0);
              if ( v7 >= 0 )
              {
                v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(
                       pperrinfo,
                       0);
                if ( v7 >= 0 )
                {
                  v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                         pperrinfo,
                         &IID_IErrorInfo,
                         &perrinfo);
                  if ( v7 >= 0 )
                    v7 = SetErrorInfo(0, perrinfo);
                }
              }
            }
          }
        }
        else
        {
          v7 = -2147024882;
        }
      }
    }
  }
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  SysFreeString(v4);
  SysFreeString(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a098  mov     [rsp-30h+arg_10], r8d
0x14000a09d  mov     [rsp-30h+arg_18], r9
0x14000a0a2  push    rbp
0x14000a0a3  push    rbx
0x14000a0a4  push    rsi
0x14000a0a5  push    rdi
0x14000a0a6  push    r14
0x14000a0a8  push    r15
0x14000a0aa  mov     rbp, rsp
0x14000a0ad  sub     rsp, 58h
0x14000a0b1  mov     r14, rcx
0x14000a0b4  mov     [rbp+var_28], 0
0x14000a0bc  xor     edi, edi
0x14000a0be  mov     [rbp+perrinfo], 0
0x14000a0c6  xor     esi, esi
0x14000a0c8  mov     [rbp+lpWideCharStr], rdi
0x14000a0cc  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x14000a0d0  mov     [rbp+var_20], rsi
0x14000a0d4  mov     r15, rdx
0x14000a0d7  mov     [rbp+pperrinfo], 0
0x14000a0df  call    cs:__imp_CreateErrorInfo
0x14000a0e5  mov     ebx, eax
0x14000a0e7  test    eax, eax
0x14000a0e9  js      loc_14000A1E4
0x14000a0ef  mov     rcx, [rbp+pperrinfo]
0x14000a0f3  mov     rdx, r14
0x14000a0f6  mov     rax, [rcx]
0x14000a0f9  mov     rax, [rax+18h]
0x14000a0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a102  mov     ebx, eax
0x14000a104  test    eax, eax
0x14000a106  js      loc_14000A1E4
0x14000a10c  mov     rcx, [rbp+pperrinfo]
0x14000a110  mov     rdx, r15
0x14000a113  mov     rax, [rcx]
0x14000a116  mov     rax, [rax+20h]
0x14000a11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a11f  mov     ebx, eax
0x14000a121  test    eax, eax
0x14000a123  js      loc_14000A1E4
0x14000a129  mov     edx, [rbp+arg_10]; unsigned int
0x14000a12c  lea     rcx, [rbp+lpWideCharStr]; unsigned __int16 **
0x14000a130  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x14000a135  mov     rdi, [rbp+lpWideCharStr]
0x14000a139  test    eax, eax
0x14000a13b  jnz     short loc_14000A147
0x14000a13d  mov     ebx, 8007000Eh
0x14000a142  jmp     loc_14000A1E4
0x14000a147  lea     rax, [rbp+arg_18]
0x14000a14b  mov     rcx, rdi; lpWideCharStr
0x14000a14e  lea     r8, [rbp+var_28]; char **
0x14000a152  mov     [rbp+var_28], rax
0x14000a156  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x14000a15a  call    ?FormatLine@@YAJPEBGPEAPEAGPEAPEAD@Z; FormatLine(ushort const *,ushort * *,char * *)
0x14000a15f  mov     [rbp+var_28], rsi
0x14000a163  mov     ebx, eax
0x14000a165  mov     rsi, [rbp+var_20]
0x14000a169  test    eax, eax
0x14000a16b  js      short loc_14000A1E4
0x14000a16d  mov     rcx, [rbp+pperrinfo]
0x14000a171  mov     rdx, rsi
0x14000a174  mov     rax, [rcx]
0x14000a177  mov     rax, [rax+28h]
0x14000a17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a180  mov     ebx, eax
0x14000a182  test    eax, eax
0x14000a184  js      short loc_14000A1E4
0x14000a186  mov     rcx, [rbp+pperrinfo]
0x14000a18a  xor     edx, edx
0x14000a18c  mov     rax, [rcx]
0x14000a18f  mov     rax, [rax+30h]
0x14000a193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a198  mov     ebx, eax
0x14000a19a  test    eax, eax
0x14000a19c  js      short loc_14000A1E4
0x14000a19e  mov     rcx, [rbp+pperrinfo]
0x14000a1a2  xor     edx, edx
0x14000a1a4  mov     rax, [rcx]
0x14000a1a7  mov     rax, [rax+38h]
0x14000a1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1b0  mov     ebx, eax
0x14000a1b2  test    eax, eax
0x14000a1b4  js      short loc_14000A1E4
0x14000a1b6  mov     rcx, [rbp+pperrinfo]
0x14000a1ba  lea     r8, [rbp+perrinfo]
0x14000a1be  lea     rdx, IID_IErrorInfo
0x14000a1c5  mov     rax, [rcx]
0x14000a1c8  mov     rax, [rax]
0x14000a1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1d0  mov     ebx, eax
0x14000a1d2  test    eax, eax
0x14000a1d4  js      short loc_14000A1E4
0x14000a1d6  mov     rdx, [rbp+perrinfo]; perrinfo
0x14000a1da  xor     ecx, ecx; dwReserved
0x14000a1dc  call    cs:__imp_SetErrorInfo
0x14000a1e2  mov     ebx, eax
0x14000a1e4  mov     rcx, [rbp+pperrinfo]
0x14000a1e8  test    rcx, rcx
0x14000a1eb  jz      short loc_14000A1F9
0x14000a1ed  mov     rax, [rcx]
0x14000a1f0  mov     rax, [rax+10h]
0x14000a1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1f9  mov     rcx, [rbp+perrinfo]
0x14000a1fd  test    rcx, rcx
0x14000a200  jz      short loc_14000A20E
0x14000a202  mov     rax, [rcx]
0x14000a205  mov     rax, [rax+10h]
0x14000a209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a20e  mov     rcx, rdi; bstrString
0x14000a211  call    cs:__imp_SysFreeString
0x14000a217  mov     rcx, rsi; bstrString
0x14000a21a  call    cs:__imp_SysFreeString
0x14000a220  mov     eax, ebx
0x14000a222  add     rsp, 58h
0x14000a226  pop     r15
0x14000a228  pop     r14
0x14000a22a  pop     rdi
0x14000a22b  pop     rsi
0x14000a22c  pop     rbx
0x14000a22d  pop     rbp
0x14000a22e  retn
```

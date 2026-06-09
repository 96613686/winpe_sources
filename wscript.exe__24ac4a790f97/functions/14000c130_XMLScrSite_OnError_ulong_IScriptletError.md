# XMLScrSite::OnError(ulong,IScriptletError *)

- ea: `0x14000c130`
- end: `0x14000c404`
- name: `?OnError@XMLScrSite@@UEAAJKPEAUIScriptletError@@@Z`
- size: `724`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned int, struct IScriptletError *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x140007ac8`
- `0x140009b54`
- `0x14000c130`
- `0x14001755a`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000c3a6`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3b0`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3ba`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3c4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3cd`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3a6`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3b0`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3ba`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3c4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c3cd`

## pseudocode

```c
__int64 __fastcall XMLScrSite::OnError(XMLScrSite *this, char a2, struct IScriptletError *a3)
{
  __int64 v6; // rax
  OLECHAR *v7; // r14
  struct IDispatch *v8; // rdi
  __int64 (__fastcall *v9)(struct IScriptletError *, _BYTE *); // rax
  __int64 result; // rax
  BSTR v11; // rbx
  int v12; // eax
  int v13; // ebx
  BSTR v14; // r9
  int v15; // eax
  __int64 v16; // rcx
  int ScriptDispatch; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-89h]
  unsigned int v20; // [rsp+50h] [rbp-59h] BYREF
  BSTR v21; // [rsp+58h] [rbp-51h] BYREF
  BSTR v22; // [rsp+60h] [rbp-49h] BYREF
  struct IDispatch *v23; // [rsp+68h] [rbp-41h] BYREF
  const wchar_t *v24; // [rsp+70h] [rbp-39h] BYREF
  __int128 v25; // [rsp+78h] [rbp-31h] BYREF
  __int64 v26; // [rsp+88h] [rbp-21h]
  _BYTE v27[8]; // [rsp+90h] [rbp-19h] BYREF
  BSTR v28; // [rsp+98h] [rbp-11h]
  BSTR bstrString; // [rsp+A0h] [rbp-9h]
  BSTR v30; // [rsp+A8h] [rbp-1h]
  DWORD dwMessageId; // [rsp+C8h] [rbp+1Fh]
  int v32; // [rsp+120h] [rbp+77h] BYREF
  unsigned int v33; // [rsp+128h] [rbp+7Fh] BYREF

  memset_0(v27, 0, 0x40u);
  v33 = 0;
  v26 = 0;
  v6 = *(_QWORD *)a3;
  v32 = 0;
  v7 = 0;
  v20 = 0;
  v8 = 0;
  v25 = 0;
  v9 = *(__int64 (__fastcall **)(struct IScriptletError *, _BYTE *))(v6 + 24);
  v24 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  result = v9(a3, v27);
  if ( (int)result < 0 )
    return result;
  _InterlockedExchange((volatile __int32 *)(*((_QWORD *)this + 4) + 40LL), 0);
  if ( dwMessageId == -2147467260 )
    goto LABEL_26;
  if ( dwMessageId != -2147155972 )
  {
    if ( dwMessageId == -2147155971 )
    {
LABEL_17:
      v13 = 0;
      goto LABEL_28;
    }
    if ( dwMessageId != -2147155970 )
    {
      v11 = bstrString;
      if ( !bstrString || !*bstrString )
      {
        v12 = FormatHResult(dwMessageId, &v22);
        v7 = v22;
        v13 = v12;
        if ( v12 < 0 )
          goto LABEL_28;
        v11 = v22;
      }
      if ( (*(int (__fastcall **)(struct IScriptletError *, unsigned int *, int *))(*(_QWORD *)a3 + 32LL))(
             a3,
             &v33,
             &v32) < 0 )
      {
        v33 = 0;
        v32 = -1;
      }
      if ( (*(int (__fastcall **)(struct IScriptletError *, BSTR *))(*(_QWORD *)a3 + 40LL))(a3, &v21) >= 0 )
      {
        v14 = v21;
      }
      else
      {
        v14 = 0;
        v21 = 0;
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, BSTR, BSTR, BSTR, DWORD, int))(**((_QWORD **)this + 4)
                                                                                            + 40LL))(
              *((_QWORD *)this + 4),
              v33,
              (unsigned int)(v32 + 1),
              v28,
              v11,
              v14,
              dwMessageId,
              a2 & 1);
      goto LABEL_16;
    }
LABEL_26:
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 64LL))(*((_QWORD *)this + 4));
    if ( v13 >= 0 )
      v13 = 0;
    goto LABEL_28;
  }
  if ( *((_DWORD *)this + 12) )
    goto LABEL_17;
  v16 = *((_QWORD *)this + 5);
  *((_DWORD *)this + 12) = 1;
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 40LL))(v16);
  if ( v13 < 0 )
    goto LABEL_28;
  ScriptDispatch = CHost::GetScriptDispatch(*((CHost **)this + 4), &v23);
  v8 = v23;
  v13 = ScriptDispatch;
  if ( ScriptDispatch < 0 )
    goto LABEL_28;
  v20 = 0;
  v24 = L"WScript_OnScriptTerminate";
  v18 = ((__int64 (__fastcall *)(struct IDispatch *, GUID *, const wchar_t **, __int64, int, unsigned int *))v23->lpVtbl->GetIDsOfNames)(
          v23,
          &GUID_NULL,
          &v24,
          1,
          1024,
          &v20);
  if ( v18 < 0 )
  {
    v13 = 0;
    if ( v18 != -2147352570 )
      v13 = v18;
    goto LABEL_28;
  }
  v25 = 0;
  v26 = 0;
  LOWORD(v19) = 1;
  v15 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, GUID *, __int64, int, __int128 *, _QWORD, _QWORD, _QWORD))v8->lpVtbl->Invoke)(
          v8,
          v20,
          &GUID_NULL,
          1024,
          v19,
          &v25,
          0,
          0,
          0);
LABEL_16:
  v13 = v15;
  if ( v15 >= 0 )
    goto LABEL_17;
LABEL_28:
  SysFreeString(bstrString);
  SysFreeString(v28);
  SysFreeString(v30);
  SysFreeString(v21);
  SysFreeString(v7);
  if ( v8 )
    ((void (__fastcall *)(struct IDispatch *))v8->lpVtbl->Release)(v8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000c130  mov     [rsp-8+arg_0], rbx
0x14000c135  push    rbp
0x14000c136  push    rsi
0x14000c137  push    rdi
0x14000c138  push    r12
0x14000c13a  push    r13
0x14000c13c  push    r14
0x14000c13e  push    r15
0x14000c140  lea     rbp, [rsp-27h]
0x14000c145  sub     rsp, 0D0h
0x14000c14c  mov     r12d, edx
0x14000c14f  mov     r15, r8
0x14000c152  xor     edx, edx; Val
0x14000c154  mov     rsi, rcx
0x14000c157  lea     rcx, [rbp+57h+var_70]; void *
0x14000c15b  lea     r8d, [rdx+40h]; Size
0x14000c15f  call    memset_0
0x14000c164  xor     r13d, r13d
0x14000c167  lea     rdx, [rbp+57h+var_70]
0x14000c16b  xor     eax, eax
0x14000c16d  mov     [rbp+57h+arg_18], r13d
0x14000c171  mov     [rbp+57h+var_78], rax
0x14000c175  xorps   xmm0, xmm0
0x14000c178  mov     rax, [r15]
0x14000c17b  mov     rcx, r15
0x14000c17e  mov     [rbp+57h+arg_10], r13d
0x14000c182  mov     r14d, r13d
0x14000c185  mov     [rbp+57h+var_B0], r13d
0x14000c189  mov     edi, r13d
0x14000c18c  movups  [rbp+57h+var_88], xmm0
0x14000c190  mov     rax, [rax+18h]
0x14000c194  mov     [rbp+57h+var_90], r13
0x14000c198  mov     [rbp+57h+var_A8], r13
0x14000c19c  mov     [rbp+57h+var_A0], r13
0x14000c1a0  mov     [rbp+57h+var_98], r13
0x14000c1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c1a9  test    eax, eax
0x14000c1ab  js      loc_14000C3E9
0x14000c1b1  mov     rcx, [rsi+20h]
0x14000c1b5  mov     eax, r13d
0x14000c1b8  xchg    eax, [rcx+28h]
0x14000c1bb  mov     ecx, [rbp+57h+dwMessageId]; dwMessageId
0x14000c1be  cmp     ecx, 80004004h
0x14000c1c4  jz      loc_14000C38A
0x14000c1ca  cmp     ecx, 8004FFFCh
0x14000c1d0  jz      loc_14000C2AB
0x14000c1d6  cmp     ecx, 8004FFFDh
0x14000c1dc  jz      loc_14000C2A3
0x14000c1e2  cmp     ecx, 8004FFFEh
0x14000c1e8  jz      loc_14000C38A
0x14000c1ee  mov     rbx, [rbp+57h+bstrString]
0x14000c1f2  test    rbx, rbx
0x14000c1f5  jz      short loc_14000C1FD
0x14000c1f7  cmp     r13w, [rbx]
0x14000c1fb  jnz     short loc_14000C217
0x14000c1fd  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x14000c201  call    ?FormatHResult@@YAJJPEAPEAG@Z; FormatHResult(long,ushort * *)
0x14000c206  mov     r14, [rbp+57h+var_A0]
0x14000c20a  mov     ebx, eax
0x14000c20c  test    eax, eax
0x14000c20e  js      loc_14000C3A2
0x14000c214  mov     rbx, r14
0x14000c217  mov     rax, [r15]
0x14000c21a  lea     r8, [rbp+57h+arg_10]
0x14000c21e  lea     rdx, [rbp+57h+arg_18]
0x14000c222  mov     rcx, r15
0x14000c225  mov     rax, [rax+20h]
0x14000c229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c22e  test    eax, eax
0x14000c230  jns     short loc_14000C23D
0x14000c232  mov     [rbp+57h+arg_18], r13d
0x14000c236  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x14000c23d  mov     rax, [r15]
0x14000c240  lea     rdx, [rbp+57h+var_A8]
0x14000c244  mov     rcx, r15
0x14000c247  mov     rax, [rax+28h]
0x14000c24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c250  test    eax, eax
0x14000c252  jns     short loc_14000C25D
0x14000c254  mov     r9, r13
0x14000c257  mov     [rbp+57h+var_A8], r13
0x14000c25b  jmp     short loc_14000C261
0x14000c25d  mov     r9, [rbp+57h+var_A8]
0x14000c261  mov     edx, [rbp+57h+dwMessageId]
0x14000c264  and     r12d, 1
0x14000c268  mov     rcx, [rsi+20h]
0x14000c26c  mov     r8d, [rbp+57h+arg_10]
0x14000c270  mov     dword ptr [rsp+100h+var_C8], r12d
0x14000c275  inc     r8d
0x14000c278  mov     dword ptr [rsp+100h+var_D0], edx
0x14000c27c  mov     rax, [rcx]
0x14000c27f  mov     edx, [rbp+57h+arg_18]
0x14000c282  mov     [rsp+100h+var_D8], r9
0x14000c287  mov     r9, [rbp+57h+var_68]
0x14000c28b  mov     rax, [rax+28h]
0x14000c28f  mov     [rsp+100h+var_E0], rbx
0x14000c294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c299  mov     ebx, eax
0x14000c29b  test    eax, eax
0x14000c29d  js      loc_14000C3A2
0x14000c2a3  mov     ebx, r13d
0x14000c2a6  jmp     loc_14000C3A2
0x14000c2ab  cmp     [rsi+30h], r13d
0x14000c2af  jnz     short loc_14000C2A3
0x14000c2b1  mov     rcx, [rsi+28h]
0x14000c2b5  mov     r15d, 1
0x14000c2bb  mov     [rsi+30h], r15d
0x14000c2bf  mov     rax, [rcx]
0x14000c2c2  mov     rax, [rax+28h]
0x14000c2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c2cb  mov     ebx, eax
0x14000c2cd  test    eax, eax
0x14000c2cf  js      loc_14000C3A2
0x14000c2d5  mov     rcx, [rsi+20h]; this
0x14000c2d9  lea     rdx, [rbp+57h+var_98]; struct IDispatch **
0x14000c2dd  call    ?GetScriptDispatch@CHost@@QEAAJPEAPEAUIDispatch@@@Z; CHost::GetScriptDispatch(IDispatch * *)
0x14000c2e2  mov     rdi, [rbp+57h+var_98]
0x14000c2e6  mov     ebx, eax
0x14000c2e8  test    eax, eax
0x14000c2ea  js      loc_14000C3A2
0x14000c2f0  lea     rax, aWscriptOnscrip; "WScript_OnScriptTerminate"
0x14000c2f7  mov     [rbp+57h+var_B0], r13d
0x14000c2fb  mov     [rbp+57h+var_90], rax
0x14000c2ff  lea     rcx, [rbp+57h+var_B0]
0x14000c303  mov     rax, [rdi]
0x14000c306  lea     r8, [rbp+57h+var_90]
0x14000c30a  mov     [rsp+100h+var_D8], rcx
0x14000c30f  lea     rdx, GUID_NULL
0x14000c316  mov     ebx, 400h
0x14000c31b  mov     r9d, r15d
0x14000c31e  mov     rcx, rdi
0x14000c321  mov     dword ptr [rsp+100h+var_E0], ebx
0x14000c325  mov     rax, [rax+28h]
0x14000c329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c32e  test    eax, eax
0x14000c330  jns     short loc_14000C33F
0x14000c332  cmp     eax, 80020006h
0x14000c337  mov     ebx, r13d
0x14000c33a  cmovnz  ebx, eax
0x14000c33d  jmp     short loc_14000C3A2
0x14000c33f  mov     edx, [rbp+57h+var_B0]
0x14000c342  lea     rcx, [rbp+57h+var_88]
0x14000c346  mov     [rsp+100h+var_C0], r13
0x14000c34b  lea     r8, GUID_NULL
0x14000c352  mov     [rsp+100h+var_C8], r13
0x14000c357  xorps   xmm0, xmm0
0x14000c35a  movdqu  [rbp+57h+var_88], xmm0
0x14000c35f  mov     [rbp+57h+var_78], r13
0x14000c363  mov     r9d, ebx
0x14000c366  mov     rax, [rdi]
0x14000c369  mov     [rsp+100h+var_D0], r13
0x14000c36e  mov     [rsp+100h+var_D8], rcx
0x14000c373  mov     rcx, rdi
0x14000c376  mov     word ptr [rsp+100h+var_E0], r15w
0x14000c37c  mov     rax, [rax+30h]
0x14000c380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c385  jmp     loc_14000C299
0x14000c38a  mov     rcx, [rsi+20h]
0x14000c38e  mov     rax, [rcx]
0x14000c391  mov     rax, [rax+40h]
0x14000c395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c39a  test    eax, eax
0x14000c39c  mov     ebx, eax
0x14000c39e  cmovns  ebx, r13d
0x14000c3a2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14000c3a6  call    cs:__imp_SysFreeString
0x14000c3ac  mov     rcx, [rbp+57h+var_68]; bstrString
0x14000c3b0  call    cs:__imp_SysFreeString
0x14000c3b6  mov     rcx, [rbp+57h+var_58]; bstrString
0x14000c3ba  call    cs:__imp_SysFreeString
0x14000c3c0  mov     rcx, [rbp+57h+var_A8]; bstrString
0x14000c3c4  call    cs:__imp_SysFreeString
0x14000c3ca  mov     rcx, r14; bstrString
0x14000c3cd  call    cs:__imp_SysFreeString
0x14000c3d3  test    rdi, rdi
0x14000c3d6  jz      short loc_14000C3E7
0x14000c3d8  mov     rax, [rdi]
0x14000c3db  mov     rcx, rdi
0x14000c3de  mov     rax, [rax+10h]
0x14000c3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c3e7  mov     eax, ebx
0x14000c3e9  mov     rbx, [rsp+100h+arg_0]
0x14000c3f1  add     rsp, 0D0h
0x14000c3f8  pop     r15
0x14000c3fa  pop     r14
0x14000c3fc  pop     r13
0x14000c3fe  pop     r12
0x14000c400  pop     rdi
0x14000c401  pop     rsi
0x14000c402  pop     rbp
0x14000c403  retn
```

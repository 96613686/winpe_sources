# UWFUpdateAgent::MatchKBNumber(IUpdate *)

- ea: `0x180004008`
- end: `0x180004223`
- name: `?MatchKBNumber@UWFUpdateAgent@@AEAAHPEAUIUpdate@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(UWFUpdateAgent *__hidden this, struct IUpdate *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000490c`

## callees

- `0x180001536`
- `0x180002570`
- `0x180002db0`
- `0x180004008`
- `0x180006010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800041c6`
- `msvcrt!_wcsicmp` at `0x1800041c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004074`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004126`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004074`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004126`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041e3`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::MatchKBNumber(UWFUpdateAgent *this, struct IUpdate *a2)
{
  LSTATUS MultiString; // eax
  DWORD v4; // ecx
  unsigned __int64 v6; // rdi
  size_t v7; // rax
  void *v8; // rsi
  size_t v9; // rax
  const unsigned __int16 *v10; // rdx
  HKEY v11; // rcx
  unsigned __int16 **v12; // r14
  LSTATUS v13; // eax
  struct IUpdateVtbl *lpVtbl; // rax
  unsigned int v15; // r15d
  unsigned int i; // edi
  int v17; // ebx
  UWFUpdateAgent *v18; // [rsp+80h] [rbp+38h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp+40h] BYREF
  int v20; // [rsp+90h] [rbp+48h] BYREF
  __int64 v21; // [rsp+98h] [rbp+50h] BYREF

  v18 = this;
  if ( !a2 )
    return 0;
  LODWORD(v18) = 0;
  LODWORD(String1) = 0;
  MultiString = UwfServicingRegGetMultiString(
                  (HKEY)this,
                  (const unsigned __int16 *)a2,
                  L"KBNumber",
                  0,
                  (int *)&String1,
                  0,
                  (int *)&v18);
  if ( MultiString < 0 )
  {
    if ( (MultiString & 0x1FFF0000) == 0x70000 )
      MultiString = (unsigned __int16)MultiString;
    v4 = MultiString;
    goto LABEL_6;
  }
  if ( !(_DWORD)String1 )
    return 0;
  v6 = (int)v18;
  if ( !(_DWORD)v18 )
    return 0;
  v7 = 2LL * (int)String1;
  if ( !is_mul_ok((int)String1, 2u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
  {
LABEL_13:
    v4 = 14;
LABEL_6:
    SetLastError(v4);
    return 0;
  }
  v9 = 8 * v6;
  if ( !is_mul_ok(v6, 8u) )
    v9 = -1;
  v12 = (unsigned __int16 **)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v12 )
  {
    operator delete(v8);
    goto LABEL_13;
  }
  v13 = UwfServicingRegGetMultiString(v11, v10, L"KBNumber", (unsigned __int16 *)v8, (int *)&String1, v12, (int *)&v18);
  if ( v13 < 0 )
  {
    SetLastError(v13);
    operator delete(v8);
    operator delete(v12);
    return 0;
  }
  lpVtbl = a2->lpVtbl;
  v15 = 0;
  v21 = 0;
  if ( ((int (__fastcall *)(struct IUpdate *, __int64 *))lpVtbl->get_KBArticleIDs)(a2, &v21) < 0 )
    goto LABEL_32;
  if ( v21 )
  {
    v20 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 80LL))(v21, &v20) >= 0 )
    {
      for ( i = 0; (int)i < v20; ++i )
      {
        String1 = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v21 + 56LL))(v21, i, &String1) < 0 )
          break;
        v17 = 0;
        if ( (int)v18 > 0 )
        {
          while ( _wcsicmp(String1, v12[v17]) )
          {
            if ( ++v17 >= (int)v18 )
              goto LABEL_30;
          }
          v15 = 1;
        }
LABEL_30:
        SysFreeString(String1);
        if ( v15 == 1 )
          break;
      }
    }
LABEL_32:
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  operator delete(v8);
  operator delete(v12);
  return v15;
}

```

## disassembly

```asm
0x180004008  mov     r11, rsp
0x18000400b  mov     [r11+8], rcx
0x18000400f  push    rbp
0x180004010  push    rbx
0x180004011  push    rsi
0x180004012  push    rdi
0x180004013  push    r14
0x180004015  push    r15
0x180004017  mov     rbp, rsp
0x18000401a  sub     rsp, 48h
0x18000401e  mov     rbx, rdx
0x180004021  test    rdx, rdx
0x180004024  jz      short loc_18000407A
0x180004026  lea     rax, [rbp+arg_0]
0x18000402a  mov     dword ptr [rbp+arg_0], 0
0x180004031  mov     [r11-48h], rax
0x180004035  lea     r8, aKbnumber; "KBNumber"
0x18000403c  lea     rax, [rbp+String1]
0x180004040  mov     qword ptr [r11-50h], 0
0x180004048  xor     r9d, r9d; unsigned __int16 *
0x18000404b  mov     [r11-58h], rax
0x18000404f  mov     dword ptr [rbp+String1], 0
0x180004056  call    ?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z; UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)
0x18000405b  test    eax, eax
0x18000405d  jns     short loc_180004089
0x18000405f  mov     ecx, eax
0x180004061  and     ecx, 1FFF0000h
0x180004067  cmp     ecx, 70000h
0x18000406d  jnz     short loc_180004072
0x18000406f  movzx   eax, ax
0x180004072  mov     ecx, eax; dwErrCode
0x180004074  call    cs:__imp_SetLastError
0x18000407a  xor     eax, eax
0x18000407c  add     rsp, 48h
0x180004080  pop     r15
0x180004082  pop     r14
0x180004084  pop     rdi
0x180004085  pop     rsi
0x180004086  pop     rbx
0x180004087  pop     rbp
0x180004088  retn
0x180004089  movsxd  rax, dword ptr [rbp+String1]
0x18000408d  test    eax, eax
0x18000408f  jz      short loc_18000407A
0x180004091  movsxd  rdi, dword ptr [rbp+arg_0]
0x180004095  test    edi, edi
0x180004097  jz      short loc_18000407A
0x180004099  mov     rcx, rax
0x18000409c  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800040a3  mov     eax, 2
0x1800040a8  mul     rcx
0x1800040ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800040b2  cmovb   rax, r14
0x1800040b6  mov     rcx, rax; unsigned __int64
0x1800040b9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800040be  mov     rsi, rax
0x1800040c1  test    rax, rax
0x1800040c4  jnz     short loc_1800040CD
0x1800040c6  mov     ecx, 0Eh
0x1800040cb  jmp     short loc_180004074
0x1800040cd  mov     eax, 8
0x1800040d2  mul     rdi
0x1800040d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800040dc  cmovb   rax, r14
0x1800040e0  mov     rcx, rax; unsigned __int64
0x1800040e3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800040e8  mov     r14, rax
0x1800040eb  test    rax, rax
0x1800040ee  jnz     short loc_1800040FA
0x1800040f0  mov     rcx, rsi; void *
0x1800040f3  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800040f8  jmp     short loc_1800040C6
0x1800040fa  lea     rax, [rbp+arg_0]
0x1800040fe  mov     r9, rsi; unsigned __int16 *
0x180004101  mov     [rsp+48h+var_18], rax; int *
0x180004106  lea     r8, aKbnumber; "KBNumber"
0x18000410d  lea     rax, [rbp+String1]
0x180004111  mov     [rsp+48h+var_20], r14; unsigned __int16 **
0x180004116  mov     [rsp+48h+var_28], rax; int *
0x18000411b  call    ?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z; UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)
0x180004120  test    eax, eax
0x180004122  jns     short loc_180004141
0x180004124  mov     ecx, eax; dwErrCode
0x180004126  call    cs:__imp_SetLastError
0x18000412c  mov     rcx, rsi; void *
0x18000412f  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180004134  mov     rcx, r14; void *
0x180004137  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x18000413c  jmp     loc_18000407A
0x180004141  mov     rax, [rbx]
0x180004144  lea     rdx, [rbp+arg_18]
0x180004148  xor     r15d, r15d
0x18000414b  mov     rcx, rbx
0x18000414e  mov     [rbp+arg_18], r15
0x180004152  mov     rax, [rax+170h]
0x180004159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000415e  test    eax, eax
0x180004160  js      loc_1800041F6
0x180004166  mov     rcx, [rbp+arg_18]
0x18000416a  test    rcx, rcx
0x18000416d  jz      loc_18000420B
0x180004173  mov     [rbp+arg_10], r15d
0x180004177  lea     rdx, [rbp+arg_10]
0x18000417b  mov     rax, [rcx]
0x18000417e  mov     rax, [rax+50h]
0x180004182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004187  test    eax, eax
0x180004189  js      short loc_1800041F6
0x18000418b  xor     edi, edi
0x18000418d  cmp     [rbp+arg_10], edi
0x180004190  jle     short loc_1800041F6
0x180004192  mov     rcx, [rbp+arg_18]
0x180004196  lea     r8, [rbp+String1]
0x18000419a  mov     [rbp+String1], 0
0x1800041a2  mov     edx, edi
0x1800041a4  mov     rax, [rcx]
0x1800041a7  mov     rax, [rax+38h]
0x1800041ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b0  test    eax, eax
0x1800041b2  js      short loc_1800041F6
0x1800041b4  xor     ebx, ebx
0x1800041b6  cmp     dword ptr [rbp+arg_0], ebx
0x1800041b9  jle     short loc_1800041DF
0x1800041bb  mov     rcx, [rbp+String1]; String1
0x1800041bf  movsxd  rdx, ebx
0x1800041c2  mov     rdx, [r14+rdx*8]; String2
0x1800041c6  call    cs:__imp__wcsicmp
0x1800041cc  test    eax, eax
0x1800041ce  jz      short loc_1800041D9
0x1800041d0  inc     ebx
0x1800041d2  cmp     ebx, dword ptr [rbp+arg_0]
0x1800041d5  jl      short loc_1800041BB
0x1800041d7  jmp     short loc_1800041DF
0x1800041d9  mov     r15d, 1
0x1800041df  mov     rcx, [rbp+String1]; bstrString
0x1800041e3  call    cs:__imp_SysFreeString
0x1800041e9  cmp     r15d, 1
0x1800041ed  jz      short loc_1800041F6
0x1800041ef  inc     edi
0x1800041f1  cmp     edi, [rbp+arg_10]
0x1800041f4  jl      short loc_180004192
0x1800041f6  mov     rcx, [rbp+arg_18]
0x1800041fa  test    rcx, rcx
0x1800041fd  jz      short loc_18000420B
0x1800041ff  mov     rdx, [rcx]
0x180004202  mov     rax, [rdx+10h]
0x180004206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420b  mov     rcx, rsi; void *
0x18000420e  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180004213  mov     rcx, r14; void *
0x180004216  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x18000421b  mov     eax, r15d
0x18000421e  jmp     loc_18000407C
```

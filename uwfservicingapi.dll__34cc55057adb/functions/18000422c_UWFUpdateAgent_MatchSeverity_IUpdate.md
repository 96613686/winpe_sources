# UWFUpdateAgent::MatchSeverity(IUpdate *)

- ea: `0x18000422c`
- end: `0x1800043eb`
- name: `?MatchSeverity@UWFUpdateAgent@@AEAAHPEAUIUpdate@@@Z`
- size: `447`
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
- `0x18000422c`
- `0x180006010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800043b0`
- `msvcrt!_wcsicmp` at `0x1800043b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000429b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004354`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000429b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004354`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800043cd`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::MatchSeverity(UWFUpdateAgent *this, struct IUpdate *a2)
{
  LSTATUS MultiString; // eax
  DWORD v4; // ecx
  unsigned __int64 v6; // rsi
  size_t v7; // rax
  void *v8; // rdi
  size_t v9; // rax
  const unsigned __int16 *v10; // rdx
  HKEY v11; // rcx
  unsigned __int16 **v12; // rsi
  LSTATUS v13; // eax
  struct IUpdateVtbl *lpVtbl; // rax
  unsigned int v15; // r15d
  int v16; // r14d
  int v17; // ebx
  UWFUpdateAgent *v18; // [rsp+70h] [rbp+30h] BYREF
  int v19; // [rsp+78h] [rbp+38h] BYREF
  wchar_t *String1; // [rsp+80h] [rbp+40h] BYREF

  v18 = this;
  if ( !a2 )
    return 0;
  LODWORD(v18) = 0;
  v19 = 0;
  MultiString = UwfServicingRegGetMultiString(
                  (HKEY)this,
                  (const unsigned __int16 *)a2,
                  L"Severity",
                  0,
                  &v19,
                  0,
                  (int *)&v18);
  if ( MultiString < 0 )
  {
    if ( (MultiString & 0x1FFF0000) == 0x70000 )
      MultiString = (unsigned __int16)MultiString;
    v4 = MultiString;
    goto LABEL_6;
  }
  if ( !v19 )
    return 0;
  v6 = (int)v18;
  if ( !(_DWORD)v18 )
    return 0;
  v7 = 2LL * v19;
  if ( !is_mul_ok(v19, 2u) )
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
  v13 = UwfServicingRegGetMultiString(v11, v10, L"Severity", (unsigned __int16 *)v8, &v19, v12, (int *)&v18);
  if ( v13 < 0 )
  {
    SetLastError(v13);
    operator delete(v8);
    operator delete(v12);
    return 0;
  }
  lpVtbl = a2->lpVtbl;
  String1 = 0;
  v15 = 0;
  if ( ((int (__fastcall *)(struct IUpdate *, wchar_t **))lpVtbl->get_MsrcSeverity)(a2, &String1) >= 0 )
  {
    if ( String1 )
    {
      v16 = (int)v18;
      v17 = 0;
      if ( (int)v18 > 0 )
      {
        while ( _wcsicmp(String1, v12[v17]) )
        {
          if ( ++v17 >= v16 )
            goto LABEL_27;
        }
        v15 = 1;
      }
    }
  }
LABEL_27:
  SysFreeString(String1);
  operator delete(v8);
  operator delete(v12);
  return v15;
}

```

## disassembly

```asm
0x18000422c  mov     r11, rsp
0x18000422f  mov     [r11+20h], rbx
0x180004233  mov     [r11+8], rcx
0x180004237  push    rbp
0x180004238  push    rsi
0x180004239  push    rdi
0x18000423a  push    r14
0x18000423c  push    r15
0x18000423e  mov     rbp, rsp
0x180004241  sub     rsp, 40h
0x180004245  mov     rbx, rdx
0x180004248  test    rdx, rdx
0x18000424b  jz      short loc_1800042A1
0x18000424d  lea     rax, [rbp+arg_0]
0x180004251  mov     dword ptr [rbp+arg_0], 0
0x180004258  mov     [r11-38h], rax
0x18000425c  lea     r8, aSeverity; "Severity"
0x180004263  lea     rax, [rbp+arg_8]
0x180004267  mov     qword ptr [r11-40h], 0
0x18000426f  xor     r9d, r9d; unsigned __int16 *
0x180004272  mov     [r11-48h], rax
0x180004276  mov     [rbp+arg_8], 0
0x18000427d  call    ?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z; UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)
0x180004282  test    eax, eax
0x180004284  jns     short loc_1800042B7
0x180004286  mov     ecx, eax
0x180004288  and     ecx, 1FFF0000h
0x18000428e  cmp     ecx, 70000h
0x180004294  jnz     short loc_180004299
0x180004296  movzx   eax, ax
0x180004299  mov     ecx, eax; dwErrCode
0x18000429b  call    cs:__imp_SetLastError
0x1800042a1  xor     eax, eax
0x1800042a3  mov     rbx, [rsp+40h+arg_18]
0x1800042ab  add     rsp, 40h
0x1800042af  pop     r15
0x1800042b1  pop     r14
0x1800042b3  pop     rdi
0x1800042b4  pop     rsi
0x1800042b5  pop     rbp
0x1800042b6  retn
0x1800042b7  movsxd  rax, [rbp+arg_8]
0x1800042bb  test    eax, eax
0x1800042bd  jz      short loc_1800042A1
0x1800042bf  movsxd  rsi, dword ptr [rbp+arg_0]
0x1800042c3  test    esi, esi
0x1800042c5  jz      short loc_1800042A1
0x1800042c7  mov     rcx, rax
0x1800042ca  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800042d1  mov     eax, 2
0x1800042d6  mul     rcx
0x1800042d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800042e0  cmovb   rax, r14
0x1800042e4  mov     rcx, rax; unsigned __int64
0x1800042e7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800042ec  mov     rdi, rax
0x1800042ef  test    rax, rax
0x1800042f2  jnz     short loc_1800042FB
0x1800042f4  mov     ecx, 0Eh
0x1800042f9  jmp     short loc_18000429B
0x1800042fb  mov     eax, 8
0x180004300  mul     rsi
0x180004303  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000430a  cmovb   rax, r14
0x18000430e  mov     rcx, rax; unsigned __int64
0x180004311  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004316  mov     rsi, rax
0x180004319  test    rax, rax
0x18000431c  jnz     short loc_180004328
0x18000431e  mov     rcx, rdi; void *
0x180004321  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180004326  jmp     short loc_1800042F4
0x180004328  lea     rax, [rbp+arg_0]
0x18000432c  mov     r9, rdi; unsigned __int16 *
0x18000432f  mov     [rsp+40h+var_10], rax; int *
0x180004334  lea     r8, aSeverity; "Severity"
0x18000433b  lea     rax, [rbp+arg_8]
0x18000433f  mov     [rsp+40h+var_18], rsi; unsigned __int16 **
0x180004344  mov     [rsp+40h+var_20], rax; int *
0x180004349  call    ?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z; UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)
0x18000434e  test    eax, eax
0x180004350  jns     short loc_18000436F
0x180004352  mov     ecx, eax; dwErrCode
0x180004354  call    cs:__imp_SetLastError
0x18000435a  mov     rcx, rdi; void *
0x18000435d  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180004362  mov     rcx, rsi; void *
0x180004365  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x18000436a  jmp     loc_1800042A1
0x18000436f  mov     rax, [rbx]
0x180004372  lea     rdx, [rbp+String1]
0x180004376  mov     rcx, rbx
0x180004379  mov     [rbp+String1], 0
0x180004381  xor     r15d, r15d
0x180004384  mov     rax, [rax+110h]
0x18000438b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004390  test    eax, eax
0x180004392  js      short loc_1800043C9
0x180004394  cmp     [rbp+String1], r15
0x180004398  jz      short loc_1800043C9
0x18000439a  mov     r14d, dword ptr [rbp+arg_0]
0x18000439e  xor     ebx, ebx
0x1800043a0  test    r14d, r14d
0x1800043a3  jle     short loc_1800043C9
0x1800043a5  mov     rcx, [rbp+String1]; String1
0x1800043a9  movsxd  rdx, ebx
0x1800043ac  mov     rdx, [rsi+rdx*8]; String2
0x1800043b0  call    cs:__imp__wcsicmp
0x1800043b6  test    eax, eax
0x1800043b8  jz      short loc_1800043C3
0x1800043ba  inc     ebx
0x1800043bc  cmp     ebx, r14d
0x1800043bf  jl      short loc_1800043A5
0x1800043c1  jmp     short loc_1800043C9
0x1800043c3  mov     r15d, 1
0x1800043c9  mov     rcx, [rbp+String1]; bstrString
0x1800043cd  call    cs:__imp_SysFreeString
0x1800043d3  mov     rcx, rdi; void *
0x1800043d6  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800043db  mov     rcx, rsi; void *
0x1800043de  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800043e3  mov     eax, r15d
0x1800043e6  jmp     loc_1800042A3
```

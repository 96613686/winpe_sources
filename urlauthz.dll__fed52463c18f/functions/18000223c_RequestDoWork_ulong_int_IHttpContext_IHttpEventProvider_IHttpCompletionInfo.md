# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x18000223c`
- end: `0x180002535`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `761`
- prototype: `__int64(__int64, int, struct IHttpContext *, ...)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001a00`
- `0x180001a60`

## callees

- `0x180001008`
- `0x18000223c`
- `0x180002768`
- `0x180003158`
- `0x180004010`

## pseudocode

```c
__int64 RequestDoWork(__int64 a1, int a2, struct IHttpContext *a3, ...)
{
  __int64 v3; // rax
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rbx
  _DWORD *v8; // rax
  int v9; // edi
  int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // [rsp+78h] [rbp+38h] BYREF
  struct INativeSectionException *v20; // [rsp+80h] [rbp+40h] BYREF
  __int64 v21; // [rsp+88h] [rbp+48h] BYREF
  va_list va; // [rsp+88h] [rbp+48h]
  va_list va1; // [rsp+90h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v21 = va_arg(va1, _QWORD);
  v19 = a2;
  v3 = *(_QWORD *)a3;
  v20 = 0;
  v21 = 0;
  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160))(a3);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v7 = (**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, g_UrlAuthzModuleId);
  if ( !v7 )
  {
    v8 = operator new(0x28u);
    v7 = (__int64)v8;
    if ( !v8 )
    {
      v9 = -2147024888;
      goto LABEL_19;
    }
    v8[8] = 0;
    *(_QWORD *)v8 = &URL_AUTHZ_META_STORED_CONTEXT::`vftable';
    v8[6] = 0;
    *((_QWORD *)v8 + 2) = v8 + 2;
    *((_QWORD *)v8 + 1) = v8 + 2;
    v9 = URL_AUTHZ_META_STORED_CONTEXT::Initialize((URL_AUTHZ_META_STORED_CONTEXT *)v8, a3, &v20);
    if ( v9 < 0 )
    {
      (**(void (__fastcall ***)(__int64))v7)(v7);
LABEL_19:
      if ( v20 )
        (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v20)(
          v20,
          &IID_IAppHostConfigException,
          (__int64 *)va);
      v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17) + 536) = 0;
      v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v18 + 24LL))(
        v18,
        500,
        "Internal Server Error",
        19,
        v9,
        v21,
        0);
      if ( v21 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        v21 = 0;
      }
      if ( v20 )
        (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v20 + 16LL))(v20);
      return 2;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v6 + 8LL))(v6, v7, g_UrlAuthzModuleId);
    if ( v9 < 0 )
    {
      (**(void (__fastcall ***)(__int64))v7)(v7);
      if ( v9 == -2147024811 )
      {
        v7 = (**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, g_UrlAuthzModuleId);
        v9 = 0;
      }
      else
      {
        v7 = 0;
      }
    }
    if ( v9 < 0 )
      goto LABEL_19;
  }
  if ( *(_DWORD *)(v7 + 32) )
  {
    v13 = 1;
  }
  else
  {
    v10 = URL_AUTHZ_RULE_LIST::DoAuthorizationCheck((URL_AUTHZ_RULE_LIST *)(v7 + 8), a3, &v19);
    if ( v10 < 0 )
    {
      v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) + 536) = 0;
      v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v12 + 24LL))(
        v12,
        401,
        "Unauthorized",
        2,
        v10,
        0,
        0);
      return 2;
    }
    v13 = v19;
  }
  if ( v13 )
    return 0;
  v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) + 536) = 0;
  v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v15 + 24LL))(
    v15,
    401,
    "Unauthorized",
    2,
    -2147024891,
    0,
    0);
  return 2;
}

```

## disassembly

```asm
0x18000223c  mov     [rsp-28h+arg_0], rbx
0x180002241  mov     [rsp-28h+arg_18], r9
0x180002246  mov     [rsp-28h+arg_8], edx
0x18000224a  push    rbp
0x18000224b  push    rsi
0x18000224c  push    rdi
0x18000224d  push    r14
0x18000224f  push    r15
0x180002251  mov     rbp, rsp
0x180002254  sub     rsp, 40h
0x180002258  mov     rax, [r8]
0x18000225b  xor     r15d, r15d
0x18000225e  mov     rcx, r8
0x180002261  mov     [rbp+arg_10], r15
0x180002265  mov     r14, r8
0x180002268  mov     [rbp+arg_18], r15
0x18000226c  mov     [rbp+arg_8], r15d
0x180002270  mov     rax, [rax+0A0h]
0x180002277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000227c  mov     rdx, rax
0x18000227f  mov     rcx, [rax]
0x180002282  mov     rax, [rcx+18h]
0x180002286  mov     rcx, rdx
0x180002289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228e  mov     rdx, cs:?g_UrlAuthzModuleId@@3PEAXEA; void * g_UrlAuthzModuleId
0x180002295  mov     rsi, rax
0x180002298  mov     rcx, [rax]
0x18000229b  mov     rax, [rcx]
0x18000229e  mov     rcx, rsi
0x1800022a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a6  mov     rbx, rax
0x1800022a9  test    rax, rax
0x1800022ac  jnz     loc_18000236C
0x1800022b2  lea     ecx, [rax+28h]; Size
0x1800022b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800022ba  mov     rbx, rax
0x1800022bd  test    rax, rax
0x1800022c0  jz      loc_18000245F
0x1800022c6  lea     rax, ??_7URL_AUTHZ_META_STORED_CONTEXT@@6B@; const URL_AUTHZ_META_STORED_CONTEXT::`vftable'
0x1800022cd  mov     [rbx+20h], r15d
0x1800022d1  mov     [rbx], rax
0x1800022d4  lea     r8, [rbp+arg_10]; struct INativeSectionException **
0x1800022d8  lea     rax, [rbx+8]
0x1800022dc  mov     rdx, r14; struct IHttpContext *
0x1800022df  mov     rcx, rbx; this
0x1800022e2  mov     [rax+10h], r15d
0x1800022e6  mov     [rax+8], rax
0x1800022ea  mov     [rax], rax
0x1800022ed  call    ?Initialize@URL_AUTHZ_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; URL_AUTHZ_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)
0x1800022f2  mov     edi, eax
0x1800022f4  test    eax, eax
0x1800022f6  jns     short loc_18000230B
0x1800022f8  mov     rcx, [rbx]
0x1800022fb  mov     rax, [rcx]
0x1800022fe  mov     rcx, rbx
0x180002301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002306  jmp     loc_180002464
0x18000230b  mov     rax, [rsi]
0x18000230e  mov     rdx, rbx
0x180002311  mov     r8, cs:?g_UrlAuthzModuleId@@3PEAXEA; void * g_UrlAuthzModuleId
0x180002318  mov     rcx, rsi
0x18000231b  mov     rax, [rax+8]
0x18000231f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002324  mov     edi, eax
0x180002326  test    eax, eax
0x180002328  jns     short loc_180002360
0x18000232a  mov     rax, [rbx]
0x18000232d  mov     rcx, rbx
0x180002330  mov     rax, [rax]
0x180002333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002338  cmp     edi, 80070055h
0x18000233e  jnz     short loc_18000235D
0x180002340  mov     rax, [rsi]
0x180002343  mov     rcx, rsi
0x180002346  mov     rdx, cs:?g_UrlAuthzModuleId@@3PEAXEA; void * g_UrlAuthzModuleId
0x18000234d  mov     rax, [rax]
0x180002350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002355  mov     rbx, rax
0x180002358  mov     edi, r15d
0x18000235b  jmp     short loc_180002360
0x18000235d  mov     rbx, r15
0x180002360  test    edi, edi
0x180002362  cmovs   rbx, r15
0x180002366  js      loc_180002464
0x18000236c  cmp     [rbx+20h], r15d
0x180002370  jnz     loc_180002400
0x180002376  lea     rcx, [rbx+8]; this
0x18000237a  mov     rdx, r14; struct IHttpContext *
0x18000237d  lea     r8, [rbp+arg_8]; int *
0x180002381  call    ?DoAuthorizationCheck@URL_AUTHZ_RULE_LIST@@QEAAJPEAVIHttpContext@@PEAH@Z; URL_AUTHZ_RULE_LIST::DoAuthorizationCheck(IHttpContext *,int *)
0x180002386  mov     ebx, eax
0x180002388  test    eax, eax
0x18000238a  jns     short loc_1800023FB
0x18000238c  mov     rcx, [r14]
0x18000238f  mov     rax, [rcx+20h]
0x180002393  mov     rcx, r14
0x180002396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000239b  mov     rdx, rax
0x18000239e  mov     rcx, [rax]
0x1800023a1  mov     rax, [rcx+8]
0x1800023a5  mov     rcx, rdx
0x1800023a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ad  mov     rcx, r14
0x1800023b0  mov     [rax+218h], r15w
0x1800023b8  mov     rax, [r14]
0x1800023bb  mov     rax, [rax+20h]
0x1800023bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c4  mov     [rsp+40h+var_10], r15d
0x1800023c9  mov     [rsp+40h+var_18], r15
0x1800023ce  mov     [rsp+40h+var_20], ebx
0x1800023d2  mov     rcx, [rax]
0x1800023d5  lea     r8, aUnauthorized; "Unauthorized"
0x1800023dc  mov     r10, rax
0x1800023df  mov     r9d, 2
0x1800023e5  mov     edx, 191h
0x1800023ea  mov     rax, [rcx+18h]
0x1800023ee  mov     rcx, r10
0x1800023f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f6  jmp     loc_18000251F
0x1800023fb  mov     eax, [rbp+arg_8]
0x1800023fe  jmp     short loc_180002405
0x180002400  mov     eax, 1
0x180002405  test    eax, eax
0x180002407  jnz     short loc_180002458
0x180002409  mov     rax, [r14]
0x18000240c  mov     rcx, r14
0x18000240f  mov     rax, [rax+20h]
0x180002413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002418  mov     rdx, rax
0x18000241b  mov     rcx, [rax]
0x18000241e  mov     rax, [rcx+8]
0x180002422  mov     rcx, rdx
0x180002425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000242a  mov     rcx, r14
0x18000242d  mov     [rax+218h], r15w
0x180002435  mov     rax, [r14]
0x180002438  mov     rax, [rax+20h]
0x18000243c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002441  mov     [rsp+40h+var_10], r15d
0x180002446  mov     [rsp+40h+var_18], r15
0x18000244b  mov     [rsp+40h+var_20], 80070005h
0x180002453  jmp     loc_1800023D2
0x180002458  xor     eax, eax
0x18000245a  jmp     loc_180002524
0x18000245f  mov     edi, 80070008h
0x180002464  mov     rcx, [rbp+arg_10]
0x180002468  test    rcx, rcx
0x18000246b  jz      short loc_180002483
0x18000246d  mov     rax, [rcx]
0x180002470  lea     r8, [rbp+arg_18]
0x180002474  lea     rdx, IID_IAppHostConfigException
0x18000247b  mov     rax, [rax]
0x18000247e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002483  mov     rax, [r14]
0x180002486  mov     rcx, r14
0x180002489  mov     rax, [rax+20h]
0x18000248d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002492  mov     rdx, rax
0x180002495  mov     rcx, [rax]
0x180002498  mov     rax, [rcx+8]
0x18000249c  mov     rcx, rdx
0x18000249f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a4  mov     rcx, r14
0x1800024a7  mov     [rax+218h], r15w
0x1800024af  mov     rax, [r14]
0x1800024b2  mov     rax, [rax+20h]
0x1800024b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024bb  mov     r10, rax
0x1800024be  mov     [rsp+40h+var_10], r15d
0x1800024c3  mov     edx, 1F4h
0x1800024c8  lea     r8, aInternalServer; "Internal Server Error"
0x1800024cf  mov     r9d, 13h
0x1800024d5  mov     rcx, [rax]
0x1800024d8  mov     rax, [rcx+18h]
0x1800024dc  mov     rcx, [rbp+arg_18]
0x1800024e0  mov     [rsp+40h+var_18], rcx
0x1800024e5  mov     rcx, r10
0x1800024e8  mov     [rsp+40h+var_20], edi
0x1800024ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f1  mov     rcx, [rbp+arg_18]
0x1800024f5  test    rcx, rcx
0x1800024f8  jz      short loc_18000250A
0x1800024fa  mov     rax, [rcx]
0x1800024fd  mov     rax, [rax+10h]
0x180002501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002506  mov     [rbp+arg_18], r15
0x18000250a  mov     rcx, [rbp+arg_10]
0x18000250e  test    rcx, rcx
0x180002511  jz      short loc_18000251F
0x180002513  mov     rax, [rcx]
0x180002516  mov     rax, [rax+10h]
0x18000251a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000251f  mov     eax, 2
0x180002524  mov     rbx, [rsp+40h+arg_0]
0x180002529  add     rsp, 40h
0x18000252d  pop     r15
0x18000252f  pop     r14
0x180002531  pop     rdi
0x180002532  pop     rsi
0x180002533  pop     rbp
0x180002534  retn
```

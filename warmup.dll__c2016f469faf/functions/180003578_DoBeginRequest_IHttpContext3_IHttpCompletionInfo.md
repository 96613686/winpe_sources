# DoBeginRequest(IHttpContext3 *,IHttpCompletionInfo *)

- ea: `0x180003578`
- end: `0x18000372a`
- name: `?DoBeginRequest@@YA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext3@@PEAVIHttpCompletionInfo@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000268c`

## callees

- `0x180002cb0`
- `0x180003578`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall DoBeginRequest(__int64 *a1, __int64 a2)
{
  int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v10; // rax
  int Extended; // edi
  __int64 (__fastcall ***v12)(_QWORD, void *); // rax
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rax
  int v16; // [rsp+60h] [rbp+8h] BYREF
  _BYTE *v17; // [rsp+68h] [rbp+10h] BYREF
  __int64 v18; // [rsp+70h] [rbp+18h] BYREF

  v18 = 0;
  v17 = 0;
  v4 = 0;
  v16 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 192))(a1);
  v7 = v5;
  if ( v5 )
    LOBYTE(v4) = *(_WORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, 0) != 0;
  v8 = *a1;
  if ( a2 )
  {
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(v8 + 200))(a1, v6, v7);
    return 2;
  }
  if ( (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(v8 + 232))(a1, v6, v7) || !v4 )
    return 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 8))(a1);
  Extended = HttpGetExtendedInterface<IHttpApplication,IHttpApplication2>(g_pServer, v10, &v18);
  if ( Extended < 0 )
  {
LABEL_14:
    v15 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 32))(a1);
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v15 + 24LL))(
      v15,
      500,
      "Server Error",
      0,
      Extended,
      0,
      0);
    return 2;
  }
  if ( (*(int (__fastcall **)(__int64 *, const char *, _BYTE **, int *))(*a1 + 120))(a1, "APP_WARMING_UP", &v17, &v16) < 0
    || *v17 != 49
    || v17[1] )
  {
    return 0;
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18);
  v13 = (**v12)(v12, g_ModuleID);
  v14 = v13;
  if ( !v13 )
  {
    Extended = -2147467259;
    goto LABEL_14;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13) )
    return 0;
  Extended = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 40LL))(v14, a1);
  if ( Extended < 0 )
    goto LABEL_14;
  return 1;
}

```

## disassembly

```asm
0x180003578  mov     rax, rsp
0x18000357b  mov     [rax+20h], rbx
0x18000357f  push    rbp
0x180003580  push    rsi
0x180003581  push    rdi
0x180003582  sub     rsp, 40h
0x180003586  xor     ebp, ebp
0x180003588  mov     rsi, rdx
0x18000358b  mov     [rax+18h], rbp
0x18000358f  mov     rbx, rcx
0x180003592  mov     [rax+10h], rbp
0x180003596  mov     edi, ebp
0x180003598  mov     [rax+8], ebp
0x18000359b  mov     rax, [rcx]
0x18000359e  mov     rax, [rax+0C0h]
0x1800035a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035aa  mov     r8, rax
0x1800035ad  test    rax, rax
0x1800035b0  jz      short loc_1800035CA
0x1800035b2  mov     rcx, [rax]
0x1800035b5  xor     edx, edx
0x1800035b7  mov     rax, [rcx+20h]
0x1800035bb  mov     rcx, r8
0x1800035be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c3  cmp     [rax], bp
0x1800035c6  setnz   dil
0x1800035ca  mov     rax, [rbx]
0x1800035cd  mov     rcx, rbx
0x1800035d0  test    rsi, rsi
0x1800035d3  jz      short loc_1800035EB
0x1800035d5  mov     rax, [rax+0C8h]
0x1800035dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e1  mov     eax, 2
0x1800035e6  jmp     loc_18000371D
0x1800035eb  mov     rax, [rax+0E8h]
0x1800035f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f7  test    rax, rax
0x1800035fa  jnz     loc_18000371B
0x180003600  test    edi, edi
0x180003602  jz      loc_18000371B
0x180003608  mov     rax, [rbx]
0x18000360b  mov     rcx, rbx
0x18000360e  mov     rax, [rax+8]
0x180003612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003617  mov     rcx, cs:?g_pServer@@3PEAVIHttpServer@@EA; IHttpServer * g_pServer
0x18000361e  lea     r8, [rsp+58h+arg_10]
0x180003623  mov     rdx, rax
0x180003626  call    ??$HttpGetExtendedInterface@VIHttpApplication@@VIHttpApplication2@@@@YAJPEAVIHttpServer@@PEAVIHttpApplication@@PEAPEAVIHttpApplication2@@@Z; HttpGetExtendedInterface<IHttpApplication,IHttpApplication2>(IHttpServer *,IHttpApplication *,IHttpApplication2 * *)
0x18000362b  mov     edi, eax
0x18000362d  test    eax, eax
0x18000362f  js      short loc_1800036A7
0x180003631  mov     rax, [rbx]
0x180003634  lea     r9, [rsp+58h+arg_0]
0x180003639  lea     r8, [rsp+58h+arg_8]
0x18000363e  mov     rcx, rbx
0x180003641  lea     rdx, aAppWarmingUp; "APP_WARMING_UP"
0x180003648  mov     rax, [rax+78h]
0x18000364c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003651  test    eax, eax
0x180003653  js      loc_18000371B
0x180003659  mov     rax, [rsp+58h+arg_8]
0x18000365e  cmp     byte ptr [rax], 31h ; '1'
0x180003661  jnz     loc_18000371B
0x180003667  cmp     [rax+1], bpl
0x18000366b  jnz     loc_18000371B
0x180003671  mov     rcx, [rsp+58h+arg_10]
0x180003676  mov     rax, [rcx]
0x180003679  mov     rax, [rax+18h]
0x18000367d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003682  mov     rdx, cs:?g_ModuleID@@3PEAXEA; void * g_ModuleID
0x180003689  mov     r8, rax
0x18000368c  mov     rcx, [rax]
0x18000368f  mov     rax, [rcx]
0x180003692  mov     rcx, r8
0x180003695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369a  mov     rdi, rax
0x18000369d  test    rax, rax
0x1800036a0  jnz     short loc_1800036E9
0x1800036a2  mov     edi, 80004005h
0x1800036a7  mov     rax, [rbx]
0x1800036aa  mov     rcx, rbx
0x1800036ad  mov     rax, [rax+20h]
0x1800036b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b6  mov     r10, rax
0x1800036b9  mov     [rsp+58h+var_28], ebp
0x1800036bd  xor     r9d, r9d
0x1800036c0  mov     [rsp+58h+var_30], rbp
0x1800036c5  mov     edx, 1F4h
0x1800036ca  mov     [rsp+58h+var_38], edi
0x1800036ce  mov     rcx, [rax]
0x1800036d1  lea     r8, aServerError; "Server Error"
0x1800036d8  mov     rax, [rcx+18h]
0x1800036dc  mov     rcx, r10
0x1800036df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e4  jmp     loc_1800035E1
0x1800036e9  mov     rax, [rax]
0x1800036ec  mov     rcx, rdi
0x1800036ef  mov     rax, [rax+20h]
0x1800036f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f8  test    eax, eax
0x1800036fa  jz      short loc_18000371B
0x1800036fc  mov     rax, [rdi]
0x1800036ff  mov     rdx, rbx
0x180003702  mov     rcx, rdi
0x180003705  mov     rax, [rax+28h]
0x180003709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370e  mov     edi, eax
0x180003710  test    eax, eax
0x180003712  js      short loc_1800036A7
0x180003714  mov     eax, 1
0x180003719  jmp     short loc_18000371D
0x18000371b  xor     eax, eax
0x18000371d  mov     rbx, [rsp+58h+arg_18]
0x180003722  add     rsp, 40h
0x180003726  pop     rdi
0x180003727  pop     rsi
0x180003728  pop     rbp
0x180003729  retn
```

# W3_STATIC_FILE_HANDLER::SetupHttpCachedResponse(IHttpContext *,_HTTP_CACHE_POLICY *)

- ea: `0x18000420c`
- end: `0x180004393`
- name: `?SetupHttpCachedResponse@W3_STATIC_FILE_HANDLER@@AEAAJPEAVIHttpContext@@PEAU_HTTP_CACHE_POLICY@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(W3_STATIC_FILE_HANDLER *__hidden this, struct IHttpContext *, struct _HTTP_CACHE_POLICY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180002dd8`

## callees

- `0x18000420c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall W3_STATIC_FILE_HANDLER::SetupHttpCachedResponse(
        W3_STATIC_FILE_HANDLER *this,
        struct IHttpContext *a2,
        struct _HTTP_CACHE_POLICY *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v12; // rax
  ULONG v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  W3_STATIC_FILE_HANDLER *v16; // [rsp+50h] [rbp+8h] BYREF

  v16 = this;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  LODWORD(v16) = 0;
  v8 = v7;
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 120LL))(v6)
    || *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) + 8) != 200 )
  {
    return (unsigned int)-2147024846;
  }
  if ( !(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 208LL))(a2) )
  {
    v9 = 18;
LABEL_5:
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 112LL))(v6, v9);
    return (unsigned int)-2147024846;
  }
  v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 208LL))(a2);
  if ( !(*(unsigned int (__fastcall **)(__int64, W3_STATIC_FILE_HANDLER **))(*(_QWORD *)v12 + 120LL))(v12, &v16) )
  {
    v9 = 2;
    goto LABEL_5;
  }
  if ( *(_QWORD *)(v8 + 96) )
  {
    v9 = 16;
    goto LABEL_5;
  }
  v13 = (unsigned int)v16;
  v10 = 0;
  if ( (_DWORD)v16 == -1 )
  {
    v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
    if ( *(_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) != 92
      || (v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2),
          *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15) + 2) != 92)
      || W3_STATIC_FILE_HANDLER::sm_fDoDirmonForUnc
      || a3->Policy != HttpCachePolicyTimeToLive )
    {
      a3->Policy = HttpCachePolicyUserInvalidates;
    }
  }
  else
  {
    a3->Policy = HttpCachePolicyTimeToLive;
    a3->SecondsToLive = v13;
  }
  return v10;
}

```

## disassembly

```asm
0x18000420c  mov     [rsp+arg_0], rcx
0x180004211  push    rbx
0x180004212  push    rsi
0x180004213  push    rdi
0x180004214  push    r14
0x180004216  sub     rsp, 28h
0x18000421a  mov     rax, [rdx]
0x18000421d  mov     rcx, rdx
0x180004220  mov     r14, r8
0x180004223  mov     rsi, rdx
0x180004226  mov     rax, [rax+18h]
0x18000422a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000422f  mov     rcx, [rsi]
0x180004232  mov     rbx, rax
0x180004235  mov     rax, [rcx+20h]
0x180004239  mov     rcx, rsi
0x18000423c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004241  mov     rcx, [rbx]
0x180004244  mov     rdi, rax
0x180004247  mov     rax, [rcx+8]
0x18000424b  mov     rcx, rbx
0x18000424e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004253  mov     dword ptr [rsp+48h+arg_0], 0
0x18000425b  mov     rbx, rax
0x18000425e  mov     rcx, [rdi]
0x180004261  mov     rax, [rcx+78h]
0x180004265  mov     rcx, rdi
0x180004268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000426d  test    eax, eax
0x18000426f  jz      short loc_1800042B4
0x180004271  mov     rcx, [rdi]
0x180004274  mov     rax, [rcx+8]
0x180004278  mov     rcx, rdi
0x18000427b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004280  mov     ecx, 0C8h
0x180004285  cmp     [rax+8], cx
0x180004289  jnz     short loc_1800042B4
0x18000428b  mov     rax, [rsi]
0x18000428e  mov     rcx, rsi
0x180004291  mov     rax, [rax+0D0h]
0x180004298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000429d  test    rax, rax
0x1800042a0  jnz     short loc_1800042C5
0x1800042a2  lea     edx, [rax+12h]
0x1800042a5  mov     rax, [rdi]
0x1800042a8  mov     rcx, rdi
0x1800042ab  mov     rax, [rax+70h]
0x1800042af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042b4  mov     ebx, 80070032h
0x1800042b9  mov     eax, ebx
0x1800042bb  add     rsp, 28h
0x1800042bf  pop     r14
0x1800042c1  pop     rdi
0x1800042c2  pop     rsi
0x1800042c3  pop     rbx
0x1800042c4  retn
0x1800042c5  mov     rax, [rsi]
0x1800042c8  mov     rcx, rsi
0x1800042cb  mov     rax, [rax+0D0h]
0x1800042d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d7  mov     r8, rax
0x1800042da  lea     rdx, [rsp+48h+arg_0]
0x1800042df  mov     rcx, [rax]
0x1800042e2  mov     rax, [rcx+78h]
0x1800042e6  mov     rcx, r8
0x1800042e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ee  test    eax, eax
0x1800042f0  jnz     short loc_1800042F7
0x1800042f2  lea     edx, [rax+2]
0x1800042f5  jmp     short loc_1800042A5
0x1800042f7  cmp     qword ptr [rbx+60h], 0
0x1800042fc  jz      short loc_180004305
0x1800042fe  mov     edx, 10h
0x180004303  jmp     short loc_1800042A5
0x180004305  mov     eax, dword ptr [rsp+48h+arg_0]
0x180004309  xor     ebx, ebx
0x18000430b  cmp     eax, 0FFFFFFFFh
0x18000430e  jnz     short loc_180004383
0x180004310  mov     rax, [rsi]
0x180004313  mov     rcx, rsi
0x180004316  mov     rax, [rax+0A0h]
0x18000431d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004322  mov     rdx, rax
0x180004325  mov     rcx, [rax]
0x180004328  mov     rax, [rcx+8]
0x18000432c  mov     rcx, rdx
0x18000432f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004334  cmp     word ptr [rax], 5Ch ; '\'
0x180004338  jnz     short loc_180004377
0x18000433a  mov     rax, [rsi]
0x18000433d  mov     rcx, rsi
0x180004340  mov     rax, [rax+0A0h]
0x180004347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000434c  mov     rdx, rax
0x18000434f  mov     rcx, [rax]
0x180004352  mov     rax, [rcx+8]
0x180004356  mov     rcx, rdx
0x180004359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000435e  cmp     word ptr [rax+2], 5Ch ; '\'
0x180004363  jnz     short loc_180004377
0x180004365  cmp     cs:?sm_fDoDirmonForUnc@W3_STATIC_FILE_HANDLER@@0HA, ebx; int W3_STATIC_FILE_HANDLER::sm_fDoDirmonForUnc
0x18000436b  jnz     short loc_180004377
0x18000436d  cmp     dword ptr [r14], 2
0x180004371  jz      loc_1800042B9
0x180004377  mov     dword ptr [r14], 1
0x18000437e  jmp     loc_1800042B9
0x180004383  mov     dword ptr [r14], 2
0x18000438a  mov     [r14+4], eax
0x18000438e  jmp     loc_1800042B9
```

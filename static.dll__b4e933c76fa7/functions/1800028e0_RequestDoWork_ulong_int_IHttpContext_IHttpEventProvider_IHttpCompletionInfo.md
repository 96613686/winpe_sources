# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800028e0`
- end: `0x180002bbe`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `734`
- prototype: `__int64 __fastcall(int, __int64, struct IHttpContext *, void (__fastcall ***)(_QWORD, __int64), __int64)`
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001e40`
- `0x180001ea0`
- `0x180001f00`
- `0x180001f60`
- `0x180001fc0`
- `0x180002020`
- `0x180002080`
- `0x1800020e0`
- `0x180002140`
- `0x1800021a0`
- `0x180002200`
- `0x180002460`
- `0x1800024c0`
- `0x180002520`
- `0x180002580`
- `0x180002620`
- `0x180002700`

## callees

- `0x1800028e0`
- `0x180002dd8`
- `0x180004590`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall RequestDoWork(
        int a1,
        __int64 a2,
        struct IHttpContext *a3,
        void (__fastcall ***a4)(_QWORD, __int64),
        __int64 a5)
{
  __int64 v7; // rax
  int ParsedMetadata; // edi
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  _QWORD *v13; // rax
  void (__fastcall ***v14)(_QWORD); // rdi
  __int64 v15; // rax
  int v16; // r14d
  __int64 v17; // rax
  __int64 v18; // rax
  struct INativeSectionException *v19; // [rsp+40h] [rbp-28h] BYREF
  struct STATIC_META_STORED_CONTEXT *v20; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v21[3]; // [rsp+50h] [rbp-18h] BYREF
  int v22; // [rsp+A8h] [rbp+40h] BYREF

  v20 = 0;
  v19 = 0;
  a5 = 0;
  v21[0] = 0;
  v22 = 0;
  if ( a1 != 128 )
    return 0;
  if ( !(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 208LL))(a3) )
    return 0;
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 208LL))(a3);
  if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7) & 0x10) != 0 )
    return 0;
  ParsedMetadata = STATIC_META_STORED_CONTEXT::GetParsedMetadata(a3, &v20, &v19);
  if ( ParsedMetadata < 0 )
  {
    if ( v19 )
      (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v19)(
        v19,
        &IID_IAppHostConfigException,
        &a5);
    v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9) + 536) = 0;
    v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v10 + 24LL))(
      v10,
      500,
      "Internal Server Error",
      19,
      ParsedMetadata,
      a5,
      0);
    if ( a5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 16LL))(a5);
      a5 = 0;
    }
    if ( v19 )
    {
      (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    v11 = (unsigned int)ParsedMetadata;
    goto LABEL_12;
  }
  v13 = (_QWORD *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a3 + 144LL))(a3, 24);
  v14 = (void (__fastcall ***)(_QWORD))v13;
  if ( !v13 )
  {
    v11 = 2147942408LL;
LABEL_12:
    (**a4)(a4, v11);
    return 2;
  }
  v13[1] = 0;
  *v13 = &W3_STATIC_FILE_HANDLER::`vftable';
  v13[2] = 0;
  v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
  v16 = (*(__int64 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD), void *))(*(_QWORD *)v15 + 8LL))(
          v15,
          v14,
          g_pStaticFileModuleContext);
  if ( v16 < 0 )
  {
    (**v14)(v14);
    (**a4)(a4, (unsigned int)v16);
    return 2;
  }
  if ( (*(int (__fastcall **)(struct IHttpContext *, const char *, _QWORD *, int *))(*(_QWORD *)a3 + 128LL))(
         a3,
         "DAV",
         v21,
         &v22) >= 0
    && v22 )
  {
    v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17) + 536) = 0;
    v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v18 + 24LL))(
      v18,
      404,
      "Not Found",
      16,
      -2147024894,
      0,
      0);
    (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 200LL))(a3);
    return 0;
  }
  return W3_STATIC_FILE_HANDLER::DoWork((__int64)v14, a3, (__int64)v20);
}

```

## disassembly

```asm
0x1800028e0  mov     [rsp-30h+arg_8], edx
0x1800028e4  push    rbp
0x1800028e5  push    rbx
0x1800028e6  push    rsi
0x1800028e7  push    rdi
0x1800028e8  push    r14
0x1800028ea  push    r15
0x1800028ec  mov     rbp, rsp
0x1800028ef  sub     rsp, 68h
0x1800028f3  xor     r15d, r15d
0x1800028f6  mov     rsi, r9
0x1800028f9  mov     [rbp+var_20], r15
0x1800028fd  mov     rbx, r8
0x180002900  mov     [rbp+var_28], r15
0x180002904  mov     [rbp+arg_20], r15
0x180002908  mov     [rbp+var_18], r15
0x18000290c  mov     [rbp+arg_8], r15d
0x180002910  cmp     ecx, 80h
0x180002916  jnz     loc_180002B8C
0x18000291c  mov     rax, [r8]
0x18000291f  mov     rcx, rbx
0x180002922  mov     rax, [rax+0D0h]
0x180002929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000292e  test    rax, rax
0x180002931  jz      loc_180002B8C
0x180002937  mov     rax, [rbx]
0x18000293a  mov     rcx, rbx
0x18000293d  mov     rax, [rax+0D0h]
0x180002944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002949  mov     rdx, rax
0x18000294c  mov     rcx, [rax]
0x18000294f  mov     rax, [rcx+38h]
0x180002953  mov     rcx, rdx
0x180002956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000295b  test    al, 10h
0x18000295d  jnz     loc_180002B8C
0x180002963  lea     r8, [rbp+var_28]; struct INativeSectionException **
0x180002967  mov     rcx, rbx; struct IHttpContext *
0x18000296a  lea     rdx, [rbp+var_20]; struct STATIC_META_STORED_CONTEXT **
0x18000296e  call    ?GetParsedMetadata@STATIC_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAVINativeSectionException@@@Z; STATIC_META_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,STATIC_META_STORED_CONTEXT * *,INativeSectionException * *)
0x180002973  mov     edi, eax
0x180002975  test    eax, eax
0x180002977  jns     loc_180002A56
0x18000297d  mov     rcx, [rbp+var_28]
0x180002981  test    rcx, rcx
0x180002984  jz      short loc_18000299C
0x180002986  mov     rdx, [rcx]
0x180002989  lea     r8, [rbp+arg_20]
0x18000298d  mov     rax, [rdx]
0x180002990  lea     rdx, IID_IAppHostConfigException
0x180002997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000299c  mov     rax, [rbx]
0x18000299f  mov     rcx, rbx
0x1800029a2  mov     rax, [rax+20h]
0x1800029a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ab  mov     rdx, rax
0x1800029ae  mov     rcx, [rax]
0x1800029b1  mov     rax, [rcx+8]
0x1800029b5  mov     rcx, rdx
0x1800029b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029bd  mov     rcx, rbx
0x1800029c0  mov     [rax+218h], r15w
0x1800029c8  mov     rax, [rbx]
0x1800029cb  mov     rax, [rax+20h]
0x1800029cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d4  mov     r10, rax
0x1800029d7  mov     [rsp+68h+var_38], r15d
0x1800029dc  mov     edx, 1F4h
0x1800029e1  lea     r8, aInternalServer; "Internal Server Error"
0x1800029e8  mov     r9d, 13h
0x1800029ee  mov     rcx, [rax]
0x1800029f1  mov     rax, [rcx+18h]
0x1800029f5  mov     rcx, [rbp+arg_20]
0x1800029f9  mov     [rsp+68h+var_40], rcx
0x1800029fe  mov     rcx, r10
0x180002a01  mov     dword ptr [rsp+68h+var_48], edi
0x180002a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0a  mov     rcx, [rbp+arg_20]
0x180002a0e  test    rcx, rcx
0x180002a11  jz      short loc_180002A23
0x180002a13  mov     rax, [rcx]
0x180002a16  mov     rax, [rax+10h]
0x180002a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a1f  mov     [rbp+arg_20], r15
0x180002a23  mov     rcx, [rbp+var_28]
0x180002a27  test    rcx, rcx
0x180002a2a  jz      short loc_180002A3C
0x180002a2c  mov     rax, [rcx]
0x180002a2f  mov     rax, [rax+10h]
0x180002a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a38  mov     [rbp+var_28], r15
0x180002a3c  mov     edx, edi
0x180002a3e  mov     rax, [rsi]
0x180002a41  mov     rax, [rax]
0x180002a44  mov     rcx, rsi
0x180002a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4c  mov     eax, 2
0x180002a51  jmp     loc_180002B8E
0x180002a56  mov     rax, [rbx]
0x180002a59  mov     edx, 18h
0x180002a5e  mov     rcx, rbx
0x180002a61  mov     rax, [rax+90h]
0x180002a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6d  mov     rdi, rax
0x180002a70  test    rax, rax
0x180002a73  jz      loc_180002BB4
0x180002a79  lea     rax, ??_7W3_STATIC_FILE_HANDLER@@6B@; const W3_STATIC_FILE_HANDLER::`vftable'
0x180002a80  mov     [rdi+8], r15
0x180002a84  mov     [rdi], rax
0x180002a87  mov     [rdi+10h], r15
0x180002a8b  mov     rcx, [rbx]
0x180002a8e  mov     rax, [rcx+38h]
0x180002a92  mov     rcx, rbx
0x180002a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a9a  mov     r8, cs:?g_pStaticFileModuleContext@@3PEAXEA; void * g_pStaticFileModuleContext
0x180002aa1  mov     r9, rax
0x180002aa4  mov     rdx, rdi
0x180002aa7  mov     rcx, [rax]
0x180002aaa  mov     rax, [rcx+8]
0x180002aae  mov     rcx, r9
0x180002ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab6  mov     r14d, eax
0x180002ab9  test    eax, eax
0x180002abb  jns     short loc_180002AD9
0x180002abd  mov     rcx, [rdi]
0x180002ac0  mov     rax, [rcx]
0x180002ac3  mov     rcx, rdi
0x180002ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002acb  mov     rcx, [rsi]
0x180002ace  mov     edx, r14d
0x180002ad1  mov     rax, [rcx]
0x180002ad4  jmp     loc_180002A44
0x180002ad9  mov     rax, [rbx]
0x180002adc  lea     r9, [rbp+arg_8]
0x180002ae0  lea     r8, [rbp+var_18]
0x180002ae4  mov     rcx, rbx
0x180002ae7  lea     rdx, aDav; "DAV"
0x180002aee  mov     rax, [rax+80h]
0x180002af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002afa  test    eax, eax
0x180002afc  js      loc_180002B9B
0x180002b02  cmp     [rbp+arg_8], r15d
0x180002b06  jbe     loc_180002B9B
0x180002b0c  mov     rax, [rbx]
0x180002b0f  mov     rcx, rbx
0x180002b12  mov     rax, [rax+20h]
0x180002b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b1b  mov     rdx, rax
0x180002b1e  mov     rcx, [rax]
0x180002b21  mov     rax, [rcx+8]
0x180002b25  mov     rcx, rdx
0x180002b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b2d  mov     rcx, rbx
0x180002b30  mov     [rax+218h], r15w
0x180002b38  mov     rax, [rbx]
0x180002b3b  mov     rax, [rax+20h]
0x180002b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b44  mov     r10, rax
0x180002b47  mov     [rsp+68h+var_38], r15d
0x180002b4c  mov     edx, 194h
0x180002b51  mov     [rsp+68h+var_40], r15
0x180002b56  mov     r9d, 10h
0x180002b5c  mov     dword ptr [rsp+68h+var_48], 80070002h
0x180002b64  mov     rcx, [rax]
0x180002b67  lea     r8, aNotFound; "Not Found"
0x180002b6e  mov     rax, [rcx+18h]
0x180002b72  mov     rcx, r10
0x180002b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7a  mov     rax, [rbx]
0x180002b7d  mov     rcx, rbx
0x180002b80  mov     rax, [rax+0C8h]
0x180002b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b8c  xor     eax, eax
0x180002b8e  add     rsp, 68h
0x180002b92  pop     r15
0x180002b94  pop     r14
0x180002b96  pop     rdi
0x180002b97  pop     rsi
0x180002b98  pop     rbx
0x180002b99  pop     rbp
0x180002b9a  retn
0x180002b9b  mov     r8, [rbp+var_20]
0x180002b9f  xor     r9d, r9d
0x180002ba2  mov     rdx, rbx
0x180002ba5  mov     [rsp+68h+var_48], r15
0x180002baa  mov     rcx, rdi
0x180002bad  call    ?DoWork@W3_STATIC_FILE_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVSTATIC_META_STORED_CONTEXT@@HPEAVSTRA@@@Z; W3_STATIC_FILE_HANDLER::DoWork(IHttpContext *,STATIC_META_STORED_CONTEXT *,int,STRA *)
0x180002bb2  jmp     short loc_180002B8E
0x180002bb4  mov     edx, 80070008h
0x180002bb9  jmp     loc_180002A3E
```

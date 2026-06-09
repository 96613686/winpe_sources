# WARMUP_APPLICATION_CONTEXT::RewriteUrl(IHttpContext *)

- ea: `0x180004810`
- end: `0x180004a81`
- name: `?RewriteUrl@WARMUP_APPLICATION_CONTEXT@@UEAAJPEAVIHttpContext@@@Z`
- size: `625`
- prototype: `__int64 __fastcall(WARMUP_APPLICATION_CONTEXT *__hidden this, struct IHttpContext *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180004810`
- `0x180006010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180004a08`
- `iisutil!PuDbgPrint` at `0x180004a08`

## string_xrefs

- `0x1800049e5`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmupcontext.cxx`
- `0x1800049d8`: `WARMUP_APPLICATION_CONTEXT::RewriteUrl`

## pseudocode

```c
__int64 __fastcall WARMUP_APPLICATION_CONTEXT::RewriteUrl(WARMUP_APPLICATION_CONTEXT *this, struct IHttpContext *a2)
{
  __int64 v2; // rax
  int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rax
  void (__fastcall ***v10)(_QWORD); // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(_QWORD *)a2;
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64, __int64 *))(v2 + 248))(a2, 3, &v17);
  if ( v5 < 0
    || (v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17),
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v6 + 88LL))(
               v6,
               *((_QWORD *)this + 7),
               *((unsigned int *)this + 18),
               1),
        v5 < 0)
    || (v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17),
        v5 = (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v7 + 72LL))(v7, "GET"),
        v5 < 0)
    || (v5 = (*(__int64 (__fastcall **)(__int64, const char *, const wchar_t *))(*(_QWORD *)v17 + 136LL))(
               v17,
               "SKIP_MANAGED_MODULES",
               L"1"),
        v5 < 0) )
  {
LABEL_12:
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 256LL))(v17);
    return (unsigned int)v5;
  }
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
  (*(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v8 + 56LL))(v8, "If-Modified-Since");
  v9 = operator new(0x10u);
  v10 = (void (__fastcall ***)(_QWORD))v9;
  if ( !v9 )
  {
    v5 = -2147024882;
    goto LABEL_12;
  }
  v9[1] = 0;
  *v9 = &MODULE_CONTEXT::`vftable';
  v9[1] = v17;
  v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
  v5 = (*(__int64 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD), void *))(*(_QWORD *)v11 + 8LL))(
         v11,
         v10,
         g_ModuleID);
  if ( v5 < 0 )
    goto LABEL_10;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
    v13 = *(const wchar_t **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12) + 88);
    v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmupcontext.cxx",
      241,
      "WARMUP_APPLICATION_CONTEXT::RewriteUrl",
      "Mapping [%S] to [%S]\r\n",
      *(const wchar_t **)(v15 + 88),
      v13);
  }
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64, __int64))(*(_QWORD *)a2 + 104LL))(a2, 1, v17);
  if ( v5 < 0 )
  {
LABEL_10:
    (**v10)(v10);
    goto LABEL_12;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004810  mov     r11, rsp
0x180004813  mov     [r11+8], rbx
0x180004817  mov     [r11+18h], rsi
0x18000481b  push    rdi
0x18000481c  sub     rsp, 40h
0x180004820  mov     rax, [rdx]
0x180004823  lea     r8, [r11+10h]
0x180004827  mov     rsi, rdx
0x18000482a  mov     qword ptr [r11+10h], 0
0x180004832  mov     rdi, rcx
0x180004835  mov     edx, 3
0x18000483a  mov     rcx, rsi
0x18000483d  mov     rax, [rax+0F8h]
0x180004844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004849  mov     ebx, eax
0x18000484b  test    eax, eax
0x18000484d  js      loc_180004A56
0x180004853  mov     rcx, [rsp+48h+arg_8]
0x180004858  mov     rax, [rcx]
0x18000485b  mov     rax, [rax+18h]
0x18000485f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004864  mov     r8d, [rdi+48h]
0x180004868  mov     r10, rax
0x18000486b  mov     rdx, [rdi+38h]
0x18000486f  mov     r9d, 1
0x180004875  mov     rcx, [rax]
0x180004878  mov     rax, [rcx+58h]
0x18000487c  mov     rcx, r10
0x18000487f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004884  mov     ebx, eax
0x180004886  test    eax, eax
0x180004888  js      loc_180004A56
0x18000488e  mov     rcx, [rsp+48h+arg_8]
0x180004893  mov     rax, [rcx]
0x180004896  mov     rax, [rax+18h]
0x18000489a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489f  mov     r8, rax
0x1800048a2  lea     rdx, aGet; "GET"
0x1800048a9  mov     rcx, [rax]
0x1800048ac  mov     rax, [rcx+48h]
0x1800048b0  mov     rcx, r8
0x1800048b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b8  mov     ebx, eax
0x1800048ba  test    eax, eax
0x1800048bc  js      loc_180004A56
0x1800048c2  mov     rcx, [rsp+48h+arg_8]
0x1800048c7  lea     r8, a1; "1"
0x1800048ce  lea     rdx, aSkipManagedMod; "SKIP_MANAGED_MODULES"
0x1800048d5  mov     rax, [rcx]
0x1800048d8  mov     rax, [rax+88h]
0x1800048df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e4  mov     ebx, eax
0x1800048e6  test    eax, eax
0x1800048e8  js      loc_180004A56
0x1800048ee  mov     rcx, [rsp+48h+arg_8]
0x1800048f3  mov     rax, [rcx]
0x1800048f6  mov     rax, [rax+18h]
0x1800048fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ff  mov     r8, rax
0x180004902  lea     rdx, aIfModifiedSinc; "If-Modified-Since"
0x180004909  mov     rcx, [rax]
0x18000490c  mov     rax, [rcx+38h]
0x180004910  mov     rcx, r8
0x180004913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004918  mov     ecx, 10h; Size
0x18000491d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004922  mov     rdi, rax
0x180004925  test    rax, rax
0x180004928  jz      loc_180004A51
0x18000492e  mov     qword ptr [rdi+8], 0
0x180004936  lea     rax, ??_7MODULE_CONTEXT@@6B@; const MODULE_CONTEXT::`vftable'
0x18000493d  mov     [rdi], rax
0x180004940  mov     rcx, [rsp+48h+arg_8]
0x180004945  mov     [rdi+8], rcx
0x180004949  mov     rcx, [rsi]
0x18000494c  mov     rax, [rcx+38h]
0x180004950  mov     rcx, rsi
0x180004953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004958  mov     r8, cs:?g_ModuleID@@3PEAXEA; void * g_ModuleID
0x18000495f  mov     r9, rax
0x180004962  mov     rdx, rdi
0x180004965  mov     rcx, [rax]
0x180004968  mov     rax, [rcx+8]
0x18000496c  mov     rcx, r9
0x18000496f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004974  mov     ebx, eax
0x180004976  test    eax, eax
0x180004978  js      loc_180004A41
0x18000497e  test    byte ptr cs:g_dwDebugFlags, 3
0x180004985  jz      loc_180004A0E
0x18000498b  mov     rcx, [rsp+48h+arg_8]
0x180004990  mov     rax, [rcx]
0x180004993  mov     rax, [rax+18h]
0x180004997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000499c  mov     rdx, rax
0x18000499f  mov     rcx, [rax]
0x1800049a2  mov     rax, [rcx+8]
0x1800049a6  mov     rcx, rdx
0x1800049a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ae  mov     rcx, rsi
0x1800049b1  mov     rbx, [rax+58h]
0x1800049b5  mov     rax, [rsi]
0x1800049b8  mov     rax, [rax+18h]
0x1800049bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c1  mov     rdx, rax
0x1800049c4  mov     rcx, [rax]
0x1800049c7  mov     rax, [rcx+8]
0x1800049cb  mov     rcx, rdx
0x1800049ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049d3  mov     [rsp+48h+var_18], rbx
0x1800049d8  lea     r9, aWarmupApplicat_0; "WARMUP_APPLICATION_CONTEXT::RewriteUrl"
0x1800049df  mov     r8d, 0F1h
0x1800049e5  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800049ec  mov     rcx, [rax+58h]
0x1800049f0  lea     rax, aMappingSToS; "Mapping [%S] to [%S]\r\n"
0x1800049f7  mov     [rsp+48h+var_20], rcx
0x1800049fc  mov     rcx, cs:g_pDebug
0x180004a03  mov     [rsp+48h+var_28], rax
0x180004a08  call    cs:__imp_PuDbgPrint
0x180004a0e  mov     rax, [rsi]
0x180004a11  xor     r9d, r9d
0x180004a14  mov     r8, [rsp+48h+arg_8]
0x180004a19  mov     rcx, rsi
0x180004a1c  mov     [rsp+48h+var_20], 0
0x180004a25  mov     [rsp+48h+var_28], 0
0x180004a2e  mov     rax, [rax+68h]
0x180004a32  lea     edx, [r9+1]
0x180004a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a3b  mov     ebx, eax
0x180004a3d  test    eax, eax
0x180004a3f  jns     short loc_180004A6F
0x180004a41  mov     rax, [rdi]
0x180004a44  mov     rcx, rdi
0x180004a47  mov     rax, [rax]
0x180004a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a4f  jmp     short loc_180004A56
0x180004a51  mov     ebx, 8007000Eh
0x180004a56  mov     rcx, [rsp+48h+arg_8]
0x180004a5b  test    rcx, rcx
0x180004a5e  jz      short loc_180004A6F
0x180004a60  mov     rax, [rcx]
0x180004a63  mov     rax, [rax+100h]
0x180004a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a6f  mov     rsi, [rsp+48h+arg_10]
0x180004a74  mov     eax, ebx
0x180004a76  mov     rbx, [rsp+48h+arg_0]
0x180004a7b  add     rsp, 40h
0x180004a7f  pop     rdi
0x180004a80  retn
```

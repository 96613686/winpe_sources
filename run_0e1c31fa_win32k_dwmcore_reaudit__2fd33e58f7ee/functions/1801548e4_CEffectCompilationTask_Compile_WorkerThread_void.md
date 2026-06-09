# CEffectCompilationTask::Compile_WorkerThread(void)

- ea: `0x1801548e4`
- end: `0x180154a87`
- name: `?Compile_WorkerThread@CEffectCompilationTask@@AEAAXXZ`
- size: `419`
- prototype: `void __fastcall(CEffectCompilationTask *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802422b0`

## callees

- `0x180035124`
- `0x180042de0`
- `0x180044220`
- `0x180053b90`
- `0x1801548e4`
- `0x180154a90`
- `0x1801d6e60`
- `0x1801d6ec4`
- `0x18020a2b8`
- `0x180242338`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1801548fe`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1801548fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180154a54`
- `OLEAUT32!__imp_SysFreeString` at `0x180154a54`
- `wuceffects!CompileEffectDescription` at `0x180154924`
- `wuceffects!CompileEffectDescription` at `0x180154924`

## pseudocode

```c
void __fastcall CEffectCompilationTask::Compile_WorkerThread(CEffectCompilationTask *this)
{
  __int64 v2; // rcx
  int v3; // esi
  _QWORD *v4; // rax
  void (__fastcall ***v5)(_QWORD); // rcx
  _QWORD *v6; // rdi
  __int64 v7; // rdx
  OLECHAR *v8; // rbp
  CEffectCompilationService *v9; // rcx
  void (__fastcall ***v10)(_QWORD); // rcx
  void (__fastcall ***v11)(_QWORD); // [rsp+50h] [rbp+8h] BYREF
  char v12; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  SetRestrictedErrorInfo(0);
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    McTemplateU0x_EventWriteTransfer(v2, EVTDESC_COMPILE_EFFECT_Start);
  Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&v11);
  v3 = CompileEffectDescription(*((_QWORD *)this + 7), &v11);
  if ( v3 < 0 )
  {
    v8 = (OLECHAR *)*((_QWORD *)this + 11);
    if ( v8 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      SysFreeString(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
    }
    *((_QWORD *)this + 11) = 0;
    CEffectCompilationTask::GetRestrictedErrorDescription((unsigned __int16 **)this + 11);
  }
  else
  {
    v4 = MIDL_user_allocate(0x28u);
    v6 = v4;
    if ( v4 )
    {
      v5 = v11;
      *v4 = 0;
      v4[1] = 0;
      *((_DWORD *)v4 + 4) = 0;
      v4[3] = this;
      v4[4] = v5;
      if ( v5 )
        (**v5)(v5);
    }
    else
    {
      v6 = 0;
    }
    v7 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v6;
    if ( v7 )
      std::default_delete<CCompiledEffectCache>::operator()();
    if ( !*((_QWORD *)this + 10) )
    {
      v3 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0xB9u, 0);
    }
  }
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    McTemplateU0x_EventWriteTransfer(v5, EVTDESC_COMPILE_EFFECT_Stop);
  v9 = (CEffectCompilationService *)*((_QWORD *)this + 2);
  *((_DWORD *)this + 19) = v3;
  *((_DWORD *)this + 18) = (v3 >> 31) + 3;
  CEffectCompilationService::OnTaskCompleted_AnyThread(v9, this, 0);
  v10 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*v10)[1](v10);
  }
}

```

## disassembly

```asm
0x1801548e4  mov     [rsp+arg_10], rbx
0x1801548e9  push    rbp
0x1801548ea  push    rsi
0x1801548eb  push    rdi
0x1801548ec  sub     rsp, 30h
0x1801548f0  mov     rbx, rcx
0x1801548f3  mov     [rsp+48h+arg_0], 0
0x1801548fc  xor     ecx, ecx
0x1801548fe  call    cs:__imp_SetRestrictedErrorInfo
0x180154904  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18015490b  jnz     loc_180154A33
0x180154911  lea     rcx, [rsp+48h+arg_0]
0x180154916  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x18015491b  mov     rcx, [rbx+38h]
0x18015491f  lea     rdx, [rsp+48h+arg_0]
0x180154924  call    cs:__imp_CompileEffectDescription
0x18015492a  mov     esi, eax
0x18015492c  test    eax, eax
0x18015492e  js      loc_1801549BD
0x180154934  mov     ecx, 28h ; '('; size
0x180154939  call    MIDL_user_allocate
0x18015493e  mov     rdi, rax
0x180154941  test    rax, rax
0x180154944  jz      loc_180154A2C
0x18015494a  mov     rcx, [rsp+48h+arg_0]
0x18015494f  mov     qword ptr [rax], 0
0x180154956  mov     qword ptr [rax+8], 0
0x18015495e  mov     dword ptr [rax+10h], 0
0x180154965  mov     [rax+18h], rbx
0x180154969  mov     [rax+20h], rcx
0x18015496d  test    rcx, rcx
0x180154970  jz      short loc_18015497D
0x180154972  mov     rdx, [rcx]
0x180154975  mov     rax, [rdx]
0x180154978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015497d  mov     rdx, [rbx+50h]
0x180154981  mov     [rbx+50h], rdi
0x180154985  test    rdx, rdx
0x180154988  jnz     loc_180154A69
0x18015498e  cmp     qword ptr [rbx+50h], 0
0x180154993  jnz     short loc_1801549D8
0x180154995  xor     edx, edx; int *
0x180154997  mov     [rsp+48h+var_20], 0; void *
0x1801549a0  mov     esi, 8007000Eh
0x1801549a5  mov     [rsp+48h+var_28], 0B9h; unsigned int
0x1801549ad  mov     r9d, esi; int
0x1801549b0  xor     r8d, r8d; unsigned int
0x1801549b3  lea     ecx, [rdx+14h]; unsigned int
0x1801549b6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801549bb  jmp     short loc_1801549D8
0x1801549bd  lea     rdi, [rbx+58h]
0x1801549c1  mov     rbp, [rdi]
0x1801549c4  test    rbp, rbp
0x1801549c7  jnz     short loc_180154A47
0x1801549c9  mov     rcx, rdi; unsigned __int16 **
0x1801549cc  mov     qword ptr [rdi], 0
0x1801549d3  call    ?GetRestrictedErrorDescription@CEffectCompilationTask@@SAJPEAPEAG@Z; CEffectCompilationTask::GetRestrictedErrorDescription(ushort * *)
0x1801549d8  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1801549df  jnz     loc_180154A73
0x1801549e5  mov     rcx, [rbx+10h]; this
0x1801549e9  xor     r8d, r8d; bool
0x1801549ec  mov     [rbx+4Ch], esi
0x1801549ef  mov     rdx, rbx; struct CEffectCompilationTask *
0x1801549f2  sar     esi, 1Fh
0x1801549f5  add     esi, 3
0x1801549f8  mov     [rbx+48h], esi
0x1801549fb  call    ?OnTaskCompleted_AnyThread@CEffectCompilationService@@AEAAXPEAVCEffectCompilationTask@@_N@Z; CEffectCompilationService::OnTaskCompleted_AnyThread(CEffectCompilationTask *,bool)
0x180154a00  mov     rcx, [rsp+48h+arg_0]
0x180154a05  test    rcx, rcx
0x180154a08  jz      short loc_180154A1F
0x180154a0a  mov     [rsp+48h+arg_0], 0
0x180154a13  mov     rax, [rcx]
0x180154a16  mov     rax, [rax+8]
0x180154a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154a1f  mov     rbx, [rsp+48h+arg_10]
0x180154a24  add     rsp, 30h
0x180154a28  pop     rdi
0x180154a29  pop     rsi
0x180154a2a  pop     rbp
0x180154a2b  retn
0x180154a2c  xor     edi, edi
0x180154a2e  jmp     loc_18015497D
0x180154a33  mov     r8, rbx
0x180154a36  lea     rdx, EVTDESC_COMPILE_EFFECT_Start
0x180154a3d  call    McTemplateU0x_EventWriteTransfer
0x180154a42  jmp     loc_180154911
0x180154a47  lea     rcx, [rsp+48h+arg_8]; this
0x180154a4c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180154a51  mov     rcx, rbp; bstrString
0x180154a54  call    cs:__imp_SysFreeString
0x180154a5a  lea     rcx, [rsp+48h+arg_8]; this
0x180154a5f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180154a64  jmp     loc_1801549C9
0x180154a69  call    ??R?$default_delete@VCCompiledEffectCache@@@std@@QEBAXPEAVCCompiledEffectCache@@@Z; std::default_delete<CCompiledEffectCache>::operator()(CCompiledEffectCache *)
0x180154a6e  jmp     loc_18015498E
0x180154a73  mov     r8, rbx
0x180154a76  lea     rdx, EVTDESC_COMPILE_EFFECT_Stop
0x180154a7d  call    McTemplateU0x_EventWriteTransfer
0x180154a82  jmp     loc_1801549E5
```

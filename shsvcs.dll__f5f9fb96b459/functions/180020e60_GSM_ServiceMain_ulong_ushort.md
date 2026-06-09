# GSM::ServiceMain(ulong,ushort * *)

- ea: `0x180020e60`
- end: `0x180020f24`
- name: `?ServiceMain@GSM@@YAXKPEAPEAG@Z`
- size: `196`
- prototype: `void __fastcall(GSM *this, const unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001c040`

## callees

- `0x1800140f0`
- `0x1800149a0`
- `0x180020e60`
- `0x180022184`
- `0x1800222d4`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180020ea5`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180020ea5`

## pseudocode

```c
void __fastcall GSM::ServiceMain(GSM *this, const unsigned __int16 **a2, unsigned __int16 **a3)
{
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  const unsigned __int16 *v7; // r8
  int v8[4]; // [rsp+20h] [rbp-C8h] BYREF
  void **v9; // [rsp+30h] [rbp-B8h] BYREF
  int v10; // [rsp+38h] [rbp-B0h]
  int v11; // [rsp+40h] [rbp-A8h]
  __int64 v12; // [rsp+48h] [rbp-A0h]
  unsigned __int16 v13[64]; // [rsp+50h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59029361>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_59029361>::GetImpl'::`2'::impl,
                          a2,
                          a3) )
  {
    v8[0] = 1;
    if ( !(unsigned int)SetProcessMitigationPolicy(16, v8) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, v4, v5, v6);
  }
  v7 = *a2;
  v9 = &GSM::CServiceMainTask::`vftable';
  v10 = 1;
  v11 = -2147418113;
  v12 = 0;
  GSM::g_loadedcontext = 1;
  if ( (int)StringCchCopyW(v13, 0x40u, v7) >= 0 )
    CThreadTask::_CallDoStuff((CThreadTask *)&v9);
}

```

## disassembly

```asm
0x180020e60  push    rbx
0x180020e62  sub     rsp, 0E0h
0x180020e69  mov     rax, cs:__security_cookie
0x180020e70  xor     rax, rsp
0x180020e73  mov     [rsp+0E8h+var_18], rax
0x180020e7b  mov     rbx, rdx
0x180020e7e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59029361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59029361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59029361> `wil::Feature<__WilFeatureTraits_Feature_59029361>::GetImpl(void)'::`2'::impl
0x180020e85  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59029361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59029361>::__private_IsEnabled(void)
0x180020e8a  test    al, al
0x180020e8c  jz      short loc_180020EBC
0x180020e8e  mov     r8d, 4
0x180020e94  mov     [rsp+0E8h+var_C8], 1
0x180020e9c  lea     rdx, [rsp+0E8h+var_C8]
0x180020ea1  lea     ecx, [r8+0Ch]
0x180020ea5  call    cs:__imp_SetProcessMitigationPolicy
0x180020eab  test    eax, eax
0x180020ead  jnz     short loc_180020EBC
0x180020eaf  mov     rcx, [rsp+0E8h]; this
0x180020eb7  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180020ebc  mov     r8, [rbx]; unsigned __int16 *
0x180020ebf  lea     rax, ??_7CServiceMainTask@GSM@@6B@; const GSM::CServiceMainTask::`vftable'
0x180020ec6  mov     edx, 40h ; '@'; unsigned __int64
0x180020ecb  mov     [rsp+0E8h+var_B8], rax
0x180020ed0  lea     rcx, [rsp+0E8h+var_98]; unsigned __int16 *
0x180020ed5  mov     [rsp+0E8h+var_B0], 1
0x180020edd  mov     [rsp+0E8h+var_A8], 8000FFFFh
0x180020ee5  mov     [rsp+0E8h+var_A0], 0
0x180020eee  mov     cs:?g_loadedcontext@GSM@@3W4LOADEDCONTEXT@1@A, 1; GSM::LOADEDCONTEXT GSM::g_loadedcontext
0x180020ef8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020efd  test    eax, eax
0x180020eff  js      short loc_180020F0B
0x180020f01  lea     rcx, [rsp+0E8h+var_B8]; this
0x180020f06  call    ?_CallDoStuff@CThreadTask@@AEAAJXZ; CThreadTask::_CallDoStuff(void)
0x180020f0b  mov     rcx, [rsp+0E8h+var_18]
0x180020f13  xor     rcx, rsp; StackCookie
0x180020f16  call    __security_check_cookie
0x180020f1b  add     rsp, 0E0h
0x180020f22  pop     rbx
0x180020f23  retn
```

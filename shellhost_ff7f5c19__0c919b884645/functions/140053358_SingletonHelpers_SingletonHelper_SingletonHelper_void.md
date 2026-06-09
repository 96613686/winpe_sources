# SingletonHelpers::SingletonHelper::~SingletonHelper(void)

- ea: `0x140053358`
- end: `0x14005344e`
- name: `??1SingletonHelper@SingletonHelpers@@QEAA@XZ`
- size: `246`
- prototype: `void __fastcall(SingletonHelpers::SingletonHelper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005458c`

## callees

- `0x140009d6c`
- `0x14000ab50`
- `0x14000c0c8`
- `0x14000d218`
- `0x140046a30`
- `0x140053190`
- `0x140053358`
- `0x140054d44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140053386`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140053386`

## string_xrefs

- `0x14005343c`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

## pseudocode

```c
void __fastcall SingletonHelpers::SingletonHelper::~SingletonHelper(SingletonHelpers::SingletonHelper *this)
{
  _QWORD *v2; // rbp
  char **v3; // rbx
  char **v4; // rsi
  int v5; // ebx
  const char *v6; // r9
  __int64 v7; // rcx
  char *v8; // rax
  __int64 v9; // rcx
  char *v10; // rax
  void *v11; // rdx
  wil::details *v12; // rcx
  _QWORD v13[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v14[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)this = &SingletonHelpers::SingletonHelper::`vftable';
  v2 = (_QWORD *)((char *)this + 112);
  if ( *((_QWORD *)this + 14) )
  {
    v5 = *((_DWORD *)this + 30);
    if ( v5 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x136,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
        v6);
    v3 = (char **)((char *)this + 40);
    v7 = *((_QWORD *)this + 7);
    if ( *((_QWORD *)this + 8) <= 7u )
      v8 = (char *)this + 40;
    else
      v8 = *v3;
    v13[0] = v8;
    v13[1] = v7;
    v4 = (char **)((char *)this + 8);
    v9 = *((_QWORD *)this + 3);
    if ( *((_QWORD *)this + 4) <= 7u )
      v10 = (char *)this + 8;
    else
      v10 = *v4;
    v14[0] = v10;
    v14[1] = v9;
    SingletonHelpers::details::ClearDataForSingletonInstance(v2, (__int64)v14, (__int64)v13, v6);
  }
  else
  {
    v3 = (char **)((char *)this + 40);
    v4 = (char **)((char *)this + 8);
  }
  std::_Func_class<void,>::~_Func_class<void,>((char *)this + 264);
  FlowEndpointBase::~FlowEndpointBase((SingletonHelpers::SingletonHelper *)((char *)this + 128));
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v2);
  v12 = (wil::details *)*((_QWORD *)this + 13);
  if ( v12 )
    wil::details::CloseHandle(v12, v11);
  std::wstring::~wstring((char *)this + 72);
  std::wstring::~wstring(v3);
  std::wstring::~wstring(v4);
}

```

## disassembly

```asm
0x140053358  push    rbx
0x14005335a  push    rbp
0x14005335b  push    rsi
0x14005335c  push    rdi
0x14005335d  sub     rsp, 48h
0x140053361  mov     rdi, rcx
0x140053364  lea     rax, ??_7SingletonHelper@SingletonHelpers@@6B@; const SingletonHelpers::SingletonHelper::`vftable'
0x14005336b  mov     [rcx], rax
0x14005336e  lea     rbp, [rcx+70h]
0x140053372  cmp     qword ptr [rbp+0], 0
0x140053377  jnz     short loc_140053383
0x140053379  lea     rbx, [rcx+28h]
0x14005337d  lea     rsi, [rcx+8]
0x140053381  jmp     short loc_1400533E8
0x140053383  mov     ebx, [rcx+78h]
0x140053386  call    cs:__imp_GetCurrentThreadId
0x14005338c  cmp     ebx, eax
0x14005338e  jnz     loc_140053437
0x140053394  lea     rbx, [rdi+28h]
0x140053398  mov     rcx, [rbx+10h]
0x14005339c  cmp     qword ptr [rbx+18h], 7
0x1400533a1  jbe     short loc_1400533A8
0x1400533a3  mov     rax, [rbx]
0x1400533a6  jmp     short loc_1400533AB
0x1400533a8  mov     rax, rbx
0x1400533ab  mov     [rsp+68h+var_48], rax
0x1400533b0  mov     [rsp+68h+var_40], rcx
0x1400533b5  lea     rsi, [rdi+8]
0x1400533b9  mov     rcx, [rsi+10h]
0x1400533bd  cmp     qword ptr [rsi+18h], 7
0x1400533c2  jbe     short loc_1400533C9
0x1400533c4  mov     rax, [rsi]
0x1400533c7  jmp     short loc_1400533CC
0x1400533c9  mov     rax, rsi
0x1400533cc  mov     [rsp+68h+var_38], rax
0x1400533d1  mov     [rsp+68h+var_30], rcx
0x1400533d6  lea     r8, [rsp+68h+var_48]
0x1400533db  lea     rdx, [rsp+68h+var_38]
0x1400533e0  mov     rcx, rbp
0x1400533e3  call    ?ClearDataForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@1@Z
0x1400533e8  lea     rcx, [rdi+108h]
0x1400533ef  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1400533f4  lea     rcx, [rdi+80h]; this
0x1400533fb  call    ??1FlowEndpointBase@@UEAA@XZ; FlowEndpointBase::~FlowEndpointBase(void)
0x140053400  mov     rcx, rbp
0x140053403  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140053408  mov     rcx, [rdi+68h]; this
0x14005340c  test    rcx, rcx
0x14005340f  jz      short loc_140053416
0x140053411  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140053416  lea     rcx, [rdi+48h]
0x14005341a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005341f  mov     rcx, rbx
0x140053422  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140053427  mov     rcx, rsi
0x14005342a  add     rsp, 48h
0x14005342e  pop     rdi
0x14005342f  pop     rsi
0x140053430  pop     rbp
0x140053431  pop     rbx
0x140053432  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140053437  mov     rcx, [rsp+68h]; this
0x14005343c  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Sing"...
0x140053443  mov     edx, 136h; void *
0x140053448  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

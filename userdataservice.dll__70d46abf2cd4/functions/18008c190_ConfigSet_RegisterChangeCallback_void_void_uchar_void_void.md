# ConfigSet::RegisterChangeCallback(void (*)(void *,uchar),void *,void * *)

- ea: `0x18008c190`
- end: `0x18008c381`
- name: `?RegisterChangeCallback@ConfigSet@@QEAAJP6AXPEAXE@Z0PEAPEAX@Z`
- size: `497`
- prototype: `int(ConfigSet *__hidden this, void (*)(void *, unsigned __int8), void *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1801038b8`

## callees

- `0x1800303cc`
- `0x180030948`
- `0x18008c190`
- `0x18008cab4`
- `0x1800977c4`
- `0x1800c99ac`
- `0x1800c9a54`
- `0x1800cedc4`
- `0x180102748`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c2b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c2b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c2f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c30d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c2f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c30d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008c1c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008c1c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c24d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c24d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18008c243`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18008c243`

## string_xrefs

- `0x18008c1fd`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18008c2db`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18008c341`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigSet::RegisterChangeCallback(
        ConfigSet *this,
        void (*a2)(void *, unsigned __int8),
        void *a3,
        void **a4)
{
  HANDLE EventW; // rax
  HANDLE v8; // rbx
  signed int LastError; // eax
  unsigned int v10; // ebx
  void **v11; // rax
  signed int v12; // eax
  _QWORD *v13; // rax
  void *v14; // rcx
  void *v15; // rbx
  __int64 (__fastcall ***v16)(_QWORD, __int64); // rcx
  HANDLE hObject; // [rsp+30h] [rbp-30h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, __int64); // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  void *v21; // [rsp+48h] [rbp-18h] BYREF

  hObject = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset(&hObject, EventW);
  v8 = hObject;
  if ( !hObject )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent_39(v10);
    goto LABEL_22;
  }
  v21 = 0;
  v11 = tlx::replace<void *,unsigned long (*)(void *),&private: static unsigned long ConfigSet::UnregisterWaitAndBlock(void *),0>(&v21);
  if ( !RegisterWaitForSingleObject(v11, v8, MessagingSettings::_ConfigSetChangeCallback, a3, 0xFFFFFFFF, 0) )
  {
    v12 = GetLastError();
    v10 = v12;
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_19;
  }
  v13 = operator new(0x18u);
  if ( !v13 )
  {
    v10 = -2147024882;
LABEL_19:
    Log_HREvent_39(v10);
LABEL_20:
    if ( v21 )
      ConfigSet::UnregisterWaitAndBlock(v21);
    goto LABEL_22;
  }
  v14 = v21;
  *v13 = &ConfigSet::ConfigSetListener::`vftable';
  v13[1] = v14;
  v13[2] = v8;
  v15 = v21;
  v21 = 0;
  v19 = (__int64 (__fastcall ***)(_QWORD, __int64))v13;
  hObject = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  utl::list<tlx::auto_ptr<ConfigSet::ConfigSetListener,&void tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)>,utl::allocator<tlx::auto_ptr<ConfigSet::ConfigSetListener,&void tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)>>>::emplace<tlx::auto_ptr<ConfigSet::ConfigSetListener,&void tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)>,0>(
    (__int64)this + 48,
    &v20,
    (__int64)this + 48,
    (__int64 *)&v19);
  if ( !v20 )
  {
    v10 = -2147024882;
    Log_HREvent_39(-2147024882);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( v19 )
      tlx::_delete<ConfigSet::ConfigSetListener>(v19);
    goto LABEL_20;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v16 = v19;
  *a4 = v15;
  if ( v16 )
    tlx::_delete<ConfigSet::ConfigSetListener>(v16);
  if ( v21 )
    ConfigSet::UnregisterWaitAndBlock(v21);
  v10 = 0;
LABEL_22:
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&hObject);
  return v10;
}

```

## disassembly

```asm
0x18008c190  push    rbp
0x18008c192  push    rbx
0x18008c193  push    rsi
0x18008c194  push    rdi
0x18008c195  push    r14
0x18008c197  mov     rbp, rsp
0x18008c19a  sub     rsp, 60h
0x18008c19e  mov     rax, cs:__security_cookie
0x18008c1a5  xor     rax, rsp
0x18008c1a8  mov     [rbp+var_10], rax
0x18008c1ac  mov     r14, r9
0x18008c1af  mov     [rbp+hObject], 0
0x18008c1b7  mov     rdi, r8
0x18008c1ba  mov     rsi, rcx
0x18008c1bd  xor     r9d, r9d; lpName
0x18008c1c0  xor     r8d, r8d; bInitialState
0x18008c1c3  xor     ecx, ecx; lpEventAttributes
0x18008c1c5  xor     edx, edx; bManualReset
0x18008c1c7  call    cs:__imp_CreateEventW
0x18008c1cd  mov     rdx, rax
0x18008c1d0  lea     rcx, [rbp+hObject]
0x18008c1d4  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x18008c1d9  mov     rbx, [rbp+hObject]
0x18008c1dd  test    rbx, rbx
0x18008c1e0  jnz     short loc_18008C212
0x18008c1e2  call    cs:__imp_GetLastError
0x18008c1e8  mov     ebx, eax
0x18008c1ea  test    eax, eax
0x18008c1ec  jle     short loc_18008C1F7
0x18008c1ee  movzx   ebx, ax
0x18008c1f1  or      ebx, 80070000h
0x18008c1f7  mov     r9d, 472h
0x18008c1fd  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18008c204  xor     edx, edx
0x18008c206  mov     ecx, ebx; int
0x18008c208  call    Log_HREvent_39
0x18008c20d  jmp     loc_18008C35F
0x18008c212  lea     rcx, [rbp+var_18]
0x18008c216  mov     [rbp+var_18], 0
0x18008c21e  call    ??$replace@PEAXP6AKPEAX@Z$1?UnregisterWaitAndBlock@ConfigSet@@CAK0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AKPEAX@Z$1?UnregisterWaitAndBlock@ConfigSet@@CAK0@Z$0A@@0@@Z; tlx::replace<void *,ulong (*)(void *),&ConfigSet::UnregisterWaitAndBlock(void *),0>(tlx::auto_xxx<void *,ulong (*)(void *),&ConfigSet::UnregisterWaitAndBlock(void *),0> &)
0x18008c223  mov     r9, rdi; Context
0x18008c226  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18008c22e  lea     r8, ?_ConfigSetChangeCallback@MessagingSettings@@CAXPEAXE@Z; Callback
0x18008c235  mov     [rsp+60h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18008c23d  mov     rdx, rbx; hObject
0x18008c240  mov     rcx, rax; phNewWaitObject
0x18008c243  call    cs:__imp_RegisterWaitForSingleObject
0x18008c249  test    eax, eax
0x18008c24b  jnz     short loc_18008C26D
0x18008c24d  call    cs:__imp_GetLastError
0x18008c253  mov     ebx, eax
0x18008c255  test    eax, eax
0x18008c257  jle     short loc_18008C262
0x18008c259  movzx   ebx, ax
0x18008c25c  or      ebx, 80070000h
0x18008c262  mov     r9d, 476h
0x18008c268  jmp     loc_18008C341
0x18008c26d  mov     ecx, 18h; Size
0x18008c272  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008c277  test    rax, rax
0x18008c27a  jz      loc_18008C336
0x18008c280  mov     rcx, [rbp+var_18]
0x18008c284  lea     rdx, ??_7ConfigSetListener@ConfigSet@@6B@; const ConfigSet::ConfigSetListener::`vftable'
0x18008c28b  mov     [rax], rdx
0x18008c28e  lea     rdi, [rsi+8]
0x18008c292  mov     [rax+8], rcx
0x18008c296  mov     rcx, rdi; lpCriticalSection
0x18008c299  mov     [rax+10h], rbx
0x18008c29d  mov     rbx, [rbp+var_18]
0x18008c2a1  mov     [rbp+var_18], 0
0x18008c2a9  mov     [rbp+var_28], rax
0x18008c2ad  mov     [rbp+hObject], 0
0x18008c2b5  call    cs:__imp_EnterCriticalSection
0x18008c2bb  lea     rcx, [rsi+30h]
0x18008c2bf  mov     r8, rcx
0x18008c2c2  lea     r9, [rbp+var_28]
0x18008c2c6  lea     rdx, [rbp+var_20]
0x18008c2ca  call    ??$emplace@V?$auto_ptr@VConfigSetListener@ConfigSet@@$1??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAV12@@Z@tlx@@$0A@@?$list@V?$auto_ptr@VConfigSetListener@ConfigSet@@$1??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAV12@@Z@tlx@@V?$allocator@V?$auto_ptr@VConfigSetListener@ConfigSet@@$1??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAV12@@Z@tlx@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@V?$auto_ptr@VConfigSetListener@ConfigSet@@$1??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAV12@@Z@tlx@@@utl@@V?$auto_ptr@VConfigSetListener@ConfigSet@@$1??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAV12@@Z@tlx@@@1@V?$_DlistConstIt@U?$_DlistNode@V?$auto_ptr@VConfigSetListener@ConfigSet@@$1??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAV12@@Z@tlx@@@utl@@V?$auto_ptr@VConfigSetListener@ConfigSet@@$1??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAV12@@Z@tlx@@@1@$$QEAV?$auto_ptr@VConfigSetListener@ConfigSet@@$1??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAV12@@Z@tlx@@@Z; utl::list<tlx::auto_ptr<ConfigSet::ConfigSetListener,&tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)>,utl::allocator<tlx::auto_ptr<ConfigSet::ConfigSetListener,&tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)>>>::emplace<tlx::auto_ptr<ConfigSet::ConfigSetListener,&tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)>,0>(utl::_DlistConstIt<utl::_DlistNode<tlx::auto_ptr<ConfigSet::ConfigSetListener,&tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)>>,tlx::auto_ptr<ConfigSet::ConfigSetListener,&tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)>>,tlx::auto_ptr<ConfigSet::ConfigSetListener,&tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)> &&)
0x18008c2cf  cmp     [rbp+var_20], 0
0x18008c2d4  jnz     short loc_18008C30A
0x18008c2d6  mov     ebx, 8007000Eh
0x18008c2db  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18008c2e2  mov     ecx, ebx; int
0x18008c2e4  mov     r9d, 484h
0x18008c2ea  xor     edx, edx
0x18008c2ec  call    Log_HREvent_39
0x18008c2f1  mov     rcx, rdi; lpCriticalSection
0x18008c2f4  call    cs:__imp_LeaveCriticalSection
0x18008c2fa  mov     rcx, [rbp+var_28]
0x18008c2fe  test    rcx, rcx
0x18008c301  jz      short loc_18008C351
0x18008c303  call    ??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAVConfigSetListener@ConfigSet@@@Z; tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)
0x18008c308  jmp     short loc_18008C351
0x18008c30a  mov     rcx, rdi; lpCriticalSection
0x18008c30d  call    cs:__imp_LeaveCriticalSection
0x18008c313  mov     rcx, [rbp+var_28]
0x18008c317  mov     [r14], rbx
0x18008c31a  test    rcx, rcx
0x18008c31d  jz      short loc_18008C324
0x18008c31f  call    ??$_delete@VConfigSetListener@ConfigSet@@@tlx@@YAXPEAVConfigSetListener@ConfigSet@@@Z; tlx::_delete<ConfigSet::ConfigSetListener>(ConfigSet::ConfigSetListener *)
0x18008c324  mov     rcx, [rbp+var_18]; void *
0x18008c328  test    rcx, rcx
0x18008c32b  jz      short loc_18008C332
0x18008c32d  call    ?UnregisterWaitAndBlock@ConfigSet@@CAKPEAX@Z; ConfigSet::UnregisterWaitAndBlock(void *)
0x18008c332  xor     ebx, ebx
0x18008c334  jmp     short loc_18008C35F
0x18008c336  mov     r9d, 47Ah
0x18008c33c  mov     ebx, 8007000Eh
0x18008c341  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18008c348  xor     edx, edx
0x18008c34a  mov     ecx, ebx; int
0x18008c34c  call    Log_HREvent_39
0x18008c351  mov     rcx, [rbp+var_18]; void *
0x18008c355  test    rcx, rcx
0x18008c358  jz      short loc_18008C35F
0x18008c35a  call    ?UnregisterWaitAndBlock@ConfigSet@@CAKPEAX@Z; ConfigSet::UnregisterWaitAndBlock(void *)
0x18008c35f  lea     rcx, [rbp+hObject]
0x18008c363  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18008c368  mov     eax, ebx
0x18008c36a  mov     rcx, [rbp+var_10]
0x18008c36e  xor     rcx, rsp; StackCookie
0x18008c371  call    __security_check_cookie
0x18008c376  add     rsp, 60h
0x18008c37a  pop     r14
0x18008c37c  pop     rdi
0x18008c37d  pop     rsi
0x18008c37e  pop     rbx
0x18008c37f  pop     rbp
0x18008c380  retn
```

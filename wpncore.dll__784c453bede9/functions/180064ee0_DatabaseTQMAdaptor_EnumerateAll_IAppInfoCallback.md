# DatabaseTQMAdaptor::EnumerateAll(IAppInfoCallback *)

- ea: `0x180064ee0`
- end: `0x18006521e`
- name: `?EnumerateAll@DatabaseTQMAdaptor@@UEAAJPEAVIAppInfoCallback@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(DatabaseTQMAdaptor *__hidden this, struct IAppInfoCallback *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x180064ee0`
- `0x1800654ec`
- `0x1800b99f0`
- `0x1800ba574`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065061`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065074`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006500a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006506c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006500a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006506c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065138`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DatabaseTQMAdaptor::EnumerateAll(DatabaseTQMAdaptor *this, struct IAppInfoCallback *a2)
{
  __int64 (*v3)(void); // rbx
  int v4; // eax
  int v5; // eax
  const char *v6; // r9
  unsigned int i; // esi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, WpnDatabaseHelpers **); // rbx
  int v10; // eax
  WpnDatabaseHelpers *v11; // r14
  __int64 (__fastcall *v12)(WpnDatabaseHelpers *, LPVOID *); // r15
  void *v13; // rdi
  DWORD LastError; // ebx
  int v15; // eax
  WpnDatabaseHelpers *v16; // r14
  __int64 (__fastcall *v17)(WpnDatabaseHelpers *, LPVOID *); // r15
  void *v18; // rdi
  DWORD v19; // ebx
  int v20; // eax
  unsigned int *v21; // r8
  int SettingTypeFromHandler; // eax
  int v23; // eax
  WpnDatabaseHelpers *v24; // rcx
  __int64 v25; // rcx
  int v27; // [rsp+20h] [rbp-2C8h] BYREF
  WpnDatabaseHelpers *v28; // [rsp+28h] [rbp-2C0h] BYREF
  __int64 v29; // [rsp+30h] [rbp-2B8h] BYREF
  LPVOID v30; // [rsp+38h] [rbp-2B0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-2A8h] BYREF
  _BYTE v32[32]; // [rsp+50h] [rbp-298h] BYREF
  LPVOID v33; // [rsp+70h] [rbp-278h]
  _BYTE v34[544]; // [rsp+80h] [rbp-268h] BYREF
  LPVOID v35; // [rsp+2A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v29 = 0;
  v3 = *(__int64 (**)(void))(**((_QWORD **)this + 3) + 232LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  try
  {
    v4 = v3();
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x416,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v4,
        v27);
    v27 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 32LL))(v29, &v27);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x419,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v5,
        v27);
    for ( i = 0; i < v27; ++i )
    {
      memset_0(v32, 0, 0x258u);
      v28 = 0;
      pv[0] = 0;
      v30 = 0;
      v8 = v29;
      v9 = *(__int64 (__fastcall **)(__int64, _QWORD, WpnDatabaseHelpers **))(*(_QWORD *)v29 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      v10 = v9(v8, i, &v28);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x422,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
          (const char *)(unsigned int)v10,
          v27);
      v11 = v28;
      v12 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, LPVOID *))(*(_QWORD *)v28 + 24LL);
      v13 = pv[0];
      if ( pv[0] )
      {
        LastError = GetLastError();
        CoTaskMemFree(v13);
        SetLastError(LastError);
      }
      pv[0] = 0;
      v15 = v12(v11, pv);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x423,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
          (const char *)(unsigned int)v15,
          v27);
      v33 = pv[0];
      v16 = v28;
      v17 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, LPVOID *))(*(_QWORD *)v28 + 40LL);
      v18 = v30;
      if ( v30 )
      {
        v19 = GetLastError();
        CoTaskMemFree(v18);
        SetLastError(v19);
      }
      v30 = 0;
      v20 = v17(v16, &v30);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x425,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
          (const char *)(unsigned int)v20,
          v27);
      v35 = v30;
      SettingTypeFromHandler = WpnDatabaseHelpers::GetSettingTypeFromHandler(
                                 v28,
                                 (struct INotificationHandler *)v34,
                                 v21);
      if ( SettingTypeFromHandler < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x429,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
          (const char *)(unsigned int)SettingTypeFromHandler,
          v27);
      v23 = (**(__int64 (__fastcall ***)(struct IAppInfoCallback *, _BYTE *))a2)(a2, v32);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x42B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
          (const char *)(unsigned int)v23,
          v27);
      if ( v30 )
        CoTaskMemFree(v30);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      v24 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(WpnDatabaseHelpers *))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
    v25 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x42E,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
                           v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180064ee0  mov     [rsp+arg_10], rbx
0x180064ee5  push    rsi
0x180064ee6  push    rdi
0x180064ee7  push    r12
0x180064ee9  push    r14
0x180064eeb  push    r15
0x180064eed  sub     rsp, 2C0h
0x180064ef4  mov     rax, cs:__security_cookie
0x180064efb  xor     rax, rsp
0x180064efe  mov     [rsp+2E8h+var_38], rax
0x180064f06  mov     r12, rdx
0x180064f09  mov     [rsp+2E8h+var_2B8], 0
0x180064f12  mov     rdi, [rcx+18h]
0x180064f16  mov     rax, [rdi]
0x180064f19  mov     rbx, [rax+0E8h]
0x180064f20  lea     rcx, [rsp+2E8h+var_2B8]
0x180064f25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064f2a  lea     rdx, [rsp+2E8h+var_2B8]
0x180064f2f  mov     rcx, rdi
0x180064f32  mov     rax, rbx
0x180064f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f3a  mov     rcx, [rsp+2E8h]; this
0x180064f42  test    eax, eax
0x180064f44  js      loc_1800651A5
0x180064f4a  mov     [rsp+2E8h+var_2C8], 0; int
0x180064f52  mov     rcx, [rsp+2E8h+var_2B8]
0x180064f57  mov     rax, [rcx]
0x180064f5a  lea     rdx, [rsp+2E8h+var_2C8]
0x180064f5f  mov     rax, [rax+20h]
0x180064f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f68  mov     rcx, [rsp+2E8h]; this
0x180064f70  test    eax, eax
0x180064f72  js      loc_1800651B9
0x180064f78  xor     esi, esi
0x180064f7a  cmp     esi, [rsp+2E8h+var_2C8]
0x180064f7e  jnb     loc_1800651CE
0x180064f84  xor     edx, edx; Val
0x180064f86  mov     r8d, 258h; Size
0x180064f8c  lea     rcx, [rsp+2E8h+var_298]; void *
0x180064f91  call    memset_0
0x180064f96  mov     [rsp+2E8h+var_2C0], 0
0x180064f9f  mov     [rsp+2E8h+pv], 0
0x180064fa8  mov     [rsp+2E8h+var_2B0], 0
0x180064fb1  mov     rdi, [rsp+2E8h+var_2B8]
0x180064fb6  mov     rax, [rdi]
0x180064fb9  mov     rbx, [rax+18h]
0x180064fbd  lea     rcx, [rsp+2E8h+var_2C0]
0x180064fc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064fc7  lea     r8, [rsp+2E8h+var_2C0]
0x180064fcc  mov     edx, esi
0x180064fce  mov     rcx, rdi
0x180064fd1  mov     rax, rbx
0x180064fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064fd9  mov     rcx, [rsp+2E8h]; this
0x180064fe1  test    eax, eax
0x180064fe3  js      loc_180065140
0x180064fe9  mov     r14, [rsp+2E8h+var_2C0]
0x180064fee  mov     rax, [r14]
0x180064ff1  mov     r15, [rax+18h]
0x180064ff5  mov     rdi, [rsp+2E8h+pv]
0x180064ffa  test    rdi, rdi
0x180064ffd  jz      short loc_180065018
0x180064fff  call    cs:__imp_GetLastError
0x180065005  mov     ebx, eax
0x180065007  mov     rcx, rdi; pv
0x18006500a  call    cs:__imp_CoTaskMemFree
0x180065010  mov     ecx, ebx; dwErrCode
0x180065012  call    cs:__imp_SetLastError
0x180065018  mov     [rsp+2E8h+pv], 0
0x180065021  lea     rdx, [rsp+2E8h+pv]
0x180065026  mov     rcx, r14
0x180065029  mov     rax, r15
0x18006502c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065031  mov     rcx, [rsp+2E8h]; this
0x180065039  test    eax, eax
0x18006503b  js      loc_180065154
0x180065041  mov     rax, [rsp+2E8h+pv]
0x180065046  mov     [rsp+2E8h+var_278], rax
0x18006504b  mov     r14, [rsp+2E8h+var_2C0]
0x180065050  mov     rax, [r14]
0x180065053  mov     r15, [rax+28h]
0x180065057  mov     rdi, [rsp+2E8h+var_2B0]
0x18006505c  test    rdi, rdi
0x18006505f  jz      short loc_18006507A
0x180065061  call    cs:__imp_GetLastError
0x180065067  mov     ebx, eax
0x180065069  mov     rcx, rdi; pv
0x18006506c  call    cs:__imp_CoTaskMemFree
0x180065072  mov     ecx, ebx; dwErrCode
0x180065074  call    cs:__imp_SetLastError
0x18006507a  mov     [rsp+2E8h+var_2B0], 0
0x180065083  lea     rdx, [rsp+2E8h+var_2B0]
0x180065088  mov     rcx, r14
0x18006508b  mov     rax, r15
0x18006508e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065093  mov     rcx, [rsp+2E8h]; this
0x18006509b  test    eax, eax
0x18006509d  js      loc_180065168
0x1800650a3  mov     rax, [rsp+2E8h+var_2B0]
0x1800650a8  mov     [rsp+2E8h+var_48], rax
0x1800650b0  lea     rdx, [rsp+2E8h+var_268]; struct INotificationHandler *
0x1800650b8  mov     rcx, [rsp+2E8h+var_2C0]; this
0x1800650bd  call    ?GetSettingTypeFromHandler@WpnDatabaseHelpers@@YAJPEAUINotificationHandler@@PEAK@Z; WpnDatabaseHelpers::GetSettingTypeFromHandler(INotificationHandler *,ulong *)
0x1800650c2  mov     rcx, [rsp+2E8h]; this
0x1800650ca  test    eax, eax
0x1800650cc  js      loc_18006517C
0x1800650d2  mov     rax, [r12]
0x1800650d6  lea     rdx, [rsp+2E8h+var_298]
0x1800650db  mov     rcx, r12
0x1800650de  mov     rax, [rax]
0x1800650e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650e6  mov     rcx, [rsp+2E8h]; this
0x1800650ee  test    eax, eax
0x1800650f0  js      loc_180065190
0x1800650f6  mov     rcx, [rsp+2E8h+var_2B0]; pv
0x1800650fb  test    rcx, rcx
0x1800650fe  jz      short loc_180065107
0x180065100  call    cs:__imp_CoTaskMemFree
0x180065106  nop
0x180065107  mov     rcx, [rsp+2E8h+pv]; pv
0x18006510c  test    rcx, rcx
0x18006510f  jnz     short loc_180065138
0x180065111  mov     rcx, [rsp+2E8h+var_2C0]
0x180065116  test    rcx, rcx
0x180065119  jz      short loc_180065131
0x18006511b  mov     [rsp+2E8h+var_2C0], 0
0x180065124  mov     rax, [rcx]
0x180065127  mov     rax, [rax+10h]
0x18006512b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065130  nop
0x180065131  inc     esi
0x180065133  jmp     loc_180064F7A
0x180065138  call    cs:__imp_CoTaskMemFree
0x18006513e  jmp     short loc_180065111
0x180065140  mov     r9d, eax; char *
0x180065143  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006514a  mov     edx, 422h; void *
0x18006514f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065154  mov     r9d, eax; char *
0x180065157  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006515e  mov     edx, 423h; void *
0x180065163  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065168  mov     r9d, eax; char *
0x18006516b  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180065172  mov     edx, 425h; void *
0x180065177  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006517c  mov     r9d, eax; char *
0x18006517f  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180065186  mov     edx, 429h; void *
0x18006518b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065190  mov     r9d, eax; char *
0x180065193  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006519a  mov     edx, 42Bh; void *
0x18006519f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800651a5  mov     r9d, eax; char *
0x1800651a8  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800651af  mov     edx, 416h; void *
0x1800651b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800651b9  mov     r9d, eax; char *
0x1800651bc  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800651c3  mov     edx, 419h; void *
0x1800651c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800651ce  mov     rcx, [rsp+2E8h+var_2B8]
0x1800651d3  test    rcx, rcx
0x1800651d6  jz      short loc_1800651EE
0x1800651d8  mov     [rsp+2E8h+var_2B8], 0
0x1800651e1  mov     rax, [rcx]
0x1800651e4  mov     rax, [rax+10h]
0x1800651e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651ed  nop
0x1800651ee  xor     eax, eax
0x1800651f0  mov     rcx, [rsp+2E8h+var_38]
0x1800651f8  xor     rcx, rsp; StackCookie
0x1800651fb  call    __security_check_cookie
0x180065200  mov     rbx, [rsp+2E8h+arg_10]
0x180065208  add     rsp, 2C0h
0x18006520f  pop     r15
0x180065211  pop     r14
0x180065213  pop     r12
0x180065215  pop     rdi
0x180065216  pop     rsi
0x180065217  retn
0x180065218  mov     eax, [rsp+2E8h+var_2C8]
0x18006521c  jmp     short loc_1800651F0
```

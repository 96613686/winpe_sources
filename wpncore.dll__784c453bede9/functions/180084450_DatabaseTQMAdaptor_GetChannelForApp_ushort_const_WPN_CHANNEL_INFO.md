# DatabaseTQMAdaptor::GetChannelForApp(ushort const *,WPN_CHANNEL_INFO *)

- ea: `0x180084450`
- end: `0x180084687`
- name: `?GetChannelForApp@DatabaseTQMAdaptor@@UEAAJPEBGPEAUWPN_CHANNEL_INFO@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(DatabaseTQMAdaptor *__hidden this, const unsigned __int16 *, struct WPN_CHANNEL_INFO *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x180084450`
- `0x1800f2460`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18008450a`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180084580`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18008450a`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180084580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084639`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008464a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084639`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008464a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DatabaseTQMAdaptor::GetChannelForApp(
        DatabaseTQMAdaptor *this,
        const unsigned __int16 *a2,
        struct WPN_CHANNEL_INFO *a3)
{
  __int64 (*v4)(void); // rbx
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // eax
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  __int64 *v15; // rcx
  __int64 result; // rax
  char *Source; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 *v19; // [rsp+50h] [rbp+8h] BYREF
  char *v20; // [rsp+68h] [rbp+20h] BYREF

  v19 = 0;
  v4 = *(__int64 (**)(void))(**((_QWORD **)this + 2) + 272LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  try
  {
    v5 = v4();
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x462,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v5,
        (int)Source);
    Source = 0;
    v6 = *v19;
    Source = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, char **))(v6 + 32))(v19, &Source);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x465,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v7,
        (int)Source);
    v8 = strcpy_s((char *)a3 + 2072, 0x41u, Source);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x466,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)v8,
        (unsigned int)Source);
    v20 = 0;
    v9 = *v19;
    v20 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, char **))(v9 + 40))(v19, &v20);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x469,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v10,
        (int)Source);
    v11 = strcpy_s((char *)a3 + 16, 0x801u, v20);
    if ( v11 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x46A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)v11,
        (unsigned int)Source);
    v12 = (*(__int64 (__fastcall **)(__int64 *, struct WPN_CHANNEL_INFO *))(*v19 + 56))(v19, a3);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x46C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v12,
        (int)Source);
    v13 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v19 + 48))(v19, (char *)a3 + 8);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x46D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
        (const char *)(unsigned int)v13,
        (int)Source);
    *(_QWORD *)a3 = *(unsigned int *)a3;
    *((_QWORD *)a3 + 1) = *((unsigned int *)a3 + 2);
    if ( v20 )
      CoTaskMemFree(v20);
    if ( Source )
      CoTaskMemFree(Source);
    v15 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x472,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x180084450  mov     [rsp+arg_8], rbx
0x180084455  push    rsi
0x180084456  push    rdi
0x180084457  push    r14
0x180084459  sub     rsp, 30h
0x18008445d  mov     rsi, r8
0x180084460  mov     r14, rdx
0x180084463  mov     [rsp+48h+arg_0], 0
0x18008446c  mov     rdi, [rcx+10h]
0x180084470  mov     rax, [rdi]
0x180084473  mov     rbx, [rax+110h]
0x18008447a  lea     rcx, [rsp+48h+arg_0]
0x18008447f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180084484  lea     r8, [rsp+48h+arg_0]
0x180084489  mov     rdx, r14
0x18008448c  mov     rcx, rdi
0x18008448f  mov     rax, rbx
0x180084492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084497  mov     rcx, [rsp+48h]; this
0x18008449c  test    eax, eax
0x18008449e  jns     short loc_1800844B4
0x1800844a0  mov     r9d, eax; char *
0x1800844a3  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800844aa  mov     edx, 462h; void *
0x1800844af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800844b4  mov     [rsp+48h+Source], 0
0x1800844bd  mov     rcx, [rsp+48h+arg_0]
0x1800844c2  mov     rax, [rcx]
0x1800844c5  mov     [rsp+48h+Source], 0; int
0x1800844ce  lea     rdx, [rsp+48h+Source]
0x1800844d3  mov     rax, [rax+20h]
0x1800844d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800844dc  mov     rcx, [rsp+48h]; this
0x1800844e1  test    eax, eax
0x1800844e3  jns     short loc_1800844F9
0x1800844e5  mov     r9d, eax; char *
0x1800844e8  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800844ef  mov     edx, 465h; void *
0x1800844f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800844f9  lea     rcx, [rsi+818h]; Destination
0x180084500  mov     r8, [rsp+48h+Source]; Source
0x180084505  mov     edx, 41h ; 'A'; SizeInBytes
0x18008450a  call    cs:__imp_strcpy_s
0x180084510  mov     rcx, [rsp+48h]; this
0x180084515  test    eax, eax
0x180084517  jz      short loc_18008452D
0x180084519  mov     r9d, eax; char *
0x18008451c  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084523  mov     edx, 466h; void *
0x180084528  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18008452d  mov     [rsp+48h+arg_18], 0
0x180084536  mov     rcx, [rsp+48h+arg_0]
0x18008453b  mov     rax, [rcx]
0x18008453e  mov     [rsp+48h+arg_18], 0
0x180084547  lea     rdx, [rsp+48h+arg_18]
0x18008454c  mov     rax, [rax+28h]
0x180084550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084555  mov     rcx, [rsp+48h]; this
0x18008455a  test    eax, eax
0x18008455c  jns     short loc_180084572
0x18008455e  mov     r9d, eax; char *
0x180084561  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084568  mov     edx, 469h; void *
0x18008456d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084572  lea     rcx, [rsi+10h]; Destination
0x180084576  mov     r8, [rsp+48h+arg_18]; Source
0x18008457b  mov     edx, 801h; SizeInBytes
0x180084580  call    cs:__imp_strcpy_s
0x180084586  mov     rcx, [rsp+48h]; this
0x18008458b  test    eax, eax
0x18008458d  jz      short loc_1800845A3
0x18008458f  mov     r9d, eax; char *
0x180084592  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084599  mov     edx, 46Ah; void *
0x18008459e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800845a3  mov     rcx, [rsp+48h+arg_0]
0x1800845a8  mov     rax, [rcx]
0x1800845ab  mov     rdx, rsi
0x1800845ae  mov     rax, [rax+38h]
0x1800845b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845b7  mov     rcx, [rsp+48h]; this
0x1800845bc  test    eax, eax
0x1800845be  jns     short loc_1800845D4
0x1800845c0  mov     r9d, eax; char *
0x1800845c3  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800845ca  mov     edx, 46Ch; void *
0x1800845cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800845d4  mov     rcx, [rsp+48h+arg_0]
0x1800845d9  lea     rbx, [rsi+8]
0x1800845dd  mov     rax, [rcx]
0x1800845e0  mov     rdx, rbx
0x1800845e3  mov     rax, [rax+30h]
0x1800845e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845ec  mov     rcx, [rsp+48h]; this
0x1800845f1  test    eax, eax
0x1800845f3  jns     short loc_180084609
0x1800845f5  mov     r9d, eax; char *
0x1800845f8  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800845ff  mov     edx, 46Dh; void *
0x180084604  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084609  mov     rcx, [rsi]
0x18008460c  mov     rdx, 0FFFFFFFF00000000h
0x180084616  and     rcx, rdx
0x180084619  mov     eax, [rsi]
0x18008461b  or      rcx, rax
0x18008461e  mov     [rsi], rcx
0x180084621  mov     rcx, [rbx]
0x180084624  and     rcx, rdx
0x180084627  mov     eax, [rbx]
0x180084629  or      rcx, rax
0x18008462c  mov     [rbx], rcx
0x18008462f  mov     rcx, [rsp+48h+arg_18]; pv
0x180084634  test    rcx, rcx
0x180084637  jz      short loc_180084640
0x180084639  call    cs:__imp_CoTaskMemFree
0x18008463f  nop
0x180084640  mov     rcx, [rsp+48h+Source]; pv
0x180084645  test    rcx, rcx
0x180084648  jz      short loc_180084651
0x18008464a  call    cs:__imp_CoTaskMemFree
0x180084650  nop
0x180084651  mov     rcx, [rsp+48h+arg_0]
0x180084656  test    rcx, rcx
0x180084659  jz      short loc_180084671
0x18008465b  mov     [rsp+48h+arg_0], 0
0x180084664  mov     rax, [rcx]
0x180084667  mov     rax, [rax+10h]
0x18008466b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084670  nop
0x180084671  xor     eax, eax
0x180084673  jmp     short loc_180084679
0x180084675  mov     eax, dword ptr [rsp+48h+arg_0]
0x180084679  mov     rbx, [rsp+48h+arg_8]
0x18008467e  add     rsp, 30h
0x180084682  pop     r14
0x180084684  pop     rdi
0x180084685  pop     rsi
0x180084686  retn
```

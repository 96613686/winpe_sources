# DoDeleteSubscriptionItem(_GUID const *,int)

- ea: `0x18001913c`
- end: `0x180019395`
- name: `?DoDeleteSubscriptionItem@@YAJPEFBU_GUID@@H@Z`
- size: `601`
- prototype: `__int64 __fastcall(const struct _GUID *, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b880`
- `0x180018a40`
- `0x180018cf0`
- `0x180018d98`
- `0x180019084`

## callees

- `0x18001913c`
- `0x180019858`
- `0x180019ae0`
- `0x18001c8fc`
- `0x180029236`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!SHDeleteKeyW` at `0x18001935b`
- `SHLWAPI!SHDeleteKeyW` at `0x18001935b`
- `ole32!CoCreateInstance` at `0x1800191c2`
- `ole32!CoCreateInstance` at `0x18001928c`
- `ole32!CoCreateInstance` at `0x180019310`
- `ole32!CoCreateInstance` at `0x1800191c2`
- `ole32!CoCreateInstance` at `0x18001928c`
- `ole32!CoCreateInstance` at `0x180019310`

## pseudocode

```c
__int64 __fastcall DoDeleteSubscriptionItem(const struct _GUID *a1, int a2, unsigned int a3)
{
  struct _GUID *v3; // rbx
  struct ISubscriptionItem *v5; // rdi
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  struct ISubscriptionItem *v7; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v8; // [rsp+40h] [rbp-C0h] BYREF
  int v9; // [rsp+50h] [rbp-B0h] BYREF
  __int128 Buf2; // [rsp+54h] [rbp-ACh] BYREF
  IID rclsid; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v12; // [rsp+74h] [rbp-8Ch]
  WCHAR pszSubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  v8 = 0;
  if ( a1 )
    v8 = (__int128)*a1;
  v3 = (struct _GUID *)((unsigned __int64)&v8 & ((unsigned __int128)-(__int128)(unsigned __int64)a1 >> 64));
  if ( !v3 )
    return 2147942487LL;
  if ( a2 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_SubscriptionThrottler, 0, 5u, &IID_ISubscriptionThrottler, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, __int64, struct _GUID *))(*(_QWORD *)ppv + 32LL))(ppv, 1, v3);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  if ( !ItemKeyNameFromCookie(v3, pszSubKey, a3) )
    return 2147500037LL;
  v7 = 0;
  if ( (int)SubscriptionItemFromCookie(0, v3, &v7) >= 0 )
  {
    v5 = v7;
    v9 = 44;
    v12 = 0;
    Buf2 = 0;
    rclsid = 0;
    if ( ((int (__fastcall *)(struct ISubscriptionItem *, int *))v7->lpVtbl->GetSubscriptionItemInfo)(v7, &v9) >= 0 )
    {
      ppv = 0;
      if ( CoCreateInstance((const IID *const)rclsid.Data4, 0, 1u, &IID_ISubscriptionAgentControl, &ppv) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, struct ISubscriptionItem *, __int64))(*(_QWORD *)ppv + 56LL))(ppv, v5, 1);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      FireSubscriptionEvent(2u, v3);
      if ( memcmp_0(&GUID_NULL, (char *)&Buf2 + 8, 0x10u) )
      {
        v7 = 0;
        if ( CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, (LPVOID *)&v7) >= 0 )
        {
          ((void (__fastcall *)(struct ISubscriptionItem *, char *))v7->lpVtbl->ReadProperties)(v7, (char *)&Buf2 + 8);
          ((void (__fastcall *)(struct ISubscriptionItem *))v7->lpVtbl->Release)(v7);
        }
      }
    }
    ((void (__fastcall *)(struct ISubscriptionItem *))v5->lpVtbl->Release)(v5);
  }
  return SHDeleteKeyW(HKEY_CURRENT_USER, pszSubKey) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18001913c  mov     [rsp-8+arg_8], rbx
0x180019141  mov     [rsp-8+arg_10], rdi
0x180019146  push    rbp
0x180019147  lea     rbp, [rsp-1A0h]
0x18001914f  sub     rsp, 2A0h
0x180019156  mov     rax, cs:__security_cookie
0x18001915d  xor     rax, rsp
0x180019160  mov     [rbp+1A0h+var_10], rax
0x180019167  xorps   xmm0, xmm0
0x18001916a  movups  [rsp+2A0h+var_260], xmm0
0x18001916f  test    rcx, rcx
0x180019172  jz      short loc_18001917D
0x180019174  movups  xmm0, xmmword ptr [rcx]
0x180019177  movdqu  [rsp+2A0h+var_260], xmm0
0x18001917d  neg     rcx
0x180019180  lea     rax, [rsp+2A0h+var_260]
0x180019185  sbb     rbx, rbx
0x180019188  and     rbx, rax
0x18001918b  jnz     short loc_180019197
0x18001918d  mov     eax, 80070057h
0x180019192  jmp     loc_180019371
0x180019197  test    edx, edx
0x180019199  jz      short loc_1800191F6
0x18001919b  xor     edx, edx; pUnkOuter
0x18001919d  mov     [rsp+2A0h+var_270], 0
0x1800191a6  lea     rax, [rsp+2A0h+var_270]
0x1800191ab  lea     r9, IID_ISubscriptionThrottler; riid
0x1800191b2  mov     [rsp+2A0h+ppv], rax; ppv
0x1800191b7  lea     rcx, CLSID_SubscriptionThrottler; rclsid
0x1800191be  lea     r8d, [rdx+5]; dwClsContext
0x1800191c2  call    cs:__imp_CoCreateInstance
0x1800191c8  test    eax, eax
0x1800191ca  js      short loc_1800191F6
0x1800191cc  mov     rcx, [rsp+2A0h+var_270]
0x1800191d1  mov     r8, rbx
0x1800191d4  mov     edx, 1
0x1800191d9  mov     rax, [rcx]
0x1800191dc  mov     rax, [rax+20h]
0x1800191e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191e5  mov     rcx, [rsp+2A0h+var_270]
0x1800191ea  mov     rax, [rcx]
0x1800191ed  mov     rax, [rax+10h]
0x1800191f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191f6  lea     rdx, [rbp+1A0h+pszSubKey]; unsigned __int16 *
0x1800191fa  mov     rcx, rbx; struct _GUID *
0x1800191fd  call    ?ItemKeyNameFromCookie@@YAHPEBU_GUID@@PEAGK@Z; ItemKeyNameFromCookie(_GUID const *,ushort *,ulong)
0x180019202  test    eax, eax
0x180019204  jz      loc_18001936C
0x18001920a  lea     r8, [rsp+2A0h+var_268]; struct ISubscriptionItem **
0x18001920f  mov     [rsp+2A0h+var_268], 0
0x180019218  mov     rdx, rbx; struct _GUID *
0x18001921b  xor     ecx, ecx; int
0x18001921d  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x180019222  test    eax, eax
0x180019224  js      loc_180019350
0x18001922a  mov     rdi, [rsp+2A0h+var_268]
0x18001922f  lea     rdx, [rsp+2A0h+var_250]
0x180019234  xor     eax, eax
0x180019236  mov     [rsp+2A0h+var_250], 2Ch ; ','
0x18001923e  xorps   xmm0, xmm0
0x180019241  mov     [rsp+2A0h+var_22C], rax
0x180019246  movups  [rsp+2A0h+Buf2], xmm0
0x18001924b  mov     rcx, rdi
0x18001924e  movups  xmmword ptr [rsp+2A0h+rclsid.Data1], xmm0
0x180019253  mov     rax, [rdi]
0x180019256  mov     rax, [rax+20h]
0x18001925a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001925f  test    eax, eax
0x180019261  js      loc_180019341
0x180019267  xor     edx, edx; pUnkOuter
0x180019269  mov     [rsp+2A0h+var_270], 0
0x180019272  lea     rax, [rsp+2A0h+var_270]
0x180019277  lea     r9, IID_ISubscriptionAgentControl; riid
0x18001927e  mov     [rsp+2A0h+ppv], rax; ppv
0x180019283  lea     rcx, [rsp+2A0h+rclsid.Data4]; rclsid
0x180019288  lea     r8d, [rdx+1]; dwClsContext
0x18001928c  call    cs:__imp_CoCreateInstance
0x180019292  test    eax, eax
0x180019294  js      short loc_1800192C1
0x180019296  mov     rcx, [rsp+2A0h+var_270]
0x18001929b  mov     r8d, 1
0x1800192a1  mov     rdx, rdi
0x1800192a4  mov     rax, [rcx]
0x1800192a7  mov     rax, [rax+38h]
0x1800192ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192b0  mov     rcx, [rsp+2A0h+var_270]
0x1800192b5  mov     rax, [rcx]
0x1800192b8  mov     rax, [rax+10h]
0x1800192bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192c1  mov     rdx, rbx
0x1800192c4  mov     ecx, 2
0x1800192c9  call    FireSubscriptionEvent
0x1800192ce  mov     r8d, 10h; Size
0x1800192d4  lea     rdx, [rsp+2A0h+Buf2+8]; Buf2
0x1800192d9  lea     rcx, GUID_NULL; Buf1
0x1800192e0  call    memcmp_0
0x1800192e5  test    eax, eax
0x1800192e7  jz      short loc_180019341
0x1800192e9  xor     edx, edx; pUnkOuter
0x1800192eb  mov     [rsp+2A0h+var_268], 0
0x1800192f4  lea     rax, [rsp+2A0h+var_268]
0x1800192f9  lea     r9, IID_ISyncScheduleMgr; riid
0x180019300  mov     [rsp+2A0h+ppv], rax; ppv
0x180019305  lea     rcx, CLSID_SyncMgr; rclsid
0x18001930c  lea     r8d, [rdx+17h]; dwClsContext
0x180019310  call    cs:__imp_CoCreateInstance
0x180019316  test    eax, eax
0x180019318  js      short loc_180019341
0x18001931a  mov     rcx, [rsp+2A0h+var_268]
0x18001931f  lea     rdx, [rsp+2A0h+Buf2+8]
0x180019324  mov     rax, [rcx]
0x180019327  mov     rax, [rax+30h]
0x18001932b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019330  mov     rcx, [rsp+2A0h+var_268]
0x180019335  mov     rax, [rcx]
0x180019338  mov     rax, [rax+10h]
0x18001933c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019341  mov     rax, [rdi]
0x180019344  mov     rcx, rdi
0x180019347  mov     rax, [rax+10h]
0x18001934b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019350  lea     rdx, [rbp+1A0h+pszSubKey]; pszSubKey
0x180019354  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001935b  call    cs:__imp_SHDeleteKeyW
0x180019361  neg     eax
0x180019363  sbb     eax, eax
0x180019365  and     eax, 80004005h
0x18001936a  jmp     short loc_180019371
0x18001936c  mov     eax, 80004005h
0x180019371  mov     rcx, [rbp+1A0h+var_10]
0x180019378  xor     rcx, rsp; StackCookie
0x18001937b  call    __security_check_cookie
0x180019380  lea     r11, [rsp+2A0h+var_s0]
0x180019388  mov     rbx, [r11+18h]
0x18001938c  mov     rdi, [r11+20h]
0x180019390  mov     rsp, r11
0x180019393  pop     rbp
0x180019394  retn
```

# CSubscriptionMgr::CreateSubscription(HWND__ *,ushort const *,ushort const *,ulong,SUBSCRIPTIONTYPE,_tagSubscriptionInfo *)

- ea: `0x180016f80`
- end: `0x1800170c1`
- name: `?CreateSubscription@CSubscriptionMgr@@UEAAJPEAUHWND__@@PEBG1KW4SUBSCRIPTIONTYPE@@PEAU_tagSubscriptionInfo@@@Z`
- size: `321`
- prototype: `int(CSubscriptionMgr *__hidden this, HWND, const unsigned __int16 *, const unsigned __int16 *, unsigned int, enum SUBSCRIPTIONTYPE, struct _tagSubscriptionInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180016e18`
- `0x180016f80`
- `0x1800170c8`
- `0x180017d60`
- `0x18002a010`

## import_xrefs

- `IEFRAME!__imp_SHAddSubscribeFavorite` at `0x180017075`
- `IEFRAME!__imp_SHAddSubscribeFavorite` at `0x180017075`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::CreateSubscription(
        CSubscriptionMgr *this,
        HWND a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        enum SUBSCRIPTIONTYPE a6,
        struct _tagSubscriptionInfo *a7)
{
  int SubscriptionNoSummary; // ebx
  _DWORD v14[18]; // [rsp+40h] [rbp-48h] BYREF

  v14[0] = 0;
  if ( (a5 & 4) != 0 || (a5 & 1) == 0 )
  {
    SubscriptionNoSummary = CSubscriptionMgr::CreateSubscriptionNoSummary(
                              (CSubscriptionMgr *)((char *)this - 16),
                              a2,
                              a3,
                              a4,
                              a5,
                              a6,
                              a7);
    if ( !SubscriptionNoSummary )
      RemoveURLMapping(a3);
  }
  else
  {
    if ( (unsigned int)a6 < SUBSTYPE_DESKTOPURL )
      return (unsigned int)SHAddSubscribeFavorite(a2, a3, a4, a5, a6, a7);
    if ( a6 != SUBSTYPE_DESKTOPURL && a6 != SUBSTYPE_DESKTOPCHANNEL )
      return (unsigned int)CSubscriptionMgr::CreateSubscriptionNoSummary(
                             (CSubscriptionMgr *)((char *)this - 16),
                             a2,
                             a3,
                             a4,
                             a5,
                             a6,
                             a7);
    SubscriptionNoSummary = (*(__int64 (__fastcall **)(CSubscriptionMgr *, unsigned __int16 *, _DWORD *))(*(_QWORD *)this + 48LL))(
                              this,
                              a3,
                              v14);
    if ( SubscriptionNoSummary < 0 || !v14[0] )
      return (unsigned int)CSubscriptionMgr::CreateDesktopSubscription(
                             (CSubscriptionMgr *)((char *)this - 16),
                             a2,
                             a3,
                             a4,
                             a5,
                             a6,
                             a7);
  }
  return (unsigned int)SubscriptionNoSummary;
}

```

## disassembly

```asm
0x180016f80  push    rbx
0x180016f82  push    rbp
0x180016f83  push    rsi
0x180016f84  push    rdi
0x180016f85  push    r12
0x180016f87  push    r14
0x180016f89  push    r15
0x180016f8b  sub     rsp, 50h
0x180016f8f  mov     esi, dword ptr [rsp+88h+arg_20]
0x180016f96  mov     r15, r9
0x180016f99  mov     [rsp+88h+var_48], 0
0x180016fa1  mov     rdi, r8
0x180016fa4  mov     r12, rdx
0x180016fa7  mov     r14, rcx
0x180016faa  test    sil, 4
0x180016fae  jnz     loc_18001707D
0x180016fb4  test    sil, 1
0x180016fb8  jz      loc_18001707D
0x180016fbe  mov     ebp, [rsp+88h+arg_28]
0x180016fc5  mov     ecx, ebp
0x180016fc7  test    ebp, ebp
0x180016fc9  jz      loc_180017058
0x180016fcf  sub     ecx, 1
0x180016fd2  jz      loc_180017058
0x180016fd8  sub     ecx, 1
0x180016fdb  jz      short loc_180017007
0x180016fdd  cmp     ecx, 2
0x180016fe0  jz      short loc_180017007
0x180016fe2  mov     rax, [rsp+88h+arg_30]
0x180016fea  lea     rcx, [r14-10h]; this
0x180016fee  mov     [rsp+88h+var_58], rax; struct _tagSubscriptionInfo *
0x180016ff3  mov     [rsp+88h+var_60], ebp; enum SUBSCRIPTIONTYPE
0x180016ff7  mov     dword ptr [rsp+88h+var_68], esi; char
0x180016ffb  call    ?CreateSubscriptionNoSummary@CSubscriptionMgr@@IEAAJPEAUHWND__@@PEBG1KW4SUBSCRIPTIONTYPE@@PEAU_tagSubscriptionInfo@@@Z; CSubscriptionMgr::CreateSubscriptionNoSummary(HWND__ *,ushort const *,ushort const *,ulong,SUBSCRIPTIONTYPE,_tagSubscriptionInfo *)
0x180017000  mov     ebx, eax
0x180017002  jmp     loc_1800170B0
0x180017007  mov     rax, [r14]
0x18001700a  lea     r8, [rsp+88h+var_48]
0x18001700f  mov     rdx, rdi
0x180017012  mov     rcx, r14
0x180017015  mov     rax, [rax+30h]
0x180017019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001701e  mov     ebx, eax
0x180017020  test    eax, eax
0x180017022  js      short loc_18001702F
0x180017024  cmp     [rsp+88h+var_48], 0
0x180017029  jnz     loc_1800170B0
0x18001702f  mov     rax, [rsp+88h+arg_30]
0x180017037  lea     rcx, [r14-10h]; this
0x18001703b  mov     [rsp+88h+var_58], rax; struct _tagSubscriptionInfo *
0x180017040  mov     r9, r15; unsigned __int16 *
0x180017043  mov     [rsp+88h+var_60], ebp; enum SUBSCRIPTIONTYPE
0x180017047  mov     r8, rdi; unsigned __int16 *
0x18001704a  mov     rdx, r12; HWND
0x18001704d  mov     dword ptr [rsp+88h+var_68], esi; unsigned int
0x180017051  call    ?CreateDesktopSubscription@CSubscriptionMgr@@IEAAJPEAUHWND__@@PEBG1KW4SUBSCRIPTIONTYPE@@PEAU_tagSubscriptionInfo@@@Z; CSubscriptionMgr::CreateDesktopSubscription(HWND__ *,ushort const *,ushort const *,ulong,SUBSCRIPTIONTYPE,_tagSubscriptionInfo *)
0x180017056  jmp     short loc_180017000
0x180017058  mov     rax, [rsp+88h+arg_30]
0x180017060  mov     r9d, esi
0x180017063  mov     qword ptr [rsp+88h+var_60], rax
0x180017068  mov     r8, r15
0x18001706b  mov     rdx, rdi
0x18001706e  mov     dword ptr [rsp+88h+var_68], ebp
0x180017072  mov     rcx, r12
0x180017075  call    cs:__imp_SHAddSubscribeFavorite
0x18001707b  jmp     short loc_180017000
0x18001707d  mov     rax, [rsp+88h+arg_30]
0x180017085  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180017089  mov     [rsp+88h+var_58], rax; struct _tagSubscriptionInfo *
0x18001708e  mov     eax, [rsp+88h+arg_28]
0x180017095  mov     [rsp+88h+var_60], eax; enum SUBSCRIPTIONTYPE
0x180017099  mov     dword ptr [rsp+88h+var_68], esi; char
0x18001709d  call    ?CreateSubscriptionNoSummary@CSubscriptionMgr@@IEAAJPEAUHWND__@@PEBG1KW4SUBSCRIPTIONTYPE@@PEAU_tagSubscriptionInfo@@@Z; CSubscriptionMgr::CreateSubscriptionNoSummary(HWND__ *,ushort const *,ushort const *,ulong,SUBSCRIPTIONTYPE,_tagSubscriptionInfo *)
0x1800170a2  mov     ebx, eax
0x1800170a4  test    eax, eax
0x1800170a6  jnz     short loc_1800170B0
0x1800170a8  mov     rcx, rdi; unsigned __int16 *
0x1800170ab  call    ?RemoveURLMapping@@YAXPEBG@Z; RemoveURLMapping(ushort const *)
0x1800170b0  mov     eax, ebx
0x1800170b2  add     rsp, 50h
0x1800170b6  pop     r15
0x1800170b8  pop     r14
0x1800170ba  pop     r12
0x1800170bc  pop     rdi
0x1800170bd  pop     rsi
0x1800170be  pop     rbp
0x1800170bf  pop     rbx
0x1800170c0  retn
```

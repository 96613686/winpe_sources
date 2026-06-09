# CreateSubscriptionFromOOEBuf(OOEBuf *,MYPIDL * *)

- ea: `0x18000b514`
- end: `0x18000b87a`
- name: `?CreateSubscriptionFromOOEBuf@@YAJPEAUOOEBuf@@PEAPEFAUMYPIDL@@@Z`
- size: `870`
- prototype: `__int64 __fastcall(struct OOEBuf *, struct MYPIDL **)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800170c8`

## callees

- `0x180003950`
- `0x18000afb4`
- `0x18000b514`
- `0x18000bc30`
- `0x18000bce0`
- `0x18000cc84`
- `0x18000d63c`
- `0x18000dd40`
- `0x18000ddd8`
- `0x180018a40`
- `0x180019ae0`
- `0x18001c054`
- `0x18001c384`
- `0x18001c728`
- `0x18001c8fc`
- `0x180029236`
- `0x18002924e`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000b58d`
- `ole32!CoTaskMemAlloc` at `0x18000b58d`
- `ole32!CoTaskMemFree` at `0x18000b833`
- `ole32!CoTaskMemFree` at `0x18000b833`

## pseudocode

```c
__int64 __fastcall CreateSubscriptionFromOOEBuf(struct OOEBuf *a1, LPVOID *a2)
{
  unsigned int v4; // eax
  unsigned __int16 v5; // bx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rsi
  _WORD *v8; // r14
  IID *v9; // r12
  _QWORD *v10; // rbx
  unsigned int v11; // r9d
  int updated; // esi
  __int64 v13; // rbx
  unsigned int v14; // r8d
  struct _GUID v15; // xmm1
  int v16; // ecx
  enum SUBSCRIPTIONSCHEDULE Group; // eax
  int v18; // ecx
  enum SUBSCRIPTIONSCHEDULE v19; // esi
  enum SUBSCRIPTIONTYPE ItemCategory; // eax
  struct ISubscriptionItem *v21; // rcx
  __int64 v22; // rbx
  enum SUBSCRIPTIONSCHEDULE v23; // r8d
  __int128 v24; // xmm1
  const unsigned __int16 *v25; // rdx
  __int128 v26; // xmm0
  int v27; // eax
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  unsigned __int16 *const *v31; // [rsp+20h] [rbp-E0h]
  struct tagVARIANT *v32; // [rsp+28h] [rbp-D8h]
  __int128 Buf2; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID v34; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v35; // [rsp+50h] [rbp-B0h] BYREF
  IID rclsid; // [rsp+60h] [rbp-A0h] BYREF
  tagSUBSCRIPTIONITEMINFO v37; // [rsp+70h] [rbp-90h] BYREF
  struct _TASK_TRIGGER v38; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v39[2088]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = BufferSize();
  rclsid = 0;
  if ( v4 <= 0xFFFF )
  {
    v5 = v4 + 224;
    if ( (unsigned __int16)(v4 + 224) >= (unsigned __int16)v4 && (unsigned __int64)v5 + 2 >= v5 )
    {
      v6 = (unsigned __int16 *)CoTaskMemAlloc(v5 + 2LL);
      v7 = v6;
      if ( v6 )
      {
        memset_0(v6, 0, v5 + 2LL);
        *v7 = v5;
        v8 = v7 + 4;
        v7[1] = 29701;
        *a2 = v7;
        CopyToMyPooe(a1, v7 + 4);
        v9 = (IID *)(v7 + 64);
        Buf2 = *((_OWORD *)v7 + 8);
        v10 = v7 + 100;
        if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
        {
          rclsid = *v9;
          ReadCookieFromInetDB((_WORD *)((char *)v8 + *v10), &rclsid);
          *v9 = rclsid;
          if ( !memcmp_0(&GUID_NULL, &rclsid, 0x10u) )
            CreateCookie(v7 + 64);
        }
        rclsid = *v9;
        WriteCookieToInetDB((_WORD *)((char *)v8 + *v10), &rclsid, 0);
        *v9 = rclsid;
        *(_QWORD *)&v37.cbSize = 44;
        memset(&v37.dwPriority, 0, 36);
        v37.clsidAgent = *(CLSID *)(v7 + 82);
        StringCchCopyW(v39, 0x824u, (_WORD *)((char *)v8 + *v10));
        updated = AddUpdateSubscription((struct _GUID *)v7 + 8, &v37, v39, v11, v31, v32);
        if ( updated < 0 )
          goto LABEL_22;
        *(_QWORD *)&Buf2 = 0;
        updated = SubscriptionItemFromCookie(0, (const struct _GUID *)(v8 + 60), (struct ISubscriptionItem **)&Buf2);
        if ( updated < 0 )
          goto LABEL_22;
        v13 = Buf2;
        updated = WritePropertiesToItem((struct OOEntry *)v8, (struct ISubscriptionItem *)Buf2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( updated < 0 )
          goto LABEL_22;
        *(_QWORD *)&Buf2 = 0;
        updated = SubscriptionItemFromCookie(1, (const struct _GUID *)(v8 + 60), (struct ISubscriptionItem **)&Buf2);
        if ( updated < 0 )
          goto LABEL_22;
        v14 = *((_DWORD *)v8 + 29);
        v15 = *(struct _GUID *)(v8 + 68);
        v16 = *((_DWORD *)v8 + 11);
        v34 = *(struct _GUID *)(v8 + 78);
        v35 = v15;
        Group = GetGroup(v16, &v34, v14, &v35);
        v18 = *((_DWORD *)v8 + 11);
        v19 = Group;
        v34 = *(struct _GUID *)(v8 + 78);
        ItemCategory = GetItemCategory(v18, &v34);
        v22 = Buf2;
        if ( v19 )
        {
          v23 = v19;
        }
        else
        {
          if ( (ItemCategory == SUBSTYPE_CHANNEL || ItemCategory == SUBSTYPE_DESKTOPCHANNEL) && v8[34] == 48 )
          {
            v24 = *(_OWORD *)(v8 + 42);
            v25 = (_WORD *)((char *)v8 + *((_QWORD *)v8 + 25));
            *(_OWORD *)&v38.cbTriggerSize = *(_OWORD *)(v8 + 34);
            v26 = *(_OWORD *)(v8 + 50);
            *(_OWORD *)&v38.wStartHour = v24;
            *(_OWORD *)&v38.TriggerType = v26;
            v27 = ScheduleIt((struct ISubscriptionItem *)Buf2, v25, &v38);
            v28 = *(_OWORD *)&v38.wStartHour;
            *(_OWORD *)(v8 + 34) = *(_OWORD *)&v38.cbTriggerSize;
            v29 = *(_OWORD *)&v38.TriggerType;
            *(_OWORD *)(v8 + 42) = v28;
            *(_OWORD *)(v8 + 50) = v29;
            *(GUID *)(v8 + 68) = GUID_NULL;
            goto LABEL_20;
          }
          v23 = SUBSSCHED_DAILY;
        }
        v27 = AddIt(v21, (struct OOEntry *)v8, v23);
LABEL_20:
        updated = v27;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( updated >= 0 )
        {
          FireSubscriptionEvent(1u, (IID *)(v8 + 60));
          return (unsigned int)updated;
        }
LABEL_22:
        CoTaskMemFree(*a2);
        *a2 = 0;
        return (unsigned int)updated;
      }
    }
  }
  *a2 = 0;
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000b514  mov     [rsp-8+arg_10], rbx
0x18000b519  mov     [rsp-8+arg_18], rsi
0x18000b51e  push    rbp
0x18000b51f  push    rdi
0x18000b520  push    r12
0x18000b522  push    r14
0x18000b524  push    r15
0x18000b526  lea     rbp, [rsp-1030h]
0x18000b52e  mov     eax, 1130h
0x18000b533  call    _alloca_probe
0x18000b538  sub     rsp, rax
0x18000b53b  mov     rax, cs:__security_cookie
0x18000b542  xor     rax, rsp
0x18000b545  mov     [rbp+1050h+var_30], rax
0x18000b54c  mov     r15, rdx
0x18000b54f  mov     r12, rcx
0x18000b552  call    BufferSize
0x18000b557  xorps   xmm0, xmm0
0x18000b55a  movups  xmmword ptr [rsp+1150h+rclsid.Data1], xmm0
0x18000b55f  cmp     eax, 0FFFFh
0x18000b564  ja      loc_18000B845
0x18000b56a  mov     ebx, 0E0h
0x18000b56f  add     ebx, eax
0x18000b571  cmp     bx, ax
0x18000b574  jb      loc_18000B845
0x18000b57a  movzx   eax, bx
0x18000b57d  lea     r14, [rax+2]
0x18000b581  cmp     r14, rax
0x18000b584  jb      loc_18000B845
0x18000b58a  mov     rcx, r14; cb
0x18000b58d  call    cs:__imp_CoTaskMemAlloc
0x18000b593  xor     edi, edi
0x18000b595  mov     rsi, rax
0x18000b598  test    rax, rax
0x18000b59b  jz      loc_18000B840
0x18000b5a1  mov     r8, r14; Size
0x18000b5a4  xor     edx, edx; Val
0x18000b5a6  mov     rcx, rax; void *
0x18000b5a9  call    memset_0
0x18000b5ae  mov     [rsi], bx
0x18000b5b1  lea     r14, [rsi+8]
0x18000b5b5  mov     word ptr [rsi+2], 7405h
0x18000b5bb  mov     rdx, r14
0x18000b5be  mov     rcx, r12
0x18000b5c1  mov     [r15], rsi
0x18000b5c4  call    CopyToMyPooe
0x18000b5c9  lea     r12, [r14+78h]
0x18000b5cd  movups  xmm0, xmmword ptr [r12]
0x18000b5d2  lea     esi, [rdi+10h]
0x18000b5d5  mov     r8d, esi; Size
0x18000b5d8  lea     rdx, [rsp+1150h+Buf2]; Buf2
0x18000b5dd  lea     rcx, GUID_NULL; Buf1
0x18000b5e4  movdqu  [rsp+1150h+Buf2], xmm0
0x18000b5ea  call    memcmp_0
0x18000b5ef  lea     rbx, [r14+0C0h]
0x18000b5f6  test    eax, eax
0x18000b5f8  jnz     short loc_18000B640
0x18000b5fa  movups  xmm0, xmmword ptr [r12]
0x18000b5ff  lea     rdx, [rsp+1150h+rclsid]; lpiid
0x18000b604  movdqu  xmmword ptr [rsp+1150h+rclsid.Data1], xmm0
0x18000b60a  mov     rcx, [rbx]
0x18000b60d  add     rcx, r14; unsigned __int16 *
0x18000b610  call    ?ReadCookieFromInetDB@@YAJPEBGPEAU_GUID@@@Z; ReadCookieFromInetDB(ushort const *,_GUID *)
0x18000b615  movups  xmm0, xmmword ptr [rsp+1150h+rclsid.Data1]
0x18000b61a  mov     r8d, esi; Size
0x18000b61d  lea     rdx, [rsp+1150h+rclsid]; Buf2
0x18000b622  lea     rcx, GUID_NULL; Buf1
0x18000b629  movdqu  xmmword ptr [r12], xmm0
0x18000b62f  call    memcmp_0
0x18000b634  test    eax, eax
0x18000b636  jnz     short loc_18000B640
0x18000b638  mov     rcx, r12
0x18000b63b  call    CreateCookie
0x18000b640  movups  xmm0, xmmword ptr [r12]
0x18000b645  xor     r8d, r8d; int
0x18000b648  lea     rdx, [rsp+1150h+rclsid]; rclsid
0x18000b64d  movdqu  xmmword ptr [rsp+1150h+rclsid.Data1], xmm0
0x18000b653  mov     rcx, [rbx]
0x18000b656  add     rcx, r14; unsigned __int16 *
0x18000b659  call    ?WriteCookieToInetDB@@YAJPEBGPEBU_GUID@@H@Z; WriteCookieToInetDB(ushort const *,_GUID const *,int)
0x18000b65e  movups  xmm0, xmmword ptr [rsp+1150h+rclsid.Data1]
0x18000b663  lea     rcx, [rbp+1050h+var_1080]; unsigned __int16 *
0x18000b667  mov     edx, 824h; unsigned __int64
0x18000b66c  xorps   xmm1, xmm1
0x18000b66f  movdqu  xmmword ptr [r12], xmm0
0x18000b675  mov     qword ptr [rsp+1150h+var_10E0.cbSize], 2Ch ; ','
0x18000b67e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000b685  mov     [rsp+1150h+var_10E0.dwPriority], edi
0x18000b689  movdqu  xmmword ptr [rbp+1050h+var_10E0.clsidAgent.Data1], xmm1
0x18000b68e  movdqu  xmmword ptr [rsp+1150h+var_10E0.ScheduleGroup.Data1], xmm0
0x18000b694  movups  xmm0, xmmword ptr [r14+9Ch]
0x18000b69c  movdqu  xmmword ptr [rbp+1050h+var_10E0.clsidAgent.Data1], xmm0
0x18000b6a1  mov     r8, [rbx]
0x18000b6a4  add     r8, r14; unsigned __int16 *
0x18000b6a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b6ac  lea     r8, [rbp+1050h+var_1080]; unsigned __int16 *
0x18000b6b0  mov     rcx, r12; struct _GUID *
0x18000b6b3  lea     rdx, [rsp+1150h+var_10E0]; struct tagSUBSCRIPTIONITEMINFO *
0x18000b6b8  call    ?AddUpdateSubscription@@YAJPEFAU_GUID@@PEBUtagSUBSCRIPTIONITEMINFO@@PEBGKQEBQEAGQEAUtagVARIANT@@@Z; AddUpdateSubscription(_GUID *,tagSUBSCRIPTIONITEMINFO const *,ushort const *,ulong,ushort * const * const,tagVARIANT * const)
0x18000b6bd  mov     esi, eax
0x18000b6bf  test    eax, eax
0x18000b6c1  js      loc_18000B830
0x18000b6c7  lea     r8, [rsp+1150h+Buf2]; struct ISubscriptionItem **
0x18000b6cc  mov     qword ptr [rsp+1150h+Buf2], rdi
0x18000b6d1  mov     rdx, r12; struct _GUID *
0x18000b6d4  xor     ecx, ecx; int
0x18000b6d6  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x18000b6db  mov     esi, eax
0x18000b6dd  test    eax, eax
0x18000b6df  js      loc_18000B830
0x18000b6e5  mov     rbx, qword ptr [rsp+1150h+Buf2]
0x18000b6ea  mov     rcx, r14; struct OOEntry *
0x18000b6ed  mov     rdx, rbx; struct ISubscriptionItem *
0x18000b6f0  call    ?WritePropertiesToItem@@YAJPEFAUOOEntry@@PEAUISubscriptionItem@@@Z; WritePropertiesToItem(OOEntry *,ISubscriptionItem *)
0x18000b6f5  mov     esi, eax
0x18000b6f7  mov     rcx, rbx
0x18000b6fa  mov     rax, [rbx]
0x18000b6fd  mov     rax, [rax+10h]
0x18000b701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b706  test    esi, esi
0x18000b708  js      loc_18000B830
0x18000b70e  lea     r8, [rsp+1150h+Buf2]; struct ISubscriptionItem **
0x18000b713  mov     qword ptr [rsp+1150h+Buf2], rdi
0x18000b718  mov     rdx, r12; struct _GUID *
0x18000b71b  mov     ecx, 1; int
0x18000b720  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x18000b725  mov     esi, eax
0x18000b727  test    eax, eax
0x18000b729  js      loc_18000B830
0x18000b72f  movups  xmm0, xmmword ptr [r14+9Ch]
0x18000b737  mov     r8d, [r14+74h]; unsigned int
0x18000b73b  lea     r9, [rsp+1150h+var_1100]; struct _GUID *
0x18000b740  movups  xmm1, xmmword ptr [r14+88h]
0x18000b748  mov     ecx, [r14+2Ch]; int
0x18000b74c  lea     rdx, [rsp+1150h+var_1110]; struct _GUID *
0x18000b751  movdqu  xmmword ptr [rsp+1150h+var_1110.Data1], xmm0
0x18000b757  movdqu  xmmword ptr [rsp+1150h+var_1100.Data1], xmm1
0x18000b75d  call    ?GetGroup@@YA?AW4SUBSCRIPTIONSCHEDULE@@HAEBU_GUID@@K0@Z; GetGroup(int,_GUID const &,ulong,_GUID const &)
0x18000b762  movups  xmm0, xmmword ptr [r14+9Ch]
0x18000b76a  mov     ecx, [r14+2Ch]; int
0x18000b76e  lea     rdx, [rsp+1150h+var_1110]; struct _GUID *
0x18000b773  mov     esi, eax
0x18000b775  movdqu  xmmword ptr [rsp+1150h+var_1110.Data1], xmm0
0x18000b77b  call    ?GetItemCategory@@YA?AW4SUBSCRIPTIONTYPE@@HAEBU_GUID@@@Z; GetItemCategory(int,_GUID const &)
0x18000b780  mov     rbx, qword ptr [rsp+1150h+Buf2]
0x18000b785  test    esi, esi
0x18000b787  jnz     short loc_18000B801
0x18000b789  cmp     eax, 1
0x18000b78c  jz      short loc_18000B79B
0x18000b78e  cmp     eax, 4
0x18000b791  jz      short loc_18000B79B
0x18000b793  mov     r8d, 1
0x18000b799  jmp     short loc_18000B804
0x18000b79b  cmp     word ptr [r14+44h], 30h ; '0'
0x18000b7a1  jnz     short loc_18000B793
0x18000b7a3  movups  xmm0, xmmword ptr [r14+44h]
0x18000b7a8  mov     rdx, [r14+0C8h]
0x18000b7af  lea     r8, [rbp+1050h+var_10B0]; struct _TASK_TRIGGER *
0x18000b7b3  movups  xmm1, xmmword ptr [r14+54h]
0x18000b7b8  add     rdx, r14; unsigned __int16 *
0x18000b7bb  mov     rcx, rbx; struct ISubscriptionItem *
0x18000b7be  movups  xmmword ptr [rbp+1050h+var_10B0.cbTriggerSize], xmm0
0x18000b7c2  movups  xmm0, xmmword ptr [r14+64h]
0x18000b7c7  movups  xmmword ptr [rbp+1050h+var_10B0.wStartHour], xmm1
0x18000b7cb  movups  xmmword ptr [rbp+1050h+var_10B0.TriggerType], xmm0
0x18000b7cf  call    ?ScheduleIt@@YAJPEAUISubscriptionItem@@PEBGPEAU_TASK_TRIGGER@@@Z; ScheduleIt(ISubscriptionItem *,ushort const *,_TASK_TRIGGER *)
0x18000b7d4  movups  xmm0, xmmword ptr [rbp+1050h+var_10B0.cbTriggerSize]
0x18000b7d8  movups  xmm1, xmmword ptr [rbp+1050h+var_10B0.wStartHour]
0x18000b7dc  movups  xmmword ptr [r14+44h], xmm0
0x18000b7e1  movups  xmm0, xmmword ptr [rbp+1050h+var_10B0.TriggerType]
0x18000b7e5  movups  xmmword ptr [r14+54h], xmm1
0x18000b7ea  movups  xmmword ptr [r14+64h], xmm0
0x18000b7ef  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18000b7f6  movdqu  xmmword ptr [r14+88h], xmm1
0x18000b7ff  jmp     short loc_18000B80C
0x18000b801  mov     r8d, esi; enum SUBSCRIPTIONSCHEDULE
0x18000b804  mov     rdx, r14; struct OOEntry *
0x18000b807  call    ?AddIt@@YAJPEAUISubscriptionItem@@PEFAUOOEntry@@W4SUBSCRIPTIONSCHEDULE@@@Z; AddIt(ISubscriptionItem *,OOEntry *,SUBSCRIPTIONSCHEDULE)
0x18000b80c  mov     esi, eax
0x18000b80e  mov     rcx, rbx
0x18000b811  mov     rax, [rbx]
0x18000b814  mov     rax, [rax+10h]
0x18000b818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b81d  test    esi, esi
0x18000b81f  js      short loc_18000B830
0x18000b821  mov     rdx, r12
0x18000b824  mov     ecx, 1
0x18000b829  call    FireSubscriptionEvent
0x18000b82e  jmp     short loc_18000B83C
0x18000b830  mov     rcx, [r15]; pv
0x18000b833  call    cs:__imp_CoTaskMemFree
0x18000b839  mov     [r15], rdi
0x18000b83c  mov     eax, esi
0x18000b83e  jmp     short loc_18000B84F
0x18000b840  mov     rdi, rsi
0x18000b843  jmp     short loc_18000B847
0x18000b845  xor     edi, edi
0x18000b847  mov     [r15], rdi
0x18000b84a  mov     eax, 8007000Eh
0x18000b84f  mov     rcx, [rbp+1050h+var_30]
0x18000b856  xor     rcx, rsp; StackCookie
0x18000b859  call    __security_check_cookie
0x18000b85e  lea     r11, [rsp+1150h+var_20]
0x18000b866  mov     rbx, [r11+40h]
0x18000b86a  mov     rsi, [r11+48h]
0x18000b86e  mov     rsp, r11
0x18000b871  pop     r15
0x18000b873  pop     r14
0x18000b875  pop     r12
0x18000b877  pop     rdi
0x18000b878  pop     rbp
0x18000b879  retn
```

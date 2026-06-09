# GetItemSchedule(_GUID *,_GUID *)

- ea: `0x18000bd20`
- end: `0x18000be74`
- name: `?GetItemSchedule@@YAJPEAU_GUID@@0@Z`
- size: `340`
- prototype: `__int64 __fastcall(struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800185b4`

## callees

- `0x18000b910`
- `0x18000bd20`
- `0x180019ae0`
- `0x180029236`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000bd8e`
- `ole32!CoCreateInstance` at `0x18000bd8e`
- `ole32!CoUninitialize` at `0x18000be48`
- `ole32!CoUninitialize` at `0x18000be48`
- `ole32!CoInitialize` at `0x18000bd61`
- `ole32!CoInitialize` at `0x18000bd61`

## pseudocode

```c
__int64 __fastcall GetItemSchedule(struct _GUID *a1, struct _GUID *a2)
{
  HRESULT v4; // edi
  struct ISubscriptionItem *v5; // rbx
  struct ISubscriptionItem *v7[2]; // [rsp+30h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-40h] BYREF
  _OWORD Buf1[3]; // [rsp+48h] [rbp-38h] BYREF

  ppv = 0;
  *a2 = GUID_NULL;
  v4 = CoInitialize(0);
  if ( v4 >= 0 )
  {
    v4 = CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv);
    if ( v4 >= 0 )
    {
      v7[0] = 0;
      v4 = SubscriptionItemFromCookie(0, a1, v7);
      if ( v4 >= 0 )
      {
        v5 = v7[0];
        memset(Buf1, 0, 44);
        LODWORD(Buf1[0]) = 44;
        v4 = ((__int64 (__fastcall *)(struct ISubscriptionItem *, _OWORD *))v7[0]->lpVtbl->GetSubscriptionItemInfo)(
               v7[0],
               Buf1);
        ((void (__fastcall *)(struct ISubscriptionItem *))v5->lpVtbl->Release)(v5);
        if ( v4 < 0 || !memcmp_0((char *)Buf1 + 12, &GUID_NULL, 0x10u) )
        {
          v7[0] = (struct ISubscriptionItem *)a1;
          v7[1] = (struct ISubscriptionItem *)a2;
          EnumSchedules((__int64 (__fastcall *)(__int64, __int128 *, __int64))GetItemScheduleCallback, (__int64)v7);
        }
        else
        {
          *a2 = *(struct _GUID *)((char *)Buf1 + 12);
        }
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000bd20  mov     [rsp-18h+arg_10], rbx
0x18000bd25  mov     [rsp-18h+arg_18], rsi
0x18000bd2a  push    rbp
0x18000bd2b  push    rdi
0x18000bd2c  push    r14
0x18000bd2e  mov     rbp, rsp
0x18000bd31  sub     rsp, 80h
0x18000bd38  mov     rax, cs:__security_cookie
0x18000bd3f  xor     rax, rsp
0x18000bd42  mov     [rbp+var_8], rax
0x18000bd46  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000bd4d  mov     r14, rcx
0x18000bd50  mov     [rbp+var_40], 0
0x18000bd58  xor     ecx, ecx; pvReserved
0x18000bd5a  mov     rsi, rdx
0x18000bd5d  movdqu  xmmword ptr [rdx], xmm0
0x18000bd61  call    cs:__imp_CoInitialize
0x18000bd67  mov     edi, eax
0x18000bd69  test    eax, eax
0x18000bd6b  js      loc_18000BE4E
0x18000bd71  xor     edx, edx; pUnkOuter
0x18000bd73  lea     rax, [rbp+var_40]
0x18000bd77  lea     r9, IID_ISyncScheduleMgr; riid
0x18000bd7e  mov     [rsp+80h+ppv], rax; ppv
0x18000bd83  lea     rcx, CLSID_SyncMgr; rclsid
0x18000bd8a  lea     r8d, [rdx+17h]; dwClsContext
0x18000bd8e  call    cs:__imp_CoCreateInstance
0x18000bd94  mov     edi, eax
0x18000bd96  test    eax, eax
0x18000bd98  js      loc_18000BE48
0x18000bd9e  lea     r8, [rbp+var_50]; struct ISubscriptionItem **
0x18000bda2  mov     [rbp+var_50], 0
0x18000bdaa  mov     rdx, r14; struct _GUID *
0x18000bdad  xor     ecx, ecx; int
0x18000bdaf  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x18000bdb4  mov     edi, eax
0x18000bdb6  test    eax, eax
0x18000bdb8  js      short loc_18000BE38
0x18000bdba  mov     rbx, [rbp+var_50]
0x18000bdbe  lea     rdx, [rbp+Buf1]
0x18000bdc2  xorps   xmm0, xmm0
0x18000bdc5  mov     rcx, rbx
0x18000bdc8  movups  [rbp+Buf1], xmm0
0x18000bdcc  mov     dword ptr [rbp+Buf1], 2Ch ; ','
0x18000bdd3  movups  [rbp+var_28], xmm0
0x18000bdd7  movups  [rbp+var_28+0Ch], xmm0
0x18000bddb  mov     rax, [rbx]
0x18000bdde  mov     rax, [rax+20h]
0x18000bde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde7  mov     edi, eax
0x18000bde9  mov     rcx, rbx
0x18000bdec  mov     rax, [rbx]
0x18000bdef  mov     rax, [rax+10h]
0x18000bdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf8  test    edi, edi
0x18000bdfa  js      short loc_18000BE20
0x18000bdfc  mov     r8d, 10h; Size
0x18000be02  lea     rdx, GUID_NULL; Buf2
0x18000be09  lea     rcx, [rbp+Buf1+0Ch]; Buf1
0x18000be0d  call    memcmp_0
0x18000be12  test    eax, eax
0x18000be14  jz      short loc_18000BE20
0x18000be16  movups  xmm0, [rbp+Buf1+0Ch]
0x18000be1a  movdqu  xmmword ptr [rsi], xmm0
0x18000be1e  jmp     short loc_18000BE38
0x18000be20  lea     rdx, [rbp+var_50]; __int64
0x18000be24  mov     [rbp+var_50], r14
0x18000be28  lea     rcx, ?GetItemScheduleCallback@@YAHPEAUISyncSchedule@@PEBU_GUID@@_J@Z; int (*)(struct ISyncSchedule *, const struct _GUID *, __int64)
0x18000be2f  mov     [rbp+var_48], rsi
0x18000be33  call    ?EnumSchedules@@YAJP6AHPEAUISyncSchedule@@PEBU_GUID@@_J@Z2@Z; EnumSchedules(int (*)(ISyncSchedule *,_GUID const *,__int64),__int64)
0x18000be38  mov     rcx, [rbp+var_40]
0x18000be3c  mov     rax, [rcx]
0x18000be3f  mov     rax, [rax+10h]
0x18000be43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be48  call    cs:__imp_CoUninitialize
0x18000be4e  mov     eax, edi
0x18000be50  mov     rcx, [rbp+var_8]
0x18000be54  xor     rcx, rsp; StackCookie
0x18000be57  call    __security_check_cookie
0x18000be5c  lea     r11, [rsp+80h+var_s0]
0x18000be64  mov     rbx, [r11+30h]
0x18000be68  mov     rsi, [r11+38h]
0x18000be6c  mov     rsp, r11
0x18000be6f  pop     r14
0x18000be71  pop     rdi
0x18000be72  pop     rbp
0x18000be73  retn
```

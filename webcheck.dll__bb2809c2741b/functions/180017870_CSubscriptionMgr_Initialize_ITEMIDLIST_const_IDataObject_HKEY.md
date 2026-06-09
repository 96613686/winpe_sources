# CSubscriptionMgr::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x180017870`
- end: `0x180017a9b`
- name: `?Initialize@CSubscriptionMgr@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(CSubscriptionMgr *__hidden this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003950`
- `0x180017524`
- `0x180017870`
- `0x18001939c`
- `0x18001c728`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800179ce`
- `ole32!CoCreateInstance` at `0x1800179ce`
- `ole32!CoUninitialize` at `0x180017a68`
- `ole32!CoUninitialize` at `0x180017a68`
- `ole32!CoInitialize` at `0x1800179a0`
- `ole32!CoInitialize` at `0x1800179a0`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::Initialize(
        CSubscriptionMgr *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  const unsigned __int16 *v4; // r12
  _DWORD *v5; // rsi
  const unsigned __int16 *v7; // r15
  int InfoFromDataObject; // ebx
  struct ISubscriptionItem *v9; // rbx
  int v10; // r14d
  LPVOID *v11; // rdi
  __int64 (__fastcall ***v12)(LPVOID, GUID *, struct ISubscriptionItem **); // rcx
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+30h] [rbp-D0h]
  struct ISubscriptionItem *v16; // [rsp+40h] [rbp-C0h] BYREF
  IID rclsid; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v19[3]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v20[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v21[2088]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v4 = (const unsigned __int16 *)((char *)this + 4224);
  v16 = 0;
  v5 = (_DWORD *)((char *)this + 5284);
  v7 = (const unsigned __int16 *)((char *)this + 56);
  rclsid = 0;
  v18 = 0;
  InfoFromDataObject = GetInfoFromDataObject(
                         a3,
                         (unsigned __int16 *)this + 2372,
                         (__int64)a3,
                         (unsigned __int16 *)this + 2112,
                         ppv,
                         (LPWSTR)this + 28,
                         v15,
                         (CSubscriptionMgr *)((char *)this + 5284));
  if ( InfoFromDataObject >= 0 )
  {
    if ( DoGetItemFromURL(v7, &v16) < 0 )
      goto LABEL_6;
    v9 = v16;
    memset(v19, 0, 44);
    LODWORD(v19[0]) = 44;
    v10 = ((__int64 (__fastcall *)(struct ISubscriptionItem *, _OWORD *))v16->lpVtbl->GetSubscriptionItemInfo)(v16, v19);
    if ( v10 >= 0 )
      rclsid = *(IID *)((char *)&v19[1] + 12);
    ((void (__fastcall *)(struct ISubscriptionItem *, __int128 *))v9->lpVtbl->GetCookie)(v9, &v18);
    ((void (__fastcall *)(struct ISubscriptionItem *))v9->lpVtbl->Release)(v9);
    if ( v10 < 0 )
    {
LABEL_6:
      CreateCookie(&v18);
      if ( *v5 != 1 )
        return (unsigned int)-2147467259;
      rclsid = CLSID_WebCrawlerAgent;
    }
    InfoFromDataObject = CoInitialize(0);
    if ( InfoFromDataObject >= 0 )
    {
      v11 = (LPVOID *)((char *)this + 5272);
      InfoFromDataObject = CoCreateInstance(&rclsid, 0, 1u, &IID_IUnknown, v11);
      if ( InfoFromDataObject >= 0 )
      {
        v12 = (__int64 (__fastcall ***)(LPVOID, GUID *, struct ISubscriptionItem **))*v11;
        v16 = 0;
        InfoFromDataObject = (**v12)(v12, &IID_ISubscriptionAgentShellExt, &v16);
        if ( InfoFromDataObject >= 0 )
        {
          StringCchCopyW(v21, 0x824u, v7);
          StringCchCopyW(v20, 0x105u, v4);
          InfoFromDataObject = ((__int64 (__fastcall *)(struct ISubscriptionItem *, __int128 *, unsigned __int16 *, unsigned __int16 *, _DWORD))v16->lpVtbl->GetCookie)(
                                 v16,
                                 &v18,
                                 v21,
                                 v20,
                                 0);
          ((void (__fastcall *)(struct ISubscriptionItem *))v16->lpVtbl->Release)(v16);
        }
      }
      CoUninitialize();
    }
  }
  return (unsigned int)InfoFromDataObject;
}

```

## disassembly

```asm
0x180017870  mov     [rsp-8+arg_8], rbx
0x180017875  mov     [rsp-8+arg_18], rsi
0x18001787a  push    rbp
0x18001787b  push    rdi
0x18001787c  push    r12
0x18001787e  push    r14
0x180017880  push    r15
0x180017882  lea     rbp, [rsp-1210h]
0x18001788a  mov     eax, 1310h
0x18001788f  call    _alloca_probe
0x180017894  sub     rsp, rax
0x180017897  mov     rax, cs:__security_cookie
0x18001789e  xor     rax, rsp
0x1800178a1  mov     [rbp+1230h+var_30], rax
0x1800178a8  lea     r12, [rcx+1080h]
0x1800178af  mov     [rsp+1330h+var_12F0], 0
0x1800178b8  lea     rsi, [rcx+14A4h]
0x1800178bf  mov     rdi, rcx
0x1800178c2  lea     r15, [rcx+38h]
0x1800178c6  mov     [rsp+1330h+var_12F8], rsi; enum INIT_SRC_ENUM *
0x1800178cb  xorps   xmm0, xmm0
0x1800178ce  mov     [rsp+1330h+lpszBuffer], r15; lpszBuffer
0x1800178d3  xorps   xmm1, xmm1
0x1800178d6  lea     rdx, [rcx+1288h]; unsigned __int16 *
0x1800178dd  mov     r9, r12; unsigned __int16 *
0x1800178e0  mov     rcx, r8; struct IDataObject *
0x1800178e3  movups  xmmword ptr [rsp+1330h+rclsid.Data1], xmm0
0x1800178e8  movups  [rsp+1330h+var_12D8], xmm1
0x1800178ed  call    ?GetInfoFromDataObject@@YAJPEAUIDataObject@@PEAGK1K1KPEAW4INIT_SRC_ENUM@@@Z; GetInfoFromDataObject(IDataObject *,ushort *,ulong,ushort *,ulong,ushort *,ulong,INIT_SRC_ENUM *)
0x1800178f2  mov     ebx, eax
0x1800178f4  test    eax, eax
0x1800178f6  js      loc_180017A6E
0x1800178fc  lea     rdx, [rsp+1330h+var_12F0]; struct ISubscriptionItem **
0x180017901  mov     rcx, r15; unsigned __int16 *
0x180017904  call    ?DoGetItemFromURL@@YAJPEBGPEAPEAUISubscriptionItem@@@Z; DoGetItemFromURL(ushort const *,ISubscriptionItem * *)
0x180017909  test    eax, eax
0x18001790b  js      short loc_180017978
0x18001790d  mov     rbx, [rsp+1330h+var_12F0]
0x180017912  lea     rdx, [rsp+1330h+var_12C8]
0x180017917  xorps   xmm0, xmm0
0x18001791a  mov     rcx, rbx
0x18001791d  movups  [rsp+1330h+var_12C8], xmm0
0x180017922  mov     dword ptr [rsp+1330h+var_12C8], 2Ch ; ','
0x18001792a  movups  xmmword ptr [rsp+1330h+var_12B8], xmm0
0x18001792f  movups  xmmword ptr [rbp+1230h+var_12B8+0Ch], xmm0
0x180017933  mov     rax, [rbx]
0x180017936  mov     rax, [rax+20h]
0x18001793a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001793f  mov     r14d, eax
0x180017942  test    eax, eax
0x180017944  js      short loc_180017950
0x180017946  movups  xmm0, xmmword ptr [rbp+1230h+var_12B8+0Ch]
0x18001794a  movdqu  xmmword ptr [rsp+1330h+rclsid.Data1], xmm0
0x180017950  mov     rdx, [rbx]
0x180017953  mov     rcx, rbx
0x180017956  mov     rax, [rdx+18h]
0x18001795a  lea     rdx, [rsp+1330h+var_12D8]
0x18001795f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017964  mov     rax, [rbx]
0x180017967  mov     rcx, rbx
0x18001796a  mov     rax, [rax+10h]
0x18001796e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017973  test    r14d, r14d
0x180017976  jns     short loc_18001799E
0x180017978  lea     rcx, [rsp+1330h+var_12D8]
0x18001797d  call    CreateCookie
0x180017982  cmp     dword ptr [rsi], 1
0x180017985  jz      short loc_180017991
0x180017987  mov     ebx, 80004005h
0x18001798c  jmp     loc_180017A6E
0x180017991  movups  xmm0, xmmword ptr cs:CLSID_WebCrawlerAgent.Data1
0x180017998  movdqu  xmmword ptr [rsp+1330h+rclsid.Data1], xmm0
0x18001799e  xor     ecx, ecx; pvReserved
0x1800179a0  call    cs:__imp_CoInitialize
0x1800179a6  mov     ebx, eax
0x1800179a8  test    eax, eax
0x1800179aa  js      loc_180017A6E
0x1800179b0  xor     edx, edx; pUnkOuter
0x1800179b2  lea     r9, IID_IUnknown; riid
0x1800179b9  add     rdi, 1498h
0x1800179c0  lea     rcx, [rsp+1330h+rclsid]; rclsid
0x1800179c5  mov     [rsp+1330h+ppv], rdi; ppv
0x1800179ca  lea     r8d, [rdx+1]; dwClsContext
0x1800179ce  call    cs:__imp_CoCreateInstance
0x1800179d4  mov     ebx, eax
0x1800179d6  test    eax, eax
0x1800179d8  js      loc_180017A68
0x1800179de  mov     rcx, [rdi]
0x1800179e1  lea     r8, [rsp+1330h+var_12F0]
0x1800179e6  mov     [rsp+1330h+var_12F0], 0
0x1800179ef  lea     rdx, IID_ISubscriptionAgentShellExt
0x1800179f6  mov     rax, [rcx]
0x1800179f9  mov     rax, [rax]
0x1800179fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a01  mov     ebx, eax
0x180017a03  test    eax, eax
0x180017a05  js      short loc_180017A68
0x180017a07  mov     r8, r15; unsigned __int16 *
0x180017a0a  lea     rcx, [rbp+1230h+var_1080]; unsigned __int16 *
0x180017a11  mov     edx, 824h; unsigned __int64
0x180017a16  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a1b  mov     r8, r12; unsigned __int16 *
0x180017a1e  lea     rcx, [rbp+1230h+var_1290]; unsigned __int16 *
0x180017a22  mov     edx, 105h; unsigned __int64
0x180017a27  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a2c  mov     rcx, [rsp+1330h+var_12F0]
0x180017a31  lea     r9, [rbp+1230h+var_1290]
0x180017a35  lea     r8, [rbp+1230h+var_1080]
0x180017a3c  mov     dword ptr [rsp+1330h+ppv], 0
0x180017a44  lea     rdx, [rsp+1330h+var_12D8]
0x180017a49  mov     rax, [rcx]
0x180017a4c  mov     rax, [rax+18h]
0x180017a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a55  mov     rcx, [rsp+1330h+var_12F0]
0x180017a5a  mov     ebx, eax
0x180017a5c  mov     rax, [rcx]
0x180017a5f  mov     rax, [rax+10h]
0x180017a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a68  call    cs:__imp_CoUninitialize
0x180017a6e  mov     eax, ebx
0x180017a70  mov     rcx, [rbp+1230h+var_30]
0x180017a77  xor     rcx, rsp; StackCookie
0x180017a7a  call    __security_check_cookie
0x180017a7f  lea     r11, [rsp+1330h+var_20]
0x180017a87  mov     rbx, [r11+38h]
0x180017a8b  mov     rsi, [r11+48h]
0x180017a8f  mov     rsp, r11
0x180017a92  pop     r15
0x180017a94  pop     r14
0x180017a96  pop     r12
0x180017a98  pop     rdi
0x180017a99  pop     rbp
0x180017a9a  retn
```

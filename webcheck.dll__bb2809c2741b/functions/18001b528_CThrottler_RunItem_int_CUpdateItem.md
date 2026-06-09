# CThrottler::RunItem(int,CUpdateItem *)

- ea: `0x18001b528`
- end: `0x18001b6be`
- name: `?RunItem@CThrottler@@AEAAXHPEAUCUpdateItem@@@Z`
- size: `406`
- prototype: `void __fastcall(CThrottler *__hidden this, int, struct CUpdateItem *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18001a6fc`

## callees

- `0x180019ae0`
- `0x18001a620`
- `0x18001ab54`
- `0x18001b528`
- `0x18001c8fc`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `USER32!LoadStringW` at `0x18001b5a1`
- `USER32!LoadStringW` at `0x18001b5a1`
- `ole32!CoCreateInstance` at `0x18001b650`
- `ole32!CoCreateInstance` at `0x18001b650`

## pseudocode

```c
void __fastcall CThrottler::RunItem(CThrottler *this, int a2, struct CUpdateItem *a3)
{
  struct _GUID *v3; // rbp
  int v6; // eax
  __int64 v7; // rcx
  HRESULT Instance; // ebx
  struct ISubscriptionItem *v9; // rdi
  struct ISubscriptionItem *v10; // [rsp+40h] [rbp-278h] BYREF
  IID v11[3]; // [rsp+48h] [rbp-270h] BYREF
  WCHAR Buffer[256]; // [rsp+80h] [rbp-238h] BYREF

  v3 = (struct _GUID *)((char *)a3 + 8);
  *((_QWORD *)this + a2 + 7) = a3;
  v6 = *((_DWORD *)a3 + 6);
  if ( (v6 & 2) != 0 )
  {
    v7 = *(_QWORD *)a3;
    *((_DWORD *)a3 + 6) = v6 & 0xFFFFFFF9 | 4;
    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, 0);
    if ( Instance >= 0 )
    {
      LoadStringW(g_hinstMUI, 0x2035u, Buffer, 256);
      CThrottler::NotifyHandlers(this, 1, v3);
      return;
    }
LABEL_9:
    if ( Instance >= 0 )
      return;
    goto LABEL_10;
  }
  v10 = 0;
  Instance = SubscriptionItemFromCookie(0, v3, &v10);
  if ( Instance >= 0 )
  {
    v9 = v10;
    memset(v11, 0, 44);
    v11[0].Data1 = 44;
    Instance = ((__int64 (__fastcall *)(struct ISubscriptionItem *, IID *))v10->lpVtbl->GetSubscriptionItemInfo)(
                 v10,
                 v11);
    if ( Instance >= 0 )
    {
      Instance = CoCreateInstance(
                   (const IID *const)&v11[1].Data4[4],
                   0,
                   1u,
                   &IID_ISubscriptionAgentControl,
                   (LPVOID *)a3);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, struct ISubscriptionItem *, CThrottler *))(**(_QWORD **)a3 + 24LL))(
                     *(_QWORD *)a3,
                     v9,
                     this);
        FireSubscriptionEvent(4u, v3);
      }
    }
    ((void (__fastcall *)(struct ISubscriptionItem *))v9->lpVtbl->Release)(v9);
    goto LABEL_9;
  }
LABEL_10:
  CThrottler::FailedUpdate(this, Instance, v3);
}

```

## disassembly

```asm
0x18001b528  push    rbx
0x18001b52a  push    rbp
0x18001b52b  push    rsi
0x18001b52c  push    rdi
0x18001b52d  push    r14
0x18001b52f  sub     rsp, 290h
0x18001b536  mov     rax, cs:__security_cookie
0x18001b53d  xor     rax, rsp
0x18001b540  mov     [rsp+2B8h+var_38], rax
0x18001b548  movsxd  rax, edx
0x18001b54b  lea     rbp, [r8+8]
0x18001b54f  mov     rsi, r8
0x18001b552  mov     r14, rcx
0x18001b555  mov     [rcx+rax*8+38h], r8
0x18001b55a  mov     eax, [r8+18h]
0x18001b55e  test    al, 2
0x18001b560  jz      short loc_18001B5DE
0x18001b562  mov     rcx, [r8]
0x18001b565  and     eax, 0FFFFFFFDh
0x18001b568  or      eax, 4
0x18001b56b  xor     edx, edx
0x18001b56d  mov     [r8+18h], eax
0x18001b571  mov     rax, [rcx]
0x18001b574  mov     rax, [rax+28h]
0x18001b578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b57d  mov     ebx, eax
0x18001b57f  test    eax, eax
0x18001b581  js      loc_18001B68F
0x18001b587  mov     rcx, cs:g_hinstMUI; hInstance
0x18001b58e  lea     r8, [rsp+2B8h+Buffer]; lpBuffer
0x18001b596  mov     r9d, 100h; cchBufferMax
0x18001b59c  mov     edx, 2035h; uID
0x18001b5a1  call    cs:__imp_LoadStringW
0x18001b5a7  or      r9d, 0FFFFFFFFh
0x18001b5ab  lea     rax, [rsp+2B8h+Buffer]
0x18001b5b3  mov     [rsp+2B8h+var_280], rax
0x18001b5b8  mov     r8, rbp; struct _GUID *
0x18001b5bb  mov     [rsp+2B8h+var_288], 4F001h
0x18001b5c3  mov     rcx, r14; this
0x18001b5c6  mov     [rsp+2B8h+var_290], r9d
0x18001b5cb  lea     edx, [r9+2]; int
0x18001b5cf  mov     dword ptr [rsp+2B8h+ppv], r9d
0x18001b5d4  call    ?NotifyHandlers@CThrottler@@AEAAJHPEBU_GUID@@ZZ; CThrottler::NotifyHandlers(int,_GUID const *,...)
0x18001b5d9  jmp     loc_18001B6A0
0x18001b5de  lea     r8, [rsp+2B8h+var_278]; struct ISubscriptionItem **
0x18001b5e3  mov     [rsp+2B8h+var_278], 0
0x18001b5ec  mov     rdx, rbp; struct _GUID *
0x18001b5ef  xor     ecx, ecx; int
0x18001b5f1  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x18001b5f6  mov     ebx, eax
0x18001b5f8  test    eax, eax
0x18001b5fa  js      loc_18001B693
0x18001b600  mov     rdi, [rsp+2B8h+var_278]
0x18001b605  lea     rdx, [rsp+2B8h+var_270]
0x18001b60a  xorps   xmm0, xmm0
0x18001b60d  mov     rcx, rdi
0x18001b610  movups  [rsp+2B8h+var_270], xmm0
0x18001b615  mov     dword ptr [rsp+2B8h+var_270], 2Ch ; ','
0x18001b61d  movups  xmmword ptr [rsp+2B8h+rclsid], xmm0
0x18001b622  movups  xmmword ptr [rsp+2B8h+rclsid+0Ch], xmm0
0x18001b627  mov     rax, [rdi]
0x18001b62a  mov     rax, [rax+20h]
0x18001b62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b633  mov     ebx, eax
0x18001b635  test    eax, eax
0x18001b637  js      short loc_18001B680
0x18001b639  xor     edx, edx; pUnkOuter
0x18001b63b  mov     [rsp+2B8h+ppv], rsi; ppv
0x18001b640  lea     r9, IID_ISubscriptionAgentControl; riid
0x18001b647  lea     rcx, [rsp+2B8h+rclsid+0Ch]; rclsid
0x18001b64c  lea     r8d, [rdx+1]; dwClsContext
0x18001b650  call    cs:__imp_CoCreateInstance
0x18001b656  mov     ebx, eax
0x18001b658  test    eax, eax
0x18001b65a  js      short loc_18001B680
0x18001b65c  mov     rcx, [rsi]
0x18001b65f  mov     r8, r14
0x18001b662  mov     rdx, rdi
0x18001b665  mov     rax, [rcx]
0x18001b668  mov     rax, [rax+18h]
0x18001b66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b671  mov     rdx, rbp
0x18001b674  mov     ecx, 4
0x18001b679  mov     ebx, eax
0x18001b67b  call    FireSubscriptionEvent
0x18001b680  mov     rax, [rdi]
0x18001b683  mov     rcx, rdi
0x18001b686  mov     rax, [rax+10h]
0x18001b68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b68f  test    ebx, ebx
0x18001b691  jns     short loc_18001B6A0
0x18001b693  mov     r8, rbp; struct _GUID *
0x18001b696  mov     edx, ebx; int
0x18001b698  mov     rcx, r14; this
0x18001b69b  call    ?FailedUpdate@CThrottler@@AEAAXJPEBU_GUID@@@Z; CThrottler::FailedUpdate(long,_GUID const *)
0x18001b6a0  mov     rcx, [rsp+2B8h+var_38]
0x18001b6a8  xor     rcx, rsp; StackCookie
0x18001b6ab  call    __security_check_cookie
0x18001b6b0  add     rsp, 290h
0x18001b6b7  pop     r14
0x18001b6b9  pop     rdi
0x18001b6ba  pop     rsi
0x18001b6bb  pop     rbp
0x18001b6bc  pop     rbx
0x18001b6bd  retn
```

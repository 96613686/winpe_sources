# p9fs::Plan9FileSystem::~Plan9FileSystem(void)

- ea: `0x1800245d4`
- end: `0x1800246f0`
- name: `??1Plan9FileSystem@p9fs@@UEAA@XZ`
- size: `284`
- prototype: `void __fastcall(p9fs::Plan9FileSystem *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180024990`

## callees

- `0x180004534`
- `0x18000e334`
- `0x180023a58`
- `0x1800245d4`
- `0x180027950`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800246c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800246c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800246bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800246bf`
- `WS2_32!__imp_closesocket` at `0x1800246d8`
- `WS2_32!__imp_closesocket` at `0x1800246d8`
- `WS2_32!__imp_WSACleanup` at `0x1800245f9`
- `WS2_32!__imp_WSACleanup` at `0x1800245f9`

## pseudocode

```c
void __fastcall p9fs::Plan9FileSystem::~Plan9FileSystem(p9fs::Plan9FileSystem *this)
{
  volatile signed __int32 *v2; // rbx
  volatile signed __int32 *v3; // rbx
  struct _TP_IO *v4; // rbx
  SOCKET v5; // rcx

  *(_QWORD *)this = &p9fs::Plan9FileSystem::`vftable';
  p9fs::Plan9FileSystem::Teardown(this);
  if ( *((_BYTE *)this + 272) )
    WSACleanup();
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 36);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<p9fs::Share>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<p9fs::Share>>,void *>>>(
    (char *)this + 240,
    (char *)this + 240,
    *(_QWORD *)(*((_QWORD *)this + 30) + 8LL));
  operator delete(*((void **)this + 30), 0x50u);
  p9fs::CancelToken::~CancelToken((p9fs::Plan9FileSystem *)((char *)this + 72));
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (struct _TP_IO *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    WaitForThreadpoolIoCallbacks(*((PTP_IO *)this + 4), 0);
    CloseThreadpoolIo(v4);
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 != -1 )
    closesocket(v5);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x1800245d4  mov     [rsp+arg_8], rbx
0x1800245d9  push    rdi
0x1800245da  sub     rsp, 20h
0x1800245de  mov     rdi, rcx
0x1800245e1  lea     rax, ??_7Plan9FileSystem@p9fs@@6B@; const p9fs::Plan9FileSystem::`vftable'
0x1800245e8  mov     [rcx], rax
0x1800245eb  call    ?Teardown@Plan9FileSystem@p9fs@@UEAAJXZ; p9fs::Plan9FileSystem::Teardown(void)
0x1800245f0  cmp     byte ptr [rdi+110h], 0
0x1800245f7  jz      short loc_1800245FF
0x1800245f9  call    cs:__imp_WSACleanup
0x1800245ff  mov     rbx, [rdi+120h]
0x180024606  test    rbx, rbx
0x180024609  jz      short loc_180024642
0x18002460b  or      eax, 0FFFFFFFFh
0x18002460e  lock xadd [rbx+8], eax
0x180024613  cmp     eax, 1
0x180024616  jnz     short loc_180024642
0x180024618  mov     rax, [rbx]
0x18002461b  mov     rcx, rbx
0x18002461e  mov     rax, [rax]
0x180024621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024626  or      eax, 0FFFFFFFFh
0x180024629  lock xadd [rbx+0Ch], eax
0x18002462e  cmp     eax, 1
0x180024631  jnz     short loc_180024642
0x180024633  mov     rax, [rbx]
0x180024636  mov     rcx, rbx
0x180024639  mov     rax, [rax+8]
0x18002463d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024642  lea     rbx, [rdi+0F0h]
0x180024649  mov     r8, [rbx]
0x18002464c  mov     r8, [r8+8]
0x180024650  mov     rdx, rbx
0x180024653  mov     rcx, rbx
0x180024656  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@UShare@p9fs@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<p9fs::Share>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<p9fs::Share>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<p9fs::Share>>,void *>> &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<p9fs::Share>>,void *> *)
0x18002465b  mov     edx, 50h ; 'P'; unsigned __int64
0x180024660  mov     rcx, [rbx]; void *
0x180024663  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024668  lea     rcx, [rdi+48h]; this
0x18002466c  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x180024671  mov     rbx, [rdi+40h]
0x180024675  test    rbx, rbx
0x180024678  jz      short loc_1800246B1
0x18002467a  or      eax, 0FFFFFFFFh
0x18002467d  lock xadd [rbx+8], eax
0x180024682  cmp     eax, 1
0x180024685  jnz     short loc_1800246B1
0x180024687  mov     rax, [rbx]
0x18002468a  mov     rcx, rbx
0x18002468d  mov     rax, [rax]
0x180024690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024695  or      eax, 0FFFFFFFFh
0x180024698  lock xadd [rbx+0Ch], eax
0x18002469d  cmp     eax, 1
0x1800246a0  jnz     short loc_1800246B1
0x1800246a2  mov     rax, [rbx]
0x1800246a5  mov     rcx, rbx
0x1800246a8  mov     rax, [rax+8]
0x1800246ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246b1  mov     rbx, [rdi+20h]
0x1800246b5  test    rbx, rbx
0x1800246b8  jz      short loc_1800246CE
0x1800246ba  xor     edx, edx; fCancelPendingCallbacks
0x1800246bc  mov     rcx, rbx; pio
0x1800246bf  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800246c5  mov     rcx, rbx; pio
0x1800246c8  call    cs:__imp_CloseThreadpoolIo
0x1800246ce  mov     rcx, [rdi+18h]; s
0x1800246d2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800246d6  jz      short loc_1800246DE
0x1800246d8  call    cs:__imp_closesocket
0x1800246de  mov     dword ptr [rdi+0Ch], 0C0000001h
0x1800246e5  mov     rbx, [rsp+28h+arg_8]
0x1800246ea  add     rsp, 20h
0x1800246ee  pop     rdi
0x1800246ef  retn
```

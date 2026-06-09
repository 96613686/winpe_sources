# SocketTransport::~SocketTransport(void)

- ea: `0x14005f5c8`
- end: `0x14005f67e`
- name: `??1SocketTransport@@UEAA@XZ`
- size: `182`
- prototype: `void __fastcall(SocketTransport *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14005fa70`

## callees

- `0x1400056c4`
- `0x14002c0a8`
- `0x14005ecec`
- `0x14005f5c8`
- `0x14005fb20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14005f631`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14005f643`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14005f631`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14005f643`
- `WS2_32!__imp_closesocket` at `0x14005f653`
- `WS2_32!__imp_closesocket` at `0x14005f663`
- `WS2_32!__imp_closesocket` at `0x14005f653`
- `WS2_32!__imp_closesocket` at `0x14005f663`
- `WS2_32!__imp_WSACleanup` at `0x14005f5ed`
- `WS2_32!__imp_WSACleanup` at `0x14005f5ed`

## pseudocode

```c
void __fastcall SocketTransport::~SocketTransport(void **this)
{
  struct _TP_IO *v2; // rcx
  struct _TP_IO *v3; // rcx
  SOCKET v4; // rcx
  SOCKET v5; // rcx

  *this = &SocketTransport::`vftable';
  SocketTransport::Close((SocketTransport *)this);
  if ( *((_BYTE *)this + 384) )
    WSACleanup();
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>(
    this + 30,
    this + 30,
    *((_QWORD *)this[30] + 1));
  operator delete(this[30], 0x38u);
  std::vector<unsigned char>::~vector<unsigned char>(this + 19);
  v2 = (struct _TP_IO *)this[17];
  if ( v2 )
    CloseThreadpoolIo(v2);
  v3 = (struct _TP_IO *)this[16];
  if ( v3 )
    CloseThreadpoolIo(v3);
  v4 = (SOCKET)this[15];
  if ( v4 != -1 )
    closesocket(v4);
  v5 = (SOCKET)this[14];
  if ( v5 != -1 )
    closesocket(v5);
  *this = &Transport::`vftable';
}

```

## disassembly

```asm
0x14005f5c8  mov     [rsp+arg_8], rbx
0x14005f5cd  push    rdi
0x14005f5ce  sub     rsp, 20h
0x14005f5d2  lea     rax, ??_7SocketTransport@@6B@; const SocketTransport::`vftable'
0x14005f5d9  mov     rdi, rcx
0x14005f5dc  mov     [rcx], rax
0x14005f5df  call    ?Close@SocketTransport@@UEAAXXZ; SocketTransport::Close(void)
0x14005f5e4  cmp     byte ptr [rdi+180h], 0
0x14005f5eb  jz      short loc_14005F5F3
0x14005f5ed  call    cs:__imp_WSACleanup
0x14005f5f3  lea     rbx, [rdi+0F0h]
0x14005f5fa  mov     r8, [rbx]
0x14005f5fd  mov     rdx, rbx
0x14005f600  mov     rcx, rbx
0x14005f603  mov     r8, [r8+8]
0x14005f607  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *> *)
0x14005f60c  mov     rcx, [rbx]; void *
0x14005f60f  mov     edx, 38h ; '8'; unsigned __int64
0x14005f614  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14005f619  lea     rcx, [rdi+98h]
0x14005f620  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14005f625  mov     rcx, [rdi+88h]; pio
0x14005f62c  test    rcx, rcx
0x14005f62f  jz      short loc_14005F637
0x14005f631  call    cs:__imp_CloseThreadpoolIo
0x14005f637  mov     rcx, [rdi+80h]; pio
0x14005f63e  test    rcx, rcx
0x14005f641  jz      short loc_14005F649
0x14005f643  call    cs:__imp_CloseThreadpoolIo
0x14005f649  mov     rcx, [rdi+78h]; s
0x14005f64d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14005f651  jz      short loc_14005F659
0x14005f653  call    cs:__imp_closesocket
0x14005f659  mov     rcx, [rdi+70h]; s
0x14005f65d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14005f661  jz      short loc_14005F669
0x14005f663  call    cs:__imp_closesocket
0x14005f669  mov     rbx, [rsp+28h+arg_8]
0x14005f66e  lea     rax, ??_7Transport@@6B@; const Transport::`vftable'
0x14005f675  mov     [rdi], rax
0x14005f678  add     rsp, 20h
0x14005f67c  pop     rdi
0x14005f67d  retn
```

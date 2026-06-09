# p9fs::Plan9FileSystem::Plan9FileSystem(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> &&)

- ea: `0x180023f74`
- end: `0x180024117`
- name: `??0Plan9FileSystem@p9fs@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800288d0`

## callees

- `0x180004144`
- `0x180023f74`
- `0x1800286fc`
- `0x18002a5d8`
- `0x18002b720`
- `0x180034010`

## import_xrefs

- `WS2_32!__imp_listen` at `0x1800240e8`
- `WS2_32!__imp_listen` at `0x1800240e8`

## string_xrefs

- `0x180024102`: `onecore\vm\dv\storage\plan9\dll\windows\p9windows.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall p9fs::Plan9FileSystem::Plan9FileSystem(__int64 a1, void **a2)
{
  void *v4; // rdx
  _QWORD *v5; // rax
  unsigned __int64 v6; // rdx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPlan9FileSystem>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &p9fs::Plan9FileSystem::`vftable';
  v4 = *a2;
  *a2 = (void *)-1LL;
  *(_QWORD *)(a1 + 16) = &p9fs::Socket::`vftable';
  *(_QWORD *)(a1 + 24) = -1;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  p9fs::Socket::Reset((p9fs::Socket *)(a1 + 16), v4);
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 2;
  *(_OWORD *)(a1 + 96) = 0;
  *(_OWORD *)(a1 + 112) = 0;
  *(_OWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 144) = -1;
  *(_DWORD *)(a1 + 148) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_BYTE *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_OWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 184) = a1 + 176;
  *(_QWORD *)(a1 + 176) = a1 + 176;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 1;
  *(_QWORD *)(a1 + 224) = &p9fs::ShareList::`vftable';
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  v5 = operator new(0x50u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *(_QWORD *)(a1 + 240) = v5;
  *(_QWORD *)(a1 + 256) = 0;
  *(_BYTE *)(a1 + 264) = 1;
  *(_BYTE *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  if ( !*(_BYTE *)(a1 + 48) )
    p9fs::util::SetConnectedSuspendFlag(*(p9fs::util **)(a1 + 24), v6);
  if ( listen(*(_QWORD *)(a1 + 24), 1) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9windows.h",
      v7);
  return a1;
}

```

## disassembly

```asm
0x180023f74  mov     [rsp+arg_10], rbx
0x180023f79  push    rbp
0x180023f7a  push    rsi
0x180023f7b  push    rdi
0x180023f7c  sub     rsp, 30h
0x180023f80  mov     rbx, rdx
0x180023f83  mov     rdi, rcx
0x180023f86  mov     [rsp+48h+var_20], rcx
0x180023f8b  mov     dword ptr [rcx+0Ch], 1
0x180023f92  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPlan9FileSystem@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPlan9FileSystem>::`vftable'
0x180023f99  mov     [rcx], rax
0x180023f9c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180023fa3  xor     ebp, ebp
0x180023fa5  test    rcx, rcx
0x180023fa8  jz      short loc_180023FB7
0x180023faa  mov     rax, [rcx]
0x180023fad  mov     rax, [rax+8]
0x180023fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fb6  nop
0x180023fb7  lea     rax, ??_7Plan9FileSystem@p9fs@@6B@; const p9fs::Plan9FileSystem::`vftable'
0x180023fbe  mov     [rdi], rax
0x180023fc1  lea     rcx, [rdi+10h]; this
0x180023fc5  mov     [rsp+48h+var_28], rcx
0x180023fca  mov     rdx, [rbx]; unsigned __int64
0x180023fcd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023fd1  mov     [rbx], rsi
0x180023fd4  lea     rax, ??_7Socket@p9fs@@6B@; const p9fs::Socket::`vftable'
0x180023fdb  mov     [rcx], rax
0x180023fde  mov     [rcx+8], rsi
0x180023fe2  mov     [rcx+10h], rbp
0x180023fe6  mov     [rcx+18h], rbp
0x180023fea  mov     [rcx+20h], bpl
0x180023fee  call    ?Reset@Socket@p9fs@@QEAAX_K@Z; p9fs::Socket::Reset(unsigned __int64)
0x180023ff3  nop
0x180023ff4  mov     [rdi+38h], rbp
0x180023ff8  mov     [rdi+40h], rbp
0x180023ffc  mov     qword ptr [rdi+48h], 2
0x180024004  xorps   xmm0, xmm0
0x180024007  movups  xmmword ptr [rdi+60h], xmm0
0x18002400b  movups  xmmword ptr [rdi+70h], xmm0
0x18002400f  movups  xmmword ptr [rdi+80h], xmm0
0x180024016  mov     [rdi+50h], rbp
0x18002401a  mov     [rdi+58h], rbp
0x18002401e  mov     [rdi+90h], esi
0x180024024  mov     [rdi+94h], ebp
0x18002402a  mov     [rdi+98h], rbp
0x180024031  xor     eax, eax
0x180024033  mov     [rdi+0A0h], al
0x180024039  mov     [rdi+0A8h], rbp
0x180024040  lea     rax, [rdi+0B0h]
0x180024047  movups  xmmword ptr [rdi+0C0h], xmm0
0x18002404e  mov     [rax+8], rax
0x180024052  mov     [rax], rax
0x180024055  mov     [rdi+0D0h], rbp
0x18002405c  mov     qword ptr [rdi+0D8h], 1
0x180024067  lea     rax, ??_7ShareList@p9fs@@6B@; const p9fs::ShareList::`vftable'
0x18002406e  mov     [rdi+0E0h], rax
0x180024075  xor     eax, eax
0x180024077  mov     [rdi+0E8h], rax
0x18002407e  lea     rbx, [rdi+0F0h]
0x180024085  mov     [rbx], rbp
0x180024088  mov     [rbx+8], rbp
0x18002408c  lea     ecx, [rsi+51h]; Size
0x18002408f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024094  mov     [rax], rax
0x180024097  mov     [rax+8], rax
0x18002409b  mov     [rax+10h], rax
0x18002409f  mov     word ptr [rax+18h], 101h
0x1800240a5  mov     [rbx], rax
0x1800240a8  mov     [rdi+100h], rbp
0x1800240af  mov     byte ptr [rdi+108h], 1
0x1800240b6  mov     [rdi+110h], bpl
0x1800240bd  mov     [rdi+118h], rbp
0x1800240c4  mov     [rdi+120h], rbp
0x1800240cb  cmp     [rdi+30h], bpl
0x1800240cf  jnz     short loc_1800240DA
0x1800240d1  mov     rcx, [rdi+18h]; this
0x1800240d5  call    ?SetConnectedSuspendFlag@util@p9fs@@YAX_K@Z; p9fs::util::SetConnectedSuspendFlag(unsigned __int64)
0x1800240da  mov     rsi, [rsp+48h]
0x1800240df  mov     edx, 1; backlog
0x1800240e4  mov     rcx, [rdi+18h]; s
0x1800240e8  call    cs:__imp_listen
0x1800240ee  test    eax, eax
0x1800240f0  jnz     short loc_180024102
0x1800240f2  mov     rax, rdi
0x1800240f5  mov     rbx, [rsp+48h+arg_10]
0x1800240fa  add     rsp, 30h
0x1800240fe  pop     rdi
0x1800240ff  pop     rsi
0x180024100  pop     rbp
0x180024101  retn
0x180024102  lea     r8, aOnecoreVmDvSto_3; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180024109  mov     edx, 18h; void *
0x18002410e  mov     rcx, rsi; this
0x180024111  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

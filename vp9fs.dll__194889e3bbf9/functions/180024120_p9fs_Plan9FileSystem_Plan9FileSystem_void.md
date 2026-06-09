# p9fs::Plan9FileSystem::Plan9FileSystem(void)

- ea: `0x180024120`
- end: `0x1800242ea`
- name: `??0Plan9FileSystem@p9fs@@QEAA@XZ`
- size: `458`
- prototype: `__int64 __fastcall(p9fs::Plan9FileSystem *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025340`

## callees

- `0x180004120`
- `0x180004144`
- `0x180004c80`
- `0x18000ae8c`
- `0x180024120`
- `0x180034010`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x180024294`
- `WS2_32!__imp_WSAStartup` at `0x180024294`

## string_xrefs

- `0x1800242d8`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
p9fs::Plan9FileSystem *__fastcall p9fs::Plan9FileSystem::Plan9FileSystem(p9fs::Plan9FileSystem *this)
{
  _QWORD *v2; // rax
  unsigned int v3; // eax
  unsigned int v5; // [rsp+20h] [rbp-1C8h]
  WSAData WSAData; // [rsp+30h] [rbp-1B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v5 = (unsigned int)this;
  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPlan9FileSystem>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &p9fs::Plan9FileSystem::`vftable';
  *((_QWORD *)this + 2) = &p9fs::Socket::`vftable';
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_BYTE *)this + 48) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 2;
  *((_OWORD *)this + 6) = 0;
  *((_OWORD *)this + 7) = 0;
  *((_OWORD *)this + 8) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 36) = -1;
  *((_DWORD *)this + 37) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_BYTE *)this + 160) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_OWORD *)this + 12) = 0;
  *((_QWORD *)this + 23) = (char *)this + 176;
  *((_QWORD *)this + 22) = (char *)this + 176;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 1;
  *((_QWORD *)this + 28) = &p9fs::ShareList::`vftable';
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  v2 = operator new(0x50u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *((_QWORD *)this + 30) = v2;
  *((_QWORD *)this + 32) = 0;
  *((_BYTE *)this + 264) = 0;
  *((_BYTE *)this + 272) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v3 = WSAStartup(0x202u, &WSAData);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x267,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
      (const char *)v3,
      v5);
  *((_BYTE *)this + 272) = 1;
  return this;
}

```

## disassembly

```asm
0x180024120  mov     [rsp+arg_8], rbx
0x180024125  mov     [rsp+arg_10], rsi
0x18002412a  push    rdi
0x18002412b  sub     rsp, 1E0h
0x180024132  mov     rax, cs:__security_cookie
0x180024139  xor     rax, rsp
0x18002413c  mov     [rsp+1E8h+var_18], rax
0x180024144  mov     rdi, rcx
0x180024147  mov     qword ptr [rsp+1E8h+var_1C8], rcx; unsigned int
0x18002414c  mov     dword ptr [rcx+0Ch], 1
0x180024153  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPlan9FileSystem@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPlan9FileSystem>::`vftable'
0x18002415a  mov     [rcx], rax
0x18002415d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180024164  xor     esi, esi
0x180024166  test    rcx, rcx
0x180024169  jz      short loc_180024178
0x18002416b  mov     rax, [rcx]
0x18002416e  mov     rax, [rax+8]
0x180024172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024177  nop
0x180024178  lea     rax, ??_7Plan9FileSystem@p9fs@@6B@; const p9fs::Plan9FileSystem::`vftable'
0x18002417f  mov     [rdi], rax
0x180024182  lea     rax, ??_7Socket@p9fs@@6B@; const p9fs::Socket::`vftable'
0x180024189  mov     [rdi+10h], rax
0x18002418d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180024191  mov     [rdi+18h], rcx
0x180024195  mov     [rdi+20h], rsi
0x180024199  mov     [rdi+28h], rsi
0x18002419d  mov     [rdi+30h], sil
0x1800241a1  mov     [rdi+38h], rsi
0x1800241a5  mov     [rdi+40h], rsi
0x1800241a9  mov     qword ptr [rdi+48h], 2
0x1800241b1  xorps   xmm0, xmm0
0x1800241b4  movups  xmmword ptr [rdi+60h], xmm0
0x1800241b8  movups  xmmword ptr [rdi+70h], xmm0
0x1800241bc  movups  xmmword ptr [rdi+80h], xmm0
0x1800241c3  mov     [rdi+50h], rsi
0x1800241c7  mov     [rdi+58h], rsi
0x1800241cb  mov     [rdi+90h], ecx
0x1800241d1  mov     [rdi+94h], esi
0x1800241d7  mov     [rdi+98h], rsi
0x1800241de  xor     eax, eax
0x1800241e0  mov     [rdi+0A0h], al
0x1800241e6  mov     [rdi+0A8h], rsi
0x1800241ed  lea     rax, [rdi+0B0h]
0x1800241f4  movups  xmmword ptr [rdi+0C0h], xmm0
0x1800241fb  mov     [rax+8], rax
0x1800241ff  mov     [rax], rax
0x180024202  mov     [rdi+0D0h], rsi
0x180024209  mov     qword ptr [rdi+0D8h], 1
0x180024214  lea     rax, ??_7ShareList@p9fs@@6B@; const p9fs::ShareList::`vftable'
0x18002421b  mov     [rdi+0E0h], rax
0x180024222  xor     eax, eax
0x180024224  mov     [rdi+0E8h], rax
0x18002422b  lea     rbx, [rdi+0F0h]
0x180024232  mov     [rbx], rsi
0x180024235  mov     [rbx+8], rsi
0x180024239  lea     ecx, [rax+50h]; Size
0x18002423c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024241  mov     [rax], rax
0x180024244  mov     [rax+8], rax
0x180024248  mov     [rax+10h], rax
0x18002424c  mov     word ptr [rax+18h], 101h
0x180024252  mov     [rbx], rax
0x180024255  mov     [rdi+100h], rsi
0x18002425c  mov     [rdi+108h], sil
0x180024263  mov     [rdi+110h], sil
0x18002426a  mov     [rdi+118h], rsi
0x180024271  mov     [rdi+120h], rsi
0x180024278  xor     edx, edx; Val
0x18002427a  mov     r8d, 198h; Size
0x180024280  lea     rcx, [rsp+1E8h+WSAData]; void *
0x180024285  call    memset_0
0x18002428a  mov     ecx, 202h; wVersionRequested
0x18002428f  lea     rdx, [rsp+1E8h+WSAData]; lpWSAData
0x180024294  call    cs:__imp_WSAStartup
0x18002429a  mov     rcx, [rsp+1E8h]; this
0x1800242a2  test    eax, eax
0x1800242a4  jnz     short loc_1800242D5
0x1800242a6  mov     byte ptr [rdi+110h], 1
0x1800242ad  mov     rax, rdi
0x1800242b0  mov     rcx, [rsp+1E8h+var_18]
0x1800242b8  xor     rcx, rsp; StackCookie
0x1800242bb  call    __security_check_cookie
0x1800242c0  lea     r11, [rsp+1E8h+var_8]
0x1800242c8  mov     rbx, [r11+18h]
0x1800242cc  mov     rsi, [r11+20h]
0x1800242d0  mov     rsp, r11
0x1800242d3  pop     rdi
0x1800242d4  retn
0x1800242d5  mov     r9d, eax; char *
0x1800242d8  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x1800242df  mov     edx, 267h; void *
0x1800242e4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```

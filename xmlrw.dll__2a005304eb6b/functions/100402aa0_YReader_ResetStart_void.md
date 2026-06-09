# YReader::ResetStart(void)

- ea: `0x100402aa0`
- end: `0x100402d7e`
- name: `?ResetStart@YReader@@AEAAXXZ`
- size: `734`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x100402f30`

## callees

- `0x100402aa0`
- `0x100415ce0`
- `0x100416b40`
- `0x100423650`
- `0x1004277a0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100402b48`
- `KERNEL32!HeapFree` at `0x100402b48`
- `KERNEL32!GetTickCount` at `0x100402c05`
- `KERNEL32!GetTickCount` at `0x100402c05`

## pseudocode

```c
void __fastcall YReader::ResetStart(YReader *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void *v3; // r8
  struct IMalloc *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  void *v8; // rcx
  DWORD TickCount; // eax
  struct IMalloc *v10; // rdx
  __int128 v11; // xmm0
  __int128 v12; // [rsp+20h] [rbp-18h]

  while ( *((_DWORD *)this + 20) )
  {
    v2 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 9) + 8LL * (unsigned int)--*((_DWORD *)this + 20));
    if ( v2 )
      (**v2)(v2, 1);
  }
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_DWORD *)this + 64) = 0;
  v3 = (void *)*((_QWORD *)this + 45);
  if ( v3 )
  {
    v4 = (struct IMalloc *)*((_QWORD *)this + 44);
    if ( v4 || (v4 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v4->lpVtbl->Free)(v4, *((_QWORD *)this + 45));
    else
      HeapFree(g_hHeap, 0, v3);
    *((_QWORD *)this + 45) = 0;
    *((_DWORD *)this + 92) = 0;
  }
  *(_QWORD *)(*((_QWORD *)this + 54) + 16LL) = *((_QWORD *)this + 54) + 32LL;
  *((_QWORD *)this + 55) = *((_QWORD *)this + 54);
  LODWORD(v5) = *((_DWORD *)this + 118);
  while ( (_DWORD)v5 )
  {
    v6 = *((_QWORD *)this + 58);
    v5 = (unsigned int)(v5 - 1);
    *((_DWORD *)this + 118) = v5;
    v7 = *(void (__fastcall ****)(_QWORD, __int64))(v6 + 8 * v5);
    if ( v7 )
    {
      (**v7)(v7, 1);
      LODWORD(v5) = *((_DWORD *)this + 118);
    }
  }
  while ( *((_DWORD *)this + 140) > 2u )
    NamespaceSupport::PopPrefix((YReader *)((char *)this + 512));
  v8 = (void *)*((_QWORD *)this + 153);
  if ( v8 )
  {
    memset(v8, 0, 24LL * *((unsigned int *)this + 310));
    *((_DWORD *)this + 309) = 0;
  }
  TickCount = GetTickCount();
  *((_DWORD *)this + 308) = TickCount ^ ((TickCount ^ (TickCount << 7)) << 11);
  *((_BYTE *)this + 1248) = 0;
  *((_DWORD *)this + 132) = 1;
  _htable<DeclNotation>::reset((char *)this + 1336);
  _htable<DeclNotation>::reset((char *)this + 1376);
  _htable<DeclNotation>::reset((char *)this + 1416);
  _htable<DeclNotation>::reset((char *)this + 1456);
  (*(void (__fastcall **)(char *, void *))(*((_QWORD *)this + 157) + 16LL))((char *)this + 1256, &CodeStringPtr::empty);
  (*(void (__fastcall **)(char *, void *))(*((_QWORD *)this + 157) + 32LL))((char *)this + 1256, &CodeStringPtr::empty);
  (*(void (__fastcall **)(char *, void *))(*((_QWORD *)this + 157) + 48LL))((char *)this + 1256, &CodeStringPtr::empty);
  (*(void (__fastcall **)(char *, void *))(*((_QWORD *)this + 157) + 64LL))((char *)this + 1256, &CodeStringPtr::empty);
  v10 = (struct IMalloc *)*((_QWORD *)this + 1);
  *(_QWORD *)&v12 = YReader::ParseError;
  DWORD2(v12) = 0;
  v11 = v12;
  *(_QWORD *)&v12 = YReader::ParseElementN;
  DWORD2(v12) = 0;
  *((_OWORD *)this + 94) = v11;
  *((_DWORD *)this + 445) = 1;
  *((_DWORD *)this + 444) = 0;
  *((_OWORD *)this + 96) = v12;
  CloneStringPtr::Reset((YReader *)((char *)this + 1744), v10);
  CloneStringPtr::Reset((YReader *)((char *)this + 1760), *((struct IMalloc **)this + 1));
  *((_BYTE *)this + 1787) = 0;
  *(_WORD *)((char *)this + 1793) = 0;
  *((_BYTE *)this + 1795) = 0;
  *((_DWORD *)this + 464) = 0;
  *((_DWORD *)this + 472) = 0;
  *((_QWORD *)this + 349) = 0;
  *((_QWORD *)this + 350) = 0;
  *((_DWORD *)this + 710) = 0;
  *((_DWORD *)this + 1326) = 0;
  *((_DWORD *)this + 1942) = 0;
  *((_DWORD *)this + 2046) = 0;
  *((_BYTE *)this + 1784) = 1;
}

```

## disassembly

```asm
0x100402aa0  mov     [rsp+arg_0], rbx
0x100402aa5  mov     [rsp+arg_8], rsi
0x100402aaa  push    rdi
0x100402aab  sub     rsp, 30h
0x100402aaf  cmp     dword ptr [rcx+50h], 0
0x100402ab3  mov     rbx, rcx
0x100402ab6  jz      short loc_100402AEA
0x100402ab8  nop     dword ptr [rax+rax+00000000h]
0x100402ac0  dec     dword ptr [rbx+50h]
0x100402ac3  mov     ecx, [rbx+50h]
0x100402ac6  mov     rax, [rbx+48h]
0x100402aca  mov     rcx, [rax+rcx*8]
0x100402ace  test    rcx, rcx
0x100402ad1  jz      short loc_100402AE4
0x100402ad3  mov     rax, [rcx]
0x100402ad6  mov     edx, 1
0x100402adb  mov     rax, [rax]
0x100402ade  call    cs:__guard_dispatch_icall_fptr
0x100402ae4  cmp     dword ptr [rbx+50h], 0
0x100402ae8  jnz     short loc_100402AC0
0x100402aea  xor     esi, esi
0x100402aec  mov     [rbx+68h], rsi
0x100402af0  mov     [rbx+90h], esi
0x100402af6  mov     [rbx+0D8h], rsi
0x100402afd  mov     [rbx+138h], esi
0x100402b03  mov     [rbx+100h], esi
0x100402b09  mov     r8, [rbx+168h]; lpMem
0x100402b10  test    r8, r8
0x100402b13  jz      short loc_100402B5B
0x100402b15  mov     rcx, [rbx+160h]
0x100402b1c  test    rcx, rcx
0x100402b1f  jnz     short loc_100402B2D
0x100402b21  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100402b28  test    rcx, rcx
0x100402b2b  jz      short loc_100402B3F
0x100402b2d  mov     rax, [rcx]
0x100402b30  mov     rdx, r8
0x100402b33  mov     rax, [rax+28h]
0x100402b37  call    cs:__guard_dispatch_icall_fptr
0x100402b3d  jmp     short loc_100402B4E
0x100402b3f  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100402b46  xor     edx, edx; dwFlags
0x100402b48  call    cs:__imp_HeapFree
0x100402b4e  mov     [rbx+168h], rsi
0x100402b55  mov     [rbx+170h], esi
0x100402b5b  mov     rcx, [rbx+1B0h]
0x100402b62  lea     rax, [rcx+20h]
0x100402b66  mov     [rcx+10h], rax
0x100402b6a  mov     rax, [rbx+1B0h]
0x100402b71  mov     [rbx+1B8h], rax
0x100402b78  mov     edx, [rbx+1D8h]
0x100402b7e  test    edx, edx
0x100402b80  jz      short loc_100402BC3
0x100402b82  nop     dword ptr [rax+00h]
0x100402b86  nop     word ptr [rax+rax+00000000h]
0x100402b90  mov     rax, [rbx+1D0h]
0x100402b97  dec     edx
0x100402b99  mov     [rbx+1D8h], edx
0x100402b9f  mov     rcx, [rax+rdx*8]
0x100402ba3  test    rcx, rcx
0x100402ba6  jz      short loc_100402BBF
0x100402ba8  mov     rax, [rcx]
0x100402bab  mov     edx, 1
0x100402bb0  mov     rax, [rax]
0x100402bb3  call    cs:__guard_dispatch_icall_fptr
0x100402bb9  mov     edx, [rbx+1D8h]
0x100402bbf  test    edx, edx
0x100402bc1  jnz     short loc_100402B90
0x100402bc3  lea     rdi, [rbx+200h]
0x100402bca  cmp     dword ptr [rdi+30h], 2
0x100402bce  jbe     short loc_100402BDE
0x100402bd0  mov     rcx, rdi; this
0x100402bd3  call    ?PopPrefix@NamespaceSupport@@AEAAXXZ; NamespaceSupport::PopPrefix(void)
0x100402bd8  cmp     dword ptr [rdi+30h], 2
0x100402bdc  ja      short loc_100402BD0
0x100402bde  mov     rcx, [rdi+2C8h]; void *
0x100402be5  test    rcx, rcx
0x100402be8  jz      short loc_100402C05
0x100402bea  mov     eax, [rdi+2D8h]
0x100402bf0  xor     edx, edx; Val
0x100402bf2  lea     r8, [rax+rax*2]
0x100402bf6  shl     r8, 3; Size
0x100402bfa  call    memset
0x100402bff  mov     [rdi+2D4h], esi
0x100402c05  call    cs:__imp_GetTickCount
0x100402c0b  mov     ecx, eax
0x100402c0d  shl     ecx, 7
0x100402c10  xor     ecx, eax
0x100402c12  shl     ecx, 0Bh
0x100402c15  xor     ecx, eax
0x100402c17  mov     [rdi+2D0h], ecx
0x100402c1d  mov     [rdi+2E0h], sil
0x100402c24  mov     dword ptr [rdi+10h], 1
0x100402c2b  lea     rdi, [rbx+4E8h]
0x100402c32  lea     rcx, [rdi+50h]
0x100402c36  call    ?reset@?$_htable@VDeclNotation@@@@QEAAXXZ; _htable<DeclNotation>::reset(void)
0x100402c3b  lea     rcx, [rdi+78h]
0x100402c3f  call    ?reset@?$_htable@VDeclNotation@@@@QEAAXXZ; _htable<DeclNotation>::reset(void)
0x100402c44  lea     rcx, [rdi+0A0h]
0x100402c4b  call    ?reset@?$_htable@VDeclNotation@@@@QEAAXXZ; _htable<DeclNotation>::reset(void)
0x100402c50  lea     rcx, [rdi+0C8h]
0x100402c57  call    ?reset@?$_htable@VDeclNotation@@@@QEAAXXZ; _htable<DeclNotation>::reset(void)
0x100402c5c  mov     rax, [rdi]
0x100402c5f  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100402c66  mov     rcx, rdi
0x100402c69  mov     rax, [rax+10h]
0x100402c6d  call    cs:__guard_dispatch_icall_fptr
0x100402c73  mov     rax, [rdi]
0x100402c76  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100402c7d  mov     rcx, rdi
0x100402c80  mov     rax, [rax+20h]
0x100402c84  call    cs:__guard_dispatch_icall_fptr
0x100402c8a  mov     rax, [rdi]
0x100402c8d  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100402c94  mov     rcx, rdi
0x100402c97  mov     rax, [rax+30h]
0x100402c9b  call    cs:__guard_dispatch_icall_fptr
0x100402ca1  mov     rax, [rdi]
0x100402ca4  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100402cab  mov     rcx, rdi
0x100402cae  mov     rax, [rax+40h]
0x100402cb2  call    cs:__guard_dispatch_icall_fptr
0x100402cb8  mov     rdx, [rbx+8]; struct IMalloc *
0x100402cbc  lea     rax, ?ParseError@YReader@@AEAAXXZ; YReader::ParseError(void)
0x100402cc3  mov     qword ptr [rsp+38h+var_18], rax
0x100402cc8  lea     rcx, [rbx+6D0h]; this
0x100402ccf  mov     dword ptr [rsp+38h+var_18+8], esi
0x100402cd3  lea     rax, ?ParseElementN@YReader@@AEAAXXZ; YReader::ParseElementN(void)
0x100402cda  movups  xmm0, [rsp+38h+var_18]
0x100402cdf  mov     qword ptr [rsp+38h+var_18], rax
0x100402ce4  mov     dword ptr [rsp+38h+var_18+8], esi
0x100402ce8  movups  xmmword ptr [rbx+5E0h], xmm0
0x100402cef  mov     dword ptr [rbx+6F4h], 1
0x100402cf9  movups  xmm0, [rsp+38h+var_18]
0x100402cfe  mov     [rbx+6F0h], esi
0x100402d04  movups  xmmword ptr [rbx+600h], xmm0
0x100402d0b  call    ?Reset@CloneStringPtr@@QEAAXPEAUIMalloc@@@Z; CloneStringPtr::Reset(IMalloc *)
0x100402d10  mov     rdx, [rbx+8]; struct IMalloc *
0x100402d14  lea     rcx, [rbx+6E0h]; this
0x100402d1b  call    ?Reset@CloneStringPtr@@QEAAXPEAUIMalloc@@@Z; CloneStringPtr::Reset(IMalloc *)
0x100402d20  mov     [rbx+6FBh], sil
0x100402d27  mov     [rbx+701h], si
0x100402d2e  mov     [rbx+703h], sil
0x100402d35  mov     [rbx+740h], esi
0x100402d3b  mov     [rbx+760h], esi
0x100402d41  mov     [rbx+0AE8h], rsi
0x100402d48  mov     [rbx+0AF0h], rsi
0x100402d4f  mov     [rbx+0B18h], esi
0x100402d55  mov     [rbx+14B8h], esi
0x100402d5b  mov     [rbx+1E58h], esi
0x100402d61  mov     [rbx+1FF8h], esi
0x100402d67  mov     rsi, [rsp+38h+arg_8]
0x100402d6c  mov     byte ptr [rbx+6F8h], 1
0x100402d73  mov     rbx, [rsp+38h+arg_0]
0x100402d78  add     rsp, 30h
0x100402d7c  pop     rdi
0x100402d7d  retn
```

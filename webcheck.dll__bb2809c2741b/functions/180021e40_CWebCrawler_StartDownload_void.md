# CWebCrawler::StartDownload(void)

- ea: `0x180021e40`
- end: `0x180022116`
- name: `?StartDownload@CWebCrawler@@MEAAJXZ`
- size: `726`
- prototype: `__int64 __fastcall(CWebCrawler *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000597c`
- `0x18001ba08`
- `0x180021e40`
- `0x18002211c`
- `0x18002924e`
- `0x18002a010`

## import_xrefs

- `WININET!CreateUrlCacheGroup` at `0x180021e9c`
- `WININET!CreateUrlCacheGroup` at `0x180021e9c`

## pseudocode

```c
__int64 __fastcall CWebCrawler::StartDownload(CWebCrawler *this)
{
  bool v2; // zf
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  CUrlDownload *v11; // rax
  CUrlDownload *v12; // rax

  v2 = (*((_DWORD *)this + 11) & 0x200000) == 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 64) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_DWORD *)this + 94) = 0;
  if ( v2 )
  {
    if ( !*((_QWORD *)this + 34) )
      *((_QWORD *)this + 34) = CreateUrlCacheGroup((*((_DWORD *)this + 34) & 1) == 0, 0);
  }
  else
  {
    *((_QWORD *)this + 34) = 0;
  }
  v3 = operator new(0x438u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *((_DWORD *)v3 + 4) = 0;
    v3[4] = 0;
    v3[3] = 0;
    v3[5] = 0;
    memset_0(v3 + 6, 0, 0x3F8u);
    *v4 = &CWCDwordStringList::`vftable';
    v4[134] = 0;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 20) = v4;
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v4 + 8LL))(v4, *((_DWORD *)this + 35) != 0 ? -1 : 512);
  else
    *((_DWORD *)this + 27) = -2147467259;
  if ( *((_DWORD *)this + 35) && *((char *)this + 136) >= 0 )
  {
    v5 = operator new(0x438u);
    v6 = v5;
    if ( v5 )
    {
      v5[1] = 0;
      *((_DWORD *)v5 + 4) = 0;
      v5[4] = 0;
      v5[3] = 0;
      v5[5] = 0;
      memset_0(v5 + 6, 0, 0x3F8u);
      *v6 = &CWCDwordStringList::`vftable';
      v6[134] = 0;
    }
    else
    {
      v6 = 0;
    }
    *((_QWORD *)this + 21) = v6;
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v6 + 8LL))(v6, 512);
    else
      *((_DWORD *)this + 27) = -2147467259;
  }
  v7 = operator new(0x438u);
  v8 = v7;
  if ( v7 )
  {
    v7[1] = 0;
    *((_DWORD *)v7 + 4) = 0;
    v7[4] = 0;
    v7[3] = 0;
    v7[5] = 0;
    memset_0(v7 + 6, 0, 0x3F8u);
    *v8 = &CWCDwordStringList::`vftable';
    v8[134] = 0;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 24) = v8;
  if ( v8 )
    (*(void (__fastcall **)(_QWORD *, __int64))(*v8 + 8LL))(v8, 512);
  else
    *((_DWORD *)this + 27) = -2147467259;
  if ( (*((_DWORD *)this + 11) & 0x200000) == 0 )
  {
    v9 = operator new(0x438u);
    v10 = v9;
    if ( v9 )
    {
      v9[1] = 0;
      *((_DWORD *)v9 + 4) = 0;
      v9[4] = 0;
      v9[3] = 0;
      v9[5] = 0;
      memset_0(v9 + 6, 0, 0x3F8u);
      *v10 = &CWCDwordStringList::`vftable';
      v10[134] = 0;
    }
    else
    {
      v10 = 0;
    }
    *((_QWORD *)this + 31) = v10;
    if ( v10 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v10 + 8LL))(v10, 0xFFFFFFFFLL);
    else
      *((_DWORD *)this + 27) = -2147467259;
  }
  if ( *((_DWORD *)this + 27) != -2147467259 )
  {
    v11 = (CUrlDownload *)operator new(0x318u);
    if ( v11 )
      v12 = CUrlDownload::CUrlDownload(
              v11,
              (struct CUrlDownloadSink *)(((unsigned __int64)this + 112) & -(__int64)(this != 0)),
              (int)this + 112);
    else
      v12 = 0;
    *((_QWORD *)this + 43) = v12;
    if ( !v12 )
      return 2147942414LL;
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 20) + 16LL))(
           *((_QWORD *)this + 20),
           *((_QWORD *)this + 16),
           *((unsigned int *)this + 35),
           0) == 2
      && *(_DWORD *)(*((_QWORD *)this + 20) + 12LL) == 1 )
    {
      return CWebCrawler::StartNextDownload(this);
    }
    *((_DWORD *)this + 27) = -2147467259;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180021e40  push    rbx
0x180021e42  push    rbp
0x180021e43  push    rsi
0x180021e44  push    rdi
0x180021e45  push    r12
0x180021e47  push    r14
0x180021e49  push    r15
0x180021e4b  sub     rsp, 30h
0x180021e4f  xor     esi, esi
0x180021e51  mov     rbx, rcx
0x180021e54  test    dword ptr [rcx+2Ch], 200000h
0x180021e5b  mov     [rcx+128h], rsi
0x180021e62  mov     [rcx+130h], rsi
0x180021e69  mov     [rcx+100h], esi
0x180021e6f  mov     [rcx+138h], esi
0x180021e75  mov     [rcx+178h], esi
0x180021e7b  jz      short loc_180021E86
0x180021e7d  mov     [rcx+110h], rsi
0x180021e84  jmp     short loc_180021EA9
0x180021e86  cmp     [rcx+110h], rsi
0x180021e8d  jnz     short loc_180021EA9
0x180021e8f  mov     ecx, [rcx+88h]
0x180021e95  xor     edx, edx; lpReserved
0x180021e97  not     ecx
0x180021e99  and     ecx, 1; dwFlags
0x180021e9c  call    cs:__imp_CreateUrlCacheGroup
0x180021ea2  mov     [rbx+110h], rax
0x180021ea9  mov     r14d, 438h
0x180021eaf  mov     ecx, r14d; dwBytes
0x180021eb2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021eb7  lea     r15d, [r14-40h]
0x180021ebb  mov     rdi, rax
0x180021ebe  lea     r12, ??_7CWCDwordStringList@@6B@; const CWCDwordStringList::`vftable'
0x180021ec5  test    rax, rax
0x180021ec8  jz      short loc_180021EF7
0x180021eca  lea     rcx, [rax+30h]; void *
0x180021ece  mov     [rax+8], rsi
0x180021ed2  mov     r8d, r15d; Size
0x180021ed5  mov     [rax+10h], esi
0x180021ed8  xor     edx, edx; Val
0x180021eda  mov     [rax+20h], rsi
0x180021ede  mov     [rax+18h], rsi
0x180021ee2  mov     [rax+28h], rsi
0x180021ee6  call    memset_0
0x180021eeb  mov     [rdi], r12
0x180021eee  mov     [rdi+430h], rsi
0x180021ef5  jmp     short loc_180021EFA
0x180021ef7  mov     rdi, rsi
0x180021efa  mov     [rbx+0A0h], rdi
0x180021f01  mov     ebp, 80004005h
0x180021f06  test    rdi, rdi
0x180021f09  jz      short loc_180021F30
0x180021f0b  mov     eax, [rbx+8Ch]
0x180021f11  mov     rcx, rdi
0x180021f14  mov     r8, [rdi]
0x180021f17  neg     eax
0x180021f19  sbb     edx, edx
0x180021f1b  btr     edx, 9
0x180021f1f  mov     rax, [r8+8]
0x180021f23  add     edx, 200h
0x180021f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f2e  jmp     short loc_180021F33
0x180021f30  mov     [rbx+6Ch], ebp
0x180021f33  cmp     [rbx+8Ch], esi
0x180021f39  jz      short loc_180021FA9
0x180021f3b  test    byte ptr [rbx+88h], 80h
0x180021f42  jnz     short loc_180021FA9
0x180021f44  mov     rcx, r14; dwBytes
0x180021f47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021f4c  mov     rdi, rax
0x180021f4f  test    rax, rax
0x180021f52  jz      short loc_180021F81
0x180021f54  lea     rcx, [rax+30h]; void *
0x180021f58  mov     [rax+8], rsi
0x180021f5c  mov     r8, r15; Size
0x180021f5f  mov     [rax+10h], esi
0x180021f62  xor     edx, edx; Val
0x180021f64  mov     [rax+20h], rsi
0x180021f68  mov     [rax+18h], rsi
0x180021f6c  mov     [rax+28h], rsi
0x180021f70  call    memset_0
0x180021f75  mov     [rdi], r12
0x180021f78  mov     [rdi+430h], rsi
0x180021f7f  jmp     short loc_180021F84
0x180021f81  mov     rdi, rsi
0x180021f84  mov     [rbx+0A8h], rdi
0x180021f8b  test    rdi, rdi
0x180021f8e  jz      short loc_180021FA6
0x180021f90  mov     rax, [rdi]
0x180021f93  mov     edx, 200h
0x180021f98  mov     rcx, rdi
0x180021f9b  mov     rax, [rax+8]
0x180021f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fa4  jmp     short loc_180021FA9
0x180021fa6  mov     [rbx+6Ch], ebp
0x180021fa9  mov     rcx, r14; dwBytes
0x180021fac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021fb1  mov     rdi, rax
0x180021fb4  test    rax, rax
0x180021fb7  jz      short loc_180021FE6
0x180021fb9  lea     rcx, [rax+30h]; void *
0x180021fbd  mov     [rax+8], rsi
0x180021fc1  mov     r8, r15; Size
0x180021fc4  mov     [rax+10h], esi
0x180021fc7  xor     edx, edx; Val
0x180021fc9  mov     [rax+20h], rsi
0x180021fcd  mov     [rax+18h], rsi
0x180021fd1  mov     [rax+28h], rsi
0x180021fd5  call    memset_0
0x180021fda  mov     [rdi], r12
0x180021fdd  mov     [rdi+430h], rsi
0x180021fe4  jmp     short loc_180021FE9
0x180021fe6  mov     rdi, rsi
0x180021fe9  mov     [rbx+0C0h], rdi
0x180021ff0  test    rdi, rdi
0x180021ff3  jz      short loc_18002200B
0x180021ff5  mov     rax, [rdi]
0x180021ff8  mov     edx, 200h
0x180021ffd  mov     rcx, rdi
0x180022000  mov     rax, [rax+8]
0x180022004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022009  jmp     short loc_18002200E
0x18002200b  mov     [rbx+6Ch], ebp
0x18002200e  test    dword ptr [rbx+2Ch], 200000h
0x180022015  jnz     short loc_18002207A
0x180022017  mov     rcx, r14; dwBytes
0x18002201a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002201f  mov     rdi, rax
0x180022022  test    rax, rax
0x180022025  jz      short loc_180022054
0x180022027  lea     rcx, [rax+30h]; void *
0x18002202b  mov     [rax+8], rsi
0x18002202f  mov     r8, r15; Size
0x180022032  mov     [rax+10h], esi
0x180022035  xor     edx, edx; Val
0x180022037  mov     [rax+20h], rsi
0x18002203b  mov     [rax+18h], rsi
0x18002203f  mov     [rax+28h], rsi
0x180022043  call    memset_0
0x180022048  mov     [rdi], r12
0x18002204b  mov     [rdi+430h], rsi
0x180022052  jmp     short loc_180022057
0x180022054  mov     rdi, rsi
0x180022057  mov     [rbx+0F8h], rdi
0x18002205e  test    rdi, rdi
0x180022061  jz      short loc_180022077
0x180022063  mov     rax, [rdi]
0x180022066  or      edx, 0FFFFFFFFh
0x180022069  mov     rcx, rdi
0x18002206c  mov     rax, [rax+8]
0x180022070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022075  jmp     short loc_18002207A
0x180022077  mov     [rbx+6Ch], ebp
0x18002207a  cmp     [rbx+6Ch], ebp
0x18002207d  jz      loc_180022105
0x180022083  mov     ecx, 318h; dwBytes
0x180022088  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002208d  test    rax, rax
0x180022090  jz      short loc_1800220AC
0x180022092  lea     r8, [rbx+70h]; unsigned int
0x180022096  mov     rcx, rbx
0x180022099  neg     rcx
0x18002209c  mov     rcx, rax; this
0x18002209f  sbb     rdx, rdx
0x1800220a2  and     rdx, r8; struct CUrlDownloadSink *
0x1800220a5  call    ??0CUrlDownload@@QEAA@PEAVCUrlDownloadSink@@I@Z; CUrlDownload::CUrlDownload(CUrlDownloadSink *,uint)
0x1800220aa  jmp     short loc_1800220AF
0x1800220ac  mov     rax, rsi
0x1800220af  mov     [rbx+158h], rax
0x1800220b6  test    rax, rax
0x1800220b9  jnz     short loc_1800220C2
0x1800220bb  mov     eax, 8007000Eh
0x1800220c0  jmp     short loc_180022107
0x1800220c2  mov     rcx, [rbx+0A0h]
0x1800220c9  xor     r9d, r9d
0x1800220cc  mov     r8d, [rbx+8Ch]
0x1800220d3  mov     rdx, [rbx+80h]
0x1800220da  mov     rax, [rcx]
0x1800220dd  mov     rax, [rax+10h]
0x1800220e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220e6  cmp     eax, 2
0x1800220e9  jnz     short loc_180022102
0x1800220eb  mov     rax, [rbx+0A0h]
0x1800220f2  cmp     dword ptr [rax+0Ch], 1
0x1800220f6  jnz     short loc_180022102
0x1800220f8  mov     rcx, rbx; this
0x1800220fb  call    ?StartNextDownload@CWebCrawler@@IEAAJXZ; CWebCrawler::StartNextDownload(void)
0x180022100  jmp     short loc_180022107
0x180022102  mov     [rbx+6Ch], ebp
0x180022105  mov     eax, ebp
0x180022107  add     rsp, 30h
0x18002210b  pop     r15
0x18002210d  pop     r14
0x18002210f  pop     r12
0x180022111  pop     rdi
0x180022112  pop     rsi
0x180022113  pop     rbp
0x180022114  pop     rbx
0x180022115  retn
```

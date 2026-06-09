# CHttp2::RemoveStream(CHttp2Stream *,ulong,long)

- ea: `0x18002f0d4`
- end: `0x18002f2fe`
- name: `?RemoveStream@CHttp2@@AEAAXPEAVCHttp2Stream@@KJ@Z`
- size: `554`
- prototype: `void __fastcall(CHttp2 *__hidden this, struct CHttp2Stream *, unsigned int, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18002f330`
- `0x180052198`
- `0x180067390`

## callees

- `0x18002d290`
- `0x18002db48`
- `0x18002eaf4`
- `0x18002eb98`
- `0x18002f0d4`
- `0x18002fc50`
- `0x180034ba4`
- `0x1800358d8`
- `0x18004f9f0`
- `0x180050870`
- `0x18006b430`
- `0x1800722f0`
- `0x180092500`
- `0x180092564`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f137`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1f4`

## pseudocode

```c
void __fastcall CHttp2::RemoveStream(CHttp2 *this, struct CHttp2Stream *a2, unsigned int a3, unsigned int a4)
{
  CHttp2SendContext *v4; // rbx
  int v5; // r14d
  int v6; // r15d
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  CHttp2 *v11; // rcx
  int v12; // r14d
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v14; // rax
  int v15; // eax
  struct CHttp2SendContext *v16; // rdx
  int v17; // [rsp+30h] [rbp-38h] BYREF
  struct CHttp2SendContext *v18; // [rsp+38h] [rbp-30h] BYREF
  int v19; // [rsp+44h] [rbp-24h]
  struct _LIST_ENTRY v20; // [rsp+48h] [rbp-20h] BYREF

  v4 = 0;
  v5 = 0;
  v20.Blink = &v20;
  v6 = 0;
  v19 = 0;
  v18 = 0;
  v20.Flink = &v20;
  v17 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( a3
    && (v15 = CHttp2::CreateResetStreamSendContext(this, *((_DWORD *)a2 + 4), a3, &v18), v4 = v18, v5 = v15, v15 < 0) )
  {
    v19 = 4365;
  }
  else
  {
    if ( v9 )
    {
      EnterCriticalSection(v9);
      v6 = 1;
    }
    if ( (int)CHttp2::IsAborted(this) >= 0 )
    {
      if ( v4 )
      {
        v16 = v4;
        v4 = 0;
        CHttp2::InsertSendContext(v11, v16);
        CHttp2::QueueSendProcessing(this);
      }
      CHttp2::RemoveStreamLocked(this, a2, a4, &v20, &v17);
    }
    if ( v9 && v6 )
    {
      LeaveCriticalSection(v9);
      v6 = 0;
    }
  }
  if ( v5 < 0 )
    CHttp2::Abort(this, v5);
  if ( v4 )
    CHttp2SendContext::Release(v4);
  v12 = WX_WIN32_FROM_HR(a4);
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_qD(1050, 44, WPP_1eba17a514423a0ebe5ee43bce786d1b_Traceguids, this, a4);
  while ( 1 )
  {
    Flink = v20.Flink;
    if ( v20.Flink == &v20 )
      break;
    if ( v20.Flink->Blink != &v20 || (v14 = v20.Flink->Flink, v20.Flink->Flink->Blink != v20.Flink) )
      __fastfail(3u);
    v20.Flink = v20.Flink->Flink;
    v14->Blink = &v20;
    Flink->Blink = Flink;
    Flink->Flink = Flink;
    CHttp2SendContext::CompleteIo((RTL_SRWLOCK *)&Flink[-1].Blink, v12);
    CHttp2SendContext::Release((CHttp2SendContext *)&Flink[-1].Blink);
  }
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_(1050, 45, WPP_1eba17a514423a0ebe5ee43bce786d1b_Traceguids);
  if ( v17 )
    CHttp2Stream::Release(a2);
  if ( v6 )
  {
    if ( v9 )
      LeaveCriticalSection(v9);
  }
}

```

## disassembly

```asm
0x18002f0d4  push    rbp
0x18002f0d6  push    rbx
0x18002f0d7  push    rsi
0x18002f0d8  push    rdi
0x18002f0d9  push    r12
0x18002f0db  push    r13
0x18002f0dd  push    r14
0x18002f0df  push    r15
0x18002f0e1  mov     rbp, rsp
0x18002f0e4  sub     rsp, 68h
0x18002f0e8  mov     rax, cs:__security_cookie
0x18002f0ef  xor     rax, rsp
0x18002f0f2  mov     [rbp+var_10], rax
0x18002f0f6  xor     ebx, ebx
0x18002f0f8  lea     rax, [rbp+var_20]
0x18002f0fc  xor     r14d, r14d
0x18002f0ff  mov     [rbp+var_20.Blink], rax
0x18002f103  xor     r15d, r15d
0x18002f106  mov     [rbp+var_24], r14d
0x18002f10a  mov     [rbp+var_30], rbx
0x18002f10e  lea     rax, [rbp+var_20]
0x18002f112  mov     [rbp+var_20.Flink], rax
0x18002f116  mov     r12d, r9d
0x18002f119  mov     [rbp+var_38], ebx
0x18002f11c  mov     r13, rdx
0x18002f11f  lea     rdi, [rcx+8]
0x18002f123  mov     rsi, rcx
0x18002f126  test    r8d, r8d
0x18002f129  jnz     loc_18002F25E
0x18002f12f  test    rdi, rdi
0x18002f132  jz      short loc_18002F149
0x18002f134  mov     rcx, rdi; lpCriticalSection
0x18002f137  call    cs:__imp_EnterCriticalSection
0x18002f13e  nop     dword ptr [rax+rax+00h]
0x18002f143  mov     r15d, 1
0x18002f149  mov     rcx, rsi; this
0x18002f14c  call    ?IsAborted@CHttp2@@AEAAJXZ; CHttp2::IsAborted(void)
0x18002f151  test    eax, eax
0x18002f153  js      short loc_18002F179
0x18002f155  test    rbx, rbx
0x18002f158  jnz     loc_18002F285
0x18002f15e  lea     rax, [rbp+var_38]
0x18002f162  mov     r8d, r12d; int
0x18002f165  lea     r9, [rbp+var_20]; struct _LIST_ENTRY *
0x18002f169  mov     [rsp+68h+var_48], rax; int *
0x18002f16e  mov     rdx, r13; struct CHttp2Stream *
0x18002f171  mov     rcx, rsi; this
0x18002f174  call    ?RemoveStreamLocked@CHttp2@@AEAAXPEAVCHttp2Stream@@JPEAU_LIST_ENTRY@@PEAH@Z; CHttp2::RemoveStreamLocked(CHttp2Stream *,long,_LIST_ENTRY *,int *)
0x18002f179  test    rdi, rdi
0x18002f17c  jz      short loc_18002F195
0x18002f17e  test    r15d, r15d
0x18002f181  jz      short loc_18002F195
0x18002f183  mov     rcx, rdi; lpCriticalSection
0x18002f186  call    cs:__imp_LeaveCriticalSection
0x18002f18d  nop     dword ptr [rax+rax+00h]
0x18002f192  xor     r15d, r15d
0x18002f195  test    r14d, r14d
0x18002f198  js      loc_18002F2A3
0x18002f19e  test    rbx, rbx
0x18002f1a1  jnz     loc_18002F2B3
0x18002f1a7  mov     ecx, r12d
0x18002f1aa  call    WX_WIN32_FROM_HR
0x18002f1af  mov     r14d, eax
0x18002f1b2  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002f1b9  jnz     loc_18002F2C0
0x18002f1bf  mov     rbx, [rbp+var_20.Flink]
0x18002f1c3  lea     rax, [rbp+var_20]
0x18002f1c7  cmp     rbx, rax
0x18002f1ca  jnz     short loc_18002F21E
0x18002f1cc  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002f1d3  jnz     loc_18002F2E3
0x18002f1d9  cmp     [rbp+var_38], 0
0x18002f1dd  jz      short loc_18002F1E7
0x18002f1df  mov     rcx, r13; this
0x18002f1e2  call    ?Release@CHttp2Stream@@QEAAKXZ; CHttp2Stream::Release(void)
0x18002f1e7  test    r15d, r15d
0x18002f1ea  jz      short loc_18002F200
0x18002f1ec  test    rdi, rdi
0x18002f1ef  jz      short loc_18002F200
0x18002f1f1  mov     rcx, rdi; lpCriticalSection
0x18002f1f4  call    cs:__imp_LeaveCriticalSection
0x18002f1fb  nop     dword ptr [rax+rax+00h]
0x18002f200  mov     rcx, [rbp+var_10]
0x18002f204  xor     rcx, rsp; StackCookie
0x18002f207  call    __security_check_cookie
0x18002f20c  add     rsp, 68h
0x18002f210  pop     r15
0x18002f212  pop     r14
0x18002f214  pop     r13
0x18002f216  pop     r12
0x18002f218  pop     rdi
0x18002f219  pop     rsi
0x18002f21a  pop     rbx
0x18002f21b  pop     rbp
0x18002f21c  retn
0x18002f21e  lea     rax, [rbp+var_20]
0x18002f222  cmp     [rbx+8], rax
0x18002f226  jnz     short loc_18002F29C
0x18002f228  mov     rax, [rbx]
0x18002f22b  cmp     [rax+8], rbx
0x18002f22f  jnz     short loc_18002F29C
0x18002f231  mov     [rbp+var_20.Flink], rax
0x18002f235  lea     rcx, [rbp+var_20]
0x18002f239  mov     [rax+8], rcx
0x18002f23d  mov     edx, r14d; unsigned int
0x18002f240  lea     rcx, [rbx-8]; this
0x18002f244  mov     [rbx+8], rbx
0x18002f248  mov     [rbx], rbx
0x18002f24b  call    ?CompleteIo@CHttp2SendContext@@QEAAXK@Z; CHttp2SendContext::CompleteIo(ulong)
0x18002f250  lea     rcx, [rbx-8]; this
0x18002f254  call    ?Release@CHttp2SendContext@@QEAAKXZ; CHttp2SendContext::Release(void)
0x18002f259  jmp     loc_18002F1BF
0x18002f25e  mov     edx, [rdx+10h]; unsigned int
0x18002f261  lea     r9, [rbp+var_30]; struct CHttp2SendContext **
0x18002f265  call    ?CreateResetStreamSendContext@CHttp2@@AEAAJKKPEAPEAVCHttp2SendContext@@@Z; CHttp2::CreateResetStreamSendContext(ulong,ulong,CHttp2SendContext * *)
0x18002f26a  mov     rbx, [rbp+var_30]
0x18002f26e  mov     r14d, eax
0x18002f271  test    eax, eax
0x18002f273  jns     loc_18002F12F
0x18002f279  mov     [rbp+var_24], 110Dh
0x18002f280  jmp     loc_18002F195
0x18002f285  mov     rdx, rbx; struct CHttp2SendContext *
0x18002f288  xor     ebx, ebx
0x18002f28a  call    ?InsertSendContext@CHttp2@@AEAAXPEAVCHttp2SendContext@@@Z; CHttp2::InsertSendContext(CHttp2SendContext *)
0x18002f28f  mov     rcx, rsi; this
0x18002f292  call    ?QueueSendProcessing@CHttp2@@AEAAXXZ; CHttp2::QueueSendProcessing(void)
0x18002f297  jmp     loc_18002F15E
0x18002f29c  mov     ecx, 3
0x18002f2a1  int     29h; Win8: RtlFailFast(ecx)
0x18002f2a3  mov     edx, r14d; int
0x18002f2a6  mov     rcx, rsi; this
0x18002f2a9  call    ?Abort@CHttp2@@QEAAXJ@Z; CHttp2::Abort(long)
0x18002f2ae  jmp     loc_18002F19E
0x18002f2b3  mov     rcx, rbx; this
0x18002f2b6  call    ?Release@CHttp2SendContext@@QEAAKXZ; CHttp2SendContext::Release(void)
0x18002f2bb  jmp     loc_18002F1A7
0x18002f2c0  mov     edx, 2Ch ; ','
0x18002f2c5  mov     dword ptr [rsp+68h+var_48], r12d
0x18002f2ca  mov     ecx, 41Ah
0x18002f2cf  lea     r8, WPP_1eba17a514423a0ebe5ee43bce786d1b_Traceguids
0x18002f2d6  mov     r9, rsi
0x18002f2d9  call    WPP_SF_qD
0x18002f2de  jmp     loc_18002F1BF
0x18002f2e3  mov     edx, 2Dh ; '-'
0x18002f2e8  lea     r8, WPP_1eba17a514423a0ebe5ee43bce786d1b_Traceguids
0x18002f2ef  mov     ecx, 41Ah
0x18002f2f4  call    WPP_SF_
0x18002f2f9  jmp     loc_18002F1D9
```

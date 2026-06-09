# HTTP2ServerVirtualConnection::Close(int)

- ea: `0x180007be0`
- end: `0x180007ceb`
- name: `?Close@HTTP2ServerVirtualConnection@@UEAAXH@Z`
- size: `267`
- prototype: `void __fastcall(HTTP2ServerVirtualConnection *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bed0`

## callees

- `0x180003218`
- `0x180003d50`
- `0x180005ae8`
- `0x180007be0`
- `0x180009940`
- `0x18000f290`
- `0x18000f2bc`
- `0x18001ac1c`
- `0x18001b930`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180007c61`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180007c61`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007c6b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007c6b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007c48`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007c48`

## pseudocode

```c
void __fastcall HTTP2ServerVirtualConnection::Close(HTTP2ServerVirtualConnection *this, __int64 a2)
{
  PRTL_AVL_TABLE v2; // rdi
  int i; // esi
  __int64 v5; // rbp
  struct HTTP2Channel *v6; // rax
  int RightChild; // ecx
  char *v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  struct _RTL_BALANCED_LINKS *Parent; // rax
  signed __int32 v13[18]; // [rsp+0h] [rbp-48h] BYREF

  v2 = g_pServerCookieCollection;
  for ( i = 0; i < 2; ++i )
  {
    v5 = 16LL * i;
    v6 = HTTP2ChannelPointer::LockChannelPointer((HTTP2ServerVirtualConnection *)((char *)this + v5 + 200), a2);
    if ( v6 )
    {
      _InterlockedOr(v13, 0);
      _InterlockedOr(v13, 0);
      if ( *((_DWORD *)v6 + 21) )
      {
        RpcpReportFatalError(21);
        __debugbreak();
      }
      HTTP2ChannelPointer::UnlockChannelPointer((HTTP2ServerVirtualConnection *)((char *)this + v5 + 200), a2);
    }
  }
  if ( !*((_BYTE *)this + 508) )
  {
    RtlAcquireSRWLockExclusive(&v2[1].BalancedRoot.LeftChild);
    RightChild = (int)v2[1].BalancedRoot.RightChild;
    v8 = (char *)this + 88;
    if ( RightChild )
    {
      if ( RightChild == 1 )
        RtlDeleteElementGenericTableAvl(v2, v8);
    }
    else
    {
      v9 = (_QWORD *)GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::ListFind(
                       v2,
                       v8);
      if ( v9 )
      {
        v10 = *v9;
        if ( *(_QWORD **)(*v9 + 8LL) != v9 || (v11 = (_QWORD *)v9[1], (_QWORD *)*v11 != v9) )
          __fastfail(3u);
        *v11 = v10;
        *(_QWORD *)(v10 + 8) = v11;
        Parent = v2->BalancedRoot.Parent;
        --LODWORD(v2->BalancedRoot.RightChild);
        *(_QWORD *)&v2->BalancedRoot.Balance = Parent;
      }
    }
    RtlReleaseSRWLockExclusive(&v2[1].BalancedRoot.LeftChild);
    *((_BYTE *)this + 508) = 1;
  }
  HTTP2ServerVirtualConnection::Abort(this, 0);
  HTTP2VirtualConnection::DisconnectChannels(this, 0, 0);
  HTTP2TimeoutTargetConnection::CancelAllTimeouts(this);
  HTTP2ServerVirtualConnection::~HTTP2ServerVirtualConnection(this);
}

```

## disassembly

```asm
0x180007be0  push    rbx
0x180007be2  push    rbp
0x180007be3  push    rsi
0x180007be4  push    rdi
0x180007be5  sub     rsp, 28h
0x180007be9  mov     rdi, cs:?g_pServerCookieCollection@@3PEAVCookieCollection@@EA; CookieCollection * g_pServerCookieCollection
0x180007bf0  mov     rbx, rcx
0x180007bf3  xor     esi, esi
0x180007bf5  movsxd  rbp, esi
0x180007bf8  lea     rcx, [rbx+0C8h]
0x180007bff  shl     rbp, 4
0x180007c03  add     rcx, rbp; this
0x180007c06  call    ?LockChannelPointer@HTTP2ChannelPointer@@QEAAPEAVHTTP2Channel@@XZ; HTTP2ChannelPointer::LockChannelPointer(void)
0x180007c0b  test    rax, rax
0x180007c0e  jz      short loc_180007C34
0x180007c10  lock or [rsp+48h+var_48], 0
0x180007c15  lock or [rsp+48h+var_48], 0
0x180007c1a  mov     eax, [rax+54h]
0x180007c1d  test    eax, eax
0x180007c1f  jnz     loc_180007CA7
0x180007c25  lea     rcx, [rbx+0C8h]
0x180007c2c  add     rcx, rbp; this
0x180007c2f  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x180007c34  inc     esi
0x180007c36  cmp     esi, 2
0x180007c39  jl      short loc_180007BF5
0x180007c3b  cmp     byte ptr [rbx+1FCh], 0
0x180007c42  jnz     short loc_180007C78
0x180007c44  lea     rcx, [rdi+70h]
0x180007c48  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007c4e  mov     ecx, [rdi+78h]
0x180007c51  lea     rdx, [rbx+58h]; Buffer
0x180007c55  test    ecx, ecx
0x180007c57  jz      short loc_180007CB2
0x180007c59  cmp     ecx, 1
0x180007c5c  jnz     short loc_180007C67
0x180007c5e  mov     rcx, rdi; Table
0x180007c61  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180007c67  lea     rcx, [rdi+70h]
0x180007c6b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007c71  mov     byte ptr [rbx+1FCh], 1
0x180007c78  xor     edx, edx; void *
0x180007c7a  mov     rcx, rbx; this
0x180007c7d  call    ?Abort@HTTP2ServerVirtualConnection@@UEAAXPEAX@Z; HTTP2ServerVirtualConnection::Abort(void *)
0x180007c82  xor     r8d, r8d; int
0x180007c85  xor     edx, edx; int
0x180007c87  mov     rcx, rbx; this
0x180007c8a  call    ?DisconnectChannels@HTTP2VirtualConnection@@MEAAXHH@Z; HTTP2VirtualConnection::DisconnectChannels(int,int)
0x180007c8f  mov     rcx, rbx; this
0x180007c92  call    ?CancelAllTimeouts@HTTP2TimeoutTargetConnection@@QEAAXXZ; HTTP2TimeoutTargetConnection::CancelAllTimeouts(void)
0x180007c97  mov     rcx, rbx; this
0x180007c9a  add     rsp, 28h
0x180007c9e  pop     rdi
0x180007c9f  pop     rsi
0x180007ca0  pop     rbp
0x180007ca1  pop     rbx
0x180007ca2  jmp     ??1HTTP2ServerVirtualConnection@@UEAA@XZ; HTTP2ServerVirtualConnection::~HTTP2ServerVirtualConnection(void)
0x180007ca7  xor     edx, edx
0x180007ca9  lea     ecx, [rdx+15h]
0x180007cac  call    RpcpReportFatalError
0x180007cb1  int     3; Trap to Debugger
0x180007cb2  mov     rcx, rdi
0x180007cb5  call    ?ListFind@?$GenericTable@VHTTP2ServerCookie@@$0A@$1??$DefaultCompareKeys@VHTTP2Cookie@@@@YAHAEBVHTTP2Cookie@@0@Z@@AEAAPEAVHTTP2ServerCookie@@AEAVHTTP2Cookie@@@Z; GenericTable<HTTP2ServerCookie,0,&DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::ListFind(HTTP2Cookie &)
0x180007cba  test    rax, rax
0x180007cbd  jz      short loc_180007C67
0x180007cbf  mov     rcx, [rax]
0x180007cc2  cmp     [rcx+8], rax
0x180007cc6  jnz     short loc_180007CE4
0x180007cc8  mov     rdx, [rax+8]
0x180007ccc  cmp     [rdx], rax
0x180007ccf  jnz     short loc_180007CE4
0x180007cd1  mov     [rdx], rcx
0x180007cd4  mov     [rcx+8], rdx
0x180007cd8  mov     rax, [rdi]
0x180007cdb  dec     dword ptr [rdi+10h]
0x180007cde  mov     [rdi+18h], rax
0x180007ce2  jmp     short loc_180007C67
0x180007ce4  mov     ecx, 3
0x180007ce9  int     29h; Win8: RtlFailFast(ecx)
```

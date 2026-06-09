# minrpc::RpcSocket::IoCompletionCallback(void *,ulong,unsigned __int64)

- ea: `0x180065d00`
- end: `0x1800660a3`
- name: `?IoCompletionCallback@RpcSocket@minrpc@@AEAAXPEAXK_K@Z`
- size: `931`
- prototype: `void __fastcall(minrpc::RpcSocket *this, char *, signed int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18008c520`

## callees

- `0x180065d00`
- `0x1800660ac`
- `0x18006d84c`
- `0x18007917c`
- `0x180091004`
- `0x18009129c`
- `0x180092390`
- `0x1800c6874`
- `0x1800d337c`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065d32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065f10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065fac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065d32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065f10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065fac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065d6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065d6e`
- `WS2_32!__imp_setsockopt` at `0x18006600a`
- `WS2_32!__imp_setsockopt` at `0x18006600a`
- `WS2_32!__imp_WSAGetLastError` at `0x180066014`
- `WS2_32!__imp_WSAGetLastError` at `0x180066014`

## string_xrefs

- `0x180065d91`: `IoCompletionCallback[Recv]`
- `0x180065db8`: `IoCompletionCallback[Recv]`
- `0x180065f4c`: `IoCompletionCallback[Send]`
- `0x18006602d`: `IoCompletionCallback[setsockopt]`
- `0x180065fe4`: `IoCompletionCallback[Conn]`
- `0x180065ea1`: `IoCompletionCallback[PacketTooBig]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall minrpc::RpcSocket::IoCompletionCallback(minrpc::RpcSocket *this, char *a2, signed int a3, __int64 a4)
{
  char v7; // al
  const char *v8; // r9
  __int64 v9; // r8
  unsigned int i; // esi
  void **v11; // rcx
  unsigned int v12; // edx
  unsigned int v13; // r9d
  unsigned int v14; // r15d
  char v15; // al
  __int64 v16; // r8
  __int64 v17; // rcx
  char v18; // al
  int Error; // eax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-18h] BYREF
  char v21; // [rsp+38h] [rbp-10h]

  if ( a2 != (char *)this + 192 )
  {
    if ( a2 == (char *)this + 160 )
    {
      SRWLock = (PSRWLOCK)this;
      v21 = 0;
      AcquireSRWLockExclusive((PSRWLOCK)this);
      *((_BYTE *)this + 136) &= ~1u;
      v15 = *((_BYTE *)this + 138);
      LOBYTE(v16) = *((_BYTE *)this + 137);
      v21 = 1;
      if ( v15 == 2 )
      {
        if ( !a3 )
        {
          v17 = 32LL * ((unsigned __int8)v16 ^ 1u);
          *(_DWORD *)((char *)this + v17 + 96) += a4;
          if ( *(_DWORD *)((char *)this + v17 + 96) < *(_DWORD *)((char *)this + v17 + 100) )
            LOBYTE(v16) = v16 ^ 1;
          else
            *(_QWORD *)((char *)this + v17 + 96) = 0;
          minrpc::RpcSocket::StartSend(this, &SRWLock, v16);
          goto LABEL_60;
        }
        if ( a3 > 0 )
          a3 = (unsigned __int16)a3 | 0x80070000;
        v8 = "IoCompletionCallback[Send]";
        goto LABEL_11;
      }
    }
    else
    {
      if ( a2 != (char *)this + 168 )
        return;
      SRWLock = (PSRWLOCK)this;
      v21 = 0;
      AcquireSRWLockExclusive((PSRWLOCK)this);
      v18 = *((_BYTE *)this + 138);
      v21 = 1;
      if ( v18 == 1 )
      {
        if ( a3 )
        {
          *((_BYTE *)this + 136) &= ~4u;
          if ( a3 > 0 )
            a3 = (unsigned __int16)a3 | 0x80070000;
          v8 = "IoCompletionCallback[Conn]";
LABEL_11:
          v9 = (unsigned int)a3;
LABEL_12:
          minrpc::RpcSocket::DisconnectLocked(this, &SRWLock, v9, v8);
LABEL_60:
          utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&SRWLock);
          return;
        }
        if ( setsockopt(*((_QWORD *)this + 3), 0xFFFF, 28688, 0, 0) )
        {
          Error = WSAGetLastError();
          *((_BYTE *)this + 136) &= ~4u;
          if ( Error > 0 )
            Error = (unsigned __int16)Error | 0x80070000;
          v8 = "IoCompletionCallback[setsockopt]";
          v9 = (unsigned int)Error;
          goto LABEL_12;
        }
        (***((void (__fastcall ****)(_QWORD, PSRWLOCK *))this + 1))(*((_QWORD *)this + 1), &SRWLock);
        if ( !v21 )
          utl::unique_lock<utl::mutex>::lock(&SRWLock);
        if ( *((_BYTE *)this + 138) == 1 )
        {
          *((_BYTE *)this + 138) = 2;
          *((_BYTE *)this + 136) &= ~4u;
LABEL_59:
          minrpc::RpcSocket::StartRecv((__int64)this, (__int64)&SRWLock);
          goto LABEL_60;
        }
      }
      *((_BYTE *)this + 136) &= ~4u;
    }
LABEL_24:
    minrpc::RpcSocket::CheckForDisconnectComplete(this, &SRWLock);
    goto LABEL_60;
  }
  SRWLock = (PSRWLOCK)this;
  v21 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this);
  v7 = *((_BYTE *)this + 138);
  v21 = 1;
  if ( v7 == 2 )
  {
    if ( !a3 )
    {
      if ( a4 )
      {
        *((_DWORD *)this + 16) += a4;
        for ( i = 0; ; i = v14 )
        {
          v11 = (void **)((char *)this + 40);
          v12 = *((_DWORD *)this + 16) - i;
          if ( v12 < 8 )
          {
LABEL_31:
            if ( i )
            {
              memmove_0(*v11, (char *)*v11 + i, v12);
              *((_DWORD *)this + 16) -= i;
            }
            *((_BYTE *)this + 136) &= ~2u;
            goto LABEL_59;
          }
          v13 = *(_DWORD *)((char *)*v11 + i);
          if ( v13 > 0x10000000 )
            break;
          v14 = i + v13 + (-v13 & 7) + 8;
          if ( *((_DWORD *)this + 16) < v14 )
            goto LABEL_31;
          (*(void (__fastcall **)(_QWORD, PSRWLOCK *, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
            *((_QWORD *)this + 1),
            &SRWLock,
            *(unsigned int *)((char *)*v11 + i + 4));
          if ( !v21 )
            utl::unique_lock<utl::mutex>::lock(&SRWLock);
          if ( *((_BYTE *)this + 138) != 2 )
          {
            *((_BYTE *)this + 136) &= ~2u;
            goto LABEL_24;
          }
        }
        *((_BYTE *)this + 136) &= ~2u;
        if ( !*((_BYTE *)this + 138) )
          goto LABEL_5;
        if ( *((_BYTE *)this + 138) == 1 || *((_BYTE *)this + 138) == 2 )
        {
          *((_DWORD *)this + 36) = -2147024883;
          *((_QWORD *)this + 19) = "IoCompletionCallback[PacketTooBig]";
          *((_BYTE *)this + 138) = 3;
          tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),-1>>::reset(
            (char *)this + 24,
            -1);
          goto LABEL_4;
        }
        if ( *((_BYTE *)this + 138) != 3 )
          __int2c();
        goto LABEL_5;
      }
      *((_BYTE *)this + 136) &= ~2u;
      v8 = "IoCompletionCallback[Recv]";
      v9 = 2147952501LL;
      goto LABEL_12;
    }
    *((_BYTE *)this + 136) &= ~2u;
    if ( a3 > 0 )
      a3 = (unsigned __int16)a3 | 0x80070000;
    v8 = "IoCompletionCallback[Recv]";
    goto LABEL_11;
  }
  *((_BYTE *)this + 136) &= ~2u;
LABEL_4:
  minrpc::RpcSocket::CheckForDisconnectComplete(this, &SRWLock);
LABEL_5:
  if ( v21 )
    ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x180065d00  push    rbp
0x180065d02  push    rbx
0x180065d03  push    rsi
0x180065d04  push    r12
0x180065d06  push    r14
0x180065d08  push    r15
0x180065d0a  mov     rbp, rsp
0x180065d0d  sub     rsp, 48h
0x180065d11  lea     rax, [rcx+0C0h]
0x180065d18  mov     r15, r9
0x180065d1b  mov     esi, r8d
0x180065d1e  mov     rbx, rcx
0x180065d21  cmp     rdx, rax
0x180065d24  jnz     loc_180065EF8
0x180065d2a  mov     [rbp+SRWLock], rcx
0x180065d2e  mov     [rbp+var_10], 0
0x180065d32  call    cs:__imp_AcquireSRWLockExclusive
0x180065d38  mov     al, [rbx+8Ah]
0x180065d3e  mov     r14d, 2
0x180065d44  mov     [rbp+var_10], 1
0x180065d48  cmp     al, r14b
0x180065d4b  jz      short loc_180065D79
0x180065d4d  and     byte ptr [rbx+88h], 0FDh
0x180065d54  lea     rdx, [rbp+SRWLock]
0x180065d58  mov     rcx, rbx
0x180065d5b  call    ?CheckForDisconnectComplete@RpcSocket@minrpc@@AEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z; minrpc::RpcSocket::CheckForDisconnectComplete(utl::unique_lock<utl::mutex> &)
0x180065d60  cmp     [rbp+var_10], 0
0x180065d64  jz      loc_180066095
0x180065d6a  mov     rcx, [rbp+SRWLock]; SRWLock
0x180065d6e  call    cs:__imp_ReleaseSRWLockExclusive
0x180065d74  jmp     loc_180066095
0x180065d79  test    esi, esi
0x180065d7b  jz      short loc_180065DAC
0x180065d7d  and     byte ptr [rbx+88h], 0FDh
0x180065d84  test    esi, esi
0x180065d86  jle     short loc_180065D91
0x180065d88  movzx   esi, si
0x180065d8b  or      esi, 80070000h
0x180065d91  lea     r9, aIocompletionca_1; "IoCompletionCallback[Recv]"
0x180065d98  mov     r8d, esi
0x180065d9b  lea     rdx, [rbp+SRWLock]
0x180065d9f  mov     rcx, rbx
0x180065da2  call    ?DisconnectLocked@RpcSocket@minrpc@@QEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@JPEBD@Z; minrpc::RpcSocket::DisconnectLocked(utl::unique_lock<utl::mutex> &,long,char const *)
0x180065da7  jmp     loc_18006608C
0x180065dac  test    r15, r15
0x180065daf  jnz     short loc_180065DC7
0x180065db1  and     byte ptr [rbx+88h], 0FDh
0x180065db8  lea     r9, aIocompletionca_1; "IoCompletionCallback[Recv]"
0x180065dbf  mov     r8d, 80072775h
0x180065dc5  jmp     short loc_180065D9B
0x180065dc7  add     [rbx+40h], r15d
0x180065dcb  xor     esi, esi
0x180065dcd  mov     edx, [rbx+40h]
0x180065dd0  lea     rcx, [rbx+28h]
0x180065dd4  sub     edx, esi
0x180065dd6  mov     r10d, esi
0x180065dd9  cmp     edx, 8
0x180065ddc  jb      loc_180065ED6
0x180065de2  mov     r8, [rcx]
0x180065de5  mov     r9d, [r8+r10]
0x180065de9  cmp     r9d, 10000000h
0x180065df0  ja      short loc_180065E6F
0x180065df2  mov     r15d, r9d
0x180065df5  neg     r15d
0x180065df8  and     r15d, 7
0x180065dfc  add     r15d, 8
0x180065e00  add     r15d, r9d
0x180065e03  add     r15d, esi
0x180065e06  cmp     [rbx+40h], r15d
0x180065e0a  jb      loc_180065ED6
0x180065e10  mov     rcx, [rbx+8]
0x180065e14  lea     rdx, [r8+8]
0x180065e18  mov     r8d, [r8+r10+4]
0x180065e1d  add     rdx, r10
0x180065e20  mov     qword ptr [rsp+48h+optlen], rdx
0x180065e25  lea     rdx, [rbp+SRWLock]
0x180065e29  mov     rax, [rcx]
0x180065e2c  mov     rax, [rax+10h]
0x180065e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e35  cmp     [rbp+var_10], 0
0x180065e39  jnz     short loc_180065E44
0x180065e3b  lea     rcx, [rbp+SRWLock]
0x180065e3f  call    ?lock@?$unique_lock@Vmutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::mutex>::lock(void)
0x180065e44  mov     al, [rbx+8Ah]
0x180065e4a  cmp     al, r14b
0x180065e4d  jnz     short loc_180065E57
0x180065e4f  mov     esi, r15d
0x180065e52  jmp     loc_180065DCD
0x180065e57  and     byte ptr [rbx+88h], 0FDh
0x180065e5e  lea     rdx, [rbp+SRWLock]
0x180065e62  mov     rcx, rbx
0x180065e65  call    ?CheckForDisconnectComplete@RpcSocket@minrpc@@AEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z; minrpc::RpcSocket::CheckForDisconnectComplete(utl::unique_lock<utl::mutex> &)
0x180065e6a  jmp     loc_18006608C
0x180065e6f  and     byte ptr [rbx+88h], 0FDh
0x180065e76  movzx   eax, byte ptr [rbx+8Ah]
0x180065e7d  mov     ecx, eax
0x180065e7f  test    al, al
0x180065e81  jz      loc_180065D60
0x180065e87  sub     ecx, 1
0x180065e8a  jz      short loc_180065EA1
0x180065e8c  sub     ecx, 1
0x180065e8f  jz      short loc_180065EA1
0x180065e91  cmp     ecx, 1
0x180065e94  jz      loc_180065D60
0x180065e9a  int     2Ch; Windows NT - assertion failure
0x180065e9c  jmp     loc_180065D60
0x180065ea1  lea     rax, aIocompletionca_3; "IoCompletionCallback[PacketTooBig]"
0x180065ea8  mov     dword ptr [rbx+90h], 8007000Dh
0x180065eb2  mov     [rbx+98h], rax
0x180065eb9  lea     rcx, [rbx+18h]
0x180065ebd  mov     eax, 3
0x180065ec2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180065ec6  xchg    al, [rbx+8Ah]
0x180065ecc  call    ?reset@?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@QEAAX_K@Z; tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>>::reset(unsigned __int64)
0x180065ed1  jmp     loc_180065D54
0x180065ed6  test    esi, esi
0x180065ed8  jz      short loc_180065EEC
0x180065eda  mov     rcx, [rcx]; void *
0x180065edd  mov     r8d, edx; Size
0x180065ee0  lea     rdx, [rcx+r10]; Src
0x180065ee4  call    memmove_0
0x180065ee9  sub     [rbx+40h], esi
0x180065eec  and     byte ptr [rbx+88h], 0FDh
0x180065ef3  jmp     loc_180066080
0x180065ef8  lea     rax, [rcx+0A0h]
0x180065eff  cmp     rdx, rax
0x180065f02  jnz     loc_180065F94
0x180065f08  mov     [rbp+SRWLock], rbx
0x180065f0c  mov     [rbp+var_10], 0
0x180065f10  call    cs:__imp_AcquireSRWLockExclusive
0x180065f16  and     byte ptr [rbx+88h], 0FEh
0x180065f1d  mov     r14d, 2
0x180065f23  mov     al, [rbx+8Ah]
0x180065f29  mov     r8b, [rbx+89h]
0x180065f30  mov     [rbp+var_10], 1
0x180065f34  cmp     al, r14b
0x180065f37  jnz     loc_180065E5E
0x180065f3d  test    esi, esi
0x180065f3f  jz      short loc_180065F58
0x180065f41  jle     short loc_180065F4C
0x180065f43  movzx   esi, si
0x180065f46  or      esi, 80070000h
0x180065f4c  lea     r9, aIocompletionca_4; "IoCompletionCallback[Send]"
0x180065f53  jmp     loc_180065D98
0x180065f58  mov     al, r8b
0x180065f5b  xor     al, 1
0x180065f5d  movzx   edx, al
0x180065f60  mov     ecx, edx
0x180065f62  shl     rcx, 5
0x180065f66  add     [rcx+rbx+60h], r15d
0x180065f6b  mov     eax, [rcx+rbx+60h]
0x180065f6f  cmp     eax, [rcx+rbx+64h]
0x180065f73  jb      short loc_180065F80
0x180065f75  mov     qword ptr [rcx+rbx+60h], 0
0x180065f7e  jmp     short loc_180065F83
0x180065f80  mov     r8b, dl
0x180065f83  lea     rdx, [rbp+SRWLock]
0x180065f87  mov     rcx, rbx
0x180065f8a  call    ?StartSend@RpcSocket@minrpc@@AEAA_NAEAV?$unique_lock@Vmutex@utl@@@utl@@E@Z; minrpc::RpcSocket::StartSend(utl::unique_lock<utl::mutex> &,uchar)
0x180065f8f  jmp     loc_18006608C
0x180065f94  lea     rax, [rcx+0A8h]
0x180065f9b  cmp     rdx, rax
0x180065f9e  jnz     loc_180066095
0x180065fa4  mov     [rbp+SRWLock], rbx
0x180065fa8  mov     [rbp+var_10], 0
0x180065fac  call    cs:__imp_AcquireSRWLockExclusive
0x180065fb2  mov     al, [rbx+8Ah]
0x180065fb8  mov     [rbp+var_10], 1
0x180065fbc  cmp     al, 1
0x180065fbe  jz      short loc_180065FCC
0x180065fc0  and     byte ptr [rbx+88h], 0FBh
0x180065fc7  jmp     loc_180065E5E
0x180065fcc  test    esi, esi
0x180065fce  jz      short loc_180065FF0
0x180065fd0  and     byte ptr [rbx+88h], 0FBh
0x180065fd7  test    esi, esi
0x180065fd9  jle     short loc_180065FE4
0x180065fdb  movzx   esi, si
0x180065fde  or      esi, 80070000h
0x180065fe4  lea     r9, aIocompletionca_2; "IoCompletionCallback[Conn]"
0x180065feb  jmp     loc_180065D98
0x180065ff0  mov     rcx, [rbx+18h]; s
0x180065ff4  xor     r9d, r9d; optval
0x180065ff7  mov     edx, 0FFFFh; level
0x180065ffc  mov     [rsp+48h+optlen], 0; optlen
0x180066004  mov     r8d, 7010h; optname
0x18006600a  call    cs:__imp_setsockopt
0x180066010  test    eax, eax
0x180066012  jz      short loc_18006603C
0x180066014  call    cs:__imp_WSAGetLastError
0x18006601a  and     byte ptr [rbx+88h], 0FBh
0x180066021  test    eax, eax
0x180066023  jle     short loc_18006602D
0x180066025  movzx   eax, ax
0x180066028  or      eax, 80070000h
0x18006602d  lea     r9, aIocompletionca; "IoCompletionCallback[setsockopt]"
0x180066034  mov     r8d, eax
0x180066037  jmp     loc_180065D9B
0x18006603c  mov     rcx, [rbx+8]
0x180066040  lea     rdx, [rbp+SRWLock]
0x180066044  mov     rax, [rcx]
0x180066047  mov     rax, [rax]
0x18006604a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006604f  cmp     [rbp+var_10], 0
0x180066053  jnz     short loc_18006605E
0x180066055  lea     rcx, [rbp+SRWLock]
0x180066059  call    ?lock@?$unique_lock@Vmutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::mutex>::lock(void)
0x18006605e  mov     al, [rbx+8Ah]
0x180066064  cmp     al, 1
0x180066066  jnz     loc_180065FC0
0x18006606c  mov     r14d, 2
0x180066072  xchg    r14b, [rbx+8Ah]
0x180066079  and     byte ptr [rbx+88h], 0FBh
0x180066080  lea     rdx, [rbp+SRWLock]
0x180066084  mov     rcx, rbx
0x180066087  call    ?StartRecv@RpcSocket@minrpc@@AEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z; minrpc::RpcSocket::StartRecv(utl::unique_lock<utl::mutex> &)
0x18006608c  lea     rcx, [rbp+SRWLock]
0x180066090  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x180066095  add     rsp, 48h
0x180066099  pop     r15
0x18006609b  pop     r14
0x18006609d  pop     r12
0x18006609f  pop     rsi
0x1800660a0  pop     rbx
0x1800660a1  pop     rbp
0x1800660a2  retn
```

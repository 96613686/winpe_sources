# SIO_CACHE::Flush(void)

- ea: `0x14001dd60`
- end: `0x14001df18`
- name: `?Flush@SIO_CACHE@@QEAAJXZ`
- size: `440`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14002b7a4`
- `0x1400480e4`

## callees

- `0x1400044d0`
- `0x140009f80`
- `0x14000a070`
- `0x140019700`
- `0x14001dd60`
- `0x14001df20`
- `0x1400265c0`
- `0x140026db0`
- `0x1400440b4`
- `0x140046214`
- `0x140048918`
- `0x140051f68`
- `0x140052000`
- `0x140052908`
- `0x140068150`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14001ddb3`
- `HAL!KeQueryPerformanceCounter` at `0x14001dea1`
- `HAL!KeQueryPerformanceCounter` at `0x14001ddb3`
- `HAL!KeQueryPerformanceCounter` at `0x14001dea1`

## pseudocode

```c
__int64 __fastcall SIO_CACHE::Flush(SIO_CACHE *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  struct SIO_SPACE *v4; // r15
  struct SIO_SPACE *Child; // rbp
  LARGE_INTEGER v6; // r14
  int v7; // ebx
  bool v9; // r14
  LARGE_INTEGER PerformanceCounter; // r12
  int *v11[4]; // [rsp+20h] [rbp-148h] BYREF
  char v12; // [rsp+40h] [rbp-128h]
  char v13; // [rsp+48h] [rbp-120h]
  unsigned __int8 v14; // [rsp+50h] [rbp-118h]
  char v15; // [rsp+58h] [rbp-110h]
  __int64 v16; // [rsp+E0h] [rbp-88h]

  SC_PACKET::SC_PACKET((SC_PACKET *)v11);
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  LOBYTE(v3) = 11;
  v4 = (struct SIO_SPACE *)v2;
  Child = (struct SIO_SPACE *)SIO_SPACE::GetChild(v2, v3);
  if ( SIO_CACHE::IsDirty(this) )
  {
    v9 = 0;
    v7 = 0;
    while ( !v9 )
    {
      if ( SIO_SLOTS::IsFull((SIO_CACHE *)((char *)this + 16)) )
      {
        v7 = SIO_CACHE::WriteCheckpoint(this);
        if ( v7 < 0 )
          goto LABEL_5;
      }
      v7 = SIO_SLOTS::GetWritePacket((SIO_CACHE *)((char *)this + 16), (struct SC_PACKET *)v11);
      if ( v7 < 0 )
        goto LABEL_5;
      v9 = (unsigned int)SIO_CACHE::FormatLines(this, (struct SC_PACKET *)v11) != 261;
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v7 = SIO_SLOTS::FlushSynchronous((SIO_CACHE *)((char *)this + 16), Child);
      if ( v7 >= 0 )
      {
        _InterlockedExchange64((volatile __int64 *)this + 70, PerformanceCounter.QuadPart);
        v7 = SIO_SLOTS::FlushSynchronous((SIO_CACHE *)((char *)this + 16), v4);
      }
      if ( !v16 )
        goto LABEL_4;
      if ( v7 < 0 || (v7 = SIO_SLOTS::WriteSlots((SIO_CACHE *)((char *)this + 16), (struct SC_PACKET *)v11), v7 < 0) )
      {
        SIO_CACHE::AbortFlush(this);
        goto LABEL_5;
      }
      SIO_CACHE::CommitFlush(this);
    }
  }
  else
  {
    v6 = KeQueryPerformanceCounter(0);
    v7 = SIO_SLOTS::FlushSynchronous((SIO_CACHE *)((char *)this + 16), Child);
    if ( v7 < 0 )
      goto LABEL_5;
    _InterlockedExchange64((volatile __int64 *)this + 70, v6.QuadPart);
    v7 = SIO_SLOTS::FlushSynchronous((SIO_CACHE *)((char *)this + 16), v4);
LABEL_4:
    if ( v7 < 0 )
    {
LABEL_5:
      if ( *((_BYTE *)this + 89) || *((_BYTE *)this + 90) || ((v7 + 1058602989) & 0xFFFFFFF7) != 0 )
        SC_ENV::EventWrite(
          0x410u,
          *((_QWORD *)this + 1) + 40LL,
          6,
          (unsigned int)v7,
          v11[0],
          (__int64)v11[1],
          (__int64)v11[2],
          (__int64)v11[3],
          v12,
          v13,
          v14,
          v15);
    }
  }
  SIO_LOG_PACKET::~SIO_LOG_PACKET((SIO_LOG_PACKET *)v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001dd60  push    rbx
0x14001dd62  push    rbp
0x14001dd63  push    rsi
0x14001dd64  push    rdi
0x14001dd65  push    r12
0x14001dd67  push    r13
0x14001dd69  push    r14
0x14001dd6b  push    r15
0x14001dd6d  sub     rsp, 128h
0x14001dd74  mov     rsi, rcx
0x14001dd77  lea     rcx, [rsp+168h+var_148]; this
0x14001dd7c  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14001dd81  mov     rcx, [rsi+8]
0x14001dd85  mov     rax, [rcx]
0x14001dd88  mov     rax, [rax+50h]
0x14001dd8c  call    _guard_dispatch_icall
0x14001dd91  mov     dl, 0Bh
0x14001dd93  mov     rcx, rax
0x14001dd96  mov     r15, rax
0x14001dd99  call    ?GetChild@SIO_SPACE@@QEAAPEAV1@W4_SC_SPACE_USAGE@@@Z; SIO_SPACE::GetChild(_SC_SPACE_USAGE)
0x14001dd9e  mov     rcx, rsi; this
0x14001dda1  mov     rbp, rax
0x14001dda4  call    ?IsDirty@SIO_CACHE@@QEAAEXZ; SIO_CACHE::IsDirty(void)
0x14001dda9  test    al, al
0x14001ddab  jnz     loc_14001DE42
0x14001ddb1  xor     ecx, ecx; PerformanceFrequency
0x14001ddb3  call    cs:__imp_KeQueryPerformanceCounter
0x14001ddba  nop     dword ptr [rax+rax+00h]
0x14001ddbf  mov     rdx, rbp; struct SIO_SPACE *
0x14001ddc2  lea     rcx, [rsi+10h]; this
0x14001ddc6  mov     r14, rax
0x14001ddc9  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x14001ddce  mov     ebx, eax
0x14001ddd0  test    eax, eax
0x14001ddd2  js      short loc_14001DDED
0x14001ddd4  xchg    r14, [rsi+230h]
0x14001dddb  mov     rdx, r15; struct SIO_SPACE *
0x14001ddde  lea     rcx, [rsi+10h]; this
0x14001dde2  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x14001dde7  mov     ebx, eax
0x14001dde9  test    ebx, ebx
0x14001ddeb  jns     short loc_14001DE21
0x14001dded  cmp     byte ptr [rsi+59h], 0
0x14001ddf1  jnz     short loc_14001DE06
0x14001ddf3  cmp     byte ptr [rsi+5Ah], 0
0x14001ddf7  jnz     short loc_14001DE06
0x14001ddf9  lea     eax, [rbx+3F18FFEDh]
0x14001ddff  test    eax, 0FFFFFFF7h
0x14001de04  jz      short loc_14001DE21
0x14001de06  mov     rdx, [rsi+8]
0x14001de0a  mov     r9d, ebx
0x14001de0d  add     rdx, 28h ; '('
0x14001de11  mov     ecx, 410h; unsigned int
0x14001de16  mov     r8d, 6
0x14001de1c  call    ?EventWrite@SC_ENV@@SAXKZZ; SC_ENV::EventWrite(ulong,...)
0x14001de21  lea     rcx, [rsp+168h+var_148]; this
0x14001de26  call    ??1SIO_LOG_PACKET@@UEAA@XZ; SIO_LOG_PACKET::~SIO_LOG_PACKET(void)
0x14001de2b  mov     eax, ebx
0x14001de2d  add     rsp, 128h
0x14001de34  pop     r15
0x14001de36  pop     r14
0x14001de38  pop     r13
0x14001de3a  pop     r12
0x14001de3c  pop     rdi
0x14001de3d  pop     rsi
0x14001de3e  pop     rbp
0x14001de3f  pop     rbx
0x14001de40  retn
0x14001de42  xor     r14b, r14b
0x14001de45  mov     r13d, 1
0x14001de4b  xor     ebx, ebx
0x14001de4d  test    r14b, r14b
0x14001de50  jnz     short loc_14001DE21
0x14001de52  lea     rcx, [rsi+10h]; this
0x14001de56  call    ?IsFull@SIO_SLOTS@@QEAAEXZ; SIO_SLOTS::IsFull(void)
0x14001de5b  test    al, al
0x14001de5d  jz      short loc_14001DE6D
0x14001de5f  mov     rcx, rsi; this
0x14001de62  call    ?WriteCheckpoint@SIO_CACHE@@IEAAJXZ; SIO_CACHE::WriteCheckpoint(void)
0x14001de67  mov     ebx, eax
0x14001de69  test    eax, eax
0x14001de6b  js      short loc_14001DDED
0x14001de6d  lea     rdx, [rsp+168h+var_148]; struct SC_PACKET *
0x14001de72  lea     rcx, [rsi+10h]; this
0x14001de76  call    ?GetWritePacket@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::GetWritePacket(SC_PACKET *)
0x14001de7b  mov     ebx, eax
0x14001de7d  test    eax, eax
0x14001de7f  js      loc_14001DDED
0x14001de85  lea     rdx, [rsp+168h+var_148]; struct SC_PACKET *
0x14001de8a  mov     rcx, rsi; this
0x14001de8d  call    ?FormatLines@SIO_CACHE@@IEAAJPEAVSC_PACKET@@@Z; SIO_CACHE::FormatLines(SC_PACKET *)
0x14001de92  cmp     eax, 105h
0x14001de97  movzx   r14d, r14b
0x14001de9b  cmovnz  r14d, r13d
0x14001de9f  xor     ecx, ecx; PerformanceFrequency
0x14001dea1  call    cs:__imp_KeQueryPerformanceCounter
0x14001dea8  nop     dword ptr [rax+rax+00h]
0x14001dead  mov     rdx, rbp; struct SIO_SPACE *
0x14001deb0  lea     rcx, [rsi+10h]; this
0x14001deb4  mov     r12, rax
0x14001deb7  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x14001debc  mov     ebx, eax
0x14001debe  test    eax, eax
0x14001dec0  js      short loc_14001DED7
0x14001dec2  xchg    r12, [rsi+230h]
0x14001dec9  mov     rdx, r15; struct SIO_SPACE *
0x14001decc  lea     rcx, [rsi+10h]; this
0x14001ded0  call    ?FlushSynchronous@SIO_SLOTS@@QEAAJPEAVSIO_SPACE@@@Z; SIO_SLOTS::FlushSynchronous(SIO_SPACE *)
0x14001ded5  mov     ebx, eax
0x14001ded7  cmp     [rsp+168h+var_88], 0
0x14001dee0  jz      loc_14001DDE9
0x14001dee6  test    ebx, ebx
0x14001dee8  js      short loc_14001DF0B
0x14001deea  lea     rdx, [rsp+168h+var_148]; struct SC_PACKET *
0x14001deef  lea     rcx, [rsi+10h]; this
0x14001def3  call    ?WriteSlots@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteSlots(SC_PACKET *)
0x14001def8  mov     ebx, eax
0x14001defa  test    eax, eax
0x14001defc  js      short loc_14001DF0B
0x14001defe  mov     rcx, rsi; this
0x14001df01  call    ?CommitFlush@SIO_CACHE@@IEAAXXZ; SIO_CACHE::CommitFlush(void)
0x14001df06  jmp     loc_14001DE4D
0x14001df0b  mov     rcx, rsi; this
0x14001df0e  call    ?AbortFlush@SIO_CACHE@@IEAAXXZ; SIO_CACHE::AbortFlush(void)
0x14001df13  jmp     loc_14001DDED
```

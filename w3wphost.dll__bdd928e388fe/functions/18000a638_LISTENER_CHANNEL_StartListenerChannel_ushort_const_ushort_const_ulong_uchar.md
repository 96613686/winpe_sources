# LISTENER_CHANNEL::StartListenerChannel(ushort const *,ushort const *,ulong,uchar *)

- ea: `0x18000a638`
- end: `0x18000a7a7`
- name: `?StartListenerChannel@LISTENER_CHANNEL@@QEAAJPEBG0KPEAE@Z`
- size: `367`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000abd0`

## callees

- `0x180001f68`
- `0x1800063a0`
- `0x180009ef0`
- `0x18000a638`
- `0x18000c386`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6a6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a794`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a794`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a659`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a659`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000a69c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000a69c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a6cd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000a6cd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a666`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a680`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a666`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a680`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::StartListenerChannel(
        LISTENER_CHANNEL *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int8 *Src)
{
  CReaderWriterLock3 *v5; // r14
  size_t v6; // rbp
  signed int v10; // ebx
  signed int LastError; // eax
  void *Ptr; // rax
  LISTENER_CHANNEL_WORKITEM *v13; // rax
  struct W3WP_HOST_WORKITEM *v14; // rsi
  W3WP_HOST *v15; // rcx
  char *v16; // rdi
  char **v17; // rcx

  v5 = (LISTENER_CHANNEL *)((char *)this + 280);
  v6 = a4;
  CReaderWriterLock3::WriteLock((LISTENER_CHANNEL *)((char *)this + 280));
  v10 = STRU::Copy((LISTENER_CHANNEL *)((char *)this + 80), a2);
  if ( v10 >= 0 )
  {
    v10 = STRU::Copy((LISTENER_CHANNEL *)((char *)this + 136), a3);
    if ( v10 >= 0 )
    {
      if ( BUFFER::Resize((LISTENER_CHANNEL *)((char *)this + 192), v6) )
      {
        *((_DWORD *)this + 60) = v6;
        Ptr = BUFFER::QueryPtr((LISTENER_CHANNEL *)((char *)this + 192));
        memcpy_0(Ptr, Src, v6);
        v13 = (LISTENER_CHANNEL_WORKITEM *)operator new(0x30u);
        v14 = v13;
        if ( !v13 )
        {
          v10 = -2147024888;
          goto LABEL_15;
        }
        LISTENER_CHANNEL_WORKITEM::LISTENER_CHANNEL_WORKITEM(v13, this, 1);
        *(_QWORD *)v14 = &LISTENER_CHANNEL_START_WORKITEM::`vftable';
        v15 = (W3WP_HOST *)(unsigned int)(*((_DWORD *)this + 66) - 2);
        if ( ((unsigned int)v15 & 0xFFFFFFFD) != 0 )
        {
          *((_DWORD *)this + 66) = 2;
          _InterlockedAdd(&LISTENER_CHANNEL::s_lNotStoppedCount, 1u);
          v10 = W3WP_HOST::QueueWorkItem(v15, v14);
          if ( v10 < 0 )
          {
            _InterlockedDecrement(&LISTENER_CHANNEL::s_lNotStoppedCount);
            (**(void (__fastcall ***)(struct W3WP_HOST_WORKITEM *, __int64))v14)(v14, 1);
            goto LABEL_15;
          }
        }
        else
        {
          v16 = (char *)this + 296;
          v17 = (char **)*((_QWORD *)v16 + 1);
          if ( *v17 != v16 )
            __fastfail(3u);
          *((_QWORD *)v14 + 2) = v16;
          *((_QWORD *)v14 + 3) = v17;
          *v17 = (char *)v14 + 16;
          *((_QWORD *)v16 + 1) = (char *)v14 + 16;
        }
        v10 = 0;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_15:
  CReaderWriterLock3::WriteUnlock(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a638  push    rbx
0x18000a63a  push    rbp
0x18000a63b  push    rsi
0x18000a63c  push    rdi
0x18000a63d  push    r14
0x18000a63f  sub     rsp, 20h
0x18000a643  lea     r14, [rcx+118h]
0x18000a64a  mov     ebp, r9d
0x18000a64d  mov     rdi, rcx
0x18000a650  mov     rsi, r8
0x18000a653  mov     rcx, r14
0x18000a656  mov     rbx, rdx
0x18000a659  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a65f  lea     rcx, [rdi+50h]
0x18000a663  mov     rdx, rbx
0x18000a666  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a66c  mov     ebx, eax
0x18000a66e  test    eax, eax
0x18000a670  js      loc_18000A791
0x18000a676  lea     rcx, [rdi+88h]
0x18000a67d  mov     rdx, rsi
0x18000a680  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a686  mov     ebx, eax
0x18000a688  test    eax, eax
0x18000a68a  js      loc_18000A791
0x18000a690  lea     rsi, [rdi+0C0h]
0x18000a697  mov     edx, ebp
0x18000a699  mov     rcx, rsi
0x18000a69c  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000a6a2  test    al, al
0x18000a6a4  jnz     short loc_18000A6C4
0x18000a6a6  call    cs:__imp_GetLastError
0x18000a6ac  mov     ebx, eax
0x18000a6ae  test    eax, eax
0x18000a6b0  jle     loc_18000A791
0x18000a6b6  movzx   ebx, ax
0x18000a6b9  or      ebx, 80070000h
0x18000a6bf  jmp     loc_18000A791
0x18000a6c4  mov     rcx, rsi
0x18000a6c7  mov     [rdi+0F0h], ebp
0x18000a6cd  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000a6d3  mov     rdx, [rsp+48h+Src]; Src
0x18000a6d8  mov     r8, rbp; Size
0x18000a6db  mov     rcx, rax; void *
0x18000a6de  call    memcpy_0
0x18000a6e3  mov     ecx, 30h ; '0'; Size
0x18000a6e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6ed  mov     rsi, rax
0x18000a6f0  test    rax, rax
0x18000a6f3  jz      loc_18000A78C
0x18000a6f9  mov     ebp, 1
0x18000a6fe  mov     rdx, rdi; struct LISTENER_CHANNEL *
0x18000a701  mov     r8d, ebp; int
0x18000a704  mov     rcx, rax; this
0x18000a707  call    ??0LISTENER_CHANNEL_WORKITEM@@QEAA@PEAVLISTENER_CHANNEL@@H@Z; LISTENER_CHANNEL_WORKITEM::LISTENER_CHANNEL_WORKITEM(LISTENER_CHANNEL *,int)
0x18000a70c  lea     rax, ??_7LISTENER_CHANNEL_START_WORKITEM@@6B@; const LISTENER_CHANNEL_START_WORKITEM::`vftable'
0x18000a713  mov     [rsi], rax
0x18000a716  mov     ecx, [rdi+108h]
0x18000a71c  sub     ecx, 2; this
0x18000a71f  test    ecx, 0FFFFFFFDh
0x18000a725  jz      short loc_18000A75F
0x18000a727  mov     dword ptr [rdi+108h], 2
0x18000a731  lock add cs:?s_lNotStoppedCount@LISTENER_CHANNEL@@0JA, ebp; long LISTENER_CHANNEL::s_lNotStoppedCount
0x18000a738  mov     rdx, rsi; struct W3WP_HOST_WORKITEM *
0x18000a73b  call    ?QueueWorkItem@W3WP_HOST@@QEAAJPEAVW3WP_HOST_WORKITEM@@@Z; W3WP_HOST::QueueWorkItem(W3WP_HOST_WORKITEM *)
0x18000a740  mov     ebx, eax
0x18000a742  test    eax, eax
0x18000a744  jns     short loc_18000A788
0x18000a746  lock dec cs:?s_lNotStoppedCount@LISTENER_CHANNEL@@0JA; long LISTENER_CHANNEL::s_lNotStoppedCount
0x18000a74d  mov     edx, ebp
0x18000a74f  mov     rax, [rsi]
0x18000a752  mov     rcx, rsi
0x18000a755  mov     rax, [rax]
0x18000a758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a75d  jmp     short loc_18000A791
0x18000a75f  add     rdi, 128h
0x18000a766  mov     rcx, [rdi+8]
0x18000a76a  cmp     [rcx], rdi
0x18000a76d  jz      short loc_18000A776
0x18000a76f  mov     ecx, 3
0x18000a774  int     29h; Win8: RtlFailFast(ecx)
0x18000a776  lea     rax, [rsi+10h]
0x18000a77a  mov     [rax], rdi
0x18000a77d  mov     [rax+8], rcx
0x18000a781  mov     [rcx], rax
0x18000a784  mov     [rdi+8], rax
0x18000a788  xor     ebx, ebx
0x18000a78a  jmp     short loc_18000A791
0x18000a78c  mov     ebx, 80070008h
0x18000a791  mov     rcx, r14
0x18000a794  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a79a  mov     eax, ebx
0x18000a79c  add     rsp, 20h
0x18000a7a0  pop     r14
0x18000a7a2  pop     rdi
0x18000a7a3  pop     rsi
0x18000a7a4  pop     rbp
0x18000a7a5  pop     rbx
0x18000a7a6  retn
```

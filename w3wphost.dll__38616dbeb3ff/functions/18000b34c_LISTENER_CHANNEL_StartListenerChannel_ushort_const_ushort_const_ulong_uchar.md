# LISTENER_CHANNEL::StartListenerChannel(ushort const *,ushort const *,ulong,uchar *)

- ea: `0x18000b34c`
- end: `0x18000b4e6`
- name: `?StartListenerChannel@LISTENER_CHANNEL@@QEAAJPEBG0KPEAE@Z`
- size: `410`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000b8e8`

## callees

- `0x180002090`
- `0x1800069cc`
- `0x18000aaf0`
- `0x18000b34c`
- `0x18000d2a6`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3d2`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b4cc`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b4cc`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b36d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b36d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000b3c2`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000b3c2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b3ff`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b3ff`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b380`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b3a0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b380`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b3a0`

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
0x18000b34c  push    rbx
0x18000b34e  push    rbp
0x18000b34f  push    rsi
0x18000b350  push    rdi
0x18000b351  push    r14
0x18000b353  sub     rsp, 20h
0x18000b357  lea     r14, [rcx+118h]
0x18000b35e  mov     ebp, r9d
0x18000b361  mov     rdi, rcx
0x18000b364  mov     rsi, r8
0x18000b367  mov     rcx, r14
0x18000b36a  mov     rbx, rdx
0x18000b36d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b374  nop     dword ptr [rax+rax+00h]
0x18000b379  lea     rcx, [rdi+50h]
0x18000b37d  mov     rdx, rbx
0x18000b380  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b387  nop     dword ptr [rax+rax+00h]
0x18000b38c  mov     ebx, eax
0x18000b38e  test    eax, eax
0x18000b390  js      loc_18000B4C9
0x18000b396  lea     rcx, [rdi+88h]
0x18000b39d  mov     rdx, rsi
0x18000b3a0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b3a7  nop     dword ptr [rax+rax+00h]
0x18000b3ac  mov     ebx, eax
0x18000b3ae  test    eax, eax
0x18000b3b0  js      loc_18000B4C9
0x18000b3b6  lea     rsi, [rdi+0C0h]
0x18000b3bd  mov     edx, ebp
0x18000b3bf  mov     rcx, rsi
0x18000b3c2  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000b3c9  nop     dword ptr [rax+rax+00h]
0x18000b3ce  test    al, al
0x18000b3d0  jnz     short loc_18000B3F6
0x18000b3d2  call    cs:__imp_GetLastError
0x18000b3d9  nop     dword ptr [rax+rax+00h]
0x18000b3de  mov     ebx, eax
0x18000b3e0  test    eax, eax
0x18000b3e2  jle     loc_18000B4C9
0x18000b3e8  movzx   ebx, ax
0x18000b3eb  or      ebx, 80070000h
0x18000b3f1  jmp     loc_18000B4C9
0x18000b3f6  mov     rcx, rsi
0x18000b3f9  mov     [rdi+0F0h], ebp
0x18000b3ff  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b406  nop     dword ptr [rax+rax+00h]
0x18000b40b  mov     rdx, [rsp+48h+Src]; Src
0x18000b410  mov     r8, rbp; Size
0x18000b413  mov     rcx, rax; void *
0x18000b416  call    memcpy_0
0x18000b41b  mov     ecx, 30h ; '0'; Size
0x18000b420  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b425  mov     rsi, rax
0x18000b428  test    rax, rax
0x18000b42b  jz      loc_18000B4C4
0x18000b431  mov     ebp, 1
0x18000b436  mov     rdx, rdi; struct LISTENER_CHANNEL *
0x18000b439  mov     r8d, ebp; int
0x18000b43c  mov     rcx, rax; this
0x18000b43f  call    ??0LISTENER_CHANNEL_WORKITEM@@QEAA@PEAVLISTENER_CHANNEL@@H@Z; LISTENER_CHANNEL_WORKITEM::LISTENER_CHANNEL_WORKITEM(LISTENER_CHANNEL *,int)
0x18000b444  lea     rax, ??_7LISTENER_CHANNEL_START_WORKITEM@@6B@; const LISTENER_CHANNEL_START_WORKITEM::`vftable'
0x18000b44b  mov     [rsi], rax
0x18000b44e  mov     ecx, [rdi+108h]
0x18000b454  sub     ecx, 2; this
0x18000b457  test    ecx, 0FFFFFFFDh
0x18000b45d  jz      short loc_18000B497
0x18000b45f  mov     dword ptr [rdi+108h], 2
0x18000b469  lock add cs:?s_lNotStoppedCount@LISTENER_CHANNEL@@0JA, ebp; long LISTENER_CHANNEL::s_lNotStoppedCount
0x18000b470  mov     rdx, rsi; struct W3WP_HOST_WORKITEM *
0x18000b473  call    ?QueueWorkItem@W3WP_HOST@@QEAAJPEAVW3WP_HOST_WORKITEM@@@Z; W3WP_HOST::QueueWorkItem(W3WP_HOST_WORKITEM *)
0x18000b478  mov     ebx, eax
0x18000b47a  test    eax, eax
0x18000b47c  jns     short loc_18000B4C0
0x18000b47e  lock dec cs:?s_lNotStoppedCount@LISTENER_CHANNEL@@0JA; long LISTENER_CHANNEL::s_lNotStoppedCount
0x18000b485  mov     edx, ebp
0x18000b487  mov     rax, [rsi]
0x18000b48a  mov     rcx, rsi
0x18000b48d  mov     rax, [rax]
0x18000b490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b495  jmp     short loc_18000B4C9
0x18000b497  add     rdi, 128h
0x18000b49e  mov     rcx, [rdi+8]
0x18000b4a2  cmp     [rcx], rdi
0x18000b4a5  jz      short loc_18000B4AE
0x18000b4a7  mov     ecx, 3
0x18000b4ac  int     29h; Win8: RtlFailFast(ecx)
0x18000b4ae  lea     rax, [rsi+10h]
0x18000b4b2  mov     [rax], rdi
0x18000b4b5  mov     [rax+8], rcx
0x18000b4b9  mov     [rcx], rax
0x18000b4bc  mov     [rdi+8], rax
0x18000b4c0  xor     ebx, ebx
0x18000b4c2  jmp     short loc_18000B4C9
0x18000b4c4  mov     ebx, 80070008h
0x18000b4c9  mov     rcx, r14
0x18000b4cc  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b4d3  nop     dword ptr [rax+rax+00h]
0x18000b4d8  mov     eax, ebx
0x18000b4da  add     rsp, 20h
0x18000b4de  pop     r14
0x18000b4e0  pop     rdi
0x18000b4e1  pop     rsi
0x18000b4e2  pop     rbp
0x18000b4e3  pop     rbx
0x18000b4e4  retn
```

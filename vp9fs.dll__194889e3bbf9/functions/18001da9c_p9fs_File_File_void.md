# p9fs::File::~File(void)

- ea: `0x18001da9c`
- end: `0x18001db4c`
- name: `??1File@p9fs@@UEAA@XZ`
- size: `176`
- prototype: `void __fastcall(p9fs::File *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001df90`
- `0x18001fbb0`
- `0x1800212b8`
- `0x180022728`
- `0x180022e00`
- `0x18003211b`
- `0x180032366`
- `0x18003256d`

## callees

- `0x180004534`
- `0x18001d940`
- `0x18001da9c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001db1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001db1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001db16`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001db16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db33`
- `lxutil!LxUtilDirectoryEnumeratorCleanup` at `0x18001dab5`
- `lxutil!LxUtilDirectoryEnumeratorCleanup` at `0x18001dab5`

## pseudocode

```c
void __fastcall p9fs::File::~File(p9fs::File *this)
{
  void *v1; // rbx
  volatile signed __int32 *v3; // rbx
  struct _TP_IO *v4; // rbx
  char *v5; // rcx

  v1 = (void *)*((_QWORD *)this + 12);
  if ( v1 )
  {
    LxUtilDirectoryEnumeratorCleanup(*((_QWORD *)this + 12));
    operator delete(v1, 0x28u);
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (struct _TP_IO *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    WaitForThreadpoolIoCallbacks(*((PTP_IO *)this + 7), 0);
    CloseThreadpoolIo(v4);
  }
  v5 = (char *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  std::wstring::~wstring((char *)this + 16);
}

```

## disassembly

```asm
0x18001da9c  mov     [rsp+arg_0], rbx
0x18001daa1  push    rdi
0x18001daa2  sub     rsp, 20h
0x18001daa6  mov     rbx, [rcx+60h]
0x18001daaa  mov     rdi, rcx
0x18001daad  test    rbx, rbx
0x18001dab0  jz      short loc_18001DAC8
0x18001dab2  mov     rcx, rbx
0x18001dab5  call    cs:__imp_LxUtilDirectoryEnumeratorCleanup
0x18001dabb  mov     edx, 28h ; '('; unsigned __int64
0x18001dac0  mov     rcx, rbx; void *
0x18001dac3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001dac8  mov     rbx, [rdi+50h]
0x18001dacc  test    rbx, rbx
0x18001dacf  jz      short loc_18001DB08
0x18001dad1  or      eax, 0FFFFFFFFh
0x18001dad4  lock xadd [rbx+8], eax
0x18001dad9  cmp     eax, 1
0x18001dadc  jnz     short loc_18001DB08
0x18001dade  mov     rax, [rbx]
0x18001dae1  mov     rcx, rbx
0x18001dae4  mov     rax, [rax]
0x18001dae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daec  or      eax, 0FFFFFFFFh
0x18001daef  lock xadd [rbx+0Ch], eax
0x18001daf4  cmp     eax, 1
0x18001daf7  jnz     short loc_18001DB08
0x18001daf9  mov     rax, [rbx]
0x18001dafc  mov     rcx, rbx
0x18001daff  mov     rax, [rax+8]
0x18001db03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db08  mov     rbx, [rdi+38h]
0x18001db0c  test    rbx, rbx
0x18001db0f  jz      short loc_18001DB25
0x18001db11  xor     edx, edx; fCancelPendingCallbacks
0x18001db13  mov     rcx, rbx; pio
0x18001db16  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18001db1c  mov     rcx, rbx; pio
0x18001db1f  call    cs:__imp_CloseThreadpoolIo
0x18001db25  mov     rcx, [rdi+30h]; hObject
0x18001db29  lea     rax, [rcx-1]
0x18001db2d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001db31  ja      short loc_18001DB39
0x18001db33  call    cs:__imp_CloseHandle
0x18001db39  lea     rcx, [rdi+10h]
0x18001db3d  mov     rbx, [rsp+28h+arg_0]
0x18001db42  add     rsp, 20h
0x18001db46  pop     rdi
0x18001db47  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```

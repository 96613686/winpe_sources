# p9fs::Socket::`vector deleting destructor'(uint)

- ea: `0x180024a80`
- end: `0x180024ae7`
- name: `??_ESocket@p9fs@@UEAAPEAXI@Z`
- size: `103`
- prototype: `void *__fastcall(p9fs::Socket *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180004534`
- `0x180024a80`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180024aab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180024aab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180024aa2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180024aa2`
- `WS2_32!__imp_closesocket` at `0x180024abb`
- `WS2_32!__imp_closesocket` at `0x180024abb`

## pseudocode

```c
p9fs::Socket *__fastcall p9fs::Socket::`vector deleting destructor'(p9fs::Socket *this, char a2)
{
  struct _TP_IO *v2; // rdi
  SOCKET v5; // rcx

  v2 = (struct _TP_IO *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    WaitForThreadpoolIoCallbacks(v2, 0);
    CloseThreadpoolIo(v2);
  }
  v5 = *((_QWORD *)this + 1);
  if ( v5 != -1 )
    closesocket(v5);
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x28u);
  return this;
}

```

## disassembly

```asm
0x180024a80  mov     [rsp+arg_0], rbx
0x180024a85  mov     [rsp+arg_8], rsi
0x180024a8a  push    rdi
0x180024a8b  sub     rsp, 20h
0x180024a8f  mov     rdi, [rcx+10h]
0x180024a93  mov     esi, edx
0x180024a95  mov     rbx, rcx
0x180024a98  test    rdi, rdi
0x180024a9b  jz      short loc_180024AB1
0x180024a9d  xor     edx, edx; fCancelPendingCallbacks
0x180024a9f  mov     rcx, rdi; pio
0x180024aa2  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180024aa8  mov     rcx, rdi; pio
0x180024aab  call    cs:__imp_CloseThreadpoolIo
0x180024ab1  mov     rcx, [rbx+8]; s
0x180024ab5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180024ab9  jz      short loc_180024AC1
0x180024abb  call    cs:__imp_closesocket
0x180024ac1  test    sil, 1
0x180024ac5  jz      short loc_180024AD4
0x180024ac7  mov     edx, 28h ; '('; unsigned __int64
0x180024acc  mov     rcx, rbx; void *
0x180024acf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024ad4  mov     rsi, [rsp+28h+arg_8]
0x180024ad9  mov     rax, rbx
0x180024adc  mov     rbx, [rsp+28h+arg_0]
0x180024ae1  add     rsp, 20h
0x180024ae5  pop     rdi
0x180024ae6  retn
```

# p9fs::Socket::~Socket(void)

- ea: `0x1800247c0`
- end: `0x180024805`
- name: `??1Socket@p9fs@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(p9fs::Socket *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003261a`
- `0x1800326cc`

## callees

- `0x1800247c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800247e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800247e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800247db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800247db`
- `WS2_32!__imp_closesocket` at `0x1800247f4`
- `WS2_32!__imp_closesocket` at `0x1800247f4`

## pseudocode

```c
void __fastcall p9fs::Socket::~Socket(p9fs::Socket *this)
{
  struct _TP_IO *v1; // rbx
  SOCKET v3; // rcx

  v1 = (struct _TP_IO *)*((_QWORD *)this + 2);
  if ( v1 )
  {
    WaitForThreadpoolIoCallbacks(*((PTP_IO *)this + 2), 0);
    CloseThreadpoolIo(v1);
  }
  v3 = *((_QWORD *)this + 1);
  if ( v3 != -1 )
    closesocket(v3);
}

```

## disassembly

```asm
0x1800247c0  mov     [rsp+arg_0], rbx
0x1800247c5  push    rdi
0x1800247c6  sub     rsp, 20h
0x1800247ca  mov     rbx, [rcx+10h]
0x1800247ce  mov     rdi, rcx
0x1800247d1  test    rbx, rbx
0x1800247d4  jz      short loc_1800247EA
0x1800247d6  xor     edx, edx; fCancelPendingCallbacks
0x1800247d8  mov     rcx, rbx; pio
0x1800247db  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800247e1  mov     rcx, rbx; pio
0x1800247e4  call    cs:__imp_CloseThreadpoolIo
0x1800247ea  mov     rcx, [rdi+8]; s
0x1800247ee  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800247f2  jz      short loc_1800247FA
0x1800247f4  call    cs:__imp_closesocket
0x1800247fa  mov     rbx, [rsp+28h+arg_0]
0x1800247ff  add     rsp, 20h
0x180024803  pop     rdi
0x180024804  retn
```

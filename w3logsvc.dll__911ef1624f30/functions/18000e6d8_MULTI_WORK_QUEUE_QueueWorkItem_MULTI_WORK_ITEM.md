# MULTI_WORK_QUEUE::QueueWorkItem(MULTI_WORK_ITEM *)

- ea: `0x18000e6d8`
- end: `0x18000e758`
- name: `?QueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `128`
- prototype: `__int64 __fastcall(MULTI_WORK_QUEUE *this, void (__fastcall ***)(struct MULTI_WORK_ITEM *, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e4c4`

## callees

- `0x18000e6d8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e713`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000e6ff`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000e6ff`

## pseudocode

```c
__int64 __fastcall MULTI_WORK_QUEUE::QueueWorkItem(
        MULTI_WORK_QUEUE *this,
        void (__fastcall ***a2)(struct MULTI_WORK_ITEM *, __int64))
{
  unsigned int v3; // ebx
  signed int LastError; // eax

  if ( *((_DWORD *)this + 3) )
  {
    v3 = -2147024726;
    goto LABEL_10;
  }
  v3 = 0;
  if ( TrySubmitThreadpoolCallback(
         (PTP_SIMPLE_CALLBACK)MultiWorkQueueWorkCallback,
         a2,
         (PTP_CALLBACK_ENVIRON)((char *)this + 16)) )
  {
    return v3;
  }
  if ( !GetLastError() )
  {
    v3 = -2147467259;
LABEL_10:
    if ( a2 )
      (**a2)((struct MULTI_WORK_ITEM *)a2, 1);
    return v3;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( (v3 & 0x80000000) != 0 )
    goto LABEL_10;
  return v3;
}

```

## disassembly

```asm
0x18000e6d8  mov     [rsp+arg_0], rbx
0x18000e6dd  push    rdi
0x18000e6de  sub     rsp, 20h
0x18000e6e2  cmp     dword ptr [rcx+0Ch], 0
0x18000e6e6  mov     rdi, rdx
0x18000e6e9  jz      short loc_18000E6F2
0x18000e6eb  mov     ebx, 800700AAh
0x18000e6f0  jmp     short loc_18000E733
0x18000e6f2  lea     r8, [rcx+10h]; pcbe
0x18000e6f6  xor     ebx, ebx
0x18000e6f8  lea     rcx, ?MultiWorkQueueWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000e6ff  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000e705  test    eax, eax
0x18000e707  jnz     short loc_18000E74B
0x18000e709  call    cs:__imp_GetLastError
0x18000e70f  test    eax, eax
0x18000e711  jz      short loc_18000E72E
0x18000e713  call    cs:__imp_GetLastError
0x18000e719  mov     ebx, eax
0x18000e71b  test    eax, eax
0x18000e71d  jle     short loc_18000E728
0x18000e71f  movzx   ebx, ax
0x18000e722  or      ebx, 80070000h
0x18000e728  test    ebx, ebx
0x18000e72a  jns     short loc_18000E74B
0x18000e72c  jmp     short loc_18000E733
0x18000e72e  mov     ebx, 80004005h
0x18000e733  test    rdi, rdi
0x18000e736  jz      short loc_18000E74B
0x18000e738  mov     rcx, [rdi]
0x18000e73b  mov     edx, 1
0x18000e740  mov     rax, [rcx]
0x18000e743  mov     rcx, rdi
0x18000e746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e74b  mov     eax, ebx
0x18000e74d  mov     rbx, [rsp+28h+arg_0]
0x18000e752  add     rsp, 20h
0x18000e756  pop     rdi
0x18000e757  retn
```

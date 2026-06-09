# UlAtqFreeContext(void *)

- ea: `0x18000ecb0`
- end: `0x18000edb3`
- name: `?UlAtqFreeContext@@YAXPEAX@Z`
- size: `259`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000f770`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eda8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eda8`
- `W3TP!ThreadPoolPostCompletion` at `0x18000ed73`

## pseudocode

```c
void __fastcall UlAtqFreeContext(char *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  char *v4; // rcx

  if ( UL_NATIVE_REQUEST::sm_cRequestsPending >= 2 * UL_NATIVE_REQUEST::sm_cDesiredPendingRequests )
  {
    UL_NATIVE_REQUEST::FreeWorkerRequest((struct UL_NATIVE_REQUEST *)a1);
  }
  else
  {
    v2 = (void *)*((_QWORD *)a1 + 376);
    if ( v2 )
    {
      CloseHandle(v2);
      *((_QWORD *)a1 + 376) = 0;
    }
    v3 = (void *)*((_QWORD *)a1 + 377);
    if ( v3 )
    {
      CloseHandle(v3);
      *((_QWORD *)a1 + 377) = 0;
    }
    v4 = (char *)*((_QWORD *)a1 + 368);
    if ( v4 != a1 + 32 )
      LocalFree(v4);
    ++*((_DWORD *)a1 + 756);
    *((_QWORD *)a1 + 2) = 0;
    *((_QWORD *)a1 + 368) = a1 + 32;
    *((_DWORD *)a1 + 738) = 2912;
    *((_DWORD *)a1 + 1) = 0;
    *((_QWORD *)a1 + 1) = 0;
    *((_QWORD *)a1 + 3) = 0;
    *((_DWORD *)a1 + 784) = 0;
    *((_OWORD *)a1 + 194) = 0;
    *((_OWORD *)a1 + 195) = 0;
    *(_OWORD *)(a1 + 3064) = 0;
    *(_OWORD *)(a1 + 3080) = 0;
    ThreadPoolPostCompletion(
      *((_DWORD *)a1 + 4),
      (void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))WP_CONTEXT::OnCompletion,
      (struct _OVERLAPPED *)a1 + 97);
  }
}

```

## disassembly

```asm
0x18000ecb0  push    rbx
0x18000ecb2  sub     rsp, 20h
0x18000ecb6  mov     eax, cs:?sm_cDesiredPendingRequests@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cDesiredPendingRequests
0x18000ecbc  mov     rbx, rcx
0x18000ecbf  add     eax, eax
0x18000ecc1  cmp     cs:?sm_cRequestsPending@UL_NATIVE_REQUEST@@0KA, eax; ulong UL_NATIVE_REQUEST::sm_cRequestsPending
0x18000ecc7  jnb     loc_18000ED7A
0x18000eccd  mov     rcx, [rcx+0BC0h]; hObject
0x18000ecd4  mov     [rsp+28h+arg_0], rsi
0x18000ecd9  xor     esi, esi
0x18000ecdb  mov     [rsp+28h+arg_8], rdi
0x18000ece0  test    rcx, rcx
0x18000ece3  jnz     loc_18000ED84
0x18000ece9  mov     rcx, [rbx+0BC8h]; hObject
0x18000ecf0  test    rcx, rcx
0x18000ecf3  jnz     loc_18000ED96
0x18000ecf9  mov     rcx, [rbx+0B80h]; hMem
0x18000ed00  lea     rdi, [rbx+20h]
0x18000ed04  cmp     rcx, rdi
0x18000ed07  jnz     loc_18000EDA8
0x18000ed0d  inc     dword ptr [rbx+0BD0h]
0x18000ed13  lea     r8, [rbx+0C20h]
0x18000ed1a  mov     [rbx+10h], rsi
0x18000ed1e  lea     rdx, ?OnCompletion@WP_CONTEXT@@SAXKKPEAU_OVERLAPPED@@@Z; WP_CONTEXT::OnCompletion(ulong,ulong,_OVERLAPPED *)
0x18000ed25  xorps   xmm0, xmm0
0x18000ed28  mov     [rbx+0B80h], rdi
0x18000ed2f  mov     dword ptr [rbx+0B88h], 0B60h
0x18000ed39  mov     [rbx+4], esi
0x18000ed3c  mov     [rbx+8], rsi
0x18000ed40  mov     [rbx+18h], rsi
0x18000ed44  mov     [rbx+0C40h], esi
0x18000ed4a  movups  xmmword ptr [r8], xmm0
0x18000ed4e  movups  xmmword ptr [r8+10h], xmm0
0x18000ed53  movups  xmmword ptr [rbx+0BF8h], xmm0
0x18000ed5a  movups  xmmword ptr [rbx+0C08h], xmm0
0x18000ed61  mov     ecx, [rbx+10h]; this
0x18000ed64  mov     rdi, [rsp+28h+arg_8]
0x18000ed69  mov     rsi, [rsp+28h+arg_0]
0x18000ed6e  add     rsp, 20h
0x18000ed72  pop     rbx
0x18000ed73  jmp     cs:__imp_?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x18000ed7a  add     rsp, 20h
0x18000ed7e  pop     rbx
0x18000ed7f  jmp     ?FreeWorkerRequest@UL_NATIVE_REQUEST@@SAXPEAV1@@Z; UL_NATIVE_REQUEST::FreeWorkerRequest(UL_NATIVE_REQUEST *)
0x18000ed84  call    cs:__imp_CloseHandle
0x18000ed8a  mov     [rbx+0BC0h], rsi
0x18000ed91  jmp     loc_18000ECE9
0x18000ed96  call    cs:__imp_CloseHandle
0x18000ed9c  mov     [rbx+0BC8h], rsi
0x18000eda3  jmp     loc_18000ECF9
0x18000eda8  call    cs:__imp_LocalFree
0x18000edae  jmp     loc_18000ED0D
```

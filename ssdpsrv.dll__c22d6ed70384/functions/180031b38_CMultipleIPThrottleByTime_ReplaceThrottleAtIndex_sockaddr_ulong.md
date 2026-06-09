# CMultipleIPThrottleByTime::ReplaceThrottleAtIndex(sockaddr *,ulong)

- ea: `0x180031b38`
- end: `0x180031bc2`
- name: `?ReplaceThrottleAtIndex@CMultipleIPThrottleByTime@@IEAAHPEAUsockaddr@@K@Z`
- size: `138`
- prototype: `__int64 __fastcall(CMultipleIPThrottleByTime *this, struct sockaddr *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800229f0`

## callees

- `0x1800307dc`
- `0x180031884`
- `0x180031b38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031b74`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031b74`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031b63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031b63`

## pseudocode

```c
__int64 __fastcall CMultipleIPThrottleByTime::ReplaceThrottleAtIndex(
        CMultipleIPThrottleByTime *this,
        struct sockaddr *a2,
        unsigned int a3)
{
  unsigned int v3; // esi
  __int64 v4; // rdi
  DWORD *v7; // r14
  unsigned int v8; // edx
  CSingleThrottleByTime *v9; // rcx

  v3 = 0;
  v4 = a3;
  v7 = *(DWORD **)(*((_QWORD *)this + 9) + 8LL * a3);
  if ( v7 )
  {
    v7[3] = v7[2];
    *v7 = GetTickCount();
    free(*(void **)(*((_QWORD *)this + 8) + 8 * v4));
    *(_QWORD *)(*((_QWORD *)this + 8) + 8 * v4) = DupSockAddr(a2);
    if ( *(_QWORD *)(*((_QWORD *)this + 8) + 8 * v4) )
    {
      return 1;
    }
    else
    {
      v9 = *(CSingleThrottleByTime **)(*((_QWORD *)this + 9) + 8 * v4);
      if ( v9 )
        CSingleThrottleByTime::`scalar deleting destructor'(v9, v8);
      *(_QWORD *)(*((_QWORD *)this + 9) + 8 * v4) = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180031b38  push    rbx
0x180031b3a  push    rbp
0x180031b3b  push    rsi
0x180031b3c  push    rdi
0x180031b3d  push    r14
0x180031b3f  sub     rsp, 20h
0x180031b43  mov     rax, [rcx+48h]
0x180031b47  xor     esi, esi
0x180031b49  mov     edi, r8d
0x180031b4c  mov     rbp, rdx
0x180031b4f  mov     rbx, rcx
0x180031b52  mov     r14, [rax+rdi*8]
0x180031b56  test    r14, r14
0x180031b59  jz      short loc_180031BB5
0x180031b5b  mov     eax, [r14+8]
0x180031b5f  mov     [r14+0Ch], eax
0x180031b63  call    cs:__imp_GetTickCount
0x180031b69  mov     [r14], eax
0x180031b6c  mov     rcx, [rbx+40h]
0x180031b70  mov     rcx, [rcx+rdi*8]; Block
0x180031b74  call    cs:__imp_free
0x180031b7a  mov     rcx, rbp; struct sockaddr *
0x180031b7d  call    ?DupSockAddr@@YAPEAUsockaddr_storage@@PEAUsockaddr@@@Z; DupSockAddr(sockaddr *)
0x180031b82  mov     rcx, [rbx+40h]
0x180031b86  mov     [rcx+rdi*8], rax
0x180031b8a  mov     rax, [rbx+40h]
0x180031b8e  cmp     [rax+rdi*8], rsi
0x180031b92  jnz     short loc_180031BB0
0x180031b94  mov     rax, [rbx+48h]
0x180031b98  mov     rcx, [rax+rdi*8]; this
0x180031b9c  test    rcx, rcx
0x180031b9f  jz      short loc_180031BA6
0x180031ba1  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x180031ba6  mov     rax, [rbx+48h]
0x180031baa  mov     [rax+rdi*8], rsi
0x180031bae  jmp     short loc_180031BB5
0x180031bb0  mov     esi, 1
0x180031bb5  mov     eax, esi
0x180031bb7  add     rsp, 20h
0x180031bbb  pop     r14
0x180031bbd  pop     rdi
0x180031bbe  pop     rsi
0x180031bbf  pop     rbp
0x180031bc0  pop     rbx
0x180031bc1  retn
```

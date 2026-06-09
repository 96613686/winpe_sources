# CMultipleIPThrottleByTime::ReplaceThrottleAtIndex(sockaddr *,ulong)

- ea: `0x180034430`
- end: `0x1800344c7`
- name: `?ReplaceThrottleAtIndex@CMultipleIPThrottleByTime@@IEAAHPEAUsockaddr@@K@Z`
- size: `151`
- prototype: `int(CMultipleIPThrottleByTime *__hidden this, struct sockaddr *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800243f0`

## callees

- `0x180032b9c`
- `0x180034154`
- `0x180034430`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034472`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034472`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003445b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003445b`

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
0x180034430  push    rbx
0x180034432  push    rbp
0x180034433  push    rsi
0x180034434  push    rdi
0x180034435  push    r14
0x180034437  sub     rsp, 20h
0x18003443b  mov     rax, [rcx+48h]
0x18003443f  xor     esi, esi
0x180034441  mov     edi, r8d
0x180034444  mov     rbp, rdx
0x180034447  mov     rbx, rcx
0x18003444a  mov     r14, [rax+rdi*8]
0x18003444e  test    r14, r14
0x180034451  jz      short loc_1800344B9
0x180034453  mov     eax, [r14+8]
0x180034457  mov     [r14+0Ch], eax
0x18003445b  call    cs:__imp_GetTickCount
0x180034462  nop     dword ptr [rax+rax+00h]
0x180034467  mov     [r14], eax
0x18003446a  mov     rcx, [rbx+40h]
0x18003446e  mov     rcx, [rcx+rdi*8]; Block
0x180034472  call    cs:__imp_free
0x180034479  nop     dword ptr [rax+rax+00h]
0x18003447e  mov     rcx, rbp; struct sockaddr *
0x180034481  call    ?DupSockAddr@@YAPEAUsockaddr_storage@@PEAUsockaddr@@@Z; DupSockAddr(sockaddr *)
0x180034486  mov     rcx, [rbx+40h]
0x18003448a  mov     [rcx+rdi*8], rax
0x18003448e  mov     rax, [rbx+40h]
0x180034492  cmp     [rax+rdi*8], rsi
0x180034496  jnz     short loc_1800344B4
0x180034498  mov     rax, [rbx+48h]
0x18003449c  mov     rcx, [rax+rdi*8]; this
0x1800344a0  test    rcx, rcx
0x1800344a3  jz      short loc_1800344AA
0x1800344a5  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x1800344aa  mov     rax, [rbx+48h]
0x1800344ae  mov     [rax+rdi*8], rsi
0x1800344b2  jmp     short loc_1800344B9
0x1800344b4  mov     esi, 1
0x1800344b9  mov     eax, esi
0x1800344bb  add     rsp, 20h
0x1800344bf  pop     r14
0x1800344c1  pop     rdi
0x1800344c2  pop     rsi
0x1800344c3  pop     rbp
0x1800344c4  pop     rbx
0x1800344c5  retn
```

# CPool<PxeRequest>::GetObjectW(int)

- ea: `0x180004f14`
- end: `0x180004ff9`
- name: `?GetObjectW@?$CPool@VPxeRequest@@@@QEAAPEAVPxeRequest@@H@Z`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005aa4`

## callees

- `0x180001ad8`
- `0x180004f14`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180004f2a`
- `KERNEL32!InterlockedPopEntrySList` at `0x180004f2a`

## pseudocode

```c
PSLIST_ENTRY __fastcall CPool<PxeRequest>::GetObjectW(__int64 a1)
{
  PSLIST_ENTRY v2; // rbx
  PSLIST_ENTRY v3; // rax
  char *v4; // rax

  v2 = 0;
  v3 = InterlockedPopEntrySList((PSLIST_HEADER)a1);
  if ( v3 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
    v2 = v3 - 13;
  }
  if ( !v2 )
  {
    v4 = (char *)operator new(0xE0u, (const struct std::nothrow_t *)&std::nothrow);
    v2 = (PSLIST_ENTRY)v4;
    if ( !v4 )
      return 0;
    *((_QWORD *)v4 + 23) = 0;
    *((_QWORD *)v4 + 24) = 0;
    *(_OWORD *)(v4 + 72) = 0;
    *((_QWORD *)v4 + 11) = 0;
    *((_DWORD *)v4 + 24) = 0;
    *(_OWORD *)(v4 + 100) = 0;
    *(_QWORD *)(v4 + 116) = 0;
    *(_QWORD *)(v4 + 124) = 0;
    *(_OWORD *)v4 = 0;
    *((_OWORD *)v4 + 1) = 0;
    *((_OWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 17) = 0;
    *((_QWORD *)v4 + 20) = 0;
    *((_QWORD *)v4 + 8) = 0;
    *((_DWORD *)v4 + 14) = 0;
    *((_QWORD *)v4 + 18) = 0;
    *((_DWORD *)v4 + 42) = 0;
    *((_QWORD *)v4 + 19) = 0;
  }
  _InterlockedExchange((volatile __int32 *)&v2[10].Next + 3, 2);
  v2[11].Next = (struct _SLIST_ENTRY *)a1;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
  return v2;
}

```

## disassembly

```asm
0x180004f14  mov     [rsp+arg_0], rbx
0x180004f19  mov     [rsp+arg_8], rsi
0x180004f1e  push    rdi
0x180004f1f  sub     rsp, 20h
0x180004f23  xor     esi, esi
0x180004f25  mov     rdi, rcx
0x180004f28  mov     ebx, esi
0x180004f2a  call    cs:__imp_InterlockedPopEntrySList
0x180004f31  nop     dword ptr [rax+rax+00h]
0x180004f36  test    rax, rax
0x180004f39  jz      short loc_180004F46
0x180004f3b  lock dec dword ptr [rdi+10h]
0x180004f3f  lea     rbx, [rax-0D0h]
0x180004f46  test    rbx, rbx
0x180004f49  jnz     short loc_180004FCA
0x180004f4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004f52  mov     ecx, 0E0h; unsigned __int64
0x180004f57  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004f5c  mov     rbx, rax
0x180004f5f  test    rax, rax
0x180004f62  jz      loc_180004FF4
0x180004f68  mov     [rax+0B8h], rsi
0x180004f6f  xorps   xmm0, xmm0
0x180004f72  mov     [rax+0C0h], rsi
0x180004f79  xor     eax, eax
0x180004f7b  movups  xmmword ptr [rbx+48h], xmm0
0x180004f7f  mov     [rbx+58h], rax
0x180004f83  mov     [rbx+60h], eax
0x180004f86  movups  xmmword ptr [rbx+64h], xmm0
0x180004f8a  mov     [rbx+74h], rax
0x180004f8e  mov     [rbx+7Ch], rax
0x180004f92  movups  xmmword ptr [rbx], xmm0
0x180004f95  movups  xmmword ptr [rbx+10h], xmm0
0x180004f99  movups  xmmword ptr [rbx+20h], xmm0
0x180004f9d  mov     [rbx+30h], rax
0x180004fa1  mov     [rbx+88h], rsi
0x180004fa8  mov     [rbx+0A0h], rsi
0x180004faf  mov     [rbx+40h], rsi
0x180004fb3  mov     [rbx+38h], esi
0x180004fb6  mov     [rbx+90h], rsi
0x180004fbd  mov     [rbx+0A8h], esi
0x180004fc3  mov     [rbx+98h], rsi
0x180004fca  mov     ecx, 2
0x180004fcf  xchg    ecx, [rbx+0ACh]
0x180004fd5  mov     [rbx+0B0h], rdi
0x180004fdc  lock inc dword ptr [rdi+20h]
0x180004fe0  mov     rsi, [rsp+28h+arg_8]
0x180004fe5  mov     rax, rbx
0x180004fe8  mov     rbx, [rsp+28h+arg_0]
0x180004fed  add     rsp, 20h
0x180004ff1  pop     rdi
0x180004ff2  retn
0x180004ff4  mov     rbx, rsi
0x180004ff7  jmp     short loc_180004FE0
```

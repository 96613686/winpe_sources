# Tpm20ResourceMgr::CleanAllCachedResponses(void)

- ea: `0x1400133c8`
- end: `0x14001341a`
- name: `?CleanAllCachedResponses@Tpm20ResourceMgr@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(Tpm20ResourceMgr *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000efc0`
- `0x140013210`
- `0x140016afc`
- `0x14001b394`

## callees

- `0x1400133c8`
- `0x140013490`
- `0x1400454a0`

## pseudocode

```c
void __fastcall Tpm20ResourceMgr::CleanAllCachedResponses(Tpm20ResourceMgr *this)
{
  int i; // edi
  void *v3; // rcx

  for ( i = 0; i < 5; ++i )
    Tpm20ResourceMgr::CleanCachedReadPublicResponse(this, i);
  v3 = (void *)*((_QWORD *)this + 20);
  if ( v3 )
  {
    TpmFree(v3);
    *((_QWORD *)this + 20) = 0;
    *((_DWORD *)this + 39) = 0;
  }
}

```

## disassembly

```asm
0x1400133c8  mov     [rsp+arg_0], rbx
0x1400133cd  push    rdi
0x1400133ce  sub     rsp, 20h
0x1400133d2  mov     rbx, rcx
0x1400133d5  xor     edi, edi
0x1400133d7  mov     edx, edi; int
0x1400133d9  mov     rcx, rbx; this
0x1400133dc  call    ?CleanCachedReadPublicResponse@Tpm20ResourceMgr@@AEAAHH@Z; Tpm20ResourceMgr::CleanCachedReadPublicResponse(int)
0x1400133e1  inc     edi
0x1400133e3  cmp     edi, 5
0x1400133e6  jl      short loc_1400133D7
0x1400133e8  mov     rcx, [rbx+0A0h]; void *
0x1400133ef  test    rcx, rcx
0x1400133f2  jz      short loc_14001340E
0x1400133f4  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x1400133f9  mov     qword ptr [rbx+0A0h], 0
0x140013404  mov     dword ptr [rbx+9Ch], 0
0x14001340e  mov     rbx, [rsp+28h+arg_0]
0x140013413  add     rsp, 20h
0x140013417  pop     rdi
0x140013418  retn
```

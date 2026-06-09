# WanNdisCloseAdapterComplete

- ea: `0x140017010`
- end: `0x1400170c8`
- name: `WanNdisCloseAdapterComplete`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002bb0`

## callees

- `0x140017010`
- `0x140019b00`

## import_xrefs

- `NDIS!NdisCompleteBindAdapterEx` at `0x140017097`
- `NDIS!NdisCompleteBindAdapterEx` at `0x140017097`
- `NDIS!NdisCompleteUnbindAdapterEx` at `0x1400170ab`
- `NDIS!NdisCompleteUnbindAdapterEx` at `0x1400170ab`

## pseudocode

```c
void __fastcall WanNdisCloseAdapterComplete(__int64 a1)
{
  NDIS_HANDLE v1; // rbx
  NDIS_HANDLE v2; // rdi
  __int64 *v3; // rax
  NDIS_STATUS v4; // esi
  bool v5; // zf
  __int64 *v6; // rax

  v1 = (NDIS_HANDLE)qword_140009A18;
  v2 = (NDIS_HANDLE)qword_140009A10;
  v3 = &qword_140009A18;
  v4 = dword_140009A20;
  v5 = a1 == 212578788;
  if ( a1 != 212578788 )
  {
    v1 = UnbindContext;
    v3 = (__int64 *)&UnbindContext;
    v2 = BindAdapterContext;
    v4 = Status;
  }
  LOBYTE(a1) = a1 == 212578788;
  *v3 = 0;
  v6 = &qword_140009A10;
  if ( !v5 )
    v6 = (__int64 *)&BindAdapterContext;
  *v6 = 0;
  WanpFreeBindResourcesAndReleaseLock(a1, &BindAdapterContext);
  if ( v2 )
    NdisCompleteBindAdapterEx(v2, v4);
  if ( v1 )
    NdisCompleteUnbindAdapterEx(v1);
}

```

## disassembly

```asm
0x140017010  mov     [rsp+arg_0], rbx
0x140017015  mov     [rsp+arg_8], rsi
0x14001701a  push    rdi
0x14001701b  sub     rsp, 20h
0x14001701f  mov     rbx, cs:qword_140009A18
0x140017026  lea     rdx, UnbindContext
0x14001702d  mov     rdi, cs:qword_140009A10
0x140017034  lea     rax, qword_140009A18
0x14001703b  mov     esi, cs:dword_140009A20
0x140017041  mov     r8d, 0CABB1E4h
0x140017047  cmp     rcx, r8
0x14001704a  cmovnz  rbx, cs:UnbindContext
0x140017052  cmovnz  rax, rdx
0x140017056  cmovnz  rdi, cs:BindAdapterContext
0x14001705e  lea     rdx, BindAdapterContext
0x140017065  cmovnz  esi, cs:Status
0x14001706c  setz    cl
0x14001706f  mov     qword ptr [rax], 0
0x140017076  lea     rax, qword_140009A10
0x14001707d  cmovnz  rax, rdx
0x140017081  mov     qword ptr [rax], 0
0x140017088  call    WanpFreeBindResourcesAndReleaseLock
0x14001708d  test    rdi, rdi
0x140017090  jz      short loc_1400170A3
0x140017092  mov     edx, esi; Status
0x140017094  mov     rcx, rdi; BindAdapterContext
0x140017097  call    cs:__imp_NdisCompleteBindAdapterEx
0x14001709e  nop     dword ptr [rax+rax+00h]
0x1400170a3  test    rbx, rbx
0x1400170a6  jz      short loc_1400170B7
0x1400170a8  mov     rcx, rbx; UnbindContext
0x1400170ab  call    cs:__imp_NdisCompleteUnbindAdapterEx
0x1400170b2  nop     dword ptr [rax+rax+00h]
0x1400170b7  mov     rbx, [rsp+28h+arg_0]
0x1400170bc  mov     rsi, [rsp+28h+arg_8]
0x1400170c1  add     rsp, 20h
0x1400170c5  pop     rdi
0x1400170c6  retn
```

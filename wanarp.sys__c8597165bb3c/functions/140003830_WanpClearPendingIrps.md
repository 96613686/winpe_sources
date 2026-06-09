# WanpClearPendingIrps

- ea: `0x140003830`
- end: `0x1400038e1`
- name: `WanpClearPendingIrps`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003ba8`
- `0x1400139e8`

## callees

- `0x140003830`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000389b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400038c9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000389b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400038c9`
- `ntoskrnl!IofCompleteRequest` at `0x1400038b0`
- `ntoskrnl!IofCompleteRequest` at `0x1400038b0`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140003858`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140003858`

## pseudocode

```c
void __fastcall WanpClearPendingIrps(char a1)
{
  __int64 *v1; // rdi
  __int64 *v2; // rbx
  __int64 v3; // rax
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  Irql = 0;
  v1 = &g_lePendingV4IrpList;
  if ( !a1 )
    v1 = &g_lePendingV6IrpList;
  while ( 1 )
  {
    IoAcquireCancelSpinLock(&Irql);
    v2 = (__int64 *)*v1;
    if ( (__int64 *)*v1 == v1 )
      break;
    if ( (__int64 *)v2[1] != v1 || (v3 = *v2, *(__int64 **)(*v2 + 8) != v2) )
      __fastfail(3u);
    *v1 = v3;
    *(_QWORD *)(v3 + 8) = v1;
    _InterlockedExchange64(v2 - 8, 0);
    *((_DWORD *)v2 - 30) = -1073741810;
    *(v2 - 14) = 0;
    IoReleaseCancelSpinLock(Irql);
    IofCompleteRequest((PIRP)(v2 - 21), 2);
  }
  IoReleaseCancelSpinLock(Irql);
}

```

## disassembly

```asm
0x140003830  mov     [rsp+arg_8], rbx
0x140003835  push    rdi
0x140003836  sub     rsp, 20h
0x14000383a  test    cl, cl
0x14000383c  mov     [rsp+28h+Irql], 0
0x140003841  lea     rax, g_lePendingV6IrpList
0x140003848  lea     rdi, g_lePendingV4IrpList
0x14000384f  cmovz   rdi, rax
0x140003853  lea     rcx, [rsp+28h+Irql]; Irql
0x140003858  call    cs:__imp_IoAcquireCancelSpinLock
0x14000385f  nop     dword ptr [rax+rax+00h]
0x140003864  mov     rbx, [rdi]
0x140003867  cmp     rbx, rdi
0x14000386a  jz      short loc_1400038C5
0x14000386c  cmp     [rbx+8], rdi
0x140003870  jnz     short loc_1400038BE
0x140003872  mov     rax, [rbx]
0x140003875  cmp     [rax+8], rbx
0x140003879  jnz     short loc_1400038BE
0x14000387b  mov     [rdi], rax
0x14000387e  mov     [rax+8], rdi
0x140003882  xor     eax, eax
0x140003884  xchg    rax, [rbx-40h]
0x140003888  mov     dword ptr [rbx-78h], 0C000000Eh
0x14000388f  mov     qword ptr [rbx-70h], 0
0x140003897  mov     cl, [rsp+28h+Irql]; Irql
0x14000389b  call    cs:__imp_IoReleaseCancelSpinLock
0x1400038a2  nop     dword ptr [rax+rax+00h]
0x1400038a7  mov     dl, 2; PriorityBoost
0x1400038a9  lea     rcx, [rbx-0A8h]; Irp
0x1400038b0  call    cs:__imp_IofCompleteRequest
0x1400038b7  nop     dword ptr [rax+rax+00h]
0x1400038bc  jmp     short loc_140003853
0x1400038be  mov     ecx, 3
0x1400038c3  int     29h; Win8: RtlFailFast(ecx)
0x1400038c5  mov     cl, [rsp+28h+Irql]; Irql
0x1400038c9  call    cs:__imp_IoReleaseCancelSpinLock
0x1400038d0  nop     dword ptr [rax+rax+00h]
0x1400038d5  mov     rbx, [rsp+28h+arg_8]
0x1400038da  add     rsp, 20h
0x1400038de  pop     rdi
0x1400038df  retn
```

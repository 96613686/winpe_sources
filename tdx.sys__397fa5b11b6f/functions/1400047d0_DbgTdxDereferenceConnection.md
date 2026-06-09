# DbgTdxDereferenceConnection

- ea: `0x1400047d0`
- end: `0x140004917`
- name: `DbgTdxDereferenceConnection`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010b0`
- `0x1400012b0`
- `0x1400023b0`
- `0x140002920`
- `0x140002ccc`
- `0x140002fb0`
- `0x140003c9c`
- `0x1400043b0`
- `0x140004df4`
- `0x140005b00`
- `0x1400087a0`
- `0x140009290`
- `0x14000a040`
- `0x14000aad0`
- `0x140010100`
- `0x140010748`
- `0x140011fd0`
- `0x140012a8c`
- `0x1400135a0`
- `0x1400135ec`
- `0x140013900`
- `0x1400139b0`
- `0x140013ad0`
- `0x140015780`
- `0x1400159f0`

## callees

- `0x1400047d0`
- `0x140013af4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400048b6`
- `ntoskrnl!IofCompleteRequest` at `0x1400048b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400047f6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400047f6`
- `ntoskrnl!RtlGetCallersAddress` at `0x140004843`
- `ntoskrnl!RtlGetCallersAddress` at `0x140004843`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000486b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000486b`

## pseudocode

```c
void __fastcall DbgTdxDereferenceConnection(__int64 a1, __int64 a2, int a3)
{
  KIRQL v6; // al
  int v7; // r9d
  __int64 v8; // r14
  KIRQL v9; // di
  int v10; // edx
  int v11; // r8d
  IRP *v12; // rcx
  PVOID CallersAddress; // [rsp+70h] [rbp+8h] BYREF

  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 368));
  v7 = *(_DWORD *)(a1 + 16) - 1;
  v8 = a1 + 32LL * *(unsigned int *)(a1 + 632);
  CallersAddress = 0;
  v9 = v6;
  *(_DWORD *)(v8 + 400) = v7;
  *(_QWORD *)(v8 + 376) = a2;
  *(_DWORD *)(v8 + 384) = a3;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v8 + 392));
  *(_DWORD *)(a1 + 632) = ((unsigned __int8)*(_DWORD *)(a1 + 632) + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 368), v9);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_qdssD(WPP_GLOBAL_Control->AttachedDevice, v10, v11, a1, *(_DWORD *)(v8 + 400), (__int64)"--", a2, a3);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
  {
    v12 = *(IRP **)(a1 + 48);
    if ( v12 )
    {
      v12->IoStatus.Status = 0;
      v12->IoStatus.Information = 0;
      *(_QWORD *)(a1 + 48) = 0;
      IofCompleteRequest(v12, 0);
    }
  }
}

```

## disassembly

```asm
0x1400047d0  mov     [rsp+arg_8], rbx
0x1400047d5  mov     [rsp+arg_10], rbp
0x1400047da  push    rsi
0x1400047db  push    rdi
0x1400047dc  push    r12
0x1400047de  push    r14
0x1400047e0  push    r15
0x1400047e2  sub     rsp, 40h
0x1400047e6  mov     rbx, rcx
0x1400047e9  mov     ebp, r8d
0x1400047ec  add     rcx, 170h; SpinLock
0x1400047f3  mov     r15, rdx
0x1400047f6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400047fd  nop     dword ptr [rax+rax+00h]
0x140004802  mov     r14d, [rbx+278h]
0x140004809  lea     rcx, [rsp+68h+CallersAddress]; CallersAddress
0x14000480e  mov     r9d, [rbx+10h]
0x140004812  xor     r12d, r12d
0x140004815  dec     r9d
0x140004818  shl     r14, 5
0x14000481c  add     r14, rbx
0x14000481f  mov     [rsp+68h+CallersAddress], r12
0x140004824  movzx   edi, al
0x140004827  lea     rdx, [r14+188h]; CallersCaller
0x14000482e  mov     [r14+190h], r9d
0x140004835  mov     [r14+178h], r15
0x14000483c  mov     [r14+180h], ebp
0x140004843  call    cs:__imp_RtlGetCallersAddress
0x14000484a  nop     dword ptr [rax+rax+00h]
0x14000484f  mov     eax, [rbx+278h]
0x140004855  lea     rcx, [rbx+170h]; SpinLock
0x14000485c  inc     eax
0x14000485e  movzx   edx, dil; NewIrql
0x140004862  and     eax, 7
0x140004865  mov     [rbx+278h], eax
0x14000486b  call    cs:__imp_KeReleaseSpinLock
0x140004872  nop     dword ptr [rax+rax+00h]
0x140004877  mov     rcx, cs:WPP_GLOBAL_Control
0x14000487e  lea     rax, WPP_GLOBAL_Control
0x140004885  cmp     rcx, rax
0x140004888  jz      short loc_140004890
0x14000488a  cmp     byte ptr [rcx+29h], 5
0x14000488e  jnb     short loc_1400048DD
0x140004890  mov     eax, 0FFFFFFFFh
0x140004895  lock xadd [rbx+10h], eax
0x14000489a  cmp     eax, 1
0x14000489d  jnz     short loc_1400048C2
0x14000489f  mov     rcx, [rbx+30h]; Irp
0x1400048a3  test    rcx, rcx
0x1400048a6  jz      short loc_1400048C2
0x1400048a8  mov     [rcx+30h], r12d
0x1400048ac  xor     edx, edx; PriorityBoost
0x1400048ae  mov     [rcx+38h], r12
0x1400048b2  mov     [rbx+30h], r12
0x1400048b6  call    cs:__imp_IofCompleteRequest
0x1400048bd  nop     dword ptr [rax+rax+00h]
0x1400048c2  mov     rbx, [rsp+68h+arg_8]
0x1400048c7  mov     rbp, [rsp+68h+arg_10]
0x1400048cf  add     rsp, 40h
0x1400048d3  pop     r15
0x1400048d5  pop     r14
0x1400048d7  pop     r12
0x1400048d9  pop     rdi
0x1400048da  pop     rsi
0x1400048db  retn
0x1400048dd  test    dword ptr [rcx+2Ch], 200h
0x1400048e4  jz      short loc_140004890
0x1400048e6  mov     rcx, [rcx+18h]
0x1400048ea  lea     rax, asc_14001AAE0; "--"
0x1400048f1  mov     [rsp+68h+var_30], ebp
0x1400048f5  mov     r9, rbx
0x1400048f8  mov     [rsp+68h+var_38], r15
0x1400048fd  mov     [rsp+68h+var_40], rax
0x140004902  mov     eax, [r14+190h]
0x140004909  mov     [rsp+68h+var_48], eax
0x14000490d  call    WPP_SF_qdssD
0x140004912  jmp     loc_140004890
```

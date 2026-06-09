# UbpmRunConsumerQueuedActions

- ea: `0x180018538`
- end: `0x180018603`
- name: `UbpmRunConsumerQueuedActions`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180019a30`
- `0x18002dcc0`
- `0x180035df0`

## callees

- `0x180018538`
- `0x180018610`
- `0x180035944`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800185e5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001858d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001858d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001859d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001859d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800185c9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800185c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800185a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800185a3`

## pseudocode

```c
__int64 __fastcall UbpmRunConsumerQueuedActions(__int64 a1, unsigned int a2, char a3)
{
  struct _GUID *v4; // rcx
  unsigned int v5; // ebx
  unsigned __int64 v8; // rax
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  v4 = (struct _GUID *)(*(_QWORD *)(a1 + 24) + 84LL);
  v5 = 0;
  v8 = -*(_QWORD *)&v4->Data1;
  if ( !*(_QWORD *)&v4->Data1 )
    v8 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] - *(_QWORD *)v4->Data4;
  if ( v8 && (int)UbpmUtilIsNetworkConnected(v4, &v10) >= 0 )
    LOBYTE(v5) = v10 != 0;
  v10 = v5;
  RtlAcquireSRWLockShared(a1 + 48);
  RtlAcquireSRWLockExclusive(a1 + 208);
  *(_DWORD *)(a1 + 216) = GetCurrentThreadId();
  UbpmpRunConsumerQueuedActions(a1, (struct _UBPM_CONSTRAINT_PRECHECK_INFO *)&v10, a2, a3);
  *(_DWORD *)(a1 + 216) = 0;
  RtlReleaseSRWLockExclusive(a1 + 208);
  return RtlReleaseSRWLockShared(a1 + 48);
}

```

## disassembly

```asm
0x180018538  mov     [rsp+arg_8], rbx
0x18001853d  mov     [rsp+arg_10], rbp
0x180018542  push    rsi
0x180018543  push    rdi
0x180018544  push    r14
0x180018546  sub     rsp, 20h
0x18001854a  mov     rsi, rcx
0x18001854d  mov     [rsp+38h+arg_0], 0
0x180018555  mov     rcx, [rcx+18h]
0x180018559  xorps   xmm0, xmm0
0x18001855c  add     rcx, 54h ; 'T'; struct _GUID *
0x180018560  xor     ebx, ebx
0x180018562  movq    rax, xmm0
0x180018567  mov     bpl, r8b
0x18001856a  mov     r14d, edx
0x18001856d  sub     rax, [rcx]
0x180018570  jnz     short loc_180018580
0x180018572  psrldq  xmm0, 8
0x180018577  movq    rax, xmm0
0x18001857c  sub     rax, [rcx+8]
0x180018580  test    rax, rax
0x180018583  jnz     short loc_1800185EC
0x180018585  mov     [rsp+38h+arg_0], ebx
0x180018589  lea     rcx, [rsi+30h]
0x18001858d  call    cs:__imp_RtlAcquireSRWLockShared
0x180018593  lea     rbx, [rsi+0D0h]
0x18001859a  mov     rcx, rbx
0x18001859d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800185a3  call    cs:__imp_GetCurrentThreadId
0x1800185a9  mov     r9b, bpl
0x1800185ac  lea     rdx, [rsp+38h+arg_0]
0x1800185b1  mov     r8d, r14d
0x1800185b4  mov     [rbx+8], eax
0x1800185b7  mov     rcx, rsi
0x1800185ba  call    ?UbpmpRunConsumerQueuedActions@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@W4_UBPM_QUEUED_ACTION_QUEUE_REASON@@E@Z; UbpmpRunConsumerQueuedActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_QUEUED_ACTION_QUEUE_REASON,uchar)
0x1800185bf  mov     rcx, rbx
0x1800185c2  mov     dword ptr [rbx+8], 0
0x1800185c9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800185cf  lea     rcx, [rsi+30h]
0x1800185d3  mov     rbx, [rsp+38h+arg_8]
0x1800185d8  mov     rbp, [rsp+38h+arg_10]
0x1800185dd  add     rsp, 20h
0x1800185e1  pop     r14
0x1800185e3  pop     rdi
0x1800185e4  pop     rsi
0x1800185e5  jmp     cs:__imp_RtlReleaseSRWLockShared
0x1800185ec  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x1800185f1  call    ?UbpmUtilIsNetworkConnected@@YAJPEAU_GUID@@PEAK@Z; UbpmUtilIsNetworkConnected(_GUID *,ulong *)
0x1800185f6  test    eax, eax
0x1800185f8  js      short loc_180018585
0x1800185fa  cmp     [rsp+38h+arg_0], ebx
0x1800185fe  setnz   bl
0x180018601  jmp     short loc_180018585
```

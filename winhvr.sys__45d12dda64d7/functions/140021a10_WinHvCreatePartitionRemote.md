# WinHvCreatePartitionRemote

- ea: `0x140021a10`
- end: `0x140021c2f`
- name: `WinHvCreatePartitionRemote`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140007980`
- `0x140009c90`
- `0x14000b008`
- `0x14000b040`
- `0x14001ffd0`
- `0x140021a10`
- `0x140021c40`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140021b7f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140021b7f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140021b3d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140021b3d`
- `ntoskrnl!KeInitializeEvent` at `0x140021b1a`
- `ntoskrnl!KeInitializeEvent` at `0x140021b1a`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140021b2a`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140021b2a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140021a34`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140021a34`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140021c0f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140021c0f`

## pseudocode

```c
__int64 __fastcall WinHvCreatePartitionRemote(
        __int64 a1,
        int a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        _QWORD *a6,
        __int64 (__fastcall *a7)(),
        __int64 a8)
{
  int Partition; // ebx
  __int64 Pool; // rdi
  __int64 (__fastcall *v15)(); // r15
  _QWORD *v16; // rax
  int v17; // ebp
  unsigned int v18; // eax

  if ( ExAcquireRundownProtection(&RunRef) )
  {
    if ( qword_1400160E0 )
    {
      Pool = WinHvpAllocatePool(66, 120, 1500923991);
      if ( !Pool )
        return 3221225626LL;
      v15 = WinHvpAutoDepositRemote;
      if ( a7 )
        v15 = a7;
      Partition = WinHvpCreatePartition(a2, a3, a4, a5, 0, 1, (__int64)a6);
      if ( Partition < 0 )
      {
        WinHvpFreePoolWithTag(Pool, 1500923991);
      }
      else
      {
        *(_QWORD *)(Pool + 16) = a1;
        *(_QWORD *)(Pool + 24) = *a6;
        *(_DWORD *)(Pool + 32) = a3;
        *(_QWORD *)(Pool + 40) = v15;
        *(_QWORD *)(Pool + 48) = a8;
        *(_DWORD *)(Pool + 56) = 1;
        *(_QWORD *)(Pool + 64) = 0;
        *(_DWORD *)(Pool + 72) = 0;
        KeInitializeEvent((PRKEVENT)(Pool + 80), SynchronizationEvent, 0);
        ExInitializeRundownProtection((PEX_RUNDOWN_REF)(Pool + 112));
        ExAcquireFastMutex(&WinHvpRemoteIdMapLock);
        v16 = WinHvpRemoteIdMap;
        if ( *((_UNKNOWN ***)WinHvpRemoteIdMap + 1) != &WinHvpRemoteIdMap )
          __fastfail(3u);
        *(_QWORD *)(Pool + 8) = &WinHvpRemoteIdMap;
        v17 = 0;
        *(_QWORD *)Pool = v16;
        v16[1] = Pool;
        WinHvpRemoteIdMap = (_UNKNOWN *)Pool;
        ExReleaseFastMutex(&WinHvpRemoteIdMapLock);
        v18 = -1070268405;
        while ( 1 )
        {
          Partition = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, int))v15)(
                        a8,
                        a1,
                        a3,
                        v18,
                        65,
                        v17);
          if ( Partition < 0 )
            break;
          v18 = WinHvpInitializePartitionRemote(*a6);
          ++v17;
          if ( v18 != -1070268405 && v18 != -1070268299 && v18 != -1070268287 && v18 != -1070268286 )
          {
            Partition = ((__int64 (__fastcall *)(__int64, _QWORD))qword_1400160E0)(a1, *a6);
            if ( Partition >= 0 )
              goto LABEL_21;
            break;
          }
        }
        WinHvDeletePartitionRemote(a1);
      }
    }
    else
    {
      Partition = -1070268414;
    }
LABEL_21:
    ExReleaseRundownProtection(&RunRef);
  }
  else
  {
    return (unsigned int)-1070268408;
  }
  return (unsigned int)Partition;
}

```

## disassembly

```asm
0x140021a10  push    rbx
0x140021a12  push    rbp
0x140021a13  push    rsi
0x140021a14  push    rdi
0x140021a15  push    r12
0x140021a17  push    r13
0x140021a19  push    r14
0x140021a1b  push    r15
0x140021a1d  sub     rsp, 48h
0x140021a21  mov     rsi, rcx
0x140021a24  mov     ebx, r9d
0x140021a27  lea     rcx, RunRef; RunRef
0x140021a2e  mov     r12d, r8d
0x140021a31  mov     rbp, rdx
0x140021a34  call    cs:__imp_ExAcquireRundownProtection
0x140021a3b  nop     dword ptr [rax+rax+00h]
0x140021a40  test    al, al
0x140021a42  jnz     short loc_140021A4E
0x140021a44  mov     ebx, 0C0350008h
0x140021a49  jmp     loc_140021C1B
0x140021a4e  cmp     cs:qword_1400160E0, 0
0x140021a56  jnz     short loc_140021A62
0x140021a58  mov     ebx, 0C0350002h
0x140021a5d  jmp     loc_140021C08
0x140021a62  mov     edx, 78h ; 'x'
0x140021a67  mov     r13d, 59764857h
0x140021a6d  mov     r8d, r13d
0x140021a70  lea     ecx, [rdx-36h]
0x140021a73  call    WinHvpAllocatePool
0x140021a78  mov     rdi, rax
0x140021a7b  test    rax, rax
0x140021a7e  jnz     short loc_140021A8A
0x140021a80  mov     eax, 0C000009Ah
0x140021a85  jmp     loc_140021C1D
0x140021a8a  mov     rax, [rsp+88h+arg_30]
0x140021a92  lea     r15, WinHvpAutoDepositRemote
0x140021a99  mov     r14, [rsp+88h+arg_28]
0x140021aa1  test    rax, rax
0x140021aa4  mov     r9, [rsp+88h+arg_20]
0x140021aac  mov     r8d, ebx
0x140021aaf  mov     [rsp+88h+var_58], r14
0x140021ab4  mov     edx, r12d
0x140021ab7  mov     byte ptr [rsp+88h+var_60], 1
0x140021abc  mov     rcx, rbp
0x140021abf  cmovnz  r15, rax
0x140021ac3  mov     [rsp+88h+var_68], 0
0x140021acc  call    WinHvpCreatePartition
0x140021ad1  mov     ebx, eax
0x140021ad3  test    eax, eax
0x140021ad5  js      loc_140021BFD
0x140021adb  mov     r13, [rsp+88h+arg_38]
0x140021ae3  lea     rcx, [rdi+50h]; Event
0x140021ae7  mov     [rdi+10h], rsi
0x140021aeb  xor     r8d, r8d; State
0x140021aee  mov     rax, [r14]
0x140021af1  mov     [rdi+18h], rax
0x140021af5  mov     eax, 1
0x140021afa  mov     [rdi+20h], r12d
0x140021afe  mov     edx, eax; Type
0x140021b00  mov     [rdi+28h], r15
0x140021b04  mov     [rdi+30h], r13
0x140021b08  mov     [rdi+38h], eax
0x140021b0b  mov     qword ptr [rdi+40h], 0
0x140021b13  mov     dword ptr [rdi+48h], 0
0x140021b1a  call    cs:__imp_KeInitializeEvent
0x140021b21  nop     dword ptr [rax+rax+00h]
0x140021b26  lea     rcx, [rdi+70h]; RunRef
0x140021b2a  call    cs:__imp_ExInitializeRundownProtection
0x140021b31  nop     dword ptr [rax+rax+00h]
0x140021b36  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x140021b3d  call    cs:__imp_ExAcquireFastMutex
0x140021b44  nop     dword ptr [rax+rax+00h]
0x140021b49  mov     rax, cs:WinHvpRemoteIdMap
0x140021b50  lea     rcx, WinHvpRemoteIdMap
0x140021b57  cmp     [rax+8], rcx
0x140021b5b  jz      short loc_140021B64
0x140021b5d  mov     ecx, 3
0x140021b62  int     29h; Win8: RtlFailFast(ecx)
0x140021b64  mov     [rdi+8], rcx
0x140021b68  xor     ebp, ebp
0x140021b6a  mov     [rdi], rax
0x140021b6d  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x140021b74  mov     [rax+8], rdi
0x140021b78  mov     cs:WinHvpRemoteIdMap, rdi
0x140021b7f  call    cs:__imp_ExReleaseFastMutex
0x140021b86  nop     dword ptr [rax+rax+00h]
0x140021b8b  mov     edi, 0C035000Bh
0x140021b90  mov     eax, edi
0x140021b92  mov     r9d, eax
0x140021b95  mov     [rsp+88h+var_60], ebp
0x140021b99  mov     rax, r15
0x140021b9c  mov     dword ptr [rsp+88h+var_68], 41h ; 'A'
0x140021ba4  mov     r8d, r12d
0x140021ba7  mov     rdx, rsi
0x140021baa  mov     rcx, r13
0x140021bad  call    _guard_dispatch_icall
0x140021bb2  mov     ebx, eax
0x140021bb4  test    eax, eax
0x140021bb6  js      short loc_140021BF3
0x140021bb8  mov     rcx, [r14]
0x140021bbb  call    WinHvpInitializePartitionRemote
0x140021bc0  inc     ebp
0x140021bc2  cmp     eax, edi
0x140021bc4  jz      short loc_140021B92
0x140021bc6  cmp     eax, 0C0350075h
0x140021bcb  jz      short loc_140021B92
0x140021bcd  cmp     eax, 0C0350081h
0x140021bd2  jz      short loc_140021B92
0x140021bd4  cmp     eax, 0C0350082h
0x140021bd9  jz      short loc_140021B92
0x140021bdb  mov     rdx, [r14]
0x140021bde  mov     rcx, rsi
0x140021be1  mov     rax, cs:qword_1400160E0
0x140021be8  call    _guard_dispatch_icall
0x140021bed  mov     ebx, eax
0x140021bef  test    eax, eax
0x140021bf1  jns     short loc_140021C08
0x140021bf3  mov     rcx, rsi
0x140021bf6  call    WinHvDeletePartitionRemote
0x140021bfb  jmp     short loc_140021C08
0x140021bfd  mov     edx, r13d
0x140021c00  mov     rcx, rdi
0x140021c03  call    WinHvpFreePoolWithTag
0x140021c08  lea     rcx, RunRef; RunRef
0x140021c0f  call    cs:__imp_ExReleaseRundownProtection
0x140021c16  nop     dword ptr [rax+rax+00h]
0x140021c1b  mov     eax, ebx
0x140021c1d  add     rsp, 48h
0x140021c21  pop     r15
0x140021c23  pop     r14
0x140021c25  pop     r13
0x140021c27  pop     r12
0x140021c29  pop     rdi
0x140021c2a  pop     rsi
0x140021c2b  pop     rbp
0x140021c2c  pop     rbx
0x140021c2d  retn
```

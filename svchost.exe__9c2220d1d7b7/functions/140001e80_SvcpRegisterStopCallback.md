# SvcpRegisterStopCallback

- ea: `0x140001e80`
- end: `0x1400020d0`
- name: `SvcpRegisterStopCallback`
- size: `592`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140001e20`
- `0x140001e50`

## callees

- `0x140001e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140001f79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140001f79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002062`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002062`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140001f4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140001f4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140001ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000200d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000204a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140001ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000200d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000204a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140001f1f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140001f1f`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x140001fd3`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x140001fd3`
- `ntdll!TpAllocWait` at `0x140002095`
- `ntdll!TpAllocWait` at `0x140002095`
- `ntdll!TpSetWait` at `0x1400020b7`
- `ntdll!TpSetWait` at `0x1400020b7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x140008e39`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x140008e39`

## pseudocode

```c
__int64 __fastcall SvcpRegisterStopCallback(
        _QWORD *a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7)
{
  __int64 i; // rbp
  __int64 v13; // r15
  __int64 v14; // rbp
  unsigned int v15; // ebx
  _QWORD *v16; // rax
  void *v17; // r12
  char v18; // bl
  NTSTATUS v19; // r13d
  DWORD LastError; // eax
  __int64 v21; // [rsp+60h] [rbp+8h] BYREF

  v21 = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
    return 87;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= ServiceCount )
      return 13;
    v13 = 96 * i;
    if ( CompareStringOrdinal(a2, -1, *(LPCWCH *)(96 * i + ServiceArray), -1, 1) == 2 )
      break;
  }
  v14 = v13 + ServiceArray;
  if ( !(v13 + ServiceArray) )
    return 13;
  AcquireSRWLockExclusive((PSRWLOCK)(v14 + 32));
  if ( *(_QWORD *)(v14 + 24) )
  {
    v17 = 0;
    v15 = 13;
  }
  else
  {
    v15 = 8;
    v16 = HeapAlloc(g_hHeap, 8u, 0x10u);
    v17 = v16;
    if ( v16 )
    {
      v18 = a7;
      *v16 = a5;
      v16[1] = v14;
      if ( v18 )
      {
        v19 = 0;
        *a1 = RegisterWaitForSingleObjectEx(a3, SvchostStopCallback, v16, 0xFFFFFFFFLL, a6);
      }
      else
      {
        v19 = TpAllocWait(&v21, SvchostTpStopCallback, v16, 0);
        if ( v19 >= 0 )
        {
          TpSetWait(v21, a3, 0);
          *a1 = v21;
        }
      }
      if ( *a1 )
      {
        ++*(_DWORD *)(v14 + 48);
        v15 = 0;
        *(_QWORD *)(v14 + 24) = a4;
        ReleaseSRWLockExclusive((PSRWLOCK)(v14 + 32));
        return v15;
      }
      if ( v18 )
        LastError = GetLastError();
      else
        LastError = RtlNtStatusToDosErrorNoTeb(v19);
      v15 = LastError;
      ReleaseSRWLockExclusive((PSRWLOCK)(v14 + 32));
      if ( !v15 )
        return v15;
      goto LABEL_22;
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(v14 + 32));
LABEL_22:
  HeapFree(g_hHeap, 0, v17);
  return v15;
}

```

## disassembly

```asm
0x140001e80  push    rbx
0x140001e82  push    rsi
0x140001e83  push    rdi
0x140001e84  push    r14
0x140001e86  sub     rsp, 38h
0x140001e8a  mov     [rsp+58h+arg_0], 0
0x140001e93  mov     rdi, r9
0x140001e96  mov     rsi, r8
0x140001e99  mov     rbx, rdx
0x140001e9c  mov     r14, rcx
0x140001e9f  test    rcx, rcx
0x140001ea2  jz      loc_14000202E
0x140001ea8  test    rdx, rdx
0x140001eab  jz      loc_14000202E
0x140001eb1  test    r8, r8
0x140001eb4  jz      loc_14000202E
0x140001eba  test    r9, r9
0x140001ebd  jz      loc_14000202E
0x140001ec3  mov     [rsp+58h+arg_8], rbp
0x140001ec8  xor     ebp, ebp
0x140001eca  mov     [rsp+58h+var_28], r15
0x140001ecf  cmp     ebp, cs:ServiceCount
0x140001ed5  jb      short loc_140001EF1
0x140001ed7  mov     eax, 0Dh
0x140001edc  mov     r15, [rsp+58h+var_28]
0x140001ee1  mov     rbp, [rsp+58h+arg_8]
0x140001ee6  add     rsp, 38h
0x140001eea  pop     r14
0x140001eec  pop     rdi
0x140001eed  pop     rsi
0x140001eee  pop     rbx
0x140001eef  retn
0x140001ef1  mov     r8, cs:ServiceArray
0x140001ef8  lea     r15, ds:0[rbp*2]
0x140001f00  mov     r9d, 0FFFFFFFFh; cchCount2
0x140001f06  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x140001f0e  add     r15, rbp
0x140001f11  mov     edx, r9d; cchCount1
0x140001f14  shl     r15, 5
0x140001f18  mov     rcx, rbx; lpString1
0x140001f1b  mov     r8, [r15+r8]; lpString2
0x140001f1f  call    cs:__imp_CompareStringOrdinal
0x140001f26  nop     dword ptr [rax+rax+00h]
0x140001f2b  cmp     eax, 2
0x140001f2e  jnz     loc_14000207F
0x140001f34  mov     rbp, cs:ServiceArray
0x140001f3b  add     rbp, r15
0x140001f3e  jz      short loc_140001ED7
0x140001f40  mov     [rsp+58h+arg_10], r12
0x140001f45  lea     rcx, [rbp+20h]; SRWLock
0x140001f49  mov     [rsp+58h+arg_18], r13
0x140001f4e  call    cs:__imp_AcquireSRWLockExclusive
0x140001f55  nop     dword ptr [rax+rax+00h]
0x140001f5a  cmp     qword ptr [rbp+18h], 0
0x140001f5f  jnz     loc_14000203E
0x140001f65  mov     rcx, cs:g_hHeap; hHeap
0x140001f6c  mov     ebx, 8
0x140001f71  mov     edx, ebx; dwFlags
0x140001f73  mov     r8d, 10h; dwBytes
0x140001f79  call    cs:__imp_HeapAlloc
0x140001f80  nop     dword ptr [rax+rax+00h]
0x140001f85  mov     r12, rax
0x140001f88  test    rax, rax
0x140001f8b  jz      loc_140002046
0x140001f91  movzx   ebx, [rsp+58h+arg_30]
0x140001f99  mov     r8, r12
0x140001f9c  mov     rax, [rsp+58h+arg_20]
0x140001fa4  mov     [r12], rax
0x140001fa8  mov     [r12+8], rbp
0x140001fad  test    bl, bl
0x140001faf  jz      loc_140002086
0x140001fb5  mov     eax, [rsp+58h+arg_28]
0x140001fbc  lea     rdx, SvchostStopCallback
0x140001fc3  xor     r13d, r13d
0x140001fc6  mov     [rsp+58h+bIgnoreCase], eax
0x140001fca  mov     r9d, 0FFFFFFFFh
0x140001fd0  mov     rcx, rsi
0x140001fd3  call    cs:__imp_RegisterWaitForSingleObjectEx
0x140001fda  nop     dword ptr [rax+rax+00h]
0x140001fdf  mov     [r14], rax
0x140001fe2  cmp     qword ptr [r14], 0
0x140001fe6  jz      loc_140008E20
0x140001fec  inc     dword ptr [rbp+30h]
0x140001fef  lea     rcx, [rbp+20h]; SRWLock
0x140001ff3  xor     ebx, ebx
0x140001ff5  mov     [rbp+18h], rdi
0x140001ff9  call    cs:__imp_ReleaseSRWLockExclusive
0x140002000  nop     dword ptr [rax+rax+00h]
0x140002005  jmp     short loc_14000201D
0x140002007  mov     ebx, eax
0x140002009  lea     rcx, [rbp+20h]; SRWLock
0x14000200d  call    cs:__imp_ReleaseSRWLockExclusive
0x140002014  nop     dword ptr [rax+rax+00h]
0x140002019  test    ebx, ebx
0x14000201b  jnz     short loc_140002056
0x14000201d  mov     r13, [rsp+58h+arg_18]
0x140002022  mov     eax, ebx
0x140002024  mov     r12, [rsp+58h+arg_10]
0x140002029  jmp     loc_140001EDC
0x14000202e  mov     eax, 57h ; 'W'
0x140002033  add     rsp, 38h
0x140002037  pop     r14
0x140002039  pop     rdi
0x14000203a  pop     rsi
0x14000203b  pop     rbx
0x14000203c  retn
0x14000203e  xor     r12d, r12d
0x140002041  mov     ebx, 0Dh
0x140002046  lea     rcx, [rbp+20h]; SRWLock
0x14000204a  call    cs:__imp_ReleaseSRWLockExclusive
0x140002051  nop     dword ptr [rax+rax+00h]
0x140002056  mov     rcx, cs:g_hHeap; hHeap
0x14000205d  mov     r8, r12; lpMem
0x140002060  xor     edx, edx; dwFlags
0x140002062  call    cs:__imp_HeapFree
0x140002069  nop     dword ptr [rax+rax+00h]
0x14000206e  mov     r13, [rsp+58h+arg_18]
0x140002073  mov     eax, ebx
0x140002075  mov     r12, [rsp+58h+arg_10]
0x14000207a  jmp     loc_140001EDC
0x14000207f  inc     ebp
0x140002081  jmp     loc_140001ECF
0x140002086  xor     r9d, r9d
0x140002089  lea     rdx, SvchostTpStopCallback
0x140002090  lea     rcx, [rsp+58h+arg_0]
0x140002095  call    cs:__imp_TpAllocWait
0x14000209c  nop     dword ptr [rax+rax+00h]
0x1400020a1  mov     r13d, eax
0x1400020a4  test    eax, eax
0x1400020a6  js      loc_140001FE2
0x1400020ac  mov     rcx, [rsp+58h+arg_0]
0x1400020b1  xor     r8d, r8d
0x1400020b4  mov     rdx, rsi
0x1400020b7  call    cs:__imp_TpSetWait
0x1400020be  nop     dword ptr [rax+rax+00h]
0x1400020c3  mov     rcx, [rsp+58h+arg_0]
0x1400020c8  mov     [r14], rcx
0x1400020cb  jmp     loc_140001FE2
0x140008e20  test    bl, bl
0x140008e22  jz      short loc_140008E36
0x140008e24  call    cs:__imp_GetLastError
0x140008e2b  nop     dword ptr [rax+rax+00h]
0x140008e30  nop
0x140008e31  jmp     loc_140002007
0x140008e36  mov     ecx, r13d; Status
0x140008e39  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x140008e40  nop     dword ptr [rax+rax+00h]
0x140008e45  nop
0x140008e46  jmp     loc_140002007
```

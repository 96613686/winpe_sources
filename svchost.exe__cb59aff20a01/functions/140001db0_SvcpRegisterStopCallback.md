# SvcpRegisterStopCallback

- ea: `0x140001db0`
- end: `0x140001fd5`
- name: `SvcpRegisterStopCallback`
- size: `549`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140001d50`
- `0x140001d80`

## callees

- `0x140001db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001fca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140001e9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140001e9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001f66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001f66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140001e77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140001e77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140001f10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140001f1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140001f54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140001f10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140001f1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140001f54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140001e4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140001e4e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x140001ef0`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x140001ef0`
- `ntdll!TpAllocWait` at `0x140001f93`
- `ntdll!TpAllocWait` at `0x140001f93`
- `ntdll!TpSetWait` at `0x140001faf`
- `ntdll!TpSetWait` at `0x140001faf`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000879d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000879d`

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
0x140001db0  push    rbx
0x140001db2  push    rsi
0x140001db3  push    rdi
0x140001db4  push    r14
0x140001db6  sub     rsp, 38h
0x140001dba  mov     [rsp+58h+arg_0], 0
0x140001dc3  mov     rdi, r9
0x140001dc6  mov     rsi, r8
0x140001dc9  mov     rbx, rdx
0x140001dcc  mov     r14, rcx
0x140001dcf  test    rcx, rcx
0x140001dd2  jz      loc_140001F39
0x140001dd8  test    rdx, rdx
0x140001ddb  jz      loc_140001F39
0x140001de1  test    r8, r8
0x140001de4  jz      loc_140001F39
0x140001dea  test    r9, r9
0x140001ded  jz      loc_140001F39
0x140001df3  mov     [rsp+58h+arg_8], rbp
0x140001df8  xor     ebp, ebp
0x140001dfa  mov     [rsp+58h+var_28], r15
0x140001dff  cmp     ebp, cs:ServiceCount
0x140001e05  jb      short loc_140001E20
0x140001e07  mov     eax, 0Dh
0x140001e0c  mov     r15, [rsp+58h+var_28]
0x140001e11  mov     rbp, [rsp+58h+arg_8]
0x140001e16  add     rsp, 38h
0x140001e1a  pop     r14
0x140001e1c  pop     rdi
0x140001e1d  pop     rsi
0x140001e1e  pop     rbx
0x140001e1f  retn
0x140001e20  mov     r8, cs:ServiceArray
0x140001e27  lea     r15, ds:0[rbp*2]
0x140001e2f  mov     r9d, 0FFFFFFFFh; cchCount2
0x140001e35  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x140001e3d  add     r15, rbp
0x140001e40  mov     edx, r9d; cchCount1
0x140001e43  shl     r15, 5
0x140001e47  mov     rcx, rbx; lpString1
0x140001e4a  mov     r8, [r15+r8]; lpString2
0x140001e4e  call    cs:__imp_CompareStringOrdinal
0x140001e54  cmp     eax, 2
0x140001e57  jnz     loc_140001F7D
0x140001e5d  mov     rbp, cs:ServiceArray
0x140001e64  add     rbp, r15
0x140001e67  jz      short loc_140001E07
0x140001e69  mov     [rsp+58h+arg_10], r12
0x140001e6e  lea     rcx, [rbp+20h]; SRWLock
0x140001e72  mov     [rsp+58h+arg_18], r13
0x140001e77  call    cs:__imp_AcquireSRWLockExclusive
0x140001e7d  cmp     qword ptr [rbp+18h], 0
0x140001e82  jnz     loc_140001F48
0x140001e88  mov     rcx, cs:g_hHeap; hHeap
0x140001e8f  mov     ebx, 8
0x140001e94  mov     edx, ebx; dwFlags
0x140001e96  mov     r8d, 10h; dwBytes
0x140001e9c  call    cs:__imp_HeapAlloc
0x140001ea2  mov     r12, rax
0x140001ea5  test    rax, rax
0x140001ea8  jz      loc_140001F50
0x140001eae  movzx   ebx, [rsp+58h+arg_30]
0x140001eb6  mov     r8, r12
0x140001eb9  mov     rax, [rsp+58h+arg_20]
0x140001ec1  mov     [r12], rax
0x140001ec5  mov     [r12+8], rbp
0x140001eca  test    bl, bl
0x140001ecc  jz      loc_140001F84
0x140001ed2  mov     eax, [rsp+58h+arg_28]
0x140001ed9  lea     rdx, SvchostStopCallback
0x140001ee0  xor     r13d, r13d
0x140001ee3  mov     [rsp+58h+bIgnoreCase], eax
0x140001ee7  mov     r9d, 0FFFFFFFFh
0x140001eed  mov     rcx, rsi
0x140001ef0  call    cs:__imp_RegisterWaitForSingleObjectEx
0x140001ef6  mov     [r14], rax
0x140001ef9  cmp     qword ptr [r14], 0
0x140001efd  jz      loc_140001FC2
0x140001f03  inc     dword ptr [rbp+30h]
0x140001f06  lea     rcx, [rbp+20h]; SRWLock
0x140001f0a  xor     ebx, ebx
0x140001f0c  mov     [rbp+18h], rdi
0x140001f10  call    cs:__imp_ReleaseSRWLockExclusive
0x140001f16  jmp     short loc_140001F28
0x140001f18  mov     ebx, eax
0x140001f1a  lea     rcx, [rbp+20h]; SRWLock
0x140001f1e  call    cs:__imp_ReleaseSRWLockExclusive
0x140001f24  test    ebx, ebx
0x140001f26  jnz     short loc_140001F5A
0x140001f28  mov     r13, [rsp+58h+arg_18]
0x140001f2d  mov     eax, ebx
0x140001f2f  mov     r12, [rsp+58h+arg_10]
0x140001f34  jmp     loc_140001E0C
0x140001f39  mov     eax, 57h ; 'W'
0x140001f3e  add     rsp, 38h
0x140001f42  pop     r14
0x140001f44  pop     rdi
0x140001f45  pop     rsi
0x140001f46  pop     rbx
0x140001f47  retn
0x140001f48  xor     r12d, r12d
0x140001f4b  mov     ebx, 0Dh
0x140001f50  lea     rcx, [rbp+20h]; SRWLock
0x140001f54  call    cs:__imp_ReleaseSRWLockExclusive
0x140001f5a  mov     rcx, cs:g_hHeap; hHeap
0x140001f61  mov     r8, r12; lpMem
0x140001f64  xor     edx, edx; dwFlags
0x140001f66  call    cs:__imp_HeapFree
0x140001f6c  mov     r13, [rsp+58h+arg_18]
0x140001f71  mov     eax, ebx
0x140001f73  mov     r12, [rsp+58h+arg_10]
0x140001f78  jmp     loc_140001E0C
0x140001f7d  inc     ebp
0x140001f7f  jmp     loc_140001DFF
0x140001f84  xor     r9d, r9d
0x140001f87  lea     rdx, SvchostTpStopCallback
0x140001f8e  lea     rcx, [rsp+58h+arg_0]
0x140001f93  call    cs:__imp_TpAllocWait
0x140001f99  mov     r13d, eax
0x140001f9c  test    eax, eax
0x140001f9e  js      loc_140001EF9
0x140001fa4  mov     rcx, [rsp+58h+arg_0]
0x140001fa9  xor     r8d, r8d
0x140001fac  mov     rdx, rsi
0x140001faf  call    cs:__imp_TpSetWait
0x140001fb5  mov     rcx, [rsp+58h+arg_0]
0x140001fba  mov     [r14], rcx
0x140001fbd  jmp     loc_140001EF9
0x140001fc2  test    bl, bl
0x140001fc4  jz      loc_14000879A
0x140001fca  call    cs:__imp_GetLastError
0x140001fd0  jmp     loc_140001F18
0x14000879a  mov     ecx, r13d; Status
0x14000879d  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400087a3  nop
0x1400087a4  jmp     loc_140001F18
```

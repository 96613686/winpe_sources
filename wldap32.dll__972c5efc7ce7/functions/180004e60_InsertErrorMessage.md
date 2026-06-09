# InsertErrorMessage

- ea: `0x180004e60`
- end: `0x18000512e`
- name: `InsertErrorMessage`
- size: `718`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000bf40`
- `0x180012ab0`
- `0x1800164a0`

## callees

- `0x1800037a8`
- `0x180004e60`
- `0x180005134`
- `0x180006510`
- `0x18001e2c0`
- `0x180029560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004eb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004eb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ee2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ee2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e70`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004e85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004e85`

## string_xrefs

- `0x1800050b9`: `InsertErrorMessage AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n`
- `0x180005075`: `InsertErrorMessage could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n`
- `0x18000502d`: `InsertErrorMessage no per-thread entry, connection 0x%x, thread 0x%x.\n`

## pseudocode

```c
void __fastcall InsertErrorMessage(__int64 a1, __int64 a2)
{
  DWORD CurrentThreadId; // r14d
  _QWORD *Value; // rax
  __int64 CurrentPerThreadEntry; // rbx
  _QWORD *v7; // rdi
  _QWORD *v8; // rbx
  _DWORD *v9; // rax
  int v10; // ecx
  _DWORD *v11; // rbx
  unsigned int v12; // eax
  CHAR *v13; // rcx

  CurrentThreadId = GetCurrentThreadId();
  Value = TlsGetValue(GlobalTlsLastErrorIndex);
  if ( Value )
  {
    CurrentPerThreadEntry = Value[1];
    if ( CurrentPerThreadEntry )
      goto LABEL_3;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
    LDAPClientPrint(
      0x400000,
      "InsertErrorMessage could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n",
      a1,
      CurrentThreadId);
  if ( !(unsigned int)AddPerThreadEntry(CurrentThreadId) )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(
        0x400000,
        "InsertErrorMessage AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n",
        a1,
        CurrentThreadId);
    SetConnectionError(a1, 90);
    return;
  }
  CurrentPerThreadEntry = GetCurrentPerThreadEntry();
  if ( CurrentPerThreadEntry )
  {
LABEL_3:
    EnterCriticalSection(&PerThreadListLock);
    v7 = (_QWORD *)(CurrentPerThreadEntry + 24);
    v8 = *(_QWORD **)(CurrentPerThreadEntry + 24);
    if ( v8 )
    {
      while ( v8[1] != a1 )
      {
        v7 = v8;
        v8 = (_QWORD *)*v8;
        if ( !v8 )
          goto LABEL_4;
      }
      v13 = (CHAR *)v8[3];
      if ( v13 )
        ldap_memfree(v13);
      v8[3] = a2;
    }
    else
    {
LABEL_4:
      v9 = HeapAlloc(LdapHeap, 8u, 0x28u);
      v10 = g_fTracingOn;
      v11 = v9;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      {
        LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 40, (_DWORD)v9, 1920091468);
        v10 = g_fTracingOn;
      }
      v12 = LdapAllocatedHeap;
      if ( v11 )
      {
        *v11 = 1920091468;
        v11[1] = 32;
        v11 += 2;
        v12 += 32;
        LdapAllocatedHeap = v12;
      }
      if ( v10 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
          32,
          (_DWORD)v11,
          1920091468,
          v12);
      if ( !v11 )
      {
        LeaveCriticalSection(&PerThreadListLock);
        SetConnectionError(a1, 90);
        return;
      }
      *((_QWORD *)v11 + 1) = a1;
      v11[4] = CurrentThreadId;
      *((_QWORD *)v11 + 3) = a2;
      *(_QWORD *)v11 = 0;
      *v7 = v11;
    }
    LeaveCriticalSection(&PerThreadListLock);
  }
  else
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(
        0x400000,
        "InsertErrorMessage no per-thread entry, connection 0x%x, thread 0x%x.\n",
        a1,
        CurrentThreadId);
    SetConnectionError(a1, 82);
  }
}

```

## disassembly

```asm
0x180004e60  push    rbx
0x180004e62  push    rbp
0x180004e63  push    rsi
0x180004e64  push    r14
0x180004e66  sub     rsp, 38h
0x180004e6a  mov     rsi, rdx
0x180004e6d  mov     rbp, rcx
0x180004e70  call    cs:__imp_GetCurrentThreadId
0x180004e77  nop     dword ptr [rax+rax+00h]
0x180004e7c  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x180004e82  mov     r14d, eax
0x180004e85  call    cs:__imp_TlsGetValue
0x180004e8c  nop     dword ptr [rax+rax+00h]
0x180004e91  test    rax, rax
0x180004e94  jz      loc_180005053
0x180004e9a  mov     rbx, [rax+8]
0x180004e9e  test    rbx, rbx
0x180004ea1  jz      loc_180005053
0x180004ea7  lea     rcx, PerThreadListLock; lpCriticalSection
0x180004eae  mov     [rsp+58h+arg_0], rdi
0x180004eb3  call    cs:__imp_EnterCriticalSection
0x180004eba  nop     dword ptr [rax+rax+00h]
0x180004ebf  lea     rdi, [rbx+18h]
0x180004ec3  mov     rbx, [rbx+18h]
0x180004ec7  test    rbx, rbx
0x180004eca  jnz     loc_180004F53
0x180004ed0  mov     rcx, cs:LdapHeap; hHeap
0x180004ed7  mov     edx, 8; dwFlags
0x180004edc  mov     r8d, 28h ; '('; dwBytes
0x180004ee2  call    cs:__imp_HeapAlloc
0x180004ee9  nop     dword ptr [rax+rax+00h]
0x180004eee  mov     ecx, cs:g_fTracingOn
0x180004ef4  mov     rbx, rax
0x180004ef7  test    ecx, ecx
0x180004ef9  jnz     loc_180004FB5
0x180004eff  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180004f05  test    rbx, rbx
0x180004f08  jz      short loc_180004F24
0x180004f0a  mov     dword ptr [rbx], 7272454Ch
0x180004f10  mov     dword ptr [rbx+4], 20h ; ' '
0x180004f17  add     rbx, 8
0x180004f1b  add     eax, 20h ; ' '
0x180004f1e  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180004f24  test    ecx, ecx
0x180004f26  jnz     loc_1800050E9
0x180004f2c  test    rbx, rbx
0x180004f2f  jnz     short loc_180004F9D
0x180004f31  lea     rcx, PerThreadListLock; lpCriticalSection
0x180004f38  call    cs:__imp_LeaveCriticalSection
0x180004f3f  nop     dword ptr [rax+rax+00h]
0x180004f44  mov     edx, 5Ah ; 'Z'
0x180004f49  mov     rcx, rbp
0x180004f4c  call    SetConnectionError
0x180004f51  jmp     short loc_180004F8D
0x180004f53  cmp     [rbx+8], rbp
0x180004f57  jz      short loc_180004F69
0x180004f59  mov     rdi, rbx
0x180004f5c  mov     rbx, [rbx]
0x180004f5f  test    rbx, rbx
0x180004f62  jnz     short loc_180004F53
0x180004f64  jmp     loc_180004ED0
0x180004f69  mov     rcx, [rbx+18h]; Block
0x180004f6d  test    rcx, rcx
0x180004f70  jnz     loc_1800050DF
0x180004f76  mov     [rbx+18h], rsi
0x180004f7a  lea     rcx, PerThreadListLock; lpCriticalSection
0x180004f81  call    cs:__imp_LeaveCriticalSection
0x180004f88  nop     dword ptr [rax+rax+00h]
0x180004f8d  mov     rdi, [rsp+58h+arg_0]
0x180004f92  add     rsp, 38h
0x180004f96  pop     r14
0x180004f98  pop     rsi
0x180004f99  pop     rbp
0x180004f9a  pop     rbx
0x180004f9b  retn
0x180004f9d  mov     [rbx+8], rbp
0x180004fa1  mov     [rbx+10h], r14d
0x180004fa5  mov     [rbx+18h], rsi
0x180004fa9  mov     qword ptr [rbx], 0
0x180004fb0  mov     [rdi], rbx
0x180004fb3  jmp     short loc_180004F7A
0x180004fb5  cmp     cs:g_fProviderEnabled, 0
0x180004fbc  jz      loc_180004EFF
0x180004fc2  test    byte ptr cs:g_ulTraceFlags, 8
0x180004fc9  jz      loc_180004EFF
0x180004fcf  mov     r9, rbx
0x180004fd2  mov     [rsp+58h+var_38], 7272454Ch
0x180004fda  mov     r8d, 28h ; '('
0x180004fe0  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x180004fe7  mov     ecx, 8
0x180004fec  call    LDAPClientPrint
0x180004ff1  mov     ecx, cs:g_fTracingOn
0x180004ff7  jmp     loc_180004EFF
0x180004ffc  call    GetCurrentPerThreadEntry
0x180005001  mov     rbx, rax
0x180005004  test    rax, rax
0x180005007  jnz     loc_180004EA7
0x18000500d  cmp     cs:g_fTracingOn, eax
0x180005013  jz      short loc_180005041
0x180005015  cmp     cs:g_fProviderEnabled, eax
0x18000501b  jz      short loc_180005041
0x18000501d  test    cs:g_ulTraceFlags, 400000h
0x180005028  jz      short loc_180005041
0x18000502a  mov     r9d, r14d
0x18000502d  lea     rdx, aInserterrormes_0; "InsertErrorMessage no per-thread entry,"...
0x180005034  mov     r8, rbp
0x180005037  mov     ecx, 400000h
0x18000503c  call    LDAPClientPrint
0x180005041  mov     edx, 52h ; 'R'
0x180005046  mov     rcx, rbp
0x180005049  call    SetConnectionError
0x18000504e  jmp     loc_180004F92
0x180005053  cmp     cs:g_fTracingOn, 0
0x18000505a  jz      short loc_180005089
0x18000505c  cmp     cs:g_fProviderEnabled, 0
0x180005063  jz      short loc_180005089
0x180005065  test    cs:g_ulTraceFlags, 400000h
0x180005070  jz      short loc_180005089
0x180005072  mov     r9d, r14d
0x180005075  lea     rdx, aInserterrormes_1; "InsertErrorMessage could not find Threa"...
0x18000507c  mov     r8, rbp
0x18000507f  mov     ecx, 400000h
0x180005084  call    LDAPClientPrint
0x180005089  mov     ecx, r14d
0x18000508c  call    AddPerThreadEntry
0x180005091  test    eax, eax
0x180005093  jnz     loc_180004FFC
0x180005099  cmp     cs:g_fTracingOn, eax
0x18000509f  jz      short loc_1800050CD
0x1800050a1  cmp     cs:g_fProviderEnabled, eax
0x1800050a7  jz      short loc_1800050CD
0x1800050a9  test    cs:g_ulTraceFlags, 400000h
0x1800050b4  jz      short loc_1800050CD
0x1800050b6  mov     r9d, r14d
0x1800050b9  lea     rdx, aInserterrormes; "InsertErrorMessage AddPerThreadEntry fa"...
0x1800050c0  mov     r8, rbp
0x1800050c3  mov     ecx, 400000h
0x1800050c8  call    LDAPClientPrint
0x1800050cd  mov     edx, 5Ah ; 'Z'
0x1800050d2  mov     rcx, rbp
0x1800050d5  call    SetConnectionError
0x1800050da  jmp     loc_180004F92
0x1800050df  call    ldap_memfree
0x1800050e4  jmp     loc_180004F76
0x1800050e9  cmp     cs:g_fProviderEnabled, 0
0x1800050f0  jz      loc_180004F2C
0x1800050f6  test    byte ptr cs:g_ulTraceFlags, 8
0x1800050fd  jz      loc_180004F2C
0x180005103  mov     [rsp+58h+var_30], eax
0x180005107  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x18000510e  mov     r9, rbx
0x180005111  mov     [rsp+58h+var_38], 7272454Ch
0x180005119  mov     r8d, 20h ; ' '
0x18000511f  mov     ecx, 8
0x180005124  call    LDAPClientPrint
0x180005129  jmp     loc_180004F2C
```

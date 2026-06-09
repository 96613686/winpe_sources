# ClearPendingListForConnection

- ea: `0x180048450`
- end: `0x18004872c`
- name: `ClearPendingListForConnection`
- size: `732`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009040`
- `0x18003b448`

## callees

- `0x1800037a8`
- `0x180008660`
- `0x180008710`
- `0x18000b440`
- `0x18001ce90`
- `0x1800236f0`
- `0x1800299c0`
- `0x180048450`
- `0x180048734`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800484df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048622`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800484df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048622`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004866d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048686`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004866d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048686`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800485c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800485c2`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180048708`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180048708`
- `ntdll!RtlReleaseResource` at `0x1800486b3`
- `ntdll!RtlReleaseResource` at `0x1800486b3`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048479`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048479`

## string_xrefs

- `0x1800485d1`: `ldapClearPending thread 0x%x has connection 0x%x simulated as down\n`

## pseudocode

```c
void __fastcall ClearPendingListForConnection(__int64 a1)
{
  _QWORD *v2; // rsi
  __int64 *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // r15
  char v7; // bp
  int i; // eax
  unsigned __int16 v9; // ax
  bool v10; // zf
  __int64 v11; // rcx
  unsigned __int16 v12; // r8
  unsigned __int16 j; // dx
  int k; // eax
  unsigned __int16 v15; // ax
  int v16; // ebp
  DWORD CurrentThreadId; // eax
  __int64 v18; // rax
  _QWORD *v19; // rbx

  v2 = 0;
  RtlAcquireResourceExclusive(&RequestListLock, 1u);
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
    LDAPClientPrint(0x1000000, "LdapClearPendingList cleared for connection 0x%x.\n", a1);
  v3 = (__int64 *)GlobalListRequests;
  while ( v3 != &GlobalListRequests )
  {
    v4 = ReferenceLdapRequest(v3);
    v3 = (__int64 *)*v3;
    v5 = v4;
    if ( v4 )
    {
      v6 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
      v7 = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
      if ( a1 == *(_QWORD *)(v5 + 32) )
      {
        for ( i = *(_DWORD *)(v5 + 152); i; --i )
        {
          _InterlockedDecrement(&GlobalCountOfOpenRequests);
          _InterlockedDecrement64(&qword_180066138);
        }
        v9 = *(_WORD *)(v5 + 152);
        v10 = *(_WORD *)(v5 + 182) == v9;
        *(_WORD *)(v5 + 182) -= v9;
        v7 = v10;
        *(_DWORD *)(v5 + 152) = 0;
      }
      v11 = *(_QWORD *)(v5 + 168);
      if ( v11 )
      {
        v12 = *(_WORD *)(v5 + 176);
        for ( j = 0; j < v12; v11 += 64 )
        {
          if ( *(_QWORD *)v11 == a1 )
          {
            for ( k = *(_DWORD *)(v11 + 48); k; --k )
            {
              _InterlockedDecrement(&GlobalCountOfOpenRequests);
              _InterlockedDecrement64(&qword_180066138);
            }
            v15 = *(_WORD *)(v11 + 48);
            v10 = *(_WORD *)(v5 + 182) == v15;
            *(_WORD *)(v5 + 182) -= v15;
            if ( v10 )
              v7 = 1;
            *(_DWORD *)(v11 + 48) = 0;
          }
          ++j;
        }
      }
      if ( v7 )
      {
        v16 = SimulateErrorMessage(a1, v5);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
        {
          CurrentThreadId = GetCurrentThreadId();
          LDAPClientPrint(
            128,
            "ldapClearPending thread 0x%x has connection 0x%x simulated as down\n",
            CurrentThreadId,
            a1);
        }
        if ( v16 )
          *(_BYTE *)(v5 + 184) = 1;
        v18 = ldapMalloc(16, 1682525516);
        if ( v18 )
        {
          *(_QWORD *)v18 = v2;
          v2 = (_QWORD *)v18;
          *(_DWORD *)(v18 + 8) = *(_DWORD *)(v5 + 108);
        }
      }
      LeaveCriticalSection(v6);
      EnterCriticalSection(v6);
      --*(_DWORD *)(v5 + 16);
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
        LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v5, *(_DWORD *)(v5 + 16));
      if ( *(_DWORD *)(v5 + 16) )
      {
        LeaveCriticalSection(v6);
      }
      else
      {
        LeaveCriticalSection(v6);
        DereferenceLdapRequest2(v5, 1);
      }
    }
  }
  *(_DWORD *)(a1 + 472) = 0;
  RtlReleaseResource(&RequestListLock);
  if ( v2 )
  {
    do
    {
      v19 = v2;
      v2 = (_QWORD *)*v2;
      CheckForWaiters(*((unsigned int *)v19 + 2), 0, a1);
      ldapFree(v19, 1682525516);
    }
    while ( v2 );
    if ( GlobalParallelRecvMode )
      PostQueuedCompletionStatus(*(HANDLE *)(a1 + 896), 0, 0xFFFFFFFFFFFFFFFFuLL, 0);
    else
      LdapWakeupSelect();
  }
}

```

## disassembly

```asm
0x180048450  mov     [rsp+arg_8], rbx
0x180048455  mov     [rsp+arg_10], rbp
0x18004845a  push    rsi
0x18004845b  push    rdi
0x18004845c  push    r13
0x18004845e  push    r14
0x180048460  push    r15
0x180048462  sub     rsp, 20h
0x180048466  mov     rdi, rcx
0x180048469  xor     esi, esi
0x18004846b  lea     rcx, RequestListLock; Resource
0x180048472  lea     r13d, [rsi+1]
0x180048476  mov     dl, r13b; Wait
0x180048479  call    cs:__imp_RtlAcquireResourceExclusive
0x180048480  nop     dword ptr [rax+rax+00h]
0x180048485  cmp     cs:g_fTracingOn, esi
0x18004848b  jz      short loc_1800484B2
0x18004848d  cmp     cs:g_fProviderEnabled, esi
0x180048493  jz      short loc_1800484B2
0x180048495  mov     ecx, 1000000h
0x18004849a  test    cs:g_ulTraceFlags, rcx
0x1800484a1  jz      short loc_1800484B2
0x1800484a3  mov     r8, rdi
0x1800484a6  lea     rdx, aLdapclearpendi_0; "LdapClearPendingList cleared for connec"...
0x1800484ad  call    LDAPClientPrint
0x1800484b2  mov     r14, cs:GlobalListRequests
0x1800484b9  jmp     loc_180048692
0x1800484be  mov     rcx, r14
0x1800484c1  call    ReferenceLdapRequest
0x1800484c6  mov     r14, [r14]
0x1800484c9  mov     rbx, rax
0x1800484cc  test    rax, rax
0x1800484cf  jz      loc_180048692
0x1800484d5  lea     r15, [rax+30h]
0x1800484d9  xor     bpl, bpl
0x1800484dc  mov     rcx, r15; lpCriticalSection
0x1800484df  call    cs:__imp_EnterCriticalSection
0x1800484e6  nop     dword ptr [rax+rax+00h]
0x1800484eb  cmp     rdi, [rbx+20h]
0x1800484ef  jnz     short loc_18004852F
0x1800484f1  mov     eax, [rbx+98h]
0x1800484f7  test    eax, eax
0x1800484f9  jz      short loc_18004850F
0x1800484fb  lock dec cs:GlobalCountOfOpenRequests
0x180048502  lock dec cs:qword_180066138
0x18004850a  add     eax, 0FFFFFFFFh
0x18004850d  jnz     short loc_1800484FB
0x18004850f  movzx   eax, word ptr [rbx+98h]
0x180048516  sub     [rbx+0B6h], ax
0x18004851d  movzx   ebp, bpl
0x180048521  cmovz   ebp, r13d
0x180048525  mov     dword ptr [rbx+98h], 0
0x18004852f  mov     rcx, [rbx+0A8h]
0x180048536  test    rcx, rcx
0x180048539  jz      short loc_180048595
0x18004853b  movzx   r8d, word ptr [rbx+0B0h]
0x180048543  xor     edx, edx
0x180048545  xor     eax, eax
0x180048547  cmp     ax, r8w
0x18004854b  jnb     short loc_180048595
0x18004854d  cmp     [rcx], rdi
0x180048550  jnz     short loc_180048587
0x180048552  mov     eax, [rcx+30h]
0x180048555  test    eax, eax
0x180048557  jz      short loc_18004856D
0x180048559  lock dec cs:GlobalCountOfOpenRequests
0x180048560  lock dec cs:qword_180066138
0x180048568  add     eax, 0FFFFFFFFh
0x18004856b  jnz     short loc_180048559
0x18004856d  movzx   eax, word ptr [rcx+30h]
0x180048571  sub     [rbx+0B6h], ax
0x180048578  movzx   ebp, bpl
0x18004857c  cmovz   ebp, r13d
0x180048580  mov     dword ptr [rcx+30h], 0
0x180048587  add     dx, r13w
0x18004858b  add     rcx, 40h ; '@'
0x18004858f  cmp     dx, r8w
0x180048593  jb      short loc_18004854D
0x180048595  test    bpl, bpl
0x180048598  jz      short loc_180048610
0x18004859a  mov     rdx, rbx
0x18004859d  mov     rcx, rdi
0x1800485a0  call    SimulateErrorMessage
0x1800485a5  cmp     cs:g_fTracingOn, 0
0x1800485ac  mov     ebp, eax
0x1800485ae  jz      short loc_1800485E5
0x1800485b0  cmp     cs:g_fProviderEnabled, 0
0x1800485b7  jz      short loc_1800485E5
0x1800485b9  test    byte ptr cs:g_ulTraceFlags, 80h
0x1800485c0  jz      short loc_1800485E5
0x1800485c2  call    cs:__imp_GetCurrentThreadId
0x1800485c9  nop     dword ptr [rax+rax+00h]
0x1800485ce  mov     r9, rdi
0x1800485d1  lea     rdx, aLdapclearpendi; "ldapClearPending thread 0x%x has connec"...
0x1800485d8  mov     r8d, eax
0x1800485db  mov     ecx, 80h
0x1800485e0  call    LDAPClientPrint
0x1800485e5  test    ebp, ebp
0x1800485e7  jz      short loc_1800485F0
0x1800485e9  mov     [rbx+0B8h], r13b
0x1800485f0  mov     edx, 64494D4Ch
0x1800485f5  mov     ecx, 10h
0x1800485fa  call    ldapMalloc
0x1800485ff  test    rax, rax
0x180048602  jz      short loc_180048610
0x180048604  mov     [rax], rsi
0x180048607  mov     rsi, rax
0x18004860a  mov     ecx, [rbx+6Ch]
0x18004860d  mov     [rax+8], ecx
0x180048610  mov     rcx, r15; lpCriticalSection
0x180048613  call    cs:__imp_LeaveCriticalSection
0x18004861a  nop     dword ptr [rax+rax+00h]
0x18004861f  mov     rcx, r15; lpCriticalSection
0x180048622  call    cs:__imp_EnterCriticalSection
0x180048629  nop     dword ptr [rax+rax+00h]
0x18004862e  dec     dword ptr [rbx+10h]
0x180048631  cmp     cs:g_fTracingOn, 0
0x180048638  jz      short loc_180048664
0x18004863a  cmp     cs:g_fProviderEnabled, 0
0x180048641  jz      short loc_180048664
0x180048643  test    byte ptr cs:g_ulTraceFlags, 4
0x18004864a  jz      short loc_180048664
0x18004864c  mov     r9d, [rbx+10h]
0x180048650  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x180048657  mov     r8, rbx
0x18004865a  mov     ecx, 4
0x18004865f  call    LDAPClientPrint
0x180048664  cmp     dword ptr [rbx+10h], 0
0x180048668  mov     rcx, r15; lpCriticalSection
0x18004866b  jnz     short loc_180048686
0x18004866d  call    cs:__imp_LeaveCriticalSection
0x180048674  nop     dword ptr [rax+rax+00h]
0x180048679  mov     edx, r13d
0x18004867c  mov     rcx, rbx
0x18004867f  call    DereferenceLdapRequest2
0x180048684  jmp     short loc_180048692
0x180048686  call    cs:__imp_LeaveCriticalSection
0x18004868d  nop     dword ptr [rax+rax+00h]
0x180048692  lea     rax, GlobalListRequests
0x180048699  cmp     r14, rax
0x18004869c  jnz     loc_1800484BE
0x1800486a2  lea     rcx, RequestListLock; Resource
0x1800486a9  mov     dword ptr [rdi+1D8h], 0
0x1800486b3  call    cs:__imp_RtlReleaseResource
0x1800486ba  nop     dword ptr [rax+rax+00h]
0x1800486bf  test    rsi, rsi
0x1800486c2  jz      short loc_180048714
0x1800486c4  mov     rbx, rsi
0x1800486c7  mov     r8, rdi
0x1800486ca  mov     rsi, [rsi]
0x1800486cd  xor     edx, edx
0x1800486cf  mov     ecx, [rbx+8]
0x1800486d2  call    CheckForWaiters
0x1800486d7  mov     edx, 64494D4Ch
0x1800486dc  mov     rcx, rbx
0x1800486df  call    ldapFree
0x1800486e4  test    rsi, rsi
0x1800486e7  jnz     short loc_1800486C4
0x1800486e9  cmp     cs:GlobalParallelRecvMode, esi
0x1800486ef  jnz     short loc_1800486F8
0x1800486f1  call    LdapWakeupSelect
0x1800486f6  jmp     short loc_180048714
0x1800486f8  mov     rcx, [rdi+380h]; CompletionPort
0x1800486ff  xor     r9d, r9d; lpOverlapped
0x180048702  or      r8, 0FFFFFFFFFFFFFFFFh; dwCompletionKey
0x180048706  xor     edx, edx; dwNumberOfBytesTransferred
0x180048708  call    cs:__imp_PostQueuedCompletionStatus
0x18004870f  nop     dword ptr [rax+rax+00h]
0x180048714  mov     rbx, [rsp+48h+arg_8]
0x180048719  mov     rbp, [rsp+48h+arg_10]
0x18004871e  add     rsp, 20h
0x180048722  pop     r15
0x180048724  pop     r14
0x180048726  pop     r13
0x180048728  pop     rdi
0x180048729  pop     rsi
0x18004872a  retn
```

# WaCreateStaticDnsCacheEntry

- ea: `0x18005f910`
- end: `0x18005fb56`
- name: `WaCreateStaticDnsCacheEntry`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005f6e8`

## callees

- `0x1800052bc`
- `0x180022540`
- `0x18005f910`
- `0x18005fb5c`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005f958`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005f958`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f9f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f9f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005fa7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005fa7c`
- `ntdll!RtlDowncaseUnicodeChar` at `0x18005fab5`
- `ntdll!RtlDowncaseUnicodeChar` at `0x18005fab5`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005fa3b`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005fa3b`

## pseudocode

```c
__int64 __fastcall WaCreateStaticDnsCacheEntry(__int64 a1, WCHAR *a2, char *a3, int a4)
{
  int v8; // edx
  unsigned int DnsQueryResultFromAddrInfo; // eax
  __int64 v10; // r15
  unsigned int StaticDnsCacheEntry; // ebx
  int v12; // esi
  char *v13; // rbx
  WCHAR *i; // rdi
  WCHAR v15; // ax
  RTL_SRWLOCK *v16; // rbp
  RTL_SRWLOCK *j; // rdi
  RTL_SRWLOCK *v18; // rbx
  char *Ptr; // rdx
  RTL_SRWLOCK *v21; // rax
  RTL_SRWLOCK **v22; // rcx
  int v23; // [rsp+20h] [rbp-88h]
  __int64 v24; // [rsp+40h] [rbp-68h] BYREF
  __int64 v25; // [rsp+48h] [rbp-60h]
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-58h] BYREF

  v25 = a1;
  v24 = 0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  LOBYTE(v8) = 1;
  DnsQueryResultFromAddrInfo = WapCreateDnsQueryResultFromAddrInfo(
                                 a4,
                                 v8,
                                 0,
                                 0,
                                 PerformanceCount.QuadPart,
                                 0,
                                 (__int64)&v24);
  v10 = v24;
  StaticDnsCacheEntry = DnsQueryResultFromAddrInfo;
  if ( !DnsQueryResultFromAddrInfo )
  {
    v12 = 0;
    v13 = a3;
    for ( i = a2; v13; v12 = v15 + 127 * v12 )
    {
      --v13;
      if ( *i >= 0x80u )
        v15 = RtlDowncaseUnicodeChar(*i);
      else
        v15 = *((unsigned __int8 *)WaToLowerTable + *(unsigned __int8 *)i);
      ++i;
    }
    v16 = (RTL_SRWLOCK *)(a1 + 24LL * (v12 & 0x7F) + 8);
    AcquireSRWLockExclusive(v16);
    for ( j = (RTL_SRWLOCK *)v16[1].Ptr; ; j = (RTL_SRWLOCK *)j->Ptr )
    {
      if ( j == &v16[1] )
        goto LABEL_15;
      v18 = j - 3;
      if ( HIDWORD(j[-3].Ptr) == v12 )
      {
        Ptr = (char *)v18[6].Ptr;
        if ( Ptr == a3
          && (LOBYTE(v18[14].Ptr)
           || !BYTE2(v18[14].Ptr)
           && !BYTE3(v18[14].Ptr)
           && !LODWORD(v18[13].Ptr)
           && (!WaKirDnsResolution || !HIDWORD(v18[14].Ptr))) )
        {
          LOBYTE(v23) = 1;
          if ( !(unsigned int)RtlCompareUnicodeStrings(v18[5].Ptr, Ptr, a2, a3, v23) )
            break;
        }
      }
    }
    if ( v18[9].Ptr && !LOBYTE(v18[14].Ptr) && HIDWORD(v18[13].Ptr) != WaNetworkChangeGenerationId )
    {
      v21 = (RTL_SRWLOCK *)j->Ptr;
      if ( *((RTL_SRWLOCK **)j->Ptr + 1) != j || (v22 = (RTL_SRWLOCK **)j[1].Ptr, *v22 != j) )
        __fastfail(3u);
      *v22 = v21;
      v21[1].Ptr = v22;
      j[1].Ptr = j;
      j->Ptr = j;
      goto LABEL_15;
    }
    if ( j == (RTL_SRWLOCK *)24 )
    {
LABEL_15:
      StaticDnsCacheEntry = WapCreateStaticDnsCacheEntry(v25, (_DWORD)v16, (_DWORD)a2, (_DWORD)a3, v12, v10);
      goto LABEL_16;
    }
    StaticDnsCacheEntry = 183;
LABEL_16:
    ReleaseSRWLockExclusive(v16);
  }
  if ( v10 )
    WaDereferenceDnsQueryResult(v10);
  return StaticDnsCacheEntry;
}

```

## disassembly

```asm
0x18005f910  push    rbx
0x18005f912  push    rbp
0x18005f913  push    rsi
0x18005f914  push    rdi
0x18005f915  push    r12
0x18005f917  push    r13
0x18005f919  push    r14
0x18005f91b  push    r15
0x18005f91d  sub     rsp, 68h
0x18005f921  mov     rax, cs:__security_cookie
0x18005f928  xor     rax, rsp
0x18005f92b  mov     [rsp+0A8h+var_50], rax
0x18005f930  mov     rbp, rcx
0x18005f933  mov     [rsp+0A8h+var_60], rcx
0x18005f938  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x18005f93d  mov     [rsp+0A8h+var_68], 0
0x18005f946  mov     rbx, r9
0x18005f949  mov     qword ptr [rsp+0A8h+PerformanceCount], 0
0x18005f952  mov     r14, r8
0x18005f955  mov     r13, rdx
0x18005f958  call    cs:__imp_QueryPerformanceCounter
0x18005f95f  nop     dword ptr [rax+rax+00h]
0x18005f964  lea     rax, [rsp+0A8h+var_68]
0x18005f969  xor     r9d, r9d
0x18005f96c  mov     [rsp+0A8h+var_78], rax
0x18005f971  xor     r8d, r8d
0x18005f974  mov     rax, qword ptr [rsp+0A8h+PerformanceCount]
0x18005f979  mov     dl, 1
0x18005f97b  mov     dword ptr [rsp+0A8h+var_80], 0
0x18005f983  mov     rcx, rbx
0x18005f986  mov     [rsp+0A8h+var_88], rax
0x18005f98b  call    WapCreateDnsQueryResultFromAddrInfo
0x18005f990  mov     r15, [rsp+0A8h+var_68]
0x18005f995  mov     ebx, eax
0x18005f997  test    eax, eax
0x18005f999  jnz     loc_18005FA88
0x18005f99f  xor     esi, esi
0x18005f9a1  mov     rbx, r14
0x18005f9a4  mov     rdi, r13
0x18005f9a7  test    r14, r14
0x18005f9aa  jz      short loc_18005F9DC
0x18005f9ac  dec     rbx
0x18005f9af  mov     eax, 80h
0x18005f9b4  cmp     [rdi], ax
0x18005f9b7  jnb     loc_18005FAB2
0x18005f9bd  movzx   eax, byte ptr [rdi]
0x18005f9c0  lea     rcx, WaToLowerTable
0x18005f9c7  movzx   eax, byte ptr [rax+rcx]
0x18005f9cb  imul    esi, 7Fh
0x18005f9ce  add     rdi, 2
0x18005f9d2  movzx   eax, ax
0x18005f9d5  add     esi, eax
0x18005f9d7  test    rbx, rbx
0x18005f9da  jnz     short loc_18005F9AC
0x18005f9dc  mov     eax, esi
0x18005f9de  and     eax, 7Fh
0x18005f9e1  lea     rax, [rax+rax*2]
0x18005f9e5  lea     rbp, [rbp+rax*8+0]
0x18005f9ea  add     rbp, 8
0x18005f9ee  mov     rcx, rbp; SRWLock
0x18005f9f1  call    cs:__imp_AcquireSRWLockExclusive
0x18005f9f8  nop     dword ptr [rax+rax+00h]
0x18005f9fd  lea     r12, [rbp+8]
0x18005fa01  mov     rdi, [r12]
0x18005fa05  cmp     rdi, r12
0x18005fa08  jz      short loc_18005FA5B
0x18005fa0a  lea     rbx, [rdi-18h]
0x18005fa0e  cmp     [rbx+4], esi
0x18005fa11  jnz     short loc_18005FA1C
0x18005fa13  mov     rdx, [rbx+30h]
0x18005fa17  cmp     rdx, r14
0x18005fa1a  jz      short loc_18005FA21
0x18005fa1c  mov     rdi, [rdi]
0x18005fa1f  jmp     short loc_18005FA05
0x18005fa21  xor     eax, eax
0x18005fa23  cmp     [rbx+70h], al
0x18005fa26  jz      loc_18005FAF9
0x18005fa2c  mov     rcx, [rbx+28h]
0x18005fa30  mov     r9, r14
0x18005fa33  mov     r8, r13
0x18005fa36  mov     byte ptr [rsp+0A8h+var_88], 1
0x18005fa3b  call    cs:__imp_RtlCompareUnicodeStrings
0x18005fa42  nop     dword ptr [rax+rax+00h]
0x18005fa47  test    eax, eax
0x18005fa49  jnz     short loc_18005FA1C
0x18005fa4b  cmp     qword ptr [rbx+48h], 0
0x18005fa50  jnz     loc_18005FB2E
0x18005fa56  test    rbx, rbx
0x18005fa59  jnz     short loc_18005FAC6
0x18005fa5b  mov     rcx, [rsp+0A8h+var_60]
0x18005fa60  mov     r9, r14
0x18005fa63  mov     [rsp+0A8h+var_80], r15
0x18005fa68  mov     r8, r13
0x18005fa6b  mov     rdx, rbp
0x18005fa6e  mov     dword ptr [rsp+0A8h+var_88], esi
0x18005fa72  call    WapCreateStaticDnsCacheEntry
0x18005fa77  mov     ebx, eax
0x18005fa79  mov     rcx, rbp; SRWLock
0x18005fa7c  call    cs:__imp_ReleaseSRWLockExclusive
0x18005fa83  nop     dword ptr [rax+rax+00h]
0x18005fa88  test    r15, r15
0x18005fa8b  jnz     loc_18005FB49
0x18005fa91  mov     eax, ebx
0x18005fa93  mov     rcx, [rsp+0A8h+var_50]
0x18005fa98  xor     rcx, rsp; StackCookie
0x18005fa9b  call    __security_check_cookie
0x18005faa0  add     rsp, 68h
0x18005faa4  pop     r15
0x18005faa6  pop     r14
0x18005faa8  pop     r13
0x18005faaa  pop     r12
0x18005faac  pop     rdi
0x18005faad  pop     rsi
0x18005faae  pop     rbp
0x18005faaf  pop     rbx
0x18005fab0  retn
0x18005fab2  movzx   ecx, word ptr [rdi]; Source
0x18005fab5  call    cs:__imp_RtlDowncaseUnicodeChar
0x18005fabc  nop     dword ptr [rax+rax+00h]
0x18005fac1  jmp     loc_18005F9CB
0x18005fac6  mov     ebx, 0B7h
0x18005facb  jmp     short loc_18005FA79
0x18005facd  mov     rax, [rdi]
0x18005fad0  cmp     [rax+8], rdi
0x18005fad4  jnz     short loc_18005FAF2
0x18005fad6  mov     rcx, [rdi+8]
0x18005fada  cmp     [rcx], rdi
0x18005fadd  jnz     short loc_18005FAF2
0x18005fadf  mov     [rcx], rax
0x18005fae2  mov     [rax+8], rcx
0x18005fae6  mov     [rdi+8], rdi
0x18005faea  mov     [rdi], rdi
0x18005faed  jmp     loc_18005FA5B
0x18005faf2  mov     ecx, 3
0x18005faf7  int     29h; Win8: RtlFailFast(ecx)
0x18005faf9  cmp     [rbx+72h], al
0x18005fafc  jnz     loc_18005FA1C
0x18005fb02  cmp     [rbx+73h], al
0x18005fb05  jnz     loc_18005FA1C
0x18005fb0b  cmp     [rbx+68h], eax
0x18005fb0e  jnz     loc_18005FA1C
0x18005fb14  cmp     cs:WaKirDnsResolution, al
0x18005fb1a  jz      loc_18005FA2C
0x18005fb20  cmp     [rbx+74h], eax
0x18005fb23  jnz     loc_18005FA1C
0x18005fb29  jmp     loc_18005FA2C
0x18005fb2e  cmp     byte ptr [rbx+70h], 0
0x18005fb32  jnz     loc_18005FA56
0x18005fb38  mov     eax, cs:WaNetworkChangeGenerationId
0x18005fb3e  cmp     [rbx+6Ch], eax
0x18005fb41  jz      loc_18005FA56
0x18005fb47  jmp     short loc_18005FACD
0x18005fb49  mov     rcx, r15
0x18005fb4c  call    WaDereferenceDnsQueryResult
0x18005fb51  jmp     loc_18005FA91
```

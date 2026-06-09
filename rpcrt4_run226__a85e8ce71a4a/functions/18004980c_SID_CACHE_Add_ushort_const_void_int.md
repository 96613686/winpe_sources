# SID_CACHE::Add(ushort const *,void *,int)

- ea: `0x18004980c`
- end: `0x180049a09`
- name: `?Add@SID_CACHE@@QEAAJPEBGPEAXH@Z`
- size: `509`
- prototype: `int(SID_CACHE *__hidden this, const unsigned __int16 *, void *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e0f0`
- `0x1800306c8`
- `0x18004962c`

## callees

- `0x180022870`
- `0x18002d420`
- `0x18002f460`
- `0x18004980c`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1800498f2`
- `ntdll!NtQuerySystemTime` at `0x18004999d`
- `ntdll!NtQuerySystemTime` at `0x1800498f2`
- `ntdll!NtQuerySystemTime` at `0x18004999d`
- `ntdll!_wcsicmp` at `0x180049950`
- `ntdll!_wcsicmp` at `0x180049950`
- `ntdll!RtlLeaveCriticalSection` at `0x18004992e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800499f9`
- `ntdll!RtlLeaveCriticalSection` at `0x18004992e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800499f9`
- `ntdll!RtlEnterCriticalSection` at `0x180049845`
- `ntdll!RtlEnterCriticalSection` at `0x180049845`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180049966`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180049966`

## pseudocode

```c
__int64 __fastcall SID_CACHE::Add(SID_CACHE *this, const unsigned __int16 *a2, void *a3, int a4)
{
  __int64 v4; // rdi
  unsigned int v7; // r15d
  __int64 v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // r12
  __int64 i; // rbp
  const wchar_t *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // r15
  unsigned __int16 *v15; // rax
  void *v16; // rax
  unsigned int v17; // ebx
  union _LARGE_INTEGER *v19; // rbx
  void *v20; // rax

  v4 = *(_QWORD *)&SIDCache.Revision;
  v7 = 0;
  v8 = *(_QWORD *)(*(_QWORD *)&SIDCache.Revision + 16LL);
  v9 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)&SIDCache.Revision + 96LL);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)&SIDCache.Revision + 96LL));
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
    {
      v12 = v7;
      v13 = 3LL * v7;
      v14 = v4 + 24LL * v7;
      if ( *(_QWORD *)(v14 + 16) )
      {
        FreeWrapper(*(void **)(v4 + 8 * v13));
        FreeWrapper(*(void **)(v14 + 8));
        *(_QWORD *)(v4 + 8 * v13) = 0;
        *(_QWORD *)(v14 + 8) = 0;
        *(_QWORD *)(v14 + 16) = 0;
      }
      v15 = DuplicateString(a2);
      *(_QWORD *)(v4 + 8 * v13) = v15;
      if ( !v15 )
        goto LABEL_26;
      v16 = DuplicateSID(a3);
      *(_QWORD *)(v14 + 8) = v16;
      if ( !v16 )
      {
        FreeWrapper(*(void **)(v4 + 8 * v13));
        *(_QWORD *)(v4 + 8 * v13) = 0;
        v17 = 14;
        goto LABEL_16;
      }
      if ( a4 )
      {
        *(_QWORD *)(v14 + 16) = 1;
      }
      else if ( NtQuerySystemTime((PLARGE_INTEGER)(v14 + 16)) )
      {
        FreeWrapper(*(void **)(v4 + 24 * v12));
        *(_QWORD *)(v4 + 24 * v12) = 0;
        FreeWrapper(0);
        *(_QWORD *)(v4 + 24 * v12) = 0;
        *(_QWORD *)(v4 + 24 * v12 + 16) = 0;
      }
LABEL_15:
      v17 = 0;
LABEL_16:
      RtlLeaveCriticalSection(v9);
      return v17;
    }
    v11 = *(const wchar_t **)(v4 + 24 * i);
    if ( v11 )
    {
      if ( !_wcsicmp(a2, v11) )
        break;
    }
    if ( v8 > *(_QWORD *)(v4 + 24 * i + 16) )
    {
      v8 = *(_QWORD *)(v4 + 24 * i + 16);
      v7 = i;
    }
  }
  if ( EqualSid(a3, *(PSID *)(v4 + 24 * i + 8))
    || (FreeWrapper(*(void **)(v4 + 24 * i + 8)), v20 = DuplicateSID(a3), (*(_QWORD *)(v4 + 24 * i + 8) = v20) != 0) )
  {
    v19 = (union _LARGE_INTEGER *)(v4 + 24 * i);
    if ( a4 )
    {
      v19[2].QuadPart = 1;
    }
    else if ( NtQuerySystemTime(v19 + 2) )
    {
      FreeWrapper(*(void **)(v4 + 24 * i));
      *(_QWORD *)(v4 + 24 * i) = 0;
      FreeWrapper(0);
      *(_QWORD *)(v4 + 24 * i) = 0;
      v19[2].QuadPart = 0;
    }
    goto LABEL_15;
  }
  FreeWrapper(*(void **)(v4 + 24 * i));
  *(_QWORD *)(v4 + 24 * i) = 0;
  *(_QWORD *)(v4 + 24 * i + 16) = 0;
LABEL_26:
  RtlLeaveCriticalSection(v9);
  return 14;
}

```

## disassembly

```asm
0x18004980c  mov     [rsp+arg_0], rbx
0x180049811  mov     [rsp+arg_18], r9d
0x180049816  mov     [rsp+String1], rdx
0x18004981b  push    rbp
0x18004981c  push    rsi
0x18004981d  push    rdi
0x18004981e  push    r12
0x180049820  push    r13
0x180049822  push    r14
0x180049824  push    r15
0x180049826  sub     rsp, 20h
0x18004982a  mov     rdi, qword ptr cs:?SIDCache@@3PEAVSID_CACHE@@EA.Revision; SID_CACHE * SIDCache ...
0x180049831  mov     r14d, r9d
0x180049834  mov     r13, r8
0x180049837  xor     r15d, r15d
0x18004983a  mov     rbx, [rdi+10h]
0x18004983e  lea     r12, [rdi+60h]
0x180049842  mov     rcx, r12; CriticalSection
0x180049845  call    cs:__imp_RtlEnterCriticalSection
0x18004984b  xor     ebp, ebp
0x18004984d  cmp     ebp, 4
0x180049850  jnb     short loc_18004987D
0x180049852  lea     rsi, ds:0[rbp*2]
0x18004985a  add     rsi, rbp
0x18004985d  mov     rdx, [rdi+rsi*8]; String2
0x180049861  test    rdx, rdx
0x180049864  jnz     loc_18004994B
0x18004986a  cmp     rbx, [rdi+rsi*8+10h]
0x18004986f  jle     short loc_180049879
0x180049871  mov     rbx, [rdi+rsi*8+10h]
0x180049876  mov     r15d, ebp
0x180049879  inc     ebp
0x18004987b  jmp     short loc_18004984D
0x18004987d  mov     ebx, r15d
0x180049880  xor     ebp, ebp
0x180049882  lea     rsi, [rbx+rbx*2]
0x180049886  lea     r14, [rdi+rsi*8]
0x18004988a  lea     r15, [rdi+rsi*8]
0x18004988e  cmp     [r14+10h], rbp
0x180049892  jz      short loc_1800498B2
0x180049894  mov     rcx, [rdi+rsi*8]; lpMem
0x180049898  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004989d  mov     rcx, [r15+8]; lpMem
0x1800498a1  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800498a6  mov     [rdi+rsi*8], rbp
0x1800498aa  mov     [r15+8], rbp
0x1800498ae  mov     [r14+10h], rbp
0x1800498b2  mov     rcx, [rsp+58h+String1]; Src
0x1800498b7  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x1800498bc  mov     [rdi+rsi*8], rax
0x1800498c0  test    rax, rax
0x1800498c3  jz      loc_1800499F6
0x1800498c9  mov     rcx, r13; pSourceSid
0x1800498cc  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x1800498d1  mov     [r15+8], rax
0x1800498d5  test    rax, rax
0x1800498d8  jz      loc_180049985
0x1800498de  cmp     [rsp+58h+arg_18], ebp
0x1800498e2  jz      short loc_1800498EE
0x1800498e4  mov     qword ptr [r14+10h], 1
0x1800498ec  jmp     short loc_180049929
0x1800498ee  lea     rcx, [r14+10h]; SystemTime
0x1800498f2  call    cs:__imp_NtQuerySystemTime
0x1800498f8  test    eax, eax
0x1800498fa  jz      short loc_180049929
0x1800498fc  lea     rcx, [rbx+rbx*2]
0x180049900  mov     rcx, [rdi+rcx*8]; lpMem
0x180049904  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180049909  lea     rax, [rbx+rbx*2]
0x18004990d  xor     ecx, ecx; lpMem
0x18004990f  mov     [rdi+rax*8], rbp
0x180049913  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180049918  lea     rax, [rbx+rbx*2]
0x18004991c  mov     [rdi+rax*8], rbp
0x180049920  lea     rax, [rbx+rbx*2]
0x180049924  mov     [rdi+rax*8+10h], rbp
0x180049929  mov     ebx, ebp
0x18004992b  mov     rcx, r12; CriticalSection
0x18004992e  call    cs:__imp_RtlLeaveCriticalSection
0x180049934  mov     eax, ebx
0x180049936  mov     rbx, [rsp+58h+arg_0]
0x18004993b  add     rsp, 20h
0x18004993f  pop     r15
0x180049941  pop     r14
0x180049943  pop     r13
0x180049945  pop     r12
0x180049947  pop     rdi
0x180049948  pop     rsi
0x180049949  pop     rbp
0x18004994a  retn
0x18004994b  mov     rcx, [rsp+58h+String1]; String1
0x180049950  call    cs:__imp__wcsicmp
0x180049956  test    eax, eax
0x180049958  jnz     loc_18004986A
0x18004995e  mov     rdx, [rdi+rsi*8+8]; pSid2
0x180049963  mov     rcx, r13; pSid1
0x180049966  call    cs:__imp_EqualSid
0x18004996c  xor     ebp, ebp
0x18004996e  test    eax, eax
0x180049970  jz      short loc_1800499C8
0x180049972  lea     rbx, [rdi+rsi*8]
0x180049976  test    r14d, r14d
0x180049979  jz      short loc_180049999
0x18004997b  mov     qword ptr [rbx+10h], 1
0x180049983  jmp     short loc_180049929
0x180049985  mov     rcx, [rdi+rsi*8]; lpMem
0x180049989  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004998e  mov     [rdi+rsi*8], rbp
0x180049992  mov     ebx, 0Eh
0x180049997  jmp     short loc_18004992B
0x180049999  lea     rcx, [rbx+10h]; SystemTime
0x18004999d  call    cs:__imp_NtQuerySystemTime
0x1800499a3  test    eax, eax
0x1800499a5  jz      short loc_180049929
0x1800499a7  mov     rcx, [rdi+rsi*8]; lpMem
0x1800499ab  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800499b0  xor     ecx, ecx; lpMem
0x1800499b2  mov     [rdi+rsi*8], rbp
0x1800499b6  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800499bb  mov     [rdi+rsi*8], rbp
0x1800499bf  mov     [rbx+10h], rbp
0x1800499c3  jmp     loc_180049929
0x1800499c8  mov     rcx, [rdi+rsi*8+8]; lpMem
0x1800499cd  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800499d2  mov     rcx, r13; pSourceSid
0x1800499d5  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x1800499da  mov     [rdi+rsi*8+8], rax
0x1800499df  test    rax, rax
0x1800499e2  jnz     short loc_180049972
0x1800499e4  mov     rcx, [rdi+rsi*8]; lpMem
0x1800499e8  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800499ed  mov     [rdi+rsi*8], rbp
0x1800499f1  mov     [rdi+rsi*8+10h], rbp
0x1800499f6  mov     rcx, r12; CriticalSection
0x1800499f9  call    cs:__imp_RtlLeaveCriticalSection
0x1800499ff  mov     eax, 0Eh
0x180049a04  jmp     loc_180049936
```

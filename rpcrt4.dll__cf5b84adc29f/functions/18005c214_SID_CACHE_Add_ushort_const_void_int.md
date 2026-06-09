# SID_CACHE::Add(ushort const *,void *,int)

- ea: `0x18005c214`
- end: `0x18005c443`
- name: `?Add@SID_CACHE@@QEAAJPEBGPEAXH@Z`
- size: `559`
- prototype: `int(SID_CACHE *__hidden this, const unsigned __int16 *, void *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f480`
- `0x180031a64`
- `0x18005c028`

## callees

- `0x180023a40`
- `0x18002e750`
- `0x1800307e0`
- `0x18005c214`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x18005c300`
- `ntdll!NtQuerySystemTime` at `0x18005c3c7`
- `ntdll!NtQuerySystemTime` at `0x18005c300`
- `ntdll!NtQuerySystemTime` at `0x18005c3c7`
- `ntdll!_wcsicmp` at `0x18005c36b`
- `ntdll!_wcsicmp` at `0x18005c36b`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c342`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c42d`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c342`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c42d`
- `ntdll!RtlEnterCriticalSection` at `0x18005c24d`
- `ntdll!RtlEnterCriticalSection` at `0x18005c24d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005c387`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005c387`

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
0x18005c214  mov     [rsp+arg_0], rbx
0x18005c219  mov     [rsp+arg_18], r9d
0x18005c21e  mov     [rsp+String1], rdx
0x18005c223  push    rbp
0x18005c224  push    rsi
0x18005c225  push    rdi
0x18005c226  push    r12
0x18005c228  push    r13
0x18005c22a  push    r14
0x18005c22c  push    r15
0x18005c22e  sub     rsp, 20h
0x18005c232  mov     rdi, qword ptr cs:?SIDCache@@3PEAVSID_CACHE@@EA.Revision; SID_CACHE * SIDCache ...
0x18005c239  mov     r14d, r9d
0x18005c23c  mov     r13, r8
0x18005c23f  xor     r15d, r15d
0x18005c242  mov     rbx, [rdi+10h]
0x18005c246  lea     r12, [rdi+60h]
0x18005c24a  mov     rcx, r12; CriticalSection
0x18005c24d  call    cs:__imp_RtlEnterCriticalSection
0x18005c254  nop     dword ptr [rax+rax+00h]
0x18005c259  xor     ebp, ebp
0x18005c25b  cmp     ebp, 4
0x18005c25e  jnb     short loc_18005C28B
0x18005c260  lea     rsi, ds:0[rbp*2]
0x18005c268  add     rsi, rbp
0x18005c26b  mov     rdx, [rdi+rsi*8]; String2
0x18005c26f  test    rdx, rdx
0x18005c272  jnz     loc_18005C366
0x18005c278  cmp     rbx, [rdi+rsi*8+10h]
0x18005c27d  jle     short loc_18005C287
0x18005c27f  mov     rbx, [rdi+rsi*8+10h]
0x18005c284  mov     r15d, ebp
0x18005c287  inc     ebp
0x18005c289  jmp     short loc_18005C25B
0x18005c28b  mov     ebx, r15d
0x18005c28e  xor     ebp, ebp
0x18005c290  lea     rsi, [rbx+rbx*2]
0x18005c294  lea     r14, [rdi+rsi*8]
0x18005c298  lea     r15, [rdi+rsi*8]
0x18005c29c  cmp     [r14+10h], rbp
0x18005c2a0  jz      short loc_18005C2C0
0x18005c2a2  mov     rcx, [rdi+rsi*8]; lpMem
0x18005c2a6  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c2ab  mov     rcx, [r15+8]; lpMem
0x18005c2af  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c2b4  mov     [rdi+rsi*8], rbp
0x18005c2b8  mov     [r15+8], rbp
0x18005c2bc  mov     [r14+10h], rbp
0x18005c2c0  mov     rcx, [rsp+58h+String1]; Src
0x18005c2c5  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18005c2ca  mov     [rdi+rsi*8], rax
0x18005c2ce  test    rax, rax
0x18005c2d1  jz      loc_18005C42A
0x18005c2d7  mov     rcx, r13; pSourceSid
0x18005c2da  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x18005c2df  mov     [r15+8], rax
0x18005c2e3  test    rax, rax
0x18005c2e6  jz      loc_18005C3AC
0x18005c2ec  cmp     [rsp+58h+arg_18], ebp
0x18005c2f0  jz      short loc_18005C2FC
0x18005c2f2  mov     qword ptr [r14+10h], 1
0x18005c2fa  jmp     short loc_18005C33D
0x18005c2fc  lea     rcx, [r14+10h]; SystemTime
0x18005c300  call    cs:__imp_NtQuerySystemTime
0x18005c307  nop     dword ptr [rax+rax+00h]
0x18005c30c  test    eax, eax
0x18005c30e  jz      short loc_18005C33D
0x18005c310  lea     rcx, [rbx+rbx*2]
0x18005c314  mov     rcx, [rdi+rcx*8]; lpMem
0x18005c318  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c31d  lea     rax, [rbx+rbx*2]
0x18005c321  xor     ecx, ecx; lpMem
0x18005c323  mov     [rdi+rax*8], rbp
0x18005c327  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c32c  lea     rax, [rbx+rbx*2]
0x18005c330  mov     [rdi+rax*8], rbp
0x18005c334  lea     rax, [rbx+rbx*2]
0x18005c338  mov     [rdi+rax*8+10h], rbp
0x18005c33d  mov     ebx, ebp
0x18005c33f  mov     rcx, r12; CriticalSection
0x18005c342  call    cs:__imp_RtlLeaveCriticalSection
0x18005c349  nop     dword ptr [rax+rax+00h]
0x18005c34e  mov     eax, ebx
0x18005c350  mov     rbx, [rsp+58h+arg_0]
0x18005c355  add     rsp, 20h
0x18005c359  pop     r15
0x18005c35b  pop     r14
0x18005c35d  pop     r13
0x18005c35f  pop     r12
0x18005c361  pop     rdi
0x18005c362  pop     rsi
0x18005c363  pop     rbp
0x18005c364  retn
0x18005c366  mov     rcx, [rsp+58h+String1]; String1
0x18005c36b  call    cs:__imp__wcsicmp
0x18005c372  nop     dword ptr [rax+rax+00h]
0x18005c377  test    eax, eax
0x18005c379  jnz     loc_18005C278
0x18005c37f  mov     rdx, [rdi+rsi*8+8]; pSid2
0x18005c384  mov     rcx, r13; pSid1
0x18005c387  call    cs:__imp_EqualSid
0x18005c38e  nop     dword ptr [rax+rax+00h]
0x18005c393  xor     ebp, ebp
0x18005c395  test    eax, eax
0x18005c397  jz      short loc_18005C3FC
0x18005c399  lea     rbx, [rdi+rsi*8]
0x18005c39d  test    r14d, r14d
0x18005c3a0  jz      short loc_18005C3C3
0x18005c3a2  mov     qword ptr [rbx+10h], 1
0x18005c3aa  jmp     short loc_18005C33D
0x18005c3ac  mov     rcx, [rdi+rsi*8]; lpMem
0x18005c3b0  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c3b5  mov     [rdi+rsi*8], rbp
0x18005c3b9  mov     ebx, 0Eh
0x18005c3be  jmp     loc_18005C33F
0x18005c3c3  lea     rcx, [rbx+10h]; SystemTime
0x18005c3c7  call    cs:__imp_NtQuerySystemTime
0x18005c3ce  nop     dword ptr [rax+rax+00h]
0x18005c3d3  test    eax, eax
0x18005c3d5  jz      loc_18005C33D
0x18005c3db  mov     rcx, [rdi+rsi*8]; lpMem
0x18005c3df  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c3e4  xor     ecx, ecx; lpMem
0x18005c3e6  mov     [rdi+rsi*8], rbp
0x18005c3ea  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c3ef  mov     [rdi+rsi*8], rbp
0x18005c3f3  mov     [rbx+10h], rbp
0x18005c3f7  jmp     loc_18005C33D
0x18005c3fc  mov     rcx, [rdi+rsi*8+8]; lpMem
0x18005c401  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c406  mov     rcx, r13; pSourceSid
0x18005c409  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x18005c40e  mov     [rdi+rsi*8+8], rax
0x18005c413  test    rax, rax
0x18005c416  jnz     short loc_18005C399
0x18005c418  mov     rcx, [rdi+rsi*8]; lpMem
0x18005c41c  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005c421  mov     [rdi+rsi*8], rbp
0x18005c425  mov     [rdi+rsi*8+10h], rbp
0x18005c42a  mov     rcx, r12; CriticalSection
0x18005c42d  call    cs:__imp_RtlLeaveCriticalSection
0x18005c434  nop     dword ptr [rax+rax+00h]
0x18005c439  mov     eax, 0Eh
0x18005c43e  jmp     loc_18005C350
```

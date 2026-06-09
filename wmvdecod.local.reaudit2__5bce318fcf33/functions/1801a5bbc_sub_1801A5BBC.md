# sub_1801A5BBC

- ea: `0x1801a5bbc`
- end: `0x1801a5da1`
- name: `sub_1801A5BBC`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801a49b0`

## callees

- `0x180099e80`
- `0x180099e8c`
- `0x180099ee0`
- `0x1801a5bbc`
- `0x1801b5268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a5cda`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801a5cda`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801a5c93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801a5c93`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a5c1e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a5c74`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a5c1e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801a5c74`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801a5d68`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801a5d68`

## pseudocode

```c
__int64 __fastcall sub_1801A5BBC(__int64 a1, int a2)
{
  LPCRITICAL_SECTION *v4; // rdi
  __int64 v5; // rax
  __int64 *v6; // rsi
  __int64 v7; // rax
  HANDLE EventW; // rax
  int i; // edi
  void *v10; // rax

  if ( a2 > 64 )
    return 4294967282LL;
  v4 = (LPCRITICAL_SECTION *)(a1 + 1864);
  *(_DWORD *)(a1 + 15448) = a2;
  *(_DWORD *)(a1 + 1872) = 0;
  if ( a1 != -1864 )
  {
    v5 = o_malloc(40);
    if ( v5 )
    {
      *(_OWORD *)v5 = 0;
      *(_OWORD *)(v5 + 16) = 0;
      *(_QWORD *)(v5 + 32) = 0;
      *v4 = (LPCRITICAL_SECTION)v5;
      InitializeCriticalSection((LPCRITICAL_SECTION)v5);
    }
    else
    {
      *v4 = 0;
    }
  }
  if ( !*v4 )
    return 4294967294LL;
  _InterlockedExchange((volatile __int32 *)(a1 + 5940), 0);
  if ( !*v4 )
    return 4294967294LL;
  v6 = (__int64 *)(a1 + 5920);
  if ( a1 != -5920 )
  {
    v7 = o_malloc(40);
    if ( v7 )
    {
      *(_OWORD *)v7 = 0;
      *(_OWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v7 + 32) = 0;
      *v6 = v7;
      InitializeCriticalSection((LPCRITICAL_SECTION)v7);
    }
    else
    {
      *v6 = 0;
    }
  }
  if ( !*v6 )
  {
    if ( *v4 )
    {
      DeleteCriticalSection(*v4);
      o_free(*v4);
      *v4 = 0;
    }
    return 4294967294LL;
  }
  *(_DWORD *)(a1 + 1848) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 1856) = EventW;
  if ( !EventW )
    return 4294967294LL;
  for ( i = 0; i < *(_DWORD *)(a1 + 15448); ++i )
  {
    v10 = (void *)sub_1801B5268(a1 + 8, 262208);
    *(_QWORD *)(a1 + 8LL * i + 2136) = v10;
    if ( !v10 )
      return 4294967294LL;
    memset(v10, 0, 0x40040u);
    **(_QWORD **)(a1 + 8LL * i + 2136) = a1;
    *(_DWORD *)(*(_QWORD *)(a1 + 8LL * i + 2136) + 8LL) = i;
    *(_QWORD *)(*(_QWORD *)(a1 + 8LL * i + 2136) + 16LL) = CreateThread(
                                                             0,
                                                             0,
                                                             sub_18005CC80,
                                                             *(LPVOID *)(a1 + 8LL * i + 2136),
                                                             4u,
                                                             0);
    if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8LL * i + 2136) + 16LL) )
      return 4294967294LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1801a5bbc  mov     [rsp+arg_0], rbx
0x1801a5bc1  mov     [rsp+arg_8], rsi
0x1801a5bc6  push    rdi
0x1801a5bc7  sub     rsp, 30h
0x1801a5bcb  mov     rbx, rcx
0x1801a5bce  cmp     edx, 40h ; '@'
0x1801a5bd1  jle     short loc_1801A5BDD
0x1801a5bd3  mov     eax, 0FFFFFFF2h
0x1801a5bd8  jmp     loc_1801A5CB3
0x1801a5bdd  lea     rdi, [rcx+748h]
0x1801a5be4  mov     [rcx+3C58h], edx
0x1801a5bea  mov     dword ptr [rcx+750h], 0
0x1801a5bf4  test    rdi, rdi
0x1801a5bf7  jz      short loc_1801A5C2F
0x1801a5bf9  mov     ecx, 28h ; '('
0x1801a5bfe  call    _o_malloc
0x1801a5c03  test    rax, rax
0x1801a5c06  jz      short loc_1801A5C2C
0x1801a5c08  xorps   xmm0, xmm0
0x1801a5c0b  xor     ecx, ecx
0x1801a5c0d  movups  xmmword ptr [rax], xmm0
0x1801a5c10  movups  xmmword ptr [rax+10h], xmm0
0x1801a5c14  mov     [rax+20h], rcx
0x1801a5c18  mov     rcx, rax; lpCriticalSection
0x1801a5c1b  mov     [rdi], rax
0x1801a5c1e  call    cs:InitializeCriticalSection
0x1801a5c25  nop     dword ptr [rax+rax+00h]
0x1801a5c2a  jmp     short loc_1801A5C2F
0x1801a5c2c  mov     [rdi], rax
0x1801a5c2f  cmp     qword ptr [rdi], 0
0x1801a5c33  jz      short loc_1801A5CAE
0x1801a5c35  xor     eax, eax
0x1801a5c37  xchg    eax, [rbx+1734h]
0x1801a5c3d  cmp     qword ptr [rdi], 0
0x1801a5c41  jz      short loc_1801A5CAE
0x1801a5c43  lea     rsi, [rbx+1720h]
0x1801a5c4a  test    rsi, rsi
0x1801a5c4d  jz      short loc_1801A5C85
0x1801a5c4f  mov     ecx, 28h ; '('
0x1801a5c54  call    _o_malloc
0x1801a5c59  test    rax, rax
0x1801a5c5c  jz      short loc_1801A5C82
0x1801a5c5e  xorps   xmm0, xmm0
0x1801a5c61  xor     ecx, ecx
0x1801a5c63  movups  xmmword ptr [rax], xmm0
0x1801a5c66  movups  xmmword ptr [rax+10h], xmm0
0x1801a5c6a  mov     [rax+20h], rcx
0x1801a5c6e  mov     rcx, rax; lpCriticalSection
0x1801a5c71  mov     [rsi], rax
0x1801a5c74  call    cs:InitializeCriticalSection
0x1801a5c7b  nop     dword ptr [rax+rax+00h]
0x1801a5c80  jmp     short loc_1801A5C85
0x1801a5c82  mov     [rsi], rax
0x1801a5c85  cmp     qword ptr [rsi], 0
0x1801a5c89  jnz     short loc_1801A5CC4
0x1801a5c8b  mov     rcx, [rdi]; lpCriticalSection
0x1801a5c8e  test    rcx, rcx
0x1801a5c91  jz      short loc_1801A5CAE
0x1801a5c93  call    cs:DeleteCriticalSection
0x1801a5c9a  nop     dword ptr [rax+rax+00h]
0x1801a5c9f  mov     rcx, [rdi]
0x1801a5ca2  call    _o_free
0x1801a5ca7  mov     qword ptr [rdi], 0
0x1801a5cae  mov     eax, 0FFFFFFFEh
0x1801a5cb3  mov     rbx, [rsp+38h+arg_0]
0x1801a5cb8  mov     rsi, [rsp+38h+arg_8]
0x1801a5cbd  add     rsp, 30h
0x1801a5cc1  pop     rdi
0x1801a5cc2  retn
0x1801a5cc4  xor     r9d, r9d; lpName
0x1801a5cc7  mov     dword ptr [rbx+738h], 0
0x1801a5cd1  xor     r8d, r8d; bInitialState
0x1801a5cd4  xor     ecx, ecx; lpEventAttributes
0x1801a5cd6  lea     edx, [r9+1]; bManualReset
0x1801a5cda  call    cs:CreateEventW
0x1801a5ce1  nop     dword ptr [rax+rax+00h]
0x1801a5ce6  mov     [rbx+740h], rax
0x1801a5ced  test    rax, rax
0x1801a5cf0  jz      short loc_1801A5CAE
0x1801a5cf2  xor     edi, edi
0x1801a5cf4  cmp     edi, [rbx+3C58h]
0x1801a5cfa  jge     loc_1801A5D9A
0x1801a5d00  lea     rcx, [rbx+8]
0x1801a5d04  mov     edx, 40040h
0x1801a5d09  call    sub_1801B5268
0x1801a5d0e  movsxd  rsi, edi
0x1801a5d11  mov     [rbx+rsi*8+858h], rax
0x1801a5d19  test    rax, rax
0x1801a5d1c  jz      short loc_1801A5CAE
0x1801a5d1e  xor     edx, edx; Val
0x1801a5d20  mov     r8d, 40040h; Size
0x1801a5d26  mov     rcx, rax; void *
0x1801a5d29  call    memset
0x1801a5d2e  mov     rax, [rbx+rsi*8+858h]
0x1801a5d36  lea     r8, sub_18005CC80; lpStartAddress
0x1801a5d3d  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1801a5d46  xor     edx, edx; dwStackSize
0x1801a5d48  xor     ecx, ecx; lpThreadAttributes
0x1801a5d4a  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1801a5d52  mov     [rax], rbx
0x1801a5d55  mov     rax, [rbx+rsi*8+858h]
0x1801a5d5d  mov     [rax+8], edi
0x1801a5d60  mov     r9, [rbx+rsi*8+858h]; lpParameter
0x1801a5d68  call    cs:CreateThread
0x1801a5d6f  nop     dword ptr [rax+rax+00h]
0x1801a5d74  mov     rcx, [rbx+rsi*8+858h]
0x1801a5d7c  mov     [rcx+10h], rax
0x1801a5d80  mov     rax, [rbx+rsi*8+858h]
0x1801a5d88  cmp     qword ptr [rax+10h], 0
0x1801a5d8d  jz      loc_1801A5CAE
0x1801a5d93  inc     edi
0x1801a5d95  jmp     loc_1801A5CF4
0x1801a5d9a  xor     eax, eax
0x1801a5d9c  jmp     loc_1801A5CB3
```

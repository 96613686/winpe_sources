# SstpWebSendRequestEntityCompletion

- ea: `0x180001160`
- end: `0x180001237`
- name: `SstpWebSendRequestEntityCompletion`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002e00`
- `0x180006b64`

## callees

- `0x180001160`
- `0x180002908`
- `0x1800077bc`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001192`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800011f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001192`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800011f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800011c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800011c9`

## pseudocode

```c
__int64 __fastcall SstpWebSendRequestEntityCompletion(__int64 a1, int a2)
{
  __int64 v2; // rbp
  char *v4; // rdi
  char *v5; // rdi
  _QWORD *v6; // rbx
  __int64 v7; // rax
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 56);
  if ( a2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 288));
    InitiateCallContextCleanup(v2, 1u);
  }
  v4 = (char *)SstpSvcGlobals;
  *(_QWORD *)(a1 + 56) = 0;
  v5 = v4 + 424;
  v6 = (_QWORD *)(a1 - 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 64));
  if ( (_QWORD *)*v6 == v6 )
  {
    v7 = *((_QWORD *)v5 + 5);
    *v6 = v7;
    v6[1] = v5 + 40;
    *(_QWORD *)(v7 + 8) = v6;
    *((_QWORD *)v5 + 5) = v6;
    ++*(_DWORD *)(v6[2] + 28LL);
    if ( ++*((_DWORD *)v5 + 5) >= *((_DWORD *)v5 + 4) )
    {
      FreeUnusedBufferPoolBlocks(v5);
      *((_DWORD *)v5 + 5) = 0;
    }
  }
  else
  {
    ++g_ulDoubleBufferFrees;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 64));
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 208), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return (*(__int64 (__fastcall **)(__int64))(v2 + 216))(v2 + 208);
  return result;
}

```

## disassembly

```asm
0x180001160  push    rbx
0x180001162  push    rbp
0x180001163  push    rsi
0x180001164  push    rdi
0x180001165  sub     rsp, 28h
0x180001169  mov     rbp, [rcx+38h]
0x18000116d  mov     rbx, rcx
0x180001170  test    edx, edx
0x180001172  jnz     short loc_1800011EA
0x180001174  mov     rdi, cs:SstpSvcGlobals
0x18000117b  mov     qword ptr [rbx+38h], 0
0x180001183  add     rdi, 1A8h
0x18000118a  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18000118e  lea     rcx, [rdi+40h]; lpCriticalSection
0x180001192  call    cs:__imp_EnterCriticalSection
0x180001198  cmp     [rbx], rbx
0x18000119b  jnz     short loc_180001209
0x18000119d  mov     rax, [rdi+28h]
0x1800011a1  lea     rcx, [rdi+28h]
0x1800011a5  mov     [rbx], rax
0x1800011a8  mov     [rbx+8], rcx
0x1800011ac  mov     [rax+8], rbx
0x1800011b0  mov     [rcx], rbx
0x1800011b3  mov     rax, [rbx+10h]
0x1800011b7  inc     dword ptr [rax+1Ch]
0x1800011ba  inc     dword ptr [rdi+14h]
0x1800011bd  mov     eax, [rdi+14h]
0x1800011c0  cmp     eax, [rdi+10h]
0x1800011c3  jnb     short loc_180001211
0x1800011c5  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800011c9  call    cs:__imp_LeaveCriticalSection
0x1800011cf  mov     eax, 0FFFFFFFFh
0x1800011d4  lock xadd [rbp+0D0h], eax
0x1800011dc  cmp     eax, 1
0x1800011df  jz      short loc_180001222
0x1800011e1  add     rsp, 28h
0x1800011e5  pop     rdi
0x1800011e6  pop     rsi
0x1800011e7  pop     rbp
0x1800011e8  pop     rbx
0x1800011e9  retn
0x1800011ea  lea     rcx, [rbp+120h]; lpCriticalSection
0x1800011f1  call    cs:__imp_EnterCriticalSection
0x1800011f7  mov     edx, 1
0x1800011fc  mov     rcx, rbp
0x1800011ff  call    InitiateCallContextCleanup
0x180001204  jmp     loc_180001174
0x180001209  inc     cs:g_ulDoubleBufferFrees
0x18000120f  jmp     short loc_1800011C5
0x180001211  mov     rcx, rdi
0x180001214  call    FreeUnusedBufferPoolBlocks
0x180001219  mov     dword ptr [rdi+14h], 0
0x180001220  jmp     short loc_1800011C5
0x180001222  mov     rax, [rbp+0D8h]
0x180001229  lea     rcx, [rbp+0D0h]
0x180001230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001235  jmp     short loc_1800011E1
```

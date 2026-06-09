# SstpWebSendRequestEntityCompletion

- ea: `0x1800011b0`
- end: `0x18000129e`
- name: `SstpWebSendRequestEntityCompletion`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003010`
- `0x1800071cc`

## callees

- `0x1800011b0`
- `0x180002aac`
- `0x180007f48`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800011e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001252`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800011e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001252`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001223`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001223`

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
0x1800011b0  push    rbx
0x1800011b2  push    rbp
0x1800011b3  push    rsi
0x1800011b4  push    rdi
0x1800011b5  sub     rsp, 28h
0x1800011b9  mov     rbp, [rcx+38h]
0x1800011bd  mov     rbx, rcx
0x1800011c0  test    edx, edx
0x1800011c2  jnz     loc_18000124B
0x1800011c8  mov     rdi, cs:SstpSvcGlobals
0x1800011cf  mov     qword ptr [rbx+38h], 0
0x1800011d7  add     rdi, 1A8h
0x1800011de  add     rbx, 0FFFFFFFFFFFFFFE8h
0x1800011e2  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800011e6  call    cs:__imp_EnterCriticalSection
0x1800011ed  nop     dword ptr [rax+rax+00h]
0x1800011f2  cmp     [rbx], rbx
0x1800011f5  jnz     short loc_180001270
0x1800011f7  mov     rax, [rdi+28h]
0x1800011fb  lea     rcx, [rdi+28h]
0x1800011ff  mov     [rbx], rax
0x180001202  mov     [rbx+8], rcx
0x180001206  mov     [rax+8], rbx
0x18000120a  mov     [rcx], rbx
0x18000120d  mov     rax, [rbx+10h]
0x180001211  inc     dword ptr [rax+1Ch]
0x180001214  inc     dword ptr [rdi+14h]
0x180001217  mov     eax, [rdi+14h]
0x18000121a  cmp     eax, [rdi+10h]
0x18000121d  jnb     short loc_180001278
0x18000121f  lea     rcx, [rdi+40h]; lpCriticalSection
0x180001223  call    cs:__imp_LeaveCriticalSection
0x18000122a  nop     dword ptr [rax+rax+00h]
0x18000122f  mov     eax, 0FFFFFFFFh
0x180001234  lock xadd [rbp+0D0h], eax
0x18000123c  cmp     eax, 1
0x18000123f  jz      short loc_180001289
0x180001241  add     rsp, 28h
0x180001245  pop     rdi
0x180001246  pop     rsi
0x180001247  pop     rbp
0x180001248  pop     rbx
0x180001249  retn
0x18000124b  lea     rcx, [rbp+120h]; lpCriticalSection
0x180001252  call    cs:__imp_EnterCriticalSection
0x180001259  nop     dword ptr [rax+rax+00h]
0x18000125e  mov     edx, 1
0x180001263  mov     rcx, rbp
0x180001266  call    InitiateCallContextCleanup
0x18000126b  jmp     loc_1800011C8
0x180001270  inc     cs:g_ulDoubleBufferFrees
0x180001276  jmp     short loc_18000121F
0x180001278  mov     rcx, rdi
0x18000127b  call    FreeUnusedBufferPoolBlocks
0x180001280  mov     dword ptr [rdi+14h], 0
0x180001287  jmp     short loc_18000121F
0x180001289  mov     rax, [rbp+0D8h]
0x180001290  lea     rcx, [rbp+0D0h]
0x180001297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000129c  jmp     short loc_180001241
```

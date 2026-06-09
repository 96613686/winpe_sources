# ChReferenceClientChannel

- ea: `0x1400111ac`
- end: `0x1400112d3`
- name: `ChReferenceClientChannel`
- size: `295`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011418`
- `0x140011920`
- `0x140011a2c`
- `0x14002deb8`

## callees

- `0x1400111ac`
- `0x140012198`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001126b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400112c2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001126b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400112c2`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400111ca`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400111ca`

## pseudocode

```c
volatile signed __int32 *__fastcall ChReferenceClientChannel(__int64 a1, unsigned int a2)
{
  struct _FAST_MUTEX *v2; // rdi
  __int64 *v5; // r8
  volatile signed __int32 *i; // rbx
  signed __int64 v7; // rax
  unsigned __int64 j; // rcx
  signed __int64 v9; // rtt
  char v10; // dl
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8

  v2 = (struct _FAST_MUTEX *)(a1 + 432);
  ExAcquireFastMutex((PFAST_MUTEX)(a1 + 432));
  v5 = (__int64 *)(a1 + 616);
  for ( i = *(volatile signed __int32 **)(a1 + 616); i != (volatile signed __int32 *)v5; i = *(volatile signed __int32 **)i )
  {
    if ( *((_DWORD *)i + 6) == a2 )
    {
      _m_prefetchw((const void *)(i + 60));
      v7 = *((_QWORD *)i + 30);
      for ( j = v7 + 1; j > 1; j = v7 + 1 )
      {
        v9 = v7;
        v7 = _InterlockedCompareExchange64((volatile signed __int64 *)i + 30, j, v7);
        if ( v9 == v7 )
        {
          v10 = 1;
          goto LABEL_10;
        }
      }
      if ( j != 1 )
        __fastfail(0xEu);
      v10 = 0;
LABEL_10:
      v11 = _InterlockedExchangeAdd(i + 320, 1u) & 0x1F;
      LOBYTE(i[2 * v11 + 321]) = (4 * v10) | 3;
      HIWORD(i[2 * v11 + 321]) = 663;
      i[2 * v11 + 322] = 4;
      if ( v10 )
      {
        ExReleaseFastMutex(v2);
        return i;
      }
    }
  }
  ExReleaseFastMutex(v2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, v12, v13, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x1400111ac  mov     [rsp+arg_0], rbx
0x1400111b1  mov     [rsp+arg_8], rsi
0x1400111b6  push    rdi
0x1400111b7  sub     rsp, 20h
0x1400111bb  lea     rdi, [rcx+1B0h]
0x1400111c2  mov     rbx, rcx
0x1400111c5  mov     rcx, rdi; FastMutex
0x1400111c8  mov     esi, edx
0x1400111ca  call    cs:__imp_ExAcquireFastMutex
0x1400111d1  nop     dword ptr [rax+rax+00h]
0x1400111d6  lea     r8, [rbx+268h]
0x1400111dd  mov     rbx, [r8]
0x1400111e0  jmp     short loc_14001125F
0x1400111e2  cmp     [rbx+18h], esi
0x1400111e5  jnz     short loc_14001125C
0x1400111e7  prefetchw byte ptr [rbx+0F0h]
0x1400111ee  mov     rax, [rbx+0F0h]
0x1400111f5  lea     rcx, [rax+1]
0x1400111f9  jmp     short loc_140011210
0x1400111fb  lock cmpxchg [rbx+0F0h], rcx
0x140011204  mov     rcx, rax
0x140011207  jz      loc_1400112B8
0x14001120d  inc     rcx
0x140011210  cmp     rcx, 1
0x140011214  ja      short loc_1400111FB
0x140011216  cmp     rcx, 1
0x14001121a  jz      short loc_140011223
0x14001121c  mov     ecx, 0Eh
0x140011221  int     29h; Win8: RtlFailFast(ecx)
0x140011223  xor     dl, dl
0x140011225  mov     ecx, 1
0x14001122a  lock xadd [rbx+500h], ecx
0x140011232  and     ecx, 1Fh
0x140011235  mov     al, dl
0x140011237  shl     al, 2
0x14001123a  or      al, 3
0x14001123c  mov     [rbx+rcx*8+504h], al
0x140011243  mov     word ptr [rbx+rcx*8+506h], 297h
0x14001124d  mov     dword ptr [rbx+rcx*8+508h], 4
0x140011258  test    dl, dl
0x14001125a  jnz     short loc_1400112BF
0x14001125c  mov     rbx, [rbx]
0x14001125f  cmp     rbx, r8
0x140011262  jnz     loc_1400111E2
0x140011268  mov     rcx, rdi; FastMutex
0x14001126b  call    cs:__imp_ExReleaseFastMutex
0x140011272  nop     dword ptr [rax+rax+00h]
0x140011277  mov     rcx, cs:WPP_GLOBAL_Control
0x14001127e  lea     rax, WPP_GLOBAL_Control
0x140011285  cmp     rcx, rax
0x140011288  jz      short loc_1400112A5
0x14001128a  test    dword ptr [rcx+2Ch], 80000h
0x140011291  jz      short loc_1400112A5
0x140011293  cmp     byte ptr [rcx+29h], 3
0x140011297  jb      short loc_1400112A5
0x140011299  mov     rcx, [rcx+18h]
0x14001129d  mov     r9d, esi
0x1400112a0  call    WPP_SF_D
0x1400112a5  xor     eax, eax
0x1400112a7  mov     rbx, [rsp+28h+arg_0]
0x1400112ac  mov     rsi, [rsp+28h+arg_8]
0x1400112b1  add     rsp, 20h
0x1400112b5  pop     rdi
0x1400112b6  retn
0x1400112b8  mov     dl, 1
0x1400112ba  jmp     loc_140011225
0x1400112bf  mov     rcx, rdi; FastMutex
0x1400112c2  call    cs:__imp_ExReleaseFastMutex
0x1400112c9  nop     dword ptr [rax+rax+00h]
0x1400112ce  mov     rax, rbx
0x1400112d1  jmp     short loc_1400112A7
```

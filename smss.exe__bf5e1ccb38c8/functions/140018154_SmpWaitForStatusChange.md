# SmpWaitForStatusChange

- ea: `0x140018154`
- end: `0x1400182c6`
- name: `SmpWaitForStatusChange`
- size: `370`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001580`
- `0x140001630`
- `0x140001f60`
- `0x140002bb0`
- `0x140008210`

## callees

- `0x140001450`
- `0x1400030f0`
- `0x140003114`
- `0x140008cd0`
- `0x14000aca0`
- `0x140017ff0`
- `0x140018088`
- `0x140018154`

## import_xrefs

- `ntdll!NtDelayExecution` at `0x1400181a6`
- `ntdll!NtDelayExecution` at `0x1400181a6`
- `ntdll!NtWaitForMultipleObjects` at `0x140018233`
- `ntdll!NtWaitForMultipleObjects` at `0x140018233`

## pseudocode

```c
__int64 __fastcall SmpWaitForStatusChange(__int64 a1, int a2, unsigned int *a3)
{
  void *v6; // rsi
  _DWORD *SubSysSynch; // rbx
  signed __int64 v8; // rax
  ULONG v9; // ecx
  NTSTATUS v10; // eax
  unsigned int v11; // esi
  __int64 ProcessId; // rax
  HANDLE Object[5]; // [rsp+30h] [rbp-28h] BYREF
  LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  *(_OWORD *)Object = 0;
  v6 = 0;
  while ( 1 )
  {
    SubSysSynch = *(_DWORD **)(a1 + 16);
    if ( SubSysSynch )
      goto LABEL_10;
    SmpUnlockKnownSubSysList(a3);
    SubSysSynch = SmpGetSubSysSynch();
    if ( !SubSysSynch )
    {
      Interval.QuadPart = -50000000;
      NtDelayExecution(0, &Interval);
    }
    SmpLockKnownSubSysList(*(unsigned int *)(a1 + 64), *a3, 0);
    if ( (unsigned int)SmpCheckSubSysStatus(a1) )
      break;
    if ( SubSysSynch )
    {
      if ( *(_QWORD *)(a1 + 16) )
      {
        v6 = SubSysSynch;
        SubSysSynch = *(_DWORD **)(a1 + 16);
      }
      else
      {
        v8 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 16), (signed __int64)SubSysSynch, 0);
        if ( v8 )
        {
          v6 = SubSysSynch;
          SubSysSynch = (_DWORD *)v8;
        }
      }
LABEL_10:
      _InterlockedIncrement(SubSysSynch);
      SmpUnlockKnownSubSysList(a3);
      if ( v6 )
        SmpDisposeSubSysSynch(v6);
      v9 = 1;
      Object[0] = *((HANDLE *)SubSysSynch + 1);
      if ( a2 == 1 )
      {
        v9 = 2;
        Object[1] = *(HANDLE *)(a1 + 32);
      }
      v10 = NtWaitForMultipleObjects(v9, Object, WaitAny, 0, 0);
      v11 = v10;
      if ( v10 )
      {
        if ( v10 == 1 )
        {
          ProcessId = SmpGetProcessId(*(void **)(a1 + 48));
          SmLogFailureInt((__int64)"SmpWaitForStatusChange", 0x3C5u, ProcessId, 0, 1u);
          v11 = -1073741823;
        }
      }
      else
      {
        if ( _InterlockedExchangeAdd(SubSysSynch, 0xFFFFFFFF) == 1 )
          SmpDisposeSubSysSynch(SubSysSynch);
        v11 = 0;
      }
      SmpLockKnownSubSysList(*(unsigned int *)(a1 + 64), *a3, 0);
      return v11;
    }
  }
  if ( SubSysSynch )
    SmpDisposeSubSysSynch(SubSysSynch);
  return 0;
}

```

## disassembly

```asm
0x140018154  mov     [rsp+arg_8], rbx
0x140018159  mov     [rsp+arg_10], rbp
0x14001815e  push    rsi
0x14001815f  push    rdi
0x140018160  push    r14
0x140018162  sub     rsp, 40h
0x140018166  xorps   xmm0, xmm0
0x140018169  mov     r14, r8
0x14001816c  movups  xmmword ptr [rsp+58h+Object], xmm0
0x140018171  mov     ebp, edx
0x140018173  mov     rdi, rcx
0x140018176  xor     esi, esi
0x140018178  mov     rbx, [rdi+10h]
0x14001817c  test    rbx, rbx
0x14001817f  jnz     short loc_1400181E6
0x140018181  mov     rcx, r14
0x140018184  call    SmpUnlockKnownSubSysList
0x140018189  call    SmpGetSubSysSynch
0x14001818e  mov     rbx, rax
0x140018191  test    rax, rax
0x140018194  jnz     short loc_1400181AC
0x140018196  lea     rdx, [rsp+58h+Interval]; Interval
0x14001819b  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFD050F80h
0x1400181a4  xor     ecx, ecx; Alertable
0x1400181a6  call    cs:__imp_NtDelayExecution
0x1400181ac  mov     edx, [r14]
0x1400181af  xor     r8d, r8d
0x1400181b2  mov     ecx, [rdi+40h]
0x1400181b5  call    SmpLockKnownSubSysList
0x1400181ba  mov     rcx, rdi
0x1400181bd  call    SmpCheckSubSysStatus
0x1400181c2  test    eax, eax
0x1400181c4  jnz     loc_140018260
0x1400181ca  test    rbx, rbx
0x1400181cd  jz      short loc_140018178
0x1400181cf  mov     rax, [rdi+10h]
0x1400181d3  test    rax, rax
0x1400181d6  jnz     short loc_140018257
0x1400181d8  lock cmpxchg [rdi+10h], rbx
0x1400181de  jz      short loc_1400181E6
0x1400181e0  mov     rsi, rbx
0x1400181e3  mov     rbx, rax
0x1400181e6  lock inc dword ptr [rbx]
0x1400181e9  mov     rcx, r14
0x1400181ec  call    SmpUnlockKnownSubSysList
0x1400181f1  test    rsi, rsi
0x1400181f4  jz      short loc_1400181FE
0x1400181f6  mov     rcx, rsi; BaseAddress
0x1400181f9  call    SmpDisposeSubSysSynch
0x1400181fe  mov     rax, [rbx+8]
0x140018202  mov     ecx, 1
0x140018207  mov     [rsp+58h+Object], rax
0x14001820c  cmp     ebp, ecx
0x14001820e  jnz     short loc_14001821E
0x140018210  mov     rax, [rdi+20h]
0x140018214  mov     ecx, 2; Count
0x140018219  mov     [rsp+58h+Object+8], rax
0x14001821e  xor     r9d, r9d; Alertable
0x140018221  mov     [rsp+58h+Time], 0; Time
0x14001822a  lea     rdx, [rsp+58h+Object]; Object
0x14001822f  lea     r8d, [r9+1]; WaitType
0x140018233  call    cs:__imp_NtWaitForMultipleObjects
0x140018239  mov     esi, eax
0x14001823b  test    eax, eax
0x14001823d  jnz     short loc_140018271
0x14001823f  or      eax, 0FFFFFFFFh
0x140018242  lock xadd [rbx], eax
0x140018246  cmp     eax, 1
0x140018249  jnz     short loc_140018253
0x14001824b  mov     rcx, rbx; BaseAddress
0x14001824e  call    SmpDisposeSubSysSynch
0x140018253  xor     esi, esi
0x140018255  jmp     short loc_1400182A3
0x140018257  mov     rsi, rbx
0x14001825a  mov     rbx, [rdi+10h]
0x14001825e  jmp     short loc_1400181E6
0x140018260  test    rbx, rbx
0x140018263  jz      short loc_14001826D
0x140018265  mov     rcx, rbx; BaseAddress
0x140018268  call    SmpDisposeSubSysSynch
0x14001826d  xor     eax, eax
0x14001826f  jmp     short loc_1400182B3
0x140018271  cmp     eax, 1
0x140018274  jnz     short loc_1400182A3
0x140018276  mov     rcx, [rdi+30h]
0x14001827a  call    SmpGetProcessId
0x14001827f  mov     r8, rax
0x140018282  mov     dword ptr [rsp+58h+Time], 1
0x14001828a  xor     r9d, r9d
0x14001828d  lea     rcx, aSmpwaitforstat; "SmpWaitForStatusChange"
0x140018294  mov     edx, 3C5h
0x140018299  call    SmLogFailureInt
0x14001829e  mov     esi, 0C0000001h
0x1400182a3  mov     edx, [r14]
0x1400182a6  xor     r8d, r8d
0x1400182a9  mov     ecx, [rdi+40h]
0x1400182ac  call    SmpLockKnownSubSysList
0x1400182b1  mov     eax, esi
0x1400182b3  mov     rbx, [rsp+58h+arg_8]
0x1400182b8  mov     rbp, [rsp+58h+arg_10]
0x1400182bd  add     rsp, 40h
0x1400182c1  pop     r14
0x1400182c3  pop     rdi
0x1400182c4  pop     rsi
0x1400182c5  retn
```

# CTimerQueue::HrInitialize(void)

- ea: `0x18000b384`
- end: `0x18000b473`
- name: `?HrInitialize@CTimerQueue@@QEAAJXZ`
- size: `239`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a768`

## callees

- `0x18000554c`
- `0x18000b384`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b3c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b45e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b3c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b45e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b39e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b39e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000b3d8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000b3d8`

## pseudocode

```c
__int64 __fastcall CTimerQueue::HrInitialize(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  unsigned int v4; // esi
  __int64 i; // rbp
  HANDLE TimerQueue; // rax
  __int64 v7; // r14
  unsigned int Win32Error; // eax

  v1 = this + 40;
  EnterCriticalSection(this + 40);
  if ( (int)++LODWORD(this[41].DebugInfo) <= 1 )
  {
    v4 = 0;
    for ( i = 0; i != 100; ++i )
    {
      TimerQueue = CreateTimerQueue();
      v7 = 2 * i;
      *((_QWORD *)&this->DebugInfo + 2 * i) = TimerQueue;
      if ( !TimerQueue )
      {
        Win32Error = HrFromLastWin32Error();
        v4 = Win32Error;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, Win32Error);
      }
      *((_WORD *)&this->LockCount + 4 * v7) = 0;
    }
    if ( v4 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v4);
    LeaveCriticalSection(v1);
    return v4;
  }
  else
  {
    LeaveCriticalSection(v1);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b384  push    rbx
0x18000b386  push    rbp
0x18000b387  push    rsi
0x18000b388  push    rdi
0x18000b389  push    r14
0x18000b38b  push    r15
0x18000b38d  sub     rsp, 28h
0x18000b391  lea     rbx, [rcx+640h]
0x18000b398  mov     rdi, rcx
0x18000b39b  mov     rcx, rbx; lpCriticalSection
0x18000b39e  call    cs:__imp_EnterCriticalSection
0x18000b3a4  mov     eax, [rdi+668h]
0x18000b3aa  inc     eax
0x18000b3ac  mov     [rdi+668h], eax
0x18000b3b2  mov     eax, [rdi+668h]
0x18000b3b8  cmp     eax, 1
0x18000b3bb  jle     short loc_18000B3CD
0x18000b3bd  mov     rcx, rbx; lpCriticalSection
0x18000b3c0  call    cs:__imp_LeaveCriticalSection
0x18000b3c6  xor     eax, eax
0x18000b3c8  jmp     loc_18000B466
0x18000b3cd  xor     esi, esi
0x18000b3cf  lea     r15, WPP_GLOBAL_Control
0x18000b3d6  xor     ebp, ebp
0x18000b3d8  call    cs:__imp_CreateTimerQueue
0x18000b3de  mov     r14, rbp
0x18000b3e1  add     r14, r14
0x18000b3e4  mov     [rdi+r14*8], rax
0x18000b3e8  test    rax, rax
0x18000b3eb  jnz     short loc_18000B41E
0x18000b3ed  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000b3f2  mov     esi, eax
0x18000b3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3fb  cmp     rcx, r15
0x18000b3fe  jz      short loc_18000B41E
0x18000b400  test    byte ptr [rcx+1Ch], 1
0x18000b404  jz      short loc_18000B41E
0x18000b406  mov     rcx, [rcx+10h]
0x18000b40a  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18000b411  mov     edx, 0Ah
0x18000b416  mov     r9d, eax
0x18000b419  call    WPP_SF_d
0x18000b41e  xor     eax, eax
0x18000b420  inc     rbp
0x18000b423  mov     [rdi+r14*8+8], ax
0x18000b429  cmp     rbp, 64h ; 'd'
0x18000b42d  jnz     short loc_18000B3D8
0x18000b42f  test    esi, esi
0x18000b431  jz      short loc_18000B45B
0x18000b433  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b43a  cmp     rcx, r15
0x18000b43d  jz      short loc_18000B45B
0x18000b43f  test    byte ptr [rcx+1Ch], 1
0x18000b443  jz      short loc_18000B45B
0x18000b445  mov     rcx, [rcx+10h]
0x18000b449  lea     edx, [rax+0Bh]
0x18000b44c  mov     r9d, esi
0x18000b44f  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18000b456  call    WPP_SF_d
0x18000b45b  mov     rcx, rbx; lpCriticalSection
0x18000b45e  call    cs:__imp_LeaveCriticalSection
0x18000b464  mov     eax, esi
0x18000b466  add     rsp, 28h
0x18000b46a  pop     r15
0x18000b46c  pop     r14
0x18000b46e  pop     rdi
0x18000b46f  pop     rsi
0x18000b470  pop     rbp
0x18000b471  pop     rbx
0x18000b472  retn
```

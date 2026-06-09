# CContentCache::Shutdown(void)

- ea: `0x18000a3c4`
- end: `0x18000a51f`
- name: `?Shutdown@CContentCache@@QEAAKXZ`
- size: `347`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000cde0`
- `0x180017254`

## callees

- `0x18000a3c4`
- `0x18001a9a8`
- `0x180026d70`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x18000a3f0`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a3f0`
- `KERNEL32!LeaveCriticalSection` at `0x18000a507`
- `KERNEL32!LeaveCriticalSection` at `0x18000a507`
- `KERNEL32!EnterCriticalSection` at `0x18000a438`
- `KERNEL32!EnterCriticalSection` at `0x18000a438`

## pseudocode

```c
__int64 __fastcall CContentCache::Shutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  signed __int32 i; // eax
  DWORD v3; // eax
  _QWORD *v4; // rdi
  _QWORD *v5; // rsi
  _QWORD *v6; // rax
  _QWORD *OwningThread; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rcx

  for ( i = _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1].SpinCount, 0);
        i;
        i = _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1].SpinCount, 0) )
  {
    v3 = WaitForSingleObjectEx(lpCriticalSection[2].DebugInfo, 0x1F4u, 1);
    if ( v3 && v3 != 258 && v3 != 192 )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(0x80000u, L"CChildCount::WaitForChildren failed; %u", v3);
      break;
    }
  }
  EnterCriticalSection(lpCriticalSection);
  lpCriticalSection[1].OwningThread = 0;
  v4 = *(_QWORD **)&lpCriticalSection[5].LockCount;
  while ( v4 )
  {
    v5 = v4;
    v6 = *(_QWORD **)&lpCriticalSection[5].LockCount;
    OwningThread = lpCriticalSection[5].OwningThread;
    if ( v6 == OwningThread )
    {
      lpCriticalSection[5].OwningThread = 0;
      *(_QWORD *)&lpCriticalSection[5].LockCount = 0;
LABEL_16:
      v4 = 0;
      goto LABEL_18;
    }
    if ( v4 != v6 )
    {
      if ( v4 != OwningThread )
      {
        v10 = v4 + 5;
        v4 = (_QWORD *)v4[5];
        *(_QWORD *)(v5[6] + 40LL) = v4;
        *(_QWORD *)(*v10 + 48LL) = v5[6];
        goto LABEL_18;
      }
      v9 = (_QWORD *)OwningThread[6];
      lpCriticalSection[5].OwningThread = v9;
      v9[5] = 0;
      goto LABEL_16;
    }
    v8 = v6[5];
    *(_QWORD *)&lpCriticalSection[5].LockCount = v8;
    *(_QWORD *)(v8 + 48) = 0;
    v4 = *(_QWORD **)&lpCriticalSection[5].LockCount;
LABEL_18:
    --HIDWORD(lpCriticalSection[5].LockSemaphore);
    v11 = v5[1];
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      v5[1] = 0;
    }
    operator delete(v5);
  }
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x18000a3c4  mov     [rsp+arg_0], rbx
0x18000a3c9  mov     [rsp+arg_8], rsi
0x18000a3ce  push    rdi
0x18000a3cf  sub     rsp, 20h
0x18000a3d3  mov     rbx, rcx
0x18000a3d6  xor     eax, eax
0x18000a3d8  lock xadd [rcx+48h], eax
0x18000a3dd  test    eax, eax
0x18000a3df  jz      short loc_18000A435
0x18000a3e1  mov     rcx, [rbx+50h]; hHandle
0x18000a3e5  mov     edx, 1F4h; dwMilliseconds
0x18000a3ea  mov     r8d, 1; bAlertable
0x18000a3f0  call    cs:__imp_WaitForSingleObjectEx
0x18000a3f6  test    eax, eax
0x18000a3f8  jz      short loc_18000A408
0x18000a3fa  cmp     eax, 102h
0x18000a3ff  jz      short loc_18000A408
0x18000a401  cmp     eax, 0C0h
0x18000a406  jnz     short loc_18000A411
0x18000a408  xor     eax, eax
0x18000a40a  lock xadd [rbx+48h], eax
0x18000a40f  jmp     short loc_18000A3DD
0x18000a411  mov     r9, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a418  test    r9, r9
0x18000a41b  jz      short loc_18000A435
0x18000a41d  mov     r8d, eax
0x18000a420  lea     rdx, aCchildcountWai; "CChildCount::WaitForChildren failed; %u"
0x18000a427  mov     rax, r9
0x18000a42a  mov     ecx, 80000h
0x18000a42f  call    cs:__guard_dispatch_icall_fptr
0x18000a435  mov     rcx, rbx; lpCriticalSection
0x18000a438  call    cs:__imp_EnterCriticalSection
0x18000a43e  and     qword ptr [rbx+38h], 0
0x18000a443  mov     rdi, [rbx+0D0h]
0x18000a44a  jmp     loc_18000A4FB
0x18000a44f  mov     rsi, rdi
0x18000a452  test    rdi, rdi
0x18000a455  jz      short loc_18000A4D3
0x18000a457  mov     rax, [rbx+0D0h]
0x18000a45e  mov     rcx, [rbx+0D8h]
0x18000a465  cmp     rax, rcx
0x18000a468  jnz     short loc_18000A47C
0x18000a46a  and     qword ptr [rbx+0D8h], 0
0x18000a472  and     qword ptr [rbx+0D0h], 0
0x18000a47a  jmp     short loc_18000A4AF
0x18000a47c  cmp     rdi, rax
0x18000a47f  jnz     short loc_18000A49A
0x18000a481  mov     rax, [rax+28h]
0x18000a485  mov     [rbx+0D0h], rax
0x18000a48c  and     qword ptr [rax+30h], 0
0x18000a491  mov     rdi, [rbx+0D0h]
0x18000a498  jmp     short loc_18000A4CD
0x18000a49a  cmp     rdi, rcx
0x18000a49d  jnz     short loc_18000A4B3
0x18000a49f  mov     rax, [rcx+30h]
0x18000a4a3  mov     [rbx+0D8h], rax
0x18000a4aa  and     qword ptr [rax+28h], 0
0x18000a4af  xor     edi, edi
0x18000a4b1  jmp     short loc_18000A4CD
0x18000a4b3  mov     rax, [rsi+30h]
0x18000a4b7  lea     rcx, [rdi+28h]
0x18000a4bb  mov     rdi, [rcx]
0x18000a4be  mov     [rax+28h], rdi
0x18000a4c2  mov     rcx, [rcx]
0x18000a4c5  mov     rax, [rsi+30h]
0x18000a4c9  mov     [rcx+30h], rax
0x18000a4cd  dec     dword ptr [rbx+0E4h]
0x18000a4d3  test    rsi, rsi
0x18000a4d6  jz      short loc_18000A4FB
0x18000a4d8  mov     rcx, [rsi+8]
0x18000a4dc  test    rcx, rcx
0x18000a4df  jz      short loc_18000A4F3
0x18000a4e1  mov     rax, [rcx]
0x18000a4e4  mov     rax, [rax+8]
0x18000a4e8  call    cs:__guard_dispatch_icall_fptr
0x18000a4ee  and     qword ptr [rsi+8], 0
0x18000a4f3  mov     rcx, rsi; void *
0x18000a4f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a4fb  test    rdi, rdi
0x18000a4fe  jnz     loc_18000A44F
0x18000a504  mov     rcx, rbx; lpCriticalSection
0x18000a507  call    cs:__imp_LeaveCriticalSection
0x18000a50d  mov     rbx, [rsp+28h+arg_0]
0x18000a512  xor     eax, eax
0x18000a514  mov     rsi, [rsp+28h+arg_8]
0x18000a519  add     rsp, 20h
0x18000a51d  pop     rdi
0x18000a51e  retn
```

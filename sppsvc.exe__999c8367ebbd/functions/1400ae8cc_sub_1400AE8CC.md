# sub_1400AE8CC

- ea: `0x1400ae8cc`
- end: `0x1400aea63`
- name: `sub_1400AE8CC`
- size: `407`
- prototype: `void()`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400ae668`
- `0x1400ae8c0`

## callees

- `0x140059870`
- `0x1400710d0`
- `0x140071c04`
- `0x14007fb70`
- `0x1400ad5a8`
- `0x1400ae8cc`
- `0x1400aea6c`
- `0x1400aead0`
- `0x1400d9e5c`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1400ae9a3`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400ae9a3`
- `KERNEL32!Sleep` at `0x1400ae8f7`
- `KERNEL32!Sleep` at `0x1400ae918`
- `KERNEL32!Sleep` at `0x1400ae8f7`
- `KERNEL32!Sleep` at `0x1400ae918`
- `KERNEL32!DeleteTimerQueue` at `0x1400ae9c0`
- `KERNEL32!DeleteTimerQueue` at `0x1400ae9c0`

## string_xrefs

- `0x1400ae967`: `msft:spp/notifications/common/systemhostservicestopping`
- `0x1400aea0e`: `msft:spp/notifications/host/service/stop`

## pseudocode

```c
void sub_1400AE8CC()
{
  int v0; // edx
  __int64 v1; // rdi
  void (__fastcall *v2)(__int64, const wchar_t *, _QWORD, _QWORD, _QWORD); // rbx
  __int64 v3; // rdi
  void (__fastcall *v4)(__int64, const wchar_t *, _QWORD, _QWORD, _QWORD); // rbx

  while ( 1 )
  {
    v0 = dword_1404470B8;
    if ( (dword_1404470B8 & 1) != 0 )
      break;
    if ( v0 == _InterlockedCompareExchange(&dword_1404470B8, dword_1404470B8 | 1, dword_1404470B8) )
    {
      if ( v0 > 1 )
      {
        while ( _InterlockedCompareExchange(&dword_1404470B8, 1, 1) != 1 )
          Sleep(0x64u);
      }
      if ( dword_14044606C && dword_140446070 >= 0 )
      {
        v1 = qword_140446280;
        v2 = *(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)qword_140446280 + 40LL);
        _guard_check_icall_fptr();
        v2(v1, L"msft:spp/notifications/common/systemhostservicestopping", 0, 0, 0);
      }
      sub_1400AEAD0();
      sub_1400AD5A8(&unk_140446300);
      sub_1400AEA6C();
      if ( Timer )
      {
        DeleteTimerQueueTimer(qword_1404470A0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        Timer = 0;
      }
      if ( qword_1404470A0 )
      {
        DeleteTimerQueue(qword_1404470A0);
        qword_1404470A0 = 0;
      }
      if ( dword_14044606C )
      {
        if ( dword_140446070 >= 0 )
        {
          v3 = qword_140446280;
          v4 = *(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)qword_140446280
                                                                                       + 40LL);
          _guard_check_icall_fptr();
          v4(v3, L"msft:spp/notifications/host/service/stop", 0, 0, 0);
        }
      }
      sub_1400710D0();
      sub_1400D9E5C(&qword_140446230);
      sub_140071C04((__int64)&dword_1404470B8);
      _InterlockedExchange(&dword_140446068, 1);
      sub_14007FB70(1u, dword_140446070, 0);
      return;
    }
    Sleep(0xAu);
  }
}

```

## disassembly

```asm
0x1400ae8cc  mov     [rsp+arg_0], rbx
0x1400ae8d1  mov     [rsp+arg_8], rsi
0x1400ae8d6  push    rdi
0x1400ae8d7  sub     rsp, 30h
0x1400ae8db  mov     esi, 1
0x1400ae8e0  jmp     short loc_1400AE8FD
0x1400ae8e2  mov     ecx, edx
0x1400ae8e4  mov     eax, edx
0x1400ae8e6  or      ecx, esi
0x1400ae8e8  lock cmpxchg cs:dword_1404470B8, ecx
0x1400ae8f0  jz      short loc_1400AE90D
0x1400ae8f2  mov     ecx, 0Ah; dwMilliseconds
0x1400ae8f7  call    cs:Sleep
0x1400ae8fd  mov     edx, cs:dword_1404470B8
0x1400ae903  test    sil, dl
0x1400ae906  jz      short loc_1400AE8E2
0x1400ae908  jmp     loc_1400AEA52
0x1400ae90d  cmp     edx, esi
0x1400ae90f  jle     short loc_1400AE92A
0x1400ae911  jmp     short loc_1400AE91E
0x1400ae913  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1400ae918  call    cs:Sleep
0x1400ae91e  mov     eax, esi
0x1400ae920  lock cmpxchg cs:dword_1404470B8, esi
0x1400ae928  jnz     short loc_1400AE913
0x1400ae92a  mov     eax, cs:dword_14044606C
0x1400ae930  test    eax, eax
0x1400ae932  jz      short loc_1400AE976
0x1400ae934  mov     eax, cs:dword_140446070
0x1400ae93a  test    eax, eax
0x1400ae93c  js      short loc_1400AE976
0x1400ae93e  mov     rdi, cs:qword_140446280
0x1400ae945  mov     rax, [rdi]
0x1400ae948  mov     rbx, [rax+28h]
0x1400ae94c  mov     rax, cs:__guard_check_icall_fptr
0x1400ae953  mov     rcx, rbx
0x1400ae956  call    rax ; _guard_check_icall_nop
0x1400ae958  mov     rax, rbx
0x1400ae95b  mov     [rsp+38h+var_18], 0
0x1400ae964  xor     r9d, r9d
0x1400ae967  lea     rdx, aMsftSppNotific_18; "msft:spp/notifications/common/systemhos"...
0x1400ae96e  xor     r8d, r8d
0x1400ae971  mov     rcx, rdi
0x1400ae974  call    rax
0x1400ae976  call    sub_1400AEAD0
0x1400ae97b  lea     rcx, unk_140446300
0x1400ae982  call    sub_1400AD5A8
0x1400ae987  call    sub_1400AEA6C
0x1400ae98c  mov     rdx, cs:Timer; Timer
0x1400ae993  test    rdx, rdx
0x1400ae996  jz      short loc_1400AE9B4
0x1400ae998  mov     rcx, cs:qword_1404470A0; TimerQueue
0x1400ae99f  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1400ae9a3  call    cs:DeleteTimerQueueTimer
0x1400ae9a9  mov     cs:Timer, 0
0x1400ae9b4  mov     rcx, cs:qword_1404470A0; TimerQueue
0x1400ae9bb  test    rcx, rcx
0x1400ae9be  jz      short loc_1400AE9D1
0x1400ae9c0  call    cs:DeleteTimerQueue
0x1400ae9c6  mov     cs:qword_1404470A0, 0
0x1400ae9d1  mov     eax, cs:dword_14044606C
0x1400ae9d7  test    eax, eax
0x1400ae9d9  jz      short loc_1400AEA1D
0x1400ae9db  mov     eax, cs:dword_140446070
0x1400ae9e1  test    eax, eax
0x1400ae9e3  js      short loc_1400AEA1D
0x1400ae9e5  mov     rdi, cs:qword_140446280
0x1400ae9ec  mov     rax, [rdi]
0x1400ae9ef  mov     rbx, [rax+28h]
0x1400ae9f3  mov     rax, cs:__guard_check_icall_fptr
0x1400ae9fa  mov     rcx, rbx
0x1400ae9fd  call    rax ; _guard_check_icall_nop
0x1400ae9ff  mov     rax, rbx
0x1400aea02  mov     [rsp+38h+var_18], 0
0x1400aea0b  xor     r9d, r9d
0x1400aea0e  lea     rdx, aMsftSppNotific_19; "msft:spp/notifications/host/service/sto"...
0x1400aea15  xor     r8d, r8d
0x1400aea18  mov     rcx, rdi
0x1400aea1b  call    rax
0x1400aea1d  call    sub_1400710D0
0x1400aea22  lea     rcx, qword_140446230
0x1400aea29  call    sub_1400D9E5C
0x1400aea2e  lea     rcx, dword_1404470B8
0x1400aea35  call    sub_140071C04
0x1400aea3a  mov     eax, esi
0x1400aea3c  xor     r8d, r8d
0x1400aea3f  xchg    eax, cs:dword_140446068
0x1400aea45  mov     edx, cs:dword_140446070
0x1400aea4b  mov     ecx, esi
0x1400aea4d  call    sub_14007FB70
0x1400aea52  mov     rbx, [rsp+38h+arg_0]
0x1400aea57  mov     rsi, [rsp+38h+arg_8]
0x1400aea5c  add     rsp, 30h
0x1400aea60  pop     rdi
0x1400aea61  retn
```

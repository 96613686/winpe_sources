# CLocalAccounts::_NotifyThreadProc(void *)

- ea: `0x180011840`
- end: `0x18001193f`
- name: `?_NotifyThreadProc@CLocalAccounts@@KAKPEAX@Z`
- size: `255`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000bcc0`
- `0x180011840`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001190e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001190e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001189b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001189b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001186c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001186c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180011884`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180011884`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011901`

## pseudocode

```c
__int64 __fastcall CLocalAccounts::_NotifyThreadProc(char *Parameter)
{
  int Error; // edi
  __int64 v3; // rcx
  DWORD v4; // ecx
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  Error = 0;
  while ( *((_DWORD *)Parameter + 11) )
  {
    if ( Error < 0 )
      break;
    if ( WaitForSingleObject(*((HANDLE *)Parameter + 13), 0xFFFFFFFF) )
    {
      Error = -2147467259;
    }
    else if ( ResetEvent(*((HANDLE *)Parameter + 13)) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 48));
      v3 = *((_QWORD *)Parameter + 11);
      v6 = 0;
      if ( v3 )
      {
        Error = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v3 + 40LL))(
                  v3,
                  *((unsigned int *)Parameter + 24),
                  &GUID_f0009734_e8de_48e5_b603_bfa5966a8f7c,
                  &v6);
        if ( Error >= 0 )
        {
          if ( v6 )
          {
            Error = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          }
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 48));
      v4 = *((_DWORD *)Parameter + 10);
      if ( v4 )
        Sleep(v4);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180011840  mov     [rsp+arg_8], rbx
0x180011845  mov     [rsp+arg_10], rsi
0x18001184a  push    rdi
0x18001184b  sub     rsp, 30h
0x18001184f  xor     edi, edi
0x180011851  mov     rbx, rcx
0x180011854  cmp     [rcx+2Ch], edi
0x180011857  jz      loc_18001191E
0x18001185d  test    edi, edi
0x18001185f  js      loc_18001191E
0x180011865  mov     rcx, [rbx+68h]; hHandle
0x180011869  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001186c  call    cs:__imp_WaitForSingleObject
0x180011872  test    eax, eax
0x180011874  jz      short loc_180011880
0x180011876  mov     edi, 80004005h
0x18001187b  jmp     loc_180011914
0x180011880  mov     rcx, [rbx+68h]; hEvent
0x180011884  call    cs:__imp_ResetEvent
0x18001188a  test    eax, eax
0x18001188c  jnz     short loc_180011897
0x18001188e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011893  mov     edi, eax
0x180011895  jmp     short loc_180011914
0x180011897  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001189b  call    cs:__imp_EnterCriticalSection
0x1800118a1  mov     rcx, [rbx+58h]
0x1800118a5  mov     [rsp+38h+arg_0], 0
0x1800118ae  test    rcx, rcx
0x1800118b1  jz      short loc_1800118FD
0x1800118b3  mov     rax, [rcx]
0x1800118b6  lea     r9, [rsp+38h+arg_0]
0x1800118bb  mov     edx, [rbx+60h]
0x1800118be  lea     r8, _GUID_f0009734_e8de_48e5_b603_bfa5966a8f7c
0x1800118c5  mov     rax, [rax+28h]
0x1800118c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118ce  mov     edi, eax
0x1800118d0  test    eax, eax
0x1800118d2  js      short loc_1800118FD
0x1800118d4  mov     rcx, [rsp+38h+arg_0]
0x1800118d9  test    rcx, rcx
0x1800118dc  jz      short loc_1800118FD
0x1800118de  mov     rax, [rcx]
0x1800118e1  mov     rax, [rax+18h]
0x1800118e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118ea  mov     rcx, [rsp+38h+arg_0]
0x1800118ef  mov     edi, eax
0x1800118f1  mov     rax, [rcx]
0x1800118f4  mov     rax, [rax+10h]
0x1800118f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118fd  lea     rcx, [rbx+30h]; lpCriticalSection
0x180011901  call    cs:__imp_LeaveCriticalSection
0x180011907  mov     ecx, [rbx+28h]; dwMilliseconds
0x18001190a  test    ecx, ecx
0x18001190c  jz      short loc_180011914
0x18001190e  call    cs:__imp_Sleep
0x180011914  cmp     dword ptr [rbx+2Ch], 0
0x180011918  jnz     loc_18001185D
0x18001191e  mov     rax, [rbx]
0x180011921  mov     rcx, rbx
0x180011924  mov     rax, [rax+10h]
0x180011928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001192d  mov     rbx, [rsp+38h+arg_8]
0x180011932  mov     eax, edi
0x180011934  mov     rsi, [rsp+38h+arg_10]
0x180011939  add     rsp, 30h
0x18001193d  pop     rdi
0x18001193e  retn
```

# CService::HandlerEx(ulong)

- ea: `0x180005c10`
- end: `0x180005d7c`
- name: `?HandlerEx@CService@@MEAAKK@Z`
- size: `364`
- prototype: `__int64 __fastcall(CService *this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180005c10`
- `0x18000df48`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005d12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005d12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d6a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005d61`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005d61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005d52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005d52`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005c69`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005cb0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005d36`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005c69`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005cb0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005d36`
- `ntdll!RtlNtStatusToDosError` at `0x180005d3e`
- `ntdll!RtlNtStatusToDosError` at `0x180005d3e`

## pseudocode

```c
__int64 __fastcall CService::HandlerEx(CService *this, int a2)
{
  unsigned int i; // eax
  __int64 v4; // r8
  ULONG v5; // esi
  SERVICE_STATUS_HANDLE v6; // rdi
  bool v7; // zf
  struct _SERVICE_STATUS *v8; // rdx
  const unsigned __int16 *v10; // rbx
  const unsigned __int16 *v11; // rax
  NTSTATUS v12; // ebx
  __int64 v13; // rax
  void *v14; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  void *SpinCount; // rcx

  for ( i = 0; i < 0xD; ++i )
  {
    v4 = (int)i;
    if ( a2 == LODWORD(qword_180011C20[v4]) )
    {
      v5 = HIDWORD(qword_180011C20[v4]);
      goto LABEL_6;
    }
  }
  v5 = 120;
LABEL_6:
  v6 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 3);
  if ( !v6 )
    return v5;
  v7 = a2 == 1;
  v8 = (struct _SERVICE_STATUS *)((char *)this + 32);
  if ( v7 )
  {
    *((_DWORD *)this + 9) = 3;
    SetServiceStatus(v6, v8);
    (*(void (__fastcall **)(CService *, _QWORD))(*(_QWORD *)this + 8LL))(this, 0);
    v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 16LL))(*((_QWORD *)this + 11));
    v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 8LL))(*((_QWORD *)this + 11));
    v12 = CServerUtilities::Stop(v11, v10);
    if ( v12 < 0 )
    {
      *((_DWORD *)this + 9) = 4;
      SetServiceStatus(v6, (LPSERVICE_STATUS)((char *)this + 32));
      v5 = RtlNtStatusToDosError(v12);
    }
    else
    {
      v13 = *((_QWORD *)this + 10);
      if ( v13 )
      {
        v14 = *(void **)(v13 + 64);
        if ( v14 )
        {
          if ( WaitForSingleObject(v14, 0xEA60u) == 258 )
            v5 = 1460;
        }
      }
    }
    v15 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10);
    if ( v15 )
    {
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      SpinCount = (void *)v15[1].SpinCount;
      if ( SpinCount )
        SetEvent(SpinCount);
      LeaveCriticalSection(v15);
    }
    return v5;
  }
  else
  {
    SetServiceStatus(v6, v8);
    return v5;
  }
}

```

## disassembly

```asm
0x180005c10  mov     [rsp+arg_10], rsi
0x180005c15  mov     [rsp+arg_18], rdi
0x180005c1a  push    r14
0x180005c1c  sub     rsp, 20h
0x180005c20  mov     r14, rcx
0x180005c23  lea     rsi, qword_180011C20
0x180005c2a  xor     eax, eax
0x180005c2c  nop     dword ptr [rax+00h]
0x180005c30  cmp     eax, 0Dh
0x180005c33  jnb     short loc_180005C9A
0x180005c35  movsxd  r8, eax
0x180005c38  lea     r8, ds:0[r8*8]
0x180005c40  cmp     edx, [r8+rsi]
0x180005c44  jz      short loc_180005C4A
0x180005c46  inc     eax
0x180005c48  jmp     short loc_180005C30
0x180005c4a  mov     esi, [r8+rsi+4]
0x180005c4f  mov     rdi, [rcx+18h]
0x180005c53  test    rdi, rdi
0x180005c56  jz      short loc_180005C87
0x180005c58  cmp     edx, 1
0x180005c5b  mov     [rsp+28h+arg_8], rbp
0x180005c60  lea     rdx, [rcx+20h]; lpServiceStatus
0x180005c64  jz      short loc_180005CA1
0x180005c66  mov     rcx, rdi; hServiceStatus
0x180005c69  call    cs:__imp_SetServiceStatus
0x180005c6f  mov     eax, esi
0x180005c71  mov     rbp, [rsp+28h+arg_8]
0x180005c76  mov     rsi, [rsp+28h+arg_10]
0x180005c7b  mov     rdi, [rsp+28h+arg_18]
0x180005c80  add     rsp, 20h
0x180005c84  pop     r14
0x180005c86  retn
0x180005c87  mov     rdi, [rsp+28h+arg_18]
0x180005c8c  mov     eax, esi
0x180005c8e  mov     rsi, [rsp+28h+arg_10]
0x180005c93  add     rsp, 20h
0x180005c97  pop     r14
0x180005c99  retn
0x180005c9a  mov     esi, 78h ; 'x'
0x180005c9f  jmp     short loc_180005C4F
0x180005ca1  mov     dword ptr [rcx+24h], 3
0x180005ca8  mov     rcx, rdi; hServiceStatus
0x180005cab  mov     [rsp+28h+arg_0], rbx
0x180005cb0  call    cs:__imp_SetServiceStatus
0x180005cb6  mov     rax, [r14]
0x180005cb9  xor     edx, edx
0x180005cbb  mov     rcx, r14
0x180005cbe  mov     rax, [rax+8]
0x180005cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc7  mov     rcx, [r14+58h]
0x180005ccb  mov     rax, [rcx]
0x180005cce  mov     rax, [rax+10h]
0x180005cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd7  mov     rcx, [r14+58h]
0x180005cdb  mov     rbx, rax
0x180005cde  mov     rdx, [rcx]
0x180005ce1  mov     rax, [rdx+8]
0x180005ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cea  mov     rdx, rbx; unsigned __int16 *
0x180005ced  mov     rcx, rax; unsigned __int16 *
0x180005cf0  call    ?Stop@CServerUtilities@@SAJPEBG0@Z; CServerUtilities::Stop(ushort const *,ushort const *)
0x180005cf5  mov     ebx, eax
0x180005cf7  test    eax, eax
0x180005cf9  js      short loc_180005D27
0x180005cfb  mov     rax, [r14+50h]
0x180005cff  test    rax, rax
0x180005d02  jz      short loc_180005D46
0x180005d04  mov     rcx, [rax+40h]; hHandle
0x180005d08  test    rcx, rcx
0x180005d0b  jz      short loc_180005D46
0x180005d0d  mov     edx, 0EA60h; dwMilliseconds
0x180005d12  call    cs:__imp_WaitForSingleObject
0x180005d18  cmp     eax, 102h
0x180005d1d  mov     ecx, 5B4h
0x180005d22  cmovz   esi, ecx
0x180005d25  jmp     short loc_180005D46
0x180005d27  lea     rdx, [r14+20h]; lpServiceStatus
0x180005d2b  mov     dword ptr [r14+24h], 4
0x180005d33  mov     rcx, rdi; hServiceStatus
0x180005d36  call    cs:__imp_SetServiceStatus
0x180005d3c  mov     ecx, ebx; Status
0x180005d3e  call    cs:__imp_RtlNtStatusToDosError
0x180005d44  mov     esi, eax
0x180005d46  mov     rbx, [r14+50h]
0x180005d4a  test    rbx, rbx
0x180005d4d  jz      short loc_180005D70
0x180005d4f  mov     rcx, rbx; lpCriticalSection
0x180005d52  call    cs:__imp_EnterCriticalSection
0x180005d58  mov     rcx, [rbx+48h]; hEvent
0x180005d5c  test    rcx, rcx
0x180005d5f  jz      short loc_180005D67
0x180005d61  call    cs:__imp_SetEvent
0x180005d67  mov     rcx, rbx; lpCriticalSection
0x180005d6a  call    cs:__imp_LeaveCriticalSection
0x180005d70  mov     rbx, [rsp+28h+arg_0]
0x180005d75  mov     eax, esi
0x180005d77  jmp     loc_180005C71
```

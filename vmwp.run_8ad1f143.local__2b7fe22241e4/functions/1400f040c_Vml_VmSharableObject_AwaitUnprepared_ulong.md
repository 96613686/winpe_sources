# Vml::VmSharableObject::AwaitUnprepared(ulong)

- ea: `0x1400f040c`
- end: `0x1400f0538`
- name: `?AwaitUnprepared@VmSharableObject@Vml@@QEBA_NK@Z`
- size: `300`
- prototype: `bool __fastcall(Vml::VmSharableObject *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400f01d8`
- `0x14028aa30`

## callees

- `0x14008c984`
- `0x14009fa0c`
- `0x1400f040c`
- `0x14013acac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400f04e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400f04e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400f0461`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400f0461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f04ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f04ac`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400f048c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400f048c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400f0433`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400f0433`

## string_xrefs

- `0x1400f04bc`: `onecore\vm\common\vml\VmSharableObject.h`
- `0x1400f04ff`: `onecore\vm\common\vml\VmSharableObject.h`
- `0x1400f0526`: `onecore\vm\common\vml\VmSharableObject.h`

## pseudocode

```c
char __fastcall Vml::VmSharableObject::AwaitUnprepared(Vml::VmSharableObject *this, int a2, __int64 a3, const char *a4)
{
  char v5; // di
  void *v6; // rbx
  HANDLE EventW; // rax
  const char *v8; // r9
  DWORD TimeRemaining; // eax
  DWORD v10; // eax
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v14; // [rsp+50h] [rbp+8h] BYREF
  DWORD TickCount; // [rsp+54h] [rbp+Ch]

  if ( (*((_DWORD *)this + 4) & 0x7000000u) < 0x3000000 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12A9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSharableObject.h",
      a4);
  v5 = 0;
  v14 = a2;
  TickCount = GetTickCount();
LABEL_3:
  v6 = (void *)*((_QWORD *)this + 8);
  while ( 1 )
  {
    if ( v6 == (void *)-1LL )
      return 1;
    if ( v6 )
      goto LABEL_13;
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      if ( (unsigned int)Vml::VmTimeoutTimer::IsExpired((Vml::VmTimeoutTimer *)&v14) )
        return v5;
      Sleep(0x12Cu);
      goto LABEL_3;
    }
    v6 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)this + 8, (signed __int64)EventW, 0);
    if ( !v6 )
      break;
    if ( !CloseHandle(EventW) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x12DA,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSharableObject.h",
        v8);
  }
  v6 = EventW;
LABEL_13:
  TimeRemaining = Vml::VmTimeoutTimer::GetTimeRemaining((Vml::VmTimeoutTimer *)&v14);
  v10 = WaitForSingleObject(v6, TimeRemaining);
  if ( !v10 )
    return 1;
  if ( v10 != 258 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12FA,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSharableObject.h",
      v11);
  return v5;
}

```

## disassembly

```asm
0x1400f040c  push    rbx
0x1400f040e  push    rbp
0x1400f040f  push    rsi
0x1400f0410  push    rdi
0x1400f0411  sub     rsp, 28h
0x1400f0415  mov     rax, [rcx+10h]
0x1400f0419  mov     rsi, rcx
0x1400f041c  and     eax, 7000000h
0x1400f0421  cmp     eax, 3000000h
0x1400f0426  jb      loc_1400F0521
0x1400f042c  xor     dil, dil
0x1400f042f  mov     [rsp+48h+arg_0], edx
0x1400f0433  call    cs:__imp_GetTickCount
0x1400f043a  nop     dword ptr [rax+rax+00h]
0x1400f043f  mov     [rsp+48h+arg_4], eax
0x1400f0443  mov     rbx, [rsi+40h]
0x1400f0447  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400f044b  jz      loc_1400F0511
0x1400f0451  test    rbx, rbx
0x1400f0454  jnz     short loc_1400F04D4
0x1400f0456  xor     r9d, r9d; lpName
0x1400f0459  lea     edx, [rbx+1]; bManualReset
0x1400f045c  xor     r8d, r8d; bInitialState
0x1400f045f  xor     ecx, ecx; lpEventAttributes
0x1400f0461  call    cs:__imp_CreateEventW
0x1400f0468  nop     dword ptr [rax+rax+00h]
0x1400f046d  mov     rcx, rax; hObject
0x1400f0470  test    rax, rax
0x1400f0473  jnz     short loc_1400F049A
0x1400f0475  lea     rcx, [rsp+48h+arg_0]; this
0x1400f047a  call    ?IsExpired@VmTimeoutTimer@Vml@@QEBAHXZ; Vml::VmTimeoutTimer::IsExpired(void)
0x1400f047f  test    eax, eax
0x1400f0481  jnz     loc_1400F0514
0x1400f0487  mov     ecx, 12Ch; dwMilliseconds
0x1400f048c  call    cs:__imp_Sleep
0x1400f0493  nop     dword ptr [rax+rax+00h]
0x1400f0498  jmp     short loc_1400F0443
0x1400f049a  xor     eax, eax
0x1400f049c  lock cmpxchg [rsi+40h], rcx
0x1400f04a2  mov     rbx, rax
0x1400f04a5  jz      short loc_1400F04D1
0x1400f04a7  mov     rbp, [rsp+48h]
0x1400f04ac  call    cs:__imp_CloseHandle
0x1400f04b3  nop     dword ptr [rax+rax+00h]
0x1400f04b8  test    eax, eax
0x1400f04ba  jnz     short loc_1400F0447
0x1400f04bc  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400f04c3  mov     edx, 12DAh; void *
0x1400f04c8  mov     rcx, rbp; this
0x1400f04cb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400f04d1  mov     rbx, rcx
0x1400f04d4  lea     rcx, [rsp+48h+arg_0]; this
0x1400f04d9  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x1400f04de  mov     edx, eax; dwMilliseconds
0x1400f04e0  mov     rcx, rbx; hHandle
0x1400f04e3  call    cs:__imp_WaitForSingleObject
0x1400f04ea  nop     dword ptr [rax+rax+00h]
0x1400f04ef  test    eax, eax
0x1400f04f1  jz      short loc_1400F0511
0x1400f04f3  cmp     eax, 102h
0x1400f04f8  jz      short loc_1400F0514
0x1400f04fa  mov     rcx, [rsp+48h]; this
0x1400f04ff  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400f0506  mov     edx, 12FAh; void *
0x1400f050b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400f0511  mov     dil, 1
0x1400f0514  mov     al, dil
0x1400f0517  add     rsp, 28h
0x1400f051b  pop     rdi
0x1400f051c  pop     rsi
0x1400f051d  pop     rbp
0x1400f051e  pop     rbx
0x1400f051f  retn
0x1400f0521  mov     rcx, [rsp+48h]; this
0x1400f0526  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400f052d  mov     edx, 12A9h; void *
0x1400f0532  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

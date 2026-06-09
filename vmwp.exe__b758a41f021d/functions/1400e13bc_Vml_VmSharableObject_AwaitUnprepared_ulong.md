# Vml::VmSharableObject::AwaitUnprepared(ulong)

- ea: `0x1400e13bc`
- end: `0x1400e14e8`
- name: `?AwaitUnprepared@VmSharableObject@Vml@@QEBA_NK@Z`
- size: `300`
- prototype: `bool __fastcall(Vml::VmSharableObject *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400e1188`
- `0x140293390`

## callees

- `0x140064f4c`
- `0x1400a06d0`
- `0x1400e13bc`
- `0x140126d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400e1411`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400e1411`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400e1493`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400e1493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e145c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e145c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400e143c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400e143c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400e13e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400e13e3`

## string_xrefs

- `0x1400e146c`: `onecore\vm\common\vml\VmSharableObject.h`
- `0x1400e14af`: `onecore\vm\common\vml\VmSharableObject.h`
- `0x1400e14d6`: `onecore\vm\common\vml\VmSharableObject.h`

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
0x1400e13bc  push    rbx
0x1400e13be  push    rbp
0x1400e13bf  push    rsi
0x1400e13c0  push    rdi
0x1400e13c1  sub     rsp, 28h
0x1400e13c5  mov     rax, [rcx+10h]
0x1400e13c9  mov     rsi, rcx
0x1400e13cc  and     eax, 7000000h
0x1400e13d1  cmp     eax, 3000000h
0x1400e13d6  jb      loc_1400E14D1
0x1400e13dc  xor     dil, dil
0x1400e13df  mov     [rsp+48h+arg_0], edx
0x1400e13e3  call    cs:__imp_GetTickCount
0x1400e13ea  nop     dword ptr [rax+rax+00h]
0x1400e13ef  mov     [rsp+48h+arg_4], eax
0x1400e13f3  mov     rbx, [rsi+40h]
0x1400e13f7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400e13fb  jz      loc_1400E14C1
0x1400e1401  test    rbx, rbx
0x1400e1404  jnz     short loc_1400E1484
0x1400e1406  xor     r9d, r9d; lpName
0x1400e1409  lea     edx, [rbx+1]; bManualReset
0x1400e140c  xor     r8d, r8d; bInitialState
0x1400e140f  xor     ecx, ecx; lpEventAttributes
0x1400e1411  call    cs:__imp_CreateEventW
0x1400e1418  nop     dword ptr [rax+rax+00h]
0x1400e141d  mov     rcx, rax; hObject
0x1400e1420  test    rax, rax
0x1400e1423  jnz     short loc_1400E144A
0x1400e1425  lea     rcx, [rsp+48h+arg_0]; this
0x1400e142a  call    ?IsExpired@VmTimeoutTimer@Vml@@QEBAHXZ; Vml::VmTimeoutTimer::IsExpired(void)
0x1400e142f  test    eax, eax
0x1400e1431  jnz     loc_1400E14C4
0x1400e1437  mov     ecx, 12Ch; dwMilliseconds
0x1400e143c  call    cs:__imp_Sleep
0x1400e1443  nop     dword ptr [rax+rax+00h]
0x1400e1448  jmp     short loc_1400E13F3
0x1400e144a  xor     eax, eax
0x1400e144c  lock cmpxchg [rsi+40h], rcx
0x1400e1452  mov     rbx, rax
0x1400e1455  jz      short loc_1400E1481
0x1400e1457  mov     rbp, [rsp+48h]
0x1400e145c  call    cs:__imp_CloseHandle
0x1400e1463  nop     dword ptr [rax+rax+00h]
0x1400e1468  test    eax, eax
0x1400e146a  jnz     short loc_1400E13F7
0x1400e146c  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400e1473  mov     edx, 12DAh; void *
0x1400e1478  mov     rcx, rbp; this
0x1400e147b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400e1481  mov     rbx, rcx
0x1400e1484  lea     rcx, [rsp+48h+arg_0]; this
0x1400e1489  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x1400e148e  mov     edx, eax; dwMilliseconds
0x1400e1490  mov     rcx, rbx; hHandle
0x1400e1493  call    cs:__imp_WaitForSingleObject
0x1400e149a  nop     dword ptr [rax+rax+00h]
0x1400e149f  test    eax, eax
0x1400e14a1  jz      short loc_1400E14C1
0x1400e14a3  cmp     eax, 102h
0x1400e14a8  jz      short loc_1400E14C4
0x1400e14aa  mov     rcx, [rsp+48h]; this
0x1400e14af  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400e14b6  mov     edx, 12FAh; void *
0x1400e14bb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400e14c1  mov     dil, 1
0x1400e14c4  mov     al, dil
0x1400e14c7  add     rsp, 28h
0x1400e14cb  pop     rdi
0x1400e14cc  pop     rsi
0x1400e14cd  pop     rbp
0x1400e14ce  pop     rbx
0x1400e14cf  retn
0x1400e14d1  mov     rcx, [rsp+48h]; this
0x1400e14d6  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400e14dd  mov     edx, 12A9h; void *
0x1400e14e2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

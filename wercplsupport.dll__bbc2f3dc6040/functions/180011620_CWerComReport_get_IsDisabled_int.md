# CWerComReport::get_IsDisabled(int *)

- ea: `0x180011620`
- end: `0x1800116d6`
- name: `?get_IsDisabled@CWerComReport@@UEAAJPEAH@Z`
- size: `182`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006c9c`
- `0x180007d20`
- `0x180007fe0`
- `0x18000e35c`
- `0x180011620`

## import_xrefs

- `wer!WerpIsDisabled` at `0x1800116a3`
- `wer!WerpIsDisabled` at `0x1800116a3`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_IsDisabled(CWerComReport *this, int *a2)
{
  int WerApiLock; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF
  __int64 v7; // [rsp+48h] [rbp+20h] BYREF

  v6 = 2;
  WerApiLock = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( WerApiLock >= 0 )
  {
    v7 = 0;
    WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v7, (CWerComReport *)((char *)this - 24));
    if ( WerApiLock >= 0 )
    {
      WerApiLock = WerpIsDisabled(*((_QWORD *)this + 1), a2);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)WerApiLock);
    }
    if ( v7 )
      _InterlockedExchange((volatile __int32 *)(v7 + 48), 0);
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)WerApiLock;
}

```

## disassembly

```asm
0x180011620  mov     rax, rsp
0x180011623  mov     [rax+8], rbx
0x180011627  mov     [rax+10h], rsi
0x18001162b  push    rdi
0x18001162c  sub     rsp, 20h
0x180011630  mov     rdi, rcx
0x180011633  mov     dword ptr [rax+18h], 2
0x18001163a  lea     rcx, [rax+18h]; this
0x18001163e  mov     rsi, rdx
0x180011641  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011646  mov     ebx, eax
0x180011648  test    eax, eax
0x18001164a  js      short loc_1800116BA
0x18001164c  lea     rdx, [rdi-18h]; struct CWerComReport *
0x180011650  mov     [rsp+28h+arg_18], 0
0x180011659  lea     rcx, [rsp+28h+arg_18]; this
0x18001165e  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x180011663  mov     ebx, eax
0x180011665  test    eax, eax
0x180011667  jns     short loc_18001169C
0x180011669  mov     rcx, cs:WPP_GLOBAL_Control
0x180011670  lea     rax, WPP_GLOBAL_Control
0x180011677  cmp     rcx, rax
0x18001167a  jz      short loc_1800116AB
0x18001167c  test    byte ptr [rcx+1Ch], 1
0x180011680  jz      short loc_1800116AB
0x180011682  mov     rcx, [rcx+10h]
0x180011686  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18001168d  mov     edx, 1Bh
0x180011692  mov     r9d, ebx
0x180011695  call    WPP_SF_d
0x18001169a  jmp     short loc_1800116AB
0x18001169c  mov     rcx, [rdi+8]
0x1800116a0  mov     rdx, rsi
0x1800116a3  call    cs:__imp_WerpIsDisabled
0x1800116a9  mov     ebx, eax
0x1800116ab  mov     rax, [rsp+28h+arg_18]
0x1800116b0  test    rax, rax
0x1800116b3  jz      short loc_1800116BA
0x1800116b5  xor     ecx, ecx
0x1800116b7  xchg    ecx, [rax+30h]
0x1800116ba  lea     rcx, [rsp+28h+arg_10]; this
0x1800116bf  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x1800116c4  mov     rsi, [rsp+28h+arg_8]
0x1800116c9  mov     eax, ebx
0x1800116cb  mov     rbx, [rsp+28h+arg_0]
0x1800116d0  add     rsp, 20h
0x1800116d4  pop     rdi
0x1800116d5  retn
```

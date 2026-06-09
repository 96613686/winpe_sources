# CWerComReport::get_NumLoadedModules(ulong *)

- ea: `0x180011860`
- end: `0x180011916`
- name: `?get_NumLoadedModules@CWerComReport@@UEAAJPEAK@Z`
- size: `182`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006c9c`
- `0x180007d20`
- `0x180007fe0`
- `0x18000e35c`
- `0x180011860`

## import_xrefs

- `wer!WerpGetNumLoadedModules` at `0x1800118e3`
- `wer!WerpGetNumLoadedModules` at `0x1800118e3`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_NumLoadedModules(CWerComReport *this, unsigned int *a2)
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
      WerApiLock = WerpGetNumLoadedModules(*((_QWORD *)this + 1), a2);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
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
0x180011860  mov     rax, rsp
0x180011863  mov     [rax+8], rbx
0x180011867  mov     [rax+10h], rsi
0x18001186b  push    rdi
0x18001186c  sub     rsp, 20h
0x180011870  mov     rdi, rcx
0x180011873  mov     dword ptr [rax+18h], 2
0x18001187a  lea     rcx, [rax+18h]; this
0x18001187e  mov     rsi, rdx
0x180011881  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011886  mov     ebx, eax
0x180011888  test    eax, eax
0x18001188a  js      short loc_1800118FA
0x18001188c  lea     rdx, [rdi-18h]; struct CWerComReport *
0x180011890  mov     [rsp+28h+arg_18], 0
0x180011899  lea     rcx, [rsp+28h+arg_18]; this
0x18001189e  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x1800118a3  mov     ebx, eax
0x1800118a5  test    eax, eax
0x1800118a7  jns     short loc_1800118DC
0x1800118a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118b0  lea     rax, WPP_GLOBAL_Control
0x1800118b7  cmp     rcx, rax
0x1800118ba  jz      short loc_1800118EB
0x1800118bc  test    byte ptr [rcx+1Ch], 1
0x1800118c0  jz      short loc_1800118EB
0x1800118c2  mov     rcx, [rcx+10h]
0x1800118c6  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800118cd  mov     edx, 39h ; '9'
0x1800118d2  mov     r9d, ebx
0x1800118d5  call    WPP_SF_d
0x1800118da  jmp     short loc_1800118EB
0x1800118dc  mov     rcx, [rdi+8]
0x1800118e0  mov     rdx, rsi
0x1800118e3  call    cs:__imp_WerpGetNumLoadedModules
0x1800118e9  mov     ebx, eax
0x1800118eb  mov     rax, [rsp+28h+arg_18]
0x1800118f0  test    rax, rax
0x1800118f3  jz      short loc_1800118FA
0x1800118f5  xor     ecx, ecx
0x1800118f7  xchg    ecx, [rax+30h]
0x1800118fa  lea     rcx, [rsp+28h+arg_10]; this
0x1800118ff  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011904  mov     rsi, [rsp+28h+arg_8]
0x180011909  mov     eax, ebx
0x18001190b  mov     rbx, [rsp+28h+arg_0]
0x180011910  add     rsp, 20h
0x180011914  pop     rdi
0x180011915  retn
```

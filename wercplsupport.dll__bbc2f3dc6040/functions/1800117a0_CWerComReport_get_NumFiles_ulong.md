# CWerComReport::get_NumFiles(ulong *)

- ea: `0x1800117a0`
- end: `0x180011856`
- name: `?get_NumFiles@CWerComReport@@UEAAJPEAK@Z`
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
- `0x1800117a0`

## import_xrefs

- `wer!WerpGetNumFiles` at `0x180011823`
- `wer!WerpGetNumFiles` at `0x180011823`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_NumFiles(CWerComReport *this, unsigned int *a2)
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
      WerApiLock = WerpGetNumFiles(*((_QWORD *)this + 1), a2);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
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
0x1800117a0  mov     rax, rsp
0x1800117a3  mov     [rax+8], rbx
0x1800117a7  mov     [rax+10h], rsi
0x1800117ab  push    rdi
0x1800117ac  sub     rsp, 20h
0x1800117b0  mov     rdi, rcx
0x1800117b3  mov     dword ptr [rax+18h], 2
0x1800117ba  lea     rcx, [rax+18h]; this
0x1800117be  mov     rsi, rdx
0x1800117c1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x1800117c6  mov     ebx, eax
0x1800117c8  test    eax, eax
0x1800117ca  js      short loc_18001183A
0x1800117cc  lea     rdx, [rdi-18h]; struct CWerComReport *
0x1800117d0  mov     [rsp+28h+arg_18], 0
0x1800117d9  lea     rcx, [rsp+28h+arg_18]; this
0x1800117de  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x1800117e3  mov     ebx, eax
0x1800117e5  test    eax, eax
0x1800117e7  jns     short loc_18001181C
0x1800117e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117f0  lea     rax, WPP_GLOBAL_Control
0x1800117f7  cmp     rcx, rax
0x1800117fa  jz      short loc_18001182B
0x1800117fc  test    byte ptr [rcx+1Ch], 1
0x180011800  jz      short loc_18001182B
0x180011802  mov     rcx, [rcx+10h]
0x180011806  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18001180d  mov     edx, 38h ; '8'
0x180011812  mov     r9d, ebx
0x180011815  call    WPP_SF_d
0x18001181a  jmp     short loc_18001182B
0x18001181c  mov     rcx, [rdi+8]
0x180011820  mov     rdx, rsi
0x180011823  call    cs:__imp_WerpGetNumFiles
0x180011829  mov     ebx, eax
0x18001182b  mov     rax, [rsp+28h+arg_18]
0x180011830  test    rax, rax
0x180011833  jz      short loc_18001183A
0x180011835  xor     ecx, ecx
0x180011837  xchg    ecx, [rax+30h]
0x18001183a  lea     rcx, [rsp+28h+arg_10]; this
0x18001183f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011844  mov     rsi, [rsp+28h+arg_8]
0x180011849  mov     eax, ebx
0x18001184b  mov     rbx, [rsp+28h+arg_0]
0x180011850  add     rsp, 20h
0x180011854  pop     rdi
0x180011855  retn
```

# Reachability_PollPeer(AutoPtr<NtpPeer>,bool *)

- ea: `0x180014994`
- end: `0x180014b1d`
- name: `?Reachability_PollPeer@@YAJV?$AutoPtr@UNtpPeer@@@@PEA_N@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003163c`

## callees

- `0x1800144f0`
- `0x180014994`
- `0x1800164b0`
- `0x180018138`
- `0x180019828`
- `0x18001d9a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800149cd`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180014ad1`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800149cd`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180014ad1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014afb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014afb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149e1`

## string_xrefs

- `0x180014a50`: `Reachability: Attempting to contact peer %s.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Reachability_PollPeer(volatile signed __int32 **a1, char *a2)
{
  __int64 v3; // r14
  LPCRITICAL_SECTION *v4; // rsi
  int v5; // eax
  LPCRITICAL_SECTION v6; // r14
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  volatile signed __int32 **v8; // rax
  __int64 v9; // r8
  char v11; // [rsp+20h] [rbp-78h]
  __int64 v12; // [rsp+28h] [rbp-70h]
  volatile signed __int32 *v14; // [rsp+B8h] [rbp+20h] BYREF

  v11 = 0;
  v3 = *((_QWORD *)*a1 + 1);
  v4 = (LPCRITICAL_SECTION *)(v3 + 120);
  v12 = _set_se_translator(SeTransFunc);
  EnterCriticalSection(*(LPCRITICAL_SECTION *)(v3 + 120));
  v5 = *(_DWORD *)(v3 + 128);
  if ( v5 == 3 )
  {
    v11 = 1;
  }
  else if ( v5 != 2 )
  {
    if ( !v5 )
    {
      *(_DWORD *)(v3 + 128) = 1;
      *(_BYTE *)(*((_QWORD *)*a1 + 1) + 288LL) = 0;
      if ( (unsigned __int8)FileLogAllowEntry(116) )
        FileLogAdd(L"Reachability: Attempting to contact peer %s.\n", *((_QWORD *)*a1 + 1) + 290LL);
    }
    v6 = *v4;
    if ( *v4 )
    {
      v14 = *(volatile signed __int32 **)&v6[1].LockCount;
      DebugInfo = v6[1].DebugInfo;
      if ( DebugInfo != (PRTL_CRITICAL_SECTION_DEBUG)v14 )
      {
        v8 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v14, (volatile signed __int32 **)&DebugInfo->ProcessLocksList);
        SetPeerTimeRemaining(v8, v9);
        v6[1].DebugInfo = *(PRTL_CRITICAL_SECTION_DEBUG *)v6[1].DebugInfo;
      }
    }
    _set_se_translator(v12);
  }
  *a2 = v11;
  LeaveCriticalSection(*v4);
  AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(a1);
  return 0;
}

```

## disassembly

```asm
0x180014994  mov     rax, rsp
0x180014997  mov     [rax+10h], rdx
0x18001499b  mov     [rax+8], rcx
0x18001499f  push    rbx
0x1800149a0  push    rsi
0x1800149a1  push    rdi
0x1800149a2  push    r14
0x1800149a4  sub     rsp, 78h
0x1800149a8  mov     rdi, rcx
0x1800149ab  mov     byte ptr [rax-77h], 0
0x1800149af  mov     byte ptr [rax-78h], 0
0x1800149b3  mov     rax, [rcx]
0x1800149b6  mov     r14, [rax+8]
0x1800149ba  lea     rsi, [r14+78h]
0x1800149be  mov     [rsp+98h+arg_10], rsi
0x1800149c6  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800149cd  call    cs:__imp__set_se_translator
0x1800149d4  nop     dword ptr [rax+rax+00h]
0x1800149d9  mov     [rsp+98h+var_70], rax
0x1800149de  mov     rcx, [rsi]; lpCriticalSection
0x1800149e1  call    cs:__imp_EnterCriticalSection
0x1800149e8  nop     dword ptr [rax+rax+00h]
0x1800149ed  xor     ebx, ebx
0x1800149ef  mov     [rsp+98h+var_74], ebx
0x1800149f3  mov     [rsp+98h+var_77], 1
0x1800149f8  mov     eax, [r14+80h]
0x1800149ff  cmp     eax, 3
0x180014a02  jnz     short loc_180014A0E
0x180014a04  mov     [rsp+98h+var_78], 1
0x180014a09  jmp     loc_180014AE1
0x180014a0e  cmp     eax, 2
0x180014a11  jnz     short loc_180014A18
0x180014a13  jmp     loc_180014AE1
0x180014a18  test    eax, eax
0x180014a1a  jnz     short loc_180014A5C
0x180014a1c  mov     dword ptr [r14+80h], 1
0x180014a27  mov     rax, [rdi]
0x180014a2a  mov     rcx, [rax+8]
0x180014a2e  mov     [rcx+120h], bl
0x180014a34  mov     ecx, 74h ; 't'
0x180014a39  call    FileLogAllowEntry
0x180014a3e  test    al, al
0x180014a40  jz      short loc_180014A5C
0x180014a42  mov     rax, [rdi]
0x180014a45  mov     rdx, [rax+8]
0x180014a49  add     rdx, 122h
0x180014a50  lea     rcx, aReachabilityAt; "Reachability: Attempting to contact pee"...
0x180014a57  call    FileLogAdd
0x180014a5c  mov     r14, [rsi]
0x180014a5f  test    r14, r14
0x180014a62  jz      short loc_180014AB2
0x180014a64  mov     rax, [r14+30h]
0x180014a68  mov     [rsp+98h+arg_18], rax
0x180014a70  mov     rdx, [r14+28h]
0x180014a74  cmp     rdx, rax
0x180014a77  jz      short loc_180014AB2
0x180014a79  mov     r8, [r14+40h]
0x180014a7d  lea     rax, [rsp+98h+arg_18]
0x180014a85  mov     [rsp+98h+var_68], rax
0x180014a8a  add     rdx, 10h
0x180014a8e  lea     rcx, [rsp+98h+arg_18]
0x180014a96  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@AEBV0@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(AutoPtr<NtpPeer> const &)
0x180014a9b  nop
0x180014a9c  mov     rdx, r8
0x180014a9f  mov     rcx, rax
0x180014aa2  call    ?SetPeerTimeRemaining@@YAXV?$AutoPtr@UNtpPeer@@@@UNtTimePeriod@@@Z; SetPeerTimeRemaining(AutoPtr<NtpPeer>,NtTimePeriod)
0x180014aa7  mov     rax, [r14+28h]
0x180014aab  mov     rcx, [rax]
0x180014aae  mov     [r14+28h], rcx
0x180014ab2  jmp     short loc_180014ACC
0x180014ab4  jmp     short loc_180014AB8
0x180014ab6  jmp     short $+2
0x180014ab8  mov     rdi, [rsp+98h+arg_0]
0x180014ac0  mov     ebx, [rsp+98h+var_74]
0x180014ac4  mov     rsi, [rsp+98h+arg_10]
0x180014acc  mov     rcx, [rsp+98h+var_70]
0x180014ad1  call    cs:__imp__set_se_translator
0x180014ad8  nop     dword ptr [rax+rax+00h]
0x180014add  test    ebx, ebx
0x180014adf  js      short loc_180014AF1
0x180014ae1  mov     cl, [rsp+98h+var_78]
0x180014ae5  mov     rax, [rsp+98h+arg_8]
0x180014aed  mov     [rax], cl
0x180014aef  xor     ebx, ebx
0x180014af1  cmp     [rsp+98h+var_77], 0
0x180014af6  jz      short loc_180014B08
0x180014af8  mov     rcx, [rsi]; lpCriticalSection
0x180014afb  call    cs:__imp_LeaveCriticalSection
0x180014b02  nop     dword ptr [rax+rax+00h]
0x180014b07  nop
0x180014b08  mov     rcx, rdi
0x180014b0b  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x180014b10  mov     eax, ebx
0x180014b12  add     rsp, 78h
0x180014b16  pop     r14
0x180014b18  pop     rdi
0x180014b19  pop     rsi
0x180014b1a  pop     rbx
0x180014b1b  retn
```

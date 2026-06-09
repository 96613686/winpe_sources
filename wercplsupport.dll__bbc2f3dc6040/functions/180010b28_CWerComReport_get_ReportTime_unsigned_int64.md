# CWerComReport::_get_ReportTime(unsigned __int64 *)

- ea: `0x180010b28`
- end: `0x180010c02`
- name: `?_get_ReportTime@CWerComReport@@QEAAJPEA_K@Z`
- size: `218`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011980`

## callees

- `0x180006c9c`
- `0x18000e35c`
- `0x180010b28`

## import_xrefs

- `wer!WerpGetReportTime` at `0x180010bad`
- `wer!WerpGetReportTime` at `0x180010bad`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_ReportTime(CWerComReport *this, unsigned __int64 *a2)
{
  int WerApiLock; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v8, this);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 39;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  WerApiLock = WerpGetReportTime(*((_QWORD *)this + 4), &v9);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 40;
      goto LABEL_5;
    }
LABEL_6:
    if ( v8 )
      _InterlockedExchange((volatile __int32 *)(v8 + 48), 0);
    return (unsigned int)WerApiLock;
  }
  *a2 = v9;
  if ( v8 )
    _InterlockedExchange((volatile __int32 *)(v8 + 48), 0);
  return 0;
}

```

## disassembly

```asm
0x180010b28  mov     rax, rsp
0x180010b2b  mov     [rax+8], rbx
0x180010b2f  mov     [rax+10h], rsi
0x180010b33  push    rdi
0x180010b34  sub     rsp, 20h
0x180010b38  mov     rsi, rdx
0x180010b3b  mov     qword ptr [rax+20h], 0
0x180010b43  mov     rdx, rcx; struct CWerComReport *
0x180010b46  mov     qword ptr [rax+18h], 0
0x180010b4e  mov     rdi, rcx
0x180010b51  lea     rcx, [rax+18h]; this
0x180010b55  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x180010b5a  mov     ebx, eax
0x180010b5c  test    eax, eax
0x180010b5e  jns     short loc_180010BA4
0x180010b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b67  lea     rdx, WPP_GLOBAL_Control
0x180010b6e  cmp     rcx, rdx
0x180010b71  jz      short loc_180010B91
0x180010b73  test    byte ptr [rcx+1Ch], 1
0x180010b77  jz      short loc_180010B91
0x180010b79  mov     edx, 27h ; '''
0x180010b7e  mov     rcx, [rcx+10h]
0x180010b82  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010b89  mov     r9d, ebx
0x180010b8c  call    WPP_SF_d
0x180010b91  mov     rax, [rsp+28h+arg_10]
0x180010b96  test    rax, rax
0x180010b99  jz      short loc_180010BA0
0x180010b9b  xor     ecx, ecx
0x180010b9d  xchg    ecx, [rax+30h]
0x180010ba0  mov     eax, ebx
0x180010ba2  jmp     short loc_180010BF2
0x180010ba4  mov     rcx, [rdi+20h]
0x180010ba8  lea     rdx, [rsp+28h+arg_18]
0x180010bad  call    cs:__imp_WerpGetReportTime
0x180010bb3  mov     ebx, eax
0x180010bb5  test    eax, eax
0x180010bb7  jns     short loc_180010BD9
0x180010bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bc0  lea     rdx, WPP_GLOBAL_Control
0x180010bc7  cmp     rcx, rdx
0x180010bca  jz      short loc_180010B91
0x180010bcc  test    byte ptr [rcx+1Ch], 1
0x180010bd0  jz      short loc_180010B91
0x180010bd2  mov     edx, 28h ; '('
0x180010bd7  jmp     short loc_180010B7E
0x180010bd9  mov     rax, [rsp+28h+arg_18]
0x180010bde  mov     [rsi], rax
0x180010be1  mov     rax, [rsp+28h+arg_10]
0x180010be6  test    rax, rax
0x180010be9  jz      short loc_180010BF0
0x180010beb  xor     ecx, ecx
0x180010bed  xchg    ecx, [rax+30h]
0x180010bf0  xor     eax, eax
0x180010bf2  mov     rbx, [rsp+28h+arg_0]
0x180010bf7  mov     rsi, [rsp+28h+arg_8]
0x180010bfc  add     rsp, 20h
0x180010c00  pop     rdi
0x180010c01  retn
```

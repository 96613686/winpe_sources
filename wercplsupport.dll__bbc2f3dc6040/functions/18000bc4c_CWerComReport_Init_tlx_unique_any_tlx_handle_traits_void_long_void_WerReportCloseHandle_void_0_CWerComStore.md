# CWerComReport::Init(tlx::unique_any<tlx::handle_traits<void *,long (void *),&WerReportCloseHandle(void *),0>>,CWerComStore *)

- ea: `0x18000bc4c`
- end: `0x18000bcf5`
- name: `?Init@CWerComReport@@QEAAJV?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@Z$0A@@tlx@@@tlx@@PEAVCWerComStore@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fb0c`

## callees

- `0x180002850`
- `0x18000bc4c`
- `0x180013010`

## import_xrefs

- `wer!WerReportCloseHandle` at `0x18000bc85`
- `wer!WerReportCloseHandle` at `0x18000bcdd`
- `wer!WerReportCloseHandle` at `0x18000bc85`
- `wer!WerReportCloseHandle` at `0x18000bcdd`

## pseudocode

```c
__int64 __fastcall CWerComReport::Init(__int64 a1, HREPORT *a2, __int64 a3)
{
  HREPORT v3; // rax
  void *v7; // rcx
  unsigned int v8; // ebx

  v3 = *a2;
  if ( *a2 && a3 )
  {
    *a2 = 0;
    v7 = *(void **)(a1 + 32);
    *(_QWORD *)(a1 + 32) = v3;
    if ( v7 )
      WerReportCloseHandle(v7);
    *(_QWORD *)(a1 + 40) = a3;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
    v8 = 0;
  }
  else
  {
    v8 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
  }
  if ( *a2 )
    WerReportCloseHandle(*a2);
  return v8;
}

```

## disassembly

```asm
0x18000bc4c  mov     [rsp+arg_0], rbx
0x18000bc51  mov     [rsp+arg_8], rsi
0x18000bc56  push    rdi
0x18000bc57  sub     rsp, 20h
0x18000bc5b  mov     rax, [rdx]
0x18000bc5e  mov     rbx, r8
0x18000bc61  mov     rdi, rdx
0x18000bc64  mov     rsi, rcx
0x18000bc67  test    rax, rax
0x18000bc6a  jz      short loc_18000BCA2
0x18000bc6c  test    rbx, rbx
0x18000bc6f  jz      short loc_18000BCA2
0x18000bc71  mov     qword ptr [rdx], 0
0x18000bc78  mov     rcx, [rcx+20h]; hReportHandle
0x18000bc7c  mov     [rsi+20h], rax
0x18000bc80  test    rcx, rcx
0x18000bc83  jz      short loc_18000BC8B
0x18000bc85  call    cs:__imp_WerReportCloseHandle
0x18000bc8b  mov     [rsi+28h], rbx
0x18000bc8f  mov     rcx, rbx
0x18000bc92  mov     rax, [rbx]
0x18000bc95  mov     rax, [rax+8]
0x18000bc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc9e  xor     ebx, ebx
0x18000bca0  jmp     short loc_18000BCD5
0x18000bca2  mov     ebx, 80070057h
0x18000bca7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcae  lea     rax, WPP_GLOBAL_Control
0x18000bcb5  cmp     rcx, rax
0x18000bcb8  jz      short loc_18000BCD5
0x18000bcba  test    byte ptr [rcx+1Ch], 1
0x18000bcbe  jz      short loc_18000BCD5
0x18000bcc0  mov     rcx, [rcx+10h]
0x18000bcc4  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000bccb  mov     edx, 1Ah
0x18000bcd0  call    WPP_SF_
0x18000bcd5  mov     rcx, [rdi]; hReportHandle
0x18000bcd8  test    rcx, rcx
0x18000bcdb  jz      short loc_18000BCE3
0x18000bcdd  call    cs:__imp_WerReportCloseHandle
0x18000bce3  mov     rsi, [rsp+28h+arg_8]
0x18000bce8  mov     eax, ebx
0x18000bcea  mov     rbx, [rsp+28h+arg_0]
0x18000bcef  add     rsp, 20h
0x18000bcf3  pop     rdi
0x18000bcf4  retn
```

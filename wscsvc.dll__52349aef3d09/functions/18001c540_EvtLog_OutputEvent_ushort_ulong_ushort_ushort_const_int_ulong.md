# EvtLog_OutputEvent(ushort,ulong,ushort,ushort const * *,int,ulong)

- ea: `0x18001c540`
- end: `0x18001c5db`
- name: `?EvtLog_OutputEvent@@YAXGKGPEAPEBGHK@Z`
- size: `155`
- prototype: `void __fastcall(WORD, DWORD, WORD, const unsigned __int16 **, int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001cb1c`

## callees

- `0x18001c540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5d3`
- `ADVAPI32!RegisterEventSourceW` at `0x18001c561`
- `ADVAPI32!RegisterEventSourceW` at `0x18001c561`
- `ADVAPI32!DeregisterEventSource` at `0x18001c5c2`
- `ADVAPI32!DeregisterEventSource` at `0x18001c5c2`
- `ADVAPI32!ReportEventW` at `0x18001c5b5`
- `ADVAPI32!ReportEventW` at `0x18001c5b5`

## string_xrefs

- `0x18001c551`: `SecurityCenter`

## pseudocode

```c
void __fastcall EvtLog_OutputEvent(WORD a1, DWORD a2, WORD a3, const unsigned __int16 **a4, int a5, unsigned int a6)
{
  HANDLE v10; // rbx
  unsigned int *lpRawData; // r10

  v10 = RegisterEventSourceW(0, L"SecurityCenter");
  if ( v10 )
  {
    lpRawData = &a6;
    if ( !a5 )
      lpRawData = 0;
    if ( !ReportEventW(v10, a1, 0, a2, 0, a3, a5 != 0 ? 4 : 0, a4, lpRawData) )
      GetLastError();
    DeregisterEventSource(v10);
  }
}

```

## disassembly

```asm
0x18001c540  push    rbx
0x18001c542  push    rbp
0x18001c543  push    rsi
0x18001c544  push    rdi
0x18001c545  push    r14
0x18001c547  sub     rsp, 50h
0x18001c54b  mov     ebp, edx
0x18001c54d  movzx   r14d, cx
0x18001c551  lea     rdx, SourceName; "SecurityCenter"
0x18001c558  xor     ecx, ecx; lpUNCServerName
0x18001c55a  mov     rdi, r9
0x18001c55d  movzx   esi, r8w
0x18001c561  call    cs:__imp_RegisterEventSourceW
0x18001c567  mov     rbx, rax
0x18001c56a  test    rax, rax
0x18001c56d  jz      short loc_18001C5C8
0x18001c56f  mov     r9d, [rsp+78h+arg_20]
0x18001c577  lea     r10, [rsp+78h+arg_28]
0x18001c57f  xor     eax, eax
0x18001c581  movzx   edx, r14w; wType
0x18001c585  test    r9d, r9d
0x18001c588  mov     rcx, rbx; hEventLog
0x18001c58b  cmovz   r10, rax
0x18001c58f  neg     r9d
0x18001c592  mov     [rsp+78h+lpRawData], r10; lpRawData
0x18001c597  mov     r9d, ebp; dwEventID
0x18001c59a  sbb     eax, eax
0x18001c59c  mov     [rsp+78h+lpStrings], rdi; lpStrings
0x18001c5a1  and     eax, 4
0x18001c5a4  xor     r8d, r8d; wCategory
0x18001c5a7  mov     [rsp+78h+dwDataSize], eax; dwDataSize
0x18001c5ab  mov     [rsp+78h+wNumStrings], si; wNumStrings
0x18001c5b0  mov     [rsp+78h+lpUserSid], r8; lpUserSid
0x18001c5b5  call    cs:__imp_ReportEventW
0x18001c5bb  test    eax, eax
0x18001c5bd  jz      short loc_18001C5D3
0x18001c5bf  mov     rcx, rbx; hEventLog
0x18001c5c2  call    cs:__imp_DeregisterEventSource
0x18001c5c8  add     rsp, 50h
0x18001c5cc  pop     r14
0x18001c5ce  pop     rdi
0x18001c5cf  pop     rsi
0x18001c5d0  pop     rbp
0x18001c5d1  pop     rbx
0x18001c5d2  retn
0x18001c5d3  call    cs:__imp_GetLastError
0x18001c5d9  jmp     short loc_18001C5BF
```

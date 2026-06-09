# _stub_DCompositionGetStatistics

- ea: `0x14003a7b0`
- end: `0x14003a857`
- name: `_stub_DCompositionGetStatistics`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x14003a7b0`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a7f9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x14003a7f9`

## string_xrefs

- `0x14003a7df`: `NtDCompositionGetStatistics`

## pseudocode

```c
__int64 __fastcall stub_DCompositionGetStatistics(int a1, int a2, int a3, int a4, __int64 a5)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtDCompositionGetStatistics(a1, a2, a3, a4, a5);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtDCompositionGetStatistics(a1, a2, a3, a4, a5);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[37] + 4 * (unsigned int)W32pServiceLimitFilter + 7);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x14003a7b0  sub     rsp, 48h
0x14003a7b4  mov     [rsp+48h+var_28], rcx
0x14003a7b9  mov     [rsp+48h+var_20], rdx
0x14003a7be  mov     [rsp+48h+var_18], r8
0x14003a7c3  mov     [rsp+48h+var_10], r9
0x14003a7c8  mov     rcx, 12Fh
0x14003a7cf  call    cs:__imp_IsWin32KSyscallFiltered
0x14003a7d6  nop     dword ptr [rax+rax+00h]
0x14003a7db  test    al, al
0x14003a7dd  jz      short loc_14003A833
0x14003a7df  lea     rcx, aNtdcomposition_27; "NtDCompositionGetStatistics"
0x14003a7e6  mov     rdx, 12Fh
0x14003a7ed  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x14003a7f4  nop     dword ptr [rax+rax+00h]
0x14003a7f9  call    cs:__imp_PsIsWin32KFilterEnabled
0x14003a800  nop     dword ptr [rax+rax+00h]
0x14003a805  test    al, al
0x14003a807  jz      short loc_14003A833
0x14003a809  lea     rcx, W32pServiceTableFilter
0x14003a810  mov     edx, cs:W32pServiceLimitFilter
0x14003a816  mov     rax, 12Fh
0x14003a81d  lea     rcx, [rcx+rdx*4]
0x14003a821  movsx   eax, byte ptr [rcx+rax]
0x14003a825  or      eax, eax
0x14003a827  jle     short loc_14003A82E
0x14003a829  mov     eax, 0C000001Ch
0x14003a82e  add     rsp, 48h
0x14003a832  retn
0x14003a833  mov     rax, cs:__imp_NtDCompositionGetStatistics
0x14003a83a  mov     rcx, [rsp+48h+var_28]
0x14003a83f  mov     rdx, [rsp+48h+var_20]
0x14003a844  mov     r8, [rsp+48h+var_18]
0x14003a849  mov     r9, [rsp+48h+var_10]
0x14003a84e  add     rsp, 48h
0x14003a852  jmp     rax
```

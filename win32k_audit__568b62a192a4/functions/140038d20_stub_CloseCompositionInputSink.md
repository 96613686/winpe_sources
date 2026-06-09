# _stub_CloseCompositionInputSink

- ea: `0x140038d20`
- end: `0x140038dc7`
- name: `_stub_CloseCompositionInputSink`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140038d20`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038d69`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140038d69`

## string_xrefs

- `0x140038d4f`: `NtCloseCompositionInputSink`

## pseudocode

```c
__int64 __fastcall stub_CloseCompositionInputSink(__int64 a1)
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtCloseCompositionInputSink(a1);
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtCloseCompositionInputSink(a1);
  result = (unsigned int)*((char *)&W32pServiceTableFilter[33] + 4 * (unsigned int)W32pServiceLimitFilter + 3);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140038d20  sub     rsp, 48h
0x140038d24  mov     [rsp+48h+var_28], rcx
0x140038d29  mov     [rsp+48h+var_20], rdx
0x140038d2e  mov     [rsp+48h+var_18], r8
0x140038d33  mov     [rsp+48h+var_10], r9
0x140038d38  mov     rcx, 10Bh
0x140038d3f  call    cs:__imp_IsWin32KSyscallFiltered
0x140038d46  nop     dword ptr [rax+rax+00h]
0x140038d4b  test    al, al
0x140038d4d  jz      short loc_140038DA3
0x140038d4f  lea     rcx, aNtclosecomposi; "NtCloseCompositionInputSink"
0x140038d56  mov     rdx, 10Bh
0x140038d5d  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140038d64  nop     dword ptr [rax+rax+00h]
0x140038d69  call    cs:__imp_PsIsWin32KFilterEnabled
0x140038d70  nop     dword ptr [rax+rax+00h]
0x140038d75  test    al, al
0x140038d77  jz      short loc_140038DA3
0x140038d79  lea     rcx, W32pServiceTableFilter
0x140038d80  mov     edx, cs:W32pServiceLimitFilter
0x140038d86  mov     rax, 10Bh
0x140038d8d  lea     rcx, [rcx+rdx*4]
0x140038d91  movsx   eax, byte ptr [rcx+rax]
0x140038d95  or      eax, eax
0x140038d97  jle     short loc_140038D9E
0x140038d99  mov     eax, 0C000001Ch
0x140038d9e  add     rsp, 48h
0x140038da2  retn
0x140038da3  mov     rax, cs:__imp_NtCloseCompositionInputSink
0x140038daa  mov     rcx, [rsp+48h+var_28]
0x140038daf  mov     rdx, [rsp+48h+var_20]
0x140038db4  mov     r8, [rsp+48h+var_18]
0x140038db9  mov     r9, [rsp+48h+var_10]
0x140038dbe  add     rsp, 48h
0x140038dc2  jmp     rax
```

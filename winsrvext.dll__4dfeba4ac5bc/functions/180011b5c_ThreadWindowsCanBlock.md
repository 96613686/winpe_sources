# ThreadWindowsCanBlock

- ea: `0x180011b5c`
- end: `0x180011bcf`
- name: `ThreadWindowsCanBlock`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c10`

## callees

- `0x180011b5c`

## import_xrefs

- `USER32!EnumThreadWindows` at `0x180011b7d`
- `USER32!EnumThreadWindows` at `0x180011b7d`
- `USER32!ShutdownBlockReasonQuery` at `0x180011bb2`
- `USER32!ShutdownBlockReasonQuery` at `0x180011bb2`

## pseudocode

```c
_BOOL8 __fastcall ThreadWindowsCanBlock(__int64 a1, BOOL *a2)
{
  DWORD v2; // ecx
  DWORD pcchBuff; // [rsp+30h] [rbp+8h] BYREF
  LPARAM lParam; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(a1 + 48);
  lParam = 0;
  EnumThreadWindows(v2, FindReasonOrVisibleWindowFromThread, (LPARAM)&lParam);
  if ( a2 )
  {
    if ( !lParam )
    {
      *a2 = 0;
      return 0;
    }
    pcchBuff = 0;
    *a2 = ShutdownBlockReasonQuery((HWND)lParam, 0, &pcchBuff);
  }
  return lParam != 0;
}

```

## disassembly

```asm
0x180011b5c  push    rbx
0x180011b5e  sub     rsp, 20h
0x180011b62  mov     ecx, [rcx+30h]; dwThreadId
0x180011b65  lea     r8, [rsp+28h+lParam]; lParam
0x180011b6a  mov     rbx, rdx
0x180011b6d  mov     [rsp+28h+lParam], 0
0x180011b76  lea     rdx, FindReasonOrVisibleWindowFromThread; lpfn
0x180011b7d  call    cs:__imp_EnumThreadWindows
0x180011b84  nop     dword ptr [rax+rax+00h]
0x180011b89  test    rbx, rbx
0x180011b8c  jz      short loc_180011BC0
0x180011b8e  mov     rcx, [rsp+28h+lParam]; hWnd
0x180011b93  test    rcx, rcx
0x180011b96  jnz     short loc_180011BA3
0x180011b98  mov     [rbx], ecx
0x180011b9a  xor     eax, eax
0x180011b9c  add     rsp, 20h
0x180011ba0  pop     rbx
0x180011ba1  retn
0x180011ba3  lea     r8, [rsp+28h+pcchBuff]; pcchBuff
0x180011ba8  mov     [rsp+28h+pcchBuff], 0
0x180011bb0  xor     edx, edx; pwszBuff
0x180011bb2  call    cs:__imp_ShutdownBlockReasonQuery
0x180011bb9  nop     dword ptr [rax+rax+00h]
0x180011bbe  mov     [rbx], eax
0x180011bc0  cmp     [rsp+28h+lParam], 0
0x180011bc6  jz      short loc_180011B9A
0x180011bc8  mov     eax, 1
0x180011bcd  jmp     short loc_180011B9C
```

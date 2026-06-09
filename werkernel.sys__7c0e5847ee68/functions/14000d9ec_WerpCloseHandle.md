# WerpCloseHandle

- ea: `0x14000d9ec`
- end: `0x14000da63`
- name: `WerpCloseHandle`
- size: `119`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c630`
- `0x14000c6f0`

## callees

- `0x14000d9ec`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000da0b`
- `ntoskrnl!DbgPrintEx` at `0x14000da49`
- `ntoskrnl!DbgPrintEx` at `0x14000da0b`
- `ntoskrnl!DbgPrintEx` at `0x14000da49`
- `ntoskrnl!ZwClose` at `0x14000da1e`
- `ntoskrnl!ZwClose` at `0x14000da1e`

## pseudocode

```c
__int64 __fastcall WerpCloseHandle(void *a1)
{
  unsigned int v3; // edi
  ULONG v4; // edx
  NTSTATUS v5; // [rsp+20h] [rbp-18h]

  if ( a1 )
  {
    v5 = ZwClose(a1);
    v3 = v5;
    v4 = 1;
    if ( v5 >= 0 )
      v4 = 3;
    DbgPrintEx(5u, v4, "WERKERNELHOST: WerpCloseHandle: ZwClose(%p) returned 0x%X\n", a1, v5);
    return v3;
  }
  else
  {
    DbgPrintEx(5u, 3u, "WERKERNELHOST: WerpCloseHandle: NULL handle\n");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000d9ec  mov     [rsp+arg_0], rbx
0x14000d9f1  push    rdi
0x14000d9f2  sub     rsp, 30h
0x14000d9f6  mov     rbx, rcx
0x14000d9f9  test    rcx, rcx
0x14000d9fc  jnz     short loc_14000DA1E
0x14000d9fe  lea     edx, [rcx+3]; Level
0x14000da01  lea     ecx, [rbx+5]; ComponentId
0x14000da04  lea     r8, aWerkernelhostW_58; "WERKERNELHOST: WerpCloseHandle: NULL ha"...
0x14000da0b  call    cs:__imp_DbgPrintEx
0x14000da12  nop     dword ptr [rax+rax+00h]
0x14000da17  mov     eax, 0C000000Dh
0x14000da1c  jmp     short loc_14000DA57
0x14000da1e  call    cs:__imp_ZwClose
0x14000da25  nop     dword ptr [rax+rax+00h]
0x14000da2a  mov     ecx, 5; ComponentId
0x14000da2f  mov     [rsp+38h+var_18], eax
0x14000da33  lea     r8, aWerkernelhostW_33; "WERKERNELHOST: WerpCloseHandle: ZwClose"...
0x14000da3a  mov     edi, eax
0x14000da3c  mov     r9, rbx
0x14000da3f  lea     edx, [rcx-4]
0x14000da42  test    eax, eax
0x14000da44  js      short loc_14000DA49
0x14000da46  lea     edx, [rcx-2]; Level
0x14000da49  call    cs:__imp_DbgPrintEx
0x14000da50  nop     dword ptr [rax+rax+00h]
0x14000da55  mov     eax, edi
0x14000da57  mov     rbx, [rsp+38h+arg_0]
0x14000da5c  add     rsp, 30h
0x14000da60  pop     rdi
0x14000da61  retn
```

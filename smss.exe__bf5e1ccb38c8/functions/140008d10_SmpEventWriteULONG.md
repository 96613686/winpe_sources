# SmpEventWriteULONG

- ea: `0x140008d10`
- end: `0x140008d87`
- name: `SmpEventWriteULONG`
- size: `119`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000d418`
- `0x14000eb40`

## callees

- `0x140008d10`
- `0x14001cc40`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x140008d7f`
- `ntdll!EtwEventWrite` at `0x140008d7f`
- `ntdll!EtwEventEnabled` at `0x140008d4d`
- `ntdll!EtwEventEnabled` at `0x140008d4d`

## pseudocode

```c
void __fastcall SmpEventWriteULONG(PCEVENT_DESCRIPTOR EventDescriptor, int a2)
{
  _QWORD v3[2]; // [rsp+20h] [rbp-28h] BYREF
  int v4; // [rsp+58h] [rbp+10h] BYREF

  v4 = a2;
  if ( SmpTraceHandle )
  {
    if ( EtwEventEnabled(SmpTraceHandle, EventDescriptor) )
    {
      v3[0] = &v4;
      v3[1] = 4;
      EtwEventWrite(SmpTraceHandle, EventDescriptor, 1, v3);
    }
  }
}

```

## disassembly

```asm
0x140008d10  mov     [rsp+arg_8], edx
0x140008d14  push    rbx
0x140008d15  sub     rsp, 40h
0x140008d19  mov     rax, cs:__security_cookie
0x140008d20  xor     rax, rsp
0x140008d23  mov     [rsp+48h+var_18], rax
0x140008d28  mov     rbx, rcx
0x140008d2b  mov     rcx, cs:SmpTraceHandle; RegHandle
0x140008d32  test    rcx, rcx
0x140008d35  jnz     short loc_140008D4A
0x140008d37  mov     rcx, [rsp+48h+var_18]
0x140008d3c  xor     rcx, rsp; StackCookie
0x140008d3f  call    __security_check_cookie
0x140008d44  add     rsp, 40h
0x140008d48  pop     rbx
0x140008d49  retn
0x140008d4a  mov     rdx, rbx; EventDescriptor
0x140008d4d  call    cs:__imp_EtwEventEnabled
0x140008d53  test    al, al
0x140008d55  jz      short loc_140008D37
0x140008d57  mov     rcx, cs:SmpTraceHandle
0x140008d5e  lea     rax, [rsp+48h+arg_8]
0x140008d63  lea     r9, [rsp+48h+var_28]
0x140008d68  mov     [rsp+48h+var_28], rax
0x140008d6d  mov     r8d, 1
0x140008d73  mov     [rsp+48h+var_20], 4
0x140008d7c  mov     rdx, rbx
0x140008d7f  call    cs:__imp_EtwEventWrite
0x140008d85  jmp     short loc_140008D37
```

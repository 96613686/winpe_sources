# SmpEventWriteString

- ea: `0x140011bb0`
- end: `0x140011c49`
- name: `SmpEventWriteString`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140011d24`

## callees

- `0x140011bb0`
- `0x14001cc40`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x140011c30`
- `ntdll!EtwEventWrite` at `0x140011c30`
- `ntdll!EtwEventEnabled` at `0x140011bdb`
- `ntdll!EtwEventEnabled` at `0x140011bdb`

## pseudocode

```c
void __fastcall SmpEventWriteString(__int64 a1, unsigned __int16 *a2)
{
  unsigned __int16 v3; // ax
  __int16 v4; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v5[3]; // [rsp+28h] [rbp-30h] BYREF
  int v6; // [rsp+40h] [rbp-18h]
  int v7; // [rsp+44h] [rbp-14h]

  if ( SmpTraceHandle )
  {
    if ( EtwEventEnabled(SmpTraceHandle, &SmssEvt_CrashDumpCopy_Error) )
    {
      v3 = *a2;
      v6 = *a2;
      v4 = v3 >> 1;
      v5[0] = &v4;
      v5[2] = *((_QWORD *)a2 + 1);
      v5[1] = 2;
      v7 = 0;
      EtwEventWrite(SmpTraceHandle, &SmssEvt_CrashDumpCopy_Error, 2, v5);
    }
  }
}

```

## disassembly

```asm
0x140011bb0  push    rbx
0x140011bb2  sub     rsp, 50h
0x140011bb6  mov     rax, cs:__security_cookie
0x140011bbd  xor     rax, rsp
0x140011bc0  mov     [rsp+58h+var_10], rax
0x140011bc5  mov     rcx, cs:SmpTraceHandle; RegHandle
0x140011bcc  mov     rbx, rdx
0x140011bcf  test    rcx, rcx
0x140011bd2  jz      short loc_140011C36
0x140011bd4  lea     rdx, SmssEvt_CrashDumpCopy_Error; EventDescriptor
0x140011bdb  call    cs:__imp_EtwEventEnabled
0x140011be1  test    al, al
0x140011be3  jz      short loc_140011C36
0x140011be5  movzx   ecx, word ptr [rbx]
0x140011be8  lea     r9, [rsp+58h+var_30]
0x140011bed  movzx   eax, cx
0x140011bf0  mov     [rsp+58h+var_18], ecx
0x140011bf4  mov     rcx, cs:SmpTraceHandle
0x140011bfb  lea     rdx, SmssEvt_CrashDumpCopy_Error
0x140011c02  shr     ax, 1
0x140011c05  mov     r8d, 2
0x140011c0b  mov     [rsp+58h+var_38], ax
0x140011c10  lea     rax, [rsp+58h+var_38]
0x140011c15  mov     [rsp+58h+var_30], rax
0x140011c1a  mov     rax, [rbx+8]
0x140011c1e  mov     [rsp+58h+var_20], rax
0x140011c23  mov     [rsp+58h+var_28], r8
0x140011c28  mov     [rsp+58h+var_14], 0
0x140011c30  call    cs:__imp_EtwEventWrite
0x140011c36  mov     rcx, [rsp+58h+var_10]
0x140011c3b  xor     rcx, rsp; StackCookie
0x140011c3e  call    __security_check_cookie
0x140011c43  add     rsp, 50h
0x140011c47  pop     rbx
0x140011c48  retn
```

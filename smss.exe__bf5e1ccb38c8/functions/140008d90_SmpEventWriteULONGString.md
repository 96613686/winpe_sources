# SmpEventWriteULONGString

- ea: `0x140008d90`
- end: `0x140008e4b`
- name: `SmpEventWriteULONGString`
- size: `187`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400053e0`

## callees

- `0x140008d90`
- `0x14001cc40`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x140008e43`
- `ntdll!EtwEventWrite` at `0x140008e43`
- `ntdll!EtwEventEnabled` at `0x140008dc2`
- `ntdll!EtwEventEnabled` at `0x140008dc2`

## pseudocode

```c
void __fastcall SmpEventWriteULONGString(PCEVENT_DESCRIPTOR EventDescriptor, int a2, unsigned __int16 *a3)
{
  unsigned __int16 v5; // ax
  __int64 v6; // rax
  __int16 v7; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v8[5]; // [rsp+28h] [rbp-40h] BYREF
  int v9; // [rsp+50h] [rbp-18h]
  int v10; // [rsp+54h] [rbp-14h]
  int v11; // [rsp+78h] [rbp+10h] BYREF

  v11 = a2;
  if ( SmpTraceHandle )
  {
    if ( EtwEventEnabled(SmpTraceHandle, EventDescriptor) )
    {
      v5 = *a3;
      v9 = *a3;
      v7 = v5 >> 1;
      v8[0] = &v11;
      v8[2] = &v7;
      v6 = *((_QWORD *)a3 + 1);
      v10 = 0;
      v8[4] = v6;
      v8[1] = 4;
      v8[3] = 2;
      EtwEventWrite(SmpTraceHandle, EventDescriptor, 3, v8);
    }
  }
}

```

## disassembly

```asm
0x140008d90  mov     [rsp+arg_10], rbx
0x140008d95  mov     [rsp+arg_8], edx
0x140008d99  push    rdi
0x140008d9a  sub     rsp, 60h
0x140008d9e  mov     rax, cs:__security_cookie
0x140008da5  xor     rax, rsp
0x140008da8  mov     [rsp+68h+var_10], rax
0x140008dad  mov     rbx, rcx
0x140008db0  mov     rdi, r8
0x140008db3  mov     rcx, cs:SmpTraceHandle; RegHandle
0x140008dba  test    rcx, rcx
0x140008dbd  jz      short loc_140008DCC
0x140008dbf  mov     rdx, rbx; EventDescriptor
0x140008dc2  call    cs:__imp_EtwEventEnabled
0x140008dc8  test    al, al
0x140008dca  jnz     short loc_140008DE7
0x140008dcc  mov     rcx, [rsp+68h+var_10]
0x140008dd1  xor     rcx, rsp; StackCookie
0x140008dd4  call    __security_check_cookie
0x140008dd9  mov     rbx, [rsp+68h+arg_10]
0x140008de1  add     rsp, 60h
0x140008de5  pop     rdi
0x140008de6  retn
0x140008de7  movzx   ecx, word ptr [rdi]
0x140008dea  lea     r9, [rsp+68h+var_40]
0x140008def  movzx   eax, cx
0x140008df2  mov     [rsp+68h+var_18], ecx
0x140008df6  mov     rcx, cs:SmpTraceHandle
0x140008dfd  xor     edx, edx
0x140008dff  shr     ax, 1
0x140008e02  mov     r8d, 3
0x140008e08  mov     [rsp+68h+var_48], ax
0x140008e0d  lea     rax, [rsp+68h+arg_8]
0x140008e12  mov     [rsp+68h+var_40], rax
0x140008e17  lea     rax, [rsp+68h+var_48]
0x140008e1c  mov     [rsp+68h+var_30], rax
0x140008e21  mov     rax, [rdi+8]
0x140008e25  mov     [rsp+68h+var_14], edx
0x140008e29  mov     rdx, rbx
0x140008e2c  mov     [rsp+68h+var_20], rax
0x140008e31  mov     [rsp+68h+var_38], 4
0x140008e3a  mov     [rsp+68h+var_28], 2
0x140008e43  call    cs:__imp_EtwEventWrite
0x140008e49  jmp     short loc_140008DCC
```

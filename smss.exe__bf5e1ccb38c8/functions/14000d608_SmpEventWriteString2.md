# SmpEventWriteString2

- ea: `0x14000d608`
- end: `0x14000d6f2`
- name: `SmpEventWriteString2`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x140015ae8`

## callees

- `0x14000d608`
- `0x14001cc40`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x14000d6cb`
- `ntdll!EtwEventWrite` at `0x14000d6cb`
- `ntdll!EtwEventEnabled` at `0x14000d648`
- `ntdll!EtwEventEnabled` at `0x14000d648`

## pseudocode

```c
void __fastcall SmpEventWriteString2(__int64 a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v5; // r8d
  unsigned __int16 v6; // ax
  __int64 v7; // rax
  __int16 v8; // [rsp+20h] [rbp-60h] BYREF
  __int16 v9; // [rsp+24h] [rbp-5Ch] BYREF
  _QWORD v10[5]; // [rsp+30h] [rbp-50h] BYREF
  int v11; // [rsp+58h] [rbp-28h]
  int v12; // [rsp+5Ch] [rbp-24h]
  __int64 v13; // [rsp+60h] [rbp-20h]
  int v14; // [rsp+68h] [rbp-18h]
  int v15; // [rsp+6Ch] [rbp-14h]

  if ( SmpTraceHandle )
  {
    if ( EtwEventEnabled(SmpTraceHandle, &SmssEvt_FileRename_Info) )
    {
      v5 = *a3;
      v6 = *a2;
      v11 = *a2;
      v8 = v6 >> 1;
      v9 = (unsigned __int16)v5 >> 1;
      v10[0] = &v8;
      v10[2] = &v9;
      v10[4] = *((_QWORD *)a2 + 1);
      v7 = *((_QWORD *)a3 + 1);
      v14 = v5;
      v13 = v7;
      v10[1] = 2;
      v10[3] = 2;
      v12 = 0;
      v15 = 0;
      EtwEventWrite(SmpTraceHandle, &SmssEvt_FileRename_Info, 4, v10);
    }
  }
}

```

## disassembly

```asm
0x14000d608  mov     [rsp-8+arg_0], rbx
0x14000d60d  mov     [rsp-8+arg_8], rdi
0x14000d612  push    rbp
0x14000d613  mov     rbp, rsp
0x14000d616  sub     rsp, 80h
0x14000d61d  mov     rax, cs:__security_cookie
0x14000d624  xor     rax, rsp
0x14000d627  mov     [rbp+var_10], rax
0x14000d62b  mov     rcx, cs:SmpTraceHandle; RegHandle
0x14000d632  mov     rbx, r8
0x14000d635  mov     rdi, rdx
0x14000d638  test    rcx, rcx
0x14000d63b  jz      loc_14000D6D1
0x14000d641  lea     rdx, SmssEvt_FileRename_Info; EventDescriptor
0x14000d648  call    cs:__imp_EtwEventEnabled
0x14000d64e  test    al, al
0x14000d650  jz      short loc_14000D6D1
0x14000d652  movzx   ecx, word ptr [rdi]
0x14000d655  lea     r9, [rbp+var_50]
0x14000d659  movzx   r8d, word ptr [rbx]
0x14000d65d  lea     rdx, SmssEvt_FileRename_Info
0x14000d664  movzx   eax, cx
0x14000d667  mov     [rbp+var_28], ecx
0x14000d66a  mov     rcx, cs:SmpTraceHandle
0x14000d671  shr     ax, 1
0x14000d674  mov     [rbp+var_60], ax
0x14000d678  movzx   eax, r8w
0x14000d67c  shr     ax, 1
0x14000d67f  mov     [rbp+var_5C], ax
0x14000d683  lea     rax, [rbp+var_60]
0x14000d687  mov     [rbp+var_50], rax
0x14000d68b  lea     rax, [rbp+var_5C]
0x14000d68f  mov     [rbp+var_40], rax
0x14000d693  mov     rax, [rdi+8]
0x14000d697  mov     [rbp+var_30], rax
0x14000d69b  mov     rax, [rbx+8]
0x14000d69f  mov     [rbp+var_18], r8d
0x14000d6a3  mov     r8d, 4
0x14000d6a9  mov     [rbp+var_20], rax
0x14000d6ad  mov     [rbp+var_48], 2
0x14000d6b5  mov     [rbp+var_38], 2
0x14000d6bd  mov     [rbp+var_24], 0
0x14000d6c4  mov     [rbp+var_14], 0
0x14000d6cb  call    cs:__imp_EtwEventWrite
0x14000d6d1  mov     rcx, [rbp+var_10]
0x14000d6d5  xor     rcx, rsp; StackCookie
0x14000d6d8  call    __security_check_cookie
0x14000d6dd  lea     r11, [rsp+80h+var_s0]
0x14000d6e5  mov     rbx, [r11+10h]
0x14000d6e9  mov     rdi, [r11+18h]
0x14000d6ed  mov     rsp, r11
0x14000d6f0  pop     rbp
0x14000d6f1  retn
```

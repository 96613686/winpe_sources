# WinHvUncommitGpaPages

- ea: `0x140001d00`
- end: `0x140001ee1`
- name: `WinHvUncommitGpaPages`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001d00`
- `0x140002240`
- `0x140009c90`
- `0x14000a040`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!HvlInvokeHypercall` at `0x140001dd2`
- `ntoskrnl!HvlInvokeHypercall` at `0x140001dd2`

## pseudocode

```c
__int64 __fastcall WinHvUncommitGpaPages(__int64 a1, __int64 a2, unsigned __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  __int64 v9; // r9
  _QWORD *v10; // r15
  unsigned int v11; // edi
  signed int v12; // ebx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 *v18; // rax
  signed int v19; // eax
  unsigned int v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v21; // [rsp+38h] [rbp-41h] BYREF
  __int64 v22; // [rsp+40h] [rbp-39h]
  _QWORD v23[16]; // [rsp+50h] [rbp-29h] BYREF

  memset(v23, 0, 0x40u);
  v8 = v23[0];
  v9 = 0;
  v21 = 0;
  v10 = 0;
  v11 = 0;
  v20 = 0;
  v12 = 0;
  *a4 = 0;
  do
  {
    if ( !a3 )
      break;
    if ( !v8 )
    {
      WinHvpSetupHypercall(&v21, 0, (__int64)v23);
      v18 = v21;
      v9 = 0;
      *v21 = a1;
      v10 = v18 + 1;
      v18[1] = a2;
      v8 = v23[0];
    }
    v13 = a3;
    if ( a3 >= 0xFFF )
      v13 = 4095;
    if ( *(_BYTE *)(v8 + 24) )
    {
      v19 = WinHvpSlowHypercallRemote(191, v13, *(_QWORD *)(v8 + 8), *(_QWORD *)(v8 + 16), (__int64)&v20);
      v11 = v20;
      v12 = v19;
    }
    else
    {
      v14 = *(_QWORD *)(v8 + 16) ? *(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL) : 0LL;
      v15 = *(_QWORD *)(v8 + 8) ? *(_QWORD *)(*(_QWORD *)(v8 + 40) + 24LL) : 0LL;
      HIDWORD(v22) = v13 & 0xFFF;
      LODWORD(v22) = WinHvpNested != 0 ? -2147483457 : 191;
      if ( WinHvpConnected )
      {
        v16 = HvlInvokeHypercall(v22, v15, v14);
        v9 = 0;
        v11 = WORD2(v16) & 0xFFF;
        v20 = v11;
        v12 = (_WORD)v16 ? (unsigned __int16)v16 | 0xC0350000 : 0;
      }
      else
      {
        v12 = -1070264320;
      }
    }
    *a4 += v11;
    a3 -= v11;
    *v10 += v11;
    a2 += v11;
    v8 = v23[0];
    if ( (__int64 (__fastcall *)())v23[7] == WinHvpReleaseFallbackBuffers )
    {
      ((void (__fastcall *)(_QWORD, __int64, __int64, __int64))v23[7])(v23[0], v15, v14, v9);
      v9 = 0;
      v8 = 0;
      v23[0] = 0;
    }
    else
    {
      v9 = 0;
    }
  }
  while ( v12 >= 0 );
  if ( v8 )
    ((void (*)(void))v23[7])();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140001d00  push    rbp
0x140001d02  push    rbx
0x140001d03  push    rsi
0x140001d04  push    rdi
0x140001d05  push    r12
0x140001d07  push    r13
0x140001d09  push    r14
0x140001d0b  push    r15
0x140001d0d  lea     rbp, [rsp-1Fh]
0x140001d12  sub     rsp, 98h
0x140001d19  mov     r14, rdx
0x140001d1c  mov     rsi, r8
0x140001d1f  xor     edx, edx; Val
0x140001d21  mov     r13, rcx
0x140001d24  lea     rcx, [rbp+57h+var_80]; void *
0x140001d28  mov     r12, r9
0x140001d2b  lea     r8d, [rdx+40h]; Size
0x140001d2f  call    memset
0x140001d34  mov     rcx, [rbp+57h+var_80]
0x140001d38  xor     r9d, r9d
0x140001d3b  mov     [rbp+57h+var_98], r9
0x140001d3f  mov     r15d, r9d
0x140001d42  mov     edi, r9d
0x140001d45  mov     [rbp+57h+var_A0], r9d
0x140001d49  mov     ebx, r9d
0x140001d4c  mov     [r12], r9
0x140001d50  test    rsi, rsi
0x140001d53  jz      loc_140001E2F
0x140001d59  test    rcx, rcx
0x140001d5c  jz      loc_140001E54
0x140001d62  mov     eax, esi
0x140001d64  cmp     rsi, 0FFFh
0x140001d6b  jb      short loc_140001D72
0x140001d6d  mov     eax, 0FFFh
0x140001d72  cmp     [rcx+18h], r9b
0x140001d76  jnz     loc_140001E94
0x140001d7c  cmp     [rcx+10h], r9
0x140001d80  jz      loc_140001E7E
0x140001d86  mov     r8, [rcx+28h]
0x140001d8a  mov     r8, [r8+28h]
0x140001d8e  cmp     [rcx+8], r9
0x140001d92  jz      loc_140001EBB
0x140001d98  mov     rdx, [rcx+28h]
0x140001d9c  mov     rdx, [rdx+18h]
0x140001da0  and     eax, 0FFFh
0x140001da5  mov     dword ptr [rbp+57h+var_90+4], eax
0x140001da8  mov     al, cs:WinHvpNested
0x140001dae  neg     al
0x140001db0  sbb     ecx, ecx
0x140001db2  and     ecx, 80000000h
0x140001db8  add     ecx, 0BFh
0x140001dbe  cmp     cs:WinHvpConnected, r9b
0x140001dc5  mov     dword ptr [rbp+57h+var_90], ecx
0x140001dc8  jz      loc_140001EC3
0x140001dce  mov     rcx, [rbp+57h+var_90]
0x140001dd2  call    cs:__imp_HvlInvokeHypercall
0x140001dd9  nop     dword ptr [rax+rax+00h]
0x140001dde  mov     rdi, rax
0x140001de1  xor     r9d, r9d
0x140001de4  shr     rdi, 20h
0x140001de8  and     edi, 0FFFh
0x140001dee  mov     [rbp+57h+var_A0], edi
0x140001df1  test    ax, ax
0x140001df4  jnz     loc_140001E86
0x140001dfa  mov     ebx, r9d
0x140001dfd  mov     eax, edi
0x140001dff  lea     rcx, WinHvpReleaseFallbackBuffers
0x140001e06  add     [r12], rax
0x140001e0a  sub     rsi, rax
0x140001e0d  add     [r15], rax
0x140001e10  add     r14, rax
0x140001e13  mov     rax, [rbp+57h+var_48]
0x140001e17  cmp     rax, rcx
0x140001e1a  mov     rcx, [rbp+57h+var_80]
0x140001e1e  jz      loc_140001ECD
0x140001e24  xor     r9d, r9d
0x140001e27  test    ebx, ebx
0x140001e29  jns     loc_140001D50
0x140001e2f  test    rcx, rcx
0x140001e32  jz      short loc_140001E3D
0x140001e34  mov     rax, [rbp+57h+var_48]
0x140001e38  call    _guard_dispatch_icall
0x140001e3d  mov     eax, ebx
0x140001e3f  add     rsp, 98h
0x140001e46  pop     r15
0x140001e48  pop     r14
0x140001e4a  pop     r13
0x140001e4c  pop     r12
0x140001e4e  pop     rdi
0x140001e4f  pop     rsi
0x140001e50  pop     rbx
0x140001e51  pop     rbp
0x140001e52  retn
0x140001e54  lea     r8, [rbp+57h+var_80]
0x140001e58  xor     edx, edx
0x140001e5a  lea     rcx, [rbp+57h+var_98]
0x140001e5e  call    WinHvpSetupHypercall
0x140001e63  mov     rax, [rbp+57h+var_98]
0x140001e67  xor     r9d, r9d
0x140001e6a  mov     [rax], r13
0x140001e6d  lea     r15, [rax+8]
0x140001e71  mov     [rax+8], r14
0x140001e75  mov     rcx, [rbp+57h+var_80]
0x140001e79  jmp     loc_140001D62
0x140001e7e  mov     r8, r9
0x140001e81  jmp     loc_140001D8E
0x140001e86  movzx   ebx, ax
0x140001e89  or      ebx, 0C0350000h
0x140001e8f  jmp     loc_140001DFD
0x140001e94  mov     r9, [rcx+10h]
0x140001e98  lea     rdx, [rbp+57h+var_A0]
0x140001e9c  mov     r8, [rcx+8]
0x140001ea0  mov     ecx, 0BFh
0x140001ea5  mov     [rsp+0D0h+var_B0], rdx
0x140001eaa  mov     edx, eax
0x140001eac  call    WinHvpSlowHypercallRemote
0x140001eb1  mov     edi, [rbp+57h+var_A0]
0x140001eb4  mov     ebx, eax
0x140001eb6  jmp     loc_140001DFD
0x140001ebb  mov     rdx, r9
0x140001ebe  jmp     loc_140001DA0
0x140001ec3  mov     ebx, 0C0351000h
0x140001ec8  jmp     loc_140001DFD
0x140001ecd  call    _guard_dispatch_icall
0x140001ed2  xor     r9d, r9d
0x140001ed5  mov     ecx, r9d
0x140001ed8  mov     [rbp+57h+var_80], rcx
0x140001edc  jmp     loc_140001E27
```

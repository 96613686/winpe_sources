# Smb2ValidateMessageIdAndCommand

- ea: `0x140010b90`
- end: `0x140010de3`
- name: `Smb2ValidateMessageIdAndCommand`
- size: `595`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14005d3d0`
- `0x140074970`

## callees

- `0x140010b90`

## import_xrefs

- `ntoskrnl!ExAcquireSpinLockShared` at `0x140010c5d`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140010c5d`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140010ce5`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140010d69`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140010ce5`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140010d69`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140010dd1`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140010dd1`

## pseudocode

```c
__int64 __fastcall Smb2ValidateMessageIdAndCommand(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 *v5; // rsi
  __int64 v6; // r14
  unsigned __int16 v7; // ax
  __int16 v8; // ax
  unsigned int v9; // ebp
  __int64 v10; // rsi
  unsigned __int64 v11; // rdi
  KIRQL v12; // al
  unsigned __int64 v13; // rdx
  KIRQL v14; // r9
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  __int64 v17; // r8
  char v18; // r15
  int v19; // edx
  signed __int16 v20; // ax
  __int64 result; // rax
  unsigned int v22; // eax
  unsigned __int64 v23; // rax

  v5 = *(__int64 **)(*(_QWORD *)(a1 + 96) + 496LL);
  *(_QWORD *)(a1 + 528) = Smb2CleanupWorkItem;
  *(_WORD *)(a1 + 488) = 1;
  *(_WORD *)(a1 + 490) = *(_WORD *)(a2 + 14);
  if ( (unsigned int)a3 <= 4 )
    goto LABEL_31;
  if ( *(_DWORD *)a2 == 1112364031 )
  {
    result = 0;
    if ( *((_WORD *)v5 + 22) != 0xFFFF )
      result = 3221225680LL;
    if ( (_DWORD)result == -1073741616 )
      goto LABEL_32;
    return result;
  }
  if ( (unsigned int)a3 < 0x40 )
    goto LABEL_31;
  v6 = *(_QWORD *)(a1 + 560);
  if ( *(_BYTE *)v6 )
    return 0;
  v7 = *(_WORD *)(a2 + 12);
  if ( v7 >= 0x14u )
  {
LABEL_31:
    result = 3221225680LL;
LABEL_32:
    *(_DWORD *)(a1 + 488) = 0;
    return result;
  }
  *(_WORD *)(v6 + 14) = v7;
  *(_QWORD *)(v6 + 176) = *(_QWORD *)(a2 + 24);
  if ( *(_WORD *)(a2 + 12) == 12 )
  {
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 96) + 510LL) && !(unsigned __int8)SrvAdminAllowAnonymousAccess(a1, a2, a3, a4) )
      goto LABEL_31;
    return 0;
  }
  if ( (*((_BYTE *)v5 + 49) & 2) != 0 )
  {
    v8 = *(_WORD *)(a2 + 6);
    if ( v8 )
      *(_WORD *)(a1 + 488) = v8;
  }
  v9 = *(unsigned __int16 *)(a1 + 488);
  if ( !*(_WORD *)(a1 + 488) )
    goto LABEL_31;
  v10 = *v5;
  v11 = *(_QWORD *)(a2 + 24);
  v12 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)v10);
  v13 = *(_QWORD *)(v10 + 8);
  v14 = v12;
  if ( v11 < v13 || v11 > *(_QWORD *)(v10 + 16) )
    goto LABEL_30;
  v15 = *(unsigned int *)(v10 + 24) - v13 + v11;
  v16 = *(unsigned int *)(v10 + 32);
  v17 = (unsigned int)(v15 - v16);
  if ( v15 < v16 )
    v17 = (unsigned int)v15;
  if ( (_DWORD)v17 == -1 || v9 > 1 && ((v23 = v11 + v9 - 1, v23 < v11) || v23 > *(_QWORD *)(v10 + 16)) )
  {
LABEL_30:
    ExReleaseSpinLockShared((PEX_SPIN_LOCK)v10, v14);
    goto LABEL_31;
  }
  v18 = 0;
  v19 = 0;
  while ( 1 )
  {
    v20 = _InterlockedCompareExchange16((volatile signed __int16 *)(2 * v17 + *(_QWORD *)(v10 + 40)), 2, 0);
    if ( v20 )
    {
      if ( v20 == 2
        || v19
        || _InterlockedCompareExchange16((volatile signed __int16 *)(2 * v17 + *(_QWORD *)(v10 + 40)), 2, 1) != 1 )
      {
        goto LABEL_30;
      }
      v18 = 1;
    }
    if ( ++v19 == v9 )
      break;
    v22 = v17 + 1;
    v17 = 0;
    if ( v22 != *(_DWORD *)(v10 + 32) )
      v17 = v22;
  }
  ExReleaseSpinLockShared((PEX_SPIN_LOCK)v10, v14);
  *(_BYTE *)v6 = 1;
  result = 0;
  if ( v18 )
    *(_DWORD *)(a1 + 480) = 1;
  return result;
}

```

## disassembly

```asm
0x140010b90  push    rbx
0x140010b92  push    rbp
0x140010b93  push    rsi
0x140010b94  push    rdi
0x140010b95  push    r12
0x140010b97  push    r14
0x140010b99  push    r15
0x140010b9b  sub     rsp, 20h
0x140010b9f  mov     rax, [rcx+60h]
0x140010ba3  mov     r12d, 1
0x140010ba9  mov     rbx, rcx
0x140010bac  mov     rsi, [rax+1F0h]
0x140010bb3  lea     rax, Smb2CleanupWorkItem
0x140010bba  mov     [rcx+210h], rax
0x140010bc1  mov     [rcx+1E8h], r12w
0x140010bc9  movzx   eax, word ptr [rdx+0Eh]
0x140010bcd  mov     [rcx+1EAh], ax
0x140010bd4  cmp     r8d, 4
0x140010bd8  jbe     loc_140010D75
0x140010bde  cmp     dword ptr [rdx], 424D53FFh
0x140010be4  jz      loc_140010D12
0x140010bea  cmp     r8d, 40h ; '@'
0x140010bee  jb      loc_140010D75
0x140010bf4  mov     r14, [rcx+230h]
0x140010bfb  cmp     byte ptr [r14], 0
0x140010bff  jnz     loc_140010DBD
0x140010c05  movzx   eax, word ptr [rdx+0Ch]
0x140010c09  cmp     ax, 14h
0x140010c0d  jnb     loc_140010D75
0x140010c13  mov     [r14+0Eh], ax
0x140010c18  mov     rax, [rdx+18h]
0x140010c1c  mov     [r14+0B0h], rax
0x140010c23  cmp     word ptr [rdx+0Ch], 0Ch
0x140010c28  jz      loc_140010DB0
0x140010c2e  test    byte ptr [rsi+31h], 2
0x140010c32  jz      short loc_140010C44
0x140010c34  movzx   eax, word ptr [rdx+6]
0x140010c38  test    ax, ax
0x140010c3b  jz      short loc_140010C44
0x140010c3d  mov     [rcx+1E8h], ax
0x140010c44  movzx   ebp, word ptr [rcx+1E8h]
0x140010c4b  test    ebp, ebp
0x140010c4d  jz      loc_140010D75
0x140010c53  mov     rsi, [rsi]
0x140010c56  mov     rdi, [rdx+18h]
0x140010c5a  mov     rcx, rsi; SpinLock
0x140010c5d  call    cs:__imp_ExAcquireSpinLockShared
0x140010c64  nop     dword ptr [rax+rax+00h]
0x140010c69  mov     rdx, [rsi+8]
0x140010c6d  movzx   r9d, al
0x140010c71  cmp     rdi, rdx
0x140010c74  jb      loc_140010D62
0x140010c7a  cmp     rdi, [rsi+10h]
0x140010c7e  ja      loc_140010D62
0x140010c84  mov     ecx, [rsi+18h]
0x140010c87  sub     rcx, rdx
0x140010c8a  lea     rdx, [rcx+rdi]
0x140010c8e  mov     ecx, [rsi+20h]
0x140010c91  mov     r8d, edx
0x140010c94  sub     r8d, ecx
0x140010c97  cmp     rdx, rcx
0x140010c9a  cmovb   r8d, edx
0x140010c9e  cmp     r8d, 0FFFFFFFFh
0x140010ca2  jz      loc_140010D62
0x140010ca8  cmp     ebp, r12d
0x140010cab  ja      loc_140010D99
0x140010cb1  xor     r15b, r15b
0x140010cb4  mov     r11d, 2
0x140010cba  xor     edi, edi
0x140010cbc  mov     edx, edi
0x140010cbe  mov     rcx, [rsi+28h]
0x140010cc2  lea     r10, [r8+r8]
0x140010cc6  xor     eax, eax
0x140010cc8  lock cmpxchg [r10+rcx], r11w
0x140010ccf  test    ax, ax
0x140010cd2  jnz     short loc_140010D3B
0x140010cd4  inc     edx
0x140010cd6  cmp     edx, ebp
0x140010cd8  jnz     loc_140010D86
0x140010cde  movzx   edx, r9b; OldIrql
0x140010ce2  mov     rcx, rsi; SpinLock
0x140010ce5  call    cs:__imp_ExReleaseSpinLockShared
0x140010cec  nop     dword ptr [rax+rax+00h]
0x140010cf1  mov     [r14], r12b
0x140010cf4  mov     eax, edi
0x140010cf6  test    r15b, r15b
0x140010cf9  jz      short loc_140010D2B
0x140010cfb  mov     [rbx+1E0h], r12d
0x140010d02  add     rsp, 20h
0x140010d06  pop     r15
0x140010d08  pop     r14
0x140010d0a  pop     r12
0x140010d0c  pop     rdi
0x140010d0d  pop     rsi
0x140010d0e  pop     rbp
0x140010d0f  pop     rbx
0x140010d10  retn
0x140010d12  xor     edi, edi
0x140010d14  mov     edx, 0FFFFh
0x140010d19  cmp     [rsi+2Ch], dx
0x140010d1d  mov     eax, edi
0x140010d1f  mov     ecx, 0C00000D0h
0x140010d24  cmovnz  eax, ecx
0x140010d27  cmp     eax, ecx
0x140010d29  jz      short loc_140010D7A
0x140010d2b  add     rsp, 20h
0x140010d2f  pop     r15
0x140010d31  pop     r14
0x140010d33  pop     r12
0x140010d35  pop     rdi
0x140010d36  pop     rsi
0x140010d37  pop     rbp
0x140010d38  pop     rbx
0x140010d39  retn
0x140010d3b  cmp     ax, r11w
0x140010d3f  jz      short loc_140010D62
0x140010d41  test    edx, edx
0x140010d43  jnz     short loc_140010D62
0x140010d45  mov     rcx, [rsi+28h]
0x140010d49  mov     eax, r12d
0x140010d4c  lock cmpxchg [r10+rcx], r11w
0x140010d53  cmp     ax, r12w
0x140010d57  jnz     short loc_140010D62
0x140010d59  movzx   r15d, r12b
0x140010d5d  jmp     loc_140010CD4
0x140010d62  movzx   edx, r9b; OldIrql
0x140010d66  mov     rcx, rsi; SpinLock
0x140010d69  call    cs:__imp_ExReleaseSpinLockShared
0x140010d70  nop     dword ptr [rax+rax+00h]
0x140010d75  mov     eax, 0C00000D0h
0x140010d7a  mov     dword ptr [rbx+1E8h], 0
0x140010d84  jmp     short loc_140010D2B
0x140010d86  lea     eax, [r8+1]
0x140010d8a  mov     r8d, edi
0x140010d8d  cmp     eax, [rsi+20h]
0x140010d90  cmovnz  r8d, eax
0x140010d94  jmp     loc_140010CBE
0x140010d99  lea     eax, [rbp-1]
0x140010d9c  add     rax, rdi
0x140010d9f  cmp     rax, rdi
0x140010da2  jb      short loc_140010D62
0x140010da4  cmp     rax, [rsi+10h]
0x140010da8  jbe     loc_140010CB1
0x140010dae  jmp     short loc_140010D62
0x140010db0  mov     rax, [rcx+60h]
0x140010db4  cmp     byte ptr [rax+1FEh], 0
0x140010dbb  jz      short loc_140010DD1
0x140010dbd  xor     edi, edi
0x140010dbf  mov     eax, edi
0x140010dc1  add     rsp, 20h
0x140010dc5  pop     r15
0x140010dc7  pop     r14
0x140010dc9  pop     r12
0x140010dcb  pop     rdi
0x140010dcc  pop     rsi
0x140010dcd  pop     rbp
0x140010dce  pop     rbx
0x140010dcf  retn
0x140010dd1  call    cs:__imp_SrvAdminAllowAnonymousAccess
0x140010dd8  nop     dword ptr [rax+rax+00h]
0x140010ddd  test    al, al
0x140010ddf  jz      short loc_140010D75
0x140010de1  jmp     short loc_140010DBD
```

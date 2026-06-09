# WimCbLocateObject

- ea: `0x14003c280`
- end: `0x14003c444`
- name: `WimCbLocateObject`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14002cc34`
- `0x14002e540`
- `0x14003c280`
- `0x14003c44c`
- `0x14003c518`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003c373`
- `ntoskrnl!RtlCompareMemory` at `0x14003c373`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003c428`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003c428`

## pseudocode

```c
__int64 __fastcall WimCbLocateObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7,
        int a8,
        __int64 a9)
{
  __int64 v9; // rdi
  __int64 result; // rax
  __int64 v14; // rsi
  __int64 v15; // r14
  char v16; // bp
  unsigned int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rcx
  bool v20; // zf
  __int64 v21; // [rsp+38h] [rbp-40h]
  __int64 v22; // [rsp+88h] [rbp+10h] BYREF

  v9 = a5;
  v22 = 0;
  result = WimFSFFindOverlayByDataSource(a2, *(_QWORD *)(a5 + 8), &v22);
  if ( (int)result >= 0 )
  {
    v14 = v22;
LABEL_6:
    v15 = 0;
    if ( (unsigned __int8)WimFSFAcquireRundownAndRemount(a1, a2, v14) )
    {
      v16 = 1;
      if ( *(_DWORD *)v9 == 1 )
      {
        v15 = WimFSFFindStreamResource(a1, v14, v9 + 16);
        if ( !v15 )
        {
LABEL_9:
          v17 = -1073741275;
          goto LABEL_23;
        }
      }
      else
      {
        v18 = *(_QWORD *)(v14 + 104);
        if ( (*(_DWORD *)(v18 + 100) & 2) != 0
          && RtlCompareMemory((const void *)(v9 + 36), (const void *)(v18 + 946), 0x14u) != 20 )
        {
          goto LABEL_9;
        }
      }
    }
    else
    {
      v16 = 0;
    }
    v19 = a9;
    if ( a9 )
    {
      *(_QWORD *)(a9 + 24) = v14;
      if ( v15 )
      {
        *(_OWORD *)(v19 + 4) = *(_OWORD *)(v15 + 30);
        *(_DWORD *)(v19 + 20) = *(_DWORD *)(v15 + 46);
        *(_QWORD *)(v19 + 40) = *(_QWORD *)v15 & 0xFFFFFFFFFFFFFFLL;
        *(_QWORD *)(v19 + 48) = *(_QWORD *)(v15 + 16);
        *(_QWORD *)(v19 + 56) = *(_QWORD *)(v15 + 8);
        v20 = (*(_BYTE *)(v15 + 7) & 4) == 0;
      }
      else
      {
        *(_OWORD *)(v19 + 4) = *(_OWORD *)(v9 + 16);
        *(_DWORD *)(v19 + 20) = *(_DWORD *)(v9 + 32);
        if ( *(_DWORD *)v9 != 2 )
        {
          *(_QWORD *)(v19 + 48) = a4;
          goto LABEL_22;
        }
        *(_QWORD *)(v19 + 40) = *(_QWORD *)(v9 + 64);
        *(_QWORD *)(v19 + 48) = *(_QWORD *)(v9 + 56);
        *(_QWORD *)(v19 + 56) = *(_QWORD *)(v9 + 72);
        v20 = *(_QWORD *)(v9 + 56) == *(_QWORD *)(v9 + 64);
      }
      if ( !v20 )
        *(_DWORD *)v19 |= 2u;
    }
LABEL_22:
    v17 = 0;
    if ( !v16 )
      return v17;
LABEL_23:
    ExReleaseRundownProtection(*(PEX_RUNDOWN_REF *)(v14 + 96));
    return v17;
  }
  if ( a7 )
  {
    result = WimFSFCreateOverlay(&v22, a2, 0, *(_QWORD *)(v9 + 8), 0, 0, 0, v21);
    if ( (int)result >= 0 )
    {
      v14 = v22;
      _InterlockedOr((volatile signed __int32 *)(v22 + 40), 4u);
      goto LABEL_6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003c280  mov     rax, rsp
0x14003c283  push    rbx
0x14003c284  push    rbp
0x14003c285  push    rsi
0x14003c286  push    rdi
0x14003c287  push    r14
0x14003c289  push    r15
0x14003c28b  sub     rsp, 48h
0x14003c28f  mov     rdi, [rsp+78h+arg_20]
0x14003c297  lea     r8, [rax+10h]
0x14003c29b  mov     rbp, rdx
0x14003c29e  mov     qword ptr [rax+10h], 0
0x14003c2a6  mov     r15, rcx
0x14003c2a9  mov     rbx, r9
0x14003c2ac  mov     rcx, rbp
0x14003c2af  mov     rdx, [rdi+8]
0x14003c2b3  call    WimFSFFindOverlayByDataSource
0x14003c2b8  test    eax, eax
0x14003c2ba  jns     short loc_14003C311
0x14003c2bc  cmp     [rsp+78h+arg_30], 0
0x14003c2c4  jz      loc_14003C436
0x14003c2ca  mov     r9, [rdi+8]
0x14003c2ce  lea     rcx, [rsp+78h+arg_8]
0x14003c2d6  mov     [rsp+78h+var_48], 0
0x14003c2de  xor     r8d, r8d
0x14003c2e1  mov     [rsp+78h+var_50], 0
0x14003c2e9  mov     rdx, rbp
0x14003c2ec  mov     [rsp+78h+var_58], 0
0x14003c2f5  call    WimFSFCreateOverlay
0x14003c2fa  test    eax, eax
0x14003c2fc  js      loc_14003C436
0x14003c302  mov     rsi, [rsp+78h+arg_8]
0x14003c30a  lock or dword ptr [rsi+28h], 4
0x14003c30f  jmp     short loc_14003C319
0x14003c311  mov     rsi, [rsp+78h+arg_8]
0x14003c319  mov     r8, rsi
0x14003c31c  mov     rdx, rbp
0x14003c31f  mov     rcx, r15
0x14003c322  xor     r14d, r14d
0x14003c325  call    WimFSFAcquireRundownAndRemount
0x14003c32a  test    al, al
0x14003c32c  jz      short loc_14003C387
0x14003c32e  lea     ebp, [r14+1]
0x14003c332  cmp     [rdi], ebp
0x14003c334  jnz     short loc_14003C357
0x14003c336  lea     r8, [rdi+10h]
0x14003c33a  mov     rdx, rsi
0x14003c33d  mov     rcx, r15
0x14003c340  call    WimFSFFindStreamResource
0x14003c345  mov     r14, rax
0x14003c348  test    rax, rax
0x14003c34b  jnz     short loc_14003C38A
0x14003c34d  mov     ebx, 0C0000225h
0x14003c352  jmp     loc_14003C424
0x14003c357  mov     rdx, [rsi+68h]
0x14003c35b  mov     eax, [rdx+64h]
0x14003c35e  test    al, 2
0x14003c360  jz      short loc_14003C38A
0x14003c362  add     rdx, 3B2h; Source2
0x14003c369  lea     rcx, [rdi+24h]; Source1
0x14003c36d  mov     r8d, 14h; Length
0x14003c373  call    cs:__imp_RtlCompareMemory
0x14003c37a  nop     dword ptr [rax+rax+00h]
0x14003c37f  cmp     rax, 14h
0x14003c383  jz      short loc_14003C38A
0x14003c385  jmp     short loc_14003C34D
0x14003c387  xor     bpl, bpl
0x14003c38a  mov     rcx, [rsp+78h+arg_40]
0x14003c392  test    rcx, rcx
0x14003c395  jz      loc_14003C41D
0x14003c39b  mov     [rcx+18h], rsi
0x14003c39f  test    r14, r14
0x14003c3a2  jz      short loc_14003C3DF
0x14003c3a4  movups  xmm0, xmmword ptr [r14+1Eh]
0x14003c3a9  mov     rdx, 0FFFFFFFFFFFFFFh
0x14003c3b3  movups  xmmword ptr [rcx+4], xmm0
0x14003c3b7  mov     eax, [r14+2Eh]
0x14003c3bb  mov     [rcx+14h], eax
0x14003c3be  mov     rax, [r14]
0x14003c3c1  and     rax, rdx
0x14003c3c4  mov     [rcx+28h], rax
0x14003c3c8  mov     rax, [r14+10h]
0x14003c3cc  mov     [rcx+30h], rax
0x14003c3d0  mov     rax, [r14+8]
0x14003c3d4  mov     [rcx+38h], rax
0x14003c3d8  test    byte ptr [r14+7], 4
0x14003c3dd  jmp     short loc_14003C412
0x14003c3df  movups  xmm0, xmmword ptr [rdi+10h]
0x14003c3e3  movups  xmmword ptr [rcx+4], xmm0
0x14003c3e7  mov     eax, [rdi+20h]
0x14003c3ea  mov     [rcx+14h], eax
0x14003c3ed  cmp     dword ptr [rdi], 2
0x14003c3f0  jnz     short loc_14003C419
0x14003c3f2  mov     rax, [rdi+40h]
0x14003c3f6  mov     [rcx+28h], rax
0x14003c3fa  mov     rax, [rdi+38h]
0x14003c3fe  mov     [rcx+30h], rax
0x14003c402  mov     rax, [rdi+48h]
0x14003c406  mov     [rcx+38h], rax
0x14003c40a  mov     rax, [rdi+40h]
0x14003c40e  cmp     [rdi+38h], rax
0x14003c412  jz      short loc_14003C41D
0x14003c414  or      dword ptr [rcx], 2
0x14003c417  jmp     short loc_14003C41D
0x14003c419  mov     [rcx+30h], rbx
0x14003c41d  xor     ebx, ebx
0x14003c41f  test    bpl, bpl
0x14003c422  jz      short loc_14003C434
0x14003c424  mov     rcx, [rsi+60h]; RunRef
0x14003c428  call    cs:__imp_ExReleaseRundownProtection
0x14003c42f  nop     dword ptr [rax+rax+00h]
0x14003c434  mov     eax, ebx
0x14003c436  add     rsp, 48h
0x14003c43a  pop     r15
0x14003c43c  pop     r14
0x14003c43e  pop     rdi
0x14003c43f  pop     rsi
0x14003c440  pop     rbp
0x14003c441  pop     rbx
0x14003c442  retn
```

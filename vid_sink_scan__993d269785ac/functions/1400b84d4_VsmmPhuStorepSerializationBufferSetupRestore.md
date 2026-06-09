# VsmmPhuStorepSerializationBufferSetupRestore

- ea: `0x1400b84d4`
- end: `0x1400b8840`
- name: `VsmmPhuStorepSerializationBufferSetupRestore`
- size: `876`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400b408c`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400b84d4`
- `0x1400b8848`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b87d1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b87d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400b858b`
- `ntoskrnl!ExAllocatePool2` at `0x1400b86f1`
- `ntoskrnl!ExAllocatePool2` at `0x1400b858b`
- `ntoskrnl!ExAllocatePool2` at `0x1400b86f1`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400b8538`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400b85e3`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400b8538`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400b85e3`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepSerializationBufferSetupRestore(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 Pool2; // rax
  unsigned int v10; // r8d
  unsigned int i; // edx
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // r10d
  _QWORD *j; // r8
  unsigned int v18; // ecx
  __int64 v19; // r11
  __int64 v20; // r9
  __int64 v21; // rax
  PVOID v22; // rax
  unsigned int v24; // [rsp+30h] [rbp-49h] BYREF
  int v25; // [rsp+34h] [rbp-45h] BYREF
  int v26; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v27; // [rsp+3Ch] [rbp-3Dh] BYREF
  char v28[32]; // [rsp+40h] [rbp-39h] BYREF
  char v29[16]; // [rsp+60h] [rbp-19h] BYREF
  char v30[16]; // [rsp+70h] [rbp-9h] BYREF
  int *v31; // [rsp+80h] [rbp+7h]
  __int64 v32; // [rsp+88h] [rbp+Fh]
  int *v33; // [rsp+90h] [rbp+17h]
  __int64 v34; // [rsp+98h] [rbp+1Fh]
  int *v35; // [rsp+A0h] [rbp+27h]
  __int64 v36; // [rsp+A8h] [rbp+2Fh]

  *(_OWORD *)a3 = 0;
  *(_OWORD *)(a3 + 16) = 0;
  *(_OWORD *)(a3 + 32) = 0;
  *(_QWORD *)(a3 + 48) = 0;
  *(_QWORD *)(a3 + 8) = a2;
  v24 = 0;
  v5 = KsrClaimPersistedMemory(a1, a2, 0, 0, 0, &v24);
  v6 = 0;
  if ( v5 != -1073741789 )
    v6 = v5;
  if ( v6 >= 0 )
  {
    v8 = v24;
    *(_DWORD *)(a3 + 32) = v24;
    Pool2 = ExAllocatePool2(258, 8 * v8, 1833788502);
    *(_QWORD *)(a3 + 24) = Pool2;
    if ( Pool2 )
    {
      v6 = KsrClaimPersistedMemory(a1, *(_QWORD *)(a3 + 8), Pool2, v24, 0, &v24);
      if ( v6 >= 0 )
      {
        v10 = 0;
        if ( v24 )
        {
          for ( i = 0; i < v24; ++i )
          {
            v12 = i;
            v10 += *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8 * v12) >> 40;
          }
        }
        v13 = v10;
        v14 = ExAllocatePool2(256, 8LL * v10 + 48, 1833788502);
        *(_QWORD *)(a3 + 16) = v14;
        if ( v14 )
        {
          *(_QWORD *)(v14 + 12) = 0;
          v15 = 0;
          *(_QWORD *)(v14 + 20) = 0;
          *(_DWORD *)(v14 + 28) = 0;
          *(_QWORD *)v14 = 0;
          *(_WORD *)(v14 + 8) = 8 * (v13 + 6);
          *(_QWORD *)(v14 + 32) = 0;
          *(_QWORD *)(v14 + 40) = v13 << 12;
          *(_WORD *)(v14 + 10) = 2;
          v16 = v24;
          for ( j = (_QWORD *)(*(_QWORD *)(a3 + 16) + 48LL); v15 < v16; ++v15 )
          {
            v18 = 0;
            v19 = *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL * v15) & 0xFFFFFFFFFFLL;
            v20 = *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL * v15) >> 40;
            if ( (_DWORD)v20 )
            {
              do
              {
                v21 = v18++;
                *j++ = v19 + v21;
              }
              while ( v18 < (unsigned int)v20 );
              v16 = v24;
            }
          }
          v22 = MmMapLockedPagesSpecifyCache(*(PMDL *)(a3 + 16), 0, MmCached, 0, 0, 0x40000010u);
          *(_QWORD *)a3 = v22;
          if ( v22 )
            return 0;
          v6 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VsmmPhuStorepSerializationBufferSetupRestore",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
            10515);
        }
        else
        {
          v6 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VsmmPhuStorepSerializationBufferSetupRestore",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
            10479);
        }
      }
      else if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v29, "VsmmPhuStorepSerializationBufferSetupRestore");
        tlgCreate1Sz_char(v30, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
        v25 = 10457;
        v31 = &v25;
        v32 = 4;
        v33 = &v26;
        v27 = v24;
        v26 = v6;
        v35 = (int *)&v27;
        v34 = 4;
        v36 = 4;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_14004EEAE, 0, 0, 7, v28);
      }
    }
    else
    {
      v6 = -1073741670;
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorepSerializationBufferSetupRestore",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        10442);
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepSerializationBufferSetupRestore",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      10423);
  }
  LOBYTE(v7) = 1;
  VsmmPhuStorepSerializationBufferTeardown(a1, v7, a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400b84d4  mov     [rsp-8+arg_8], rbx
0x1400b84d9  mov     [rsp-8+arg_18], rsi
0x1400b84de  push    rbp
0x1400b84df  push    rdi
0x1400b84e0  push    r14
0x1400b84e2  lea     rbp, [rsp-47h]
0x1400b84e7  sub     rsp, 0C0h
0x1400b84ee  mov     rax, cs:__security_cookie
0x1400b84f5  xor     rax, rsp
0x1400b84f8  mov     [rbp+57h+var_20], rax
0x1400b84fc  xorps   xmm0, xmm0
0x1400b84ff  xor     eax, eax
0x1400b8501  movups  xmmword ptr [r8], xmm0
0x1400b8505  mov     rdi, r8
0x1400b8508  xor     r14d, r14d
0x1400b850b  movups  xmmword ptr [r8+10h], xmm0
0x1400b8510  xor     r9d, r9d
0x1400b8513  mov     rsi, rcx
0x1400b8516  movups  xmmword ptr [r8+20h], xmm0
0x1400b851b  mov     [r8+30h], rax
0x1400b851f  lea     rax, [rbp+57h+var_A0]
0x1400b8523  mov     [r8+8], rdx
0x1400b8527  xor     r8d, r8d
0x1400b852a  mov     qword ptr [rsp+0D0h+Priority], rax
0x1400b852f  mov     [rsp+0D0h+BugCheckOnFailure], r14d
0x1400b8534  mov     [rbp+57h+var_A0], r14d
0x1400b8538  call    cs:__imp_KsrClaimPersistedMemory
0x1400b853f  nop     dword ptr [rax+rax+00h]
0x1400b8544  cmp     eax, 0C0000023h
0x1400b8549  mov     ebx, r14d
0x1400b854c  cmovnz  ebx, eax
0x1400b854f  test    ebx, ebx
0x1400b8551  jns     short loc_1400B8574
0x1400b8553  mov     r9d, ebx
0x1400b8556  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b855d  mov     r8d, 28B7h
0x1400b8563  lea     rcx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400b856a  call    VidTraceErrorStatusInternal0
0x1400b856f  jmp     loc_1400B8807
0x1400b8574  mov     eax, [rbp+57h+var_A0]
0x1400b8577  mov     ecx, 102h
0x1400b857c  mov     edx, eax
0x1400b857e  mov     [rdi+20h], eax
0x1400b8581  shl     rdx, 3
0x1400b8585  mov     r8d, 6D4D6456h
0x1400b858b  call    cs:__imp_ExAllocatePool2
0x1400b8592  nop     dword ptr [rax+rax+00h]
0x1400b8597  mov     [rdi+18h], rax
0x1400b859b  test    rax, rax
0x1400b859e  jnz     short loc_1400B85C7
0x1400b85a0  mov     r9d, 0C000009Ah
0x1400b85a6  mov     ebx, r9d
0x1400b85a9  mov     r8d, 28CAh
0x1400b85af  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b85b6  lea     rcx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400b85bd  call    VidTraceErrorStatusInternal0
0x1400b85c2  jmp     loc_1400B8807
0x1400b85c7  mov     r9d, [rbp+57h+var_A0]
0x1400b85cb  lea     rcx, [rbp+57h+var_A0]
0x1400b85cf  mov     rdx, [rdi+8]
0x1400b85d3  mov     r8, rax
0x1400b85d6  mov     qword ptr [rsp+0D0h+Priority], rcx
0x1400b85db  mov     rcx, rsi
0x1400b85de  mov     [rsp+0D0h+BugCheckOnFailure], r14d
0x1400b85e3  call    cs:__imp_KsrClaimPersistedMemory
0x1400b85ea  nop     dword ptr [rax+rax+00h]
0x1400b85ef  mov     ebx, eax
0x1400b85f1  test    eax, eax
0x1400b85f3  jns     loc_1400B86B4
0x1400b85f9  mov     ecx, cs:dword_140064110
0x1400b85ff  mov     eax, 2
0x1400b8604  cmp     ecx, eax
0x1400b8606  jbe     loc_1400B8807
0x1400b860c  mov     edx, 100h
0x1400b8611  lea     rcx, dword_140064110
0x1400b8618  call    _tlgKeywordOn
0x1400b861d  test    al, al
0x1400b861f  jz      loc_1400B8807
0x1400b8625  lea     rdx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400b862c  lea     rcx, [rbp+57h+var_70]
0x1400b8630  call    _tlgCreate1Sz_char
0x1400b8635  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b863c  lea     rcx, [rbp+57h+var_60]
0x1400b8640  call    _tlgCreate1Sz_char
0x1400b8645  lea     rax, [rbp+57h+var_9C]
0x1400b8649  mov     [rbp+57h+var_9C], 28D9h
0x1400b8650  mov     [rbp+57h+var_50], rax
0x1400b8654  lea     rdx, word_14004EEAE
0x1400b865b  lea     rax, [rbp+57h+var_98]
0x1400b865f  mov     [rbp+57h+var_48], 4
0x1400b8667  mov     [rbp+57h+var_40], rax
0x1400b866b  lea     rcx, dword_140064110
0x1400b8672  mov     eax, [rbp+57h+var_A0]
0x1400b8675  xor     r9d, r9d
0x1400b8678  mov     [rbp+57h+var_94], eax
0x1400b867b  xor     r8d, r8d
0x1400b867e  lea     rax, [rbp+57h+var_94]
0x1400b8682  mov     [rbp+57h+var_98], ebx
0x1400b8685  mov     [rbp+57h+var_30], rax
0x1400b8689  lea     rax, [rbp+57h+var_90]
0x1400b868d  mov     qword ptr [rsp+0D0h+Priority], rax
0x1400b8692  mov     [rsp+0D0h+BugCheckOnFailure], 7
0x1400b869a  mov     [rbp+57h+var_38], 4
0x1400b86a2  mov     [rbp+57h+var_28], 4
0x1400b86aa  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b86af  jmp     loc_1400B8807
0x1400b86b4  mov     r9d, [rbp+57h+var_A0]
0x1400b86b8  mov     r8d, r14d
0x1400b86bb  test    r9d, r9d
0x1400b86be  jz      short loc_1400B86DB
0x1400b86c0  mov     r10, [rdi+18h]
0x1400b86c4  mov     edx, r14d
0x1400b86c7  mov     eax, edx
0x1400b86c9  inc     edx
0x1400b86cb  mov     rcx, [r10+rax*8]
0x1400b86cf  shr     rcx, 28h
0x1400b86d3  add     r8d, ecx
0x1400b86d6  cmp     edx, r9d
0x1400b86d9  jb      short loc_1400B86C7
0x1400b86db  mov     ebx, r8d
0x1400b86de  mov     ecx, 100h
0x1400b86e3  mov     r8d, 6D4D6456h
0x1400b86e9  lea     rdx, ds:30h[rbx*8]
0x1400b86f1  call    cs:__imp_ExAllocatePool2
0x1400b86f8  nop     dword ptr [rax+rax+00h]
0x1400b86fd  mov     [rdi+10h], rax
0x1400b8701  mov     rcx, rax
0x1400b8704  test    rax, rax
0x1400b8707  jnz     short loc_1400B8730
0x1400b8709  mov     r9d, 0C000009Ah
0x1400b870f  mov     ebx, r9d
0x1400b8712  mov     r8d, 28EFh
0x1400b8718  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b871f  lea     rcx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400b8726  call    VidTraceErrorStatusInternal0
0x1400b872b  jmp     loc_1400B8807
0x1400b8730  mov     [rax+0Ch], r14
0x1400b8734  mov     edx, r14d
0x1400b8737  mov     [rax+14h], r14
0x1400b873b  mov     [rax+1Ch], r14d
0x1400b873f  mov     [rax], r14
0x1400b8742  lea     eax, [rbx+6]
0x1400b8745  shl     ax, 3
0x1400b8749  shl     rbx, 0Ch
0x1400b874d  mov     [rcx+8], ax
0x1400b8751  mov     [rcx+20h], r14
0x1400b8755  mov     [rcx+2Ch], r14d
0x1400b8759  mov     [rcx+28h], ebx
0x1400b875c  mov     word ptr [rcx+0Ah], 2
0x1400b8762  mov     r8, [rdi+10h]
0x1400b8766  mov     r10d, [rbp+57h+var_A0]
0x1400b876a  add     r8, 30h ; '0'
0x1400b876e  test    r10d, r10d
0x1400b8771  jz      short loc_1400B87B7
0x1400b8773  mov     rax, [rdi+18h]
0x1400b8777  mov     ecx, edx
0x1400b8779  mov     r9, [rax+rcx*8]
0x1400b877d  mov     rax, 0FFFFFFFFFFh
0x1400b8787  mov     r11, r9
0x1400b878a  mov     ecx, r14d
0x1400b878d  and     r11, rax
0x1400b8790  shr     r9, 28h
0x1400b8794  test    r9d, r9d
0x1400b8797  jz      short loc_1400B87B0
0x1400b8799  mov     eax, ecx
0x1400b879b  inc     ecx
0x1400b879d  add     rax, r11
0x1400b87a0  mov     [r8], rax
0x1400b87a3  add     r8, 8
0x1400b87a7  cmp     ecx, r9d
0x1400b87aa  jb      short loc_1400B8799
0x1400b87ac  mov     r10d, [rbp+57h+var_A0]
0x1400b87b0  inc     edx
0x1400b87b2  cmp     edx, r10d
0x1400b87b5  jb      short loc_1400B8773
0x1400b87b7  mov     rcx, [rdi+10h]; MemoryDescriptorList
0x1400b87bb  xor     r9d, r9d; RequestedAddress
0x1400b87be  mov     [rsp+0D0h+Priority], 40000010h; Priority
0x1400b87c6  xor     edx, edx; AccessMode
0x1400b87c8  mov     [rsp+0D0h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x1400b87cd  lea     r8d, [r9+1]; CacheType
0x1400b87d1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400b87d8  nop     dword ptr [rax+rax+00h]
0x1400b87dd  mov     [rdi], rax
0x1400b87e0  test    rax, rax
0x1400b87e3  jnz     short loc_1400B8816
0x1400b87e5  mov     r9d, 0C000009Ah
0x1400b87eb  mov     ebx, r9d
0x1400b87ee  mov     r8d, 2913h
0x1400b87f4  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b87fb  lea     rcx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400b8802  call    VidTraceErrorStatusInternal0
0x1400b8807  mov     r8, rdi
0x1400b880a  mov     dl, 1
0x1400b880c  mov     rcx, rsi
0x1400b880f  call    VsmmPhuStorepSerializationBufferTeardown
0x1400b8814  jmp     short loc_1400B8819
0x1400b8816  mov     ebx, r14d
0x1400b8819  mov     eax, ebx
0x1400b881b  mov     rcx, [rbp+57h+var_20]
0x1400b881f  xor     rcx, rsp; StackCookie
0x1400b8822  call    __security_check_cookie
0x1400b8827  lea     r11, [rsp+0D0h+var_10]
0x1400b882f  mov     rbx, [r11+28h]
0x1400b8833  mov     rsi, [r11+38h]
0x1400b8837  mov     rsp, r11
0x1400b883a  pop     r14
0x1400b883c  pop     rdi
0x1400b883d  pop     rbp
0x1400b883e  retn
```

# TdxDisassociateConnection

- ea: `0x1400039c0`
- end: `0x140003c94`
- name: `TdxDisassociateConnection`
- size: `724`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140005fe0`

## callees

- `0x1400039c0`
- `0x1400054ec`
- `0x1400087a0`
- `0x14001303c`
- `0x140013bf8`
- `0x140013dc0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003bb8`
- `ntoskrnl!IofCompleteRequest` at `0x140003bb8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a7e`
- `ntoskrnl!RtlGetCallersAddress` at `0x140003ad7`
- `ntoskrnl!RtlGetCallersAddress` at `0x140003ad7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003a28`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003aff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003b17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bce`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003a28`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003aff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003b17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bce`

## pseudocode

```c
__int64 __fastcall TdxDisassociateConnection(__int64 a1, __int64 a2, void *a3)
{
  KIRQL v4; // al
  __int64 v5; // rbp
  KIRQL v6; // r15
  KIRQL v8; // al
  int v9; // ecx
  __int64 v10; // rdx
  KIRQL v11; // di
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rax
  IRP *v15; // rcx
  int v16; // r8d
  _OWORD v17[3]; // [rsp+30h] [rbp-38h] BYREF
  PVOID CallersAddress; // [rsp+80h] [rbp+18h] BYREF

  CallersAddress = a3;
  v17[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_qs(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      a1,
      (__int64)"TdxDisassociateConnection");
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v5 = *(_QWORD *)(a1 + 88);
  v6 = v4;
  if ( v5 )
  {
    if ( (unsigned int)(*(_DWORD *)(a1 + 76) - 2) <= 4 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_sqd(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          v16,
          (unsigned int)"TdxDisassociateConnection",
          a1,
          *(_DWORD *)(a1 + 76),
          v17[0]);
      }
      return 3221226043LL;
    }
    else
    {
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 552));
      v9 = *(_DWORD *)(v5 + 16) + 1;
      v10 = v5 + 32LL * *(unsigned int *)(v5 + 816);
      CallersAddress = 0;
      v11 = v8;
      *(_DWORD *)(v10 + 584) = v9;
      *(_QWORD *)(v10 + 560) = "minio\\netio\\session\\tdi\\connection.c";
      *(_DWORD *)(v10 + 568) = 1203;
      RtlGetCallersAddress(&CallersAddress, (PVOID *)(v10 + 576));
      *(_DWORD *)(v5 + 816) = ((unsigned __int8)*(_DWORD *)(v5 + 816) + 1) & 7;
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 552), v11);
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 16));
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v6);
      *((_QWORD *)&v17[0] + 1) = v17;
      *(_QWORD *)&v17[0] = v17;
      v12 = TdxDisassociateConnectionFromTransportAddress(v5, a1, v17);
      DbgTdxDereferenceTransportAddress(v5, "minio\\netio\\session\\tdi\\connection.c", 1210);
      while ( 1 )
      {
        v13 = *(_QWORD *)&v17[0];
        if ( *(_OWORD **)&v17[0] == v17 )
          break;
        if ( *(_OWORD **)(*(_QWORD *)&v17[0] + 8LL) != v17
          || (v14 = **(_QWORD **)&v17[0], *(_QWORD *)(**(_QWORD **)&v17[0] + 8LL) != *(_QWORD *)&v17[0]) )
        {
          __fastfail(3u);
        }
        *(_QWORD *)&v17[0] = **(_QWORD **)&v17[0];
        *(_QWORD *)(v14 + 8) = v17;
        v15 = (IRP *)(v13 - 168);
        v15->IoStatus.Status = -1073741536;
        v15->IoStatus.Information = 0;
        IofCompleteRequest(v15, 2);
      }
      return v12;
    }
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v4);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_sq(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
        (unsigned int)"TdxDisassociateConnection",
        a1);
    }
    return 3221226041LL;
  }
}

```

## disassembly

```asm
0x1400039c0  mov     [rsp+arg_18], rbx
0x1400039c5  mov     [rsp+CallersAddress], r8
0x1400039ca  push    rbp
0x1400039cb  push    rsi
0x1400039cc  push    rdi
0x1400039cd  push    r14
0x1400039cf  push    r15
0x1400039d1  sub     rsp, 40h
0x1400039d5  xorps   xmm0, xmm0
0x1400039d8  mov     rbx, rcx
0x1400039db  movups  [rsp+68h+var_38], xmm0
0x1400039e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400039e7  lea     rdi, WPP_GLOBAL_Control
0x1400039ee  lea     rsi, aTdxdisassociat; "TdxDisassociateConnection"
0x1400039f5  cmp     rcx, rdi
0x1400039f8  jz      short loc_140003A04
0x1400039fa  cmp     byte ptr [rcx+29h], 5
0x1400039fe  jnb     loc_140003BF0
0x140003a04  lea     rcx, [rbx+8]; SpinLock
0x140003a08  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003a0f  nop     dword ptr [rax+rax+00h]
0x140003a14  mov     rbp, [rbx+58h]
0x140003a18  movzx   r15d, al
0x140003a1c  test    rbp, rbp
0x140003a1f  jnz     short loc_140003A5E
0x140003a21  movzx   edx, al; NewIrql
0x140003a24  lea     rcx, [rbx+8]; SpinLock
0x140003a28  call    cs:__imp_KeReleaseSpinLock
0x140003a2f  nop     dword ptr [rax+rax+00h]
0x140003a34  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a3b  cmp     rcx, rdi
0x140003a3e  jnz     loc_140003C1F
0x140003a44  mov     eax, 0C0000239h
0x140003a49  mov     rbx, [rsp+68h+arg_18]
0x140003a51  add     rsp, 40h
0x140003a55  pop     r15
0x140003a57  pop     r14
0x140003a59  pop     rdi
0x140003a5a  pop     rsi
0x140003a5b  pop     rbp
0x140003a5c  retn
0x140003a5e  mov     eax, [rbx+4Ch]
0x140003a61  sub     eax, 2
0x140003a64  cmp     eax, 4
0x140003a67  jbe     loc_140003BC6
0x140003a6d  mov     [rsp+68h+arg_0], r12
0x140003a72  lea     rcx, [rbp+228h]; SpinLock
0x140003a79  mov     [rsp+68h+arg_8], r13
0x140003a7e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003a85  nop     dword ptr [rax+rax+00h]
0x140003a8a  mov     ecx, [rbp+10h]
0x140003a8d  lea     r12, aMinioNetioSess_6; "minio\\netio\\session\\tdi\\connection."...
0x140003a94  mov     edx, [rbp+330h]
0x140003a9a  inc     ecx
0x140003a9c  shl     rdx, 5
0x140003aa0  xor     r13d, r13d
0x140003aa3  add     rdx, rbp
0x140003aa6  mov     [rsp+68h+CallersAddress], r13
0x140003aae  movzx   edi, al
0x140003ab1  mov     [rdx+248h], ecx
0x140003ab7  lea     rcx, [rsp+68h+CallersAddress]; CallersAddress
0x140003abf  mov     [rdx+230h], r12
0x140003ac6  mov     dword ptr [rdx+238h], 4B3h
0x140003ad0  add     rdx, 240h; CallersCaller
0x140003ad7  call    cs:__imp_RtlGetCallersAddress
0x140003ade  nop     dword ptr [rax+rax+00h]
0x140003ae3  mov     eax, [rbp+330h]
0x140003ae9  lea     rcx, [rbp+228h]; SpinLock
0x140003af0  inc     eax
0x140003af2  movzx   edx, dil; NewIrql
0x140003af6  and     eax, 7
0x140003af9  mov     [rbp+330h], eax
0x140003aff  call    cs:__imp_KeReleaseSpinLock
0x140003b06  nop     dword ptr [rax+rax+00h]
0x140003b0b  lock inc dword ptr [rbp+10h]
0x140003b0f  movzx   edx, r15b; NewIrql
0x140003b13  lea     rcx, [rbx+8]; SpinLock
0x140003b17  call    cs:__imp_KeReleaseSpinLock
0x140003b1e  nop     dword ptr [rax+rax+00h]
0x140003b23  lea     rax, [rsp+68h+var_38]
0x140003b28  mov     rdx, rbx
0x140003b2b  mov     qword ptr [rsp+68h+var_38+8], rax
0x140003b30  lea     r8, [rsp+68h+var_38]
0x140003b35  lea     rax, [rsp+68h+var_38]
0x140003b3a  mov     rcx, rbp
0x140003b3d  mov     qword ptr [rsp+68h+var_38], rax
0x140003b42  call    TdxDisassociateConnectionFromTransportAddress
0x140003b47  mov     r8d, 4BAh
0x140003b4d  mov     rdx, r12
0x140003b50  mov     rcx, rbp
0x140003b53  mov     ebx, eax
0x140003b55  call    DbgTdxDereferenceTransportAddress
0x140003b5a  mov     r12, [rsp+68h+arg_0]
0x140003b5f  mov     rcx, qword ptr [rsp+68h+var_38]
0x140003b64  lea     rax, [rsp+68h+var_38]
0x140003b69  cmp     rcx, rax
0x140003b6c  jnz     short loc_140003B7A
0x140003b6e  mov     r13, [rsp+68h+arg_8]
0x140003b73  mov     eax, ebx
0x140003b75  jmp     loc_140003A49
0x140003b7a  lea     rax, [rsp+68h+var_38]
0x140003b7f  cmp     [rcx+8], rax
0x140003b83  jnz     loc_140003C8D
0x140003b89  mov     rax, [rcx]
0x140003b8c  cmp     [rax+8], rcx
0x140003b90  jnz     loc_140003C8D
0x140003b96  mov     qword ptr [rsp+68h+var_38], rax
0x140003b9b  lea     rdx, [rsp+68h+var_38]
0x140003ba0  mov     [rax+8], rdx
0x140003ba4  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140003bab  mov     dl, 2; PriorityBoost
0x140003bad  mov     dword ptr [rcx+30h], 0C0000120h
0x140003bb4  mov     [rcx+38h], r13
0x140003bb8  call    cs:__imp_IofCompleteRequest
0x140003bbf  nop     dword ptr [rax+rax+00h]
0x140003bc4  jmp     short loc_140003B5F
0x140003bc6  movzx   edx, r15b; NewIrql
0x140003bca  lea     rcx, [rbx+8]; SpinLock
0x140003bce  call    cs:__imp_KeReleaseSpinLock
0x140003bd5  nop     dword ptr [rax+rax+00h]
0x140003bda  mov     rcx, cs:WPP_GLOBAL_Control
0x140003be1  cmp     rcx, rdi
0x140003be4  jnz     short loc_140003C58
0x140003be6  mov     eax, 0C000023Bh
0x140003beb  jmp     loc_140003A49
0x140003bf0  test    dword ptr [rcx+2Ch], 200h
0x140003bf7  jz      loc_140003A04
0x140003bfd  mov     rcx, [rcx+18h]
0x140003c01  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140003c08  mov     edx, 0Bh
0x140003c0d  mov     [rsp+68h+var_48], rsi
0x140003c12  mov     r9, rbx
0x140003c15  call    WPP_SF_qs
0x140003c1a  jmp     loc_140003A04
0x140003c1f  cmp     byte ptr [rcx+29h], 4
0x140003c23  jb      loc_140003A44
0x140003c29  test    dword ptr [rcx+2Ch], 200h
0x140003c30  jz      loc_140003A44
0x140003c36  mov     rcx, [rcx+18h]
0x140003c3a  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140003c41  mov     edx, 21h ; '!'
0x140003c46  mov     [rsp+68h+var_48], rbx
0x140003c4b  mov     r9, rsi
0x140003c4e  call    WPP_SF_sq
0x140003c53  jmp     loc_140003A44
0x140003c58  cmp     byte ptr [rcx+29h], 4
0x140003c5c  jb      short loc_140003BE6
0x140003c5e  test    dword ptr [rcx+2Ch], 200h
0x140003c65  jz      loc_140003BE6
0x140003c6b  mov     eax, [rbx+4Ch]
0x140003c6e  mov     edx, 22h ; '"'
0x140003c73  mov     rcx, [rcx+18h]
0x140003c77  mov     r9, rsi
0x140003c7a  mov     [rsp+68h+var_40], eax
0x140003c7e  mov     [rsp+68h+var_48], rbx
0x140003c83  call    WPP_SF_sqd
0x140003c88  jmp     loc_140003BE6
0x140003c8d  mov     ecx, 3
0x140003c92  int     29h; Win8: RtlFailFast(ecx)
```

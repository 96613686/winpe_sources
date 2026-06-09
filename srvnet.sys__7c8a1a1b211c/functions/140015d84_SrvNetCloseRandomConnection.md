# SrvNetCloseRandomConnection

- ea: `0x140015d84`
- end: `0x140015ede`
- name: `SrvNetCloseRandomConnection`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400109a8`

## callees

- `0x14000380c`
- `0x14000bbcc`
- `0x140015d84`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015e22`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e8c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015ebe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e22`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e8c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015ebe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015dda`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015e43`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015ead`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015dda`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015e43`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015ead`
- `cng!SystemPrng` at `0x140015daa`
- `cng!SystemPrng` at `0x140015daa`

## pseudocode

```c
void __fastcall SrvNetCloseRandomConnection(__int64 a1)
{
  KSPIN_LOCK *v2; // rsi
  int v3; // ebx
  char v4; // r14
  KIRQL v5; // al
  unsigned int v6; // r8d
  KIRQL v7; // dl
  _QWORD *v8; // rcx
  volatile signed __int32 *v9; // rbp
  KIRQL v10; // al
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  volatile signed __int32 *v13; // rdi
  unsigned int v14; // [rsp+48h] [rbp+10h] BYREF

  v14 = 0;
  if ( (unsigned int)SystemPrng(&v14, 4) )
  {
    v2 = (KSPIN_LOCK *)(a1 + 24);
    v3 = 0;
    v4 = 0;
    v14 %= *(_DWORD *)(a1 + 180);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
    v6 = v14;
    v7 = v5;
    v8 = *(_QWORD **)(a1 + 224);
    while ( v8 != (_QWORD *)(a1 + 224) )
    {
      v9 = (volatile signed __int32 *)(v8 - 64);
      v8 = (_QWORD *)*v8;
      if ( !*((_BYTE *)v9 + 493) )
      {
        if ( v3 == v14 )
        {
          v4 = 1;
          _InterlockedIncrement(v9);
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 24), v5);
          SrvNetDisconnectConnectionInternalEx(v9, 0);
          SrvNetDereferenceConnection((PVOID)v9);
          v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
          v6 = v14;
          v7 = v10;
          break;
        }
        ++v3;
      }
    }
    v11 = (_QWORD *)(a1 + 240);
    v12 = *(_QWORD **)(a1 + 240);
    if ( !v4 )
    {
      while ( v12 != v11 )
      {
        v13 = (volatile signed __int32 *)(v12 - 64);
        v12 = (_QWORD *)*v12;
        if ( !*((_BYTE *)v13 + 493) )
        {
          if ( v3 == v6 )
          {
            _InterlockedIncrement(v13);
            KeReleaseSpinLock(v2, v7);
            SrvNetDisconnectConnectionInternalEx(v13, 0);
            SrvNetDereferenceConnection((PVOID)v13);
            v7 = KeAcquireSpinLockRaiseToDpc(v2);
            break;
          }
          ++v3;
        }
      }
    }
    KeReleaseSpinLock(v2, v7);
  }
}

```

## disassembly

```asm
0x140015d84  mov     rax, rsp
0x140015d87  mov     [rax+8], rbx
0x140015d8b  mov     [rax+18h], rbp
0x140015d8f  push    rsi
0x140015d90  push    rdi
0x140015d91  push    r14
0x140015d93  sub     rsp, 20h
0x140015d97  mov     rdi, rcx
0x140015d9a  mov     dword ptr [rax+10h], 0
0x140015da1  lea     rcx, [rax+10h]
0x140015da5  mov     edx, 4
0x140015daa  call    cs:__imp_SystemPrng
0x140015db1  nop     dword ptr [rax+rax+00h]
0x140015db6  test    eax, eax
0x140015db8  jz      loc_140015ECA
0x140015dbe  mov     eax, [rsp+38h+arg_8]
0x140015dc2  lea     rsi, [rdi+18h]
0x140015dc6  xor     edx, edx
0x140015dc8  xor     ebx, ebx
0x140015dca  div     dword ptr [rdi+0B4h]
0x140015dd0  xor     r14b, r14b
0x140015dd3  mov     rcx, rsi; SpinLock
0x140015dd6  mov     [rsp+38h+arg_8], edx
0x140015dda  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015de1  nop     dword ptr [rax+rax+00h]
0x140015de6  mov     r8d, [rsp+38h+arg_8]
0x140015deb  mov     dl, al; NewIrql
0x140015ded  lea     rax, [rdi+0E0h]
0x140015df4  mov     rcx, [rax]
0x140015df7  cmp     rcx, rax
0x140015dfa  jz      short loc_140015E56
0x140015dfc  lea     rbp, [rcx-200h]
0x140015e03  mov     rcx, [rcx]
0x140015e06  cmp     [rbp+1EDh], r14b
0x140015e0d  jnz     short loc_140015DF7
0x140015e0f  cmp     ebx, r8d
0x140015e12  jz      short loc_140015E18
0x140015e14  inc     ebx
0x140015e16  jmp     short loc_140015DF7
0x140015e18  mov     r14b, 1
0x140015e1b  lock inc dword ptr [rbp+0]
0x140015e1f  mov     rcx, rsi; SpinLock
0x140015e22  call    cs:__imp_KeReleaseSpinLock
0x140015e29  nop     dword ptr [rax+rax+00h]
0x140015e2e  xor     edx, edx
0x140015e30  mov     rcx, rbp
0x140015e33  call    SrvNetDisconnectConnectionInternalEx
0x140015e38  mov     rcx, rbp; P
0x140015e3b  call    SrvNetDereferenceConnection
0x140015e40  mov     rcx, rsi; SpinLock
0x140015e43  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015e4a  nop     dword ptr [rax+rax+00h]
0x140015e4f  mov     r8d, [rsp+38h+arg_8]
0x140015e54  mov     dl, al; NewIrql
0x140015e56  lea     rcx, [rdi+0F0h]
0x140015e5d  mov     rax, [rcx]
0x140015e60  test    r14b, r14b
0x140015e63  jnz     short loc_140015EBB
0x140015e65  cmp     rax, rcx
0x140015e68  jz      short loc_140015EBB
0x140015e6a  lea     rdi, [rax-200h]
0x140015e71  mov     rax, [rax]
0x140015e74  cmp     byte ptr [rdi+1EDh], 0
0x140015e7b  jnz     short loc_140015E65
0x140015e7d  cmp     ebx, r8d
0x140015e80  jz      short loc_140015E86
0x140015e82  inc     ebx
0x140015e84  jmp     short loc_140015E65
0x140015e86  lock inc dword ptr [rdi]
0x140015e89  mov     rcx, rsi; SpinLock
0x140015e8c  call    cs:__imp_KeReleaseSpinLock
0x140015e93  nop     dword ptr [rax+rax+00h]
0x140015e98  xor     edx, edx
0x140015e9a  mov     rcx, rdi
0x140015e9d  call    SrvNetDisconnectConnectionInternalEx
0x140015ea2  mov     rcx, rdi; P
0x140015ea5  call    SrvNetDereferenceConnection
0x140015eaa  mov     rcx, rsi; SpinLock
0x140015ead  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015eb4  nop     dword ptr [rax+rax+00h]
0x140015eb9  mov     dl, al; NewIrql
0x140015ebb  mov     rcx, rsi; SpinLock
0x140015ebe  call    cs:__imp_KeReleaseSpinLock
0x140015ec5  nop     dword ptr [rax+rax+00h]
0x140015eca  mov     rbx, [rsp+38h+arg_0]
0x140015ecf  mov     rbp, [rsp+38h+arg_10]
0x140015ed4  add     rsp, 20h
0x140015ed8  pop     r14
0x140015eda  pop     rdi
0x140015edb  pop     rsi
0x140015edc  retn
```

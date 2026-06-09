# SrvNetRdmaCloseSocket

- ea: `0x14001a050`
- end: `0x14001a242`
- name: `SrvNetRdmaCloseSocket`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000b960`

## callees

- `0x140001008`
- `0x140001040`
- `0x140015350`
- `0x140019c3c`
- `0x14001a050`
- `0x14002a3e0`
- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001a0ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a0ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a08d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a08d`
- `ntoskrnl!ExRundownCompleted` at `0x14001a0e6`
- `ntoskrnl!ExRundownCompleted` at `0x14001a0e6`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001a0d7`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001a0d7`

## pseudocode

```c
void __fastcall SrvNetRdmaCloseSocket(__int64 a1)
{
  KIRQL v2; // al
  char v3; // bl
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  char v11; // [rsp+40h] [rbp-49h] BYREF
  char v12; // [rsp+41h] [rbp-48h] BYREF
  __int64 v13; // [rsp+48h] [rbp-41h] BYREF
  __int64 v14; // [rsp+50h] [rbp-39h] BYREF
  __int64 v15[12]; // [rsp+60h] [rbp-29h] BYREF

  if ( *(_QWORD *)(a1 + 392) )
  {
    v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 80));
    v3 = *(_BYTE *)(a1 + 615);
    *(_BYTE *)(a1 + 615) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v2);
    if ( !v3 )
    {
      v4 = MEMORY[0xFFFFF78000000014];
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 648));
      ExRundownCompleted((PEX_RUNDOWN_REF)(a1 + 648));
      (*(void (__fastcall **)(_QWORD))(SmbdFastDispatch + 72))(*(_QWORD *)(a1 + 392));
      *(_QWORD *)(a1 + 392) = 0;
      SrvNetReleaseRdmaRundownProtection();
      v5 = (unsigned __int128)((MEMORY[0xFFFFF78000000014] - v4) * (__int128)0x346DC5D63886594BLL) >> 64;
      v6 = (MEMORY[0xFFFFF78000000014] - v4) / 10000;
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
      {
        v7 = *(_QWORD *)(a1 + 448);
        McTemplateK0xqzr1uu_EtwWriteTransfer(
          v7,
          v5,
          *(unsigned __int16 *)(v7 + 72) >> 1,
          v6,
          *(unsigned __int16 *)(v7 + 72) >> 1,
          *(_QWORD *)(v7 + 80),
          *(_BYTE *)(v7 + 145),
          *(_BYTE *)(v7 + 146));
      }
      if ( (unsigned int)dword_140036120 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn() )
        {
          v10 = *(_QWORD *)(a1 + 448);
          v15[4] = (__int64)&v13;
          v13 = 0x1000000;
          v15[6] = (__int64)&v14;
          v15[5] = 8;
          v14 = v6;
          v15[7] = 8;
          v11 = *(_BYTE *)(v10 + 145);
          v15[8] = (__int64)&v11;
          v15[9] = 1;
          v12 = *(_BYTE *)(v10 + 146);
          v15[10] = (__int64)&v12;
          v15[11] = 1;
          tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_1400319DF, v8, v9, 6u, (__int64)v15);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14001a050  mov     [rsp-8+arg_8], rbx
0x14001a055  mov     [rsp-8+arg_10], rsi
0x14001a05a  push    rbp
0x14001a05b  push    rdi
0x14001a05c  push    r14
0x14001a05e  lea     rbp, [rsp-47h]
0x14001a063  sub     rsp, 0D0h
0x14001a06a  mov     rax, cs:__security_cookie
0x14001a071  xor     rax, rsp
0x14001a074  mov     [rbp+57h+var_20], rax
0x14001a078  cmp     qword ptr [rcx+188h], 0
0x14001a080  mov     rsi, rcx
0x14001a083  jz      loc_14001A21D
0x14001a089  add     rcx, 50h ; 'P'; SpinLock
0x14001a08d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a094  nop     dword ptr [rax+rax+00h]
0x14001a099  mov     bl, [rsi+267h]
0x14001a09f  lea     rcx, [rsi+50h]; SpinLock
0x14001a0a3  mov     dl, al; NewIrql
0x14001a0a5  mov     byte ptr [rsi+267h], 1
0x14001a0ac  call    cs:__imp_KeReleaseSpinLock
0x14001a0b3  nop     dword ptr [rax+rax+00h]
0x14001a0b8  test    bl, bl
0x14001a0ba  jnz     loc_14001A21D
0x14001a0c0  mov     r14, 0FFFFF78000000014h
0x14001a0ca  lea     rdi, [rsi+288h]
0x14001a0d1  mov     rcx, rdi; RunRef
0x14001a0d4  mov     rbx, [r14]
0x14001a0d7  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14001a0de  nop     dword ptr [rax+rax+00h]
0x14001a0e3  mov     rcx, rdi; RunRef
0x14001a0e6  call    cs:__imp_ExRundownCompleted
0x14001a0ed  nop     dword ptr [rax+rax+00h]
0x14001a0f2  mov     rax, cs:SmbdFastDispatch
0x14001a0f9  mov     rcx, [rsi+188h]
0x14001a100  mov     rax, [rax+48h]
0x14001a104  call    _guard_dispatch_icall
0x14001a109  mov     qword ptr [rsi+188h], 0
0x14001a114  call    SrvNetReleaseRdmaRundownProtection
0x14001a119  mov     rcx, [r14]
0x14001a11c  mov     rax, 346DC5D63886594Bh
0x14001a126  sub     rcx, rbx
0x14001a129  imul    rcx
0x14001a12c  mov     rbx, rdx
0x14001a12f  sar     rbx, 0Bh
0x14001a133  mov     rax, rbx
0x14001a136  shr     rax, 3Fh
0x14001a13a  add     rbx, rax
0x14001a13d  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x14001a144  jz      short loc_14001A17F
0x14001a146  mov     rcx, [rsi+1C0h]
0x14001a14d  mov     r9, rbx
0x14001a150  mov     al, [rcx+92h]
0x14001a156  movzx   r8d, word ptr [rcx+48h]
0x14001a15b  mov     [rsp+0E0h+var_A8], al
0x14001a15f  mov     al, [rcx+91h]
0x14001a165  mov     [rsp+0E0h+var_B0], al
0x14001a169  mov     rax, [rcx+50h]
0x14001a16d  shr     r8d, 1
0x14001a170  mov     [rsp+0E0h+var_B8], rax
0x14001a175  mov     [rsp+0E0h+var_C0], r8d
0x14001a17a  call    McTemplateK0xqzr1uu_EtwWriteTransfer
0x14001a17f  mov     eax, cs:dword_140036120
0x14001a185  cmp     eax, 5
0x14001a188  jbe     loc_14001A21D
0x14001a18e  call    _tlgKeywordOn
0x14001a193  test    al, al
0x14001a195  jz      loc_14001A21D
0x14001a19b  mov     rcx, [rsi+1C0h]; int
0x14001a1a2  lea     rax, [rbp+57h+var_98]
0x14001a1a6  mov     [rbp+57h+var_60], rax
0x14001a1aa  lea     rdx, byte_1400319DF; int
0x14001a1b1  lea     rax, [rbp+57h+var_90]
0x14001a1b5  mov     [rbp+57h+var_98], 1000000h
0x14001a1bd  mov     [rbp+57h+var_50], rax
0x14001a1c1  mov     [rbp+57h+var_58], 8
0x14001a1c9  mov     [rbp+57h+var_90], rbx
0x14001a1cd  mov     [rbp+57h+var_48], 8
0x14001a1d5  mov     al, [rcx+91h]
0x14001a1db  mov     [rbp+57h+var_A0], al
0x14001a1de  lea     rax, [rbp+57h+var_A0]
0x14001a1e2  mov     [rbp+57h+var_40], rax
0x14001a1e6  mov     [rbp+57h+var_38], 1
0x14001a1ee  mov     al, [rcx+92h]
0x14001a1f4  mov     [rbp+57h+var_9F], al
0x14001a1f7  lea     rax, [rbp+57h+var_9F]
0x14001a1fb  mov     [rbp+57h+var_30], rax
0x14001a1ff  lea     rax, [rbp+57h+var_80]
0x14001a203  mov     [rsp+0E0h+var_B8], rax; __int64
0x14001a208  mov     [rsp+0E0h+var_C0], 6; ULONG
0x14001a210  mov     [rbp+57h+var_28], 1
0x14001a218  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001a21d  mov     rcx, [rbp+57h+var_20]
0x14001a221  xor     rcx, rsp; StackCookie
0x14001a224  call    __security_check_cookie
0x14001a229  lea     r11, [rsp+0E0h+var_10]
0x14001a231  mov     rbx, [r11+28h]
0x14001a235  mov     rsi, [r11+30h]
0x14001a239  mov     rsp, r11
0x14001a23c  pop     r14
0x14001a23e  pop     rdi
0x14001a23f  pop     rbp
0x14001a240  retn
```

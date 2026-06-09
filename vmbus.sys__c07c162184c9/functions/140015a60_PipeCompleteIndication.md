# PipeCompleteIndication

- ea: `0x140015a60`
- end: `0x140015bf1`
- name: `PipeCompleteIndication`
- size: `401`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140002d20`
- `0x1400150a0`
- `0x140015a60`
- `0x1400164b4`
- `0x140016588`
- `0x140016c48`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140015bcd`
- `ntoskrnl!KeSetEvent` at `0x140015bcd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015a8b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015a8b`

## pseudocode

```c
LONG __fastcall PipeCompleteIndication(PKSPIN_LOCK SpinLock, unsigned int a2)
{
  char v4; // bp
  unsigned int v5; // esi
  unsigned int v6; // eax
  int v7; // eax
  struct _KEVENT *v8; // rdi
  LONG result; // eax
  unsigned int v10; // [rsp+60h] [rbp+8h] BYREF
  _DWORD *v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = 0;
  v4 = 0;
  KeAcquireSpinLockRaiseToDpc(SpinLock);
  v10 = a2;
  if ( *((_DWORD *)SpinLock + 2) != 7 )
  {
    v5 = *((_DWORD *)SpinLock + 33);
    while ( 1 )
    {
      v6 = *((_DWORD *)SpinLock + 74);
      if ( v5 > v6 )
      {
        if ( a2 < v5 && a2 > v6 )
          goto LABEL_6;
      }
      else if ( a2 > v6 || a2 < v5 )
      {
        goto LABEL_6;
      }
      v7 = PipeValidateIndicationPacket((_DWORD)SpinLock, (unsigned int)&v10, (unsigned int)&v11, 0, 0);
      if ( v7 == -1073741807 )
        break;
      if ( v7 < 0 )
        goto LABEL_6;
      if ( v4 )
      {
        if ( *v11 == 1 )
          goto LABEL_22;
        if ( *v11 != 5 )
        {
LABEL_6:
          *((_DWORD *)SpinLock + 76) = a2;
LABEL_21:
          *((_DWORD *)SpinLock + 2) = 7;
          goto LABEL_22;
        }
      }
      else
      {
        if ( *v11 != 1 )
          goto LABEL_6;
        *v11 = 5;
        if ( a2 != v5 )
          goto LABEL_22;
        v4 = 1;
      }
      a2 = v10;
    }
    if ( v10 != *((_DWORD *)SpinLock + 74) || !v4 )
    {
      *((_DWORD *)SpinLock + 76) = v10;
      goto LABEL_21;
    }
  }
LABEL_22:
  --*((_DWORD *)SpinLock + 75);
  if ( *((_DWORD *)SpinLock + 2) != 7 && v4 && (int)PkCompleteRemoval(SpinLock + 8) < 0 )
  {
    *((_DWORD *)SpinLock + 2) = 7;
    *((_DWORD *)SpinLock + 76) = a2;
  }
  v8 = (struct _KEVENT *)SpinLock[44];
  if ( v8 && (unsigned __int8)PipeIndicationsDone(SpinLock) )
  {
    SpinLock[44] = 0;
  }
  else
  {
    v8 = 0;
    PipePollForIndicationsLocked(SpinLock);
  }
  result = PipeUnlockAndSendInterrupt(SpinLock);
  if ( v8 )
    return KeSetEvent(v8, 0, 0);
  return result;
}

```

## disassembly

```asm
0x140015a60  mov     [rsp+arg_10], rbx
0x140015a65  mov     [rsp+arg_18], rbp
0x140015a6a  push    rsi
0x140015a6b  push    rdi
0x140015a6c  push    r13
0x140015a6e  push    r14
0x140015a70  push    r15
0x140015a72  sub     rsp, 30h
0x140015a76  mov     rdi, rdx
0x140015a79  mov     [rsp+58h+arg_8], 0
0x140015a82  mov     rbx, rcx
0x140015a85  xor     bpl, bpl
0x140015a88  xor     r14b, r14b
0x140015a8b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015a92  nop     dword ptr [rax+rax+00h]
0x140015a97  mov     r13d, 7
0x140015a9d  mov     [rsp+58h+arg_0], edi
0x140015aa1  mov     r15b, al
0x140015aa4  cmp     [rbx+8], r13d
0x140015aa8  jz      loc_140015B4A
0x140015aae  mov     esi, [rbx+84h]
0x140015ab4  mov     eax, [rbx+128h]
0x140015aba  cmp     esi, eax
0x140015abc  ja      short loc_140015ACE
0x140015abe  cmp     edi, eax
0x140015ac0  ja      short loc_140015AC6
0x140015ac2  cmp     edi, esi
0x140015ac4  jnb     short loc_140015AD6
0x140015ac6  mov     [rbx+130h], edi
0x140015acc  jmp     short loc_140015B46
0x140015ace  cmp     edi, esi
0x140015ad0  jnb     short loc_140015AD6
0x140015ad2  cmp     edi, eax
0x140015ad4  ja      short loc_140015AC6
0x140015ad6  xor     r9d, r9d
0x140015ad9  mov     [rsp+58h+var_38], 0
0x140015ae2  lea     r8, [rsp+58h+arg_8]
0x140015ae7  mov     rcx, rbx
0x140015aea  lea     rdx, [rsp+58h+arg_0]
0x140015aef  call    PipeValidateIndicationPacket
0x140015af4  cmp     eax, 0C0000011h
0x140015af9  jz      short loc_140015B2F
0x140015afb  test    eax, eax
0x140015afd  js      short loc_140015AC6
0x140015aff  mov     rax, [rsp+58h+arg_8]
0x140015b04  test    bpl, bpl
0x140015b07  jnz     short loc_140015B1D
0x140015b09  cmp     dword ptr [rax], 1
0x140015b0c  jnz     short loc_140015AC6
0x140015b0e  mov     dword ptr [rax], 5
0x140015b14  cmp     edi, esi
0x140015b16  jnz     short loc_140015B4A
0x140015b18  mov     bpl, 1
0x140015b1b  jmp     short loc_140015B29
0x140015b1d  mov     ecx, [rax]
0x140015b1f  cmp     ecx, 1
0x140015b22  jz      short loc_140015B4A
0x140015b24  cmp     ecx, 5
0x140015b27  jnz     short loc_140015AC6
0x140015b29  mov     edi, [rsp+58h+arg_0]
0x140015b2d  jmp     short loc_140015AB4
0x140015b2f  mov     eax, [rsp+58h+arg_0]
0x140015b33  cmp     eax, [rbx+128h]
0x140015b39  jnz     short loc_140015B40
0x140015b3b  test    bpl, bpl
0x140015b3e  jnz     short loc_140015B4A
0x140015b40  mov     [rbx+130h], eax
0x140015b46  mov     [rbx+8], r13d
0x140015b4a  dec     dword ptr [rbx+12Ch]
0x140015b50  cmp     [rbx+8], r13d
0x140015b54  jz      short loc_140015B80
0x140015b56  test    bpl, bpl
0x140015b59  jz      short loc_140015B80
0x140015b5b  lea     rcx, [rbx+40h]
0x140015b5f  mov     edx, edi
0x140015b61  call    PkCompleteRemoval
0x140015b66  cmp     eax, 214h
0x140015b6b  jnz     short loc_140015B72
0x140015b6d  mov     r14b, 1
0x140015b70  jmp     short loc_140015B80
0x140015b72  test    eax, eax
0x140015b74  jns     short loc_140015B80
0x140015b76  mov     [rbx+8], r13d
0x140015b7a  mov     [rbx+130h], edi
0x140015b80  mov     rdi, [rbx+160h]
0x140015b87  test    rdi, rdi
0x140015b8a  jz      short loc_140015BA5
0x140015b8c  mov     rcx, rbx
0x140015b8f  call    PipeIndicationsDone
0x140015b94  test    al, al
0x140015b96  jz      short loc_140015BA5
0x140015b98  mov     qword ptr [rbx+160h], 0
0x140015ba3  jmp     short loc_140015BAF
0x140015ba5  xor     edi, edi
0x140015ba7  mov     rcx, rbx
0x140015baa  call    PipePollForIndicationsLocked
0x140015baf  xor     r9d, r9d
0x140015bb2  mov     r8b, r14b
0x140015bb5  mov     dl, r15b
0x140015bb8  mov     rcx, rbx; SpinLock
0x140015bbb  call    PipeUnlockAndSendInterrupt
0x140015bc0  test    rdi, rdi
0x140015bc3  jz      short loc_140015BD9
0x140015bc5  xor     r8d, r8d; Wait
0x140015bc8  xor     edx, edx; Increment
0x140015bca  mov     rcx, rdi; Event
0x140015bcd  call    cs:__imp_KeSetEvent
0x140015bd4  nop     dword ptr [rax+rax+00h]
0x140015bd9  mov     rbx, [rsp+58h+arg_10]
0x140015bde  mov     rbp, [rsp+58h+arg_18]
0x140015be3  add     rsp, 30h
0x140015be7  pop     r15
0x140015be9  pop     r14
0x140015beb  pop     r13
0x140015bed  pop     rdi
0x140015bee  pop     rsi
0x140015bef  retn
```

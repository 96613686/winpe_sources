# SkmmCommitBasicEnclavePages

- ea: `0x14001ce38`
- end: `0x14001d0a6`
- name: `SkmmCommitBasicEnclavePages`
- size: `622`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, void *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140021428`

## callees

- `0x14000f0f0`
- `0x14000f8b0`
- `0x14001ce38`
- `0x14001d414`
- `0x14001df2c`
- `0x14001e4d8`
- `0x14003492c`
- `0x140037e68`
- `0x140065d00`
- `0x14006a4b8`
- `0x140095cd8`
- `0x1400b0014`
- `0x1400d4e8c`

## pseudocode

```c
__int64 __fastcall SkmmCommitBasicEnclavePages(unsigned __int64 a1, unsigned __int64 a2, void *a3, unsigned int a4)
{
  PVOID StackBase; // rdi
  unsigned int *v8; // rdi
  unsigned __int64 v9; // r14
  unsigned int v10; // edx
  unsigned __int64 v11; // rcx
  __int64 v12; // r8
  void *Pool; // rax
  void *v15; // rsi
  _QWORD *v16; // rcx
  __int64 v17; // rcx
  unsigned int *v18; // r12
  unsigned int v19; // edi
  unsigned int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // r8
  unsigned int *v24; // [rsp+30h] [rbp-38h]
  int v25; // [rsp+38h] [rbp-30h]
  int ProtectionMask; // [rsp+70h] [rbp+8h]

  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    v8 = (unsigned int *)*((_QWORD *)StackBase + 10);
  else
    v8 = 0;
  if ( (((unsigned __int16)a2 | (unsigned __int16)a1) & 0xFFF) != 0 )
    return 3221225485LL;
  v9 = a1 >> 12;
  v10 = v8[142];
  if ( a1 >> 12 < (v8[140] | ((unsigned __int64)(v10 & 0xFFF) << 32)) )
    return 3221225496LL;
  v11 = v9 + (a2 >> 12) - 1;
  v25 = v9 + (a2 >> 12) - 1;
  if ( v11 < v9 || v11 > (v8[141] | ((unsigned __int64)(v10 & 0xFFF000) << 20)) )
    return 3221225496LL;
  ProtectionMask = SkmiMakeProtectionMask(a4);
  if ( !ProtectionMask )
    return 3221225541LL;
  if ( a3 )
  {
    if ( v12 == 1 )
    {
      Pool = (void *)SkAllocatePool(512, 4096, 1346651478);
      v15 = Pool;
      if ( !Pool )
        return 3221225626LL;
      RtlCopyFromUser(Pool, a3, 0x1000u);
      goto LABEL_16;
    }
    return 3221225485LL;
  }
  v15 = 0;
LABEL_16:
  v16 = KeGetPcr()->NtTib.StackBase;
  if ( v16 )
  {
    v17 = v16[18];
    if ( v17 )
      --*(_WORD *)(v17 + xmmword_140167150);
  }
  v24 = v8 + 64;
  RtlAcquireSRWLockShared(v8 + 64);
  v18 = v8 + 134;
  SkmiLockVad(v8 + 134);
  if ( (unsigned __int8)SkpsBasicEnclaveThreadInRange(v8, a1, a1 + a2 - 1) )
  {
    v19 = -1073741800;
  }
  else
  {
    if ( v15 )
      v20 = SkmiCommitBasicEnclavePage((_DWORD)v8, a1 >> 12, 1, (_DWORD)v15, ProtectionMask);
    else
      v20 = SkmiCommitVirtualPageRange((_DWORD)v8, (int)v8 + 536, a1 >> 12, v25, ProtectionMask);
    v19 = v20;
  }
  SkmiUnlockVad(v18);
  RtlReleaseSRWLockShared(v24);
  v21 = KeGetPcr()->NtTib.StackBase;
  if ( v21 )
  {
    v22 = v21[18];
    if ( v22 )
    {
      if ( (*(_WORD *)(v22 + xmmword_140167150))++ == 0xFFFF
        && *(_QWORD *)(v22 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v21[17]
        && !*(_WORD *)(v22 + *((_QWORD *)&xmmword_140167150 + 1)) )
      {
        SkiCheckForKernelApcDelivery();
      }
    }
  }
  if ( v15 )
    SkFreePool(512, v15);
  return v19;
}

```

## disassembly

```asm
0x14001ce38  mov     [rsp+arg_10], rbx
0x14001ce3d  mov     [rsp+arg_18], rsi
0x14001ce42  mov     [rsp+arg_8], rdx
0x14001ce47  push    rdi
0x14001ce48  push    r12
0x14001ce4a  push    r13
0x14001ce4c  push    r14
0x14001ce4e  push    r15
0x14001ce50  sub     rsp, 40h
0x14001ce54  mov     r12, r8
0x14001ce57  mov     r8, rdx
0x14001ce5a  mov     r13, rcx
0x14001ce5d  mov     rdi, gs:8
0x14001ce66  xor     ebx, ebx
0x14001ce68  test    rdi, rdi
0x14001ce6b  jz      short loc_14001CE73
0x14001ce6d  mov     rdi, [rdi+50h]
0x14001ce71  jmp     short loc_14001CE76
0x14001ce73  mov     rdi, rbx
0x14001ce76  mov     eax, r13d
0x14001ce79  or      eax, r8d
0x14001ce7c  mov     r10d, 0FFFh
0x14001ce82  test    r10d, eax
0x14001ce85  jnz     loc_14001D086
0x14001ce8b  mov     r14, r13
0x14001ce8e  shr     r14, 0Ch
0x14001ce92  mov     edx, [rdi+238h]
0x14001ce98  mov     ecx, edx
0x14001ce9a  and     rcx, r10
0x14001ce9d  shl     rcx, 20h
0x14001cea1  mov     eax, [rdi+230h]
0x14001cea7  or      rcx, rax
0x14001ceaa  cmp     r14, rcx
0x14001cead  jb      loc_14001D07F
0x14001ceb3  shr     r8, 0Ch
0x14001ceb7  lea     rcx, [r8-1]
0x14001cebb  add     rcx, r14
0x14001cebe  mov     [rsp+68h+var_30], rcx
0x14001cec3  cmp     rcx, r14
0x14001cec6  jb      loc_14001D07F
0x14001cecc  and     edx, 0FFF000h
0x14001ced2  shl     rdx, 14h
0x14001ced6  mov     eax, [rdi+234h]
0x14001cedc  or      rdx, rax
0x14001cedf  cmp     rcx, rdx
0x14001cee2  ja      loc_14001D07F
0x14001cee8  mov     ecx, r9d
0x14001ceeb  call    SkmiMakeProtectionMask
0x14001cef0  mov     [rsp+68h+arg_0], eax
0x14001cef4  test    eax, eax
0x14001cef6  jnz     short loc_14001CF02
0x14001cef8  mov     eax, 0C0000045h
0x14001cefd  jmp     loc_14001D08B
0x14001cf02  mov     r15d, 1
0x14001cf08  test    r12, r12
0x14001cf0b  jz      short loc_14001CF64
0x14001cf0d  cmp     r8, r15
0x14001cf10  jnz     loc_14001D086
0x14001cf16  mov     edx, 1000h
0x14001cf1b  mov     ecx, 200h
0x14001cf20  mov     r8d, 50444556h
0x14001cf26  call    SkAllocatePool
0x14001cf2b  mov     rsi, rax
0x14001cf2e  mov     [rsp+68h+var_38], rax
0x14001cf33  test    rax, rax
0x14001cf36  jnz     short loc_14001CF42
0x14001cf38  mov     eax, 0C000009Ah
0x14001cf3d  jmp     loc_14001D08B
0x14001cf42  mov     r8d, 1000h; Size
0x14001cf48  mov     rdx, r12; Src
0x14001cf4b  mov     rcx, rax; void *
0x14001cf4e  call    RtlCopyFromUser
0x14001cf53  jmp     short loc_14001CF67
0x14001cf55  mov     edi, 0C0000005h
0x14001cf5a  mov     rsi, [rsp+68h+var_38]
0x14001cf5f  jmp     loc_14001D069
0x14001cf64  mov     rsi, rbx
0x14001cf67  mov     rcx, gs:8
0x14001cf70  test    rcx, rcx
0x14001cf73  jz      short loc_14001CF8D
0x14001cf75  mov     rcx, [rcx+90h]
0x14001cf7c  test    rcx, rcx
0x14001cf7f  jz      short loc_14001CF8D
0x14001cf81  mov     rax, qword ptr cs:xmmword_140167150
0x14001cf88  dec     word ptr [rcx+rax]
0x14001cf8c  nop
0x14001cf8d  lea     rax, [rdi+100h]
0x14001cf94  mov     [rsp+68h+var_38], rax
0x14001cf99  mov     rcx, rax
0x14001cf9c  call    RtlAcquireSRWLockShared
0x14001cfa1  lea     r12, [rdi+218h]
0x14001cfa8  mov     rcx, r12
0x14001cfab  call    SkmiLockVad
0x14001cfb0  mov     r8, [rsp+68h+arg_8]
0x14001cfb5  dec     r8
0x14001cfb8  add     r8, r13
0x14001cfbb  mov     rdx, r13
0x14001cfbe  mov     rcx, rdi
0x14001cfc1  call    SkpsBasicEnclaveThreadInRange
0x14001cfc6  test    al, al
0x14001cfc8  jz      short loc_14001CFD1
0x14001cfca  mov     edi, 0C0000018h
0x14001cfcf  jmp     short loc_14001D003
0x14001cfd1  mov     eax, [rsp+68h+arg_0]
0x14001cfd5  mov     rcx, rdi
0x14001cfd8  mov     [rsp+68h+var_48], eax
0x14001cfdc  test    rsi, rsi
0x14001cfdf  jz      short loc_14001CFF1
0x14001cfe1  mov     r9, rsi
0x14001cfe4  mov     r8d, r15d
0x14001cfe7  mov     rdx, r14
0x14001cfea  call    SkmiCommitBasicEnclavePage
0x14001cfef  jmp     short loc_14001D001
0x14001cff1  mov     r9, [rsp+68h+var_30]
0x14001cff6  mov     r8, r14
0x14001cff9  mov     rdx, r12
0x14001cffc  call    SkmiCommitVirtualPageRange
0x14001d001  mov     edi, eax
0x14001d003  mov     rcx, r12
0x14001d006  call    SkmiUnlockVad
0x14001d00b  mov     rcx, [rsp+68h+var_38]
0x14001d010  call    RtlReleaseSRWLockShared
0x14001d015  mov     rcx, gs:8
0x14001d01e  test    rcx, rcx
0x14001d021  jz      short loc_14001D069
0x14001d023  mov     r8, [rcx+90h]
0x14001d02a  test    r8, r8
0x14001d02d  jz      short loc_14001D069
0x14001d02f  nop
0x14001d030  mov     rax, qword ptr cs:xmmword_140167150
0x14001d037  add     [r8+rax], r15w
0x14001d03c  jnz     short loc_14001D069
0x14001d03e  mov     rax, [rcx+88h]
0x14001d045  nop
0x14001d046  mov     rdx, qword ptr cs:xmmword_140167160
0x14001d04d  add     rax, rdx
0x14001d050  cmp     [r8+rdx], rax
0x14001d054  jz      short loc_14001D069
0x14001d056  mov     rax, qword ptr cs:xmmword_140167150+8
0x14001d05d  cmp     [r8+rax], bx
0x14001d062  jnz     short loc_14001D069
0x14001d064  call    SkiCheckForKernelApcDelivery
0x14001d069  test    rsi, rsi
0x14001d06c  jz      short loc_14001D07B
0x14001d06e  mov     rdx, rsi
0x14001d071  mov     ecx, 200h
0x14001d076  call    SkFreePool
0x14001d07b  mov     eax, edi
0x14001d07d  jmp     short loc_14001D08B
0x14001d07f  mov     eax, 0C0000018h
0x14001d084  jmp     short loc_14001D08B
0x14001d086  mov     eax, 0C000000Dh
0x14001d08b  lea     r11, [rsp+68h+var_28]
0x14001d090  mov     rbx, [r11+40h]
0x14001d094  mov     rsi, [r11+48h]
0x14001d098  mov     rsp, r11
0x14001d09b  pop     r15
0x14001d09d  pop     r14
0x14001d09f  pop     r13
0x14001d0a1  pop     r12
0x14001d0a3  pop     rdi
0x14001d0a4  retn
```

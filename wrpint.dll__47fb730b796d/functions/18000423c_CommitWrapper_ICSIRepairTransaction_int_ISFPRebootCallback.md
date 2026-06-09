# CommitWrapper(ICSIRepairTransaction *,int *,ISFPRebootCallback *)

- ea: `0x18000423c`
- end: `0x1800043a5`
- name: `?CommitWrapper@@YAJPEAUICSIRepairTransaction@@PEAHPEAUISFPRebootCallback@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(struct ICSIRepairTransaction *, int *, struct ISFPRebootCallback *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002d00`
- `0x1800031c0`
- `0x180003a40`

## callees

- `0x18000423c`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CommitWrapper(struct ICSIRepairTransaction *a1, int *a2, struct ISFPRebootCallback *a3)
{
  __int64 v3; // rax
  int v7; // ebx
  __int64 v8; // rax
  struct ICSIRepairTransaction *v9; // rcx
  void (*v10)(void); // rax
  int v12; // [rsp+30h] [rbp-10h] BYREF
  int v13; // [rsp+34h] [rbp-Ch] BYREF

  v3 = *(_QWORD *)a1;
  v12 = 0;
  v13 = 1;
  v7 = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, __int64, _QWORD, int *))(v3 + 56))(a1, 14, 0, &v12);
  if ( v7 < 0 )
  {
    if ( v7 == -2147467259 && v12 == 5 )
      v7 = -2147483638;
    v8 = *(_QWORD *)a1;
    goto LABEL_19;
  }
  if ( v12 == 1 )
    return (unsigned int)v7;
  if ( v12 == 2 || (unsigned int)(v12 - 3) > 1 )
  {
    (*(void (__fastcall **)(struct ICSIRepairTransaction *, _QWORD, int *))(*(_QWORD *)a1 + 64LL))(a1, 0, &v12);
    return (unsigned int)-2147418113;
  }
  if ( a3 )
  {
    v7 = (*(__int64 (__fastcall **)(struct ISFPRebootCallback *, int *))(*(_QWORD *)a3 + 24LL))(a3, &v13);
    v8 = *(_QWORD *)a1;
    if ( v7 >= 0 )
    {
      v9 = a1;
      if ( v13 )
        goto LABEL_8;
LABEL_20:
      (*(void (__fastcall **)(struct ICSIRepairTransaction *, _QWORD, int *))(v8 + 64))(v9, 0, &v12);
      return (unsigned int)v7;
    }
LABEL_19:
    v9 = a1;
    goto LABEL_20;
  }
  v8 = *(_QWORD *)a1;
  v9 = a1;
LABEL_8:
  v7 = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, __int64, _QWORD, int *))(v8 + 56))(v9, 15, 0, &v12);
  if ( v7 < 0 || v12 != 2 )
  {
    (*(void (__fastcall **)(struct ICSIRepairTransaction *, _QWORD, int *))(*(_QWORD *)a1 + 64LL))(a1, 0, &v12);
    return 2147549183LL;
  }
  v10 = (void (*)(void))qword_18002B8B8;
  *a2 = 1;
  if ( v10 )
    v10();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000423c  push    rbp
0x18000423e  push    rbx
0x18000423f  push    rsi
0x180004240  push    rdi
0x180004241  push    r14
0x180004243  mov     rbp, rsp
0x180004246  sub     rsp, 40h
0x18000424a  mov     rax, cs:__security_cookie
0x180004251  xor     rax, rsp
0x180004254  mov     [rbp+var_8], rax
0x180004258  mov     rax, [rcx]
0x18000425b  lea     r9, [rbp+var_10]
0x18000425f  mov     rsi, r8
0x180004262  mov     [rbp+var_10], 0
0x180004269  xor     r8d, r8d
0x18000426c  mov     [rbp+var_C], 1
0x180004273  mov     r14, rdx
0x180004276  mov     rdi, rcx
0x180004279  mov     rax, [rax+38h]
0x18000427d  lea     edx, [r8+0Eh]
0x180004281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004286  mov     ebx, eax
0x180004288  test    eax, eax
0x18000428a  js      loc_180004363
0x180004290  mov     eax, [rbp+var_10]
0x180004293  sub     eax, 1
0x180004296  jz      loc_18000438C
0x18000429c  sub     eax, 1
0x18000429f  jz      loc_180004347
0x1800042a5  sub     eax, 1
0x1800042a8  jz      short loc_1800042B3
0x1800042aa  cmp     eax, 1
0x1800042ad  jnz     loc_180004347
0x1800042b3  test    rsi, rsi
0x1800042b6  jz      loc_18000433F
0x1800042bc  mov     rax, [rsi]
0x1800042bf  lea     rdx, [rbp+var_C]
0x1800042c3  mov     rcx, rsi
0x1800042c6  mov     rax, [rax+18h]
0x1800042ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042cf  mov     ebx, eax
0x1800042d1  mov     rax, [rdi]
0x1800042d4  test    ebx, ebx
0x1800042d6  js      loc_18000437A
0x1800042dc  cmp     [rbp+var_C], 0
0x1800042e0  mov     rcx, rdi
0x1800042e3  jz      loc_18000437D
0x1800042e9  mov     rax, [rax+38h]
0x1800042ed  lea     r9, [rbp+var_10]
0x1800042f1  xor     r8d, r8d
0x1800042f4  lea     edx, [r8+0Fh]
0x1800042f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042fd  mov     ebx, eax
0x1800042ff  test    eax, eax
0x180004301  js      short loc_180004323
0x180004303  cmp     [rbp+var_10], 2
0x180004307  jnz     short loc_180004323
0x180004309  mov     rax, cs:qword_18002B8B8
0x180004310  mov     dword ptr [r14], 1
0x180004317  test    rax, rax
0x18000431a  jz      short loc_18000438C
0x18000431c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004321  jmp     short loc_18000438C
0x180004323  mov     rax, [rdi]
0x180004326  lea     r8, [rbp+var_10]
0x18000432a  xor     edx, edx
0x18000432c  mov     rcx, rdi
0x18000432f  mov     rax, [rax+40h]
0x180004333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004338  mov     eax, 8000FFFFh
0x18000433d  jmp     short loc_18000438E
0x18000433f  mov     rax, [rdi]
0x180004342  mov     rcx, rdi
0x180004345  jmp     short loc_1800042E9
0x180004347  mov     rax, [rdi]
0x18000434a  lea     r8, [rbp+var_10]
0x18000434e  xor     edx, edx
0x180004350  mov     rcx, rdi
0x180004353  mov     rax, [rax+40h]
0x180004357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000435c  mov     ebx, 8000FFFFh
0x180004361  jmp     short loc_18000438C
0x180004363  cmp     ebx, 80004005h
0x180004369  jnz     short loc_180004377
0x18000436b  cmp     [rbp+var_10], 5
0x18000436f  mov     eax, 8000000Ah
0x180004374  cmovz   ebx, eax
0x180004377  mov     rax, [rdi]
0x18000437a  mov     rcx, rdi
0x18000437d  mov     rax, [rax+40h]
0x180004381  lea     r8, [rbp+var_10]
0x180004385  xor     edx, edx
0x180004387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000438c  mov     eax, ebx
0x18000438e  mov     rcx, [rbp+var_8]
0x180004392  xor     rcx, rsp; StackCookie
0x180004395  call    __security_check_cookie
0x18000439a  add     rsp, 40h
0x18000439e  pop     r14
0x1800043a0  pop     rdi
0x1800043a1  pop     rsi
0x1800043a2  pop     rbx
0x1800043a3  pop     rbp
0x1800043a4  retn
```

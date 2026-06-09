# LOCK_SET::AddUriLock(IPubLock *)

- ea: `0x180003450`
- end: `0x180003522`
- name: `?AddUriLock@LOCK_SET@@UEAAJPEAVIPubLock@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(LOCK_SET *__hidden this, struct IPubLock *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003058`
- `0x180003450`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall LOCK_SET::AddUriLock(LOCK_SET *this, struct IPubLock *a2)
{
  int v4; // edi
  unsigned int v5; // r8d
  char *v6; // r9
  unsigned __int16 *v7; // rdx
  unsigned __int16 v8; // ax
  unsigned __int16 v9; // cx
  unsigned int v10; // r8d
  struct LOCK_ENTRY *v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = 0;
  v4 = URI_LOCK_LIST::AddLock2((LOCK_SET *)((char *)this + 8), a2, &v12);
  if ( v4 >= 0 )
  {
    v5 = 0;
    v6 = (char *)v12 + 16;
    v7 = (unsigned __int16 *)*((_QWORD *)v12 + 2);
    v8 = *v7;
    if ( *((_DWORD *)this + 1248) )
    {
      while ( v8 )
      {
        ++v7;
        v5 = v8 + 101 * v5;
        v8 = *v7;
      }
    }
    else
    {
      while ( v8 )
      {
        v9 = v8;
        v8 = *++v7;
        v5 = (v9 & 0xFFDF) + 101 * v5;
      }
    }
    v10 = v5 % 0x83;
    *((_QWORD *)v12 + 3) = *((_QWORD *)this + v10 + 493);
    *((_QWORD *)this + v10 + 493) = v6;
    if ( (*(unsigned int (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 72LL))(a2) )
      ++*((_DWORD *)this + 1251);
    else
      ++*((_DWORD *)this + 1250);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003450  push    rbx
0x180003452  push    rbp
0x180003453  push    rsi
0x180003454  push    rdi
0x180003455  sub     rsp, 28h
0x180003459  mov     rbx, rcx
0x18000345c  lea     r8, [rsp+48h+arg_0]; struct LOCK_ENTRY **
0x180003461  xor     ebp, ebp
0x180003463  add     rcx, 8; this
0x180003467  mov     [rsp+48h+arg_0], rbp
0x18000346c  mov     rsi, rdx
0x18000346f  call    ?AddLock2@URI_LOCK_LIST@@QEAAJPEAVIPubLock@@PEAPEAULOCK_ENTRY@@@Z; URI_LOCK_LIST::AddLock2(IPubLock *,LOCK_ENTRY * *)
0x180003474  mov     edi, eax
0x180003476  test    eax, eax
0x180003478  js      loc_180003517
0x18000347e  mov     r9, [rsp+48h+arg_0]
0x180003483  mov     r8d, ebp
0x180003486  add     r9, 10h
0x18000348a  mov     rdx, [r9]
0x18000348d  movzx   eax, word ptr [rdx]
0x180003490  cmp     [rbx+1380h], ebp
0x180003496  jz      short loc_1800034C9
0x180003498  jmp     short loc_1800034AB
0x18000349a  movzx   eax, ax
0x18000349d  lea     rdx, [rdx+2]
0x1800034a1  imul    r8d, 65h ; 'e'
0x1800034a5  add     r8d, eax
0x1800034a8  movzx   eax, word ptr [rdx]
0x1800034ab  test    ax, ax
0x1800034ae  jnz     short loc_18000349A
0x1800034b0  jmp     short loc_1800034CE
0x1800034b2  movzx   ecx, ax
0x1800034b5  lea     rdx, [rdx+2]
0x1800034b9  movzx   eax, word ptr [rdx]
0x1800034bc  and     ecx, 0FFDFh
0x1800034c2  imul    r8d, 65h ; 'e'
0x1800034c6  add     r8d, ecx
0x1800034c9  test    ax, ax
0x1800034cc  jnz     short loc_1800034B2
0x1800034ce  mov     eax, 0FA232CF3h
0x1800034d3  mov     rcx, rsi
0x1800034d6  mul     r8d
0x1800034d9  shr     edx, 7
0x1800034dc  imul    eax, edx, 83h
0x1800034e2  sub     r8d, eax
0x1800034e5  mov     rax, [rbx+r8*8+0F68h]
0x1800034ed  mov     [r9+8], rax
0x1800034f1  mov     [rbx+r8*8+0F68h], r9
0x1800034f9  mov     rax, [rsi]
0x1800034fc  mov     rax, [rax+48h]
0x180003500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003505  test    eax, eax
0x180003507  jnz     short loc_180003511
0x180003509  inc     dword ptr [rbx+1388h]
0x18000350f  jmp     short loc_180003517
0x180003511  inc     dword ptr [rbx+138Ch]
0x180003517  mov     eax, edi
0x180003519  add     rsp, 28h
0x18000351d  pop     rdi
0x18000351e  pop     rsi
0x18000351f  pop     rbp
0x180003520  pop     rbx
0x180003521  retn
```

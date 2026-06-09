# CScriptingEngine::Compile(CScriptFile *,ulong)

- ea: `0x14000d190`
- end: `0x14000d292`
- name: `?Compile@CScriptingEngine@@QEAAJPEAVCScriptFile@@K@Z`
- size: `258`
- prototype: `int __fastcall(CScriptingEngine *this, struct CScriptFile *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007dc8`

## callees

- `0x14000d190`
- `0x140011954`
- `0x1400147b0`
- `0x140018010`

## pseudocode

```c
int __fastcall CScriptingEngine::Compile(CScriptingEngine *this, struct CScriptFile *a2, unsigned int a3)
{
  __int64 v3; // rsi
  const unsigned __int16 *v6; // rbx
  int result; // eax
  const unsigned __int16 *v8; // rcx
  unsigned __int16 v9; // ax
  __int64 *v10; // rbx
  __int64 v11; // rcx

  v3 = a3;
  if ( !a3 )
  {
LABEL_10:
    if ( !*((_DWORD *)this + 32) )
      return 0;
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, int, _QWORD, _QWORD))(**((_QWORD **)this + 13) + 40LL))(
               *((_QWORD *)this + 13),
               *((_QWORD *)this + 15),
               0,
               0,
               0,
               *((unsigned int *)this + 22),
               1,
               130,
               0,
               0);
    if ( result >= 0 )
      return 0;
    if ( result == -2147352319 )
      return -2147155969;
    return result;
  }
  v6 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
  result = CCharSink::Emit((CScriptingEngine *)((char *)this + 120), v6, a3);
  if ( result >= 0 )
  {
    if ( (_DWORD)v3 )
    {
      v8 = &v6[v3];
      while ( v6 < v8 )
      {
        v9 = *v6++;
        if ( v9 == 10 )
          ++*((_DWORD *)this + 34);
      }
    }
    v10 = (__int64 *)((char *)this + 144);
    result = CScriptBlock::Create(a2, this, 0, v3, (struct CScriptBlock **)this + 18);
    if ( result >= 0 )
    {
      v11 = *v10;
      *((_QWORD *)a2 + 14) = *v10;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      goto LABEL_10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d190  push    rbx
0x14000d192  push    rbp
0x14000d193  push    rsi
0x14000d194  push    rdi
0x14000d195  push    r14
0x14000d197  sub     rsp, 60h
0x14000d19b  mov     esi, r8d
0x14000d19e  mov     r14, rdx
0x14000d1a1  mov     rbp, rcx
0x14000d1a4  test    r8d, r8d
0x14000d1a7  jz      short loc_14000D21B
0x14000d1a9  mov     rbx, [rdx+48h]
0x14000d1ad  mov     r8d, esi; unsigned int
0x14000d1b0  mov     rdx, rbx; unsigned __int16 *
0x14000d1b3  add     rcx, 78h ; 'x'; this
0x14000d1b7  call    ?Emit@CCharSink@@QEAAJPEBGK@Z; CCharSink::Emit(ushort const *,ulong)
0x14000d1bc  test    eax, eax
0x14000d1be  js      loc_14000D287
0x14000d1c4  cmp     esi, 1
0x14000d1c7  jb      short loc_14000D1E7
0x14000d1c9  lea     rcx, [rbx+rsi*2]
0x14000d1cd  jmp     short loc_14000D1E2
0x14000d1cf  movzx   eax, word ptr [rbx]
0x14000d1d2  add     rbx, 2
0x14000d1d6  cmp     ax, 0Ah
0x14000d1da  jnz     short loc_14000D1E2
0x14000d1dc  inc     dword ptr [rbp+88h]
0x14000d1e2  cmp     rbx, rcx
0x14000d1e5  jb      short loc_14000D1CF
0x14000d1e7  lea     rbx, [rbp+90h]
0x14000d1ee  mov     r9d, esi; unsigned int
0x14000d1f1  xor     r8d, r8d; unsigned int
0x14000d1f4  mov     [rsp+88h+var_68], rbx; struct CScriptBlock **
0x14000d1f9  mov     rdx, rbp; struct CScriptingEngine *
0x14000d1fc  mov     rcx, r14; struct CScriptFile *
0x14000d1ff  call    ?Create@CScriptBlock@@SAJPEAVCScriptFile@@PEAVCScriptingEngine@@KKPEAPEAV1@@Z; CScriptBlock::Create(CScriptFile *,CScriptingEngine *,ulong,ulong,CScriptBlock * *)
0x14000d204  test    eax, eax
0x14000d206  js      short loc_14000D287
0x14000d208  mov     rcx, [rbx]
0x14000d20b  mov     [r14+70h], rcx
0x14000d20f  mov     rax, [rcx]
0x14000d212  mov     rax, [rax+8]
0x14000d216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d21b  cmp     dword ptr [rbp+80h], 0
0x14000d222  jz      short loc_14000D285
0x14000d224  mov     r8d, [rbp+58h]
0x14000d228  xor     r9d, r9d
0x14000d22b  mov     rcx, [rbp+68h]
0x14000d22f  mov     rdx, [rbp+78h]
0x14000d233  mov     [rsp+88h+var_40], 0
0x14000d23c  mov     [rsp+88h+var_48], 0
0x14000d245  mov     rax, [rcx]
0x14000d248  mov     [rsp+88h+var_50], 82h
0x14000d250  mov     [rsp+88h+var_58], 1
0x14000d258  mov     [rsp+88h+var_60], r8
0x14000d25d  xor     r8d, r8d
0x14000d260  mov     rax, [rax+28h]
0x14000d264  mov     [rsp+88h+var_68], 0
0x14000d26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d272  test    eax, eax
0x14000d274  jns     short loc_14000D285
0x14000d276  cmp     eax, 80020101h
0x14000d27b  mov     ecx, 8004FFFFh
0x14000d280  cmovz   eax, ecx
0x14000d283  jmp     short loc_14000D287
0x14000d285  xor     eax, eax
0x14000d287  add     rsp, 60h
0x14000d28b  pop     r14
0x14000d28d  pop     rdi
0x14000d28e  pop     rsi
0x14000d28f  pop     rbp
0x14000d290  pop     rbx
0x14000d291  retn
```

# WdsLogCreate

- ea: `0x180020210`
- end: `0x18002027a`
- name: `WdsLogCreate`
- size: `106`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct tagLOG_FIELD_INFO *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18001bd30`
- `0x18001c350`
- `0x18001cb20`

## callees

- `0x180001144`
- `0x18001e114`
- `0x18001e314`
- `0x18001f020`
- `0x180020210`
- `0x180022e40`

## pseudocode

```c
CLogManager *__fastcall WdsLogCreate(unsigned __int16 *a1, struct tagLOG_FIELD_INFO *a2, unsigned int a3)
{
  CLogManager *v6; // rax
  CLogManager *v7; // rax
  CLogManager *v8; // rbx
  unsigned int v9; // edx

  if ( !(unsigned int)InitDefaultACL(0) )
    return 0;
  v6 = (CLogManager *)operator new(0x98u);
  if ( !v6 )
    return 0;
  v7 = CLogManager::CLogManager(v6);
  v8 = v7;
  if ( !v7 )
    return 0;
  if ( !(unsigned int)CLogManager::Init(v7, a1, a2, a3) )
  {
    CLogManager::`scalar deleting destructor'(v8, v9);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180020210  push    rbx
0x180020212  push    rbp
0x180020213  push    rsi
0x180020214  push    rdi
0x180020215  sub     rsp, 28h
0x180020219  mov     rbp, rcx
0x18002021c  mov     edi, r8d
0x18002021f  xor     ecx, ecx
0x180020221  mov     rsi, rdx
0x180020224  call    InitDefaultACL
0x180020229  test    eax, eax
0x18002022b  jz      short loc_180020269
0x18002022d  mov     ecx, 98h; Size
0x180020232  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020237  test    rax, rax
0x18002023a  jz      short loc_180020269
0x18002023c  mov     rcx, rax; this
0x18002023f  call    ??0CLogManager@@QEAA@XZ; CLogManager::CLogManager(void)
0x180020244  mov     rbx, rax
0x180020247  test    rax, rax
0x18002024a  jz      short loc_180020269
0x18002024c  mov     r9d, edi; unsigned int
0x18002024f  mov     r8, rsi; struct tagLOG_FIELD_INFO *
0x180020252  mov     rdx, rbp; unsigned __int16 *
0x180020255  mov     rcx, rax; this
0x180020258  call    ?Init@CLogManager@@QEAAHPEBGPEAUtagLOG_FIELD_INFO@@I@Z; CLogManager::Init(ushort const *,tagLOG_FIELD_INFO *,uint)
0x18002025d  test    eax, eax
0x18002025f  jnz     short loc_180020275
0x180020261  mov     rcx, rbx; this
0x180020264  call    ??_GCLogManager@@QEAAPEAXI@Z; CLogManager::`scalar deleting destructor'(uint)
0x180020269  xor     eax, eax
0x18002026b  add     rsp, 28h
0x18002026f  pop     rdi
0x180020270  pop     rsi
0x180020271  pop     rbp
0x180020272  pop     rbx
0x180020273  retn
0x180020275  mov     rax, rbx
0x180020278  jmp     short loc_18002026B
```

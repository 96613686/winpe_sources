# CWamAdmin::CreateApplication(ushort const *,ulong,ushort const *,int)

- ea: `0x180002730`
- end: `0x180002844`
- name: `?CreateApplication@CWamAdmin@@UEAAJPEBGK0H@Z`
- size: `276`
- prototype: `__int64 __fastcall(CWamAdmin *this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x180001084`
- `0x180002730`
- `0x180002e7c`
- `0x1800062b8`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWamAdmin::CreateApplication(
        CWamAdmin *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        int a5)
{
  int v9; // ebx
  char *v10; // r14
  int v11; // eax
  struct IMSAdminBaseW *v12; // rdx
  unsigned int v13; // r9d
  __int64 v14; // rcx
  unsigned int v16; // [rsp+28h] [rbp-60h]
  unsigned int v17; // [rsp+30h] [rbp-58h]
  void *Block; // [rsp+40h] [rbp-48h] BYREF
  int v19; // [rsp+98h] [rbp+10h] BYREF

  Block = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v10 = (char *)this - 16;
  v9 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, void **))(*((_QWORD *)this - 2) + 88LL))(
         (char *)this - 16,
         a2,
         &Block);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(char *, void *, _QWORD))(*(_QWORD *)v10 + 72LL))(v10, Block, a3);
    if ( v9 >= 0 )
    {
      if ( !a5 )
      {
        if ( !a4 )
        {
          v9 = 0;
          goto LABEL_13;
        }
LABEL_16:
        v19 = 0;
        v9 = DoesAppPoolExist(a4, &v19);
        if ( v9 < 0 )
          goto LABEL_13;
        if ( !v19 )
        {
          v9 = -2147023728;
          goto LABEL_13;
        }
LABEL_11:
        v9 = WamRegMetabaseConfig::MDSetStringProperty(
               (WamRegMetabaseConfig *)v14,
               v12,
               (const unsigned __int16 *)Block,
               v13,
               a4,
               v16,
               v17);
        if ( v9 >= 0 )
          v9 = 0;
        goto LABEL_13;
      }
      if ( a5 != 1 )
        goto LABEL_16;
      v11 = (*(__int64 (__fastcall **)(CWamAdmin *, const unsigned __int16 *))(*(_QWORD *)this + 40LL))(this, a4);
      v14 = 0x80000000LL;
      v9 = v11;
      if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147024713 )
        goto LABEL_11;
    }
  }
LABEL_13:
  if ( Block != a2 )
    operator delete(Block);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002730  push    rbx
0x180002732  push    rbp
0x180002733  push    rsi
0x180002734  push    rdi
0x180002735  push    r14
0x180002737  push    r15
0x180002739  sub     rsp, 58h
0x18000273d  mov     [rsp+88h+Block], 0
0x180002746  mov     rdi, r9
0x180002749  mov     ebp, r8d
0x18000274c  mov     rsi, rdx
0x18000274f  mov     r15, rcx
0x180002752  test    rdx, rdx
0x180002755  jnz     short loc_180002761
0x180002757  mov     ebx, 80070057h
0x18000275c  jmp     loc_180002803
0x180002761  lea     r14, [rcx-10h]
0x180002765  mov     rax, [r14]
0x180002768  lea     r8, [rsp+88h+Block]
0x18000276d  mov     rcx, r14
0x180002770  mov     rax, [rax+58h]
0x180002774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002779  mov     ebx, eax
0x18000277b  test    eax, eax
0x18000277d  js      short loc_1800027F4
0x18000277f  mov     rax, [r14]
0x180002782  mov     r8d, ebp
0x180002785  mov     rdx, [rsp+88h+Block]
0x18000278a  mov     rcx, r14
0x18000278d  mov     rax, [rax+48h]
0x180002791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002796  mov     ebx, eax
0x180002798  test    eax, eax
0x18000279a  js      short loc_1800027F4
0x18000279c  mov     eax, [rsp+88h+arg_20]
0x1800027a3  test    eax, eax
0x1800027a5  jnz     short loc_1800027B0
0x1800027a7  test    rdi, rdi
0x1800027aa  jnz     short loc_180002812
0x1800027ac  xor     ebx, ebx
0x1800027ae  jmp     short loc_1800027F4
0x1800027b0  cmp     eax, 1
0x1800027b3  jnz     short loc_180002812
0x1800027b5  mov     rax, [r15]
0x1800027b8  mov     rdx, rdi
0x1800027bb  mov     rcx, r15
0x1800027be  mov     rax, [rax+28h]
0x1800027c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c7  mov     ecx, 80000000h; this
0x1800027cc  mov     ebx, eax
0x1800027ce  add     eax, ecx
0x1800027d0  test    ecx, eax
0x1800027d2  jnz     short loc_1800027DC
0x1800027d4  cmp     ebx, 800700B7h
0x1800027da  jnz     short loc_1800027F4
0x1800027dc  mov     r8, [rsp+88h+Block]; unsigned __int16 *
0x1800027e1  mov     [rsp+88h+var_68], rdi; unsigned __int16 *
0x1800027e6  call    ?MDSetStringProperty@WamRegMetabaseConfig@@QEAAJPEAUIMSAdminBaseW@@PEBGK1KK@Z; WamRegMetabaseConfig::MDSetStringProperty(IMSAdminBaseW *,ushort const *,ulong,ushort const *,ulong,ulong)
0x1800027eb  mov     ebx, eax
0x1800027ed  xor     eax, eax
0x1800027ef  test    ebx, ebx
0x1800027f1  cmovns  ebx, eax
0x1800027f4  mov     rcx, [rsp+88h+Block]; Block
0x1800027f9  cmp     rcx, rsi
0x1800027fc  jz      short loc_180002803
0x1800027fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002803  mov     eax, ebx
0x180002805  add     rsp, 58h
0x180002809  pop     r15
0x18000280b  pop     r14
0x18000280d  pop     rdi
0x18000280e  pop     rsi
0x18000280f  pop     rbp
0x180002810  pop     rbx
0x180002811  retn
0x180002812  lea     rdx, [rsp+88h+arg_8]; int *
0x18000281a  mov     [rsp+88h+arg_8], 0
0x180002825  mov     rcx, rdi; unsigned __int16 *
0x180002828  call    ?DoesAppPoolExist@@YAJPEBGPEAH@Z; DoesAppPoolExist(ushort const *,int *)
0x18000282d  mov     ebx, eax
0x18000282f  test    eax, eax
0x180002831  js      short loc_1800027F4
0x180002833  cmp     [rsp+88h+arg_8], 0
0x18000283b  jnz     short loc_1800027DC
0x18000283d  mov     ebx, 80070490h
0x180002842  jmp     short loc_1800027F4
```

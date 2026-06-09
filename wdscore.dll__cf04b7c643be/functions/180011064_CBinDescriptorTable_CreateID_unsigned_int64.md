# CBinDescriptorTable::CreateID(unsigned __int64)

- ea: `0x180011064`
- end: `0x1800111d4`
- name: `?CreateID@CBinDescriptorTable@@QEAA_K_K@Z`
- size: `368`
- prototype: `unsigned __int64 __fastcall(CBinDescriptorTable *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800104fc`
- `0x180010e44`

## callees

- `0x18000f9b8`
- `0x18000fcf0`
- `0x180011064`
- `0x1800111dc`
- `0x180012408`
- `0x180013480`
- `0x180013738`
- `0x180017ab4`

## pseudocode

```c
__int64 __fastcall CBinDescriptorTable::CreateID(CBinDescriptorTable *this, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  _QWORD *v8; // rsi
  unsigned __int64 i; // rax
  CSpinLockFileMappingArray *v10; // rcx
  __int64 v11; // rax
  unsigned __int64 v13; // [rsp+90h] [rbp+18h] BYREF

  v4 = 0;
  v5 = *((_QWORD *)this + 48);
  if ( v5 )
    AcquireWriteAccess((volatile int *)(*(_QWORD *)(*(_QWORD *)v5 + 8LL) + 20LL));
  while ( 1 )
  {
    v6 = 1;
    if ( !(unsigned int)CBin::EnumReset(this, 8u) )
      break;
    v13 = 0;
    while ( 1 )
    {
      v8 = CBin::EnumView(this, &v13, v7);
      if ( !v8 )
        break;
      if ( v13 < 8 )
        goto LABEL_18;
      for ( i = 0; i < v13; i += 8LL )
      {
        if ( !*v8 )
        {
          v10 = (CSpinLockFileMappingArray *)*((_QWORD *)this + 48);
          if ( !v10 || (unsigned int)CSpinLockFileMappingArray::CreateIndex(v10, v6) )
          {
            *v8 = a2;
            v4 = 1;
            goto LABEL_15;
          }
          goto LABEL_18;
        }
        ++v6;
        ++v8;
      }
    }
LABEL_15:
    CBin::EnumFinish(this);
    if ( v4 )
    {
      v4 = 1;
      break;
    }
    CMemoryManager::Allocate(*((CMemoryManager **)this + 12), *((_QWORD *)this + 10), 1u, 1, 1, 0);
  }
LABEL_18:
  v11 = *((_QWORD *)this + 48);
  if ( v11 )
    ReleaseAccess((volatile int *)(*(_QWORD *)(*(_QWORD *)v11 + 8LL) + 20LL));
  return v6 & -(__int64)(v4 != 0);
}

```

## disassembly

```asm
0x180011064  mov     [rsp+arg_8], rbx
0x180011069  mov     [rsp+arg_0], rcx
0x18001106e  push    rsi
0x18001106f  push    rdi
0x180011070  push    r13
0x180011072  push    r14
0x180011074  push    r15
0x180011076  sub     rsp, 50h
0x18001107a  mov     r15, rdx
0x18001107d  mov     rdi, rcx
0x180011080  xor     ebx, ebx
0x180011082  mov     rax, [rcx+180h]
0x180011089  test    rax, rax
0x18001108c  jz      short loc_18001109F
0x18001108e  mov     rax, [rax]
0x180011091  mov     rcx, [rax+8]
0x180011095  add     rcx, 14h; volatile int *
0x180011099  call    ?AcquireWriteAccess@@YAXPECJ@Z; AcquireWriteAccess(long volatile *)
0x18001109e  nop
0x18001109f  mov     r13d, 1
0x1800110a5  mov     r14, r13
0x1800110a8  mov     [rsp+78h+var_38], r13
0x1800110ad  mov     edx, 8; unsigned __int64
0x1800110b2  mov     rcx, rdi; this
0x1800110b5  call    ?EnumReset@CBin@@QEAAH_K@Z; CBin::EnumReset(unsigned __int64)
0x1800110ba  test    eax, eax
0x1800110bc  jz      loc_18001119A
0x1800110c2  mov     [rsp+78h+var_40], 0
0x1800110cb  mov     [rsp+78h+arg_10], 0
0x1800110d7  lea     rdx, [rsp+78h+arg_10]; unsigned __int64 *
0x1800110df  mov     rcx, rdi; this
0x1800110e2  call    ?EnumView@CBin@@QEAAPEAXAEA_K_K@Z; CBin::EnumView(unsigned __int64 &,unsigned __int64)
0x1800110e7  mov     rsi, rax
0x1800110ea  mov     [rsp+78h+var_40], rax
0x1800110ef  test    rax, rax
0x1800110f2  jz      short loc_18001115E
0x1800110f4  cmp     [rsp+78h+arg_10], 8
0x1800110fd  jb      loc_18001119A
0x180011103  xor     eax, eax
0x180011105  mov     [rsp+78h+var_30], rax
0x18001110a  cmp     rax, [rsp+78h+arg_10]
0x180011112  jnb     short loc_180011155
0x180011114  cmp     qword ptr [rsi], 0
0x180011118  jnz     short loc_18001113E
0x18001111a  mov     rcx, [rdi+180h]; this
0x180011121  test    rcx, rcx
0x180011124  jz      short loc_180011132
0x180011126  mov     rdx, r14; unsigned __int64
0x180011129  call    ?CreateIndex@CSpinLockFileMappingArray@@QEAAH_K@Z; CSpinLockFileMappingArray::CreateIndex(unsigned __int64)
0x18001112e  test    eax, eax
0x180011130  jz      short loc_18001119A
0x180011132  mov     [rsi], r15
0x180011135  mov     ebx, r13d
0x180011138  mov     [rsp+78h+var_48], ebx
0x18001113c  jmp     short loc_18001115E
0x18001113e  add     r14, r13
0x180011141  mov     [rsp+78h+var_38], r14
0x180011146  add     rax, 8
0x18001114a  add     rsi, 8
0x18001114e  mov     [rsp+78h+var_40], rsi
0x180011153  jmp     short loc_180011105
0x180011155  test    ebx, ebx
0x180011157  jnz     short loc_18001115E
0x180011159  jmp     loc_1800110D7
0x18001115e  mov     rcx, rdi; this
0x180011161  call    ?EnumFinish@CBin@@QEAAHXZ; CBin::EnumFinish(void)
0x180011166  test    ebx, ebx
0x180011168  jnz     short loc_180011193
0x18001116a  mov     [rsp+78h+var_50], 0; struct SMainPageHeader *
0x180011173  mov     [rsp+78h+var_58], r13d; int
0x180011178  mov     r9d, r13d; int
0x18001117b  mov     r8, r13; unsigned __int64
0x18001117e  mov     rdx, [rdi+50h]; unsigned __int64
0x180011182  mov     rcx, [rdi+60h]; this
0x180011186  call    ?Allocate@CMemoryManager@@QEAA_K_K0HHPEAUSMainPageHeader@@@Z; CMemoryManager::Allocate(unsigned __int64,unsigned __int64,int,int,SMainPageHeader *)
0x18001118b  test    ebx, ebx
0x18001118d  jz      loc_1800110A5
0x180011193  mov     ebx, r13d
0x180011196  mov     [rsp+78h+var_48], ebx
0x18001119a  mov     rax, [rdi+180h]
0x1800111a1  test    rax, rax
0x1800111a4  jz      short loc_1800111B6
0x1800111a6  mov     rax, [rax]
0x1800111a9  mov     rcx, [rax+8]
0x1800111ad  add     rcx, 14h; volatile int *
0x1800111b1  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x1800111b6  neg     ebx
0x1800111b8  sbb     rax, rax
0x1800111bb  and     rax, r14
0x1800111be  mov     rbx, [rsp+78h+arg_8]
0x1800111c6  add     rsp, 50h
0x1800111ca  pop     r15
0x1800111cc  pop     r14
0x1800111ce  pop     r13
0x1800111d0  pop     rdi
0x1800111d1  pop     rsi
0x1800111d2  retn
0x1800287b7  push    rbp
0x1800287b9  sub     rsp, 30h
0x1800287bd  mov     rbp, rdx
0x1800287c0  mov     rax, [rbp+80h]
0x1800287c7  cmp     qword ptr [rax+180h], 0
0x1800287cf  jz      short loc_1800287E9
0x1800287d1  mov     rax, [rax+180h]
0x1800287d8  mov     rcx, [rax]
0x1800287db  mov     rcx, [rcx+8]
0x1800287df  add     rcx, 14h; volatile int *
0x1800287e3  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x1800287e8  nop
0x1800287e9  add     rsp, 30h
0x1800287ed  pop     rbp
0x1800287ee  retn
```

# CTypeManager::OpenBin(CBin &,unsigned __int64,int,uint *)

- ea: `0x180017888`
- end: `0x180017962`
- name: `?OpenBin@CTypeManager@@QEAAHAEAVCBin@@_KHPEAI@Z`
- size: `218`
- prototype: `int(CTypeManager *__hidden this, struct CBin *, unsigned __int64, int, unsigned int *)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x180011914`
- `0x180012704`
- `0x1800128dc`
- `0x180013b28`
- `0x180013fb4`
- `0x1800142c8`

## callees

- `0x18000f798`
- `0x18000fa70`
- `0x1800150dc`
- `0x1800151c4`
- `0x180017888`
- `0x180017acc`
- `0x180027510`

## pseudocode

```c
__int64 __fastcall CTypeManager::OpenBin(
        CTypeManager *this,
        struct CBin *a2,
        unsigned __int64 a3,
        int a4,
        unsigned int *a5)
{
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rbx
  _BYTE v12[400]; // [rsp+30h] [rbp-1B8h] BYREF

  if ( !a3
    || !(unsigned int)CBinDescriptorTable::Init(
                        (CBinDescriptorTable *)v12,
                        *((_QWORD *)this + 1),
                        *((struct CMemoryManager **)this + 4),
                        (CTypeManager *)((char *)this + 24),
                        0) )
  {
    return 0;
  }
  v9 = a4
     ? CBinDescriptorTable::AcquireWriteAccess((CBinDescriptorTable *)v12, a3, a5)
     : CBinDescriptorTable::AcquireReadAccess((CBinDescriptorTable *)v12, a3, a5);
  v10 = v9;
  if ( !v9 )
    return 0;
  if ( !(unsigned int)CBin::Init(a2, v9, *((struct CMemoryManager **)this + 4), a3) )
  {
    CBinDescriptorTable::ReleaseAccess((CBinDescriptorTable *)v12, v10);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180017888  mov     [rsp+arg_0], rbx
0x18001788d  mov     [rsp+arg_18], rbp
0x180017892  push    rsi
0x180017893  push    rdi
0x180017894  push    r14
0x180017896  sub     rsp, 1D0h
0x18001789d  mov     rax, cs:__security_cookie
0x1800178a4  xor     rax, rsp
0x1800178a7  mov     [rsp+1E8h+var_28], rax
0x1800178af  mov     rbx, [rsp+1E8h+arg_20]
0x1800178b7  mov     ebp, r9d
0x1800178ba  mov     rdi, r8
0x1800178bd  mov     r14, rdx
0x1800178c0  mov     rsi, rcx
0x1800178c3  test    r8, r8
0x1800178c6  jz      short loc_180017930
0x1800178c8  mov     r8, [rcx+20h]; struct CMemoryManager *
0x1800178cc  lea     r9, [rcx+18h]; struct CSpinLockFileMappingArray *
0x1800178d0  mov     rdx, [rcx+8]; unsigned __int64
0x1800178d4  lea     rcx, [rsp+1E8h+var_1B8]; this
0x1800178d9  mov     [rsp+1E8h+var_1C8], 0; int
0x1800178e1  call    ?Init@CBinDescriptorTable@@QEAAH_KPEAVCMemoryManager@@PEAVCSpinLockFileMappingArray@@H@Z; CBinDescriptorTable::Init(unsigned __int64,CMemoryManager *,CSpinLockFileMappingArray *,int)
0x1800178e6  test    eax, eax
0x1800178e8  jz      short loc_180017930
0x1800178ea  lea     rcx, [rsp+1E8h+var_1B8]; this
0x1800178ef  mov     r8, rbx; unsigned int *
0x1800178f2  mov     rdx, rdi; unsigned __int64
0x1800178f5  test    ebp, ebp
0x1800178f7  jz      short loc_180017900
0x1800178f9  call    ?AcquireWriteAccess@CBinDescriptorTable@@QEAA_K_KPEAI@Z; CBinDescriptorTable::AcquireWriteAccess(unsigned __int64,uint *)
0x1800178fe  jmp     short loc_180017905
0x180017900  call    ?AcquireReadAccess@CBinDescriptorTable@@QEAA_K_KPEAI@Z; CBinDescriptorTable::AcquireReadAccess(unsigned __int64,uint *)
0x180017905  mov     rbx, rax
0x180017908  test    rax, rax
0x18001790b  jz      short loc_180017930
0x18001790d  mov     r8, [rsi+20h]; struct CMemoryManager *
0x180017911  mov     r9, rdi; unsigned __int64
0x180017914  mov     rdx, rax; unsigned __int64
0x180017917  mov     rcx, r14; this
0x18001791a  call    ?Init@CBin@@QEAAH_KPEAVCMemoryManager@@0@Z; CBin::Init(unsigned __int64,CMemoryManager *,unsigned __int64)
0x18001791f  test    eax, eax
0x180017921  jnz     short loc_18001795B
0x180017923  mov     rdx, rbx; unsigned __int64
0x180017926  lea     rcx, [rsp+1E8h+var_1B8]; this
0x18001792b  call    ?ReleaseAccess@CBinDescriptorTable@@QEAAX_K@Z; CBinDescriptorTable::ReleaseAccess(unsigned __int64)
0x180017930  xor     eax, eax
0x180017932  mov     rcx, [rsp+1E8h+var_28]
0x18001793a  xor     rcx, rsp; StackCookie
0x18001793d  call    __security_check_cookie
0x180017942  lea     r11, [rsp+1E8h+var_18]
0x18001794a  mov     rbx, [r11+20h]
0x18001794e  mov     rbp, [r11+38h]
0x180017952  mov     rsp, r11
0x180017955  pop     r14
0x180017957  pop     rdi
0x180017958  pop     rsi
0x180017959  retn
0x18001795b  mov     eax, 1
0x180017960  jmp     short loc_180017932
```

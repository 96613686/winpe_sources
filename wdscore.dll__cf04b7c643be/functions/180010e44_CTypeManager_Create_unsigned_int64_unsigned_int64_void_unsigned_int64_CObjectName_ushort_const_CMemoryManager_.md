# CTypeManager::Create(unsigned __int64,unsigned __int64,void *,unsigned __int64,CObjectName &,ushort const *,CMemoryManager *,unsigned __int64 &,unsigned __int64 &,int)

- ea: `0x180010e44`
- end: `0x180010fda`
- name: `?Create@CTypeManager@@QEAAH_K0PEAX0AEAVCObjectName@@PEBGPEAVCMemoryManager@@AEA_K5H@Z`
- size: `406`
- prototype: `__int64 __usercall@<rax>(CTypeManager *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, struct CObjectName *, const unsigned __int16 *, struct CMemoryManager *, unsigned __int64 *, unsigned __int64 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x180011578`

## callees

- `0x18000fcf0`
- `0x180010e44`
- `0x180011064`
- `0x1800149c4`
- `0x1800151c4`
- `0x180017598`
- `0x180027510`

## pseudocode

```c
__int64 __fastcall CTypeManager::Create(
        CTypeManager *this,
        __int64 a2,
        __int64 a3,
        void *a4,
        unsigned __int64 a5,
        const unsigned __int16 **a6,
        unsigned __int16 *a7,
        struct CMemoryManager *a8,
        unsigned __int64 *a9,
        unsigned __int64 *a10,
        int a11)
{
  __int64 result; // rax
  unsigned int v13; // esi
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  unsigned __int64 ID; // rax
  __int64 v19; // rdx
  _BYTE v20[400]; // [rsp+70h] [rbp-1C8h] BYREF

  result = 0;
  if ( a8 && a7 )
  {
    v13 = 0;
    v14 = 0;
    *a9 = 0;
    *a10 = 0;
    v15 = CMemoryManager::Allocate(a8, 0, 1u, 0, 1, 0);
    *a9 = v15;
    if ( v15 )
    {
      if ( (unsigned int)CBinDescriptorTable::Init((CBinDescriptorTable *)v20, v15, a8, 0, 1) )
      {
        v17 = CMemoryManager::Allocate(a8, 0, 0x100u, 0, 0, 0);
        v14 = v17;
        if ( v17 )
        {
          ID = CBinDescriptorTable::CreateID((CBinDescriptorTable *)v20, v17);
          *a10 = ID;
          v13 = CTypeManager::Open(this, v19, *a9, ID, a6, a7, a8, a11);
        }
      }
    }
    if ( !v13 )
    {
      if ( v14 )
        CMemoryManager::Free(a8, v14, v16);
      if ( *a9 )
        CMemoryManager::Free(a8, *a9, v16);
    }
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180010e44  mov     [rsp+arg_8], rbx
0x180010e49  mov     [rsp+arg_10], rsi
0x180010e4e  push    rdi
0x180010e4f  push    r12
0x180010e51  push    r13
0x180010e53  push    r14
0x180010e55  push    r15
0x180010e57  sub     rsp, 210h
0x180010e5e  mov     rax, cs:__security_cookie
0x180010e65  xor     rax, rsp
0x180010e68  mov     [rsp+238h+var_38], rax
0x180010e70  mov     r13, rcx
0x180010e73  mov     rax, [rsp+238h+arg_28]
0x180010e7b  mov     [rsp+238h+var_1E0], rax
0x180010e80  mov     r15, [rsp+238h+arg_30]
0x180010e88  mov     rdi, [rsp+238h+arg_38]
0x180010e90  mov     [rsp+238h+var_1E8], rdi
0x180010e95  mov     r14, [rsp+238h+arg_40]
0x180010e9d  mov     [rsp+238h+var_1D8], r14
0x180010ea2  mov     r12, [rsp+238h+arg_48]
0x180010eaa  xor     eax, eax
0x180010eac  test    rdi, rdi
0x180010eaf  jz      loc_180010FAC
0x180010eb5  test    r15, r15
0x180010eb8  jz      loc_180010FAC
0x180010ebe  mov     esi, eax
0x180010ec0  mov     [rsp+238h+var_1F8], eax
0x180010ec4  mov     ebx, eax
0x180010ec6  mov     [rsp+238h+var_1F0], rax
0x180010ecb  mov     [r14], rax
0x180010ece  mov     [r12], rax
0x180010ed2  mov     [rsp+238h+var_210], rax; struct SMainPageHeader *
0x180010ed7  lea     eax, [rbx+1]
0x180010eda  mov     dword ptr [rsp+238h+var_218], eax; int
0x180010ede  xor     r9d, r9d; int
0x180010ee1  mov     r8d, eax; unsigned __int64
0x180010ee4  xor     edx, edx; unsigned __int64
0x180010ee6  mov     rcx, rdi; this
0x180010ee9  call    ?Allocate@CMemoryManager@@QEAA_K_K0HHPEAUSMainPageHeader@@@Z; CMemoryManager::Allocate(unsigned __int64,unsigned __int64,int,int,SMainPageHeader *)
0x180010eee  mov     [r14], rax
0x180010ef1  test    rax, rax
0x180010ef4  jz      loc_180010F86
0x180010efa  mov     dword ptr [rsp+238h+var_218], 1; int
0x180010f02  xor     r9d, r9d; struct CSpinLockFileMappingArray *
0x180010f05  mov     r8, rdi; struct CMemoryManager *
0x180010f08  mov     rdx, rax; unsigned __int64
0x180010f0b  lea     rcx, [rsp+238h+var_1C8]; this
0x180010f10  call    ?Init@CBinDescriptorTable@@QEAAH_KPEAVCMemoryManager@@PEAVCSpinLockFileMappingArray@@H@Z; CBinDescriptorTable::Init(unsigned __int64,CMemoryManager *,CSpinLockFileMappingArray *,int)
0x180010f15  test    eax, eax
0x180010f17  jz      short loc_180010F86
0x180010f19  mov     [rsp+238h+var_210], rbx; struct SMainPageHeader *
0x180010f1e  mov     dword ptr [rsp+238h+var_218], ebx; int
0x180010f22  xor     r9d, r9d; int
0x180010f25  xor     edx, edx; unsigned __int64
0x180010f27  mov     r8d, 100h; unsigned __int64
0x180010f2d  mov     rcx, rdi; this
0x180010f30  call    ?Allocate@CMemoryManager@@QEAA_K_K0HHPEAUSMainPageHeader@@@Z; CMemoryManager::Allocate(unsigned __int64,unsigned __int64,int,int,SMainPageHeader *)
0x180010f35  mov     rbx, rax
0x180010f38  mov     [rsp+238h+var_1F0], rax
0x180010f3d  test    rax, rax
0x180010f40  jz      short loc_180010F86
0x180010f42  mov     rdx, rax; unsigned __int64
0x180010f45  lea     rcx, [rsp+238h+var_1C8]; this
0x180010f4a  call    ?CreateID@CBinDescriptorTable@@QEAA_K_K@Z; CBinDescriptorTable::CreateID(unsigned __int64)
0x180010f4f  mov     r9, rax; unsigned __int64
0x180010f52  mov     [r12], rax
0x180010f56  mov     eax, [rsp+238h+arg_50]
0x180010f5d  mov     [rsp+238h+var_200], eax; int
0x180010f61  mov     [rsp+238h+var_208], rdi; struct CMemoryManager *
0x180010f66  mov     [rsp+238h+var_210], r15; unsigned __int16 *
0x180010f6b  mov     rax, [rsp+238h+var_1E0]
0x180010f70  mov     [rsp+238h+var_218], rax; struct CObjectName *
0x180010f75  mov     r8, [r14]; unsigned __int64
0x180010f78  mov     rcx, r13; this
0x180010f7b  call    ?Open@CTypeManager@@QEAAH_K00AEAVCObjectName@@PEBGPEAVCMemoryManager@@H@Z; CTypeManager::Open(unsigned __int64,unsigned __int64,unsigned __int64,CObjectName &,ushort const *,CMemoryManager *,int)
0x180010f80  mov     esi, eax
0x180010f82  mov     [rsp+238h+var_1F8], eax
0x180010f86  test    esi, esi
0x180010f88  jnz     short loc_180010FAA
0x180010f8a  test    rbx, rbx
0x180010f8d  jz      short loc_180010F9A
0x180010f8f  mov     rdx, rbx; unsigned __int64
0x180010f92  mov     rcx, rdi; this
0x180010f95  call    ?Free@CMemoryManager@@QEAAH_K0@Z; CMemoryManager::Free(unsigned __int64,unsigned __int64)
0x180010f9a  mov     rdx, [r14]; unsigned __int64
0x180010f9d  test    rdx, rdx
0x180010fa0  jz      short loc_180010FAA
0x180010fa2  mov     rcx, rdi; this
0x180010fa5  call    ?Free@CMemoryManager@@QEAAH_K0@Z; CMemoryManager::Free(unsigned __int64,unsigned __int64)
0x180010faa  mov     eax, esi
0x180010fac  mov     rcx, [rsp+238h+var_38]
0x180010fb4  xor     rcx, rsp; StackCookie
0x180010fb7  call    __security_check_cookie
0x180010fbc  lea     r11, [rsp+238h+var_28]
0x180010fc4  mov     rbx, [r11+38h]
0x180010fc8  mov     rsi, [r11+40h]
0x180010fcc  mov     rsp, r11
0x180010fcf  pop     r15
0x180010fd1  pop     r14
0x180010fd3  pop     r13
0x180010fd5  pop     r12
0x180010fd7  pop     rdi
0x180010fd8  retn
0x180028771  push    rbp
0x180028773  sub     rsp, 40h
0x180028777  mov     rbp, rdx
0x18002877a  cmp     dword ptr [rbp+40h], 0
0x18002877e  jnz     short loc_1800287AA
0x180028780  mov     rdx, [rbp+48h]; unsigned __int64
0x180028784  test    rdx, rdx
0x180028787  jz      short loc_180028793
0x180028789  mov     rcx, [rbp+50h]; this
0x18002878d  call    ?Free@CMemoryManager@@QEAAH_K0@Z; CMemoryManager::Free(unsigned __int64,unsigned __int64)
0x180028792  nop
0x180028793  mov     rdx, [rbp+60h]
0x180028797  cmp     qword ptr [rdx], 0
0x18002879b  jz      short loc_1800287AA
0x18002879d  mov     rdx, [rdx]; unsigned __int64
0x1800287a0  mov     rcx, [rbp+50h]; this
0x1800287a4  call    ?Free@CMemoryManager@@QEAAH_K0@Z; CMemoryManager::Free(unsigned __int64,unsigned __int64)
0x1800287a9  nop
0x1800287aa  add     rsp, 40h
0x1800287ae  pop     rbp
0x1800287af  retn
```

# CConsistentFileMapping::Create(ushort const *,CObjectName &,int,int,int,unsigned __int64,int *,ulong)

- ea: `0x180010ab0`
- end: `0x180010bf4`
- name: `?Create@CConsistentFileMapping@@UEAAHPEBGAEAVCObjectName@@HHH_KPEAHK@Z`
- size: `324`
- prototype: `__int64 __usercall@<rax>(CConsistentFileMapping *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct CObjectName *@<r8>, int@<r9d>, int, int, unsigned __int64, int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x180010400`
- `0x180010ab0`
- `0x18001541c`
- `0x180016ae8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CConsistentFileMapping::Create(
        CConsistentFileMapping *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        int a4,
        int a5,
        int a6,
        unsigned __int64 a7,
        int *a8,
        unsigned int a9)
{
  unsigned int v14; // ebx
  int v15; // [rsp+38h] [rbp-60h]
  unsigned __int16 *v16[7]; // [rsp+60h] [rbp-38h] BYREF
  unsigned __int16 *v17; // [rsp+A8h] [rbp+10h] BYREF

  v16[1] = (unsigned __int16 *)-2LL;
  if ( !a2
    || !*a3
    || !CObjectName::Init((CConsistentFileMapping *)((char *)this + 80), *a3, 0)
    || !CObjectName::Init((CConsistentFileMapping *)((char *)this + 88), a2, 0) )
  {
    return 0;
  }
  v17 = 0;
  if ( !CObjectName::Init((CObjectName *)&v17, *a3, L"CFM") )
  {
    CObjectName::Close((CObjectName *)&v17);
    return 0;
  }
  v16[0] = 0;
  if ( !CObjectName::Init((CObjectName *)v16, *a3, L"Mtx") )
  {
    CObjectName::Close((CObjectName *)v16);
    CObjectName::Close((CObjectName *)&v17);
    return 0;
  }
  v14 = CConsistentFileMapping::Open(this, a2, v16[0], v17, a4, a5, a6, v15, a7, a8, a9);
  CObjectName::Close((CObjectName *)v16);
  CObjectName::Close((CObjectName *)&v17);
  return v14;
}

```

## disassembly

```asm
0x180010ab0  push    rbx
0x180010ab2  push    rbp
0x180010ab3  push    rsi
0x180010ab4  push    rdi
0x180010ab5  sub     rsp, 78h
0x180010ab9  mov     [rsp+98h+var_30], 0FFFFFFFFFFFFFFFEh
0x180010ac2  mov     ebp, r9d
0x180010ac5  mov     rbx, r8
0x180010ac8  mov     rdi, rdx
0x180010acb  mov     rsi, rcx
0x180010ace  test    rdx, rdx
0x180010ad1  jz      short loc_180010B33
0x180010ad3  mov     rdx, [r8]; unsigned __int16 *
0x180010ad6  test    rdx, rdx
0x180010ad9  jz      short loc_180010B33
0x180010adb  add     rcx, 50h ; 'P'; this
0x180010adf  xor     r8d, r8d; unsigned __int16 *
0x180010ae2  call    ?Init@CObjectName@@QEAAHPEBG0@Z; CObjectName::Init(ushort const *,ushort const *)
0x180010ae7  test    eax, eax
0x180010ae9  jz      short loc_180010B33
0x180010aeb  lea     rcx, [rsi+58h]; this
0x180010aef  xor     r8d, r8d; unsigned __int16 *
0x180010af2  mov     rdx, rdi; unsigned __int16 *
0x180010af5  call    ?Init@CObjectName@@QEAAHPEBG0@Z; CObjectName::Init(ushort const *,ushort const *)
0x180010afa  test    eax, eax
0x180010afc  jz      short loc_180010B33
0x180010afe  mov     [rsp+98h+arg_8], 0
0x180010b0a  lea     r8, aCfm; "CFM"
0x180010b11  mov     rdx, [rbx]; unsigned __int16 *
0x180010b14  lea     rcx, [rsp+98h+arg_8]; this
0x180010b1c  call    ?Init@CObjectName@@QEAAHPEBG0@Z; CObjectName::Init(ushort const *,ushort const *)
0x180010b21  test    eax, eax
0x180010b23  jnz     short loc_180010B3F
0x180010b25  lea     rcx, [rsp+98h+arg_8]; this
0x180010b2d  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180010b32  nop
0x180010b33  xor     eax, eax
0x180010b35  add     rsp, 78h
0x180010b39  pop     rdi
0x180010b3a  pop     rsi
0x180010b3b  pop     rbp
0x180010b3c  pop     rbx
0x180010b3d  retn
0x180010b3f  mov     [rsp+98h+var_38], 0
0x180010b48  lea     r8, aMtx; "Mtx"
0x180010b4f  mov     rdx, [rbx]; unsigned __int16 *
0x180010b52  lea     rcx, [rsp+98h+var_38]; this
0x180010b57  call    ?Init@CObjectName@@QEAAHPEBG0@Z; CObjectName::Init(ushort const *,ushort const *)
0x180010b5c  test    eax, eax
0x180010b5e  jnz     short loc_180010B7B
0x180010b60  lea     rcx, [rsp+98h+var_38]; this
0x180010b65  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180010b6a  nop
0x180010b6b  lea     rcx, [rsp+98h+arg_8]; this
0x180010b73  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180010b78  nop
0x180010b79  jmp     short loc_180010B33
0x180010b7b  mov     eax, [rsp+98h+arg_40]
0x180010b82  mov     [rsp+98h+var_48], eax; unsigned int
0x180010b86  mov     rax, [rsp+98h+arg_38]
0x180010b8e  mov     [rsp+98h+var_50], rax; int *
0x180010b93  mov     rax, [rsp+98h+arg_30]
0x180010b9b  mov     [rsp+98h+var_58], rax; unsigned __int64
0x180010ba0  mov     eax, [rsp+98h+arg_28]
0x180010ba7  mov     [rsp+98h+var_68], eax; int
0x180010bab  mov     eax, [rsp+98h+arg_20]
0x180010bb2  mov     [rsp+98h+var_70], eax; int
0x180010bb6  mov     [rsp+98h+var_78], ebp; int
0x180010bba  mov     r9, [rsp+98h+arg_8]; unsigned __int16 *
0x180010bc2  mov     r8, [rsp+98h+var_38]; unsigned __int16 *
0x180010bc7  mov     rdx, rdi; unsigned __int16 *
0x180010bca  mov     rcx, rsi; this
0x180010bcd  call    ?Open@CConsistentFileMapping@@IEAAHPEBG00HHHH_KPEAHK@Z; CConsistentFileMapping::Open(ushort const *,ushort const *,ushort const *,int,int,int,int,unsigned __int64,int *,ulong)
0x180010bd2  mov     ebx, eax
0x180010bd4  lea     rcx, [rsp+98h+var_38]; this
0x180010bd9  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180010bde  nop
0x180010bdf  lea     rcx, [rsp+98h+arg_8]; this
0x180010be7  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180010bec  nop
0x180010bed  mov     eax, ebx
0x180010bef  jmp     loc_180010B35
```

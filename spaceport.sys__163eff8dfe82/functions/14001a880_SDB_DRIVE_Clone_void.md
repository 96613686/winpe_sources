# SDB_DRIVE::Clone(void)

- ea: `0x14001a880`
- end: `0x14001ab6d`
- name: `?Clone@SDB_DRIVE@@UEAAPEAVSDB_OBJECT@@XZ`
- size: `749`
- prototype: `struct SDB_OBJECT *__fastcall(SDB_DRIVE *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x140098cd8`
- `0x14009bbbc`

## callees

- `0x140016860`
- `0x14001a880`
- `0x14001ab80`
- `0x140026790`
- `0x1400268c0`
- `0x140026e00`
- `0x14002b012`
- `0x14005bf10`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001a8b2`
- `ntoskrnl!ExAllocatePool2` at `0x14001aa5a`
- `ntoskrnl!ExAllocatePool2` at `0x14001a8b2`
- `ntoskrnl!ExAllocatePool2` at `0x14001aa5a`
- `ntoskrnl!RtlCopyBitMap` at `0x14006ad8d`
- `ntoskrnl!RtlCopyBitMap` at `0x14006ad8d`

## pseudocode

```c
struct SDB_OBJECT *__fastcall SDB_DRIVE::Clone(SDB_DRIVE *this)
{
  __int64 v2; // rcx
  SDB_DRIVE *Pool2; // rax
  SC_SPARSE *v5; // rax
  SDB_DRIVE *v6; // rax
  SDB_DRIVE *v7; // rbx
  SDB_DRIVE *v8; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm0
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v16; // rcx
  SC_SPARSE *v17; // rax
  ULONG *v18; // rax

  v2 = 256;
  if ( !*((_BYTE *)WPP_MAIN_CB.DeviceExtension + 442) )
    v2 = 64;
  Pool2 = (SDB_DRIVE *)ExAllocatePool2(v2, 320, 1682075731);
  if ( !Pool2 )
    return 0;
  v6 = SDB_DRIVE::SDB_DRIVE(Pool2);
  v7 = v6;
  if ( !v6 )
    return 0;
  v8 = this;
  v9 = 2;
  do
  {
    v6 = (SDB_DRIVE *)((char *)v6 + 128);
    v10 = *(_OWORD *)v8;
    v8 = (SDB_DRIVE *)((char *)v8 + 128);
    *((_OWORD *)v6 - 8) = v10;
    *((_OWORD *)v6 - 7) = *((_OWORD *)v8 - 7);
    *((_OWORD *)v6 - 6) = *((_OWORD *)v8 - 6);
    *((_OWORD *)v6 - 5) = *((_OWORD *)v8 - 5);
    *((_OWORD *)v6 - 4) = *((_OWORD *)v8 - 4);
    *((_OWORD *)v6 - 3) = *((_OWORD *)v8 - 3);
    *((_OWORD *)v6 - 2) = *((_OWORD *)v8 - 2);
    *((_OWORD *)v6 - 1) = *((_OWORD *)v8 - 1);
    --v9;
  }
  while ( v9 );
  *(_OWORD *)v6 = *(_OWORD *)v8;
  *((_OWORD *)v6 + 1) = *((_OWORD *)v8 + 1);
  *((_OWORD *)v6 + 2) = *((_OWORD *)v8 + 2);
  *((_OWORD *)v6 + 3) = *((_OWORD *)v8 + 3);
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = 0;
  *((_QWORD *)v7 + 9) = 0;
  *((_QWORD *)v7 + 10) = 0;
  *((_QWORD *)v7 + 11) = 0;
  *((_QWORD *)v7 + 12) = 0;
  *((_QWORD *)v7 + 24) = 0;
  *((_QWORD *)v7 + 26) = 0;
  v11 = (unsigned __int16 *)*((_QWORD *)this + 6);
  if ( !v11 || (int)SpStringCchCopyHelper(v11, 0x100u, (unsigned __int16 **)v7 + 6) >= 0 )
  {
    v12 = (unsigned __int16 *)*((_QWORD *)this + 7);
    if ( !v12 || (int)SpStringCchCopyHelper(v12, 0x400u, (unsigned __int16 **)v7 + 7) >= 0 )
    {
      v13 = (unsigned __int16 *)*((_QWORD *)this + 9);
      if ( !v13 || (int)SpStringCchCopyHelper(v13, 0x100u, (unsigned __int16 **)v7 + 9) >= 0 )
      {
        v14 = (unsigned __int16 *)*((_QWORD *)this + 10);
        if ( !v14 || (int)SpStringCchCopyHelper(v14, 0x100u, (unsigned __int16 **)v7 + 10) >= 0 )
        {
          v15 = (unsigned __int16 *)*((_QWORD *)this + 11);
          if ( !v15 || (int)SpStringCchCopyHelper(v15, 0x100u, (unsigned __int16 **)v7 + 11) >= 0 )
          {
            v16 = (unsigned __int16 *)*((_QWORD *)this + 12);
            if ( !v16 || (int)SpStringCchCopyHelper(v16, 0x100u, (unsigned __int16 **)v7 + 12) >= 0 )
            {
              if ( *((_QWORD *)this + 24) )
              {
                v17 = (SC_SPARSE *)ExAllocatePool2(64, 80, 1633185875);
                if ( !v17 )
                {
                  *((_QWORD *)v7 + 24) = 0;
                  goto LABEL_6;
                }
                v5 = SC_SPARSE::SC_SPARSE(v17);
                *((_QWORD *)v7 + 24) = v5;
                if ( !v5
                  || (int)SC_SPARSE::Initialize(v5, *(_QWORD *)(*((_QWORD *)this + 24) + 64LL)) < 0
                  || (int)SC_SPARSE::Copy(*((SC_SPARSE **)this + 24), *((struct SC_SPARSE **)v7 + 24)) < 0 )
                {
                  goto LABEL_6;
                }
              }
              if ( *((_QWORD *)this + 26) )
              {
                v18 = (ULONG *)SC_ENV::Allocate(
                                 ((unsigned int)(*((_DWORD *)this + 50) + 31) >> 3) & 0x1FFFFFFC,
                                 0x64427053u,
                                 1u,
                                 0);
                if ( !v18 )
                  goto LABEL_6;
                RtlInitializeBitMap_0((PRTL_BITMAP)((char *)v7 + 200), v18, *((_DWORD *)this + 50));
                RtlCopyBitMap((char *)this + 200, (char *)v7 + 200, 0);
              }
              return v7;
            }
          }
        }
      }
    }
  }
LABEL_6:
  (**(void (__fastcall ***)(SDB_DRIVE *, __int64))v7)(v7, 1);
  return 0;
}

```

## disassembly

```asm
0x14001a880  push    rsi
0x14001a882  push    rdi
0x14001a883  sub     rsp, 38h
0x14001a887  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14001a88e  mov     rdi, rcx
0x14001a891  mov     edx, 40h ; '@'
0x14001a896  xor     esi, esi
0x14001a898  mov     ecx, 100h
0x14001a89d  mov     r8d, 64427053h
0x14001a8a3  cmp     [rax+1BAh], sil
0x14001a8aa  cmovz   ecx, edx
0x14001a8ad  mov     edx, 140h
0x14001a8b2  call    cs:__imp_ExAllocatePool2
0x14001a8b9  nop     dword ptr [rax+rax+00h]
0x14001a8be  test    rax, rax
0x14001a8c1  jnz     short loc_14001A921
0x14001a8c3  mov     eax, esi
0x14001a8c5  add     rsp, 38h
0x14001a8c9  pop     rdi
0x14001a8ca  pop     rsi
0x14001a8cb  retn
0x14001a8cd  mov     rcx, rax; this
0x14001a8d0  call    ??0SC_SPARSE@@QEAA@XZ; SC_SPARSE::SC_SPARSE(void)
0x14001a8d5  mov     [rbx+0C0h], rax
0x14001a8dc  test    rax, rax
0x14001a8df  jnz     loc_14001AB2A
0x14001a8e5  mov     rcx, [rbx]
0x14001a8e8  mov     edx, 1
0x14001a8ed  mov     rax, [rcx]
0x14001a8f0  mov     rcx, rbx
0x14001a8f3  call    _guard_dispatch_icall
0x14001a8f8  mov     rax, rsi
0x14001a8fb  mov     r14, [rsp+48h+var_20]
0x14001a900  mov     r13, [rsp+48h+var_18]
0x14001a905  mov     r12, [rsp+48h+arg_10]
0x14001a90a  mov     rbp, [rsp+48h+arg_8]
0x14001a90f  mov     r15, [rsp+48h+var_28]
0x14001a914  mov     rbx, [rsp+48h+arg_0]
0x14001a919  add     rsp, 38h
0x14001a91d  pop     rdi
0x14001a91e  pop     rsi
0x14001a91f  retn
0x14001a921  mov     rcx, rax; this
0x14001a924  mov     [rsp+48h+arg_0], rbx
0x14001a929  call    ??0SDB_DRIVE@@QEAA@XZ; SDB_DRIVE::SDB_DRIVE(void)
0x14001a92e  mov     rbx, rax
0x14001a931  test    rax, rax
0x14001a934  jz      loc_14001AB65
0x14001a93a  mov     [rsp+48h+arg_8], rbp
0x14001a93f  mov     rcx, rdi
0x14001a942  mov     [rsp+48h+arg_10], r12
0x14001a947  mov     edx, 2
0x14001a94c  mov     [rsp+48h+var_18], r13
0x14001a951  mov     [rsp+48h+var_20], r14
0x14001a956  mov     [rsp+48h+var_28], r15
0x14001a95b  lea     rax, [rax+80h]
0x14001a962  movups  xmm0, xmmword ptr [rcx]
0x14001a965  lea     rcx, [rcx+80h]
0x14001a96c  movups  xmmword ptr [rax-80h], xmm0
0x14001a970  movups  xmm1, xmmword ptr [rcx-70h]
0x14001a974  movups  xmmword ptr [rax-70h], xmm1
0x14001a978  movups  xmm0, xmmword ptr [rcx-60h]
0x14001a97c  movups  xmmword ptr [rax-60h], xmm0
0x14001a980  movups  xmm1, xmmword ptr [rcx-50h]
0x14001a984  movups  xmmword ptr [rax-50h], xmm1
0x14001a988  movups  xmm0, xmmword ptr [rcx-40h]
0x14001a98c  movups  xmmword ptr [rax-40h], xmm0
0x14001a990  movups  xmm1, xmmword ptr [rcx-30h]
0x14001a994  movups  xmmword ptr [rax-30h], xmm1
0x14001a998  movups  xmm0, xmmword ptr [rcx-20h]
0x14001a99c  movups  xmmword ptr [rax-20h], xmm0
0x14001a9a0  movups  xmm1, xmmword ptr [rcx-10h]
0x14001a9a4  movups  xmmword ptr [rax-10h], xmm1
0x14001a9a8  sub     rdx, 1
0x14001a9ac  jnz     short loc_14001A95B
0x14001a9ae  movups  xmm0, xmmword ptr [rcx]
0x14001a9b1  lea     r8, [rbx+30h]; unsigned __int16 **
0x14001a9b5  movups  xmmword ptr [rax], xmm0
0x14001a9b8  movups  xmm1, xmmword ptr [rcx+10h]
0x14001a9bc  movups  xmmword ptr [rax+10h], xmm1
0x14001a9c0  movups  xmm0, xmmword ptr [rcx+20h]
0x14001a9c4  movups  xmmword ptr [rax+20h], xmm0
0x14001a9c8  movups  xmm1, xmmword ptr [rcx+30h]
0x14001a9cc  movups  xmmword ptr [rax+30h], xmm1
0x14001a9d0  xor     eax, eax
0x14001a9d2  mov     [r8], rax
0x14001a9d5  mov     [rbx+38h], rax
0x14001a9d9  mov     [rbx+48h], rax
0x14001a9dd  mov     [rbx+50h], rax
0x14001a9e1  mov     [rbx+58h], rax
0x14001a9e5  mov     [rbx+60h], rax
0x14001a9e9  mov     [rbx+0C0h], rax
0x14001a9f0  mov     [rbx+0D0h], rax
0x14001a9f7  mov     rcx, [rdi+30h]; unsigned __int16 *
0x14001a9fb  test    rcx, rcx
0x14001a9fe  jnz     loc_14001AAA7
0x14001aa04  mov     rcx, [rdi+38h]; unsigned __int16 *
0x14001aa08  test    rcx, rcx
0x14001aa0b  jnz     loc_14001AABE
0x14001aa11  mov     rcx, [rdi+48h]; unsigned __int16 *
0x14001aa15  test    rcx, rcx
0x14001aa18  jnz     loc_14001AAD9
0x14001aa1e  mov     rcx, [rdi+50h]; unsigned __int16 *
0x14001aa22  test    rcx, rcx
0x14001aa25  jnz     short loc_14001AA90
0x14001aa27  mov     rcx, [rdi+58h]; unsigned __int16 *
0x14001aa2b  test    rcx, rcx
0x14001aa2e  jnz     loc_14001AAF4
0x14001aa34  mov     rcx, [rdi+60h]; unsigned __int16 *
0x14001aa38  test    rcx, rcx
0x14001aa3b  jnz     loc_14001AB0F
0x14001aa41  cmp     [rdi+0C0h], rsi
0x14001aa48  jz      short loc_14001AA7B
0x14001aa4a  mov     edx, 50h ; 'P'
0x14001aa4f  mov     ecx, 40h ; '@'
0x14001aa54  mov     r8d, 61587053h
0x14001aa5a  call    cs:__imp_ExAllocatePool2
0x14001aa61  nop     dword ptr [rax+rax+00h]
0x14001aa66  test    rax, rax
0x14001aa69  jnz     loc_14001A8CD
0x14001aa6f  mov     [rbx+0C0h], rsi
0x14001aa76  jmp     loc_14001A8E5
0x14001aa7b  cmp     [rdi+0D0h], rsi
0x14001aa82  jnz     loc_14006AD3A
0x14001aa88  mov     rax, rbx
0x14001aa8b  jmp     loc_14001A8FB
0x14001aa90  lea     r8, [rbx+50h]; unsigned __int16 **
0x14001aa94  mov     edx, 100h; unsigned int
0x14001aa99  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x14001aa9e  test    eax, eax
0x14001aaa0  jns     short loc_14001AA27
0x14001aaa2  jmp     loc_14001A8E5
0x14001aaa7  mov     edx, 100h; unsigned int
0x14001aaac  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x14001aab1  test    eax, eax
0x14001aab3  js      loc_14001A8E5
0x14001aab9  jmp     loc_14001AA04
0x14001aabe  lea     r8, [rbx+38h]; unsigned __int16 **
0x14001aac2  mov     edx, 400h; unsigned int
0x14001aac7  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x14001aacc  test    eax, eax
0x14001aace  js      loc_14001A8E5
0x14001aad4  jmp     loc_14001AA11
0x14001aad9  lea     r8, [rbx+48h]; unsigned __int16 **
0x14001aadd  mov     edx, 100h; unsigned int
0x14001aae2  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x14001aae7  test    eax, eax
0x14001aae9  js      loc_14001A8E5
0x14001aaef  jmp     loc_14001AA1E
0x14001aaf4  lea     r8, [rbx+58h]; unsigned __int16 **
0x14001aaf8  mov     edx, 100h; unsigned int
0x14001aafd  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x14001ab02  test    eax, eax
0x14001ab04  js      loc_14001A8E5
0x14001ab0a  jmp     loc_14001AA34
0x14001ab0f  lea     r8, [rbx+60h]; unsigned __int16 **
0x14001ab13  mov     edx, 100h; unsigned int
0x14001ab18  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x14001ab1d  test    eax, eax
0x14001ab1f  js      loc_14001A8E5
0x14001ab25  jmp     loc_14001AA41
0x14001ab2a  mov     rdx, [rdi+0C0h]
0x14001ab31  mov     rcx, rax; this
0x14001ab34  mov     rdx, [rdx+40h]; unsigned __int64
0x14001ab38  call    ?Initialize@SC_SPARSE@@QEAAJ_K@Z; SC_SPARSE::Initialize(unsigned __int64)
0x14001ab3d  test    eax, eax
0x14001ab3f  js      loc_14001A8E5
0x14001ab45  mov     rdx, [rbx+0C0h]; struct SC_SPARSE *
0x14001ab4c  mov     rcx, [rdi+0C0h]; this
0x14001ab53  call    ?Copy@SC_SPARSE@@QEAAJPEAV1@@Z; SC_SPARSE::Copy(SC_SPARSE *)
0x14001ab58  test    eax, eax
0x14001ab5a  js      loc_14001A8E5
0x14001ab60  jmp     loc_14001AA7B
0x14001ab65  mov     rax, rsi
0x14001ab68  jmp     loc_14001A914
0x14006ad3a  mov     ecx, [rdi+0C8h]
0x14006ad40  xor     r9d, r9d; unsigned int
0x14006ad43  add     ecx, 1Fh
0x14006ad46  mov     r8b, 1; unsigned __int8
0x14006ad49  shr     rcx, 3
0x14006ad4d  mov     edx, 64427053h; unsigned int
0x14006ad52  and     ecx, 1FFFFFFCh; unsigned __int64
0x14006ad58  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14006ad5d  test    rax, rax
0x14006ad60  jz      loc_14001A8E5
0x14006ad66  mov     r8d, [rdi+0C8h]; SizeOfBitMap
0x14006ad6d  lea     rcx, [rbx+0C8h]; BitMapHeader
0x14006ad74  mov     rdx, rax; BitMapBuffer
0x14006ad77  call    RtlInitializeBitMap_0
0x14006ad7c  xor     r8d, r8d
0x14006ad7f  lea     rdx, [rbx+0C8h]
0x14006ad86  lea     rcx, [rdi+0C8h]
0x14006ad8d  call    cs:__imp_RtlCopyBitMap
0x14006ad94  nop     dword ptr [rax+rax+00h]
0x14006ad99  nop
0x14006ad9a  jmp     loc_14001AA88
```

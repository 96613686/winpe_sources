# CSetupClnClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800047e0`
- end: `0x1800048e9`
- name: `?CreateInstance@CSetupClnClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(CSetupClnClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800019e4`
- `0x1800047e0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CSetupClnClassFactory::CreateInstance(
        CSetupClnClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v7; // rax
  char *v8; // rbx
  unsigned int v9; // edi

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v7 = *(_QWORD *)&GUID_84e04a55_2d42_4909_86e3_62fd11483e8b.Data1 - *(_QWORD *)((char *)this + 12);
  if ( *(_QWORD *)&GUID_84e04a55_2d42_4909_86e3_62fd11483e8b.Data1 == *(_QWORD *)((char *)this + 12) )
    v7 = *(_QWORD *)GUID_84e04a55_2d42_4909_86e3_62fd11483e8b.Data4 - *(_QWORD *)((char *)this + 20);
  if ( v7 )
    return 2147746065LL;
  v8 = (char *)operator new(0x60u);
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 1;
    *(_QWORD *)v8 = &CSetupFilesCleanup::`vftable';
    *((_QWORD *)v8 + 2) = 0;
    *((_DWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 5) = 0;
    *(_QWORD *)(v8 + 52) = 0;
    *((_DWORD *)v8 + 15) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 9) = 0;
    *((_QWORD *)v8 + 10) = 0;
    _InterlockedIncrement(&dword_18001FBD4);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v9 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v8)(v8, a3, a4);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x1800047e0  mov     [rsp+arg_0], rbx
0x1800047e5  mov     [rsp+arg_8], rbp
0x1800047ea  push    rsi
0x1800047eb  push    rdi
0x1800047ec  push    r14
0x1800047ee  sub     rsp, 20h
0x1800047f2  xor     r14d, r14d
0x1800047f5  mov     rsi, r9
0x1800047f8  mov     rbp, r8
0x1800047fb  test    r9, r9
0x1800047fe  jnz     short loc_18000480A
0x180004800  mov     eax, 80070057h
0x180004805  jmp     loc_1800048D6
0x18000480a  mov     [r9], r14
0x18000480d  test    rdx, rdx
0x180004810  jz      short loc_18000481C
0x180004812  mov     eax, 80040110h
0x180004817  jmp     loc_1800048D6
0x18000481c  mov     rax, qword ptr cs:_GUID_84e04a55_2d42_4909_86e3_62fd11483e8b.Data1
0x180004823  sub     rax, [rcx+0Ch]
0x180004827  jnz     short loc_180004834
0x180004829  mov     rax, qword ptr cs:_GUID_84e04a55_2d42_4909_86e3_62fd11483e8b.Data4
0x180004830  sub     rax, [rcx+14h]
0x180004834  test    rax, rax
0x180004837  jnz     loc_1800048D1
0x18000483d  lea     ecx, [rax+60h]; Size
0x180004840  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004845  mov     [rsp+38h+arg_18], rax
0x18000484a  mov     rbx, rax
0x18000484d  test    rax, rax
0x180004850  jz      short loc_180004890
0x180004852  lea     rax, ??_7CSetupFilesCleanup@@6B@; const CSetupFilesCleanup::`vftable'
0x180004859  mov     dword ptr [rbx+8], 1
0x180004860  mov     [rbx], rax
0x180004863  mov     [rbx+10h], r14
0x180004867  mov     [rbx+18h], r14d
0x18000486b  mov     [rbx+20h], r14
0x18000486f  mov     [rbx+28h], r14
0x180004873  mov     [rbx+34h], r14
0x180004877  mov     [rbx+3Ch], r14d
0x18000487b  mov     [rbx+40h], r14
0x18000487f  mov     [rbx+48h], r14
0x180004883  mov     [rbx+50h], r14
0x180004887  lock inc cs:dword_18001FBD4
0x18000488e  jmp     short loc_180004893
0x180004890  mov     rbx, r14
0x180004893  test    rbx, rbx
0x180004896  mov     edi, r14d
0x180004899  mov     eax, 8007000Eh
0x18000489e  cmovz   edi, eax
0x1800048a1  jz      short loc_1800048CD
0x1800048a3  mov     rax, [rbx]
0x1800048a6  mov     r8, rsi
0x1800048a9  mov     rdx, rbp
0x1800048ac  mov     rcx, rbx
0x1800048af  mov     rax, [rax]
0x1800048b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b7  mov     edi, eax
0x1800048b9  test    rbx, rbx
0x1800048bc  jz      short loc_1800048CD
0x1800048be  mov     rax, [rbx]
0x1800048c1  mov     rcx, rbx
0x1800048c4  mov     rax, [rax+10h]
0x1800048c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048cd  mov     eax, edi
0x1800048cf  jmp     short loc_1800048D6
0x1800048d1  mov     eax, 80040111h
0x1800048d6  mov     rbx, [rsp+38h+arg_0]
0x1800048db  mov     rbp, [rsp+38h+arg_8]
0x1800048e0  add     rsp, 20h
0x1800048e4  pop     r14
0x1800048e6  pop     rdi
0x1800048e7  pop     rsi
0x1800048e8  retn
```

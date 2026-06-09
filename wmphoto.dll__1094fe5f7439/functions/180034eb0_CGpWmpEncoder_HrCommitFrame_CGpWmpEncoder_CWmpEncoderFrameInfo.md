# CGpWmpEncoder::HrCommitFrame(CGpWmpEncoder::CWmpEncoderFrameInfo *)

- ea: `0x180034eb0`
- end: `0x180034fc1`
- name: `?HrCommitFrame@CGpWmpEncoder@@UEAAJPEAUCWmpEncoderFrameInfo@1@@Z`
- size: `273`
- prototype: `__int64 __fastcall(CGpWmpEncoder *__hidden this, struct CGpWmpEncoder::CWmpEncoderFrameInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002be10`

## callees

- `0x180034eb0`
- `0x18003a160`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall CGpWmpEncoder::HrCommitFrame(CGpWmpEncoder *this, struct CGpWmpEncoder::CWmpEncoderFrameInfo *a2)
{
  char *v4; // rcx
  _QWORD *v5; // rdx
  int v6; // edx
  int v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  v8 = 0;
  if ( *((_DWORD *)this + 4) == 3 )
  {
    v4 = (char *)this + 104;
    v5 = (_QWORD *)*((_QWORD *)v4 + 1);
    if ( v5 == *((_QWORD **)v4 + 2) )
    {
      try
      {
        std::vector<IWICColorContext *>::_Emplace_reallocate<IWICColorContext * const &>(v4, v5, a2);
      }
      catch ( std::bad_alloc )
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      *v5 = *(_QWORD *)a2;
      *((_QWORD *)v4 + 1) += 8LL;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 12) + 40LL))(
           *((_QWORD *)this + 12),
           0,
           1,
           &v9);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 12) + 40LL))(
             *((_QWORD *)this + 12),
             *((unsigned int *)this + 32),
             0,
             0);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD, struct CGpWmpEncoder::CWmpEncoderFrameInfo *, __int64, int *))(**((_QWORD **)this + 12) + 32LL))(
               *((_QWORD *)this + 12),
               a2,
               4,
               &v8);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 12) + 40LL))(
                 *((_QWORD *)this + 12),
                 v9,
                 0,
                 0);
          if ( v6 >= 0 )
          {
            *((_DWORD *)this + 32) = *(_DWORD *)a2 + 12 * *((_DWORD *)a2 + 1) + 2;
            *((_DWORD *)this + 4) = 2;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2003292412;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180034eb0  mov     [rsp+arg_8], rbx
0x180034eb5  push    rdi
0x180034eb6  sub     rsp, 30h
0x180034eba  mov     rdi, rdx
0x180034ebd  mov     rbx, rcx
0x180034ec0  mov     [rsp+38h+arg_10], 0
0x180034ec9  mov     [rsp+38h+arg_0], 0
0x180034ed1  cmp     dword ptr [rcx+10h], 3
0x180034ed5  jnz     loc_180034FAF
0x180034edb  add     rcx, 68h ; 'h'
0x180034edf  mov     rdx, [rcx+8]
0x180034ee3  cmp     rdx, [rcx+10h]
0x180034ee7  jz      short loc_180034EF6
0x180034ee9  mov     rax, [rdi]
0x180034eec  mov     [rdx], rax
0x180034eef  add     qword ptr [rcx+8], 8
0x180034ef4  jmp     short loc_180034EFF
0x180034ef6  mov     r8, rdi
0x180034ef9  call    ??$_Emplace_reallocate@AEBQEAUIWICColorContext@@@?$vector@PEAUIWICColorContext@@V?$allocator@PEAUIWICColorContext@@@std@@@std@@AEAAPEAPEAUIWICColorContext@@QEAPEAU2@AEBQEAU2@@Z; std::vector<IWICColorContext *>::_Emplace_reallocate<IWICColorContext * const &>(IWICColorContext * * const,IWICColorContext * const &)
0x180034efe  nop
0x180034eff  mov     rcx, [rbx+60h]
0x180034f03  xor     edx, edx
0x180034f05  mov     rax, [rcx]
0x180034f08  lea     r9, [rsp+38h+arg_10]
0x180034f0d  lea     r8d, [rdx+1]
0x180034f11  mov     rax, [rax+28h]
0x180034f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f1a  mov     edx, eax
0x180034f1c  test    eax, eax
0x180034f1e  js      loc_180034FB4
0x180034f24  mov     rcx, [rbx+60h]
0x180034f28  mov     edx, [rbx+80h]
0x180034f2e  mov     rax, [rcx]
0x180034f31  xor     r9d, r9d
0x180034f34  xor     r8d, r8d
0x180034f37  mov     rax, [rax+28h]
0x180034f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f40  mov     edx, eax
0x180034f42  test    eax, eax
0x180034f44  js      short loc_180034FB4
0x180034f46  mov     rcx, [rbx+60h]
0x180034f4a  mov     rax, [rcx]
0x180034f4d  lea     r9, [rsp+38h+arg_0]
0x180034f52  mov     r8d, 4
0x180034f58  mov     rdx, rdi
0x180034f5b  mov     rax, [rax+20h]
0x180034f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f64  mov     edx, eax
0x180034f66  test    eax, eax
0x180034f68  js      short loc_180034FB4
0x180034f6a  mov     rcx, [rbx+60h]
0x180034f6e  mov     rax, [rcx]
0x180034f71  xor     r9d, r9d
0x180034f74  xor     r8d, r8d
0x180034f77  mov     rdx, [rsp+38h+arg_10]
0x180034f7c  mov     rax, [rax+28h]
0x180034f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f85  mov     edx, eax
0x180034f87  test    eax, eax
0x180034f89  js      short loc_180034FB4
0x180034f8b  mov     eax, [rdi+4]
0x180034f8e  lea     ecx, [rax+rax*2]
0x180034f91  lea     ecx, ds:2[rcx*4]
0x180034f98  add     ecx, [rdi]
0x180034f9a  mov     [rbx+80h], ecx
0x180034fa0  mov     dword ptr [rbx+10h], 2
0x180034fa7  jmp     short loc_180034FB4
0x180034fa9  mov     edx, [rsp+38h+arg_0]
0x180034fad  jmp     short loc_180034FB4
0x180034faf  mov     edx, 88982F04h
0x180034fb4  mov     eax, edx
0x180034fb6  mov     rbx, [rsp+38h+arg_8]
0x180034fbb  add     rsp, 30h
0x180034fbf  pop     rdi
0x180034fc0  retn
```

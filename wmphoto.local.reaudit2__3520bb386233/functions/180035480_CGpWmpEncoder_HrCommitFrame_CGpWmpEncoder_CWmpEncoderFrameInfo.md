# CGpWmpEncoder::HrCommitFrame(CGpWmpEncoder::CWmpEncoderFrameInfo *)

- ea: `0x180035480`
- end: `0x180035592`
- name: `?HrCommitFrame@CGpWmpEncoder@@UEAAJPEAUCWmpEncoderFrameInfo@1@@Z`
- size: `274`
- prototype: `__int64 __fastcall(CGpWmpEncoder *__hidden this, struct CGpWmpEncoder::CWmpEncoderFrameInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002c090`

## callees

- `0x180035480`
- `0x18003a8ac`
- `0x180045010`

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
0x180035480  mov     [rsp+arg_8], rbx
0x180035485  push    rdi
0x180035486  sub     rsp, 30h
0x18003548a  mov     rdi, rdx
0x18003548d  mov     rbx, rcx
0x180035490  mov     [rsp+38h+arg_10], 0
0x180035499  mov     [rsp+38h+arg_0], 0
0x1800354a1  cmp     dword ptr [rcx+10h], 3
0x1800354a5  jnz     loc_18003557F
0x1800354ab  add     rcx, 68h ; 'h'
0x1800354af  mov     rdx, [rcx+8]
0x1800354b3  cmp     rdx, [rcx+10h]
0x1800354b7  jz      short loc_1800354C6
0x1800354b9  mov     rax, [rdi]
0x1800354bc  mov     [rdx], rax
0x1800354bf  add     qword ptr [rcx+8], 8
0x1800354c4  jmp     short loc_1800354CF
0x1800354c6  mov     r8, rdi
0x1800354c9  call    ??$_Emplace_reallocate@AEBQEAUIWICColorContext@@@?$vector@PEAUIWICColorContext@@V?$allocator@PEAUIWICColorContext@@@std@@@std@@AEAAPEAPEAUIWICColorContext@@QEAPEAU2@AEBQEAU2@@Z; std::vector<IWICColorContext *>::_Emplace_reallocate<IWICColorContext * const &>(IWICColorContext * * const,IWICColorContext * const &)
0x1800354ce  nop
0x1800354cf  mov     rcx, [rbx+60h]
0x1800354d3  xor     edx, edx
0x1800354d5  mov     rax, [rcx]
0x1800354d8  lea     r9, [rsp+38h+arg_10]
0x1800354dd  lea     r8d, [rdx+1]
0x1800354e1  mov     rax, [rax+28h]
0x1800354e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354ea  mov     edx, eax
0x1800354ec  test    eax, eax
0x1800354ee  js      loc_180035584
0x1800354f4  mov     rcx, [rbx+60h]
0x1800354f8  mov     edx, [rbx+80h]
0x1800354fe  mov     rax, [rcx]
0x180035501  xor     r9d, r9d
0x180035504  xor     r8d, r8d
0x180035507  mov     rax, [rax+28h]
0x18003550b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035510  mov     edx, eax
0x180035512  test    eax, eax
0x180035514  js      short loc_180035584
0x180035516  mov     rcx, [rbx+60h]
0x18003551a  mov     rax, [rcx]
0x18003551d  lea     r9, [rsp+38h+arg_0]
0x180035522  mov     r8d, 4
0x180035528  mov     rdx, rdi
0x18003552b  mov     rax, [rax+20h]
0x18003552f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035534  mov     edx, eax
0x180035536  test    eax, eax
0x180035538  js      short loc_180035584
0x18003553a  mov     rcx, [rbx+60h]
0x18003553e  mov     rax, [rcx]
0x180035541  xor     r9d, r9d
0x180035544  xor     r8d, r8d
0x180035547  mov     rdx, [rsp+38h+arg_10]
0x18003554c  mov     rax, [rax+28h]
0x180035550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035555  mov     edx, eax
0x180035557  test    eax, eax
0x180035559  js      short loc_180035584
0x18003555b  mov     eax, [rdi+4]
0x18003555e  lea     ecx, [rax+rax*2]
0x180035561  lea     ecx, ds:2[rcx*4]
0x180035568  add     ecx, [rdi]
0x18003556a  mov     [rbx+80h], ecx
0x180035570  mov     dword ptr [rbx+10h], 2
0x180035577  jmp     short loc_180035584
0x180035579  mov     edx, [rsp+38h+arg_0]
0x18003557d  jmp     short loc_180035584
0x18003557f  mov     edx, 88982F04h
0x180035584  mov     eax, edx
0x180035586  mov     rbx, [rsp+38h+arg_8]
0x18003558b  add     rsp, 30h
0x18003558f  pop     rdi
0x180035590  retn
```

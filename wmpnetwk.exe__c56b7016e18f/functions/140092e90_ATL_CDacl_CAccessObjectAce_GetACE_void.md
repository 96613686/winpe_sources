# ATL::CDacl::CAccessObjectAce::GetACE(void)

- ea: `0x140092e90`
- end: `0x140092f98`
- name: `?GetACE@CAccessObjectAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `264`
- prototype: `void *__fastcall(ATL::CDacl::CAccessObjectAce *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1400396dc`
- `0x140046d00`
- `0x140054390`
- `0x140092e90`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x140092f6a`
- `ADVAPI32!GetLengthSid` at `0x140092f6a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140092ebc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140092ebc`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessObjectAce::GetACE(ATL::CDacl::CAccessObjectAce *this)
{
  char *v1; // rdi
  size_t v3; // rbx
  char *v4; // rax
  __int64 v5; // rax
  char v6; // al
  __int128 *v7; // rdx
  ATL::Checked *v8; // rbp
  int v9; // ecx
  __int128 v10; // xmm0
  __int128 *v11; // rax
  __int128 v12; // xmm0
  DWORD LengthSid; // eax
  unsigned __int64 v15; // [rsp+20h] [rbp-28h]

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessObjectAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = (char *)malloc(v3);
    v1 = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
    memset_0(v4, 0, v3);
    v1[1] = *((_BYTE *)this + 132);
    v5 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    v6 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessObjectAce *))(v5 + 24))(this);
    v7 = (__int128 *)*((_QWORD *)this + 19);
    v8 = (ATL::Checked *)(v1 + 44);
    *v1 = v6;
    *(_QWORD *)(v1 + 4) = *((unsigned int *)this + 32);
    if ( v7 )
    {
      v10 = *v7;
      *((_DWORD *)v1 + 2) = 1;
      v9 = 3;
      *(_OWORD *)(v1 + 12) = v10;
    }
    else
    {
      v8 = (ATL::Checked *)(v1 + 28);
      v9 = 2;
    }
    v11 = (__int128 *)*((_QWORD *)this + 20);
    if ( v11 )
    {
      v12 = *v11;
      if ( v7 )
        *(_OWORD *)(v1 + 28) = v12;
      else
        *(_OWORD *)(v1 + 12) = v12;
      *((_DWORD *)v1 + 2) = v9;
    }
    else
    {
      v8 = (ATL::Checked *)((char *)v8 - 16);
    }
    LengthSid = GetLengthSid((char *)this + 16);
    ATL::Checked::memcpy_s(
      v8,
      (void *)(v8 - (ATL::Checked *)v1),
      (unsigned __int64)this + 16,
      (const void *)LengthSid,
      v15);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x140092e90  push    rbx
0x140092e92  push    rbp
0x140092e93  push    rsi
0x140092e94  push    rdi
0x140092e95  sub     rsp, 28h
0x140092e99  mov     rdi, [rcx+88h]
0x140092ea0  mov     rsi, rcx
0x140092ea3  test    rdi, rdi
0x140092ea6  jnz     loc_140092F8C
0x140092eac  mov     rax, [rcx]
0x140092eaf  mov     rax, [rax+10h]
0x140092eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092eb8  mov     ecx, eax; Size
0x140092eba  mov     ebx, eax
0x140092ebc  call    cs:__imp_malloc
0x140092ec2  mov     rdi, rax
0x140092ec5  test    rax, rax
0x140092ec8  jnz     short loc_140092ED5
0x140092eca  mov     ecx, 8007000Eh; int
0x140092ecf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140092ed5  mov     r8, rbx; Size
0x140092ed8  xor     edx, edx; Val
0x140092eda  mov     rcx, rdi; void *
0x140092edd  call    memset_0
0x140092ee2  mov     al, [rsi+84h]
0x140092ee8  mov     rcx, rsi
0x140092eeb  mov     [rdi+1], al
0x140092eee  mov     rax, [rsi]
0x140092ef1  mov     [rdi+2], bx
0x140092ef5  mov     rax, [rax+18h]
0x140092ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140092efe  mov     rdx, [rsi+98h]
0x140092f05  lea     rbp, [rdi+2Ch]
0x140092f09  mov     [rdi], al
0x140092f0b  mov     eax, [rsi+80h]
0x140092f11  mov     [rdi+4], eax
0x140092f14  mov     dword ptr [rdi+8], 0
0x140092f1b  test    rdx, rdx
0x140092f1e  jnz     short loc_140092F29
0x140092f20  add     rbp, 0FFFFFFFFFFFFFFF0h
0x140092f24  lea     ecx, [rdx+2]
0x140092f27  jmp     short loc_140092F3D
0x140092f29  movups  xmm0, xmmword ptr [rdx]
0x140092f2c  mov     dword ptr [rdi+8], 1
0x140092f33  mov     ecx, 3
0x140092f38  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x140092f3d  mov     rax, [rsi+0A0h]
0x140092f44  test    rax, rax
0x140092f47  jnz     short loc_140092F4F
0x140092f49  sub     rbp, 10h
0x140092f4d  jmp     short loc_140092F66
0x140092f4f  movups  xmm0, xmmword ptr [rax]
0x140092f52  test    rdx, rdx
0x140092f55  jz      short loc_140092F5E
0x140092f57  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x140092f5c  jmp     short loc_140092F63
0x140092f5e  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x140092f63  mov     [rdi+8], ecx
0x140092f66  lea     rcx, [rsi+10h]; pSid
0x140092f6a  call    cs:__imp_GetLengthSid
0x140092f70  mov     rdx, rbp
0x140092f73  mov     r9d, eax; void *
0x140092f76  sub     rdx, rdi; void *
0x140092f79  lea     r8, [rsi+10h]; unsigned __int64
0x140092f7d  mov     rcx, rbp; this
0x140092f80  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x140092f85  mov     [rsi+88h], rdi
0x140092f8c  mov     rax, rdi
0x140092f8f  add     rsp, 28h
0x140092f93  pop     rdi
0x140092f94  pop     rsi
0x140092f95  pop     rbp
0x140092f96  pop     rbx
0x140092f97  retn
```

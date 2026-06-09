# ATL::CDacl::CAccessObjectAce::GetACE(void)

- ea: `0x18006f210`
- end: `0x18006f333`
- name: `?GetACE@CAccessObjectAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `291`
- prototype: `void *__fastcall(ATL::CDacl::CAccessObjectAce *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002c2f4`
- `0x1800529a0`
- `0x18006f210`
- `0x1800829fa`
- `0x180088010`

## import_xrefs

- `msvcrt!malloc` at `0x18006f23c`
- `msvcrt!malloc` at `0x18006f23c`
- `msvcrt!memcpy_s` at `0x18006f30c`
- `msvcrt!memcpy_s` at `0x18006f30c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006f2f0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006f2f0`

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
  char *v8; // rbp
  int v9; // ecx
  __int128 v10; // xmm0
  __int128 *v11; // rax
  __int128 v12; // xmm0
  DWORD LengthSid; // eax
  errno_t v14; // eax

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessObjectAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = (char *)malloc(v3);
    v1 = v4;
    if ( !v4 )
      ATL::PrivateAtlThrow(0x8007000E);
    memset_0(v4, 0, v3);
    v1[1] = *((_BYTE *)this + 132);
    v5 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    v6 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessObjectAce *))(v5 + 24))(this);
    v7 = (__int128 *)*((_QWORD *)this + 19);
    v8 = v1 + 44;
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
      v8 = v1 + 28;
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
      v8 -= 16;
    }
    LengthSid = GetLengthSid((char *)this + 16);
    v14 = memcpy_s(v8, v8 - v1, (char *)this + 16, LengthSid);
    ATL::AtlCrtErrorCheck(v14);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x18006f210  push    rbx
0x18006f212  push    rbp
0x18006f213  push    rsi
0x18006f214  push    rdi
0x18006f215  sub     rsp, 28h
0x18006f219  mov     rdi, [rcx+88h]
0x18006f220  mov     rsi, rcx
0x18006f223  test    rdi, rdi
0x18006f226  jnz     loc_18006F326
0x18006f22c  mov     rax, [rcx]
0x18006f22f  mov     rax, [rax+10h]
0x18006f233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f238  mov     ecx, eax; Size
0x18006f23a  mov     ebx, eax
0x18006f23c  call    cs:__imp_malloc
0x18006f243  nop     dword ptr [rax+rax+00h]
0x18006f248  mov     rdi, rax
0x18006f24b  test    rax, rax
0x18006f24e  jnz     short loc_18006F25B
0x18006f250  mov     ecx, 8007000Eh; unsigned int
0x18006f255  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18006f25b  mov     r8, rbx; Size
0x18006f25e  xor     edx, edx; Val
0x18006f260  mov     rcx, rdi; void *
0x18006f263  call    memset_0
0x18006f268  mov     al, [rsi+84h]
0x18006f26e  mov     rcx, rsi
0x18006f271  mov     [rdi+1], al
0x18006f274  mov     rax, [rsi]
0x18006f277  mov     [rdi+2], bx
0x18006f27b  mov     rax, [rax+18h]
0x18006f27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f284  mov     rdx, [rsi+98h]
0x18006f28b  lea     rbp, [rdi+2Ch]
0x18006f28f  mov     [rdi], al
0x18006f291  mov     eax, [rsi+80h]
0x18006f297  mov     [rdi+4], eax
0x18006f29a  mov     dword ptr [rdi+8], 0
0x18006f2a1  test    rdx, rdx
0x18006f2a4  jnz     short loc_18006F2AF
0x18006f2a6  add     rbp, 0FFFFFFFFFFFFFFF0h
0x18006f2aa  lea     ecx, [rdx+2]
0x18006f2ad  jmp     short loc_18006F2C3
0x18006f2af  movups  xmm0, xmmword ptr [rdx]
0x18006f2b2  mov     dword ptr [rdi+8], 1
0x18006f2b9  mov     ecx, 3
0x18006f2be  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18006f2c3  mov     rax, [rsi+0A0h]
0x18006f2ca  test    rax, rax
0x18006f2cd  jnz     short loc_18006F2D5
0x18006f2cf  sub     rbp, 10h
0x18006f2d3  jmp     short loc_18006F2EC
0x18006f2d5  movups  xmm0, xmmword ptr [rax]
0x18006f2d8  test    rdx, rdx
0x18006f2db  jz      short loc_18006F2E4
0x18006f2dd  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x18006f2e2  jmp     short loc_18006F2E9
0x18006f2e4  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18006f2e9  mov     [rdi+8], ecx
0x18006f2ec  lea     rcx, [rsi+10h]; pSid
0x18006f2f0  call    cs:__imp_GetLengthSid
0x18006f2f7  nop     dword ptr [rax+rax+00h]
0x18006f2fc  mov     rdx, rbp
0x18006f2ff  mov     r9d, eax; SourceSize
0x18006f302  sub     rdx, rdi; DestinationSize
0x18006f305  lea     r8, [rsi+10h]; Source
0x18006f309  mov     rcx, rbp; Destination
0x18006f30c  call    cs:__imp_memcpy_s
0x18006f313  nop     dword ptr [rax+rax+00h]
0x18006f318  mov     ecx, eax; int
0x18006f31a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006f31f  mov     [rsi+88h], rdi
0x18006f326  mov     rax, rdi
0x18006f329  add     rsp, 28h
0x18006f32d  pop     rdi
0x18006f32e  pop     rsi
0x18006f32f  pop     rbp
0x18006f330  pop     rbx
0x18006f331  retn
```

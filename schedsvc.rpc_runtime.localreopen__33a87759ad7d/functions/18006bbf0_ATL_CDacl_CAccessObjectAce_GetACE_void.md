# ATL::CDacl::CAccessObjectAce::GetACE(void)

- ea: `0x18006bbf0`
- end: `0x18006bd00`
- name: `?GetACE@CAccessObjectAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `272`
- prototype: `void *__fastcall(ATL::CDacl::CAccessObjectAce *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001fc54`
- `0x1800504b4`
- `0x18006bbf0`
- `0x18007e68a`
- `0x180084010`

## import_xrefs

- `msvcrt!malloc` at `0x18006bc1c`
- `msvcrt!malloc` at `0x18006bc1c`
- `msvcrt!memcpy_s` at `0x18006bce0`
- `msvcrt!memcpy_s` at `0x18006bce0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006bcca`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006bcca`

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
0x18006bbf0  push    rbx
0x18006bbf2  push    rbp
0x18006bbf3  push    rsi
0x18006bbf4  push    rdi
0x18006bbf5  sub     rsp, 28h
0x18006bbf9  mov     rdi, [rcx+88h]
0x18006bc00  mov     rsi, rcx
0x18006bc03  test    rdi, rdi
0x18006bc06  jnz     loc_18006BCF4
0x18006bc0c  mov     rax, [rcx]
0x18006bc0f  mov     rax, [rax+10h]
0x18006bc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc18  mov     ecx, eax; Size
0x18006bc1a  mov     ebx, eax
0x18006bc1c  call    cs:__imp_malloc
0x18006bc22  mov     rdi, rax
0x18006bc25  test    rax, rax
0x18006bc28  jnz     short loc_18006BC35
0x18006bc2a  mov     ecx, 8007000Eh; unsigned int
0x18006bc2f  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18006bc35  mov     r8, rbx; Size
0x18006bc38  xor     edx, edx; Val
0x18006bc3a  mov     rcx, rdi; void *
0x18006bc3d  call    memset_0
0x18006bc42  mov     al, [rsi+84h]
0x18006bc48  mov     rcx, rsi
0x18006bc4b  mov     [rdi+1], al
0x18006bc4e  mov     rax, [rsi]
0x18006bc51  mov     [rdi+2], bx
0x18006bc55  mov     rax, [rax+18h]
0x18006bc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc5e  mov     rdx, [rsi+98h]
0x18006bc65  lea     rbp, [rdi+2Ch]
0x18006bc69  mov     [rdi], al
0x18006bc6b  mov     eax, [rsi+80h]
0x18006bc71  mov     [rdi+4], eax
0x18006bc74  mov     dword ptr [rdi+8], 0
0x18006bc7b  test    rdx, rdx
0x18006bc7e  jnz     short loc_18006BC89
0x18006bc80  add     rbp, 0FFFFFFFFFFFFFFF0h
0x18006bc84  lea     ecx, [rdx+2]
0x18006bc87  jmp     short loc_18006BC9D
0x18006bc89  movups  xmm0, xmmword ptr [rdx]
0x18006bc8c  mov     dword ptr [rdi+8], 1
0x18006bc93  mov     ecx, 3
0x18006bc98  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18006bc9d  mov     rax, [rsi+0A0h]
0x18006bca4  test    rax, rax
0x18006bca7  jnz     short loc_18006BCAF
0x18006bca9  sub     rbp, 10h
0x18006bcad  jmp     short loc_18006BCC6
0x18006bcaf  movups  xmm0, xmmword ptr [rax]
0x18006bcb2  test    rdx, rdx
0x18006bcb5  jz      short loc_18006BCBE
0x18006bcb7  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x18006bcbc  jmp     short loc_18006BCC3
0x18006bcbe  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18006bcc3  mov     [rdi+8], ecx
0x18006bcc6  lea     rcx, [rsi+10h]; pSid
0x18006bcca  call    cs:__imp_GetLengthSid
0x18006bcd0  mov     rdx, rbp
0x18006bcd3  mov     r9d, eax; SourceSize
0x18006bcd6  sub     rdx, rdi; DestinationSize
0x18006bcd9  lea     r8, [rsi+10h]; Source
0x18006bcdd  mov     rcx, rbp; Destination
0x18006bce0  call    cs:__imp_memcpy_s
0x18006bce6  mov     ecx, eax; int
0x18006bce8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006bced  mov     [rsi+88h], rdi
0x18006bcf4  mov     rax, rdi
0x18006bcf7  add     rsp, 28h
0x18006bcfb  pop     rdi
0x18006bcfc  pop     rsi
0x18006bcfd  pop     rbp
0x18006bcfe  pop     rbx
0x18006bcff  retn
```

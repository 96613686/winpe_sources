# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x180025f94`
- end: `0x180026247`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `691`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180029730`
- `0x180029890`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x180005504`
- `0x180006e48`
- `0x180025f94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180026150`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18002618f`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800261a7`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800261dc`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180026150`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18002618f`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800261a7`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800261dc`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180025fc1`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180025fc1`
- `RPCRT4!UuidCreate` at `0x18002605e`
- `RPCRT4!UuidCreate` at `0x1800260db`
- `RPCRT4!UuidCreate` at `0x18002605e`
- `RPCRT4!UuidCreate` at `0x1800260db`

## pseudocode

```c
struct TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::Extend(const char *a1)
{
  __int64 v2; // rax
  char v3; // al
  __int64 v4; // rbp
  unsigned __int64 v5; // rdi
  char *v6; // rax
  char *v7; // rbx
  char *v8; // rax
  _BYTE *v9; // rsi
  char v10; // r15
  struct TraceLoggingCorrelationVector *result; // rax
  UUID Uuid; // [rsp+20h] [rbp-48h] BYREF

  v2 = strchr(a1, 46) - a1;
  if ( v2 == 22 )
  {
    v3 = 2;
  }
  else
  {
    if ( v2 != 16 )
      return 0;
    v3 = 1;
  }
  v4 = 65;
  if ( v3 != 1 )
    v4 = 129;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  if ( v5 >= v4 - 1 && (v5 != v4 - 1 || a1[v5 - 1] != 33) )
    return 0;
  if ( v3 == 1 )
  {
    v8 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v7 = v8;
    if ( v8 )
    {
      v8[130] = 65;
      Uuid = 0;
      UuidCreate(&Uuid);
      v7[129] = 17;
      *((_QWORD *)v7 + 17) = 0x1300000000LL;
      memset_0(v7, 0, 0x81u);
      TLV::Base64Encode<129>(&Uuid, 12, v7);
      *((_WORD *)v7 + 8) = 46;
      goto LABEL_19;
    }
  }
  else
  {
    if ( v3 != 2 )
      return 0;
    v6 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      v6[130] = -127;
      Uuid = 0;
      UuidCreate(&Uuid);
      v7[129] = 23;
      *((_QWORD *)v7 + 17) = 0x1900000000LL;
      memset_0(v7, 0, 0x81u);
      TLV::Base64Encode<129>(&Uuid, 16, v7);
      *((_WORD *)v7 + 11) = 46;
      goto LABEL_19;
    }
  }
  v7 = 0;
LABEL_19:
  if ( v7 )
  {
    if ( v5 && a1[v5 - 1] == 33 )
    {
      _o_strncpy_s(v7, 129, a1, v5 - 1);
      v9 = v7 + 129;
      v7[129] = v5 - 1;
      *((_QWORD *)v7 + 17) = (v5 + 1) << 32;
    }
    else
    {
      v9 = v7 + 129;
      if ( v5 == v4 - 2 )
      {
        _o_strncpy_s(v7, 129, a1, v5);
        *v9 = v5;
      }
      else
      {
        v10 = v5 + 1;
        if ( v5 != v4 - 3 )
        {
          _o_strncpy_s(v7, 129, a1, v5);
          v7[v5] = 46;
          *v9 = v10;
          *((_QWORD *)v7 + 17) = (v5 + 3) << 32;
          *((_QWORD *)v7 + 17) &= ~0x8000000000000000uLL;
          goto LABEL_30;
        }
        _o_strncpy_s(v7, 129, a1, v5);
        v7[v5] = 46;
        *v9 = v10;
      }
      *((_QWORD *)v7 + 17) = v4 << 32;
    }
    *((_QWORD *)v7 + 17) |= 0x8000000000000000uLL;
LABEL_30:
    result = (struct TraceLoggingCorrelationVector *)v7;
    v7[(unsigned __int8)*v9] = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180025f94  mov     [rsp+arg_8], rbx
0x180025f99  mov     [rsp+arg_10], rbp
0x180025f9e  push    rsi
0x180025f9f  push    rdi
0x180025fa0  push    r13
0x180025fa2  push    r14
0x180025fa4  push    r15
0x180025fa6  sub     rsp, 40h
0x180025faa  mov     rax, cs:__security_cookie
0x180025fb1  xor     rax, rsp
0x180025fb4  mov     [rsp+68h+var_38], rax
0x180025fb9  mov     edx, 2Eh ; '.'; Val
0x180025fbe  mov     r14, rcx
0x180025fc1  call    cs:__imp_strchr
0x180025fc7  sub     rax, r14
0x180025fca  cmp     rax, 16h
0x180025fce  jnz     short loc_180025FD4
0x180025fd0  mov     al, 2
0x180025fd2  jmp     short loc_180025FE0
0x180025fd4  cmp     rax, 10h
0x180025fd8  jnz     loc_18002621F
0x180025fde  mov     al, 1
0x180025fe0  mov     ebp, 41h ; 'A'
0x180025fe5  cmp     al, 1
0x180025fe7  lea     r13d, [rbp+40h]
0x180025feb  cmovnz  ebp, r13d
0x180025fef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025ff3  inc     rdi
0x180025ff6  cmp     byte ptr [r14+rdi], 0
0x180025ffb  jnz     short loc_180025FF3
0x180025ffd  lea     rcx, [rbp-1]
0x180026001  cmp     rdi, rcx
0x180026004  jb      short loc_180026018
0x180026006  jnz     loc_18002621F
0x18002600c  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x180026012  jnz     loc_18002621F
0x180026018  movzx   ecx, al
0x18002601b  sub     ecx, 1
0x18002601e  jz      loc_1800260AE
0x180026024  cmp     ecx, 1
0x180026027  jnz     loc_18002621F
0x18002602d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026034  mov     ecx, 90h; unsigned __int64
0x180026039  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002603e  mov     rbx, rax
0x180026041  test    rax, rax
0x180026044  jz      loc_18002612B
0x18002604a  xorps   xmm0, xmm0
0x18002604d  mov     [rax+82h], r13b
0x180026054  lea     rcx, [rsp+68h+Uuid]; Uuid
0x180026059  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18002605e  call    cs:__imp_UuidCreate
0x180026064  movaps  xmm0, xmmword ptr [rsp+68h+Uuid.Data1]
0x180026069  mov     rax, 1900000000h
0x180026073  movdqa  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x180026079  mov     r8, r13; Size
0x18002607c  mov     byte ptr [rbx+81h], 17h
0x180026083  xor     edx, edx; Val
0x180026085  mov     rcx, rbx; void *
0x180026088  mov     [rbx+88h], rax
0x18002608f  call    memset_0
0x180026094  mov     r8, rbx
0x180026097  lea     rcx, [rsp+68h+Uuid]
0x18002609c  mov     edx, 10h
0x1800260a1  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1800260a6  mov     word ptr [rbx+16h], 2Eh ; '.'
0x1800260ac  jmp     short loc_18002612D
0x1800260ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800260b5  mov     ecx, 90h; unsigned __int64
0x1800260ba  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800260bf  mov     rbx, rax
0x1800260c2  test    rax, rax
0x1800260c5  jz      short loc_18002612B
0x1800260c7  xorps   xmm0, xmm0
0x1800260ca  mov     byte ptr [rax+82h], 41h ; 'A'
0x1800260d1  lea     rcx, [rsp+68h+Uuid]; Uuid
0x1800260d6  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x1800260db  call    cs:__imp_UuidCreate
0x1800260e1  movaps  xmm0, xmmword ptr [rsp+68h+Uuid.Data1]
0x1800260e6  mov     rax, 1300000000h
0x1800260f0  movdqa  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x1800260f6  mov     r8, r13; Size
0x1800260f9  mov     byte ptr [rbx+81h], 11h
0x180026100  xor     edx, edx; Val
0x180026102  mov     rcx, rbx; void *
0x180026105  mov     [rbx+88h], rax
0x18002610c  call    memset_0
0x180026111  mov     r8, rbx
0x180026114  lea     rcx, [rsp+68h+Uuid]
0x180026119  mov     edx, 0Ch
0x18002611e  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180026123  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180026129  jmp     short loc_18002612D
0x18002612b  xor     ebx, ebx
0x18002612d  test    rbx, rbx
0x180026130  jz      loc_18002621F
0x180026136  test    rdi, rdi
0x180026139  jz      short loc_180026173
0x18002613b  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x180026141  jnz     short loc_180026173
0x180026143  lea     r9, [rdi-1]
0x180026147  mov     r8, r14
0x18002614a  mov     rdx, r13
0x18002614d  mov     rcx, rbx
0x180026150  call    cs:__imp__o_strncpy_s
0x180026156  lea     eax, [rdi-1]
0x180026159  lea     rsi, [rbx+81h]
0x180026160  mov     [rsi], al
0x180026162  lea     rax, [rdi+1]
0x180026166  shl     rax, 20h
0x18002616a  mov     [rbx+88h], rax
0x180026171  jmp     short loc_1800261BF
0x180026173  lea     rax, [rbp-2]
0x180026177  mov     r9, rdi
0x18002617a  lea     rsi, [rbx+81h]
0x180026181  mov     r8, r14
0x180026184  mov     rdx, r13
0x180026187  mov     rcx, rbx
0x18002618a  cmp     rdi, rax
0x18002618d  jnz     short loc_18002619A
0x18002618f  call    cs:__imp__o_strncpy_s
0x180026195  mov     [rsi], dil
0x180026198  jmp     short loc_1800261B4
0x18002619a  lea     rax, [rbp-3]
0x18002619e  lea     r15d, [rdi+1]
0x1800261a2  cmp     rdi, rax
0x1800261a5  jnz     short loc_1800261DC
0x1800261a7  call    cs:__imp__o_strncpy_s
0x1800261ad  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x1800261b1  mov     [rsi], r15b
0x1800261b4  shl     rbp, 20h
0x1800261b8  mov     [rbx+88h], rbp
0x1800261bf  mov     rax, [rbx+88h]
0x1800261c6  mov     rcx, 8000000000000000h
0x1800261d0  or      rax, rcx
0x1800261d3  mov     [rbx+88h], rax
0x1800261da  jmp     short loc_180026213
0x1800261dc  call    cs:__imp__o_strncpy_s
0x1800261e2  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x1800261e6  lea     rcx, [rdi+3]
0x1800261ea  shl     rcx, 20h
0x1800261ee  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800261f8  mov     [rsi], r15b
0x1800261fb  mov     [rbx+88h], rcx
0x180026202  mov     rcx, [rbx+88h]
0x180026209  and     rcx, rax
0x18002620c  mov     [rbx+88h], rcx
0x180026213  movzx   ecx, byte ptr [rsi]
0x180026216  mov     rax, rbx
0x180026219  mov     byte ptr [rcx+rbx], 0
0x18002621d  jmp     short loc_180026221
0x18002621f  xor     eax, eax
0x180026221  mov     rcx, [rsp+68h+var_38]
0x180026226  xor     rcx, rsp; StackCookie
0x180026229  call    __security_check_cookie
0x18002622e  lea     r11, [rsp+68h+var_28]
0x180026233  mov     rbx, [r11+38h]
0x180026237  mov     rbp, [r11+40h]
0x18002623b  mov     rsp, r11
0x18002623e  pop     r15
0x180026240  pop     r14
0x180026242  pop     r13
0x180026244  pop     rdi
0x180026245  pop     rsi
0x180026246  retn
```

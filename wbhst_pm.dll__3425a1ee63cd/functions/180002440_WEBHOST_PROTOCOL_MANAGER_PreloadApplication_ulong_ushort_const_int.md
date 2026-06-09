# WEBHOST_PROTOCOL_MANAGER::PreloadApplication(ulong,ushort const *,int)

- ea: `0x180002440`
- end: `0x1800025b3`
- name: `?PreloadApplication@WEBHOST_PROTOCOL_MANAGER@@UEAAJKPEBGH@Z`
- size: `371`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *this, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002440`
- `0x1800031f8`
- `0x180004842`
- `0x180004880`
- `0x180005010`

## import_xrefs

- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000254a`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000254a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002527`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002527`
- `iisutil!SkipTo` at `0x1800024dd`
- `iisutil!SkipTo` at `0x1800024dd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000250e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000250e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002575`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002575`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002494`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002494`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::PreloadApplication(
        WEBHOST_PROTOCOL_MANAGER *this,
        unsigned int a2,
        unsigned __int16 *a3)
{
  int v6; // ebx
  int v7; // ebx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rdx
  _BYTE v14[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v17[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v18[256]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v14, v18, 0x100u);
  if ( *((_QWORD *)this + 10) )
  {
    v6 = StringCchPrintfW(v17, 0x20u, L"/LM/W3SVC/%u/ROOT", a2);
    if ( v6 >= 0 )
    {
      v7 = 0;
      v8 = a3;
      while ( 1 )
      {
        v9 = SkipTo(v8, 0x2Fu);
        v10 = v9;
        if ( !v9 )
          break;
        v8 = v9 + 1;
        if ( v7 == 3 )
          v8 = (unsigned __int16 *)v10;
        if ( ++v7 >= 4 )
        {
          v10 = v8;
          goto LABEL_10;
        }
      }
      if ( v7 != 3 )
      {
        v6 = -2147024893;
        goto LABEL_16;
      }
LABEL_10:
      v6 = STRU::Copy((STRU *)v14, v17);
      if ( v6 >= 0 )
      {
        if ( !v10 || (v6 = STRU::Append((STRU *)v14, v10), v6 >= 0) )
        {
          v11 = v15;
          v12 = (unsigned int)(v16 - 1);
          if ( *(_WORD *)(v15 + 2 * v12) == 47 )
          {
            STRU::SetLen((STRU *)v14, v12);
            v11 = v15;
          }
          v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64, __int64))(**((_QWORD **)this + 10) + 32LL))(
                 *((_QWORD *)this + 10),
                 a3,
                 v11,
                 1);
        }
      }
    }
  }
  else
  {
    v6 = -2147467263;
  }
LABEL_16:
  STRU::~STRU((STRU *)v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002440  mov     [rsp-8+arg_18], rbx
0x180002445  push    rbp
0x180002446  push    rsi
0x180002447  push    rdi
0x180002448  push    r14
0x18000244a  push    r15
0x18000244c  lea     rbp, [rsp-1C0h]
0x180002454  sub     rsp, 2C0h
0x18000245b  mov     rax, cs:__security_cookie
0x180002462  xor     rax, rsp
0x180002465  mov     [rbp+1E0h+var_30], rax
0x18000246c  mov     rsi, r8
0x18000246f  mov     ebx, edx
0x180002471  mov     r14, rcx
0x180002474  xor     edx, edx; Val
0x180002476  mov     r8d, 200h; Size
0x18000247c  lea     rcx, [rbp+1E0h+var_230]; void *
0x180002480  call    memset_0
0x180002485  mov     r8d, 100h
0x18000248b  lea     rdx, [rbp+1E0h+var_230]
0x18000248f  lea     rcx, [rsp+2E0h+var_2B0]
0x180002494  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000249a  cmp     qword ptr [r14+50h], 0
0x18000249f  jnz     short loc_1800024AB
0x1800024a1  mov     ebx, 80004001h
0x1800024a6  jmp     loc_180002570
0x1800024ab  mov     r9d, ebx
0x1800024ae  lea     r8, aLmW3svcURoot; "/LM/W3SVC/%u/ROOT"
0x1800024b5  mov     edx, 20h ; ' '; unsigned __int64
0x1800024ba  lea     rcx, [rsp+2E0h+var_270]; unsigned __int16 *
0x1800024bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800024c4  mov     ebx, eax
0x1800024c6  test    eax, eax
0x1800024c8  js      loc_180002570
0x1800024ce  xor     ebx, ebx
0x1800024d0  mov     rax, rsi
0x1800024d3  lea     r15d, [rbx+2Fh]
0x1800024d7  mov     edx, r15d
0x1800024da  mov     rcx, rax
0x1800024dd  call    cs:__imp_?SkipTo@@YAPEAGPEAGG@Z; SkipTo(ushort *,ushort)
0x1800024e3  mov     rdi, rax
0x1800024e6  test    rax, rax
0x1800024e9  jz      loc_1800025A3
0x1800024ef  add     rax, 2
0x1800024f3  cmp     ebx, 3
0x1800024f6  cmovz   rax, rdi
0x1800024fa  inc     ebx
0x1800024fc  cmp     ebx, 4
0x1800024ff  jl      short loc_1800024D7
0x180002501  mov     rdi, rax
0x180002504  lea     rdx, [rsp+2E0h+var_270]
0x180002509  lea     rcx, [rsp+2E0h+var_2B0]
0x18000250e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002514  mov     ebx, eax
0x180002516  test    eax, eax
0x180002518  js      short loc_180002570
0x18000251a  test    rdi, rdi
0x18000251d  jz      short loc_180002533
0x18000251f  mov     rdx, rdi
0x180002522  lea     rcx, [rsp+2E0h+var_2B0]
0x180002527  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000252d  mov     ebx, eax
0x18000252f  test    eax, eax
0x180002531  js      short loc_180002570
0x180002533  mov     edx, [rsp+2E0h+var_280]
0x180002537  mov     r8, [rsp+2E0h+var_290]
0x18000253c  dec     edx
0x18000253e  cmp     [r8+rdx*2], r15w
0x180002543  jnz     short loc_180002555
0x180002545  lea     rcx, [rsp+2E0h+var_2B0]
0x18000254a  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180002550  mov     r8, [rsp+2E0h+var_290]
0x180002555  mov     rcx, [r14+50h]
0x180002559  mov     r9d, 1
0x18000255f  mov     rdx, rsi
0x180002562  mov     rax, [rcx]
0x180002565  mov     rax, [rax+20h]
0x180002569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000256e  mov     ebx, eax
0x180002570  lea     rcx, [rsp+2E0h+var_2B0]
0x180002575  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000257b  mov     eax, ebx
0x18000257d  mov     rcx, [rbp+1E0h+var_30]
0x180002584  xor     rcx, rsp; StackCookie
0x180002587  call    __security_check_cookie
0x18000258c  mov     rbx, [rsp+2E0h+arg_18]
0x180002594  add     rsp, 2C0h
0x18000259b  pop     r15
0x18000259d  pop     r14
0x18000259f  pop     rdi
0x1800025a0  pop     rsi
0x1800025a1  pop     rbp
0x1800025a2  retn
0x1800025a3  cmp     ebx, 3
0x1800025a6  jz      loc_180002504
0x1800025ac  mov     ebx, 80070003h
0x1800025b1  jmp     short loc_180002570
```

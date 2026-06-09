# AppendVerbListToHeader(IHttpResponse *,char const *,DAV_VERB *,ulong)

- ea: `0x1800054f8`
- end: `0x1800055fd`
- name: `?AppendVerbListToHeader@@YAJPEAVIHttpResponse@@PEBDPEAUDAV_VERB@@K@Z`
- size: `261`
- prototype: `__int64 __fastcall(struct IHttpResponse *, const char *, struct DAV_VERB *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006434`
- `0x18000e3e8`

## callees

- `0x1800054f8`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000555f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005576`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000555f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005576`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800055d4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800055d4`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180005596`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180005596`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180005528`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180005528`

## pseudocode

```c
__int64 __fastcall AppendVerbListToHeader(struct IHttpResponse *a1, const char *a2, const char **a3, unsigned int a4)
{
  int v8; // ebx
  const char *v9; // rax
  unsigned int v10; // esi
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v13; // [rsp+50h] [rbp-48h]
  unsigned __int16 v14; // [rsp+60h] [rbp-38h]

  STRA::STRA((STRA *)v12);
  if ( a4 )
  {
    v9 = (const char *)(*(__int64 (__fastcall **)(struct IHttpResponse *, const char *, _QWORD))(*(_QWORD *)a1 + 72LL))(
                         a1,
                         a2,
                         0);
    if ( v9 )
    {
      v8 = STRA::Copy((STRA *)v12, v9);
      if ( v8 < 0 )
        goto LABEL_11;
    }
    else
    {
      v8 = STRA::Copy((STRA *)v12, *a3 + 2);
      if ( v8 < 0 )
        goto LABEL_11;
      --a4;
      a3 += 2;
    }
    v10 = 0;
    if ( a4 )
    {
      while ( 1 )
      {
        v8 = STRA::Append((STRA *)v12, a3[2 * v10]);
        if ( v8 < 0 )
          break;
        if ( ++v10 >= a4 )
          goto LABEL_10;
      }
    }
    else
    {
LABEL_10:
      v8 = (*(__int64 (__fastcall **)(struct IHttpResponse *, const char *, __int64, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
             a1,
             a2,
             v13,
             v14,
             1);
    }
  }
  else
  {
    v8 = 0;
  }
LABEL_11:
  STRA::~STRA((STRA *)v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800054f8  mov     [rsp+arg_18], rbx
0x1800054fd  push    rbp
0x1800054fe  push    rsi
0x1800054ff  push    rdi
0x180005500  push    r14
0x180005502  push    r15
0x180005504  sub     rsp, 70h
0x180005508  mov     rax, cs:__security_cookie
0x18000550f  xor     rax, rsp
0x180005512  mov     [rsp+98h+var_30], rax
0x180005517  mov     r15, rcx
0x18000551a  mov     edi, r9d
0x18000551d  lea     rcx, [rsp+98h+var_68]
0x180005522  mov     r14, r8
0x180005525  mov     rbp, rdx
0x180005528  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000552e  test    edi, edi
0x180005530  jnz     short loc_180005539
0x180005532  xor     ebx, ebx
0x180005534  jmp     loc_1800055CF
0x180005539  mov     rax, [r15]
0x18000553c  xor     r8d, r8d
0x18000553f  mov     rdx, rbp
0x180005542  mov     rcx, r15
0x180005545  mov     rax, [rax+48h]
0x180005549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554e  lea     rcx, [rsp+98h+var_68]
0x180005553  test    rax, rax
0x180005556  jnz     short loc_180005573
0x180005558  mov     rdx, [r14]
0x18000555b  add     rdx, 2
0x18000555f  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180005565  mov     ebx, eax
0x180005567  test    eax, eax
0x180005569  js      short loc_1800055CF
0x18000556b  dec     edi
0x18000556d  add     r14, 10h
0x180005571  jmp     short loc_180005582
0x180005573  mov     rdx, rax
0x180005576  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000557c  mov     ebx, eax
0x18000557e  test    eax, eax
0x180005580  js      short loc_1800055CF
0x180005582  xor     esi, esi
0x180005584  test    edi, edi
0x180005586  jz      short loc_1800055A8
0x180005588  mov     edx, esi
0x18000558a  lea     rcx, [rsp+98h+var_68]
0x18000558f  add     rdx, rdx
0x180005592  mov     rdx, [r14+rdx*8]
0x180005596  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000559c  mov     ebx, eax
0x18000559e  test    eax, eax
0x1800055a0  js      short loc_1800055CF
0x1800055a2  inc     esi
0x1800055a4  cmp     esi, edi
0x1800055a6  jb      short loc_180005588
0x1800055a8  mov     rax, [r15]
0x1800055ab  mov     rdx, rbp
0x1800055ae  movzx   r9d, [rsp+98h+var_38]
0x1800055b4  mov     rcx, r15
0x1800055b7  mov     r8, [rsp+98h+var_48]
0x1800055bc  mov     [rsp+98h+var_78], 1
0x1800055c4  mov     rax, [rax+28h]
0x1800055c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055cd  mov     ebx, eax
0x1800055cf  lea     rcx, [rsp+98h+var_68]
0x1800055d4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800055da  mov     eax, ebx
0x1800055dc  mov     rcx, [rsp+98h+var_30]
0x1800055e1  xor     rcx, rsp; StackCookie
0x1800055e4  call    __security_check_cookie
0x1800055e9  mov     rbx, [rsp+98h+arg_18]
0x1800055f1  add     rsp, 70h
0x1800055f5  pop     r15
0x1800055f7  pop     r14
0x1800055f9  pop     rdi
0x1800055fa  pop     rsi
0x1800055fb  pop     rbp
0x1800055fc  retn
```

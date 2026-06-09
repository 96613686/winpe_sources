# OPTIONS_VERB_HANDLER::SetupMsAuthorViaHeader(IHttpContext *)

- ea: `0x18000e57c`
- end: `0x18000e6d7`
- name: `?SetupMsAuthorViaHeader@OPTIONS_VERB_HANDLER@@CAJPEAVIHttpContext@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(struct IHttpContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000e3e8`

## callees

- `0x18000e57c`
- `0x1800224ce`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000e630`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000e630`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000e6a1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000e6b0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000e6a1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000e6b0`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000e648`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000e648`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000e5a2`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000e5a2`

## pseudocode

```c
__int64 __fastcall OPTIONS_VERB_HANDLER::SetupMsAuthorViaHeader(struct IHttpContext *a1)
{
  __int64 v2; // rax
  const char *v3; // rax
  const char *v4; // rdi
  const char *v5; // rbx
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // r9
  _BYTE v10[32]; // [rsp+30h] [rbp-48h] BYREF
  const char *v11; // [rsp+50h] [rbp-28h]

  STRA::STRA((STRA *)v10);
  v2 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  v3 = (const char *)(*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v2 + 72LL))(
                       v2,
                       "MS-Author-Via",
                       0);
  v4 = v3;
  if ( !v3 )
  {
    v5 = "DAV";
    goto LABEL_9;
  }
  if ( strcmp_0(v3, "DAV") )
  {
    v5 = "MS-FP/4.0,DAV";
    if ( strcmp_0(v4, "MS-FP/4.0,DAV") )
    {
      if ( strcmp_0(v4, "MS-FP/4.0") )
      {
        v6 = STRA::Copy((STRA *)v10, v4);
        if ( v6 < 0 )
          goto LABEL_12;
        v6 = STRA::Append((STRA *)v10, ",DAV");
        if ( v6 < 0 )
          goto LABEL_12;
        v5 = v11;
      }
LABEL_9:
      v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
      v8 = -1;
      do
        ++v8;
      while ( v5[v8] );
      v6 = (*(__int64 (__fastcall **)(__int64, const char *, const char *))(*(_QWORD *)v7 + 40LL))(
             v7,
             "MS-Author-Via",
             v5);
LABEL_12:
      STRA::~STRA((STRA *)v10);
      return (unsigned int)v6;
    }
  }
  STRA::~STRA((STRA *)v10);
  return 0;
}

```

## disassembly

```asm
0x18000e57c  mov     [rsp+arg_8], rbx
0x18000e581  mov     [rsp+arg_10], rsi
0x18000e586  push    rdi
0x18000e587  sub     rsp, 70h
0x18000e58b  mov     rax, cs:__security_cookie
0x18000e592  xor     rax, rsp
0x18000e595  mov     [rsp+78h+var_10], rax
0x18000e59a  mov     rsi, rcx
0x18000e59d  lea     rcx, [rsp+78h+var_48]
0x18000e5a2  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000e5a8  mov     rax, [rsi]
0x18000e5ab  mov     rcx, rsi
0x18000e5ae  mov     rax, [rax+20h]
0x18000e5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5b7  mov     r9, rax
0x18000e5ba  lea     rdx, aMsAuthorVia; "MS-Author-Via"
0x18000e5c1  xor     r8d, r8d
0x18000e5c4  mov     rcx, [rax]
0x18000e5c7  mov     rax, [rcx+48h]
0x18000e5cb  mov     rcx, r9
0x18000e5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5d3  mov     rdi, rax
0x18000e5d6  test    rax, rax
0x18000e5d9  jnz     short loc_18000E5E4
0x18000e5db  lea     rbx, aDav_0; "DAV"
0x18000e5e2  jmp     short loc_18000E659
0x18000e5e4  lea     rdx, aDav_0; "DAV"
0x18000e5eb  mov     rcx, rdi; Str1
0x18000e5ee  call    strcmp_0
0x18000e5f3  test    eax, eax
0x18000e5f5  jz      loc_18000E6AB
0x18000e5fb  lea     rbx, aMsFp40Dav; "MS-FP/4.0,DAV"
0x18000e602  mov     rcx, rdi; Str1
0x18000e605  mov     rdx, rbx; Str2
0x18000e608  call    strcmp_0
0x18000e60d  test    eax, eax
0x18000e60f  jz      loc_18000E6AB
0x18000e615  lea     rdx, aMsFp40; "MS-FP/4.0"
0x18000e61c  mov     rcx, rdi; Str1
0x18000e61f  call    strcmp_0
0x18000e624  test    eax, eax
0x18000e626  jz      short loc_18000E659
0x18000e628  mov     rdx, rdi
0x18000e62b  lea     rcx, [rsp+78h+var_48]
0x18000e630  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000e636  mov     ebx, eax
0x18000e638  test    eax, eax
0x18000e63a  js      short loc_18000E69C
0x18000e63c  lea     rdx, aDav_1; ",DAV"
0x18000e643  lea     rcx, [rsp+78h+var_48]
0x18000e648  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000e64e  mov     ebx, eax
0x18000e650  test    eax, eax
0x18000e652  js      short loc_18000E69C
0x18000e654  mov     rbx, [rsp+78h+var_28]
0x18000e659  mov     rax, [rsi]
0x18000e65c  mov     rcx, rsi
0x18000e65f  mov     rax, [rax+20h]
0x18000e663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e668  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000e66c  mov     rcx, [rax]
0x18000e66f  mov     r10, [rcx+28h]
0x18000e673  inc     r9
0x18000e676  cmp     byte ptr [rbx+r9], 0
0x18000e67b  jnz     short loc_18000E673
0x18000e67d  mov     rcx, rax
0x18000e680  mov     [rsp+78h+var_58], 1
0x18000e688  mov     rax, r10
0x18000e68b  lea     rdx, aMsAuthorVia; "MS-Author-Via"
0x18000e692  mov     r8, rbx
0x18000e695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e69a  mov     ebx, eax
0x18000e69c  lea     rcx, [rsp+78h+var_48]
0x18000e6a1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000e6a7  mov     eax, ebx
0x18000e6a9  jmp     short loc_18000E6B8
0x18000e6ab  lea     rcx, [rsp+78h+var_48]
0x18000e6b0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000e6b6  xor     eax, eax
0x18000e6b8  mov     rcx, [rsp+78h+var_10]
0x18000e6bd  xor     rcx, rsp; StackCookie
0x18000e6c0  call    __security_check_cookie
0x18000e6c5  lea     r11, [rsp+78h+var_8]
0x18000e6ca  mov     rbx, [r11+18h]
0x18000e6ce  mov     rsi, [r11+20h]
0x18000e6d2  mov     rsp, r11
0x18000e6d5  pop     rdi
0x18000e6d6  retn
```

# W3WP_HOST::GetApplicationPropertiesFromAppId(ushort const *,ushort *,ulong *,ulong *)

- ea: `0x180001cd0`
- end: `0x180001e56`
- name: `?GetApplicationPropertiesFromAppId@W3WP_HOST@@UEAAJPEBGPEAGPEAK2@Z`
- size: `390`
- prototype: `int(W3WP_HOST *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001cd0`
- `0x18000d2a6`
- `0x18000d2be`
- `0x18000d2f0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180001d75`
- `msvcrt!_wcsupr` at `0x180001d75`
- `msvcrt!wcsstr` at `0x180001d9c`
- `msvcrt!wcsstr` at `0x180001d9c`
- `msvcrt!_wtoi` at `0x180001e0a`
- `msvcrt!_wtoi` at `0x180001e0a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001d66`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001d86`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001d66`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001d86`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001d23`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001d23`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001d47`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001d47`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001e29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001e29`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::GetApplicationPropertiesFromAppId(
        W3WP_HOST *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned __int64 v8; // rbx
  unsigned int v9; // ebx
  wchar_t *Str; // rax
  const wchar_t *v11; // rax
  wchar_t *v12; // rax
  const wchar_t *v13; // rax
  const wchar_t *v14; // rdx
  __int64 v15; // rax
  unsigned int v17; // ecx
  unsigned int v18; // eax
  int v19; // eax
  _BYTE v21[64]; // [rsp+20h] [rbp-278h] BYREF
  unsigned __int16 v22[256]; // [rsp+60h] [rbp-238h] BYREF

  memset_0(v22, 0, sizeof(v22));
  STRU::STRU((STRU *)v21, v22, 0x100u);
  v8 = -1;
  if ( a4 )
  {
    if ( (int)STRU::Copy((STRU *)v21, a2) < 0 )
    {
      v9 = -2147024888;
      goto LABEL_19;
    }
    Str = STRU::QueryStr((STRU *)v21);
    _wcsupr(Str);
    v11 = STRU::QueryStr((STRU *)v21);
    v12 = wcsstr(v11, L"/ROOT");
    if ( !v12 )
    {
LABEL_5:
      v9 = -2147024809;
      goto LABEL_19;
    }
    v13 = v12 + 5;
    v14 = L"/";
    if ( *v13 )
      v14 = v13;
    v15 = -1;
    while ( v14[++v15] != 0 )
      ;
    v17 = v15 + 1;
    v18 = *a4;
    *a4 = v17;
    if ( v18 < v17 )
    {
      v9 = -2147024774;
      goto LABEL_19;
    }
    memcpy_0(a3, v14, 2LL * v17);
  }
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 < 0xB )
    goto LABEL_5;
  v19 = _wtoi(a2 + 10);
  if ( !v19 )
    goto LABEL_5;
  if ( a5 )
    *a5 = v19;
  v9 = 0;
LABEL_19:
  STRU::~STRU((STRU *)v21);
  return v9;
}

```

## disassembly

```asm
0x180001cd0  push    rbx
0x180001cd2  push    rbp
0x180001cd3  push    rsi
0x180001cd4  push    rdi
0x180001cd5  push    r14
0x180001cd7  sub     rsp, 270h
0x180001cde  mov     rax, cs:__security_cookie
0x180001ce5  xor     rax, rsp
0x180001ce8  mov     [rsp+298h+var_38], rax
0x180001cf0  mov     r14, [rsp+298h+arg_20]
0x180001cf8  lea     rcx, [rsp+298h+var_238]; void *
0x180001cfd  mov     rbp, r8
0x180001d00  mov     rdi, rdx
0x180001d03  xor     edx, edx; Val
0x180001d05  mov     r8d, 200h; Size
0x180001d0b  mov     rsi, r9
0x180001d0e  call    memset_0
0x180001d13  mov     r8d, 100h
0x180001d19  lea     rdx, [rsp+298h+var_238]
0x180001d1e  lea     rcx, [rsp+298h+var_278]
0x180001d23  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001d2a  nop     dword ptr [rax+rax+00h]
0x180001d2f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001d36  test    rsi, rsi
0x180001d39  jz      loc_180001DF6
0x180001d3f  mov     rdx, rdi
0x180001d42  lea     rcx, [rsp+298h+var_278]
0x180001d47  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001d4e  nop     dword ptr [rax+rax+00h]
0x180001d53  test    eax, eax
0x180001d55  jns     short loc_180001D61
0x180001d57  mov     ebx, 80070008h
0x180001d5c  jmp     loc_180001E24
0x180001d61  lea     rcx, [rsp+298h+var_278]
0x180001d66  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001d6d  nop     dword ptr [rax+rax+00h]
0x180001d72  mov     rcx, rax; String
0x180001d75  call    cs:__imp__wcsupr
0x180001d7c  nop     dword ptr [rax+rax+00h]
0x180001d81  lea     rcx, [rsp+298h+var_278]
0x180001d86  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001d8d  nop     dword ptr [rax+rax+00h]
0x180001d92  mov     rcx, rax; Str
0x180001d95  lea     rdx, aRoot; "/ROOT"
0x180001d9c  call    cs:__imp_wcsstr
0x180001da3  nop     dword ptr [rax+rax+00h]
0x180001da8  test    rax, rax
0x180001dab  jnz     short loc_180001DB4
0x180001dad  mov     ebx, 80070057h
0x180001db2  jmp     short loc_180001E24
0x180001db4  add     rax, 0Ah
0x180001db8  lea     rdx, asc_18000FCBC; "/"
0x180001dbf  cmp     word ptr [rax], 0
0x180001dc3  cmovnz  rdx, rax; Src
0x180001dc7  mov     rax, rbx
0x180001dca  cmp     word ptr [rdx+rax*2+2], 0
0x180001dd0  lea     rax, [rax+1]
0x180001dd4  jnz     short loc_180001DCA
0x180001dd6  lea     ecx, [rax+1]
0x180001dd9  mov     eax, [rsi]
0x180001ddb  mov     [rsi], ecx
0x180001ddd  cmp     eax, ecx
0x180001ddf  jnb     short loc_180001DE8
0x180001de1  mov     ebx, 8007007Ah
0x180001de6  jmp     short loc_180001E24
0x180001de8  mov     r8d, ecx
0x180001deb  mov     rcx, rbp; void *
0x180001dee  add     r8, r8; Size
0x180001df1  call    memcpy_0
0x180001df6  inc     rbx
0x180001df9  cmp     word ptr [rdi+rbx*2], 0
0x180001dfe  jnz     short loc_180001DF6
0x180001e00  cmp     rbx, 0Bh
0x180001e04  jb      short loc_180001DAD
0x180001e06  lea     rcx, [rdi+14h]; String
0x180001e0a  call    cs:__imp__wtoi
0x180001e11  nop     dword ptr [rax+rax+00h]
0x180001e16  test    eax, eax
0x180001e18  jz      short loc_180001DAD
0x180001e1a  test    r14, r14
0x180001e1d  jz      short loc_180001E22
0x180001e1f  mov     [r14], eax
0x180001e22  xor     ebx, ebx
0x180001e24  lea     rcx, [rsp+298h+var_278]
0x180001e29  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001e30  nop     dword ptr [rax+rax+00h]
0x180001e35  mov     eax, ebx
0x180001e37  mov     rcx, [rsp+298h+var_38]
0x180001e3f  xor     rcx, rsp; StackCookie
0x180001e42  call    __security_check_cookie
0x180001e47  add     rsp, 270h
0x180001e4e  pop     r14
0x180001e50  pop     rdi
0x180001e51  pop     rsi
0x180001e52  pop     rbp
0x180001e53  pop     rbx
0x180001e54  retn
```

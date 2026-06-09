# W3WP_HOST::GetApplicationPropertiesFromAppId(ushort const *,ushort *,ulong *,ulong *)

- ea: `0x180001c30`
- end: `0x180001d85`
- name: `?GetApplicationPropertiesFromAppId@W3WP_HOST@@UEAAJPEBGPEAGPEAK2@Z`
- size: `341`
- prototype: `int(W3WP_HOST *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001c30`
- `0x18000c386`
- `0x18000c39e`
- `0x18000c3d0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180001cc3`
- `msvcrt!_wcsupr` at `0x180001cc3`
- `msvcrt!wcsstr` at `0x180001cde`
- `msvcrt!wcsstr` at `0x180001cde`
- `msvcrt!_wtoi` at `0x180001d46`
- `msvcrt!_wtoi` at `0x180001d46`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001cba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001cce`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001cba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001cce`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001c83`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001c83`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001ca1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001ca1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001d5f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001d5f`

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
0x180001c30  push    rbx
0x180001c32  push    rbp
0x180001c33  push    rsi
0x180001c34  push    rdi
0x180001c35  push    r14
0x180001c37  sub     rsp, 270h
0x180001c3e  mov     rax, cs:__security_cookie
0x180001c45  xor     rax, rsp
0x180001c48  mov     [rsp+298h+var_38], rax
0x180001c50  mov     r14, [rsp+298h+arg_20]
0x180001c58  lea     rcx, [rsp+298h+var_238]; void *
0x180001c5d  mov     rbp, r8
0x180001c60  mov     rdi, rdx
0x180001c63  xor     edx, edx; Val
0x180001c65  mov     r8d, 200h; Size
0x180001c6b  mov     rsi, r9
0x180001c6e  call    memset_0
0x180001c73  mov     r8d, 100h
0x180001c79  lea     rdx, [rsp+298h+var_238]
0x180001c7e  lea     rcx, [rsp+298h+var_278]
0x180001c83  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001c89  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001c90  test    rsi, rsi
0x180001c93  jz      loc_180001D32
0x180001c99  mov     rdx, rdi
0x180001c9c  lea     rcx, [rsp+298h+var_278]
0x180001ca1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001ca7  test    eax, eax
0x180001ca9  jns     short loc_180001CB5
0x180001cab  mov     ebx, 80070008h
0x180001cb0  jmp     loc_180001D5A
0x180001cb5  lea     rcx, [rsp+298h+var_278]
0x180001cba  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001cc0  mov     rcx, rax; String
0x180001cc3  call    cs:__imp__wcsupr
0x180001cc9  lea     rcx, [rsp+298h+var_278]
0x180001cce  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001cd4  mov     rcx, rax; Str
0x180001cd7  lea     rdx, aRoot; "/ROOT"
0x180001cde  call    cs:__imp_wcsstr
0x180001ce4  test    rax, rax
0x180001ce7  jnz     short loc_180001CF0
0x180001ce9  mov     ebx, 80070057h
0x180001cee  jmp     short loc_180001D5A
0x180001cf0  add     rax, 0Ah
0x180001cf4  lea     rdx, asc_18000ECAC; "/"
0x180001cfb  cmp     word ptr [rax], 0
0x180001cff  cmovnz  rdx, rax; Src
0x180001d03  mov     rax, rbx
0x180001d06  cmp     word ptr [rdx+rax*2+2], 0
0x180001d0c  lea     rax, [rax+1]
0x180001d10  jnz     short loc_180001D06
0x180001d12  lea     ecx, [rax+1]
0x180001d15  mov     eax, [rsi]
0x180001d17  mov     [rsi], ecx
0x180001d19  cmp     eax, ecx
0x180001d1b  jnb     short loc_180001D24
0x180001d1d  mov     ebx, 8007007Ah
0x180001d22  jmp     short loc_180001D5A
0x180001d24  mov     r8d, ecx
0x180001d27  mov     rcx, rbp; void *
0x180001d2a  add     r8, r8; Size
0x180001d2d  call    memcpy_0
0x180001d32  inc     rbx
0x180001d35  cmp     word ptr [rdi+rbx*2], 0
0x180001d3a  jnz     short loc_180001D32
0x180001d3c  cmp     rbx, 0Bh
0x180001d40  jb      short loc_180001CE9
0x180001d42  lea     rcx, [rdi+14h]; String
0x180001d46  call    cs:__imp__wtoi
0x180001d4c  test    eax, eax
0x180001d4e  jz      short loc_180001CE9
0x180001d50  test    r14, r14
0x180001d53  jz      short loc_180001D58
0x180001d55  mov     [r14], eax
0x180001d58  xor     ebx, ebx
0x180001d5a  lea     rcx, [rsp+298h+var_278]
0x180001d5f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001d65  mov     eax, ebx
0x180001d67  mov     rcx, [rsp+298h+var_38]
0x180001d6f  xor     rcx, rsp; StackCookie
0x180001d72  call    __security_check_cookie
0x180001d77  add     rsp, 270h
0x180001d7e  pop     r14
0x180001d80  pop     rdi
0x180001d81  pop     rsi
0x180001d82  pop     rbp
0x180001d83  pop     rbx
0x180001d84  retn
```

# SXReader::ElementT(void)

- ea: `0x100405790`
- end: `0x10040598b`
- name: `?ElementT@SXReader@@AEAAXXZ`
- size: `507`
- prototype: `void __fastcall(SXReader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x100404f80`

## callees

- `0x100401350`
- `0x100405790`
- `0x100405a70`
- `0x1004101e0`
- `0x100410ba0`
- `0x1004177d0`
- `0x100424580`

## pseudocode

```c
void __fastcall SXReader::ElementT(SXReader *this)
{
  __int64 v2; // rsi
  char *v3; // rbx
  unsigned int v4; // eax
  char *v5; // rbp
  char *v6; // rbx
  __int64 v7; // rax
  char *v8; // rbp
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r11
  int v14; // eax

  SXReadBase::CheckNSDecl(
    this,
    (const wchar_t *)(*((_QWORD *)this + 148) + 24LL),
    *(_DWORD *)(*((_QWORD *)this + 148) + 16LL),
    (const wchar_t *)(*((_QWORD *)this + 147) + 24LL),
    *(_DWORD *)(*((_QWORD *)this + 147) + 16LL),
    0);
  v2 = *((_QWORD *)this + 188);
  v3 = *(char **)(v2 + 56);
  v4 = *(_DWORD *)(v2 + 52);
  v5 = &v3[128 * (unsigned __int64)v4];
  if ( v3 != v5 )
  {
    do
    {
      (**(void (__fastcall ***)(void *, _QWORD))v3)(v3, 0);
      v3 += 128;
    }
    while ( v3 != v5 );
    v4 = *(_DWORD *)(v2 + 52);
    v3 = *(char **)(v2 + 56);
  }
  memset(v3, 0, (unsigned __int64)v4 << 7);
  *(_DWORD *)(v2 + 52) = 0;
  v6 = *(char **)(v2 + 88);
  v7 = *(unsigned int *)(v2 + 84);
  v8 = &v6[144 * v7];
  if ( v6 != v8 )
  {
    do
    {
      (**(void (__fastcall ***)(void *, _QWORD))v6)(v6, 0);
      v6 += 144;
    }
    while ( v6 != v8 );
    v7 = *(unsigned int *)(v2 + 84);
    v6 = *(char **)(v2 + 88);
  }
  memset(v6, 0, 144 * v7);
  *(_DWORD *)(v2 + 84) = 0;
  while ( SXReadBase::GetNextAttribute(this) )
    SXReader::AttributeT(this);
  LODWORD(v9) = *((_DWORD *)this + 30);
  while ( (unsigned int)v9 > 1 )
  {
    v9 = (unsigned int)(v9 - 1);
    v10 = *((_QWORD *)this + 14) + 48 * v9;
    if ( *(_DWORD *)(v10 + 28) < *((_DWORD *)this + 282) )
      break;
    if ( !*(_BYTE *)(v10 + 32) )
      (*(void (__fastcall **)(SXReader *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 24LL))(
        this,
        *(_QWORD *)v10,
        *(unsigned int *)(v10 + 8),
        *(_QWORD *)(v10 + 16),
        *(_DWORD *)(v10 + 24));
  }
  v11 = *((_QWORD *)this + 185);
  if ( v11 )
  {
    v12 = *((_QWORD *)this + 188);
    v13 = v12 + 16;
    if ( !v12 )
      v13 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, _QWORD, _DWORD, __int64))(*(_QWORD *)v11 + 64LL))(
            v11,
            *((_QWORD *)this + 147) + 24LL,
            *(unsigned int *)(*((_QWORD *)this + 147) + 16LL),
            *((_QWORD *)this + 149) + 24LL,
            *(_DWORD *)(*((_QWORD *)this + 149) + 16LL),
            *((_QWORD *)this + 151),
            *((_DWORD *)this + 304),
            v13);
    if ( v14 < 0 )
    {
      _mm_lfence();
      MXRRaiseException(v14);
      JUMPOUT(0x10040598ALL);
    }
  }
}

```

## disassembly

```asm
0x100405790  mov     [rsp+arg_0], rbx
0x100405795  mov     [rsp+arg_8], rbp
0x10040579a  mov     [rsp+arg_10], rsi
0x10040579f  mov     [rsp+arg_18], rdi
0x1004057a4  push    r14
0x1004057a6  sub     rsp, 50h
0x1004057aa  mov     rax, [rcx+498h]
0x1004057b1  mov     rdi, rcx
0x1004057b4  mov     r8, [rcx+4A0h]
0x1004057bb  mov     [rsp+58h+var_30], 0; bool
0x1004057c0  lea     r9, [rax+18h]; wchar_t *
0x1004057c4  mov     eax, [rax+10h]
0x1004057c7  lea     rdx, [r8+18h]; wchar_t *
0x1004057cb  mov     [rsp+58h+var_38], eax; unsigned int
0x1004057cf  mov     r8d, [r8+10h]; unsigned int
0x1004057d3  call    ?CheckNSDecl@SXReadBase@@IEAAXPEB_WK0K_N@Z; SXReadBase::CheckNSDecl(wchar_t const *,ulong,wchar_t const *,ulong,bool)
0x1004057d8  mov     rsi, [rdi+5E0h]
0x1004057df  mov     rbx, [rsi+38h]
0x1004057e3  mov     eax, [rsi+34h]
0x1004057e6  mov     ebp, eax
0x1004057e8  shl     rbp, 7
0x1004057ec  add     rbp, rbx
0x1004057ef  cmp     rbx, rbp
0x1004057f2  jz      short loc_100405815
0x1004057f4  mov     rax, [rbx]
0x1004057f7  xor     edx, edx
0x1004057f9  mov     rcx, rbx
0x1004057fc  mov     rax, [rax]
0x1004057ff  call    cs:__guard_dispatch_icall_fptr
0x100405805  sub     rbx, 0FFFFFFFFFFFFFF80h
0x100405809  cmp     rbx, rbp
0x10040580c  jnz     short loc_1004057F4
0x10040580e  mov     eax, [rsi+34h]
0x100405811  mov     rbx, [rsi+38h]
0x100405815  mov     r8d, eax
0x100405818  xor     edx, edx; Val
0x10040581a  shl     r8, 7; Size
0x10040581e  mov     rcx, rbx; void *
0x100405821  call    memset
0x100405826  xor     r14d, r14d
0x100405829  mov     [rsi+34h], r14d
0x10040582d  mov     rbx, [rsi+58h]
0x100405831  mov     eax, [rsi+54h]
0x100405834  lea     rbp, [rax+rax*8]
0x100405838  shl     rbp, 4
0x10040583c  add     rbp, rbx
0x10040583f  cmp     rbx, rbp
0x100405842  jz      short loc_100405868
0x100405844  mov     rax, [rbx]
0x100405847  xor     edx, edx
0x100405849  mov     rcx, rbx
0x10040584c  mov     rax, [rax]
0x10040584f  call    cs:__guard_dispatch_icall_fptr
0x100405855  add     rbx, 90h
0x10040585c  cmp     rbx, rbp
0x10040585f  jnz     short loc_100405844
0x100405861  mov     eax, [rsi+54h]
0x100405864  mov     rbx, [rsi+58h]
0x100405868  lea     r8, [rax+rax*8]
0x10040586c  xor     edx, edx; Val
0x10040586e  shl     r8, 4; Size
0x100405872  mov     rcx, rbx; void *
0x100405875  call    memset
0x10040587a  mov     rcx, rdi; this
0x10040587d  mov     [rsi+54h], r14d
0x100405881  call    ?GetNextAttribute@SXReadBase@@IEAA_NXZ; SXReadBase::GetNextAttribute(void)
0x100405886  test    al, al
0x100405888  jz      short loc_1004058A4
0x10040588a  nop     word ptr [rax+rax+00h]
0x100405890  mov     rcx, rdi; this
0x100405893  call    ?AttributeT@SXReader@@AEAAXXZ; SXReader::AttributeT(void)
0x100405898  mov     rcx, rdi; this
0x10040589b  call    ?GetNextAttribute@SXReadBase@@IEAA_NXZ; SXReadBase::GetNextAttribute(void)
0x1004058a0  test    al, al
0x1004058a2  jnz     short loc_100405890
0x1004058a4  mov     ebx, [rdi+78h]
0x1004058a7  cmp     ebx, 1
0x1004058aa  jbe     short loc_1004058F6
0x1004058ac  nop     dword ptr [rax+00h]
0x1004058b0  mov     eax, [rdi+468h]
0x1004058b6  dec     ebx
0x1004058b8  lea     rdx, [rbx+rbx*2]
0x1004058bc  shl     rdx, 4
0x1004058c0  add     rdx, [rdi+70h]
0x1004058c4  cmp     [rdx+1Ch], eax
0x1004058c7  jl      short loc_1004058F6
0x1004058c9  cmp     [rdx+20h], r14b
0x1004058cd  jnz     short loc_1004058F1
0x1004058cf  mov     ecx, [rdx+18h]
0x1004058d2  mov     rax, [rdi]
0x1004058d5  mov     r9, [rdx+10h]
0x1004058d9  mov     r8d, [rdx+8]
0x1004058dd  mov     rdx, [rdx]
0x1004058e0  mov     rax, [rax+18h]
0x1004058e4  mov     [rsp+58h+var_38], ecx
0x1004058e8  mov     rcx, rdi
0x1004058eb  call    cs:__guard_dispatch_icall_fptr
0x1004058f1  cmp     ebx, 1
0x1004058f4  ja      short loc_1004058B0
0x1004058f6  mov     rcx, [rdi+5C8h]
0x1004058fd  test    rcx, rcx
0x100405900  jz      short loc_100405965
0x100405902  mov     rax, [rdi+5E0h]
0x100405909  mov     r10, [rcx]
0x10040590c  test    rax, rax
0x10040590f  mov     r8, [rdi+498h]
0x100405916  mov     rbx, [rdi+4A8h]
0x10040591d  lea     r11, [rax+10h]
0x100405921  mov     rax, [r10+40h]
0x100405925  cmovz   r11, r14
0x100405929  mov     r10d, [rdi+4C0h]
0x100405930  lea     rdx, [r8+18h]
0x100405934  mov     r8d, [r8+10h]
0x100405938  lea     r9, [rbx+18h]
0x10040593c  mov     [rsp+58h+var_20], r11
0x100405941  mov     [rsp+58h+var_28], r10d
0x100405946  mov     r10, [rdi+4B8h]
0x10040594d  mov     qword ptr [rsp+58h+var_30], r10
0x100405952  mov     r10d, [rbx+10h]
0x100405956  mov     [rsp+58h+var_38], r10d
0x10040595b  call    cs:__guard_dispatch_icall_fptr
0x100405961  test    eax, eax
0x100405963  js      short loc_100405980
0x100405965  mov     rbx, [rsp+58h+arg_0]
0x10040596a  mov     rbp, [rsp+58h+arg_8]
0x10040596f  mov     rsi, [rsp+58h+arg_10]
0x100405974  mov     rdi, [rsp+58h+arg_18]
0x100405979  add     rsp, 50h
0x10040597d  pop     r14
0x10040597f  retn
0x100405980  lfence
0x100405983  mov     ecx, eax; int
0x100405985  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```

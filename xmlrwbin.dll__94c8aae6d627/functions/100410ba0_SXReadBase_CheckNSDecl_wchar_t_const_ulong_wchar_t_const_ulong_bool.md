# SXReadBase::CheckNSDecl(wchar_t const *,ulong,wchar_t const *,ulong,bool)

- ea: `0x100410ba0`
- end: `0x100410d0b`
- name: `?CheckNSDecl@SXReadBase@@IEAAXPEB_WK0K_N@Z`
- size: `363`
- prototype: `void __fastcall(SXReadBase *__hidden this, const wchar_t *, unsigned int, const wchar_t *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x100405790`
- `0x100405a70`

## callees

- `0x100401350`
- `0x100410810`
- `0x100410ba0`
- `0x10041b390`

## pseudocode

```c
void __fastcall SXReadBase::CheckNSDecl(
        SXReadBase *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        bool a6)
{
  __int64 v6; // r11
  size_t v10; // rdi
  unsigned int v11; // eax
  const wchar_t *v12; // r8
  const wchar_t *i; // r10
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rbx

  v6 = *((_QWORD *)this + 11);
  v10 = a3;
  if ( !v6 )
    goto LABEL_20;
  v11 = *((_DWORD *)this + 20);
  v12 = &a2[a3];
  for ( i = a2; i < v12; v11 = v14 ^ (33 * v11) )
    v14 = *i++;
  v15 = *(unsigned int *)(v6 + 4LL * (v11 % *((_DWORD *)this + 21)));
  if ( !(_DWORD)v15 )
    goto LABEL_20;
  while ( 1 )
  {
    v16 = *((_QWORD *)this + 14) + 48 * v15;
    if ( (_DWORD)v10 == *(_DWORD *)(v16 + 8) && (!(_DWORD)v10 || !wcsncmp(a2, *(const wchar_t **)v16, v10)) )
      break;
    v15 = *(unsigned int *)(v16 + 40);
    if ( !(_DWORD)v15 )
      goto LABEL_20;
  }
  if ( *(_DWORD *)(v16 + 28) != *((_DWORD *)this + 282) )
  {
    if ( !a6 && *(_DWORD *)(v16 + 24) == a5 && (!a5 || !wcsncmp(a2, *(const wchar_t **)v16, v10)) )
      return;
LABEL_20:
    SXReadBase::PushXmlns(this, a2, v10, a4, a5, a6, *((_DWORD *)this + 282));
    return;
  }
  if ( *(_DWORD *)(v16 + 24) != a5 || a5 && wcsncmp(a2, *(const wchar_t **)v16, v10) )
  {
    MXRRaiseException(-2147467259);
    JUMPOUT(0x100410D0ALL);
  }
  if ( a6 )
    *(_BYTE *)(v16 + 32) = 1;
}

```

## disassembly

```asm
0x100410ba0  mov     [rsp+arg_0], rbx
0x100410ba5  mov     [rsp+arg_8], rbp
0x100410baa  mov     [rsp+arg_10], rsi
0x100410baf  push    rdi
0x100410bb0  push    r12
0x100410bb2  push    r13
0x100410bb4  push    r14
0x100410bb6  push    r15
0x100410bb8  sub     rsp, 40h
0x100410bbc  mov     r11, [rcx+58h]
0x100410bc0  mov     r13, r9
0x100410bc3  movzx   r12d, [rsp+68h+arg_28]
0x100410bcc  mov     r14, rdx
0x100410bcf  mov     r15d, [rsp+68h+arg_20]
0x100410bd7  mov     rsi, rcx
0x100410bda  mov     edi, r8d
0x100410bdd  test    r11, r11
0x100410be0  jz      loc_100410CBB
0x100410be6  mov     eax, [rcx+50h]
0x100410be9  lea     r8, [rdx+rdi*2]
0x100410bed  mov     r10, rdx
0x100410bf0  cmp     rdx, r8
0x100410bf3  jnb     short loc_100410C12
0x100410bf5  nop     word ptr [rax+rax+00000000h]
0x100410c00  movzx   ecx, word ptr [r10]
0x100410c04  add     r10, 2
0x100410c08  imul    eax, 21h ; '!'
0x100410c0b  xor     eax, ecx
0x100410c0d  cmp     r10, r8
0x100410c10  jb      short loc_100410C00
0x100410c12  xor     edx, edx
0x100410c14  div     dword ptr [rsi+54h]
0x100410c17  mov     eax, [r11+rdx*4]
0x100410c1b  test    eax, eax
0x100410c1d  jz      loc_100410CBB
0x100410c23  nop     dword ptr [rax+00h]
0x100410c27  nop     word ptr [rax+rax+00000000h]
0x100410c30  lea     rbx, [rax+rax*2]
0x100410c34  shl     rbx, 4
0x100410c38  add     rbx, [rsi+70h]
0x100410c3c  cmp     edi, [rbx+8]
0x100410c3f  jnz     short loc_100410C57
0x100410c41  test    edi, edi
0x100410c43  jz      short loc_100410C60
0x100410c45  mov     rdx, [rbx]; String2
0x100410c48  mov     r8, rdi; MaxCount
0x100410c4b  mov     rcx, r14; String1
0x100410c4e  call    wcsncmp
0x100410c53  test    eax, eax
0x100410c55  jz      short loc_100410C60
0x100410c57  mov     eax, [rbx+28h]
0x100410c5a  test    eax, eax
0x100410c5c  jnz     short loc_100410C30
0x100410c5e  jmp     short loc_100410CBB
0x100410c60  mov     eax, [rsi+468h]
0x100410c66  cmp     [rbx+1Ch], eax
0x100410c69  jnz     short loc_100410C99
0x100410c6b  mov     eax, r15d
0x100410c6e  cmp     [rbx+18h], eax
0x100410c71  jnz     loc_100410D00
0x100410c77  test    eax, eax
0x100410c79  jz      short loc_100410C8D
0x100410c7b  mov     rdx, [rbx]; String2
0x100410c7e  mov     r8, rdi; MaxCount
0x100410c81  mov     rcx, r14; String1
0x100410c84  call    wcsncmp
0x100410c89  test    eax, eax
0x100410c8b  jnz     short loc_100410D00
0x100410c8d  cmp     r12b, 0
0x100410c91  jz      short loc_100410CE0
0x100410c93  mov     byte ptr [rbx+20h], 1
0x100410c97  jmp     short loc_100410CE0
0x100410c99  test    r12b, r12b
0x100410c9c  jnz     short loc_100410CBB
0x100410c9e  cmp     [rbx+18h], r15d
0x100410ca2  jnz     short loc_100410CBB
0x100410ca4  test    r15d, r15d
0x100410ca7  jz      short loc_100410CE0
0x100410ca9  mov     rdx, [rbx]; String2
0x100410cac  mov     r8, rdi; MaxCount
0x100410caf  mov     rcx, r14; String1
0x100410cb2  call    wcsncmp
0x100410cb7  test    eax, eax
0x100410cb9  jz      short loc_100410CE0
0x100410cbb  mov     eax, [rsi+468h]
0x100410cc1  mov     r9, r13; wchar_t *
0x100410cc4  mov     [rsp+68h+var_38], eax; int
0x100410cc8  mov     r8d, edi; unsigned int
0x100410ccb  mov     [rsp+68h+var_40], r12b; bool
0x100410cd0  mov     rdx, r14; wchar_t *
0x100410cd3  mov     rcx, rsi; this
0x100410cd6  mov     [rsp+68h+var_48], r15d; unsigned int
0x100410cdb  call    ?PushXmlns@SXReadBase@@IEAAXPEB_WK0K_NH@Z; SXReadBase::PushXmlns(wchar_t const *,ulong,wchar_t const *,ulong,bool,int)
0x100410ce0  mov     rbx, [rsp+68h+arg_0]
0x100410ce5  mov     rbp, [rsp+68h+arg_8]
0x100410cea  mov     rsi, [rsp+68h+arg_10]
0x100410cf2  add     rsp, 40h
0x100410cf6  pop     r15
0x100410cf8  pop     r14
0x100410cfa  pop     r13
0x100410cfc  pop     r12
0x100410cfe  pop     rdi
0x100410cff  retn
0x100410d00  mov     ecx, 80004005h; int
0x100410d05  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```

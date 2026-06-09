# CharacterSource::PullAhead(void)

- ea: `0x10040d2e0`
- end: `0x10040d411`
- name: `?PullAhead@CharacterSource@@IEAAKXZ`
- size: `305`
- prototype: `unsigned int __fastcall(CharacterSource *__hidden this)`
- caller_count: `28`
- callee_count: `5`
- tags: ``

## callers

- `0x1004189f0`
- `0x100418c80`
- `0x100418ce0`
- `0x100418e00`
- `0x100418f00`
- `0x1004191c0`
- `0x1004192a0`
- `0x100419320`
- `0x100419460`
- `0x1004195a0`
- `0x1004196b0`
- `0x1004197b0`
- `0x100419830`
- `0x100419970`
- `0x100419ac0`
- `0x100419c10`
- `0x100419ca0`
- `0x100419d40`
- `0x100419df0`
- `0x100419e70`
- `0x100419fb0`
- `0x10041a0d0`
- `0x10041a230`
- `0x10041a310`
- `0x10041a380`
- `0x10041a4c0`
- `0x10041a600`
- `0x10041b030`

## callees

- `0x100401780`
- `0x10040d2e0`
- `0x10040d420`
- `0x100425d50`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall CharacterSource::PullAhead(CharacterSource *this)
{
  int v2; // ecx
  unsigned int v3; // edx
  int v4; // eax
  const void *v5; // rdi
  __int64 v6; // rsi
  void *v7; // rax
  unsigned __int64 v8; // rcx
  int v9; // eax
  void *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  __int64 result; // rax
  unsigned int v16; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 16);
  v3 = *((_DWORD *)this + 8);
  if ( v2 - *((_DWORD *)this + 14) >= v3 )
    goto LABEL_2;
  v4 = *((_DWORD *)this + 10);
  if ( *((_BYTE *)this + 25) )
  {
    if ( v2 - v4 > v3 )
LABEL_2:
      CharacterSource::Grow(this);
  }
  else
  {
    v5 = (const void *)*((_QWORD *)this + 7);
    v6 = (unsigned int)((_DWORD)v5 - v4);
    v7 = (void *)*((_QWORD *)this + 5);
    if ( v5 != v7 )
    {
      v8 = *((_QWORD *)this + 12);
      if ( v8 > (unsigned __int64)v5 )
      {
        *((_QWORD *)this + 14) -= v6;
        v10 = (void *)(v8 - v6);
      }
      else
      {
        v9 = (*(__int64 (__fastcall **)(CharacterSource *, _QWORD, const void *))(*(_QWORD *)this + 112LL))(
               this,
               *((_QWORD *)this + 12),
               v5);
        if ( *((_QWORD *)this + 12) == *((_QWORD *)this + 14) )
          v9 += *((_DWORD *)this + 30);
        *((_DWORD *)this + 30) = v9;
        v7 = (void *)*((_QWORD *)this + 5);
        *((_QWORD *)this + 14) = v7;
        v10 = v7;
      }
      v11 = *((_QWORD *)this + 8);
      *((_QWORD *)this + 12) = v10;
      memmove(v7, v5, v11 - (_QWORD)v5);
      v12 = *((_QWORD *)this + 5);
      *((_QWORD *)this + 6) -= v6;
      *((_QWORD *)this + 8) -= v6;
      *((_QWORD *)this + 9) -= v6;
      *((_QWORD *)this + 10) -= v6;
      *((_QWORD *)this + 16) += v6;
      *((_QWORD *)this + 7) = v12;
    }
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 2) + 56LL))(
          *((_QWORD *)this + 2),
          *((_QWORD *)this + 8),
          (unsigned int)(*((_DWORD *)this + 7) + *((_DWORD *)this + 10) - *((_DWORD *)this + 16)),
          &v16);
  if ( v13 < 0 )
  {
    _mm_lfence();
    MXRRaiseException(v13);
    JUMPOUT(0x10040D410LL);
  }
  v14 = *((_QWORD *)this + 8);
  result = v16;
  *((_QWORD *)this + 10) = v14;
  *((_QWORD *)this + 8) = v14 + result;
  return result;
}

```

## disassembly

```asm
0x10040d2e0  push    rbx
0x10040d2e2  sub     rsp, 30h
0x10040d2e6  mov     rbx, rcx
0x10040d2e9  mov     ecx, [rcx+40h]
0x10040d2ec  mov     eax, ecx
0x10040d2ee  sub     eax, [rbx+38h]
0x10040d2f1  mov     edx, [rbx+20h]
0x10040d2f4  cmp     eax, edx
0x10040d2f6  jb      short loc_10040D305
0x10040d2f8  mov     rcx, rbx; this
0x10040d2fb  call    ?Grow@CharacterSource@@AEAAXXZ; CharacterSource::Grow(void)
0x10040d300  jmp     loc_10040D3C2
0x10040d305  cmp     byte ptr [rbx+19h], 0
0x10040d309  mov     eax, [rbx+28h]
0x10040d30c  jz      short loc_10040D325
0x10040d30e  sub     ecx, eax
0x10040d310  cmp     ecx, edx
0x10040d312  jbe     loc_10040D3C2
0x10040d318  mov     rcx, rbx; this
0x10040d31b  call    ?Grow@CharacterSource@@AEAAXXZ; CharacterSource::Grow(void)
0x10040d320  jmp     loc_10040D3C2
0x10040d325  mov     [rsp+38h+arg_8], rsi
0x10040d32a  mov     [rsp+38h+arg_10], rdi
0x10040d32f  mov     rdi, [rbx+38h]
0x10040d333  mov     esi, edi
0x10040d335  sub     esi, eax
0x10040d337  mov     rax, [rbx+28h]
0x10040d33b  cmp     rdi, rax
0x10040d33e  jz      short loc_10040D3B8
0x10040d340  mov     rcx, [rbx+60h]
0x10040d344  cmp     rcx, rdi
0x10040d347  ja      short loc_10040D37C
0x10040d349  mov     rax, [rbx]
0x10040d34c  mov     rdx, rcx
0x10040d34f  mov     r8, rdi
0x10040d352  mov     rcx, rbx
0x10040d355  mov     rax, [rax+70h]
0x10040d359  call    cs:__guard_dispatch_icall_fptr
0x10040d35f  mov     rcx, [rbx+70h]
0x10040d363  cmp     [rbx+60h], rcx
0x10040d367  jnz     short loc_10040D36C
0x10040d369  add     eax, [rbx+78h]
0x10040d36c  mov     [rbx+78h], eax
0x10040d36f  mov     rax, [rbx+28h]
0x10040d373  mov     [rbx+70h], rax
0x10040d377  mov     rcx, rax
0x10040d37a  jmp     short loc_10040D383
0x10040d37c  sub     [rbx+70h], rsi
0x10040d380  sub     rcx, rsi
0x10040d383  mov     r8, [rbx+40h]
0x10040d387  mov     rdx, rdi; Src
0x10040d38a  mov     [rbx+60h], rcx
0x10040d38e  sub     r8, rdi; Size
0x10040d391  mov     rcx, rax; void *
0x10040d394  call    memmove
0x10040d399  mov     rax, [rbx+28h]
0x10040d39d  sub     [rbx+30h], rsi
0x10040d3a1  sub     [rbx+40h], rsi
0x10040d3a5  sub     [rbx+48h], rsi
0x10040d3a9  sub     [rbx+50h], rsi
0x10040d3ad  add     [rbx+80h], rsi
0x10040d3b4  mov     [rbx+38h], rax
0x10040d3b8  mov     rsi, [rsp+38h+arg_8]
0x10040d3bd  mov     rdi, [rsp+38h+arg_10]
0x10040d3c2  mov     rcx, [rbx+10h]
0x10040d3c6  lea     r9, [rsp+38h+arg_0]
0x10040d3cb  mov     r8d, [rbx+28h]
0x10040d3cf  add     r8d, [rbx+1Ch]
0x10040d3d3  sub     r8d, [rbx+40h]
0x10040d3d7  mov     rax, [rcx]
0x10040d3da  mov     rdx, [rbx+40h]
0x10040d3de  mov     rax, [rax+38h]
0x10040d3e2  call    cs:__guard_dispatch_icall_fptr
0x10040d3e8  test    eax, eax
0x10040d3ea  js      short loc_10040D406
0x10040d3ec  mov     rdx, [rbx+40h]
0x10040d3f0  mov     eax, [rsp+38h+arg_0]
0x10040d3f4  mov     [rbx+50h], rdx
0x10040d3f8  lea     rcx, [rdx+rax]
0x10040d3fc  mov     [rbx+40h], rcx
0x10040d400  add     rsp, 30h
0x10040d404  pop     rbx
0x10040d405  retn
0x10040d406  lfence
0x10040d409  mov     ecx, eax; int
0x10040d40b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```

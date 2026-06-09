# NCoreLibrary::TString::Update(ushort const *)

- ea: `0x1800157d4`
- end: `0x180015874`
- name: `?Update@TString@NCoreLibrary@@QEAAJPEBG@Z`
- size: `160`
- prototype: `int(NCoreLibrary::TString *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180015424`
- `0x1800158e4`
- `0x180015970`

## callees

- `0x18000522c`
- `0x18000b710`
- `0x180013acc`
- `0x1800157d4`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TString::Update(void **this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int16 *v6; // rax
  NCoreLibrary::TString *v7; // rcx
  unsigned __int16 *v8; // rsi
  int v9; // ebx

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = v4 + 1;
    v6 = (unsigned __int16 *)operator new(saturated_mul(v4 + 1, 2u));
    v8 = v6;
    if ( v6 )
    {
      v9 = StringCchCopyW(v6, v5, a2);
      if ( v9 >= 0 )
      {
        NCoreLibrary::TString::vFree(v7, *this);
        *this = v8;
        v8 = 0;
      }
    }
    else
    {
      v9 = -2147024882;
    }
    NCoreLibrary::TString::vFree(v7, v8);
  }
  else
  {
    v9 = 0;
    NCoreLibrary::TString::vFree((NCoreLibrary::TString *)this, *this);
    *this = &NCoreLibrary::TString::gszNullState;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800157d4  push    rbx
0x1800157d6  push    rbp
0x1800157d7  push    rsi
0x1800157d8  push    rdi
0x1800157d9  push    r14
0x1800157db  sub     rsp, 20h
0x1800157df  xor     r14d, r14d
0x1800157e2  mov     rbx, rdx
0x1800157e5  mov     rdi, rcx
0x1800157e8  test    rdx, rdx
0x1800157eb  jz      short loc_180015851
0x1800157ed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800157f1  mov     rax, rcx
0x1800157f4  inc     rax
0x1800157f7  cmp     [rdx+rax*2], r14w
0x1800157fc  jnz     short loc_1800157F4
0x1800157fe  lea     rbp, [rax+1]
0x180015802  mov     eax, 2
0x180015807  mul     rbp
0x18001580a  cmovb   rax, rcx
0x18001580e  mov     rcx, rax; Size
0x180015811  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015816  mov     rsi, rax
0x180015819  test    rax, rax
0x18001581c  jnz     short loc_180015825
0x18001581e  mov     ebx, 8007000Eh
0x180015823  jmp     short loc_180015847
0x180015825  mov     r8, rbx; unsigned __int16 *
0x180015828  mov     rdx, rbp; unsigned __int64
0x18001582b  mov     rcx, rsi; unsigned __int16 *
0x18001582e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015833  mov     ebx, eax
0x180015835  test    eax, eax
0x180015837  js      short loc_180015847
0x180015839  mov     rdx, [rdi]; void *
0x18001583c  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180015841  mov     [rdi], rsi
0x180015844  mov     rsi, r14
0x180015847  mov     rdx, rsi; void *
0x18001584a  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x18001584f  jmp     short loc_180015866
0x180015851  mov     rdx, [rcx]; void *
0x180015854  mov     ebx, r14d
0x180015857  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x18001585c  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180015863  mov     [rdi], rax
0x180015866  mov     eax, ebx
0x180015868  add     rsp, 20h
0x18001586c  pop     r14
0x18001586e  pop     rdi
0x18001586f  pop     rsi
0x180015870  pop     rbp
0x180015871  pop     rbx
0x180015872  retn
```

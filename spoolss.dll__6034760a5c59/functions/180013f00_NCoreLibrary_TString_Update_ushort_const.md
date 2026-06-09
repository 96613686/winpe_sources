# NCoreLibrary::TString::Update(ushort const *)

- ea: `0x180013f00`
- end: `0x180013f9f`
- name: `?Update@TString@NCoreLibrary@@QEAAJPEBG@Z`
- size: `159`
- prototype: `int(NCoreLibrary::TString *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180013720`
- `0x180014008`
- `0x180014080`

## callees

- `0x180004ecc`
- `0x18000ae10`
- `0x180012344`
- `0x180013f00`

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
0x180013f00  push    rbx
0x180013f02  push    rbp
0x180013f03  push    rsi
0x180013f04  push    rdi
0x180013f05  push    r14
0x180013f07  sub     rsp, 20h
0x180013f0b  xor     r14d, r14d
0x180013f0e  mov     rbx, rdx
0x180013f11  mov     rdi, rcx
0x180013f14  test    rdx, rdx
0x180013f17  jz      short loc_180013F7D
0x180013f19  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013f1d  mov     rax, rcx
0x180013f20  inc     rax
0x180013f23  cmp     [rdx+rax*2], r14w
0x180013f28  jnz     short loc_180013F20
0x180013f2a  lea     rbp, [rax+1]
0x180013f2e  mov     eax, 2
0x180013f33  mul     rbp
0x180013f36  cmovb   rax, rcx
0x180013f3a  mov     rcx, rax; Size
0x180013f3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013f42  mov     rsi, rax
0x180013f45  test    rax, rax
0x180013f48  jnz     short loc_180013F51
0x180013f4a  mov     ebx, 8007000Eh
0x180013f4f  jmp     short loc_180013F73
0x180013f51  mov     r8, rbx; unsigned __int16 *
0x180013f54  mov     rdx, rbp; unsigned __int64
0x180013f57  mov     rcx, rsi; unsigned __int16 *
0x180013f5a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013f5f  mov     ebx, eax
0x180013f61  test    eax, eax
0x180013f63  js      short loc_180013F73
0x180013f65  mov     rdx, [rdi]; void *
0x180013f68  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180013f6d  mov     [rdi], rsi
0x180013f70  mov     rsi, r14
0x180013f73  mov     rdx, rsi; void *
0x180013f76  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180013f7b  jmp     short loc_180013F92
0x180013f7d  mov     rdx, [rcx]; void *
0x180013f80  mov     ebx, r14d
0x180013f83  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180013f88  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180013f8f  mov     [rdi], rax
0x180013f92  mov     eax, ebx
0x180013f94  add     rsp, 20h
0x180013f98  pop     r14
0x180013f9a  pop     rdi
0x180013f9b  pop     rsi
0x180013f9c  pop     rbp
0x180013f9d  pop     rbx
0x180013f9e  retn
```

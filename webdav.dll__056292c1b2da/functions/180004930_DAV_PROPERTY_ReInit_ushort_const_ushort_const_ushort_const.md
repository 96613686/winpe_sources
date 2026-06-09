# DAV_PROPERTY::ReInit(ushort const *,ushort const *,ushort const *)

- ea: `0x180004930`
- end: `0x1800049fb`
- name: `?ReInit@DAV_PROPERTY@@UEAAJPEBG00@Z`
- size: `203`
- prototype: `__int64 __fastcall(DAV_PROPERTY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180004930`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004992`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800049b4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800049d6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004992`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800049b4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800049d6`

## pseudocode

```c
__int64 __fastcall DAV_PROPERTY::ReInit(
        DAV_PROPERTY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  STRU *v4; // rbp
  STRU *v5; // r14
  int v7; // r11d
  _WORD *v10; // r10
  _WORD *v11; // rcx

  v4 = (DAV_PROPERTY *)((char *)this + 144);
  v5 = (DAV_PROPERTY *)((char *)this + 200);
  v7 = 0;
  **((_WORD **)this + 15) = 0;
  v10 = (_WORD *)*((_QWORD *)this + 22);
  *((_DWORD *)this + 34) = 0;
  *v10 = 0;
  v11 = (_WORD *)*((_QWORD *)this + 29);
  *((_DWORD *)v4 + 12) = 0;
  *v11 = 0;
  *((_DWORD *)v5 + 12) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  if ( a2 )
  {
    v7 = STRU::Copy((DAV_PROPERTY *)((char *)this + 88), a2);
    if ( v7 < 0 )
      return (unsigned int)v7;
    *((_DWORD *)this + 64) = 1;
  }
  if ( a3 )
  {
    v7 = STRU::Copy(v4, a3);
    if ( v7 < 0 )
      return (unsigned int)v7;
    *((_DWORD *)this + 65) = 1;
  }
  if ( a4 )
  {
    v7 = STRU::Copy(v5, a4);
    if ( v7 >= 0 )
      *((_DWORD *)this + 66) = 1;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004930  push    rbx
0x180004932  push    rbp
0x180004933  push    rsi
0x180004934  push    rdi
0x180004935  push    r14
0x180004937  sub     rsp, 20h
0x18000493b  mov     r10, [rcx+78h]
0x18000493f  lea     rbp, [rcx+90h]
0x180004946  xor     eax, eax
0x180004948  lea     r14, [rcx+0C8h]
0x18000494f  mov     rbx, rcx
0x180004952  xor     r11d, r11d
0x180004955  mov     rdi, r9
0x180004958  mov     rsi, r8
0x18000495b  mov     [r10], ax
0x18000495f  mov     r10, [rbp+20h]
0x180004963  mov     [rcx+88h], eax
0x180004969  mov     [r10], ax
0x18000496d  mov     rcx, [r14+20h]
0x180004971  mov     [rbp+30h], eax
0x180004974  mov     [rcx], ax
0x180004977  mov     [r14+30h], eax
0x18000497b  mov     [rbx+100h], rax
0x180004982  mov     [rbx+108h], rax
0x180004989  test    rdx, rdx
0x18000498c  jz      short loc_1800049A9
0x18000498e  lea     rcx, [rbx+58h]
0x180004992  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004998  mov     r11d, eax
0x18000499b  test    eax, eax
0x18000499d  js      short loc_1800049ED
0x18000499f  mov     dword ptr [rbx+100h], 1
0x1800049a9  test    rsi, rsi
0x1800049ac  jz      short loc_1800049CB
0x1800049ae  mov     rdx, rsi
0x1800049b1  mov     rcx, rbp
0x1800049b4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800049ba  mov     r11d, eax
0x1800049bd  test    eax, eax
0x1800049bf  js      short loc_1800049ED
0x1800049c1  mov     dword ptr [rbx+104h], 1
0x1800049cb  test    rdi, rdi
0x1800049ce  jz      short loc_1800049ED
0x1800049d0  mov     rdx, rdi
0x1800049d3  mov     rcx, r14
0x1800049d6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800049dc  mov     r11d, eax
0x1800049df  test    eax, eax
0x1800049e1  js      short loc_1800049ED
0x1800049e3  mov     dword ptr [rbx+108h], 1
0x1800049ed  mov     eax, r11d
0x1800049f0  add     rsp, 20h
0x1800049f4  pop     r14
0x1800049f6  pop     rdi
0x1800049f7  pop     rsi
0x1800049f8  pop     rbp
0x1800049f9  pop     rbx
0x1800049fa  retn
```

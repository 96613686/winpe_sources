# DIRECT_ACCESS_QUERY::IsUseProxy(ushort * *,int *)

- ea: `0x1800087b4`
- end: `0x180008850`
- name: `?IsUseProxy@DIRECT_ACCESS_QUERY@@QEAAKPEAPEAGPEAH@Z`
- size: `156`
- prototype: `unsigned int __fastcall(DIRECT_ACCESS_QUERY *__hidden this, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a22c`
- `0x18000dfe8`

## callees

- `0x1800087b4`
- `0x18000c998`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1800087f5`
- `KERNEL32!GlobalAlloc` at `0x1800087f5`
- `KERNEL32!GlobalFree` at `0x18000882f`
- `KERNEL32!GlobalFree` at `0x18000882f`

## pseudocode

```c
__int64 __fastcall DIRECT_ACCESS_QUERY::IsUseProxy(DIRECT_ACCESS_QUERY *this, unsigned __int16 **a2, int *a3)
{
  bool v4; // zf
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // r15d
  unsigned __int16 *v11; // rax
  void *v12; // r11

  v4 = *((_DWORD *)this + 1) == 2;
  *a2 = 0;
  v7 = 0;
  *a3 = 0;
  if ( v4 )
  {
    v8 = *((_QWORD *)this + 1);
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v8 + 2 * v9) );
    v10 = v9 + 1;
    v11 = (unsigned __int16 *)GlobalAlloc(0, (unsigned int)(2 * (v9 + 1)));
    if ( v11 )
    {
      if ( (int)StringCchCopyW(v11, v10, *((unsigned __int16 **)this + 1)) < 0 )
      {
        GlobalFree(v12);
        return 1359;
      }
      else
      {
        *a2 = (unsigned __int16 *)v12;
        *a3 = 1;
      }
    }
    else
    {
      return 8;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800087b4  push    rbx
0x1800087b6  push    rbp
0x1800087b7  push    rsi
0x1800087b8  push    rdi
0x1800087b9  push    r14
0x1800087bb  push    r15
0x1800087bd  sub     rsp, 28h
0x1800087c1  xor     ebp, ebp
0x1800087c3  mov     rsi, r8
0x1800087c6  cmp     dword ptr [rcx+4], 2
0x1800087ca  mov     r14, rdx
0x1800087cd  mov     rdi, rcx
0x1800087d0  mov     [rdx], rbp
0x1800087d3  mov     ebx, ebp
0x1800087d5  mov     [r8], ebp
0x1800087d8  jnz     short loc_180008840
0x1800087da  mov     rcx, [rcx+8]
0x1800087de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800087e2  inc     rax
0x1800087e5  cmp     [rcx+rax*2], bp
0x1800087e9  jnz     short loc_1800087E2
0x1800087eb  lea     r15d, [rax+1]
0x1800087ef  xor     ecx, ecx; uFlags
0x1800087f1  lea     edx, [r15+r15]; dwBytes
0x1800087f5  call    cs:__imp_GlobalAlloc
0x1800087fc  nop     dword ptr [rax+rax+00h]
0x180008801  mov     r11, rax
0x180008804  test    rax, rax
0x180008807  jnz     short loc_18000880E
0x180008809  lea     ebx, [rax+8]
0x18000880c  jmp     short loc_180008840
0x18000880e  mov     r8, [rdi+8]; unsigned __int16 *
0x180008812  mov     rcx, r11; unsigned __int16 *
0x180008815  mov     edx, r15d; unsigned __int64
0x180008818  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000881d  test    eax, eax
0x18000881f  js      short loc_18000882C
0x180008821  mov     [r14], r11
0x180008824  mov     dword ptr [rsi], 1
0x18000882a  jmp     short loc_180008840
0x18000882c  mov     rcx, r11; hMem
0x18000882f  call    cs:__imp_GlobalFree
0x180008836  nop     dword ptr [rax+rax+00h]
0x18000883b  mov     ebx, 54Fh
0x180008840  mov     eax, ebx
0x180008842  add     rsp, 28h
0x180008846  pop     r15
0x180008848  pop     r14
0x18000884a  pop     rdi
0x18000884b  pop     rsi
0x18000884c  pop     rbp
0x18000884d  pop     rbx
0x18000884e  retn
```

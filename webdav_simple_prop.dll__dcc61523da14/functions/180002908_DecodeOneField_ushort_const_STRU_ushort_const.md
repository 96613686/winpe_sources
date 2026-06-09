# DecodeOneField(ushort const *,STRU *,ushort const * *)

- ea: `0x180002908`
- end: `0x18000296c`
- name: `?DecodeOneField@@YAJPEBGPEAVSTRU@@PEAPEBG@Z`
- size: `100`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct STRU *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000283c`

## callees

- `0x180002908`

## import_xrefs

- `iisutil!?Unescape@STRU@@QEAAJXZ` at `0x18000294c`
- `iisutil!?Unescape@STRU@@QEAAJXZ` at `0x18000294c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000293d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000293d`

## pseudocode

```c
__int64 __fastcall DecodeOneField(const unsigned __int16 *a1, struct STRU *a2, const unsigned __int16 **a3)
{
  int v6; // ecx

  if ( *a1 == 48 )
  {
    *a3 = 0;
    return 0;
  }
  else if ( *a1 == 49 )
  {
    v6 = STRU::Copy(a2, a1 + 1);
    if ( v6 >= 0 )
    {
      v6 = STRU::Unescape(a2);
      if ( v6 >= 0 )
        *a3 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
    }
    return (unsigned int)v6;
  }
  else
  {
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180002908  mov     [rsp+arg_0], rbx
0x18000290d  push    rdi
0x18000290e  sub     rsp, 20h
0x180002912  cmp     word ptr [rcx], 30h ; '0'
0x180002916  mov     rdi, r8
0x180002919  mov     rbx, rdx
0x18000291c  jnz     short loc_180002929
0x18000291e  mov     qword ptr [r8], 0
0x180002925  xor     eax, eax
0x180002927  jmp     short loc_180002961
0x180002929  cmp     word ptr [rcx], 31h ; '1'
0x18000292d  jz      short loc_180002936
0x18000292f  mov     eax, 80070057h
0x180002934  jmp     short loc_180002961
0x180002936  lea     rdx, [rcx+2]
0x18000293a  mov     rcx, rbx
0x18000293d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002943  mov     ecx, eax
0x180002945  test    eax, eax
0x180002947  js      short loc_18000295F
0x180002949  mov     rcx, rbx
0x18000294c  call    cs:__imp_?Unescape@STRU@@QEAAJXZ; STRU::Unescape(void)
0x180002952  mov     ecx, eax
0x180002954  test    eax, eax
0x180002956  js      short loc_18000295F
0x180002958  mov     rax, [rbx+20h]
0x18000295c  mov     [rdi], rax
0x18000295f  mov     eax, ecx
0x180002961  mov     rbx, [rsp+28h+arg_0]
0x180002966  add     rsp, 20h
0x18000296a  pop     rdi
0x18000296b  retn
```

# CClientUtils::MakeSubKey(ushort *,uint,ushort const *)

- ea: `0x180007f84`
- end: `0x180007fc8`
- name: `?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z`
- size: `68`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007180`
- `0x180007430`
- `0x180007820`
- `0x180008bc0`
- `0x1800095c8`
- `0x180009d6c`

## callees

- `0x180005dac`
- `0x180007f84`

## pseudocode

```c
void __fastcall CClientUtils::MakeSubKey(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // rdx

  StringCchPrintfW(a1, 0x109u, L"SOFTWARE\\Microsoft\\Terminal Server Client\\%s", a3);
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( v4 )
  {
    if ( a1[v4 - 1] == 92 )
      a1[v4 - 1] = 0;
  }
}

```

## disassembly

```asm
0x180007f84  push    rbx
0x180007f86  sub     rsp, 20h
0x180007f8a  mov     r9, r8
0x180007f8d  mov     edx, 109h; unsigned __int64
0x180007f92  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Terminal Server Cl"...
0x180007f99  mov     rbx, rcx
0x180007f9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007fa1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007fa5  xor     eax, eax
0x180007fa7  inc     rdx
0x180007faa  cmp     [rbx+rdx*2], ax
0x180007fae  jnz     short loc_180007FA7
0x180007fb0  test    rdx, rdx
0x180007fb3  jz      short loc_180007FC2
0x180007fb5  cmp     word ptr [rbx+rdx*2-2], 5Ch ; '\'
0x180007fbb  jnz     short loc_180007FC2
0x180007fbd  mov     [rbx+rdx*2-2], ax
0x180007fc2  add     rsp, 20h
0x180007fc6  pop     rbx
0x180007fc7  retn
```

# ATL::CSid::Sid(void)

- ea: `0x1400073b4`
- end: `0x140007427`
- name: `?Sid@CSid@ATL@@QEBAPEBGXZ`
- size: `115`
- prototype: `const unsigned __int16 *__fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140006d7c`

## callees

- `0x14000491c`
- `0x1400073b4`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x1400073de`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1400073de`
- `KERNEL32!LocalFree` at `0x140007412`
- `KERNEL32!LocalFree` at `0x140007412`

## pseudocode

```c
const unsigned __int16 *__fastcall ATL::CSid::Sid(ATL::CSid *this)
{
  char *v1; // rbx
  __int64 v2; // r8
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  v1 = (char *)this + 104;
  if ( !*(_DWORD *)(*((_QWORD *)this + 13) - 16LL) )
  {
    hMem = 0;
    if ( ConvertSidToStringSidW((char *)this + 8, (LPWSTR *)&hMem) )
    {
      if ( hMem )
      {
        v2 = -1;
        do
          ++v2;
        while ( *((_WORD *)hMem + v2) );
      }
      else
      {
        v2 = 0;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(v1, hMem, v2);
      LocalFree(hMem);
    }
  }
  return *(const unsigned __int16 **)v1;
}

```

## disassembly

```asm
0x1400073b4  mov     r11, rsp
0x1400073b7  mov     [r11+18h], rbx
0x1400073bb  mov     [r11+8], rcx
0x1400073bf  push    rdi
0x1400073c0  sub     rsp, 20h
0x1400073c4  lea     rbx, [rcx+68h]
0x1400073c8  mov     rax, [rbx]
0x1400073cb  xor     edi, edi
0x1400073cd  cmp     [rax-10h], edi
0x1400073d0  jnz     short loc_140007418
0x1400073d2  mov     [r11+10h], rdi
0x1400073d6  add     rcx, 8; Sid
0x1400073da  lea     rdx, [r11+10h]; StringSid
0x1400073de  call    cs:__imp_ConvertSidToStringSidW
0x1400073e4  test    eax, eax
0x1400073e6  jz      short loc_140007418
0x1400073e8  mov     rdx, [rsp+28h+hMem]
0x1400073ed  test    rdx, rdx
0x1400073f0  jnz     short loc_1400073F7
0x1400073f2  mov     r8d, edi
0x1400073f5  jmp     short loc_140007405
0x1400073f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400073fb  inc     r8
0x1400073fe  cmp     [rdx+r8*2], di
0x140007403  jnz     short loc_1400073FB
0x140007405  mov     rcx, rbx
0x140007408  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000740d  mov     rcx, [rsp+28h+hMem]; hMem
0x140007412  call    cs:__imp_LocalFree
0x140007418  mov     rax, [rbx]
0x14000741b  mov     rbx, [rsp+28h+arg_10]
0x140007420  add     rsp, 20h
0x140007424  pop     rdi
0x140007425  retn
```

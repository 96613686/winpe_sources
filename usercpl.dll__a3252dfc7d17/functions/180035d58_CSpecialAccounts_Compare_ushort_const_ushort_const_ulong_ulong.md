# CSpecialAccounts::_Compare(ushort const *,ushort const *,ulong,ulong)

- ea: `0x180035d58`
- end: `0x180035df3`
- name: `?_Compare@CSpecialAccounts@@CA_NPEBG0KK@Z`
- size: `155`
- prototype: `char __fastcall(LPCWCH lpString1, LPCWCH lpString2, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180035eec`

## callees

- `0x180035d58`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035dad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035de3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035dad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035de3`
- `KERNEL32!lstrlenW` at `0x180035d85`
- `KERNEL32!lstrlenW` at `0x180035d90`
- `KERNEL32!lstrlenW` at `0x180035d85`
- `KERNEL32!lstrlenW` at `0x180035d90`

## pseudocode

```c
char __fastcall CSpecialAccounts::_Compare(LPCWCH lpString1, LPCWCH lpString2, int a3, int a4)
{
  unsigned __int16 v5; // si
  char v8; // di
  int v9; // ebx
  int v10; // eax

  v5 = a3;
  if ( (a3 & 0xFFFF0000) == 0 )
  {
    if ( CompareStringOrdinal(lpString1, -1, lpString2, -1, 1) != 2 )
      return 0;
    return v5 == a4;
  }
  v8 = 0;
  if ( (a3 & 0xFFFF0000) == 0x10000 )
  {
    v9 = lstrlenW(lpString1);
    v10 = lstrlenW(lpString2);
    if ( v9 >= v10 && CompareStringOrdinal(lpString1, v10, lpString2, v10, 1) == 2 )
      return v5 == a4;
  }
  return v8;
}

```

## disassembly

```asm
0x180035d58  push    rbx
0x180035d5a  push    rbp
0x180035d5b  push    rsi
0x180035d5c  push    rdi
0x180035d5d  push    r14
0x180035d5f  push    r15
0x180035d61  sub     rsp, 38h
0x180035d65  mov     eax, r8d
0x180035d68  mov     r15d, r9d
0x180035d6b  mov     esi, r8d
0x180035d6e  mov     rbp, rdx
0x180035d71  mov     r14, rcx
0x180035d74  and     eax, 0FFFF0000h
0x180035d79  jz      short loc_180035DD2
0x180035d7b  xor     dil, dil
0x180035d7e  cmp     eax, 10000h
0x180035d83  jnz     short loc_180035DC2
0x180035d85  call    cs:__imp_lstrlenW
0x180035d8b  mov     rcx, rbp; lpString
0x180035d8e  mov     ebx, eax
0x180035d90  call    cs:__imp_lstrlenW
0x180035d96  cmp     ebx, eax
0x180035d98  jl      short loc_180035DC2
0x180035d9a  mov     r9d, eax; cchCount2
0x180035d9d  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180035da5  mov     r8, rbp; lpString2
0x180035da8  mov     edx, eax; cchCount1
0x180035daa  mov     rcx, r14; lpString1
0x180035dad  call    cs:__imp_CompareStringOrdinal
0x180035db3  cmp     eax, 2
0x180035db6  jnz     short loc_180035DC2
0x180035db8  movzx   eax, si
0x180035dbb  cmp     eax, r15d
0x180035dbe  setz    dil
0x180035dc2  mov     al, dil
0x180035dc5  add     rsp, 38h
0x180035dc9  pop     r15
0x180035dcb  pop     r14
0x180035dcd  pop     rdi
0x180035dce  pop     rsi
0x180035dcf  pop     rbp
0x180035dd0  pop     rbx
0x180035dd1  retn
0x180035dd2  or      edx, 0FFFFFFFFh; cchCount1
0x180035dd5  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180035ddd  mov     r9d, edx; cchCount2
0x180035de0  mov     r8, rbp; lpString2
0x180035de3  call    cs:__imp_CompareStringOrdinal
0x180035de9  cmp     eax, 2
0x180035dec  jz      short loc_180035DB8
0x180035dee  xor     dil, dil
0x180035df1  jmp     short loc_180035DC2
```

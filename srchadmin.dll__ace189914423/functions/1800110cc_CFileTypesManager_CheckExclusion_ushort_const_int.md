# CFileTypesManager::_CheckExclusion(ushort const *,int *)

- ea: `0x1800110cc`
- end: `0x18001113e`
- name: `?_CheckExclusion@CFileTypesManager@@AEAAJPEBGPEAH@Z`
- size: `114`
- prototype: `int(CFileTypesManager *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fe10`
- `0x1800102e0`

## callees

- `0x1800110cc`
- `0x18002fdf0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001111b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001111b`

## pseudocode

```c
__int64 __fastcall CFileTypesManager::_CheckExclusion(CFileTypesManager *this, const unsigned __int16 *a2, int *a3)
{
  _DWORD *v3; // rbx
  const WCHAR *lpString2; // rax

  v3 = (_DWORD *)*((_QWORD *)this + 3);
  *a3 = 0;
  if ( v3 )
    LODWORD(v3) = *v3;
  do
  {
    if ( (int)v3 < 0 )
      break;
    lpString2 = (const WCHAR *)DPA_GetPtr(*((HDPA *)this + 3), (int)v3);
    if ( CompareStringW(0x7Fu, 1u, a2, -1, lpString2, -1) == 2 )
      *a3 = 1;
    LODWORD(v3) = (_DWORD)v3 - 1;
  }
  while ( !*a3 );
  return 0;
}

```

## disassembly

```asm
0x1800110cc  push    rbx
0x1800110ce  push    rbp
0x1800110cf  push    rsi
0x1800110d0  push    rdi
0x1800110d1  sub     rsp, 38h
0x1800110d5  mov     rbx, [rcx+18h]
0x1800110d9  mov     rdi, r8
0x1800110dc  mov     dword ptr [r8], 0
0x1800110e3  mov     rbp, rdx
0x1800110e6  mov     rsi, rcx
0x1800110e9  test    rbx, rbx
0x1800110ec  jz      short loc_1800110F0
0x1800110ee  mov     ebx, [rbx]
0x1800110f0  test    ebx, ebx
0x1800110f2  js      short loc_180011133
0x1800110f4  mov     rcx, [rsi+18h]; hdpa
0x1800110f8  movsxd  rdx, ebx; i
0x1800110fb  call    DPA_GetPtr
0x180011100  or      r9d, 0FFFFFFFFh; cchCount1
0x180011104  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001110c  mov     r8, rbp; lpString1
0x18001110f  mov     [rsp+58h+lpString2], rax; lpString2
0x180011114  lea     edx, [r9+2]; dwCmpFlags
0x180011118  lea     ecx, [rdx+7Eh]; Locale
0x18001111b  call    cs:__imp_CompareStringW
0x180011121  cmp     eax, 2
0x180011124  jnz     short loc_18001112C
0x180011126  mov     dword ptr [rdi], 1
0x18001112c  dec     ebx
0x18001112e  cmp     dword ptr [rdi], 0
0x180011131  jz      short loc_1800110F0
0x180011133  xor     eax, eax
0x180011135  add     rsp, 38h
0x180011139  pop     rdi
0x18001113a  pop     rsi
0x18001113b  pop     rbp
0x18001113c  pop     rbx
0x18001113d  retn
```

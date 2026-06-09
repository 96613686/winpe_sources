# T2OSSvcInstallFont

- ea: `0x18001cd6c`
- end: `0x18001ce24`
- name: `T2OSSvcInstallFont`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800190a4`

## callees

- `0x18001cd6c`
- `0x18002b010`

## import_xrefs

- `GDI32!AddFontResourceA` at `0x18001cddc`
- `GDI32!AddFontResourceA` at `0x18001cddc`
- `GDI32!CreateScalableFontResourceA` at `0x18001cdfc`
- `GDI32!CreateScalableFontResourceA` at `0x18001cdfc`

## pseudocode

```c
__int64 __fastcall T2OSSvcInstallFont(__int64 a1, int a2, int a3, __int64 a4)
{
  __int64 v5; // rax
  bool v6; // zf
  int v7; // eax
  const CHAR *v8; // rcx
  int v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  if ( fnAddFontMemResourceEx )
  {
    if ( a3 || !a2 )
    {
      v5 = fnAddFontMemResourceEx(*(_QWORD *)(a1 + 200), *(unsigned int *)(a1 + 4), 0, &v10);
      *(_QWORD *)(a4 + 920) = v5;
      v6 = v5 == 0;
      goto LABEL_12;
    }
  }
  else if ( !a2 || a3 )
  {
    v7 = 1;
    goto LABEL_9;
  }
  v7 = 0;
LABEL_9:
  *(_DWORD *)(a4 + 908) = v7;
  if ( v7 )
  {
    if ( !CreateScalableFontResourceA(1u, (LPCSTR)a4, (LPCSTR)(a4 + 260), 0) )
    {
      *(_DWORD *)(a4 + 944) = 518;
      return 0;
    }
    v8 = (const CHAR *)a4;
  }
  else
  {
    v8 = (const CHAR *)(a4 + 260);
  }
  v6 = AddFontResourceA(v8) == 0;
LABEL_12:
  if ( v6 )
  {
    *(_DWORD *)(a4 + 944) = 512;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001cd6c  push    rbx
0x18001cd6e  sub     rsp, 30h
0x18001cd72  mov     rax, cs:fnAddFontMemResourceEx
0x18001cd79  mov     rbx, r9
0x18001cd7c  mov     [rsp+38h+arg_18], 0
0x18001cd84  test    rax, rax
0x18001cd87  jz      short loc_18001CDB5
0x18001cd89  test    r8d, r8d
0x18001cd8c  jnz     short loc_18001CD92
0x18001cd8e  test    edx, edx
0x18001cd90  jnz     short loc_18001CDBE
0x18001cd92  mov     edx, [rcx+4]
0x18001cd95  lea     r9, [rsp+38h+arg_18]
0x18001cd9a  mov     rcx, [rcx+0C8h]
0x18001cda1  xor     r8d, r8d
0x18001cda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cda9  mov     [rbx+398h], rax
0x18001cdb0  test    rax, rax
0x18001cdb3  jmp     short loc_18001CDE4
0x18001cdb5  test    edx, edx
0x18001cdb7  jz      short loc_18001CDC2
0x18001cdb9  test    r8d, r8d
0x18001cdbc  jnz     short loc_18001CDC2
0x18001cdbe  xor     eax, eax
0x18001cdc0  jmp     short loc_18001CDC7
0x18001cdc2  mov     eax, 1
0x18001cdc7  mov     [r9+38Ch], eax
0x18001cdce  lea     r8, [r9+104h]; lpszFile
0x18001cdd5  test    eax, eax
0x18001cdd7  jnz     short loc_18001CDF2
0x18001cdd9  mov     rcx, r8; LPCSTR
0x18001cddc  call    cs:__imp_AddFontResourceA
0x18001cde2  test    eax, eax
0x18001cde4  jnz     short loc_18001CE19
0x18001cde6  mov     dword ptr [rbx+3B0h], 200h
0x18001cdf0  jmp     short loc_18001CE10
0x18001cdf2  xor     r9d, r9d; lpszPath
0x18001cdf5  mov     rdx, rbx; lpszFont
0x18001cdf8  lea     ecx, [r9+1]; fdwHidden
0x18001cdfc  call    cs:__imp_CreateScalableFontResourceA
0x18001ce02  test    eax, eax
0x18001ce04  jnz     short loc_18001CE14
0x18001ce06  mov     dword ptr [rbx+3B0h], 206h
0x18001ce10  xor     eax, eax
0x18001ce12  jmp     short loc_18001CE1E
0x18001ce14  mov     rcx, rbx
0x18001ce17  jmp     short loc_18001CDDC
0x18001ce19  mov     eax, 1
0x18001ce1e  add     rsp, 30h
0x18001ce22  pop     rbx
0x18001ce23  retn
```

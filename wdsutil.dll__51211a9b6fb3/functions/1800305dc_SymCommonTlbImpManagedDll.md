# SymCommonTlbImpManagedDll

- ea: `0x1800305dc`
- end: `0x1800307e7`
- name: `SymCommonTlbImpManagedDll`
- size: `523`
- prototype: `__int64 __fastcall(PVOID BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002fae4`

## callees

- `0x1800305dc`

## import_xrefs

- `msvcrt!_memicmp` at `0x1800306bd`
- `msvcrt!_memicmp` at `0x1800306bd`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180030610`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180030643`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180030610`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180030643`
- `ntdll!RtlImageRvaToVa` at `0x1800306a1`
- `ntdll!RtlImageRvaToVa` at `0x180030701`
- `ntdll!RtlImageRvaToVa` at `0x180030754`
- `ntdll!RtlImageRvaToVa` at `0x18003078e`
- `ntdll!RtlImageRvaToVa` at `0x1800306a1`
- `ntdll!RtlImageRvaToVa` at `0x180030701`
- `ntdll!RtlImageRvaToVa` at `0x180030754`
- `ntdll!RtlImageRvaToVa` at `0x18003078e`

## string_xrefs

- `0x1800306b3`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall SymCommonTlbImpManagedDll(char *BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)
{
  unsigned int v6; // ebx
  ULONG *v7; // r14
  char *v8; // rsi
  __int64 v9; // r8
  char *v10; // rax
  char *v11; // rax
  __int64 v12; // r8
  __int64 *v13; // rax
  __int64 v14; // rcx
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF

  v6 = 1;
  Size = 0;
  v7 = 0;
  v8 = 0;
  if ( RtlImageDirectoryEntryToData(BaseAddress, MappedAsImage, 0, &Size) || Size )
    goto LABEL_15;
  v7 = (ULONG *)RtlImageDirectoryEntryToData(BaseAddress, MappedAsImage, 1u, &Size);
  if ( !v7 )
    return 0;
  if ( !Size )
    return 0;
  v9 = v7[3];
  if ( !(_DWORD)v9 || !*v7 || v7[2] || Size >= 0x28 && v7[8] )
    return 0;
  v10 = MappedAsImage ? &BaseAddress[v9] : (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v9, 0);
  if ( _memicmp(v10, "mscoree.dll", 0xCu) )
LABEL_15:
    v6 = 0;
  if ( !v6 )
    return v6;
  if ( NtHeader->OptionalHeader.Magic == 267 )
  {
    if ( MappedAsImage )
      v11 = &BaseAddress[*v7];
    else
      v11 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, *v7, 0);
    v12 = *(unsigned int *)v11;
    if ( (int)v12 < 0 || *((_DWORD *)v11 + 1) )
      return 0;
    if ( MappedAsImage )
    {
      v8 = &BaseAddress[v12];
      goto LABEL_36;
    }
LABEL_34:
    v8 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v12, 0);
    goto LABEL_36;
  }
  if ( NtHeader->OptionalHeader.Magic == 523 )
  {
    if ( MappedAsImage )
      v13 = (__int64 *)&BaseAddress[*v7];
    else
      v13 = (__int64 *)RtlImageRvaToVa(NtHeader, BaseAddress, *v7, 0);
    if ( *v13 < 0 || v13[1] )
      return 0;
    if ( MappedAsImage )
    {
      v8 = &BaseAddress[*v13];
      goto LABEL_36;
    }
    LODWORD(v12) = *(_DWORD *)v13;
    goto LABEL_34;
  }
  v6 = 0;
LABEL_36:
  if ( v6 )
  {
    v14 = *(_QWORD *)(v8 + 2) - 0x4D6C6C44726F435FLL;
    if ( *(_QWORD *)(v8 + 2) == 0x4D6C6C44726F435FLL )
      v14 = *(unsigned int *)(v8 + 10) - 7235937LL;
    if ( v14 )
      return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800305dc  mov     rax, rsp
0x1800305df  push    rbx
0x1800305e0  push    rsi
0x1800305e1  push    rdi
0x1800305e2  push    r12
0x1800305e4  push    r14
0x1800305e6  push    r15
0x1800305e8  sub     rsp, 38h
0x1800305ec  mov     r15b, r8b
0x1800305ef  mov     r12, rdx
0x1800305f2  mov     rdi, rcx
0x1800305f5  mov     ebx, 1
0x1800305fa  mov     dword ptr [rax+20h], 0
0x180030601  xor     r14d, r14d
0x180030604  xor     esi, esi
0x180030606  xor     r8d, r8d; Directory
0x180030609  lea     r9, [rax+20h]; Size
0x18003060d  mov     dl, r15b; MappedAsImage
0x180030610  call    cs:__imp_RtlImageDirectoryEntryToData
0x180030617  nop     dword ptr [rax+rax+00h]
0x18003061c  test    rax, rax
0x18003061f  jnz     loc_1800306CD
0x180030625  cmp     [rsp+68h+Size], eax
0x18003062c  jnz     loc_1800306CD
0x180030632  mov     r8d, ebx; Directory
0x180030635  lea     r9, [rsp+68h+Size]; Size
0x18003063d  mov     dl, r15b; MappedAsImage
0x180030640  mov     rcx, rdi; BaseAddress
0x180030643  call    cs:__imp_RtlImageDirectoryEntryToData
0x18003064a  nop     dword ptr [rax+rax+00h]
0x18003064f  mov     r14, rax
0x180030652  test    rax, rax
0x180030655  jz      short loc_180030686
0x180030657  mov     eax, [rsp+68h+Size]
0x18003065e  test    eax, eax
0x180030660  jz      short loc_180030686
0x180030662  mov     [rsp+68h+var_40], r14
0x180030667  mov     r8d, [r14+0Ch]; Rva
0x18003066b  test    r8d, r8d
0x18003066e  jz      short loc_180030686
0x180030670  cmp     [r14], esi
0x180030673  jz      short loc_180030686
0x180030675  cmp     [r14+8], esi
0x180030679  jnz     short loc_180030686
0x18003067b  cmp     eax, 28h ; '('
0x18003067e  jb      short loc_18003068D
0x180030680  cmp     [r14+20h], esi
0x180030684  jz      short loc_18003068D
0x180030686  xor     ebx, ebx
0x180030688  jmp     loc_1800307CA
0x18003068d  test    r15b, r15b
0x180030690  jz      short loc_180030698
0x180030692  lea     rax, [rdi+r8]
0x180030696  jmp     short loc_1800306AD
0x180030698  xor     r9d, r9d; SectionHeader
0x18003069b  mov     rdx, rdi; BaseAddress
0x18003069e  mov     rcx, r12; NtHeader
0x1800306a1  call    cs:__imp_RtlImageRvaToVa
0x1800306a8  nop     dword ptr [rax+rax+00h]
0x1800306ad  mov     r8d, 0Ch; Size
0x1800306b3  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x1800306ba  mov     rcx, rax; Buf1
0x1800306bd  call    cs:__imp__memicmp
0x1800306c4  nop     dword ptr [rax+rax+00h]
0x1800306c9  test    eax, eax
0x1800306cb  jz      short loc_1800306D3
0x1800306cd  xor     ebx, ebx
0x1800306cf  mov     [rsp+68h+var_48], ebx
0x1800306d3  test    ebx, ebx
0x1800306d5  jz      loc_1800307CE
0x1800306db  mov     eax, 10Bh
0x1800306e0  cmp     [r12+18h], ax
0x1800306e6  jnz     short loc_18003072E
0x1800306e8  test    r15b, r15b
0x1800306eb  jz      short loc_1800306F5
0x1800306ed  mov     eax, [r14]
0x1800306f0  add     rax, rdi
0x1800306f3  jmp     short loc_18003070D
0x1800306f5  xor     r9d, r9d; SectionHeader
0x1800306f8  mov     r8d, [r14]; Rva
0x1800306fb  mov     rdx, rdi; BaseAddress
0x1800306fe  mov     rcx, r12; NtHeader
0x180030701  call    cs:__imp_RtlImageRvaToVa
0x180030708  nop     dword ptr [rax+rax+00h]
0x18003070d  mov     r8d, [rax]
0x180030710  test    r8d, r8d
0x180030713  js      loc_180030686
0x180030719  cmp     dword ptr [rax+4], 0
0x18003071d  jnz     loc_180030686
0x180030723  test    r15b, r15b
0x180030726  jz      short loc_180030785
0x180030728  lea     rsi, [rdi+r8]
0x18003072c  jmp     short loc_1800307A5
0x18003072e  mov     eax, 20Bh
0x180030733  cmp     [r12+18h], ax
0x180030739  jnz     short loc_18003079F
0x18003073b  test    r15b, r15b
0x18003073e  jz      short loc_180030748
0x180030740  mov     eax, [r14]
0x180030743  add     rax, rdi
0x180030746  jmp     short loc_180030760
0x180030748  xor     r9d, r9d; SectionHeader
0x18003074b  mov     r8d, [r14]; Rva
0x18003074e  mov     rdx, rdi; BaseAddress
0x180030751  mov     rcx, r12; NtHeader
0x180030754  call    cs:__imp_RtlImageRvaToVa
0x18003075b  nop     dword ptr [rax+rax+00h]
0x180030760  mov     rcx, [rax]
0x180030763  test    rcx, rcx
0x180030766  js      loc_180030686
0x18003076c  cmp     qword ptr [rax+8], 0
0x180030771  jnz     loc_180030686
0x180030777  test    r15b, r15b
0x18003077a  jz      short loc_180030782
0x18003077c  lea     rsi, [rcx+rdi]
0x180030780  jmp     short loc_1800307A5
0x180030782  mov     r8d, [rax]; Rva
0x180030785  xor     r9d, r9d; SectionHeader
0x180030788  mov     rdx, rdi; BaseAddress
0x18003078b  mov     rcx, r12; NtHeader
0x18003078e  call    cs:__imp_RtlImageRvaToVa
0x180030795  nop     dword ptr [rax+rax+00h]
0x18003079a  mov     rsi, rax
0x18003079d  jmp     short loc_1800307A5
0x18003079f  xor     ebx, ebx
0x1800307a1  mov     [rsp+68h+var_48], ebx
0x1800307a5  test    ebx, ebx
0x1800307a7  jz      short loc_1800307CE
0x1800307a9  mov     rcx, [rsi+2]
0x1800307ad  sub     rcx, cs:qword_18003BE70
0x1800307b4  jnz     short loc_1800307C2
0x1800307b6  mov     ecx, [rsi+0Ah]
0x1800307b9  mov     eax, cs:dword_18003BE78
0x1800307bf  sub     rcx, rax
0x1800307c2  xor     eax, eax
0x1800307c4  test    rcx, rcx
0x1800307c7  cmovnz  ebx, eax
0x1800307ca  mov     [rsp+68h+var_48], ebx
0x1800307ce  jmp     short loc_1800307D6
0x1800307d0  xor     ebx, ebx
0x1800307d2  mov     [rsp+68h+var_48], ebx
0x1800307d6  mov     eax, ebx
0x1800307d8  add     rsp, 38h
0x1800307dc  pop     r15
0x1800307de  pop     r14
0x1800307e0  pop     r12
0x1800307e2  pop     rdi
0x1800307e3  pop     rsi
0x1800307e4  pop     rbx
0x1800307e5  retn
```

# CLdapBer::HrAddValue(ushort const *,ulong)

- ea: `0x180011f50`
- end: `0x1800123f5`
- name: `?HrAddValue@CLdapBer@@QEAAKPEBGK@Z`
- size: `1189`
- prototype: `unsigned int(CLdapBer *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `16`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e0d0`
- `0x1800112b0`
- `0x180012400`
- `0x180012ab0`
- `0x1800164a0`
- `0x180027cf0`
- `0x18002d1a8`
- `0x18002dbac`
- `0x180039cd0`
- `0x18003a274`
- `0x18003c5bc`
- `0x18003e508`
- `0x18003f138`
- `0x1800400e4`
- `0x180047254`
- `0x18004a984`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x180011f50`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001220b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001220b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012181`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180011fc8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012079`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180011fc8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012079`

## pseudocode

```c
__int64 __fastcall CLdapBer::HrAddValue(CLdapBer *this, const unsigned __int16 *a2, char a3)
{
  int v3; // eax
  _DWORD *v4; // r14
  const WCHAR *v7; // rbp
  int v8; // ebx
  const WCHAR *v9; // rax
  unsigned int v10; // eax
  unsigned int cbMultiByte; // esi
  __int64 v12; // r9
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rcx
  unsigned int v19; // r15d
  DWORD LastError; // eax
  DWORD v21; // ebx
  unsigned int v22; // r12d
  int v23; // ecx
  unsigned int v24; // eax
  const void *v25; // rdx
  __int16 v26; // [rsp+70h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 216);
  v4 = 0;
  v26 = 0;
  if ( v3 )
  {
    a3 = v3;
    *((_DWORD *)this + 216) = 0;
  }
  v7 = (const WCHAR *)&v26;
  v8 = 0;
  if ( a2 )
    v7 = a2;
  v9 = v7;
  do
  {
    if ( !*v9 )
      break;
    ++v8;
    ++v9;
  }
  while ( v9 );
  v10 = WideCharToMultiByte(*((_DWORD *)this + 215), 0, v7, v8, 0, 0, 0, 0);
  cbMultiByte = v10;
  if ( !v10 && v8 )
  {
    LastError = GetLastError();
    v21 = LastError;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrAddValue received error of 0x%x from WideCharToMultiByte.\n", LastError);
    if ( v21 == 122 )
      return 2147942487LL;
    return 82;
  }
  v12 = v10 + 6;
  if ( (unsigned int)v12 < v10 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbValue 0x%x\n", v10);
    return 82;
  }
  v13 = *(unsigned int *)this;
  v14 = v13 + v12;
  if ( (int)v13 + (int)v12 < (unsigned int)v13 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n", v13, v12);
    return 82;
  }
  v15 = *((unsigned int *)this + 2);
  if ( v14 > (unsigned int)v15 || !(_DWORD)v15 )
  {
    if ( (unsigned int)v12 > 0x400 )
    {
      v19 = v15 + v12;
      if ( (int)v15 + (int)v12 < (unsigned int)v15 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataMax 0x%x, NeededLength 0x%x\n", v15, v12);
        return 82;
      }
    }
    else
    {
      v19 = v15 + 1024;
      if ( (int)v15 + 1024 < (unsigned int)v15 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n", v15, 1024);
        return 82;
      }
    }
    v22 = v19 + 8;
    if ( v19 + 8 < v19 )
      v22 = -1;
    else
      v4 = HeapAlloc(LdapHeap, 8u, v22);
    v23 = g_fTracingOn;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    {
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", v22, (_DWORD)v4, 1919238732);
      v23 = g_fTracingOn;
    }
    v24 = LdapAllocatedHeap;
    if ( v4 )
    {
      *v4 = 1919238732;
      v4[1] = v19;
      v4 += 2;
      v24 += v19;
      LdapAllocatedHeap = v24;
    }
    if ( v23 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        v19,
        (_DWORD)v4,
        1919238732,
        v24);
    if ( !v4 )
      return 90;
    v25 = (const void *)*((_QWORD *)this + 2);
    if ( v25 )
    {
      memcpy_0(v4, v25, *((unsigned int *)this + 2));
      ldapFree(*((_QWORD *)this + 2), 1919238732);
    }
    *((_QWORD *)this + 2) = v4;
    *((_DWORD *)this + 2) = v19;
  }
  *(_BYTE *)(*((unsigned int *)this + 1) + *((_QWORD *)this + 2)) = a3;
  v16 = *((_DWORD *)this + 1) + 1;
  *((_DWORD *)this + 1) = v16;
  if ( cbMultiByte > 0x7F )
  {
    if ( cbMultiByte > 0x7FFF )
    {
      if ( cbMultiByte >= 0x7FFFFFFF )
        return 2147942487LL;
      *(_BYTE *)(v16 + *((_QWORD *)this + 2)) = -124;
      *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = HIBYTE(cbMultiByte);
      *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE2(cbMultiByte);
    }
    else
    {
      *(_BYTE *)(v16 + *((_QWORD *)this + 2)) = -126;
    }
    *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE1(cbMultiByte);
    v17 = (unsigned int)++*((_DWORD *)this + 1);
  }
  else
  {
    v17 = v16;
  }
  *(_BYTE *)(v17 + *((_QWORD *)this + 2)) = cbMultiByte;
  ++*((_DWORD *)this + 1);
  if ( v8 )
    cbMultiByte = WideCharToMultiByte(
                    *((_DWORD *)this + 215),
                    0,
                    v7,
                    v8,
                    (LPSTR)(*((_QWORD *)this + 2) + *((unsigned int *)this + 1)),
                    cbMultiByte,
                    0,
                    0);
  *((_DWORD *)this + 1) += cbMultiByte;
  *(_DWORD *)this = *((_DWORD *)this + 1);
  return 0;
}

```

## disassembly

```asm
0x180011f50  mov     [rsp+arg_18], rbx
0x180011f55  push    rbp
0x180011f56  push    rsi
0x180011f57  push    rdi
0x180011f58  push    r13
0x180011f5a  push    r14
0x180011f5c  sub     rsp, 40h
0x180011f60  mov     eax, [rcx+360h]
0x180011f66  xor     r14d, r14d
0x180011f69  mov     [rsp+68h+arg_0], r14w
0x180011f6f  mov     r13d, r8d
0x180011f72  mov     rdi, rcx
0x180011f75  test    eax, eax
0x180011f77  jnz     loc_180012332
0x180011f7d  test    rdx, rdx
0x180011f80  lea     rbp, [rsp+68h+arg_0]
0x180011f85  mov     ebx, r14d
0x180011f88  cmovnz  rbp, rdx
0x180011f8c  mov     rax, rbp
0x180011f8f  nop
0x180011f90  cmp     [rax], r14w
0x180011f94  jz      short loc_180011F9E
0x180011f96  inc     ebx
0x180011f98  add     rax, 2
0x180011f9c  jnz     short loc_180011F90
0x180011f9e  mov     ecx, [rcx+35Ch]; CodePage
0x180011fa4  xor     edx, edx; dwFlags
0x180011fa6  mov     [rsp+68h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180011fab  mov     r9d, ebx; cchWideChar
0x180011fae  mov     [rsp+68h+lpDefaultChar], r14; lpDefaultChar
0x180011fb3  mov     r8, rbp; lpWideCharStr
0x180011fb6  mov     [rsp+68h+cbMultiByte], r14d; cbMultiByte
0x180011fbb  mov     [rsp+68h+lpMultiByteStr], r14; lpMultiByteStr
0x180011fc0  cmp     ecx, 0FDE9h
0x180011fc6  jnz     short $+2
0x180011fc8  call    cs:__imp_WideCharToMultiByte
0x180011fcf  nop     dword ptr [rax+rax+00h]
0x180011fd4  mov     [rsp+68h+arg_10], r15
0x180011fdc  mov     esi, eax
0x180011fde  test    eax, eax
0x180011fe0  jz      loc_180012179
0x180011fe6  lea     r9d, [rsi+6]
0x180011fea  cmp     r9d, esi
0x180011fed  jb      loc_1800120AF
0x180011ff3  mov     r8d, [rdi]
0x180011ff6  lea     eax, [r8+r9]
0x180011ffa  cmp     eax, r8d
0x180011ffd  jb      loc_1800120E4
0x180012003  mov     r8d, [rdi+8]
0x180012007  cmp     eax, r8d
0x18001200a  ja      loc_18001212B
0x180012010  test    r8d, r8d
0x180012013  jz      loc_18001212B
0x180012019  mov     ecx, [rdi+4]
0x18001201c  mov     rax, [rdi+10h]
0x180012020  mov     [rcx+rax], r13b
0x180012024  mov     eax, [rdi+4]
0x180012027  inc     eax
0x180012029  mov     [rdi+4], eax
0x18001202c  cmp     esi, 7Fh
0x18001202f  ja      loc_1800120F8
0x180012035  mov     ecx, eax
0x180012037  mov     rax, [rdi+10h]
0x18001203b  mov     [rcx+rax], sil
0x18001203f  inc     dword ptr [rdi+4]
0x180012042  mov     eax, [rdi+4]
0x180012045  test    ebx, ebx
0x180012047  jz      short loc_180012087
0x180012049  mov     ecx, [rdi+35Ch]; CodePage
0x18001204f  xor     edx, edx; dwFlags
0x180012051  mov     [rsp+68h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180012056  mov     r9d, ebx; cchWideChar
0x180012059  mov     [rsp+68h+lpDefaultChar], r14; lpDefaultChar
0x18001205e  mov     r8d, eax
0x180012061  add     r8, [rdi+10h]
0x180012065  mov     [rsp+68h+cbMultiByte], esi; cbMultiByte
0x180012069  mov     [rsp+68h+lpMultiByteStr], r8; lpMultiByteStr
0x18001206e  mov     r8, rbp; lpWideCharStr
0x180012071  cmp     ecx, 0FDE9h
0x180012077  jnz     short $+2
0x180012079  call    cs:__imp_WideCharToMultiByte
0x180012080  nop     dword ptr [rax+rax+00h]
0x180012085  mov     esi, eax
0x180012087  add     [rdi+4], esi
0x18001208a  mov     eax, [rdi+4]
0x18001208d  mov     [rdi], eax
0x18001208f  mov     eax, r14d
0x180012092  mov     r15, [rsp+68h+arg_10]
0x18001209a  mov     rbx, [rsp+68h+arg_18]
0x1800120a2  add     rsp, 40h
0x1800120a6  pop     r14
0x1800120a8  pop     r13
0x1800120aa  pop     rdi
0x1800120ab  pop     rsi
0x1800120ac  pop     rbp
0x1800120ad  retn
0x1800120af  cmp     cs:g_fTracingOn, r14d
0x1800120b6  jz      short loc_1800120F1
0x1800120b8  cmp     cs:g_fProviderEnabled, r14d
0x1800120bf  jz      short loc_1800120F1
0x1800120c1  test    cs:g_ulTraceFlags, 10000000h
0x1800120cc  jz      short loc_1800120F1
0x1800120ce  mov     r8d, esi
0x1800120d1  lea     rdx, aHraddvalueInte_0; "HrAddValue: integer overflow. cbValue 0"...
0x1800120d8  mov     ecx, 10000000h
0x1800120dd  call    LDAPClientPrint
0x1800120e2  jmp     short loc_1800120F1
0x1800120e4  cmp     cs:g_fTracingOn, r14d
0x1800120eb  jnz     loc_1800123E3
0x1800120f1  mov     eax, 52h ; 'R'
0x1800120f6  jmp     short loc_180012092
0x1800120f8  cmp     esi, 7FFFh
0x1800120fe  ja      loc_1800121AF
0x180012104  mov     ecx, eax
0x180012106  mov     rax, [rdi+10h]
0x18001210a  mov     byte ptr [rcx+rax], 82h
0x18001210e  inc     dword ptr [rdi+4]
0x180012111  mov     ecx, esi
0x180012113  mov     edx, [rdi+4]
0x180012116  mov     rax, [rdi+10h]
0x18001211a  shr     ecx, 8
0x18001211d  mov     [rdx+rax], cl
0x180012120  inc     dword ptr [rdi+4]
0x180012123  mov     ecx, [rdi+4]
0x180012126  jmp     loc_180012037
0x18001212b  cmp     r9d, 400h
0x180012132  ja      loc_180012286
0x180012138  lea     r15d, [r8+400h]
0x18001213f  cmp     r15d, r8d
0x180012142  jnb     loc_1800121EA
0x180012148  cmp     cs:g_fTracingOn, r14d
0x18001214f  jz      short loc_1800120F1
0x180012151  cmp     cs:g_fProviderEnabled, r14d
0x180012158  jz      short loc_1800120F1
0x18001215a  test    cs:g_ulTraceFlags, 10000000h
0x180012165  jz      short loc_1800120F1
0x180012167  mov     r9d, 400h
0x18001216d  lea     rdx, aHrensurebuffer_0; "HrEnsureBuffer: integer overflow. DataM"...
0x180012174  jmp     loc_180012323
0x180012179  test    ebx, ebx
0x18001217b  jz      loc_180011FE6
0x180012181  call    cs:__imp_GetLastError
0x180012188  nop     dword ptr [rax+rax+00h]
0x18001218d  cmp     cs:g_fTracingOn, r14d
0x180012194  mov     ebx, eax
0x180012196  jnz     loc_180012341
0x18001219c  cmp     ebx, 7Ah ; 'z'
0x18001219f  jnz     loc_1800120F1
0x1800121a5  mov     eax, 80070057h
0x1800121aa  jmp     loc_180012092
0x1800121af  cmp     esi, 7FFFFFFFh
0x1800121b5  jnb     short loc_1800121A5
0x1800121b7  mov     ecx, eax
0x1800121b9  mov     rax, [rdi+10h]
0x1800121bd  mov     byte ptr [rcx+rax], 84h
0x1800121c1  mov     ecx, esi
0x1800121c3  inc     dword ptr [rdi+4]
0x1800121c6  mov     edx, [rdi+4]
0x1800121c9  mov     rax, [rdi+10h]
0x1800121cd  shr     ecx, 18h
0x1800121d0  mov     [rdx+rax], cl
0x1800121d3  mov     ecx, esi
0x1800121d5  inc     dword ptr [rdi+4]
0x1800121d8  mov     edx, [rdi+4]
0x1800121db  mov     rax, [rdi+10h]
0x1800121df  shr     ecx, 10h
0x1800121e2  mov     [rdx+rax], cl
0x1800121e5  jmp     loc_18001210E
0x1800121ea  mov     [rsp+68h+arg_8], r12
0x1800121ef  lea     r12d, [r15+8]
0x1800121f3  cmp     r12d, r15d
0x1800121f6  jb      loc_18001227E
0x1800121fc  mov     rcx, cs:LdapHeap; hHeap
0x180012203  mov     edx, 8; dwFlags
0x180012208  mov     r8d, r12d; dwBytes
0x18001220b  call    cs:__imp_HeapAlloc
0x180012212  nop     dword ptr [rax+rax+00h]
0x180012217  mov     r14, rax
0x18001221a  mov     ecx, cs:g_fTracingOn
0x180012220  test    ecx, ecx
0x180012222  jnz     loc_1800122C7
0x180012228  mov     r12, [rsp+68h+arg_8]
0x18001222d  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180012233  test    r14, r14
0x180012236  jz      short loc_180012250
0x180012238  mov     dword ptr [r14], 7265424Ch
0x18001223f  mov     [r14+4], r15d
0x180012243  add     r14, 8
0x180012247  add     eax, r15d
0x18001224a  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180012250  test    ecx, ecx
0x180012252  jnz     loc_180012378
0x180012258  test    r14, r14
0x18001225b  jz      loc_1800123BA
0x180012261  mov     rdx, [rdi+10h]; Src
0x180012265  test    rdx, rdx
0x180012268  jnz     loc_1800123C4
0x18001226e  mov     [rdi+10h], r14
0x180012272  xor     r14d, r14d
0x180012275  mov     [rdi+8], r15d
0x180012279  jmp     loc_180012019
0x18001227e  mov     r12d, 0FFFFFFFFh
0x180012284  jmp     short loc_18001221A
0x180012286  lea     r15d, [r8+r9]
0x18001228a  cmp     r15d, r8d
0x18001228d  jnb     loc_1800121EA
0x180012293  cmp     cs:g_fTracingOn, r14d
0x18001229a  jz      loc_1800120F1
0x1800122a0  cmp     cs:g_fProviderEnabled, r14d
0x1800122a7  jz      loc_1800120F1
0x1800122ad  test    cs:g_ulTraceFlags, 10000000h
0x1800122b8  jz      loc_1800120F1
0x1800122be  lea     rdx, aHrensurebuffer_1; "HrEnsureBuffer: integer overflow. DataM"...
0x1800122c5  jmp     short loc_180012323
0x1800122c7  cmp     cs:g_fProviderEnabled, 0
0x1800122ce  jz      loc_180012228
0x1800122d4  test    byte ptr cs:g_ulTraceFlags, 8
0x1800122db  jz      loc_180012228
0x1800122e1  mov     r9, r14
0x1800122e4  mov     dword ptr [rsp+68h+lpMultiByteStr], 7265424Ch
0x1800122ec  mov     r8d, r12d
0x1800122ef  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x1800122f6  mov     ecx, 8
0x1800122fb  call    LDAPClientPrint
0x180012300  mov     ecx, cs:g_fTracingOn
0x180012306  jmp     loc_180012228
0x18001230b  test    cs:g_ulTraceFlags, 10000000h
0x180012316  jz      loc_1800120F1
0x18001231c  lea     rdx, aHrensurebuffer; "HrEnsureBuffer: integer overflow. DataL"...
0x180012323  mov     ecx, 10000000h
0x180012328  call    LDAPClientPrint
0x18001232d  jmp     loc_1800120F1
0x180012332  mov     r13d, eax
0x180012335  mov     [rcx+360h], r14d
0x18001233c  jmp     loc_180011F7D
0x180012341  cmp     cs:g_fProviderEnabled, r14d
0x180012348  jz      loc_18001219C
0x18001234e  test    cs:g_ulTraceFlags, 2000h
0x180012359  jz      loc_18001219C
0x18001235f  mov     r8d, ebx
0x180012362  lea     rdx, aHraddvalueRece; "HrAddValue received error of 0x%x from "...
0x180012369  mov     ecx, 2000h
0x18001236e  call    LDAPClientPrint
0x180012373  jmp     loc_18001219C
0x180012378  cmp     cs:g_fProviderEnabled, 0
0x18001237f  jz      loc_180012258
0x180012385  test    byte ptr cs:g_ulTraceFlags, 8
0x18001238c  jz      loc_180012258
0x180012392  mov     [rsp+68h+cbMultiByte], eax
0x180012396  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x18001239d  mov     r9, r14
0x1800123a0  mov     dword ptr [rsp+68h+lpMultiByteStr], 7265424Ch
0x1800123a8  mov     r8d, r15d
0x1800123ab  mov     ecx, 8
0x1800123b0  call    LDAPClientPrint
0x1800123b5  jmp     loc_180012258
0x1800123ba  mov     eax, 5Ah ; 'Z'
0x1800123bf  jmp     loc_180012092
0x1800123c4  mov     r8d, [rdi+8]; Size
0x1800123c8  mov     rcx, r14; void *
0x1800123cb  call    memcpy_0
0x1800123d0  mov     rcx, [rdi+10h]
0x1800123d4  mov     edx, 7265424Ch
0x1800123d9  call    ldapFree
0x1800123de  jmp     loc_18001226E
0x1800123e3  cmp     cs:g_fProviderEnabled, r14d
0x1800123ea  jz      loc_1800120F1
0x1800123f0  jmp     loc_18001230B
```

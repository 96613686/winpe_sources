# ToUnicodeWithAlloc

- ea: `0x18001ffa0`
- end: `0x1800201d5`
- name: `ToUnicodeWithAlloc`
- size: `565`
- prototype: `__int64 __usercall@<rax>(LPCCH lpMultiByteStr@<rcx>, int)`
- caller_count: `35`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ce40`
- `0x18001cf70`
- `0x18001de00`
- `0x18001fb78`
- `0x1800227d8`
- `0x180031c98`
- `0x180039cd0`
- `0x18003a750`
- `0x18003a9b0`
- `0x18003bd34`
- `0x18003caf0`
- `0x18003ce30`
- `0x18003e7f0`
- `0x18003ea40`
- `0x18003f500`
- `0x18003f760`
- `0x1800400e4`
- `0x1800408b0`
- `0x180040b10`
- `0x180040f90`
- `0x1800412d0`
- `0x180041620`
- `0x180043e40`
- `0x180043ec0`
- `0x180045280`
- `0x1800475f0`
- `0x180047c30`
- `0x180047f80`
- `0x1800488d0`
- `0x180048a40`
- `0x180048d40`
- `0x180049d3c`
- `0x180049f10`
- `0x18004a270`
- `0x18004af20`

## callees

- `0x1800037a8`
- `0x18001ffa0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020093`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020093`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002001b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180020104`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002001b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180020104`

## pseudocode

```c
__int64 __fastcall ToUnicodeWithAlloc(LPCCH lpMultiByteStr, int a2, WCHAR **a3, int a4, int a5)
{
  WCHAR *lpWideCharStr; // r14
  int v7; // ebx
  LPCCH v9; // rax
  __int64 v10; // rcx
  UINT v11; // ecx
  unsigned int cchWideChar; // edi
  __int64 result; // rax
  unsigned int v14; // eax
  unsigned __int64 v15; // rbp
  unsigned int v16; // r15d
  int v17; // ecx
  unsigned int v18; // eax
  UINT v19; // ecx
  __int64 v20; // rdx

  lpWideCharStr = 0;
  *a3 = 0;
  v7 = a2;
  if ( !lpMultiByteStr )
    return 0;
  if ( a2 == -1 )
  {
    v9 = lpMultiByteStr;
    v10 = 0x7FFFFFFF;
    while ( *v9 )
    {
      ++v9;
      if ( !--v10 )
        return 89;
    }
    v7 = 0x7FFFFFFF - v10;
  }
  else if ( a2 < 0 )
  {
    return 89;
  }
  if ( a5 == 2 )
    v11 = 65001;
  else
    v11 = 0;
  cchWideChar = MultiByteToWideChar(v11, 0, lpMultiByteStr, v7, 0, 0);
  if ( cchWideChar )
  {
    v14 = cchWideChar + 1;
    if ( cchWideChar + 1 < cchWideChar )
      return 89;
  }
  else
  {
    if ( v7 )
      return 89;
    v14 = cchWideChar + 1;
  }
  v15 = 2LL * v14;
  if ( v15 > 0xFFFFFFFF )
    return 89;
  v16 = v15 + 8;
  if ( (int)v15 + 8 < (unsigned int)v15 )
    v16 = -1;
  else
    lpWideCharStr = (WCHAR *)HeapAlloc(LdapHeap, 8u, v16);
  v17 = g_fTracingOn;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", v16, (_DWORD)lpWideCharStr, a4);
    v17 = g_fTracingOn;
  }
  v18 = LdapAllocatedHeap;
  if ( lpWideCharStr )
  {
    *(_DWORD *)lpWideCharStr = a4;
    *((_DWORD *)lpWideCharStr + 1) = v15;
    lpWideCharStr += 4;
    v18 += v15;
    LdapAllocatedHeap = v18;
  }
  if ( v17 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(
      8,
      "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
      v15,
      (_DWORD)lpWideCharStr,
      a4,
      v18);
  *a3 = lpWideCharStr;
  if ( !lpWideCharStr )
    return 90;
  if ( a5 == 2 )
    v19 = 65001;
  else
    v19 = 0;
  v20 = (unsigned int)MultiByteToWideChar(v19, 0, lpMultiByteStr, v7, lpWideCharStr, cchWideChar);
  result = 0;
  (*a3)[v20] = 0;
  return result;
}

```

## disassembly

```asm
0x18001ffa0  mov     [rsp+arg_18], r9d
0x18001ffa5  push    rbx
0x18001ffa6  push    r12
0x18001ffa8  push    r13
0x18001ffaa  push    r14
0x18001ffac  sub     rsp, 38h
0x18001ffb0  xor     r14d, r14d
0x18001ffb3  mov     r13, r8
0x18001ffb6  mov     [r8], r14
0x18001ffb9  mov     ebx, edx
0x18001ffbb  mov     r12, rcx
0x18001ffbe  test    rcx, rcx
0x18001ffc1  jz      loc_18002017E
0x18001ffc7  mov     [rsp+58h+arg_0], rbp
0x18001ffcc  mov     [rsp+58h+arg_8], rsi
0x18001ffd1  mov     [rsp+58h+arg_10], rdi
0x18001ffd6  cmp     edx, 0FFFFFFFFh
0x18001ffd9  jnz     short loc_180020056
0x18001ffdb  mov     ebx, 7FFFFFFFh
0x18001ffe0  mov     rax, r12
0x18001ffe3  mov     ecx, ebx
0x18001ffe5  cmp     [rax], r14b
0x18001ffe8  jz      short loc_18001FFF5
0x18001ffea  inc     rax
0x18001ffed  sub     rcx, 1
0x18001fff1  jnz     short loc_18001FFE5
0x18001fff3  jmp     short loc_180020035
0x18001fff5  sub     ebx, ecx
0x18001fff7  mov     esi, [rsp+58h+arg_20]
0x18001fffe  xor     edx, edx; dwFlags
0x180020000  mov     [rsp+58h+cchWideChar], r14d; cchWideChar
0x180020005  mov     r9d, ebx; cbMultiByte
0x180020008  mov     [rsp+58h+lpWideCharStr], r14; lpWideCharStr
0x18002000d  mov     r8, r12; lpMultiByteStr
0x180020010  cmp     esi, 2
0x180020013  jz      loc_180020129
0x180020019  xor     ecx, ecx; CodePage
0x18002001b  call    cs:__imp_MultiByteToWideChar
0x180020022  nop     dword ptr [rax+rax+00h]
0x180020027  mov     edi, eax
0x180020029  test    eax, eax
0x18002002b  jnz     short loc_18002005C
0x18002002d  test    ebx, ebx
0x18002002f  jz      loc_180020185
0x180020035  mov     eax, 59h ; 'Y'
0x18002003a  mov     rsi, [rsp+58h+arg_8]
0x18002003f  mov     rbp, [rsp+58h+arg_0]
0x180020044  mov     rdi, [rsp+58h+arg_10]
0x180020049  add     rsp, 38h
0x18002004d  pop     r14
0x18002004f  pop     r13
0x180020051  pop     r12
0x180020053  pop     rbx
0x180020054  retn
0x180020056  test    edx, edx
0x180020058  jns     short loc_18001FFF7
0x18002005a  jmp     short loc_180020035
0x18002005c  lea     eax, [rdi+1]
0x18002005f  cmp     eax, edi
0x180020061  jb      short loc_180020035
0x180020063  mov     ebp, eax
0x180020065  mov     eax, 0FFFFFFFFh
0x18002006a  add     rbp, rbp
0x18002006d  cmp     rbp, rax
0x180020070  ja      short loc_180020035
0x180020072  mov     [rsp+58h+var_28], r15
0x180020077  lea     r15d, [rbp+8]
0x18002007b  cmp     r15d, ebp
0x18002007e  jb      loc_180020121
0x180020084  mov     rcx, cs:LdapHeap; hHeap
0x18002008b  mov     edx, 8; dwFlags
0x180020090  mov     r8d, r15d; dwBytes
0x180020093  call    cs:__imp_HeapAlloc
0x18002009a  nop     dword ptr [rax+rax+00h]
0x18002009f  mov     r14, rax
0x1800200a2  mov     ecx, cs:g_fTracingOn
0x1800200a8  test    ecx, ecx
0x1800200aa  jnz     loc_18002013A
0x1800200b0  mov     r15, [rsp+58h+var_28]
0x1800200b5  mov     edx, [rsp+58h+arg_18]
0x1800200b9  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x1800200bf  test    r14, r14
0x1800200c2  jz      short loc_1800200D7
0x1800200c4  mov     [r14], edx
0x1800200c7  mov     [r14+4], ebp
0x1800200cb  add     r14, 8
0x1800200cf  add     eax, ebp
0x1800200d1  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x1800200d7  test    ecx, ecx
0x1800200d9  jnz     loc_18002018D
0x1800200df  mov     [r13+0], r14
0x1800200e3  test    r14, r14
0x1800200e6  jz      loc_1800201CB
0x1800200ec  xor     edx, edx; dwFlags
0x1800200ee  mov     [rsp+58h+cchWideChar], edi; cchWideChar
0x1800200f2  mov     [rsp+58h+lpWideCharStr], r14; lpWideCharStr
0x1800200f7  mov     r9d, ebx; cbMultiByte
0x1800200fa  mov     r8, r12; lpMultiByteStr
0x1800200fd  cmp     esi, 2
0x180020100  jz      short loc_180020133
0x180020102  xor     ecx, ecx; CodePage
0x180020104  call    cs:__imp_MultiByteToWideChar
0x18002010b  nop     dword ptr [rax+rax+00h]
0x180020110  mov     rcx, [r13+0]
0x180020114  mov     edx, eax
0x180020116  xor     eax, eax
0x180020118  mov     [rcx+rdx*2], ax
0x18002011c  jmp     loc_18002003A
0x180020121  mov     r15d, eax
0x180020124  jmp     loc_1800200A2
0x180020129  mov     ecx, 0FDE9h
0x18002012e  jmp     loc_18002001B
0x180020133  mov     ecx, 0FDE9h
0x180020138  jmp     short loc_180020104
0x18002013a  cmp     cs:g_fProviderEnabled, 0
0x180020141  jz      loc_1800200B0
0x180020147  test    byte ptr cs:g_ulTraceFlags, 8
0x18002014e  jz      loc_1800200B0
0x180020154  mov     eax, [rsp+58h+arg_18]
0x180020158  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x18002015f  mov     r9, r14
0x180020162  mov     dword ptr [rsp+58h+lpWideCharStr], eax
0x180020166  mov     r8d, r15d
0x180020169  mov     ecx, 8
0x18002016e  call    LDAPClientPrint
0x180020173  mov     ecx, cs:g_fTracingOn
0x180020179  jmp     loc_1800200B0
0x18002017e  xor     eax, eax
0x180020180  jmp     loc_180020049
0x180020185  lea     eax, [rdi+1]
0x180020188  jmp     loc_180020063
0x18002018d  cmp     cs:g_fProviderEnabled, 0
0x180020194  jz      loc_1800200DF
0x18002019a  test    byte ptr cs:g_ulTraceFlags, 8
0x1800201a1  jz      loc_1800200DF
0x1800201a7  mov     [rsp+58h+cchWideChar], eax
0x1800201ab  mov     r9, r14
0x1800201ae  mov     dword ptr [rsp+58h+lpWideCharStr], edx
0x1800201b2  mov     r8d, ebp
0x1800201b5  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x1800201bc  mov     ecx, 8
0x1800201c1  call    LDAPClientPrint
0x1800201c6  jmp     loc_1800200DF
0x1800201cb  mov     eax, 5Ah ; 'Z'
0x1800201d0  jmp     loc_18002003A
```

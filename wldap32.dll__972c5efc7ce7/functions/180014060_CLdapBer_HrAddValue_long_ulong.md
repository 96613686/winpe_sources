# CLdapBer::HrAddValue(long,ulong)

- ea: `0x180014060`
- end: `0x180014458`
- name: `?HrAddValue@CLdapBer@@QEAAKJK@Z`
- size: `1016`
- prototype: `unsigned int __fastcall(CLdapBer *__hidden this, int, unsigned int)`
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e0d0`
- `0x1800112b0`
- `0x180012ab0`
- `0x1800164a0`
- `0x18001f96c`
- `0x1800230a0`
- `0x18002bac0`
- `0x18002d1a8`
- `0x180038678`
- `0x18003a274`
- `0x18003c5bc`
- `0x18003e508`
- `0x18003f138`
- `0x1800400e4`
- `0x18004404c`
- `0x180047254`
- `0x1800491d4`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x180014060`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001428f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001428f`

## pseudocode

```c
__int64 __fastcall CLdapBer::HrAddValue(CLdapBer *this, int a2, char a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // edi
  __int64 v9; // r9
  __int64 v11; // r8
  unsigned int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // r8d
  unsigned int v17; // r9d
  _BYTE *i; // rdx
  unsigned int v19; // r15d
  unsigned int v20; // r12d
  _DWORD *v21; // r14
  int v22; // ecx
  unsigned int v23; // eax
  const void *v24; // rdx

  if ( *((_DWORD *)this + 216) )
  {
    a3 = *((_DWORD *)this + 216);
    *((_DWORD *)this + 216) = 0;
  }
  if ( !a2 )
  {
    v8 = 1;
    v9 = 7;
    goto LABEL_15;
  }
  v6 = -16777216;
  v7 = 0x80000000;
  v8 = 4;
  do
  {
    if ( (v6 & a2) != 0 )
      break;
    v7 >>= 8;
    --v8;
    v6 >>= 8;
  }
  while ( v6 );
  if ( a2 >= 0 && (v7 & a2) != 0 )
    ++v8;
  v9 = v8 + 6;
  if ( (unsigned int)v9 >= v8 )
  {
LABEL_15:
    v11 = *(unsigned int *)this;
    v12 = v11 + v9;
    if ( (int)v11 + (int)v9 < (unsigned int)v11 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n", v11, v9);
      return 82;
    }
    v13 = *((unsigned int *)this + 2);
    if ( v12 <= (unsigned int)v13 && (_DWORD)v13 )
      goto LABEL_18;
    if ( (unsigned int)v9 > 0x400 )
    {
      v19 = v13 + v9;
      if ( (int)v13 + (int)v9 < (unsigned int)v13 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataMax 0x%x, NeededLength 0x%x\n", v13, v9);
        return 82;
      }
    }
    else
    {
      v19 = v13 + 1024;
      if ( (int)v13 + 1024 < (unsigned int)v13 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n", v13, 1024);
        return 82;
      }
    }
    v20 = v19 + 8;
    if ( v19 + 8 < v19 )
    {
      v21 = 0;
      v20 = -1;
    }
    else
    {
      v21 = HeapAlloc(LdapHeap, 8u, v20);
    }
    v22 = g_fTracingOn;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    {
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", v20, (_DWORD)v21, 1919238732);
      v22 = g_fTracingOn;
    }
    v23 = LdapAllocatedHeap;
    if ( v21 )
    {
      *v21 = 1919238732;
      v21[1] = v19;
      v21 += 2;
      v23 += v19;
      LdapAllocatedHeap = v23;
    }
    if ( v22 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        v19,
        (_DWORD)v21,
        1919238732,
        v23);
    if ( !v21 )
      return 90;
    v24 = (const void *)*((_QWORD *)this + 2);
    if ( v24 )
    {
      memcpy_0(v21, v24, *((unsigned int *)this + 2));
      ldapFree(*((_QWORD *)this + 2), 1919238732);
    }
    *((_QWORD *)this + 2) = v21;
    *((_DWORD *)this + 2) = v19;
LABEL_18:
    *(_BYTE *)(*((unsigned int *)this + 1) + *((_QWORD *)this + 2)) = a3;
    v14 = *((_DWORD *)this + 1) + 1;
    *((_DWORD *)this + 1) = v14;
    if ( v8 > 0x7F )
    {
      if ( v8 > 0x7FFF )
      {
        if ( v8 >= 0x7FFFFFFF )
          return (unsigned int)-2147024809;
        *(_BYTE *)(v14 + *((_QWORD *)this + 2)) = -124;
        *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = HIBYTE(v8);
        *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE2(v8);
      }
      else
      {
        *(_BYTE *)(v14 + *((_QWORD *)this + 2)) = -126;
      }
      *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE1(v8);
      v15 = (unsigned int)++*((_DWORD *)this + 1);
    }
    else
    {
      v15 = v14;
    }
    v16 = 0;
    v17 = v8;
    *(_BYTE *)(v15 + *((_QWORD *)this + 2)) = v8;
    for ( i = (_BYTE *)(*((_QWORD *)this + 2) + (unsigned int)++*((_DWORD *)this + 1)); v8; --v8 )
      *i++ = a2 >> (8 * v8 - 8);
    *((_DWORD *)this + 1) += v17;
    *(_DWORD *)this = *((_DWORD *)this + 1);
    return v16;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
    LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbInt 0x%x\n", v8);
  return 82;
}

```

## disassembly

```asm
0x180014060  push    rbx
0x180014062  push    rbp
0x180014063  push    rsi
0x180014064  sub     rsp, 30h
0x180014068  mov     eax, [rcx+360h]
0x18001406e  mov     ebp, r8d
0x180014071  mov     esi, edx
0x180014073  mov     rbx, rcx
0x180014076  test    eax, eax
0x180014078  jnz     loc_1800143B2
0x18001407e  mov     [rsp+48h+arg_0], rdi
0x180014083  test    esi, esi
0x180014085  jz      short loc_1800140F4
0x180014087  mov     eax, 0FF000000h
0x18001408c  mov     ecx, 80000000h
0x180014091  mov     edi, 4
0x180014096  test    esi, eax
0x180014098  jnz     short loc_1800140A6
0x18001409a  shr     ecx, 8
0x18001409d  dec     edi
0x18001409f  shr     eax, 8
0x1800140a2  test    eax, eax
0x1800140a4  jnz     short loc_180014096
0x1800140a6  test    esi, esi
0x1800140a8  jns     loc_180014311
0x1800140ae  lea     r9d, [rdi+6]
0x1800140b2  cmp     r9d, edi
0x1800140b5  jnb     short loc_1800140FF
0x1800140b7  cmp     cs:g_fTracingOn, 0
0x1800140be  jz      short loc_1800140EA
0x1800140c0  cmp     cs:g_fProviderEnabled, 0
0x1800140c7  jz      short loc_1800140EA
0x1800140c9  test    cs:g_ulTraceFlags, 10000000h
0x1800140d4  jz      short loc_1800140EA
0x1800140d6  mov     r8d, edi
0x1800140d9  lea     rdx, aHraddvalueInte; "HrAddValue: integer overflow. cbInt 0x%"...
0x1800140e0  mov     ecx, 10000000h
0x1800140e5  call    LDAPClientPrint
0x1800140ea  mov     eax, 52h ; 'R'
0x1800140ef  jmp     loc_180014197
0x1800140f4  mov     edi, 1
0x1800140f9  mov     r9d, 7
0x1800140ff  mov     r8d, [rbx]
0x180014102  mov     [rsp+48h+arg_10], r14
0x180014107  mov     [rsp+48h+arg_18], r15
0x18001410c  lea     eax, [r8+r9]
0x180014110  cmp     eax, r8d
0x180014113  jb      loc_1800141A5
0x180014119  mov     r8d, [rbx+8]
0x18001411d  cmp     eax, r8d
0x180014120  ja      loc_1800141B9
0x180014126  test    r8d, r8d
0x180014129  jz      loc_1800141B9
0x18001412f  mov     ecx, [rbx+4]
0x180014132  mov     rax, [rbx+10h]
0x180014136  mov     [rcx+rax], bpl
0x18001413a  mov     eax, [rbx+4]
0x18001413d  inc     eax
0x18001413f  mov     [rbx+4], eax
0x180014142  cmp     edi, 7Fh
0x180014145  ja      loc_180014207
0x18001414b  mov     ecx, eax
0x18001414d  mov     rax, [rbx+10h]
0x180014151  xor     r8d, r8d
0x180014154  mov     r9d, edi
0x180014157  mov     [rcx+rax], dil
0x18001415b  inc     dword ptr [rbx+4]
0x18001415e  mov     eax, [rbx+4]
0x180014161  mov     edx, eax
0x180014163  add     rdx, [rbx+10h]
0x180014167  test    edi, edi
0x180014169  jz      short loc_180014181
0x18001416b  lea     ecx, ds:0FFFFFFFFFFFFFFF8h[rdi*8]
0x180014172  mov     eax, esi
0x180014174  sar     eax, cl
0x180014176  mov     [rdx], al
0x180014178  lea     rdx, [rdx+1]
0x18001417c  add     edi, 0FFFFFFFFh
0x18001417f  jnz     short loc_18001416B
0x180014181  add     [rbx+4], r9d
0x180014185  mov     eax, [rbx+4]
0x180014188  mov     [rbx], eax
0x18001418a  mov     eax, r8d
0x18001418d  mov     r14, [rsp+48h+arg_10]
0x180014192  mov     r15, [rsp+48h+arg_18]
0x180014197  mov     rdi, [rsp+48h+arg_0]
0x18001419c  add     rsp, 30h
0x1800141a0  pop     rsi
0x1800141a1  pop     rbp
0x1800141a2  pop     rbx
0x1800141a3  retn
0x1800141a5  cmp     cs:g_fTracingOn, 0
0x1800141ac  jnz     loc_180014424
0x1800141b2  mov     eax, 52h ; 'R'
0x1800141b7  jmp     short loc_18001418D
0x1800141b9  cmp     r9d, 400h
0x1800141c0  ja      loc_18001432A
0x1800141c6  lea     r15d, [r8+400h]
0x1800141cd  cmp     r15d, r8d
0x1800141d0  jnb     loc_180014272
0x1800141d6  cmp     cs:g_fTracingOn, 0
0x1800141dd  jz      short loc_1800141B2
0x1800141df  cmp     cs:g_fProviderEnabled, 0
0x1800141e6  jz      short loc_1800141B2
0x1800141e8  test    cs:g_ulTraceFlags, 10000000h
0x1800141f3  jz      short loc_1800141B2
0x1800141f5  mov     r9d, 400h
0x1800141fb  lea     rdx, aHrensurebuffer_0; "HrEnsureBuffer: integer overflow. DataM"...
0x180014202  jmp     loc_180014449
0x180014207  cmp     edi, 7FFFh
0x18001420d  ja      short loc_180014236
0x18001420f  mov     ecx, eax
0x180014211  mov     rax, [rbx+10h]
0x180014215  mov     byte ptr [rcx+rax], 82h
0x180014219  inc     dword ptr [rbx+4]
0x18001421c  mov     ecx, edi
0x18001421e  mov     edx, [rbx+4]
0x180014221  mov     rax, [rbx+10h]
0x180014225  shr     ecx, 8
0x180014228  mov     [rdx+rax], cl
0x18001422b  inc     dword ptr [rbx+4]
0x18001422e  mov     ecx, [rbx+4]
0x180014231  jmp     loc_18001414D
0x180014236  cmp     edi, 7FFFFFFFh
0x18001423c  jnb     loc_180014306
0x180014242  mov     ecx, eax
0x180014244  mov     rax, [rbx+10h]
0x180014248  mov     byte ptr [rcx+rax], 84h
0x18001424c  mov     ecx, edi
0x18001424e  inc     dword ptr [rbx+4]
0x180014251  mov     edx, [rbx+4]
0x180014254  mov     rax, [rbx+10h]
0x180014258  shr     ecx, 18h
0x18001425b  mov     [rdx+rax], cl
0x18001425e  mov     ecx, edi
0x180014260  inc     dword ptr [rbx+4]
0x180014263  mov     edx, [rbx+4]
0x180014266  mov     rax, [rbx+10h]
0x18001426a  shr     ecx, 10h
0x18001426d  mov     [rdx+rax], cl
0x180014270  jmp     short loc_180014219
0x180014272  mov     [rsp+48h+arg_8], r12
0x180014277  lea     r12d, [r15+8]
0x18001427b  cmp     r12d, r15d
0x18001427e  jb      short loc_1800142FB
0x180014280  mov     rcx, cs:LdapHeap; hHeap
0x180014287  mov     edx, 8; dwFlags
0x18001428c  mov     r8d, r12d; dwBytes
0x18001428f  call    cs:__imp_HeapAlloc
0x180014296  nop     dword ptr [rax+rax+00h]
0x18001429b  mov     r14, rax
0x18001429e  mov     ecx, cs:g_fTracingOn
0x1800142a4  test    ecx, ecx
0x1800142a6  jnz     loc_18001436E
0x1800142ac  mov     r12, [rsp+48h+arg_8]
0x1800142b1  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x1800142b7  test    r14, r14
0x1800142ba  jz      short loc_1800142D4
0x1800142bc  mov     dword ptr [r14], 7265424Ch
0x1800142c3  mov     [r14+4], r15d
0x1800142c7  add     r14, 8
0x1800142cb  add     eax, r15d
0x1800142ce  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x1800142d4  test    ecx, ecx
0x1800142d6  jnz     loc_1800143C3
0x1800142dc  test    r14, r14
0x1800142df  jz      short loc_180014320
0x1800142e1  mov     rdx, [rbx+10h]; Src
0x1800142e5  test    rdx, rdx
0x1800142e8  jnz     loc_180014405
0x1800142ee  mov     [rbx+10h], r14
0x1800142f2  mov     [rbx+8], r15d
0x1800142f6  jmp     loc_18001412F
0x1800142fb  xor     r14d, r14d
0x1800142fe  mov     r12d, 0FFFFFFFFh
0x180014304  jmp     short loc_18001429E
0x180014306  mov     r8d, 80070057h
0x18001430c  jmp     loc_18001418A
0x180014311  test    esi, ecx
0x180014313  jz      loc_1800140AE
0x180014319  inc     edi
0x18001431b  jmp     loc_1800140AE
0x180014320  mov     eax, 5Ah ; 'Z'
0x180014325  jmp     loc_18001418D
0x18001432a  lea     r15d, [r8+r9]
0x18001432e  cmp     r15d, r8d
0x180014331  jnb     loc_180014272
0x180014337  cmp     cs:g_fTracingOn, 0
0x18001433e  jz      loc_1800141B2
0x180014344  cmp     cs:g_fProviderEnabled, 0
0x18001434b  jz      loc_1800141B2
0x180014351  test    cs:g_ulTraceFlags, 10000000h
0x18001435c  jz      loc_1800141B2
0x180014362  lea     rdx, aHrensurebuffer_1; "HrEnsureBuffer: integer overflow. DataM"...
0x180014369  jmp     loc_180014449
0x18001436e  cmp     cs:g_fProviderEnabled, 0
0x180014375  jz      loc_1800142AC
0x18001437b  test    byte ptr cs:g_ulTraceFlags, 8
0x180014382  jz      loc_1800142AC
0x180014388  mov     r9, r14
0x18001438b  mov     [rsp+48h+var_28], 7265424Ch
0x180014393  mov     r8d, r12d
0x180014396  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x18001439d  mov     ecx, 8
0x1800143a2  call    LDAPClientPrint
0x1800143a7  mov     ecx, cs:g_fTracingOn
0x1800143ad  jmp     loc_1800142AC
0x1800143b2  mov     ebp, eax
0x1800143b4  mov     dword ptr [rcx+360h], 0
0x1800143be  jmp     loc_18001407E
0x1800143c3  cmp     cs:g_fProviderEnabled, 0
0x1800143ca  jz      loc_1800142DC
0x1800143d0  test    byte ptr cs:g_ulTraceFlags, 8
0x1800143d7  jz      loc_1800142DC
0x1800143dd  mov     [rsp+48h+var_20], eax
0x1800143e1  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x1800143e8  mov     r9, r14
0x1800143eb  mov     [rsp+48h+var_28], 7265424Ch
0x1800143f3  mov     r8d, r15d
0x1800143f6  mov     ecx, 8
0x1800143fb  call    LDAPClientPrint
0x180014400  jmp     loc_1800142DC
0x180014405  mov     r8d, [rbx+8]; Size
0x180014409  mov     rcx, r14; void *
0x18001440c  call    memcpy_0
0x180014411  mov     rcx, [rbx+10h]
0x180014415  mov     edx, 7265424Ch
0x18001441a  call    ldapFree
0x18001441f  jmp     loc_1800142EE
0x180014424  cmp     cs:g_fProviderEnabled, 0
0x18001442b  jz      loc_1800141B2
0x180014431  test    cs:g_ulTraceFlags, 10000000h
0x18001443c  jz      loc_1800141B2
0x180014442  lea     rdx, aHrensurebuffer; "HrEnsureBuffer: integer overflow. DataL"...
0x180014449  mov     ecx, 10000000h
0x18001444e  call    LDAPClientPrint
0x180014453  jmp     loc_1800141B2
```

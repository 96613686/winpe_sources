# CLdapBer::HrStartWriteSequence(ulong)

- ea: `0x180011c80`
- end: `0x180011f3f`
- name: `?HrStartWriteSequence@CLdapBer@@QEAAKK@Z`
- size: `703`
- prototype: `unsigned int __fastcall(CLdapBer *__hidden this, unsigned int)`
- caller_count: `21`
- callee_count: `4`
- tags: ``

## callers

- `0x1800112b0`
- `0x180012400`
- `0x180012ab0`
- `0x180013610`
- `0x1800164a0`
- `0x18001f96c`
- `0x1800230a0`
- `0x18002bac0`
- `0x18002d1a8`
- `0x18002dbac`
- `0x180038678`
- `0x180039cd0`
- `0x18003a274`
- `0x18003c5bc`
- `0x18003e508`
- `0x18003f138`
- `0x1800400e4`
- `0x18004404c`
- `0x180047254`
- `0x1800491d4`
- `0x18004a984`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x180011c80`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011d89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011d89`

## pseudocode

```c
__int64 __fastcall CLdapBer::HrStartWriteSequence(CLdapBer *this, char a2)
{
  unsigned int v4; // eax
  unsigned int v5; // r8d
  __int64 v6; // rax
  int v7; // edx
  int v8; // ecx
  __int64 result; // rax
  unsigned int v10; // ebp
  unsigned int v11; // r14d
  _DWORD *v12; // rsi
  int v13; // ecx
  unsigned int v14; // eax
  const void *v15; // rdx

  if ( *((_DWORD *)this + 216) )
  {
    a2 = *((_DWORD *)this + 216);
    *((_DWORD *)this + 216) = 0;
  }
  v4 = *(_DWORD *)this + 6;
  if ( v4 < *(_DWORD *)this )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientPrint(
        0x10000000,
        "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n",
        *(_DWORD *)this,
        6);
    return 82;
  }
  v5 = *((_DWORD *)this + 2);
  if ( v4 > v5 || !v5 )
  {
    v10 = v5 + 1024;
    if ( v5 + 1024 >= v5 )
    {
      v11 = v5 + 1032;
      if ( v5 + 1032 < v5 + 1024 )
      {
        v12 = 0;
        v11 = -1;
      }
      else
      {
        v12 = HeapAlloc(LdapHeap, 8u, v11);
      }
      v13 = g_fTracingOn;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      {
        LDAPClientPrint(
          8,
          "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
          v11,
          (_DWORD)v12,
          1919238732);
        v13 = g_fTracingOn;
      }
      v14 = LdapAllocatedHeap;
      if ( v12 )
      {
        *v12 = 1919238732;
        v12[1] = v10;
        v12 += 2;
        v14 += v10;
        LdapAllocatedHeap = v14;
      }
      if ( v13 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
          v10,
          (_DWORD)v12,
          1919238732,
          v14);
      if ( !v12 )
        return 90;
      v15 = (const void *)*((_QWORD *)this + 2);
      if ( v15 )
      {
        memcpy_0(v12, v15, *((unsigned int *)this + 2));
        ldapFree(*((_QWORD *)this + 2), 1919238732);
      }
      *((_QWORD *)this + 2) = v12;
      *((_DWORD *)this + 2) = v10;
      goto LABEL_6;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
    {
      LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n", v5, 1024);
      return 82;
    }
    return 82;
  }
LABEL_6:
  *(_BYTE *)((unsigned int)(*((_DWORD *)this + 1))++ + *((_QWORD *)this + 2)) = a2;
  v6 = *((unsigned int *)this + 8);
  if ( (unsigned int)v6 >= 0x32 )
  {
    result = 2147942414LL;
  }
  else
  {
    v7 = *((_DWORD *)this + 209);
    v8 = *((_DWORD *)this + 210);
    *((_DWORD *)this + 4 * v6 + 9) = *((_DWORD *)this + 1);
    *((_DWORD *)this + 4 * *((unsigned int *)this + 8) + 10) = 5;
    *((_DWORD *)this + 4 * *((unsigned int *)this + 8) + 11) = v8;
    *((_DWORD *)this + 4 * (unsigned int)(*((_DWORD *)this + 8))++ + 12) = v7;
    result = 0;
  }
  *((_DWORD *)this + 1) += 5;
  *(_DWORD *)this = *((_DWORD *)this + 1);
  return result;
}

```

## disassembly

```asm
0x180011c80  mov     [rsp+arg_18], rbx
0x180011c85  push    rdi
0x180011c86  sub     rsp, 30h
0x180011c8a  mov     eax, [rcx+360h]
0x180011c90  mov     edi, edx
0x180011c92  mov     rbx, rcx
0x180011c95  test    eax, eax
0x180011c97  jnz     loc_180011E3D
0x180011c9d  mov     r8d, [rcx]
0x180011ca0  mov     [rsp+38h+arg_0], rbp
0x180011ca5  mov     [rsp+38h+arg_8], rsi
0x180011caa  lea     eax, [r8+6]
0x180011cae  cmp     eax, r8d
0x180011cb1  jb      loc_180011D48
0x180011cb7  mov     r8d, [rcx+8]
0x180011cbb  cmp     eax, r8d
0x180011cbe  ja      loc_180011D5C
0x180011cc4  test    r8d, r8d
0x180011cc7  jz      loc_180011D5C
0x180011ccd  mov     ecx, [rbx+4]
0x180011cd0  mov     rax, [rbx+10h]
0x180011cd4  mov     [rcx+rax], dil
0x180011cd8  inc     dword ptr [rbx+4]
0x180011cdb  mov     eax, [rbx+20h]
0x180011cde  mov     r8d, [rbx+4]
0x180011ce2  cmp     eax, 32h ; '2'
0x180011ce5  jnb     loc_180011F35
0x180011ceb  mov     edx, [rbx+344h]
0x180011cf1  add     rax, rax
0x180011cf4  mov     ecx, [rbx+348h]
0x180011cfa  mov     [rbx+rax*8+24h], r8d
0x180011cff  mov     eax, [rbx+20h]
0x180011d02  add     rax, rax
0x180011d05  mov     dword ptr [rbx+rax*8+28h], 5
0x180011d0d  mov     eax, [rbx+20h]
0x180011d10  add     rax, rax
0x180011d13  mov     [rbx+rax*8+2Ch], ecx
0x180011d17  mov     eax, [rbx+20h]
0x180011d1a  add     rax, 3
0x180011d1e  add     rax, rax
0x180011d21  mov     [rbx+rax*8], edx
0x180011d24  inc     dword ptr [rbx+20h]
0x180011d27  xor     eax, eax
0x180011d29  add     dword ptr [rbx+4], 5
0x180011d2d  mov     ecx, [rbx+4]
0x180011d30  mov     [rbx], ecx
0x180011d32  mov     rsi, [rsp+38h+arg_8]
0x180011d37  mov     rbp, [rsp+38h+arg_0]
0x180011d3c  mov     rbx, [rsp+38h+arg_18]
0x180011d41  add     rsp, 30h
0x180011d45  pop     rdi
0x180011d46  retn
0x180011d48  cmp     cs:g_fTracingOn, 0
0x180011d4f  jnz     loc_180011E4E
0x180011d55  mov     eax, 52h ; 'R'
0x180011d5a  jmp     short loc_180011D32
0x180011d5c  lea     ebp, [r8+400h]
0x180011d63  cmp     ebp, r8d
0x180011d66  jb      loc_180011E88
0x180011d6c  mov     [rsp+38h+arg_10], r14
0x180011d71  lea     r14d, [rbp+8]
0x180011d75  cmp     r14d, ebp
0x180011d78  jb      short loc_180011DED
0x180011d7a  mov     rcx, cs:LdapHeap; hHeap
0x180011d81  mov     edx, 8; dwFlags
0x180011d86  mov     r8d, r14d; dwBytes
0x180011d89  call    cs:__imp_HeapAlloc
0x180011d90  nop     dword ptr [rax+rax+00h]
0x180011d95  mov     rsi, rax
0x180011d98  mov     ecx, cs:g_fTracingOn
0x180011d9e  test    ecx, ecx
0x180011da0  jnz     short loc_180011E01
0x180011da2  mov     r14, [rsp+38h+arg_10]
0x180011da7  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180011dad  test    rsi, rsi
0x180011db0  jz      short loc_180011DC7
0x180011db2  mov     dword ptr [rsi], 7265424Ch
0x180011db8  mov     [rsi+4], ebp
0x180011dbb  add     rsi, 8
0x180011dbf  add     eax, ebp
0x180011dc1  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180011dc7  test    ecx, ecx
0x180011dc9  jnz     loc_180011ED4
0x180011dcf  test    rsi, rsi
0x180011dd2  jz      short loc_180011DF7
0x180011dd4  mov     rdx, [rbx+10h]; Src
0x180011dd8  test    rdx, rdx
0x180011ddb  jnz     loc_180011F16
0x180011de1  mov     [rbx+10h], rsi
0x180011de5  mov     [rbx+8], ebp
0x180011de8  jmp     loc_180011CCD
0x180011ded  xor     esi, esi
0x180011def  mov     r14d, 0FFFFFFFFh
0x180011df5  jmp     short loc_180011D98
0x180011df7  mov     eax, 5Ah ; 'Z'
0x180011dfc  jmp     loc_180011D32
0x180011e01  cmp     cs:g_fProviderEnabled, 0
0x180011e08  jz      short loc_180011DA2
0x180011e0a  test    byte ptr cs:g_ulTraceFlags, 8
0x180011e11  jz      short loc_180011DA2
0x180011e13  mov     r9, rsi
0x180011e16  mov     [rsp+38h+var_18], 7265424Ch
0x180011e1e  mov     r8d, r14d
0x180011e21  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x180011e28  mov     ecx, 8
0x180011e2d  call    LDAPClientPrint
0x180011e32  mov     ecx, cs:g_fTracingOn
0x180011e38  jmp     loc_180011DA2
0x180011e3d  mov     edi, eax
0x180011e3f  mov     dword ptr [rcx+360h], 0
0x180011e49  jmp     loc_180011C9D
0x180011e4e  cmp     cs:g_fProviderEnabled, 0
0x180011e55  jz      loc_180011D55
0x180011e5b  test    cs:g_ulTraceFlags, 10000000h
0x180011e66  jz      loc_180011D55
0x180011e6c  mov     r9d, 6
0x180011e72  lea     rdx, aHrensurebuffer; "HrEnsureBuffer: integer overflow. DataL"...
0x180011e79  mov     ecx, 10000000h
0x180011e7e  call    LDAPClientPrint
0x180011e83  jmp     loc_180011D55
0x180011e88  cmp     cs:g_fTracingOn, 0
0x180011e8f  jz      loc_180011D55
0x180011e95  cmp     cs:g_fProviderEnabled, 0
0x180011e9c  jz      loc_180011D55
0x180011ea2  test    cs:g_ulTraceFlags, 10000000h
0x180011ead  jz      loc_180011D55
0x180011eb3  mov     r9d, 400h
0x180011eb9  lea     rdx, aHrensurebuffer_0; "HrEnsureBuffer: integer overflow. DataM"...
0x180011ec0  mov     ecx, 10000000h
0x180011ec5  call    LDAPClientPrint
0x180011eca  mov     eax, 52h ; 'R'
0x180011ecf  jmp     loc_180011D32
0x180011ed4  cmp     cs:g_fProviderEnabled, 0
0x180011edb  jz      loc_180011DCF
0x180011ee1  test    byte ptr cs:g_ulTraceFlags, 8
0x180011ee8  jz      loc_180011DCF
0x180011eee  mov     [rsp+38h+var_10], eax
0x180011ef2  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x180011ef9  mov     r9, rsi
0x180011efc  mov     [rsp+38h+var_18], 7265424Ch
0x180011f04  mov     r8d, ebp
0x180011f07  mov     ecx, 8
0x180011f0c  call    LDAPClientPrint
0x180011f11  jmp     loc_180011DCF
0x180011f16  mov     r8d, [rbx+8]; Size
0x180011f1a  mov     rcx, rsi; void *
0x180011f1d  call    memcpy_0
0x180011f22  mov     rcx, [rbx+10h]
0x180011f26  mov     edx, 7265424Ch
0x180011f2b  call    ldapFree
0x180011f30  jmp     loc_180011DE1
0x180011f35  mov     eax, 8007000Eh
0x180011f3a  jmp     loc_180011D29
```

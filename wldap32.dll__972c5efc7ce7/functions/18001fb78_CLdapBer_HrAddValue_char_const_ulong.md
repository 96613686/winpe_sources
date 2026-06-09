# CLdapBer::HrAddValue(char const *,ulong)

- ea: `0x18001fb78`
- end: `0x18001ff8c`
- name: `?HrAddValue@CLdapBer@@QEAAKPEBDK@Z`
- size: `1044`
- prototype: `unsigned int __fastcall(CLdapBer *__hidden this, LPCCH lpMultiByteStr, unsigned int)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e0d0`
- `0x1800112b0`
- `0x180012ab0`
- `0x18001f96c`
- `0x18002bac0`
- `0x180039cd0`
- `0x1800400e4`
- `0x1800491d4`
- `0x18004a984`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x180011020`
- `0x18001fb78`
- `0x18001ffa0`
- `0x180020970`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fc8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fc8c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001fd01`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001fd99`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001fd01`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001fd99`

## string_xrefs

- `0x18001ff01`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
__int64 __fastcall CLdapBer::HrAddValue(CLdapBer *this, LPCCH lpMultiByteStr, char a3)
{
  const WCHAR *v5; // rsi
  int v6; // r12d
  const CHAR *v7; // rbp
  __int64 cbMultiByte; // rdi
  unsigned int v9; // r15d
  __int64 result; // rax
  WCHAR *v11; // rbx
  int v12; // r8d
  int v13; // eax
  HANDLE v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned int v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // r8
  char v21; // [rsp+80h] [rbp+8h] BYREF
  LPCWCH lpWideCharStr; // [rsp+88h] [rbp+10h]

  v21 = 0;
  lpWideCharStr = 0;
  v5 = 0;
  v6 = 0;
  if ( *((_DWORD *)this + 216) )
  {
    a3 = *((_DWORD *)this + 216);
    *((_DWORD *)this + 216) = 0;
  }
  v7 = &v21;
  if ( lpMultiByteStr )
    v7 = lpMultiByteStr;
  cbMultiByte = -1;
  do
    ++cbMultiByte;
  while ( v7[cbMultiByte] );
  if ( *((_DWORD *)this + 215) == 65001 && (_DWORD)cbMultiByte )
  {
    result = ToUnicodeWithAlloc(v7, 1);
    if ( (_DWORD)result )
      return result;
    v5 = lpWideCharStr;
    v6 = strlenW(lpWideCharStr, v19, v20);
    LODWORD(cbMultiByte) = WideCharToMultiByte(0xFDE9u, 0, v5, v6, 0, 0, 0, 0);
    if ( !(_DWORD)cbMultiByte )
    {
      ldapFree((__int64)v5, 1768838476);
      return 90;
    }
  }
  if ( (int)cbMultiByte + 6 >= (unsigned int)cbMultiByte )
  {
    v9 = CLdapBer::HrEnsureBuffer(this, cbMultiByte + 6, 0);
    if ( v9 )
    {
      if ( !v5 )
        return v9;
      v11 = (WCHAR *)(v5 - 4);
      if ( *((_DWORD *)v5 - 2) == 1684095564 )
        return v9;
      if ( *(_DWORD *)v11 == 1701987916 )
      {
        if ( !g_fTracingOn )
        {
LABEL_16:
          if ( *(_DWORD *)v11 != 1768838476 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1768838476, *(_DWORD *)v11);
          v12 = *((_DWORD *)v11 + 1);
          v13 = LdapAllocatedHeap - v12;
          LdapAllocatedHeap -= v12;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(
              8,
              "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
              v12,
              (_DWORD)v5,
              1768838476,
              v13);
          v14 = LdapHeap;
          *(_DWORD *)v11 = 1701987916;
          HeapFree(v14, 0, (LPVOID)(v5 - 4));
          return v9;
        }
        if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)v5);
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
          *((_DWORD *)v11 + 1),
          (_DWORD)v5 - 8,
          1768838476);
      goto LABEL_16;
    }
    *(_BYTE *)(*((unsigned int *)this + 1) + *((_QWORD *)this + 2)) = a3;
    v15 = *((_DWORD *)this + 1) + 1;
    *((_DWORD *)this + 1) = v15;
    if ( (unsigned int)cbMultiByte > 0x7F )
    {
      if ( (unsigned int)cbMultiByte > 0x7FFF )
      {
        if ( (unsigned int)cbMultiByte >= 0x7FFFFFFF )
          return (unsigned int)-2147024809;
        *(_BYTE *)(v15 + *((_QWORD *)this + 2)) = -124;
        *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE3(cbMultiByte);
        *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE2(cbMultiByte);
      }
      else
      {
        *(_BYTE *)(v15 + *((_QWORD *)this + 2)) = -126;
      }
      *(_BYTE *)((unsigned int)++*((_DWORD *)this + 1) + *((_QWORD *)this + 2)) = BYTE1(cbMultiByte);
      v16 = (unsigned int)++*((_DWORD *)this + 1);
    }
    else
    {
      v16 = v15;
    }
    *(_BYTE *)(v16 + *((_QWORD *)this + 2)) = cbMultiByte;
    v17 = (unsigned int)++*((_DWORD *)this + 1);
    if ( *((_DWORD *)this + 215) == 65001 && (_DWORD)cbMultiByte )
    {
      LODWORD(cbMultiByte) = WideCharToMultiByte(
                               0xFDE9u,
                               0,
                               v5,
                               v6,
                               (LPSTR)(*((_QWORD *)this + 2) + v17),
                               cbMultiByte,
                               0,
                               0);
      ldapFree((__int64)v5, 1768838476);
      v18 = 0;
      if ( !(_DWORD)cbMultiByte )
        v18 = 90;
    }
    else
    {
      memcpy_0((void *)(*((_QWORD *)this + 2) + (unsigned int)v17), v7, (unsigned int)cbMultiByte);
      v18 = 0;
    }
    *((_DWORD *)this + 1) += cbMultiByte;
    *(_DWORD *)this = *((_DWORD *)this + 1);
    return v18;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
    LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbValue 0x%x\n", cbMultiByte);
  return 82;
}

```

## disassembly

```asm
0x18001fb78  mov     rax, rsp
0x18001fb7b  mov     [rax+18h], rbx
0x18001fb7f  push    rbp
0x18001fb80  push    rsi
0x18001fb81  push    rdi
0x18001fb82  push    r12
0x18001fb84  push    r13
0x18001fb86  push    r14
0x18001fb88  push    r15
0x18001fb8a  sub     rsp, 40h
0x18001fb8e  xor     r13d, r13d
0x18001fb91  mov     r14d, r8d
0x18001fb94  mov     [rax+8], r13b
0x18001fb98  mov     rbx, rcx
0x18001fb9b  mov     [rax+10h], r13
0x18001fb9f  mov     esi, r13d
0x18001fba2  mov     eax, [rcx+360h]
0x18001fba8  mov     r12d, r13d
0x18001fbab  test    eax, eax
0x18001fbad  jnz     loc_18001FE8F
0x18001fbb3  test    rdx, rdx
0x18001fbb6  lea     rbp, [rsp+78h+arg_0]
0x18001fbbe  cmovnz  rbp, rdx
0x18001fbc2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001fbc6  inc     rdi
0x18001fbc9  cmp     [rdi+rbp], r13b
0x18001fbcd  jnz     short loc_18001FBC6
0x18001fbcf  cmp     dword ptr [rcx+35Ch], 0FDE9h
0x18001fbd9  mov     r15d, 696E554Ch
0x18001fbdf  jz      loc_18001FD38
0x18001fbe5  lea     edx, [rdi+6]; unsigned int
0x18001fbe8  cmp     edx, edi
0x18001fbea  jb      loc_18001FE9E
0x18001fbf0  xor     r8d, r8d; int
0x18001fbf3  mov     rcx, rbx; this
0x18001fbf6  call    ?HrEnsureBuffer@CLdapBer@@AEAAKKH@Z; CLdapBer::HrEnsureBuffer(ulong,int)
0x18001fbfb  mov     r15d, eax
0x18001fbfe  test    eax, eax
0x18001fc00  jz      loc_18001FC9D
0x18001fc06  test    rsi, rsi
0x18001fc09  jnz     short loc_18001FC27
0x18001fc0b  mov     eax, r15d
0x18001fc0e  mov     rbx, [rsp+78h+arg_10]
0x18001fc16  add     rsp, 40h
0x18001fc1a  pop     r15
0x18001fc1c  pop     r14
0x18001fc1e  pop     r13
0x18001fc20  pop     r12
0x18001fc22  pop     rdi
0x18001fc23  pop     rsi
0x18001fc24  pop     rbp
0x18001fc25  retn
0x18001fc27  lea     rbx, [rsi-8]
0x18001fc2b  cmp     dword ptr [rbx], 6461424Ch
0x18001fc31  jz      short loc_18001FC0B
0x18001fc33  mov     ebp, 6572464Ch
0x18001fc38  mov     edi, 8
0x18001fc3d  cmp     [rbx], ebp
0x18001fc3f  jz      loc_18001FED7
0x18001fc45  cmp     cs:g_fTracingOn, r13d
0x18001fc4c  jnz     loc_18001FF14
0x18001fc52  cmp     dword ptr [rbx], 696E554Ch
0x18001fc58  jnz     loc_18001FE4C
0x18001fc5e  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001fc64  mov     r8d, [rbx+4]
0x18001fc68  sub     eax, r8d
0x18001fc6b  cmp     cs:g_fTracingOn, r13d
0x18001fc72  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001fc78  jnz     loc_18001FF50
0x18001fc7e  mov     rcx, cs:LdapHeap; hHeap
0x18001fc85  mov     r8, rbx; lpMem
0x18001fc88  xor     edx, edx; dwFlags
0x18001fc8a  mov     [rbx], ebp
0x18001fc8c  call    cs:__imp_HeapFree
0x18001fc93  nop     dword ptr [rax+rax+00h]
0x18001fc98  jmp     loc_18001FC0B
0x18001fc9d  mov     ecx, [rbx+4]
0x18001fca0  mov     rax, [rbx+10h]
0x18001fca4  mov     [rcx+rax], r14b
0x18001fca8  mov     eax, [rbx+4]
0x18001fcab  inc     eax
0x18001fcad  mov     [rbx+4], eax
0x18001fcb0  cmp     edi, 7Fh
0x18001fcb3  ja      loc_18001FDC2
0x18001fcb9  mov     ecx, eax
0x18001fcbb  mov     rax, [rbx+10h]
0x18001fcbf  mov     [rcx+rax], dil
0x18001fcc3  mov     ecx, 0FDE9h; CodePage
0x18001fcc8  inc     dword ptr [rbx+4]
0x18001fccb  mov     eax, [rbx+4]
0x18001fcce  cmp     [rbx+35Ch], ecx
0x18001fcd4  jnz     loc_18001FDF1
0x18001fcda  test    edi, edi
0x18001fcdc  jz      loc_18001FDF1
0x18001fce2  add     rax, [rbx+10h]
0x18001fce6  mov     r9d, r12d; cchWideChar
0x18001fce9  mov     [rsp+78h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18001fcee  mov     r8, rsi; lpWideCharStr
0x18001fcf1  mov     [rsp+78h+lpDefaultChar], r13; lpDefaultChar
0x18001fcf6  xor     edx, edx; dwFlags
0x18001fcf8  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x18001fcfc  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x18001fd01  call    cs:__imp_WideCharToMultiByte
0x18001fd08  nop     dword ptr [rax+rax+00h]
0x18001fd0d  mov     edx, 696E554Ch
0x18001fd12  mov     rcx, rsi
0x18001fd15  mov     edi, eax
0x18001fd17  call    ldapFree
0x18001fd1c  test    edi, edi
0x18001fd1e  mov     ecx, r13d
0x18001fd21  mov     eax, 5Ah ; 'Z'
0x18001fd26  cmovz   ecx, eax
0x18001fd29  add     [rbx+4], edi
0x18001fd2c  mov     eax, [rbx+4]
0x18001fd2f  mov     [rbx], eax
0x18001fd31  mov     eax, ecx
0x18001fd33  jmp     loc_18001FC0E
0x18001fd38  test    edi, edi
0x18001fd3a  jz      loc_18001FBE5
0x18001fd40  mov     r9d, r15d
0x18001fd43  mov     dword ptr [rsp+78h+lpMultiByteStr], 1; int
0x18001fd4b  lea     r8, [rsp+78h+lpWideCharStr]
0x18001fd53  mov     edx, edi
0x18001fd55  mov     rcx, rbp; lpMultiByteStr
0x18001fd58  call    ToUnicodeWithAlloc
0x18001fd5d  test    eax, eax
0x18001fd5f  jnz     loc_18001FC0E
0x18001fd65  mov     rsi, [rsp+78h+lpWideCharStr]
0x18001fd6d  mov     rcx, rsi
0x18001fd70  call    strlenW
0x18001fd75  mov     [rsp+78h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18001fd7a  mov     r9d, eax; cchWideChar
0x18001fd7d  mov     [rsp+78h+lpDefaultChar], r13; lpDefaultChar
0x18001fd82  mov     r8, rsi; lpWideCharStr
0x18001fd85  mov     [rsp+78h+cbMultiByte], r13d; cbMultiByte
0x18001fd8a  xor     edx, edx; dwFlags
0x18001fd8c  mov     ecx, 0FDE9h; CodePage
0x18001fd91  mov     [rsp+78h+lpMultiByteStr], r13; lpMultiByteStr
0x18001fd96  mov     r12d, eax
0x18001fd99  call    cs:__imp_WideCharToMultiByte
0x18001fda0  nop     dword ptr [rax+rax+00h]
0x18001fda5  mov     edi, eax
0x18001fda7  test    eax, eax
0x18001fda9  jnz     loc_18001FBE5
0x18001fdaf  mov     edx, r15d
0x18001fdb2  mov     rcx, rsi
0x18001fdb5  call    ldapFree
0x18001fdba  lea     eax, [rdi+5Ah]
0x18001fdbd  jmp     loc_18001FC0E
0x18001fdc2  cmp     edi, 7FFFh
0x18001fdc8  ja      short loc_18001FE0A
0x18001fdca  mov     ecx, eax
0x18001fdcc  mov     rax, [rbx+10h]
0x18001fdd0  mov     byte ptr [rcx+rax], 82h
0x18001fdd4  inc     dword ptr [rbx+4]
0x18001fdd7  mov     ecx, edi
0x18001fdd9  mov     edx, [rbx+4]
0x18001fddc  mov     rax, [rbx+10h]
0x18001fde0  shr     ecx, 8
0x18001fde3  mov     [rdx+rax], cl
0x18001fde6  inc     dword ptr [rbx+4]
0x18001fde9  mov     ecx, [rbx+4]
0x18001fdec  jmp     loc_18001FCBB
0x18001fdf1  mov     ecx, eax
0x18001fdf3  mov     rdx, rbp; Src
0x18001fdf6  add     rcx, [rbx+10h]; void *
0x18001fdfa  mov     r8d, edi; Size
0x18001fdfd  call    memcpy_0
0x18001fe02  mov     ecx, r13d
0x18001fe05  jmp     loc_18001FD29
0x18001fe0a  cmp     edi, 7FFFFFFFh
0x18001fe10  jnb     short loc_18001FE42
0x18001fe12  mov     ecx, eax
0x18001fe14  mov     rax, [rbx+10h]
0x18001fe18  mov     byte ptr [rcx+rax], 84h
0x18001fe1c  mov     ecx, edi
0x18001fe1e  inc     dword ptr [rbx+4]
0x18001fe21  mov     edx, [rbx+4]
0x18001fe24  mov     rax, [rbx+10h]
0x18001fe28  shr     ecx, 18h
0x18001fe2b  mov     [rdx+rax], cl
0x18001fe2e  mov     ecx, edi
0x18001fe30  inc     dword ptr [rbx+4]
0x18001fe33  mov     edx, [rbx+4]
0x18001fe36  mov     rax, [rbx+10h]
0x18001fe3a  shr     ecx, 10h
0x18001fe3d  mov     [rdx+rax], cl
0x18001fe40  jmp     short loc_18001FDD4
0x18001fe42  mov     ecx, 80070057h
0x18001fe47  jmp     loc_18001FD31
0x18001fe4c  cmp     cs:g_fTracingOn, r13d
0x18001fe53  jz      loc_18001FC5E
0x18001fe59  cmp     cs:g_fProviderEnabled, r13d
0x18001fe60  jz      loc_18001FC5E
0x18001fe66  test    byte ptr cs:g_ulTraceFlags, dil
0x18001fe6d  jz      loc_18001FC5E
0x18001fe73  mov     r9d, [rbx]
0x18001fe76  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x18001fe7d  mov     r8d, 696E554Ch
0x18001fe83  mov     ecx, edi
0x18001fe85  call    LDAPClientPrint
0x18001fe8a  jmp     loc_18001FC5E
0x18001fe8f  mov     r14d, eax
0x18001fe92  mov     [rcx+360h], r13d
0x18001fe99  jmp     loc_18001FBB3
0x18001fe9e  cmp     cs:g_fTracingOn, r13d
0x18001fea5  jz      short loc_18001FECD
0x18001fea7  cmp     cs:g_fProviderEnabled, r13d
0x18001feae  jz      short loc_18001FECD
0x18001feb0  mov     ecx, 10000000h
0x18001feb5  test    cs:g_ulTraceFlags, rcx
0x18001febc  jz      short loc_18001FECD
0x18001febe  mov     r8d, edi
0x18001fec1  lea     rdx, aHraddvalueInte_0; "HrAddValue: integer overflow. cbValue 0"...
0x18001fec8  call    LDAPClientPrint
0x18001fecd  mov     eax, 52h ; 'R'
0x18001fed2  jmp     loc_18001FC0E
0x18001fed7  cmp     cs:g_fTracingOn, r13d
0x18001fede  jz      loc_18001FC52
0x18001fee4  cmp     cs:g_fProviderEnabled, r13d
0x18001feeb  jz      loc_18001FC45
0x18001fef1  test    byte ptr cs:g_ulTraceFlags, dil
0x18001fef8  jz      loc_18001FC45
0x18001fefe  mov     r8, rsi
0x18001ff01  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x18001ff08  mov     ecx, edi
0x18001ff0a  call    LDAPClientPrint
0x18001ff0f  jmp     loc_18001FC45
0x18001ff14  cmp     cs:g_fProviderEnabled, r13d
0x18001ff1b  jz      loc_18001FC52
0x18001ff21  test    byte ptr cs:g_ulTraceFlags, dil
0x18001ff28  jz      loc_18001FC52
0x18001ff2e  mov     r8d, [rbx+4]
0x18001ff32  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x18001ff39  mov     r9, rbx
0x18001ff3c  mov     dword ptr [rsp+78h+lpMultiByteStr], 696E554Ch
0x18001ff44  mov     ecx, edi
0x18001ff46  call    LDAPClientPrint
0x18001ff4b  jmp     loc_18001FC52
0x18001ff50  cmp     cs:g_fProviderEnabled, r13d
0x18001ff57  jz      loc_18001FC7E
0x18001ff5d  test    byte ptr cs:g_ulTraceFlags, dil
0x18001ff64  jz      loc_18001FC7E
0x18001ff6a  mov     [rsp+78h+cbMultiByte], eax
0x18001ff6e  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x18001ff75  mov     r9, rsi
0x18001ff78  mov     dword ptr [rsp+78h+lpMultiByteStr], 696E554Ch
0x18001ff80  mov     ecx, edi
0x18001ff82  call    LDAPClientPrint
0x18001ff87  jmp     loc_18001FC7E
```

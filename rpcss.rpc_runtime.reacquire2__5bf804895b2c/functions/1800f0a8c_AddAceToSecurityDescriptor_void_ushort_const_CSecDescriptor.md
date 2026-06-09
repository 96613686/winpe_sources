# AddAceToSecurityDescriptor(void *,ushort const *,CSecDescriptor * *)

- ea: `0x1800f0a8c`
- end: `0x1800f0d7d`
- name: `?AddAceToSecurityDescriptor@@YAJPEAXPEBGPEAPEAVCSecDescriptor@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, struct CSecDescriptor **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009c624`

## callees

- `0x180034260`
- `0x18006bdc4`
- `0x18008172c`
- `0x1800f0a8c`
- `0x180112d84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0bfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f0ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f0d47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f0ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f0d47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0b80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0c68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0c9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0b80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0c68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0c9d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800f0c4e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800f0cbb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800f0c4e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800f0cbb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f0bed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f0bed`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800f0ac2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800f0ac2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f0d2a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f0d5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f0d2a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f0d5d`

## string_xrefs

- `0x1800f0b36`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800f0b2f`: `AddAceToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall AddAceToSecurityDescriptor(void *a1, const unsigned __int16 *a2, struct CSecDescriptor **a3)
{
  WCHAR *v5; // rbp
  signed int v6; // eax
  signed int v7; // ebx
  int v8; // r8d
  __int64 v9; // rax
  __int64 v10; // rcx
  SIZE_T v11; // rdi
  unsigned __int16 *v12; // rax
  signed int v13; // eax
  signed int LastError; // eax
  DWORD SecurityDescriptorLength; // edi
  void *v16; // rax
  void *v17; // rsi
  struct CSecDescriptor *v18; // rax
  struct CSecDescriptor *v19; // rdi
  HANDLE v20; // rcx
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  hMem = 0;
  SecurityDescriptor = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(a1, 1u, 0x7Fu, (LPWSTR *)&hMem, 0) )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    do
      ++v9;
    while ( *((_WORD *)hMem + v9) );
    v11 = (unsigned int)(2 * (v10 + v9) + 2);
    v12 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v11);
    v5 = v12;
    if ( v12 )
    {
      v7 = StringCbPrintfW(v12, v11, L"%s%s", hMem, a2);
      if ( v7 >= 0 )
      {
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v5, 1u, &SecurityDescriptor, 0) )
        {
          SecurityDescriptorLength = GetSecurityDescriptorLength(SecurityDescriptor);
          v16 = HeapAlloc(g_hHeap, 0, SecurityDescriptorLength);
          v17 = v16;
          if ( v16 )
          {
            memcpy_0(v16, SecurityDescriptor, SecurityDescriptorLength);
            v18 = (struct CSecDescriptor *)HeapAlloc(g_hHeap, 0, 0x10u);
            v19 = v18;
            if ( v18 )
            {
              *((_DWORD *)v18 + 3) = 1;
              *((_DWORD *)v18 + 2) = GetSecurityDescriptorLength(v17);
              *(_QWORD *)v19 = v17;
              *a3 = v19;
            }
            else
            {
              v20 = g_hHeap;
              *a3 = 0;
              HeapFree(v20, 0, v17);
              v7 = -2147024882;
              if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v8 = 144;
                goto LABEL_8;
              }
            }
          }
          else
          {
            v7 = -2147024882;
          }
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            v8 = 117;
            goto LABEL_8;
          }
        }
      }
    }
    else
    {
      v13 = GetLastError();
      v7 = v13;
      if ( v13 > 0 )
        v7 = (unsigned __int16)v13 | 0x80070000;
    }
  }
  else
  {
    v5 = 0;
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v8 = 86;
LABEL_8:
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
        (unsigned int)"AddAceToSecurityDescriptor",
        v8,
        0,
        (__int64)L"%!HRESULT!",
        v7);
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    HeapFree(g_hHeap, 0, v5);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800f0a8c  mov     rax, rsp
0x1800f0a8f  mov     [rax+8], rbx
0x1800f0a93  push    rbp
0x1800f0a94  push    rsi
0x1800f0a95  push    rdi
0x1800f0a96  push    r14
0x1800f0a98  push    r15
0x1800f0a9a  sub     rsp, 30h
0x1800f0a9e  xor     r15d, r15d
0x1800f0aa1  lea     r9, [rax+18h]; StringSecurityDescriptor
0x1800f0aa5  mov     r14, r8
0x1800f0aa8  mov     [r8], r15
0x1800f0aab  mov     rbx, rdx
0x1800f0aae  mov     [rax+18h], r15
0x1800f0ab2  mov     [rax+20h], r15
0x1800f0ab6  lea     edx, [r15+1]; RequestedStringSDRevision
0x1800f0aba  mov     [rax-38h], r15
0x1800f0abe  lea     r8d, [r15+7Fh]; SecurityInformation
0x1800f0ac2  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800f0ac9  nop     dword ptr [rax+rax+00h]
0x1800f0ace  test    eax, eax
0x1800f0ad0  jnz     short loc_1800F0B47
0x1800f0ad2  mov     ebp, r15d
0x1800f0ad5  call    cs:__imp_GetLastError
0x1800f0adc  nop     dword ptr [rax+rax+00h]
0x1800f0ae1  mov     ebx, eax
0x1800f0ae3  test    eax, eax
0x1800f0ae5  jle     short loc_1800F0AF0
0x1800f0ae7  movzx   ebx, ax
0x1800f0aea  or      ebx, 80070000h
0x1800f0af0  mov     eax, cs:dword_1801574B8
0x1800f0af6  test    eax, eax
0x1800f0af8  jnz     short loc_1800F0B16
0x1800f0afa  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800f0b01  jz      loc_1800F0D20
0x1800f0b07  xor     ecx, ecx
0x1800f0b09  call    IsWppLevelEnabled
0x1800f0b0e  test    al, al
0x1800f0b10  jz      loc_1800F0D20
0x1800f0b16  mov     r8d, 56h ; 'V'
0x1800f0b1c  lea     rax, aHresult; "%!HRESULT!"
0x1800f0b23  mov     [rsp+58h+var_30], ebx
0x1800f0b27  xor     r9d, r9d
0x1800f0b2a  mov     [rsp+58h+var_38], rax
0x1800f0b2f  lea     rdx, aAddacetosecuri; "AddAceToSecurityDescriptor"
0x1800f0b36  lea     rcx, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x1800f0b3d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800f0b42  jmp     loc_1800F0D20
0x1800f0b47  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f0b4b  mov     rcx, rax
0x1800f0b4e  inc     rcx
0x1800f0b51  cmp     [rbx+rcx*2], r15w
0x1800f0b56  jnz     short loc_1800F0B4E
0x1800f0b58  mov     rdx, [rsp+58h+hMem]
0x1800f0b5d  inc     rax
0x1800f0b60  cmp     [rdx+rax*2], r15w
0x1800f0b65  jnz     short loc_1800F0B5D
0x1800f0b67  add     rax, rcx
0x1800f0b6a  xor     edx, edx; dwFlags
0x1800f0b6c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f0b73  lea     rax, ds:2[rax*2]
0x1800f0b7b  mov     r8d, eax; dwBytes
0x1800f0b7e  mov     edi, eax
0x1800f0b80  call    cs:__imp_HeapAlloc
0x1800f0b87  nop     dword ptr [rax+rax+00h]
0x1800f0b8c  mov     rbp, rax
0x1800f0b8f  test    rax, rax
0x1800f0b92  jnz     short loc_1800F0BB8
0x1800f0b94  call    cs:__imp_GetLastError
0x1800f0b9b  nop     dword ptr [rax+rax+00h]
0x1800f0ba0  mov     ebx, eax
0x1800f0ba2  test    eax, eax
0x1800f0ba4  jle     loc_1800F0D20
0x1800f0baa  movzx   ebx, ax
0x1800f0bad  or      ebx, 80070000h
0x1800f0bb3  jmp     loc_1800F0D20
0x1800f0bb8  mov     r9, [rsp+58h+hMem]
0x1800f0bbd  lea     r8, aSS_0; "%s%s"
0x1800f0bc4  mov     rdx, rdi; unsigned __int64
0x1800f0bc7  mov     [rsp+58h+var_38], rbx
0x1800f0bcc  mov     rcx, rbp; unsigned __int16 *
0x1800f0bcf  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f0bd4  mov     ebx, eax
0x1800f0bd6  test    eax, eax
0x1800f0bd8  js      loc_1800F0D20
0x1800f0bde  xor     r9d, r9d; SecurityDescriptorSize
0x1800f0be1  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1800f0be6  mov     rcx, rbp; StringSecurityDescriptor
0x1800f0be9  lea     edx, [r9+1]; StringSDRevision
0x1800f0bed  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f0bf4  nop     dword ptr [rax+rax+00h]
0x1800f0bf9  test    eax, eax
0x1800f0bfb  jnz     short loc_1800F0C49
0x1800f0bfd  call    cs:__imp_GetLastError
0x1800f0c04  nop     dword ptr [rax+rax+00h]
0x1800f0c09  mov     ebx, eax
0x1800f0c0b  test    eax, eax
0x1800f0c0d  jle     short loc_1800F0C18
0x1800f0c0f  movzx   ebx, ax
0x1800f0c12  or      ebx, 80070000h
0x1800f0c18  mov     eax, cs:dword_1801574B8
0x1800f0c1e  test    eax, eax
0x1800f0c20  jnz     short loc_1800F0C3E
0x1800f0c22  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800f0c29  jz      loc_1800F0D20
0x1800f0c2f  xor     ecx, ecx
0x1800f0c31  call    IsWppLevelEnabled
0x1800f0c36  test    al, al
0x1800f0c38  jz      loc_1800F0D20
0x1800f0c3e  mov     r8d, 75h ; 'u'
0x1800f0c44  jmp     loc_1800F0B1C
0x1800f0c49  mov     rcx, [rsp+58h+SecurityDescriptor]; pSecurityDescriptor
0x1800f0c4e  call    cs:__imp_GetSecurityDescriptorLength
0x1800f0c55  nop     dword ptr [rax+rax+00h]
0x1800f0c5a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f0c61  xor     edx, edx; dwFlags
0x1800f0c63  mov     r8d, eax; dwBytes
0x1800f0c66  mov     edi, eax
0x1800f0c68  call    cs:__imp_HeapAlloc
0x1800f0c6f  nop     dword ptr [rax+rax+00h]
0x1800f0c74  mov     rsi, rax
0x1800f0c77  test    rax, rax
0x1800f0c7a  jz      loc_1800F0D1B
0x1800f0c80  mov     rdx, [rsp+58h+SecurityDescriptor]; Src
0x1800f0c85  mov     r8d, edi; Size
0x1800f0c88  mov     rcx, rax; void *
0x1800f0c8b  call    memcpy_0
0x1800f0c90  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f0c97  xor     edx, edx; dwFlags
0x1800f0c99  lea     r8d, [rdx+10h]; dwBytes
0x1800f0c9d  call    cs:__imp_HeapAlloc
0x1800f0ca4  nop     dword ptr [rax+rax+00h]
0x1800f0ca9  mov     rdi, rax
0x1800f0cac  test    rax, rax
0x1800f0caf  jz      short loc_1800F0CD2
0x1800f0cb1  mov     rcx, rsi; pSecurityDescriptor
0x1800f0cb4  mov     dword ptr [rax+0Ch], 1
0x1800f0cbb  call    cs:__imp_GetSecurityDescriptorLength
0x1800f0cc2  nop     dword ptr [rax+rax+00h]
0x1800f0cc7  mov     [rdi+8], eax
0x1800f0cca  mov     [rdi], rsi
0x1800f0ccd  mov     [r14], rdi
0x1800f0cd0  jmp     short loc_1800F0D20
0x1800f0cd2  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f0cd9  mov     r8, rsi; lpMem
0x1800f0cdc  xor     edx, edx; dwFlags
0x1800f0cde  mov     [r14], r15
0x1800f0ce1  call    cs:__imp_HeapFree
0x1800f0ce8  nop     dword ptr [rax+rax+00h]
0x1800f0ced  mov     eax, cs:dword_1801574B8
0x1800f0cf3  mov     ebx, 8007000Eh
0x1800f0cf8  test    eax, eax
0x1800f0cfa  jnz     short loc_1800F0D10
0x1800f0cfc  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800f0d03  jz      short loc_1800F0D20
0x1800f0d05  xor     ecx, ecx
0x1800f0d07  call    IsWppLevelEnabled
0x1800f0d0c  test    al, al
0x1800f0d0e  jz      short loc_1800F0D20
0x1800f0d10  mov     r8d, 90h
0x1800f0d16  jmp     loc_1800F0B1C
0x1800f0d1b  mov     ebx, 8007000Eh
0x1800f0d20  mov     rcx, [rsp+58h+hMem]; hMem
0x1800f0d25  test    rcx, rcx
0x1800f0d28  jz      short loc_1800F0D36
0x1800f0d2a  call    cs:__imp_LocalFree
0x1800f0d31  nop     dword ptr [rax+rax+00h]
0x1800f0d36  test    rbp, rbp
0x1800f0d39  jz      short loc_1800F0D53
0x1800f0d3b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f0d42  mov     r8, rbp; lpMem
0x1800f0d45  xor     edx, edx; dwFlags
0x1800f0d47  call    cs:__imp_HeapFree
0x1800f0d4e  nop     dword ptr [rax+rax+00h]
0x1800f0d53  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1800f0d58  test    rcx, rcx
0x1800f0d5b  jz      short loc_1800F0D69
0x1800f0d5d  call    cs:__imp_LocalFree
0x1800f0d64  nop     dword ptr [rax+rax+00h]
0x1800f0d69  mov     eax, ebx
0x1800f0d6b  mov     rbx, [rsp+58h+arg_0]
0x1800f0d70  add     rsp, 30h
0x1800f0d74  pop     r15
0x1800f0d76  pop     r14
0x1800f0d78  pop     rdi
0x1800f0d79  pop     rsi
0x1800f0d7a  pop     rbp
0x1800f0d7b  retn
```

# UnpackEASLockoutData(uchar *,ulong,_USER_COUNT_ENTRY * *,ulong *,ulong *)

- ea: `0x18006c94c`
- end: `0x18006cbd9`
- name: `?UnpackEASLockoutData@@YAKPEAEKPEAPEAU_USER_COUNT_ENTRY@@PEAK2@Z`
- size: `653`
- prototype: `unsigned int __fastcall(unsigned __int8 *, unsigned int, struct _USER_COUNT_ENTRY **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006c3f0`

## callees

- `0x18006a608`
- `0x18006c94c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cbab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cbab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ca08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cb9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ca08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cb9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ca19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ca19`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006c9b5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006cb6e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006c9b5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006cb6e`
- `ADVAPI32!IsValidSid` at `0x18006c9c9`
- `ADVAPI32!IsValidSid` at `0x18006c9c9`

## string_xrefs

- `0x18006ca42`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006ca8b`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006cb0b`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x18006cad2`: `Lockout Metadata Invalid - Total Size < sizeof(SID)`
- `0x18006ca92`: `Lockout Metadata Invalid - Total Size < SIDLength`
- `0x18006ca49`: `Lockout Metadata Invalid - Invalid SID Entry`

## pseudocode

```c
__int64 __fastcall UnpackEASLockoutData(
        unsigned __int8 *a1,
        int a2,
        struct _USER_COUNT_ENTRY **a3,
        unsigned int *a4,
        unsigned int *a5)
{
  int v6; // edi
  unsigned __int8 *v7; // r14
  unsigned int v8; // ebp
  unsigned __int8 *v9; // rax
  int v10; // ebx
  unsigned int v11; // ebx
  char *v12; // r15
  DWORD LengthSid; // eax
  __int64 v14; // r12
  unsigned int v15; // eax
  unsigned __int64 v16; // rbx
  HANDLE ProcessHeap; // rax
  void *v18; // rbp
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  DWORD v21; // eax
  HANDLE v22; // rax
  int v24; // [rsp+20h] [rbp-78h]
  const wchar_t *v25; // [rsp+28h] [rbp-70h]
  __int128 v26; // [rsp+40h] [rbp-58h]

  *a3 = 0;
  *a4 = 0;
  v6 = a2;
  v7 = a1;
  *a5 = 0;
  v8 = 0;
  DWORD1(v26) = 0;
  if ( a1 && a2 && (v9 = a1, v10 = a2, a2 > 0) )
  {
    while ( (unsigned int)v10 >= 4 )
    {
      v11 = v10 - 4;
      if ( v11 < 0xC )
      {
        v25 = L"Lockout Metadata Invalid - Total Size < sizeof(SID)";
        v24 = 253;
        goto LABEL_17;
      }
      v12 = (char *)(v9 + 4);
      LengthSid = GetLengthSid(v9 + 4);
      v14 = LengthSid;
      if ( v11 < LengthSid )
      {
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          0,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
          264,
          L"Lockout Metadata Invalid - Total Size < SIDLength",
          &Class);
        v15 = 1;
        *a4 = 0;
        goto LABEL_10;
      }
      if ( !IsValidSid(v12) )
      {
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          0,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
          274,
          L"Lockout Metadata Invalid - Invalid SID Entry",
          &Class);
        v15 = 1;
        *a4 = 0;
        goto LABEL_10;
      }
      v9 = (unsigned __int8 *)&v12[v14];
      ++v8;
      v10 = v11 - v14;
      if ( v10 <= 0 )
        goto LABEL_9;
    }
    v25 = L"Lockout Metadata Invalid - Total Size < sizeof(DWORD)";
    v24 = 240;
LABEL_17:
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      0,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      v24,
      v25,
      &Class);
    v15 = 1;
    *a4 = 0;
  }
  else
  {
LABEL_9:
    v15 = v8 + 1;
    *a4 = v8;
    if ( v8 + 1 < v8 )
    {
LABEL_28:
      v19 = 534;
      goto LABEL_29;
    }
  }
LABEL_10:
  *a5 = v15;
  v16 = 16LL * v15;
  if ( v16 > 0xFFFFFFFF )
    goto LABEL_28;
  ProcessHeap = GetProcessHeap();
  v18 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v16);
  if ( !v18 )
  {
    v19 = 14;
LABEL_29:
    *a4 = 0;
    *a5 = 0;
    return v19;
  }
  if ( v7 && v6 && *a4 )
  {
    v20 = 0;
    while ( v6 > 0 )
    {
      if ( (unsigned int)v6 < 4 || v20 >= *a4 )
      {
        v19 = 1359;
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v18);
        goto LABEL_29;
      }
      LODWORD(v26) = *(_DWORD *)v7;
      *((_QWORD *)&v26 + 1) = v7 + 4;
      *((_OWORD *)v18 + v20) = v26;
      v21 = GetLengthSid(v7 + 4);
      v7 += v21 + 4;
      v6 += -4 - v21;
      ++v20;
    }
  }
  v19 = 0;
  *a3 = (struct _USER_COUNT_ENTRY *)v18;
  return v19;
}

```

## disassembly

```asm
0x18006c94c  mov     [rsp+arg_10], r8
0x18006c951  push    rbx
0x18006c952  push    rbp
0x18006c953  push    rsi
0x18006c954  push    rdi
0x18006c955  push    r12
0x18006c957  push    r13
0x18006c959  push    r14
0x18006c95b  push    r15
0x18006c95d  sub     rsp, 58h
0x18006c961  mov     r13, [rsp+98h+arg_20]
0x18006c969  xor     r15d, r15d
0x18006c96c  mov     [r8], r15
0x18006c96f  xorps   xmm0, xmm0
0x18006c972  mov     [r9], r15d
0x18006c975  mov     rsi, r9
0x18006c978  mov     edi, edx
0x18006c97a  mov     r14, rcx
0x18006c97d  mov     [r13+0], r15d
0x18006c981  mov     ebp, r15d
0x18006c984  movups  [rsp+98h+var_58], xmm0
0x18006c989  test    rcx, rcx
0x18006c98c  jz      short loc_18006C9E3
0x18006c98e  test    edx, edx
0x18006c990  jz      short loc_18006C9E3
0x18006c992  mov     rax, rcx
0x18006c995  mov     ebx, edx
0x18006c997  jle     short loc_18006C9E3
0x18006c999  cmp     ebx, 4
0x18006c99c  jb      loc_18006CAE8
0x18006c9a2  add     ebx, 0FFFFFFFCh
0x18006c9a5  cmp     ebx, 0Ch
0x18006c9a8  jb      loc_18006CAC6
0x18006c9ae  lea     r15, [rax+4]
0x18006c9b2  mov     rcx, r15; pSid
0x18006c9b5  call    cs:__imp_GetLengthSid
0x18006c9bb  mov     r12d, eax
0x18006c9be  cmp     ebx, eax
0x18006c9c0  jb      loc_18006CA7C
0x18006c9c6  mov     rcx, r15; pSid
0x18006c9c9  call    cs:__imp_IsValidSid
0x18006c9cf  test    eax, eax
0x18006c9d1  jz      short loc_18006CA33
0x18006c9d3  lea     rax, [r15+r12]
0x18006c9d7  inc     ebp
0x18006c9d9  xor     r15d, r15d
0x18006c9dc  sub     ebx, r12d
0x18006c9df  test    ebx, ebx
0x18006c9e1  jg      short loc_18006C999
0x18006c9e3  lea     eax, [rbp+1]
0x18006c9e6  mov     [rsi], ebp
0x18006c9e8  cmp     eax, ebp
0x18006c9ea  jb      loc_18006CBB3
0x18006c9f0  mov     ebx, eax
0x18006c9f2  mov     [r13+0], eax
0x18006c9f6  mov     eax, 0FFFFFFFFh
0x18006c9fb  shl     rbx, 4
0x18006c9ff  cmp     rbx, rax
0x18006ca02  ja      loc_18006CBB3
0x18006ca08  call    cs:__imp_GetProcessHeap
0x18006ca0e  mov     r8d, ebx; dwBytes
0x18006ca11  mov     edx, 8; dwFlags
0x18006ca16  mov     rcx, rax; hHeap
0x18006ca19  call    cs:__imp_HeapAlloc
0x18006ca1f  mov     rbp, rax
0x18006ca22  test    rax, rax
0x18006ca25  jnz     loc_18006CB30
0x18006ca2b  lea     ebx, [rax+0Eh]
0x18006ca2e  jmp     loc_18006CBB8
0x18006ca33  xor     r8d, r8d
0x18006ca36  lea     rax, Class
0x18006ca3d  mov     [rsp+98h+var_68], rax
0x18006ca42  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x18006ca49  lea     rax, aLockoutMetadat_1; "Lockout Metadata Invalid - Invalid SID "...
0x18006ca50  mov     [rsp+98h+var_70], rax
0x18006ca55  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006ca5c  lea     ebp, [r8+1]
0x18006ca60  mov     [rsp+98h+var_78], 112h
0x18006ca68  mov     ecx, ebp; unsigned int
0x18006ca6a  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006ca6f  mov     eax, ebp
0x18006ca71  mov     dword ptr [rsi], 0
0x18006ca77  jmp     loc_18006C9F0
0x18006ca7c  lea     rax, Class
0x18006ca83  xor     r8d, r8d
0x18006ca86  mov     [rsp+98h+var_68], rax
0x18006ca8b  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x18006ca92  lea     rax, aLockoutMetadat; "Lockout Metadata Invalid - Total Size <"...
0x18006ca99  mov     [rsp+98h+var_70], rax
0x18006ca9e  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006caa5  lea     ecx, [r8+1]; unsigned int
0x18006caa9  mov     [rsp+98h+var_78], 108h
0x18006cab1  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006cab6  mov     eax, 1
0x18006cabb  mov     dword ptr [rsi], 0
0x18006cac1  jmp     loc_18006C9F0
0x18006cac6  lea     rax, Class
0x18006cacd  mov     [rsp+98h+var_68], rax
0x18006cad2  lea     rax, aLockoutMetadat_0; "Lockout Metadata Invalid - Total Size <"...
0x18006cad9  mov     [rsp+98h+var_70], rax
0x18006cade  mov     [rsp+98h+var_78], 0FDh
0x18006cae6  jmp     short loc_18006CB08
0x18006cae8  lea     rax, Class
0x18006caef  mov     [rsp+98h+var_68], rax
0x18006caf4  lea     rax, aLockoutMetadat_2; "Lockout Metadata Invalid - Total Size <"...
0x18006cafb  mov     [rsp+98h+var_70], rax
0x18006cb00  mov     [rsp+98h+var_78], 0F0h
0x18006cb08  xor     r8d, r8d
0x18006cb0b  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x18006cb12  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006cb19  lea     r12d, [r8+1]
0x18006cb1d  mov     ecx, r12d; unsigned int
0x18006cb20  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006cb25  mov     eax, r12d
0x18006cb28  mov     [rsi], r15d
0x18006cb2b  jmp     loc_18006C9F0
0x18006cb30  test    r14, r14
0x18006cb33  jz      short loc_18006CB89
0x18006cb35  test    edi, edi
0x18006cb37  jz      short loc_18006CB89
0x18006cb39  cmp     dword ptr [rsi], 0
0x18006cb3c  jz      short loc_18006CB89
0x18006cb3e  xor     ebx, ebx
0x18006cb40  jmp     short loc_18006CB85
0x18006cb42  cmp     edi, 4
0x18006cb45  jb      short loc_18006CB98
0x18006cb47  lea     r15, [r14+4]
0x18006cb4b  mov     eax, [r14]
0x18006cb4e  mov     qword ptr [rsp+98h+var_58+8], r15
0x18006cb53  mov     dword ptr [rsp+98h+var_58], eax
0x18006cb57  cmp     ebx, [rsi]
0x18006cb59  jnb     short loc_18006CB98
0x18006cb5b  movups  xmm0, [rsp+98h+var_58]
0x18006cb60  mov     eax, ebx
0x18006cb62  mov     rcx, r15; pSid
0x18006cb65  add     rax, rax
0x18006cb68  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x18006cb6e  call    cs:__imp_GetLengthSid
0x18006cb74  mov     ecx, 0FFFFFFFCh
0x18006cb79  mov     r14d, eax
0x18006cb7c  sub     ecx, eax
0x18006cb7e  add     r14, r15
0x18006cb81  add     edi, ecx
0x18006cb83  inc     ebx
0x18006cb85  test    edi, edi
0x18006cb87  jg      short loc_18006CB42
0x18006cb89  mov     rax, [rsp+98h+arg_10]
0x18006cb91  xor     ebx, ebx
0x18006cb93  mov     [rax], rbp
0x18006cb96  jmp     short loc_18006CBC6
0x18006cb98  mov     ebx, 54Fh
0x18006cb9d  call    cs:__imp_GetProcessHeap
0x18006cba3  mov     r8, rbp; lpMem
0x18006cba6  xor     edx, edx; dwFlags
0x18006cba8  mov     rcx, rax; hHeap
0x18006cbab  call    cs:__imp_HeapFree
0x18006cbb1  jmp     short loc_18006CBB8
0x18006cbb3  mov     ebx, 216h
0x18006cbb8  mov     dword ptr [rsi], 0
0x18006cbbe  mov     dword ptr [r13+0], 0
0x18006cbc6  mov     eax, ebx
0x18006cbc8  add     rsp, 58h
0x18006cbcc  pop     r15
0x18006cbce  pop     r14
0x18006cbd0  pop     r13
0x18006cbd2  pop     r12
0x18006cbd4  pop     rdi
0x18006cbd5  pop     rsi
0x18006cbd6  pop     rbp
0x18006cbd7  pop     rbx
0x18006cbd8  retn
```

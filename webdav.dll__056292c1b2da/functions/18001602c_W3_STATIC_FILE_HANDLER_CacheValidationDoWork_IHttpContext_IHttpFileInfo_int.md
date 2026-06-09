# W3_STATIC_FILE_HANDLER::CacheValidationDoWork(IHttpContext *,IHttpFileInfo *,int *)

- ea: `0x18001602c`
- end: `0x18001637b`
- name: `?CacheValidationDoWork@W3_STATIC_FILE_HANDLER@@SAJPEAVIHttpContext@@PEAVIHttpFileInfo@@PEAH@Z`
- size: `847`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IHttpFileInfo *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003860`
- `0x180016708`

## callees

- `0x18001602c`
- `0x180016384`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016276`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800161dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800161dd`
- `iisutil!StringTimeToFileTime` at `0x1800161aa`
- `iisutil!StringTimeToFileTime` at `0x18001621b`
- `iisutil!StringTimeToFileTime` at `0x1800161aa`
- `iisutil!StringTimeToFileTime` at `0x18001621b`

## pseudocode

```c
__int64 __fastcall W3_STATIC_FILE_HANDLER::CacheValidationDoWork(
        struct IHttpContext *a1,
        struct IHttpFileInfo *a2,
        int *a3)
{
  __int64 v6; // rdi
  __int64 v7; // r14
  int v8; // r13d
  const char *v9; // rbx
  __int64 v10; // rax
  int v11; // r12d
  const char *v12; // rax
  const char *v13; // rax
  __int64 v14; // rax
  const char *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  const char *v18; // r8
  __int64 v19; // rdx
  signed int LastError; // eax
  unsigned int v21; // esi
  __int64 v22; // rcx
  void (__fastcall *v23)(__int64, __int64, const char *, _QWORD, unsigned int, _QWORD, _DWORD); // rax
  __int64 v24; // rax
  unsigned int v26; // [rsp+20h] [rbp-30h]
  union _LARGE_INTEGER v27[2]; // [rsp+40h] [rbp-10h] BYREF
  char *v28; // [rsp+90h] [rbp+40h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp+58h] BYREF

  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v8 = 0;
  v9 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 29);
  if ( !v9
    || ((v10 = (*(__int64 (__fastcall **)(struct IHttpFileInfo *, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0),
         *(_BYTE *)v10 != 87)
     || *(_BYTE *)(v10 + 1) != 47)
    && (unsigned int)FindInETagList((const char *)v10, v9, 0) )
  {
    v28 = (char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 31);
    v11 = 1;
    if ( v28 )
    {
      v12 = (const char *)(*(__int64 (__fastcall **)(struct IHttpFileInfo *, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0);
      if ( (unsigned int)FindInETagList(v12, v28, 1) )
        v11 = 0;
      else
        v8 = 1;
    }
    LODWORD(v28) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) + 36);
    v13 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 30);
    if ( v8 || !v13 )
    {
      if ( v11 )
        goto LABEL_15;
    }
    else
    {
      v27[0].QuadPart = 0;
      if ( !StringTimeToFileTime(v13, v27) )
        goto LABEL_19;
      v14 = *(_QWORD *)a2;
      SystemTimeAsFileTime = 0;
      (*(void (__fastcall **)(struct IHttpFileInfo *, struct _FILETIME *))(v14 + 104))(a2, &SystemTimeAsFileTime);
      if ( *(_QWORD *)&SystemTimeAsFileTime > v27[0].QuadPart
        || (GetSystemTimeAsFileTime(&SystemTimeAsFileTime), *(_QWORD *)&SystemTimeAsFileTime < v27[0].QuadPart) )
      {
LABEL_15:
        v15 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 33);
        if ( !v15 )
          goto LABEL_29;
        v28 = 0;
        if ( StringTimeToFileTime(v15, (union _LARGE_INTEGER *)&v28) )
        {
          v16 = *(_QWORD *)a2;
          SystemTimeAsFileTime = 0;
          (*(void (__fastcall **)(struct IHttpFileInfo *, struct _FILETIME *))(v16 + 104))(a2, &SystemTimeAsFileTime);
          if ( *(_QWORD *)&SystemTimeAsFileTime > (__int64)v28 )
          {
            v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
            v18 = "Precondition Failed";
            v19 = 412;
            v26 = 0;
LABEL_22:
            *(_WORD *)(v17 + 536) = 0;
            v22 = v6;
            v23 = *(void (__fastcall **)(__int64, __int64, const char *, _QWORD, unsigned int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL);
            goto LABEL_23;
          }
LABEL_29:
          *a3 = 0;
          return 0;
        }
LABEL_19:
        LastError = GetLastError();
        v21 = LastError;
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v18 = "Bad Request";
        v19 = 400;
        v26 = v21;
        goto LABEL_22;
      }
    }
    v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    v22 = v6;
    v26 = 0;
    *(_QWORD *)(v24 + 272) = 0;
    *(_WORD *)(v24 + 264) = 0;
    v23 = *(void (__fastcall **)(__int64, __int64, const char *, _QWORD, unsigned int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL);
    if ( (unsigned int)((_DWORD)v28 - 4) <= 1 )
    {
      v23(v6, 304, "Not Modified", 0, 0, 0, 0);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 48LL))(v6, 19);
      goto LABEL_24;
    }
    v19 = 412;
    v18 = "Precondition Failed";
LABEL_23:
    v23(v22, v19, v18, 0, v26, 0, 0);
LABEL_24:
    *a3 = 1;
    return 0;
  }
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) + 536) = 0;
  (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL))(
    v6,
    412,
    "Precondition Failed",
    0,
    0,
    0,
    0);
  *a3 = 1;
  return 0;
}

```

## disassembly

```asm
0x18001602c  mov     [rsp-38h+arg_8], rbx
0x180016031  push    rbp
0x180016032  push    rsi
0x180016033  push    rdi
0x180016034  push    r12
0x180016036  push    r13
0x180016038  push    r14
0x18001603a  push    r15
0x18001603c  mov     rbp, rsp
0x18001603f  sub     rsp, 50h
0x180016043  mov     rax, [rcx]
0x180016046  mov     r15, r8
0x180016049  mov     rsi, rdx
0x18001604c  mov     rbx, rcx
0x18001604f  mov     rax, [rax+20h]
0x180016053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016058  mov     r9, [rbx]
0x18001605b  mov     rdi, rax
0x18001605e  mov     rcx, rbx
0x180016061  mov     rax, [r9+18h]
0x180016065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001606a  mov     r14, rax
0x18001606d  xor     r8d, r8d
0x180016070  mov     rcx, [rax]
0x180016073  lea     edx, [r8+1Dh]
0x180016077  mov     rax, [rcx+10h]
0x18001607b  mov     rcx, r14
0x18001607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016083  xor     r13d, r13d
0x180016086  mov     rbx, rax
0x180016089  test    rax, rax
0x18001608c  jz      short loc_18001610C
0x18001608e  mov     rcx, [rsi]
0x180016091  xor     edx, edx
0x180016093  mov     rax, [rcx+60h]
0x180016097  mov     rcx, rsi
0x18001609a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001609f  cmp     byte ptr [rax], 57h ; 'W'
0x1800160a2  jnz     short loc_1800160AA
0x1800160a4  cmp     byte ptr [rax+1], 2Fh ; '/'
0x1800160a8  jz      short loc_1800160BC
0x1800160aa  xor     r8d, r8d; int
0x1800160ad  mov     rdx, rbx; char *
0x1800160b0  mov     rcx, rax; char *
0x1800160b3  call    ?FindInETagList@@YAHPEBD0H@Z; FindInETagList(char const *,char const *,int)
0x1800160b8  test    eax, eax
0x1800160ba  jnz     short loc_18001610C
0x1800160bc  mov     rax, [rdi]
0x1800160bf  mov     rcx, rdi
0x1800160c2  mov     rax, [rax+8]
0x1800160c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160cb  mov     [rsp+50h+var_20], r13d
0x1800160d0  lea     r8, aPreconditionFa; "Precondition Failed"
0x1800160d7  xor     r9d, r9d
0x1800160da  mov     [rsp+50h+var_28], r13
0x1800160df  mov     edx, 19Ch
0x1800160e4  mov     [rsp+50h+var_30], r13d
0x1800160e9  mov     [rax+218h], r13w
0x1800160f1  mov     rcx, rdi
0x1800160f4  mov     rax, [rdi]
0x1800160f7  mov     rax, [rax+18h]
0x1800160fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016100  mov     dword ptr [r15], 1
0x180016107  jmp     loc_180016361
0x18001610c  mov     rax, [r14]
0x18001610f  xor     r8d, r8d
0x180016112  mov     rcx, r14
0x180016115  mov     rax, [rax+10h]
0x180016119  lea     edx, [r8+1Fh]
0x18001611d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016122  mov     [rbp+arg_0], rax
0x180016126  mov     ebx, 1
0x18001612b  mov     r12d, ebx
0x18001612e  test    rax, rax
0x180016131  jz      short loc_18001615F
0x180016133  mov     rcx, [rsi]
0x180016136  xor     edx, edx
0x180016138  mov     rax, [rcx+60h]
0x18001613c  mov     rcx, rsi
0x18001613f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016144  mov     rdx, [rbp+arg_0]; char *
0x180016148  mov     rcx, rax; char *
0x18001614b  mov     r8d, ebx; int
0x18001614e  call    ?FindInETagList@@YAHPEBD0H@Z; FindInETagList(char const *,char const *,int)
0x180016153  test    eax, eax
0x180016155  jz      short loc_18001615C
0x180016157  xor     r12d, r12d
0x18001615a  jmp     short loc_18001615F
0x18001615c  mov     r13d, ebx
0x18001615f  mov     rax, [r14]
0x180016162  mov     rcx, r14
0x180016165  mov     rax, [rax+8]
0x180016169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001616e  xor     r8d, r8d
0x180016171  mov     rcx, r14
0x180016174  mov     eax, [rax+24h]
0x180016177  mov     dword ptr [rbp+arg_0], eax
0x18001617a  lea     edx, [r8+1Eh]
0x18001617e  mov     rax, [r14]
0x180016181  mov     rax, [rax+10h]
0x180016185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001618a  test    r13d, r13d
0x18001618d  jnz     loc_1800162D6
0x180016193  xor     r13d, r13d
0x180016196  test    rax, rax
0x180016199  jz      loc_1800162D9
0x18001619f  lea     rdx, [rbp+var_10]
0x1800161a3  mov     qword ptr [rbp+var_10], r13
0x1800161a7  mov     rcx, rax
0x1800161aa  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x1800161b0  test    eax, eax
0x1800161b2  jz      loc_180016276
0x1800161b8  mov     rax, [rsi]
0x1800161bb  lea     rdx, [rbp+SystemTimeAsFileTime]
0x1800161bf  mov     rcx, rsi
0x1800161c2  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800161c6  mov     rax, [rax+68h]
0x1800161ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161cf  mov     rax, qword ptr [rbp+var_10]
0x1800161d3  cmp     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800161d7  jg      short loc_1800161F1
0x1800161d9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800161dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800161e3  mov     rax, qword ptr [rbp+var_10]
0x1800161e7  cmp     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800161eb  jge     loc_1800162E2
0x1800161f1  mov     rax, [r14]
0x1800161f4  xor     r8d, r8d
0x1800161f7  mov     rcx, r14
0x1800161fa  mov     rax, [rax+10h]
0x1800161fe  lea     edx, [r8+21h]
0x180016202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016207  test    rax, rax
0x18001620a  jz      loc_18001635E
0x180016210  lea     rdx, [rbp+arg_0]
0x180016214  mov     [rbp+arg_0], r13
0x180016218  mov     rcx, rax
0x18001621b  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x180016221  test    eax, eax
0x180016223  jz      short loc_180016276
0x180016225  mov     rax, [rsi]
0x180016228  lea     rdx, [rbp+SystemTimeAsFileTime]
0x18001622c  mov     rcx, rsi
0x18001622f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x180016233  mov     rax, [rax+68h]
0x180016237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001623c  mov     rax, [rbp+arg_0]
0x180016240  cmp     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180016244  jle     loc_18001635E
0x18001624a  mov     rax, [rdi]
0x18001624d  mov     rcx, rdi
0x180016250  mov     rax, [rax+8]
0x180016254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016259  mov     [rsp+50h+var_20], r13d
0x18001625e  lea     r8, aPreconditionFa; "Precondition Failed"
0x180016265  mov     [rsp+50h+var_28], r13
0x18001626a  mov     edx, 19Ch
0x18001626f  mov     [rsp+50h+var_30], r13d
0x180016274  jmp     short loc_1800162B4
0x180016276  call    cs:__imp_GetLastError
0x18001627c  mov     esi, eax
0x18001627e  test    eax, eax
0x180016280  jle     short loc_18001628B
0x180016282  movzx   esi, ax
0x180016285  or      esi, 80070000h
0x18001628b  mov     rax, [rdi]
0x18001628e  mov     rcx, rdi
0x180016291  mov     rax, [rax+8]
0x180016295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001629a  mov     [rsp+50h+var_20], r13d
0x18001629f  lea     r8, aBadRequest; "Bad Request"
0x1800162a6  mov     [rsp+50h+var_28], r13
0x1800162ab  mov     edx, 190h
0x1800162b0  mov     [rsp+50h+var_30], esi
0x1800162b4  mov     [rax+218h], r13w
0x1800162bc  xor     r9d, r9d
0x1800162bf  mov     rax, [rdi]
0x1800162c2  mov     rcx, rdi
0x1800162c5  mov     rax, [rax+18h]
0x1800162c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ce  mov     [r15], ebx
0x1800162d1  jmp     loc_180016361
0x1800162d6  xor     r13d, r13d
0x1800162d9  test    r12d, r12d
0x1800162dc  jnz     loc_1800161F1
0x1800162e2  mov     rax, [rdi]
0x1800162e5  mov     rcx, rdi
0x1800162e8  mov     rax, [rax+8]
0x1800162ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162f1  mov     [rsp+50h+var_20], r13d
0x1800162f6  xor     r9d, r9d
0x1800162f9  mov     [rsp+50h+var_28], r13
0x1800162fe  mov     rcx, rdi
0x180016301  mov     [rsp+50h+var_30], r13d
0x180016306  mov     [rax+110h], r13
0x18001630d  mov     [rax+108h], r13w
0x180016315  mov     eax, dword ptr [rbp+arg_0]
0x180016318  add     eax, 0FFFFFFFCh
0x18001631b  cmp     eax, ebx
0x18001631d  mov     rax, [rdi]
0x180016320  mov     rax, [rax+18h]
0x180016324  jbe     short loc_180016334
0x180016326  mov     edx, 19Ch
0x18001632b  lea     r8, aPreconditionFa; "Precondition Failed"
0x180016332  jmp     short loc_1800162C9
0x180016334  lea     r8, aNotModified; "Not Modified"
0x18001633b  mov     edx, 130h
0x180016340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016345  mov     rax, [rdi]
0x180016348  mov     edx, 13h
0x18001634d  mov     rcx, rdi
0x180016350  mov     rax, [rax+30h]
0x180016354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016359  jmp     loc_1800162CE
0x18001635e  mov     [r15], r13d
0x180016361  mov     rbx, [rsp+50h+arg_8]
0x180016369  xor     eax, eax
0x18001636b  add     rsp, 50h
0x18001636f  pop     r15
0x180016371  pop     r14
0x180016373  pop     r13
0x180016375  pop     r12
0x180016377  pop     rdi
0x180016378  pop     rsi
0x180016379  pop     rbp
0x18001637a  retn
```

# CTempFileNameArray::_TryCreatingInPath(ushort const *,ushort const *,ushort const *,ushort *,uint)

- ea: `0x18001fe64`
- end: `0x1800200db`
- name: `?_TryCreatingInPath@CTempFileNameArray@@AEAAJPEBG00PEAGI@Z`
- size: `631`
- prototype: `__int64 __usercall@<rax>(CTempFileNameArray *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x18001f080`

## callees

- `0x180010c30`
- `0x18001fae8`
- `0x18001fe64`
- `0x18002024c`
- `0x1800350a0`
- `0x180036f50`
- `0x180046e24`
- `0x180046f04`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18001ffc8`
- `SHELL32!SHChangeNotify` at `0x18001ffc8`
- `SHLWAPI!PathFileExistsW` at `0x18001ff9e`
- `SHLWAPI!PathFileExistsW` at `0x18001ff9e`
- `SHLWAPI!StrCmpIW` at `0x18002003f`
- `SHLWAPI!StrCmpIW` at `0x180020055`
- `SHLWAPI!StrCmpIW` at `0x18002003f`
- `SHLWAPI!StrCmpIW` at `0x180020055`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020077`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020077`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ff8b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ff8b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001ffaf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001ffaf`
- `RPCRT4!UuidCreate` at `0x18001fedc`
- `RPCRT4!UuidCreate` at `0x18001fedc`
- `RPCRT4!RpcStringFreeW` at `0x18001ff5b`
- `RPCRT4!RpcStringFreeW` at `0x18001ff5b`
- `RPCRT4!UuidToStringW` at `0x18001fefb`
- `RPCRT4!UuidToStringW` at `0x18001fefb`

## pseudocode

```c
__int64 __fastcall CTempFileNameArray::_TryCreatingInPath(
        CTempFileNameArray *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v5; // rdi
  const unsigned __int16 *v6; // r13
  const unsigned __int16 *v7; // rsi
  const unsigned __int16 *v8; // r14
  int Error; // ebx
  int i; // r12d
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r8
  WCHAR *v15; // r13
  unsigned int v16; // r10d
  int *v17; // rax
  int v18; // esi
  int v19; // edi
  const WCHAR *ItemPtr; // r14
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  v5 = a5;
  v6 = a4;
  v7 = a3;
  v8 = a2;
  Error = -2147024816;
  for ( i = 1; i < 100; ++i )
  {
    if ( Error != -2147024816 )
      break;
    Uuid = 0;
    if ( !UuidCreate(&Uuid) )
    {
      StringUuid = 0;
      if ( !UuidToStringW(&Uuid, &StringUuid) )
      {
        v12 = -1;
        v13 = -1;
        do
          ++v13;
        while ( v6[v13] );
        do
          ++v12;
        while ( v7[v12] );
        v14 = 205 - v12;
        if ( v13 < 205 - v12 )
          v14 = v13;
        v15 = ConstructStringFromTemplate(L"%1_%2!.*s!.%3\\", StringUuid, v14, v6, StringUuid + 33);
        RpcStringFreeW(&StringUuid);
        if ( v15 )
        {
          StringCchCopyW(pszPath, 0x104u, v7);
          if ( PathCchAppend(pszPath, v16, v15) < 0 )
          {
            Error = -2147417803;
          }
          else if ( PathFileExistsW(pszPath) )
          {
            v17 = (int *)*((_QWORD *)this + 8);
            if ( v17 )
            {
              v18 = *v17;
              v19 = 0;
              if ( *v17 <= 0 )
              {
LABEL_24:
                v5 = a5;
              }
              else
              {
                while ( 1 )
                {
                  ItemPtr = (const WCHAR *)DSA_GetItemPtr(*((HDSA *)this + 8), v19);
                  if ( !StrCmpIW(a2, ItemPtr) && !StrCmpIW(pszPath, ItemPtr + 260) )
                    break;
                  if ( ++v19 >= v18 )
                  {
                    v8 = a2;
                    goto LABEL_24;
                  }
                }
                v5 = a5;
                v8 = a2;
                Error = StringCchCopyW(a5, 0x104u, pszPath);
              }
              v7 = a3;
            }
          }
          else if ( CreateDirectoryW(pszPath, 0) )
          {
            SHChangeNotify(8, 5u, pszPath, 0);
            Error = CTempFileNameArray::_AddDir(this, pszPath);
            if ( Error >= 0 )
            {
              Error = CTempFileNameArray::_AddRootDir(this, v8, pszPath);
              if ( Error >= 0 )
                StringCchCopyW(v5, 0x104u, pszPath);
            }
          }
          else
          {
            Error = ResultFromKnownLastError();
          }
          LocalFree(v15);
        }
        v6 = a4;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001fe64  push    rbp
0x18001fe66  push    rbx
0x18001fe67  push    rsi
0x18001fe68  push    rdi
0x18001fe69  push    r12
0x18001fe6b  push    r13
0x18001fe6d  push    r14
0x18001fe6f  push    r15
0x18001fe71  lea     rbp, [rsp-198h]
0x18001fe79  sub     rsp, 298h
0x18001fe80  mov     rax, cs:__security_cookie
0x18001fe87  xor     rax, rsp
0x18001fe8a  mov     [rbp+1D0h+var_50], rax
0x18001fe91  mov     rdi, [rbp+1D0h+arg_20]
0x18001fe98  mov     r13, r9
0x18001fe9b  mov     [rsp+2D0h+var_298], rdi
0x18001fea0  mov     rsi, r8
0x18001fea3  mov     [rsp+2D0h+var_288], r9
0x18001fea8  mov     r14, rdx
0x18001feab  mov     [rsp+2D0h+var_290], r8
0x18001feb0  mov     r15, rcx
0x18001feb3  mov     [rsp+2D0h+psz1], rdx
0x18001feb8  mov     ebx, 80070050h
0x18001febd  mov     r12d, 1
0x18001fec3  cmp     ebx, 80070050h
0x18001fec9  jnz     loc_18002008F
0x18001fecf  xorps   xmm0, xmm0
0x18001fed2  lea     rcx, [rsp+2D0h+Uuid]; Uuid
0x18001fed7  movups  xmmword ptr [rsp+2D0h+Uuid.Data1], xmm0
0x18001fedc  call    cs:__imp_UuidCreate
0x18001fee2  xor     edx, edx
0x18001fee4  test    eax, eax
0x18001fee6  jnz     loc_180020082
0x18001feec  mov     [rsp+2D0h+StringUuid], rdx
0x18001fef1  lea     rcx, [rsp+2D0h+Uuid]; Uuid
0x18001fef6  lea     rdx, [rsp+2D0h+StringUuid]; StringUuid
0x18001fefb  call    cs:__imp_UuidToStringW
0x18001ff01  xor     edx, edx
0x18001ff03  test    eax, eax
0x18001ff05  jnz     loc_180020082
0x18001ff0b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ff0f  mov     rax, rcx
0x18001ff12  inc     rax
0x18001ff15  cmp     [r13+rax*2+0], dx
0x18001ff1b  jnz     short loc_18001FF12
0x18001ff1d  inc     rcx
0x18001ff20  cmp     [rsi+rcx*2], dx
0x18001ff24  jnz     short loc_18001FF1D
0x18001ff26  mov     rdx, [rsp+2D0h+StringUuid]
0x18001ff2b  mov     r8d, 0CDh
0x18001ff31  sub     r8, rcx
0x18001ff34  mov     r9, r13
0x18001ff37  cmp     rax, r8
0x18001ff3a  lea     rcx, a12S3; "%1_%2!.*s!.%3\\"
0x18001ff41  cmovb   r8, rax
0x18001ff45  lea     rax, [rdx+42h]
0x18001ff49  mov     [rsp+2D0h+var_2B0], rax
0x18001ff4e  call    ?ConstructStringFromTemplate@@YAPEAGPEBXZZ; ConstructStringFromTemplate(void const *,...)
0x18001ff53  lea     rcx, [rsp+2D0h+StringUuid]; String
0x18001ff58  mov     r13, rax
0x18001ff5b  call    cs:__imp_RpcStringFreeW
0x18001ff61  test    r13, r13
0x18001ff64  jz      loc_18002007D
0x18001ff6a  mov     r10d, 104h
0x18001ff70  lea     rcx, [rsp+2D0h+pszPath]; unsigned __int16 *
0x18001ff75  mov     edx, r10d; unsigned __int64
0x18001ff78  mov     r8, rsi; unsigned __int16 *
0x18001ff7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ff80  mov     r8, r13; pszMore
0x18001ff83  lea     rcx, [rsp+2D0h+pszPath]; pszPath
0x18001ff88  mov     edx, r10d; cchPath
0x18001ff8b  call    cs:__imp_PathCchAppend
0x18001ff91  test    eax, eax
0x18001ff93  js      loc_1800200D4
0x18001ff99  lea     rcx, [rsp+2D0h+pszPath]; pszPath
0x18001ff9e  call    cs:__imp_PathFileExistsW
0x18001ffa4  test    eax, eax
0x18001ffa6  jnz     short loc_180020018
0x18001ffa8  xor     edx, edx; lpSecurityAttributes
0x18001ffaa  lea     rcx, [rsp+2D0h+pszPath]; lpPathName
0x18001ffaf  call    cs:__imp_CreateDirectoryW
0x18001ffb5  test    eax, eax
0x18001ffb7  jz      short loc_18002000F
0x18001ffb9  xor     r9d, r9d; dwItem2
0x18001ffbc  lea     r8, [rsp+2D0h+pszPath]; dwItem1
0x18001ffc1  lea     edx, [r9+5]; uFlags
0x18001ffc5  lea     ecx, [rdx+3]; wEventId
0x18001ffc8  call    cs:__imp_SHChangeNotify
0x18001ffce  lea     rdx, [rsp+2D0h+pszPath]; unsigned __int16 *
0x18001ffd3  mov     rcx, r15; this
0x18001ffd6  call    ?_AddDir@CTempFileNameArray@@AEAAJPEBG@Z; CTempFileNameArray::_AddDir(ushort const *)
0x18001ffdb  mov     ebx, eax
0x18001ffdd  test    eax, eax
0x18001ffdf  js      loc_180020074
0x18001ffe5  lea     r8, [rsp+2D0h+pszPath]; unsigned __int16 *
0x18001ffea  mov     rdx, r14; unsigned __int16 *
0x18001ffed  mov     rcx, r15; this
0x18001fff0  call    ?_AddRootDir@CTempFileNameArray@@AEAAJPEBG0@Z; CTempFileNameArray::_AddRootDir(ushort const *,ushort const *)
0x18001fff5  mov     ebx, eax
0x18001fff7  test    eax, eax
0x18001fff9  js      short loc_180020074
0x18001fffb  lea     r8, [rsp+2D0h+pszPath]; unsigned __int16 *
0x180020000  mov     edx, 104h; unsigned __int64
0x180020005  mov     rcx, rdi; unsigned __int16 *
0x180020008  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002000d  jmp     short loc_180020074
0x18002000f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180020014  mov     ebx, eax
0x180020016  jmp     short loc_180020074
0x180020018  mov     rax, [r15+40h]
0x18002001c  test    rax, rax
0x18002001f  jz      short loc_180020074
0x180020021  mov     esi, [rax]
0x180020023  xor     edi, edi
0x180020025  test    esi, esi
0x180020027  jle     short loc_18002006A
0x180020029  mov     rcx, [r15+40h]; hdsa
0x18002002d  mov     edx, edi; i
0x18002002f  call    DSA_GetItemPtr
0x180020034  mov     rcx, [rsp+2D0h+psz1]; psz1
0x180020039  mov     rdx, rax; psz2
0x18002003c  mov     r14, rax
0x18002003f  call    cs:__imp_StrCmpIW
0x180020045  test    eax, eax
0x180020047  jnz     short loc_18002005F
0x180020049  lea     rdx, [r14+208h]; psz2
0x180020050  lea     rcx, [rsp+2D0h+pszPath]; psz1
0x180020055  call    cs:__imp_StrCmpIW
0x18002005b  test    eax, eax
0x18002005d  jz      short loc_1800200B4
0x18002005f  inc     edi
0x180020061  cmp     edi, esi
0x180020063  jl      short loc_180020029
0x180020065  mov     r14, [rsp+2D0h+psz1]
0x18002006a  mov     rdi, [rsp+2D0h+var_298]
0x18002006f  mov     rsi, [rsp+2D0h+var_290]
0x180020074  mov     rcx, r13; hMem
0x180020077  call    cs:__imp_LocalFree
0x18002007d  mov     r13, [rsp+2D0h+var_288]
0x180020082  inc     r12d
0x180020085  cmp     r12d, 64h ; 'd'
0x180020089  jl      loc_18001FEC3
0x18002008f  mov     eax, ebx
0x180020091  mov     rcx, [rbp+1D0h+var_50]
0x180020098  xor     rcx, rsp; StackCookie
0x18002009b  call    __security_check_cookie
0x1800200a0  add     rsp, 298h
0x1800200a7  pop     r15
0x1800200a9  pop     r14
0x1800200ab  pop     r13
0x1800200ad  pop     r12
0x1800200af  pop     rdi
0x1800200b0  pop     rsi
0x1800200b1  pop     rbx
0x1800200b2  pop     rbp
0x1800200b3  retn
0x1800200b4  mov     rdi, [rsp+2D0h+var_298]
0x1800200b9  lea     r8, [rsp+2D0h+pszPath]; unsigned __int16 *
0x1800200be  mov     rcx, rdi; unsigned __int16 *
0x1800200c1  mov     edx, 104h; unsigned __int64
0x1800200c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800200cb  mov     r14, [rsp+2D0h+psz1]
0x1800200d0  mov     ebx, eax
0x1800200d2  jmp     short loc_18002006F
0x1800200d4  mov     ebx, 80010135h
0x1800200d9  jmp     short loc_180020074
```

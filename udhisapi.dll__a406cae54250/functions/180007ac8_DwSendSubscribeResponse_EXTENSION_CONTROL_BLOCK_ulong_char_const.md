# DwSendSubscribeResponse(_EXTENSION_CONTROL_BLOCK *,ulong,char const *)

- ea: `0x180007ac8`
- end: `0x180007d15`
- name: `?DwSendSubscribeResponse@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@KPEBD@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, int, const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006f64`
- `0x180007310`

## callees

- `0x180001400`
- `0x180006bc4`
- `0x180007ac8`
- `0x180008344`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bfb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bfb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007bc3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007bc3`

## string_xrefs

- `0x180007b34`: `SID: %s\n`

## pseudocode

```c
__int64 __fastcall DwSendSubscribeResponse(struct _EXTENSION_CONTROL_BLOCK *a1, int a2, const char *a3)
{
  char *v5; // rax
  __int64 v6; // r8
  unsigned int v7; // ebx
  char *v8; // rax
  __int64 v9; // rdx
  bool v10; // cf
  __int64 v11; // r8
  unsigned int v12; // r15d
  char *v13; // rax
  char *v14; // rdi
  __int64 v16; // rax
  char *v17; // r8
  __int64 v18; // rcx
  char *v19; // rdx
  char *v20; // rax
  HCONN ConnID; // rcx
  BOOL (__stdcall *ServerSupportFunction)(HCONN, DWORD, LPVOID, LPDWORD, LPDWORD); // rax
  unsigned int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h]
  char v26[256]; // [rsp+60h] [rbp-A0h] BYREF
  char v27[256]; // [rsp+160h] [rbp+60h] BYREF

  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( (int)StringCbPrintfA(v26, 0x100u, "Timeout: Second-%d\r\n", a2) >= 0
    && (int)StringCbPrintfA(v27, 0x100u, "SID: %s\r\n", a3) >= 0 )
  {
    v5 = v26;
    v6 = 0x7FFFFFFF;
    v7 = 1;
    do
    {
      if ( !*v5 )
        break;
      ++v5;
      --v6;
    }
    while ( v6 );
    v8 = v27;
    v9 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
    v10 = v6 != 0;
    v11 = 0x7FFFFFFF;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v11;
    }
    while ( v11 );
    v12 = (v10 ? v9 + 3 : 3) + (v11 != 0 ? 0x7FFFFFFF - v11 : 0);
    v13 = (char *)malloc(v12);
    v14 = v13;
    if ( !v13 )
    {
      v7 = 4;
      a1->dwHttpStatusCode = 503;
      return v7;
    }
    if ( v12 )
    {
      if ( v12 <= 0x7FFFFFFFuLL )
      {
        v16 = 2147483646;
        v17 = v26;
        v18 = v12;
        v19 = v14;
        do
        {
          if ( !v16 )
            break;
          if ( !*v17 )
            break;
          *v19++ = *v17++;
          --v16;
          --v18;
        }
        while ( v18 );
        v20 = v19 - 1;
        if ( v18 )
          v20 = v19;
        *v20 = 0;
        if ( v18 && (int)StringCchCatA(v14, v12, v27) >= 0 && (int)StringCchCatA(v14, v12, "\r\n") >= 0 )
        {
          ((void (__fastcall *)(HCONN, __int64, unsigned int *, _QWORD, _QWORD))a1->ServerSupportFunction)(
            a1->ConnID,
            1008,
            &v23,
            0,
            0);
          ConnID = a1->ConnID;
          ServerSupportFunction = a1->ServerSupportFunction;
          *(_QWORD *)&v24 = 0;
          *((_QWORD *)&v24 + 1) = v14;
          LODWORD(v25) = 0;
          *(_QWORD *)((char *)&v25 + 4) = __PAIR64__(v23, v12);
          ((void (__fastcall *)(HCONN, __int64, __int128 *, _QWORD, _QWORD))ServerSupportFunction)(
            ConnID,
            1016,
            &v24,
            0,
            0);
          goto LABEL_15;
        }
      }
      else
      {
        *v13 = 0;
      }
    }
    v7 = 4;
    a1->dwHttpStatusCode = 503;
LABEL_15:
    free(v14);
    return v7;
  }
  a1->dwHttpStatusCode = 503;
  return 4;
}

```

## disassembly

```asm
0x180007ac8  push    rbp
0x180007aca  push    rbx
0x180007acb  push    rsi
0x180007acc  push    rdi
0x180007acd  push    r13
0x180007acf  push    r14
0x180007ad1  push    r15
0x180007ad3  lea     rbp, [rsp-170h]
0x180007adb  sub     rsp, 270h
0x180007ae2  mov     rax, cs:__security_cookie
0x180007ae9  xor     rax, rsp
0x180007aec  mov     [rbp+1A0h+var_40], rax
0x180007af3  xorps   xmm0, xmm0
0x180007af6  mov     [rsp+2A0h+var_270], 0
0x180007afe  mov     rbx, r8
0x180007b01  mov     r14, rcx
0x180007b04  mov     r9d, edx
0x180007b07  lea     r8, aTimeoutSecondD; "Timeout: Second-%d\r\n"
0x180007b0e  mov     edi, 100h
0x180007b13  lea     rcx, [rsp+2A0h+var_240]; char *
0x180007b18  mov     edx, edi; unsigned __int64
0x180007b1a  movups  [rsp+2A0h+var_268], xmm0
0x180007b1f  movups  [rsp+2A0h+var_258], xmm0
0x180007b24  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180007b29  test    eax, eax
0x180007b2b  js      loc_180007CE7
0x180007b31  mov     r9, rbx
0x180007b34  lea     r8, aSidS; "SID: %s\r\n"
0x180007b3b  mov     edx, edi; unsigned __int64
0x180007b3d  lea     rcx, [rbp+1A0h+var_140]; char *
0x180007b41  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180007b46  test    eax, eax
0x180007b48  js      loc_180007CE7
0x180007b4e  mov     r13d, 7FFFFFFFh
0x180007b54  lea     rax, [rsp+2A0h+var_240]
0x180007b59  mov     r8d, r13d
0x180007b5c  mov     ebx, 1
0x180007b61  cmp     byte ptr [rax], 0
0x180007b64  jz      short loc_180007B6E
0x180007b66  add     rax, rbx
0x180007b69  sub     r8, rbx
0x180007b6c  jnz     short loc_180007B61
0x180007b6e  mov     rax, r8
0x180007b71  mov     rcx, r13
0x180007b74  sub     rcx, r8
0x180007b77  neg     rax
0x180007b7a  lea     rax, [rbp+1A0h+var_140]
0x180007b7e  sbb     rdx, rdx
0x180007b81  and     rdx, rcx
0x180007b84  neg     r8
0x180007b87  mov     r8, r13
0x180007b8a  sbb     r9, r9
0x180007b8d  and     r9, rdx
0x180007b90  cmp     byte ptr [rax], 0
0x180007b93  jz      short loc_180007B9D
0x180007b95  add     rax, rbx
0x180007b98  sub     r8, rbx
0x180007b9b  jnz     short loc_180007B90
0x180007b9d  mov     rax, r8
0x180007ba0  mov     r15d, r13d
0x180007ba3  sub     r15d, r8d
0x180007ba6  neg     rax
0x180007ba9  sbb     edx, edx
0x180007bab  and     r15d, edx
0x180007bae  neg     r8
0x180007bb1  sbb     eax, eax
0x180007bb3  add     r9d, 3
0x180007bb7  and     r15d, eax
0x180007bba  add     r15d, r9d
0x180007bbd  mov     ecx, r15d; Size
0x180007bc0  mov     esi, r15d
0x180007bc3  call    cs:__imp_malloc
0x180007bc9  mov     rdi, rax
0x180007bcc  test    rax, rax
0x180007bcf  jnz     short loc_180007BDE
0x180007bd1  lea     ebx, [rax+4]
0x180007bd4  mov     dword ptr [r14+10h], 1F7h
0x180007bdc  jmp     short loc_180007C01
0x180007bde  test    r15d, r15d
0x180007be1  jz      short loc_180007BEB
0x180007be3  cmp     rsi, r13
0x180007be6  jbe     short loc_180007C08
0x180007be8  mov     byte ptr [rax], 0
0x180007beb  mov     ebx, 4
0x180007bf0  mov     dword ptr [r14+10h], 1F7h
0x180007bf8  mov     rcx, rdi; Block
0x180007bfb  call    cs:__imp_free
0x180007c01  mov     eax, ebx
0x180007c03  jmp     loc_180007CF4
0x180007c08  mov     eax, 7FFFFFFEh
0x180007c0d  lea     r8, [rsp+2A0h+var_240]
0x180007c12  mov     rcx, rsi
0x180007c15  mov     rdx, rdi
0x180007c18  test    rax, rax
0x180007c1b  jz      short loc_180007C36
0x180007c1d  mov     r9b, [r8]
0x180007c20  test    r9b, r9b
0x180007c23  jz      short loc_180007C36
0x180007c25  mov     [rdx], r9b
0x180007c28  add     r8, rbx
0x180007c2b  add     rdx, rbx
0x180007c2e  sub     rax, rbx
0x180007c31  sub     rcx, rbx
0x180007c34  jnz     short loc_180007C18
0x180007c36  test    rcx, rcx
0x180007c39  lea     rax, [rdx-1]
0x180007c3d  cmovnz  rax, rdx
0x180007c41  mov     byte ptr [rax], 0
0x180007c44  jz      short loc_180007BEB
0x180007c46  lea     r8, [rbp+1A0h+var_140]; char *
0x180007c4a  mov     rdx, rsi; unsigned __int64
0x180007c4d  mov     rcx, rdi; char *
0x180007c50  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180007c55  test    eax, eax
0x180007c57  js      short loc_180007BEB
0x180007c59  lea     r8, asc_18000D924; "\r\n"
0x180007c60  mov     rdx, rsi; unsigned __int64
0x180007c63  mov     rcx, rdi; char *
0x180007c66  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180007c6b  test    eax, eax
0x180007c6d  js      loc_180007BEB
0x180007c73  mov     rcx, [r14+8]
0x180007c77  lea     r8, [rsp+2A0h+var_270]
0x180007c7c  mov     rax, [r14+0B8h]
0x180007c83  xor     r9d, r9d
0x180007c86  mov     edx, 3F0h
0x180007c8b  mov     [rsp+2A0h+var_280], 0
0x180007c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c99  mov     eax, [rsp+2A0h+var_270]
0x180007c9d  lea     r8, [rsp+2A0h+var_268]
0x180007ca2  mov     rcx, [r14+8]
0x180007ca6  xor     r9d, r9d
0x180007ca9  mov     dword ptr [rsp+2A0h+var_258+8], eax
0x180007cad  mov     edx, 3F8h
0x180007cb2  mov     rax, [r14+0B8h]
0x180007cb9  mov     qword ptr [rsp+2A0h+var_268], 0
0x180007cc2  mov     qword ptr [rsp+2A0h+var_268+8], rdi
0x180007cc7  mov     dword ptr [rsp+2A0h+var_258], 0
0x180007ccf  mov     dword ptr [rsp+2A0h+var_258+4], r15d
0x180007cd4  mov     [rsp+2A0h+var_280], 0
0x180007cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce2  jmp     loc_180007BF8
0x180007ce7  mov     dword ptr [r14+10h], 1F7h
0x180007cef  mov     eax, 4
0x180007cf4  mov     rcx, [rbp+1A0h+var_40]
0x180007cfb  xor     rcx, rsp; StackCookie
0x180007cfe  call    __security_check_cookie
0x180007d03  add     rsp, 270h
0x180007d0a  pop     r15
0x180007d0c  pop     r14
0x180007d0e  pop     r13
0x180007d10  pop     rdi
0x180007d11  pop     rsi
0x180007d12  pop     rbx
0x180007d13  pop     rbp
0x180007d14  retn
```

# CSpVAEngineModel::GetUbmAsStream(ushort const *,void * *,unsigned __int64 *)

- ea: `0x1801b7b9c`
- end: `0x1801b7d8e`
- name: `?GetUbmAsStream@CSpVAEngineModel@@AEAAJPEBGPEAPEAXPEA_K@Z`
- size: `498`
- prototype: `__int64 __fastcall(CSpVAEngineModel *__hidden this, const unsigned __int16 *, void **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801b7624`

## callees

- `0x180013ec0`
- `0x1801b7b9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1801b7c25`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1801b7c25`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1801b7d56`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1801b7d56`
- `api-ms-win-crt-private-l1-1-0!_o_fgetc` at `0x1801b7cc0`
- `api-ms-win-crt-private-l1-1-0!_o_fgetc` at `0x1801b7cc0`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1801b7c5a`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1801b7c84`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1801b7c5a`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1801b7c84`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x1801b7c6d`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x1801b7c6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7d68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7d68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b7c98`

## pseudocode

```c
__int64 __fastcall CSpVAEngineModel::GetUbmAsStream(
        CSpVAEngineModel *this,
        const unsigned __int16 *a2,
        void **a3,
        unsigned __int64 *a4)
{
  int v6; // ebx
  int v7; // eax
  SIZE_T v8; // rsi
  void *v9; // rax
  _BYTE *v10; // r14
  const wchar_t *v11; // rax
  __int64 v12; // rbp
  int v13; // eax
  FILE *Stream; // [rsp+60h] [rbp+8h] BYREF

  Stream = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::GetUbmAsStream",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(432)",
      -2147467261);
    goto LABEL_24;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::GetUbmAsStream",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(433)",
      -2147467261);
    goto LABEL_24;
  }
  if ( !a4 )
  {
    v6 = -2147467261;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::GetUbmAsStream",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(434)",
      -2147467261);
    goto LABEL_24;
  }
  if ( _wfopen_s(&Stream, a2, L"rb") )
  {
    v6 = -2147024809;
    v11 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(438)";
    goto LABEL_23;
  }
  if ( !Stream )
  {
    v6 = -2147467259;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::GetUbmAsStream",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(439)",
      -2147467259);
    goto LABEL_24;
  }
  if ( fseek(Stream, 0, 2) )
  {
    v6 = -2147467259;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::GetUbmAsStream",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(441)",
      -2147467259);
    goto LABEL_24;
  }
  v7 = _o_ftell(Stream);
  v8 = v7;
  if ( v7 <= 0 )
  {
    v6 = -2147467259;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::GetUbmAsStream",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(444)",
      -2147467259);
    goto LABEL_24;
  }
  if ( fseek(Stream, 0, 0) )
  {
    v6 = -2147467259;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::GetUbmAsStream",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(446)",
      -2147467259);
    goto LABEL_24;
  }
  *a3 = 0;
  v9 = CoTaskMemAlloc(v8);
  *a3 = v9;
  v10 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v11 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(450)";
LABEL_23:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::GetUbmAsStream",
      v11,
      v6);
    goto LABEL_24;
  }
  v6 = 0;
  v12 = 0;
  do
  {
    v13 = _o_fgetc(Stream);
    if ( v13 == -1 )
      break;
    v10[v12] = v13;
    v12 = (unsigned int)(v12 + 1);
  }
  while ( (int)v12 < (int)v8 );
  *a4 = v8;
LABEL_24:
  if ( Stream )
    fclose(Stream);
  if ( v6 < 0 && *a3 )
  {
    CoTaskMemFree(*a3);
    *a3 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801b7b9c  mov     rax, rsp
0x1801b7b9f  mov     [rax+10h], rbx
0x1801b7ba3  mov     [rax+18h], rbp
0x1801b7ba7  mov     [rax+8], rcx
0x1801b7bab  push    rsi
0x1801b7bac  push    rdi
0x1801b7bad  push    r12
0x1801b7baf  push    r14
0x1801b7bb1  push    r15
0x1801b7bb3  sub     rsp, 30h
0x1801b7bb7  mov     qword ptr [rax+8], 0
0x1801b7bbf  mov     r12, r9
0x1801b7bc2  mov     rdi, r8
0x1801b7bc5  test    rdx, rdx
0x1801b7bc8  jnz     short loc_1801B7BE1
0x1801b7bca  mov     eax, 80004003h
0x1801b7bcf  mov     ebx, eax
0x1801b7bd1  mov     [rsp+58h+var_30], eax
0x1801b7bd5  lea     rax, aOnecoreuapEndu_238; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7bdc  jmp     loc_1801B7D28
0x1801b7be1  test    rdi, rdi
0x1801b7be4  jnz     short loc_1801B7BFD
0x1801b7be6  mov     eax, 80004003h
0x1801b7beb  mov     ebx, eax
0x1801b7bed  mov     [rsp+58h+var_30], eax
0x1801b7bf1  lea     rax, aOnecoreuapEndu_354; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7bf8  jmp     loc_1801B7D28
0x1801b7bfd  test    r12, r12
0x1801b7c00  jnz     short loc_1801B7C19
0x1801b7c02  mov     eax, 80004003h
0x1801b7c07  mov     ebx, eax
0x1801b7c09  mov     [rsp+58h+var_30], eax
0x1801b7c0d  lea     rax, aOnecoreuapEndu_320; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7c14  jmp     loc_1801B7D28
0x1801b7c19  lea     r8, aRb; "rb"
0x1801b7c20  lea     rcx, [rsp+58h+Stream]; Stream
0x1801b7c25  call    cs:__imp__wfopen_s
0x1801b7c2b  test    eax, eax
0x1801b7c2d  jnz     loc_1801B7D18
0x1801b7c33  mov     rcx, [rsp+58h+Stream]; Stream
0x1801b7c38  test    rcx, rcx
0x1801b7c3b  jnz     short loc_1801B7C54
0x1801b7c3d  mov     eax, 80004005h
0x1801b7c42  mov     ebx, eax
0x1801b7c44  mov     [rsp+58h+var_30], eax
0x1801b7c48  lea     rax, aOnecoreuapEndu_38; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7c4f  jmp     loc_1801B7D28
0x1801b7c54  xor     edx, edx; Offset
0x1801b7c56  lea     r8d, [rdx+2]; Origin
0x1801b7c5a  call    cs:__imp_fseek
0x1801b7c60  test    eax, eax
0x1801b7c62  jnz     loc_1801B7D04
0x1801b7c68  mov     rcx, [rsp+58h+Stream]
0x1801b7c6d  call    cs:__imp__o_ftell
0x1801b7c73  movsxd  rsi, eax
0x1801b7c76  test    eax, eax
0x1801b7c78  jle     short loc_1801B7CF0
0x1801b7c7a  mov     rcx, [rsp+58h+Stream]; Stream
0x1801b7c7f  xor     r8d, r8d; Origin
0x1801b7c82  xor     edx, edx; Offset
0x1801b7c84  call    cs:__imp_fseek
0x1801b7c8a  test    eax, eax
0x1801b7c8c  jnz     short loc_1801B7CDC
0x1801b7c8e  mov     rcx, rsi; cb
0x1801b7c91  mov     qword ptr [rdi], 0
0x1801b7c98  call    cs:__imp_CoTaskMemAlloc
0x1801b7c9e  mov     [rdi], rax
0x1801b7ca1  mov     r14, rax
0x1801b7ca4  test    rax, rax
0x1801b7ca7  jnz     short loc_1801B7CB7
0x1801b7ca9  mov     ebx, 8007000Eh
0x1801b7cae  lea     rax, aOnecoreuapEndu_108; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7cb5  jmp     short loc_1801B7D24
0x1801b7cb7  xor     ebx, ebx
0x1801b7cb9  xor     ebp, ebp
0x1801b7cbb  mov     rcx, [rsp+58h+Stream]
0x1801b7cc0  call    cs:__imp__o_fgetc
0x1801b7cc6  cmp     eax, 0FFFFFFFFh
0x1801b7cc9  jz      short loc_1801B7CD6
0x1801b7ccb  mov     [rbp+r14+0], al
0x1801b7cd0  inc     ebp
0x1801b7cd2  cmp     ebp, esi
0x1801b7cd4  jl      short loc_1801B7CBB
0x1801b7cd6  mov     [r12], rsi
0x1801b7cda  jmp     short loc_1801B7D4C
0x1801b7cdc  mov     eax, 80004005h
0x1801b7ce1  mov     ebx, eax
0x1801b7ce3  mov     [rsp+58h+var_30], eax
0x1801b7ce7  lea     rax, aOnecoreuapEndu_251; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7cee  jmp     short loc_1801B7D28
0x1801b7cf0  mov     eax, 80004005h
0x1801b7cf5  mov     ebx, eax
0x1801b7cf7  mov     [rsp+58h+var_30], eax
0x1801b7cfb  lea     rax, aOnecoreuapEndu_244; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7d02  jmp     short loc_1801B7D28
0x1801b7d04  mov     eax, 80004005h
0x1801b7d09  mov     ebx, eax
0x1801b7d0b  mov     [rsp+58h+var_30], eax
0x1801b7d0f  lea     rax, aOnecoreuapEndu_162; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7d16  jmp     short loc_1801B7D28
0x1801b7d18  mov     ebx, 80070057h
0x1801b7d1d  lea     rax, aOnecoreuapEndu_104; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7d24  mov     [rsp+58h+var_30], ebx
0x1801b7d28  lea     r9, aCspvaenginemod_8; "CSpVAEngineModel::GetUbmAsStream"
0x1801b7d2f  mov     [rsp+58h+var_38], rax
0x1801b7d34  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1801b7d3b  mov     ecx, 2; int
0x1801b7d40  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1801b7d47  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801b7d4c  mov     rcx, [rsp+58h+Stream]; Stream
0x1801b7d51  test    rcx, rcx
0x1801b7d54  jz      short loc_1801B7D5C
0x1801b7d56  call    cs:__imp_fclose
0x1801b7d5c  test    ebx, ebx
0x1801b7d5e  jns     short loc_1801B7D75
0x1801b7d60  mov     rcx, [rdi]; pv
0x1801b7d63  test    rcx, rcx
0x1801b7d66  jz      short loc_1801B7D75
0x1801b7d68  call    cs:__imp_CoTaskMemFree
0x1801b7d6e  mov     qword ptr [rdi], 0
0x1801b7d75  mov     rbp, [rsp+58h+arg_10]
0x1801b7d7a  mov     eax, ebx
0x1801b7d7c  mov     rbx, [rsp+58h+arg_8]
0x1801b7d81  add     rsp, 30h
0x1801b7d85  pop     r15
0x1801b7d87  pop     r14
0x1801b7d89  pop     r12
0x1801b7d8b  pop     rdi
0x1801b7d8c  pop     rsi
0x1801b7d8d  retn
```

# CSREngine::GetModelFileName(ushort const *,SR_FILETYPE,int,int,ushort * *,ulong *,int)

- ea: `0x18000b6a0`
- end: `0x18000b82e`
- name: `?GetModelFileName@CSREngine@@UEAAJPEBGW4SR_FILETYPE@@HHPEAPEAGPEAKH@Z`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800034b0`
- `0x18000b6a0`
- `0x18000ca0c`
- `0x1800996c8`
- `0x1800a048c`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18000b7bf`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18000b7bf`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000b7d5`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000b7d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b80f`

## pseudocode

```c
__int64 __fastcall CSREngine::GetModelFileName(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        wchar_t **a6,
        __int64 a7,
        int a8)
{
  __int64 v10; // rdi
  int v11; // eax
  int v12; // ebx
  wchar_t *v13; // rcx
  int v14; // edi
  int v15; // edi
  int v16; // edi
  const wchar_t *v17; // rdx
  LPVOID pv; // [rsp+40h] [rbp-30h] BYREF
  FILE *Stream; // [rsp+48h] [rbp-28h] BYREF
  __int64 Buffer; // [rsp+50h] [rbp-20h] BYREF
  int v22; // [rsp+58h] [rbp-18h]

  v10 = (int)a3;
  *a6 = 0;
  pv = 0;
  CSREngine::GetUserModelFileKeyName(a1 - 16, a2, a3, &pv, a7, a7, a8);
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID, const wchar_t *, int, wchar_t **))(**(_QWORD **)(a1 + 232)
                                                                                             + 152LL))(
          *(_QWORD *)(a1 + 232),
          a1 + 96,
          pv,
          L"MSASR\\",
          a5 != 0 ? 32796 : 28,
          a6);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 >= 0 || a5 )
      goto LABEL_20;
    goto LABEL_17;
  }
  v13 = *a6;
  Buffer = 0;
  v22 = 0;
  v12 = CSRTopicSLM::ReadFileHeader(v13, 0xCu, &Buffer);
  if ( v12 >= 0 && (int)Buffer <= *((_DWORD *)&CSREngine::s_aversionMin + v10) )
  {
    v14 = v10 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          if ( (unsigned int)(v16 - 1) >= 2 )
            goto LABEL_20;
        }
      }
    }
    else if ( CPPT::SanityCheckDLM(*a6) )
    {
      goto LABEL_11;
    }
    if ( v22 == a4 )
      goto LABEL_20;
  }
LABEL_11:
  if ( a5 )
  {
    v17 = *a6;
    Stream = 0;
    _wfopen_s(&Stream, v17, L"wb");
    if ( Stream )
    {
      fclose(Stream);
      v12 = 1;
    }
    else
    {
      v12 = -2147467259;
    }
    goto LABEL_20;
  }
LABEL_17:
  if ( *a6 )
  {
    CoTaskMemFree(*a6);
    *a6 = 0;
  }
  v12 = -2147200966;
LABEL_20:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b6a0  push    rbp
0x18000b6a2  push    rbx
0x18000b6a3  push    rsi
0x18000b6a4  push    rdi
0x18000b6a5  push    r12
0x18000b6a7  mov     rbp, rsp
0x18000b6aa  sub     rsp, 70h
0x18000b6ae  mov     rax, cs:__security_cookie
0x18000b6b5  xor     rax, rsp
0x18000b6b8  mov     [rbp+var_10], rax
0x18000b6bc  mov     r10, [rbp+arg_30]
0x18000b6c0  mov     r12d, r9d
0x18000b6c3  mov     eax, [rbp+arg_38]
0x18000b6c6  lea     r9, [rbp+pv]
0x18000b6ca  mov     rsi, [rbp+arg_28]
0x18000b6ce  mov     rbx, rcx
0x18000b6d1  mov     [rsp+70h+var_40], eax
0x18000b6d5  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000b6d9  movsxd  rdi, r8d
0x18000b6dc  mov     [rsp+70h+var_48], r10
0x18000b6e1  mov     r8d, edi
0x18000b6e4  mov     qword ptr [rsi], 0
0x18000b6eb  mov     [rbp+pv], 0
0x18000b6f3  mov     [rsp+70h+var_50], r10
0x18000b6f8  call    ?GetUserModelFileKeyName@CSREngine@@QEAAKPEBGW4SR_FILETYPE@@PEAPEAGPEAK3H@Z; CSREngine::GetUserModelFileKeyName(ushort const *,SR_FILETYPE,ushort * *,ulong *,ulong *,int)
0x18000b6fd  mov     eax, [rbp+arg_20]
0x18000b700  lea     rdx, [rbx+60h]
0x18000b704  mov     rcx, [rbx+0E8h]
0x18000b70b  neg     eax
0x18000b70d  mov     [rsp+70h+var_48], rsi
0x18000b712  sbb     r8d, r8d
0x18000b715  and     r8d, 8000h
0x18000b71c  mov     r9, [rcx]
0x18000b71f  add     r8d, 1Ch
0x18000b723  mov     dword ptr [rsp+70h+var_50], r8d
0x18000b728  mov     r8, [rbp+pv]
0x18000b72c  mov     rax, [r9+98h]
0x18000b733  lea     r9, aMsasr; "MSASR\\"
0x18000b73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b73f  mov     ebx, eax
0x18000b741  test    eax, eax
0x18000b743  jnz     loc_18000B7E2
0x18000b749  mov     rcx, [rsi]; FileName
0x18000b74c  lea     r8, [rbp+Buffer]; Buffer
0x18000b750  xor     eax, eax
0x18000b752  lea     edx, [rbx+0Ch]; ElementCount
0x18000b755  mov     [rbp+Buffer], rax
0x18000b759  mov     [rbp+var_18], eax
0x18000b75c  call    ?ReadFileHeader@CSRTopicSLM@@SAJPEBG_KPEAX@Z; CSRTopicSLM::ReadFileHeader(ushort const *,unsigned __int64,void *)
0x18000b761  mov     ebx, eax
0x18000b763  test    eax, eax
0x18000b765  js      short loc_18000B7A3
0x18000b767  lea     rax, ?s_aversionMin@CSREngine@@0QBHB; int const near * const CSREngine::s_aversionMin
0x18000b76e  mov     ecx, [rax+rdi*4]
0x18000b771  cmp     dword ptr [rbp+Buffer], ecx
0x18000b774  jg      short loc_18000B7A3
0x18000b776  sub     edi, 1
0x18000b779  jz      short loc_18000B791
0x18000b77b  sub     edi, 1
0x18000b77e  jz      short loc_18000B79D
0x18000b780  sub     edi, 1
0x18000b783  jz      short loc_18000B79D
0x18000b785  sub     edi, 1
0x18000b788  jz      short loc_18000B79D
0x18000b78a  cmp     edi, 1
0x18000b78d  jz      short loc_18000B79D
0x18000b78f  jmp     short loc_18000B804
0x18000b791  mov     rcx, [rsi]; FileName
0x18000b794  call    ?SanityCheckDLM@CPPT@@SA_NPEBG@Z; CPPT::SanityCheckDLM(ushort const *)
0x18000b799  test    al, al
0x18000b79b  jnz     short loc_18000B7A3
0x18000b79d  cmp     [rbp+var_18], r12d
0x18000b7a1  jz      short loc_18000B804
0x18000b7a3  cmp     [rbp+arg_20], 0
0x18000b7a7  jz      short loc_18000B7EA
0x18000b7a9  mov     rdx, [rsi]; FileName
0x18000b7ac  lea     r8, aWb; "wb"
0x18000b7b3  lea     rcx, [rbp+Stream]; Stream
0x18000b7b7  mov     [rbp+Stream], 0
0x18000b7bf  call    cs:__imp__wfopen_s
0x18000b7c5  mov     rcx, [rbp+Stream]; Stream
0x18000b7c9  test    rcx, rcx
0x18000b7cc  jnz     short loc_18000B7D5
0x18000b7ce  mov     ebx, 80004005h
0x18000b7d3  jmp     short loc_18000B804
0x18000b7d5  call    cs:__imp_fclose
0x18000b7db  mov     ebx, 1
0x18000b7e0  jmp     short loc_18000B804
0x18000b7e2  jns     short loc_18000B804
0x18000b7e4  cmp     [rbp+arg_20], 0
0x18000b7e8  jnz     short loc_18000B804
0x18000b7ea  mov     rcx, [rsi]; pv
0x18000b7ed  test    rcx, rcx
0x18000b7f0  jz      short loc_18000B7FF
0x18000b7f2  call    cs:__imp_CoTaskMemFree
0x18000b7f8  mov     qword ptr [rsi], 0
0x18000b7ff  mov     ebx, 8004503Ah
0x18000b804  cmp     [rbp+pv], 0
0x18000b809  jz      short loc_18000B815
0x18000b80b  mov     rcx, [rbp+pv]; pv
0x18000b80f  call    cs:__imp_CoTaskMemFree
0x18000b815  mov     eax, ebx
0x18000b817  mov     rcx, [rbp+var_10]
0x18000b81b  xor     rcx, rsp; StackCookie
0x18000b81e  call    __security_check_cookie
0x18000b823  add     rsp, 70h
0x18000b827  pop     r12
0x18000b829  pop     rdi
0x18000b82a  pop     rsi
0x18000b82b  pop     rbx
0x18000b82c  pop     rbp
0x18000b82d  retn
```

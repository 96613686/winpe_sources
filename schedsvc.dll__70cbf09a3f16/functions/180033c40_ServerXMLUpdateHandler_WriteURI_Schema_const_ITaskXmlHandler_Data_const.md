# ServerXMLUpdateHandler::WriteURI(Schema const &,ITaskXmlHandler::Data const *)

- ea: `0x180033c40`
- end: `0x180034208`
- name: `?WriteURI@ServerXMLUpdateHandler@@AEAAXAEBUSchema@@PEBUData@ITaskXmlHandler@@@Z`
- size: `1480`
- prototype: `void __fastcall(ServerXMLUpdateHandler *__hidden this, const struct Schema *, const struct ITaskXmlHandler::Data *)`
- caller_count: `3`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180033bc0`
- `0x18003fd40`
- `0x18007e2d8`

## callees

- `0x180025310`
- `0x180033c40`
- `0x1800346c0`
- `0x180052118`
- `0x180054330`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800341e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800341e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180033d82`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180033d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033eea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033eea`
- `RPCRT4!UuidCreate` at `0x180034117`
- `RPCRT4!UuidCreate` at `0x180034117`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003413d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003413d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ServerXMLUpdateHandler::WriteURI(
        ServerXMLUpdateHandler *this,
        const struct Schema *a2,
        const struct ITaskXmlHandler::Data *a3)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r10
  unsigned __int16 v9; // r11
  int i; // ecx
  int v11; // r9d
  bool v12; // zf
  unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  unsigned __int64 v16; // rdx
  unsigned int *v17; // rbx
  unsigned int v18; // eax
  const struct SchemaEntry * near *v19; // r8
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ecx
  __int64 v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r9
  const OLECHAR *v27; // rax
  __int64 v28; // rbx
  OLECHAR *v29; // r11
  OLECHAR v30; // cx
  __int64 v31; // rcx
  _WORD *v32; // rax
  __int64 v33; // rdx
  unsigned __int16 *v34; // rax
  unsigned __int16 v35; // cx
  unsigned __int64 v36; // r9
  __int64 v37; // rax
  OLECHAR v38; // r8
  const OLECHAR *v39; // rax
  OLECHAR *v40; // rcx
  int v41; // eax
  unsigned __int16 *v42; // rdx
  char v43[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h]
  int v46; // [rsp+48h] [rbp-B8h]
  __int16 v47; // [rsp+4Ch] [rbp-B4h]
  int *v48; // [rsp+60h] [rbp-A0h]
  LPVOID lpMem; // [rsp+68h] [rbp-98h]
  UUID Uuid; // [rsp+80h] [rbp-80h] BYREF
  int v51; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h]
  __int16 v53; // [rsp+A0h] [rbp-60h]
  char v54; // [rsp+4A2h] [rbp+3A2h]
  OLECHAR sz[8]; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int128 v56; // [rsp+4C0h] [rbp+3C0h]
  __int128 v57; // [rsp+4D0h] [rbp+3D0h]
  __int128 v58; // [rsp+4E0h] [rbp+3E0h]
  __int128 v59; // [rsp+4F0h] [rbp+3F0h]
  _WORD v60[264]; // [rsp+500h] [rbp+400h] BYREF

  Uuid = 0;
  *(_OWORD *)sz = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  memset_0(v60, 0, 0x20Au);
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 101);
  if ( !v6 || (v6 = *(const unsigned __int16 **)v6) == 0 )
  {
    if ( a3 )
    {
      v42 = *(unsigned __int16 **)(*((_QWORD *)a3 + 6) + 8LL);
    }
    else
    {
      v41 = UuidCreate(&Uuid);
      if ( v41 && v41 != 1824 )
      {
        if ( v41 > 0 )
          v41 = (unsigned __int16)v41 | 0x80070000;
        ServerXMLUpdateHandler::UpdateHR(this, v41);
        return;
      }
      if ( !StringFromGUID2(&Uuid, sz, 40) )
      {
        ServerXMLUpdateHandler::UpdateHR(this, -2147024774);
        return;
      }
      v42 = sz;
    }
    tsched::TaskPathCanonicalize((tsched *)v60, v42, v6);
    goto LABEL_15;
  }
  v7 = 261;
  v8 = 2147483646;
  if ( !*v6 )
  {
    v39 = L"\\";
    v40 = v60;
    do
    {
      if ( !v8 )
        goto LABEL_69;
      v38 = *v39;
      if ( !*v39 )
        goto LABEL_69;
      ++v39;
      *v40++ = v38;
      --v8;
      --v7;
    }
    while ( v7 );
    --v40;
LABEL_69:
    *v40 = 0;
    goto LABEL_15;
  }
  if ( *v6 == 92 )
    goto LABEL_5;
  v26 = 2147483646;
  v27 = L"\\";
  v28 = 261;
  v29 = v60;
  do
  {
    if ( !v26 || (v30 = *v27) == 0 )
    {
      *v29 = 0;
LABEL_5:
      v9 = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= 261 )
          goto LABEL_15;
        v11 = v6[i];
        if ( !(_WORD)v11 )
        {
          if ( v9 != 92 || i <= 1 )
          {
            v31 = 261;
            v32 = v60;
            do
            {
              if ( !*v32 )
                break;
              ++v32;
              --v31;
            }
            while ( v31 );
            if ( v31 )
            {
              v33 = v31;
              v34 = &v60[261 - v31];
              do
              {
                if ( !v8 )
                  break;
                v35 = *v6;
                if ( !*v6 )
                  break;
                ++v6;
                *v34++ = v35;
                --v8;
                --v33;
              }
              while ( v33 );
              v13 = v34 - 1;
              if ( v33 )
                v13 = v34;
              *v13 = 0;
            }
          }
          goto LABEL_15;
        }
        if ( v11 == 92 )
          break;
        if ( v11 == 32 )
        {
          if ( v9 == 92 )
            goto LABEL_15;
          v12 = v9 == 0;
          goto LABEL_10;
        }
        if ( v11 != 46 )
        {
          if ( v11 == 47 )
            goto LABEL_15;
          v12 = v11 == 58;
          goto LABEL_10;
        }
        if ( v9 == 46 || v9 == 92 && v6[i + 1] == 92 )
          goto LABEL_15;
LABEL_11:
        v9 = v6[i];
      }
      v12 = v9 == 92;
LABEL_10:
      if ( v12 )
        goto LABEL_15;
      goto LABEL_11;
    }
    ++v27;
    *v29++ = v30;
    --v26;
    --v28;
  }
  while ( v28 );
  *(v29 - 1) = 0;
LABEL_15:
  v54 &= 0xFCu;
  v53 = 0;
  v14 = -1;
  do
    ++v14;
  while ( v60[v14] );
  v51 = v14;
  bstrString = v60;
  v43[0] = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  lpMem = 0;
  v48 = &v51;
  v15 = TriggersXmlHandler::ProcessValue((__int64)this, (__int64)a2, 4, (__int64)v43);
  if ( v15 < 0 && *((int *)this + 268) >= 0 )
    *((_DWORD *)this + 268) = v15;
  v17 = (unsigned int *)*((_QWORD *)this + 131);
  v18 = v17[38];
  if ( v18 )
  {
    v17[38] = v18 + 1;
    goto LABEL_32;
  }
  v16 = *v17;
  if ( (_DWORD)v16 == 65542 )
  {
LABEL_20:
    v19 = (&Schema::schemaEntries)[(unsigned __int16)v16] + 64;
  }
  else
  {
    switch ( (int)v16 )
    {
      case 65536:
      case 65537:
        v36 = 0;
        v37 = (unsigned __int16)v16;
        v16 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v16];
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_20;
      default:
        goto LABEL_92;
    }
    while ( v36 < v16 )
    {
      v19 = &(&Schema::schemaEntries)[v37][16 * v36];
      if ( *(_DWORD *)v19 == 4 )
        goto LABEL_22;
      ++v36;
    }
LABEL_92:
    v19 = (const struct SchemaEntry * near *)&qword_18009D560;
  }
  if ( *(_DWORD *)v19 )
  {
LABEL_22:
    v20 = *((_QWORD *)v17 + 2);
    if ( !v20 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
    v21 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const, _BYTE))(*(_QWORD *)v20 + 216LL))(
            v20,
            &ChannelPath,
            v19[1],
            Schema::namespaceUri,
            0);
    v22 = v21;
    if ( v21 >= 0 )
    {
      if ( v21 )
        goto LABEL_32;
      v23 = *((_QWORD *)v17 + 2);
      if ( !v23 )
        _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
      v22 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v23 + 224LL))(v23, v60);
      if ( v22 >= 0 )
      {
LABEL_32:
        v22 = 1;
        goto LABEL_33;
      }
    }
    goto LABEL_24;
  }
  v22 = 1;
  v17[38] = 1;
LABEL_33:
  v24 = v17[38];
  if ( v24 )
  {
    v17[38] = v24 - 1;
  }
  else
  {
    v25 = *((_QWORD *)v17 + 2);
    if ( !v25 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 120LL))(v25);
  }
  if ( v22 < 0 )
  {
LABEL_24:
    if ( *((int *)this + 268) >= 0 )
      *((_DWORD *)this + 268) = v22;
  }
  if ( lpMem )
    HeapFree(g_PrivateHeap, 0, lpMem);
  if ( (v54 & 1) != 0 )
    SysFreeString(bstrString);
}

```

## disassembly

```asm
0x180033c40  push    rbp
0x180033c42  push    rbx
0x180033c43  push    rsi
0x180033c44  push    rdi
0x180033c45  push    r14
0x180033c47  lea     rbp, [rsp-620h]
0x180033c4f  sub     rsp, 720h
0x180033c56  mov     rax, cs:__security_cookie
0x180033c5d  xor     rax, rsp
0x180033c60  mov     [rbp+640h+var_30], rax
0x180033c67  mov     rbx, r8
0x180033c6a  mov     r14, rdx
0x180033c6d  mov     rsi, rcx
0x180033c70  xorps   xmm0, xmm0
0x180033c73  movups  xmmword ptr [rbp+640h+Uuid.Data1], xmm0
0x180033c77  xorps   xmm1, xmm1
0x180033c7a  movups  xmmword ptr [rbp+640h+sz], xmm1
0x180033c81  movups  [rbp+640h+var_280], xmm1
0x180033c88  movups  [rbp+640h+var_270], xmm1
0x180033c8f  movups  [rbp+640h+var_260], xmm1
0x180033c96  movups  [rbp+640h+var_250], xmm1
0x180033c9d  xor     edx, edx; Val
0x180033c9f  mov     r8d, 20Ah; Size
0x180033ca5  lea     rcx, [rbp+640h+var_240]; void *
0x180033cac  call    memset_0
0x180033cb1  mov     r8, [rsi+328h]
0x180033cb8  test    r8, r8
0x180033cbb  jz      loc_180034104
0x180033cc1  mov     r8, [r8]
0x180033cc4  test    r8, r8
0x180033cc7  jz      loc_180034104
0x180033ccd  movzx   eax, word ptr [r8]
0x180033cd1  mov     edx, 105h
0x180033cd6  mov     r10d, 7FFFFFFEh
0x180033cdc  test    ax, ax
0x180033cdf  jz      loc_1800340F1
0x180033ce5  cmp     ax, 5Ch ; '\'
0x180033ce9  jnz     loc_180033F35
0x180033cef  xor     r11d, r11d
0x180033cf2  xor     ecx, ecx
0x180033cf4  cmp     ecx, edx
0x180033cf6  jge     short loc_180033D35
0x180033cf8  movsxd  rdi, ecx
0x180033cfb  movzx   r9d, word ptr [r8+rdi*2]
0x180033d00  test    r9w, r9w
0x180033d04  jz      loc_180033F8E
0x180033d0a  mov     ebx, r9d
0x180033d0d  cmp     r9d, 5Ch ; '\'
0x180033d11  jnz     loc_180033E59
0x180033d17  cmp     r11w, r9w
0x180033d1b  jz      short loc_180033D35
0x180033d1d  movzx   r11d, r9w
0x180033d21  inc     ecx
0x180033d23  jmp     short loc_180033CF4
0x180033d25  lea     rcx, [rax-2]
0x180033d29  test    rdx, rdx
0x180033d2c  cmovnz  rcx, rax
0x180033d30  xor     eax, eax
0x180033d32  mov     [rcx], ax
0x180033d35  movzx   eax, [rbp+640h+var_29E]
0x180033d3c  and     al, 0FCh
0x180033d3e  and     al, 0FCh
0x180033d40  mov     [rbp+640h+var_29E], al
0x180033d46  xor     eax, eax
0x180033d48  mov     [rbp+640h+var_6A0], ax
0x180033d4c  lea     rcx, [rbp+640h+var_240]
0x180033d53  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180033d5a  nop     word ptr [rax+rax+00h]
0x180033d60  inc     rax
0x180033d63  cmp     word ptr [rcx+rax*2], 0
0x180033d68  jnz     short loc_180033D60
0x180033d6a  mov     [rbp+640h+var_6B0], eax
0x180033d6d  lea     rax, [rbp+640h+var_240]
0x180033d74  mov     [rbp+640h+bstrString], rax
0x180033d78  mov     [rsp+740h+var_710], 0
0x180033d7d  lea     rcx, [rsp+740h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180033d82  call    cs:__imp_GetSystemTimeAsFileTime
0x180033d88  xor     eax, eax
0x180033d8a  mov     [rsp+740h+var_700], rax
0x180033d8f  mov     [rsp+740h+var_6F8], eax
0x180033d93  mov     [rsp+740h+var_6F4], ax
0x180033d98  mov     [rsp+740h+lpMem], rax
0x180033d9d  lea     rax, [rbp+640h+var_6B0]
0x180033da1  mov     [rsp+740h+var_6E0], rax
0x180033da6  mov     [rsp+740h+var_720], 0
0x180033dab  lea     r9, [rsp+740h+var_710]
0x180033db0  mov     r8d, 4
0x180033db6  mov     rdx, r14
0x180033db9  mov     rcx, rsi
0x180033dbc  call    ?ProcessValue@TriggersXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z; TriggersXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)
0x180033dc1  test    eax, eax
0x180033dc3  js      loc_180034171
0x180033dc9  mov     rbx, [rsi+418h]
0x180033dd0  mov     eax, [rbx+98h]
0x180033dd6  test    eax, eax
0x180033dd8  jnz     loc_180034189
0x180033dde  mov     edx, [rbx]; struct IErrorInfo *
0x180033de0  lea     r8, __ImageBase
0x180033de7  cmp     edx, 10006h
0x180033ded  jnz     loc_18003400F
0x180033df3  movzx   eax, dx; jumptable 000000018003402B cases 65538-65541
0x180033df6  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180033dfe  add     r8, 200h
0x180033e05  mov     eax, [r8]
0x180033e08  test    eax, eax
0x180033e0a  jz      loc_1800341A2
0x180033e10  mov     rcx, [rbx+10h]
0x180033e14  test    rcx, rcx
0x180033e17  jz      loc_1800341B2
0x180033e1d  mov     rax, [rcx]
0x180033e20  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180033e27  mov     r8, [r8+8]
0x180033e2b  lea     rdx, ChannelPath
0x180033e32  mov     rax, [rax+0D8h]
0x180033e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e3e  mov     ecx, eax
0x180033e40  test    eax, eax
0x180033e42  jns     short loc_180033E76
0x180033e44  cmp     dword ptr [rsi+430h], 0
0x180033e4b  jl      loc_180033ED7
0x180033e51  mov     [rsi+430h], ecx
0x180033e57  jmp     short loc_180033ED7
0x180033e59  sub     ebx, 20h ; ' '
0x180033e5c  jnz     loc_180033F1B
0x180033e62  cmp     r11w, 5Ch ; '\'
0x180033e67  jz      loc_180033D35
0x180033e6d  test    r11w, r11w
0x180033e71  jmp     loc_180033D1B
0x180033e76  jnz     short loc_180033EA1
0x180033e78  mov     rcx, [rbx+10h]
0x180033e7c  test    rcx, rcx
0x180033e7f  jz      loc_1800341BD
0x180033e85  mov     rax, [rcx]
0x180033e88  lea     rdx, [rbp+640h+var_240]
0x180033e8f  mov     rax, [rax+0E0h]
0x180033e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e9b  mov     ecx, eax
0x180033e9d  test    eax, eax
0x180033e9f  js      short loc_180033E44
0x180033ea1  mov     ecx, 1
0x180033ea6  mov     eax, [rbx+98h]
0x180033eac  test    eax, eax
0x180033eae  jnz     loc_1800341C8
0x180033eb4  mov     rcx, [rbx+10h]
0x180033eb8  test    rcx, rcx
0x180033ebb  jz      loc_1800341D5
0x180033ec1  mov     rax, [rcx]
0x180033ec4  mov     rax, [rax+78h]
0x180033ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ecd  mov     ecx, eax
0x180033ecf  test    ecx, ecx
0x180033ed1  js      loc_180033E44
0x180033ed7  mov     r8, [rsp+740h+lpMem]; lpMem
0x180033edc  test    r8, r8
0x180033edf  jz      short loc_180033EF1
0x180033ee1  xor     edx, edx; dwFlags
0x180033ee3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180033eea  call    cs:__imp_HeapFree
0x180033ef0  nop
0x180033ef1  test    [rbp+640h+var_29E], 1
0x180033ef8  jnz     loc_1800341E0
0x180033efe  mov     rcx, [rbp+640h+var_30]
0x180033f05  xor     rcx, rsp; StackCookie
0x180033f08  call    __security_check_cookie
0x180033f0d  add     rsp, 720h
0x180033f14  pop     r14
0x180033f16  pop     rdi
0x180033f17  pop     rsi
0x180033f18  pop     rbx
0x180033f19  pop     rbp
0x180033f1a  retn
0x180033f1b  sub     ebx, 0Eh
0x180033f1e  jz      loc_1800340BC
0x180033f24  sub     ebx, 1
0x180033f27  jz      loc_180033D35
0x180033f2d  cmp     ebx, 0Bh
0x180033f30  jmp     loc_180033D1B
0x180033f35  mov     r9, r10
0x180033f38  lea     rax, asc_1800A3DA8; "\\"
0x180033f3f  mov     rbx, rdx
0x180033f42  lea     r11, [rbp+640h+var_240]
0x180033f49  nop     dword ptr [rax+00000000h]
0x180033f50  test    r9, r9
0x180033f53  jz      short loc_180033F83
0x180033f55  movzx   ecx, word ptr [rax]
0x180033f58  test    cx, cx
0x180033f5b  jz      short loc_180033F7E
0x180033f5d  add     rax, 2
0x180033f61  mov     [r11], cx
0x180033f65  add     r11, 2
0x180033f69  dec     r9
0x180033f6c  sub     rbx, 1
0x180033f70  jnz     short loc_180033F50
0x180033f72  xor     eax, eax
0x180033f74  mov     [r11-2], ax
0x180033f79  jmp     loc_180033D35
0x180033f7e  test    rbx, rbx
0x180033f81  jz      short loc_180033F72
0x180033f83  xor     eax, eax
0x180033f85  mov     [r11], ax
0x180033f89  jmp     loc_180033CEF
0x180033f8e  cmp     r11w, 5Ch ; '\'
0x180033f93  jz      loc_1800340E3
0x180033f99  mov     rcx, rdx
0x180033f9c  lea     rax, [rbp+640h+var_240]
0x180033fa3  cmp     word ptr [rax], 0
0x180033fa7  jz      short loc_180033FB3
0x180033fa9  add     rax, 2
0x180033fad  sub     rcx, 1
0x180033fb1  jnz     short loc_180033FA3
0x180033fb3  mov     r9, rdx
0x180033fb6  sub     r9, rcx
0x180033fb9  xor     eax, eax
0x180033fbb  test    rcx, rcx
0x180033fbe  cmovz   r9, rax
0x180033fc2  jz      loc_180033D35
0x180033fc8  sub     rdx, r9
0x180033fcb  lea     rax, [rbp+640h+var_240]
0x180033fd2  lea     rax, [rax+r9*2]
0x180033fd6  jz      loc_180033D25
0x180033fdc  nop     dword ptr [rax+00h]
0x180033fe0  test    r10, r10
0x180033fe3  jz      loc_180033D25
0x180033fe9  movzx   ecx, word ptr [r8]
0x180033fed  test    cx, cx
0x180033ff0  jz      loc_180033D25
0x180033ff6  add     r8, 2
0x180033ffa  mov     [rax], cx
0x180033ffd  add     rax, 2
0x180034001  dec     r10
0x180034004  sub     rdx, 1
0x180034008  jnz     short loc_180033FE0
0x18003400a  jmp     loc_180033D25
0x18003400f  lea     eax, [rdx-10000h]; switch 6 cases
0x180034015  cmp     eax, 5
0x180034018  ja      def_18003402B; jumptable 000000018003402B default case
0x18003401e  cdqe
0x180034020  mov     ecx, ds:(jpt_18003402B - 180000000h)[r8+rax*4]
0x180034028  add     rcx, r8
0x18003402b  jmp     rcx; switch jump
0x18003402d  xor     r9d, r9d; jumptable 000000018003402B cases 65536,65537
0x180034030  movzx   eax, dx
0x180034033  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r8+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x18003403b  lea     r10, rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180034042  lea     r10, [r10+rax*8]
0x180034046  cmp     r9, rdx
0x180034049  jnb     def_18003402B; jumptable 000000018003402B default case
0x18003404f  mov     r8, r9
0x180034052  shl     r8, 7
0x180034056  add     r8, [r10]
0x180034059  cmp     dword ptr [r8], 4
0x18003405d  jz      loc_180033E10
0x180034063  inc     r9
0x180034066  jmp     short loc_180034046
0x180034068  test    r10, r10
0x18003406b  jz      short loc_180034090
0x18003406d  movzx   r8d, word ptr [rax]
0x180034071  test    r8w, r8w
0x180034075  jz      short loc_18003409A
0x180034077  add     rax, 2
0x18003407b  mov     [rcx], r8w
0x18003407f  add     rcx, 2
0x180034083  dec     r10
0x180034086  sub     rdx, 1
0x18003408a  jnz     short loc_180034068
0x18003408c  sub     rcx, 2
0x180034090  xor     eax, eax
0x180034092  mov     [rcx], ax
0x180034095  jmp     loc_180033D35
0x18003409a  test    rdx, rdx
0x18003409d  jnz     short loc_180034090
0x18003409f  jmp     short loc_18003408C
0x1800340a1  test    eax, eax
0x1800340a3  jle     short loc_1800340AD
0x1800340a5  movzx   eax, ax
0x1800340a8  or      eax, 80070000h
0x1800340ad  mov     edx, eax; int
0x1800340af  mov     rcx, rsi; this
0x1800340b2  call    ?UpdateHR@ServerXMLUpdateHandler@@AEAAXJ@Z; ServerXMLUpdateHandler::UpdateHR(long)
0x1800340b7  jmp     loc_180033EFE
0x1800340bc  cmp     r11w, 2Eh ; '.'
0x1800340c1  jz      loc_180033D35
0x1800340c7  cmp     r11w, 5Ch ; '\'
0x1800340cc  jnz     loc_180033D1D
0x1800340d2  cmp     [r8+rdi*2+2], r11w
0x1800340d8  jz      loc_180033D35
0x1800340de  jmp     loc_180033D1D
0x1800340e3  cmp     ecx, 1
0x1800340e6  jle     loc_180033F99
0x1800340ec  jmp     loc_180033D35
0x1800340f1  lea     rax, asc_1800A3DA8; "\\"
0x1800340f8  lea     rcx, [rbp+640h+var_240]
0x1800340ff  jmp     loc_180034068
0x180034104  test    rbx, rbx
0x180034107  jz      short loc_180034113
0x180034109  mov     rdx, [rbx+30h]
0x18003410d  mov     rdx, [rdx+8]
0x180034111  jmp     short loc_180034160
0x180034113  lea     rcx, [rbp+640h+Uuid]; Uuid
0x180034117  call    cs:__imp_UuidCreate
  ... truncated ...
```

# CCachedINIFile::GetString(ushort const *,ushort const *,ushort const *,CACHEDPRIVATEPROFILEFLAGS,ushort * *)

- ea: `0x18018f860`
- end: `0x18018fe4e`
- name: `?GetString@CCachedINIFile@@QEAAJPEBG00W4CACHEDPRIVATEPROFILEFLAGS@@PEAPEAG@Z`
- size: `1518`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18018f760`
- `0x18019040c`

## callees

- `0x18004d470`
- `0x18004d720`
- `0x18006b970`
- `0x18018f860`
- `0x18018fff0`
- `0x1801901e4`
- `0x1801902dc`
- `0x18019040c`
- `0x1803b1f60`
- `0x1803b2ac0`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x18018f933`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18018fa64`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18018f933`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18018fa64`
- `ntdll!RtlFreeAnsiString` at `0x18018f9c2`
- `ntdll!RtlFreeAnsiString` at `0x18018fb64`
- `ntdll!RtlFreeAnsiString` at `0x18018f9c2`
- `ntdll!RtlFreeAnsiString` at `0x18018fb64`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18018fc98`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18018fc98`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18018fd08`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18018fd08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018fba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018fcca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018fba6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018fcca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018fd17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018fd33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018fd55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018fda3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018fd17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018fd33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018fd55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018fda3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCachedINIFile::GetString(__int64 a1, WCHAR *a2, WCHAR *a3, __int64 a4, char a5, wchar_t **a6)
{
  __int64 v7; // r13
  wchar_t *v8; // r15
  __int64 v9; // r14
  signed int v10; // edi
  int i; // esi
  unsigned __int64 v13; // rbx
  __int64 v14; // rax
  NTSTATUS v15; // eax
  LPARAM v16; // rcx
  LPARAM v17; // r13
  int v18; // r15d
  signed int v19; // r14d
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rsi
  __int64 v23; // rax
  NTSTATUS v24; // eax
  LPARAM v25; // rcx
  LPARAM v26; // r13
  int v27; // r14d
  int j; // edi
  __int64 v29; // r15
  CCachedINIFile *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rdx
  const OLECHAR *v33; // rdi
  unsigned __int64 v34; // rsi
  wchar_t *v35; // rax
  unsigned __int64 v36; // rdx
  OLECHAR *v37; // r8
  __int64 v38; // rcx
  OLECHAR v39; // ax
  __int64 v40; // r9
  OLECHAR *v41; // rcx
  __int64 v42; // rsi
  bool v43; // cf
  DWORD v44; // eax
  DWORD v45; // edi
  void *v46; // rax
  void *v47; // rbx
  size_t v48; // rax
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-49h] BYREF
  struct _STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  struct _STRING AnsiString; // [rsp+70h] [rbp-29h] BYREF
  HDPA hdpa; // [rsp+80h] [rbp-19h]
  UNICODE_STRING p1; // [rsp+88h] [rbp-11h] BYREF
  __int128 v56; // [rsp+98h] [rbp-1h]

  v7 = a1;
  v8 = 0;
  *a6 = 0;
  v9 = *(_QWORD *)(a1 + 80);
  if ( !v9 || !*(_DWORD *)v9 )
    return (unsigned int)-2147467259;
  i = 0;
  DestinationString = 0;
  v13 = -1;
  if ( *(_DWORD *)(a1 + 56) )
  {
    v10 = 0;
  }
  else
  {
    *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
    SourceString.Buffer = a2;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    SourceString.Length = 2 * v14;
    SourceString.MaximumLength = 2 * v14 + 2;
    v15 = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 1u);
    v10 = v15;
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_23;
    v9 = *(_QWORD *)(v7 + 80);
  }
  hdpa = 0;
  v16 = *(int *)(v7 + 56);
  if ( (_DWORD)v16 )
    AnsiString.Buffer = (PCHAR)a2;
  else
    *(_QWORD *)&AnsiString.Length = DestinationString.Buffer;
  v17 = v16;
  v18 = *(_DWORD *)v9;
  for ( i = 0; i < v18; ++i )
  {
    if ( !CCachedINIFile::s_CompareSection(&AnsiString, *(void **)(*(_QWORD *)(v9 + 8) + 8LL * i), v17) )
    {
      if ( i != -1 )
        goto LABEL_20;
      break;
    }
  }
  v10 = -2147467259;
  i = 0;
LABEL_20:
  if ( hdpa )
  {
    DPA_DestroyCallback(hdpa, CQueueItem::AppliesTo, 0);
    v8 = 0;
    hdpa = 0;
    DPA_Destroy(0);
    hdpa = 0;
  }
  else
  {
    v8 = 0;
  }
  v7 = a1;
LABEL_23:
  if ( DestinationString.Buffer )
    RtlFreeAnsiString(&DestinationString);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v19 = -2147467259;
  v20 = *(_QWORD *)(v7 + 80);
  if ( v20 && i >= 0 && i < *(_DWORD *)v20 )
  {
    _mm_lfence();
    v21 = *(_QWORD *)(*(_QWORD *)(v20 + 8) + 8LL * i);
  }
  else
  {
    v21 = 0;
  }
  *(_QWORD *)&DestinationString.Length = v21;
  *(_QWORD *)&SourceString.Length = 0;
  v22 = *(_QWORD *)(v21 + 16);
  if ( !v22 )
    goto LABEL_58;
  AnsiString = 0;
  if ( !*(_DWORD *)(v7 + 56) )
  {
    *(_DWORD *)(&p1.MaximumLength + 1) = 0;
    p1.Buffer = a3;
    v23 = -1;
    do
      ++v23;
    while ( a3[v23] );
    p1.Length = 2 * v23;
    p1.MaximumLength = 2 * v23 + 2;
    v24 = RtlUnicodeStringToAnsiString(&AnsiString, &p1, 1u);
    v19 = v24;
    if ( v24 > 0 )
      v19 = (unsigned __int16)v24 | 0x80070000;
    if ( v19 < 0 )
      goto LABEL_56;
    v22 = *(_QWORD *)(v21 + 16);
  }
  p1 = 0;
  v56 = 0;
  v25 = *(int *)(v7 + 56);
  if ( (_DWORD)v25 )
    p1.Buffer = a3;
  else
    *(_QWORD *)&p1.Length = AnsiString.Buffer;
  v26 = v25;
  v27 = *(_DWORD *)v22;
  for ( j = 0; ; ++j )
  {
    if ( j >= v27 )
      goto LABEL_54;
    v29 = 8LL * j;
    if ( !CCachedINIFile::s_CompareSection(&p1, *(void **)(*(_QWORD *)(v22 + 8) + v29), v26) )
      break;
  }
  if ( j == -1 )
  {
LABEL_54:
    v19 = -2147467259;
    v7 = a1;
    goto LABEL_55;
  }
  v31 = *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 16LL);
  if ( v31 && j >= 0 && j < *(_DWORD *)v31 )
  {
    _mm_lfence();
    v32 = *(_QWORD *)(v29 + *(_QWORD *)(v31 + 8));
  }
  else
  {
    v32 = 0;
  }
  v7 = a1;
  if ( *(_DWORD *)(a1 + 56) )
  {
    v33 = *(const OLECHAR **)(v32 + 24);
    do
      ++v13;
    while ( v33[v13] );
    v34 = v13 + 1;
    if ( v13 + 1 >= v13 )
    {
      *(_QWORD *)&SourceString.Length = 0;
      if ( is_mul_ok(v34, 2u) )
      {
        v35 = (wchar_t *)CoTaskMemAlloc(2 * v34);
        v8 = v35;
        if ( v35 )
          v19 = 0;
        else
          v19 = -2147024882;
        if ( v19 >= 0 )
        {
          if ( (v35 || v13 == -1) && v34 <= 0x7FFFFFFF )
          {
            if ( v13 >= 0x7FFFFFFF )
            {
              if ( v13 != -1 )
                *v35 = 0;
            }
            else
            {
              if ( !v33 )
              {
                v33 = &WindowName;
                v13 = 0;
              }
              if ( v34 )
              {
                v36 = v34;
                v37 = v35;
                v38 = 0;
                do
                {
                  if ( !v13 )
                    break;
                  v39 = *v33;
                  if ( !*v33 )
                    break;
                  ++v33;
                  *v37++ = v39;
                  --v13;
                  ++v38;
                  --v36;
                }
                while ( v36 );
                v40 = v38 - 1;
                if ( v36 )
                  v40 = v38;
                v41 = v37 - 1;
                if ( v36 )
                  v41 = v37;
                *v41 = 0;
                if ( v36 )
                {
                  v43 = v34 == v40;
                  v42 = v34 - v40;
                  if ( !v43 && v42 != 1 )
                    StringExHandleFillBehindNullW(&v8[v40], 2 * v42, 0x300u);
                }
              }
            }
          }
          else
          {
            *v35 = 0;
          }
        }
        goto LABEL_56;
      }
    }
    v19 = -2147024362;
LABEL_55:
    v8 = 0;
    goto LABEL_56;
  }
  v19 = CCachedINIFile::_AnsiToUnicodeWrapper(v30, *(const char **)(v32 + 16), (unsigned __int16 **)&SourceString);
  v8 = *(wchar_t **)&SourceString.Length;
LABEL_56:
  if ( AnsiString.Buffer )
    RtlFreeAnsiString(&AnsiString);
LABEL_58:
  if ( v19 >= 0 )
  {
    if ( (a5 & 1) != 0 )
    {
      *(_QWORD *)&SourceString.Length = 0;
      if ( CCachedINIFile::GetUTF7String((CCachedINIFile *)v7, a2, a3, v8, (unsigned __int16 **)&SourceString) >= 0 )
      {
        CoTaskMemFree(v8);
        v8 = *(wchar_t **)&SourceString.Length;
      }
    }
    if ( (a5 & 2) != 0 )
    {
      v44 = ExpandEnvironmentStringsW(v8, 0, 0);
      v45 = v44;
      if ( !v44 )
      {
        v19 = -2147467259;
        goto LABEL_92;
      }
      *(_QWORD *)&SourceString.Length = 0;
      if ( !is_mul_ok(v44, 2u) )
      {
        v19 = -2147024362;
        CoTaskMemFree(v8);
        return (unsigned int)v19;
      }
      v46 = CoTaskMemAlloc(2LL * v44);
      v47 = v46;
      if ( v46 )
      {
        v48 = SHGetSize(v46);
        memset_0(v47, 0, v48);
        v19 = 0;
      }
      else
      {
        v19 = -2147024882;
      }
      if ( v19 < 0 )
        goto LABEL_92;
      SHExpandEnvironmentStringsW(v8, v47, v45);
      CoTaskMemFree(v8);
      v8 = (wchar_t *)v47;
    }
    *a6 = v8;
    v8 = 0;
LABEL_92:
    CoTaskMemFree(v8);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18018f860  mov     [rsp-8+arg_18], rbx
0x18018f865  push    rbp
0x18018f866  push    rsi
0x18018f867  push    rdi
0x18018f868  push    r12
0x18018f86a  push    r13
0x18018f86c  push    r14
0x18018f86e  push    r15
0x18018f870  lea     rbp, [rsp-17h]
0x18018f875  sub     rsp, 0B0h
0x18018f87c  mov     rax, cs:__security_cookie
0x18018f883  xor     rax, rsp
0x18018f886  mov     [rbp+47h+var_38], rax
0x18018f88a  mov     [rbp+47h+var_A0], r8
0x18018f88e  mov     r12, rdx
0x18018f891  mov     r13, rcx
0x18018f894  mov     [rbp+47h+var_A8], rcx
0x18018f898  mov     rax, [rbp+47h+arg_28]
0x18018f89c  mov     [rbp+47h+var_98], rax
0x18018f8a0  xor     r15d, r15d
0x18018f8a3  mov     [rax], r15
0x18018f8a6  mov     r14, [rcx+50h]
0x18018f8aa  test    r14, r14
0x18018f8ad  jnz     short loc_18018F8DE
0x18018f8af  mov     edi, 80004005h
0x18018f8b4  mov     eax, edi
0x18018f8b6  mov     rcx, [rbp+47h+var_38]
0x18018f8ba  xor     rcx, rsp; StackCookie
0x18018f8bd  call    __security_check_cookie
0x18018f8c2  mov     rbx, [rsp+0E0h+arg_18]
0x18018f8ca  add     rsp, 0B0h
0x18018f8d1  pop     r15
0x18018f8d3  pop     r14
0x18018f8d5  pop     r13
0x18018f8d7  pop     r12
0x18018f8d9  pop     rdi
0x18018f8da  pop     rsi
0x18018f8db  pop     rbp
0x18018f8dc  retn
0x18018f8de  cmp     [r14], r15d
0x18018f8e1  jz      short loc_18018F8AF
0x18018f8e3  mov     esi, r15d
0x18018f8e6  mov     dword ptr [rbp+47h+var_B0], r15d
0x18018f8ea  xorps   xmm0, xmm0
0x18018f8ed  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18018f8f1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18018f8f8  cmp     [rcx+38h], r15d
0x18018f8fc  jnz     loc_18018FD44
0x18018f902  mov     dword ptr [rbp+47h+SourceString+4], r15d
0x18018f906  mov     [rbp+47h+SourceString.Buffer], r12
0x18018f90a  mov     rax, rbx
0x18018f90d  nop     dword ptr [rax]
0x18018f910  inc     rax
0x18018f913  cmp     [rdx+rax*2], si
0x18018f917  jnz     short loc_18018F910
0x18018f919  add     ax, ax
0x18018f91c  mov     [rbp+47h+SourceString.Length], ax
0x18018f920  add     ax, 2
0x18018f924  mov     [rbp+47h+SourceString.MaximumLength], ax
0x18018f928  mov     r8b, 1; AllocateDestinationString
0x18018f92b  lea     rdx, [rbp+47h+SourceString]; SourceString
0x18018f92f  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18018f933  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18018f93a  nop     dword ptr [rax+rax+00h]
0x18018f93f  mov     edi, eax
0x18018f941  test    eax, eax
0x18018f943  jle     short loc_18018F94E
0x18018f945  movzx   edi, ax
0x18018f948  or      edi, 80070000h
0x18018f94e  test    edi, edi
0x18018f950  js      short loc_18018F9B7
0x18018f952  mov     r14, [r13+50h]
0x18018f956  mov     [rbp+47h+hdpa], r15
0x18018f95a  movsxd  rcx, dword ptr [r13+38h]
0x18018f95e  test    ecx, ecx
0x18018f960  jz      loc_18018FB81
0x18018f966  mov     [rbp+47h+AnsiString.Buffer], r12
0x18018f96a  mov     r13, rcx
0x18018f96d  mov     r15d, [r14]
0x18018f970  xor     esi, esi
0x18018f972  cmp     esi, r15d
0x18018f975  jge     short loc_18018F99B
0x18018f977  movsxd  rax, esi
0x18018f97a  mov     rdx, [r14+8]
0x18018f97e  mov     r8, r13; lParam
0x18018f981  mov     rdx, [rdx+rax*8]; p2
0x18018f985  lea     rcx, [rbp+47h+AnsiString]; p1
0x18018f989  call    ?s_CompareSection@CCachedINIFile@@CAHPEBUINISECTION@@0_J@Z; CCachedINIFile::s_CompareSection(INISECTION const *,INISECTION const *,__int64)
0x18018f98e  test    eax, eax
0x18018f990  jz      short loc_18018F996
0x18018f992  inc     esi
0x18018f994  jmp     short loc_18018F972
0x18018f996  cmp     esi, 0FFFFFFFFh
0x18018f999  jnz     short loc_18018F9A3
0x18018f99b  mov     edi, 80004005h
0x18018f9a0  mov     esi, dword ptr [rbp+47h+var_B0]
0x18018f9a3  mov     rcx, [rbp+47h+hdpa]; hdpa
0x18018f9a7  test    rcx, rcx
0x18018f9aa  jnz     loc_18018FE09
0x18018f9b0  xor     r15d, r15d
0x18018f9b3  mov     r13, [rbp+47h+var_A8]
0x18018f9b7  cmp     [rbp+47h+DestinationString.Buffer], 0
0x18018f9bc  jz      short loc_18018F9CE
0x18018f9be  lea     rcx, [rbp+47h+DestinationString]; AnsiString
0x18018f9c2  call    cs:__imp_RtlFreeAnsiString
0x18018f9c9  nop     dword ptr [rax+rax+00h]
0x18018f9ce  test    edi, edi
0x18018f9d0  js      loc_18018F8B4
0x18018f9d6  mov     r14d, 80004005h
0x18018f9dc  mov     rax, [r13+50h]
0x18018f9e0  test    rax, rax
0x18018f9e3  jz      loc_18018FD66
0x18018f9e9  test    esi, esi
0x18018f9eb  js      loc_18018FD66
0x18018f9f1  cmp     esi, [rax]
0x18018f9f3  jge     loc_18018FD66
0x18018f9f9  lfence
0x18018f9fc  movsxd  rcx, esi
0x18018f9ff  mov     rax, [rax+8]
0x18018fa03  mov     rdi, [rax+rcx*8]
0x18018fa07  mov     qword ptr [rbp+47h+DestinationString.Length], rdi
0x18018fa0b  mov     [rbp+47h+var_B0], r15
0x18018fa0f  mov     qword ptr [rbp+47h+SourceString.Length], r15
0x18018fa13  mov     rsi, [rdi+10h]
0x18018fa17  test    rsi, rsi
0x18018fa1a  jz      loc_18018FB70
0x18018fa20  xorps   xmm0, xmm0
0x18018fa23  movups  xmmword ptr [rbp+47h+AnsiString.Length], xmm0
0x18018fa27  cmp     dword ptr [r13+38h], 0
0x18018fa2c  jnz     short loc_18018FA8F
0x18018fa2e  mov     dword ptr [rbp+47h+p1+4], 0
0x18018fa35  mov     rcx, [rbp+47h+var_A0]
0x18018fa39  mov     [rbp+47h+p1.Buffer], rcx
0x18018fa3d  mov     rax, rbx
0x18018fa40  inc     rax
0x18018fa43  cmp     word ptr [rcx+rax*2], 0
0x18018fa48  jnz     short loc_18018FA40
0x18018fa4a  add     ax, ax
0x18018fa4d  mov     [rbp+47h+p1.Length], ax
0x18018fa51  add     ax, 2
0x18018fa55  mov     [rbp+47h+p1.MaximumLength], ax
0x18018fa59  mov     r8b, 1; AllocateDestinationString
0x18018fa5c  lea     rdx, [rbp+47h+p1]; SourceString
0x18018fa60  lea     rcx, [rbp+47h+AnsiString]; DestinationString
0x18018fa64  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18018fa6b  nop     dword ptr [rax+rax+00h]
0x18018fa70  mov     r14d, eax
0x18018fa73  test    eax, eax
0x18018fa75  jle     short loc_18018FA82
0x18018fa77  movzx   r14d, ax
0x18018fa7b  or      r14d, 80070000h
0x18018fa82  test    r14d, r14d
0x18018fa85  js      loc_18018FB59
0x18018fa8b  mov     rsi, [rdi+10h]
0x18018fa8f  xorps   xmm0, xmm0
0x18018fa92  movups  xmmword ptr [rbp+47h+p1.Length], xmm0
0x18018fa96  movups  [rbp+47h+var_48], xmm0
0x18018fa9a  movsxd  rcx, dword ptr [r13+38h]
0x18018fa9e  test    ecx, ecx
0x18018faa0  jz      loc_18018FC6E
0x18018faa6  mov     rax, [rbp+47h+var_A0]
0x18018faaa  mov     [rbp+47h+p1.Buffer], rax
0x18018faae  mov     r13, rcx
0x18018fab1  mov     r14d, [rsi]
0x18018fab4  xor     edi, edi
0x18018fab6  cmp     edi, r14d
0x18018fab9  jge     loc_18018FB4B
0x18018fabf  movsxd  rax, edi
0x18018fac2  lea     r15, ds:0[rax*8]
0x18018faca  mov     rdx, [rsi+8]
0x18018face  mov     r8, r13; lParam
0x18018fad1  mov     rdx, [rdx+r15]; p2
0x18018fad5  lea     rcx, [rbp+47h+p1]; p1
0x18018fad9  call    ?s_CompareSection@CCachedINIFile@@CAHPEBUINISECTION@@0_J@Z; CCachedINIFile::s_CompareSection(INISECTION const *,INISECTION const *,__int64)
0x18018fade  test    eax, eax
0x18018fae0  jz      short loc_18018FAE6
0x18018fae2  inc     edi
0x18018fae4  jmp     short loc_18018FAB6
0x18018fae6  cmp     edi, 0FFFFFFFFh
0x18018fae9  jz      short loc_18018FB4B
0x18018faeb  mov     rax, qword ptr [rbp+47h+DestinationString.Length]
0x18018faef  mov     rax, [rax+10h]
0x18018faf3  test    rax, rax
0x18018faf6  jz      loc_18018FD6E
0x18018fafc  test    edi, edi
0x18018fafe  js      loc_18018FD6E
0x18018fb04  cmp     edi, [rax]
0x18018fb06  jge     loc_18018FD6E
0x18018fb0c  lfence
0x18018fb0f  mov     rax, [rax+8]
0x18018fb13  mov     rdx, [r15+rax]
0x18018fb17  mov     r13, [rbp+47h+var_A8]
0x18018fb1b  cmp     dword ptr [r13+38h], 0
0x18018fb20  jz      loc_18018FDB8
0x18018fb26  mov     rdi, [rdx+18h]
0x18018fb2a  nop     word ptr [rax+rax+00h]
0x18018fb30  inc     rbx
0x18018fb33  cmp     word ptr [rdi+rbx*2], 0
0x18018fb38  jnz     short loc_18018FB30
0x18018fb3a  lea     rsi, [rbx+1]
0x18018fb3e  cmp     rsi, rbx
0x18018fb41  jnb     short loc_18018FB8E
0x18018fb43  mov     r14d, 80070216h
0x18018fb49  jmp     short loc_18018FB55
0x18018fb4b  mov     r14d, 80004005h
0x18018fb51  mov     r13, [rbp+47h+var_A8]
0x18018fb55  mov     r15, [rbp+47h+var_B0]
0x18018fb59  cmp     [rbp+47h+AnsiString.Buffer], 0
0x18018fb5e  jz      short loc_18018FB70
0x18018fb60  lea     rcx, [rbp+47h+AnsiString]; AnsiString
0x18018fb64  call    cs:__imp_RtlFreeAnsiString
0x18018fb6b  nop     dword ptr [rax+rax+00h]
0x18018fb70  test    r14d, r14d
0x18018fb73  jns     loc_18018FC7B
0x18018fb79  mov     eax, r14d
0x18018fb7c  jmp     loc_18018F8B6
0x18018fb81  mov     rax, [rbp+47h+DestinationString.Buffer]
0x18018fb85  mov     qword ptr [rbp+47h+AnsiString.Length], rax
0x18018fb89  jmp     loc_18018F96A
0x18018fb8e  mov     qword ptr [rbp+47h+SourceString.Length], 0
0x18018fb96  mov     eax, 2
0x18018fb9b  mul     rsi
0x18018fb9e  test    rdx, rdx
0x18018fba1  jnz     short loc_18018FB43
0x18018fba3  mov     rcx, rax; cb
0x18018fba6  call    cs:__imp_CoTaskMemAlloc
0x18018fbad  nop     dword ptr [rax+rax+00h]
0x18018fbb2  mov     r15, rax
0x18018fbb5  test    rax, rax
0x18018fbb8  jz      loc_18018FDDF
0x18018fbbe  xor     r14d, r14d
0x18018fbc1  test    r14d, r14d
0x18018fbc4  js      short loc_18018FB59
0x18018fbc6  test    r15, r15
0x18018fbc9  jz      loc_18018FDEA
0x18018fbcf  cmp     rsi, 7FFFFFFFh
0x18018fbd6  ja      loc_18018FDF3
0x18018fbdc  cmp     rbx, 7FFFFFFFh
0x18018fbe3  jnb     loc_18018FE2F
0x18018fbe9  test    rdi, rdi
0x18018fbec  jz      loc_18018FDD1
0x18018fbf2  test    rsi, rsi
0x18018fbf5  jz      loc_18018FB59
0x18018fbfb  mov     rdx, rsi
0x18018fbfe  mov     r8, r15
0x18018fc01  xor     ecx, ecx
0x18018fc03  test    rbx, rbx
0x18018fc06  jz      short loc_18018FC28
0x18018fc08  movzx   eax, word ptr [rdi]
0x18018fc0b  test    ax, ax
0x18018fc0e  jz      short loc_18018FC28
0x18018fc10  add     rdi, 2
0x18018fc14  mov     [r8], ax
0x18018fc18  add     r8, 2
0x18018fc1c  dec     rbx
0x18018fc1f  inc     rcx
0x18018fc22  sub     rdx, 1
0x18018fc26  jnz     short loc_18018FC03
0x18018fc28  lea     r9, [rcx-1]
0x18018fc2c  test    rdx, rdx
0x18018fc2f  cmovnz  r9, rcx
0x18018fc33  lea     rcx, [r8-2]
0x18018fc37  cmovnz  rcx, r8
0x18018fc3b  xor     eax, eax
0x18018fc3d  mov     [rcx], ax
0x18018fc40  test    rdx, rdx
0x18018fc43  jz      loc_18018FB59
0x18018fc49  sub     rsi, r9
0x18018fc4c  cmp     rsi, 1
0x18018fc50  jbe     loc_18018FB59
0x18018fc56  lea     rdx, [rsi+rsi]; cbRemaining
0x18018fc5a  lea     rcx, [r15+r9*2]; pszDestEnd
0x18018fc5e  mov     r8d, 300h; dwFlags
0x18018fc64  call    StringExHandleFillBehindNullW
0x18018fc69  jmp     loc_18018FB59
0x18018fc6e  mov     rax, [rbp+47h+AnsiString.Buffer]
0x18018fc72  mov     qword ptr [rbp+47h+p1.Length], rax
0x18018fc76  jmp     loc_18018FAAE
0x18018fc7b  mov     ebx, dword ptr [rbp+47h+arg_20]
0x18018fc7e  test    bl, 1
0x18018fc81  jnz     loc_18018FD75
0x18018fc87  test    bl, 2
0x18018fc8a  jz      loc_18018FD26
0x18018fc90  xor     r8d, r8d; nSize
0x18018fc93  xor     edx, edx; lpDst
0x18018fc95  mov     rcx, r15; lpSrc
0x18018fc98  call    cs:__imp_ExpandEnvironmentStringsW
0x18018fc9f  nop     dword ptr [rax+rax+00h]
0x18018fca4  mov     edi, eax
0x18018fca6  test    eax, eax
0x18018fca8  jz      loc_18018FE43
0x18018fcae  mov     qword ptr [rbp+47h+SourceString.Length], 0
0x18018fcb6  mov     eax, 2
0x18018fcbb  mul     rdi
0x18018fcbe  test    rdx, rdx
0x18018fcc1  jnz     loc_18018FD4C
0x18018fcc7  mov     rcx, rax; cb
0x18018fcca  call    cs:__imp_CoTaskMemAlloc
0x18018fcd1  nop     dword ptr [rax+rax+00h]
0x18018fcd6  mov     rbx, rax
  ... truncated ...
```

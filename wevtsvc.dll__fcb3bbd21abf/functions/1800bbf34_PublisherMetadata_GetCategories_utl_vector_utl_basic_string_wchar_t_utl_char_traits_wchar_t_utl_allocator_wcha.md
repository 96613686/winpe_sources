# PublisherMetadata::GetCategories(utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &,utl::vector<ulong,utl::allocator<ulong>> &,utl::vector<_GUID,utl::allocator<_GUID>> &,utl::vector<ulong,utl::allocator<ulong>> &)

- ea: `0x1800bbf34`
- end: `0x1800bc45d`
- name: `?GetCategories@PublisherMetadata@@AEAAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAV?$vector@KV?$allocator@K@utl@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@utl@@@3@1@Z`
- size: `1321`
- prototype: `__int64 __fastcall(__int64, __int64 *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x1800bcc50`

## callees

- `0x180004980`
- `0x180014bd0`
- `0x180017b60`
- `0x1800211f8`
- `0x18002d5a4`
- `0x1800335a8`
- `0x1800338c0`
- `0x1800341a4`
- `0x180038e74`
- `0x180092008`
- `0x1800bbf34`
- `0x1800bd3dc`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc3e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc3e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bbffe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bbffe`

## pseudocode

```c
__int64 __fastcall PublisherMetadata::GetCategories(__int64 a1, __int64 *a2, _QWORD *a3, _QWORD *a4, _QWORD *a5)
{
  LPCWSTR *v9; // rbx
  unsigned int v10; // r12d
  unsigned int v11; // eax
  int v12; // edi
  __int64 v13; // rcx
  HMODULE Library; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // r9d
  int StringResource; // eax
  __int64 v19; // rcx
  _WORD **v20; // rdx
  char *v21; // r8
  unsigned int v22; // r12d
  unsigned int *v23; // rax
  unsigned int *v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // ebx
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+30h] [rbp-51h] BYREF
  __int64 v30; // [rsp+40h] [rbp-41h]
  int v31; // [rsp+48h] [rbp-39h]
  __int64 v32; // [rsp+4Ch] [rbp-35h]
  char v33; // [rsp+54h] [rbp-2Dh]
  unsigned int v34; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v35; // [rsp+5Ch] [rbp-25h] BYREF
  __int64 v36; // [rsp+60h] [rbp-21h]
  _WORD *v37; // [rsp+68h] [rbp-19h] BYREF
  _WORD *v38; // [rsp+70h] [rbp-11h]
  HMODULE v39[9]; // [rsp+88h] [rbp+7h] BYREF
  unsigned int v40; // [rsp+E0h] [rbp+5Fh]
  __int64 v41; // [rsp+E0h] [rbp+5Fh]

  v9 = (LPCWSTR *)(a1 + 208);
  v10 = 0;
  if ( !*(_BYTE *)(a1 + 375) )
  {
    v11 = ExpandFilePathsInPlace((void *)(a1 + 208));
    v12 = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_5b779035add530f74e9405630361780f_Traceguids, v11);
      }
      *(_QWORD *)&pExceptionObject = &byte_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v30 = 0;
      v31 = v12;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    *(_BYTE *)(a1 + 375) = 1;
  }
  Library = LoadLibraryExW(*v9, 0, 0x20u);
  v39[0] = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_5b779035add530f74e9405630361780f_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v30 = 0;
    v31 = LastError;
    v32 = 0x274FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v15 = *a2;
  v16 = a2[1];
  a2[1] = *a2;
  utl::_RangeDestroyApc<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
    v13,
    v15,
    (v16 - v15) >> 5);
  a3[1] = *a3;
  a4[1] = *a4;
  a5[1] = *a5;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v37);
  while ( v10 < *(_DWORD *)(a1 + 360) )
  {
    v38 = v37;
    *v37 = 0;
    v40 = v10 + 1;
    LOBYTE(v17) = *(_BYTE *)(a1 + 371);
    StringResource = LoadStringResource((_DWORD)Library, v10 + 1, *(unsigned __int16 *)(a1 + 368), v17, (__int64)&v37);
    if ( StringResource )
    {
      if ( StringResource != -2147024579 )
      {
        if ( StringResource != -2147023081 )
        {
          v26 = (unsigned __int16)StringResource;
          if ( !(_WORD)StringResource )
            v26 = 1287;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_5b779035add530f74e9405630361780f_Traceguids, v26);
          }
          pExceptionObject = 0;
          v30 = 0;
          v31 = v26;
          v32 = 0x292FFFFFFFFLL;
          throw (EvtException *)&pExceptionObject;
        }
        if ( *(_BYTE *)(a1 + 371) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_5b779035add530f74e9405630361780f_Traceguids, 1815);
          }
          pExceptionObject = 0;
          v30 = 0;
          v31 = 1815;
          v32 = 0x28CFFFFFFFFLL;
          throw (EvtException *)&pExceptionObject;
        }
      }
      break;
    }
    if ( (unsigned __int64)(v38 - v37) >= 0x7D0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_5b779035add530f74e9405630361780f_Traceguids, 13);
      }
      pExceptionObject = 0;
      v30 = 0;
      v31 = 13;
      v32 = 0x29AFFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v19 = a2[1];
    if ( v19 == a2[2] )
    {
      v36 = *a2;
      if ( !(unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(a2) )
        goto LABEL_36;
      v21 = (char *)&v37;
      v19 = a2[1];
      if ( (unsigned __int64)&v37 - v36 < v19 - *a2 )
        v21 = (char *)&v37 + *a2 - v36;
      v20 = (_WORD **)v21;
    }
    else
    {
      v20 = &v37;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      v19,
      v20);
    a2[1] += 32;
    v22 = v10 + 1;
    v34 = v22;
    v23 = (unsigned int *)a3[1];
    if ( v23 == (unsigned int *)a3[2] )
    {
      v36 = *a3;
      if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_Grow(a3) )
        goto LABEL_36;
      if ( (unsigned __int64)&v34 - v36 < a3[1] - *a3 )
        v22 = *(unsigned int *)((char *)&v34 + *a3 - v36);
      *(_DWORD *)a3[1] = v22;
    }
    else
    {
      *v23 = v22;
    }
    a3[1] += 4LL;
    if ( a4[1] == a4[2] && !(unsigned __int8)utl::vector<_GUID,utl::allocator<_GUID>>::_Grow(a4) )
    {
LABEL_36:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_5b779035add530f74e9405630361780f_Traceguids, 14);
      }
      pExceptionObject = 0;
      v30 = 0;
      v31 = 14;
      v32 = 0x2A2FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    *(_OWORD *)a4[1] = 0;
    a4[1] += 16LL;
    v10 = v40;
    v35 = v40;
    v24 = (unsigned int *)a5[1];
    if ( v24 == (unsigned int *)a5[2] )
    {
      v41 = *a5;
      if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_Grow(a5) )
        goto LABEL_36;
      if ( (unsigned __int64)&v35 - v41 >= a5[1] - *a5 )
        v25 = v10;
      else
        v25 = *(unsigned int *)((char *)&v35 + *a5 - v41);
      *(_DWORD *)a5[1] = v25;
    }
    else
    {
      *v24 = v40;
    }
    a5[1] += 4LL;
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v37);
  return tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(v39);
}

```

## disassembly

```asm
0x1800bbf34  push    rbp
0x1800bbf36  push    rbx
0x1800bbf37  push    rsi
0x1800bbf38  push    rdi
0x1800bbf39  push    r12
0x1800bbf3b  push    r13
0x1800bbf3d  push    r14
0x1800bbf3f  push    r15
0x1800bbf41  lea     rbp, [rsp-17h]
0x1800bbf46  sub     rsp, 98h
0x1800bbf4d  mov     r13, r9
0x1800bbf50  mov     rsi, r8
0x1800bbf53  mov     r14, rdx
0x1800bbf56  mov     r15, rcx
0x1800bbf59  lea     rbx, [rcx+0D0h]
0x1800bbf60  xor     r12d, r12d
0x1800bbf63  cmp     [rcx+177h], r12b
0x1800bbf6a  jnz     loc_1800BBFF5
0x1800bbf70  mov     rcx, rbx
0x1800bbf73  call    ExpandFilePathsInPlace
0x1800bbf78  mov     edi, eax
0x1800bbf7a  test    eax, eax
0x1800bbf7c  jz      short loc_1800BBFED
0x1800bbf7e  lea     rcx, WPP_GLOBAL_Control
0x1800bbf85  mov     r10, cs:WPP_GLOBAL_Control
0x1800bbf8c  cmp     r10, rcx
0x1800bbf8f  jz      short loc_1800BBFBA
0x1800bbf91  test    dword ptr [r10+1Ch], 10000h
0x1800bbf99  jz      short loc_1800BBFBA
0x1800bbf9b  cmp     byte ptr [r10+19h], 2
0x1800bbfa0  jb      short loc_1800BBFBA
0x1800bbfa2  lea     edx, [r12+23h]
0x1800bbfa7  mov     r9d, eax
0x1800bbfaa  lea     r8, WPP_5b779035add530f74e9405630361780f_Traceguids
0x1800bbfb1  mov     rcx, [r10+10h]
0x1800bbfb5  call    WPP_SF_d
0x1800bbfba  lea     rax, byte_1800EC961
0x1800bbfc1  mov     qword ptr [rbp+4Fh+pExceptionObject], rax
0x1800bbfc5  mov     qword ptr [rbp+4Fh+pExceptionObject+8], r12
0x1800bbfc9  mov     [rbp+4Fh+var_90], r12
0x1800bbfcd  mov     [rbp+4Fh+var_88], edi
0x1800bbfd0  mov     [rbp+4Fh+var_84], 0FFFFFFFFFFFFFFFFh
0x1800bbfd8  mov     [rbp+4Fh+var_7C], r12b
0x1800bbfdc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bbfe3  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800bbfe7  call    _CxxThrowException_0
0x1800bbfed  mov     byte ptr [r15+177h], 1
0x1800bbff5  xor     edx, edx; hFile
0x1800bbff7  lea     r8d, [rdx+20h]; dwFlags
0x1800bbffb  mov     rcx, [rbx]; lpLibFileName
0x1800bbffe  call    cs:__imp_LoadLibraryExW
0x1800bc004  mov     rbx, rax
0x1800bc007  mov     [rbp+4Fh+var_48], rax
0x1800bc00b  test    rax, rax
0x1800bc00e  jz      loc_1800BC3E2
0x1800bc014  mov     rdx, [r14]
0x1800bc017  mov     r8, [r14+8]
0x1800bc01b  mov     [r14+8], rdx
0x1800bc01f  sub     r8, rdx
0x1800bc022  sar     r8, 5
0x1800bc026  call    ??$_RangeDestroyApc@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@0@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64)
0x1800bc02b  mov     rax, [rsi]
0x1800bc02e  mov     [rsi+8], rax
0x1800bc032  mov     rax, [r13+0]
0x1800bc036  mov     [r13+8], rax
0x1800bc03a  mov     rdi, [rbp+4Fh+arg_20]
0x1800bc03e  mov     rax, [rdi]
0x1800bc041  mov     [rdi+8], rax
0x1800bc045  lea     rcx, [rbp+4Fh+var_68]; void *
0x1800bc049  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800bc04e  nop
0x1800bc04f  cmp     r12d, [r15+168h]
0x1800bc056  jnb     loc_1800BC3BB
0x1800bc05c  mov     rcx, [rbp+4Fh+var_68]
0x1800bc060  mov     [rbp+4Fh+var_60], rcx
0x1800bc064  xor     eax, eax
0x1800bc066  mov     [rcx], ax
0x1800bc069  lea     edx, [r12+1]
0x1800bc06e  mov     dword ptr [rbp+4Fh+arg_0], edx
0x1800bc071  lea     rax, [rbp+4Fh+var_68]
0x1800bc075  mov     [rsp+0D0h+var_B0], rax
0x1800bc07a  mov     r9b, [r15+173h]
0x1800bc081  movzx   r8d, word ptr [r15+170h]
0x1800bc089  mov     rcx, rbx
0x1800bc08c  call    LoadStringResource
0x1800bc091  test    eax, eax
0x1800bc093  jnz     loc_1800BC2B5
0x1800bc099  mov     rax, [rbp+4Fh+var_60]
0x1800bc09d  sub     rax, [rbp+4Fh+var_68]
0x1800bc0a1  sar     rax, 1
0x1800bc0a4  cmp     rax, 7D0h
0x1800bc0aa  jnb     loc_1800BC246
0x1800bc0b0  mov     rcx, [r14+8]
0x1800bc0b4  cmp     rcx, [r14+10h]
0x1800bc0b8  jz      short loc_1800BC0C0
0x1800bc0ba  lea     rdx, [rbp+4Fh+var_68]
0x1800bc0be  jmp     short loc_1800BC0FC
0x1800bc0c0  mov     rax, [r14]
0x1800bc0c3  mov     [rbp+4Fh+var_70], rax
0x1800bc0c7  mov     rcx, r14
0x1800bc0ca  call    ?_Grow@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(void)
0x1800bc0cf  test    al, al
0x1800bc0d1  jz      loc_1800BC1D7
0x1800bc0d7  lea     r8, [rbp+4Fh+var_68]
0x1800bc0db  lea     rdx, [rbp+4Fh+var_68]
0x1800bc0df  sub     rdx, [rbp+4Fh+var_70]
0x1800bc0e3  mov     rcx, [r14+8]
0x1800bc0e7  mov     r9, [r14]
0x1800bc0ea  mov     rax, rcx
0x1800bc0ed  sub     rax, r9
0x1800bc0f0  cmp     rdx, rax
0x1800bc0f3  jnb     short loc_1800BC0F9
0x1800bc0f5  lea     r8, [rdx+r9]
0x1800bc0f9  mov     rdx, r8
0x1800bc0fc  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1800bc101  add     qword ptr [r14+8], 20h ; ' '
0x1800bc106  inc     r12d
0x1800bc109  mov     [rbp+4Fh+var_78], r12d
0x1800bc10d  mov     rax, [rsi+8]
0x1800bc111  cmp     rax, [rsi+10h]
0x1800bc115  jz      short loc_1800BC11C
0x1800bc117  mov     [rax], r12d
0x1800bc11a  jmp     short loc_1800BC154
0x1800bc11c  mov     rax, [rsi]
0x1800bc11f  mov     [rbp+4Fh+var_70], rax
0x1800bc123  mov     rcx, rsi
0x1800bc126  call    ?_Grow@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_NXZ; utl::vector<ulong,utl::allocator<ulong>>::_Grow(void)
0x1800bc12b  test    al, al
0x1800bc12d  jz      loc_1800BC1D7
0x1800bc133  lea     rcx, [rbp+4Fh+var_78]
0x1800bc137  sub     rcx, [rbp+4Fh+var_70]
0x1800bc13b  mov     r8, [rsi+8]
0x1800bc13f  mov     rdx, [rsi]
0x1800bc142  mov     rax, r8
0x1800bc145  sub     rax, rdx
0x1800bc148  cmp     rcx, rax
0x1800bc14b  jnb     short loc_1800BC151
0x1800bc14d  mov     r12d, [rcx+rdx]
0x1800bc151  mov     [r8], r12d
0x1800bc154  add     qword ptr [rsi+8], 4
0x1800bc159  mov     rax, [r13+10h]
0x1800bc15d  cmp     [r13+8], rax
0x1800bc161  jnz     short loc_1800BC16F
0x1800bc163  mov     rcx, r13
0x1800bc166  call    ?_Grow@?$vector@U_GUID@@V?$allocator@U_GUID@@@utl@@@utl@@AEAA_NXZ; utl::vector<_GUID,utl::allocator<_GUID>>::_Grow(void)
0x1800bc16b  test    al, al
0x1800bc16d  jz      short loc_1800BC1D7
0x1800bc16f  xorps   xmm0, xmm0
0x1800bc172  mov     rax, [r13+8]
0x1800bc176  movups  xmmword ptr [rax], xmm0
0x1800bc179  add     qword ptr [r13+8], 10h
0x1800bc17e  mov     r12d, dword ptr [rbp+4Fh+arg_0]
0x1800bc182  mov     [rbp+4Fh+var_74], r12d
0x1800bc186  mov     rax, [rdi+8]
0x1800bc18a  cmp     rax, [rdi+10h]
0x1800bc18e  jz      short loc_1800BC195
0x1800bc190  mov     [rax], r12d
0x1800bc193  jmp     short loc_1800BC1CD
0x1800bc195  mov     rax, [rdi]
0x1800bc198  mov     [rbp+4Fh+arg_0], rax
0x1800bc19c  mov     rcx, rdi
0x1800bc19f  call    ?_Grow@?$vector@KV?$allocator@K@utl@@@utl@@AEAA_NXZ; utl::vector<ulong,utl::allocator<ulong>>::_Grow(void)
0x1800bc1a4  test    al, al
0x1800bc1a6  jz      short loc_1800BC1D7
0x1800bc1a8  lea     rcx, [rbp+4Fh+var_74]
0x1800bc1ac  sub     rcx, [rbp+4Fh+arg_0]
0x1800bc1b0  mov     r8, [rdi+8]
0x1800bc1b4  mov     rdx, [rdi]
0x1800bc1b7  mov     rax, r8
0x1800bc1ba  sub     rax, rdx
0x1800bc1bd  cmp     rcx, rax
0x1800bc1c0  jnb     short loc_1800BC1C7
0x1800bc1c2  mov     eax, [rcx+rdx]
0x1800bc1c5  jmp     short loc_1800BC1CA
0x1800bc1c7  mov     eax, r12d
0x1800bc1ca  mov     [r8], eax
0x1800bc1cd  add     qword ptr [rdi+8], 4
0x1800bc1d2  jmp     loc_1800BC04F
0x1800bc1d7  lea     rcx, WPP_GLOBAL_Control
0x1800bc1de  mov     ebx, 0Eh
0x1800bc1e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc1ea  cmp     rax, rcx
0x1800bc1ed  jz      short loc_1800BC214
0x1800bc1ef  test    dword ptr [rax+1Ch], 10000h
0x1800bc1f6  jz      short loc_1800BC214
0x1800bc1f8  cmp     byte ptr [rax+19h], 2
0x1800bc1fc  jb      short loc_1800BC214
0x1800bc1fe  lea     edx, [rbx+1Ah]
0x1800bc201  mov     r9d, ebx
0x1800bc204  lea     r8, WPP_5b779035add530f74e9405630361780f_Traceguids
0x1800bc20b  mov     rcx, [rax+10h]
0x1800bc20f  call    WPP_SF_d
0x1800bc214  xorps   xmm0, xmm0
0x1800bc217  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x1800bc21c  mov     [rbp+4Fh+var_90], 0
0x1800bc224  mov     [rbp+4Fh+var_88], ebx
0x1800bc227  mov     dword ptr [rbp+4Fh+var_84], 0FFFFFFFFh
0x1800bc22e  mov     dword ptr [rbp+4Fh+var_84+4], 2A2h
0x1800bc235  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bc23c  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800bc240  call    _CxxThrowException_0
0x1800bc246  lea     rcx, WPP_GLOBAL_Control
0x1800bc24d  mov     ebx, 0Dh
0x1800bc252  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc259  cmp     rax, rcx
0x1800bc25c  jz      short loc_1800BC283
0x1800bc25e  test    dword ptr [rax+1Ch], 10000h
0x1800bc265  jz      short loc_1800BC283
0x1800bc267  cmp     byte ptr [rax+19h], 2
0x1800bc26b  jb      short loc_1800BC283
0x1800bc26d  lea     edx, [rbx+1Ah]
0x1800bc270  mov     r9d, ebx
0x1800bc273  lea     r8, WPP_5b779035add530f74e9405630361780f_Traceguids
0x1800bc27a  mov     rcx, [rax+10h]
0x1800bc27e  call    WPP_SF_d
0x1800bc283  xorps   xmm0, xmm0
0x1800bc286  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x1800bc28b  mov     [rbp+4Fh+var_90], 0
0x1800bc293  mov     [rbp+4Fh+var_88], ebx
0x1800bc296  mov     dword ptr [rbp+4Fh+var_84], 0FFFFFFFFh
0x1800bc29d  mov     dword ptr [rbp+4Fh+var_84+4], 29Ah
0x1800bc2a4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bc2ab  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800bc2af  call    _CxxThrowException_0
0x1800bc2b5  cmp     eax, 8007013Dh
0x1800bc2ba  jz      loc_1800BC3BB
0x1800bc2c0  cmp     eax, 80070717h
0x1800bc2c5  jz      short loc_1800BC340
0x1800bc2c7  movzx   ebx, ax
0x1800bc2ca  mov     eax, 507h
0x1800bc2cf  test    ebx, ebx
0x1800bc2d1  cmovz   ebx, eax
0x1800bc2d4  lea     rcx, WPP_GLOBAL_Control
0x1800bc2db  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc2e2  cmp     rax, rcx
0x1800bc2e5  jz      short loc_1800BC30E
0x1800bc2e7  test    dword ptr [rax+1Ch], 10000h
0x1800bc2ee  jz      short loc_1800BC30E
0x1800bc2f0  cmp     byte ptr [rax+19h], 2
0x1800bc2f4  jb      short loc_1800BC30E
0x1800bc2f6  mov     edx, 26h ; '&'
0x1800bc2fb  mov     r9d, ebx
0x1800bc2fe  lea     r8, WPP_5b779035add530f74e9405630361780f_Traceguids
0x1800bc305  mov     rcx, [rax+10h]
0x1800bc309  call    WPP_SF_d
0x1800bc30e  xorps   xmm0, xmm0
0x1800bc311  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x1800bc316  mov     [rbp+4Fh+var_90], 0
0x1800bc31e  mov     [rbp+4Fh+var_88], ebx
0x1800bc321  mov     dword ptr [rbp+4Fh+var_84], 0FFFFFFFFh
0x1800bc328  mov     dword ptr [rbp+4Fh+var_84+4], 292h
0x1800bc32f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bc336  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800bc33a  call    _CxxThrowException_0
0x1800bc340  cmp     byte ptr [r15+173h], 0
0x1800bc348  jz      short loc_1800BC3BB
0x1800bc34a  lea     rcx, WPP_GLOBAL_Control
0x1800bc351  mov     ebx, 717h
0x1800bc356  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc35d  cmp     rax, rcx
0x1800bc360  jz      short loc_1800BC389
0x1800bc362  test    dword ptr [rax+1Ch], 10000h
0x1800bc369  jz      short loc_1800BC389
0x1800bc36b  cmp     byte ptr [rax+19h], 2
0x1800bc36f  jb      short loc_1800BC389
0x1800bc371  mov     edx, 25h ; '%'
0x1800bc376  mov     r9d, ebx
0x1800bc379  lea     r8, WPP_5b779035add530f74e9405630361780f_Traceguids
0x1800bc380  mov     rcx, [rax+10h]
0x1800bc384  call    WPP_SF_d
0x1800bc389  xorps   xmm0, xmm0
0x1800bc38c  movdqu  [rbp+4Fh+pExceptionObject], xmm0
0x1800bc391  mov     [rbp+4Fh+var_90], 0
0x1800bc399  mov     [rbp+4Fh+var_88], ebx
0x1800bc39c  mov     dword ptr [rbp+4Fh+var_84], 0FFFFFFFFh
0x1800bc3a3  mov     dword ptr [rbp+4Fh+var_84+4], 28Ch
0x1800bc3aa  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bc3b1  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1800bc3b5  call    _CxxThrowException_0
0x1800bc3bb  lea     rcx, [rbp+4Fh+var_68]; void *
0x1800bc3bf  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800bc3c4  nop
0x1800bc3c5  lea     rcx, [rbp+4Fh+var_48]
0x1800bc3c9  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x1800bc3ce  add     rsp, 98h
0x1800bc3d5  pop     r15
0x1800bc3d7  pop     r14
0x1800bc3d9  pop     r13
0x1800bc3db  pop     r12
0x1800bc3dd  pop     rdi
0x1800bc3de  pop     rsi
0x1800bc3df  pop     rbx
0x1800bc3e0  pop     rbp
0x1800bc3e1  retn
0x1800bc3e2  call    cs:__imp_GetLastError
0x1800bc3e8  nop
0x1800bc3e9  mov     ebx, eax
0x1800bc3eb  mov     eax, 507h
0x1800bc3f0  test    ebx, ebx
0x1800bc3f2  cmovz   ebx, eax
  ... truncated ...
```

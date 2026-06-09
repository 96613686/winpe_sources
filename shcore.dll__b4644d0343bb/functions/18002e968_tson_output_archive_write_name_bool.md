# tson::output_archive::write_name(bool)

- ea: `0x18002e968`
- end: `0x18002ec83`
- name: `?write_name@output_archive@tson@@AEAA_N_N@Z`
- size: `795`
- prototype: `bool __fastcall(tson::output_archive *__hidden this, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e80c`
- `0x18002e8fc`

## callees

- `0x18002dbec`
- `0x18002e4a8`
- `0x18002e968`
- `0x18002ed70`
- `0x18002ee58`
- `0x180038ebc`
- `0x180038f20`
- `0x180067256`
- `0x1800672e8`
- `0x18009341c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002eb17`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002eb73`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002eb17`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002eb73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ea78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ea78`

## pseudocode

```c
char __fastcall tson::output_archive::write_name(tson::output_archive *this, char a2)
{
  char *v2; // rsi
  __int64 v4; // rax
  __int64 v6; // rbx
  tson::write_buffer *v7; // rbx
  __int64 v8; // rbx
  unsigned __int64 v9; // rdx
  char *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  rsize_t v13; // r15
  char *v14; // rax
  char *v15; // rsi
  const void *v16; // r8
  rsize_t v17; // r14
  void *v18; // rbp
  __int64 v19; // rsi
  size_t v20; // rbx
  const void *v21; // r14
  void *v22; // rcx
  size_t v24; // rbp
  __int64 v25; // rcx
  __int64 v26; // rcx
  char v27; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 24;
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
    v2 = &v2[4 * v4 - 4];
  else
    *v2 = 1;
  if ( *((_DWORD *)v2 + 1) == 2 )
  {
    *((_DWORD *)v2 + 1) = 3;
    v26 = *((_QWORD *)this + 18);
    v27 = 3;
    tson::write_buffer::push_back<enum tson::details::archive_marker>(v26, &v27);
    tson::write_buffer::push_back(*((tson::write_buffer **)this + 18), (char *)this + 10, 2u);
    *((_WORD *)this + 5) = 0;
  }
  else if ( !*((_DWORD *)v2 + 1) )
  {
    *((_DWORD *)v2 + 1) = 1;
    v6 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v6 + 2072) < *(_QWORD *)(v6 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v6 + 2072))++ = 1;
    }
  }
  *((_QWORD *)this + 2) = 0;
  if ( *((_DWORD *)v2 + 1) == 3 )
    return 1;
  if ( !a2 )
  {
    if ( !*(_QWORD *)this )
    {
      *((_BYTE *)this + 8) = 1;
      *(_QWORD *)this = "-";
    }
    v7 = (tson::write_buffer *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 2) = *((_QWORD *)v7 + 259) - *((_QWORD *)v7 + 258);
    if ( *((_QWORD *)v7 + 259) < *((_QWORD *)v7 + 260) || tson::write_buffer::reserve(v7, 1u) )
      *(_BYTE *)(*((_QWORD *)v7 + 259))++ = 5;
    v8 = *((_QWORD *)this + 18);
    v9 = *(_QWORD *)(v8 + 2080);
    v10 = *(char **)(v8 + 2072);
    if ( (unsigned __int64)v10 >= v9 )
    {
      v11 = v9 - *(_QWORD *)(v8 + 2064);
      v12 = 1;
      if ( v11 > 1 )
        v12 = v11;
      v13 = 2 * v12;
      v14 = (char *)CoTaskMemAlloc(2 * v12);
      v15 = v14;
      if ( !v14 )
      {
        *(_BYTE *)(v8 + 8) = 1;
        goto LABEL_21;
      }
      v16 = *(const void **)(v8 + 2064);
      v17 = *(_QWORD *)(v8 + 2072) - (_QWORD)v16;
      memcpy_s_1(v14, v13, v16, v17);
      v18 = *(void **)v8;
      if ( *(_QWORD *)v8 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v27);
        CoTaskMemFree(v18);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v27);
      }
      *(_QWORD *)v8 = v15;
      v10 = &v15[v17];
      *(_QWORD *)(v8 + 2072) = &v15[v17];
      *(_QWORD *)(v8 + 2080) = &v15[v13];
      *(_QWORD *)(v8 + 2064) = v15;
    }
    *v10 = *((_BYTE *)this + 8);
    ++*(_QWORD *)(v8 + 2072);
LABEL_21:
    v19 = *((_QWORD *)this + 18);
    v20 = *((unsigned __int8 *)this + 8);
    v21 = *(const void **)this;
    if ( *(_QWORD *)(v19 + 2080) - *(_QWORD *)(v19 + 2072) < v20
      && !tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), *((unsigned __int8 *)this + 8)) )
    {
      goto LABEL_27;
    }
    if ( v20 )
    {
      v22 = *(void **)(v19 + 2072);
      if ( !v22 )
        goto LABEL_24;
      v24 = *(_QWORD *)(v19 + 2080) - (_QWORD)v22;
      if ( v21 && v24 >= v20 )
      {
        memcpy_0(v22, v21, v20);
        goto LABEL_26;
      }
      memset_0(v22, 0, *(_QWORD *)(v19 + 2080) - (_QWORD)v22);
      if ( v21 )
      {
        if ( v24 >= v20 )
          goto LABEL_26;
        *(_DWORD *)_o__errno() = 34;
      }
      else
      {
LABEL_24:
        *(_DWORD *)_o__errno() = 22;
      }
      invalid_parameter_noinfo();
    }
LABEL_26:
    *(_QWORD *)(v19 + 2072) += v20;
LABEL_27:
    *(_QWORD *)this = 0;
    return 1;
  }
  v25 = *((_QWORD *)this + 18);
  *(_QWORD *)this = 0;
  v27 = 6;
  tson::write_buffer::push_back<enum tson::details::archive_marker>(v25, &v27);
  return 0;
}

```

## disassembly

```asm
0x18002e968  mov     [rsp+arg_8], rbx
0x18002e96d  mov     [rsp+arg_10], rbp
0x18002e972  push    rsi
0x18002e973  push    rdi
0x18002e974  push    r13
0x18002e976  push    r14
0x18002e978  push    r15
0x18002e97a  sub     rsp, 20h
0x18002e97e  lea     rsi, [rcx+18h]
0x18002e982  mov     bpl, dl
0x18002e985  mov     rax, [rsi+68h]
0x18002e989  mov     rdi, rcx
0x18002e98c  mov     r13d, 1
0x18002e992  test    rax, rax
0x18002e995  jz      loc_18002EBE7
0x18002e99b  lea     rsi, [rsi+rax*4]
0x18002e99f  add     rsi, 0FFFFFFFFFFFFFFFCh
0x18002e9a3  cmp     dword ptr [rsi+4], 2
0x18002e9a7  jz      loc_18002EBEF
0x18002e9ad  cmp     dword ptr [rsi+4], 0
0x18002e9b1  jnz     short loc_18002E9E3
0x18002e9b3  mov     [rsi+4], r13d
0x18002e9b7  mov     rbx, [rcx+90h]
0x18002e9be  mov     rax, [rbx+820h]
0x18002e9c5  cmp     [rbx+818h], rax
0x18002e9cc  jnb     loc_18002EBAB
0x18002e9d2  mov     rax, [rbx+818h]
0x18002e9d9  mov     [rax], r13b
0x18002e9dc  add     [rbx+818h], r13
0x18002e9e3  mov     qword ptr [rdi+10h], 0
0x18002e9eb  cmp     dword ptr [rsi+4], 3
0x18002e9ef  jz      loc_18002EB36
0x18002e9f5  test    bpl, bpl
0x18002e9f8  jnz     loc_18002EBC3
0x18002e9fe  cmp     qword ptr [rdi], 0
0x18002ea02  jz      loc_18002EC2D
0x18002ea08  mov     rbx, [rdi+90h]
0x18002ea0f  mov     rax, [rbx+818h]
0x18002ea16  sub     rax, [rbx+810h]
0x18002ea1d  mov     [rdi+10h], rax
0x18002ea21  mov     rax, [rbx+820h]
0x18002ea28  cmp     [rbx+818h], rax
0x18002ea2f  jnb     loc_18002EB93
0x18002ea35  mov     rax, [rbx+818h]
0x18002ea3c  mov     byte ptr [rax], 5
0x18002ea3f  add     [rbx+818h], r13
0x18002ea46  mov     rbx, [rdi+90h]
0x18002ea4d  mov     rdx, [rbx+820h]
0x18002ea54  mov     rcx, [rbx+818h]
0x18002ea5b  cmp     rcx, rdx
0x18002ea5e  jb      short loc_18002EAD5
0x18002ea60  sub     rdx, [rbx+810h]
0x18002ea67  mov     rax, r13
0x18002ea6a  cmp     rdx, r13
0x18002ea6d  cmova   rax, rdx
0x18002ea71  lea     r15, [rax+rax]
0x18002ea75  mov     rcx, r15; cb
0x18002ea78  call    cs:__imp_CoTaskMemAlloc
0x18002ea7e  mov     rsi, rax
0x18002ea81  test    rax, rax
0x18002ea84  jz      loc_18002EC62
0x18002ea8a  mov     r8, [rbx+810h]; Source
0x18002ea91  mov     rdx, r15; DestinationSize
0x18002ea94  mov     r14, [rbx+818h]
0x18002ea9b  mov     rcx, rax; Destination
0x18002ea9e  sub     r14, r8
0x18002eaa1  mov     r9, r14; SourceSize
0x18002eaa4  call    memcpy_s_1
0x18002eaa9  mov     rbp, [rbx]
0x18002eaac  test    rbp, rbp
0x18002eaaf  jnz     loc_18002EC40
0x18002eab5  mov     [rbx], rsi
0x18002eab8  lea     rcx, [r14+rsi]
0x18002eabc  lea     rax, [r15+rsi]
0x18002eac0  mov     [rbx+818h], rcx
0x18002eac7  mov     [rbx+820h], rax
0x18002eace  mov     [rbx+810h], rsi
0x18002ead5  mov     al, [rdi+8]
0x18002ead8  mov     [rcx], al
0x18002eada  add     [rbx+818h], r13
0x18002eae1  mov     rsi, [rdi+90h]
0x18002eae8  movzx   ebx, byte ptr [rdi+8]
0x18002eaec  mov     r14, [rdi]
0x18002eaef  mov     rax, [rsi+820h]
0x18002eaf6  sub     rax, [rsi+818h]
0x18002eafd  cmp     rax, rbx
0x18002eb00  jb      loc_18002EC6B
0x18002eb06  test    rbx, rbx
0x18002eb09  jz      short loc_18002EB28
0x18002eb0b  mov     rcx, [rsi+818h]; void *
0x18002eb12  test    rcx, rcx
0x18002eb15  jnz     short loc_18002EB50
0x18002eb17  call    cs:__imp__o__errno
0x18002eb1d  mov     dword ptr [rax], 16h
0x18002eb23  call    _invalid_parameter_noinfo
0x18002eb28  add     [rsi+818h], rbx
0x18002eb2f  mov     qword ptr [rdi], 0
0x18002eb36  mov     al, r13b
0x18002eb39  mov     rbx, [rsp+48h+arg_8]
0x18002eb3e  mov     rbp, [rsp+48h+arg_10]
0x18002eb43  add     rsp, 20h
0x18002eb47  pop     r15
0x18002eb49  pop     r14
0x18002eb4b  pop     r13
0x18002eb4d  pop     rdi
0x18002eb4e  pop     rsi
0x18002eb4f  retn
0x18002eb50  mov     rbp, [rsi+820h]
0x18002eb57  sub     rbp, rcx
0x18002eb5a  test    r14, r14
0x18002eb5d  jnz     short loc_18002EB81
0x18002eb5f  mov     r8, rbp; Size
0x18002eb62  xor     edx, edx; Val
0x18002eb64  call    memset_0
0x18002eb69  test    r14, r14
0x18002eb6c  jz      short loc_18002EB17
0x18002eb6e  cmp     rbp, rbx
0x18002eb71  jnb     short loc_18002EB28
0x18002eb73  call    cs:__imp__o__errno
0x18002eb79  mov     dword ptr [rax], 22h ; '"'
0x18002eb7f  jmp     short loc_18002EB23
0x18002eb81  cmp     rbp, rbx
0x18002eb84  jb      short loc_18002EB5F
0x18002eb86  mov     r8, rbx; Size
0x18002eb89  mov     rdx, r14; Src
0x18002eb8c  call    memcpy_0
0x18002eb91  jmp     short loc_18002EB28
0x18002eb93  mov     rdx, r13; unsigned __int64
0x18002eb96  mov     rcx, rbx; this
0x18002eb99  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18002eb9e  test    al, al
0x18002eba0  jnz     loc_18002EA35
0x18002eba6  jmp     loc_18002EA46
0x18002ebab  mov     rdx, r13; unsigned __int64
0x18002ebae  mov     rcx, rbx; this
0x18002ebb1  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18002ebb6  test    al, al
0x18002ebb8  jnz     loc_18002E9D2
0x18002ebbe  jmp     loc_18002E9E3
0x18002ebc3  mov     rcx, [rdi+90h]
0x18002ebca  lea     rdx, [rsp+48h+arg_0]
0x18002ebcf  mov     qword ptr [rdi], 0
0x18002ebd6  mov     [rsp+48h+arg_0], 6
0x18002ebdb  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x18002ebe0  xor     al, al
0x18002ebe2  jmp     loc_18002EB39
0x18002ebe7  mov     [rsi], r13b
0x18002ebea  jmp     loc_18002E9A3
0x18002ebef  mov     dword ptr [rsi+4], 3
0x18002ebf6  lea     rdx, [rsp+48h+arg_0]
0x18002ebfb  mov     rcx, [rcx+90h]
0x18002ec02  mov     [rsp+48h+arg_0], 3
0x18002ec07  call    ??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z; tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)
0x18002ec0c  mov     rcx, [rdi+90h]; this
0x18002ec13  lea     rdx, [rdi+0Ah]; void *
0x18002ec17  mov     r8d, 2; unsigned __int64
0x18002ec1d  call    ?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z; tson::write_buffer::push_back(void const *,unsigned __int64)
0x18002ec22  xor     eax, eax
0x18002ec24  mov     [rdi+0Ah], ax
0x18002ec28  jmp     loc_18002E9E3
0x18002ec2d  lea     rax, asc_1800AFAE4; "-"
0x18002ec34  mov     [rdi+8], r13b
0x18002ec38  mov     [rdi], rax
0x18002ec3b  jmp     loc_18002EA08
0x18002ec40  lea     rcx, [rsp+48h+arg_0]; this
0x18002ec45  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002ec4a  mov     rcx, rbp; pv
0x18002ec4d  call    cs:__imp_CoTaskMemFree
0x18002ec53  lea     rcx, [rsp+48h+arg_0]; this
0x18002ec58  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002ec5d  jmp     loc_18002EAB5
0x18002ec62  mov     [rbx+8], r13b
0x18002ec66  jmp     loc_18002EAE1
0x18002ec6b  mov     rdx, rbx; unsigned __int64
0x18002ec6e  mov     rcx, rsi; this
0x18002ec71  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18002ec76  test    al, al
0x18002ec78  jz      loc_18002EB2F
0x18002ec7e  jmp     loc_18002EB06
```

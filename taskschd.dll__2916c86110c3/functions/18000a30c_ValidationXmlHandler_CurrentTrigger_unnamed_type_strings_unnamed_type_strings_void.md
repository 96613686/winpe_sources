# ValidationXmlHandler::CurrentTrigger::_unnamed_type_strings_::~_unnamed_type_strings_(void)

- ea: `0x18000a30c`
- end: `0x18000a56c`
- name: `??1_unnamed_type_strings_@CurrentTrigger@ValidationXmlHandler@@QEAA@XZ`
- size: `608`
- prototype: `void __fastcall(ValidationXmlHandler::CurrentTrigger::_unnamed_type_strings_ *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180007d18`
- `0x180008244`

## callees

- `0x180009a78`
- `0x18000a30c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000a3f0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a41b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a446`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a471`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a49c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a4c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a4ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a3f0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a41b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a446`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a471`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a49c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a4c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a4ee`

## pseudocode

```c
void __fastcall ValidationXmlHandler::CurrentTrigger::_unnamed_type_strings_::~_unnamed_type_strings_(
        ValidationXmlHandler::CurrentTrigger::_unnamed_type_strings_ *this)
{
  __int64 v1; // rdi
  __int64 v3; // rdi
  __int64 v4; // rdi
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rdi
  __int64 v8; // rdi
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx

  v1 = *((_QWORD *)this + 6);
  if ( v1 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v1 + 16)) )
    {
      if ( *(_QWORD *)v1 )
      {
        SysFreeString(*(BSTR *)v1);
        *(_QWORD *)v1 = 0;
      }
      v9 = *(void **)(v1 + 8);
      if ( v9 )
      {
        operator delete(v9);
        *(_QWORD *)(v1 + 8) = 0;
      }
      operator delete((void *)v1);
    }
    *((_QWORD *)this + 6) = 0;
  }
  v3 = *((_QWORD *)this + 5);
  if ( v3 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v3 + 16)) )
    {
      if ( *(_QWORD *)v3 )
      {
        SysFreeString(*(BSTR *)v3);
        *(_QWORD *)v3 = 0;
      }
      v10 = *(void **)(v3 + 8);
      if ( v10 )
      {
        operator delete(v10);
        *(_QWORD *)(v3 + 8) = 0;
      }
      operator delete((void *)v3);
    }
    *((_QWORD *)this + 5) = 0;
  }
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v4 + 16)) )
    {
      if ( *(_QWORD *)v4 )
      {
        SysFreeString(*(BSTR *)v4);
        *(_QWORD *)v4 = 0;
      }
      v11 = *(void **)(v4 + 8);
      if ( v11 )
      {
        operator delete(v11);
        *(_QWORD *)(v4 + 8) = 0;
      }
      operator delete((void *)v4);
    }
    *((_QWORD *)this + 4) = 0;
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v5 + 16)) )
    {
      if ( *(_QWORD *)v5 )
      {
        SysFreeString(*(BSTR *)v5);
        *(_QWORD *)v5 = 0;
      }
      v12 = *(void **)(v5 + 8);
      if ( v12 )
      {
        operator delete(v12);
        *(_QWORD *)(v5 + 8) = 0;
      }
      operator delete((void *)v5);
    }
    *((_QWORD *)this + 3) = 0;
  }
  v6 = *((_QWORD *)this + 2);
  if ( v6 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v6 + 16)) )
    {
      if ( *(_QWORD *)v6 )
      {
        SysFreeString(*(BSTR *)v6);
        *(_QWORD *)v6 = 0;
      }
      v13 = *(void **)(v6 + 8);
      if ( v13 )
      {
        operator delete(v13);
        *(_QWORD *)(v6 + 8) = 0;
      }
      operator delete((void *)v6);
    }
    *((_QWORD *)this + 2) = 0;
  }
  v7 = *((_QWORD *)this + 1);
  if ( v7 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v7 + 16)) )
    {
      if ( *(_QWORD *)v7 )
      {
        SysFreeString(*(BSTR *)v7);
        *(_QWORD *)v7 = 0;
      }
      v14 = *(void **)(v7 + 8);
      if ( v14 )
      {
        operator delete(v14);
        *(_QWORD *)(v7 + 8) = 0;
      }
      operator delete((void *)v7);
    }
    *((_QWORD *)this + 1) = 0;
  }
  v8 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v8 + 16)) )
    {
      if ( *(_QWORD *)v8 )
      {
        SysFreeString(*(BSTR *)v8);
        *(_QWORD *)v8 = 0;
      }
      v15 = *(void **)(v8 + 8);
      if ( v15 )
      {
        operator delete(v15);
        *(_QWORD *)(v8 + 8) = 0;
      }
      operator delete((void *)v8);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000a30c  push    rbx
0x18000a30e  push    rbp
0x18000a30f  push    rsi
0x18000a310  push    rdi
0x18000a311  sub     rsp, 28h
0x18000a315  mov     rdi, [rcx+30h]
0x18000a319  or      ebp, 0FFFFFFFFh
0x18000a31c  xor     esi, esi
0x18000a31e  mov     rbx, rcx
0x18000a321  test    rdi, rdi
0x18000a324  jz      short loc_18000A339
0x18000a326  mov     eax, ebp
0x18000a328  lock xadd [rdi+10h], eax
0x18000a32d  add     eax, ebp
0x18000a32f  jz      loc_18000A3E8
0x18000a335  mov     [rbx+30h], rsi
0x18000a339  mov     rdi, [rbx+28h]
0x18000a33d  test    rdi, rdi
0x18000a340  jz      short loc_18000A355
0x18000a342  mov     eax, ebp
0x18000a344  lock xadd [rdi+10h], eax
0x18000a349  add     eax, ebp
0x18000a34b  jz      loc_18000A413
0x18000a351  mov     [rbx+28h], rsi
0x18000a355  mov     rdi, [rbx+20h]
0x18000a359  test    rdi, rdi
0x18000a35c  jz      short loc_18000A371
0x18000a35e  mov     eax, ebp
0x18000a360  lock xadd [rdi+10h], eax
0x18000a365  add     eax, ebp
0x18000a367  jz      loc_18000A43E
0x18000a36d  mov     [rbx+20h], rsi
0x18000a371  mov     rdi, [rbx+18h]
0x18000a375  test    rdi, rdi
0x18000a378  jz      short loc_18000A38D
0x18000a37a  mov     eax, ebp
0x18000a37c  lock xadd [rdi+10h], eax
0x18000a381  add     eax, ebp
0x18000a383  jz      loc_18000A469
0x18000a389  mov     [rbx+18h], rsi
0x18000a38d  mov     rdi, [rbx+10h]
0x18000a391  test    rdi, rdi
0x18000a394  jz      short loc_18000A3A9
0x18000a396  mov     eax, ebp
0x18000a398  lock xadd [rdi+10h], eax
0x18000a39d  add     eax, ebp
0x18000a39f  jz      loc_18000A494
0x18000a3a5  mov     [rbx+10h], rsi
0x18000a3a9  mov     rdi, [rbx+8]
0x18000a3ad  test    rdi, rdi
0x18000a3b0  jz      short loc_18000A3C5
0x18000a3b2  mov     eax, ebp
0x18000a3b4  lock xadd [rdi+10h], eax
0x18000a3b9  add     eax, ebp
0x18000a3bb  jz      loc_18000A4BF
0x18000a3c1  mov     [rbx+8], rsi
0x18000a3c5  mov     rdi, [rbx]
0x18000a3c8  test    rdi, rdi
0x18000a3cb  jz      short loc_18000A3DF
0x18000a3cd  mov     eax, ebp
0x18000a3cf  lock xadd [rdi+10h], eax
0x18000a3d4  add     eax, ebp
0x18000a3d6  jz      loc_18000A4E6
0x18000a3dc  mov     [rbx], rsi
0x18000a3df  add     rsp, 28h
0x18000a3e3  pop     rdi
0x18000a3e4  pop     rsi
0x18000a3e5  pop     rbp
0x18000a3e6  pop     rbx
0x18000a3e7  retn
0x18000a3e8  mov     rcx, [rdi]; bstrString
0x18000a3eb  test    rcx, rcx
0x18000a3ee  jz      short loc_18000A3F9
0x18000a3f0  call    cs:__imp_SysFreeString
0x18000a3f6  mov     [rdi], rsi
0x18000a3f9  mov     rcx, [rdi+8]; void *
0x18000a3fd  test    rcx, rcx
0x18000a400  jnz     loc_18000A50D
0x18000a406  mov     rcx, rdi; void *
0x18000a409  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a40e  jmp     loc_18000A335
0x18000a413  mov     rcx, [rdi]; bstrString
0x18000a416  test    rcx, rcx
0x18000a419  jz      short loc_18000A424
0x18000a41b  call    cs:__imp_SysFreeString
0x18000a421  mov     [rdi], rsi
0x18000a424  mov     rcx, [rdi+8]; void *
0x18000a428  test    rcx, rcx
0x18000a42b  jnz     loc_18000A51B
0x18000a431  mov     rcx, rdi; void *
0x18000a434  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a439  jmp     loc_18000A351
0x18000a43e  mov     rcx, [rdi]; bstrString
0x18000a441  test    rcx, rcx
0x18000a444  jz      short loc_18000A44F
0x18000a446  call    cs:__imp_SysFreeString
0x18000a44c  mov     [rdi], rsi
0x18000a44f  mov     rcx, [rdi+8]; void *
0x18000a453  test    rcx, rcx
0x18000a456  jnz     loc_18000A529
0x18000a45c  mov     rcx, rdi; void *
0x18000a45f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a464  jmp     loc_18000A36D
0x18000a469  mov     rcx, [rdi]; bstrString
0x18000a46c  test    rcx, rcx
0x18000a46f  jz      short loc_18000A47A
0x18000a471  call    cs:__imp_SysFreeString
0x18000a477  mov     [rdi], rsi
0x18000a47a  mov     rcx, [rdi+8]; void *
0x18000a47e  test    rcx, rcx
0x18000a481  jnz     loc_18000A537
0x18000a487  mov     rcx, rdi; void *
0x18000a48a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a48f  jmp     loc_18000A389
0x18000a494  mov     rcx, [rdi]; bstrString
0x18000a497  test    rcx, rcx
0x18000a49a  jz      short loc_18000A4A5
0x18000a49c  call    cs:__imp_SysFreeString
0x18000a4a2  mov     [rdi], rsi
0x18000a4a5  mov     rcx, [rdi+8]; void *
0x18000a4a9  test    rcx, rcx
0x18000a4ac  jnz     loc_18000A545
0x18000a4b2  mov     rcx, rdi; void *
0x18000a4b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a4ba  jmp     loc_18000A3A5
0x18000a4bf  mov     rcx, [rdi]; bstrString
0x18000a4c2  test    rcx, rcx
0x18000a4c5  jz      short loc_18000A4D0
0x18000a4c7  call    cs:__imp_SysFreeString
0x18000a4cd  mov     [rdi], rsi
0x18000a4d0  mov     rcx, [rdi+8]; void *
0x18000a4d4  test    rcx, rcx
0x18000a4d7  jnz     short loc_18000A553
0x18000a4d9  mov     rcx, rdi; void *
0x18000a4dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a4e1  jmp     loc_18000A3C1
0x18000a4e6  mov     rcx, [rdi]; bstrString
0x18000a4e9  test    rcx, rcx
0x18000a4ec  jz      short loc_18000A4F7
0x18000a4ee  call    cs:__imp_SysFreeString
0x18000a4f4  mov     [rdi], rsi
0x18000a4f7  mov     rcx, [rdi+8]; void *
0x18000a4fb  test    rcx, rcx
0x18000a4fe  jnz     short loc_18000A561
0x18000a500  mov     rcx, rdi; void *
0x18000a503  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a508  jmp     loc_18000A3DC
0x18000a50d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a512  mov     [rdi+8], rsi
0x18000a516  jmp     loc_18000A406
0x18000a51b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a520  mov     [rdi+8], rsi
0x18000a524  jmp     loc_18000A431
0x18000a529  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a52e  mov     [rdi+8], rsi
0x18000a532  jmp     loc_18000A45C
0x18000a537  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a53c  mov     [rdi+8], rsi
0x18000a540  jmp     loc_18000A487
0x18000a545  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a54a  mov     [rdi+8], rsi
0x18000a54e  jmp     loc_18000A4B2
0x18000a553  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a558  mov     [rdi+8], rsi
0x18000a55c  jmp     loc_18000A4D9
0x18000a561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a566  mov     [rdi+8], rsi
0x18000a56a  jmp     short loc_18000A500
```

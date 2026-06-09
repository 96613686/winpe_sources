# EmailHelper::HTMLStreamWToPlainTextStreamW(IStream *,IStream * *)

- ea: `0x1800714d0`
- end: `0x180071600`
- name: `?HTMLStreamWToPlainTextStreamW@EmailHelper@@YAJPEAUIStream@@PEAPEAU2@@Z`
- size: `304`
- prototype: `int(EmailHelper *__hidden this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800f87b4`

## callees

- `0x18006f0a8`
- `0x180071228`
- `0x1800714d0`
- `0x1800786b8`
- `0x1800977ac`

## import_xrefs

- `UserDataTypeHelperUtil!ReadStreamContent` at `0x180071504`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x180071504`
- `UserDataTypeHelperUtil!StreamFromStringW` at `0x180071566`
- `UserDataTypeHelperUtil!StreamFromStringW` at `0x180071566`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800715cf`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800715cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180071550`
- `OLEAUT32!__imp_SysFreeString` at `0x180071587`
- `OLEAUT32!__imp_SysFreeString` at `0x1800715a3`
- `OLEAUT32!__imp_SysFreeString` at `0x180071550`
- `OLEAUT32!__imp_SysFreeString` at `0x180071587`
- `OLEAUT32!__imp_SysFreeString` at `0x1800715a3`

## pseudocode

```c
__int64 __fastcall EmailHelper::HTMLStreamWToPlainTextStreamW(EmailHelper *this, LPSTREAM *a2, struct IStream **a3)
{
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // r8
  unsigned int v8; // ebx
  OLECHAR *v9; // rbx
  int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // edi
  HRESULT StreamOnHGlobal; // eax
  __int64 v15; // r8
  void *Block; // [rsp+48h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  Block = 0;
  v5 = tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>((__int64)&Block);
  if ( (int)ReadStreamContent(this, v5, 0xFFFFFFFFLL) >= 0 && Block )
  {
    bstrString = 0;
    v6 = ParsePlainTextFromHtml(Block, &bstrString);
    v8 = v6;
    if ( v6 < 0 )
    {
      Log_HREvent_1((unsigned int)v6, 1, v7, 544);
      SysFreeString(bstrString);
LABEL_15:
      if ( Block )
        operator delete(Block);
      return v8;
    }
    v9 = bstrString;
    v10 = StreamFromStringW(bstrString, a2);
    v12 = v10;
    if ( v10 < 0 )
    {
      Log_HREvent_1((unsigned int)v10, 1, v11, 545);
      SysFreeString(v9);
      if ( Block )
        operator delete(Block);
      return v12;
    }
    SysFreeString(v9);
  }
  else
  {
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a2);
    v8 = StreamOnHGlobal;
    if ( StreamOnHGlobal < 0 )
    {
      Log_HREvent_1((unsigned int)StreamOnHGlobal, 1, v15, 539);
      goto LABEL_15;
    }
  }
  if ( Block )
    operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x1800714d0  mov     [rsp+arg_0], rbx
0x1800714d5  push    rdi
0x1800714d6  sub     rsp, 30h
0x1800714da  mov     rbx, rcx
0x1800714dd  mov     qword ptr [rdx], 0
0x1800714e4  lea     rcx, [rsp+38h+Block]
0x1800714e9  mov     [rsp+38h+Block], 0
0x1800714f2  mov     rdi, rdx
0x1800714f5  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x1800714fa  mov     rdx, rax
0x1800714fd  or      r8d, 0FFFFFFFFh
0x180071501  mov     rcx, rbx
0x180071504  call    cs:__imp_ReadStreamContent
0x18007150a  test    eax, eax
0x18007150c  js      loc_1800715C5
0x180071512  mov     rcx, [rsp+38h+Block]
0x180071517  test    rcx, rcx
0x18007151a  jz      loc_1800715C5
0x180071520  lea     rdx, [rsp+38h+bstrString]
0x180071525  mov     [rsp+38h+bstrString], 0
0x18007152e  call    ParsePlainTextFromHtml
0x180071533  mov     ebx, eax
0x180071535  test    eax, eax
0x180071537  jns     short loc_18007155B
0x180071539  mov     edx, 1
0x18007153e  mov     r9d, 220h
0x180071544  mov     ecx, eax
0x180071546  call    Log_HREvent_1
0x18007154b  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180071550  call    cs:__imp_SysFreeString
0x180071556  jmp     loc_1800715ED
0x18007155b  mov     rbx, [rsp+38h+bstrString]
0x180071560  mov     rdx, rdi
0x180071563  mov     rcx, rbx
0x180071566  call    cs:__imp_StreamFromStringW
0x18007156c  mov     edi, eax
0x18007156e  test    eax, eax
0x180071570  jns     short loc_1800715A0
0x180071572  mov     edx, 1
0x180071577  mov     r9d, 221h
0x18007157d  mov     ecx, eax
0x18007157f  call    Log_HREvent_1
0x180071584  mov     rcx, rbx; bstrString
0x180071587  call    cs:__imp_SysFreeString
0x18007158d  mov     rcx, [rsp+38h+Block]; Block
0x180071592  test    rcx, rcx
0x180071595  jz      short loc_18007159C
0x180071597  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007159c  mov     eax, edi
0x18007159e  jmp     short loc_1800715BA
0x1800715a0  mov     rcx, rbx; bstrString
0x1800715a3  call    cs:__imp_SysFreeString
0x1800715a9  mov     rcx, [rsp+38h+Block]; Block
0x1800715ae  test    rcx, rcx
0x1800715b1  jz      short loc_1800715B8
0x1800715b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800715b8  xor     eax, eax
0x1800715ba  mov     rbx, [rsp+38h+arg_0]
0x1800715bf  add     rsp, 30h
0x1800715c3  pop     rdi
0x1800715c4  retn
0x1800715c5  mov     r8, rdi; ppstm
0x1800715c8  mov     edx, 1; fDeleteOnRelease
0x1800715cd  xor     ecx, ecx; hGlobal
0x1800715cf  call    cs:__imp_CreateStreamOnHGlobal
0x1800715d5  mov     ebx, eax
0x1800715d7  test    eax, eax
0x1800715d9  jns     short loc_1800715A9
0x1800715db  mov     edx, 1
0x1800715e0  mov     r9d, 21Bh
0x1800715e6  mov     ecx, eax
0x1800715e8  call    Log_HREvent_1
0x1800715ed  mov     rcx, [rsp+38h+Block]; Block
0x1800715f2  test    rcx, rcx
0x1800715f5  jz      short loc_1800715FC
0x1800715f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800715fc  mov     eax, ebx
0x1800715fe  jmp     short loc_1800715BA
```

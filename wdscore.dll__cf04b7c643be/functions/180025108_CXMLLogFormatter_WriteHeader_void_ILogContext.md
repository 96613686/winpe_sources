# CXMLLogFormatter::WriteHeader(void *,ILogContext *)

- ea: `0x180025108`
- end: `0x180025261`
- name: `?WriteHeader@CXMLLogFormatter@@AEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800242b0`

## callees

- `0x18002309c`
- `0x180023204`
- `0x180023380`
- `0x180025108`
- `0x18002a010`

## string_xrefs

- `0x180025115`: `<xml xmlns:s="uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C14882"\n xmlns:dt="uuid:C2F41010-65B3-11d1-A29F-00AA00C14882"\n xmlns:rs="urn:schemas-microsoft-com:rowset"\n xmlns:z="#RowsetSchema">\n<s:Schema id="RowsetSchema">\n<s:ElementType name="row" content="eltOnly" rs:updatable="true">\n`

## pseudocode

```c
_BOOL8 __fastcall CXMLLogFormatter::WriteHeader(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rax
  int v5; // esi
  unsigned int v6; // ebp
  unsigned int i; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // esi
  __int64 v12; // r8
  int v13; // edx
  int v14; // edx
  int v15; // edx
  const char *v16; // rax
  __int64 *v18; // [rsp+30h] [rbp-68h] BYREF
  int v19; // [rsp+38h] [rbp-60h]
  __int64 v20; // [rsp+3Ch] [rbp-5Ch]
  const char *v21; // [rsp+48h] [rbp-50h]
  const char *v22; // [rsp+50h] [rbp-48h]
  __int128 v23; // [rsp+58h] [rbp-40h]

  v18 = a3;
  v21 = "<xml xmlns:s=\"uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C14882\"\n"
        " xmlns:dt=\"uuid:C2F41010-65B3-11d1-A29F-00AA00C14882\"\n"
        " xmlns:rs=\"urn:schemas-microsoft-com:rowset\"\n"
        " xmlns:z=\"#RowsetSchema\">\n"
        "<s:Schema id=\"RowsetSchema\">\n"
        "<s:ElementType name=\"row\" content=\"eltOnly\" rs:updatable=\"true\">\n";
  v22 = "</s:ElementType>\n</s:Schema>\n<rs:data>\n";
  v3 = *a3;
  v20 = 0;
  v23 = 0;
  v5 = 120 * (*(__int64 (__fastcall **)(__int64 *))(v3 + 56))(a3);
  v6 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 56))(a3);
  for ( i = 0; i < v6; ++i )
  {
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a3 + 48))(a3, i);
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v8 + 2 * v9) );
    v5 += v9;
  }
  v19 = v5 + 2;
  if ( !(unsigned int)CLogEntryBuilder::BeginEntry((CLogEntryBuilder *)&v18) )
    return 0;
  v10 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 56))(a3);
  while ( v10 < v11 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a3 + 48))(a3, v10);
    v13 = *(_DWORD *)(v12 + 520);
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          if ( v15 == 1 )
            v16 = "dateTime";
          else
            v16 = (const char *)&byte_180030077;
        }
        else
        {
          v16 = "hexBinary";
        }
      }
      else
      {
        v16 = "int";
      }
    }
    else
    {
      v16 = "string";
    }
    if ( !CLogEntryBuilder::Printf(
            (CLogEntryBuilder *)&v18,
            "<s:AttributeType name=\"%S\" rs:number=\"%d\">\n<s:datatype dt:type=\"%s\"/>\n</s:AttributeType>\n",
            (const wchar_t *)v12,
            v10,
            v16) )
      return 0;
    ++v10;
  }
  return (unsigned int)CLogEntryBuilder::EndEntry((CLogEntryBuilder *)&v18) != 0;
}

```

## disassembly

```asm
0x180025108  mov     r11, rsp
0x18002510b  push    rbx
0x18002510c  push    rbp
0x18002510d  push    rsi
0x18002510e  push    rdi
0x18002510f  push    r14
0x180025111  sub     rsp, 70h
0x180025115  lea     rax, aXmlXmlnsSUuidB; "<xml xmlns:s=\"uuid:BDC6E3F0-6DA3-11d1-"...
0x18002511c  mov     [r11-68h], r8
0x180025120  mov     [r11-50h], rax
0x180025124  xorps   xmm0, xmm0
0x180025127  lea     rax, aSElementtypeSS; "</s:ElementType>\n</s:Schema>\n<rs:data"...
0x18002512e  xor     r14d, r14d
0x180025131  mov     [r11-48h], rax
0x180025135  mov     rcx, r8
0x180025138  mov     rax, [r8]
0x18002513b  mov     rdi, r8
0x18002513e  mov     [r11-5Ch], r14
0x180025142  movdqu  [rsp+98h+var_40], xmm0
0x180025148  mov     rax, [rax+38h]
0x18002514c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025151  imul    esi, eax, 78h ; 'x'
0x180025154  mov     rcx, rdi
0x180025157  mov     rax, [rdi]
0x18002515a  mov     rax, [rax+38h]
0x18002515e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025163  mov     ebp, eax
0x180025165  mov     ebx, r14d
0x180025168  test    eax, eax
0x18002516a  jz      short loc_180025193
0x18002516c  mov     rcx, [rdi]
0x18002516f  mov     edx, ebx
0x180025171  mov     rax, [rcx+30h]
0x180025175  mov     rcx, rdi
0x180025178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002517d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180025181  inc     rcx
0x180025184  cmp     [rax+rcx*2], r14w
0x180025189  jnz     short loc_180025181
0x18002518b  add     esi, ecx
0x18002518d  inc     ebx
0x18002518f  cmp     ebx, ebp
0x180025191  jb      short loc_18002516C
0x180025193  lea     eax, [rsi+2]
0x180025196  lea     rcx, [rsp+98h+var_68]; this
0x18002519b  mov     [rsp+98h+var_60], eax
0x18002519f  call    ?BeginEntry@CLogEntryBuilder@@QEAAHXZ; CLogEntryBuilder::BeginEntry(void)
0x1800251a4  test    eax, eax
0x1800251a6  jz      loc_180025253
0x1800251ac  mov     rax, [rdi]
0x1800251af  mov     rcx, rdi
0x1800251b2  mov     ebx, r14d
0x1800251b5  mov     rax, [rax+38h]
0x1800251b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251be  mov     esi, eax
0x1800251c0  cmp     ebx, esi
0x1800251c2  jnb     short loc_18002523D
0x1800251c4  mov     rcx, [rdi]
0x1800251c7  mov     edx, ebx
0x1800251c9  mov     rax, [rcx+30h]
0x1800251cd  mov     rcx, rdi
0x1800251d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251d5  mov     r8, rax
0x1800251d8  mov     edx, [rax+208h]
0x1800251de  test    edx, edx
0x1800251e0  jz      short loc_180025215
0x1800251e2  sub     edx, 1
0x1800251e5  jz      short loc_18002520C
0x1800251e7  sub     edx, 1
0x1800251ea  jz      short loc_180025203
0x1800251ec  cmp     edx, 1
0x1800251ef  jz      short loc_1800251FA
0x1800251f1  lea     rax, byte_180030077
0x1800251f8  jmp     short loc_18002521C
0x1800251fa  lea     rax, aDatetime; "dateTime"
0x180025201  jmp     short loc_18002521C
0x180025203  lea     rax, aHexbinary; "hexBinary"
0x18002520a  jmp     short loc_18002521C
0x18002520c  lea     rax, aInt; "int"
0x180025213  jmp     short loc_18002521C
0x180025215  lea     rax, aString; "string"
0x18002521c  mov     r9d, ebx
0x18002521f  mov     [rsp+98h+var_78], rax
0x180025224  lea     rdx, aSAttributetype; "<s:AttributeType name=\"%S\" rs:number="...
0x18002522b  lea     rcx, [rsp+98h+var_68]; this
0x180025230  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x180025235  test    eax, eax
0x180025237  jz      short loc_180025253
0x180025239  inc     ebx
0x18002523b  jmp     short loc_1800251C0
0x18002523d  lea     rcx, [rsp+98h+var_68]; this
0x180025242  call    ?EndEntry@CLogEntryBuilder@@QEAAHXZ; CLogEntryBuilder::EndEntry(void)
0x180025247  test    eax, eax
0x180025249  mov     ecx, r14d
0x18002524c  setnz   cl
0x18002524f  mov     eax, ecx
0x180025251  jmp     short loc_180025255
0x180025253  xor     eax, eax
0x180025255  add     rsp, 70h
0x180025259  pop     r14
0x18002525b  pop     rdi
0x18002525c  pop     rsi
0x18002525d  pop     rbp
0x18002525e  pop     rbx
0x18002525f  retn
```

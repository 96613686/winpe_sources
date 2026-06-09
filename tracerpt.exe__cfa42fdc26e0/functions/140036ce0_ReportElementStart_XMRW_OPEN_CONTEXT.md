# ReportElementStart(_XMRW_OPEN_CONTEXT *)

- ea: `0x140036ce0`
- end: `0x140037047`
- name: `?ReportElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140032dcc`

## callees

- `0x140002730`
- `0x140016808`
- `0x14002c4d4`
- `0x140030910`
- `0x14003694c`
- `0x140036a60`
- `0x140036b34`
- `0x140036ce0`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ReportElementStart(struct _XMRW_OPEN_CONTEXT *a1)
{
  bool v1; // zf
  __int64 v3; // rsi
  _DWORD *v4; // rbx
  unsigned int v5; // eax
  int v6; // ecx
  int v7; // ecx
  unsigned int v8; // eax
  int i; // eax
  __int64 v10; // rcx
  struct _UNICODE_STRING v11; // xmm0
  char v12; // al
  __int64 result; // rax
  unsigned int v14; // r14d
  __int64 v15; // rcx
  WCHAR *v16; // [rsp+20h] [rbp-48h] BYREF
  WCHAR *v17; // [rsp+28h] [rbp-40h] BYREF
  struct _UNICODE_STRING v18; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING v19; // [rsp+40h] [rbp-28h]
  struct _UNICODE_STRING v20; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+38h] BYREF
  int v22; // [rsp+A8h] [rbp+40h] BYREF
  unsigned int v23; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int v24; // [rsp+B8h] [rbp+50h] BYREF

  v1 = *((_DWORD *)a1 + 12) == 1;
  v16 = 0;
  v22 = 0;
  v19 = 0;
  v21 = 0;
  if ( !v1 )
    return 0;
  v3 = *((_QWORD *)a1 + 3);
  if ( *((_QWORD *)a1 + 8) )
  {
    if ( !*((_BYTE *)a1 + 120) )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v3 + 168LL))(*((_QWORD *)a1 + 3), &v21);
      PrintMessage(0x3F3u, v21);
      return 3221745152LL;
    }
    return 0;
  }
  v4 = operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    return 8;
  v5 = 16;
  v6 = 0;
  do
  {
    ++v6;
    v5 >>= 1;
  }
  while ( v5 );
  v4[14] = v6;
  *((_QWORD *)v4 + 6) = &RptStringHashTable<256>::`vftable';
  v7 = 0;
  v8 = 256;
  *((_QWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 11) = 0;
  do
  {
    ++v7;
    v8 >>= 1;
  }
  while ( v8 );
  v4[28] = v7;
  *((_QWORD *)v4 + 13) = &RptStringHashTable<256>::`vftable';
  *((_QWORD *)v4 + 19) = 0;
  *((_QWORD *)v4 + 18) = 0;
  v4[42] = 31678523;
  *((_QWORD *)v4 + 24) = 0;
  *((_BYTE *)v4 + 200) = 0;
  *((_OWORD *)v4 + 11) = 0;
  *((_BYTE *)v4 + 208) = 0;
  *((_QWORD *)v4 + 3) = v4 + 4;
  *((_QWORD *)v4 + 2) = v4 + 4;
  *((_QWORD *)v4 + 5) = v4 + 8;
  *((_QWORD *)v4 + 4) = v4 + 8;
  v4[41] = 25;
  v4[40] = 0;
  *((_QWORD *)v4 + 1) = v4;
  *(_QWORD *)v4 = v4;
  HashTable<RPT_TID,0,1>::Init(v4 + 12);
  HashTable<RPT_TID,0,1>::Init(v4 + 26);
  *((_QWORD *)a1 + 8) = v4;
  for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 64LL))(v3);
        ;
        i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 72LL))(v3) )
  {
    v14 = i;
    if ( i )
      break;
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v3 + 112LL))(v3, &v16, &v22);
    v10 = *((_QWORD *)a1 + 3);
    v19.Buffer = v16;
    v17 = 0;
    v19.MaximumLength = 2 * v22;
    v19.Length = 2 * v22;
    v23 = 0;
    v18 = 0;
    (*(void (__fastcall **)(__int64, WCHAR **, unsigned int *))(*(_QWORD *)v10 + 128LL))(v10, &v17, &v23);
    v11 = v19;
    v18.Buffer = v17;
    v20 = v19;
    v18.MaximumLength = 2 * v23;
    v18.Length = 2 * v23;
    if ( EqualString(&v20, L"name", 0) )
    {
      v12 = *((_BYTE *)v4 + 208);
      v24 = 0;
      if ( (v12 & 4) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v24);
        PrintMessage(0x3EBu, v24);
        result = 3221745153LL;
      }
      else
      {
        *((_BYTE *)v4 + 200) = 1;
        *((_BYTE *)v4 + 208) = v12 | 4;
        RPT_STRING::operator=((__int64)(v4 + 42), (const void **)&v18);
        result = 0;
      }
    }
    else
    {
      v20 = v11;
      if ( EqualString(&v20, L"version", 0) )
      {
        result = ReportAttributeVersion(a1, &v18, (struct _TRACERPT_REPORT *)v4);
      }
      else
      {
        v20 = v11;
        if ( !EqualString(&v20, L"threshold", 0) )
          continue;
        result = ReportAttributeThreshold(a1, &v18, (struct _TRACERPT_REPORT *)v4);
      }
    }
    if ( (_DWORD)result )
      return result;
  }
  if ( i >= 0 )
  {
    if ( (v4[52] & 5) == 5 )
    {
      return 0;
    }
    else
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 168LL))(v3, &v21);
      if ( (v4[52] & 4) == 0 )
        PrintMessage(0x3F5u, v21);
      if ( (v4[52] & 1) == 0 )
        PrintMessage(0x3FEu, v21);
      return 3221745169LL;
    }
  }
  else
  {
    v15 = *((_QWORD *)a1 + 3);
    v23 = 0;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 168LL))(v15, &v23);
    PrintMessage(0x3E9u, v23, v14);
    return v14;
  }
}

```

## disassembly

```asm
0x140036ce0  push    rbp
0x140036ce2  push    rbx
0x140036ce3  push    rsi
0x140036ce4  push    rdi
0x140036ce5  push    r14
0x140036ce7  push    r15
0x140036ce9  mov     rbp, rsp
0x140036cec  sub     rsp, 68h
0x140036cf0  xor     r15d, r15d
0x140036cf3  xorps   xmm0, xmm0
0x140036cf6  cmp     dword ptr [rcx+30h], 1
0x140036cfa  mov     rdi, rcx
0x140036cfd  mov     [rbp+var_48], r15
0x140036d01  mov     [rbp+arg_8], r15d
0x140036d05  movups  [rbp+var_28], xmm0
0x140036d09  mov     [rbp+arg_0], r15d
0x140036d0d  jnz     loc_140037038
0x140036d13  mov     rsi, [rcx+18h]
0x140036d17  cmp     [rcx+40h], r15
0x140036d1b  jnz     loc_140037008
0x140036d21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140036d28  mov     ecx, 0D8h; unsigned __int64
0x140036d2d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140036d32  mov     rbx, rax
0x140036d35  test    rax, rax
0x140036d38  jz      loc_140037001
0x140036d3e  lea     eax, [r15+10h]
0x140036d42  mov     ecx, r15d
0x140036d45  inc     ecx
0x140036d47  shr     eax, 1
0x140036d49  jnz     short loc_140036D45
0x140036d4b  lea     rax, ??_7?$RptStringHashTable@$0BAA@@@6B@; const RptStringHashTable<256>::`vftable'
0x140036d52  mov     [rbx+38h], ecx
0x140036d55  mov     [rbx+30h], rax
0x140036d59  mov     ecx, r15d
0x140036d5c  mov     eax, 100h
0x140036d61  mov     [rbx+60h], r15
0x140036d65  mov     [rbx+58h], r15
0x140036d69  inc     ecx
0x140036d6b  shr     eax, 1
0x140036d6d  jnz     short loc_140036D69
0x140036d6f  mov     [rbx+70h], ecx
0x140036d72  lea     rax, ??_7?$RptStringHashTable@$0BAA@@@6B@; const RptStringHashTable<256>::`vftable'
0x140036d79  mov     [rbx+68h], rax
0x140036d7d  lea     rcx, [rbx+30h]
0x140036d81  mov     [rbx+98h], r15
0x140036d88  lea     rax, [rbx+10h]
0x140036d8c  mov     [rbx+90h], r15
0x140036d93  xorps   xmm0, xmm0
0x140036d96  mov     dword ptr [rbx+0A8h], 1E3603Bh
0x140036da0  mov     [rbx+0C0h], r15
0x140036da7  mov     [rbx+0C8h], r15b
0x140036dae  movups  xmmword ptr [rbx+0B0h], xmm0
0x140036db5  mov     [rbx+0D0h], r15b
0x140036dbc  mov     [rax+8], rax
0x140036dc0  mov     [rax], rax
0x140036dc3  lea     rax, [rbx+20h]
0x140036dc7  mov     [rax+8], rax
0x140036dcb  mov     [rax], rax
0x140036dce  mov     dword ptr [rbx+0A4h], 19h
0x140036dd8  mov     [rbx+0A0h], r15d
0x140036ddf  mov     [rbx+8], rbx
0x140036de3  mov     [rbx], rbx
0x140036de6  call    ?Init@?$HashTable@VRPT_TID@@$0A@$00@@QEAAKXZ; HashTable<RPT_TID,0,1>::Init(void)
0x140036deb  lea     rcx, [rbx+68h]
0x140036def  call    ?Init@?$HashTable@VRPT_TID@@$0A@$00@@QEAAKXZ; HashTable<RPT_TID,0,1>::Init(void)
0x140036df4  mov     [rdi+40h], rbx
0x140036df8  mov     rax, [rsi]
0x140036dfb  mov     rax, [rax+40h]
0x140036dff  jmp     loc_140036F5A
0x140036e04  inc     dword ptr [rdi+2Ch]
0x140036e07  lea     r8, [rbp+arg_8]
0x140036e0b  mov     rax, [rsi]
0x140036e0e  lea     rdx, [rbp+var_48]
0x140036e12  mov     rcx, rsi
0x140036e15  mov     rax, [rax+70h]
0x140036e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036e1e  mov     rax, [rbp+var_48]
0x140036e22  lea     r8, [rbp+arg_10]
0x140036e26  mov     rcx, [rdi+18h]
0x140036e2a  lea     rdx, [rbp+var_40]
0x140036e2e  mov     qword ptr [rbp+var_28+8], rax
0x140036e32  xorps   xmm0, xmm0
0x140036e35  movzx   eax, word ptr [rbp+arg_8]
0x140036e39  add     ax, ax
0x140036e3c  mov     [rbp+var_40], r15
0x140036e40  mov     word ptr [rbp+var_28+2], ax
0x140036e44  mov     word ptr [rbp+var_28], ax
0x140036e48  mov     [rbp+arg_10], r15d
0x140036e4c  movups  xmmword ptr [rbp+var_38.Length], xmm0
0x140036e50  mov     rax, [rcx]
0x140036e53  mov     rax, [rax+80h]
0x140036e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036e5f  mov     rax, [rbp+var_40]
0x140036e63  lea     rdx, aName_0; "name"
0x140036e6a  movaps  xmm0, [rbp+var_28]
0x140036e6e  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING
0x140036e72  mov     [rbp+var_38.Buffer], rax
0x140036e76  xor     r8d, r8d; unsigned __int8
0x140036e79  movzx   eax, word ptr [rbp+arg_10]
0x140036e7d  add     ax, ax
0x140036e80  movdqa  xmmword ptr [rbp+var_18.Length], xmm0
0x140036e85  mov     [rbp+var_38.MaximumLength], ax
0x140036e89  mov     [rbp+var_38.Length], ax
0x140036e8d  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140036e92  test    al, al
0x140036e94  jz      short loc_140036EF3
0x140036e96  mov     al, [rbx+0D0h]
0x140036e9c  mov     [rbp+arg_18], r15d
0x140036ea0  test    al, 4
0x140036ea2  jz      short loc_140036ECF
0x140036ea4  mov     rcx, [rdi+18h]
0x140036ea8  lea     rdx, [rbp+arg_18]
0x140036eac  mov     rax, [rcx]
0x140036eaf  mov     rax, [rax+0A8h]
0x140036eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ebb  mov     edx, [rbp+arg_18]
0x140036ebe  mov     ecx, 3EBh; unsigned int
0x140036ec3  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140036ec8  mov     eax, 0C007EE01h
0x140036ecd  jmp     short loc_140036F4B
0x140036ecf  or      al, 4
0x140036ed1  mov     byte ptr [rbx+0C8h], 1
0x140036ed8  lea     rcx, [rbx+0A8h]
0x140036edf  mov     [rbx+0D0h], al
0x140036ee5  lea     rdx, [rbp+var_38]
0x140036ee9  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x140036eee  mov     eax, r15d
0x140036ef1  jmp     short loc_140036F4B
0x140036ef3  xor     r8d, r8d; unsigned __int8
0x140036ef6  movdqa  xmmword ptr [rbp+var_18.Length], xmm0
0x140036efb  lea     rdx, aVersion; "version"
0x140036f02  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING
0x140036f06  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140036f0b  test    al, al
0x140036f0d  jz      short loc_140036F20
0x140036f0f  mov     r8, rbx; struct _TRACERPT_REPORT *
0x140036f12  lea     rdx, [rbp+var_38]; struct _UNICODE_STRING *
0x140036f16  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140036f19  call    ?ReportAttributeVersion@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_REPORT@@@Z; ReportAttributeVersion(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_REPORT *)
0x140036f1e  jmp     short loc_140036F4B
0x140036f20  xor     r8d, r8d; unsigned __int8
0x140036f23  movdqa  xmmword ptr [rbp+var_18.Length], xmm0
0x140036f28  lea     rdx, aThreshold; "threshold"
0x140036f2f  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING
0x140036f33  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140036f38  test    al, al
0x140036f3a  jz      short loc_140036F53
0x140036f3c  mov     r8, rbx; struct _TRACERPT_REPORT *
0x140036f3f  lea     rdx, [rbp+var_38]; struct _UNICODE_STRING *
0x140036f43  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140036f46  call    ?ReportAttributeThreshold@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_REPORT@@@Z; ReportAttributeThreshold(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_REPORT *)
0x140036f4b  test    eax, eax
0x140036f4d  jnz     loc_14003703A
0x140036f53  mov     rax, [rsi]
0x140036f56  mov     rax, [rax+48h]
0x140036f5a  mov     rcx, rsi
0x140036f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f62  mov     r14d, eax
0x140036f65  test    eax, eax
0x140036f67  jz      loc_140036E04
0x140036f6d  test    eax, eax
0x140036f6f  jns     short loc_140036FA4
0x140036f71  mov     rcx, [rdi+18h]
0x140036f75  lea     rdx, [rbp+arg_10]
0x140036f79  mov     [rbp+arg_10], r15d
0x140036f7d  mov     rax, [rcx]
0x140036f80  mov     rax, [rax+0A8h]
0x140036f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f8c  mov     edx, [rbp+arg_10]
0x140036f8f  mov     r8d, r14d
0x140036f92  mov     ecx, 3E9h; unsigned int
0x140036f97  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140036f9c  mov     eax, r14d
0x140036f9f  jmp     loc_14003703A
0x140036fa4  mov     al, [rbx+0D0h]
0x140036faa  and     al, 5
0x140036fac  cmp     al, 5
0x140036fae  jnz     short loc_140036FB8
0x140036fb0  mov     eax, r15d
0x140036fb3  jmp     loc_14003703A
0x140036fb8  mov     rax, [rsi]
0x140036fbb  lea     rdx, [rbp+arg_0]
0x140036fbf  mov     rcx, rsi
0x140036fc2  mov     rax, [rax+0A8h]
0x140036fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036fce  test    byte ptr [rbx+0D0h], 4
0x140036fd5  jnz     short loc_140036FE4
0x140036fd7  mov     edx, [rbp+arg_0]
0x140036fda  mov     ecx, 3F5h; unsigned int
0x140036fdf  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140036fe4  test    byte ptr [rbx+0D0h], 1
0x140036feb  jnz     short loc_140036FFA
0x140036fed  mov     edx, [rbp+arg_0]
0x140036ff0  mov     ecx, 3FEh; unsigned int
0x140036ff5  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140036ffa  mov     eax, 0C007EE11h
0x140036fff  jmp     short loc_14003703A
0x140037001  mov     eax, 8
0x140037006  jmp     short loc_14003703A
0x140037008  cmp     [rcx+78h], r15b
0x14003700c  jnz     short loc_140037038
0x14003700e  mov     rax, [rsi]
0x140037011  lea     rdx, [rbp+arg_0]
0x140037015  mov     rcx, rsi
0x140037018  mov     rax, [rax+0A8h]
0x14003701f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037024  mov     edx, [rbp+arg_0]
0x140037027  mov     ecx, 3F3h; unsigned int
0x14003702c  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140037031  mov     eax, 0C007EE00h
0x140037036  jmp     short loc_14003703A
0x140037038  xor     eax, eax
0x14003703a  add     rsp, 68h
0x14003703e  pop     r15
0x140037040  pop     r14
0x140037042  pop     rdi
0x140037043  pop     rsi
0x140037044  pop     rbx
0x140037045  pop     rbp
0x140037046  retn
```

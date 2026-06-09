# XML_RENDERER::AppendNamespacePrefixes(DAV_NAMESPACE_SET *)

- ea: `0x180014404`
- end: `0x1800145a0`
- name: `?AppendNamespacePrefixes@XML_RENDERER@@AEAAJPEAVDAV_NAMESPACE_SET@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, struct DAV_NAMESPACE_SET *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180015790`
- `0x1800158a8`

## callees

- `0x180004474`
- `0x180014404`
- `0x18001c550`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800144e3`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800144f6`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800144e3`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800144f6`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18001452a`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18001452a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001455c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014566`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014570`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001455c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014566`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014570`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014445`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001444f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001445a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014445`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001444f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001445a`

## string_xrefs

- `0x180014506`: ` xmlns:%s="%s"`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendNamespacePrefixes(XML_RENDERER *this, struct DAV_NAMESPACE_SET *a2)
{
  int v3; // edi
  unsigned int v5; // edx
  unsigned __int64 v6; // rcx
  __int64 i; // rbx
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // rax
  struct STATIC_WSTRING_HASH_RECORD *Next; // rax
  unsigned __int64 v13; // [rsp+20h] [rbp-99h] BYREF
  unsigned int v14; // [rsp+28h] [rbp-91h]
  int v15; // [rsp+2Ch] [rbp-8Dh]
  __int64 v16; // [rsp+30h] [rbp-89h]
  _BYTE v17[56]; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v18[32]; // [rsp+70h] [rbp-49h] BYREF
  const char *v19; // [rsp+90h] [rbp-29h]
  _BYTE v20[32]; // [rsp+A8h] [rbp-11h] BYREF
  const char *v21; // [rsp+C8h] [rbp+Fh]

  v16 = 0;
  v3 = 0;
  STRA::STRA((STRA *)v20);
  STRA::STRA((STRA *)v18);
  STRA::STRA((STRA *)v17);
  v5 = 0;
  v15 = 0;
  do
  {
    v6 = *((_QWORD *)a2 + v5 + 1);
    if ( v6 )
      break;
    ++v5;
  }
  while ( v5 < 0x83 );
  v13 = v6;
  v14 = v5;
  for ( i = (v6 - 8) & ((unsigned __int128)-(__int128)v6 >> 64); i; i = ((unsigned __int64)Next - 8)
                                                                      & -(__int64)(Next != 0) )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)i + 32LL))(i) )
    {
      v8 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(__int64))i)(i);
      v9 = v8;
      if ( v8 )
      {
        if ( *v8 )
        {
          v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 8LL))(i);
          v3 = STRA::CopyWToUTF8Unescaped((STRA *)v20, v10);
          if ( v3 < 0 )
            break;
          v3 = STRA::CopyWToUTF8Unescaped((STRA *)v18, v9);
          if ( v3 < 0 )
            break;
          v3 = SAFE_snprintf((struct STRA *)v17, " xmlns:%s=\"%s\"", v21, v19);
          if ( v3 < 0 )
            break;
          v3 = STRA::Append((XML_RENDERER *)((char *)this + 24), (const struct STRA *)v17);
          if ( v3 < 0 )
            break;
        }
      }
    }
    Next = STATIC_WSTRING_HASH::FindNext(
             (struct DAV_NAMESPACE_SET *)((char *)a2 + 8),
             (struct STATIC_WSTRING_HASH_ITER *)&v13);
  }
  STRA::~STRA((STRA *)v17);
  STRA::~STRA((STRA *)v18);
  STRA::~STRA((STRA *)v20);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180014404  mov     [rsp-8+arg_10], rbx
0x180014409  mov     [rsp-8+arg_18], rsi
0x18001440e  push    rbp
0x18001440f  push    rdi
0x180014410  push    r12
0x180014412  push    r14
0x180014414  push    r15
0x180014416  lea     rbp, [rsp-37h]
0x18001441b  sub     rsp, 0F0h
0x180014422  mov     rax, cs:__security_cookie
0x180014429  xor     rax, rsp
0x18001442c  mov     [rbp+57h+var_30], rax
0x180014430  mov     r15, rcx
0x180014433  xor     r12d, r12d
0x180014436  lea     rcx, [rbp+57h+var_68]
0x18001443a  mov     [rsp+110h+var_E0], r12
0x18001443f  mov     edi, r12d
0x180014442  mov     r14, rdx
0x180014445  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18001444b  lea     rcx, [rbp+57h+var_A0]
0x18001444f  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014455  lea     rcx, [rsp+110h+var_D8]
0x18001445a  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014460  mov     edx, r12d
0x180014463  mov     [rsp+110h+var_E4], r12d
0x180014468  mov     eax, edx
0x18001446a  mov     rcx, [r14+rax*8+8]
0x18001446f  test    rcx, rcx
0x180014472  jnz     short loc_18001447E
0x180014474  inc     edx
0x180014476  cmp     edx, 83h
0x18001447c  jb      short loc_180014468
0x18001447e  lea     rax, [rcx-8]
0x180014482  mov     [rsp+110h+var_F0], rcx
0x180014487  neg     rcx
0x18001448a  mov     [rsp+110h+var_E8], edx
0x18001448e  sbb     rbx, rbx
0x180014491  and     rbx, rax
0x180014494  jz      loc_180014557
0x18001449a  mov     rax, [rbx]
0x18001449d  mov     rcx, rbx
0x1800144a0  mov     rax, [rax+20h]
0x1800144a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144a9  test    eax, eax
0x1800144ab  jnz     loc_180014536
0x1800144b1  mov     rax, [rbx]
0x1800144b4  mov     rcx, rbx
0x1800144b7  mov     rax, [rax]
0x1800144ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144bf  mov     rsi, rax
0x1800144c2  test    rax, rax
0x1800144c5  jz      short loc_180014536
0x1800144c7  cmp     [rax], r12w
0x1800144cb  jz      short loc_180014536
0x1800144cd  mov     rax, [rbx]
0x1800144d0  mov     rcx, rbx
0x1800144d3  mov     rax, [rax+8]
0x1800144d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144dc  mov     rdx, rax
0x1800144df  lea     rcx, [rbp+57h+var_68]
0x1800144e3  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x1800144e9  mov     edi, eax
0x1800144eb  test    eax, eax
0x1800144ed  js      short loc_180014557
0x1800144ef  mov     rdx, rsi
0x1800144f2  lea     rcx, [rbp+57h+var_A0]
0x1800144f6  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x1800144fc  mov     edi, eax
0x1800144fe  test    eax, eax
0x180014500  js      short loc_180014557
0x180014502  mov     r9, [rbp+57h+var_80]
0x180014506  lea     rdx, aXmlnsSS; " xmlns:%s=\"%s\""
0x18001450d  mov     r8, [rbp+57h+var_48]
0x180014511  lea     rcx, [rsp+110h+var_D8]; struct STRA *
0x180014516  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x18001451b  mov     edi, eax
0x18001451d  test    eax, eax
0x18001451f  js      short loc_180014557
0x180014521  lea     rcx, [r15+18h]
0x180014525  lea     rdx, [rsp+110h+var_D8]
0x18001452a  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180014530  mov     edi, eax
0x180014532  test    eax, eax
0x180014534  js      short loc_180014557
0x180014536  lea     rdx, [rsp+110h+var_F0]; struct STATIC_WSTRING_HASH_ITER *
0x18001453b  lea     rcx, [r14+8]; this
0x18001453f  call    ?FindNext@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEAUSTATIC_WSTRING_HASH_ITER@@@Z; STATIC_WSTRING_HASH::FindNext(STATIC_WSTRING_HASH_ITER *)
0x180014544  lea     rcx, [rax-8]
0x180014548  neg     rax
0x18001454b  sbb     rbx, rbx
0x18001454e  and     rbx, rcx
0x180014551  jnz     loc_18001449A
0x180014557  lea     rcx, [rsp+110h+var_D8]
0x18001455c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014562  lea     rcx, [rbp+57h+var_A0]
0x180014566  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001456c  lea     rcx, [rbp+57h+var_68]
0x180014570  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014576  mov     eax, edi
0x180014578  mov     rcx, [rbp+57h+var_30]
0x18001457c  xor     rcx, rsp; StackCookie
0x18001457f  call    __security_check_cookie
0x180014584  lea     r11, [rsp+110h+var_20]
0x18001458c  mov     rbx, [r11+40h]
0x180014590  mov     rsi, [r11+48h]
0x180014594  mov     rsp, r11
0x180014597  pop     r15
0x180014599  pop     r14
0x18001459b  pop     r12
0x18001459d  pop     rdi
0x18001459e  pop     rbp
0x18001459f  retn
```

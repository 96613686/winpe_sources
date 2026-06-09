# DAV_AUTH_RULES::Initialize(IHttpContext *,INativeConfigurationElement *,INativeSectionException * *)

- ea: `0x180001d8c`
- end: `0x180001f7d`
- name: `?Initialize@DAV_AUTH_RULES@@QEAAJPEAVIHttpContext@@PEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(DAV_AUTH_RULES *__hidden this, struct IHttpContext *, struct INativeConfigurationElement *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x1800111f4`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x180001c5c`
- `0x180001d8c`
- `0x180001f84`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180001ee6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001ee6`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180001e4e`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180001e4e`

## string_xrefs

- `0x180001daa`: `defaultAccess`

## pseudocode

```c
__int64 __fastcall DAV_AUTH_RULES::Initialize(
        DAV_AUTH_RULES *this,
        struct IHttpContext *a2,
        struct INativeConfigurationElement *a3,
        struct INativeSectionException **a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v7)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD); // rax
  int v8; // edi
  unsigned int *v9; // r15
  unsigned int i; // esi
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  const unsigned __int16 *v14; // [rsp+70h] [rbp+40h] BYREF
  struct IHttpContext *v15; // [rsp+78h] [rbp+48h] BYREF
  struct INativeConfigurationElement *v16; // [rsp+88h] [rbp+58h] BYREF

  v16 = (struct INativeConfigurationElement *)a4;
  v15 = a2;
  v4 = *(_QWORD *)a3;
  v15 = 0;
  v16 = 0;
  v7 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(v4 + 48);
  v14 = 0;
  v8 = v7(a3, L"defaultAccess", (char *)this + 80, 0, 0);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a3 + 72LL))(
           a3,
           L"allowNonMimeMapFiles",
           (char *)this + 84,
           0,
           0);
    if ( v8 >= 0 )
    {
      if ( !*((_DWORD *)this + 21)
        || (v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a3 + 64LL))(
                   a3,
                   L"defaultMimeType",
                   &v14,
                   0,
                   0),
            v8 >= 0)
        && (v8 = STRA::CopyW((DAV_AUTH_RULES *)((char *)this + 24), v14), v8 >= 0) )
      {
        v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, struct IHttpContext **))(*(_QWORD *)a3 + 40LL))(
               a3,
               &v15);
        if ( v8 >= 0 )
        {
          v9 = (unsigned int *)((char *)this + 16);
          v8 = (*(__int64 (__fastcall **)(struct IHttpContext *, char *))(*(_QWORD *)v15 + 24LL))(
                 v15,
                 (char *)this + 16);
          if ( v8 >= 0 )
          {
            for ( i = 0; i < *v9; ++i )
            {
              v8 = (*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v15 + 32LL))(
                     v15,
                     i,
                     &v16);
              if ( v8 < 0 )
                break;
              v11 = operator new(0x88u);
              v12 = v11;
              if ( v11 )
              {
                v11[14] = 0;
                v11[15] = 0;
                STRU::STRU((STRU *)(v11 + 16));
                *(_QWORD *)v12 = 0;
                *((_QWORD *)v12 + 1) = 0;
                *((_QWORD *)v12 + 5) = 0;
                *((_QWORD *)v12 + 3) = 0;
                *((_QWORD *)v12 + 6) = 0;
                v12[30] = 0;
                v8 = DAV_AUTH_RULES_ENTRY::Initialize((DAV_AUTH_RULES_ENTRY *)v12, v16);
                if ( v8 < 0 )
                {
                  DAV_AUTH_RULES_ENTRY::~DAV_AUTH_RULES_ENTRY((DAV_AUTH_RULES_ENTRY *)v12);
                  operator delete(v12);
                }
                else
                {
                  **((_QWORD **)this + 1) = v12;
                  *((_QWORD *)this + 1) = v12;
                }
              }
              else
              {
                v8 = -2147024888;
              }
              (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v16 + 16LL))(v16);
              v16 = 0;
              if ( v8 < 0 )
                break;
            }
          }
          (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180001d8c  mov     [rsp-38h+arg_18], r9
0x180001d91  mov     [rsp-38h+arg_8], rdx
0x180001d96  push    rbp
0x180001d97  push    rbx
0x180001d98  push    rsi
0x180001d99  push    rdi
0x180001d9a  push    r12
0x180001d9c  push    r14
0x180001d9e  push    r15
0x180001da0  mov     rbp, rsp
0x180001da3  sub     rsp, 30h
0x180001da7  mov     rax, [r8]
0x180001daa  lea     rdx, aDefaultaccess; "defaultAccess"
0x180001db1  xor     r12d, r12d
0x180001db4  mov     rbx, r8
0x180001db7  mov     r14, rcx
0x180001dba  mov     [rbp+arg_8], r12
0x180001dbe  lea     r8, [rcx+50h]
0x180001dc2  mov     [rbp+arg_18], r12
0x180001dc6  mov     rax, [rax+30h]
0x180001dca  xor     r9d, r9d
0x180001dcd  mov     rcx, rbx
0x180001dd0  mov     [rbp+arg_0], r12
0x180001dd4  mov     [rsp+30h+var_10], r12
0x180001dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dde  mov     edi, eax
0x180001de0  test    eax, eax
0x180001de2  js      loc_180001F6C
0x180001de8  mov     rax, [rbx]
0x180001deb  lea     r8, [r14+54h]
0x180001def  xor     r9d, r9d
0x180001df2  mov     [rsp+30h+var_10], r12
0x180001df7  lea     rdx, aAllownonmimema; "allowNonMimeMapFiles"
0x180001dfe  mov     rcx, rbx
0x180001e01  mov     rax, [rax+48h]
0x180001e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e0a  mov     edi, eax
0x180001e0c  test    eax, eax
0x180001e0e  js      loc_180001F6C
0x180001e14  cmp     [r14+54h], r12d
0x180001e18  jz      short loc_180001E5E
0x180001e1a  mov     rax, [rbx]
0x180001e1d  lea     r8, [rbp+arg_0]
0x180001e21  xor     r9d, r9d
0x180001e24  mov     [rsp+30h+var_10], r12
0x180001e29  lea     rdx, aDefaultmimetyp; "defaultMimeType"
0x180001e30  mov     rcx, rbx
0x180001e33  mov     rax, [rax+40h]
0x180001e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e3c  mov     edi, eax
0x180001e3e  test    eax, eax
0x180001e40  js      loc_180001F6C
0x180001e46  mov     rdx, [rbp+arg_0]
0x180001e4a  lea     rcx, [r14+18h]
0x180001e4e  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180001e54  mov     edi, eax
0x180001e56  test    eax, eax
0x180001e58  js      loc_180001F6C
0x180001e5e  mov     rax, [rbx]
0x180001e61  lea     rdx, [rbp+arg_8]
0x180001e65  mov     rcx, rbx
0x180001e68  mov     rax, [rax+28h]
0x180001e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e71  mov     edi, eax
0x180001e73  test    eax, eax
0x180001e75  js      loc_180001F6C
0x180001e7b  mov     rcx, [rbp+arg_8]
0x180001e7f  lea     r15, [r14+10h]
0x180001e83  mov     rdx, r15
0x180001e86  mov     rax, [rcx]
0x180001e89  mov     rax, [rax+18h]
0x180001e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e92  mov     edi, eax
0x180001e94  test    eax, eax
0x180001e96  js      loc_180001F5C
0x180001e9c  mov     esi, r12d
0x180001e9f  cmp     [r15], r12d
0x180001ea2  jbe     loc_180001F5C
0x180001ea8  mov     rcx, [rbp+arg_8]
0x180001eac  lea     r8, [rbp+arg_18]
0x180001eb0  mov     edx, esi
0x180001eb2  mov     rax, [rcx]
0x180001eb5  mov     rax, [rax+20h]
0x180001eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ebe  mov     edi, eax
0x180001ec0  test    eax, eax
0x180001ec2  js      loc_180001F5C
0x180001ec8  mov     ecx, 88h; Size
0x180001ecd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ed2  mov     rbx, rax
0x180001ed5  test    rax, rax
0x180001ed8  jz      short loc_180001F34
0x180001eda  mov     [rax+38h], r12d
0x180001ede  lea     rcx, [rax+40h]
0x180001ee2  mov     [rax+3Ch], r12d
0x180001ee6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001eec  mov     [rbx], r12
0x180001eef  mov     rcx, rbx; this
0x180001ef2  mov     [rbx+8], r12
0x180001ef6  mov     [rbx+28h], r12
0x180001efa  mov     [rbx+18h], r12
0x180001efe  mov     [rbx+30h], r12
0x180001f02  mov     [rbx+78h], r12d
0x180001f06  mov     rdx, [rbp+arg_18]; struct INativeConfigurationElement *
0x180001f0a  call    ?Initialize@DAV_AUTH_RULES_ENTRY@@QEAAJPEAVINativeConfigurationElement@@@Z; DAV_AUTH_RULES_ENTRY::Initialize(INativeConfigurationElement *)
0x180001f0f  mov     edi, eax
0x180001f11  test    eax, eax
0x180001f13  js      short loc_180001F22
0x180001f15  mov     rax, [r14+8]
0x180001f19  mov     [rax], rbx
0x180001f1c  mov     [r14+8], rbx
0x180001f20  jmp     short loc_180001F39
0x180001f22  mov     rcx, rbx; this
0x180001f25  call    ??1DAV_AUTH_RULES_ENTRY@@QEAA@XZ; DAV_AUTH_RULES_ENTRY::~DAV_AUTH_RULES_ENTRY(void)
0x180001f2a  mov     rcx, rbx; Block
0x180001f2d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001f32  jmp     short loc_180001F39
0x180001f34  mov     edi, 80070008h
0x180001f39  mov     rcx, [rbp+arg_18]
0x180001f3d  mov     rax, [rcx]
0x180001f40  mov     rax, [rax+10h]
0x180001f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f49  mov     [rbp+arg_18], r12
0x180001f4d  test    edi, edi
0x180001f4f  js      short loc_180001F5C
0x180001f51  inc     esi
0x180001f53  cmp     esi, [r15]
0x180001f56  jb      loc_180001EA8
0x180001f5c  mov     rcx, [rbp+arg_8]
0x180001f60  mov     rax, [rcx]
0x180001f63  mov     rax, [rax+10h]
0x180001f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f6c  mov     eax, edi
0x180001f6e  add     rsp, 30h
0x180001f72  pop     r15
0x180001f74  pop     r14
0x180001f76  pop     r12
0x180001f78  pop     rdi
0x180001f79  pop     rsi
0x180001f7a  pop     rbx
0x180001f7b  pop     rbp
0x180001f7c  retn
```

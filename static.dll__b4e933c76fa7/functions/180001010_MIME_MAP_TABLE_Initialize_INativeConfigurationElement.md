# MIME_MAP_TABLE::Initialize(INativeConfigurationElement *)

- ea: `0x180001010`
- end: `0x1800012e7`
- name: `?Initialize@MIME_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(MIME_MAP_TABLE *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800054f0`

## callees

- `0x180001010`
- `0x180001358`
- `0x180001398`
- `0x180005354`
- `0x180007010`

## import_xrefs

- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x18000118e`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x18000118e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800011b0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800011b0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000115b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000115b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001165`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001165`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800011a3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800011a3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000117d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000117d`

## string_xrefs

- `0x1800010dc`: `fileExtension`

## pseudocode

```c
__int64 __fastcall MIME_MAP_TABLE::Initialize(MIME_MAP_TABLE *this, struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct INativeConfigurationElement *, __int64 **); // rax
  int v5; // ebx
  unsigned int i; // r15d
  __int64 v7; // rax
  const unsigned __int16 *v8; // rsi
  const unsigned __int16 *v9; // rbx
  _WORD **v10; // rax
  _WORD **v11; // r14
  unsigned int v12; // r8d
  unsigned __int16 *v13; // rdx
  unsigned __int16 v14; // ax
  unsigned int v15; // r8d
  const unsigned __int16 *v17; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v18; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+88h] [rbp+10h] BYREF
  __int64 v20; // [rsp+90h] [rbp+18h] BYREF
  __int64 *v21; // [rsp+98h] [rbp+20h] BYREF

  v2 = *(_QWORD *)a2;
  v21 = 0;
  v20 = 0;
  v19 = 0;
  v4 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 **))(v2 + 40);
  v17 = 0;
  v18 = 0;
  v5 = v4(a2, &v21);
  if ( v5 < 0 || (v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v21 + 24))(v21, &v19), v5 < 0) )
  {
LABEL_24:
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    return (unsigned int)v5;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v7 = *v21;
      if ( i >= v19 )
        break;
      v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v7 + 32))(v21, i, &v20);
      if ( v5 < 0 )
        goto LABEL_24;
      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v20 + 64LL))(
             v20,
             L"fileExtension",
             &v17,
             0,
             0);
      if ( v5 < 0 )
        goto LABEL_24;
      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v20 + 64LL))(
             v20,
             L"mimeType",
             &v18,
             0,
             0);
      if ( v5 < 0 )
        goto LABEL_24;
      v8 = v18;
      v9 = v17 + 1;
      if ( *v17 != 46 )
        v9 = v17;
      v10 = (_WORD **)operator new(0x90u);
      v11 = v10;
      if ( !v10 )
        goto LABEL_23;
      STRU::STRU((STRU *)(v10 + 3));
      STRA::STRA((STRA *)(v11 + 10));
      *((_DWORD *)v11 + 34) = 1;
      if ( (int)STRU::Copy((STRU *)(v11 + 3), v9) < 0 || (int)STRA::CopyWTruncate((STRA *)(v11 + 10), v8) < 0 )
        *((_DWORD *)v11 + 34) = 0;
      *v11 = STRU::QueryStr((STRU *)(v11 + 3));
      *((_WORD *)v11 + 8) = STRU::QueryCCH((STRU *)(v11 + 3));
      v11[1] = 0;
      if ( !*((_DWORD *)v11 + 34) )
      {
        MIME_MAP_ENTRY::~MIME_MAP_ENTRY((MIME_MAP_ENTRY *)v11);
        operator delete(v11);
LABEL_23:
        v5 = -2147024888;
        goto LABEL_24;
      }
      v12 = 0;
      v13 = *v11;
      v14 = **v11;
      if ( *((_DWORD *)this + 264) )
      {
        if ( v14 )
        {
          do
          {
            ++v13;
            v12 = v14 + 101 * v12;
            v14 = *v13;
          }
          while ( *v13 );
        }
      }
      else if ( v14 )
      {
        do
        {
          ++v13;
          v12 = (v14 & 0xFFDF) + 101 * v12;
          v14 = *v13;
        }
        while ( *v13 );
      }
      v15 = v12 % 0x83;
      v11[1] = (_WORD *)*((_QWORD *)this + v15 + 1);
      *((_QWORD *)this + v15 + 1) = v11;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    (*(void (**)(void))(v7 + 16))();
    return 0;
  }
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  mov     [r11+8], rbx
0x180001017  push    rbp
0x180001018  push    rsi
0x180001019  push    rdi
0x18000101a  push    r12
0x18000101c  push    r13
0x18000101e  push    r14
0x180001020  push    r15
0x180001022  sub     rsp, 40h
0x180001026  mov     rax, [rdx]
0x180001029  xor     r13d, r13d
0x18000102c  mov     r8, rdx
0x18000102f  mov     [r11+20h], r13
0x180001033  mov     r12, rcx
0x180001036  mov     [r11+18h], r13
0x18000103a  lea     rdx, [r11+20h]
0x18000103e  mov     [r11+10h], r13d
0x180001042  mov     rax, [rax+28h]
0x180001046  mov     rcx, r8
0x180001049  mov     [r11-48h], r13
0x18000104d  mov     [r11-40h], r13
0x180001051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001056  mov     ebx, eax
0x180001058  test    eax, eax
0x18000105a  js      loc_180001286
0x180001060  mov     rcx, [rsp+78h+arg_18]
0x180001068  lea     rdx, [rsp+78h+arg_8]
0x180001070  mov     rax, [rcx]
0x180001073  mov     rax, [rax+18h]
0x180001077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000107c  mov     ebx, eax
0x18000107e  test    eax, eax
0x180001080  js      loc_180001286
0x180001086  mov     r15d, r13d
0x180001089  nop     dword ptr [rax+00000000h]
0x180001090  mov     rcx, [rsp+78h+arg_18]
0x180001098  mov     rax, [rcx]
0x18000109b  cmp     r15d, [rsp+78h+arg_8]
0x1800010a3  jnb     loc_1800012DA
0x1800010a9  mov     rax, [rax+20h]
0x1800010ad  lea     r8, [rsp+78h+arg_10]
0x1800010b5  mov     edx, r15d
0x1800010b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010bd  mov     ebx, eax
0x1800010bf  test    eax, eax
0x1800010c1  js      loc_180001286
0x1800010c7  mov     rcx, [rsp+78h+arg_10]
0x1800010cf  lea     r8, [rsp+78h+var_48]
0x1800010d4  xor     r9d, r9d
0x1800010d7  mov     [rsp+78h+var_58], r13
0x1800010dc  lea     rdx, aFileextension; "fileExtension"
0x1800010e3  mov     rax, [rcx]
0x1800010e6  mov     rax, [rax+40h]
0x1800010ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010ef  mov     ebx, eax
0x1800010f1  test    eax, eax
0x1800010f3  js      loc_180001286
0x1800010f9  mov     rcx, [rsp+78h+arg_10]
0x180001101  lea     r8, [rsp+78h+var_40]
0x180001106  xor     r9d, r9d
0x180001109  mov     [rsp+78h+var_58], r13
0x18000110e  lea     rdx, aMimetype; "mimeType"
0x180001115  mov     rax, [rcx]
0x180001118  mov     rax, [rax+40h]
0x18000111c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001121  mov     ebx, eax
0x180001123  test    eax, eax
0x180001125  js      loc_180001286
0x18000112b  mov     rax, [rsp+78h+var_48]
0x180001130  mov     ecx, 90h; Size
0x180001135  mov     rsi, [rsp+78h+var_40]
0x18000113a  cmp     word ptr [rax], 2Eh ; '.'
0x18000113e  lea     rbx, [rax+2]
0x180001142  cmovnz  rbx, rax
0x180001146  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000114b  mov     r14, rax
0x18000114e  test    rax, rax
0x180001151  jz      loc_180001281
0x180001157  lea     rcx, [rax+18h]
0x18000115b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001161  lea     rcx, [r14+50h]
0x180001165  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000116b  mov     rdx, rbx
0x18000116e  mov     dword ptr [r14+88h], 1
0x180001179  lea     rcx, [r14+18h]
0x18000117d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001183  test    eax, eax
0x180001185  js      short loc_180001198
0x180001187  mov     rdx, rsi
0x18000118a  lea     rcx, [r14+50h]
0x18000118e  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x180001194  test    eax, eax
0x180001196  jns     short loc_18000119F
0x180001198  mov     [r14+88h], r13d
0x18000119f  lea     rcx, [r14+18h]
0x1800011a3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800011a9  lea     rcx, [r14+18h]
0x1800011ad  mov     [r14], rax
0x1800011b0  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800011b6  mov     [r14+10h], ax
0x1800011bb  mov     [r14+8], r13
0x1800011bf  cmp     [r14+88h], r13d
0x1800011c6  jz      loc_180001271
0x1800011cc  mov     r8d, r13d
0x1800011cf  mov     rdx, [r14]
0x1800011d2  movzx   eax, word ptr [rdx]
0x1800011d5  cmp     [r12+420h], r13d
0x1800011dd  jz      short loc_1800011FC
0x1800011df  test    ax, ax
0x1800011e2  jz      short loc_180001228
0x1800011e4  imul    r8d, 65h ; 'e'
0x1800011e8  lea     rdx, [rdx+2]
0x1800011ec  movzx   eax, ax
0x1800011ef  add     r8d, eax
0x1800011f2  movzx   eax, word ptr [rdx]
0x1800011f5  test    ax, ax
0x1800011f8  jnz     short loc_1800011E4
0x1800011fa  jmp     short loc_180001228
0x1800011fc  test    ax, ax
0x1800011ff  jz      short loc_180001228
0x180001201  nop     dword ptr [rax+00h]
0x180001205  nop     word ptr [rax+rax+00000000h]
0x180001210  and     eax, 0FFDFh
0x180001215  imul    r8d, 65h ; 'e'
0x180001219  lea     rdx, [rdx+2]
0x18000121d  add     r8d, eax
0x180001220  movzx   eax, word ptr [rdx]
0x180001223  test    ax, ax
0x180001226  jnz     short loc_180001210
0x180001228  mov     eax, 0FA232CF3h
0x18000122d  mul     r8d
0x180001230  shr     edx, 7
0x180001233  imul    eax, edx, 83h
0x180001239  sub     r8d, eax
0x18000123c  mov     rax, [r12+r8*8+8]
0x180001241  mov     [r14+8], rax
0x180001245  lea     rcx, [r12+r8*8]
0x180001249  mov     [rcx+8], r14
0x18000124d  mov     rcx, [rsp+78h+arg_10]
0x180001255  mov     rax, [rcx]
0x180001258  mov     rax, [rax+10h]
0x18000125c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001261  inc     r15d
0x180001264  mov     [rsp+78h+arg_10], r13
0x18000126c  jmp     loc_180001090
0x180001271  mov     rcx, r14; this
0x180001274  call    ??1MIME_MAP_ENTRY@@QEAA@XZ; MIME_MAP_ENTRY::~MIME_MAP_ENTRY(void)
0x180001279  mov     rcx, r14; Block
0x18000127c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001281  mov     ebx, 80070008h
0x180001286  mov     rcx, [rsp+78h+arg_10]
0x18000128e  test    rcx, rcx
0x180001291  jz      short loc_1800012A7
0x180001293  mov     rax, [rcx]
0x180001296  mov     rax, [rax+10h]
0x18000129a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000129f  mov     [rsp+78h+arg_10], r13
0x1800012a7  mov     rcx, [rsp+78h+arg_18]
0x1800012af  test    rcx, rcx
0x1800012b2  jz      short loc_1800012C0
0x1800012b4  mov     rax, [rcx]
0x1800012b7  mov     rax, [rax+10h]
0x1800012bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012c0  mov     eax, ebx
0x1800012c2  mov     rbx, [rsp+78h+arg_0]
0x1800012ca  add     rsp, 40h
0x1800012ce  pop     r15
0x1800012d0  pop     r14
0x1800012d2  pop     r13
0x1800012d4  pop     r12
0x1800012d6  pop     rdi
0x1800012d7  pop     rsi
0x1800012d8  pop     rbp
0x1800012d9  retn
0x1800012da  mov     rax, [rax+10h]
0x1800012de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012e3  xor     eax, eax
0x1800012e5  jmp     short loc_1800012C2
```

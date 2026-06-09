# cMapRemoteFonts

- ea: `0x140191d5c`
- end: `0x14019230f`
- name: `cMapRemoteFonts`
- size: `1459`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140191c38`
- `0x14030fce0`

## callees

- `0x140191d5c`
- `0x140192318`
- `0x14020ad58`
- `0x140210d2c`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140192280`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140192280`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140191f37`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140191f57`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140191f77`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14019216b`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14019218b`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140191f37`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140191f57`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140191f77`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14019216b`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14019218b`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14019208a`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14019208a`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x140192033`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x1401921df`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x140192033`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x1401921df`
- `win32kbase!EngSetLastError` at `0x140191f95`
- `win32kbase!EngSetLastError` at `0x140192100`
- `win32kbase!EngSetLastError` at `0x1401921a3`
- `win32kbase!EngSetLastError` at `0x140191f95`
- `win32kbase!EngSetLastError` at `0x140192100`
- `win32kbase!EngSetLastError` at `0x1401921a3`
- `win32kbase!?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z` at `0x140191eaa`
- `win32kbase!?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z` at `0x140191eaa`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x140191ffd`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x1401922ed`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x140191ffd`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x1401922ed`
- `win32kbase!?GreProbeAndCopyToAndFromUntrustedVa@@YAXPEAX_KPEBX1@Z` at `0x1401920e7`
- `win32kbase!?GreProbeAndCopyToAndFromUntrustedVa@@YAXPEAX_KPEBX1@Z` at `0x1401920e7`

## pseudocode

```c
__int64 __fastcall cMapRemoteFonts(const void **a1, DWORD a2, _QWORD *a3, int a4)
{
  union _LARGE_INTEGER v5; // r14
  char *v6; // r15
  int v7; // eax
  union _LARGE_INTEGER v8; // r13
  char *v9; // rbx
  unsigned int v10; // r13d
  char *v12; // r15
  _QWORD *v13; // r12
  char *v14; // rbx
  _QWORD *v15; // r15
  DWORD v16; // eax
  __int64 v17; // rax
  unsigned int v18; // ebx
  int v19; // [rsp+30h] [rbp-108h] BYREF
  DWORD LowPart; // [rsp+38h] [rbp-100h]
  int v21; // [rsp+40h] [rbp-F8h]
  unsigned int v22; // [rsp+44h] [rbp-F4h]
  __int64 v23; // [rsp+48h] [rbp-F0h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-E8h]
  int v25; // [rsp+54h] [rbp-E4h]
  __int64 v26; // [rsp+58h] [rbp-E0h] BYREF
  _QWORD *v27; // [rsp+60h] [rbp-D8h]
  const void **v28; // [rsp+68h] [rbp-D0h]
  __int64 v29; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+78h] [rbp-C0h]
  char *v31; // [rsp+80h] [rbp-B8h]
  unsigned __int64 v32; // [rsp+88h] [rbp-B0h]
  int v33; // [rsp+90h] [rbp-A8h]
  int v34; // [rsp+98h] [rbp-A0h] BYREF
  const void **v35; // [rsp+A0h] [rbp-98h]
  void *v36; // [rsp+A8h] [rbp-90h]
  union _LARGE_INTEGER v37; // [rsp+B0h] [rbp-88h] BYREF
  char *v38; // [rsp+B8h] [rbp-80h]
  char *v39; // [rsp+C0h] [rbp-78h]
  _QWORD *v40; // [rsp+D0h] [rbp-68h]
  char *v41; // [rsp+E0h] [rbp-58h] BYREF
  int v42; // [rsp+E8h] [rbp-50h]

  v27 = a3;
  v5.QuadPart = a2;
  v28 = a1;
  v36 = a3;
  v35 = a1;
  LowPart = a2;
  v40 = a3;
  v37.QuadPart = 0;
  v19 = 0;
  v6 = (char *)*a1;
  *a1 = 0;
  if ( a2 - 12 > 0xFFFFFF4 || !a3 )
    return 0;
  v25 = 0;
  v38 = v6;
  memset_0(a3, 0, 0x78u);
  if ( a4 == 1 )
  {
    v41 = 0;
    v42 = 0;
    GreProbeAndReadFromUntrustedVa(&v41, 0xCu, v6, 0xCu, 4u);
    v7 = HIDWORD(v41);
    v19 = HIDWORD(v41);
    if ( HIDWORD(v41) > 3 )
      return 0;
    if ( !HIDWORD(v41) )
    {
      v25 = 1;
      v19 = 2;
      v7 = 2;
    }
  }
  else
  {
    v19 = 1;
    v7 = 1;
  }
  v24 = (4 * v7 + 15) & 0xFFFFFFF8;
  v22 = v24;
  if ( v5.LowPart < v24 )
    return 0;
  v8 = v5;
  v37 = v5;
  Gre::SectionObj::SectionObj((Gre::SectionObj *)&v23, &v37);
  if ( !v23 )
  {
LABEL_16:
    Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v23);
    return 0;
  }
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 6;
  v26 = 0;
  if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))Gre::MapViewOfSectionObj::Map)(
                           &v29,
                           v23,
                           1,
                           (union _LARGE_INTEGER)v5.QuadPart,
                           &v26) )
  {
LABEL_32:
    Gre::MapViewOfSectionObj::~MapViewOfSectionObj((Gre::MapViewOfSectionObj *)&v29);
    goto LABEL_16;
  }
  v9 = v31;
  v39 = v31;
  if ( v31 <= v6 )
  {
    if ( v6 < &v31[v32] )
    {
LABEL_14:
      if ( v33 != 6 )
        Gre::MapViewOfSectionObj::Unmap((Gre::MapViewOfSectionObj *)&v29);
      goto LABEL_16;
    }
    if ( v31 < v6 )
      goto LABEL_12;
  }
  if ( a4 == 2 )
    v8.QuadPart = v5.QuadPart - 16;
  if ( v31 < &v6[v8.QuadPart] )
    goto LABEL_14;
LABEL_12:
  v41 = v31;
  if ( a4 == 2 )
  {
    v5.LowPart -= 16;
    LowPart = v5.LowPart;
    v34 = 0;
    LODWORD(v26) = v5.LowPart;
    GreProbeAndWriteToUntrustedVa(v31, 4u, &v34, 4u, 1u);
    GreProbeAndWriteToUntrustedVa(v9 + 4, 4u, &v19, 4u, 1u);
    GreProbeAndWriteToUntrustedVa(v9 + 8, 4u, &v26, 4u, 1u);
    v21 = 1;
    v10 = v24;
    v9 += 16;
  }
  else
  {
    v10 = v24;
  }
  GreProbeAndCopyToAndFromUntrustedVa(v9, v32, v6, v5.LowPart);
  v21 = 1;
  if ( v25 )
  {
    LODWORD(v26) = 0;
    v12 = v41;
    GreProbeAndWriteToUntrustedVa(v41, 4u, &v26, 4u, 1u);
    GreProbeAndWriteToUntrustedVa(v12 + 4, 4u, &v19, 4u, 1u);
  }
  v13 = v27;
  if ( !Gre::MapViewOfSectionObj::Unmap((Gre::MapViewOfSectionObj *)&v29)
    || !(unsigned __int8)Gre::MapViewOfSectionObj::Map(&v29, v23, 5) )
  {
    goto LABEL_32;
  }
  v14 = v31;
  v15 = v40;
  v40[13] = v31;
  v13[2] = &v14[v10];
  v16 = v5.LowPart + 16;
  if ( a4 != 2 )
    v16 = v5.LowPart;
  *((_DWORD *)v13 + 6) = v16 - v10;
  *((_DWORD *)v13 + 7) = v10;
  v15[11] = v32;
  *((_DWORD *)v15 + 24) = 0;
  *((_DWORD *)v15 + 25) = 1;
  v17 = v23;
  v23 = 0;
  v13[4] = v17;
  *((_DWORD *)v15 + 28) = (unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC;
  v13[9] = v29;
  *v28 = v14;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 6;
  v18 = v19;
  Gre::MapViewOfSectionObj::~MapViewOfSectionObj((Gre::MapViewOfSectionObj *)&v29);
  Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v23);
  return v18;
}

```

## disassembly

```asm
0x140191d5c  mov     [rsp+arg_18], r9d
0x140191d61  push    rbx
0x140191d62  push    rsi
0x140191d63  push    r12
0x140191d65  push    r13
0x140191d67  push    r14
0x140191d69  push    r15
0x140191d6b  sub     rsp, 108h
0x140191d72  mov     rax, cs:__security_cookie
0x140191d79  xor     rax, rsp
0x140191d7c  mov     [rsp+138h+var_48], rax
0x140191d84  mov     ebx, r9d
0x140191d87  mov     [rsp+138h+var_D8], r8
0x140191d8c  mov     r14d, edx
0x140191d8f  mov     rax, rcx
0x140191d92  mov     [rsp+138h+var_D0], rcx
0x140191d97  mov     [rsp+138h+var_90], r8
0x140191d9f  mov     [rsp+138h+var_98], rcx
0x140191da7  mov     [rsp+138h+var_100], r14d
0x140191dac  mov     rcx, r8; void *
0x140191daf  mov     [rsp+138h+var_68], rcx
0x140191db7  mov     qword ptr [rsp+138h+var_88], 0
0x140191dc3  mov     [rsp+138h+var_108], 0
0x140191dcb  mov     r15, [rax]
0x140191dce  mov     qword ptr [rax], 0
0x140191dd5  lea     eax, [r14-0Ch]
0x140191dd9  cmp     eax, 0FFFFFF4h
0x140191dde  ja      loc_140192009
0x140191de4  test    rcx, rcx
0x140191de7  jz      loc_140192009
0x140191ded  mov     [rsp+138h+var_E4], 0
0x140191df5  mov     [rsp+138h+var_80], r15
0x140191dfd  xor     edx, edx; Val
0x140191dff  lea     r8d, [rdx+78h]; Size
0x140191e03  call    memset_0
0x140191e08  mov     esi, 1
0x140191e0d  cmp     ebx, esi
0x140191e0f  jz      loc_14019205F
0x140191e15  mov     [rsp+138h+var_108], esi
0x140191e19  mov     eax, esi
0x140191e1b  lea     r12d, [rsi+3]
0x140191e1f  lea     eax, ds:0Fh[rax*4]
0x140191e26  and     eax, 0FFFFFFF8h
0x140191e29  mov     [rsp+138h+var_E8], eax
0x140191e2d  mov     [rsp+138h+var_F4], eax
0x140191e31  cmp     r14d, eax
0x140191e34  jb      loc_140192009
0x140191e3a  mov     r13, r14
0x140191e3d  mov     qword ptr [rsp+138h+var_88], r14
0x140191e45  lea     rdx, [rsp+138h+var_88]; union _LARGE_INTEGER *
0x140191e4d  lea     rcx, [rsp+138h+var_F0]; this
0x140191e52  call    ??0SectionObj@Gre@@QEAA@PEAT_LARGE_INTEGER@@@Z; Gre::SectionObj::SectionObj(_LARGE_INTEGER *)
0x140191e57  mov     rdx, [rsp+138h+var_F0]
0x140191e5c  test    rdx, rdx
0x140191e5f  jz      loc_140191FF8
0x140191e65  mov     [rsp+138h+var_C8], 0
0x140191e6e  xor     eax, eax
0x140191e70  mov     [rsp+138h+var_C0], rax
0x140191e75  mov     [rsp+138h+var_B8], rax
0x140191e7d  mov     [rsp+138h+var_B0], rax
0x140191e85  mov     [rsp+138h+var_A8], 6
0x140191e90  mov     [rsp+138h+var_E0], rax
0x140191e95  lea     rax, [rsp+138h+var_E0]
0x140191e9a  mov     [rsp+138h+var_118], rax
0x140191e9f  mov     r9, r14
0x140191ea2  mov     r8d, esi
0x140191ea5  lea     rcx, [rsp+138h+var_C8]
0x140191eaa  call    cs:__imp_?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z; Gre::MapViewOfSectionObj::Map(void *,Gre::MapViewOfSectionObj::MapKind,unsigned __int64,_LARGE_INTEGER *)
0x140191eb1  nop     dword ptr [rax+rax+00h]
0x140191eb6  test    al, al
0x140191eb8  jz      loc_140192300
0x140191ebe  mov     rbx, [rsp+138h+var_B8]
0x140191ec6  mov     [rsp+138h+var_78], rbx
0x140191ece  cmp     rbx, r15
0x140191ed1  jbe     loc_140192041
0x140191ed7  cmp     [rsp+138h+arg_18], 2
0x140191edf  jnz     short loc_140191EE5
0x140191ee1  add     r13, 0FFFFFFFFFFFFFFF0h
0x140191ee5  lea     rax, [r15+r13]
0x140191ee9  cmp     rbx, rax
0x140191eec  jb      loc_140191FEE
0x140191ef2  mov     [rsp+138h+var_58], rbx
0x140191efa  cmp     [rsp+138h+arg_18], 2
0x140191f02  jnz     loc_1401920D1
0x140191f08  add     r14d, 0FFFFFFF0h
0x140191f0c  mov     [rsp+138h+var_100], r14d
0x140191f11  mov     [rsp+138h+var_A0], 0
0x140191f1c  mov     dword ptr [rsp+138h+var_E0], r14d
0x140191f21  mov     [rsp+138h+var_118], rsi
0x140191f26  mov     r9, r12
0x140191f29  lea     r8, [rsp+138h+var_A0]
0x140191f31  mov     rdx, r12
0x140191f34  mov     rcx, rbx
0x140191f37  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140191f3e  nop     dword ptr [rax+rax+00h]
0x140191f43  lea     rcx, [rbx+4]
0x140191f47  mov     [rsp+138h+var_118], rsi
0x140191f4c  mov     r9, r12
0x140191f4f  lea     r8, [rsp+138h+var_108]
0x140191f54  mov     rdx, r12
0x140191f57  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140191f5e  nop     dword ptr [rax+rax+00h]
0x140191f63  lea     rcx, [rbx+8]
0x140191f67  mov     [rsp+138h+var_118], rsi
0x140191f6c  mov     r9, r12
0x140191f6f  lea     r8, [rsp+138h+var_E0]
0x140191f74  mov     rdx, r12
0x140191f77  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140191f7e  nop     dword ptr [rax+rax+00h]
0x140191f83  mov     eax, esi
0x140191f85  mov     [rsp+138h+var_F8], eax
0x140191f89  mov     r13d, [rsp+138h+var_E8]
0x140191f8e  jmp     short loc_140191FE2
0x140191f90  mov     ecx, 57h ; 'W'; iError
0x140191f95  call    cs:__imp_EngSetLastError
0x140191f9c  nop     dword ptr [rax+rax+00h]
0x140191fa1  xor     eax, eax
0x140191fa3  mov     [rsp+138h+var_F8], eax
0x140191fa7  lea     esi, [rax+1]
0x140191faa  lea     r12d, [rax+4]
0x140191fae  mov     r15, [rsp+138h+var_80]
0x140191fb6  mov     rcx, [rsp+138h+var_98]
0x140191fbe  mov     [rsp+138h+var_D0], rcx
0x140191fc3  mov     r14d, [rsp+138h+var_100]
0x140191fc8  mov     r8, [rsp+138h+var_90]
0x140191fd0  mov     [rsp+138h+var_D8], r8
0x140191fd5  mov     rbx, [rsp+138h+var_78]
0x140191fdd  mov     r13d, [rsp+138h+var_F4]
0x140191fe2  add     rbx, 10h
0x140191fe6  test    eax, eax
0x140191fe8  jnz     loc_1401920D6
0x140191fee  cmp     [rsp+138h+var_A8], 6
0x140191ff6  jnz     short loc_14019202E
0x140191ff8  lea     rcx, [rsp+138h+var_F0]
0x140191ffd  call    cs:__imp_??1SectionObj@Gre@@QEAA@XZ; Gre::SectionObj::~SectionObj(void)
0x140192004  nop     dword ptr [rax+rax+00h]
0x140192009  xor     eax, eax
0x14019200b  mov     rcx, [rsp+138h+var_48]
0x140192013  xor     rcx, rsp; StackCookie
0x140192016  call    __security_check_cookie
0x14019201b  add     rsp, 108h
0x140192022  pop     r15
0x140192024  pop     r14
0x140192026  pop     r13
0x140192028  pop     r12
0x14019202a  pop     rsi
0x14019202b  pop     rbx
0x14019202c  retn
0x14019202e  lea     rcx, [rsp+138h+var_C8]
0x140192033  call    cs:__imp_?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x14019203a  nop     dword ptr [rax+rax+00h]
0x14019203f  jmp     short loc_140191FF8
0x140192041  mov     rcx, [rsp+138h+var_B0]
0x140192049  add     rcx, rbx
0x14019204c  cmp     r15, rcx
0x14019204f  jb      short loc_140191FEE
0x140192051  cmp     rbx, r15
0x140192054  jnb     loc_140191ED7
0x14019205a  jmp     loc_140191EF2
0x14019205f  xor     eax, eax
0x140192061  mov     [rsp+138h+var_58], rax
0x140192069  mov     [rsp+138h+var_50], eax
0x140192070  lea     r12d, [rax+4]
0x140192074  mov     [rsp+138h+var_118], r12
0x140192079  lea     edx, [rax+0Ch]
0x14019207c  mov     r9d, edx
0x14019207f  mov     r8, r15
0x140192082  lea     rcx, [rsp+138h+var_58]
0x14019208a  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140192091  nop     dword ptr [rax+rax+00h]
0x140192096  jmp     short loc_14019209F
0x140192098  xor     eax, eax
0x14019209a  jmp     loc_14019200B
0x14019209f  mov     eax, dword ptr [rsp+138h+var_58+4]
0x1401920a6  mov     [rsp+138h+var_108], eax
0x1401920aa  cmp     eax, 3
0x1401920ad  ja      loc_140192009
0x1401920b3  test    eax, eax
0x1401920b5  jnz     loc_140191E1F
0x1401920bb  mov     [rsp+138h+var_E4], esi
0x1401920bf  mov     [rsp+138h+var_108], 2
0x1401920c7  mov     eax, 2
0x1401920cc  jmp     loc_140191E1F
0x1401920d1  mov     r13d, [rsp+138h+var_E8]
0x1401920d6  mov     r9d, r14d
0x1401920d9  mov     r8, r15
0x1401920dc  mov     rdx, [rsp+138h+var_B0]
0x1401920e4  mov     rcx, rbx
0x1401920e7  call    cs:__imp_?GreProbeAndCopyToAndFromUntrustedVa@@YAXPEAX_KPEBX1@Z; GreProbeAndCopyToAndFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64)
0x1401920ee  nop     dword ptr [rax+rax+00h]
0x1401920f3  mov     ebx, esi
0x1401920f5  mov     [rsp+138h+var_F8], ebx
0x1401920f9  jmp     short loc_14019213D
0x1401920fb  mov     ecx, 57h ; 'W'; iError
0x140192100  call    cs:__imp_EngSetLastError
0x140192107  nop     dword ptr [rax+rax+00h]
0x14019210c  xor     ebx, ebx
0x14019210e  mov     [rsp+138h+var_F8], ebx
0x140192112  lea     esi, [rbx+1]
0x140192115  lea     r12d, [rbx+4]
0x140192119  mov     rax, [rsp+138h+var_98]
0x140192121  mov     [rsp+138h+var_D0], rax
0x140192126  mov     r14d, [rsp+138h+var_100]
0x14019212b  mov     r8, [rsp+138h+var_90]
0x140192133  mov     [rsp+138h+var_D8], r8
0x140192138  mov     r13d, [rsp+138h+var_F4]
0x14019213d  cmp     [rsp+138h+var_E4], 0
0x140192142  jz      loc_1401921D5
0x140192148  mov     dword ptr [rsp+138h+var_E0], 0
0x140192150  mov     [rsp+138h+var_118], rsi
0x140192155  mov     r9, r12
0x140192158  lea     r8, [rsp+138h+var_E0]
0x14019215d  mov     rdx, r12
0x140192160  mov     r15, [rsp+138h+var_58]
0x140192168  mov     rcx, r15
0x14019216b  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140192172  nop     dword ptr [rax+rax+00h]
0x140192177  lea     rcx, [r15+4]
0x14019217b  mov     [rsp+138h+var_118], rsi
0x140192180  mov     r9, r12
0x140192183  lea     r8, [rsp+138h+var_108]
0x140192188  mov     rdx, r12
0x14019218b  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140192192  nop     dword ptr [rax+rax+00h]
0x140192197  mov     r12, [rsp+138h+var_D8]
0x14019219c  jmp     short loc_1401921DA
0x14019219e  mov     ecx, 57h ; 'W'; iError
0x1401921a3  call    cs:__imp_EngSetLastError
0x1401921aa  nop     dword ptr [rax+rax+00h]
0x1401921af  xor     ebx, ebx
0x1401921b1  lea     esi, [rbx+1]
0x1401921b4  mov     rax, [rsp+138h+var_98]
0x1401921bc  mov     [rsp+138h+var_D0], rax
0x1401921c1  mov     r14d, [rsp+138h+var_100]
0x1401921c6  mov     r12, [rsp+138h+var_90]
0x1401921ce  mov     r13d, [rsp+138h+var_F4]
0x1401921d3  jmp     short loc_1401921DA
0x1401921d5  mov     r12, [rsp+138h+var_D8]
0x1401921da  lea     rcx, [rsp+138h+var_C8]
0x1401921df  call    cs:__imp_?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x1401921e6  nop     dword ptr [rax+rax+00h]
0x1401921eb  test    al, al
0x1401921ed  jz      loc_140192300
0x1401921f3  test    ebx, ebx
0x1401921f5  jz      loc_140192300
0x1401921fb  xor     r9d, r9d
0x1401921fe  lea     r8d, [r9+5]
0x140192202  mov     rdx, [rsp+138h+var_F0]
0x140192207  lea     rcx, [rsp+138h+var_C8]
0x14019220c  call    ?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_K@Z; Gre::MapViewOfSectionObj::Map(void *,Gre::MapViewOfSectionObj::MapKind,unsigned __int64)
0x140192211  test    al, al
0x140192213  jz      loc_140192300
0x140192219  mov     rbx, [rsp+138h+var_B8]
0x140192221  mov     r15, [rsp+138h+var_68]
0x140192229  mov     [r15+68h], rbx
0x14019222d  mov     eax, r13d
0x140192230  add     rax, rbx
0x140192233  mov     [r12+10h], rax
0x140192238  lea     eax, [r14+10h]
0x14019223c  cmp     [rsp+138h+arg_18], 2
0x140192244  cmovnz  eax, r14d
0x140192248  sub     eax, r13d
0x14019224b  mov     [r12+18h], eax
0x140192250  mov     [r12+1Ch], r13d
0x140192255  mov     rax, [rsp+138h+var_B0]
0x14019225d  mov     [r15+58h], rax
0x140192261  mov     dword ptr [r15+60h], 0
0x140192269  mov     [r15+64h], esi
0x14019226d  mov     rax, [rsp+138h+var_F0]
0x140192272  mov     [rsp+138h+var_F0], 0
0x14019227b  mov     [r12+20h], rax
0x140192280  call    cs:__imp_PsGetCurrentProcessId
0x140192287  nop     dword ptr [rax+rax+00h]
0x14019228c  and     eax, 0FFFFFFFCh
0x14019228f  mov     [r15+70h], eax
0x140192293  mov     rax, [rsp+138h+var_C8]
0x140192298  mov     [r12+48h], rax
0x14019229d  mov     rax, [rsp+138h+var_D0]
0x1401922a2  mov     [rax], rbx
0x1401922a5  mov     [rsp+138h+var_B8], 0
0x1401922b1  mov     [rsp+138h+var_C8], 0
0x1401922ba  mov     [rsp+138h+var_C0], 0
0x1401922c3  mov     [rsp+138h+var_B0], 0
0x1401922cf  mov     [rsp+138h+var_A8], 6
0x1401922da  mov     ebx, [rsp+138h+var_108]
0x1401922de  lea     rcx, [rsp+138h+var_C8]; this
0x1401922e3  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x1401922e8  lea     rcx, [rsp+138h+var_F0]
0x1401922ed  call    cs:__imp_??1SectionObj@Gre@@QEAA@XZ; Gre::SectionObj::~SectionObj(void)
0x1401922f4  nop     dword ptr [rax+rax+00h]
0x1401922f9  mov     eax, ebx
0x1401922fb  jmp     loc_14019200B
0x140192300  lea     rcx, [rsp+138h+var_C8]; this
0x140192305  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x14019230a  jmp     loc_140191FF8
```

# cMapRemoteFonts

- ea: `0x14018b3ec`
- end: `0x14018b99f`
- name: `cMapRemoteFonts`
- size: `1459`
- prototype: `__int64 __fastcall(const void **, DWORD, _QWORD *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14018b2c8`
- `0x14030e050`

## callees

- `0x14018b3ec`
- `0x14018b9a8`
- `0x14020a658`
- `0x1402105cc`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14018b910`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14018b910`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b5c7`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b5e7`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b607`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b7fb`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b81b`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b5c7`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b5e7`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b607`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b7fb`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b81b`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b71a`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14018b71a`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x14018b6c3`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x14018b86f`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x14018b6c3`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x14018b86f`
- `win32kbase!EngSetLastError` at `0x14018b625`
- `win32kbase!EngSetLastError` at `0x14018b790`
- `win32kbase!EngSetLastError` at `0x14018b833`
- `win32kbase!EngSetLastError` at `0x14018b625`
- `win32kbase!EngSetLastError` at `0x14018b790`
- `win32kbase!EngSetLastError` at `0x14018b833`
- `win32kbase!?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z` at `0x14018b53a`
- `win32kbase!?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z` at `0x14018b53a`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14018b68d`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14018b97d`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14018b68d`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14018b97d`
- `win32kbase!?GreProbeAndCopyToAndFromUntrustedVa@@YAXPEAX_KPEBX1@Z` at `0x14018b777`
- `win32kbase!?GreProbeAndCopyToAndFromUntrustedVa@@YAXPEAX_KPEBX1@Z` at `0x14018b777`

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
  if ( !(unsigned __int8)Gre::MapViewOfSectionObj::Map(&v29, v23, 1) )
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
    || !(unsigned __int8)Gre::MapViewOfSectionObj::Map(&v29, v23, 5, 0) )
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
0x14018b3ec  mov     [rsp+arg_18], r9d
0x14018b3f1  push    rbx
0x14018b3f2  push    rsi
0x14018b3f3  push    r12
0x14018b3f5  push    r13
0x14018b3f7  push    r14
0x14018b3f9  push    r15
0x14018b3fb  sub     rsp, 108h
0x14018b402  mov     rax, cs:__security_cookie
0x14018b409  xor     rax, rsp
0x14018b40c  mov     [rsp+138h+var_48], rax
0x14018b414  mov     ebx, r9d
0x14018b417  mov     [rsp+138h+var_D8], r8
0x14018b41c  mov     r14d, edx
0x14018b41f  mov     rax, rcx
0x14018b422  mov     [rsp+138h+var_D0], rcx
0x14018b427  mov     [rsp+138h+var_90], r8
0x14018b42f  mov     [rsp+138h+var_98], rcx
0x14018b437  mov     [rsp+138h+var_100], r14d
0x14018b43c  mov     rcx, r8; void *
0x14018b43f  mov     [rsp+138h+var_68], rcx
0x14018b447  mov     qword ptr [rsp+138h+var_88], 0
0x14018b453  mov     [rsp+138h+var_108], 0
0x14018b45b  mov     r15, [rax]
0x14018b45e  mov     qword ptr [rax], 0
0x14018b465  lea     eax, [r14-0Ch]
0x14018b469  cmp     eax, 0FFFFFF4h
0x14018b46e  ja      loc_14018B699
0x14018b474  test    rcx, rcx
0x14018b477  jz      loc_14018B699
0x14018b47d  mov     [rsp+138h+var_E4], 0
0x14018b485  mov     [rsp+138h+var_80], r15
0x14018b48d  xor     edx, edx; Val
0x14018b48f  lea     r8d, [rdx+78h]; Size
0x14018b493  call    memset_0
0x14018b498  mov     esi, 1
0x14018b49d  cmp     ebx, esi
0x14018b49f  jz      loc_14018B6EF
0x14018b4a5  mov     [rsp+138h+var_108], esi
0x14018b4a9  mov     eax, esi
0x14018b4ab  lea     r12d, [rsi+3]
0x14018b4af  lea     eax, ds:0Fh[rax*4]
0x14018b4b6  and     eax, 0FFFFFFF8h
0x14018b4b9  mov     [rsp+138h+var_E8], eax
0x14018b4bd  mov     [rsp+138h+var_F4], eax
0x14018b4c1  cmp     r14d, eax
0x14018b4c4  jb      loc_14018B699
0x14018b4ca  mov     r13, r14
0x14018b4cd  mov     qword ptr [rsp+138h+var_88], r14
0x14018b4d5  lea     rdx, [rsp+138h+var_88]; union _LARGE_INTEGER *
0x14018b4dd  lea     rcx, [rsp+138h+var_F0]; this
0x14018b4e2  call    ??0SectionObj@Gre@@QEAA@PEAT_LARGE_INTEGER@@@Z; Gre::SectionObj::SectionObj(_LARGE_INTEGER *)
0x14018b4e7  mov     rdx, [rsp+138h+var_F0]
0x14018b4ec  test    rdx, rdx
0x14018b4ef  jz      loc_14018B688
0x14018b4f5  mov     [rsp+138h+var_C8], 0
0x14018b4fe  xor     eax, eax
0x14018b500  mov     [rsp+138h+var_C0], rax
0x14018b505  mov     [rsp+138h+var_B8], rax
0x14018b50d  mov     [rsp+138h+var_B0], rax
0x14018b515  mov     [rsp+138h+var_A8], 6
0x14018b520  mov     [rsp+138h+var_E0], rax
0x14018b525  lea     rax, [rsp+138h+var_E0]
0x14018b52a  mov     [rsp+138h+var_118], rax
0x14018b52f  mov     r9, r14
0x14018b532  mov     r8d, esi
0x14018b535  lea     rcx, [rsp+138h+var_C8]
0x14018b53a  call    cs:__imp_?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z; Gre::MapViewOfSectionObj::Map(void *,Gre::MapViewOfSectionObj::MapKind,unsigned __int64,_LARGE_INTEGER *)
0x14018b541  nop     dword ptr [rax+rax+00h]
0x14018b546  test    al, al
0x14018b548  jz      loc_14018B990
0x14018b54e  mov     rbx, [rsp+138h+var_B8]
0x14018b556  mov     [rsp+138h+var_78], rbx
0x14018b55e  cmp     rbx, r15
0x14018b561  jbe     loc_14018B6D1
0x14018b567  cmp     [rsp+138h+arg_18], 2
0x14018b56f  jnz     short loc_14018B575
0x14018b571  add     r13, 0FFFFFFFFFFFFFFF0h
0x14018b575  lea     rax, [r15+r13]
0x14018b579  cmp     rbx, rax
0x14018b57c  jb      loc_14018B67E
0x14018b582  mov     [rsp+138h+var_58], rbx
0x14018b58a  cmp     [rsp+138h+arg_18], 2
0x14018b592  jnz     loc_14018B761
0x14018b598  add     r14d, 0FFFFFFF0h
0x14018b59c  mov     [rsp+138h+var_100], r14d
0x14018b5a1  mov     [rsp+138h+var_A0], 0
0x14018b5ac  mov     dword ptr [rsp+138h+var_E0], r14d
0x14018b5b1  mov     [rsp+138h+var_118], rsi
0x14018b5b6  mov     r9, r12
0x14018b5b9  lea     r8, [rsp+138h+var_A0]
0x14018b5c1  mov     rdx, r12
0x14018b5c4  mov     rcx, rbx
0x14018b5c7  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14018b5ce  nop     dword ptr [rax+rax+00h]
0x14018b5d3  lea     rcx, [rbx+4]
0x14018b5d7  mov     [rsp+138h+var_118], rsi
0x14018b5dc  mov     r9, r12
0x14018b5df  lea     r8, [rsp+138h+var_108]
0x14018b5e4  mov     rdx, r12
0x14018b5e7  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14018b5ee  nop     dword ptr [rax+rax+00h]
0x14018b5f3  lea     rcx, [rbx+8]
0x14018b5f7  mov     [rsp+138h+var_118], rsi
0x14018b5fc  mov     r9, r12
0x14018b5ff  lea     r8, [rsp+138h+var_E0]
0x14018b604  mov     rdx, r12
0x14018b607  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14018b60e  nop     dword ptr [rax+rax+00h]
0x14018b613  mov     eax, esi
0x14018b615  mov     [rsp+138h+var_F8], eax
0x14018b619  mov     r13d, [rsp+138h+var_E8]
0x14018b61e  jmp     short loc_14018B672
0x14018b620  mov     ecx, 57h ; 'W'; iError
0x14018b625  call    cs:__imp_EngSetLastError
0x14018b62c  nop     dword ptr [rax+rax+00h]
0x14018b631  xor     eax, eax
0x14018b633  mov     [rsp+138h+var_F8], eax
0x14018b637  lea     esi, [rax+1]
0x14018b63a  lea     r12d, [rax+4]
0x14018b63e  mov     r15, [rsp+138h+var_80]
0x14018b646  mov     rcx, [rsp+138h+var_98]
0x14018b64e  mov     [rsp+138h+var_D0], rcx
0x14018b653  mov     r14d, [rsp+138h+var_100]
0x14018b658  mov     r8, [rsp+138h+var_90]
0x14018b660  mov     [rsp+138h+var_D8], r8
0x14018b665  mov     rbx, [rsp+138h+var_78]
0x14018b66d  mov     r13d, [rsp+138h+var_F4]
0x14018b672  add     rbx, 10h
0x14018b676  test    eax, eax
0x14018b678  jnz     loc_14018B766
0x14018b67e  cmp     [rsp+138h+var_A8], 6
0x14018b686  jnz     short loc_14018B6BE
0x14018b688  lea     rcx, [rsp+138h+var_F0]
0x14018b68d  call    cs:__imp_??1SectionObj@Gre@@QEAA@XZ; Gre::SectionObj::~SectionObj(void)
0x14018b694  nop     dword ptr [rax+rax+00h]
0x14018b699  xor     eax, eax
0x14018b69b  mov     rcx, [rsp+138h+var_48]
0x14018b6a3  xor     rcx, rsp; StackCookie
0x14018b6a6  call    __security_check_cookie
0x14018b6ab  add     rsp, 108h
0x14018b6b2  pop     r15
0x14018b6b4  pop     r14
0x14018b6b6  pop     r13
0x14018b6b8  pop     r12
0x14018b6ba  pop     rsi
0x14018b6bb  pop     rbx
0x14018b6bc  retn
0x14018b6be  lea     rcx, [rsp+138h+var_C8]
0x14018b6c3  call    cs:__imp_?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x14018b6ca  nop     dword ptr [rax+rax+00h]
0x14018b6cf  jmp     short loc_14018B688
0x14018b6d1  mov     rcx, [rsp+138h+var_B0]
0x14018b6d9  add     rcx, rbx
0x14018b6dc  cmp     r15, rcx
0x14018b6df  jb      short loc_14018B67E
0x14018b6e1  cmp     rbx, r15
0x14018b6e4  jnb     loc_14018B567
0x14018b6ea  jmp     loc_14018B582
0x14018b6ef  xor     eax, eax
0x14018b6f1  mov     [rsp+138h+var_58], rax
0x14018b6f9  mov     [rsp+138h+var_50], eax
0x14018b700  lea     r12d, [rax+4]
0x14018b704  mov     [rsp+138h+var_118], r12
0x14018b709  lea     edx, [rax+0Ch]
0x14018b70c  mov     r9d, edx
0x14018b70f  mov     r8, r15
0x14018b712  lea     rcx, [rsp+138h+var_58]
0x14018b71a  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14018b721  nop     dword ptr [rax+rax+00h]
0x14018b726  jmp     short loc_14018B72F
0x14018b728  xor     eax, eax
0x14018b72a  jmp     loc_14018B69B
0x14018b72f  mov     eax, dword ptr [rsp+138h+var_58+4]
0x14018b736  mov     [rsp+138h+var_108], eax
0x14018b73a  cmp     eax, 3
0x14018b73d  ja      loc_14018B699
0x14018b743  test    eax, eax
0x14018b745  jnz     loc_14018B4AF
0x14018b74b  mov     [rsp+138h+var_E4], esi
0x14018b74f  mov     [rsp+138h+var_108], 2
0x14018b757  mov     eax, 2
0x14018b75c  jmp     loc_14018B4AF
0x14018b761  mov     r13d, [rsp+138h+var_E8]
0x14018b766  mov     r9d, r14d
0x14018b769  mov     r8, r15
0x14018b76c  mov     rdx, [rsp+138h+var_B0]
0x14018b774  mov     rcx, rbx
0x14018b777  call    cs:__imp_?GreProbeAndCopyToAndFromUntrustedVa@@YAXPEAX_KPEBX1@Z; GreProbeAndCopyToAndFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64)
0x14018b77e  nop     dword ptr [rax+rax+00h]
0x14018b783  mov     ebx, esi
0x14018b785  mov     [rsp+138h+var_F8], ebx
0x14018b789  jmp     short loc_14018B7CD
0x14018b78b  mov     ecx, 57h ; 'W'; iError
0x14018b790  call    cs:__imp_EngSetLastError
0x14018b797  nop     dword ptr [rax+rax+00h]
0x14018b79c  xor     ebx, ebx
0x14018b79e  mov     [rsp+138h+var_F8], ebx
0x14018b7a2  lea     esi, [rbx+1]
0x14018b7a5  lea     r12d, [rbx+4]
0x14018b7a9  mov     rax, [rsp+138h+var_98]
0x14018b7b1  mov     [rsp+138h+var_D0], rax
0x14018b7b6  mov     r14d, [rsp+138h+var_100]
0x14018b7bb  mov     r8, [rsp+138h+var_90]
0x14018b7c3  mov     [rsp+138h+var_D8], r8
0x14018b7c8  mov     r13d, [rsp+138h+var_F4]
0x14018b7cd  cmp     [rsp+138h+var_E4], 0
0x14018b7d2  jz      loc_14018B865
0x14018b7d8  mov     dword ptr [rsp+138h+var_E0], 0
0x14018b7e0  mov     [rsp+138h+var_118], rsi
0x14018b7e5  mov     r9, r12
0x14018b7e8  lea     r8, [rsp+138h+var_E0]
0x14018b7ed  mov     rdx, r12
0x14018b7f0  mov     r15, [rsp+138h+var_58]
0x14018b7f8  mov     rcx, r15
0x14018b7fb  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14018b802  nop     dword ptr [rax+rax+00h]
0x14018b807  lea     rcx, [r15+4]
0x14018b80b  mov     [rsp+138h+var_118], rsi
0x14018b810  mov     r9, r12
0x14018b813  lea     r8, [rsp+138h+var_108]
0x14018b818  mov     rdx, r12
0x14018b81b  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14018b822  nop     dword ptr [rax+rax+00h]
0x14018b827  mov     r12, [rsp+138h+var_D8]
0x14018b82c  jmp     short loc_14018B86A
0x14018b82e  mov     ecx, 57h ; 'W'; iError
0x14018b833  call    cs:__imp_EngSetLastError
0x14018b83a  nop     dword ptr [rax+rax+00h]
0x14018b83f  xor     ebx, ebx
0x14018b841  lea     esi, [rbx+1]
0x14018b844  mov     rax, [rsp+138h+var_98]
0x14018b84c  mov     [rsp+138h+var_D0], rax
0x14018b851  mov     r14d, [rsp+138h+var_100]
0x14018b856  mov     r12, [rsp+138h+var_90]
0x14018b85e  mov     r13d, [rsp+138h+var_F4]
0x14018b863  jmp     short loc_14018B86A
0x14018b865  mov     r12, [rsp+138h+var_D8]
0x14018b86a  lea     rcx, [rsp+138h+var_C8]
0x14018b86f  call    cs:__imp_?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x14018b876  nop     dword ptr [rax+rax+00h]
0x14018b87b  test    al, al
0x14018b87d  jz      loc_14018B990
0x14018b883  test    ebx, ebx
0x14018b885  jz      loc_14018B990
0x14018b88b  xor     r9d, r9d
0x14018b88e  lea     r8d, [r9+5]
0x14018b892  mov     rdx, [rsp+138h+var_F0]
0x14018b897  lea     rcx, [rsp+138h+var_C8]
0x14018b89c  call    ?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_K@Z; Gre::MapViewOfSectionObj::Map(void *,Gre::MapViewOfSectionObj::MapKind,unsigned __int64)
0x14018b8a1  test    al, al
0x14018b8a3  jz      loc_14018B990
0x14018b8a9  mov     rbx, [rsp+138h+var_B8]
0x14018b8b1  mov     r15, [rsp+138h+var_68]
0x14018b8b9  mov     [r15+68h], rbx
0x14018b8bd  mov     eax, r13d
0x14018b8c0  add     rax, rbx
0x14018b8c3  mov     [r12+10h], rax
0x14018b8c8  lea     eax, [r14+10h]
0x14018b8cc  cmp     [rsp+138h+arg_18], 2
0x14018b8d4  cmovnz  eax, r14d
0x14018b8d8  sub     eax, r13d
0x14018b8db  mov     [r12+18h], eax
0x14018b8e0  mov     [r12+1Ch], r13d
0x14018b8e5  mov     rax, [rsp+138h+var_B0]
0x14018b8ed  mov     [r15+58h], rax
0x14018b8f1  mov     dword ptr [r15+60h], 0
0x14018b8f9  mov     [r15+64h], esi
0x14018b8fd  mov     rax, [rsp+138h+var_F0]
0x14018b902  mov     [rsp+138h+var_F0], 0
0x14018b90b  mov     [r12+20h], rax
0x14018b910  call    cs:__imp_PsGetCurrentProcessId
0x14018b917  nop     dword ptr [rax+rax+00h]
0x14018b91c  and     eax, 0FFFFFFFCh
0x14018b91f  mov     [r15+70h], eax
0x14018b923  mov     rax, [rsp+138h+var_C8]
0x14018b928  mov     [r12+48h], rax
0x14018b92d  mov     rax, [rsp+138h+var_D0]
0x14018b932  mov     [rax], rbx
0x14018b935  mov     [rsp+138h+var_B8], 0
0x14018b941  mov     [rsp+138h+var_C8], 0
0x14018b94a  mov     [rsp+138h+var_C0], 0
0x14018b953  mov     [rsp+138h+var_B0], 0
0x14018b95f  mov     [rsp+138h+var_A8], 6
0x14018b96a  mov     ebx, [rsp+138h+var_108]
0x14018b96e  lea     rcx, [rsp+138h+var_C8]; this
0x14018b973  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x14018b978  lea     rcx, [rsp+138h+var_F0]
0x14018b97d  call    cs:__imp_??1SectionObj@Gre@@QEAA@XZ; Gre::SectionObj::~SectionObj(void)
0x14018b984  nop     dword ptr [rax+rax+00h]
0x14018b989  mov     eax, ebx
0x14018b98b  jmp     loc_14018B69B
0x14018b990  lea     rcx, [rsp+138h+var_C8]; this
0x14018b995  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x14018b99a  jmp     loc_14018B688
```
